# CldiPortNotifyDisconnect

- ea: `0x140039150`
- end: `0x140039318`
- name: `CldiPortNotifyDisconnect`
- size: `456`
- prototype: `void __fastcall(PVOID **ConnectionCookie)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140016e98`
- `0x140037a3c`
- `0x140039150`
- `0x1400562ec`
- `0x14006d8d0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140039214`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140039214`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140039273`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140039273`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140039264`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140039264`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039244`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400392f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039244`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400392f1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400391b8`
- `FLTMGR!FltReleasePushLockEx` at `0x14003929a`
- `FLTMGR!FltReleasePushLockEx` at `0x1400392af`
- `FLTMGR!FltReleasePushLockEx` at `0x1400391b8`
- `FLTMGR!FltReleasePushLockEx` at `0x14003929a`
- `FLTMGR!FltReleasePushLockEx` at `0x1400392af`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003916e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391d6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391ee`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003916e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391d6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400391ee`
- `FLTMGR!FltCloseClientPort` at `0x1400392c6`
- `FLTMGR!FltCloseClientPort` at `0x1400392dd`
- `FLTMGR!FltCloseClientPort` at `0x1400392c6`
- `FLTMGR!FltCloseClientPort` at `0x1400392dd`

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
0x140039150  mov     [rsp+arg_8], rbx
0x140039155  mov     [rsp+arg_10], rbp
0x14003915a  push    rsi
0x14003915b  push    rdi
0x14003915c  push    r14
0x14003915e  sub     rsp, 20h
0x140039162  mov     rbx, rcx
0x140039165  xor     edx, edx
0x140039167  lea     rcx, PushLock
0x14003916e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140039175  nop     dword ptr [rax+rax+00h]
0x14003917a  add     dword ptr [rbx+100h], 0FFFFFFFFh
0x140039181  jz      short loc_140039187
0x140039183  xor     ebx, ebx
0x140039185  jmp     short loc_1400391AF
0x140039187  mov     rax, [rbx]
0x14003918a  cmp     [rax+8], rbx
0x14003918e  jnz     loc_140039311
0x140039194  mov     rdx, [rbx+8]
0x140039198  cmp     [rdx], rbx
0x14003919b  jnz     loc_140039311
0x1400391a1  mov     [rdx], rax
0x1400391a4  mov     [rax+8], rdx
0x1400391a8  mov     [rbx+8], rbx
0x1400391ac  mov     [rbx], rbx
0x1400391af  xor     edx, edx
0x1400391b1  lea     rcx, PushLock
0x1400391b8  call    cs:__imp_FltReleasePushLockEx
0x1400391bf  nop     dword ptr [rax+rax+00h]
0x1400391c4  test    rbx, rbx
0x1400391c7  jz      loc_1400392FD
0x1400391cd  xor     edx, edx
0x1400391cf  lea     rcx, qword_1400286A8
0x1400391d6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400391dd  nop     dword ptr [rax+rax+00h]
0x1400391e2  lea     r14, [rbx+90h]
0x1400391e9  xor     edx, edx
0x1400391eb  mov     rcx, r14
0x1400391ee  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400391f5  nop     dword ptr [rax+rax+00h]
0x1400391fa  lea     rsi, [rbx+98h]
0x140039201  jmp     short loc_140039270
0x140039203  lea     rdx, [rsp+38h+RestartKey]; RestartKey
0x140039208  mov     [rsp+38h+RestartKey], 0
0x140039211  mov     rcx, rsi; Table
0x140039214  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14003921b  nop     dword ptr [rax+rax+00h]
0x140039220  mov     rbp, rax
0x140039223  mov     rcx, [rax+8]
0x140039227  call    CldSyncGetRootInfo
0x14003922c  mov     rdi, rax
0x14003922f  test    rax, rax
0x140039232  jz      short loc_140039250
0x140039234  mov     rcx, rax
0x140039237  call    TlmWriteProviderCrashedEvent
0x14003923c  mov     edx, 69726943h; Tag
0x140039241  mov     rcx, rdi; P
0x140039244  call    cs:__imp_ExFreePoolWithTag
0x14003924b  nop     dword ptr [rax+rax+00h]
0x140039250  mov     rcx, [rbp+8]
0x140039254  mov     edx, 0C0000001h
0x140039259  call    CldSyncDisconnectRootByObject
0x14003925e  mov     rdx, rbp; Buffer
0x140039261  mov     rcx, rsi; Table
0x140039264  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14003926b  nop     dword ptr [rax+rax+00h]
0x140039270  mov     rcx, rsi; Table
0x140039273  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x14003927a  nop     dword ptr [rax+rax+00h]
0x14003927f  test    eax, eax
0x140039281  jnz     short loc_140039203
0x140039283  lea     rcx, [rbx+48h]
0x140039287  call    CldReleaseProcessInfo
0x14003928c  lea     rcx, [rbx+68h]
0x140039290  call    CldReleaseProcessInfo
0x140039295  xor     edx, edx
0x140039297  mov     rcx, r14
0x14003929a  call    cs:__imp_FltReleasePushLockEx
0x1400392a1  nop     dword ptr [rax+rax+00h]
0x1400392a6  xor     edx, edx
0x1400392a8  lea     rcx, qword_1400286A8
0x1400392af  call    cs:__imp_FltReleasePushLockEx
0x1400392b6  nop     dword ptr [rax+rax+00h]
0x1400392bb  mov     rcx, cs:Globals; Filter
0x1400392c2  lea     rdx, [rbx+10h]; ClientPort
0x1400392c6  call    cs:__imp_FltCloseClientPort
0x1400392cd  nop     dword ptr [rax+rax+00h]
0x1400392d2  mov     rcx, cs:Globals; Filter
0x1400392d9  lea     rdx, [rbx+18h]; ClientPort
0x1400392dd  call    cs:__imp_FltCloseClientPort
0x1400392e4  nop     dword ptr [rax+rax+00h]
0x1400392e9  mov     edx, 63706C43h; Tag
0x1400392ee  mov     rcx, rbx; P
0x1400392f1  call    cs:__imp_ExFreePoolWithTag
0x1400392f8  nop     dword ptr [rax+rax+00h]
0x1400392fd  mov     rbx, [rsp+38h+arg_8]
0x140039302  mov     rbp, [rsp+38h+arg_10]
0x140039307  add     rsp, 20h
0x14003930b  pop     r14
0x14003930d  pop     rdi
0x14003930e  pop     rsi
0x14003930f  retn
0x140039311  mov     ecx, 3
0x140039316  int     29h; Win8: RtlFailFast(ecx)
```
