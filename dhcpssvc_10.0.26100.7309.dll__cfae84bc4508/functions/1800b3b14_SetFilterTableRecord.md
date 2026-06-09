# SetFilterTableRecord

- ea: `0x1800b3b14`
- end: `0x1800b3e3a`
- name: `SetFilterTableRecord`
- size: `806`
- prototype: `__int64 __fastcall(int, unsigned __int8, int, int, char, char, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b30e0`

## callees

- `0x180002854`
- `0x1800b3b14`
- `0x1800b4da8`
- `0x1800b4f3c`
- `0x1800b4f88`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800b3cad`
- `msvcrt!wcsncpy_s` at `0x1800b3cad`
- `ESENT!JetUpdate` at `0x1800b3d21`
- `ESENT!JetUpdate` at `0x1800b3d21`
- `ESENT!JetBeginTransaction` at `0x1800b3b6c`
- `ESENT!JetBeginTransaction` at `0x1800b3b6c`
- `ESENT!JetRollback` at `0x1800b3db2`
- `ESENT!JetRollback` at `0x1800b3db2`
- `ESENT!JetCommitTransaction` at `0x1800b3d8d`
- `ESENT!JetCommitTransaction` at `0x1800b3d8d`
- `ESENT!JetPrepareUpdate` at `0x1800b3d63`
- `ESENT!JetPrepareUpdate` at `0x1800b3d63`
- `KERNEL32!EnterCriticalSection` at `0x1800b3b59`
- `KERNEL32!EnterCriticalSection` at `0x1800b3b59`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3e04`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3e04`

## string_xrefs

- `0x1800b3d9b`: `FilterJetCommitTransaction`
- `0x1800b3dc0`: `FilterJetRollback`
- `0x1800b3d2f`: `FilterJetCommitUpdate`
- `0x1800b3d71`: `FilterJetCancelUpdate`

## pseudocode

```c
__int64 __fastcall SetFilterTableRecord(
        int a1,
        unsigned __int8 a2,
        int a3,
        int a4,
        __int64 a5,
        char a6,
        wchar_t *Source,
        int a8)
{
  const wchar_t *v8; // r14
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // r8
  int v17; // ebx
  int v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  int v25; // eax
  int v26; // edx
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  wchar_t *v30; // rdx
  __int64 v31; // rax
  unsigned int v32; // ebx
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned __int8 v37; // [rsp+40h] [rbp-C0h] BYREF
  char v38; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Destination[128]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = Source;
  v37 = a2;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v12 = JetBeginTransaction(DhcpGlobalJetServerSession);
  v15 = FilterMapJetError(v12, "FilterJetBeginTransaction");
  if ( v15 )
    goto LABEL_27;
  v17 = a8;
  v15 = FilterJetPrepareUpdate(v14, v13, v16, &a5);
  if ( v15 )
    goto LABEL_27;
  if ( v17 == 1 && (unsigned int)FilterJetSetValue(v19, v18, *(_DWORD *)(FilterGlobalTable + 8), a1, v37) )
    goto LABEL_24;
  v20 = *(_DWORD *)(FilterGlobalTable + 24);
  if ( a4 == 1
     ? FilterJetSetValue(v19, v18, v20, (unsigned int)&a5, 1u)
     : (unsigned int)FilterJetSetValue(v19, v18, v20, 0, 0) )
  {
    goto LABEL_24;
  }
  v24 = *(_DWORD *)(FilterGlobalTable + 40);
  if ( a3 == 1 )
  {
    v38 = 1;
    v25 = FilterJetSetValue(v23, v22, v24, (unsigned int)&v38, 1u);
  }
  else
  {
    v25 = FilterJetSetValue(v23, v22, v24, 0, 0);
  }
  if ( v25
    || (unsigned int)FilterJetSetValue(v27, v26, *(_DWORD *)(FilterGlobalTable + 56), (unsigned int)&v37, 1u)
    || (unsigned int)FilterJetSetValue(v29, v28, *(_DWORD *)(FilterGlobalTable + 72), (unsigned int)&a6, 1u) )
  {
    goto LABEL_24;
  }
  if ( !v8 )
    goto LABEL_21;
  wcsncpy_s(Destination, 0x80u, v8, 0xFFFFFFFFFFFFFFFFuLL);
  v30 = Destination;
  v31 = 0x3FFFFFFF;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v31;
  }
  while ( v31 );
  if ( !v31
    || (unsigned int)FilterJetSetValue(
                       2 * (0x3FFFFFFF - (int)v31),
                       (_DWORD)v30,
                       *(_DWORD *)(FilterGlobalTable + 88),
                       (unsigned int)Destination,
                       v31 != 0 ? 2 * (0x3FFFFFFF - v31) + 2 : 2) )
  {
LABEL_24:
    v33 = JetPrepareUpdate(DhcpGlobalJetServerSession, FilterGlobalTableHandle, 3u);
    v15 = FilterMapJetError(v33, "FilterJetCancelUpdate");
  }
  else
  {
LABEL_21:
    v32 = JetUpdate(DhcpGlobalJetServerSession, FilterGlobalTableHandle, 0, 0, 0);
    v15 = FilterMapJetError(v32, "FilterJetCommitUpdate");
    if ( v32 == -1605 )
      v15 = 4;
  }
  if ( v15 )
  {
LABEL_27:
    v35 = JetRollback(DhcpGlobalJetServerSession, 0);
    FilterMapJetError(v35, "FilterJetRollback");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_0db8580d4aa93e5d318c9249289cee35_Traceguids, v15);
  }
  else
  {
    v34 = JetCommitTransaction(DhcpGlobalJetServerSession, 1u);
    FilterMapJetError(v34, "FilterJetCommitTransaction");
  }
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return v15;
}

```

## disassembly

```asm
0x1800b3b14  mov     [rsp-8+arg_10], rbx
0x1800b3b19  push    rbp
0x1800b3b1a  push    rsi
0x1800b3b1b  push    rdi
0x1800b3b1c  push    r12
0x1800b3b1e  push    r13
0x1800b3b20  push    r14
0x1800b3b22  push    r15
0x1800b3b24  lea     rbp, [rsp-60h]
0x1800b3b29  sub     rsp, 160h
0x1800b3b30  mov     rax, cs:__security_cookie
0x1800b3b37  xor     rax, rsp
0x1800b3b3a  mov     [rbp+90h+var_40], rax
0x1800b3b3e  mov     r14, [rbp+90h+Source]
0x1800b3b45  mov     rsi, rcx
0x1800b3b48  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b3b4f  mov     [rsp+190h+var_150], dl
0x1800b3b53  mov     r15d, r9d
0x1800b3b56  mov     r12d, r8d
0x1800b3b59  call    cs:__imp_EnterCriticalSection
0x1800b3b60  nop     dword ptr [rax+rax+00h]
0x1800b3b65  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3b6c  call    cs:__imp_JetBeginTransaction
0x1800b3b73  nop     dword ptr [rax+rax+00h]
0x1800b3b78  mov     ecx, eax
0x1800b3b7a  lea     rdx, aFilterjetbegin; "FilterJetBeginTransaction"
0x1800b3b81  call    FilterMapJetError
0x1800b3b86  xor     r13d, r13d
0x1800b3b89  mov     edi, eax
0x1800b3b8b  test    eax, eax
0x1800b3b8d  jnz     loc_1800B3DA9
0x1800b3b93  movzx   eax, [rsp+190h+var_150]
0x1800b3b98  lea     r9, [rbp+90h+arg_20]
0x1800b3b9f  mov     ebx, [rbp+90h+arg_38]
0x1800b3ba5  mov     [rsp+190h+var_158], ebx
0x1800b3ba9  mov     [rsp+190h+var_160], eax
0x1800b3bad  mov     [rsp+190h+var_168], rsi
0x1800b3bb2  call    FilterJetPrepareUpdate
0x1800b3bb7  mov     edi, eax
0x1800b3bb9  test    eax, eax
0x1800b3bbb  jnz     loc_1800B3DA9
0x1800b3bc1  lea     edi, [rax+1]
0x1800b3bc4  cmp     ebx, edi
0x1800b3bc6  jnz     short loc_1800B3BEC
0x1800b3bc8  mov     r8, cs:FilterGlobalTable
0x1800b3bcf  mov     r9, rsi
0x1800b3bd2  movzx   eax, [rsp+190h+var_150]
0x1800b3bd7  mov     dword ptr [rsp+190h+pcbActual], eax
0x1800b3bdb  mov     r8d, [r8+8]
0x1800b3bdf  call    FilterJetSetValue
0x1800b3be4  test    eax, eax
0x1800b3be6  jnz     loc_1800B3D4F
0x1800b3bec  mov     r8, cs:FilterGlobalTable
0x1800b3bf3  mov     r8d, [r8+18h]
0x1800b3bf7  cmp     r15d, edi
0x1800b3bfa  jnz     short loc_1800B3C09
0x1800b3bfc  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b3c00  lea     r9, [rbp+90h+arg_20]
0x1800b3c07  jmp     short loc_1800B3C11
0x1800b3c09  mov     dword ptr [rsp+190h+pcbActual], r13d
0x1800b3c0e  xor     r9d, r9d
0x1800b3c11  call    FilterJetSetValue
0x1800b3c16  test    eax, eax
0x1800b3c18  jnz     loc_1800B3D4F
0x1800b3c1e  mov     r8, cs:FilterGlobalTable
0x1800b3c25  mov     r8d, [r8+28h]
0x1800b3c29  cmp     r12d, edi
0x1800b3c2c  jnz     short loc_1800B3C3E
0x1800b3c2e  mov     [rsp+190h+var_148], dil
0x1800b3c33  lea     r9, [rsp+190h+var_148]
0x1800b3c38  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b3c3c  jmp     short loc_1800B3C46
0x1800b3c3e  mov     dword ptr [rsp+190h+pcbActual], r13d
0x1800b3c43  xor     r9d, r9d
0x1800b3c46  call    FilterJetSetValue
0x1800b3c4b  test    eax, eax
0x1800b3c4d  jnz     loc_1800B3D4F
0x1800b3c53  mov     r8, cs:FilterGlobalTable
0x1800b3c5a  lea     r9, [rsp+190h+var_150]
0x1800b3c5f  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b3c63  mov     r8d, [r8+38h]
0x1800b3c67  call    FilterJetSetValue
0x1800b3c6c  test    eax, eax
0x1800b3c6e  jnz     loc_1800B3D4F
0x1800b3c74  mov     r8, cs:FilterGlobalTable
0x1800b3c7b  lea     r9, [rbp+90h+arg_28]
0x1800b3c82  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b3c86  mov     r8d, [r8+48h]
0x1800b3c8a  call    FilterJetSetValue
0x1800b3c8f  test    eax, eax
0x1800b3c91  jnz     loc_1800B3D4F
0x1800b3c97  test    r14, r14
0x1800b3c9a  jz      short loc_1800B3D08
0x1800b3c9c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800b3ca0  lea     rcx, [rsp+190h+Destination]; Destination
0x1800b3ca5  mov     r8, r14; Source
0x1800b3ca8  mov     edx, 80h; SizeInWords
0x1800b3cad  call    cs:__imp_wcsncpy_s
0x1800b3cb4  nop     dword ptr [rax+rax+00h]
0x1800b3cb9  mov     ecx, 3FFFFFFFh
0x1800b3cbe  lea     rdx, [rsp+190h+Destination]
0x1800b3cc3  mov     eax, ecx
0x1800b3cc5  cmp     [rdx], r13w
0x1800b3cc9  jz      short loc_1800B3CD4
0x1800b3ccb  add     rdx, 2
0x1800b3ccf  sub     rax, rdi
0x1800b3cd2  jnz     short loc_1800B3CC5
0x1800b3cd4  test    rax, rax
0x1800b3cd7  jz      short loc_1800B3D4F
0x1800b3cd9  mov     r8, cs:FilterGlobalTable
0x1800b3ce0  lea     r9, [rsp+190h+Destination]
0x1800b3ce5  sub     rcx, rax
0x1800b3ce8  add     rcx, rcx
0x1800b3ceb  neg     rax
0x1800b3cee  mov     r8d, [r8+58h]
0x1800b3cf2  sbb     rax, rax
0x1800b3cf5  and     rax, rcx
0x1800b3cf8  add     eax, 2
0x1800b3cfb  mov     dword ptr [rsp+190h+pcbActual], eax
0x1800b3cff  call    FilterJetSetValue
0x1800b3d04  test    eax, eax
0x1800b3d06  jnz     short loc_1800B3D4F
0x1800b3d08  mov     rdx, cs:FilterGlobalTableHandle; tableid
0x1800b3d0f  xor     r9d, r9d; cbBookmark
0x1800b3d12  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3d19  xor     r8d, r8d; pvBookmark
0x1800b3d1c  mov     [rsp+190h+pcbActual], r13; pcbActual
0x1800b3d21  call    cs:__imp_JetUpdate
0x1800b3d28  nop     dword ptr [rax+rax+00h]
0x1800b3d2d  mov     ecx, eax
0x1800b3d2f  lea     rdx, aFilterjetcommi_0; "FilterJetCommitUpdate"
0x1800b3d36  mov     ebx, eax
0x1800b3d38  call    FilterMapJetError
0x1800b3d3d  mov     edi, eax
0x1800b3d3f  cmp     ebx, 0FFFFF9BBh
0x1800b3d45  mov     eax, 4
0x1800b3d4a  cmovz   edi, eax
0x1800b3d4d  jmp     short loc_1800B3D7F
0x1800b3d4f  mov     rdx, cs:FilterGlobalTableHandle; tableid
0x1800b3d56  mov     r8d, 3; prep
0x1800b3d5c  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3d63  call    cs:__imp_JetPrepareUpdate
0x1800b3d6a  nop     dword ptr [rax+rax+00h]
0x1800b3d6f  mov     ecx, eax
0x1800b3d71  lea     rdx, aFilterjetcance; "FilterJetCancelUpdate"
0x1800b3d78  call    FilterMapJetError
0x1800b3d7d  mov     edi, eax
0x1800b3d7f  test    edi, edi
0x1800b3d81  jnz     short loc_1800B3DA9
0x1800b3d83  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3d8a  lea     edx, [rdi+1]; grbit
0x1800b3d8d  call    cs:__imp_JetCommitTransaction
0x1800b3d94  nop     dword ptr [rax+rax+00h]
0x1800b3d99  mov     ecx, eax
0x1800b3d9b  lea     rdx, aFilterjetcommi; "FilterJetCommitTransaction"
0x1800b3da2  call    FilterMapJetError
0x1800b3da7  jmp     short loc_1800B3DFD
0x1800b3da9  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3db0  xor     edx, edx; grbit
0x1800b3db2  call    cs:__imp_JetRollback
0x1800b3db9  nop     dword ptr [rax+rax+00h]
0x1800b3dbe  mov     ecx, eax
0x1800b3dc0  lea     rdx, aFilterjetrollb; "FilterJetRollback"
0x1800b3dc7  call    FilterMapJetError
0x1800b3dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3dd3  lea     rax, WPP_GLOBAL_Control
0x1800b3dda  cmp     rcx, rax
0x1800b3ddd  jz      short loc_1800B3DFD
0x1800b3ddf  test    byte ptr [rcx+1Ch], 10h
0x1800b3de3  jz      short loc_1800B3DFD
0x1800b3de5  mov     rcx, [rcx+10h]
0x1800b3de9  lea     r8, WPP_0db8580d4aa93e5d318c9249289cee35_Traceguids
0x1800b3df0  mov     edx, 0Bh
0x1800b3df5  mov     r9d, edi
0x1800b3df8  call    WPP_SF_D
0x1800b3dfd  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b3e04  call    cs:__imp_LeaveCriticalSection
0x1800b3e0b  nop     dword ptr [rax+rax+00h]
0x1800b3e10  mov     eax, edi
0x1800b3e12  mov     rcx, [rbp+90h+var_40]
0x1800b3e16  xor     rcx, rsp; StackCookie
0x1800b3e19  call    __security_check_cookie
0x1800b3e1e  mov     rbx, [rsp+190h+arg_10]
0x1800b3e26  add     rsp, 160h
0x1800b3e2d  pop     r15
0x1800b3e2f  pop     r14
0x1800b3e31  pop     r13
0x1800b3e33  pop     r12
0x1800b3e35  pop     rdi
0x1800b3e36  pop     rsi
0x1800b3e37  pop     rbp
0x1800b3e38  retn
```
