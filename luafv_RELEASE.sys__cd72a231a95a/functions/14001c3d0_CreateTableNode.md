# CreateTableNode

- ea: `0x14001c3d0`
- end: `0x14001cadc`
- name: `CreateTableNode`
- size: `1804`
- prototype: `__int64 __fastcall(__int64, struct _RTL_SPLAY_LINKS *, int, UNICODE_STRING *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ba60`

## callees

- `0x140001200`
- `0x14000160c`
- `0x140005bb0`
- `0x140006000`
- `0x14001af3c`
- `0x14001c3d0`
- `0x14001cb30`
- `0x14001cd14`
- `0x14001ce44`
- `0x14001cea0`
- `0x14001d010`
- `0x14001dd40`
- `0x14001e580`
- `0x14001e67c`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001c626`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001c626`
- `ntoskrnl!RtlSplay` at `0x14001c861`
- `ntoskrnl!RtlSplay` at `0x14001c900`
- `ntoskrnl!RtlSplay` at `0x14001c861`
- `ntoskrnl!RtlSplay` at `0x14001c900`
- `ntoskrnl!ExInitializePushLock` at `0x14001c691`
- `ntoskrnl!ExInitializePushLock` at `0x14001c691`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c755`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c794`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca03`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca42`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c755`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c794`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca03`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001ca42`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c733`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c775`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c9e1`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ca23`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c733`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c775`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c9e1`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001ca23`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c810`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c8a3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c810`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001c8a3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001c522`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001c522`
- `ntoskrnl!ExAllocatePool2` at `0x14001cabe`
- `ntoskrnl!ExAllocatePool2` at `0x14001cabe`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c668`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c7e7`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c668`
- `FLTMGR!FltReleasePushLockEx` at `0x14001c7e7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c64c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c766`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c7ca`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001ca14`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c64c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c766`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001c7ca`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001ca14`

## pseudocode

```c
__int64 __fastcall CreateTableNode(
        __int64 a1,
        struct _RTL_SPLAY_LINKS *a2,
        int a3,
        UNICODE_STRING *a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  bool v10; // cf
  UNICODE_STRING v11; // xmm0
  __int64 result; // rax
  __int16 v13; // si
  unsigned int v14; // r12d
  int ChildTable; // ebx
  char *Pool2; // rbx
  char v17; // al
  char *v18; // rbx
  int v19; // edx
  char v20; // al
  unsigned __int8 v21; // al
  __int64 v22; // rcx
  __int16 v23; // ax
  __int64 v24; // rsi
  int v25; // eax
  struct _RTL_SPLAY_LINKS *v26; // rcx
  __int64 v27; // r15
  struct _RTL_SPLAY_LINKS *v28; // rsi
  int NodeOrParent; // eax
  struct _RTL_SPLAY_LINKS *v30; // rcx
  char v31[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-BCh]
  UNICODE_STRING String1; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING SourceString; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h]
  struct _RTL_SPLAY_LINKS *v36; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v37; // [rsp+78h] [rbp-88h]
  __int128 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  _BYTE v41[176]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = a5;
  LODWORD(v36) = a3;
  LODWORD(v39) = 0;
  v40 = a7;
  v31[0] = 0;
  SourceString = 0;
  v38 = 0;
  memset(v41, 0, sizeof(v41));
  v10 = *(_DWORD *)(a1 + 256) < 2u;
  v11 = *a4;
  v35 = 0;
  String1 = v11;
  if ( v10 )
  {
    v32 = 16;
    v13 = 1;
  }
  else if ( (*(_BYTE *)(a1 + 30) & 1) != 0 && (*(_DWORD *)(a1 + 24) & 0x410) == 0x10 )
  {
    result = GetFileInformation(a1, a4, v41);
    v13 = 0;
    if ( (int)result < 0 )
      return result;
    v32 = 0;
  }
  else
  {
    v32 = 0;
    v13 = 0;
  }
  if ( *(_QWORD *)(a1 + 40) || (ChildTable = CreateChildTable(a1), ChildTable >= 0) )
  {
    v14 = String1.Length + SourceString.Length + 264;
    if ( v14 >= 0xFFFFFFF8 )
      return (unsigned int)-1073741670;
    if ( v14 > 0x120 )
    {
      Pool2 = (char *)ExAllocatePool2(256, v14 + 8, 1717663052);
      v17 = -1;
    }
    else
    {
      Pool2 = (char *)ExAllocateFromPagedLookasideList(&TableNodeLookaside);
      v17 = 1;
    }
    if ( Pool2
      && (*(_DWORD *)Pool2 = v14,
          Pool2[4] = v17,
          FltAcquirePushLockExclusiveEx(&PoolLock, 0),
          dword_14000ECBC += v14,
          FltReleasePushLockEx(&PoolLock, 0),
          (v18 = Pool2 + 8) != 0) )
    {
      memset(v18, 0, 0x108u);
      ExInitializePushLock((PULONG_PTR)v18);
      v18[72] &= 0xF8u;
      v19 = v32;
      v20 = v18[120] & 0xF8 | 1;
      *((_DWORD *)v18 + 5) = 1;
      v18[120] = v20;
      v21 = v18[168] & 0xFA;
      *((_DWORD *)v18 + 6) = v19;
      v22 = v21 | 2u;
      v23 = *((_WORD *)v18 + 15) & 0xFFFE;
      v18[168] = v22;
      *((_WORD *)v18 + 15) = v13 | v23;
      v18[28] = *(_BYTE *)(a1 + 28);
      *((_QWORD *)v18 + 4) = a1;
      *((_QWORD *)v18 + 21) = v22 ^ (*(_QWORD *)(a1 + 168) ^ (unsigned int)v22) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_DWORD *)v18 + 64) = *(_DWORD *)(a1 + 256) + 1;
      *((_QWORD *)v18 + 28) = MEMORY[0xFFFFF78000000014];
      if ( (v19 & 0x10) != 0 )
        v18[28] &= ~8u;
      ExAcquireFastMutex(&FastMutex);
      if ( *((struct _KTHREAD **)v18 + 1) == KeGetCurrentThread() )
      {
        ++*((_DWORD *)v18 + 4);
      }
      else
      {
        ExReleaseFastMutex(&FastMutex);
        FltAcquirePushLockExclusiveEx(v18, 0);
        ExAcquireFastMutex(&FastMutex);
        *((_QWORD *)v18 + 1) = KeGetCurrentThread();
        *((_DWORD *)v18 + 4) = 1;
      }
      ExReleaseFastMutex(&FastMutex);
      v18[29] ^= (v18[29] ^ LuafvIsExcludedName(&String1)) & 1;
      if ( *(_QWORD *)(a1 + 208) )
      {
        FltAcquirePushLockExclusiveEx(&qword_14000EC58, 0);
        RemoveMruListNode(a1);
        FltReleasePushLockEx(&qword_14000EC58, 0);
      }
      *((_WORD *)v18 + 41) = String1.Length;
      *((_QWORD *)v18 + 11) = v18 + 264;
      RtlCopyUnicodeString((PUNICODE_STRING)v18 + 5, &String1);
      v24 = *(_QWORD *)(a1 + 40);
      if ( a2 )
      {
        v25 = (int)v36;
        if ( (_DWORD)v36 == 1 )
        {
          v26 = a2;
        }
        else
        {
          v26 = (struct _RTL_SPLAY_LINKS *)(v18 + 48);
          *((_QWORD *)v18 + 6) = v18 + 48;
          *((_QWORD *)v18 + 7) = 0;
          *((_QWORD *)v18 + 8) = 0;
          ++*(_DWORD *)(v24 + 16);
          if ( v25 )
          {
            if ( v25 == 2 )
              a2->LeftChild = v26;
            else
              a2->RightChild = v26;
            v26->Parent = a2;
          }
          else
          {
            *(_QWORD *)v24 = v26;
          }
        }
        *(_QWORD *)v24 = RtlSplay(v26);
      }
      else
      {
        LuafvInsertElementTable(*(_QWORD *)(a1 + 40), v18 + 48, v31);
      }
      _InterlockedAdd((volatile signed __int32 *)(a1 + 20), 1u);
      if ( SourceString.Length )
      {
        *((_WORD *)v18 + 65) = SourceString.Length;
        *((_QWORD *)v18 + 17) = *((_QWORD *)v18 + 11) + String1.Length;
        RtlCopyUnicodeString((PUNICODE_STRING)v18 + 8, &SourceString);
        v27 = *(_QWORD *)(a1 + 40);
        v28 = (struct _RTL_SPLAY_LINKS *)(v18 + 96);
        v36 = 0;
        NodeOrParent = FindNodeOrParent(v27, v18 + 120, &v36);
        v30 = v36;
        if ( NodeOrParent == 1 )
        {
          v28 = v36;
        }
        else
        {
          v28->Parent = v28;
          *((_QWORD *)v18 + 13) = 0;
          *((_QWORD *)v18 + 14) = 0;
          ++*(_DWORD *)(v27 + 16);
          if ( NodeOrParent )
          {
            if ( NodeOrParent == 2 )
              v30->LeftChild = v28;
            else
              v30->RightChild = v28;
            v28->Parent = v30;
          }
          else
          {
            *(_QWORD *)v27 = v28;
          }
        }
        *(_QWORD *)v27 = RtlSplay(v28);
        *((_WORD *)v18 + 15) |= 8u;
      }
      *v37 = v18;
      LuafvRunScavenger();
      return 0;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)ChildTable;
}

```

## disassembly

```asm
0x14001c3d0  mov     [rsp-8+arg_10], rbx
0x14001c3d5  push    rbp
0x14001c3d6  push    rsi
0x14001c3d7  push    rdi
0x14001c3d8  push    r12
0x14001c3da  push    r13
0x14001c3dc  push    r14
0x14001c3de  push    r15
0x14001c3e0  lea     rbp, [rsp-70h]
0x14001c3e5  sub     rsp, 170h
0x14001c3ec  mov     rax, cs:__security_cookie
0x14001c3f3  xor     rax, rsp
0x14001c3f6  mov     [rbp+0A0h+var_40], rax
0x14001c3fa  mov     rax, [rbp+0A0h+arg_20]
0x14001c401  xorps   xmm0, xmm0
0x14001c404  mov     rsi, [rbp+0A0h+arg_30]
0x14001c40b  mov     r13, rdx
0x14001c40e  mov     r12, [rbp+0A0h+arg_28]
0x14001c415  mov     r15, rcx
0x14001c418  mov     [rsp+1A0h+var_128], rax
0x14001c41d  lea     rcx, [rbp+0A0h+var_F0]; void *
0x14001c421  xor     eax, eax
0x14001c423  mov     dword ptr [rsp+1A0h+var_130], r8d
0x14001c428  xor     edi, edi
0x14001c42a  mov     dword ptr [rbp+0A0h+var_110], eax
0x14001c42d  xor     edx, edx; Val
0x14001c42f  mov     [rbp+0A0h+var_100], rsi
0x14001c433  mov     r8d, 0B0h; Size
0x14001c439  mov     [rsp+1A0h+var_160], dil
0x14001c43e  mov     rbx, r9
0x14001c441  movups  xmmword ptr [rsp+1A0h+SourceString.Length], xmm0
0x14001c446  movups  [rbp+0A0h+var_120], xmm0
0x14001c44a  call    memset
0x14001c44f  cmp     dword ptr [r15+100h], 2
0x14001c457  mov     r14d, edi
0x14001c45a  movups  xmm0, xmmword ptr [rbx]
0x14001c45d  mov     [rsp+1A0h+var_138], rdi
0x14001c462  movdqu  xmmword ptr [rsp+1A0h+String1.Length], xmm0
0x14001c468  lea     edi, [r14+1]
0x14001c46c  jb      loc_14001C605
0x14001c472  test    [r15+1Eh], dil
0x14001c476  jz      loc_14001CA7E
0x14001c47c  mov     eax, [r15+18h]
0x14001c480  and     eax, 410h
0x14001c485  cmp     eax, 10h
0x14001c488  jnz     loc_14001CA7E
0x14001c48e  mov     [rsp+1A0h+var_170], rsi
0x14001c493  lea     rax, [rsp+1A0h+var_138]
0x14001c498  mov     [rsp+1A0h+var_178], r12
0x14001c49d  lea     r8, [rbp+0A0h+var_F0]
0x14001c4a1  mov     rdx, rbx
0x14001c4a4  mov     [rsp+1A0h+var_180], rax
0x14001c4a9  mov     rcx, r15
0x14001c4ac  call    GetFileInformation
0x14001c4b1  xor     esi, esi
0x14001c4b3  test    eax, eax
0x14001c4b5  js      loc_14001C5DD
0x14001c4bb  mov     r14, [rsp+1A0h+var_138]
0x14001c4c0  test    r14, r14
0x14001c4c3  jz      loc_14001C993
0x14001c4c9  movzx   eax, word ptr [r14+3Ch]
0x14001c4ce  mov     [rsp+1A0h+String1.Length], ax
0x14001c4d3  mov     [rsp+1A0h+String1.MaximumLength], ax
0x14001c4d8  lea     rax, [r14+68h]
0x14001c4dc  mov     [rsp+1A0h+String1.Buffer], rax
0x14001c4e1  movsx   eax, byte ptr [r14+44h]
0x14001c4e6  mov     [rsp+1A0h+SourceString.Length], ax
0x14001c4eb  mov     [rsp+1A0h+SourceString.MaximumLength], ax
0x14001c4f0  lea     rax, [r14+46h]
0x14001c4f4  mov     [rsp+1A0h+SourceString.Buffer], rax
0x14001c4f9  mov     rax, [r15+28h]
0x14001c4fd  mov     ecx, [r14+38h]
0x14001c501  mov     [rsp+1A0h+var_15C], ecx
0x14001c505  test    rax, rax
0x14001c508  jz      loc_14001C60D
0x14001c50e  cmp     [rax+10h], esi
0x14001c511  jz      loc_14001C60D
0x14001c517  mov     r8b, dil; CaseInSensitive
0x14001c51a  lea     rcx, [rsp+1A0h+String1]; String1
0x14001c51f  mov     rdx, rbx; String2
0x14001c522  call    cs:__imp_RtlCompareUnicodeString
0x14001c529  nop     dword ptr [rax+rax+00h]
0x14001c52e  test    eax, eax
0x14001c530  jnz     loc_14001C945
0x14001c536  movzx   ecx, [rsp+1A0h+SourceString.Length]
0x14001c53b  mov     r12b, dil
0x14001c53e  movzx   edx, [rsp+1A0h+SourceString.MaximumLength]
0x14001c543  mov     eax, dword ptr [rsp+1A0h+SourceString+4]
0x14001c547  mov     r8, [rsp+1A0h+SourceString.Buffer]
0x14001c54c  mov     word ptr [rbp+0A0h+var_120+8], cx
0x14001c550  mov     word ptr [rbp+0A0h+var_120+0Ah], dx
0x14001c554  mov     dword ptr [rbp+0A0h+var_120+0Ch], eax
0x14001c557  mov     [rbp+0A0h+var_110], r8
0x14001c55b  test    cx, cx
0x14001c55e  jz      short loc_14001C58A
0x14001c560  mov     rcx, [r15+28h]
0x14001c564  lea     r9, [rsp+1A0h+var_138]
0x14001c569  lea     r8, [rbp+0A0h+var_108]
0x14001c56d  mov     [rbp+0A0h+var_108], rsi
0x14001c571  lea     rdx, [rbp+0A0h+var_120]
0x14001c575  mov     dword ptr [rsp+1A0h+var_138], esi
0x14001c579  call    LuafvLookupElementTableFull
0x14001c57e  mov     rbx, rax
0x14001c581  test    rax, rax
0x14001c584  jnz     loc_14001C9C2
0x14001c58a  movzx   esi, di
0x14001c58d  test    r12b, r12b
0x14001c590  jz      loc_14001CAA9
0x14001c596  cmp     qword ptr [r15+28h], 0
0x14001c59b  jz      loc_14001C96B
0x14001c5a1  movzx   r12d, [rsp+1A0h+SourceString.Length]
0x14001c5a7  movzx   ecx, [rsp+1A0h+String1.Length]
0x14001c5ac  add     r12d, 108h
0x14001c5b3  add     r12d, ecx
0x14001c5b6  lea     eax, [r12+8]
0x14001c5bb  cmp     eax, 8
0x14001c5be  jnb     short loc_14001C612
0x14001c5c0  mov     ebx, 0C000009Ah
0x14001c5c5  test    r14, r14
0x14001c5c8  jz      short loc_14001C5DB
0x14001c5ca  lea     rax, [rbp+0A0h+var_F0]
0x14001c5ce  cmp     r14, rax
0x14001c5d1  jz      short loc_14001C5DB
0x14001c5d3  mov     rcx, r14
0x14001c5d6  call    LuafvFreePool
0x14001c5db  mov     eax, ebx
0x14001c5dd  mov     rcx, [rbp+0A0h+var_40]
0x14001c5e1  xor     rcx, rsp; StackCookie
0x14001c5e4  call    __security_check_cookie
0x14001c5e9  mov     rbx, [rsp+1A0h+arg_10]
0x14001c5f1  add     rsp, 170h
0x14001c5f8  pop     r15
0x14001c5fa  pop     r14
0x14001c5fc  pop     r13
0x14001c5fe  pop     r12
0x14001c600  pop     rdi
0x14001c601  pop     rsi
0x14001c602  pop     rbp
0x14001c603  retn
0x14001c605  mov     [rsp+1A0h+var_15C], 10h
0x14001c60d  movzx   esi, di
0x14001c610  jmp     short loc_14001C596
0x14001c612  cmp     r12d, 120h
0x14001c619  ja      loc_14001CAB1
0x14001c61f  lea     rcx, TableNodeLookaside; Lookaside
0x14001c626  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001c62d  nop     dword ptr [rax+rax+00h]
0x14001c632  mov     rbx, rax
0x14001c635  mov     al, dil
0x14001c638  test    rbx, rbx
0x14001c63b  jz      short loc_14001C5C0
0x14001c63d  xor     edx, edx
0x14001c63f  mov     [rbx], r12d
0x14001c642  lea     rcx, PoolLock
0x14001c649  mov     [rbx+4], al
0x14001c64c  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001c653  nop     dword ptr [rax+rax+00h]
0x14001c658  add     cs:dword_14000ECBC, r12d
0x14001c65f  lea     rcx, PoolLock
0x14001c666  xor     edx, edx
0x14001c668  call    cs:__imp_FltReleasePushLockEx
0x14001c66f  nop     dword ptr [rax+rax+00h]
0x14001c674  add     rbx, 8
0x14001c678  jz      loc_14001C5C0
0x14001c67e  xor     edx, edx; Val
0x14001c680  mov     r8d, 108h; Size
0x14001c686  mov     rcx, rbx; void *
0x14001c689  call    memset
0x14001c68e  mov     rcx, rbx; PushLock
0x14001c691  call    cs:__imp_ExInitializePushLock
0x14001c698  nop     dword ptr [rax+rax+00h]
0x14001c69d  and     byte ptr [rbx+48h], 0F8h
0x14001c6a1  mov     r8d, 0FFFEh
0x14001c6a7  mov     al, [rbx+78h]
0x14001c6aa  mov     edx, [rsp+1A0h+var_15C]
0x14001c6ae  and     al, 0F9h
0x14001c6b0  or      al, dil
0x14001c6b3  mov     [rbx+14h], edi
0x14001c6b6  mov     [rbx+78h], al
0x14001c6b9  mov     al, [rbx+0A8h]
0x14001c6bf  and     al, 0FAh
0x14001c6c1  mov     [rbx+18h], edx
0x14001c6c4  or      al, 2
0x14001c6c6  movzx   ecx, al
0x14001c6c9  movzx   eax, word ptr [rbx+1Eh]
0x14001c6cd  and     ax, r8w
0x14001c6d1  mov     [rbx+0A8h], cl
0x14001c6d7  or      ax, si
0x14001c6da  mov     [rbx+1Eh], ax
0x14001c6de  mov     al, [r15+1Ch]
0x14001c6e2  mov     [rbx+1Ch], al
0x14001c6e5  mov     eax, ecx
0x14001c6e7  mov     [rbx+20h], r15
0x14001c6eb  xor     rax, [r15+0A8h]
0x14001c6f2  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001c6f6  xor     rax, rcx
0x14001c6f9  mov     [rbx+0A8h], rax
0x14001c700  mov     eax, [r15+100h]
0x14001c707  add     eax, edi
0x14001c709  mov     [rbx+100h], eax
0x14001c70f  mov     rax, ds:0FFFFF78000000014h
0x14001c719  mov     [rbx+0E0h], rax
0x14001c720  test    dl, 10h
0x14001c723  jz      short loc_14001C729
0x14001c725  and     byte ptr [rbx+1Ch], 0F7h
0x14001c729  lea     rsi, FastMutex
0x14001c730  mov     rcx, rsi; FastMutex
0x14001c733  call    cs:__imp_ExAcquireFastMutex
0x14001c73a  nop     dword ptr [rax+rax+00h]
0x14001c73f  mov     rax, gs:188h
0x14001c748  cmp     [rbx+8], rax
0x14001c74c  jz      loc_14001CAD4
0x14001c752  mov     rcx, rsi; FastMutex
0x14001c755  call    cs:__imp_ExReleaseFastMutex
0x14001c75c  nop     dword ptr [rax+rax+00h]
0x14001c761  xor     edx, edx
0x14001c763  mov     rcx, rbx
0x14001c766  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001c76d  nop     dword ptr [rax+rax+00h]
0x14001c772  mov     rcx, rsi; FastMutex
0x14001c775  call    cs:__imp_ExAcquireFastMutex
0x14001c77c  nop     dword ptr [rax+rax+00h]
0x14001c781  mov     rax, gs:188h
0x14001c78a  mov     [rbx+8], rax
0x14001c78e  mov     [rbx+10h], edi
0x14001c791  mov     rcx, rsi; FastMutex
0x14001c794  call    cs:__imp_ExReleaseFastMutex
0x14001c79b  nop     dword ptr [rax+rax+00h]
0x14001c7a0  lea     rcx, [rsp+1A0h+String1]
0x14001c7a5  call    LuafvIsExcludedName
0x14001c7aa  mov     cl, [rbx+1Dh]
0x14001c7ad  xor     al, cl
0x14001c7af  and     al, dil
0x14001c7b2  xor     al, cl
0x14001c7b4  mov     [rbx+1Dh], al
0x14001c7b7  cmp     qword ptr [r15+0D0h], 0
0x14001c7bf  jz      short loc_14001C7F3
0x14001c7c1  xor     edx, edx
0x14001c7c3  lea     rcx, qword_14000EC58
0x14001c7ca  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001c7d1  nop     dword ptr [rax+rax+00h]
0x14001c7d6  mov     rcx, r15
0x14001c7d9  call    RemoveMruListNode
0x14001c7de  xor     edx, edx
0x14001c7e0  lea     rcx, qword_14000EC58
0x14001c7e7  call    cs:__imp_FltReleasePushLockEx
0x14001c7ee  nop     dword ptr [rax+rax+00h]
0x14001c7f3  movzx   eax, [rsp+1A0h+String1.Length]
0x14001c7f8  lea     rdx, [rsp+1A0h+String1]; SourceString
0x14001c7fd  mov     [rbx+52h], ax
0x14001c801  lea     rcx, [rbx+50h]; DestinationString
0x14001c805  lea     rax, [rbx+108h]
0x14001c80c  mov     [rbx+58h], rax
0x14001c810  call    cs:__imp_RtlCopyUnicodeString
0x14001c817  nop     dword ptr [rax+rax+00h]
0x14001c81c  mov     rsi, [r15+28h]
0x14001c820  xor     edx, edx
0x14001c822  test    r13, r13
0x14001c825  jz      loc_14001C99C
0x14001c82b  mov     eax, dword ptr [rsp+1A0h+var_130]
0x14001c82f  cmp     eax, edi
0x14001c831  jz      loc_14001C98B
0x14001c837  lea     rcx, [rbx+30h]; Links
0x14001c83b  mov     [rcx], rcx
0x14001c83e  mov     [rcx+8], rdx
0x14001c842  mov     [rcx+10h], rdx
0x14001c846  add     [rsi+10h], edi
0x14001c849  test    eax, eax
0x14001c84b  jz      loc_14001C9BA
0x14001c851  cmp     eax, 2
0x14001c854  jnz     loc_14001C982
0x14001c85a  mov     [r13+8], rcx
0x14001c85e  mov     [rcx], r13
0x14001c861  call    cs:__imp_RtlSplay
0x14001c868  nop     dword ptr [rax+rax+00h]
0x14001c86d  mov     [rsi], rax
0x14001c870  lock add [r15+14h], edi
0x14001c875  movzx   eax, [rsp+1A0h+SourceString.Length]
0x14001c87a  xor     r13d, r13d
0x14001c87d  test    ax, ax
0x14001c880  jz      loc_14001C918
0x14001c886  lea     rcx, [rbx+80h]; DestinationString
0x14001c88d  mov     [rcx+2], ax
0x14001c891  lea     rdx, [rsp+1A0h+SourceString]; SourceString
0x14001c896  movzx   eax, [rsp+1A0h+String1.Length]
0x14001c89b  add     rax, [rbx+58h]
0x14001c89f  mov     [rcx+8], rax
0x14001c8a3  call    cs:__imp_RtlCopyUnicodeString
0x14001c8aa  nop     dword ptr [rax+rax+00h]
0x14001c8af  mov     r15, [r15+28h]
0x14001c8b3  lea     rsi, [rbx+60h]
0x14001c8b7  lea     rdx, [rsi+18h]
0x14001c8bb  mov     [rsp+1A0h+var_130], r13
0x14001c8c0  mov     rcx, r15
0x14001c8c3  lea     r8, [rsp+1A0h+var_130]
0x14001c8c8  call    FindNodeOrParent
0x14001c8cd  mov     rcx, [rsp+1A0h+var_130]
0x14001c8d2  cmp     eax, edi
0x14001c8d4  jz      loc_14001C966
0x14001c8da  mov     [rsi], rsi
  ... truncated ...
```
