# ProxyResolver::ResolveProxy(void *,ushort const *)

- ea: `0x18002cf3c`
- end: `0x18002d17d`
- name: `?ResolveProxy@ProxyResolver@@QEAAKPEAXPEBG@Z`
- size: `577`
- prototype: `unsigned int __fastcall(ProxyResolver *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c180`

## callees

- `0x18002cb54`
- `0x18002cecc`
- `0x18002cf3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d111`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d11f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d12e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d145`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d15c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d111`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d11f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d12e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d145`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d15c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002cfc9`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d004`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d020`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d068`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d0e2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002cfc9`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d004`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d020`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d068`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002d0e2`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002cf93`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002d0a4`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002d0bd`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002d100`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002cf93`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002d0a4`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002d0bd`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002d100`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18002cf9d`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18002cf9d`

## pseudocode

```c
__int64 __fastcall ProxyResolver::ResolveProxy(ProxyResolver *this, void *a2, const unsigned __int16 *a3)
{
  bool v3; // zf
  DWORD LastError; // ebx
  int v8; // r14d
  ProxyResolver *v9; // rcx
  unsigned int v10; // ecx
  HGLOBAL v11; // r14
  HGLOBAL v12; // rsi
  ProxyResolver *v13; // rcx
  void *lpszProxy; // rsi
  const unsigned __int16 *lpszProxyBypass; // r15
  const unsigned __int16 *v16; // rcx
  const unsigned __int16 *v17; // rcx
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+30h] [rbp-20h] BYREF
  HGLOBAL hMem; // [rsp+80h] [rbp+30h] BYREF
  HGLOBAL v21; // [rsp+98h] [rbp+48h] BYREF

  v3 = *(_DWORD *)this == 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  hMem = 0;
  v21 = 0;
  if ( !v3 )
  {
    LastError = 4317;
    goto LABEL_25;
  }
  CSPrintErrorLineFileData(a3, 0x30C01D8u, 0);
  if ( !WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
      goto LABEL_25;
    pProxyConfig.fAutoDetect = 1;
    CSPrintErrorLineFile(0x31901D8u, 0);
  }
  if ( !pProxyConfig.fAutoDetect )
    goto LABEL_11;
  v8 = 1;
  LastError = ProxyResolver::GetProxyForAutoSettings(
                this,
                a2,
                a3,
                0,
                (unsigned __int16 **)&hMem,
                (unsigned __int16 **)&v21);
  CSPrintErrorLineFile(0x32E01D8u, LastError);
  if ( !LastError )
    goto LABEL_15;
  if ( (unsigned int)ProxyResolver::IsRecoverableAutoProxyError(v9, LastError) )
  {
LABEL_11:
    if ( !pProxyConfig.lpszAutoConfigUrl )
    {
LABEL_16:
      lpszProxy = pProxyConfig.lpszProxy;
      v8 = 0;
      v16 = pProxyConfig.lpszProxy;
      pProxyConfig.lpszProxy = 0;
      CSPrintErrorLineFileData(v16, 0x36401D8u, 0);
      lpszProxyBypass = pProxyConfig.lpszProxyBypass;
      v17 = pProxyConfig.lpszProxyBypass;
      pProxyConfig.lpszProxyBypass = 0;
      CSPrintErrorLineFileData(v17, 0x36801D8u, 0);
      LastError = 0;
      goto LABEL_17;
    }
    v8 = 1;
    LastError = ProxyResolver::GetProxyForAutoSettings(
                  this,
                  a2,
                  a3,
                  pProxyConfig.lpszAutoConfigUrl,
                  (unsigned __int16 **)&hMem,
                  (unsigned __int16 **)&v21);
    CSPrintErrorLineFile(0x34B01D8u, LastError);
    if ( LastError )
    {
      if ( !(unsigned int)ProxyResolver::IsRecoverableAutoProxyError(v13, LastError) )
      {
        v10 = 55837144;
        goto LABEL_10;
      }
      goto LABEL_16;
    }
LABEL_15:
    lpszProxy = hMem;
    lpszProxyBypass = (const unsigned __int16 *)v21;
LABEL_17:
    *((_DWORD *)this + 18) = v8;
    if ( lpszProxy )
    {
      *((_DWORD *)this + 8) = 3;
      CSPrintErrorLineFile(0x37501D8u, LastError);
    }
    else
    {
      *((_DWORD *)this + 8) = 1;
    }
    *((_QWORD *)this + 5) = lpszProxy;
    v11 = 0;
    v12 = 0;
    *((_QWORD *)this + 6) = lpszProxyBypass;
    CSPrintErrorLineFileData(lpszProxyBypass, 0x37D01D8u, 0);
    *(_DWORD *)this = 1;
    goto LABEL_21;
  }
  v10 = 53936600;
LABEL_10:
  CSPrintErrorLineFile(v10, LastError);
  v11 = hMem;
  v12 = v21;
LABEL_21:
  if ( v11 )
    GlobalFree(v11);
  if ( v12 )
    GlobalFree(v12);
LABEL_25:
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
    pProxyConfig.lpszAutoConfigUrl = 0;
  }
  if ( pProxyConfig.lpszProxy )
  {
    GlobalFree(pProxyConfig.lpszProxy);
    pProxyConfig.lpszProxy = 0;
  }
  if ( pProxyConfig.lpszProxyBypass )
    GlobalFree(pProxyConfig.lpszProxyBypass);
  return LastError;
}

```

## disassembly

```asm
0x18002cf3c  mov     [rsp-28h+arg_8], rbx
0x18002cf41  mov     [rsp-28h+arg_10], rsi
0x18002cf46  push    rbp
0x18002cf47  push    rdi
0x18002cf48  push    r13
0x18002cf4a  push    r14
0x18002cf4c  push    r15
0x18002cf4e  mov     rbp, rsp
0x18002cf51  sub     rsp, 50h
0x18002cf55  cmp     dword ptr [rcx], 0
0x18002cf58  xorps   xmm0, xmm0
0x18002cf5b  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm0
0x18002cf5f  mov     rsi, r8
0x18002cf62  mov     r15, rdx
0x18002cf65  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x18002cf69  mov     rdi, rcx
0x18002cf6c  mov     [rbp+hMem], 0
0x18002cf74  mov     [rbp+arg_18], 0
0x18002cf7c  jz      short loc_18002CF88
0x18002cf7e  mov     ebx, 10DDh
0x18002cf83  jmp     loc_18002D125
0x18002cf88  xor     r8d, r8d
0x18002cf8b  mov     edx, 30C01D8h
0x18002cf90  mov     rcx, rsi
0x18002cf93  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002cf99  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x18002cf9d  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18002cfa3  mov     r13d, 1
0x18002cfa9  test    eax, eax
0x18002cfab  jnz     short loc_18002CFCF
0x18002cfad  call    cs:__imp_GetLastError
0x18002cfb3  mov     ebx, eax
0x18002cfb5  cmp     eax, 2
0x18002cfb8  jnz     loc_18002D125
0x18002cfbe  xor     edx, edx
0x18002cfc0  mov     [rbp+pProxyConfig.fAutoDetect], r13d
0x18002cfc4  mov     ecx, 31901D8h
0x18002cfc9  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002cfcf  cmp     [rbp+pProxyConfig.fAutoDetect], 0
0x18002cfd3  jz      short loc_18002D033
0x18002cfd5  lea     rax, [rbp+arg_18]
0x18002cfd9  xor     r9d, r9d; unsigned __int16 *
0x18002cfdc  mov     [rsp+50h+var_28], rax; unsigned __int16 **
0x18002cfe1  mov     r8, rsi; unsigned __int16 *
0x18002cfe4  lea     rax, [rbp+hMem]
0x18002cfe8  mov     rdx, r15; void *
0x18002cfeb  mov     rcx, rdi; this
0x18002cfee  mov     [rsp+50h+var_30], rax; unsigned __int16 **
0x18002cff3  mov     r14d, r13d
0x18002cff6  call    ?GetProxyForAutoSettings@ProxyResolver@@AEAAKPEAXPEBG1PEAPEAG2@Z; ProxyResolver::GetProxyForAutoSettings(void *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18002cffb  mov     edx, eax
0x18002cffd  mov     ecx, 32E01D8h
0x18002d002  mov     ebx, eax
0x18002d004  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002d00a  test    ebx, ebx
0x18002d00c  jz      short loc_18002D084
0x18002d00e  mov     edx, ebx; unsigned int
0x18002d010  call    ?IsRecoverableAutoProxyError@ProxyResolver@@AEAAHK@Z; ProxyResolver::IsRecoverableAutoProxyError(ulong)
0x18002d015  test    eax, eax
0x18002d017  jnz     short loc_18002D033
0x18002d019  mov     ecx, 33701D8h
0x18002d01e  mov     edx, ebx
0x18002d020  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002d026  mov     r14, [rbp+hMem]
0x18002d02a  mov     rsi, [rbp+arg_18]
0x18002d02e  jmp     loc_18002D109
0x18002d033  mov     r9, [rbp+pProxyConfig.lpszAutoConfigUrl]; unsigned __int16 *
0x18002d037  test    r9, r9
0x18002d03a  jz      short loc_18002D08E
0x18002d03c  lea     rax, [rbp+arg_18]
0x18002d040  mov     r8, rsi; unsigned __int16 *
0x18002d043  mov     [rsp+50h+var_28], rax; unsigned __int16 **
0x18002d048  mov     rdx, r15; void *
0x18002d04b  lea     rax, [rbp+hMem]
0x18002d04f  mov     rcx, rdi; this
0x18002d052  mov     [rsp+50h+var_30], rax; unsigned __int16 **
0x18002d057  mov     r14d, r13d
0x18002d05a  call    ?GetProxyForAutoSettings@ProxyResolver@@AEAAKPEAXPEBG1PEAPEAG2@Z; ProxyResolver::GetProxyForAutoSettings(void *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18002d05f  mov     edx, eax
0x18002d061  mov     ecx, 34B01D8h
0x18002d066  mov     ebx, eax
0x18002d068  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002d06e  test    ebx, ebx
0x18002d070  jz      short loc_18002D084
0x18002d072  mov     edx, ebx; unsigned int
0x18002d074  call    ?IsRecoverableAutoProxyError@ProxyResolver@@AEAAHK@Z; ProxyResolver::IsRecoverableAutoProxyError(ulong)
0x18002d079  test    eax, eax
0x18002d07b  jnz     short loc_18002D08E
0x18002d07d  mov     ecx, 35401D8h
0x18002d082  jmp     short loc_18002D01E
0x18002d084  mov     rsi, [rbp+hMem]
0x18002d088  mov     r15, [rbp+arg_18]
0x18002d08c  jmp     short loc_18002D0C5
0x18002d08e  mov     rsi, [rbp+pProxyConfig.lpszProxy]
0x18002d092  xor     r14d, r14d
0x18002d095  mov     rcx, rsi
0x18002d098  mov     [rbp+pProxyConfig.lpszProxy], r14
0x18002d09c  xor     r8d, r8d
0x18002d09f  mov     edx, 36401D8h
0x18002d0a4  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002d0aa  mov     r15, [rbp+pProxyConfig.lpszProxyBypass]
0x18002d0ae  xor     r8d, r8d
0x18002d0b1  mov     rcx, r15
0x18002d0b4  mov     [rbp+pProxyConfig.lpszProxyBypass], r14
0x18002d0b8  mov     edx, 36801D8h
0x18002d0bd  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002d0c3  xor     ebx, ebx
0x18002d0c5  mov     [rdi+48h], r14d
0x18002d0c9  test    rsi, rsi
0x18002d0cc  jnz     short loc_18002D0D4
0x18002d0ce  mov     [rdi+20h], r13d
0x18002d0d2  jmp     short loc_18002D0E8
0x18002d0d4  mov     edx, ebx
0x18002d0d6  mov     dword ptr [rdi+20h], 3
0x18002d0dd  mov     ecx, 37501D8h
0x18002d0e2  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002d0e8  mov     [rdi+28h], rsi
0x18002d0ec  xor     r14d, r14d
0x18002d0ef  xor     esi, esi
0x18002d0f1  mov     [rdi+30h], r15
0x18002d0f5  xor     r8d, r8d
0x18002d0f8  mov     edx, 37D01D8h
0x18002d0fd  mov     rcx, r15
0x18002d100  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002d106  mov     [rdi], r13d
0x18002d109  test    r14, r14
0x18002d10c  jz      short loc_18002D117
0x18002d10e  mov     rcx, r14; hMem
0x18002d111  call    cs:__imp_GlobalFree
0x18002d117  test    rsi, rsi
0x18002d11a  jz      short loc_18002D125
0x18002d11c  mov     rcx, rsi; hMem
0x18002d11f  call    cs:__imp_GlobalFree
0x18002d125  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]; hMem
0x18002d129  test    rcx, rcx
0x18002d12c  jz      short loc_18002D13C
0x18002d12e  call    cs:__imp_GlobalFree
0x18002d134  mov     [rbp+pProxyConfig.lpszAutoConfigUrl], 0
0x18002d13c  mov     rcx, [rbp+pProxyConfig.lpszProxy]; hMem
0x18002d140  test    rcx, rcx
0x18002d143  jz      short loc_18002D153
0x18002d145  call    cs:__imp_GlobalFree
0x18002d14b  mov     [rbp+pProxyConfig.lpszProxy], 0
0x18002d153  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]; hMem
0x18002d157  test    rcx, rcx
0x18002d15a  jz      short loc_18002D162
0x18002d15c  call    cs:__imp_GlobalFree
0x18002d162  lea     r11, [rsp+50h+var_s0]
0x18002d167  mov     eax, ebx
0x18002d169  mov     rbx, [r11+38h]
0x18002d16d  mov     rsi, [r11+40h]
0x18002d171  mov     rsp, r11
0x18002d174  pop     r15
0x18002d176  pop     r14
0x18002d178  pop     r13
0x18002d17a  pop     rdi
0x18002d17b  pop     rbp
0x18002d17c  retn
```
