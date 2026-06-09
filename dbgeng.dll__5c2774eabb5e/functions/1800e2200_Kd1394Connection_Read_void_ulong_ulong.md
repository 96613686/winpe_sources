# Kd1394Connection::Read(void *,ulong,ulong *)

- ea: `0x1800e2200`
- end: `0x1800e262f`
- name: `?Read@Kd1394Connection@@UEAAJPEAXKPEAK@Z`
- size: `1071`
- prototype: `int(Kd1394Connection *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800b94c4`
- `0x1800db3fc`
- `0x1800db578`
- `0x1800e2200`
- `0x1800e2638`
- `0x180416524`
- `0x180431fe0`
- `0x1804da880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800e2417`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800e2417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e22ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e24c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e24db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e252e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e22ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e24c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e24db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e252e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2545`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x1800e23f0`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x1800e23f0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e22c9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e2368`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e22c9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e2368`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800e24b0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800e251a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800e24b0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800e251a`

## string_xrefs

- `0x1800e25ea`: `1394: Read %d bytes of %d\n`

## pseudocode

```c
__int64 __fastcall Kd1394Connection::Read(Kd1394Connection *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v5; // eax
  unsigned int v7; // esi
  __int64 result; // rax
  unsigned int v9; // ebx
  void *v10; // rcx
  void *v11; // r12
  struct _OVERLAPPED *v12; // r13
  int v13; // edx
  KdConnection *v14; // rcx
  signed int LastError; // eax
  signed int v16; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  signed int v22; // eax
  signed int v23; // eax
  BOOL v24; // edx
  signed int v25; // eax
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF

  *(_OWORD *)Handles = 0;
  v5 = a3;
  while ( 1 )
  {
    v7 = *((_DWORD *)this + 172);
    if ( !v7 )
      break;
    if ( v5 < v7 )
    {
      *a4 = 0;
      return 2147942522LL;
    }
    v5 = a3;
    if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)this + 172, 0, v7) )
    {
      memmove(a2, (char *)this + 4712, v7);
      result = 0;
      *a4 = v7;
      return result;
    }
  }
  result = Kd1394Connection::SwitchVirtualDebuggerDriverMode((Kd1394Connection *)((char *)this - 16), 0);
  v9 = result;
  if ( !(_DWORD)result )
  {
    v10 = (void *)*((_QWORD *)this + 4);
    v11 = 0;
    v12 = 0;
    if ( v10 )
    {
      if ( ReadFile(v10, a2, a3, a4, (LPOVERLAPPED)((char *)this + 72)) )
      {
        v13 = 0;
LABEL_11:
        Kd1394Connection::CloseSecond((Kd1394Connection *)((char *)this - 16), v13);
        v9 = 0;
LABEL_65:
        if ( !*((_DWORD *)this + 170) )
          LnkOut(1u, L"Channel %d target has connected to the 1394 bus.\n", *((unsigned int *)this + 44));
        *((_DWORD *)this + 170) = 1;
        if ( !v9 )
        {
          if ( (*((_BYTE *)this + 56) & 1) != 0 )
            KdConnection::OutputIo(v14, L"1394: Read %d bytes of %d\n", a2, a3, *a4);
          *((_QWORD *)this + 18) += *a4;
        }
        return v9;
      }
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 == -2147023899 )
        {
          v7 = 1;
          v11 = (void *)*((_QWORD *)this + 4);
          v12 = (struct _OVERLAPPED *)((char *)this + 72);
          Handles[0] = *((HANDLE *)this + 12);
        }
      }
      else
      {
        v9 = -2147467259;
      }
    }
    v14 = (KdConnection *)*((_QWORD *)this + 80);
    if ( v14 )
    {
      if ( ReadFile(v14, a2, a3, a4, (LPOVERLAPPED)((char *)this + 648)) )
      {
        v13 = 1;
        goto LABEL_11;
      }
      if ( GetLastError() )
      {
        v16 = GetLastError();
        v9 = v16;
        if ( v16 > 0 )
          v9 = (unsigned __int16)v16 | 0x80070000;
        if ( v9 == -2147023899 )
        {
          if ( !v7 )
          {
            v11 = (void *)*((_QWORD *)this + 80);
            v12 = (struct _OVERLAPPED *)((char *)this + 648);
          }
          v14 = (KdConnection *)v7++;
          Handles[(_QWORD)v14] = (HANDLE)*((_QWORD *)this + 84);
        }
      }
      else
      {
        v9 = -2147467259;
      }
    }
    if ( !v7 )
    {
      if ( v9 != -2147024775 )
        Sleep(0xAu);
      goto LABEL_59;
    }
    v17 = WaitForMultipleObjectsEx(v7, Handles, 0, 0xFFFFFFFF, 0);
    if ( v17 )
    {
      if ( v17 != 1 )
      {
        DbgCancelIo(v11);
        if ( v7 == 2 )
          DbgCancelIo(*((void **)this + 80));
        if ( !GetLastError() )
          return (unsigned int)-2147467259;
        v22 = GetLastError();
        v9 = v22;
        if ( v22 > 0 )
          v9 = (unsigned __int16)v22 | 0x80070000;
LABEL_59:
        if ( v9 == -2147024894 )
        {
          if ( *((_DWORD *)this + 170) == 1 )
            LnkOut(1u, L"Channel %d target has disconnected from the 1394 bus.\n", *((unsigned int *)this + 44));
          *((_DWORD *)this + 170) = 0;
          return v9;
        }
        if ( v9 == -2147024775 || !v9 )
          goto LABEL_65;
        return v9;
      }
      if ( !*((_QWORD *)this + 4) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v19, v18, v20, v21);
      DbgCancelIo(*((void **)this + 4));
      if ( GetOverlappedResult(*((HANDLE *)this + 80), (LPOVERLAPPED)((char *)this + 648), a4, 0) )
      {
        v9 = 0;
      }
      else if ( GetLastError() )
      {
        v23 = GetLastError();
        v9 = v23;
        if ( v23 > 0 )
          v9 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
      v24 = 1;
    }
    else
    {
      if ( v7 == 2 )
        DbgCancelIo(*((void **)this + 80));
      if ( GetOverlappedResult(v11, v12, a4, 0) )
      {
        v9 = 0;
      }
      else if ( GetLastError() )
      {
        v25 = GetLastError();
        v9 = v25;
        if ( v25 > 0 )
          v9 = (unsigned __int16)v25 | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
      v24 = v11 == *((void **)this + 80);
    }
    Kd1394Connection::CloseSecond((Kd1394Connection *)((char *)this - 16), v24);
    goto LABEL_59;
  }
  return result;
}

```

## disassembly

```asm
0x1800e2200  mov     [rsp+arg_18], rbx
0x1800e2205  mov     [rsp+nNumberOfBytesToRead], r8d
0x1800e220a  mov     [rsp+lpBuffer], rdx
0x1800e220f  push    rbp
0x1800e2210  push    rsi
0x1800e2211  push    rdi
0x1800e2212  push    r12
0x1800e2214  push    r13
0x1800e2216  push    r14
0x1800e2218  push    r15
0x1800e221a  sub     rsp, 40h
0x1800e221e  xorps   xmm0, xmm0
0x1800e2221  mov     r14, r9
0x1800e2224  movups  xmmword ptr [rsp+78h+Handles], xmm0
0x1800e2229  mov     eax, r8d
0x1800e222c  mov     r9, rdx
0x1800e222f  mov     rdi, rcx
0x1800e2232  mov     esi, [rdi+2B0h]
0x1800e2238  test    esi, esi
0x1800e223a  jz      short loc_1800E2282
0x1800e223c  cmp     eax, esi
0x1800e223e  jb      short loc_1800E2271
0x1800e2240  xor     ecx, ecx
0x1800e2242  mov     eax, esi
0x1800e2244  lock cmpxchg [rdi+2B0h], ecx
0x1800e224c  mov     eax, [rsp+78h+nNumberOfBytesToRead]
0x1800e2253  jnz     short loc_1800E2232
0x1800e2255  mov     r8d, esi; Size
0x1800e2258  lea     rdx, [rdi+1268h]; Src
0x1800e225f  mov     rcx, r9; void *
0x1800e2262  call    memmove
0x1800e2267  xor     eax, eax
0x1800e2269  mov     [r14], esi
0x1800e226c  jmp     loc_1800E2616
0x1800e2271  mov     dword ptr [r14], 0
0x1800e2278  mov     eax, 8007007Ah
0x1800e227d  jmp     loc_1800E2616
0x1800e2282  lea     rbp, [rdi-10h]
0x1800e2286  xor     edx, edx; unsigned int
0x1800e2288  mov     rcx, rbp; this
0x1800e228b  call    ?SwitchVirtualDebuggerDriverMode@Kd1394Connection@@QEAAJK@Z; Kd1394Connection::SwitchVirtualDebuggerDriverMode(ulong)
0x1800e2290  mov     ebx, eax
0x1800e2292  test    eax, eax
0x1800e2294  jnz     loc_1800E2616
0x1800e229a  mov     rcx, [rdi+20h]; hFile
0x1800e229e  xor     r12d, r12d
0x1800e22a1  xor     r13d, r13d
0x1800e22a4  test    rcx, rcx
0x1800e22a7  jz      loc_1800E2339
0x1800e22ad  mov     r8d, [rsp+78h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1800e22b5  lea     r15, [rdi+48h]
0x1800e22b9  mov     rdx, [rsp+78h+lpBuffer]; lpBuffer
0x1800e22c1  mov     r9, r14; lpNumberOfBytesRead
0x1800e22c4  mov     [rsp+78h+lpOverlapped], r15; lpOverlapped
0x1800e22c9  call    cs:__imp_ReadFile
0x1800e22d0  nop     dword ptr [rax+rax+00h]
0x1800e22d5  test    eax, eax
0x1800e22d7  jz      short loc_1800E22EA
0x1800e22d9  xor     edx, edx; int
0x1800e22db  mov     rcx, rbp; this
0x1800e22de  call    ?CloseSecond@Kd1394Connection@@QEAAXH@Z; Kd1394Connection::CloseSecond(int)
0x1800e22e3  xor     ebx, ebx
0x1800e22e5  jmp     loc_1800E25B2
0x1800e22ea  call    cs:__imp_GetLastError
0x1800e22f1  nop     dword ptr [rax+rax+00h]
0x1800e22f6  test    eax, eax
0x1800e22f8  jnz     short loc_1800E2301
0x1800e22fa  mov     ebx, 80004005h
0x1800e22ff  jmp     short loc_1800E2339
0x1800e2301  call    cs:__imp_GetLastError
0x1800e2308  nop     dword ptr [rax+rax+00h]
0x1800e230d  mov     ebx, eax
0x1800e230f  test    eax, eax
0x1800e2311  jle     short loc_1800E231C
0x1800e2313  movzx   ebx, ax
0x1800e2316  or      ebx, 80070000h
0x1800e231c  cmp     ebx, 800703E5h
0x1800e2322  jnz     short loc_1800E2339
0x1800e2324  mov     rax, [rdi+60h]
0x1800e2328  mov     esi, 1
0x1800e232d  mov     r12, [rdi+20h]
0x1800e2331  mov     r13, r15
0x1800e2334  mov     [rsp+78h+Handles], rax
0x1800e2339  mov     rcx, [rdi+280h]; hFile
0x1800e2340  test    rcx, rcx
0x1800e2343  jz      loc_1800E23DA
0x1800e2349  mov     r8d, [rsp+78h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1800e2351  lea     r15, [rdi+288h]
0x1800e2358  mov     rdx, [rsp+78h+lpBuffer]; lpBuffer
0x1800e2360  mov     r9, r14; lpNumberOfBytesRead
0x1800e2363  mov     [rsp+78h+lpOverlapped], r15; lpOverlapped
0x1800e2368  call    cs:__imp_ReadFile
0x1800e236f  nop     dword ptr [rax+rax+00h]
0x1800e2374  test    eax, eax
0x1800e2376  jz      short loc_1800E2382
0x1800e2378  mov     edx, 1
0x1800e237d  jmp     loc_1800E22DB
0x1800e2382  call    cs:__imp_GetLastError
0x1800e2389  nop     dword ptr [rax+rax+00h]
0x1800e238e  test    eax, eax
0x1800e2390  jnz     short loc_1800E2399
0x1800e2392  mov     ebx, 80004005h
0x1800e2397  jmp     short loc_1800E23DA
0x1800e2399  call    cs:__imp_GetLastError
0x1800e23a0  nop     dword ptr [rax+rax+00h]
0x1800e23a5  mov     ebx, eax
0x1800e23a7  test    eax, eax
0x1800e23a9  jle     short loc_1800E23B4
0x1800e23ab  movzx   ebx, ax
0x1800e23ae  or      ebx, 80070000h
0x1800e23b4  cmp     ebx, 800703E5h
0x1800e23ba  jnz     short loc_1800E23DA
0x1800e23bc  test    esi, esi
0x1800e23be  jnz     short loc_1800E23CA
0x1800e23c0  mov     r12, [rdi+280h]
0x1800e23c7  mov     r13, r15
0x1800e23ca  mov     rax, [rdi+2A0h]
0x1800e23d1  mov     ecx, esi
0x1800e23d3  inc     esi
0x1800e23d5  mov     [rsp+rcx*8+78h+Handles], rax
0x1800e23da  mov     r15d, 80070079h
0x1800e23e0  test    esi, esi
0x1800e23e2  jnz     short loc_1800E2401
0x1800e23e4  cmp     ebx, r15d
0x1800e23e7  jz      loc_1800E2574
0x1800e23ed  lea     ecx, [rsi+0Ah]; dwMilliseconds
0x1800e23f0  call    cs:__imp_Sleep
0x1800e23f7  nop     dword ptr [rax+rax+00h]
0x1800e23fc  jmp     loc_1800E2574
0x1800e2401  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800e2405  mov     dword ptr [rsp+78h+lpOverlapped], 0; bAlertable
0x1800e240d  xor     r8d, r8d; bWaitAll
0x1800e2410  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1800e2415  mov     ecx, esi; nCount
0x1800e2417  call    cs:__imp_WaitForMultipleObjectsEx
0x1800e241e  nop     dword ptr [rax+rax+00h]
0x1800e2423  test    eax, eax
0x1800e2425  jz      loc_1800E24FD
0x1800e242b  cmp     eax, 1
0x1800e242e  jz      short loc_1800E2487
0x1800e2430  mov     rcx, r12; void *
0x1800e2433  call    ?DbgCancelIo@@YAHPEAX@Z; DbgCancelIo(void *)
0x1800e2438  cmp     esi, 2
0x1800e243b  jnz     short loc_1800E2449
0x1800e243d  mov     rcx, [rdi+280h]; void *
0x1800e2444  call    ?DbgCancelIo@@YAHPEAX@Z; DbgCancelIo(void *)
0x1800e2449  call    cs:__imp_GetLastError
0x1800e2450  nop     dword ptr [rax+rax+00h]
0x1800e2455  test    eax, eax
0x1800e2457  jnz     short loc_1800E2463
0x1800e2459  mov     ebx, 80004005h
0x1800e245e  jmp     loc_1800E2614
0x1800e2463  call    cs:__imp_GetLastError
0x1800e246a  nop     dword ptr [rax+rax+00h]
0x1800e246f  mov     ebx, eax
0x1800e2471  test    eax, eax
0x1800e2473  jle     loc_1800E2574
0x1800e2479  movzx   ebx, ax
0x1800e247c  or      ebx, 80070000h
0x1800e2482  jmp     loc_1800E2574
0x1800e2487  cmp     qword ptr [rdi+20h], 0
0x1800e248c  jnz     short loc_1800E2493
0x1800e248e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e2493  mov     rcx, [rdi+20h]; void *
0x1800e2497  call    ?DbgCancelIo@@YAHPEAX@Z; DbgCancelIo(void *)
0x1800e249c  mov     rcx, [rdi+280h]; hFile
0x1800e24a3  lea     rdx, [rdi+288h]; lpOverlapped
0x1800e24aa  xor     r9d, r9d; bWait
0x1800e24ad  mov     r8, r14; lpNumberOfBytesTransferred
0x1800e24b0  call    cs:__imp_GetOverlappedResult
0x1800e24b7  nop     dword ptr [rax+rax+00h]
0x1800e24bc  test    eax, eax
0x1800e24be  jz      short loc_1800E24C4
0x1800e24c0  xor     ebx, ebx
0x1800e24c2  jmp     short loc_1800E24F6
0x1800e24c4  call    cs:__imp_GetLastError
0x1800e24cb  nop     dword ptr [rax+rax+00h]
0x1800e24d0  test    eax, eax
0x1800e24d2  jnz     short loc_1800E24DB
0x1800e24d4  mov     ebx, 80004005h
0x1800e24d9  jmp     short loc_1800E24F6
0x1800e24db  call    cs:__imp_GetLastError
0x1800e24e2  nop     dword ptr [rax+rax+00h]
0x1800e24e7  mov     ebx, eax
0x1800e24e9  test    eax, eax
0x1800e24eb  jle     short loc_1800E24F6
0x1800e24ed  movzx   ebx, ax
0x1800e24f0  or      ebx, 80070000h
0x1800e24f6  mov     edx, 1
0x1800e24fb  jmp     short loc_1800E256C
0x1800e24fd  cmp     esi, 2
0x1800e2500  jnz     short loc_1800E250E
0x1800e2502  mov     rcx, [rdi+280h]; void *
0x1800e2509  call    ?DbgCancelIo@@YAHPEAX@Z; DbgCancelIo(void *)
0x1800e250e  xor     r9d, r9d; bWait
0x1800e2511  mov     r8, r14; lpNumberOfBytesTransferred
0x1800e2514  mov     rdx, r13; lpOverlapped
0x1800e2517  mov     rcx, r12; hFile
0x1800e251a  call    cs:__imp_GetOverlappedResult
0x1800e2521  nop     dword ptr [rax+rax+00h]
0x1800e2526  test    eax, eax
0x1800e2528  jz      short loc_1800E252E
0x1800e252a  xor     ebx, ebx
0x1800e252c  jmp     short loc_1800E2560
0x1800e252e  call    cs:__imp_GetLastError
0x1800e2535  nop     dword ptr [rax+rax+00h]
0x1800e253a  test    eax, eax
0x1800e253c  jnz     short loc_1800E2545
0x1800e253e  mov     ebx, 80004005h
0x1800e2543  jmp     short loc_1800E2560
0x1800e2545  call    cs:__imp_GetLastError
0x1800e254c  nop     dword ptr [rax+rax+00h]
0x1800e2551  mov     ebx, eax
0x1800e2553  test    eax, eax
0x1800e2555  jle     short loc_1800E2560
0x1800e2557  movzx   ebx, ax
0x1800e255a  or      ebx, 80070000h
0x1800e2560  xor     edx, edx
0x1800e2562  cmp     r12, [rdi+280h]
0x1800e2569  setz    dl; int
0x1800e256c  mov     rcx, rbp; this
0x1800e256f  call    ?CloseSecond@Kd1394Connection@@QEAAXH@Z; Kd1394Connection::CloseSecond(int)
0x1800e2574  cmp     ebx, 80070002h
0x1800e257a  jnz     short loc_1800E25A9
0x1800e257c  cmp     dword ptr [rdi+2A8h], 1
0x1800e2583  jnz     short loc_1800E259D
0x1800e2585  mov     r8d, [rdi+0B0h]
0x1800e258c  lea     rdx, aChannelDTarget_0; "Channel %d target has disconnected from"...
0x1800e2593  mov     ecx, 1; unsigned int
0x1800e2598  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1800e259d  mov     dword ptr [rdi+2A8h], 0
0x1800e25a7  jmp     short loc_1800E2614
0x1800e25a9  cmp     ebx, r15d
0x1800e25ac  jz      short loc_1800E25B2
0x1800e25ae  test    ebx, ebx
0x1800e25b0  jnz     short loc_1800E2614
0x1800e25b2  cmp     dword ptr [rdi+2A8h], 0
0x1800e25b9  jnz     short loc_1800E25D3
0x1800e25bb  mov     r8d, [rdi+0B0h]
0x1800e25c2  lea     rdx, aChannelDTarget; "Channel %d target has connected to the "...
0x1800e25c9  mov     ecx, 1; unsigned int
0x1800e25ce  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1800e25d3  mov     dword ptr [rdi+2A8h], 1
0x1800e25dd  test    ebx, ebx
0x1800e25df  jnz     short loc_1800E2614
0x1800e25e1  test    byte ptr [rdi+38h], 1
0x1800e25e5  jz      short loc_1800E260A
0x1800e25e7  mov     eax, [r14]
0x1800e25ea  lea     rdx, a1394ReadDBytes; "1394: Read %d bytes of %d\n"
0x1800e25f1  mov     r9d, [rsp+78h+nNumberOfBytesToRead]; unsigned int
0x1800e25f9  mov     r8, [rsp+78h+lpBuffer]; void *
0x1800e2601  mov     dword ptr [rsp+78h+lpOverlapped], eax; unsigned int
0x1800e2605  call    ?OutputIo@KdConnection@@QEAAXPEAGPEAXKK@Z; KdConnection::OutputIo(ushort *,void *,ulong,ulong)
0x1800e260a  mov     eax, [r14]
0x1800e260d  add     [rdi+90h], rax
0x1800e2614  mov     eax, ebx
0x1800e2616  mov     rbx, [rsp+78h+arg_18]
0x1800e261e  add     rsp, 40h
0x1800e2622  pop     r15
0x1800e2624  pop     r14
0x1800e2626  pop     r13
0x1800e2628  pop     r12
0x1800e262a  pop     rdi
0x1800e262b  pop     rsi
0x1800e262c  pop     rbp
0x1800e262d  retn
```
