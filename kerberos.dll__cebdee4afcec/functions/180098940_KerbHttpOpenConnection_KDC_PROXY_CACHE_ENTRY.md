# KerbHttpOpenConnection(_KDC_PROXY_CACHE_ENTRY *)

- ea: `0x180098940`
- end: `0x180098a56`
- name: `?KerbHttpOpenConnection@@YAKPEAU_KDC_PROXY_CACHE_ENTRY@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(struct _KDC_PROXY_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005228c`

## callees

- `0x18008b70c`
- `0x180098940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800989bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800989bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a01`
- `WINHTTP!WinHttpCloseHandle` at `0x180098a2e`
- `WINHTTP!WinHttpCloseHandle` at `0x180098a2e`
- `WINHTTP!WinHttpOpen` at `0x1800989af`
- `WINHTTP!WinHttpOpen` at `0x1800989af`
- `WINHTTP!WinHttpConnect` at `0x1800989f6`
- `WINHTTP!WinHttpConnect` at `0x1800989f6`

## string_xrefs

- `0x1800989c3`: `WinHttpOpen failed: %#x`
- `0x1800989d0`: `KerbHttpOpenConnection`
- `0x180098a14`: `KerbHttpOpenConnection`

## pseudocode

```c
__int64 __fastcall KerbHttpOpenConnection(struct _KDC_PROXY_CACHE_ENTRY *a1)
{
  __int64 v1; // rdx
  DWORD LastError; // edi
  const WCHAR *v4; // r9
  const WCHAR *v5; // r8
  void *v6; // rax
  void *v7; // rsi
  HINTERNET v8; // rax

  v1 = *((_QWORD *)a1 + 13);
  LastError = 0;
  if ( v1 )
  {
    if ( *((_WORD *)a1 + 48) )
      *(_WORD *)(v1 + 2 * ((unsigned __int64)*((unsigned __int16 *)a1 + 48) >> 1)) = 0;
    else
      *((_QWORD *)a1 + 13) = 0;
    if ( *((_WORD *)a1 + 56) )
      *(_WORD *)(*((_QWORD *)a1 + 15) + 2 * ((unsigned __int64)*((unsigned __int16 *)a1 + 56) >> 1)) = 0;
    else
      *((_QWORD *)a1 + 15) = 0;
    v4 = (const WCHAR *)*((_QWORD *)a1 + 15);
    LODWORD(v1) = 3;
    v5 = (const WCHAR *)*((_QWORD *)a1 + 13);
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  v6 = WinHttpOpen(L"kerberos/1.0", v1, v5, v4, 0);
  v7 = v6;
  if ( v6 )
  {
    v8 = WinHttpConnect(v6, *((LPCWSTR *)a1 + 8), *((_WORD *)a1 + 36), 0);
    if ( v8 )
    {
      *((_QWORD *)a1 + 27) = v7;
      *((_QWORD *)a1 + 28) = v8;
    }
    else
    {
      LastError = GetLastError();
      KerbTracerT::Log(1, "KerbHttpOpenConnection", 3249, "WinHttpConnect failed: %#x", LastError);
      WinHttpCloseHandle(v7);
    }
  }
  else
  {
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbHttpOpenConnection", 3234, "WinHttpOpen failed: %#x", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180098940  mov     [rsp+arg_0], rbx
0x180098945  mov     [rsp+arg_8], rsi
0x18009894a  push    rdi
0x18009894b  sub     rsp, 30h
0x18009894f  mov     rdx, [rcx+68h]
0x180098953  xor     edi, edi
0x180098955  mov     rbx, rcx
0x180098958  test    rdx, rdx
0x18009895b  jnz     short loc_180098965
0x18009895d  xor     r9d, r9d
0x180098960  xor     r8d, r8d
0x180098963  jmp     short loc_1800989A4
0x180098965  cmp     [rcx+60h], di
0x180098969  jnz     short loc_180098971
0x18009896b  mov     [rcx+68h], rdi
0x18009896f  jmp     short loc_18009897C
0x180098971  movzx   ecx, word ptr [rcx+60h]
0x180098975  shr     rcx, 1
0x180098978  mov     [rdx+rcx*2], di
0x18009897c  cmp     [rbx+70h], di
0x180098980  jnz     short loc_180098988
0x180098982  mov     [rbx+78h], rdi
0x180098986  jmp     short loc_180098997
0x180098988  movzx   edx, word ptr [rbx+70h]
0x18009898c  mov     rcx, [rbx+78h]
0x180098990  shr     rdx, 1
0x180098993  mov     [rcx+rdx*2], di
0x180098997  mov     r9, [rbx+78h]; pszProxyBypassW
0x18009899b  mov     edx, 3; dwAccessType
0x1800989a0  mov     r8, [rbx+68h]; pszProxyW
0x1800989a4  lea     rcx, pszAgentW; "kerberos/1.0"
0x1800989ab  mov     [rsp+38h+dwFlags], edi; dwFlags
0x1800989af  call    cs:__imp_WinHttpOpen
0x1800989b5  mov     rsi, rax
0x1800989b8  test    rax, rax
0x1800989bb  jnz     short loc_1800989E7
0x1800989bd  call    cs:__imp_GetLastError
0x1800989c3  lea     r9, aWinhttpopenFai; "WinHttpOpen failed: %#x"
0x1800989ca  mov     r8d, 0CA2h
0x1800989d0  lea     rdx, aKerbhttpopenco; "KerbHttpOpenConnection"
0x1800989d7  mov     [rsp+38h+dwFlags], eax
0x1800989db  lea     ecx, [rsi+1]
0x1800989de  mov     edi, eax
0x1800989e0  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800989e5  jmp     short loc_180098A44
0x1800989e7  movzx   r8d, word ptr [rbx+48h]; nServerPort
0x1800989ec  xor     r9d, r9d; dwReserved
0x1800989ef  mov     rdx, [rbx+40h]; pswzServerName
0x1800989f3  mov     rcx, rsi; hSession
0x1800989f6  call    cs:__imp_WinHttpConnect
0x1800989fc  test    rax, rax
0x1800989ff  jnz     short loc_180098A36
0x180098a01  call    cs:__imp_GetLastError
0x180098a07  lea     r9, aWinhttpconnect_0; "WinHttpConnect failed: %#x"
0x180098a0e  mov     r8d, 0CB1h
0x180098a14  lea     rdx, aKerbhttpopenco; "KerbHttpOpenConnection"
0x180098a1b  mov     [rsp+38h+dwFlags], eax
0x180098a1f  mov     ecx, 1
0x180098a24  mov     edi, eax
0x180098a26  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180098a2b  mov     rcx, rsi; hInternet
0x180098a2e  call    cs:__imp_WinHttpCloseHandle
0x180098a34  jmp     short loc_180098A44
0x180098a36  mov     [rbx+0D8h], rsi
0x180098a3d  mov     [rbx+0E0h], rax
0x180098a44  mov     rbx, [rsp+38h+arg_0]
0x180098a49  mov     eax, edi
0x180098a4b  mov     rsi, [rsp+38h+arg_8]
0x180098a50  add     rsp, 30h
0x180098a54  pop     rdi
0x180098a55  retn
```
