# UpdateTableNode

- ea: `0x14001af3c`
- end: `0x14001b644`
- name: `UpdateTableNode`
- size: `1800`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140015e28`
- `0x14001ba60`
- `0x14001c3d0`

## callees

- `0x140005bb0`
- `0x140006000`
- `0x140015bb0`
- `0x140016114`
- `0x14001af3c`
- `0x14001cb30`
- `0x14001cd14`
- `0x14001ce44`
- `0x14001d010`
- `0x14001d480`
- `0x14001dd40`
- `0x14001ddc4`
- `0x14001e580`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001b493`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b533`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b493`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b533`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b46d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b4b7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b46d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b4b7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b116`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b1da`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b3ed`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b608`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b116`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b1da`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b3ed`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b608`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b074`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b2cb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b57d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b5b3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b074`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b2cb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b57d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b5b3`
- `ntoskrnl!ExAllocatePool2` at `0x14001b14e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b331`
- `ntoskrnl!ExAllocatePool2` at `0x14001b14e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b331`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b192`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b37b`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b402`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b192`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b37b`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b402`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b176`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b35c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b3a7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b4a4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b176`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b35c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b3a7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b4a4`

## pseudocode

```c
__int64 __fastcall UpdateTableNode(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdi
  struct _UNICODE_STRING *v5; // r12
  __int64 v6; // r13
  struct _UNICODE_STRING *v7; // r15
  bool v8; // r14
  LONG v9; // esi
  PWSTR Buffer; // rax
  __int64 v11; // rsi
  int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // rsi
  WCHAR *v15; // rsi
  int v16; // esi
  __int16 v17; // ax
  __int16 v19; // ax
  __int64 Pool2; // rsi
  WCHAR *v21; // rsi
  __int64 v22; // rsi
  __int64 v23; // rcx
  const UNICODE_STRING *v24; // rax
  const UNICODE_STRING *v25; // rsi
  bool v26; // [rsp+40h] [rbp-C0h]
  _BYTE v27[3]; // [rsp+41h] [rbp-BFh] BYREF
  int Length; // [rsp+44h] [rbp-BCh] BYREF
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String1; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  PWSTR v33; // [rsp+80h] [rbp-80h]
  LONG v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v36; // [rsp+98h] [rbp-68h]
  _QWORD v37[22]; // [rsp+A0h] [rbp-60h] BYREF

  v36 = a2;
  v31 = 0;
  v27[0] = 0;
  LODWORD(v33) = 0;
  v4 = 0;
  String1 = 0;
  SourceString = 0;
  v32 = 0;
  memset(v37, 0, sizeof(v37));
  v5 = (struct _UNICODE_STRING *)(a1 + 80);
  v6 = *(_QWORD *)(a1 + 32);
  if ( *(_DWORD *)(a1 + 256) == 2 )
  {
    if ( GetVolumeRootFileId(a1, &v37[12]) < 0 )
      return a1;
    v4 = v37;
    goto LABEL_8;
  }
  if ( (*(_BYTE *)(v6 + 30) & 1) != 0 && (*(_DWORD *)(v6 + 24) & 0x410) == 0x10 )
  {
    if ( a2 )
    {
      v4 = a2;
    }
    else
    {
      if ( (int)GetFileInformation(v6, a1 + 80, v37) < 0 )
        return a1;
      v4 = v31;
    }
  }
  if ( v4 )
  {
LABEL_8:
    if ( *(_DWORD *)(a1 + 256) <= 2u )
    {
      v16 = *(_DWORD *)(a1 + 24);
LABEL_26:
      if ( (*(_BYTE *)(a1 + 30) & 0x10) == 0 )
        goto LABEL_27;
      if ( *(_QWORD *)(a1 + 176) != v4[12] )
        RemoveFileIdTableNode(a1);
      if ( (*(_BYTE *)(a1 + 30) & 0x10) == 0 )
      {
LABEL_27:
        *(_QWORD *)(a1 + 176) = v4[12];
        InsertFileIdTableNode(a1);
      }
      v17 = *(_WORD *)(a1 + 30);
      *(_DWORD *)(a1 + 24) = v16;
      *(_WORD *)(a1 + 30) = v17 & 0xFF7E | 1;
      goto LABEL_29;
    }
    String1.Length = *((_WORD *)v4 + 30);
    v7 = (struct _UNICODE_STRING *)(a1 + 128);
    String1.MaximumLength = String1.Length;
    v8 = 1;
    String1.Buffer = (PWSTR)(v4 + 13);
    SourceString.Length = *((char *)v4 + 68);
    SourceString.MaximumLength = SourceString.Length;
    SourceString.Buffer = (PWSTR)v4 + 35;
    LODWORD(v31) = *((_DWORD *)v4 + 14);
    v34 = RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(a1 + 80), 1u);
    v9 = v34;
    v26 = v34 != 0;
    if ( SourceString.Length )
    {
      if ( (*(_BYTE *)(a1 + 30) & 8) != 0 )
        v8 = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 128), &SourceString, 1u) != 0;
    }
    else
    {
      v8 = 0;
    }
    if ( v9 )
    {
      *((_QWORD *)&v32 + 1) = *(_QWORD *)&String1.Length;
      Buffer = String1.Buffer;
    }
    else
    {
      if ( !v8 )
        goto LABEL_14;
      *((_QWORD *)&v32 + 1) = *(_QWORD *)&SourceString.Length;
      Buffer = SourceString.Buffer;
    }
    v35 = 0;
    Length = 0;
    v33 = Buffer;
    v11 = LuafvLookupElementTableFull(*(_QWORD *)(v6 + 40), &v32, &v35, &Length);
    if ( v11 )
    {
      v22 = v11 - ((*(_BYTE *)(v11 + 24) & 7) != 0 ? 96LL : 48LL);
      ExAcquireFastMutex(&FastMutex);
      if ( *(struct _KTHREAD **)(v22 + 8) == KeGetCurrentThread() )
      {
        ++*(_DWORD *)(v22 + 16);
      }
      else
      {
        ExReleaseFastMutex(&FastMutex);
        FltAcquirePushLockExclusiveEx(v22, 0);
        ExAcquireFastMutex(&FastMutex);
        *(_QWORD *)(v22 + 8) = KeGetCurrentThread();
        *(_DWORD *)(v22 + 16) = 1;
      }
      ExReleaseFastMutex(&FastMutex);
      if ( v34 )
      {
        v23 = v22;
        v22 = a1;
      }
      else
      {
        v23 = a1;
      }
      v24 = (const UNICODE_STRING *)ResolveTableNodeConflict(v23, v22);
      v25 = v24;
      if ( v24 != (const UNICODE_STRING *)a1 )
      {
        v5 = (struct _UNICODE_STRING *)&v24[5];
        a1 = (__int64)v24;
        v7 = (struct _UNICODE_STRING *)&v24[8];
        v8 = 0;
        v26 = RtlCompareUnicodeString(&String1, v24 + 5, 1u) != 0;
        if ( SourceString.Length )
          v8 = (*(_BYTE *)(a1 + 30) & 8) == 0 || RtlCompareUnicodeString(v7, &SourceString, 1u) != 0;
        HIWORD(v25[1].Buffer) |= 0x80u;
      }
    }
LABEL_14:
    if ( (*(_BYTE *)(a1 + 30) & 8) != 0 && (v8 || !SourceString.Length) )
    {
      LuafvDeleteElementTable(*(PRTL_SPLAY_LINKS **)(v6 + 40), (PRTL_SPLAY_LINKS)(a1 + 96));
      *(_WORD *)(a1 + 30) &= ~8u;
    }
    if ( v26 )
    {
      Length = String1.Length;
      Pool2 = ExAllocatePool2(256, (unsigned int)String1.Length + 8, 1717663052);
      if ( !Pool2 )
        goto LABEL_29;
      *(_DWORD *)Pool2 = Length;
      *(_BYTE *)(Pool2 + 4) = -1;
      FltAcquirePushLockExclusiveEx(&PoolLock, 0);
      dword_14000ECBC += Length;
      FltReleasePushLockEx(&PoolLock, 0);
      v21 = (WCHAR *)(Pool2 + 8);
      if ( !v21 )
        goto LABEL_29;
      LuafvDeleteElementTable(*(PRTL_SPLAY_LINKS **)(v6 + 40), (PRTL_SPLAY_LINKS)(a1 + 48));
      FltAcquirePushLockExclusiveEx(&qword_14000EC60, 0);
      if ( (*(_BYTE *)(a1 + 30) & 0x20) != 0 )
      {
        LuafvFreePool(v5->Buffer);
        v5->Buffer = 0;
        *(_WORD *)(a1 + 30) &= ~0x20u;
      }
      v5->MaximumLength = String1.Length;
      v5->Buffer = v21;
      RtlCopyUnicodeString(v5, &String1);
      FltReleasePushLockEx(&qword_14000EC60, 0);
      LuafvInsertElementTable(*(_QWORD *)(v6 + 40), a1 + 48, v27);
      *(_WORD *)(a1 + 30) |= 0x20u;
      *(_BYTE *)(a1 + 29) ^= (LuafvIsExcludedName(&String1) ^ *(_BYTE *)(a1 + 29)) & 1;
    }
    else
    {
      RtlCopyUnicodeString(v5, &String1);
    }
    if ( !v8 )
    {
      if ( (*(_BYTE *)(a1 + 30) & 8) != 0 )
        RtlCopyUnicodeString(v7, &SourceString);
      goto LABEL_25;
    }
    v12 = SourceString.Length;
    v13 = ExAllocatePool2(256, (unsigned int)SourceString.Length + 8, 1717663052);
    v14 = v13;
    if ( v13 )
    {
      *(_DWORD *)v13 = v12;
      *(_BYTE *)(v13 + 4) = -1;
      FltAcquirePushLockExclusiveEx(&PoolLock, 0);
      dword_14000ECBC += v12;
      FltReleasePushLockEx(&PoolLock, 0);
      v15 = (WCHAR *)(v14 + 8);
      if ( v15 )
      {
        if ( (*(_BYTE *)(a1 + 30) & 0x40) != 0 )
        {
          LuafvFreePool(v7->Buffer);
          v7->Buffer = 0;
          *(_WORD *)(a1 + 30) &= ~0x40u;
        }
        v7->MaximumLength = SourceString.Length;
        v7->Buffer = v15;
        RtlCopyUnicodeString(v7, &SourceString);
        LuafvInsertElementTable(*(_QWORD *)(v6 + 40), a1 + 96, v27);
        *(_WORD *)(a1 + 30) |= 0x48u;
LABEL_25:
        v16 = (int)v31;
        goto LABEL_26;
      }
    }
LABEL_29:
    if ( v4 != v36 && v4 != v37 )
      LuafvFreePool(v4);
    return a1;
  }
  if ( (*(_BYTE *)(a1 + 30) & 0x10) != 0 )
    RemoveFileIdTableNode(a1);
  v19 = *(_WORD *)(a1 + 30);
  if ( (v19 & 8) != 0 )
  {
    LuafvDeleteElementTable(*(PRTL_SPLAY_LINKS **)(v6 + 40), (PRTL_SPLAY_LINKS)(a1 + 96));
    v19 = *(_WORD *)(a1 + 30) & 0xFFF7;
  }
  *(_DWORD *)(a1 + 24) = 0;
  *(_WORD *)(a1 + 30) = v19 & 0xFF7E;
  return a1;
}

```

## disassembly

```asm
0x14001af3c  mov     [rsp-8+arg_18], rbx
0x14001af41  push    rbp
0x14001af42  push    rsi
0x14001af43  push    rdi
0x14001af44  push    r12
0x14001af46  push    r13
0x14001af48  push    r14
0x14001af4a  push    r15
0x14001af4c  lea     rbp, [rsp-60h]
0x14001af51  sub     rsp, 160h
0x14001af58  mov     rax, cs:__security_cookie
0x14001af5f  xor     rax, rsp
0x14001af62  mov     [rbp+90h+var_40], rax
0x14001af66  xor     r15d, r15d
0x14001af69  mov     [rbp+90h+var_F8], rdx
0x14001af6d  xorps   xmm0, xmm0
0x14001af70  mov     [rsp+190h+var_128], r15
0x14001af75  mov     rsi, r8
0x14001af78  mov     [rsp+190h+var_14F], r15b
0x14001af7d  mov     r14, rdx
0x14001af80  mov     rbx, rcx
0x14001af83  xorps   xmm1, xmm1
0x14001af86  lea     rcx, [rbp+90h+var_F0]; void *
0x14001af8a  xor     eax, eax
0x14001af8c  xor     edx, edx; Val
0x14001af8e  mov     r8d, 0B0h; Size
0x14001af94  mov     dword ptr [rbp+90h+var_110], eax
0x14001af97  mov     edi, r15d
0x14001af9a  movups  xmmword ptr [rsp+190h+String1.Length], xmm0
0x14001af9f  movups  xmmword ptr [rsp+190h+SourceString.Length], xmm1
0x14001afa4  movups  [rsp+190h+var_120], xmm0
0x14001afa9  call    memset
0x14001afae  cmp     dword ptr [rbx+100h], 2
0x14001afb5  lea     r12, [rbx+50h]
0x14001afb9  mov     r13, [rbx+20h]
0x14001afbd  jz      loc_14001B4D9
0x14001afc3  test    byte ptr [r13+1Eh], 1
0x14001afc8  jz      short loc_14001B011
0x14001afca  mov     eax, [r13+18h]
0x14001afce  and     eax, 410h
0x14001afd3  cmp     eax, 10h
0x14001afd6  jnz     short loc_14001B011
0x14001afd8  test    r14, r14
0x14001afdb  jnz     loc_14001B4F6
0x14001afe1  mov     [rsp+190h+var_160], rsi
0x14001afe6  lea     rax, [rsp+190h+var_128]
0x14001afeb  mov     [rsp+190h+var_168], r15
0x14001aff0  lea     r8, [rbp+90h+var_F0]
0x14001aff4  mov     rdx, r12
0x14001aff7  mov     [rsp+190h+var_170], rax
0x14001affc  mov     rcx, r13
0x14001afff  call    GetFileInformation
0x14001b004  test    eax, eax
0x14001b006  js      loc_14001B254
0x14001b00c  mov     rdi, [rsp+190h+var_128]
0x14001b011  test    rdi, rdi
0x14001b014  jz      loc_14001B2E4
0x14001b01a  cmp     dword ptr [rbx+100h], 2
0x14001b021  jbe     loc_14001B2AE
0x14001b027  movzx   eax, word ptr [rdi+3Ch]
0x14001b02b  lea     rcx, [rsp+190h+String1]; String1
0x14001b030  mov     [rsp+190h+String1.Length], ax
0x14001b035  lea     r15, [rbx+80h]
0x14001b03c  mov     [rsp+190h+String1.MaximumLength], ax
0x14001b041  mov     r14d, 1
0x14001b047  lea     rax, [rdi+68h]
0x14001b04b  mov     r8b, r14b; CaseInSensitive
0x14001b04e  mov     [rsp+190h+String1.Buffer], rax
0x14001b053  mov     rdx, r12; String2
0x14001b056  movsx   eax, byte ptr [rdi+44h]
0x14001b05a  mov     [rsp+190h+SourceString.Length], ax
0x14001b05f  mov     [rsp+190h+SourceString.MaximumLength], ax
0x14001b064  lea     rax, [rdi+46h]
0x14001b068  mov     [rsp+190h+SourceString.Buffer], rax
0x14001b06d  mov     eax, [rdi+38h]
0x14001b070  mov     dword ptr [rsp+190h+var_128], eax
0x14001b074  call    cs:__imp_RtlCompareUnicodeString
0x14001b07b  nop     dword ptr [rax+rax+00h]
0x14001b080  xor     edx, edx
0x14001b082  mov     [rbp+90h+var_108], eax
0x14001b085  test    eax, eax
0x14001b087  mov     esi, eax
0x14001b089  setnz   al
0x14001b08c  mov     [rsp+190h+var_150], al
0x14001b090  cmp     [rsp+190h+SourceString.Length], dx
0x14001b095  jnz     loc_14001B2B6
0x14001b09b  mov     r14b, dl
0x14001b09e  test    esi, esi
0x14001b0a0  jz      loc_14001B27F
0x14001b0a6  movzx   eax, [rsp+190h+String1.Length]
0x14001b0ab  mov     word ptr [rsp+190h+var_120+8], ax
0x14001b0b0  movzx   eax, [rsp+190h+String1.MaximumLength]
0x14001b0b5  mov     word ptr [rsp+190h+var_120+0Ah], ax
0x14001b0ba  mov     eax, dword ptr [rsp+190h+String1+4]
0x14001b0be  mov     dword ptr [rsp+190h+var_120+0Ch], eax
0x14001b0c2  mov     rax, [rsp+190h+String1.Buffer]
0x14001b0c7  mov     [rbp+90h+var_100], rdx
0x14001b0cb  lea     r9, [rsp+190h+var_14C]
0x14001b0d0  mov     [rsp+190h+var_14C], edx
0x14001b0d4  lea     r8, [rbp+90h+var_100]
0x14001b0d8  mov     [rbp+90h+var_110], rax
0x14001b0dc  lea     rdx, [rsp+190h+var_120]
0x14001b0e1  mov     rcx, [r13+28h]
0x14001b0e5  call    LuafvLookupElementTableFull
0x14001b0ea  mov     rsi, rax
0x14001b0ed  test    rax, rax
0x14001b0f0  jnz     loc_14001B452
0x14001b0f6  test    byte ptr [rbx+1Eh], 8
0x14001b0fa  mov     sil, [rsp+190h+var_150]
0x14001b0ff  jnz     loc_14001B5D3
0x14001b105  test    sil, sil
0x14001b108  jnz     loc_14001B30F
0x14001b10e  lea     rdx, [rsp+190h+String1]; SourceString
0x14001b113  mov     rcx, r12; DestinationString
0x14001b116  call    cs:__imp_RtlCopyUnicodeString
0x14001b11d  nop     dword ptr [rax+rax+00h]
0x14001b122  xor     r12d, r12d
0x14001b125  test    r14b, r14b
0x14001b128  jz      loc_14001B1FF
0x14001b12e  movzx   r14d, [rsp+190h+SourceString.Length]
0x14001b134  lea     eax, [r14+8]
0x14001b138  cmp     eax, 8
0x14001b13b  jb      loc_14001B241
0x14001b141  mov     edx, eax
0x14001b143  mov     ecx, 100h
0x14001b148  mov     r8d, 6661754Ch
0x14001b14e  call    cs:__imp_ExAllocatePool2
0x14001b155  nop     dword ptr [rax+rax+00h]
0x14001b15a  mov     rsi, rax
0x14001b15d  test    rax, rax
0x14001b160  jz      loc_14001B241
0x14001b166  xor     edx, edx
0x14001b168  mov     [rax], r14d
0x14001b16b  lea     rcx, PoolLock
0x14001b172  mov     byte ptr [rax+4], 0FFh
0x14001b176  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b17d  nop     dword ptr [rax+rax+00h]
0x14001b182  add     cs:dword_14000ECBC, r14d
0x14001b189  lea     rcx, PoolLock
0x14001b190  xor     edx, edx
0x14001b192  call    cs:__imp_FltReleasePushLockEx
0x14001b199  nop     dword ptr [rax+rax+00h]
0x14001b19e  add     rsi, 8
0x14001b1a2  jz      loc_14001B241
0x14001b1a8  test    byte ptr [rbx+1Eh], 40h
0x14001b1ac  jz      short loc_14001B1C4
0x14001b1ae  mov     rcx, [r15+8]
0x14001b1b2  call    LuafvFreePool
0x14001b1b7  mov     eax, 0FFBFh
0x14001b1bc  mov     [r15+8], r12
0x14001b1c0  and     [rbx+1Eh], ax
0x14001b1c4  movzx   eax, [rsp+190h+SourceString.Length]
0x14001b1c9  lea     rdx, [rsp+190h+SourceString]; SourceString
0x14001b1ce  mov     rcx, r15; DestinationString
0x14001b1d1  mov     [r15+2], ax
0x14001b1d6  mov     [r15+8], rsi
0x14001b1da  call    cs:__imp_RtlCopyUnicodeString
0x14001b1e1  nop     dword ptr [rax+rax+00h]
0x14001b1e6  mov     rcx, [r13+28h]
0x14001b1ea  lea     rdx, [rbx+60h]
0x14001b1ee  lea     r8, [rsp+190h+var_14F]
0x14001b1f3  call    LuafvInsertElementTable
0x14001b1f8  or      word ptr [rbx+1Eh], 48h
0x14001b1fd  jmp     short loc_14001B209
0x14001b1ff  test    byte ptr [rbx+1Eh], 8
0x14001b203  jnz     loc_14001B600
0x14001b209  mov     esi, dword ptr [rsp+190h+var_128]
0x14001b20d  test    byte ptr [rbx+1Eh], 10h
0x14001b211  jnz     loc_14001B619
0x14001b217  mov     rax, [rdi+60h]
0x14001b21b  mov     rcx, rbx
0x14001b21e  mov     [rbx+0B0h], rax
0x14001b225  call    InsertFileIdTableNode
0x14001b22a  movzx   eax, word ptr [rbx+1Eh]
0x14001b22e  mov     ecx, 0FF7Fh
0x14001b233  and     ax, cx
0x14001b236  mov     [rbx+18h], esi
0x14001b239  or      ax, 1
0x14001b23d  mov     [rbx+1Eh], ax
0x14001b241  cmp     rdi, [rbp+90h+var_F8]
0x14001b245  jz      short loc_14001B254
0x14001b247  lea     rax, [rbp+90h+var_F0]
0x14001b24b  cmp     rdi, rax
0x14001b24e  jnz     loc_14001B637
0x14001b254  mov     rax, rbx
0x14001b257  mov     rcx, [rbp+90h+var_40]
0x14001b25b  xor     rcx, rsp; StackCookie
0x14001b25e  call    __security_check_cookie
0x14001b263  mov     rbx, [rsp+190h+arg_18]
0x14001b26b  add     rsp, 160h
0x14001b272  pop     r15
0x14001b274  pop     r14
0x14001b276  pop     r13
0x14001b278  pop     r12
0x14001b27a  pop     rdi
0x14001b27b  pop     rsi
0x14001b27c  pop     rbp
0x14001b27d  retn
0x14001b27f  test    r14b, r14b
0x14001b282  jz      loc_14001B0F6
0x14001b288  movzx   eax, [rsp+190h+SourceString.Length]
0x14001b28d  mov     word ptr [rsp+190h+var_120+8], ax
0x14001b292  movzx   eax, [rsp+190h+SourceString.MaximumLength]
0x14001b297  mov     word ptr [rsp+190h+var_120+0Ah], ax
0x14001b29c  mov     eax, dword ptr [rsp+190h+SourceString+4]
0x14001b2a0  mov     dword ptr [rsp+190h+var_120+0Ch], eax
0x14001b2a4  mov     rax, [rsp+190h+SourceString.Buffer]
0x14001b2a9  jmp     loc_14001B0C7
0x14001b2ae  mov     esi, [rbx+18h]
0x14001b2b1  jmp     loc_14001B20D
0x14001b2b6  test    byte ptr [rbx+1Eh], 8
0x14001b2ba  jz      loc_14001B09E
0x14001b2c0  mov     r8b, r14b; CaseInSensitive
0x14001b2c3  lea     rdx, [rsp+190h+SourceString]; String2
0x14001b2c8  mov     rcx, r15; String1
0x14001b2cb  call    cs:__imp_RtlCompareUnicodeString
0x14001b2d2  nop     dword ptr [rax+rax+00h]
0x14001b2d7  xor     edx, edx
0x14001b2d9  test    eax, eax
0x14001b2db  setnz   r14b
0x14001b2df  jmp     loc_14001B09E
0x14001b2e4  test    byte ptr [rbx+1Eh], 10h
0x14001b2e8  jnz     loc_14001B4FE
0x14001b2ee  movzx   eax, word ptr [rbx+1Eh]
0x14001b2f2  test    al, 8
0x14001b2f4  jnz     loc_14001B50B
0x14001b2fa  mov     ecx, 0FF7Eh
0x14001b2ff  mov     [rbx+18h], r15d
0x14001b303  and     ax, cx
0x14001b306  mov     [rbx+1Eh], ax
0x14001b30a  jmp     loc_14001B254
0x14001b30f  movzx   eax, [rsp+190h+String1.Length]
0x14001b314  mov     [rsp+190h+var_14C], eax
0x14001b318  add     eax, 8
0x14001b31b  cmp     eax, 8
0x14001b31e  jb      loc_14001B241
0x14001b324  mov     edx, eax
0x14001b326  mov     ecx, 100h
0x14001b32b  mov     r8d, 6661754Ch
0x14001b331  call    cs:__imp_ExAllocatePool2
0x14001b338  nop     dword ptr [rax+rax+00h]
0x14001b33d  mov     rsi, rax
0x14001b340  test    rax, rax
0x14001b343  jz      loc_14001B241
0x14001b349  mov     eax, [rsp+190h+var_14C]
0x14001b34d  lea     rcx, PoolLock
0x14001b354  xor     edx, edx
0x14001b356  mov     [rsi], eax
0x14001b358  mov     byte ptr [rsi+4], 0FFh
0x14001b35c  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b363  nop     dword ptr [rax+rax+00h]
0x14001b368  mov     eax, [rsp+190h+var_14C]
0x14001b36c  lea     rcx, PoolLock
0x14001b373  add     cs:dword_14000ECBC, eax
0x14001b379  xor     edx, edx
0x14001b37b  call    cs:__imp_FltReleasePushLockEx
0x14001b382  nop     dword ptr [rax+rax+00h]
0x14001b387  add     rsi, 8
0x14001b38b  jz      loc_14001B241
0x14001b391  mov     rcx, [r13+28h]; Root
0x14001b395  lea     rdx, [rbx+30h]; Links
0x14001b399  call    LuafvDeleteElementTable
0x14001b39e  xor     edx, edx
0x14001b3a0  lea     rcx, qword_14000EC60
0x14001b3a7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b3ae  nop     dword ptr [rax+rax+00h]
0x14001b3b3  test    byte ptr [rbx+1Eh], 20h
0x14001b3b7  jz      short loc_14001B3D5
0x14001b3b9  mov     rcx, [r12+8]
0x14001b3be  call    LuafvFreePool
0x14001b3c3  mov     eax, 0FFDFh
0x14001b3c8  mov     qword ptr [r12+8], 0
0x14001b3d1  and     [rbx+1Eh], ax
0x14001b3d5  movzx   eax, [rsp+190h+String1.Length]
0x14001b3da  lea     rdx, [rsp+190h+String1]; SourceString
0x14001b3df  mov     rcx, r12; DestinationString
0x14001b3e2  mov     [r12+2], ax
0x14001b3e8  mov     [r12+8], rsi
0x14001b3ed  call    cs:__imp_RtlCopyUnicodeString
0x14001b3f4  nop     dword ptr [rax+rax+00h]
0x14001b3f9  xor     edx, edx
0x14001b3fb  lea     rcx, qword_14000EC60
0x14001b402  call    cs:__imp_FltReleasePushLockEx
0x14001b409  nop     dword ptr [rax+rax+00h]
0x14001b40e  mov     rcx, [r13+28h]
0x14001b412  lea     r8, [rsp+190h+var_14F]
0x14001b417  lea     rdx, [rbx+30h]
0x14001b41b  call    LuafvInsertElementTable
0x14001b420  or      word ptr [rbx+1Eh], 20h
0x14001b425  lea     rcx, [rsp+190h+String1]
0x14001b42a  call    LuafvIsExcludedName
0x14001b42f  mov     cl, [rbx+1Dh]
0x14001b432  mov     dl, cl
0x14001b434  xor     dl, al
0x14001b436  and     dl, 1
0x14001b439  xor     dl, cl
0x14001b43b  mov     [rbx+1Dh], dl
0x14001b43e  jmp     loc_14001B122
0x14001b443  test    byte ptr [rbx+1Eh], 10h
0x14001b447  jnz     loc_14001B22A
  ... truncated ...
```
