# UpdateTableNode

- ea: `0x14001af8c`
- end: `0x14001b694`
- name: `UpdateTableNode`
- size: `1800`
- prototype: `__int64 __fastcall(__int64, _QWORD *, void **)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140015e28`
- `0x14001bab0`
- `0x14001c420`

## callees

- `0x140005f30`
- `0x140006380`
- `0x140015bb0`
- `0x140016114`
- `0x14001af8c`
- `0x14001cb80`
- `0x14001cd64`
- `0x14001ce94`
- `0x14001d060`
- `0x14001d4d0`
- `0x14001dd90`
- `0x14001de14`
- `0x14001e5d0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14001b4e3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b583`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b4e3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b583`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b4bd`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b507`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b4bd`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b507`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b166`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b22a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b43d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b658`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b166`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b22a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b43d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001b658`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b0c4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b31b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b5cd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b603`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b0c4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b31b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b5cd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b603`
- `ntoskrnl!ExAllocatePool2` at `0x14001b19e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b381`
- `ntoskrnl!ExAllocatePool2` at `0x14001b19e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b381`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b1e2`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b3cb`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b452`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b1e2`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b3cb`
- `FLTMGR!FltReleasePushLockEx` at `0x14001b452`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b1c6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b3ac`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b3f7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b4f4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b1c6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b3ac`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b3f7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001b4f4`

## pseudocode

```c
__int64 __fastcall UpdateTableNode(__int64 a1, _QWORD *a2, void **a3)
{
  _QWORD *v6; // rdi
  __int64 v7; // r9
  UNICODE_STRING *v8; // r12
  __int64 v9; // r13
  UNICODE_STRING *v10; // r15
  bool v11; // r14
  LONG v12; // esi
  PWSTR Buffer; // rax
  __int64 v14; // rsi
  int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rsi
  WCHAR *v18; // rsi
  int v19; // esi
  __int16 v20; // ax
  __int16 v22; // ax
  __int64 Pool2; // rsi
  __int64 v24; // rsi
  __int64 v25; // rsi
  __int64 v26; // rcx
  const UNICODE_STRING *v27; // rax
  const UNICODE_STRING *v28; // rsi
  bool v29; // [rsp+40h] [rbp-C0h]
  _BYTE v30[3]; // [rsp+41h] [rbp-BFh] BYREF
  int Length; // [rsp+44h] [rbp-BCh] BYREF
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String1; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v34; // [rsp+68h] [rbp-98h] BYREF
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  PWSTR v36; // [rsp+80h] [rbp-80h]
  LONG v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v39; // [rsp+98h] [rbp-68h]
  _QWORD v40[22]; // [rsp+A0h] [rbp-60h] BYREF

  v39 = a2;
  v34 = 0;
  v30[0] = 0;
  LODWORD(v36) = 0;
  v6 = 0;
  String1 = 0;
  SourceString = 0;
  v35 = 0;
  memset(v40, 0, sizeof(v40));
  v8 = (UNICODE_STRING *)(a1 + 80);
  v9 = *(_QWORD *)(a1 + 32);
  if ( *(_DWORD *)(a1 + 256) == 2 )
  {
    if ( GetVolumeRootFileId((struct _UNICODE_STRING *)a1, &v40[12]) < 0 )
      return a1;
    v6 = v40;
    goto LABEL_8;
  }
  if ( (*(_BYTE *)(v9 + 30) & 1) != 0 && (*(_DWORD *)(v9 + 24) & 0x410) == 0x10 )
  {
    if ( a2 )
    {
      v6 = a2;
    }
    else
    {
      if ( (int)GetFileInformation(v9, (struct _UNICODE_STRING *)(a1 + 80), v40, v7, &v34, 0, a3) < 0 )
        return a1;
      v6 = v34;
    }
  }
  if ( v6 )
  {
LABEL_8:
    if ( *(_DWORD *)(a1 + 256) <= 2u )
    {
      v19 = *(_DWORD *)(a1 + 24);
LABEL_26:
      if ( (*(_BYTE *)(a1 + 30) & 0x10) == 0 )
        goto LABEL_27;
      if ( *(_QWORD *)(a1 + 176) != v6[12] )
        RemoveFileIdTableNode(a1);
      if ( (*(_BYTE *)(a1 + 30) & 0x10) == 0 )
      {
LABEL_27:
        *(_QWORD *)(a1 + 176) = v6[12];
        InsertFileIdTableNode(a1);
      }
      v20 = *(_WORD *)(a1 + 30);
      *(_DWORD *)(a1 + 24) = v19;
      *(_WORD *)(a1 + 30) = v20 & 0xFF7E | 1;
      goto LABEL_29;
    }
    String1.Length = *((_WORD *)v6 + 30);
    v10 = (UNICODE_STRING *)(a1 + 128);
    String1.MaximumLength = String1.Length;
    v11 = 1;
    String1.Buffer = (PWSTR)(v6 + 13);
    SourceString.Length = *((char *)v6 + 68);
    SourceString.MaximumLength = SourceString.Length;
    SourceString.Buffer = (PWSTR)v6 + 35;
    LODWORD(v34) = *((_DWORD *)v6 + 14);
    v37 = RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(a1 + 80), 1u);
    v12 = v37;
    v29 = v37 != 0;
    if ( SourceString.Length )
    {
      if ( (*(_BYTE *)(a1 + 30) & 8) != 0 )
        v11 = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 128), &SourceString, 1u) != 0;
    }
    else
    {
      v11 = 0;
    }
    if ( v12 )
    {
      *((_QWORD *)&v35 + 1) = *(_QWORD *)&String1.Length;
      Buffer = String1.Buffer;
    }
    else
    {
      if ( !v11 )
        goto LABEL_14;
      *((_QWORD *)&v35 + 1) = *(_QWORD *)&SourceString.Length;
      Buffer = SourceString.Buffer;
    }
    v38 = 0;
    Length = 0;
    v36 = Buffer;
    v14 = LuafvLookupElementTableFull(*(PRTL_SPLAY_LINKS **)(v9 + 40), (__int64)&v35, (__int64)&v38, &Length);
    if ( v14 )
    {
      v25 = v14 - ((*(_BYTE *)(v14 + 24) & 7) != 0 ? 96LL : 48LL);
      ExAcquireFastMutex(&FastMutex);
      if ( *(struct _KTHREAD **)(v25 + 8) == KeGetCurrentThread() )
      {
        ++*(_DWORD *)(v25 + 16);
      }
      else
      {
        ExReleaseFastMutex(&FastMutex);
        FltAcquirePushLockExclusiveEx(v25, 0);
        ExAcquireFastMutex(&FastMutex);
        *(_QWORD *)(v25 + 8) = KeGetCurrentThread();
        *(_DWORD *)(v25 + 16) = 1;
      }
      ExReleaseFastMutex(&FastMutex);
      if ( v37 )
      {
        v26 = v25;
        v25 = a1;
      }
      else
      {
        v26 = a1;
      }
      v27 = (const UNICODE_STRING *)ResolveTableNodeConflict(v26, v25);
      v28 = v27;
      if ( v27 != (const UNICODE_STRING *)a1 )
      {
        v8 = (UNICODE_STRING *)&v27[5];
        a1 = (__int64)v27;
        v10 = (UNICODE_STRING *)&v27[8];
        v11 = 0;
        v29 = RtlCompareUnicodeString(&String1, v27 + 5, 1u) != 0;
        if ( SourceString.Length )
          v11 = (*(_BYTE *)(a1 + 30) & 8) == 0 || RtlCompareUnicodeString(v10, &SourceString, 1u) != 0;
        HIWORD(v28[1].Buffer) |= 0x80u;
      }
    }
LABEL_14:
    if ( (*(_BYTE *)(a1 + 30) & 8) != 0 && (v11 || !SourceString.Length) )
    {
      LuafvDeleteElementTable(*(PRTL_SPLAY_LINKS **)(v9 + 40), (PRTL_SPLAY_LINKS)(a1 + 96));
      *(_WORD *)(a1 + 30) &= ~8u;
    }
    if ( v29 )
    {
      Length = String1.Length;
      Pool2 = ExAllocatePool2(256, (unsigned int)String1.Length + 8, 1717663052);
      if ( !Pool2 )
        goto LABEL_29;
      *(_DWORD *)Pool2 = Length;
      *(_BYTE *)(Pool2 + 4) = -1;
      FltAcquirePushLockExclusiveEx(&PoolLock, 0);
      dword_14000F2FC += Length;
      FltReleasePushLockEx(&PoolLock, 0);
      v24 = Pool2 + 8;
      if ( !v24 )
        goto LABEL_29;
      LuafvDeleteElementTable(*(PRTL_SPLAY_LINKS **)(v9 + 40), (PRTL_SPLAY_LINKS)(a1 + 48));
      FltAcquirePushLockExclusiveEx(&qword_14000F2A0, 0);
      if ( (*(_BYTE *)(a1 + 30) & 0x20) != 0 )
      {
        LuafvFreePool((__int64)v8->Buffer);
        v8->Buffer = 0;
        *(_WORD *)(a1 + 30) &= ~0x20u;
      }
      v8->MaximumLength = String1.Length;
      v8->Buffer = (PWSTR)v24;
      RtlCopyUnicodeString(v8, &String1);
      FltReleasePushLockEx(&qword_14000F2A0, 0);
      LuafvInsertElementTable(*(_QWORD *)(v9 + 40), a1 + 48, v30);
      *(_WORD *)(a1 + 30) |= 0x20u;
      *(_BYTE *)(a1 + 29) ^= (LuafvIsExcludedName(&String1.Length) ^ *(_BYTE *)(a1 + 29)) & 1;
    }
    else
    {
      RtlCopyUnicodeString(v8, &String1);
    }
    if ( !v11 )
    {
      if ( (*(_BYTE *)(a1 + 30) & 8) != 0 )
        RtlCopyUnicodeString(v10, &SourceString);
      goto LABEL_25;
    }
    v15 = SourceString.Length;
    v16 = ExAllocatePool2(256, (unsigned int)SourceString.Length + 8, 1717663052);
    v17 = v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = v15;
      *(_BYTE *)(v16 + 4) = -1;
      FltAcquirePushLockExclusiveEx(&PoolLock, 0);
      dword_14000F2FC += v15;
      FltReleasePushLockEx(&PoolLock, 0);
      v18 = (WCHAR *)(v17 + 8);
      if ( v18 )
      {
        if ( (*(_BYTE *)(a1 + 30) & 0x40) != 0 )
        {
          LuafvFreePool((__int64)v10->Buffer);
          v10->Buffer = 0;
          *(_WORD *)(a1 + 30) &= ~0x40u;
        }
        v10->MaximumLength = SourceString.Length;
        v10->Buffer = v18;
        RtlCopyUnicodeString(v10, &SourceString);
        LuafvInsertElementTable(*(_QWORD *)(v9 + 40), a1 + 96, v30);
        *(_WORD *)(a1 + 30) |= 0x48u;
LABEL_25:
        v19 = (int)v34;
        goto LABEL_26;
      }
    }
LABEL_29:
    if ( v6 != v39 && v6 != v40 )
      LuafvFreePool((__int64)v6);
    return a1;
  }
  if ( (*(_BYTE *)(a1 + 30) & 0x10) != 0 )
    RemoveFileIdTableNode(a1);
  v22 = *(_WORD *)(a1 + 30);
  if ( (v22 & 8) != 0 )
  {
    LuafvDeleteElementTable(*(PRTL_SPLAY_LINKS **)(v9 + 40), (PRTL_SPLAY_LINKS)(a1 + 96));
    v22 = *(_WORD *)(a1 + 30) & 0xFFF7;
  }
  *(_DWORD *)(a1 + 24) = 0;
  *(_WORD *)(a1 + 30) = v22 & 0xFF7E;
  return a1;
}

```

## disassembly

```asm
0x14001af8c  mov     [rsp-8+arg_18], rbx
0x14001af91  push    rbp
0x14001af92  push    rsi
0x14001af93  push    rdi
0x14001af94  push    r12
0x14001af96  push    r13
0x14001af98  push    r14
0x14001af9a  push    r15
0x14001af9c  lea     rbp, [rsp-60h]
0x14001afa1  sub     rsp, 160h
0x14001afa8  mov     rax, cs:__security_cookie
0x14001afaf  xor     rax, rsp
0x14001afb2  mov     [rbp+90h+var_40], rax
0x14001afb6  xor     r15d, r15d
0x14001afb9  mov     [rbp+90h+var_F8], rdx
0x14001afbd  xorps   xmm0, xmm0
0x14001afc0  mov     [rsp+190h+var_128], r15
0x14001afc5  mov     rsi, r8
0x14001afc8  mov     [rsp+190h+var_14F], r15b
0x14001afcd  mov     r14, rdx
0x14001afd0  mov     rbx, rcx
0x14001afd3  xorps   xmm1, xmm1
0x14001afd6  lea     rcx, [rbp+90h+var_F0]; void *
0x14001afda  xor     eax, eax
0x14001afdc  xor     edx, edx; Val
0x14001afde  mov     r8d, 0B0h; Size
0x14001afe4  mov     dword ptr [rbp+90h+var_110], eax
0x14001afe7  mov     edi, r15d
0x14001afea  movups  xmmword ptr [rsp+190h+String1.Length], xmm0
0x14001afef  movups  xmmword ptr [rsp+190h+SourceString.Length], xmm1
0x14001aff4  movups  [rsp+190h+var_120], xmm0
0x14001aff9  call    memset
0x14001affe  cmp     dword ptr [rbx+100h], 2
0x14001b005  lea     r12, [rbx+50h]
0x14001b009  mov     r13, [rbx+20h]
0x14001b00d  jz      loc_14001B529
0x14001b013  test    byte ptr [r13+1Eh], 1
0x14001b018  jz      short loc_14001B061
0x14001b01a  mov     eax, [r13+18h]
0x14001b01e  and     eax, 410h
0x14001b023  cmp     eax, 10h
0x14001b026  jnz     short loc_14001B061
0x14001b028  test    r14, r14
0x14001b02b  jnz     loc_14001B546
0x14001b031  mov     [rsp+190h+var_160], rsi
0x14001b036  lea     rax, [rsp+190h+var_128]
0x14001b03b  mov     [rsp+190h+var_168], r15
0x14001b040  lea     r8, [rbp+90h+var_F0]
0x14001b044  mov     rdx, r12
0x14001b047  mov     [rsp+190h+var_170], rax
0x14001b04c  mov     rcx, r13
0x14001b04f  call    GetFileInformation
0x14001b054  test    eax, eax
0x14001b056  js      loc_14001B2A4
0x14001b05c  mov     rdi, [rsp+190h+var_128]
0x14001b061  test    rdi, rdi
0x14001b064  jz      loc_14001B334
0x14001b06a  cmp     dword ptr [rbx+100h], 2
0x14001b071  jbe     loc_14001B2FE
0x14001b077  movzx   eax, word ptr [rdi+3Ch]
0x14001b07b  lea     rcx, [rsp+190h+String1]; String1
0x14001b080  mov     [rsp+190h+String1.Length], ax
0x14001b085  lea     r15, [rbx+80h]
0x14001b08c  mov     [rsp+190h+String1.MaximumLength], ax
0x14001b091  mov     r14d, 1
0x14001b097  lea     rax, [rdi+68h]
0x14001b09b  mov     r8b, r14b; CaseInSensitive
0x14001b09e  mov     [rsp+190h+String1.Buffer], rax
0x14001b0a3  mov     rdx, r12; String2
0x14001b0a6  movsx   eax, byte ptr [rdi+44h]
0x14001b0aa  mov     [rsp+190h+SourceString.Length], ax
0x14001b0af  mov     [rsp+190h+SourceString.MaximumLength], ax
0x14001b0b4  lea     rax, [rdi+46h]
0x14001b0b8  mov     [rsp+190h+SourceString.Buffer], rax
0x14001b0bd  mov     eax, [rdi+38h]
0x14001b0c0  mov     dword ptr [rsp+190h+var_128], eax
0x14001b0c4  call    cs:__imp_RtlCompareUnicodeString
0x14001b0cb  nop     dword ptr [rax+rax+00h]
0x14001b0d0  xor     edx, edx
0x14001b0d2  mov     [rbp+90h+var_108], eax
0x14001b0d5  test    eax, eax
0x14001b0d7  mov     esi, eax
0x14001b0d9  setnz   al
0x14001b0dc  mov     [rsp+190h+var_150], al
0x14001b0e0  cmp     [rsp+190h+SourceString.Length], dx
0x14001b0e5  jnz     loc_14001B306
0x14001b0eb  mov     r14b, dl
0x14001b0ee  test    esi, esi
0x14001b0f0  jz      loc_14001B2CF
0x14001b0f6  movzx   eax, [rsp+190h+String1.Length]
0x14001b0fb  mov     word ptr [rsp+190h+var_120+8], ax
0x14001b100  movzx   eax, [rsp+190h+String1.MaximumLength]
0x14001b105  mov     word ptr [rsp+190h+var_120+0Ah], ax
0x14001b10a  mov     eax, dword ptr [rsp+190h+String1+4]
0x14001b10e  mov     dword ptr [rsp+190h+var_120+0Ch], eax
0x14001b112  mov     rax, [rsp+190h+String1.Buffer]
0x14001b117  mov     [rbp+90h+var_100], rdx
0x14001b11b  lea     r9, [rsp+190h+var_14C]
0x14001b120  mov     [rsp+190h+var_14C], edx
0x14001b124  lea     r8, [rbp+90h+var_100]
0x14001b128  mov     [rbp+90h+var_110], rax
0x14001b12c  lea     rdx, [rsp+190h+var_120]
0x14001b131  mov     rcx, [r13+28h]
0x14001b135  call    LuafvLookupElementTableFull
0x14001b13a  mov     rsi, rax
0x14001b13d  test    rax, rax
0x14001b140  jnz     loc_14001B4A2
0x14001b146  test    byte ptr [rbx+1Eh], 8
0x14001b14a  mov     sil, [rsp+190h+var_150]
0x14001b14f  jnz     loc_14001B623
0x14001b155  test    sil, sil
0x14001b158  jnz     loc_14001B35F
0x14001b15e  lea     rdx, [rsp+190h+String1]; SourceString
0x14001b163  mov     rcx, r12; DestinationString
0x14001b166  call    cs:__imp_RtlCopyUnicodeString
0x14001b16d  nop     dword ptr [rax+rax+00h]
0x14001b172  xor     r12d, r12d
0x14001b175  test    r14b, r14b
0x14001b178  jz      loc_14001B24F
0x14001b17e  movzx   r14d, [rsp+190h+SourceString.Length]
0x14001b184  lea     eax, [r14+8]
0x14001b188  cmp     eax, 8
0x14001b18b  jb      loc_14001B291
0x14001b191  mov     edx, eax
0x14001b193  mov     ecx, 100h
0x14001b198  mov     r8d, 6661754Ch
0x14001b19e  call    cs:__imp_ExAllocatePool2
0x14001b1a5  nop     dword ptr [rax+rax+00h]
0x14001b1aa  mov     rsi, rax
0x14001b1ad  test    rax, rax
0x14001b1b0  jz      loc_14001B291
0x14001b1b6  xor     edx, edx
0x14001b1b8  mov     [rax], r14d
0x14001b1bb  lea     rcx, PoolLock
0x14001b1c2  mov     byte ptr [rax+4], 0FFh
0x14001b1c6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b1cd  nop     dword ptr [rax+rax+00h]
0x14001b1d2  add     cs:dword_14000F2FC, r14d
0x14001b1d9  lea     rcx, PoolLock
0x14001b1e0  xor     edx, edx
0x14001b1e2  call    cs:__imp_FltReleasePushLockEx
0x14001b1e9  nop     dword ptr [rax+rax+00h]
0x14001b1ee  add     rsi, 8
0x14001b1f2  jz      loc_14001B291
0x14001b1f8  test    byte ptr [rbx+1Eh], 40h
0x14001b1fc  jz      short loc_14001B214
0x14001b1fe  mov     rcx, [r15+8]
0x14001b202  call    LuafvFreePool
0x14001b207  mov     eax, 0FFBFh
0x14001b20c  mov     [r15+8], r12
0x14001b210  and     [rbx+1Eh], ax
0x14001b214  movzx   eax, [rsp+190h+SourceString.Length]
0x14001b219  lea     rdx, [rsp+190h+SourceString]; SourceString
0x14001b21e  mov     rcx, r15; DestinationString
0x14001b221  mov     [r15+2], ax
0x14001b226  mov     [r15+8], rsi
0x14001b22a  call    cs:__imp_RtlCopyUnicodeString
0x14001b231  nop     dword ptr [rax+rax+00h]
0x14001b236  mov     rcx, [r13+28h]
0x14001b23a  lea     rdx, [rbx+60h]
0x14001b23e  lea     r8, [rsp+190h+var_14F]
0x14001b243  call    LuafvInsertElementTable
0x14001b248  or      word ptr [rbx+1Eh], 48h
0x14001b24d  jmp     short loc_14001B259
0x14001b24f  test    byte ptr [rbx+1Eh], 8
0x14001b253  jnz     loc_14001B650
0x14001b259  mov     esi, dword ptr [rsp+190h+var_128]
0x14001b25d  test    byte ptr [rbx+1Eh], 10h
0x14001b261  jnz     loc_14001B669
0x14001b267  mov     rax, [rdi+60h]
0x14001b26b  mov     rcx, rbx
0x14001b26e  mov     [rbx+0B0h], rax
0x14001b275  call    InsertFileIdTableNode
0x14001b27a  movzx   eax, word ptr [rbx+1Eh]
0x14001b27e  mov     ecx, 0FF7Fh
0x14001b283  and     ax, cx
0x14001b286  mov     [rbx+18h], esi
0x14001b289  or      ax, 1
0x14001b28d  mov     [rbx+1Eh], ax
0x14001b291  cmp     rdi, [rbp+90h+var_F8]
0x14001b295  jz      short loc_14001B2A4
0x14001b297  lea     rax, [rbp+90h+var_F0]
0x14001b29b  cmp     rdi, rax
0x14001b29e  jnz     loc_14001B687
0x14001b2a4  mov     rax, rbx
0x14001b2a7  mov     rcx, [rbp+90h+var_40]
0x14001b2ab  xor     rcx, rsp; StackCookie
0x14001b2ae  call    __security_check_cookie
0x14001b2b3  mov     rbx, [rsp+190h+arg_18]
0x14001b2bb  add     rsp, 160h
0x14001b2c2  pop     r15
0x14001b2c4  pop     r14
0x14001b2c6  pop     r13
0x14001b2c8  pop     r12
0x14001b2ca  pop     rdi
0x14001b2cb  pop     rsi
0x14001b2cc  pop     rbp
0x14001b2cd  retn
0x14001b2cf  test    r14b, r14b
0x14001b2d2  jz      loc_14001B146
0x14001b2d8  movzx   eax, [rsp+190h+SourceString.Length]
0x14001b2dd  mov     word ptr [rsp+190h+var_120+8], ax
0x14001b2e2  movzx   eax, [rsp+190h+SourceString.MaximumLength]
0x14001b2e7  mov     word ptr [rsp+190h+var_120+0Ah], ax
0x14001b2ec  mov     eax, dword ptr [rsp+190h+SourceString+4]
0x14001b2f0  mov     dword ptr [rsp+190h+var_120+0Ch], eax
0x14001b2f4  mov     rax, [rsp+190h+SourceString.Buffer]
0x14001b2f9  jmp     loc_14001B117
0x14001b2fe  mov     esi, [rbx+18h]
0x14001b301  jmp     loc_14001B25D
0x14001b306  test    byte ptr [rbx+1Eh], 8
0x14001b30a  jz      loc_14001B0EE
0x14001b310  mov     r8b, r14b; CaseInSensitive
0x14001b313  lea     rdx, [rsp+190h+SourceString]; String2
0x14001b318  mov     rcx, r15; String1
0x14001b31b  call    cs:__imp_RtlCompareUnicodeString
0x14001b322  nop     dword ptr [rax+rax+00h]
0x14001b327  xor     edx, edx
0x14001b329  test    eax, eax
0x14001b32b  setnz   r14b
0x14001b32f  jmp     loc_14001B0EE
0x14001b334  test    byte ptr [rbx+1Eh], 10h
0x14001b338  jnz     loc_14001B54E
0x14001b33e  movzx   eax, word ptr [rbx+1Eh]
0x14001b342  test    al, 8
0x14001b344  jnz     loc_14001B55B
0x14001b34a  mov     ecx, 0FF7Eh
0x14001b34f  mov     [rbx+18h], r15d
0x14001b353  and     ax, cx
0x14001b356  mov     [rbx+1Eh], ax
0x14001b35a  jmp     loc_14001B2A4
0x14001b35f  movzx   eax, [rsp+190h+String1.Length]
0x14001b364  mov     [rsp+190h+var_14C], eax
0x14001b368  add     eax, 8
0x14001b36b  cmp     eax, 8
0x14001b36e  jb      loc_14001B291
0x14001b374  mov     edx, eax
0x14001b376  mov     ecx, 100h
0x14001b37b  mov     r8d, 6661754Ch
0x14001b381  call    cs:__imp_ExAllocatePool2
0x14001b388  nop     dword ptr [rax+rax+00h]
0x14001b38d  mov     rsi, rax
0x14001b390  test    rax, rax
0x14001b393  jz      loc_14001B291
0x14001b399  mov     eax, [rsp+190h+var_14C]
0x14001b39d  lea     rcx, PoolLock
0x14001b3a4  xor     edx, edx
0x14001b3a6  mov     [rsi], eax
0x14001b3a8  mov     byte ptr [rsi+4], 0FFh
0x14001b3ac  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b3b3  nop     dword ptr [rax+rax+00h]
0x14001b3b8  mov     eax, [rsp+190h+var_14C]
0x14001b3bc  lea     rcx, PoolLock
0x14001b3c3  add     cs:dword_14000F2FC, eax
0x14001b3c9  xor     edx, edx
0x14001b3cb  call    cs:__imp_FltReleasePushLockEx
0x14001b3d2  nop     dword ptr [rax+rax+00h]
0x14001b3d7  add     rsi, 8
0x14001b3db  jz      loc_14001B291
0x14001b3e1  mov     rcx, [r13+28h]; Root
0x14001b3e5  lea     rdx, [rbx+30h]; Links
0x14001b3e9  call    LuafvDeleteElementTable
0x14001b3ee  xor     edx, edx
0x14001b3f0  lea     rcx, qword_14000F2A0
0x14001b3f7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001b3fe  nop     dword ptr [rax+rax+00h]
0x14001b403  test    byte ptr [rbx+1Eh], 20h
0x14001b407  jz      short loc_14001B425
0x14001b409  mov     rcx, [r12+8]
0x14001b40e  call    LuafvFreePool
0x14001b413  mov     eax, 0FFDFh
0x14001b418  mov     qword ptr [r12+8], 0
0x14001b421  and     [rbx+1Eh], ax
0x14001b425  movzx   eax, [rsp+190h+String1.Length]
0x14001b42a  lea     rdx, [rsp+190h+String1]; SourceString
0x14001b42f  mov     rcx, r12; DestinationString
0x14001b432  mov     [r12+2], ax
0x14001b438  mov     [r12+8], rsi
0x14001b43d  call    cs:__imp_RtlCopyUnicodeString
0x14001b444  nop     dword ptr [rax+rax+00h]
0x14001b449  xor     edx, edx
0x14001b44b  lea     rcx, qword_14000F2A0
0x14001b452  call    cs:__imp_FltReleasePushLockEx
0x14001b459  nop     dword ptr [rax+rax+00h]
0x14001b45e  mov     rcx, [r13+28h]
0x14001b462  lea     r8, [rsp+190h+var_14F]
0x14001b467  lea     rdx, [rbx+30h]
0x14001b46b  call    LuafvInsertElementTable
0x14001b470  or      word ptr [rbx+1Eh], 20h
0x14001b475  lea     rcx, [rsp+190h+String1]
0x14001b47a  call    LuafvIsExcludedName
0x14001b47f  mov     cl, [rbx+1Dh]
0x14001b482  mov     dl, cl
0x14001b484  xor     dl, al
0x14001b486  and     dl, 1
0x14001b489  xor     dl, cl
0x14001b48b  mov     [rbx+1Dh], dl
0x14001b48e  jmp     loc_14001B172
0x14001b493  test    byte ptr [rbx+1Eh], 10h
0x14001b497  jnz     loc_14001B27A
  ... truncated ...
```
