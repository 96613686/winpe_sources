# UxTlDestroyConnectionWorker

- ea: `0x140089800`
- end: `0x140089b07`
- name: `UxTlDestroyConnectionWorker`
- size: `775`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x140089800`
- `0x1400cb148`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400899e6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400899e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140089a27`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140089a27`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400898b5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008994f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400898b5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008994f`
- `ntoskrnl!IoFreeIrp` at `0x140089848`
- `ntoskrnl!IoFreeIrp` at `0x140089848`
- `ntoskrnl!KeSetEvent` at `0x140089a14`
- `ntoskrnl!KeSetEvent` at `0x140089a14`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140089938`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400899bf`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140089938`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400899bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400898f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400898f6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400898d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400898d6`

## pseudocode

```c
void __fastcall UxTlDestroyConnectionWorker(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v2; // rbx
  IRP *v3; // rcx
  _DWORD *v4; // rsi
  unsigned __int64 v5; // rdi
  __int64 v6; // rdi
  KIRQL v7; // al
  bool v8; // zf
  KIRQL v9; // si
  __int64 v10; // rax
  __int64 v11; // rdi
  USHORT v12; // ax
  __int64 v13; // r9
  int v14; // esi
  __int64 v15; // rdi
  USHORT CurrentNodeNumber; // ax
  ULONG_PTR v17; // rdx
  int v18; // eax
  ULONG_PTR v19; // rdx
  _DWORD v20[24]; // [rsp+40h] [rbp-88h] BYREF

  v1 = *(_QWORD *)(a1 - 224);
  v2 = a1 - 432;
  *(_QWORD *)(a1 - 432 + 208) = 0;
  v3 = *(IRP **)(a1 - 432 + 96);
  if ( v3 )
  {
    IoFreeIrp(v3);
    *(_QWORD *)(v2 + 96) = 0;
  }
  v4 = *(_DWORD **)(v2 + 104);
  if ( v4 )
  {
    memset(v20, 0, sizeof(v20));
    if ( UxDebugDisableLookaside )
    {
      v20[10] = dword_1401A0388;
      ((void (__fastcall *)(_DWORD *, _DWORD *))off_1401A0398)(v4, v20);
    }
    else if ( UxCompactMode )
    {
      v15 = qword_1401A0370;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v15, v4, CurrentNodeNumber);
    }
    else
    {
      v5 = qword_1401A0370 + ((unsigned __int64)(unsigned int)(*v4 + 1) << 7);
      if ( !*(_BYTE *)(v5 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0370, v5 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v5 + 64), v4);
    }
    *(_QWORD *)(v2 + 104) = 0;
  }
  v6 = *(_QWORD *)(v2 + 480);
  *(_QWORD *)(v2 + 480) = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6);
  v8 = (*(_DWORD *)(v6 + 12))-- == 1;
  v9 = v7;
  if ( v8 )
  {
    KeAcquireSpinLockAtDpcLevel(&UlPartitionsSpinLock);
    if ( !--UlPartitionsActiveCount )
      KeSetEvent(&UlScavengerRefreshEvent, 0, 0);
    KeReleaseSpinLockFromDpcLevel(&UlPartitionsSpinLock);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)v6, v9);
  v10 = *(_QWORD *)(v2 + 520);
  if ( v10 )
  {
    v17 = v10 + 16;
    v18 = _InterlockedDecrement((volatile signed __int32 *)(v10 + 16));
    if ( UxDebugCheckRefcount && v18 <= -1 )
      UlBugCheckEx(3u, v17, 0xAu, v18);
    if ( !v18 )
      UlAiFreeAddressInformation(*(PVOID *)(v2 + 520));
  }
  *(_DWORD *)(v2 + 56) = 7;
  *(_DWORD *)(v2 + 32) = 1129598069;
  if ( v1 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(v1 + 200) + 8680LL);
    v12 = KeGetCurrentNodeNumber();
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v11 + 8LL * v12 + 8), (PVOID)v2);
    v14 = _InterlockedDecrement((volatile signed __int32 *)(v1 + 8));
    if ( UxDebugCheckRefcount && v14 <= -1 )
      UlBugCheckEx(3u, v1 + 8, 0xFu, v14);
    if ( !v14 )
    {
      v19 = v1 + 48;
      if ( *(_QWORD *)(v1 + 48) || *(_QWORD *)(v1 + 64) || *(_QWORD *)(v1 + 80) )
        UlBugCheckEx(1u, v19, (ULONG_PTR)"minio\\http\\sys\\tl.h", 0x400u);
      LOBYTE(v13) = 1;
      UlThreadPoolEnqueueWorkItem(0, v19, UxTlDestroyListenEndpoint, v13, *(_QWORD *)(v1 + 192), -1);
    }
  }
}

```

## disassembly

```asm
0x140089800  mov     [rsp+arg_8], rbx
0x140089805  mov     [rsp+arg_10], rbp
0x14008980a  push    rsi
0x14008980b  push    rdi
0x14008980c  push    r14
0x14008980e  sub     rsp, 0B0h
0x140089815  mov     rax, cs:__security_cookie
0x14008981c  xor     rax, rsp
0x14008981f  mov     [rsp+0C8h+var_28], rax
0x140089827  mov     rbp, [rcx-0E0h]
0x14008982e  lea     rbx, [rcx-1B0h]
0x140089835  xor     r14d, r14d
0x140089838  mov     [rbx+0D0h], r14
0x14008983f  mov     rcx, [rbx+60h]; Irp
0x140089843  test    rcx, rcx
0x140089846  jz      short loc_140089858
0x140089848  call    cs:__imp_IoFreeIrp
0x14008984f  nop     dword ptr [rax+rax+00h]
0x140089854  mov     [rbx+60h], r14
0x140089858  mov     rsi, [rbx+68h]
0x14008985c  test    rsi, rsi
0x14008985f  jz      short loc_1400898C5
0x140089861  xor     edx, edx; Val
0x140089863  lea     rcx, [rsp+0C8h+var_88]; void *
0x140089868  mov     r8d, 60h ; '`'; Size
0x14008986e  call    memset
0x140089873  cmp     cs:UxDebugDisableLookaside, r14b
0x14008987a  jnz     loc_140089AE4
0x140089880  cmp     cs:UxCompactMode, r14b
0x140089887  jnz     loc_1400899B8
0x14008988d  mov     edi, [rsi]
0x14008988f  mov     rcx, cs:qword_1401A0370
0x140089896  inc     edi
0x140089898  shl     rdi, 7
0x14008989c  add     rdi, rcx
0x14008989f  movzx   eax, byte ptr [rdi+0B0h]
0x1400898a6  test    al, al
0x1400898a8  jz      loc_140089A7E
0x1400898ae  mov     rdx, rsi; Entry
0x1400898b1  lea     rcx, [rdi+40h]; Lookaside
0x1400898b5  call    cs:__imp_ExFreeToLookasideListEx
0x1400898bc  nop     dword ptr [rax+rax+00h]
0x1400898c1  mov     [rbx+68h], r14
0x1400898c5  mov     rdi, [rbx+1E0h]
0x1400898cc  mov     rcx, rdi; SpinLock
0x1400898cf  mov     [rbx+1E0h], r14
0x1400898d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400898dd  nop     dword ptr [rax+rax+00h]
0x1400898e2  add     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x1400898e6  movzx   esi, al
0x1400898e9  jz      loc_1400899DF
0x1400898ef  movzx   edx, sil; NewIrql
0x1400898f3  mov     rcx, rdi; SpinLock
0x1400898f6  call    cs:__imp_KeReleaseSpinLock
0x1400898fd  nop     dword ptr [rax+rax+00h]
0x140089902  mov     rax, [rbx+208h]
0x140089909  mov     esi, 0FFFFFFFFh
0x14008990e  test    rax, rax
0x140089911  jnz     loc_140089A38
0x140089917  mov     dword ptr [rbx+38h], 7
0x14008991e  mov     dword ptr [rbx+20h], 43544C75h
0x140089925  test    rbp, rbp
0x140089928  jz      short loc_140089976
0x14008992a  mov     rax, [rbp+0C8h]
0x140089931  mov     rdi, [rax+21E8h]
0x140089938  call    cs:__imp_KeGetCurrentNodeNumber
0x14008993f  nop     dword ptr [rax+rax+00h]
0x140089944  movzx   ecx, ax
0x140089947  mov     rdx, rbx; Entry
0x14008994a  mov     rcx, [rdi+rcx*8+8]; Lookaside
0x14008994f  call    cs:__imp_ExFreeToLookasideListEx
0x140089956  nop     dword ptr [rax+rax+00h]
0x14008995b  lea     rdx, [rbp+8]; BugCheckParameter2
0x14008995f  lock xadd [rdx], esi
0x140089963  dec     esi
0x140089965  cmp     cs:UxDebugCheckRefcount, r14b
0x14008996c  jnz     short loc_14008999F
0x14008996e  test    esi, esi
0x140089970  jz      loc_140089A8C
0x140089976  mov     rcx, [rsp+0C8h+var_28]
0x14008997e  xor     rcx, rsp; StackCookie
0x140089981  call    __security_check_cookie
0x140089986  lea     r11, [rsp+0C8h+var_18]
0x14008998e  mov     rbx, [r11+28h]
0x140089992  mov     rbp, [r11+30h]
0x140089996  mov     rsp, r11
0x140089999  pop     r14
0x14008999b  pop     rdi
0x14008999c  pop     rsi
0x14008999d  retn
0x14008999f  cmp     esi, 0FFFFFFFFh
0x1400899a2  jg      short loc_14008996E
0x1400899a4  movsxd  r9, esi; BugCheckParameter4
0x1400899a7  mov     ecx, 3; BugCheckParameter1
0x1400899ac  mov     r8d, 0Fh; BugCheckParameter3
0x1400899b2  call    UlBugCheckEx
0x1400899b8  mov     rdi, cs:qword_1401A0370
0x1400899bf  call    cs:__imp_KeGetCurrentNodeNumber
0x1400899c6  nop     dword ptr [rax+rax+00h]
0x1400899cb  movzx   r8d, ax
0x1400899cf  mov     rdx, rsi
0x1400899d2  mov     rcx, rdi
0x1400899d5  call    PplFreeToLookasideListProcessor
0x1400899da  jmp     loc_1400898C1
0x1400899df  lea     rcx, UlPartitionsSpinLock; SpinLock
0x1400899e6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400899ed  nop     dword ptr [rax+rax+00h]
0x1400899f2  mov     edx, cs:UlPartitionsActiveCount
0x1400899f8  dec     edx
0x1400899fa  mov     cs:UlPartitionsActiveCount, edx
0x140089a00  mov     edx, cs:UlPartitionsActiveCount; Increment
0x140089a06  test    edx, edx
0x140089a08  jnz     short loc_140089A20
0x140089a0a  xor     r8d, r8d; Wait
0x140089a0d  lea     rcx, UlScavengerRefreshEvent; Event
0x140089a14  call    cs:__imp_KeSetEvent
0x140089a1b  nop     dword ptr [rax+rax+00h]
0x140089a20  lea     rcx, UlPartitionsSpinLock; SpinLock
0x140089a27  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140089a2e  nop     dword ptr [rax+rax+00h]
0x140089a33  jmp     loc_1400898EF
0x140089a38  lea     rdx, [rax+10h]; BugCheckParameter2
0x140089a3c  mov     eax, esi
0x140089a3e  lock xadd [rdx], eax
0x140089a42  dec     eax
0x140089a44  cmp     cs:UxDebugCheckRefcount, r14b
0x140089a4b  jnz     short loc_140089A66
0x140089a4d  test    eax, eax
0x140089a4f  jnz     loc_140089917
0x140089a55  mov     rcx, [rbx+208h]; P
0x140089a5c  call    UlAiFreeAddressInformation
0x140089a61  jmp     loc_140089917
0x140089a66  cmp     eax, esi
0x140089a68  jg      short loc_140089A4D
0x140089a6a  movsxd  r9, eax; BugCheckParameter4
0x140089a6d  mov     ecx, 3; BugCheckParameter1
0x140089a72  mov     r8d, 0Ah; BugCheckParameter3
0x140089a78  call    UlBugCheckEx
0x140089a7e  lea     rdx, [rdi+40h]
0x140089a82  call    PplpLazyInitializeLookasideList
0x140089a87  jmp     loc_1400898AE
0x140089a8c  cmp     [rbp+30h], r14
0x140089a90  lea     rdx, [rbp+30h]; BugCheckParameter2
0x140089a94  jnz     short loc_140089A9C
0x140089a96  cmp     [rdx+10h], r14
0x140089a9a  jz      short loc_140089AB4
0x140089a9c  mov     r9d, 400h; BugCheckParameter4
0x140089aa2  lea     r8, aMinioHttpSysTl; "minio\\http\\sys\\tl.h"
0x140089aa9  mov     ecx, 1; BugCheckParameter1
0x140089aae  call    UlBugCheckEx
0x140089ab4  cmp     [rdx+20h], r14
0x140089ab8  jnz     short loc_140089A9C
0x140089aba  mov     rax, [rbp+0C0h]
0x140089ac1  lea     r8, UxTlDestroyListenEndpoint
0x140089ac8  mov     [rsp+0C8h+var_A0], 0FFFFFFFFh
0x140089ad0  mov     r9b, 1
0x140089ad3  xor     ecx, ecx
0x140089ad5  mov     [rsp+0C8h+var_A8], rax
0x140089ada  call    UlThreadPoolEnqueueWorkItem
0x140089adf  jmp     loc_140089976
0x140089ae4  mov     eax, cs:dword_1401A0388
0x140089aea  lea     rdx, [rsp+0C8h+var_88]
0x140089aef  mov     [rsp+0C8h+var_60], eax
0x140089af3  mov     rcx, rsi
0x140089af6  mov     rax, cs:off_1401A0398
0x140089afd  call    _guard_dispatch_icall
0x140089b02  jmp     loc_1400898C1
```
