# SetFilterTableRecord

- ea: `0x1800b4984`
- end: `0x1800b4ca6`
- name: `SetFilterTableRecord`
- size: `802`
- prototype: `__int64 __fastcall(int, int, int, int, char, char, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b3f3c`

## callees

- `0x18000282c`
- `0x1800b4984`
- `0x1800b5c40`
- `0x1800b5dd4`
- `0x1800b5e24`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800b4b1d`
- `msvcrt!wcsncpy_s` at `0x1800b4b1d`
- `ESENT!JetUpdate` at `0x1800b4b8d`
- `ESENT!JetUpdate` at `0x1800b4b8d`
- `ESENT!JetBeginTransaction` at `0x1800b49dc`
- `ESENT!JetBeginTransaction` at `0x1800b49dc`
- `ESENT!JetRollback` at `0x1800b4c1e`
- `ESENT!JetRollback` at `0x1800b4c1e`
- `ESENT!JetCommitTransaction` at `0x1800b4bf9`
- `ESENT!JetCommitTransaction` at `0x1800b4bf9`
- `ESENT!JetPrepareUpdate` at `0x1800b4bcf`
- `ESENT!JetPrepareUpdate` at `0x1800b4bcf`
- `KERNEL32!EnterCriticalSection` at `0x1800b49c9`
- `KERNEL32!EnterCriticalSection` at `0x1800b49c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4c70`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4c70`

## string_xrefs

- `0x1800b4c2c`: `FilterJetRollback`
- `0x1800b4c07`: `FilterJetCommitTransaction`
- `0x1800b4bdd`: `FilterJetCancelUpdate`
- `0x1800b4b9b`: `FilterJetCommitUpdate`

## pseudocode

```c
__int64 __fastcall SetFilterTableRecord(
        int a1,
        unsigned __int8 a2,
        int a3,
        int a4,
        char a5,
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
  __int64 v32; // rbx
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
    v32 = (unsigned int)JetUpdate(DhcpGlobalJetServerSession, FilterGlobalTableHandle, 0, 0, 0);
    v15 = FilterMapJetError(v32, "FilterJetCommitUpdate");
    if ( (_DWORD)v32 == -1605 )
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
0x1800b4984  mov     [rsp-8+arg_10], rbx
0x1800b4989  push    rbp
0x1800b498a  push    rsi
0x1800b498b  push    rdi
0x1800b498c  push    r12
0x1800b498e  push    r13
0x1800b4990  push    r14
0x1800b4992  push    r15
0x1800b4994  lea     rbp, [rsp-60h]
0x1800b4999  sub     rsp, 160h
0x1800b49a0  mov     rax, cs:__security_cookie
0x1800b49a7  xor     rax, rsp
0x1800b49aa  mov     [rbp+90h+var_40], rax
0x1800b49ae  mov     r14, [rbp+90h+Source]
0x1800b49b5  mov     rsi, rcx
0x1800b49b8  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b49bf  mov     [rsp+190h+var_150], dl
0x1800b49c3  mov     r15d, r9d
0x1800b49c6  mov     r12d, r8d
0x1800b49c9  call    cs:__imp_EnterCriticalSection
0x1800b49d0  nop     dword ptr [rax+rax+00h]
0x1800b49d5  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b49dc  call    cs:__imp_JetBeginTransaction
0x1800b49e3  nop     dword ptr [rax+rax+00h]
0x1800b49e8  mov     ecx, eax
0x1800b49ea  lea     rdx, aFilterjetbegin; "FilterJetBeginTransaction"
0x1800b49f1  call    FilterMapJetError
0x1800b49f6  xor     r13d, r13d
0x1800b49f9  mov     edi, eax
0x1800b49fb  test    eax, eax
0x1800b49fd  jnz     loc_1800B4C15
0x1800b4a03  movzx   eax, [rsp+190h+var_150]
0x1800b4a08  lea     r9, [rbp+90h+arg_20]
0x1800b4a0f  mov     ebx, [rbp+90h+arg_38]
0x1800b4a15  mov     [rsp+190h+var_158], ebx
0x1800b4a19  mov     [rsp+190h+var_160], eax
0x1800b4a1d  mov     [rsp+190h+var_168], rsi
0x1800b4a22  call    FilterJetPrepareUpdate
0x1800b4a27  mov     edi, eax
0x1800b4a29  test    eax, eax
0x1800b4a2b  jnz     loc_1800B4C15
0x1800b4a31  lea     edi, [rax+1]
0x1800b4a34  cmp     ebx, edi
0x1800b4a36  jnz     short loc_1800B4A5C
0x1800b4a38  mov     r8, cs:FilterGlobalTable
0x1800b4a3f  mov     r9, rsi
0x1800b4a42  movzx   eax, [rsp+190h+var_150]
0x1800b4a47  mov     dword ptr [rsp+190h+pcbActual], eax
0x1800b4a4b  mov     r8d, [r8+8]
0x1800b4a4f  call    FilterJetSetValue
0x1800b4a54  test    eax, eax
0x1800b4a56  jnz     loc_1800B4BBB
0x1800b4a5c  mov     r8, cs:FilterGlobalTable
0x1800b4a63  mov     r8d, [r8+18h]
0x1800b4a67  cmp     r15d, edi
0x1800b4a6a  jnz     short loc_1800B4A79
0x1800b4a6c  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b4a70  lea     r9, [rbp+90h+arg_20]
0x1800b4a77  jmp     short loc_1800B4A81
0x1800b4a79  mov     dword ptr [rsp+190h+pcbActual], r13d
0x1800b4a7e  xor     r9d, r9d
0x1800b4a81  call    FilterJetSetValue
0x1800b4a86  test    eax, eax
0x1800b4a88  jnz     loc_1800B4BBB
0x1800b4a8e  mov     r8, cs:FilterGlobalTable
0x1800b4a95  mov     r8d, [r8+28h]
0x1800b4a99  cmp     r12d, edi
0x1800b4a9c  jnz     short loc_1800B4AAE
0x1800b4a9e  mov     [rsp+190h+var_148], dil
0x1800b4aa3  lea     r9, [rsp+190h+var_148]
0x1800b4aa8  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b4aac  jmp     short loc_1800B4AB6
0x1800b4aae  mov     dword ptr [rsp+190h+pcbActual], r13d
0x1800b4ab3  xor     r9d, r9d
0x1800b4ab6  call    FilterJetSetValue
0x1800b4abb  test    eax, eax
0x1800b4abd  jnz     loc_1800B4BBB
0x1800b4ac3  mov     r8, cs:FilterGlobalTable
0x1800b4aca  lea     r9, [rsp+190h+var_150]
0x1800b4acf  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b4ad3  mov     r8d, [r8+38h]
0x1800b4ad7  call    FilterJetSetValue
0x1800b4adc  test    eax, eax
0x1800b4ade  jnz     loc_1800B4BBB
0x1800b4ae4  mov     r8, cs:FilterGlobalTable
0x1800b4aeb  lea     r9, [rbp+90h+arg_28]
0x1800b4af2  mov     dword ptr [rsp+190h+pcbActual], edi
0x1800b4af6  mov     r8d, [r8+48h]
0x1800b4afa  call    FilterJetSetValue
0x1800b4aff  test    eax, eax
0x1800b4b01  jnz     loc_1800B4BBB
0x1800b4b07  test    r14, r14
0x1800b4b0a  jz      short loc_1800B4B74
0x1800b4b0c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800b4b10  lea     rcx, [rsp+190h+Destination]; Destination
0x1800b4b15  mov     r8, r14; Source
0x1800b4b18  mov     edx, 80h; SizeInWords
0x1800b4b1d  call    cs:__imp_wcsncpy_s
0x1800b4b24  nop     dword ptr [rax+rax+00h]
0x1800b4b29  mov     ecx, 3FFFFFFFh
0x1800b4b2e  lea     rdx, [rsp+190h+Destination]
0x1800b4b33  mov     eax, ecx
0x1800b4b35  cmp     [rdx], r13w
0x1800b4b39  jz      short loc_1800B4B44
0x1800b4b3b  add     rdx, 2
0x1800b4b3f  sub     rax, rdi
0x1800b4b42  jnz     short loc_1800B4B35
0x1800b4b44  test    rax, rax
0x1800b4b47  jz      short loc_1800B4BBB
0x1800b4b49  mov     r8, cs:FilterGlobalTable
0x1800b4b50  lea     r9, [rsp+190h+Destination]
0x1800b4b55  sub     ecx, eax
0x1800b4b57  add     ecx, ecx
0x1800b4b59  neg     rax
0x1800b4b5c  mov     r8d, [r8+58h]
0x1800b4b60  sbb     eax, eax
0x1800b4b62  and     eax, ecx
0x1800b4b64  add     eax, 2
0x1800b4b67  mov     dword ptr [rsp+190h+pcbActual], eax
0x1800b4b6b  call    FilterJetSetValue
0x1800b4b70  test    eax, eax
0x1800b4b72  jnz     short loc_1800B4BBB
0x1800b4b74  mov     rdx, cs:FilterGlobalTableHandle; tableid
0x1800b4b7b  xor     r9d, r9d; cbBookmark
0x1800b4b7e  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b4b85  xor     r8d, r8d; pvBookmark
0x1800b4b88  mov     [rsp+190h+pcbActual], r13; pcbActual
0x1800b4b8d  call    cs:__imp_JetUpdate
0x1800b4b94  nop     dword ptr [rax+rax+00h]
0x1800b4b99  mov     ecx, eax
0x1800b4b9b  lea     rdx, aFilterjetcommi_0; "FilterJetCommitUpdate"
0x1800b4ba2  mov     ebx, eax
0x1800b4ba4  call    FilterMapJetError
0x1800b4ba9  mov     edi, eax
0x1800b4bab  cmp     ebx, 0FFFFF9BBh
0x1800b4bb1  mov     eax, 4
0x1800b4bb6  cmovz   edi, eax
0x1800b4bb9  jmp     short loc_1800B4BEB
0x1800b4bbb  mov     rdx, cs:FilterGlobalTableHandle; tableid
0x1800b4bc2  mov     r8d, 3; prep
0x1800b4bc8  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b4bcf  call    cs:__imp_JetPrepareUpdate
0x1800b4bd6  nop     dword ptr [rax+rax+00h]
0x1800b4bdb  mov     ecx, eax
0x1800b4bdd  lea     rdx, aFilterjetcance; "FilterJetCancelUpdate"
0x1800b4be4  call    FilterMapJetError
0x1800b4be9  mov     edi, eax
0x1800b4beb  test    edi, edi
0x1800b4bed  jnz     short loc_1800B4C15
0x1800b4bef  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b4bf6  lea     edx, [rdi+1]; grbit
0x1800b4bf9  call    cs:__imp_JetCommitTransaction
0x1800b4c00  nop     dword ptr [rax+rax+00h]
0x1800b4c05  mov     ecx, eax
0x1800b4c07  lea     rdx, aFilterjetcommi; "FilterJetCommitTransaction"
0x1800b4c0e  call    FilterMapJetError
0x1800b4c13  jmp     short loc_1800B4C69
0x1800b4c15  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b4c1c  xor     edx, edx; grbit
0x1800b4c1e  call    cs:__imp_JetRollback
0x1800b4c25  nop     dword ptr [rax+rax+00h]
0x1800b4c2a  mov     ecx, eax
0x1800b4c2c  lea     rdx, aFilterjetrollb; "FilterJetRollback"
0x1800b4c33  call    FilterMapJetError
0x1800b4c38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4c3f  lea     rax, WPP_GLOBAL_Control
0x1800b4c46  cmp     rcx, rax
0x1800b4c49  jz      short loc_1800B4C69
0x1800b4c4b  test    byte ptr [rcx+1Ch], 10h
0x1800b4c4f  jz      short loc_1800B4C69
0x1800b4c51  mov     rcx, [rcx+10h]
0x1800b4c55  lea     r8, WPP_0db8580d4aa93e5d318c9249289cee35_Traceguids
0x1800b4c5c  mov     edx, 0Bh
0x1800b4c61  mov     r9d, edi
0x1800b4c64  call    WPP_SF_D
0x1800b4c69  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b4c70  call    cs:__imp_LeaveCriticalSection
0x1800b4c77  nop     dword ptr [rax+rax+00h]
0x1800b4c7c  mov     eax, edi
0x1800b4c7e  mov     rcx, [rbp+90h+var_40]
0x1800b4c82  xor     rcx, rsp; StackCookie
0x1800b4c85  call    __security_check_cookie
0x1800b4c8a  mov     rbx, [rsp+190h+arg_10]
0x1800b4c92  add     rsp, 160h
0x1800b4c99  pop     r15
0x1800b4c9b  pop     r14
0x1800b4c9d  pop     r13
0x1800b4c9f  pop     r12
0x1800b4ca1  pop     rdi
0x1800b4ca2  pop     rsi
0x1800b4ca3  pop     rbp
0x1800b4ca4  retn
```
