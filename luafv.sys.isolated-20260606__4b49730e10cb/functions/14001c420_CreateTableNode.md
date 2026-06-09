# CreateTableNode

- ea: `0x14001c420`
- end: `0x14001cb2c`
- name: `CreateTableNode`
- size: `1804`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001bab0`

## callees

- `0x140001200`
- `0x14000160c`
- `0x140005f30`
- `0x140006380`
- `0x14001af8c`
- `0x14001c420`
- `0x14001cb80`
- `0x14001cd64`
- `0x14001ce94`
- `0x14001cef0`
- `0x14001d060`
- `0x14001dd90`
- `0x14001e5d0`
- `0x14001e6cc`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001c676`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001c676`
- `ntoskrnl!RtlSplay` at `0x14001c8b1`
- `ntoskrnl!RtlSplay` at `0x14001c950`
- `ntoskrnl!RtlSplay` at `0x14001c8b1`
- `ntoskrnl!RtlSplay` at `0x14001c950`
- `ntoskrnl!ExInitializePushLock` at `0x14001c6e1`
- `ntoskrnl!ExInitializePushLock` at `0x14001c6e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c7a5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c7e4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca53`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca92`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c7a5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c7e4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca53`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca92`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c783`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c7c5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ca31`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ca73`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c783`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c7c5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ca31`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ca73`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c860`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c8f3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c860`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c8f3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001c572`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001c572`
- `ntoskrnl!ExAllocatePool2` at `0x14001cb0e`
- `ntoskrnl!ExAllocatePool2` at `0x14001cb0e`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c6b8`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c837`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c6b8`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c837`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c69c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c7b6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c81a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001ca64`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c69c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c7b6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c81a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001ca64`

## pseudocode

```c
__int64 __fastcall CreateTableNode(
        __int64 a1,
        struct _RTL_SPLAY_LINKS *a2,
        int a3,
        UNICODE_STRING *a4,
        UNICODE_STRING **a5,
        void *a6,
        void **a7)
{
  __int64 v10; // r9
  bool v11; // cf
  _QWORD *v12; // r14
  UNICODE_STRING v13; // xmm0
  __int64 result; // rax
  __int16 v15; // si
  __int64 v16; // rax
  USHORT Length; // cx
  char v18; // r12
  USHORT MaximumLength; // dx
  int v20; // eax
  PWSTR Buffer; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // r12d
  int ChildTable; // ebx
  char *Pool2; // rbx
  char v27; // al
  char *v28; // rbx
  int v29; // edx
  char v30; // al
  unsigned __int8 v31; // al
  __int64 v32; // rcx
  __int16 v33; // ax
  __int64 v34; // rsi
  int v35; // eax
  struct _RTL_SPLAY_LINKS *v36; // rcx
  __int64 v37; // r15
  struct _RTL_SPLAY_LINKS *v38; // rsi
  int NodeOrParent; // eax
  struct _RTL_SPLAY_LINKS *v40; // rcx
  __int64 v41; // rbx
  void **v42; // r8
  UNICODE_STRING *updated; // rax
  __int16 Buffer_high; // cx
  char v45[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v46; // [rsp+44h] [rbp-BCh]
  UNICODE_STRING String1; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  struct _RTL_SPLAY_LINKS *v50; // [rsp+70h] [rbp-90h] BYREF
  UNICODE_STRING **v51; // [rsp+78h] [rbp-88h]
  __int128 v52; // [rsp+80h] [rbp-80h] BYREF
  PWSTR v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  void **v55; // [rsp+A0h] [rbp-60h]
  _BYTE v56[176]; // [rsp+B0h] [rbp-50h] BYREF

  v51 = a5;
  LODWORD(v50) = a3;
  LODWORD(v53) = 0;
  v55 = a7;
  v45[0] = 0;
  SourceString = 0;
  v52 = 0;
  memset(v56, 0, sizeof(v56));
  v11 = *(_DWORD *)(a1 + 256) < 2u;
  v12 = 0;
  v13 = *a4;
  v49 = 0;
  String1 = v13;
  if ( v11 )
  {
    v46 = 16;
LABEL_23:
    v15 = 1;
    goto LABEL_14;
  }
  if ( (*(_BYTE *)(a1 + 30) & 1) == 0 || (*(_DWORD *)(a1 + 24) & 0x410) != 0x10 )
  {
    v46 = 0;
    v15 = 0;
    goto LABEL_14;
  }
  result = GetFileInformation(a1, a4, v56, v10, &v49, a6, a7);
  v15 = 0;
  if ( (int)result < 0 )
    return result;
  v12 = (_QWORD *)v49;
  if ( !v49 )
  {
    v46 = 0;
    goto LABEL_14;
  }
  String1.Length = *(_WORD *)(v49 + 60);
  String1.MaximumLength = String1.Length;
  String1.Buffer = (PWSTR)(v49 + 104);
  SourceString.Length = *(char *)(v49 + 68);
  SourceString.MaximumLength = SourceString.Length;
  SourceString.Buffer = (PWSTR)(v49 + 70);
  v16 = *(_QWORD *)(a1 + 40);
  v46 = *(_DWORD *)(v49 + 56);
  if ( !v16 || !*(_DWORD *)(v16 + 16) )
    goto LABEL_23;
  if ( RtlCompareUnicodeString(&String1, a4, 1u) )
  {
    Length = String1.Length;
    v18 = 0;
    MaximumLength = String1.MaximumLength;
    v20 = *(_DWORD *)(&String1.MaximumLength + 1);
    Buffer = String1.Buffer;
  }
  else
  {
    Length = SourceString.Length;
    v18 = 1;
    MaximumLength = SourceString.MaximumLength;
    v20 = *(_DWORD *)(&SourceString.MaximumLength + 1);
    Buffer = SourceString.Buffer;
  }
  WORD4(v52) = Length;
  WORD5(v52) = MaximumLength;
  HIDWORD(v52) = v20;
  v53 = Buffer;
  if ( Length )
  {
    v22 = *(_QWORD *)(a1 + 40);
    v54 = 0;
    LODWORD(v49) = 0;
    v23 = LuafvLookupElementTableFull(v22, &v52, &v54, &v49);
    if ( v23 )
    {
      v41 = v23 - ((*(_BYTE *)(v23 + 24) & 7) != 0 ? 96LL : 48LL);
      ExAcquireFastMutex(&FastMutex);
      if ( *(struct _KTHREAD **)(v41 + 8) == KeGetCurrentThread() )
      {
        ++*(_DWORD *)(v41 + 16);
      }
      else
      {
        ExReleaseFastMutex(&FastMutex);
        FltAcquirePushLockExclusiveEx(v41, 0);
        ExAcquireFastMutex(&FastMutex);
        *(_QWORD *)(v41 + 8) = KeGetCurrentThread();
        *(_DWORD *)(v41 + 16) = 1;
      }
      ExReleaseFastMutex(&FastMutex);
      v42 = v55;
      *(_WORD *)(v41 + 30) |= 0x80u;
      updated = UpdateTableNode((UNICODE_STRING *)v41, 0, v42);
      Buffer_high = HIWORD(updated[1].Buffer);
      if ( (Buffer_high & 1) == 0 )
      {
        HIWORD(updated[1].Buffer) = Buffer_high | 0x80;
        updated = UpdateTableNode(updated, v12, 0);
      }
      *v51 = updated;
      goto LABEL_51;
    }
  }
  v15 = 1;
  if ( !v18 )
    a2 = 0;
LABEL_14:
  if ( !*(_QWORD *)(a1 + 40) )
  {
    ChildTable = CreateChildTable(a1);
    if ( ChildTable < 0 )
      goto LABEL_17;
  }
  v24 = String1.Length + SourceString.Length + 264;
  if ( v24 < 0xFFFFFFF8 )
  {
    if ( v24 > 0x120 )
    {
      Pool2 = (char *)ExAllocatePool2(256, v24 + 8, 1717663052);
      v27 = -1;
    }
    else
    {
      Pool2 = (char *)ExAllocateFromPagedLookasideList(&TableNodeLookaside);
      v27 = 1;
    }
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = v24;
      Pool2[4] = v27;
      FltAcquirePushLockExclusiveEx(&PoolLock, 0);
      dword_14000F2FC += v24;
      FltReleasePushLockEx(&PoolLock, 0);
      v28 = Pool2 + 8;
      if ( v28 )
      {
        memset(v28, 0, 0x108u);
        ExInitializePushLock((PULONG_PTR)v28);
        v28[72] &= 0xF8u;
        v29 = v46;
        v30 = v28[120] & 0xF8 | 1;
        *((_DWORD *)v28 + 5) = 1;
        v28[120] = v30;
        v31 = v28[168] & 0xFA;
        *((_DWORD *)v28 + 6) = v29;
        v32 = v31 | 2u;
        v33 = *((_WORD *)v28 + 15) & 0xFFFE;
        v28[168] = v32;
        *((_WORD *)v28 + 15) = v15 | v33;
        v28[28] = *(_BYTE *)(a1 + 28);
        *((_QWORD *)v28 + 4) = a1;
        *((_QWORD *)v28 + 21) = v32 ^ (*(_QWORD *)(a1 + 168) ^ (unsigned int)v32) & 0xFFFFFFFFFFFFFFF8uLL;
        *((_DWORD *)v28 + 64) = *(_DWORD *)(a1 + 256) + 1;
        *((_QWORD *)v28 + 28) = MEMORY[0xFFFFF78000000014];
        if ( (v29 & 0x10) != 0 )
          v28[28] &= ~8u;
        ExAcquireFastMutex(&FastMutex);
        if ( *((struct _KTHREAD **)v28 + 1) == KeGetCurrentThread() )
        {
          ++*((_DWORD *)v28 + 4);
        }
        else
        {
          ExReleaseFastMutex(&FastMutex);
          FltAcquirePushLockExclusiveEx(v28, 0);
          ExAcquireFastMutex(&FastMutex);
          *((_QWORD *)v28 + 1) = KeGetCurrentThread();
          *((_DWORD *)v28 + 4) = 1;
        }
        ExReleaseFastMutex(&FastMutex);
        v28[29] ^= (v28[29] ^ LuafvIsExcludedName(&String1)) & 1;
        if ( *(_QWORD *)(a1 + 208) )
        {
          FltAcquirePushLockExclusiveEx(&qword_14000F298, 0);
          RemoveMruListNode(a1);
          FltReleasePushLockEx(&qword_14000F298, 0);
        }
        *((_WORD *)v28 + 41) = String1.Length;
        *((_QWORD *)v28 + 11) = v28 + 264;
        RtlCopyUnicodeString((PUNICODE_STRING)v28 + 5, &String1);
        v34 = *(_QWORD *)(a1 + 40);
        if ( a2 )
        {
          v35 = (int)v50;
          if ( (_DWORD)v50 == 1 )
          {
            v36 = a2;
          }
          else
          {
            v36 = (struct _RTL_SPLAY_LINKS *)(v28 + 48);
            *((_QWORD *)v28 + 6) = v28 + 48;
            *((_QWORD *)v28 + 7) = 0;
            *((_QWORD *)v28 + 8) = 0;
            ++*(_DWORD *)(v34 + 16);
            if ( v35 )
            {
              if ( v35 == 2 )
                a2->LeftChild = v36;
              else
                a2->RightChild = v36;
              v36->Parent = a2;
            }
            else
            {
              *(_QWORD *)v34 = v36;
            }
          }
          *(_QWORD *)v34 = RtlSplay(v36);
        }
        else
        {
          LuafvInsertElementTable(*(_QWORD *)(a1 + 40), v28 + 48, v45);
        }
        _InterlockedAdd((volatile signed __int32 *)(a1 + 20), 1u);
        if ( SourceString.Length )
        {
          *((_WORD *)v28 + 65) = SourceString.Length;
          *((_QWORD *)v28 + 17) = *((_QWORD *)v28 + 11) + String1.Length;
          RtlCopyUnicodeString((PUNICODE_STRING)v28 + 8, &SourceString);
          v37 = *(_QWORD *)(a1 + 40);
          v38 = (struct _RTL_SPLAY_LINKS *)(v28 + 96);
          v50 = 0;
          NodeOrParent = FindNodeOrParent(v37, v28 + 120, &v50);
          v40 = v50;
          if ( NodeOrParent == 1 )
          {
            v38 = v50;
          }
          else
          {
            v38->Parent = v38;
            *((_QWORD *)v28 + 13) = 0;
            *((_QWORD *)v28 + 14) = 0;
            ++*(_DWORD *)(v37 + 16);
            if ( NodeOrParent )
            {
              if ( NodeOrParent == 2 )
                v40->LeftChild = v38;
              else
                v40->RightChild = v38;
              v38->Parent = v40;
            }
            else
            {
              *(_QWORD *)v37 = v38;
            }
          }
          *(_QWORD *)v37 = RtlSplay(v38);
          *((_WORD *)v28 + 15) |= 8u;
        }
        if ( v12 )
        {
          *((_QWORD *)v28 + 22) = v12[12];
          InsertFileIdTableNode(v28);
        }
        *v51 = (UNICODE_STRING *)v28;
        LuafvRunScavenger();
LABEL_51:
        ChildTable = 0;
        goto LABEL_17;
      }
    }
  }
  ChildTable = -1073741670;
LABEL_17:
  if ( v12 )
  {
    if ( v12 != (_QWORD *)v56 )
      LuafvFreePool(v12);
  }
  return (unsigned int)ChildTable;
}

```

## disassembly

```asm
0x14001c420  mov     [rsp-8+arg_10], rbx
0x14001c425  push    rbp
0x14001c426  push    rsi
0x14001c427  push    rdi
0x14001c428  push    r12
0x14001c42a  push    r13
0x14001c42c  push    r14
0x14001c42e  push    r15
0x14001c430  lea     rbp, [rsp-70h]
0x14001c435  sub     rsp, 170h
0x14001c43c  mov     rax, cs:__security_cookie
0x14001c443  xor     rax, rsp
0x14001c446  mov     [rbp+0A0h+var_40], rax
0x14001c44a  mov     rax, [rbp+0A0h+arg_20]
0x14001c451  xorps   xmm0, xmm0
0x14001c454  mov     rsi, [rbp+0A0h+arg_30]
0x14001c45b  mov     r13, rdx
0x14001c45e  mov     r12, [rbp+0A0h+arg_28]
0x14001c465  mov     r15, rcx
0x14001c468  mov     [rsp+1A0h+var_128], rax
0x14001c46d  lea     rcx, [rbp+0A0h+var_F0]; void *
0x14001c471  xor     eax, eax
0x14001c473  mov     dword ptr [rsp+1A0h+var_130], r8d
0x14001c478  xor     edi, edi
0x14001c47a  mov     dword ptr [rbp+0A0h+var_110], eax
0x14001c47d  xor     edx, edx; Val
0x14001c47f  mov     [rbp+0A0h+var_100], rsi
0x14001c483  mov     r8d, 0B0h; Size
0x14001c489  mov     [rsp+1A0h+var_160], dil
0x14001c48e  mov     rbx, r9
0x14001c491  movups  xmmword ptr [rsp+1A0h+SourceString.Length], xmm0
0x14001c496  movups  [rbp+0A0h+var_120], xmm0
0x14001c49a  call    memset
0x14001c49f  cmp     dword ptr [r15+100h], 2
0x14001c4a7  mov     r14d, edi
0x14001c4aa  movups  xmm0, xmmword ptr [rbx]
0x14001c4ad  mov     [rsp+1A0h+var_138], rdi
0x14001c4b2  movdqu  xmmword ptr [rsp+1A0h+String1.Length], xmm0
0x14001c4b8  lea     edi, [r14+1]
0x14001c4bc  jb      loc_14001C655
0x14001c4c2  test    [r15+1Eh], dil
0x14001c4c6  jz      loc_14001CACE
0x14001c4cc  mov     eax, [r15+18h]
0x14001c4d0  and     eax, 410h
0x14001c4d5  cmp     eax, 10h
0x14001c4d8  jnz     loc_14001CACE
0x14001c4de  mov     [rsp+1A0h+var_170], rsi
0x14001c4e3  lea     rax, [rsp+1A0h+var_138]
0x14001c4e8  mov     [rsp+1A0h+var_178], r12
0x14001c4ed  lea     r8, [rbp+0A0h+var_F0]
0x14001c4f1  mov     rdx, rbx
0x14001c4f4  mov     [rsp+1A0h+var_180], rax
0x14001c4f9  mov     rcx, r15
0x14001c4fc  call    GetFileInformation
0x14001c501  xor     esi, esi
0x14001c503  test    eax, eax
0x14001c505  js      loc_14001C62D
0x14001c50b  mov     r14, [rsp+1A0h+var_138]
0x14001c510  test    r14, r14
0x14001c513  jz      loc_14001C9E3
0x14001c519  movzx   eax, word ptr [r14+3Ch]
0x14001c51e  mov     [rsp+1A0h+String1.Length], ax
0x14001c523  mov     [rsp+1A0h+String1.MaximumLength], ax
0x14001c528  lea     rax, [r14+68h]
0x14001c52c  mov     [rsp+1A0h+String1.Buffer], rax
0x14001c531  movsx   eax, byte ptr [r14+44h]
0x14001c536  mov     [rsp+1A0h+SourceString.Length], ax
0x14001c53b  mov     [rsp+1A0h+SourceString.MaximumLength], ax
0x14001c540  lea     rax, [r14+46h]
0x14001c544  mov     [rsp+1A0h+SourceString.Buffer], rax
0x14001c549  mov     rax, [r15+28h]
0x14001c54d  mov     ecx, [r14+38h]
0x14001c551  mov     [rsp+1A0h+var_15C], ecx
0x14001c555  test    rax, rax
0x14001c558  jz      loc_14001C65D
0x14001c55e  cmp     [rax+10h], esi
0x14001c561  jz      loc_14001C65D
0x14001c567  mov     r8b, dil; CaseInSensitive
0x14001c56a  lea     rcx, [rsp+1A0h+String1]; String1
0x14001c56f  mov     rdx, rbx; String2
0x14001c572  call    cs:__imp_RtlCompareUnicodeString
0x14001c579  nop     dword ptr [rax+rax+00h]
0x14001c57e  test    eax, eax
0x14001c580  jnz     loc_14001C995
0x14001c586  movzx   ecx, [rsp+1A0h+SourceString.Length]
0x14001c58b  mov     r12b, dil
0x14001c58e  movzx   edx, [rsp+1A0h+SourceString.MaximumLength]
0x14001c593  mov     eax, dword ptr [rsp+1A0h+SourceString+4]
0x14001c597  mov     r8, [rsp+1A0h+SourceString.Buffer]
0x14001c59c  mov     word ptr [rbp+0A0h+var_120+8], cx
0x14001c5a0  mov     word ptr [rbp+0A0h+var_120+0Ah], dx
0x14001c5a4  mov     dword ptr [rbp+0A0h+var_120+0Ch], eax
0x14001c5a7  mov     [rbp+0A0h+var_110], r8
0x14001c5ab  test    cx, cx
0x14001c5ae  jz      short loc_14001C5DA
0x14001c5b0  mov     rcx, [r15+28h]
0x14001c5b4  lea     r9, [rsp+1A0h+var_138]
0x14001c5b9  lea     r8, [rbp+0A0h+var_108]
0x14001c5bd  mov     [rbp+0A0h+var_108], rsi
0x14001c5c1  lea     rdx, [rbp+0A0h+var_120]
0x14001c5c5  mov     dword ptr [rsp+1A0h+var_138], esi
0x14001c5c9  call    LuafvLookupElementTableFull
0x14001c5ce  mov     rbx, rax
0x14001c5d1  test    rax, rax
0x14001c5d4  jnz     loc_14001CA12
0x14001c5da  movzx   esi, di
0x14001c5dd  test    r12b, r12b
0x14001c5e0  jz      loc_14001CAF9
0x14001c5e6  cmp     qword ptr [r15+28h], 0
0x14001c5eb  jz      loc_14001C9BB
0x14001c5f1  movzx   r12d, [rsp+1A0h+SourceString.Length]
0x14001c5f7  movzx   ecx, [rsp+1A0h+String1.Length]
0x14001c5fc  add     r12d, 108h
0x14001c603  add     r12d, ecx
0x14001c606  lea     eax, [r12+8]
0x14001c60b  cmp     eax, 8
0x14001c60e  jnb     short loc_14001C662
0x14001c610  mov     ebx, 0C000009Ah
0x14001c615  test    r14, r14
0x14001c618  jz      short loc_14001C62B
0x14001c61a  lea     rax, [rbp+0A0h+var_F0]
0x14001c61e  cmp     r14, rax
0x14001c621  jz      short loc_14001C62B
0x14001c623  mov     rcx, r14
0x14001c626  call    LuafvFreePool
0x14001c62b  mov     eax, ebx
0x14001c62d  mov     rcx, [rbp+0A0h+var_40]
0x14001c631  xor     rcx, rsp; StackCookie
0x14001c634  call    __security_check_cookie
0x14001c639  mov     rbx, [rsp+1A0h+arg_10]
0x14001c641  add     rsp, 170h
0x14001c648  pop     r15
0x14001c64a  pop     r14
0x14001c64c  pop     r13
0x14001c64e  pop     r12
0x14001c650  pop     rdi
0x14001c651  pop     rsi
0x14001c652  pop     rbp
0x14001c653  retn
0x14001c655  mov     [rsp+1A0h+var_15C], 10h
0x14001c65d  movzx   esi, di
0x14001c660  jmp     short loc_14001C5E6
0x14001c662  cmp     r12d, 120h
0x14001c669  ja      loc_14001CB01
0x14001c66f  lea     rcx, TableNodeLookaside; Lookaside
0x14001c676  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001c67d  nop     dword ptr [rax+rax+00h]
0x14001c682  mov     rbx, rax
0x14001c685  mov     al, dil
0x14001c688  test    rbx, rbx
0x14001c68b  jz      short loc_14001C610
0x14001c68d  xor     edx, edx
0x14001c68f  mov     [rbx], r12d
0x14001c692  lea     rcx, PoolLock
0x14001c699  mov     [rbx+4], al
0x14001c69c  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001c6a3  nop     dword ptr [rax+rax+00h]
0x14001c6a8  add     cs:dword_14000F2FC, r12d
0x14001c6af  lea     rcx, PoolLock
0x14001c6b6  xor     edx, edx
0x14001c6b8  call    cs:__imp_FltReleasePushLockEx
0x14001c6bf  nop     dword ptr [rax+rax+00h]
0x14001c6c4  add     rbx, 8
0x14001c6c8  jz      loc_14001C610
0x14001c6ce  xor     edx, edx; Val
0x14001c6d0  mov     r8d, 108h; Size
0x14001c6d6  mov     rcx, rbx; void *
0x14001c6d9  call    memset
0x14001c6de  mov     rcx, rbx; PushLock
0x14001c6e1  call    cs:__imp_ExInitializePushLock
0x14001c6e8  nop     dword ptr [rax+rax+00h]
0x14001c6ed  and     byte ptr [rbx+48h], 0F8h
0x14001c6f1  mov     r8d, 0FFFEh
0x14001c6f7  mov     al, [rbx+78h]
0x14001c6fa  mov     edx, [rsp+1A0h+var_15C]
0x14001c6fe  and     al, 0F9h
0x14001c700  or      al, dil
0x14001c703  mov     [rbx+14h], edi
0x14001c706  mov     [rbx+78h], al
0x14001c709  mov     al, [rbx+0A8h]
0x14001c70f  and     al, 0FAh
0x14001c711  mov     [rbx+18h], edx
0x14001c714  or      al, 2
0x14001c716  movzx   ecx, al
0x14001c719  movzx   eax, word ptr [rbx+1Eh]
0x14001c71d  and     ax, r8w
0x14001c721  mov     [rbx+0A8h], cl
0x14001c727  or      ax, si
0x14001c72a  mov     [rbx+1Eh], ax
0x14001c72e  mov     al, [r15+1Ch]
0x14001c732  mov     [rbx+1Ch], al
0x14001c735  mov     eax, ecx
0x14001c737  mov     [rbx+20h], r15
0x14001c73b  xor     rax, [r15+0A8h]
0x14001c742  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001c746  xor     rax, rcx
0x14001c749  mov     [rbx+0A8h], rax
0x14001c750  mov     eax, [r15+100h]
0x14001c757  add     eax, edi
0x14001c759  mov     [rbx+100h], eax
0x14001c75f  mov     rax, ds:0FFFFF78000000014h
0x14001c769  mov     [rbx+0E0h], rax
0x14001c770  test    dl, 10h
0x14001c773  jz      short loc_14001C779
0x14001c775  and     byte ptr [rbx+1Ch], 0F7h
0x14001c779  lea     rsi, FastMutex
0x14001c780  mov     rcx, rsi; FastMutex
0x14001c783  call    cs:__imp_ExAcquireFastMutex
0x14001c78a  nop     dword ptr [rax+rax+00h]
0x14001c78f  mov     rax, gs:188h
0x14001c798  cmp     [rbx+8], rax
0x14001c79c  jz      loc_14001CB24
0x14001c7a2  mov     rcx, rsi; FastMutex
0x14001c7a5  call    cs:__imp_ExReleaseFastMutex
0x14001c7ac  nop     dword ptr [rax+rax+00h]
0x14001c7b1  xor     edx, edx
0x14001c7b3  mov     rcx, rbx
0x14001c7b6  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001c7bd  nop     dword ptr [rax+rax+00h]
0x14001c7c2  mov     rcx, rsi; FastMutex
0x14001c7c5  call    cs:__imp_ExAcquireFastMutex
0x14001c7cc  nop     dword ptr [rax+rax+00h]
0x14001c7d1  mov     rax, gs:188h
0x14001c7da  mov     [rbx+8], rax
0x14001c7de  mov     [rbx+10h], edi
0x14001c7e1  mov     rcx, rsi; FastMutex
0x14001c7e4  call    cs:__imp_ExReleaseFastMutex
0x14001c7eb  nop     dword ptr [rax+rax+00h]
0x14001c7f0  lea     rcx, [rsp+1A0h+String1]
0x14001c7f5  call    LuafvIsExcludedName
0x14001c7fa  mov     cl, [rbx+1Dh]
0x14001c7fd  xor     al, cl
0x14001c7ff  and     al, dil
0x14001c802  xor     al, cl
0x14001c804  mov     [rbx+1Dh], al
0x14001c807  cmp     qword ptr [r15+0D0h], 0
0x14001c80f  jz      short loc_14001C843
0x14001c811  xor     edx, edx
0x14001c813  lea     rcx, qword_14000F298
0x14001c81a  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001c821  nop     dword ptr [rax+rax+00h]
0x14001c826  mov     rcx, r15
0x14001c829  call    RemoveMruListNode
0x14001c82e  xor     edx, edx
0x14001c830  lea     rcx, qword_14000F298
0x14001c837  call    cs:__imp_FltReleasePushLockEx
0x14001c83e  nop     dword ptr [rax+rax+00h]
0x14001c843  movzx   eax, [rsp+1A0h+String1.Length]
0x14001c848  lea     rdx, [rsp+1A0h+String1]; SourceString
0x14001c84d  mov     [rbx+52h], ax
0x14001c851  lea     rcx, [rbx+50h]; DestinationString
0x14001c855  lea     rax, [rbx+108h]
0x14001c85c  mov     [rbx+58h], rax
0x14001c860  call    cs:__imp_RtlCopyUnicodeString
0x14001c867  nop     dword ptr [rax+rax+00h]
0x14001c86c  mov     rsi, [r15+28h]
0x14001c870  xor     edx, edx
0x14001c872  test    r13, r13
0x14001c875  jz      loc_14001C9EC
0x14001c87b  mov     eax, dword ptr [rsp+1A0h+var_130]
0x14001c87f  cmp     eax, edi
0x14001c881  jz      loc_14001C9DB
0x14001c887  lea     rcx, [rbx+30h]; Links
0x14001c88b  mov     [rcx], rcx
0x14001c88e  mov     [rcx+8], rdx
0x14001c892  mov     [rcx+10h], rdx
0x14001c896  add     [rsi+10h], edi
0x14001c899  test    eax, eax
0x14001c89b  jz      loc_14001CA0A
0x14001c8a1  cmp     eax, 2
0x14001c8a4  jnz     loc_14001C9D2
0x14001c8aa  mov     [r13+8], rcx
0x14001c8ae  mov     [rcx], r13
0x14001c8b1  call    cs:__imp_RtlSplay
0x14001c8b8  nop     dword ptr [rax+rax+00h]
0x14001c8bd  mov     [rsi], rax
0x14001c8c0  lock add [r15+14h], edi
0x14001c8c5  movzx   eax, [rsp+1A0h+SourceString.Length]
0x14001c8ca  xor     r13d, r13d
0x14001c8cd  test    ax, ax
0x14001c8d0  jz      loc_14001C968
0x14001c8d6  lea     rcx, [rbx+80h]; DestinationString
0x14001c8dd  mov     [rcx+2], ax
0x14001c8e1  lea     rdx, [rsp+1A0h+SourceString]; SourceString
0x14001c8e6  movzx   eax, [rsp+1A0h+String1.Length]
0x14001c8eb  add     rax, [rbx+58h]
0x14001c8ef  mov     [rcx+8], rax
0x14001c8f3  call    cs:__imp_RtlCopyUnicodeString
0x14001c8fa  nop     dword ptr [rax+rax+00h]
0x14001c8ff  mov     r15, [r15+28h]
0x14001c903  lea     rsi, [rbx+60h]
0x14001c907  lea     rdx, [rsi+18h]
0x14001c90b  mov     [rsp+1A0h+var_130], r13
0x14001c910  mov     rcx, r15
0x14001c913  lea     r8, [rsp+1A0h+var_130]
0x14001c918  call    FindNodeOrParent
0x14001c91d  mov     rcx, [rsp+1A0h+var_130]
0x14001c922  cmp     eax, edi
0x14001c924  jz      loc_14001C9B6
0x14001c92a  mov     [rsi], rsi
  ... truncated ...
```
