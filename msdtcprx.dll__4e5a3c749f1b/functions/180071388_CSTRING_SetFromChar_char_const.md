# CSTRING::SetFromChar(char const *)

- ea: `0x180071388`
- end: `0x180071493`
- name: `?SetFromChar@CSTRING@@AEAAXPEBD@Z`
- size: `267`
- prototype: `void(CSTRING *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e890`

## callees

- `0x18000c0c0`
- `0x180071388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800713f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800713f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800713bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800713e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800713bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800713e5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007143b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007143b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800713db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007140e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007146b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800713db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007140e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007146b`

## pseudocode

```c
void __fastcall CSTRING::SetFromChar(CSTRING *this, const char *a2)
{
  __int64 v4; // rdi
  int v5; // r12d
  void *v6; // rbx
  void *lpWideCharStr; // rsi

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = v4 + 1;
    v6 = CoTaskMemAlloc((int)v4 + 1);
    if ( !v6 )
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    lpWideCharStr = CoTaskMemAlloc(2LL * v5);
    if ( !lpWideCharStr )
    {
      CoTaskMemFree(v6);
      v6 = 0;
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    }
    if ( (unsigned int)StringCchCopyA((char *)v6, v5, a2)
      || !MultiByteToWideChar(0, 0, (LPCCH)v6, -1, (LPWSTR)lpWideCharStr, v4 + 1) )
    {
      CoTaskMemFree(v6);
      v6 = 0;
      CoTaskMemFree(lpWideCharStr);
      lpWideCharStr = 0;
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    }
  }
  else
  {
    lpWideCharStr = 0;
    LODWORD(v4) = 0;
    v6 = 0;
  }
  *(_DWORD *)&this[1].Length = v4;
  this->Buffer = (const CHAR *)lpWideCharStr;
  *(_QWORD *)&this->Length = v6;
}

```

## disassembly

```asm
0x180071388  push    rbx
0x18007138a  push    rbp
0x18007138b  push    rsi
0x18007138c  push    rdi
0x18007138d  push    r12
0x18007138f  push    r14
0x180071391  push    r15
0x180071393  sub     rsp, 30h
0x180071397  mov     rbp, rdx
0x18007139a  mov     r14, rcx
0x18007139d  test    rdx, rdx
0x1800713a0  jz      loc_180071473
0x1800713a6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800713aa  inc     rdi
0x1800713ad  cmp     byte ptr [rdi+rdx], 0
0x1800713b1  jnz     short loc_1800713AA
0x1800713b3  lea     r12d, [rdi+1]
0x1800713b7  movsxd  r15, r12d
0x1800713ba  mov     rcx, r15; cb
0x1800713bd  call    cs:__imp_CoTaskMemAlloc
0x1800713c3  mov     rbx, rax
0x1800713c6  test    rax, rax
0x1800713c9  jnz     short loc_1800713E1
0x1800713cb  xor     r9d, r9d; lpArguments
0x1800713ce  xor     r8d, r8d; nNumberOfArguments
0x1800713d1  mov     edx, 0C0000025h; dwExceptionFlags
0x1800713d6  mov     ecx, 0C0000017h; dwExceptionCode
0x1800713db  call    cs:__imp_RaiseException
0x1800713e1  lea     rcx, [r15+r15]; cb
0x1800713e5  call    cs:__imp_CoTaskMemAlloc
0x1800713eb  mov     rsi, rax
0x1800713ee  test    rax, rax
0x1800713f1  jnz     short loc_180071414
0x1800713f3  mov     rcx, rbx; pv
0x1800713f6  call    cs:__imp_CoTaskMemFree
0x1800713fc  xor     r9d, r9d; lpArguments
0x1800713ff  xor     r8d, r8d; nNumberOfArguments
0x180071402  mov     edx, 0C0000025h; dwExceptionFlags
0x180071407  mov     ecx, 0C0000017h; dwExceptionCode
0x18007140c  xor     ebx, ebx
0x18007140e  call    cs:__imp_RaiseException
0x180071414  mov     r8, rbp; char *
0x180071417  mov     rdx, r15; unsigned __int64
0x18007141a  mov     rcx, rbx; char *
0x18007141d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180071422  test    eax, eax
0x180071424  jnz     short loc_180071445
0x180071426  mov     [rsp+68h+cchWideChar], r12d; cchWideChar
0x18007142b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18007142f  mov     r8, rbx; lpMultiByteStr
0x180071432  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x180071437  xor     edx, edx; dwFlags
0x180071439  xor     ecx, ecx; CodePage
0x18007143b  call    cs:__imp_MultiByteToWideChar
0x180071441  test    eax, eax
0x180071443  jnz     short loc_180071479
0x180071445  mov     rcx, rbx; pv
0x180071448  call    cs:__imp_CoTaskMemFree
0x18007144e  mov     rcx, rsi; pv
0x180071451  xor     ebx, ebx
0x180071453  call    cs:__imp_CoTaskMemFree
0x180071459  xor     r9d, r9d; lpArguments
0x18007145c  xor     r8d, r8d; nNumberOfArguments
0x18007145f  mov     edx, 0C0000025h; dwExceptionFlags
0x180071464  mov     ecx, 0C0000017h; dwExceptionCode
0x180071469  xor     esi, esi
0x18007146b  call    cs:__imp_RaiseException
0x180071471  jmp     short loc_180071479
0x180071473  xor     esi, esi
0x180071475  xor     edi, edi
0x180071477  xor     ebx, ebx
0x180071479  mov     [r14+10h], edi
0x18007147d  mov     [r14+8], rsi
0x180071481  mov     [r14], rbx
0x180071484  add     rsp, 30h
0x180071488  pop     r15
0x18007148a  pop     r14
0x18007148c  pop     r12
0x18007148e  pop     rdi
0x18007148f  pop     rsi
0x180071490  pop     rbp
0x180071491  pop     rbx
0x180071492  retn
```
