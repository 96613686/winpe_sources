# CAsyncHttp::Connect(void)

- ea: `0x1800a694c`
- end: `0x1800a6b83`
- name: `?Connect@CAsyncHttp@@QEAAJXZ`
- size: `567`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ae020`
- `0x1800af5c0`

## callees

- `0x180022420`
- `0x1800a6744`
- `0x1800a694c`
- `0x1800a6c88`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a6a67`
- `KERNEL32!GetLastError` at `0x1800a6b02`
- `KERNEL32!GetLastError` at `0x1800a6a67`
- `KERNEL32!GetLastError` at `0x1800a6b02`
- `KERNEL32!LeaveCriticalSection` at `0x1800a6a82`
- `KERNEL32!LeaveCriticalSection` at `0x1800a6b0d`
- `KERNEL32!LeaveCriticalSection` at `0x1800a6a82`
- `KERNEL32!LeaveCriticalSection` at `0x1800a6b0d`
- `KERNEL32!EnterCriticalSection` at `0x1800a6a39`
- `KERNEL32!EnterCriticalSection` at `0x1800a6a93`
- `KERNEL32!EnterCriticalSection` at `0x1800a6a39`
- `KERNEL32!EnterCriticalSection` at `0x1800a6a93`
- `USER32!LoadStringA` at `0x1800a69e1`
- `USER32!LoadStringA` at `0x1800a69e1`
- `WININET!InternetOpenA` at `0x1800a6a58`
- `WININET!InternetOpenA` at `0x1800a6a58`
- `WININET!InternetConnectA` at `0x1800a6af4`
- `WININET!InternetConnectA` at `0x1800a6af4`
- `WININET!InternetSetOptionA` at `0x1800a6aba`
- `WININET!InternetSetOptionA` at `0x1800a6aba`

## string_xrefs

- `0x1800a6a4f`: `Athena Communities HTTP Agent`

## pseudocode

```c
__int64 __fastcall CAsyncHttp::Connect(DWORD_PTR dwContext)
{
  int v2; // edi
  HINTERNET v3; // rax
  signed int LastError; // eax
  void *v5; // rcx
  unsigned int *v6; // rsi
  __int64 v7; // rdx
  bool v9; // sf
  int dwFlags; // [rsp+20h] [rbp-288h]
  int v11[4]; // [rsp+40h] [rbp-268h] BYREF
  CHAR Buffer[272]; // [rsp+50h] [rbp-258h] BYREF
  char v13[272]; // [rsp+160h] [rbp-148h] BYREF

  if ( *(_DWORD *)(dwContext + 104) && *(_DWORD *)(dwContext + 104) != 10 )
  {
    if ( *(_QWORD *)(dwContext + 72) )
      return 2148322307LL;
    CAsyncHttp::ChangeState(dwContext, 0, 0);
  }
  CAsyncHttp::ChangeState(dwContext, 3, 3);
  if ( *(_QWORD *)(dwContext + 120) )
  {
    memset_0(v13, 0, 0x104u);
    memset_0(Buffer, 0, 0x104u);
    if ( LoadStringA(g_hLocRes, 0x450u, Buffer, 260) )
    {
      dwFlags = 80;
      StringCchPrintfA(v13, 0x104u, Buffer, dwContext + 142, dwFlags);
      (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)(dwContext + 120) + 48LL))(
        *(_QWORD *)(dwContext + 120),
        v13);
    }
  }
  *(_DWORD *)(dwContext + 2768) = 0;
  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 16));
  if ( !*(_QWORD *)(dwContext + 64) )
  {
    v3 = InternetOpenA("Athena Communities HTTP Agent", 0, 0, 0, 0);
    *(_QWORD *)(dwContext + 64) = v3;
    if ( !v3 )
    {
      LastError = GetLastError();
      *(_DWORD *)(dwContext + 116) = LastError;
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(dwContext + 16));
  if ( v2 < 0 )
  {
    v6 = (unsigned int *)(dwContext + 116);
LABEL_23:
    CAsyncHttp::FillErrorResult(*(HINTERNET *)(dwContext + 72), v6, (struct tagIXPRESULTW *)(dwContext + 2728));
    v7 = 0;
    goto LABEL_24;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 16));
  v5 = *(void **)(dwContext + 64);
  v11[0] = 1000 * *(_DWORD *)(dwContext + 136);
  if ( InternetSetOptionA(v5, 2u, v11, 4u) )
    *(_QWORD *)(dwContext + 72) = InternetConnectA(
                                    *(HINTERNET *)(dwContext + 64),
                                    (LPCSTR)(dwContext + 142),
                                    *(_WORD *)(dwContext + 140),
                                    0,
                                    0,
                                    3u,
                                    0x400200u,
                                    dwContext);
  v6 = (unsigned int *)(dwContext + 116);
  *(_DWORD *)(dwContext + 116) = GetLastError();
  LeaveCriticalSection((LPCRITICAL_SECTION)(dwContext + 16));
  if ( !*(_QWORD *)(dwContext + 72) )
  {
    v2 = *v6;
    v9 = (*v6 & 0x80000000) != 0;
    if ( (int)*v6 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80070000;
      v9 = v2 < 0;
    }
    if ( !v9 )
      return (unsigned int)v2;
    goto LABEL_23;
  }
  v2 = 0;
  v7 = 4;
LABEL_24:
  CAsyncHttp::ChangeState(dwContext, v7, 4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800a694c  push    rbx
0x1800a694e  push    rbp
0x1800a694f  push    rsi
0x1800a6950  push    rdi
0x1800a6951  sub     rsp, 288h
0x1800a6958  mov     rax, cs:__security_cookie
0x1800a695f  xor     rax, rsp
0x1800a6962  mov     [rsp+2A8h+var_38], rax
0x1800a696a  cmp     dword ptr [rcx+68h], 0
0x1800a696e  mov     rbx, rcx
0x1800a6971  jz      short loc_1800A698E
0x1800a6973  cmp     dword ptr [rcx+68h], 0Ah
0x1800a6977  jz      short loc_1800A698E
0x1800a6979  cmp     qword ptr [rcx+48h], 0
0x1800a697e  jnz     loc_1800A6B24
0x1800a6984  xor     r8d, r8d
0x1800a6987  xor     edx, edx
0x1800a6989  call    ?ChangeState@CAsyncHttp@@AEAAXW4ASYNCHTTP_STATE@@W4ASYNCHTTP_EVENT@@@Z; CAsyncHttp::ChangeState(ASYNCHTTP_STATE,ASYNCHTTP_EVENT)
0x1800a698e  mov     esi, 3
0x1800a6993  mov     rcx, rbx
0x1800a6996  mov     r8d, esi
0x1800a6999  mov     edx, esi
0x1800a699b  call    ?ChangeState@CAsyncHttp@@AEAAXW4ASYNCHTTP_STATE@@W4ASYNCHTTP_EVENT@@@Z; CAsyncHttp::ChangeState(ASYNCHTTP_STATE,ASYNCHTTP_EVENT)
0x1800a69a0  cmp     qword ptr [rbx+78h], 0
0x1800a69a5  jz      short loc_1800A6A26
0x1800a69a7  mov     edi, 104h
0x1800a69ac  lea     rcx, [rsp+2A8h+var_148]; void *
0x1800a69b4  mov     r8d, edi; Size
0x1800a69b7  xor     edx, edx; Val
0x1800a69b9  call    memset_0
0x1800a69be  mov     r8d, edi; Size
0x1800a69c1  lea     rcx, [rsp+2A8h+Buffer]; void *
0x1800a69c6  xor     edx, edx; Val
0x1800a69c8  call    memset_0
0x1800a69cd  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800a69d4  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x1800a69d9  mov     r9d, edi; cchBufferMax
0x1800a69dc  mov     edx, 450h; uID
0x1800a69e1  call    cs:__imp_LoadStringA
0x1800a69e7  test    eax, eax
0x1800a69e9  jz      short loc_1800A6A26
0x1800a69eb  lea     r9, [rbx+8Eh]
0x1800a69f2  mov     [rsp+2A8h+dwFlags], 50h ; 'P'
0x1800a69fa  lea     r8, [rsp+2A8h+Buffer]; char *
0x1800a69ff  mov     edx, edi; unsigned __int64
0x1800a6a01  lea     rcx, [rsp+2A8h+var_148]; char *
0x1800a6a09  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a6a0e  mov     rcx, [rbx+78h]
0x1800a6a12  lea     rdx, [rsp+2A8h+var_148]
0x1800a6a1a  mov     rax, [rcx]
0x1800a6a1d  mov     rax, [rax+30h]
0x1800a6a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6a26  lea     rbp, [rbx+10h]
0x1800a6a2a  mov     dword ptr [rbx+0AD0h], 0
0x1800a6a34  mov     rcx, rbp; lpCriticalSection
0x1800a6a37  xor     edi, edi
0x1800a6a39  call    cs:__imp_EnterCriticalSection
0x1800a6a3f  cmp     [rbx+40h], rdi
0x1800a6a43  jnz     short loc_1800A6A7F
0x1800a6a45  xor     r9d, r9d; lpszProxyBypass
0x1800a6a48  mov     [rsp+2A8h+dwFlags], edi; dwFlags
0x1800a6a4c  xor     r8d, r8d; lpszProxy
0x1800a6a4f  lea     rcx, szAgent; "Athena Communities HTTP Agent"
0x1800a6a56  xor     edx, edx; dwAccessType
0x1800a6a58  call    cs:__imp_InternetOpenA
0x1800a6a5e  mov     [rbx+40h], rax
0x1800a6a62  test    rax, rax
0x1800a6a65  jnz     short loc_1800A6A7F
0x1800a6a67  call    cs:__imp_GetLastError
0x1800a6a6d  mov     [rbx+74h], eax
0x1800a6a70  mov     edi, eax
0x1800a6a72  test    eax, eax
0x1800a6a74  jle     short loc_1800A6A7F
0x1800a6a76  movzx   edi, ax
0x1800a6a79  or      edi, 80070000h
0x1800a6a7f  mov     rcx, rbp; lpCriticalSection
0x1800a6a82  call    cs:__imp_LeaveCriticalSection
0x1800a6a88  test    edi, edi
0x1800a6a8a  js      loc_1800A6B40
0x1800a6a90  mov     rcx, rbp; lpCriticalSection
0x1800a6a93  call    cs:__imp_EnterCriticalSection
0x1800a6a99  imul    eax, [rbx+88h], 3E8h
0x1800a6aa3  lea     r8, [rsp+2A8h+var_268]; lpBuffer
0x1800a6aa8  mov     rcx, [rbx+40h]; hInternet
0x1800a6aac  mov     r9d, 4; dwBufferLength
0x1800a6ab2  lea     edx, [r9-2]; dwOption
0x1800a6ab6  mov     [rsp+2A8h+var_268], eax
0x1800a6aba  call    cs:__imp_InternetSetOptionA
0x1800a6ac0  test    eax, eax
0x1800a6ac2  jz      short loc_1800A6AFE
0x1800a6ac4  movzx   r8d, word ptr [rbx+8Ch]; nServerPort
0x1800a6acc  lea     rdx, [rbx+8Eh]; lpszServerName
0x1800a6ad3  mov     rcx, [rbx+40h]; hInternet
0x1800a6ad7  xor     r9d, r9d; lpszUserName
0x1800a6ada  mov     [rsp+2A8h+dwContext], rbx; dwContext
0x1800a6adf  mov     [rsp+2A8h+var_278], 400200h; dwFlags
0x1800a6ae7  mov     [rsp+2A8h+dwService], esi; dwService
0x1800a6aeb  mov     qword ptr [rsp+2A8h+dwFlags], 0; lpszPassword
0x1800a6af4  call    cs:__imp_InternetConnectA
0x1800a6afa  mov     [rbx+48h], rax
0x1800a6afe  lea     rsi, [rbx+74h]
0x1800a6b02  call    cs:__imp_GetLastError
0x1800a6b08  mov     rcx, rbp; lpCriticalSection
0x1800a6b0b  mov     [rsi], eax
0x1800a6b0d  call    cs:__imp_LeaveCriticalSection
0x1800a6b13  cmp     qword ptr [rbx+48h], 0
0x1800a6b18  jz      short loc_1800A6B2B
0x1800a6b1a  xor     edi, edi
0x1800a6b1c  lea     edx, [rdi+4]
0x1800a6b1f  mov     r8d, edx
0x1800a6b22  jmp     short loc_1800A6B5D
0x1800a6b24  mov     eax, 800CCC03h
0x1800a6b29  jmp     short loc_1800A6B67
0x1800a6b2b  mov     edi, [rsi]
0x1800a6b2d  test    edi, edi
0x1800a6b2f  jle     short loc_1800A6B3C
0x1800a6b31  movzx   edi, di
0x1800a6b34  or      edi, 80070000h
0x1800a6b3a  test    edi, edi
0x1800a6b3c  jns     short loc_1800A6B65
0x1800a6b3e  jmp     short loc_1800A6B44
0x1800a6b40  lea     rsi, [rbx+74h]
0x1800a6b44  mov     rcx, [rbx+48h]; hRequest
0x1800a6b48  lea     r8, [rbx+0AA8h]; struct tagIXPRESULTW *
0x1800a6b4f  mov     rdx, rsi; unsigned int *
0x1800a6b52  call    ?FillErrorResult@CAsyncHttp@@CAXPEAXPEAKPEAUtagIXPRESULTW@@@Z; CAsyncHttp::FillErrorResult(void *,ulong *,tagIXPRESULTW *)
0x1800a6b57  xor     edx, edx
0x1800a6b59  lea     r8d, [rdx+4]
0x1800a6b5d  mov     rcx, rbx
0x1800a6b60  call    ?ChangeState@CAsyncHttp@@AEAAXW4ASYNCHTTP_STATE@@W4ASYNCHTTP_EVENT@@@Z; CAsyncHttp::ChangeState(ASYNCHTTP_STATE,ASYNCHTTP_EVENT)
0x1800a6b65  mov     eax, edi
0x1800a6b67  mov     rcx, [rsp+2A8h+var_38]
0x1800a6b6f  xor     rcx, rsp; StackCookie
0x1800a6b72  call    __security_check_cookie
0x1800a6b77  add     rsp, 288h
0x1800a6b7e  pop     rdi
0x1800a6b7f  pop     rsi
0x1800a6b80  pop     rbp
0x1800a6b81  pop     rbx
0x1800a6b82  retn
```
