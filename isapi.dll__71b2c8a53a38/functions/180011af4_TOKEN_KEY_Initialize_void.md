# TOKEN_KEY::Initialize(void)

- ea: `0x180011af4`
- end: `0x180011b79`
- name: `?Initialize@TOKEN_KEY@@SAJXZ`
- size: `133`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e1bc`

## callees

- `0x180011af4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b1e`
- `iisutil!PuDbgPrint` at `0x180011b67`
- `iisutil!PuDbgPrint` at `0x180011b67`
- `CRYPTSP!CryptAcquireContextW` at `0x180011b14`
- `CRYPTSP!CryptAcquireContextW` at `0x180011b14`

## string_xrefs

- `0x180011b60`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180011b4e`: `TOKEN_KEY::Initialize`

## pseudocode

```c
__int64 TOKEN_KEY::Initialize(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx

  if ( CryptAcquireContextW(&TOKEN_KEY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
    return 0;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
      982,
      "TOKEN_KEY::Initialize",
      "CryptAcquireContext() failed. hr = 0x%x\n",
      v1);
  return v1;
}

```

## disassembly

```asm
0x180011af4  push    rbx
0x180011af6  sub     rsp, 30h
0x180011afa  mov     r9d, 18h; dwProvType
0x180011b00  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180011b08  xor     r8d, r8d; szProvider
0x180011b0b  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x180011b12  xor     edx, edx; szContainer
0x180011b14  call    cs:__imp_CryptAcquireContextW
0x180011b1a  test    eax, eax
0x180011b1c  jnz     short loc_180011B71
0x180011b1e  call    cs:__imp_GetLastError
0x180011b24  mov     ebx, eax
0x180011b26  test    eax, eax
0x180011b28  jle     short loc_180011B33
0x180011b2a  movzx   ebx, ax
0x180011b2d  or      ebx, 80070000h
0x180011b33  test    byte ptr cs:g_dwDebugFlags, 3
0x180011b3a  jz      short loc_180011B6D
0x180011b3c  mov     rcx, cs:g_pDebug
0x180011b43  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x180011b4a  mov     [rsp+38h+var_10], ebx
0x180011b4e  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x180011b55  mov     r8d, 3D6h
0x180011b5b  mov     qword ptr [rsp+38h+dwFlags], rax
0x180011b60  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180011b67  call    cs:__imp_PuDbgPrint
0x180011b6d  mov     eax, ebx
0x180011b6f  jmp     short loc_180011B73
0x180011b71  xor     eax, eax
0x180011b73  add     rsp, 30h
0x180011b77  pop     rbx
0x180011b78  retn
```
