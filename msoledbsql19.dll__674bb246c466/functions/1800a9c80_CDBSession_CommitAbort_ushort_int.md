# CDBSession::CommitAbort(ushort,int)

- ea: `0x1800a9c80`
- end: `0x1800a9efe`
- name: `?CommitAbort@CDBSession@@AEAAJGH@Z`
- size: `638`
- prototype: `int(CDBSession *__hidden this, unsigned __int16, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a98e0`
- `0x18011d880`
- `0x18011db40`

## callees

- `0x180003030`
- `0x180003d80`
- `0x180008980`
- `0x180009340`
- `0x180009700`
- `0x180010840`
- `0x180075260`
- `0x1800a9c80`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateGuid` at `0x1800a9e1e`
- `ole32!CoCreateGuid` at `0x1800a9e1e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a9e34`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a9e34`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800a9e40`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800a9e40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDBSession::CommitAbort(CDBSession *this, unsigned __int16 a2, int a3)
{
  int v6; // ebp
  __int64 v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // r14
  int v10; // ecx
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // esi
  int v15; // edx
  unsigned int v16; // eax
  HRESULT v17; // eax
  __int64 v19; // [rsp+30h] [rbp-68h]
  GUID pguid; // [rsp+48h] [rbp-50h] BYREF

  pguid = 0;
  v6 = 0;
  v7 = *((_QWORD *)this + 105);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 3) + 32LL) + 8LL))(*((_QWORD *)this + 3) + 32LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v7 + 88) + 32LL) + 8LL))(*(_QWORD *)(v7 + 88) + 32LL);
  v8 = *((_QWORD *)this + 3);
  v19 = v8;
  v9 = *(_QWORD *)(v7 + 88);
  v10 = *((_DWORD *)this + 212);
  if ( (v10 & 1) != 0 )
  {
    v13 = 2;
    if ( a2 )
      v13 = 4;
    *((_DWORD *)this + 212) = v10 | v13;
    v14 = CDBConnection::EndTransaction(*((CDBConnection **)this + 105), a2, a3);
    if ( v14 )
    {
      v15 = -2147418113;
      if ( v14 == 1 )
        v15 = 0;
      v16 = CErrorData::HResultFromSQLState(
              (CErrorData *)(*((_QWORD *)this + 105) + 136LL),
              v15,
              (const struct tagHRSQLSTATE *const)&off_1801D1E10,
              9u,
              1);
      v12 = v16;
      if ( (bidGblFlags & 2) != 0 )
        v16 = bidTraceHR(off_180260448[0], 539657, v16);
      CError::PostSqlErrors(
        g_pCError,
        v16,
        &GUID_0fb15084_af41_11ce_bd2b_204c4f4f5020,
        (struct CErrorData *)(*((_QWORD *)this + 105) + 136LL));
      if ( (v14 & 0xFFFE) != 0 )
      {
        if ( v12 < 0 )
        {
LABEL_27:
          _InterlockedIncrement((volatile signed __int32 *)this + 235);
          *((_DWORD *)this + 212) &= 0xFFFFFFF9;
          v8 = v19;
          goto LABEL_28;
        }
      }
      else
      {
        v12 = 0;
      }
    }
    else
    {
      v12 = 0;
    }
    if ( !a3 )
      goto LABEL_26;
    v17 = CoCreateGuid(&pguid);
    if ( v17 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260448[0], 562185, (unsigned int)v17);
      }
      v12 = -2147168255;
      v6 = 1;
    }
    else if ( this == (CDBSession *)-856LL )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      *(GUID *)((char *)this + 856) = pguid;
    }
    if ( v6 )
    {
LABEL_26:
      CDBConnection::ClearLocalXactMode(*((CDBConnection **)this + 105), *((_DWORD *)this + 213));
      *((_DWORD *)this + 212) &= ~1u;
    }
    goto LABEL_27;
  }
  if ( (bidGblFlags & 2) != 0 )
    v11 = bidTraceHR(off_180260448[0], 485385, 2147799054LL);
  else
    v11 = -2147168242;
  v12 = CError::PostHResult(g_pCError, v11, &GUID_0fb15084_af41_11ce_bd2b_204c4f4f5020);
LABEL_28:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 32) + 24LL))(v9 + 32);
LABEL_31:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v8 + 32) + 24LL))(v8 + 32);
    return (unsigned int)v12;
  }
  if ( v8 )
    goto LABEL_31;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800a9c80  push    rbx
0x1800a9c82  push    rbp
0x1800a9c83  push    rsi
0x1800a9c84  push    rdi
0x1800a9c85  push    r12
0x1800a9c87  push    r14
0x1800a9c89  push    r15
0x1800a9c8b  sub     rsp, 60h
0x1800a9c8f  mov     rax, cs:__security_cookie
0x1800a9c96  xor     rax, rsp
0x1800a9c99  mov     [rsp+98h+var_40], rax
0x1800a9c9e  mov     r15d, r8d
0x1800a9ca1  movzx   r12d, dx
0x1800a9ca5  mov     rdi, rcx
0x1800a9ca8  xorps   xmm0, xmm0
0x1800a9cab  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x1800a9cb0  xor     ebp, ebp
0x1800a9cb2  movups  xmmword ptr [rsp+98h+var_68], xmm0
0x1800a9cb7  mov     rbx, [rcx+348h]
0x1800a9cbe  mov     rcx, [rcx+18h]
0x1800a9cc2  add     rcx, 20h ; ' '
0x1800a9cc6  mov     rax, [rcx]
0x1800a9cc9  mov     rax, [rax+8]
0x1800a9ccd  call    cs:__guard_dispatch_icall_fptr
0x1800a9cd3  mov     rcx, [rbx+58h]
0x1800a9cd7  add     rcx, 20h ; ' '
0x1800a9cdb  mov     rax, [rcx]
0x1800a9cde  mov     rax, [rax+8]
0x1800a9ce2  call    cs:__guard_dispatch_icall_fptr
0x1800a9ce8  mov     rsi, [rdi+18h]
0x1800a9cec  mov     [rsp+98h+var_68], rsi
0x1800a9cf1  mov     r14, [rbx+58h]
0x1800a9cf5  mov     [rsp+98h+var_68+8], r14
0x1800a9cfa  mov     ecx, [rdi+350h]
0x1800a9d00  test    cl, 1
0x1800a9d03  jnz     short loc_1800A9D52
0x1800a9d05  test    byte ptr cs:_bidGblFlags, 2
0x1800a9d0c  jz      short loc_1800A9D31
0x1800a9d0e  mov     edx, 76809h
0x1800a9d13  mov     r8d, 8004D00Eh
0x1800a9d19  mov     rcx, cs:off_180260448; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a9d20  call    _bidTraceHR
0x1800a9d25  mov     r14, [rsp+98h+var_68+8]
0x1800a9d2a  mov     rsi, [rsp+98h+var_68]
0x1800a9d2f  jmp     short loc_1800A9D36
0x1800a9d31  mov     eax, 8004D00Eh
0x1800a9d36  lea     r8, _GUID_0fb15084_af41_11ce_bd2b_204c4f4f5020; struct _GUID *
0x1800a9d3d  mov     edx, eax; int
0x1800a9d3f  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x1800a9d46  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x1800a9d4b  mov     ebx, eax
0x1800a9d4d  jmp     loc_1800A9EB1
0x1800a9d52  mov     eax, 2
0x1800a9d57  mov     edx, 4
0x1800a9d5c  test    r12w, r12w
0x1800a9d60  cmovnz  eax, edx
0x1800a9d63  or      eax, ecx
0x1800a9d65  mov     [rdi+350h], eax
0x1800a9d6b  mov     r8d, r15d; int
0x1800a9d6e  movzx   edx, r12w; unsigned __int16
0x1800a9d72  mov     rcx, [rdi+348h]; this
0x1800a9d79  call    ?EndTransaction@CDBConnection@@QEAAHGH@Z; CDBConnection::EndTransaction(ushort,int)
0x1800a9d7e  mov     esi, eax
0x1800a9d80  test    eax, eax
0x1800a9d82  jnz     short loc_1800A9D8B
0x1800a9d84  mov     ebx, ebp
0x1800a9d86  jmp     loc_1800A9E14
0x1800a9d8b  mov     edx, 8000FFFFh
0x1800a9d90  cmp     esi, 1
0x1800a9d93  cmovz   edx, ebp; int
0x1800a9d96  mov     rcx, [rdi+348h]
0x1800a9d9d  add     rcx, 88h; this
0x1800a9da4  mov     [rsp+98h+var_78], 1; int
0x1800a9dac  mov     r9d, 9; unsigned int
0x1800a9db2  lea     r8, off_1801D1E10; struct tagHRSQLSTATE *
0x1800a9db9  call    ?HResultFromSQLState@CErrorData@@QEAAJJQEBUtagHRSQLSTATE@@KH@Z; CErrorData::HResultFromSQLState(long,tagHRSQLSTATE const * const,ulong,int)
0x1800a9dbe  mov     ebx, eax
0x1800a9dc0  test    byte ptr cs:_bidGblFlags, 2
0x1800a9dc7  jz      short loc_1800A9DDD
0x1800a9dc9  mov     r8d, eax
0x1800a9dcc  mov     edx, 83C09h
0x1800a9dd1  mov     rcx, cs:off_180260448; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a9dd8  call    _bidTraceHR
0x1800a9ddd  mov     r9, [rdi+348h]
0x1800a9de4  add     r9, 88h; struct CErrorData *
0x1800a9deb  lea     r8, _GUID_0fb15084_af41_11ce_bd2b_204c4f4f5020; struct _GUID *
0x1800a9df2  mov     edx, eax; int
0x1800a9df4  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x1800a9dfb  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x1800a9e00  test    esi, 0FFFEh
0x1800a9e06  jnz     short loc_1800A9E0C
0x1800a9e08  mov     ebx, ebp
0x1800a9e0a  jmp     short loc_1800A9E14
0x1800a9e0c  test    ebx, ebx
0x1800a9e0e  js      loc_1800A9E99
0x1800a9e14  test    r15d, r15d
0x1800a9e17  jz      short loc_1800A9E80
0x1800a9e19  lea     rcx, [rsp+98h+pguid]; pguid
0x1800a9e1e  call    cs:__imp_CoCreateGuid
0x1800a9e24  test    eax, eax
0x1800a9e26  js      short loc_1800A9E52
0x1800a9e28  lea     rax, [rdi+358h]
0x1800a9e2f  test    rax, rax
0x1800a9e32  jnz     short loc_1800A9E48
0x1800a9e34  call    cs:__imp__errno
0x1800a9e3a  mov     dword ptr [rax], 16h
0x1800a9e40  call    cs:__imp__invalid_parameter_noinfo
0x1800a9e46  jmp     short loc_1800A9E7C
0x1800a9e48  movups  xmm0, xmmword ptr [rsp+98h+pguid.Data1]
0x1800a9e4d  movups  xmmword ptr [rax], xmm0
0x1800a9e50  jmp     short loc_1800A9E7C
0x1800a9e52  test    byte ptr cs:_bidGblFlags, 2
0x1800a9e59  jz      short loc_1800A9E72
0x1800a9e5b  lfence
0x1800a9e5e  mov     r8d, eax
0x1800a9e61  mov     edx, 89409h
0x1800a9e66  mov     rcx, cs:off_180260448; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a9e6d  call    _bidTraceHR
0x1800a9e72  mov     ebx, 8004D001h
0x1800a9e77  mov     ebp, 1
0x1800a9e7c  test    ebp, ebp
0x1800a9e7e  jz      short loc_1800A9E99
0x1800a9e80  mov     edx, [rdi+354h]; int
0x1800a9e86  mov     rcx, [rdi+348h]; this
0x1800a9e8d  call    ?ClearLocalXactMode@CDBConnection@@QEAAJJ@Z; CDBConnection::ClearLocalXactMode(long)
0x1800a9e92  and     dword ptr [rdi+350h], 0FFFFFFFEh
0x1800a9e99  lock inc dword ptr [rdi+3ACh]
0x1800a9ea0  and     dword ptr [rdi+350h], 0FFFFFFF9h
0x1800a9ea7  mov     r14, [rsp+98h+var_68+8]
0x1800a9eac  mov     rsi, [rsp+98h+var_68]
0x1800a9eb1  test    r14, r14
0x1800a9eb4  jz      short loc_1800A9EC9
0x1800a9eb6  lea     rcx, [r14+20h]
0x1800a9eba  mov     rax, [rcx]
0x1800a9ebd  mov     rax, [rax+18h]
0x1800a9ec1  call    cs:__guard_dispatch_icall_fptr
0x1800a9ec7  jmp     short loc_1800A9ECE
0x1800a9ec9  test    rsi, rsi
0x1800a9ecc  jz      short loc_1800A9EE0
0x1800a9ece  lea     rcx, [rsi+20h]
0x1800a9ed2  mov     rax, [rcx]
0x1800a9ed5  mov     rax, [rax+18h]
0x1800a9ed9  call    cs:__guard_dispatch_icall_fptr
0x1800a9edf  nop
0x1800a9ee0  mov     eax, ebx
0x1800a9ee2  mov     rcx, [rsp+98h+var_40]
0x1800a9ee7  xor     rcx, rsp; StackCookie
0x1800a9eea  call    __security_check_cookie
0x1800a9eef  add     rsp, 60h
0x1800a9ef3  pop     r15
0x1800a9ef5  pop     r14
0x1800a9ef7  pop     r12
0x1800a9ef9  pop     rdi
0x1800a9efa  pop     rsi
0x1800a9efb  pop     rbp
0x1800a9efc  pop     rbx
0x1800a9efd  retn
```
