# Input_InstallLayout(HWND__ *,ushort const *,ulong)

- ea: `0x180012dc8`
- end: `0x180012f08`
- name: `?Input_InstallLayout@@YAHPEAUHWND__@@PEBGK@Z`
- size: `320`
- prototype: `__int64 __fastcall(HWND hWnd, LPCWSTR lpLocaleName, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ad4c`
- `0x18000ba98`
- `0x18000c454`
- `0x18001f70c`
- `0x180020a9c`
- `0x1800222e0`

## callees

- `0x180012dc8`
- `0x180012f10`
- `0x180027f5c`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012e52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ed0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012e61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012e61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ede`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ede`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012e3b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012e7b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012eaa`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012e3b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012e7b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012eaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012e1c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012e1c`

## pseudocode

```c
__int64 __fastcall Input_InstallLayout(HWND hWnd, LPCWSTR lpLocaleName, unsigned int a3)
{
  unsigned int v3; // edi
  const WCHAR *v7; // r12
  int LocaleInfo; // eax
  __int64 v9; // r14
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  unsigned __int16 *v12; // rbx
  HANDLE v13; // rax
  WCHAR LCData[88]; // [rsp+30h] [rbp-F8h] BYREF

  v3 = 0;
  if ( g_pfnInstallLayoutOrTip )
  {
    v7 = L"es-ES";
    if ( CompareStringOrdinal(lpLocaleName, -1, L"es-ES-TS", -1, 1) )
      v7 = lpLocaleName;
    LocaleInfo = GetLocaleInfoEx(v7, 0x5Eu, 0, 0);
    v9 = LocaleInfo;
    if ( LocaleInfo )
    {
      ProcessHeap = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * v9);
      v12 = v11;
      if ( v11 )
      {
        if ( GetLocaleInfoEx(v7, 0x5Eu, v11, v9) )
        {
          v3 = Input_InstallLayoutOrTip(v12, a3);
          if ( !v3 && hWnd && GetLocaleInfoEx(lpLocaleName, 2u, LCData, 85) )
            ShowMsg(hWnd, 0x53u, 0, 0x30u, LCData);
        }
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180012dc8  push    rbx
0x180012dca  push    rbp
0x180012dcb  push    rsi
0x180012dcc  push    rdi
0x180012dcd  push    r12
0x180012dcf  push    r14
0x180012dd1  push    r15
0x180012dd3  sub     rsp, 0F0h
0x180012dda  mov     rax, cs:__security_cookie
0x180012de1  xor     rax, rsp
0x180012de4  mov     [rsp+128h+var_48], rax
0x180012dec  xor     edi, edi
0x180012dee  mov     r15d, r8d
0x180012df1  cmp     cs:?g_pfnInstallLayoutOrTip@@3P6AHPEBGK@ZEA, rdi; int (*g_pfnInstallLayoutOrTip)(ushort const *,ulong)
0x180012df8  mov     rbp, rdx
0x180012dfb  mov     rsi, rcx
0x180012dfe  jz      loc_180012EE4
0x180012e04  or      edx, 0FFFFFFFFh; cchCount1
0x180012e07  mov     [rsp+128h+bIgnoreCase], 1; bIgnoreCase
0x180012e0f  mov     r9d, edx; cchCount2
0x180012e12  lea     r8, aEsEsTs; "es-ES-TS"
0x180012e19  mov     rcx, rbp; lpString1
0x180012e1c  call    cs:__imp_CompareStringOrdinal
0x180012e22  test    eax, eax
0x180012e24  lea     r12, aEsEs; "es-ES"
0x180012e2b  lea     edx, [rdi+5Eh]; LCType
0x180012e2e  cmovnz  r12, rbp
0x180012e32  xor     r9d, r9d; cchData
0x180012e35  mov     rcx, r12; lpLocaleName
0x180012e38  xor     r8d, r8d; lpLCData
0x180012e3b  call    cs:__imp_GetLocaleInfoEx
0x180012e41  movsxd  r14, eax
0x180012e44  test    eax, eax
0x180012e46  jz      loc_180012EE4
0x180012e4c  mov     rbx, r14
0x180012e4f  add     rbx, rbx
0x180012e52  call    cs:__imp_GetProcessHeap
0x180012e58  mov     r8, rbx; dwBytes
0x180012e5b  lea     edx, [rdi+8]; dwFlags
0x180012e5e  mov     rcx, rax; hHeap
0x180012e61  call    cs:__imp_HeapAlloc
0x180012e67  mov     rbx, rax
0x180012e6a  test    rax, rax
0x180012e6d  jz      short loc_180012EE4
0x180012e6f  mov     r9d, r14d; cchData
0x180012e72  lea     edx, [rdi+5Eh]; LCType
0x180012e75  mov     r8, rax; lpLCData
0x180012e78  mov     rcx, r12; lpLocaleName
0x180012e7b  call    cs:__imp_GetLocaleInfoEx
0x180012e81  test    eax, eax
0x180012e83  jz      short loc_180012ED0
0x180012e85  mov     edx, r15d; unsigned int
0x180012e88  mov     rcx, rbx; unsigned __int16 *
0x180012e8b  call    ?Input_InstallLayoutOrTip@@YAHPEBGK@Z; Input_InstallLayoutOrTip(ushort const *,ulong)
0x180012e90  mov     edi, eax
0x180012e92  test    eax, eax
0x180012e94  jnz     short loc_180012ED0
0x180012e96  test    rsi, rsi
0x180012e99  jz      short loc_180012ED0
0x180012e9b  lea     r9d, [rax+55h]; cchData
0x180012e9f  mov     rcx, rbp; lpLocaleName
0x180012ea2  lea     r8, [rsp+128h+LCData]; lpLCData
0x180012ea7  lea     edx, [rax+2]; LCType
0x180012eaa  call    cs:__imp_GetLocaleInfoEx
0x180012eb0  test    eax, eax
0x180012eb2  jz      short loc_180012ED0
0x180012eb4  lea     rax, [rsp+128h+LCData]
0x180012eb9  xor     r8d, r8d; UINT
0x180012ebc  lea     r9d, [rdi+30h]; uType
0x180012ec0  mov     qword ptr [rsp+128h+bIgnoreCase], rax; unsigned __int16 *
0x180012ec5  lea     edx, [rdi+53h]; uID
0x180012ec8  mov     rcx, rsi; hWnd
0x180012ecb  call    ?ShowMsg@@YAHPEAUHWND__@@IIIPEAG@Z; ShowMsg(HWND__ *,uint,uint,uint,ushort *)
0x180012ed0  call    cs:__imp_GetProcessHeap
0x180012ed6  mov     r8, rbx; lpMem
0x180012ed9  xor     edx, edx; dwFlags
0x180012edb  mov     rcx, rax; hHeap
0x180012ede  call    cs:__imp_HeapFree
0x180012ee4  mov     eax, edi
0x180012ee6  mov     rcx, [rsp+128h+var_48]
0x180012eee  xor     rcx, rsp; StackCookie
0x180012ef1  call    __security_check_cookie
0x180012ef6  add     rsp, 0F0h
0x180012efd  pop     r15
0x180012eff  pop     r14
0x180012f01  pop     r12
0x180012f03  pop     rdi
0x180012f04  pop     rsi
0x180012f05  pop     rbp
0x180012f06  pop     rbx
0x180012f07  retn
```
