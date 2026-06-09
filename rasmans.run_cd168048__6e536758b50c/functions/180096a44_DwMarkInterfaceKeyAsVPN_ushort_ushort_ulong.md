# DwMarkInterfaceKeyAsVPN(ushort *,ushort *,ulong)

- ea: `0x180096a44`
- end: `0x180096c55`
- name: `?DwMarkInterfaceKeyAsVPN@@YAKPEAG0K@Z`
- size: `529`
- prototype: `unsigned int __fastcall(STRSAFE_LPCWSTR pszSrc, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800950f8`

## callees

- `0x180056178`
- `0x180096a44`
- `0x180097e18`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180096b76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180096b76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096baa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096baa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096bf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096bf5`

## string_xrefs

- `0x180096ace`: `DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error`
- `0x180096aec`: `DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error`
- `0x180096c1d`: `DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key`
- `0x180096c03`: `DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key`

## pseudocode

```c
__int64 __fastcall DwMarkInterfaceKeyAsVPN(STRSAFE_LPCWSTR pszSrc, unsigned __int16 *a2, unsigned int a3)
{
  wchar_t *v5; // r9
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  wchar_t *v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-238h] BYREF

  *(_DWORD *)Data = 1;
  hKey = 0;
  v5 = pszDest;
  v7 = 2147483646;
  v8 = a2;
  v9 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*v8 )
      break;
    *v5++ = *v8++;
    --v7;
    --v9;
  }
  while ( v9 );
  v10 = v5 - 1;
  v11 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v10 = v5;
  *v10 = 0;
  if ( v9 )
  {
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( pszSrc[v15] );
    do
      ++v14;
    while ( a2[v14] );
    v11 = StringCchCatW(pszDest, v15 + v14 + 1, pszSrc);
    if ( v11 )
    {
      TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Call to StringCchCatW returned error");
      v12 = qword_18010FC00;
      if ( qword_18010FC00 )
      {
        v13 = L"DwMarkInterfaceKeyAsVPN : Call to StringCchCatW returned error";
        goto LABEL_23;
      }
    }
    else
    {
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20006u, &hKey);
      if ( v11 )
      {
        TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key");
        v12 = qword_18010FC00;
        if ( qword_18010FC00 )
        {
          v13 = L"DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key";
          goto LABEL_23;
        }
      }
      else
      {
        v11 = RegSetValueExW(hKey, L"VPNInterface", 0, 4u, Data, 4u);
        if ( v11 )
        {
          TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Failed to set the flag VPNInterface to 1");
          if ( qword_18010FC00 )
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRegHelpTemplateFunc)(
              gRegHelpEtwContext,
              qword_18010FC00,
              L"DwMarkInterfaceKeyAsVPN : Failed to set the flag VPNInterface to 1");
        }
        RegCloseKey(hKey);
      }
    }
  }
  else
  {
    TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error");
    v12 = qword_18010FC00;
    if ( qword_18010FC00 )
    {
      v13 = L"DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error";
LABEL_23:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRegHelpTemplateFunc)(gRegHelpEtwContext, v12, v13);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180096a44  push    rbx
0x180096a46  push    rsi
0x180096a47  push    rdi
0x180096a48  sub     rsp, 260h
0x180096a4f  mov     rax, cs:__security_cookie
0x180096a56  xor     rax, rsp
0x180096a59  mov     [rsp+278h+var_28], rax
0x180096a61  xor     esi, esi
0x180096a63  mov     dword ptr [rsp+278h+Data], 1
0x180096a6b  mov     edi, r8d
0x180096a6e  mov     [rsp+278h+hKey], rsi
0x180096a73  mov     r10, rcx
0x180096a76  lea     r9, [rsp+278h+pszDest]
0x180096a7b  mov     r11, rdx
0x180096a7e  mov     eax, 7FFFFFFEh
0x180096a83  mov     rcx, rdx
0x180096a86  mov     r8d, 104h
0x180096a8c  test    rax, rax
0x180096a8f  jz      short loc_180096AAE
0x180096a91  movzx   edx, word ptr [rcx]
0x180096a94  test    dx, dx
0x180096a97  jz      short loc_180096AAE
0x180096a99  mov     [r9], dx
0x180096a9d  add     rcx, 2
0x180096aa1  add     r9, 2
0x180096aa5  dec     rax
0x180096aa8  sub     r8, 1
0x180096aac  jnz     short loc_180096A8C
0x180096aae  mov     rax, r8
0x180096ab1  lea     rdx, [r9-2]
0x180096ab5  neg     rax
0x180096ab8  sbb     ebx, ebx
0x180096aba  not     ebx
0x180096abc  and     ebx, 8007007Ah
0x180096ac2  test    r8, r8
0x180096ac5  cmovnz  rdx, r9
0x180096ac9  mov     [rdx], si
0x180096acc  jnz     short loc_180096AF8
0x180096ace  lea     rdx, aDwmarkinterfac_5; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x180096ad5  mov     ecx, edi; unsigned int
0x180096ad7  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180096adc  mov     rdx, cs:qword_18010FC00
0x180096ae3  test    rdx, rdx
0x180096ae6  jz      loc_180096C37
0x180096aec  lea     r8, aDwmarkinterfac_7; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x180096af3  jmp     loc_180096C24
0x180096af8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180096afc  mov     rcx, rax
0x180096aff  inc     rcx
0x180096b02  cmp     [r10+rcx*2], si
0x180096b07  jnz     short loc_180096AFF
0x180096b09  inc     rax
0x180096b0c  cmp     [r11+rax*2], si
0x180096b11  jnz     short loc_180096B09
0x180096b13  lea     rdx, [rax+1]
0x180096b17  mov     r8, r10; pszSrc
0x180096b1a  add     rdx, rcx; cchDest
0x180096b1d  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180096b22  call    StringCchCatW
0x180096b27  mov     ebx, eax
0x180096b29  test    eax, eax
0x180096b2b  jz      short loc_180096B57
0x180096b2d  lea     rdx, aDwmarkinterfac_1; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x180096b34  mov     ecx, edi; unsigned int
0x180096b36  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180096b3b  mov     rdx, cs:qword_18010FC00
0x180096b42  test    rdx, rdx
0x180096b45  jz      loc_180096C37
0x180096b4b  lea     r8, aDwmarkinterfac; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x180096b52  jmp     loc_180096C24
0x180096b57  lea     rax, [rsp+278h+hKey]
0x180096b5c  mov     r9d, 20006h; samDesired
0x180096b62  xor     r8d, r8d; ulOptions
0x180096b65  mov     [rsp+278h+phkResult], rax; phkResult
0x180096b6a  lea     rdx, [rsp+278h+pszDest]; lpSubKey
0x180096b6f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180096b76  call    cs:__imp_RegOpenKeyExW
0x180096b7d  nop     dword ptr [rax+rax+00h]
0x180096b82  mov     ebx, eax
0x180096b84  test    eax, eax
0x180096b86  jnz     short loc_180096C03
0x180096b88  mov     rcx, [rsp+278h+hKey]; hKey
0x180096b8d  lea     r9d, [rax+4]; dwType
0x180096b91  lea     rax, [rsp+278h+Data]
0x180096b96  mov     [rsp+278h+cbData], r9d; cbData
0x180096b9b  xor     r8d, r8d; Reserved
0x180096b9e  mov     [rsp+278h+phkResult], rax; lpData
0x180096ba3  lea     rdx, aVpninterface; "VPNInterface"
0x180096baa  call    cs:__imp_RegSetValueExW
0x180096bb1  nop     dword ptr [rax+rax+00h]
0x180096bb6  mov     ebx, eax
0x180096bb8  test    eax, eax
0x180096bba  jz      short loc_180096BF0
0x180096bbc  lea     rdx, aDwmarkinterfac_8; "DwMarkInterfaceKeyAsVPN : Failed to set"...
0x180096bc3  mov     ecx, edi; unsigned int
0x180096bc5  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180096bca  mov     rdx, cs:qword_18010FC00
0x180096bd1  test    rdx, rdx
0x180096bd4  jz      short loc_180096BF0
0x180096bd6  mov     rcx, cs:gRegHelpEtwContext
0x180096bdd  lea     r8, aDwmarkinterfac_3; "DwMarkInterfaceKeyAsVPN : Failed to set"...
0x180096be4  mov     rax, cs:gRegHelpTemplateFunc
0x180096beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096bf0  mov     rcx, [rsp+278h+hKey]; hKey
0x180096bf5  call    cs:__imp_RegCloseKey
0x180096bfc  nop     dword ptr [rax+rax+00h]
0x180096c01  jmp     short loc_180096C37
0x180096c03  lea     rdx, aDwmarkinterfac_6; "DwMarkInterfaceKeyAsVPN : Failed to Ope"...
0x180096c0a  mov     ecx, edi; unsigned int
0x180096c0c  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x180096c11  mov     rdx, cs:qword_18010FC00
0x180096c18  test    rdx, rdx
0x180096c1b  jz      short loc_180096C37
0x180096c1d  lea     r8, aDwmarkinterfac_2; "DwMarkInterfaceKeyAsVPN : Failed to Ope"...
0x180096c24  mov     rcx, cs:gRegHelpEtwContext
0x180096c2b  mov     rax, cs:gRegHelpTemplateFunc
0x180096c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c37  mov     eax, ebx
0x180096c39  mov     rcx, [rsp+278h+var_28]
0x180096c41  xor     rcx, rsp; StackCookie
0x180096c44  call    __security_check_cookie
0x180096c49  add     rsp, 260h
0x180096c50  pop     rdi
0x180096c51  pop     rsi
0x180096c52  pop     rbx
0x180096c53  retn
```
