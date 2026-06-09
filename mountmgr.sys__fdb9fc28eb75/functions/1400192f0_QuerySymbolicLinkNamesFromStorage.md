# QuerySymbolicLinkNamesFromStorage

- ea: `0x1400192f0`
- end: `0x1400195c0`
- name: `QuerySymbolicLinkNamesFromStorage`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x140014fc0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140003280`
- `0x1400192f0`
- `0x1400195d0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001937d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400194c7`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001937d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400194c7`
- `ntoskrnl!ExAllocatePool2` at `0x140019407`
- `ntoskrnl!ExAllocatePool2` at `0x140019407`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001956d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001958b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001956d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001958b`

## string_xrefs

- `0x140019363`: `\Registry\Machine\System\MountedDevices`
- `0x1400194b0`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall QuerySymbolicLinkNamesFromStorage(__int64 a1, _QWORD *a2, struct _UNICODE_STRING **a3, _DWORD *a4)
{
  bool v4; // bl
  __int64 v5; // rax
  bool v9; // bp
  __int64 v10; // r9
  int RegistryValues; // eax
  __int64 v12; // r8
  int NewVolumeName; // r14d
  unsigned int v14; // eax
  struct _UNICODE_STRING *Pool2; // rdi
  __int64 v17; // r9
  __int64 v18; // r8
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // edx
  unsigned int i; // ebx
  PWSTR Buffer; // rcx
  _QWORD v24[23]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+F0h] [rbp+8h] BYREF

  v25 = a1;
  v4 = 0;
  v5 = a2[13] - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v5 )
    v5 = a2[14] - *(_QWORD *)GUID_NULL.Data4;
  v9 = v5 != 0;
  memset(v24, 0, 0x70u);
  v10 = a2[12];
  v24[0] = SymbolicLinkNamesFromUniqueIdCount;
  v24[3] = &v25;
  LODWORD(v25) = 0;
  RegistryValues = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v24, v10, 0);
  NewVolumeName = RegistryValues;
  if ( RegistryValues >= 0 )
  {
    v14 = v25;
    v4 = (_DWORD)v25 != 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 24, v12, (unsigned int)RegistryValues);
    }
    v14 = 0;
    LODWORD(v25) = 0;
  }
  if ( v9 )
  {
    LODWORD(v25) = ++v14;
    goto LABEL_12;
  }
  if ( v14 )
  {
LABEL_12:
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 16LL * v14, 1098149453);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26);
      return 3221225626LL;
    }
    if ( v4
      && (memset(v24, 0, 0x70u),
          v17 = a2[12],
          v24[0] = SymbolicLinkNamesFromUniqueIdQuery,
          v24[3] = Pool2,
          NewVolumeName = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v24, v17, 0),
          NewVolumeName < 0) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_34;
      v20 = 27;
    }
    else
    {
      if ( !v9 || (NewVolumeName = CreateNewVolumeName(&Pool2[(unsigned int)(v25 - 1)]), NewVolumeName >= 0) )
      {
        *a4 = v25;
        *a3 = Pool2;
        return (unsigned int)NewVolumeName;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_34:
        v21 = v25;
        for ( i = 0; i < v21; ++i )
        {
          Buffer = Pool2[i].Buffer;
          if ( Buffer )
          {
            ExFreePoolWithTag(Buffer, 0);
            v21 = v25;
          }
        }
        ExFreePoolWithTag(Pool2, 0);
        return (unsigned int)NewVolumeName;
      }
      v20 = 28;
    }
    WPP_SF_L(v19->AttachedDevice, v20, v18, (unsigned int)NewVolumeName);
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 25, v12, (unsigned int)NewVolumeName);
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x1400192f0  mov     [rsp+arg_0], rcx
0x1400192f5  push    rbx
0x1400192f6  push    rbp
0x1400192f7  push    rsi
0x1400192f8  push    rdi
0x1400192f9  push    r12
0x1400192fb  push    r13
0x1400192fd  push    r14
0x1400192ff  push    r15
0x140019301  sub     rsp, 0A8h
0x140019308  mov     rax, [rdx+68h]
0x14001930c  xor     bl, bl
0x14001930e  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140019315  mov     r12, r9
0x140019318  mov     r13, r8
0x14001931b  mov     r15, rdx
0x14001931e  jnz     short loc_14001932B
0x140019320  mov     rax, [rdx+70h]
0x140019324  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14001932b  test    rax, rax
0x14001932e  lea     rcx, [rsp+0E8h+var_B8]; void *
0x140019333  mov     r8d, 70h ; 'p'; Size
0x140019339  setnz   bpl
0x14001933d  xor     edx, edx; Val
0x14001933f  call    memset
0x140019344  mov     r9, [r15+60h]
0x140019348  lea     rax, SymbolicLinkNamesFromUniqueIdCount
0x14001934f  mov     [rsp+0E8h+var_B8], rax
0x140019354  lea     r8, [rsp+0E8h+var_B8]
0x140019359  lea     rax, [rsp+0E8h+arg_0]
0x140019361  xor     edi, edi
0x140019363  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14001936a  mov     [rsp+0E8h+var_A0], rax
0x14001936f  xor     ecx, ecx
0x140019371  mov     dword ptr [rsp+0E8h+arg_0], edi
0x140019378  mov     [rsp+0E8h+var_C8], rdi
0x14001937d  call    cs:__imp_RtlQueryRegistryValuesEx
0x140019384  nop     dword ptr [rax+rax+00h]
0x140019389  lea     rdx, WPP_GLOBAL_Control
0x140019390  mov     r14d, eax
0x140019393  test    eax, eax
0x140019395  jns     short loc_1400193D4
0x140019397  mov     rcx, cs:WPP_GLOBAL_Control
0x14001939e  cmp     rcx, rdx
0x1400193a1  jz      short loc_1400193C9
0x1400193a3  mov     edx, [rcx+2Ch]
0x1400193a6  test    dl, 1
0x1400193a9  jz      short loc_1400193C2
0x1400193ab  cmp     byte ptr [rcx+29h], 1
0x1400193af  jb      short loc_1400193C2
0x1400193b1  mov     rcx, [rcx+18h]
0x1400193b5  mov     edx, 18h
0x1400193ba  mov     r9d, eax
0x1400193bd  call    WPP_SF_L
0x1400193c2  lea     rdx, WPP_GLOBAL_Control
0x1400193c9  mov     eax, edi
0x1400193cb  mov     dword ptr [rsp+0E8h+arg_0], eax
0x1400193d2  jmp     short loc_1400193E8
0x1400193d4  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x1400193db  mov     ecx, 1
0x1400193e0  test    eax, eax
0x1400193e2  movzx   ebx, bl
0x1400193e5  cmovnz  ebx, ecx
0x1400193e8  test    bpl, bpl
0x1400193eb  jz      short loc_14001944D
0x1400193ed  inc     eax
0x1400193ef  mov     dword ptr [rsp+0E8h+arg_0], eax
0x1400193f6  mov     edx, eax
0x1400193f8  mov     ecx, 100h
0x1400193fd  shl     rdx, 4
0x140019401  mov     r8d, 41746E4Dh
0x140019407  call    cs:__imp_ExAllocatePool2
0x14001940e  nop     dword ptr [rax+rax+00h]
0x140019413  mov     rdi, rax
0x140019416  test    rax, rax
0x140019419  jnz     short loc_140019485
0x14001941b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019422  lea     rax, WPP_GLOBAL_Control
0x140019429  cmp     rcx, rax
0x14001942c  jz      short loc_140019443
0x14001942e  mov     eax, [rcx+2Ch]
0x140019431  test    al, 4
0x140019433  jz      short loc_140019443
0x140019435  mov     rcx, [rcx+18h]
0x140019439  mov     edx, 1Ah
0x14001943e  call    WPP_SF_
0x140019443  mov     eax, 0C000009Ah
0x140019448  jmp     loc_1400195AB
0x14001944d  test    eax, eax
0x14001944f  jnz     short loc_1400193F6
0x140019451  mov     rcx, cs:WPP_GLOBAL_Control
0x140019458  cmp     rcx, rdx
0x14001945b  jz      short loc_14001947B
0x14001945d  mov     eax, [rcx+2Ch]
0x140019460  test    al, 1
0x140019462  jz      short loc_14001947B
0x140019464  cmp     byte ptr [rcx+29h], 1
0x140019468  jb      short loc_14001947B
0x14001946a  mov     rcx, [rcx+18h]
0x14001946e  mov     edx, 19h
0x140019473  mov     r9d, r14d
0x140019476  call    WPP_SF_L
0x14001947b  mov     eax, 0C0000225h
0x140019480  jmp     loc_1400195AB
0x140019485  test    bl, bl
0x140019487  jz      short loc_1400194FB
0x140019489  xor     edx, edx; Val
0x14001948b  lea     rcx, [rsp+0E8h+var_B8]; void *
0x140019490  mov     r8d, 70h ; 'p'; Size
0x140019496  call    memset
0x14001949b  mov     r9, [r15+60h]
0x14001949f  lea     rax, SymbolicLinkNamesFromUniqueIdQuery
0x1400194a6  lea     r8, [rsp+0E8h+var_B8]
0x1400194ab  mov     [rsp+0E8h+var_B8], rax
0x1400194b0  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x1400194b7  mov     [rsp+0E8h+var_A0], rdi
0x1400194bc  xor     ecx, ecx
0x1400194be  mov     [rsp+0E8h+var_C8], 0
0x1400194c7  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400194ce  nop     dword ptr [rax+rax+00h]
0x1400194d3  mov     r14d, eax
0x1400194d6  test    eax, eax
0x1400194d8  jns     short loc_1400194FB
0x1400194da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400194e1  lea     rax, WPP_GLOBAL_Control
0x1400194e8  cmp     rcx, rax
0x1400194eb  jz      short loc_14001954F
0x1400194ed  mov     eax, [rcx+2Ch]
0x1400194f0  test    al, 1
0x1400194f2  jz      short loc_14001954F
0x1400194f4  mov     edx, 1Bh
0x1400194f9  jmp     short loc_140019543
0x1400194fb  test    bpl, bpl
0x1400194fe  jz      loc_140019599
0x140019504  mov     ecx, dword ptr [rsp+0E8h+arg_0]
0x14001950b  lea     rdx, [r15+68h]
0x14001950f  dec     ecx
0x140019511  shl     rcx, 4
0x140019515  add     rcx, rdi; Destination
0x140019518  call    CreateNewVolumeName
0x14001951d  mov     r14d, eax
0x140019520  test    eax, eax
0x140019522  jns     short loc_140019599
0x140019524  mov     rcx, cs:WPP_GLOBAL_Control
0x14001952b  lea     rax, WPP_GLOBAL_Control
0x140019532  cmp     rcx, rax
0x140019535  jz      short loc_14001954F
0x140019537  mov     eax, [rcx+2Ch]
0x14001953a  test    al, 1
0x14001953c  jz      short loc_14001954F
0x14001953e  mov     edx, 1Ch
0x140019543  mov     rcx, [rcx+18h]
0x140019547  mov     r9d, r14d
0x14001954a  call    WPP_SF_L
0x14001954f  mov     edx, dword ptr [rsp+0E8h+arg_0]
0x140019556  xor     ebx, ebx
0x140019558  test    edx, edx
0x14001955a  jz      short loc_140019586
0x14001955c  mov     eax, ebx
0x14001955e  add     rax, rax
0x140019561  mov     rcx, [rdi+rax*8+8]; P
0x140019566  test    rcx, rcx
0x140019569  jz      short loc_140019580
0x14001956b  xor     edx, edx; Tag
0x14001956d  call    cs:__imp_ExFreePoolWithTag
0x140019574  nop     dword ptr [rax+rax+00h]
0x140019579  mov     edx, dword ptr [rsp+0E8h+arg_0]
0x140019580  inc     ebx
0x140019582  cmp     ebx, edx
0x140019584  jb      short loc_14001955C
0x140019586  xor     edx, edx; Tag
0x140019588  mov     rcx, rdi; P
0x14001958b  call    cs:__imp_ExFreePoolWithTag
0x140019592  nop     dword ptr [rax+rax+00h]
0x140019597  jmp     short loc_1400195A8
0x140019599  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x1400195a0  mov     [r12], eax
0x1400195a4  mov     [r13+0], rdi
0x1400195a8  mov     eax, r14d
0x1400195ab  add     rsp, 0A8h
0x1400195b2  pop     r15
0x1400195b4  pop     r14
0x1400195b6  pop     r13
0x1400195b8  pop     r12
0x1400195ba  pop     rdi
0x1400195bb  pop     rsi
0x1400195bc  pop     rbp
0x1400195bd  pop     rbx
0x1400195be  retn
```
