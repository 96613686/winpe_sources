# ProxyResolver::GetProxyForAutoSettingsEx(void *,ushort const *,ushort const *)

- ea: `0x18002cc88`
- end: `0x18002ce9c`
- name: `?GetProxyForAutoSettingsEx@ProxyResolver@@AEAAKPEAXPEBG1@Z`
- size: `532`
- prototype: `unsigned int __fastcall(ProxyResolver *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cb54`

## callees

- `0x18002cc88`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002cd92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ce49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002cd92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ce49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cce3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce53`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002cd01`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002ce7f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002cd01`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002ce7f`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002cd40`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002cded`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002cd40`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002cded`

## pseudocode

```c
__int64 __fastcall ProxyResolver::GetProxyForAutoSettingsEx(
        ProxyResolver *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v9; // ecx
  DWORD v10; // ebx
  DWORD v11; // edx
  __int128 v13; // [rsp+30h] [rbp-20h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h]
  HINTERNET hInternet; // [rsp+70h] [rbp+20h] BYREF

  hInternet = 0;
  v13 = 0;
  v14 = 0;
  if ( a4 )
  {
    LODWORD(v13) = 2;
    *((_QWORD *)&v13 + 1) = a4;
  }
  else
  {
    *(_QWORD *)&v13 = 0x300000001LL;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( EventW )
  {
    LastError = ((__int64 (__fastcall *)(void *, HINTERNET *))ProxyResolver::s_pfnWinhttpCreateProxyResolver)(
                  a2,
                  &hInternet);
    v10 = LastError;
    if ( LastError )
    {
      v9 = 36110808;
      goto LABEL_7;
    }
    if ( WinHttpSetStatusCallback(hInternet, ProxyResolver::GetProxyCallBack, 0x1200000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      LastError = GetLastError();
      v9 = 36897240;
    }
    else
    {
      LastError = ((__int64 (__fastcall *)(HINTERNET, const unsigned __int16 *, __int128 *, ProxyResolver *))ProxyResolver::s_pfnWinhttpGetProxyForUrlEx)(
                    hInternet,
                    a3,
                    &v13,
                    this);
      v10 = LastError;
      if ( LastError != 997 )
      {
        v9 = 37618136;
        goto LABEL_7;
      }
      if ( !WaitForSingleObjectEx(*((HANDLE *)this + 3), 0x1D4C0u, 0) )
      {
        if ( *((_DWORD *)this + 4) )
        {
          LastError = ((__int64 (__fastcall *)(void *, HINTERNET *))ProxyResolver::s_pfnWinhttpCreateProxyResolver)(
                        a2,
                        &hInternet);
          v10 = LastError;
          if ( LastError )
          {
            v9 = 39125464;
            goto LABEL_7;
          }
          if ( WinHttpSetStatusCallback(hInternet, ProxyResolver::GetProxyCallBack, 0x1200000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
          {
            LastError = GetLastError();
            v9 = 39911896;
            goto LABEL_6;
          }
          HIDWORD(v14) = 1;
          LastError = ((__int64 (__fastcall *)(HINTERNET, const unsigned __int16 *, __int128 *, ProxyResolver *))ProxyResolver::s_pfnWinhttpGetProxyForUrlEx)(
                        hInternet,
                        a3,
                        &v13,
                        this);
          v10 = LastError;
          if ( LastError != 997 )
          {
            v9 = 40698328;
            goto LABEL_7;
          }
          if ( WaitForSingleObjectEx(*((HANDLE *)this + 3), 0x1D4C0u, 0) )
          {
            LastError = GetLastError();
            v9 = 41419224;
            goto LABEL_6;
          }
          v10 = *((_DWORD *)this + 4);
          if ( v10 )
          {
            v11 = *((_DWORD *)this + 4);
            v9 = 41877976;
            goto LABEL_8;
          }
        }
        v10 = 0;
        goto LABEL_29;
      }
      LastError = GetLastError();
      v9 = 38339032;
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = 35455448;
  }
LABEL_6:
  v10 = LastError;
LABEL_7:
  v11 = LastError;
LABEL_8:
  CSPrintErrorLineFile(v9, v11);
LABEL_29:
  CSPrintErrorLineFile(0x28701D8u, v10);
  return v10;
}

```

## disassembly

```asm
0x18002cc88  mov     [rsp-18h+arg_8], rbx
0x18002cc8d  mov     [rsp-18h+arg_10], rsi
0x18002cc92  push    rbp
0x18002cc93  push    rdi
0x18002cc94  push    r14
0x18002cc96  mov     rbp, rsp
0x18002cc99  sub     rsp, 50h
0x18002cc9d  mov     [rbp+hInternet], 0
0x18002cca5  xorps   xmm0, xmm0
0x18002cca8  mov     r14, r8
0x18002ccab  mov     rsi, rdx
0x18002ccae  mov     rdi, rcx
0x18002ccb1  movups  [rbp+var_20], xmm0
0x18002ccb5  movups  [rbp+var_10], xmm0
0x18002ccb9  test    r9, r9
0x18002ccbc  jz      short loc_18002CCCB
0x18002ccbe  mov     dword ptr [rbp+var_20], 2
0x18002ccc5  mov     qword ptr [rbp+var_20+8], r9
0x18002ccc9  jmp     short loc_18002CCD9
0x18002cccb  mov     dword ptr [rbp+var_20], 1
0x18002ccd2  mov     dword ptr [rbp+var_20+4], 3
0x18002ccd9  xor     r9d, r9d; lpName
0x18002ccdc  xor     r8d, r8d; bInitialState
0x18002ccdf  xor     edx, edx; bManualReset
0x18002cce1  xor     ecx, ecx; lpEventAttributes
0x18002cce3  call    cs:__imp_CreateEventW
0x18002cce9  mov     [rdi+18h], rax
0x18002cced  test    rax, rax
0x18002ccf0  jnz     short loc_18002CD0C
0x18002ccf2  call    cs:__imp_GetLastError
0x18002ccf8  mov     ecx, 21D01D8h
0x18002ccfd  mov     ebx, eax
0x18002ccff  mov     edx, eax
0x18002cd01  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002cd07  jmp     loc_18002CE78
0x18002cd0c  mov     rax, cs:?s_pfnWinhttpCreateProxyResolver@ProxyResolver@@0P6AKPEAXPEAPEAX@ZEA; ulong (*ProxyResolver::s_pfnWinhttpCreateProxyResolver)(void *,void * *)
0x18002cd13  lea     rdx, [rbp+hInternet]
0x18002cd17  mov     rcx, rsi
0x18002cd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd1f  mov     ebx, eax
0x18002cd21  test    eax, eax
0x18002cd23  jz      short loc_18002CD2C
0x18002cd25  mov     ecx, 22701D8h
0x18002cd2a  jmp     short loc_18002CCFF
0x18002cd2c  mov     rcx, [rbp+hInternet]; hInternet
0x18002cd30  lea     rdx, ?GetProxyCallBack@ProxyResolver@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18002cd37  xor     r9d, r9d; dwReserved
0x18002cd3a  mov     r8d, 1200000h; dwNotificationFlags
0x18002cd40  call    cs:__imp_WinHttpSetStatusCallback
0x18002cd46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cd4a  jnz     short loc_18002CD59
0x18002cd4c  call    cs:__imp_GetLastError
0x18002cd52  mov     ecx, 23301D8h
0x18002cd57  jmp     short loc_18002CCFD
0x18002cd59  mov     rcx, [rbp+hInternet]
0x18002cd5d  lea     r8, [rbp+var_20]
0x18002cd61  mov     rax, cs:?s_pfnWinhttpGetProxyForUrlEx@ProxyResolver@@0P6AKPEAXPEBGPEAU_WINHTTP_AUTOPROXY_OPTIONS@@_K@ZEA; ulong (*ProxyResolver::s_pfnWinhttpGetProxyForUrlEx)(void *,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS *,unsigned __int64)
0x18002cd68  mov     r9, rdi
0x18002cd6b  mov     rdx, r14
0x18002cd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd73  mov     ebx, eax
0x18002cd75  cmp     eax, 3E5h
0x18002cd7a  jz      short loc_18002CD86
0x18002cd7c  mov     ecx, 23E01D8h
0x18002cd81  jmp     loc_18002CCFF
0x18002cd86  mov     rcx, [rdi+18h]; hHandle
0x18002cd8a  xor     r8d, r8d; bAlertable
0x18002cd8d  mov     edx, 1D4C0h; dwMilliseconds
0x18002cd92  call    cs:__imp_WaitForSingleObjectEx
0x18002cd98  test    eax, eax
0x18002cd9a  jz      short loc_18002CDAC
0x18002cd9c  call    cs:__imp_GetLastError
0x18002cda2  mov     ecx, 24901D8h
0x18002cda7  jmp     loc_18002CCFD
0x18002cdac  cmp     dword ptr [rdi+10h], 0
0x18002cdb0  jz      loc_18002CE76
0x18002cdb6  mov     rax, cs:?s_pfnWinhttpCreateProxyResolver@ProxyResolver@@0P6AKPEAXPEAPEAX@ZEA; ulong (*ProxyResolver::s_pfnWinhttpCreateProxyResolver)(void *,void * *)
0x18002cdbd  lea     rdx, [rbp+hInternet]
0x18002cdc1  mov     rcx, rsi
0x18002cdc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdc9  mov     ebx, eax
0x18002cdcb  test    eax, eax
0x18002cdcd  jz      short loc_18002CDD9
0x18002cdcf  mov     ecx, 25501D8h
0x18002cdd4  jmp     loc_18002CCFF
0x18002cdd9  mov     rcx, [rbp+hInternet]; hInternet
0x18002cddd  lea     rdx, ?GetProxyCallBack@ProxyResolver@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18002cde4  xor     r9d, r9d; dwReserved
0x18002cde7  mov     r8d, 1200000h; dwNotificationFlags
0x18002cded  call    cs:__imp_WinHttpSetStatusCallback
0x18002cdf3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cdf7  jnz     short loc_18002CE09
0x18002cdf9  call    cs:__imp_GetLastError
0x18002cdff  mov     ecx, 26101D8h
0x18002ce04  jmp     loc_18002CCFD
0x18002ce09  mov     rcx, [rbp+hInternet]
0x18002ce0d  lea     r8, [rbp+var_20]
0x18002ce11  mov     rax, cs:?s_pfnWinhttpGetProxyForUrlEx@ProxyResolver@@0P6AKPEAXPEBGPEAU_WINHTTP_AUTOPROXY_OPTIONS@@_K@ZEA; ulong (*ProxyResolver::s_pfnWinhttpGetProxyForUrlEx)(void *,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS *,unsigned __int64)
0x18002ce18  mov     r9, rdi
0x18002ce1b  mov     rdx, r14
0x18002ce1e  mov     dword ptr [rbp+var_10+0Ch], 1
0x18002ce25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce2a  mov     ebx, eax
0x18002ce2c  cmp     eax, 3E5h
0x18002ce31  jz      short loc_18002CE3D
0x18002ce33  mov     ecx, 26D01D8h
0x18002ce38  jmp     loc_18002CCFF
0x18002ce3d  mov     rcx, [rdi+18h]; hHandle
0x18002ce41  xor     r8d, r8d; bAlertable
0x18002ce44  mov     edx, 1D4C0h; dwMilliseconds
0x18002ce49  call    cs:__imp_WaitForSingleObjectEx
0x18002ce4f  test    eax, eax
0x18002ce51  jz      short loc_18002CE63
0x18002ce53  call    cs:__imp_GetLastError
0x18002ce59  mov     ecx, 27801D8h
0x18002ce5e  jmp     loc_18002CCFD
0x18002ce63  mov     ebx, [rdi+10h]
0x18002ce66  test    ebx, ebx
0x18002ce68  jz      short loc_18002CE76
0x18002ce6a  mov     edx, ebx
0x18002ce6c  mov     ecx, 27F01D8h
0x18002ce71  jmp     loc_18002CD01
0x18002ce76  xor     ebx, ebx
0x18002ce78  mov     edx, ebx
0x18002ce7a  mov     ecx, 28701D8h
0x18002ce7f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ce85  lea     r11, [rsp+50h+var_s0]
0x18002ce8a  mov     eax, ebx
0x18002ce8c  mov     rbx, [r11+28h]
0x18002ce90  mov     rsi, [r11+30h]
0x18002ce94  mov     rsp, r11
0x18002ce97  pop     r14
0x18002ce99  pop     rdi
0x18002ce9a  pop     rbp
0x18002ce9b  retn
```
