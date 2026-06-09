# GetIdentityFromSmartcard

- ea: `0x180005b90`
- end: `0x180005cc9`
- name: `GetIdentityFromSmartcard`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002250`

## callees

- `0x180005b90`
- `0x180007288`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180005be2`
- `KERNEL32!LocalAlloc` at `0x180005be2`
- `KERNEL32!GetLastError` at `0x180005bf0`
- `KERNEL32!GetLastError` at `0x180005bf0`
- `KERNEL32!LocalFree` at `0x180005cae`
- `KERNEL32!LocalFree` at `0x180005cae`
- `RASAPI32!RasGetCustomAuthDataW` at `0x180005bc9`
- `RASAPI32!RasGetCustomAuthDataW` at `0x180005c2f`
- `RASAPI32!RasGetCustomAuthDataW` at `0x180005bc9`
- `RASAPI32!RasGetCustomAuthDataW` at `0x180005c2f`
- `rtutils!TracePrintfExA` at `0x180005c14`
- `rtutils!TracePrintfExA` at `0x180005ca0`
- `rtutils!TracePrintfExA` at `0x180005c14`
- `rtutils!TracePrintfExA` at `0x180005ca0`

## string_xrefs

- `0x180005c0a`: `Failed to allocate memory to read configuration blob: %d.`

## pseudocode

```c
__int64 __fastcall GetIdentityFromSmartcard(__int64 a1, const WCHAR *a2, unsigned int a3, __int64 a4, SIZE_T uBytes)
{
  BYTE *v8; // rdi
  DWORD CustomAuthDataW; // ebx
  BYTE *v10; // rax
  DWORD LastError; // eax
  DWORD EapCredentialsInputType; // eax
  int v14; // [rsp+60h] [rbp+8h] BYREF
  int v15; // [rsp+64h] [rbp+Ch]

  v15 = HIDWORD(a1);
  v14 = 0;
  LODWORD(uBytes) = 0;
  v8 = 0;
  CustomAuthDataW = RasGetCustomAuthDataW(0, a2, 0, (DWORD *)&uBytes);
  if ( CustomAuthDataW == 603 )
  {
    v10 = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
    v8 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      CustomAuthDataW = LastError;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to allocate memory to read configuration blob: %d.", LastError);
      return CustomAuthDataW;
    }
    CustomAuthDataW = RasGetCustomAuthDataW(0, a2, v10, (DWORD *)&uBytes);
  }
  if ( CustomAuthDataW )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasGetEapUserData failed with error: %d.", CustomAuthDataW);
  }
  else
  {
    EapCredentialsInputType = GetEapCredentialsInputType(a3, v8, (unsigned int)uBytes, &v14, 0, 257, a4);
    CustomAuthDataW = EapCredentialsInputType;
    if ( EapCredentialsInputType && g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "GetEapCredentialsInputType failed with error: %d.", EapCredentialsInputType);
  }
  if ( v8 )
    LocalFree(v8);
  return CustomAuthDataW;
}

```

## disassembly

```asm
0x180005b90  mov     rax, rsp
0x180005b93  mov     [rax+10h], rbx
0x180005b97  mov     [rax+18h], rbp
0x180005b9b  mov     [rax+8], rcx
0x180005b9f  push    rsi
0x180005ba0  push    rdi
0x180005ba1  push    r14
0x180005ba3  sub     rsp, 40h
0x180005ba7  mov     rbp, r9
0x180005baa  mov     dword ptr [rax+8], 0
0x180005bb1  mov     r14d, r8d
0x180005bb4  mov     dword ptr [rax+28h], 0
0x180005bbb  lea     r9, [rax+28h]; pdwSizeofCustomAuthData
0x180005bbf  xor     r8d, r8d; pbCustomAuthData
0x180005bc2  xor     ecx, ecx; pszPhonebook
0x180005bc4  mov     rsi, rdx
0x180005bc7  xor     edi, edi
0x180005bc9  call    cs:__imp_RasGetCustomAuthDataW
0x180005bcf  mov     ebx, eax
0x180005bd1  cmp     eax, 25Bh
0x180005bd6  jnz     short loc_180005C37
0x180005bd8  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x180005bdf  lea     ecx, [rdi+40h]; uFlags
0x180005be2  call    cs:__imp_LocalAlloc
0x180005be8  mov     rdi, rax
0x180005beb  test    rax, rax
0x180005bee  jnz     short loc_180005C1F
0x180005bf0  call    cs:__imp_GetLastError
0x180005bf6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005bfc  mov     ebx, eax
0x180005bfe  cmp     ecx, 0FFFFFFFFh
0x180005c01  jz      loc_180005CB4
0x180005c07  mov     r9d, eax
0x180005c0a  lea     r8, aFailedToAlloca; "Failed to allocate memory to read confi"...
0x180005c11  lea     edx, [rdi+0Ch]; dwFlags
0x180005c14  call    cs:__imp_TracePrintfExA
0x180005c1a  jmp     loc_180005CB4
0x180005c1f  lea     r9, [rsp+58h+uBytes]; pdwSizeofCustomAuthData
0x180005c27  mov     r8, rax; pbCustomAuthData
0x180005c2a  mov     rdx, rsi; pszEntry
0x180005c2d  xor     ecx, ecx; pszPhonebook
0x180005c2f  call    cs:__imp_RasGetCustomAuthDataW
0x180005c35  mov     ebx, eax
0x180005c37  test    ebx, ebx
0x180005c39  jz      short loc_180005C52
0x180005c3b  mov     ecx, cs:g_dwTraceId
0x180005c41  cmp     ecx, 0FFFFFFFFh
0x180005c44  jz      short loc_180005CA6
0x180005c46  mov     r9d, ebx
0x180005c49  lea     r8, aRasgeteapuserd_0; "RasGetEapUserData failed with error: %d"...
0x180005c50  jmp     short loc_180005C9B
0x180005c52  mov     r8d, dword ptr [rsp+58h+uBytes]
0x180005c5a  lea     r9, [rsp+58h+arg_0]
0x180005c5f  mov     [rsp+58h+var_28], rbp
0x180005c64  mov     rdx, rdi
0x180005c67  mov     [rsp+58h+var_30], 101h
0x180005c6f  mov     ecx, r14d
0x180005c72  mov     [rsp+58h+var_38], 0
0x180005c7b  call    GetEapCredentialsInputType
0x180005c80  mov     ebx, eax
0x180005c82  test    eax, eax
0x180005c84  jz      short loc_180005CA6
0x180005c86  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005c8c  cmp     ecx, 0FFFFFFFFh
0x180005c8f  jz      short loc_180005CA6
0x180005c91  mov     r9d, eax
0x180005c94  lea     r8, aGeteapcredenti; "GetEapCredentialsInputType failed with "...
0x180005c9b  mov     edx, 0Ch; dwFlags
0x180005ca0  call    cs:__imp_TracePrintfExA
0x180005ca6  test    rdi, rdi
0x180005ca9  jz      short loc_180005CB4
0x180005cab  mov     rcx, rdi; hMem
0x180005cae  call    cs:__imp_LocalFree
0x180005cb4  mov     rbp, [rsp+58h+arg_10]
0x180005cb9  mov     eax, ebx
0x180005cbb  mov     rbx, [rsp+58h+arg_8]
0x180005cc0  add     rsp, 40h
0x180005cc4  pop     r14
0x180005cc6  pop     rdi
0x180005cc7  pop     rsi
0x180005cc8  retn
```
