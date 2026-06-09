# HrWStrToAStr(ushort const *,char * *)

- ea: `0x180052880`
- end: `0x18005293f`
- name: `?HrWStrToAStr@@YAJPEBGPEAPEAD@Z`
- size: `191`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050d44`
- `0x180050e60`
- `0x180051638`
- `0x180052144`

## callees

- `0x180052880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052918`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800528be`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180052907`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800528be`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180052907`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800528cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800528cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005292e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005292e`

## pseudocode

```c
__int64 __fastcall HrWStrToAStr(LPCWCH lpWideCharStr, char **a2)
{
  char *v5; // rdi
  unsigned int v6; // eax
  int cbMultiByte; // ebp
  CHAR *lpMultiByteStr; // rax
  DWORD v9; // ebx

  if ( !lpWideCharStr )
  {
    *a2 = 0;
    return 0;
  }
  v5 = 0;
  v6 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( !v6 )
    goto LABEL_8;
  lpMultiByteStr = (CHAR *)CoTaskMemAlloc(v6);
  v5 = lpMultiByteStr;
  if ( lpMultiByteStr )
  {
    if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
    {
      v9 = 0;
      *a2 = v5;
      return v9;
    }
LABEL_8:
    v9 = GetLastError() | 0x80070000;
    if ( v5 )
      CoTaskMemFree(v5);
    return v9;
  }
  return (DWORD)-2147024882;
}

```

## disassembly

```asm
0x180052880  push    rbx
0x180052882  push    rbp
0x180052883  push    rsi
0x180052884  push    rdi
0x180052885  sub     rsp, 48h
0x180052889  mov     rsi, rdx
0x18005288c  mov     rbx, rcx
0x18005288f  test    rcx, rcx
0x180052892  jnz     short loc_18005289E
0x180052894  mov     [rdx], rcx
0x180052897  xor     eax, eax
0x180052899  jmp     loc_180052936
0x18005289e  xor     edi, edi
0x1800528a0  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800528a4  mov     [rsp+68h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800528a9  mov     r8, rbx; lpWideCharStr
0x1800528ac  mov     [rsp+68h+lpDefaultChar], rdi; lpDefaultChar
0x1800528b1  xor     edx, edx; dwFlags
0x1800528b3  mov     [rsp+68h+cbMultiByte], edi; cbMultiByte
0x1800528b7  xor     ecx, ecx; CodePage
0x1800528b9  mov     [rsp+68h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800528be  call    cs:__imp_WideCharToMultiByte
0x1800528c4  mov     ebp, eax
0x1800528c6  test    eax, eax
0x1800528c8  jz      short loc_180052918
0x1800528ca  mov     ecx, ebp; cb
0x1800528cc  call    cs:__imp_CoTaskMemAlloc
0x1800528d2  mov     rdi, rax
0x1800528d5  test    rax, rax
0x1800528d8  jnz     short loc_1800528E1
0x1800528da  mov     ebx, 8007000Eh
0x1800528df  jmp     short loc_180052934
0x1800528e1  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800528ea  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800528ee  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x1800528f7  mov     r8, rbx; lpWideCharStr
0x1800528fa  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x1800528fe  xor     edx, edx; dwFlags
0x180052900  xor     ecx, ecx; CodePage
0x180052902  mov     [rsp+68h+lpMultiByteStr], rdi; lpMultiByteStr
0x180052907  call    cs:__imp_WideCharToMultiByte
0x18005290d  test    eax, eax
0x18005290f  jz      short loc_180052918
0x180052911  xor     ebx, ebx
0x180052913  mov     [rsi], rdi
0x180052916  jmp     short loc_180052934
0x180052918  call    cs:__imp_GetLastError
0x18005291e  mov     ebx, eax
0x180052920  or      ebx, 80070000h
0x180052926  test    rdi, rdi
0x180052929  jz      short loc_180052934
0x18005292b  mov     rcx, rdi; pv
0x18005292e  call    cs:__imp_CoTaskMemFree
0x180052934  mov     eax, ebx
0x180052936  add     rsp, 48h
0x18005293a  pop     rdi
0x18005293b  pop     rsi
0x18005293c  pop     rbp
0x18005293d  pop     rbx
0x18005293e  retn
```
