# MountMgrDeletePoints

- ea: `0x140018560`
- end: `0x14001887e`
- name: `MountMgrDeletePoints`
- size: `798`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config`

## callers

- `0x1400147a0`

## callees

- `0x1400019c0`
- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x14000adf0`
- `0x14000b588`
- `0x1400168b0`
- `0x140018560`
- `0x140018cd0`
- `0x140019ca0`
- `0x140019e30`
- `0x14001a3d0`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400187a7`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400187a7`
- `ntoskrnl!ExAllocatePool2` at `0x140018667`
- `ntoskrnl!ExAllocatePool2` at `0x1400186d0`
- `ntoskrnl!ExAllocatePool2` at `0x140018735`
- `ntoskrnl!ExAllocatePool2` at `0x140018667`
- `ntoskrnl!ExAllocatePool2` at `0x1400186d0`
- `ntoskrnl!ExAllocatePool2` at `0x140018735`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001870c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018771`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400187ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001870c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018771`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400187ba`

## string_xrefs

- `0x14001879c`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrDeletePoints(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rax
  bool v8; // r14
  unsigned int Points; // esi
  __int64 v10; // r8
  __int64 v11; // rbx
  __int64 i; // rdi
  __int64 v13; // r15
  WCHAR *Pool2; // rax
  _WORD *v15; // rax
  void *v16; // rsi
  unsigned int v17; // ecx
  _WORD *v18; // rax
  void *v19; // rsi
  unsigned int v20; // ecx
  __int64 v21; // r8
  PCWSTR ValueName[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v23; // [rsp+30h] [rbp-28h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  *(_OWORD *)ValueName = 0;
  v23 = 0;
  if ( *(_DWORD *)(v3 + 16) >= 0x18u )
  {
    v7 = *(_QWORD *)(a2 + 24);
    v8 = *(_DWORD *)v7 && *(_WORD *)(v7 + 4);
    Points = MountMgrQueryPoints(a1, a2);
    if ( (Points & 0x80000000) == 0 )
    {
      v11 = *(_QWORD *)(a2 + 24);
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= *(_DWORD *)(v11 + 4) )
        {
          MountMgrNotify(a1);
          return Points;
        }
        v13 = v11 + 24 * i;
        LOWORD(ValueName[0]) = *(_WORD *)(v13 + 12);
        WORD1(ValueName[0]) = LOWORD(ValueName[0]) + 2;
        Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)(LOWORD(ValueName[0]) + 2), 1098149453);
        ValueName[1] = Pool2;
        if ( !Pool2 )
          break;
        memmove(Pool2, (const void *)(v11 + *(unsigned int *)(v13 + 8)), LOWORD(ValueName[0]));
        ValueName[1][(unsigned __int64)LOWORD(ValueName[0]) >> 1] = 0;
        if ( v8 )
        {
          if ( (unsigned __int8)IsDriveLetter((PCUNICODE_STRING)ValueName) )
          {
            v15 = (_WORD *)ExAllocatePool2(258, *(unsigned __int16 *)(v13 + 20) + 4LL, 1098149453);
            v16 = v15;
            if ( v15 )
            {
              v17 = *(unsigned __int16 *)(v13 + 20);
              *v15 = v17;
              memmove(v15 + 1, (const void *)(v11 + *(unsigned int *)(v13 + 16)), v17);
              CreateNoDriveLetterEntry(v16);
              ExFreePoolWithTag(v16, 0);
            }
          }
        }
        if ( !(_DWORD)i && !v8 )
        {
          v18 = (_WORD *)ExAllocatePool2(258, *(unsigned __int16 *)(v13 + 20) + 4LL, 1098149453);
          v19 = v18;
          if ( v18 )
          {
            v20 = *(unsigned __int16 *)(v13 + 20);
            *v18 = v20;
            memmove(v18 + 1, (const void *)(v11 + *(unsigned int *)(v13 + 16)), v20);
            DeleteNoDriveLetterEntry(v19);
            ExFreePoolWithTag(v19, 0);
          }
        }
        GlobalDeleteSymbolicLink(ValueName);
        Points = DeleteSymbolicLinkNameFromMemory(a1, ValueName, 0);
        RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName[1]);
        ExFreePoolWithTag((PVOID)ValueName[1], 0);
        if ( (Points & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 228, v21, Points);
          }
          return Points;
        }
        LOWORD(v23) = *(_WORD *)(v13 + 28);
        LOBYTE(v21) = 1;
        WORD1(v23) = v23;
        *((_QWORD *)&v23 + 1) = v11 + *(unsigned int *)(v13 + 24);
        MountMgrNotifyNameChange(a1, &v23, v21);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 227);
      return 3221225626LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 226, v10, Points);
      return Points;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 225, a3, 3221225485LL);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140018560  push    rbx
0x140018562  push    rbp
0x140018563  sub     rsp, 48h
0x140018567  mov     rax, [rdx+0B8h]
0x14001856e  xorps   xmm0, xmm0
0x140018571  xorps   xmm1, xmm1
0x140018574  mov     rbx, rdx
0x140018577  movups  xmmword ptr [rsp+58h+ValueName], xmm0
0x14001857c  mov     rbp, rcx
0x14001857f  movups  [rsp+58h+var_28], xmm1
0x140018584  cmp     dword ptr [rax+10h], 18h
0x140018588  jnb     short loc_1400185C5
0x14001858a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018591  lea     rax, WPP_GLOBAL_Control
0x140018598  cmp     rcx, rax
0x14001859b  jz      short loc_1400185B8
0x14001859d  mov     eax, [rcx+2Ch]
0x1400185a0  test    al, 1
0x1400185a2  jz      short loc_1400185B8
0x1400185a4  mov     rcx, [rcx+18h]
0x1400185a8  mov     edx, 0E1h
0x1400185ad  mov     r9d, 0C000000Dh
0x1400185b3  call    WPP_SF_L
0x1400185b8  mov     eax, 0C000000Dh
0x1400185bd  add     rsp, 48h
0x1400185c1  pop     rbp
0x1400185c2  pop     rbx
0x1400185c3  retn
0x1400185c5  mov     rax, [rdx+18h]
0x1400185c9  mov     [rsp+58h+arg_0], rsi
0x1400185ce  mov     [rsp+58h+arg_10], r14
0x1400185d3  cmp     dword ptr [rax], 0
0x1400185d6  jz      short loc_1400185E4
0x1400185d8  cmp     word ptr [rax+4], 0
0x1400185dd  jz      short loc_1400185E4
0x1400185df  mov     r14b, 1
0x1400185e2  jmp     short loc_1400185E7
0x1400185e4  xor     r14b, r14b
0x1400185e7  call    MountMgrQueryPoints
0x1400185ec  mov     esi, eax
0x1400185ee  test    eax, eax
0x1400185f0  jns     short loc_140018625
0x1400185f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400185f9  lea     rax, WPP_GLOBAL_Control
0x140018600  cmp     rcx, rax
0x140018603  jz      short loc_14001861E
0x140018605  mov     edx, [rcx+2Ch]
0x140018608  test    dl, 1
0x14001860b  jz      short loc_14001861E
0x14001860d  mov     rcx, [rcx+18h]
0x140018611  mov     edx, 0E2h
0x140018616  mov     r9d, esi
0x140018619  call    WPP_SF_L
0x14001861e  mov     eax, esi
0x140018620  jmp     loc_14001886C
0x140018625  mov     rbx, [rbx+18h]
0x140018629  mov     [rsp+58h+arg_8], rdi
0x14001862e  xor     edi, edi
0x140018630  mov     [rsp+58h+var_18], r15
0x140018635  cmp     edi, [rbx+4]
0x140018638  jnb     loc_140018858
0x14001863e  lea     rcx, [rdi+rdi*2]
0x140018642  mov     r8d, 41746E4Dh
0x140018648  movzx   eax, word ptr [rbx+rcx*8+0Ch]
0x14001864d  lea     r15, [rbx+rcx*8]
0x140018651  mov     word ptr [rsp+58h+ValueName], ax
0x140018656  mov     ecx, 102h
0x14001865b  add     ax, 2
0x14001865f  movzx   edx, ax
0x140018662  mov     word ptr [rsp+58h+ValueName+2], dx
0x140018667  call    cs:__imp_ExAllocatePool2
0x14001866e  nop     dword ptr [rax+rax+00h]
0x140018673  mov     [rsp+58h+ValueName+8], rax
0x140018678  test    rax, rax
0x14001867b  jz      loc_140018829
0x140018681  mov     edx, [r15+8]
0x140018685  mov     rcx, rax; void *
0x140018688  movzx   r8d, word ptr [rsp+58h+ValueName]; Size
0x14001868e  add     rdx, rbx; Src
0x140018691  call    memmove
0x140018696  movzx   edx, word ptr [rsp+58h+ValueName]
0x14001869b  xor     ecx, ecx
0x14001869d  mov     rax, [rsp+58h+ValueName+8]
0x1400186a2  shr     rdx, 1
0x1400186a5  mov     [rax+rdx*2], cx
0x1400186a9  test    r14b, r14b
0x1400186ac  jz      short loc_140018718
0x1400186ae  lea     rcx, [rsp+58h+ValueName]; String2
0x1400186b3  call    IsDriveLetter
0x1400186b8  test    al, al
0x1400186ba  jz      short loc_140018718
0x1400186bc  movzx   edx, word ptr [r15+14h]
0x1400186c1  mov     ecx, 102h
0x1400186c6  add     rdx, 4
0x1400186ca  mov     r8d, 41746E4Dh
0x1400186d0  call    cs:__imp_ExAllocatePool2
0x1400186d7  nop     dword ptr [rax+rax+00h]
0x1400186dc  mov     rsi, rax
0x1400186df  test    rax, rax
0x1400186e2  jz      short loc_140018718
0x1400186e4  movzx   ecx, word ptr [r15+14h]
0x1400186e9  mov     [rax], cx
0x1400186ec  mov     r8d, ecx; Size
0x1400186ef  mov     edx, [r15+10h]
0x1400186f3  lea     rcx, [rax+2]; void *
0x1400186f7  add     rdx, rbx; Src
0x1400186fa  call    memmove
0x1400186ff  mov     rcx, rsi
0x140018702  call    CreateNoDriveLetterEntry
0x140018707  xor     edx, edx; Tag
0x140018709  mov     rcx, rsi; P
0x14001870c  call    cs:__imp_ExFreePoolWithTag
0x140018713  nop     dword ptr [rax+rax+00h]
0x140018718  test    edi, edi
0x14001871a  jnz     short loc_14001877D
0x14001871c  test    r14b, r14b
0x14001871f  jnz     short loc_14001877D
0x140018721  movzx   edx, word ptr [r15+14h]
0x140018726  mov     ecx, 102h
0x14001872b  add     rdx, 4
0x14001872f  mov     r8d, 41746E4Dh
0x140018735  call    cs:__imp_ExAllocatePool2
0x14001873c  nop     dword ptr [rax+rax+00h]
0x140018741  mov     rsi, rax
0x140018744  test    rax, rax
0x140018747  jz      short loc_14001877D
0x140018749  movzx   ecx, word ptr [r15+14h]
0x14001874e  mov     [rax], cx
0x140018751  mov     r8d, ecx; Size
0x140018754  mov     edx, [r15+10h]
0x140018758  lea     rcx, [rax+2]; void *
0x14001875c  add     rdx, rbx; Src
0x14001875f  call    memmove
0x140018764  mov     rcx, rsi
0x140018767  call    DeleteNoDriveLetterEntry
0x14001876c  xor     edx, edx; Tag
0x14001876e  mov     rcx, rsi; P
0x140018771  call    cs:__imp_ExFreePoolWithTag
0x140018778  nop     dword ptr [rax+rax+00h]
0x14001877d  lea     rcx, [rsp+58h+ValueName]
0x140018782  call    GlobalDeleteSymbolicLink
0x140018787  xor     r8d, r8d
0x14001878a  lea     rdx, [rsp+58h+ValueName]
0x14001878f  mov     rcx, rbp
0x140018792  call    DeleteSymbolicLinkNameFromMemory
0x140018797  mov     r8, [rsp+58h+ValueName+8]; ValueName
0x14001879c  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x1400187a3  xor     ecx, ecx; RelativeTo
0x1400187a5  mov     esi, eax
0x1400187a7  call    cs:__imp_RtlDeleteRegistryValue
0x1400187ae  nop     dword ptr [rax+rax+00h]
0x1400187b3  mov     rcx, [rsp+58h+ValueName+8]; P
0x1400187b8  xor     edx, edx; Tag
0x1400187ba  call    cs:__imp_ExFreePoolWithTag
0x1400187c1  nop     dword ptr [rax+rax+00h]
0x1400187c6  test    esi, esi
0x1400187c8  js      short loc_1400187FC
0x1400187ca  movzx   eax, word ptr [r15+1Ch]
0x1400187cf  lea     rdx, [rsp+58h+var_28]
0x1400187d4  mov     word ptr [rsp+58h+var_28], ax
0x1400187d9  mov     r8b, 1
0x1400187dc  mov     word ptr [rsp+58h+var_28+2], ax
0x1400187e1  mov     rcx, rbp
0x1400187e4  mov     eax, [r15+18h]
0x1400187e8  add     rax, rbx
0x1400187eb  mov     qword ptr [rsp+58h+var_28+8], rax
0x1400187f0  call    MountMgrNotifyNameChange
0x1400187f5  inc     edi
0x1400187f7  jmp     loc_140018635
0x1400187fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140018803  lea     rax, WPP_GLOBAL_Control
0x14001880a  cmp     rcx, rax
0x14001880d  jz      short loc_140018860
0x14001880f  mov     eax, [rcx+2Ch]
0x140018812  test    al, 1
0x140018814  jz      short loc_140018860
0x140018816  mov     rcx, [rcx+18h]
0x14001881a  mov     edx, 0E4h
0x14001881f  mov     r9d, esi
0x140018822  call    WPP_SF_L
0x140018827  jmp     short loc_140018860
0x140018829  mov     rcx, cs:WPP_GLOBAL_Control
0x140018830  lea     rax, WPP_GLOBAL_Control
0x140018837  cmp     rcx, rax
0x14001883a  jz      short loc_140018851
0x14001883c  mov     eax, [rcx+2Ch]
0x14001883f  test    al, 4
0x140018841  jz      short loc_140018851
0x140018843  mov     rcx, [rcx+18h]
0x140018847  mov     edx, 0E3h
0x14001884c  call    WPP_SF_
0x140018851  mov     eax, 0C000009Ah
0x140018856  jmp     short loc_140018862
0x140018858  mov     rcx, rbp
0x14001885b  call    MountMgrNotify
0x140018860  mov     eax, esi
0x140018862  mov     r15, [rsp+58h+var_18]
0x140018867  mov     rdi, [rsp+58h+arg_8]
0x14001886c  mov     rsi, [rsp+58h+arg_0]
0x140018871  mov     r14, [rsp+58h+arg_10]
0x140018876  add     rsp, 48h
0x14001887a  pop     rbp
0x14001887b  pop     rbx
0x14001887c  retn
```
