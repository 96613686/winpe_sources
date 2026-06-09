# IASAttributeUnicodeAlloc

- ea: `0x18000ada4`
- end: `0x18000ae55`
- name: `IASAttributeUnicodeAlloc`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800115f0`
- `0x180014d20`

## callees

- `0x18000ada4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000adfa`
- `KERNEL32!GetLastError` at `0x18000adfa`
- `KERNEL32!MultiByteToWideChar` at `0x18000aded`
- `KERNEL32!MultiByteToWideChar` at `0x18000ae30`
- `KERNEL32!MultiByteToWideChar` at `0x18000aded`
- `KERNEL32!MultiByteToWideChar` at `0x18000ae30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae3d`

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
0x18000ada4  mov     rax, rsp
0x18000ada7  mov     [rax+8], rbx
0x18000adab  mov     [rax+10h], rsi
0x18000adaf  push    rdi
0x18000adb0  sub     rsp, 30h
0x18000adb4  mov     rbx, rcx
0x18000adb7  test    rcx, rcx
0x18000adba  jz      loc_18000AE43
0x18000adc0  cmp     dword ptr [rcx+10h], 5
0x18000adc4  jnz     short loc_18000AE43
0x18000adc6  cmp     qword ptr [rcx+20h], 0
0x18000adcb  jnz     short loc_18000AE43
0x18000adcd  mov     r8, [rcx+18h]; lpMultiByteStr
0x18000add1  test    r8, r8
0x18000add4  jz      short loc_18000AE43
0x18000add6  mov     dword ptr [rax-10h], 0
0x18000addd  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000ade1  xor     edx, edx; dwFlags
0x18000ade3  mov     qword ptr [rax-18h], 0
0x18000adeb  xor     ecx, ecx; CodePage
0x18000aded  call    cs:__imp_MultiByteToWideChar
0x18000adf3  movsxd  rsi, eax
0x18000adf6  test    eax, eax
0x18000adf8  jnz     short loc_18000AE02
0x18000adfa  call    cs:__imp_GetLastError
0x18000ae00  jmp     short loc_18000AE45
0x18000ae02  mov     rcx, rsi
0x18000ae05  add     rcx, rcx; cb
0x18000ae08  call    cs:__imp_CoTaskMemAlloc
0x18000ae0e  mov     rdi, rax
0x18000ae11  test    rax, rax
0x18000ae14  jnz     short loc_18000AE1B
0x18000ae16  lea     eax, [rdi+8]
0x18000ae19  jmp     short loc_18000AE45
0x18000ae1b  mov     r8, [rbx+18h]; lpMultiByteStr
0x18000ae1f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000ae23  mov     [rsp+38h+cchWideChar], esi; cchWideChar
0x18000ae27  xor     edx, edx; dwFlags
0x18000ae29  xor     ecx, ecx; CodePage
0x18000ae2b  mov     [rsp+38h+lpWideCharStr], rdi; lpWideCharStr
0x18000ae30  call    cs:__imp_MultiByteToWideChar
0x18000ae36  xchg    rdi, [rbx+20h]
0x18000ae3a  mov     rcx, rdi; pv
0x18000ae3d  call    cs:__imp_CoTaskMemFree
0x18000ae43  xor     eax, eax
0x18000ae45  mov     rbx, [rsp+38h+arg_0]
0x18000ae4a  mov     rsi, [rsp+38h+arg_8]
0x18000ae4f  add     rsp, 30h
0x18000ae53  pop     rdi
0x18000ae54  retn
```
