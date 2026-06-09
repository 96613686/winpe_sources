# CldSyncCleanup

- ea: `0x140081958`
- end: `0x140081b46`
- name: `CldSyncCleanup`
- size: `494`
- prototype: `__int64 __fastcall(struct _UNICODE_PREFIX_TABLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140081910`

## callees

- `0x1400562ec`
- `0x140081958`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400819c8`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400819c8`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x1400819a3`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x1400819a3`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400819f6`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400819f6`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140081af8`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140081af8`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140081a0d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140081a52`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140081a0d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140081a52`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400819b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081ae9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400819b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081ae9`
- `FLTMGR!FltReleasePushLockEx` at `0x140081a63`
- `FLTMGR!FltReleasePushLockEx` at `0x140081b11`
- `FLTMGR!FltReleasePushLockEx` at `0x140081b26`
- `FLTMGR!FltReleasePushLockEx` at `0x140081a63`
- `FLTMGR!FltReleasePushLockEx` at `0x140081b11`
- `FLTMGR!FltReleasePushLockEx` at `0x140081b26`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140081976`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14008198b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140081a3a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140081976`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14008198b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140081a3a`

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
0x140081958  mov     [rsp+arg_10], rbx
0x14008195d  mov     [rsp+arg_18], rbp
0x140081962  push    rsi
0x140081963  push    rdi
0x140081964  push    r14
0x140081966  sub     rsp, 20h
0x14008196a  mov     rbp, rcx
0x14008196d  xor     edx, edx
0x14008196f  lea     rcx, qword_1400286A8
0x140081976  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14008197d  nop     dword ptr [rax+rax+00h]
0x140081982  lea     r14, [rbp+8]
0x140081986  xor     edx, edx
0x140081988  mov     rcx, r14
0x14008198b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140081992  nop     dword ptr [rax+rax+00h]
0x140081997  lea     rdi, [rbp+78h]
0x14008199b  jmp     short loc_1400819C3
0x14008199d  mov     rdx, rbx; PrefixTableEntry
0x1400819a0  mov     rcx, rdi; PrefixTable
0x1400819a3  call    cs:__imp_RtlRemoveUnicodePrefix
0x1400819aa  nop     dword ptr [rax+rax+00h]
0x1400819af  mov     edx, 65707343h; Tag
0x1400819b4  mov     rcx, rbx; P
0x1400819b7  call    cs:__imp_ExFreePoolWithTag
0x1400819be  nop     dword ptr [rax+rax+00h]
0x1400819c3  mov     dl, 1; Restart
0x1400819c5  mov     rcx, rdi; PrefixTable
0x1400819c8  call    cs:__imp_RtlNextUnicodePrefix
0x1400819cf  nop     dword ptr [rax+rax+00h]
0x1400819d4  mov     rbx, rax
0x1400819d7  test    rax, rax
0x1400819da  jnz     short loc_14008199D
0x1400819dc  add     rbp, 10h
0x1400819e0  jmp     loc_140081AF5
0x1400819e5  lea     rdx, [rsp+38h+RestartKey]; RestartKey
0x1400819ea  mov     [rsp+38h+RestartKey], 0
0x1400819f3  mov     rcx, rbp; Table
0x1400819f6  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400819fd  nop     dword ptr [rax+rax+00h]
0x140081a02  mov     rcx, rbp; Table
0x140081a05  mov     rsi, [rax+8]
0x140081a09  lea     rdx, [rsi+18h]; Buffer
0x140081a0d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140081a14  nop     dword ptr [rax+rax+00h]
0x140081a19  mov     rax, [rsi+60h]
0x140081a1d  test    rax, rax
0x140081a20  jz      short loc_140081A79
0x140081a22  mov     rbx, [rsi+60h]
0x140081a26  xor     edx, edx
0x140081a28  mov     rax, [rsi]
0x140081a2b  mov     [rsp+38h+Buffer], rax
0x140081a30  lea     rdi, [rbx+90h]
0x140081a37  mov     rcx, rdi
0x140081a3a  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140081a41  nop     dword ptr [rax+rax+00h]
0x140081a46  lea     rcx, [rbx+98h]; Table
0x140081a4d  lea     rdx, [rsp+38h+Buffer]; Buffer
0x140081a52  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140081a59  nop     dword ptr [rax+rax+00h]
0x140081a5e  xor     edx, edx
0x140081a60  mov     rcx, rdi
0x140081a63  call    cs:__imp_FltReleasePushLockEx
0x140081a6a  nop     dword ptr [rax+rax+00h]
0x140081a6f  xor     edx, edx
0x140081a71  mov     rcx, rsi
0x140081a74  call    CldSyncDisconnectRootByObject
0x140081a79  mov     rcx, [rsi+20h]; P
0x140081a7d  test    rcx, rcx
0x140081a80  jz      short loc_140081A93
0x140081a82  mov     edx, 69537348h; Tag
0x140081a87  call    cs:__imp_ExFreePoolWithTag
0x140081a8e  nop     dword ptr [rax+rax+00h]
0x140081a93  mov     rcx, [rsi+10h]; P
0x140081a97  test    rcx, rcx
0x140081a9a  jz      short loc_140081AAD
0x140081a9c  mov     edx, 73557348h; Tag
0x140081aa1  call    cs:__imp_ExFreePoolWithTag
0x140081aa8  nop     dword ptr [rax+rax+00h]
0x140081aad  mov     rcx, [rsi+50h]; P
0x140081ab1  test    rcx, rcx
0x140081ab4  jz      short loc_140081AC7
0x140081ab6  mov     edx, 72736C43h; Tag
0x140081abb  call    cs:__imp_ExFreePoolWithTag
0x140081ac2  nop     dword ptr [rax+rax+00h]
0x140081ac7  mov     rcx, [rsi+40h]; P
0x140081acb  test    rcx, rcx
0x140081ace  jz      short loc_140081AE1
0x140081ad0  mov     edx, 53536C43h; Tag
0x140081ad5  call    cs:__imp_ExFreePoolWithTag
0x140081adc  nop     dword ptr [rax+rax+00h]
0x140081ae1  mov     edx, 72736C43h; Tag
0x140081ae6  mov     rcx, rsi; P
0x140081ae9  call    cs:__imp_ExFreePoolWithTag
0x140081af0  nop     dword ptr [rax+rax+00h]
0x140081af5  mov     rcx, rbp; Table
0x140081af8  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x140081aff  nop     dword ptr [rax+rax+00h]
0x140081b04  test    eax, eax
0x140081b06  jnz     loc_1400819E5
0x140081b0c  xor     edx, edx
0x140081b0e  mov     rcx, r14
0x140081b11  call    cs:__imp_FltReleasePushLockEx
0x140081b18  nop     dword ptr [rax+rax+00h]
0x140081b1d  xor     edx, edx
0x140081b1f  lea     rcx, qword_1400286A8
0x140081b26  call    cs:__imp_FltReleasePushLockEx
0x140081b2d  nop     dword ptr [rax+rax+00h]
0x140081b32  mov     rbx, [rsp+38h+arg_10]
0x140081b37  mov     rbp, [rsp+38h+arg_18]
0x140081b3c  add     rsp, 20h
0x140081b40  pop     r14
0x140081b42  pop     rdi
0x140081b43  pop     rsi
0x140081b44  retn
```
