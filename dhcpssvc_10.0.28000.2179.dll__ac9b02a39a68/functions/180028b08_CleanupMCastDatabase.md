# CleanupMCastDatabase

- ea: `0x180028b08`
- end: `0x18002905e`
- name: `CleanupMCastDatabase`
- size: `1366`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004ff20`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c164`
- `0x18000e814`
- `0x180028388`
- `0x1800283bc`
- `0x180028558`
- `0x180028670`
- `0x1800288a0`
- `0x1800288d0`
- `0x180028b08`
- `0x1800313bc`
- `0x18008f58c`

## import_xrefs

- `ESENT!JetUpdate` at `0x180028e97`
- `ESENT!JetUpdate` at `0x180028e97`
- `ESENT!JetSetCurrentIndex` at `0x180028c77`
- `ESENT!JetSetCurrentIndex` at `0x180028c77`
- `ESENT!JetMakeKey` at `0x180028cb6`
- `ESENT!JetMakeKey` at `0x180028cb6`
- `ESENT!JetSeek` at `0x180028cea`
- `ESENT!JetSeek` at `0x180028cea`
- `ESENT!JetDelete` at `0x180028f5e`
- `ESENT!JetDelete` at `0x180028f5e`
- `ESENT!JetBeginTransaction` at `0x180028e0d`
- `ESENT!JetBeginTransaction` at `0x180028f36`
- `ESENT!JetBeginTransaction` at `0x180028e0d`
- `ESENT!JetBeginTransaction` at `0x180028f36`
- `ESENT!JetPrepareUpdate` at `0x180028e41`
- `ESENT!JetPrepareUpdate` at `0x180028e41`
- `KERNEL32!WaitForSingleObject` at `0x180028c2f`
- `KERNEL32!WaitForSingleObject` at `0x18002901f`
- `KERNEL32!WaitForSingleObject` at `0x180028c2f`
- `KERNEL32!WaitForSingleObject` at `0x18002901f`
- `KERNEL32!CompareFileTime` at `0x180028d94`
- `KERNEL32!CompareFileTime` at `0x180028db9`
- `KERNEL32!CompareFileTime` at `0x180028d94`
- `KERNEL32!CompareFileTime` at `0x180028db9`
- `KERNEL32!EnterCriticalSection` at `0x180028bb6`
- `KERNEL32!EnterCriticalSection` at `0x180028c4e`
- `KERNEL32!EnterCriticalSection` at `0x180028bb6`
- `KERNEL32!EnterCriticalSection` at `0x180028c4e`
- `KERNEL32!LeaveCriticalSection` at `0x180028c18`
- `KERNEL32!LeaveCriticalSection` at `0x180029008`
- `KERNEL32!LeaveCriticalSection` at `0x18002903e`
- `KERNEL32!LeaveCriticalSection` at `0x180028c18`
- `KERNEL32!LeaveCriticalSection` at `0x180029008`
- `KERNEL32!LeaveCriticalSection` at `0x18002903e`

## string_xrefs

- `0x180028ea5`: `M:CommitUpdate`
- `0x180028f6c`: `M:DeleteCurrentRecord`
- `0x180028e4f`: `M:Cleanup:PrepUpdate`

## pseudocode

```c
__int64 __fastcall CleanupMCastDatabase(const FILETIME *a1, const FILETIME *a2, int a3, _DWORD *a4, _DWORD *a5)
{
  unsigned int v5; // esi
  JET_SESID v7; // r14
  JET_TABLEID v8; // r13
  _DWORD *v9; // r12
  int v10; // edi
  unsigned int v11; // eax
  unsigned int Key; // eax
  unsigned int v13; // eax
  unsigned int Value; // ebx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-34h] BYREF
  int pvData; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-2Ch] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-28h] BYREF
  __int128 v28; // [rsp+48h] [rbp-20h] BYREF
  JET_TABLEID v29; // [rsp+58h] [rbp-10h]
  char v33; // [rsp+C8h] [rbp+60h] BYREF

  FileTime1 = 0;
  LODWORD(v29) = 0;
  v28 = 0;
  v26 = 0;
  v5 = 0;
  v23 = 0;
  v24 = 0;
  pvData = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids);
  v7 = DhcpGlobalJetServerSession;
  v8 = MadcapGlobalClientTableHandle;
  v9 = a5;
  *a4 = 0;
  *((_QWORD *)&v28 + 1) = v7;
  v29 = v8;
  *v9 = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( (unsigned int)MadcapJetPrepareSearch(&v28, *(_QWORD *)MadcapGlobalClientTable, 1)
    || (v23 = 4, (unsigned int)MadcapJetGetValue(&v28, *(unsigned int *)(MadcapGlobalClientTable + 8), &pvData, &v23)) )
  {
LABEL_42:
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  }
  else
  {
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( WaitForSingleObject(DhcpGlobalProcessTerminationEvent, 0) )
    {
      while ( 1 )
      {
        EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        v10 = 1;
        v11 = JetSetCurrentIndex(
                DhcpGlobalJetServerSession,
                MadcapGlobalClientTableHandle,
                *(_QWORD *)MadcapGlobalClientTable);
        if ( (unsigned int)DhcpMapJetError(v11, "M:Cleanup:SetcurrentIndex") )
          goto LABEL_42;
        Key = JetMakeKey(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, &pvData, 4u, 1u);
        if ( (unsigned int)DhcpMapJetError(Key, "M:Cleanup:MakeKey")
          || (v13 = JetSeek(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, 8u),
              (unsigned int)DhcpMapJetError(v13, "M:Cleanup:Seek")) )
        {
LABEL_41:
          if ( !v10 )
            return v5;
          goto LABEL_42;
        }
        v23 = 4;
        Value = MadcapJetGetValue(&v28, *(unsigned int *)(MadcapGlobalClientTable + 8), &v24, &v23);
        if ( Value )
          break;
        v23 = 4;
        Value = MadcapJetGetValue(&v28, *(unsigned int *)(MadcapGlobalClientTable + 88), &v26, &v23);
        if ( Value )
          break;
        v23 = 8;
        Value = MadcapJetGetValue(&v28, *(unsigned int *)(MadcapGlobalClientTable + 120), &FileTime1, &v23);
        if ( Value )
          break;
        if ( CompareFileTime(&FileTime1, a1) < 0 )
        {
          if ( a3 == Value && CompareFileTime(&FileTime1, a2) >= 0 )
          {
            v23 = 1;
            Value = MadcapJetGetValue(&v28, *(unsigned int *)(MadcapGlobalClientTable + 56), &v33, &v23);
            if ( Value )
              break;
            if ( (v33 & 3) != 3 )
            {
              v15 = JetBeginTransaction(v7);
              if ( (unsigned int)DhcpMapJetError(v15, "M:BeginTransaction") )
                goto LABEL_41;
              v16 = JetPrepareUpdate(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, Value + 2);
              if ( (unsigned int)DhcpMapJetError(v16, "M:Cleanup:PrepUpdate") )
                goto LABEL_24;
              v33 |= 3u;
              if ( (unsigned int)MadcapJetSetValue(
                                   &v28,
                                   *(unsigned int *)(MadcapGlobalClientTable + 56),
                                   &v33,
                                   Value + 1) )
                goto LABEL_24;
              v17 = JetUpdate(v7, v8, 0, 0, 0);
              if ( (unsigned int)DhcpMapJetError(v17, "M:CommitUpdate") )
                goto LABEL_24;
              if ( (unsigned int)MadcapJetCommitTransaction(&v28) )
                goto LABEL_41;
              ++*a4;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v19 = DhcpIpAddressToDottedString(v24);
              WPP_SF_s(v18, 29, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, v19);
            }
            if ( !(unsigned int)DhcpMScopeReleaseAddress(v26, v24) )
            {
              v20 = JetBeginTransaction(v7);
              if ( (unsigned int)DhcpMapJetError(v20, "M:BeginTransaction") )
                goto LABEL_41;
              v21 = JetDelete(v7, v8);
              if ( !(unsigned int)DhcpMapJetError(v21, "M:DeleteCurrentRecord") )
              {
                if ( (unsigned int)MadcapJetCommitTransaction(&v28) )
                  goto LABEL_41;
                ++*v9;
                goto LABEL_38;
              }
LABEL_24:
              if ( (unsigned int)MadcapJetRollBack(&v28) )
                goto LABEL_41;
            }
          }
        }
LABEL_38:
        if ( !(unsigned int)MadcapJetNextRecord(&v28) )
        {
          v23 = 4;
          if ( !(unsigned int)MadcapJetGetValue(&v28, *(unsigned int *)(MadcapGlobalClientTable + 8), &pvData, &v23) )
          {
            LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
            v10 = 0;
            if ( WaitForSingleObject(DhcpGlobalProcessTerminationEvent, 0) )
              continue;
          }
        }
        goto LABEL_41;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, Value);
      v5 = Value;
      goto LABEL_38;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180028b08  mov     [rsp-40h+arg_10], r8d
0x180028b0d  mov     [rsp-40h+arg_8], rdx
0x180028b12  mov     [rsp-40h+lpFileTime2], rcx
0x180028b17  push    rbp
0x180028b18  push    rbx
0x180028b19  push    rsi
0x180028b1a  push    rdi
0x180028b1b  push    r12
0x180028b1d  push    r13
0x180028b1f  push    r14
0x180028b21  push    r15
0x180028b23  mov     rbp, rsp
0x180028b26  sub     rsp, 68h
0x180028b2a  xor     eax, eax
0x180028b2c  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180028b34  xorps   xmm0, xmm0
0x180028b37  mov     dword ptr [rbp+var_10], eax
0x180028b3a  movups  [rbp+var_20], xmm0
0x180028b3e  mov     [rbp+var_2C], eax
0x180028b41  xor     esi, esi
0x180028b43  mov     r15, r9
0x180028b46  mov     [rbp+var_38], 0
0x180028b4d  mov     [rbp+var_34], 0
0x180028b54  mov     [rbp+pvData], 0
0x180028b5b  mov     [rbp+arg_18], 0
0x180028b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b66  lea     rax, WPP_GLOBAL_Control
0x180028b6d  cmp     rcx, rax
0x180028b70  jz      short loc_180028B8E
0x180028b72  test    dword ptr [rcx+1Ch], 8000h
0x180028b79  jz      short loc_180028B8E
0x180028b7b  mov     rcx, [rcx+10h]
0x180028b7f  lea     edx, [rsi+1Ch]
0x180028b82  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180028b89  call    WPP_SF_
0x180028b8e  mov     r14, cs:DhcpGlobalJetServerSession
0x180028b95  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180028b9c  mov     r13, cs:MadcapGlobalClientTableHandle
0x180028ba3  mov     r12, [rbp+arg_20]
0x180028ba7  mov     [r15], esi
0x180028baa  mov     qword ptr [rbp+var_20+8], r14
0x180028bae  mov     [rbp+var_10], r13
0x180028bb2  mov     [r12], esi
0x180028bb6  call    cs:__imp_EnterCriticalSection
0x180028bbd  nop     dword ptr [rax+rax+00h]
0x180028bc2  mov     rdx, cs:MadcapGlobalClientTable
0x180028bc9  lea     rcx, [rbp+var_20]
0x180028bcd  xor     r9d, r9d
0x180028bd0  mov     [rsp+68h+grbit], esi
0x180028bd4  mov     rdx, [rdx]
0x180028bd7  lea     r8d, [r9+1]
0x180028bdb  call    MadcapJetPrepareSearch
0x180028be0  test    eax, eax
0x180028be2  jnz     loc_180029037
0x180028be8  mov     rdx, cs:MadcapGlobalClientTable
0x180028bef  lea     ebx, [rax+4]
0x180028bf2  mov     [rbp+var_38], ebx
0x180028bf5  lea     r9, [rbp+var_38]
0x180028bf9  lea     r8, [rbp+pvData]
0x180028bfd  lea     rcx, [rbp+var_20]
0x180028c01  mov     edx, [rdx+8]
0x180028c04  call    MadcapJetGetValue
0x180028c09  test    eax, eax
0x180028c0b  jnz     loc_180029037
0x180028c11  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180028c18  call    cs:__imp_LeaveCriticalSection
0x180028c1f  nop     dword ptr [rax+rax+00h]
0x180028c24  mov     rcx, cs:DhcpGlobalProcessTerminationEvent; hHandle
0x180028c2b  xor     edx, edx; dwMilliseconds
0x180028c2d  xor     edi, edi
0x180028c2f  call    cs:__imp_WaitForSingleObject
0x180028c36  nop     dword ptr [rax+rax+00h]
0x180028c3b  test    eax, eax
0x180028c3d  jz      loc_18002904A
0x180028c43  test    edi, edi
0x180028c45  jnz     short loc_180028C5F
0x180028c47  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180028c4e  call    cs:__imp_EnterCriticalSection
0x180028c55  nop     dword ptr [rax+rax+00h]
0x180028c5a  mov     edi, 1
0x180028c5f  mov     r8, cs:MadcapGlobalClientTable
0x180028c66  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028c6d  mov     rcx, cs:DhcpGlobalJetServerSession
0x180028c74  mov     r8, [r8]
0x180028c77  call    cs:__imp_JetSetCurrentIndex
0x180028c7e  nop     dword ptr [rax+rax+00h]
0x180028c83  mov     ecx, eax
0x180028c85  lea     rdx, aMCleanupSetcur; "M:Cleanup:SetcurrentIndex"
0x180028c8c  call    DhcpMapJetError
0x180028c91  test    eax, eax
0x180028c93  jnz     loc_180029037
0x180028c99  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180028ca0  lea     r8, [rbp+pvData]; pvData
0x180028ca4  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180028cab  mov     r9d, ebx; cbData
0x180028cae  mov     [rsp+68h+grbit], 1; grbit
0x180028cb6  call    cs:__imp_JetMakeKey
0x180028cbd  nop     dword ptr [rax+rax+00h]
0x180028cc2  mov     ecx, eax
0x180028cc4  lea     rdx, aMCleanupMakeke; "M:Cleanup:MakeKey"
0x180028ccb  call    DhcpMapJetError
0x180028cd0  test    eax, eax
0x180028cd2  jnz     loc_180029033
0x180028cd8  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180028cdf  lea     r8d, [rax+8]; grbit
0x180028ce3  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180028cea  call    cs:__imp_JetSeek
0x180028cf1  nop     dword ptr [rax+rax+00h]
0x180028cf6  mov     ecx, eax
0x180028cf8  lea     rdx, aMCleanupSeek; "M:Cleanup:Seek"
0x180028cff  call    DhcpMapJetError
0x180028d04  test    eax, eax
0x180028d06  jnz     loc_180029033
0x180028d0c  mov     rdx, cs:MadcapGlobalClientTable
0x180028d13  lea     r9, [rbp+var_38]
0x180028d17  mov     [rbp+var_38], ebx
0x180028d1a  lea     r8, [rbp+var_34]
0x180028d1e  lea     rcx, [rbp+var_20]
0x180028d22  mov     edx, [rdx+8]
0x180028d25  call    MadcapJetGetValue
0x180028d2a  mov     ebx, eax
0x180028d2c  test    eax, eax
0x180028d2e  jnz     loc_180028F97
0x180028d34  mov     rdx, cs:MadcapGlobalClientTable
0x180028d3b  lea     r9, [rbp+var_38]
0x180028d3f  mov     [rbp+var_38], 4
0x180028d46  lea     r8, [rbp+var_2C]
0x180028d4a  lea     rcx, [rbp+var_20]
0x180028d4e  mov     edx, [rdx+58h]
0x180028d51  call    MadcapJetGetValue
0x180028d56  mov     ebx, eax
0x180028d58  test    eax, eax
0x180028d5a  jnz     loc_180028F97
0x180028d60  mov     rdx, cs:MadcapGlobalClientTable
0x180028d67  lea     r9, [rbp+var_38]
0x180028d6b  mov     [rbp+var_38], 8
0x180028d72  lea     r8, [rbp+FileTime1]
0x180028d76  lea     rcx, [rbp+var_20]
0x180028d7a  mov     edx, [rdx+78h]
0x180028d7d  call    MadcapJetGetValue
0x180028d82  mov     ebx, eax
0x180028d84  test    eax, eax
0x180028d86  jnz     loc_180028F97
0x180028d8c  mov     rdx, [rbp+lpFileTime2]; lpFileTime2
0x180028d90  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180028d94  call    cs:__imp_CompareFileTime
0x180028d9b  nop     dword ptr [rax+rax+00h]
0x180028da0  test    eax, eax
0x180028da2  jns     loc_180028FCA
0x180028da8  cmp     [rbp+arg_10], ebx
0x180028dab  jnz     loc_180028EE4
0x180028db1  mov     rdx, [rbp+arg_8]; lpFileTime2
0x180028db5  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180028db9  call    cs:__imp_CompareFileTime
0x180028dc0  nop     dword ptr [rax+rax+00h]
0x180028dc5  test    eax, eax
0x180028dc7  js      loc_180028EE4
0x180028dcd  mov     rdx, cs:MadcapGlobalClientTable
0x180028dd4  lea     r9, [rbp+var_38]
0x180028dd8  mov     [rbp+var_38], 1
0x180028ddf  lea     r8, [rbp+arg_18]
0x180028de3  lea     rcx, [rbp+var_20]
0x180028de7  mov     edx, [rdx+38h]
0x180028dea  call    MadcapJetGetValue
0x180028def  mov     ebx, eax
0x180028df1  test    eax, eax
0x180028df3  jnz     loc_180028F97
0x180028df9  movzx   eax, [rbp+arg_18]
0x180028dfd  and     eax, 0FFFFFF03h
0x180028e02  cmp     al, 3
0x180028e04  jz      loc_180028FCA
0x180028e0a  mov     rcx, r14; sesid
0x180028e0d  call    cs:__imp_JetBeginTransaction
0x180028e14  nop     dword ptr [rax+rax+00h]
0x180028e19  mov     ecx, eax
0x180028e1b  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180028e22  call    DhcpMapJetError
0x180028e27  test    eax, eax
0x180028e29  jnz     loc_180029033
0x180028e2f  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180028e36  lea     r8d, [rbx+2]; prep
0x180028e3a  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180028e41  call    cs:__imp_JetPrepareUpdate
0x180028e48  nop     dword ptr [rax+rax+00h]
0x180028e4d  mov     ecx, eax
0x180028e4f  lea     rdx, aMCleanupPrepup; "M:Cleanup:PrepUpdate"
0x180028e56  call    DhcpMapJetError
0x180028e5b  test    eax, eax
0x180028e5d  jnz     short loc_180028ECE
0x180028e5f  mov     rdx, cs:MadcapGlobalClientTable
0x180028e66  lea     r9d, [rbx+1]
0x180028e6a  or      [rbp+arg_18], 3
0x180028e6e  lea     r8, [rbp+arg_18]
0x180028e72  lea     rcx, [rbp+var_20]
0x180028e76  mov     edx, [rdx+38h]
0x180028e79  call    MadcapJetSetValue
0x180028e7e  test    eax, eax
0x180028e80  jnz     short loc_180028ECE
0x180028e82  xor     r9d, r9d; cbBookmark
0x180028e85  mov     qword ptr [rsp+68h+grbit], 0; pcbActual
0x180028e8e  xor     r8d, r8d; pvBookmark
0x180028e91  mov     rdx, r13; tableid
0x180028e94  mov     rcx, r14; sesid
0x180028e97  call    cs:__imp_JetUpdate
0x180028e9e  nop     dword ptr [rax+rax+00h]
0x180028ea3  mov     ecx, eax
0x180028ea5  lea     rdx, aMCommitupdate; "M:CommitUpdate"
0x180028eac  call    DhcpMapJetError
0x180028eb1  test    eax, eax
0x180028eb3  jnz     short loc_180028ECE
0x180028eb5  lea     rcx, [rbp+var_20]
0x180028eb9  call    MadcapJetCommitTransaction
0x180028ebe  test    eax, eax
0x180028ec0  jnz     loc_180029033
0x180028ec6  inc     dword ptr [r15]
0x180028ec9  jmp     loc_180028FCA
0x180028ece  lea     rcx, [rbp+var_20]
0x180028ed2  call    MadcapJetRollBack
0x180028ed7  test    eax, eax
0x180028ed9  jnz     loc_180029033
0x180028edf  jmp     loc_180028FCA
0x180028ee4  mov     rbx, cs:WPP_GLOBAL_Control
0x180028eeb  lea     rax, WPP_GLOBAL_Control
0x180028ef2  cmp     rbx, rax
0x180028ef5  jz      short loc_180028F20
0x180028ef7  test    byte ptr [rbx+1Ch], 80h
0x180028efb  jz      short loc_180028F20
0x180028efd  mov     ecx, [rbp+var_34]
0x180028f00  mov     rbx, [rbx+10h]
0x180028f04  call    DhcpIpAddressToDottedString
0x180028f09  mov     r9, rax
0x180028f0c  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180028f13  mov     edx, 1Dh
0x180028f18  mov     rcx, rbx
0x180028f1b  call    WPP_SF_s
0x180028f20  mov     edx, [rbp+var_34]
0x180028f23  mov     ecx, [rbp+var_2C]
0x180028f26  call    DhcpMScopeReleaseAddress
0x180028f2b  test    eax, eax
0x180028f2d  jnz     loc_180028FCA
0x180028f33  mov     rcx, r14; sesid
0x180028f36  call    cs:__imp_JetBeginTransaction
0x180028f3d  nop     dword ptr [rax+rax+00h]
0x180028f42  mov     ecx, eax
0x180028f44  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180028f4b  call    DhcpMapJetError
0x180028f50  test    eax, eax
0x180028f52  jnz     loc_180029033
0x180028f58  mov     rdx, r13; tableid
0x180028f5b  mov     rcx, r14; sesid
0x180028f5e  call    cs:__imp_JetDelete
0x180028f65  nop     dword ptr [rax+rax+00h]
0x180028f6a  mov     ecx, eax
0x180028f6c  lea     rdx, aMDeletecurrent; "M:DeleteCurrentRecord"
0x180028f73  call    DhcpMapJetError
0x180028f78  lea     rcx, [rbp+var_20]
0x180028f7c  test    eax, eax
0x180028f7e  jnz     loc_180028ED2
0x180028f84  call    MadcapJetCommitTransaction
0x180028f89  test    eax, eax
0x180028f8b  jnz     loc_180029033
0x180028f91  inc     dword ptr [r12]
0x180028f95  jmp     short loc_180028FCA
0x180028f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f9e  lea     rax, WPP_GLOBAL_Control
0x180028fa5  cmp     rcx, rax
0x180028fa8  jz      short loc_180028FC8
0x180028faa  test    byte ptr [rcx+1Ch], 10h
0x180028fae  jz      short loc_180028FC8
0x180028fb0  mov     rcx, [rcx+10h]
0x180028fb4  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180028fbb  mov     edx, 1Eh
0x180028fc0  mov     r9d, ebx
0x180028fc3  call    WPP_SF_D
0x180028fc8  mov     esi, ebx
0x180028fca  lea     rcx, [rbp+var_20]
0x180028fce  call    MadcapJetNextRecord
0x180028fd3  test    eax, eax
0x180028fd5  jnz     short loc_180029033
0x180028fd7  mov     rdx, cs:MadcapGlobalClientTable
0x180028fde  lea     ebx, [rax+4]
0x180028fe1  mov     [rbp+var_38], ebx
0x180028fe4  lea     r9, [rbp+var_38]
0x180028fe8  lea     r8, [rbp+pvData]
0x180028fec  lea     rcx, [rbp+var_20]
0x180028ff0  mov     edx, [rdx+8]
0x180028ff3  call    MadcapJetGetValue
0x180028ff8  test    eax, eax
0x180028ffa  jnz     short loc_180029033
0x180028ffc  cmp     edi, 1
0x180028fff  jnz     short loc_180029016
0x180029001  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029008  call    cs:__imp_LeaveCriticalSection
0x18002900f  nop     dword ptr [rax+rax+00h]
0x180029014  xor     edi, edi
0x180029016  mov     rcx, cs:DhcpGlobalProcessTerminationEvent; hHandle
0x18002901d  xor     edx, edx; dwMilliseconds
0x18002901f  call    cs:__imp_WaitForSingleObject
0x180029026  nop     dword ptr [rax+rax+00h]
0x18002902b  test    eax, eax
  ... truncated ...
```
