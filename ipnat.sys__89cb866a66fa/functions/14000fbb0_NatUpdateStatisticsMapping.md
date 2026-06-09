# NatUpdateStatisticsMapping

- ea: `0x14000fbb0`
- end: `0x14000fd78`
- name: `NatUpdateStatisticsMapping`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000f134`
- `0x14001f110`

## callees

- `0x14000218c`
- `0x14000fbb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fc90`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fc90`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fd2c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fd2c`

## pseudocode

```c
void __fastcall NatUpdateStatisticsMapping(__int64 a1)
{
  unsigned __int32 v2; // r12d
  unsigned __int32 v3; // edi
  unsigned __int32 v4; // esi
  unsigned __int32 v5; // ebp
  unsigned __int32 v6; // r15d
  unsigned __int32 v7; // r14d
  __int64 v8; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  v2 = _InterlockedExchange((volatile __int32 *)(a1 + 336), 0);
  v3 = _InterlockedExchange((volatile __int32 *)(a1 + 340), 0);
  v4 = _InterlockedExchange((volatile __int32 *)(a1 + 344), 0);
  v5 = _InterlockedExchange((volatile __int32 *)(a1 + 348), 0);
  v6 = _InterlockedExchange((volatile __int32 *)(a1 + 352), 0);
  v7 = _InterlockedExchange((volatile __int32 *)(a1 + 356), 0);
  if ( v2 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 288), v2);
  if ( v3 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 296), v3);
  if ( v4 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 304), v4);
  if ( v5 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 312), v5);
  if ( v6 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 320), v6);
  if ( v7 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 328), v7);
  KeAcquireSpinLockAtDpcLevel(&InterfaceLock);
  v8 = *(_QWORD *)(a1 + 144);
  if ( v8 )
  {
    if ( v2 )
      _InterlockedAdd64((volatile signed __int64 *)(v8 + 208), v2);
    if ( v3 )
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 144) + 216LL), v3);
    if ( v4 )
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 144) + 224LL), v4);
    if ( v5 )
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 144) + 232LL), v5);
    if ( v6 )
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 144) + 240LL), v6);
    if ( v7 )
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(a1 + 144) + 248LL), v7);
  }
  KeReleaseSpinLockFromDpcLevel(&InterfaceLock);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
}

```

## disassembly

```asm
0x14000fbb0  push    rbx
0x14000fbb2  push    rbp
0x14000fbb3  push    rsi
0x14000fbb4  push    rdi
0x14000fbb5  push    r12
0x14000fbb7  push    r13
0x14000fbb9  push    r14
0x14000fbbb  push    r15
0x14000fbbd  sub     rsp, 28h
0x14000fbc1  mov     rbx, rcx
0x14000fbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbcb  lea     r13, WPP_GLOBAL_Control
0x14000fbd2  cmp     rcx, r13
0x14000fbd5  jz      short loc_14000FBF9
0x14000fbd7  mov     eax, [rcx+2Ch]
0x14000fbda  test    al, 1
0x14000fbdc  jz      short loc_14000FBF9
0x14000fbde  cmp     byte ptr [rcx+29h], 6
0x14000fbe2  jb      short loc_14000FBF9
0x14000fbe4  mov     rcx, [rcx+18h]
0x14000fbe8  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000fbef  mov     edx, 55h ; 'U'
0x14000fbf4  call    WPP_SF_
0x14000fbf9  xor     r12d, r12d
0x14000fbfc  xor     edi, edi
0x14000fbfe  xchg    r12d, [rbx+150h]
0x14000fc05  xchg    edi, [rbx+154h]
0x14000fc0b  xor     esi, esi
0x14000fc0d  xor     ebp, ebp
0x14000fc0f  xchg    esi, [rbx+158h]
0x14000fc15  xchg    ebp, [rbx+15Ch]
0x14000fc1b  xor     r15d, r15d
0x14000fc1e  xor     r14d, r14d
0x14000fc21  xchg    r15d, [rbx+160h]
0x14000fc28  xchg    r14d, [rbx+164h]
0x14000fc2f  test    r12d, r12d
0x14000fc32  jz      short loc_14000FC3F
0x14000fc34  mov     eax, r12d
0x14000fc37  lock add [rbx+120h], rax
0x14000fc3f  test    edi, edi
0x14000fc41  jz      short loc_14000FC4D
0x14000fc43  mov     eax, edi
0x14000fc45  lock add [rbx+128h], rax
0x14000fc4d  test    esi, esi
0x14000fc4f  jz      short loc_14000FC5B
0x14000fc51  mov     eax, esi
0x14000fc53  lock add [rbx+130h], rax
0x14000fc5b  test    ebp, ebp
0x14000fc5d  jz      short loc_14000FC69
0x14000fc5f  mov     eax, ebp
0x14000fc61  lock add [rbx+138h], rax
0x14000fc69  test    r15d, r15d
0x14000fc6c  jz      short loc_14000FC79
0x14000fc6e  mov     eax, r15d
0x14000fc71  lock add [rbx+140h], rax
0x14000fc79  test    r14d, r14d
0x14000fc7c  jz      short loc_14000FC89
0x14000fc7e  mov     eax, r14d
0x14000fc81  lock add [rbx+148h], rax
0x14000fc89  lea     rcx, InterfaceLock; SpinLock
0x14000fc90  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fc97  nop     dword ptr [rax+rax+00h]
0x14000fc9c  mov     rcx, [rbx+90h]
0x14000fca3  test    rcx, rcx
0x14000fca6  jz      short loc_14000FD25
0x14000fca8  test    r12d, r12d
0x14000fcab  jz      short loc_14000FCB8
0x14000fcad  mov     eax, r12d
0x14000fcb0  lock add [rcx+0D0h], rax
0x14000fcb8  test    edi, edi
0x14000fcba  jz      short loc_14000FCCD
0x14000fcbc  mov     rax, [rbx+90h]
0x14000fcc3  mov     ecx, edi
0x14000fcc5  lock add [rax+0D8h], rcx
0x14000fccd  test    esi, esi
0x14000fccf  jz      short loc_14000FCE2
0x14000fcd1  mov     rax, [rbx+90h]
0x14000fcd8  mov     ecx, esi
0x14000fcda  lock add [rax+0E0h], rcx
0x14000fce2  test    ebp, ebp
0x14000fce4  jz      short loc_14000FCF7
0x14000fce6  mov     rax, [rbx+90h]
0x14000fced  mov     ecx, ebp
0x14000fcef  lock add [rax+0E8h], rcx
0x14000fcf7  test    r15d, r15d
0x14000fcfa  jz      short loc_14000FD0E
0x14000fcfc  mov     rax, [rbx+90h]
0x14000fd03  mov     edx, r15d
0x14000fd06  lock add [rax+0F0h], rdx
0x14000fd0e  test    r14d, r14d
0x14000fd11  jz      short loc_14000FD25
0x14000fd13  mov     rax, [rbx+90h]
0x14000fd1a  mov     edx, r14d
0x14000fd1d  lock add [rax+0F8h], rdx
0x14000fd25  lea     rcx, InterfaceLock; SpinLock
0x14000fd2c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fd33  nop     dword ptr [rax+rax+00h]
0x14000fd38  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd3f  cmp     rcx, r13
0x14000fd42  jz      short loc_14000FD66
0x14000fd44  mov     eax, [rcx+2Ch]
0x14000fd47  test    al, 1
0x14000fd49  jz      short loc_14000FD66
0x14000fd4b  cmp     byte ptr [rcx+29h], 6
0x14000fd4f  jb      short loc_14000FD66
0x14000fd51  mov     rcx, [rcx+18h]
0x14000fd55  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000fd5c  mov     edx, 56h ; 'V'
0x14000fd61  call    WPP_SF_
0x14000fd66  add     rsp, 28h
0x14000fd6a  pop     r15
0x14000fd6c  pop     r14
0x14000fd6e  pop     r13
0x14000fd70  pop     r12
0x14000fd72  pop     rdi
0x14000fd73  pop     rsi
0x14000fd74  pop     rbp
0x14000fd75  pop     rbx
0x14000fd76  retn
```
