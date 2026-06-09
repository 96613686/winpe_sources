# CHTTPMailTransport::SendPostRequest(void)

- ea: `0x1800a45d8`
- end: `0x1800a49c9`
- name: `?SendPostRequest@CHTTPMailTransport@@QEAAJXZ`
- size: `1009`
- prototype: `__int64 __fastcall(CHTTPMailTransport *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1800a49d0`

## callees

- `0x1800a45d8`
- `0x1800a50d4`
- `0x1800a5af8`
- `0x1800a5c30`
- `0x1800a5cc0`
- `0x1800cca00`
- `0x1800cca90`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrGetStreamSize` at `0x1800a466d`
- `MSOERT2!HrGetStreamSize` at `0x1800a468e`
- `MSOERT2!HrGetStreamSize` at `0x1800a466d`
- `MSOERT2!HrGetStreamSize` at `0x1800a468e`
- `KERNEL32!GetLastError` at `0x1800a4732`
- `KERNEL32!GetLastError` at `0x1800a4910`
- `KERNEL32!GetLastError` at `0x1800a4921`
- `KERNEL32!GetLastError` at `0x1800a498f`
- `KERNEL32!GetLastError` at `0x1800a4732`
- `KERNEL32!GetLastError` at `0x1800a4910`
- `KERNEL32!GetLastError` at `0x1800a4921`
- `KERNEL32!GetLastError` at `0x1800a498f`
- `WININET!HttpSendRequestExA` at `0x1800a4728`
- `WININET!HttpSendRequestExA` at `0x1800a4728`
- `WININET!InternetQueryOptionA` at `0x1800a4766`
- `WININET!InternetQueryOptionA` at `0x1800a4766`
- `WININET!InternetWriteFile` at `0x1800a47fb`
- `WININET!InternetWriteFile` at `0x1800a48b7`
- `WININET!InternetWriteFile` at `0x1800a47fb`
- `WININET!InternetWriteFile` at `0x1800a48b7`
- `WININET!HttpEndRequestA` at `0x1800a4903`
- `WININET!HttpEndRequestA` at `0x1800a4903`
- `WININET!HttpQueryInfoA` at `0x1800a495c`
- `WININET!HttpQueryInfoA` at `0x1800a495c`

## pseudocode

```c
__int64 __fastcall CHTTPMailTransport::SendPostRequest(HINTERNET *this)
{
  int StreamSize; // ebx
  HINTERNET v3; // rcx
  HINTERNET v4; // rcx
  DWORD v5; // eax
  int v6; // r15d
  int v7; // r12d
  DWORD LastError; // eax
  void *v9; // rcx
  int v10; // eax
  HINTERNET v11; // rcx
  DWORD v12; // eax
  HINTERNET v13; // rcx
  DWORD v14; // eax
  BOOL v15; // r14d
  DWORD v16; // eax
  unsigned int *v17; // rsi
  unsigned int v18; // edx
  DWORD dwNumberOfBytesToWrite; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwNumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  int Buffer; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD dwBufferLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v25; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _INTERNET_BUFFERSA BuffersIn; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[4048]; // [rsp+90h] [rbp-70h] BYREF

  v23 = 0;
  StreamSize = 0;
  memset(&BuffersIn, 0, sizeof(BuffersIn));
  dwNumberOfBytesToWrite = 0;
  dwNumberOfBytesWritten = 0;
  v26 = 0;
  dwBufferLength = 0;
  Buffer = 0;
  if ( this[9] )
    CHTTPMailTransport::_LogRequest((CHTTPMailTransport *)this, 0, 0);
  v3 = this[38];
  if ( !v3 || (StreamSize = HrGetStreamSize(v3, (char *)this + 668), StreamSize >= 0) )
  {
    v4 = this[39];
    if ( v4 )
    {
      StreamSize = HrGetStreamSize(v4, &v23);
      if ( StreamSize < 0 )
        return (unsigned int)StreamSize;
      *((_DWORD *)this + 167) += v23;
    }
    v5 = *((_DWORD *)this + 167);
    memset(&BuffersIn.Next, 0, 36);
    v6 = 0;
    BuffersIn.dwStructSize = 56;
    BuffersIn.dwBufferTotal = v5;
    *(_QWORD *)&BuffersIn.dwOffsetLow = 0;
    while ( 2 )
    {
      v7 = 0;
      do
      {
        while ( 1 )
        {
          if ( v6 )
          {
            *((_DWORD *)this + 164) = 1;
            *((_DWORD *)this + 166) = 0;
            CHTTPMailTransport::_HrThunkResponse((CHTTPMailTransport *)this, 0);
            *((_DWORD *)this + 164) = 0;
            if ( *((_DWORD *)this + 64) )
              return (unsigned int)-2146644969;
          }
          if ( HttpSendRequestExA(this[31], &BuffersIn, 0, 0, 0) )
            break;
          LastError = GetLastError();
          if ( LastError != 12168 )
            goto LABEL_42;
          v7 = 1;
        }
        v9 = this[31];
        dwBufferLength = 4;
        if ( InternetQueryOptionA(v9, 0x47u, &Buffer, &dwBufferLength) )
        {
          v10 = Buffer;
        }
        else
        {
          v10 = 1;
          Buffer = 1;
        }
        if ( v10 )
        {
          v11 = this[38];
          if ( v11 )
          {
            StreamSize = (*(__int64 (__fastcall **)(HINTERNET, __int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(
                           v11,
                           v26,
                           0,
                           0);
            if ( StreamSize >= 0 )
            {
              while ( 1 )
              {
                StreamSize = (*(__int64 (__fastcall **)(HINTERNET, _BYTE *, __int64, DWORD *))(*(_QWORD *)this[38] + 24LL))(
                               this[38],
                               v28,
                               4048,
                               &dwNumberOfBytesToWrite);
                if ( StreamSize < 0 )
                  break;
                if ( !dwNumberOfBytesToWrite )
                  goto LABEL_26;
                if ( !InternetWriteFile(this[31], v28, dwNumberOfBytesToWrite, &dwNumberOfBytesWritten) )
                  goto LABEL_41;
                v12 = dwNumberOfBytesWritten;
                *((_DWORD *)this + 166) += dwNumberOfBytesWritten;
                *((_DWORD *)this + 165) = v12;
                CHTTPMailTransport::_HrThunkResponse((CHTTPMailTransport *)this, 0);
                *((_DWORD *)this + 165) = 0;
                if ( *((_DWORD *)this + 64) )
                  return (unsigned int)-2146644969;
              }
            }
            return (unsigned int)StreamSize;
          }
LABEL_26:
          v13 = this[39];
          v6 = 1;
          if ( v13 )
          {
            StreamSize = (*(__int64 (__fastcall **)(HINTERNET, __int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 40LL))(
                           v13,
                           v26,
                           0,
                           0);
            if ( StreamSize >= 0 )
            {
              while ( 1 )
              {
                StreamSize = (*(__int64 (__fastcall **)(HINTERNET, _BYTE *, __int64, DWORD *))(*(_QWORD *)this[39] + 24LL))(
                               this[39],
                               v28,
                               4048,
                               &dwNumberOfBytesToWrite);
                if ( StreamSize < 0 )
                  break;
                if ( !dwNumberOfBytesToWrite )
                  goto LABEL_33;
                if ( !InternetWriteFile(this[31], v28, dwNumberOfBytesToWrite, &dwNumberOfBytesWritten) )
                  goto LABEL_41;
                v14 = dwNumberOfBytesWritten;
                *((_DWORD *)this + 166) += dwNumberOfBytesWritten;
                *((_DWORD *)this + 165) = v14;
                CHTTPMailTransport::_HrThunkResponse((CHTTPMailTransport *)this, 0);
                *((_DWORD *)this + 165) = 0;
                if ( *((_DWORD *)this + 64) )
                  return (unsigned int)-2146644969;
              }
            }
            return (unsigned int)StreamSize;
          }
        }
LABEL_33:
        v15 = HttpEndRequestA(this[31], 0, 0, 0);
        if ( v15 )
          goto LABEL_36;
      }
      while ( GetLastError() == 12032 );
      v16 = GetLastError();
      CHTTPMailTransport::_HrThunkConnectionError((CHTTPMailTransport *)this, v16);
LABEL_36:
      v17 = (unsigned int *)(this + 29);
      v25 = 4;
      *((_DWORD *)this + 58) = 0;
      if ( !HttpQueryInfoA(this[31], 0x20000013u, this + 29, &v25, 0) )
      {
LABEL_41:
        LastError = GetLastError();
LABEL_42:
        v18 = LastError;
LABEL_43:
        CHTTPMailTransport::_HrThunkConnectionError((CHTTPMailTransport *)this, v18);
        return (unsigned int)-2147467259;
      }
      if ( (unsigned int)CHTTPMailTransport::_AuthCurrentRequest((CHTTPMailTransport *)this, *v17, v7) )
        continue;
      break;
    }
    v18 = *v17;
    if ( !v15 || v18 - 200 > 0x63 )
      goto LABEL_43;
  }
  return (unsigned int)StreamSize;
}

```

## disassembly

```asm
0x1800a45d8  push    rbp
0x1800a45da  push    rbx
0x1800a45db  push    rsi
0x1800a45dc  push    rdi
0x1800a45dd  push    r12
0x1800a45df  push    r13
0x1800a45e1  push    r14
0x1800a45e3  push    r15
0x1800a45e5  lea     rbp, [rsp-0F78h]
0x1800a45ed  mov     eax, 1078h
0x1800a45f2  call    _alloca_probe
0x1800a45f7  sub     rsp, rax
0x1800a45fa  mov     rax, cs:__security_cookie
0x1800a4601  xor     rax, rsp
0x1800a4604  mov     [rbp+0FB0h+var_50], rax
0x1800a460b  xor     r13d, r13d
0x1800a460e  xorps   xmm0, xmm0
0x1800a4611  xor     eax, eax
0x1800a4613  mov     [rsp+10B0h+var_1074], r13d
0x1800a4618  mov     rdi, rcx
0x1800a461b  mov     ebx, r13d
0x1800a461e  movups  xmmword ptr [rsp+10B0h+BuffersIn.dwStructSize], xmm0
0x1800a4623  mov     qword ptr [rbp+0FB0h+BuffersIn.dwOffsetLow], rax
0x1800a4627  movups  xmmword ptr [rsp+10B0h+BuffersIn.lpcszHeader], xmm0
0x1800a462c  mov     [rsp+10B0h+dwNumberOfBytesToWrite], r13d
0x1800a4631  movups  xmmword ptr [rsp+10B0h+BuffersIn.lpvBuffer], xmm0
0x1800a4636  mov     [rsp+10B0h+dwNumberOfBytesWritten], r13d
0x1800a463b  mov     [rsp+10B0h+var_1068], r13
0x1800a4640  mov     [rsp+10B0h+dwBufferLength], r13d
0x1800a4645  mov     [rsp+10B0h+Buffer], r13d
0x1800a464a  cmp     [rcx+48h], r13
0x1800a464e  jz      short loc_1800A465A
0x1800a4650  xor     r8d, r8d; unsigned int
0x1800a4653  xor     edx, edx; void *
0x1800a4655  call    ?_LogRequest@CHTTPMailTransport@@AEAAXPEBXK@Z; CHTTPMailTransport::_LogRequest(void const *,ulong)
0x1800a465a  mov     rcx, [rdi+130h]
0x1800a4661  test    rcx, rcx
0x1800a4664  jz      short loc_1800A467D
0x1800a4666  lea     rdx, [rdi+29Ch]
0x1800a466d  call    cs:__imp_HrGetStreamSize
0x1800a4673  mov     ebx, eax
0x1800a4675  test    eax, eax
0x1800a4677  js      loc_1800A49A4
0x1800a467d  mov     rcx, [rdi+138h]
0x1800a4684  test    rcx, rcx
0x1800a4687  jz      short loc_1800A46A8
0x1800a4689  lea     rdx, [rsp+10B0h+var_1074]
0x1800a468e  call    cs:__imp_HrGetStreamSize
0x1800a4694  mov     ebx, eax
0x1800a4696  test    eax, eax
0x1800a4698  js      loc_1800A49A4
0x1800a469e  mov     eax, [rsp+10B0h+var_1074]
0x1800a46a2  add     [rdi+29Ch], eax
0x1800a46a8  mov     eax, [rdi+29Ch]
0x1800a46ae  xorps   xmm0, xmm0
0x1800a46b1  movdqu  xmmword ptr [rsp+10B0h+BuffersIn.Next], xmm0
0x1800a46b7  mov     r15d, r13d
0x1800a46ba  mov     [rsp+10B0h+BuffersIn.dwStructSize], 38h ; '8'
0x1800a46c2  mov     qword ptr [rsp+10B0h+BuffersIn.dwHeadersLength], r13
0x1800a46c7  mov     [rsp+10B0h+BuffersIn.lpvBuffer], r13
0x1800a46cc  mov     [rsp+10B0h+BuffersIn.dwBufferLength], r13d
0x1800a46d1  mov     [rsp+10B0h+BuffersIn.dwBufferTotal], eax
0x1800a46d5  mov     qword ptr [rbp+0FB0h+BuffersIn.dwOffsetLow], r13
0x1800a46d9  mov     esi, 1
0x1800a46de  mov     r12d, r13d
0x1800a46e1  test    r15d, r15d
0x1800a46e4  jz      short loc_1800A4711
0x1800a46e6  xor     edx, edx; int
0x1800a46e8  mov     [rdi+290h], esi
0x1800a46ee  mov     rcx, rdi; this
0x1800a46f1  mov     [rdi+298h], r13d
0x1800a46f8  call    ?_HrThunkResponse@CHTTPMailTransport@@AEAAJH@Z; CHTTPMailTransport::_HrThunkResponse(int)
0x1800a46fd  mov     [rdi+290h], r13d
0x1800a4704  cmp     [rdi+100h], r13d
0x1800a470b  jnz     loc_1800A4833
0x1800a4711  mov     rcx, [rdi+0F8h]; hRequest
0x1800a4718  lea     rdx, [rsp+10B0h+BuffersIn]; lpBuffersIn
0x1800a471d  xor     r9d, r9d; dwFlags
0x1800a4720  mov     [rsp+10B0h+dwContext], r13; dwContext
0x1800a4725  xor     r8d, r8d; lpBuffersOut
0x1800a4728  call    cs:__imp_HttpSendRequestExA
0x1800a472e  test    eax, eax
0x1800a4730  jnz     short loc_1800A4748
0x1800a4732  call    cs:__imp_GetLastError
0x1800a4738  cmp     eax, 2F88h
0x1800a473d  jnz     loc_1800A4995
0x1800a4743  mov     r12d, esi
0x1800a4746  jmp     short loc_1800A46E1
0x1800a4748  mov     rcx, [rdi+0F8h]; hInternet
0x1800a474f  lea     r9, [rsp+10B0h+dwBufferLength]; lpdwBufferLength
0x1800a4754  lea     r8, [rsp+10B0h+Buffer]; lpBuffer
0x1800a4759  mov     [rsp+10B0h+dwBufferLength], 4
0x1800a4761  mov     edx, 47h ; 'G'; dwOption
0x1800a4766  call    cs:__imp_InternetQueryOptionA
0x1800a476c  test    eax, eax
0x1800a476e  jnz     short loc_1800A4778
0x1800a4770  mov     eax, esi
0x1800a4772  mov     [rsp+10B0h+Buffer], eax
0x1800a4776  jmp     short loc_1800A477C
0x1800a4778  mov     eax, [rsp+10B0h+Buffer]
0x1800a477c  test    eax, eax
0x1800a477e  jz      loc_1800A48F4
0x1800a4784  mov     rcx, [rdi+130h]
0x1800a478b  test    rcx, rcx
0x1800a478e  jz      loc_1800A483D
0x1800a4794  mov     rax, [rcx]
0x1800a4797  xor     r9d, r9d
0x1800a479a  mov     rdx, [rsp+10B0h+var_1068]
0x1800a479f  xor     r8d, r8d
0x1800a47a2  mov     rax, [rax+28h]
0x1800a47a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47ab  mov     ebx, eax
0x1800a47ad  test    eax, eax
0x1800a47af  js      loc_1800A49A4
0x1800a47b5  mov     rcx, [rdi+130h]
0x1800a47bc  lea     r9, [rsp+10B0h+dwNumberOfBytesToWrite]
0x1800a47c1  mov     r8d, 0FD0h
0x1800a47c7  lea     rdx, [rbp+0FB0h+var_1020]
0x1800a47cb  mov     rax, [rcx]
0x1800a47ce  mov     rax, [rax+18h]
0x1800a47d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47d7  mov     ebx, eax
0x1800a47d9  test    eax, eax
0x1800a47db  js      loc_1800A49A4
0x1800a47e1  mov     r8d, [rsp+10B0h+dwNumberOfBytesToWrite]; dwNumberOfBytesToWrite
0x1800a47e6  test    r8d, r8d
0x1800a47e9  jz      short loc_1800A483D
0x1800a47eb  mov     rcx, [rdi+0F8h]; hFile
0x1800a47f2  lea     r9, [rsp+10B0h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x1800a47f7  lea     rdx, [rbp+0FB0h+var_1020]; lpBuffer
0x1800a47fb  call    cs:__imp_InternetWriteFile
0x1800a4801  test    eax, eax
0x1800a4803  jz      loc_1800A498F
0x1800a4809  mov     eax, [rsp+10B0h+dwNumberOfBytesWritten]
0x1800a480d  xor     edx, edx; int
0x1800a480f  add     [rdi+298h], eax
0x1800a4815  mov     rcx, rdi; this
0x1800a4818  mov     [rdi+294h], eax
0x1800a481e  call    ?_HrThunkResponse@CHTTPMailTransport@@AEAAJH@Z; CHTTPMailTransport::_HrThunkResponse(int)
0x1800a4823  mov     [rdi+294h], r13d
0x1800a482a  cmp     [rdi+100h], r13d
0x1800a4831  jz      short loc_1800A47B5
0x1800a4833  mov     ebx, 800CCC17h
0x1800a4838  jmp     loc_1800A49A4
0x1800a483d  mov     rcx, [rdi+138h]
0x1800a4844  mov     r15d, esi
0x1800a4847  test    rcx, rcx
0x1800a484a  jz      loc_1800A48F4
0x1800a4850  mov     rax, [rcx]
0x1800a4853  xor     r9d, r9d
0x1800a4856  mov     rdx, [rsp+10B0h+var_1068]
0x1800a485b  xor     r8d, r8d
0x1800a485e  mov     rax, [rax+28h]
0x1800a4862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4867  mov     ebx, eax
0x1800a4869  test    eax, eax
0x1800a486b  js      loc_1800A49A4
0x1800a4871  mov     rcx, [rdi+138h]
0x1800a4878  lea     r9, [rsp+10B0h+dwNumberOfBytesToWrite]
0x1800a487d  mov     r8d, 0FD0h
0x1800a4883  lea     rdx, [rbp+0FB0h+var_1020]
0x1800a4887  mov     rax, [rcx]
0x1800a488a  mov     rax, [rax+18h]
0x1800a488e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4893  mov     ebx, eax
0x1800a4895  test    eax, eax
0x1800a4897  js      loc_1800A49A4
0x1800a489d  mov     r8d, [rsp+10B0h+dwNumberOfBytesToWrite]; dwNumberOfBytesToWrite
0x1800a48a2  test    r8d, r8d
0x1800a48a5  jz      short loc_1800A48F4
0x1800a48a7  mov     rcx, [rdi+0F8h]; hFile
0x1800a48ae  lea     r9, [rsp+10B0h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x1800a48b3  lea     rdx, [rbp+0FB0h+var_1020]; lpBuffer
0x1800a48b7  call    cs:__imp_InternetWriteFile
0x1800a48bd  test    eax, eax
0x1800a48bf  jz      loc_1800A498F
0x1800a48c5  mov     eax, [rsp+10B0h+dwNumberOfBytesWritten]
0x1800a48c9  xor     edx, edx; int
0x1800a48cb  add     [rdi+298h], eax
0x1800a48d1  mov     rcx, rdi; this
0x1800a48d4  mov     [rdi+294h], eax
0x1800a48da  call    ?_HrThunkResponse@CHTTPMailTransport@@AEAAJH@Z; CHTTPMailTransport::_HrThunkResponse(int)
0x1800a48df  mov     [rdi+294h], r13d
0x1800a48e6  cmp     [rdi+100h], r13d
0x1800a48ed  jz      short loc_1800A4871
0x1800a48ef  jmp     loc_1800A4833
0x1800a48f4  mov     rcx, [rdi+0F8h]; hRequest
0x1800a48fb  xor     r9d, r9d; dwContext
0x1800a48fe  xor     r8d, r8d; dwFlags
0x1800a4901  xor     edx, edx; lpBuffersOut
0x1800a4903  call    cs:__imp_HttpEndRequestA
0x1800a4909  mov     r14d, eax
0x1800a490c  test    eax, eax
0x1800a490e  jnz     short loc_1800A4931
0x1800a4910  call    cs:__imp_GetLastError
0x1800a4916  cmp     eax, 2F00h
0x1800a491b  jz      loc_1800A46E1
0x1800a4921  call    cs:__imp_GetLastError
0x1800a4927  mov     edx, eax; unsigned int
0x1800a4929  mov     rcx, rdi; this
0x1800a492c  call    ?_HrThunkConnectionError@CHTTPMailTransport@@AEAAJK@Z; CHTTPMailTransport::_HrThunkConnectionError(ulong)
0x1800a4931  lea     rsi, [rdi+0E8h]
0x1800a4938  mov     [rsp+10B0h+var_106C], 4
0x1800a4940  mov     [rsi], r13d
0x1800a4943  lea     r9, [rsp+10B0h+var_106C]; lpdwBufferLength
0x1800a4948  mov     rcx, [rdi+0F8h]; hRequest
0x1800a494f  mov     r8, rsi; lpBuffer
0x1800a4952  mov     edx, 20000013h; dwInfoLevel
0x1800a4957  mov     [rsp+10B0h+dwContext], r13; lpdwIndex
0x1800a495c  call    cs:__imp_HttpQueryInfoA
0x1800a4962  test    eax, eax
0x1800a4964  jz      short loc_1800A498F
0x1800a4966  mov     edx, [rsi]; unsigned int
0x1800a4968  mov     r8d, r12d; int
0x1800a496b  mov     rcx, rdi; this
0x1800a496e  call    ?_AuthCurrentRequest@CHTTPMailTransport@@AEAAHKH@Z; CHTTPMailTransport::_AuthCurrentRequest(ulong,int)
0x1800a4973  test    eax, eax
0x1800a4975  jnz     loc_1800A46D9
0x1800a497b  mov     edx, [rsi]
0x1800a497d  test    r14d, r14d
0x1800a4980  jz      short loc_1800A4997
0x1800a4982  lea     eax, [rdx-0C8h]
0x1800a4988  cmp     eax, 63h ; 'c'
0x1800a498b  jbe     short loc_1800A49A4
0x1800a498d  jmp     short loc_1800A4997
0x1800a498f  call    cs:__imp_GetLastError
0x1800a4995  mov     edx, eax; unsigned int
0x1800a4997  mov     rcx, rdi; this
0x1800a499a  call    ?_HrThunkConnectionError@CHTTPMailTransport@@AEAAJK@Z; CHTTPMailTransport::_HrThunkConnectionError(ulong)
0x1800a499f  mov     ebx, 80004005h
0x1800a49a4  mov     eax, ebx
0x1800a49a6  mov     rcx, [rbp+0FB0h+var_50]
0x1800a49ad  xor     rcx, rsp; StackCookie
0x1800a49b0  call    __security_check_cookie
0x1800a49b5  add     rsp, 1078h
0x1800a49bc  pop     r15
0x1800a49be  pop     r14
0x1800a49c0  pop     r13
0x1800a49c2  pop     r12
0x1800a49c4  pop     rdi
0x1800a49c5  pop     rsi
0x1800a49c6  pop     rbx
0x1800a49c7  pop     rbp
0x1800a49c8  retn
```
