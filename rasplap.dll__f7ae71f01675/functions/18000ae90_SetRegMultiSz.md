# SetRegMultiSz

- ea: `0x18000ae90`
- end: `0x18000afab`
- name: `SetRegMultiSz`
- size: `283`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a4f0`

## callees

- `0x180008c5c`
- `0x18000ae90`

## import_xrefs

- `KERNEL32!RegSetValueExW` at `0x18000af8b`
- `KERNEL32!RegSetValueExW` at `0x18000af8b`
- `KERNEL32!lstrlenW` at `0x18000aeb4`
- `KERNEL32!lstrlenW` at `0x18000aeb4`
- `KERNEL32!GlobalFree` at `0x18000af96`
- `KERNEL32!GlobalFree` at `0x18000af96`
- `KERNEL32!GlobalAlloc` at `0x18000aed9`
- `KERNEL32!GlobalAlloc` at `0x18000aed9`

## pseudocode

```c
__int64 __fastcall SetRegMultiSz(HKEY hKey, LPCWSTR lpValueName, __int64 *a3)
{
  __int64 v3; // rbx
  int v7; // edi
  int v8; // eax
  unsigned int v9; // eax
  unsigned __int64 v10; // rsi
  wchar_t *v11; // rbx
  size_t v13; // rax
  __int64 v14; // rdi
  wchar_t *v15; // rcx
  HRESULT v16; // eax
  unsigned int v17; // edi
  size_t pcchRemaining[9]; // [rsp+30h] [rbp-48h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+90h] [rbp+18h] BYREF

  v3 = *a3;
  v7 = 2;
  while ( v3 )
  {
    v8 = lstrlenW(*(LPCWSTR *)(v3 + 16));
    v3 = *(_QWORD *)(v3 + 8);
    v7 += 2 * v8 + 2;
  }
  v9 = 4;
  if ( v7 != 2 )
    v9 = v7;
  v10 = v9;
  v11 = (wchar_t *)GlobalAlloc(0x40u, v9);
  if ( !v11 )
    return 8;
  v13 = v10 >> 1;
  pcchRemaining[0] = v10 >> 1;
  if ( (_DWORD)v10 == 4 )
  {
    *(_DWORD *)v11 = 0;
  }
  else
  {
    v14 = *a3;
    v15 = v11;
    ppszDestEnd = v11;
    while ( v14 )
    {
      v16 = StringCchCopyExW(v15, v13, *(STRSAFE_LPCWSTR *)(v14 + 16), &ppszDestEnd, pcchRemaining, 0x100u);
      if ( v16 < 0 )
      {
        v17 = (unsigned __int16)v16;
        goto LABEL_17;
      }
      v15 = ppszDestEnd + 1;
      v14 = *(_QWORD *)(v14 + 8);
      v13 = --pcchRemaining[0];
      ++ppszDestEnd;
    }
    *v15 = 0;
  }
  v17 = RegSetValueExW(hKey, lpValueName, 0, 7u, (const BYTE *)v11, v10);
LABEL_17:
  GlobalFree(v11);
  return v17;
}

```

## disassembly

```asm
0x18000ae90  push    rbx
0x18000ae92  push    rbp
0x18000ae93  push    rsi
0x18000ae94  push    rdi
0x18000ae95  push    r14
0x18000ae97  push    r15
0x18000ae99  sub     rsp, 48h
0x18000ae9d  mov     rbx, [r8]
0x18000aea0  mov     r14, r8
0x18000aea3  mov     rbp, rdx
0x18000aea6  mov     r15, rcx
0x18000aea9  mov     edi, 2
0x18000aeae  jmp     short loc_18000AEC4
0x18000aeb0  mov     rcx, [rbx+10h]; lpString
0x18000aeb4  call    cs:__imp_lstrlenW
0x18000aeba  mov     rbx, [rbx+8]
0x18000aebe  lea     edi, [rdi+rax*2]
0x18000aec1  add     edi, 2
0x18000aec4  test    rbx, rbx
0x18000aec7  jnz     short loc_18000AEB0
0x18000aec9  lea     eax, [rbx+4]
0x18000aecc  cmp     edi, 2
0x18000aecf  lea     ecx, [rbx+40h]; uFlags
0x18000aed2  cmovnz  eax, edi
0x18000aed5  mov     edx, eax; dwBytes
0x18000aed7  mov     esi, eax
0x18000aed9  call    cs:__imp_GlobalAlloc
0x18000aedf  mov     rbx, rax
0x18000aee2  test    rax, rax
0x18000aee5  jnz     short loc_18000AEEF
0x18000aee7  lea     eax, [rbx+8]
0x18000aeea  jmp     loc_18000AF9E
0x18000aeef  mov     rax, rsi
0x18000aef2  shr     rax, 1
0x18000aef5  mov     [rsp+78h+var_48], rax
0x18000aefa  cmp     esi, 4
0x18000aefd  jnz     short loc_18000AF05
0x18000aeff  xor     eax, eax
0x18000af01  mov     [rbx], eax
0x18000af03  jmp     short loc_18000AF73
0x18000af05  mov     rdi, [r14]
0x18000af08  mov     rcx, rbx; pszDest
0x18000af0b  mov     [rsp+78h+ppszDestEnd], rbx
0x18000af13  test    rdi, rdi
0x18000af16  jz      short loc_18000AF6E
0x18000af18  mov     r8, [rdi+10h]; pszSrc
0x18000af1c  lea     rdx, [rsp+78h+var_48]
0x18000af21  mov     [rsp+78h+dwFlags], 100h; dwFlags
0x18000af29  lea     r9, [rsp+78h+ppszDestEnd]; ppszDestEnd
0x18000af31  mov     [rsp+78h+pcchRemaining], rdx; pcchRemaining
0x18000af36  mov     rdx, rax; cchDest
0x18000af39  call    StringCchCopyExW
0x18000af3e  test    eax, eax
0x18000af40  js      short loc_18000AF69
0x18000af42  mov     rcx, [rsp+78h+ppszDestEnd]
0x18000af4a  mov     rax, [rsp+78h+var_48]
0x18000af4f  add     rcx, 2
0x18000af53  mov     rdi, [rdi+8]
0x18000af57  dec     rax
0x18000af5a  mov     [rsp+78h+var_48], rax
0x18000af5f  mov     [rsp+78h+ppszDestEnd], rcx
0x18000af67  jmp     short loc_18000AF13
0x18000af69  movzx   edi, ax
0x18000af6c  jmp     short loc_18000AF93
0x18000af6e  xor     eax, eax
0x18000af70  mov     [rcx], ax
0x18000af73  mov     [rsp+78h+dwFlags], esi; cbData
0x18000af77  mov     r9d, 7; dwType
0x18000af7d  xor     r8d, r8d; Reserved
0x18000af80  mov     [rsp+78h+pcchRemaining], rbx; lpData
0x18000af85  mov     rdx, rbp; lpValueName
0x18000af88  mov     rcx, r15; hKey
0x18000af8b  call    cs:__imp_RegSetValueExW
0x18000af91  mov     edi, eax
0x18000af93  mov     rcx, rbx; hMem
0x18000af96  call    cs:__imp_GlobalFree
0x18000af9c  mov     eax, edi
0x18000af9e  add     rsp, 48h
0x18000afa2  pop     r15
0x18000afa4  pop     r14
0x18000afa6  pop     rdi
0x18000afa7  pop     rsi
0x18000afa8  pop     rbp
0x18000afa9  pop     rbx
0x18000afaa  retn
```
