# AiaUrlRedirectCallBack(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x180025c40`
- end: `0x180025ced`
- name: `?AiaUrlRedirectCallBack@@YAXPEAX_KK0K@Z`
- size: `173`
- prototype: `void __fastcall(HINTERNET hInternet, HINTERNET *dwContext, DWORD dwInternetStatus, const WCHAR *lpvStatusInformation)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180025c40`
- `0x18002656a`

## import_xrefs

- `CRYPT32!I_CertDiagControl` at `0x180025cd6`
- `CRYPT32!I_CertDiagControl` at `0x180025cd6`
- `WINHTTP!WinHttpCrackUrl` at `0x180025c7d`
- `WINHTTP!WinHttpCrackUrl` at `0x180025c7d`
- `WINHTTP!WinHttpCloseHandle` at `0x180025c96`
- `WINHTTP!WinHttpCloseHandle` at `0x180025c96`

## string_xrefs

- `0x180025ca6`: `HttpToHttpsRedirectDuringAia_CancelingWinHttpReceiveResponse`

## pseudocode

```c
void __fastcall AiaUrlRedirectCallBack(
        HINTERNET hInternet,
        HINTERNET *dwContext,
        DWORD dwInternetStatus,
        const WCHAR *lpvStatusInformation)
{
  _QWORD v6[2]; // [rsp+20h] [rbp-A8h] BYREF
  __int128 v7; // [rsp+30h] [rbp-98h]
  __int128 v8; // [rsp+40h] [rbp-88h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-78h] BYREF

  memset_0(&UrlComponents.dwStructSize + 1, 0, 0x64u);
  if ( lpvStatusInformation )
  {
    UrlComponents.dwStructSize = 104;
    if ( WinHttpCrackUrl(lpvStatusInformation, 0, 0, &UrlComponents) )
    {
      if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
      {
        if ( dwContext )
        {
          WinHttpCloseHandle(*dwContext);
          *dwContext = 0;
          v6[1] = 50;
          v6[0] = L"HttpToHttpsRedirectDuringAia_CancelingWinHttpReceiveResponse";
          v7 = 0;
          v8 = 0;
          I_CertDiagControl(11, v6, 0);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180025c40  mov     [rsp+arg_0], rbx
0x180025c45  push    rdi
0x180025c46  sub     rsp, 0C0h
0x180025c4d  mov     rbx, rdx
0x180025c50  lea     rcx, [rsp+0C8h+UrlComponents+4]; void *
0x180025c55  xor     edx, edx; Val
0x180025c57  mov     rdi, r9
0x180025c5a  lea     r8d, [rdx+64h]; Size
0x180025c5e  call    memset_0
0x180025c63  test    rdi, rdi
0x180025c66  jz      short loc_180025CDC
0x180025c68  lea     r9, [rsp+0C8h+UrlComponents]; lpUrlComponents
0x180025c6d  mov     [rsp+0C8h+UrlComponents.dwStructSize], 68h ; 'h'
0x180025c75  xor     r8d, r8d; dwFlags
0x180025c78  xor     edx, edx; dwUrlLength
0x180025c7a  mov     rcx, rdi; pwszUrl
0x180025c7d  call    cs:__imp_WinHttpCrackUrl
0x180025c83  test    eax, eax
0x180025c85  jz      short loc_180025CDC
0x180025c87  cmp     [rsp+0C8h+UrlComponents.nScheme], 2
0x180025c8c  jnz     short loc_180025CDC
0x180025c8e  test    rbx, rbx
0x180025c91  jz      short loc_180025CDC
0x180025c93  mov     rcx, [rbx]; hInternet
0x180025c96  call    cs:__imp_WinHttpCloseHandle
0x180025c9c  xor     r8d, r8d
0x180025c9f  mov     qword ptr [rbx], 0
0x180025ca6  lea     rax, aHttptohttpsred; "HttpToHttpsRedirectDuringAia_CancelingW"...
0x180025cad  mov     [rsp+0C8h+var_A0], 32h ; '2'
0x180025cb6  xorps   xmm0, xmm0
0x180025cb9  mov     [rsp+0C8h+var_A8], rax
0x180025cbe  xorps   xmm1, xmm1
0x180025cc1  lea     rdx, [rsp+0C8h+var_A8]
0x180025cc6  lea     ecx, [r8+0Bh]
0x180025cca  movdqu  [rsp+0C8h+var_98], xmm0
0x180025cd0  movdqu  [rsp+0C8h+var_88], xmm1
0x180025cd6  call    cs:__imp_I_CertDiagControl
0x180025cdc  mov     rbx, [rsp+0C8h+arg_0]
0x180025ce4  add     rsp, 0C0h
0x180025ceb  pop     rdi
0x180025cec  retn
```
