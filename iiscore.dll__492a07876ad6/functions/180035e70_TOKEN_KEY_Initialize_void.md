# TOKEN_KEY::Initialize(void)

- ea: `0x180035e70`
- end: `0x180035f08`
- name: `?Initialize@TOKEN_KEY@@SAJXZ`
- size: `152`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800147d0`

## callees

- `0x180035e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ea0`
- `CRYPTSP!CryptAcquireContextW` at `0x180035e90`
- `CRYPTSP!CryptAcquireContextW` at `0x180035e90`
- `iisutil!PuDbgPrint` at `0x180035eef`
- `iisutil!PuDbgPrint` at `0x180035eef`

## string_xrefs

- `0x180035ee8`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180035ed6`: `TOKEN_KEY::Initialize`

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
0x180035e70  push    rbx
0x180035e72  sub     rsp, 30h
0x180035e76  mov     r9d, 18h; dwProvType
0x180035e7c  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x180035e84  xor     r8d, r8d; szProvider
0x180035e87  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x180035e8e  xor     edx, edx; szContainer
0x180035e90  call    cs:__imp_CryptAcquireContextW
0x180035e97  nop     dword ptr [rax+rax+00h]
0x180035e9c  test    eax, eax
0x180035e9e  jnz     short loc_180035EFF
0x180035ea0  call    cs:__imp_GetLastError
0x180035ea7  nop     dword ptr [rax+rax+00h]
0x180035eac  mov     ebx, eax
0x180035eae  test    eax, eax
0x180035eb0  jle     short loc_180035EBB
0x180035eb2  movzx   ebx, ax
0x180035eb5  or      ebx, 80070000h
0x180035ebb  test    byte ptr cs:g_dwDebugFlags, 3
0x180035ec2  jz      short loc_180035EFB
0x180035ec4  mov     rcx, cs:g_pDebug
0x180035ecb  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x180035ed2  mov     [rsp+38h+var_10], ebx
0x180035ed6  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x180035edd  mov     r8d, 3D6h
0x180035ee3  mov     qword ptr [rsp+38h+dwFlags], rax
0x180035ee8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180035eef  call    cs:__imp_PuDbgPrint
0x180035ef6  nop     dword ptr [rax+rax+00h]
0x180035efb  mov     eax, ebx
0x180035efd  jmp     short loc_180035F01
0x180035eff  xor     eax, eax
0x180035f01  add     rsp, 30h
0x180035f05  pop     rbx
0x180035f06  retn
```
