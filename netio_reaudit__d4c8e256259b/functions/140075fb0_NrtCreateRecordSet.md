# NrtCreateRecordSet

- ea: `0x140075fb0`
- end: `0x1400761ca`
- name: `NrtCreateRecordSet`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140076ba0`

## callees

- `0x140050ea4`
- `0x140075bb4`
- `0x140075fb0`
- `0x1400761d0`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!RtlCreateHashTableEx` at `0x140076011`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140076037`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140076011`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140076037`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x140076161`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x140076161`
- `ntoskrnl!ExAllocatePool2` at `0x140075fe5`
- `ntoskrnl!ExAllocatePool2` at `0x140075fe5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007609d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007609d`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400760df`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400760df`

## pseudocode

```c
__int64 NrtCreateRecordSet()
{
  KSPIN_LOCK *Pool2; // rax
  unsigned int v1; // ebx
  PKSPIN_LOCK v2; // rbx
  __int64 v3; // rcx
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  __int64 v11; // [rsp+30h] [rbp-18h] BYREF

  v11 = WNF_CONT_RESTORE_FROM_SNAPSHOT_COMPLETE;
  Pool2 = (KSPIN_LOCK *)ExAllocatePool2(64, 384, 1920234062);
  NrtRecordSet = Pool2;
  if ( Pool2
    && (unsigned __int8)RtlCreateHashTableEx(Pool2 + 40, 128, 0, 0)
    && (unsigned __int8)RtlCreateHashTableEx(NrtRecordSet + 41, 128, 0, 0) )
  {
    v2 = NrtRecordSet;
    KeInitializeSpinLock(NrtRecordSet);
    v3 = 0;
    *((_DWORD *)v2 + 2) = 3;
    do
      LODWORD(v2[8 * ++v3]) = 0;
    while ( v3 != 4 );
    v4 = BCryptOpenAlgorithmProvider(&NrtRngHandle, L"RNG", 0, 1u);
    v8 = (unsigned int)v4;
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids,
          (unsigned int)v4);
      }
      NrtRngHandle = 0;
    }
    NrtCheckHvsiContainer(v6, v5, v7, v8);
    v9 = ExSubscribeWnfStateChange(&NrtContainerRestoreWnfSubscription, &v11, 1);
    v1 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids,
          (unsigned int)v9);
      }
      v1 = 0;
      NrtContainerRestoreWnfSubscription = 0;
    }
  }
  else
  {
    v1 = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids, 3221225495LL);
    }
    NrtDestroyRecordSet();
  }
  return v1;
}

```

## disassembly

```asm
0x140075fb0  mov     [rsp+arg_0], rbx
0x140075fb5  push    rsi
0x140075fb6  sub     rsp, 40h
0x140075fba  mov     rax, cs:__security_cookie
0x140075fc1  xor     rax, rsp
0x140075fc4  mov     [rsp+48h+var_10], rax
0x140075fc9  mov     rax, cs:WNF_CONT_RESTORE_FROM_SNAPSHOT_COMPLETE
0x140075fd0  mov     edx, 180h
0x140075fd5  mov     ecx, 40h ; '@'
0x140075fda  mov     [rsp+48h+var_18], rax
0x140075fdf  mov     r8d, 7274724Eh
0x140075fe5  call    cs:__imp_ExAllocatePool2
0x140075fec  nop     dword ptr [rax+rax+00h]
0x140075ff1  mov     cs:NrtRecordSet, rax
0x140075ff8  test    rax, rax
0x140075ffb  jz      short loc_140076047
0x140075ffd  mov     ebx, 80h
0x140076002  lea     rcx, [rax+140h]
0x140076009  mov     edx, ebx
0x14007600b  xor     r9d, r9d
0x14007600e  xor     r8d, r8d
0x140076011  call    cs:__imp_RtlCreateHashTableEx
0x140076018  nop     dword ptr [rax+rax+00h]
0x14007601d  test    al, al
0x14007601f  jz      short loc_140076047
0x140076021  mov     rcx, cs:NrtRecordSet
0x140076028  xor     r9d, r9d
0x14007602b  add     rcx, 148h
0x140076032  xor     r8d, r8d
0x140076035  mov     edx, ebx
0x140076037  call    cs:__imp_RtlCreateHashTableEx
0x14007603e  nop     dword ptr [rax+rax+00h]
0x140076043  test    al, al
0x140076045  jnz     short loc_140076093
0x140076047  mov     ebx, 0C0000017h
0x14007604c  mov     rcx, cs:WPP_GLOBAL_Control
0x140076053  lea     rsi, WPP_GLOBAL_Control
0x14007605a  cmp     rcx, rsi
0x14007605d  jz      short loc_140076089
0x14007605f  cmp     byte ptr [rcx+29h], 2
0x140076063  jb      short loc_140076089
0x140076065  test    dword ptr [rcx+2Ch], 100000h
0x14007606c  jz      short loc_140076089
0x14007606e  mov     rcx, [rcx+18h]
0x140076072  lea     r8, WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids
0x140076079  mov     edx, 17h
0x14007607e  mov     r9d, 0C0000017h
0x140076084  call    WPP_SF_d
0x140076089  call    NrtDestroyRecordSet
0x14007608e  jmp     loc_1400761AF
0x140076093  mov     rbx, cs:NrtRecordSet
0x14007609a  mov     rcx, rbx; SpinLock
0x14007609d  call    cs:__imp_KeInitializeSpinLock
0x1400760a4  nop     dword ptr [rax+rax+00h]
0x1400760a9  xor     ecx, ecx
0x1400760ab  mov     dword ptr [rbx+8], 3
0x1400760b2  lea     rax, [rcx+1]
0x1400760b6  inc     rcx
0x1400760b9  shl     rax, 6
0x1400760bd  mov     dword ptr [rax+rbx], 0
0x1400760c4  cmp     rcx, 4
0x1400760c8  jnz     short loc_1400760B2
0x1400760ca  lea     r9d, [rcx-3]; dwFlags
0x1400760ce  xor     r8d, r8d; pszImplementation
0x1400760d1  lea     rcx, NrtRngHandle; phAlgorithm
0x1400760d8  lea     rdx, pszAlgId; "RNG"
0x1400760df  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400760e6  nop     dword ptr [rax+rax+00h]
0x1400760eb  lea     rsi, WPP_GLOBAL_Control
0x1400760f2  mov     r9d, eax
0x1400760f5  test    eax, eax
0x1400760f7  jns     short loc_140076134
0x1400760f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140076100  cmp     rcx, rsi
0x140076103  jz      short loc_140076129
0x140076105  cmp     byte ptr [rcx+29h], 2
0x140076109  jb      short loc_140076129
0x14007610b  test    dword ptr [rcx+2Ch], 100000h
0x140076112  jz      short loc_140076129
0x140076114  mov     rcx, [rcx+18h]
0x140076118  lea     r8, WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids
0x14007611f  mov     edx, 15h
0x140076124  call    WPP_SF_d
0x140076129  mov     cs:NrtRngHandle, 0
0x140076134  call    NrtCheckHvsiContainer
0x140076139  xor     r9d, r9d
0x14007613c  mov     [rsp+48h+var_20], 0
0x140076145  lea     rax, NrtOnContainerRestore
0x14007614c  lea     rdx, [rsp+48h+var_18]
0x140076151  mov     [rsp+48h+var_28], rax
0x140076156  lea     rcx, NrtContainerRestoreWnfSubscription
0x14007615d  lea     r8d, [r9+1]
0x140076161  call    cs:__imp_ExSubscribeWnfStateChange
0x140076168  nop     dword ptr [rax+rax+00h]
0x14007616d  mov     ebx, eax
0x14007616f  test    eax, eax
0x140076171  jns     short loc_1400761AF
0x140076173  mov     rcx, cs:WPP_GLOBAL_Control
0x14007617a  cmp     rcx, rsi
0x14007617d  jz      short loc_1400761A6
0x14007617f  cmp     byte ptr [rcx+29h], 2
0x140076183  jb      short loc_1400761A6
0x140076185  test    dword ptr [rcx+2Ch], 100000h
0x14007618c  jz      short loc_1400761A6
0x14007618e  mov     rcx, [rcx+18h]
0x140076192  lea     r8, WPP_fa6ed00f1ff630e6c9a96c7c6e50e91a_Traceguids
0x140076199  mov     edx, 16h
0x14007619e  mov     r9d, eax
0x1400761a1  call    WPP_SF_d
0x1400761a6  xor     ebx, ebx
0x1400761a8  mov     cs:NrtContainerRestoreWnfSubscription, rbx
0x1400761af  mov     eax, ebx
0x1400761b1  mov     rcx, [rsp+48h+var_10]
0x1400761b6  xor     rcx, rsp; StackCookie
0x1400761b9  call    __security_check_cookie
0x1400761be  mov     rbx, [rsp+48h+arg_0]
0x1400761c3  add     rsp, 40h
0x1400761c7  pop     rsi
0x1400761c8  retn
```
