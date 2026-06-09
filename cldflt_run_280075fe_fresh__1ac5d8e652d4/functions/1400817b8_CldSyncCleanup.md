# CldSyncCleanup

- ea: `0x1400817b8`
- end: `0x1400819a6`
- name: `CldSyncCleanup`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140081770`

## callees

- `0x1400561cc`
- `0x1400817b8`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140081828`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140081828`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140081803`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140081803`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140081856`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140081856`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140081958`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140081958`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14008186d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400818b2`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14008186d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400818b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081817`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400818e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081901`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008191b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081935`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081949`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081817`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400818e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081901`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008191b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081935`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081949`
- `FLTMGR!FltReleasePushLockEx` at `0x1400818c3`
- `FLTMGR!FltReleasePushLockEx` at `0x140081971`
- `FLTMGR!FltReleasePushLockEx` at `0x140081986`
- `FLTMGR!FltReleasePushLockEx` at `0x1400818c3`
- `FLTMGR!FltReleasePushLockEx` at `0x140081971`
- `FLTMGR!FltReleasePushLockEx` at `0x140081986`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400817d6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400817eb`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14008189a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400817d6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400817eb`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14008189a`

## pseudocode

```c
__int64 __fastcall CldSyncCleanup(struct _UNICODE_PREFIX_TABLE *a1)
{
  PUNICODE_PREFIX_TABLE_ENTRY *p_NextPrefixTree; // r14
  struct _UNICODE_PREFIX_TABLE_ENTRY *UnicodePrefix; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v4; // rbx
  struct _RTL_AVL_TABLE *p_LastNextEntry; // rbp
  __int64 *v6; // rsi
  __int64 v7; // rbx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  PVOID RestartKey; // [rsp+40h] [rbp+8h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp+10h] BYREF

  FltAcquirePushLockExclusiveEx(&qword_1400286A8, 0);
  p_NextPrefixTree = &a1->NextPrefixTree;
  FltAcquirePushLockExclusiveEx(&a1->NextPrefixTree, 0);
  while ( 1 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(a1 + 5, 1u);
    v4 = UnicodePrefix;
    if ( !UnicodePrefix )
      break;
    RtlRemoveUnicodePrefix(a1 + 5, UnicodePrefix);
    ExFreePoolWithTag(v4, 0x65707343u);
  }
  p_LastNextEntry = (struct _RTL_AVL_TABLE *)&a1->LastNextEntry;
  while ( RtlNumberGenericTableElementsAvl(p_LastNextEntry) )
  {
    RestartKey = 0;
    v6 = (__int64 *)*((_QWORD *)RtlEnumerateGenericTableWithoutSplayingAvl(p_LastNextEntry, &RestartKey) + 1);
    RtlDeleteElementGenericTableAvl(p_LastNextEntry, v6 + 3);
    if ( v6[12] )
    {
      v7 = v6[12];
      Buffer = *v6;
      FltAcquirePushLockExclusiveEx(v7 + 144, 0);
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v7 + 152), &Buffer);
      FltReleasePushLockEx(v7 + 144, 0);
      CldSyncDisconnectRootByObject(v6, 0);
    }
    v8 = (void *)v6[4];
    if ( v8 )
      ExFreePoolWithTag(v8, 0x69537348u);
    v9 = (void *)v6[2];
    if ( v9 )
      ExFreePoolWithTag(v9, 0x73557348u);
    v10 = (void *)v6[10];
    if ( v10 )
      ExFreePoolWithTag(v10, 0x72736C43u);
    v11 = (void *)v6[8];
    if ( v11 )
      ExFreePoolWithTag(v11, 0x53536C43u);
    ExFreePoolWithTag(v6, 0x72736C43u);
  }
  FltReleasePushLockEx(p_NextPrefixTree, 0);
  return FltReleasePushLockEx(&qword_1400286A8, 0);
}

```

## disassembly

```asm
0x1400817b8  mov     [rsp+arg_10], rbx
0x1400817bd  mov     [rsp+arg_18], rbp
0x1400817c2  push    rsi
0x1400817c3  push    rdi
0x1400817c4  push    r14
0x1400817c6  sub     rsp, 20h
0x1400817ca  mov     rbp, rcx
0x1400817cd  xor     edx, edx
0x1400817cf  lea     rcx, qword_1400286A8
0x1400817d6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400817dd  nop     dword ptr [rax+rax+00h]
0x1400817e2  lea     r14, [rbp+8]
0x1400817e6  xor     edx, edx
0x1400817e8  mov     rcx, r14
0x1400817eb  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400817f2  nop     dword ptr [rax+rax+00h]
0x1400817f7  lea     rdi, [rbp+78h]
0x1400817fb  jmp     short loc_140081823
0x1400817fd  mov     rdx, rbx; PrefixTableEntry
0x140081800  mov     rcx, rdi; PrefixTable
0x140081803  call    cs:__imp_RtlRemoveUnicodePrefix
0x14008180a  nop     dword ptr [rax+rax+00h]
0x14008180f  mov     edx, 65707343h; Tag
0x140081814  mov     rcx, rbx; P
0x140081817  call    cs:__imp_ExFreePoolWithTag
0x14008181e  nop     dword ptr [rax+rax+00h]
0x140081823  mov     dl, 1; Restart
0x140081825  mov     rcx, rdi; PrefixTable
0x140081828  call    cs:__imp_RtlNextUnicodePrefix
0x14008182f  nop     dword ptr [rax+rax+00h]
0x140081834  mov     rbx, rax
0x140081837  test    rax, rax
0x14008183a  jnz     short loc_1400817FD
0x14008183c  add     rbp, 10h
0x140081840  jmp     loc_140081955
0x140081845  lea     rdx, [rsp+38h+RestartKey]; RestartKey
0x14008184a  mov     [rsp+38h+RestartKey], 0
0x140081853  mov     rcx, rbp; Table
0x140081856  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14008185d  nop     dword ptr [rax+rax+00h]
0x140081862  mov     rcx, rbp; Table
0x140081865  mov     rsi, [rax+8]
0x140081869  lea     rdx, [rsi+18h]; Buffer
0x14008186d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140081874  nop     dword ptr [rax+rax+00h]
0x140081879  mov     rax, [rsi+60h]
0x14008187d  test    rax, rax
0x140081880  jz      short loc_1400818D9
0x140081882  mov     rbx, [rsi+60h]
0x140081886  xor     edx, edx
0x140081888  mov     rax, [rsi]
0x14008188b  mov     [rsp+38h+Buffer], rax
0x140081890  lea     rdi, [rbx+90h]
0x140081897  mov     rcx, rdi
0x14008189a  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400818a1  nop     dword ptr [rax+rax+00h]
0x1400818a6  lea     rcx, [rbx+98h]; Table
0x1400818ad  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1400818b2  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400818b9  nop     dword ptr [rax+rax+00h]
0x1400818be  xor     edx, edx
0x1400818c0  mov     rcx, rdi
0x1400818c3  call    cs:__imp_FltReleasePushLockEx
0x1400818ca  nop     dword ptr [rax+rax+00h]
0x1400818cf  xor     edx, edx
0x1400818d1  mov     rcx, rsi
0x1400818d4  call    CldSyncDisconnectRootByObject
0x1400818d9  mov     rcx, [rsi+20h]; P
0x1400818dd  test    rcx, rcx
0x1400818e0  jz      short loc_1400818F3
0x1400818e2  mov     edx, 69537348h; Tag
0x1400818e7  call    cs:__imp_ExFreePoolWithTag
0x1400818ee  nop     dword ptr [rax+rax+00h]
0x1400818f3  mov     rcx, [rsi+10h]; P
0x1400818f7  test    rcx, rcx
0x1400818fa  jz      short loc_14008190D
0x1400818fc  mov     edx, 73557348h; Tag
0x140081901  call    cs:__imp_ExFreePoolWithTag
0x140081908  nop     dword ptr [rax+rax+00h]
0x14008190d  mov     rcx, [rsi+50h]; P
0x140081911  test    rcx, rcx
0x140081914  jz      short loc_140081927
0x140081916  mov     edx, 72736C43h; Tag
0x14008191b  call    cs:__imp_ExFreePoolWithTag
0x140081922  nop     dword ptr [rax+rax+00h]
0x140081927  mov     rcx, [rsi+40h]; P
0x14008192b  test    rcx, rcx
0x14008192e  jz      short loc_140081941
0x140081930  mov     edx, 53536C43h; Tag
0x140081935  call    cs:__imp_ExFreePoolWithTag
0x14008193c  nop     dword ptr [rax+rax+00h]
0x140081941  mov     edx, 72736C43h; Tag
0x140081946  mov     rcx, rsi; P
0x140081949  call    cs:__imp_ExFreePoolWithTag
0x140081950  nop     dword ptr [rax+rax+00h]
0x140081955  mov     rcx, rbp; Table
0x140081958  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x14008195f  nop     dword ptr [rax+rax+00h]
0x140081964  test    eax, eax
0x140081966  jnz     loc_140081845
0x14008196c  xor     edx, edx
0x14008196e  mov     rcx, r14
0x140081971  call    cs:__imp_FltReleasePushLockEx
0x140081978  nop     dword ptr [rax+rax+00h]
0x14008197d  xor     edx, edx
0x14008197f  lea     rcx, qword_1400286A8
0x140081986  call    cs:__imp_FltReleasePushLockEx
0x14008198d  nop     dword ptr [rax+rax+00h]
0x140081992  mov     rbx, [rsp+38h+arg_10]
0x140081997  mov     rbp, [rsp+38h+arg_18]
0x14008199c  add     rsp, 20h
0x1400819a0  pop     r14
0x1400819a2  pop     rdi
0x1400819a3  pop     rsi
0x1400819a4  retn
```
