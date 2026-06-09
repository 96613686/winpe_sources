# QueryUniqueIdFromMaster

- ea: `0x140010800`
- end: `0x140010963`
- name: `QueryUniqueIdFromMaster`
- size: `355`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140003280`
- `0x140010800`
- `0x140010970`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140010866`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140010866`
- `ntoskrnl!ExAllocatePool2` at `0x1400108ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400108ec`

## string_xrefs

- `0x140010852`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall QueryUniqueIdFromMaster(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r8
  int DeviceInfo; // ebx
  __int64 v8; // r8
  __int64 v10; // rbx
  _WORD *Pool2; // rax
  _QWORD v12[19]; // [rsp+30h] [rbp-98h] BYREF
  __int64 v13; // [rsp+D8h] [rbp+10h] BYREF

  v12[1] = 0;
  v13 = 0;
  memset(&v12[3], 0, 0x58u);
  v12[0] = &QueryUniqueIdQueryRoutine;
  v12[2] = *(_QWORD *)(a2 + 8);
  *(_QWORD *)a3 = 0;
  RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v12, a3, 0);
  if ( *(_QWORD *)a3 )
    return 0;
  DeviceInfo = FindDeviceInfo(a1, a2, v6, &v13);
  if ( DeviceInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 100, v8, (unsigned int)DeviceInfo);
    return (unsigned int)DeviceInfo;
  }
  v10 = v13;
  Pool2 = (_WORD *)ExAllocatePool2(258, **(unsigned __int16 **)(v13 + 96) + 4LL, 1098149453);
  *(_QWORD *)a3 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = **(_WORD **)(v10 + 96);
    memmove(
      (void *)(*(_QWORD *)a3 + 2LL),
      (const void *)(*(_QWORD *)(v10 + 96) + 2LL),
      **(unsigned __int16 **)(v10 + 96));
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140010800  push    rbx
0x140010802  push    rbp
0x140010803  push    rsi
0x140010804  push    rdi
0x140010805  sub     rsp, 0A8h
0x14001080c  mov     rsi, r8
0x14001080f  mov     rbx, rdx
0x140010812  mov     rdi, rcx
0x140010815  xor     eax, eax
0x140010817  xor     ebp, ebp
0x140010819  mov     [rsp+0C8h+var_90], rax
0x14001081e  xor     edx, edx; Val
0x140010820  mov     [rsp+0C8h+arg_8], rbp
0x140010828  mov     r8d, 58h ; 'X'; Size
0x14001082e  lea     rcx, [rsp+0C8h+var_80]; void *
0x140010833  call    memset
0x140010838  lea     rax, QueryUniqueIdQueryRoutine
0x14001083f  mov     [rsp+0C8h+var_A8], rbp
0x140010844  mov     [rsp+0C8h+var_98], rax
0x140010849  lea     r8, [rsp+0C8h+var_98]
0x14001084e  mov     rax, [rbx+8]
0x140010852  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x140010859  mov     r9, rsi
0x14001085c  mov     [rsp+0C8h+var_88], rax
0x140010861  xor     ecx, ecx
0x140010863  mov     [rsi], rbp
0x140010866  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001086d  nop     dword ptr [rax+rax+00h]
0x140010872  cmp     [rsi], rbp
0x140010875  jnz     loc_140010954
0x14001087b  lea     r9, [rsp+0C8h+arg_8]
0x140010883  mov     rdx, rbx
0x140010886  mov     rcx, rdi
0x140010889  call    FindDeviceInfo
0x14001088e  mov     ebx, eax
0x140010890  test    eax, eax
0x140010892  jns     short loc_1400108CE
0x140010894  mov     rcx, cs:WPP_GLOBAL_Control
0x14001089b  lea     rax, WPP_GLOBAL_Control
0x1400108a2  cmp     rcx, rax
0x1400108a5  jz      short loc_1400108BF
0x1400108a7  mov     eax, [rcx+2Ch]
0x1400108aa  test    al, 1
0x1400108ac  jz      short loc_1400108BF
0x1400108ae  mov     rcx, [rcx+18h]
0x1400108b2  mov     edx, 64h ; 'd'
0x1400108b7  mov     r9d, ebx
0x1400108ba  call    WPP_SF_L
0x1400108bf  mov     eax, ebx
0x1400108c1  add     rsp, 0A8h
0x1400108c8  pop     rdi
0x1400108c9  pop     rsi
0x1400108ca  pop     rbp
0x1400108cb  pop     rbx
0x1400108cc  retn
0x1400108ce  mov     rbx, [rsp+0C8h+arg_8]
0x1400108d6  mov     ecx, 102h
0x1400108db  mov     r8d, 41746E4Dh
0x1400108e1  mov     rax, [rbx+60h]
0x1400108e5  movzx   edx, word ptr [rax]
0x1400108e8  add     rdx, 4
0x1400108ec  call    cs:__imp_ExAllocatePool2
0x1400108f3  nop     dword ptr [rax+rax+00h]
0x1400108f8  mov     [rsi], rax
0x1400108fb  mov     rdx, rax
0x1400108fe  test    rax, rax
0x140010901  jnz     short loc_140010932
0x140010903  mov     rcx, cs:WPP_GLOBAL_Control
0x14001090a  lea     rax, WPP_GLOBAL_Control
0x140010911  cmp     rcx, rax
0x140010914  jz      short loc_14001092B
0x140010916  mov     eax, [rcx+2Ch]
0x140010919  test    al, 4
0x14001091b  jz      short loc_14001092B
0x14001091d  mov     rcx, [rcx+18h]
0x140010921  mov     edx, 65h ; 'e'
0x140010926  call    WPP_SF_
0x14001092b  mov     eax, 0C000009Ah
0x140010930  jmp     short loc_140010956
0x140010932  mov     rax, [rbx+60h]
0x140010936  movzx   ecx, word ptr [rax]
0x140010939  mov     [rdx], cx
0x14001093c  mov     rdx, [rbx+60h]
0x140010940  mov     rcx, [rsi]
0x140010943  add     rcx, 2; void *
0x140010947  movzx   r8d, word ptr [rdx]; Size
0x14001094b  add     rdx, 2; Src
0x14001094f  call    memmove
0x140010954  xor     eax, eax
0x140010956  add     rsp, 0A8h
0x14001095d  pop     rdi
0x14001095e  pop     rsi
0x14001095f  pop     rbp
0x140010960  pop     rbx
0x140010961  retn
```
