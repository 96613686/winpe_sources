# TOKEN_KEY::Initialize(void)

- ea: `0x180032d10`
- end: `0x180032d95`
- name: `?Initialize@TOKEN_KEY@@SAJXZ`
- size: `133`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013690`

## callees

- `0x180032d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d3a`
- `CRYPTSP!CryptAcquireContextW` at `0x180032d30`
- `CRYPTSP!CryptAcquireContextW` at `0x180032d30`
- `iisutil!PuDbgPrint` at `0x180032d83`
- `iisutil!PuDbgPrint` at `0x180032d83`

## string_xrefs

- `0x180032d7c`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180032d6a`: `TOKEN_KEY::Initialize`

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
0x180032d10  push    rbx
0x180032d12  sub     rsp, 30h
0x180032d16  mov     r9d, 18h; dwProvType
0x180032d1c  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180032d24  xor     r8d, r8d; szProvider
0x180032d27  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x180032d2e  xor     edx, edx; szContainer
0x180032d30  call    cs:__imp_CryptAcquireContextW
0x180032d36  test    eax, eax
0x180032d38  jnz     short loc_180032D8D
0x180032d3a  call    cs:__imp_GetLastError
0x180032d40  mov     ebx, eax
0x180032d42  test    eax, eax
0x180032d44  jle     short loc_180032D4F
0x180032d46  movzx   ebx, ax
0x180032d49  or      ebx, 80070000h
0x180032d4f  test    byte ptr cs:g_dwDebugFlags, 3
0x180032d56  jz      short loc_180032D89
0x180032d58  mov     rcx, cs:g_pDebug
0x180032d5f  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x180032d66  mov     [rsp+38h+var_10], ebx
0x180032d6a  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x180032d71  mov     r8d, 3D6h
0x180032d77  mov     qword ptr [rsp+38h+dwFlags], rax
0x180032d7c  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180032d83  call    cs:__imp_PuDbgPrint
0x180032d89  mov     eax, ebx
0x180032d8b  jmp     short loc_180032D8F
0x180032d8d  xor     eax, eax
0x180032d8f  add     rsp, 30h
0x180032d93  pop     rbx
0x180032d94  retn
```
