# BfsAddPolicyToGlobalFileTable

- ea: `0x14000c0f4`
- end: `0x14000c33d`
- name: `BfsAddPolicyToGlobalFileTable`
- size: `585`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140009d2c`
- `0x14000ceb4`
- `0x14000dc70`

## callees

- `0x140001008`
- `0x140001320`
- `0x1400013e0`
- `0x1400017b0`
- `0x14000c0f4`
- `0x14000c5c4`
- `0x14000d9dc`
- `0x140012ca0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c15a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c1ce`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c15a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c1ce`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c2cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c302`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c2cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c302`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c177`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c177`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c1a5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c2e4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c1a5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c2e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c148`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c166`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c1bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c148`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c166`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c1bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c1b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c2f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c30e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c1b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c2f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c30e`

## pseudocode

```c
__int64 __fastcall BfsAddPolicyToGlobalFileTable(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        UNICODE_STRING *a4,
        int a5)
{
  __int64 v8; // r12
  int v9; // r14d
  struct _UNICODE_STRING *GlobalFileEntry; // rsi
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int inserted; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v20; // [rsp+20h] [rbp-51h]
  struct _UNICODE_STRING *v21; // [rsp+30h] [rbp-41h] BYREF
  unsigned __int8 *v22; // [rsp+38h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+40h] [rbp-31h] BYREF
  struct _UNICODE_STRING **v24; // [rsp+60h] [rbp-11h]
  __int64 v25; // [rsp+68h] [rbp-9h]

  v22 = a3;
  v21 = 0;
  BfsUpdateUnicodeStringHash(&a4->Length, &v21);
  v8 = BfsFinalHash(&v21);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 8, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  v9 = 1;
  GlobalFileEntry = (struct _UNICODE_STRING *)BfsGetGlobalFileEntry(a1, a4);
  if ( !GlobalFileEntry )
  {
    ExReleasePushLockSharedEx(a1, 0);
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1, 0);
    v9 = 2;
    v21 = (struct _UNICODE_STRING *)BfsGetGlobalFileEntry(a1, a4);
    GlobalFileEntry = v21;
    if ( !v21 )
    {
      v11 = BfsCreateGlobalFileEntry(a4, a5, &v21);
      inserted = v11;
      if ( v11 < 0 )
      {
        v15 = (unsigned int)dword_140019000;
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v21) = v11;
LABEL_6:
          v25 = 4;
          v24 = &v21;
          tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v12, v13, v20, &v23);
        }
LABEL_14:
        ExReleasePushLockExclusiveEx(a1, 0);
        goto LABEL_17;
      }
      GlobalFileEntry = v21;
      inserted = BfsInsertEntryHashTable(*(_QWORD *)(a1 + 40), v8, v21);
      if ( inserted < 0 )
      {
        if ( (unsigned int)dword_140019000 <= 3 )
          goto LABEL_14;
        LODWORD(v21) = inserted;
        goto LABEL_6;
      }
    }
  }
  inserted = BfsUpdateGlobalFilePolicy(a1, (__int64)GlobalFileEntry, a2, v22);
  if ( inserted >= 0 )
  {
    if ( v9 != 2 )
    {
      if ( v9 != 1 )
      {
LABEL_18:
        ExReleasePushLockExclusiveEx(a1 + 8, 0);
        KeLeaveCriticalRegion();
        return (unsigned int)inserted;
      }
      ExReleasePushLockSharedEx(a1, 0);
LABEL_17:
      KeLeaveCriticalRegion();
      goto LABEL_18;
    }
    goto LABEL_14;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v21) = inserted;
    v24 = &v21;
    v25 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v16, (unsigned __int8 *)&byte_140016D91, v17, v18, v20, &v23);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14000c0f4  push    rbp
0x14000c0f6  push    rbx
0x14000c0f7  push    rsi
0x14000c0f8  push    rdi
0x14000c0f9  push    r12
0x14000c0fb  push    r13
0x14000c0fd  push    r14
0x14000c0ff  push    r15
0x14000c101  lea     rbp, [rsp-17h]
0x14000c106  sub     rsp, 88h
0x14000c10d  mov     rax, cs:__security_cookie
0x14000c114  xor     rax, rsp
0x14000c117  mov     [rbp+4Fh+var_50], rax
0x14000c11b  mov     r13, rdx
0x14000c11e  mov     [rbp+4Fh+var_88], r8
0x14000c122  mov     rdi, rcx
0x14000c125  mov     [rbp+4Fh+var_90], 0
0x14000c12d  lea     rdx, [rbp+4Fh+var_90]
0x14000c131  mov     rcx, r9
0x14000c134  mov     rbx, r9
0x14000c137  call    BfsUpdateUnicodeStringHash
0x14000c13c  lea     rcx, [rbp+4Fh+var_90]
0x14000c140  call    BfsFinalHash
0x14000c145  mov     r12, rax
0x14000c148  call    cs:__imp_KeEnterCriticalRegion
0x14000c14f  nop     dword ptr [rax+rax+00h]
0x14000c154  xor     edx, edx
0x14000c156  lea     rcx, [rdi+8]
0x14000c15a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c161  nop     dword ptr [rax+rax+00h]
0x14000c166  call    cs:__imp_KeEnterCriticalRegion
0x14000c16d  nop     dword ptr [rax+rax+00h]
0x14000c172  xor     edx, edx
0x14000c174  mov     rcx, rdi
0x14000c177  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000c17e  nop     dword ptr [rax+rax+00h]
0x14000c183  mov     rdx, rbx
0x14000c186  mov     rcx, rdi
0x14000c189  mov     r14d, 1
0x14000c18f  call    BfsGetGlobalFileEntry
0x14000c194  mov     rsi, rax
0x14000c197  test    rax, rax
0x14000c19a  jnz     loc_14000C26F
0x14000c1a0  xor     edx, edx
0x14000c1a2  mov     rcx, rdi
0x14000c1a5  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c1ac  nop     dword ptr [rax+rax+00h]
0x14000c1b1  call    cs:__imp_KeLeaveCriticalRegion
0x14000c1b8  nop     dword ptr [rax+rax+00h]
0x14000c1bd  call    cs:__imp_KeEnterCriticalRegion
0x14000c1c4  nop     dword ptr [rax+rax+00h]
0x14000c1c9  xor     edx, edx
0x14000c1cb  mov     rcx, rdi
0x14000c1ce  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c1d5  nop     dword ptr [rax+rax+00h]
0x14000c1da  mov     rdx, rbx
0x14000c1dd  lea     r14d, [rsi+2]
0x14000c1e1  mov     rcx, rdi
0x14000c1e4  call    BfsGetGlobalFileEntry
0x14000c1e9  mov     [rbp+4Fh+var_90], rax
0x14000c1ed  mov     rsi, rax
0x14000c1f0  test    rax, rax
0x14000c1f3  jnz     short loc_14000C26F
0x14000c1f5  mov     edx, [rbp+4Fh+arg_20]
0x14000c1f8  lea     r8, [rbp+4Fh+var_90]
0x14000c1fc  mov     rcx, rbx; SourceString
0x14000c1ff  call    BfsCreateGlobalFileEntry
0x14000c204  mov     ebx, eax
0x14000c206  test    eax, eax
0x14000c208  jns     short loc_14000C246
0x14000c20a  mov     ecx, cs:dword_140019000; int
0x14000c210  cmp     ecx, 3
0x14000c213  jbe     loc_14000C2C6
0x14000c219  mov     dword ptr [rbp+4Fh+var_90], eax
0x14000c21c  lea     rax, [rbp+4Fh+var_90]
0x14000c220  mov     [rbp+4Fh+var_58], 4
0x14000c228  mov     [rbp+4Fh+var_60], rax
0x14000c22c  lea     rdx, byte_140016D91; int
0x14000c233  lea     rax, [rbp+4Fh+var_80]
0x14000c237  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000c23c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c241  jmp     loc_14000C2C6
0x14000c246  mov     rsi, [rbp+4Fh+var_90]
0x14000c24a  mov     rdx, r12
0x14000c24d  mov     rcx, [rdi+28h]
0x14000c251  mov     r8, rsi
0x14000c254  call    BfsInsertEntryHashTable
0x14000c259  mov     ebx, eax
0x14000c25b  test    eax, eax
0x14000c25d  jns     short loc_14000C26F
0x14000c25f  mov     eax, cs:dword_140019000
0x14000c265  cmp     eax, 3
0x14000c268  jbe     short loc_14000C2C6
0x14000c26a  mov     dword ptr [rbp+4Fh+var_90], ebx
0x14000c26d  jmp     short loc_14000C21C
0x14000c26f  mov     r9, [rbp+4Fh+var_88]
0x14000c273  mov     r8, r13
0x14000c276  mov     rdx, rsi
0x14000c279  mov     rcx, rdi
0x14000c27c  call    BfsUpdateGlobalFilePolicy
0x14000c281  mov     ebx, eax
0x14000c283  test    eax, eax
0x14000c285  jns     short loc_14000C2C0
0x14000c287  mov     eax, cs:dword_140019000
0x14000c28d  cmp     eax, 3
0x14000c290  jbe     loc_14000C31A
0x14000c296  lea     rax, [rbp+4Fh+var_90]
0x14000c29a  mov     dword ptr [rbp+4Fh+var_90], ebx
0x14000c29d  mov     [rbp+4Fh+var_60], rax
0x14000c2a1  lea     rdx, byte_140016D91; int
0x14000c2a8  lea     rax, [rbp+4Fh+var_80]
0x14000c2ac  mov     [rbp+4Fh+var_58], 4
0x14000c2b4  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000c2b9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c2be  jmp     short loc_14000C31A
0x14000c2c0  cmp     r14d, 2
0x14000c2c4  jnz     short loc_14000C2D9
0x14000c2c6  xor     edx, edx
0x14000c2c8  mov     rcx, rdi
0x14000c2cb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c2d2  nop     dword ptr [rax+rax+00h]
0x14000c2d7  jmp     short loc_14000C2F0
0x14000c2d9  cmp     r14d, 1
0x14000c2dd  jnz     short loc_14000C2FC
0x14000c2df  xor     edx, edx
0x14000c2e1  mov     rcx, rdi
0x14000c2e4  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c2eb  nop     dword ptr [rax+rax+00h]
0x14000c2f0  call    cs:__imp_KeLeaveCriticalRegion
0x14000c2f7  nop     dword ptr [rax+rax+00h]
0x14000c2fc  xor     edx, edx
0x14000c2fe  lea     rcx, [rdi+8]
0x14000c302  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c309  nop     dword ptr [rax+rax+00h]
0x14000c30e  call    cs:__imp_KeLeaveCriticalRegion
0x14000c315  nop     dword ptr [rax+rax+00h]
0x14000c31a  mov     eax, ebx
0x14000c31c  mov     rcx, [rbp+4Fh+var_50]
0x14000c320  xor     rcx, rsp; StackCookie
0x14000c323  call    __security_check_cookie
0x14000c328  add     rsp, 88h
0x14000c32f  pop     r15
0x14000c331  pop     r14
0x14000c333  pop     r13
0x14000c335  pop     r12
0x14000c337  pop     rdi
0x14000c338  pop     rsi
0x14000c339  pop     rbx
0x14000c33a  pop     rbp
0x14000c33b  retn
```
