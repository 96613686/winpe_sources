# IsolationAwareInitCommonControlsEx

- ea: `0x18000e05c`
- end: `0x18000e11f`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c924`
- `0x18000ccb0`

## callees

- `0x18000df94`
- `0x18000e05c`
- `0x18000e1e8`
- `0x18002d010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000e0fb`
- `KERNEL32!DeactivateActCtx` at `0x18002c6bd`
- `KERNEL32!DeactivateActCtx` at `0x18000e0fb`
- `KERNEL32!DeactivateActCtx` at `0x18002c6bd`
- `KERNEL32!SetLastError` at `0x18000e107`
- `KERNEL32!SetLastError` at `0x18002c6c9`
- `KERNEL32!SetLastError` at `0x18000e107`
- `KERNEL32!SetLastError` at `0x18002c6c9`
- `KERNEL32!GetLastError` at `0x18000e0e6`
- `KERNEL32!GetLastError` at `0x18002c6a9`
- `KERNEL32!GetLastError` at `0x18000e0e6`
- `KERNEL32!GetLastError` at `0x18002c6a9`

## string_xrefs

- `0x18000e0a1`: `InitCommonControlsEx`

## pseudocode

```c
__int64 __fastcall IsolationAwareInitCommonControlsEx(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareInitCommonControlsEx'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("InitCommonControlsEx");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareInitCommonControlsEx'::`2'::s_pfn = v5;
  }
  v2 = v3(a1);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e05c  mov     rax, rsp
0x18000e05f  mov     [rax+8], rbx
0x18000e063  mov     [rax+18h], rsi
0x18000e067  push    rdi
0x18000e068  sub     rsp, 30h
0x18000e06c  mov     rsi, rcx
0x18000e06f  xor     edi, edi
0x18000e071  mov     [rax-18h], edi
0x18000e074  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000e07b  mov     [rax+10h], rdi
0x18000e07f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x18000e085  jnz     short loc_18000E09C
0x18000e087  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000e08d  jnz     short loc_18000E09C
0x18000e08f  lea     rcx, [rax+10h]; lpCookie
0x18000e093  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e098  test    eax, eax
0x18000e09a  jz      short loc_18000E10F
0x18000e09c  test    rbx, rbx
0x18000e09f  jnz     short loc_18000E0BC
0x18000e0a1  lea     rcx, aInitcommoncont; "InitCommonControlsEx"
0x18000e0a8  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000e0ad  mov     rbx, rax
0x18000e0b0  test    rax, rax
0x18000e0b3  jz      short loc_18000E0CD
0x18000e0b5  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000e0bc  mov     rcx, rsi
0x18000e0bf  mov     rax, rbx
0x18000e0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c7  mov     edi, eax
0x18000e0c9  mov     [rsp+38h+var_18], eax
0x18000e0cd  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e0d4  jz      short loc_18000E0DF
0x18000e0d6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e0dd  jnz     short loc_18000E10D
0x18000e0df  test    edi, edi
0x18000e0e1  jnz     short loc_18000E0F0
0x18000e0e3  lea     esi, [rdi+1]
0x18000e0e6  call    cs:__imp_GetLastError
0x18000e0ec  mov     ebx, eax
0x18000e0ee  jmp     short loc_18000E0F4
0x18000e0f0  xor     esi, esi
0x18000e0f2  xor     ebx, ebx
0x18000e0f4  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000e0f9  xor     ecx, ecx; dwFlags
0x18000e0fb  call    cs:__imp_DeactivateActCtx
0x18000e101  test    esi, esi
0x18000e103  jz      short loc_18000E10D
0x18000e105  mov     ecx, ebx; dwErrCode
0x18000e107  call    cs:__imp_SetLastError
0x18000e10d  mov     eax, edi
0x18000e10f  mov     rbx, [rsp+38h+arg_0]
0x18000e114  mov     rsi, [rsp+38h+arg_10]
0x18000e119  add     rsp, 30h
0x18000e11d  pop     rdi
0x18000e11e  retn
0x18002c681  push    rbx
0x18002c683  push    rbp
0x18002c684  push    rdi
0x18002c685  sub     rsp, 20h
0x18002c689  mov     rbp, rdx
0x18002c68c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002c693  jz      short loc_18002C69E
0x18002c695  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002c69c  jnz     short loc_18002C6D0
0x18002c69e  cmp     dword ptr [rbp+20h], 0
0x18002c6a2  jnz     short loc_18002C6B3
0x18002c6a4  mov     edi, 1
0x18002c6a9  call    cs:__imp_GetLastError
0x18002c6af  mov     ebx, eax
0x18002c6b1  jmp     short loc_18002C6B7
0x18002c6b3  xor     edi, edi
0x18002c6b5  xor     ebx, ebx
0x18002c6b7  mov     rdx, [rbp+48h]; ulCookie
0x18002c6bb  xor     ecx, ecx; dwFlags
0x18002c6bd  call    cs:__imp_DeactivateActCtx
0x18002c6c3  test    edi, edi
0x18002c6c5  jz      short loc_18002C6D0
0x18002c6c7  mov     ecx, ebx; dwErrCode
0x18002c6c9  call    cs:__imp_SetLastError
0x18002c6cf  nop
0x18002c6d0  add     rsp, 20h
0x18002c6d4  pop     rdi
0x18002c6d5  pop     rbp
0x18002c6d6  pop     rbx
0x18002c6d7  retn
```
