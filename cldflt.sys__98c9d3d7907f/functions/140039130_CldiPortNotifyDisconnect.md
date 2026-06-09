# CldiPortNotifyDisconnect

- ea: `0x140039130`
- end: `0x1400392f8`
- name: `CldiPortNotifyDisconnect`
- size: `456`
- prototype: `void __stdcall(PVOID ConnectionCookie)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140016e18`
- `0x140037a1c`
- `0x140039130`
- `0x1400561cc`
- `0x14006d7b0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400391f4`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400391f4`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140039253`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140039253`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140039244`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140039244`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039224`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400392d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039224`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400392d1`
- `FLTMGR!FltReleasePushLockEx` at `0x140039198`
- `FLTMGR!FltReleasePushLockEx` at `0x14003927a`
- `FLTMGR!FltReleasePushLockEx` at `0x14003928f`
- `FLTMGR!FltReleasePushLockEx` at `0x140039198`
- `FLTMGR!FltReleasePushLockEx` at `0x14003927a`
- `FLTMGR!FltReleasePushLockEx` at `0x14003928f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003914e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391b6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391ce`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003914e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391b6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391ce`
- `FLTMGR!FltCloseClientPort` at `0x1400392a6`
- `FLTMGR!FltCloseClientPort` at `0x1400392bd`
- `FLTMGR!FltCloseClientPort` at `0x1400392a6`
- `FLTMGR!FltCloseClientPort` at `0x1400392bd`

## pseudocode

```c
void __fastcall CldiPortNotifyDisconnect(PVOID **ConnectionCookie)
{
  PVOID *v3; // rax
  PVOID *v4; // rdx
  _QWORD *v5; // rbp
  __int64 RootInfo; // rax
  void *v7; // rdi
  PVOID RestartKey; // [rsp+40h] [rbp+8h] BYREF

  FltAcquirePushLockExclusiveEx(&PushLock, 0);
  if ( (*((_DWORD *)ConnectionCookie + 64))-- == 1 )
  {
    v3 = *ConnectionCookie;
    if ( (*ConnectionCookie)[1] != ConnectionCookie || (v4 = ConnectionCookie[1], *v4 != ConnectionCookie) )
      __fastfail(3u);
    *v4 = v3;
    v3[1] = v4;
    ConnectionCookie[1] = (PVOID *)ConnectionCookie;
    *ConnectionCookie = (PVOID *)ConnectionCookie;
  }
  else
  {
    ConnectionCookie = 0;
  }
  FltReleasePushLockEx(&PushLock, 0);
  if ( ConnectionCookie )
  {
    FltAcquirePushLockExclusiveEx(&qword_1400286A8, 0);
    FltAcquirePushLockExclusiveEx(ConnectionCookie + 18, 0);
    while ( RtlNumberGenericTableElementsAvl((PRTL_AVL_TABLE)(ConnectionCookie + 19)) )
    {
      RestartKey = 0;
      v5 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(ConnectionCookie + 19), &RestartKey);
      RootInfo = CldSyncGetRootInfo(v5[1]);
      v7 = (void *)RootInfo;
      if ( RootInfo )
      {
        TlmWriteProviderCrashedEvent(RootInfo);
        ExFreePoolWithTag(v7, 0x69726943u);
      }
      CldSyncDisconnectRootByObject(v5[1], 3221225473LL);
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(ConnectionCookie + 19), v5);
    }
    CldReleaseProcessInfo(ConnectionCookie + 9);
    CldReleaseProcessInfo(ConnectionCookie + 13);
    FltReleasePushLockEx(ConnectionCookie + 18, 0);
    FltReleasePushLockEx(&qword_1400286A8, 0);
    FltCloseClientPort(Globals, (PFLT_PORT *)ConnectionCookie + 2);
    FltCloseClientPort(Globals, (PFLT_PORT *)ConnectionCookie + 3);
    ExFreePoolWithTag(ConnectionCookie, 0x63706C43u);
  }
}

```

## disassembly

```asm
0x140039130  mov     [rsp+arg_8], rbx
0x140039135  mov     [rsp+arg_10], rbp
0x14003913a  push    rsi
0x14003913b  push    rdi
0x14003913c  push    r14
0x14003913e  sub     rsp, 20h
0x140039142  mov     rbx, rcx
0x140039145  xor     edx, edx
0x140039147  lea     rcx, PushLock
0x14003914e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140039155  nop     dword ptr [rax+rax+00h]
0x14003915a  add     dword ptr [rbx+100h], 0FFFFFFFFh
0x140039161  jz      short loc_140039167
0x140039163  xor     ebx, ebx
0x140039165  jmp     short loc_14003918F
0x140039167  mov     rax, [rbx]
0x14003916a  cmp     [rax+8], rbx
0x14003916e  jnz     loc_1400392F1
0x140039174  mov     rdx, [rbx+8]
0x140039178  cmp     [rdx], rbx
0x14003917b  jnz     loc_1400392F1
0x140039181  mov     [rdx], rax
0x140039184  mov     [rax+8], rdx
0x140039188  mov     [rbx+8], rbx
0x14003918c  mov     [rbx], rbx
0x14003918f  xor     edx, edx
0x140039191  lea     rcx, PushLock
0x140039198  call    cs:__imp_FltReleasePushLockEx
0x14003919f  nop     dword ptr [rax+rax+00h]
0x1400391a4  test    rbx, rbx
0x1400391a7  jz      loc_1400392DD
0x1400391ad  xor     edx, edx
0x1400391af  lea     rcx, qword_1400286A8
0x1400391b6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400391bd  nop     dword ptr [rax+rax+00h]
0x1400391c2  lea     r14, [rbx+90h]
0x1400391c9  xor     edx, edx
0x1400391cb  mov     rcx, r14
0x1400391ce  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400391d5  nop     dword ptr [rax+rax+00h]
0x1400391da  lea     rsi, [rbx+98h]
0x1400391e1  jmp     short loc_140039250
0x1400391e3  lea     rdx, [rsp+38h+RestartKey]; RestartKey
0x1400391e8  mov     [rsp+38h+RestartKey], 0
0x1400391f1  mov     rcx, rsi; Table
0x1400391f4  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400391fb  nop     dword ptr [rax+rax+00h]
0x140039200  mov     rbp, rax
0x140039203  mov     rcx, [rax+8]
0x140039207  call    CldSyncGetRootInfo
0x14003920c  mov     rdi, rax
0x14003920f  test    rax, rax
0x140039212  jz      short loc_140039230
0x140039214  mov     rcx, rax
0x140039217  call    TlmWriteProviderCrashedEvent
0x14003921c  mov     edx, 69726943h; Tag
0x140039221  mov     rcx, rdi; P
0x140039224  call    cs:__imp_ExFreePoolWithTag
0x14003922b  nop     dword ptr [rax+rax+00h]
0x140039230  mov     rcx, [rbp+8]
0x140039234  mov     edx, 0C0000001h
0x140039239  call    CldSyncDisconnectRootByObject
0x14003923e  mov     rdx, rbp; Buffer
0x140039241  mov     rcx, rsi; Table
0x140039244  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14003924b  nop     dword ptr [rax+rax+00h]
0x140039250  mov     rcx, rsi; Table
0x140039253  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x14003925a  nop     dword ptr [rax+rax+00h]
0x14003925f  test    eax, eax
0x140039261  jnz     short loc_1400391E3
0x140039263  lea     rcx, [rbx+48h]
0x140039267  call    CldReleaseProcessInfo
0x14003926c  lea     rcx, [rbx+68h]
0x140039270  call    CldReleaseProcessInfo
0x140039275  xor     edx, edx
0x140039277  mov     rcx, r14
0x14003927a  call    cs:__imp_FltReleasePushLockEx
0x140039281  nop     dword ptr [rax+rax+00h]
0x140039286  xor     edx, edx
0x140039288  lea     rcx, qword_1400286A8
0x14003928f  call    cs:__imp_FltReleasePushLockEx
0x140039296  nop     dword ptr [rax+rax+00h]
0x14003929b  mov     rcx, cs:Globals; Filter
0x1400392a2  lea     rdx, [rbx+10h]; ClientPort
0x1400392a6  call    cs:__imp_FltCloseClientPort
0x1400392ad  nop     dword ptr [rax+rax+00h]
0x1400392b2  mov     rcx, cs:Globals; Filter
0x1400392b9  lea     rdx, [rbx+18h]; ClientPort
0x1400392bd  call    cs:__imp_FltCloseClientPort
0x1400392c4  nop     dword ptr [rax+rax+00h]
0x1400392c9  mov     edx, 63706C43h; Tag
0x1400392ce  mov     rcx, rbx; P
0x1400392d1  call    cs:__imp_ExFreePoolWithTag
0x1400392d8  nop     dword ptr [rax+rax+00h]
0x1400392dd  mov     rbx, [rsp+38h+arg_8]
0x1400392e2  mov     rbp, [rsp+38h+arg_10]
0x1400392e7  add     rsp, 20h
0x1400392eb  pop     r14
0x1400392ed  pop     rdi
0x1400392ee  pop     rsi
0x1400392ef  retn
0x1400392f1  mov     ecx, 3
0x1400392f6  int     29h; Win8: RtlFailFast(ecx)
```
