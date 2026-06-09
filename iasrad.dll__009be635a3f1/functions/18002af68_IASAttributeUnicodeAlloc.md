# IASAttributeUnicodeAlloc

- ea: `0x18002af68`
- end: `0x18002b019`
- name: `IASAttributeUnicodeAlloc`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002875c`

## callees

- `0x18002af68`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002afbe`
- `KERNEL32!GetLastError` at `0x18002afbe`
- `KERNEL32!MultiByteToWideChar` at `0x18002afb1`
- `KERNEL32!MultiByteToWideChar` at `0x18002aff4`
- `KERNEL32!MultiByteToWideChar` at `0x18002afb1`
- `KERNEL32!MultiByteToWideChar` at `0x18002aff4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002afcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002afcc`

## pseudocode

```c
DWORD __fastcall IASAttributeUnicodeAlloc(__int64 a1)
{
  const CHAR *v2; // r8
  int v3; // eax
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  __int64 v7; // rdi

  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 16) == 5 && !*(_QWORD *)(a1 + 32) )
    {
      v2 = *(const CHAR **)(a1 + 24);
      if ( v2 )
      {
        v3 = MultiByteToWideChar(0, 0, v2, -1, 0, 0);
        cchWideChar = v3;
        if ( !v3 )
          return GetLastError();
        lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2LL * v3);
        v7 = (__int64)lpWideCharStr;
        if ( !lpWideCharStr )
          return 8;
        MultiByteToWideChar(0, 0, *(LPCCH *)(a1 + 24), -1, lpWideCharStr, cchWideChar);
        CoTaskMemFree((LPVOID)_InterlockedExchange64((volatile __int64 *)(a1 + 32), v7));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002af68  mov     rax, rsp
0x18002af6b  mov     [rax+8], rbx
0x18002af6f  mov     [rax+10h], rsi
0x18002af73  push    rdi
0x18002af74  sub     rsp, 30h
0x18002af78  mov     rbx, rcx
0x18002af7b  test    rcx, rcx
0x18002af7e  jz      loc_18002B007
0x18002af84  cmp     dword ptr [rcx+10h], 5
0x18002af88  jnz     short loc_18002B007
0x18002af8a  cmp     qword ptr [rcx+20h], 0
0x18002af8f  jnz     short loc_18002B007
0x18002af91  mov     r8, [rcx+18h]; lpMultiByteStr
0x18002af95  test    r8, r8
0x18002af98  jz      short loc_18002B007
0x18002af9a  mov     dword ptr [rax-10h], 0
0x18002afa1  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002afa5  xor     edx, edx; dwFlags
0x18002afa7  mov     qword ptr [rax-18h], 0
0x18002afaf  xor     ecx, ecx; CodePage
0x18002afb1  call    cs:__imp_MultiByteToWideChar
0x18002afb7  movsxd  rsi, eax
0x18002afba  test    eax, eax
0x18002afbc  jnz     short loc_18002AFC6
0x18002afbe  call    cs:__imp_GetLastError
0x18002afc4  jmp     short loc_18002B009
0x18002afc6  mov     rcx, rsi
0x18002afc9  add     rcx, rcx; cb
0x18002afcc  call    cs:__imp_CoTaskMemAlloc
0x18002afd2  mov     rdi, rax
0x18002afd5  test    rax, rax
0x18002afd8  jnz     short loc_18002AFDF
0x18002afda  lea     eax, [rdi+8]
0x18002afdd  jmp     short loc_18002B009
0x18002afdf  mov     r8, [rbx+18h]; lpMultiByteStr
0x18002afe3  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002afe7  mov     [rsp+38h+cchWideChar], esi; cchWideChar
0x18002afeb  xor     edx, edx; dwFlags
0x18002afed  xor     ecx, ecx; CodePage
0x18002afef  mov     [rsp+38h+lpWideCharStr], rdi; lpWideCharStr
0x18002aff4  call    cs:__imp_MultiByteToWideChar
0x18002affa  xchg    rdi, [rbx+20h]
0x18002affe  mov     rcx, rdi; pv
0x18002b001  call    cs:__imp_CoTaskMemFree
0x18002b007  xor     eax, eax
0x18002b009  mov     rbx, [rsp+38h+arg_0]
0x18002b00e  mov     rsi, [rsp+38h+arg_8]
0x18002b013  add     rsp, 30h
0x18002b017  pop     rdi
0x18002b018  retn
```
