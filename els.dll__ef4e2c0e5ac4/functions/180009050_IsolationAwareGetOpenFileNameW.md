# IsolationAwareGetOpenFileNameW

- ea: `0x180009050`
- end: `0x180009113`
- name: `IsolationAwareGetOpenFileNameW`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007bd8`

## callees

- `0x180008d1c`
- `0x180009050`
- `0x18000911c`
- `0x180021158`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800090da`
- `KERNEL32!GetLastError` at `0x1800090da`
- `KERNEL32!SetLastError` at `0x1800090fb`
- `KERNEL32!SetLastError` at `0x1800090fb`
- `KERNEL32!DeactivateActCtx` at `0x1800090ef`
- `KERNEL32!DeactivateActCtx` at `0x1800090ef`

## string_xrefs

- `0x180009095`: `GetOpenFileNameW`

## pseudocode

```c
__int64 __fastcall IsolationAwareGetOpenFileNameW(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareGetOpenFileNameW'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY("GetOpenFileNameW");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareGetOpenFileNameW'::`2'::s_pfn = v5;
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
0x180009050  mov     rax, rsp
0x180009053  mov     [rax+8], rbx
0x180009057  mov     [rax+18h], rsi
0x18000905b  push    rdi
0x18000905c  sub     rsp, 30h
0x180009060  mov     rsi, rcx
0x180009063  xor     edi, edi
0x180009065  mov     [rax-18h], edi
0x180009068  mov     rbx, cs:?s_pfn@?1??IsolationAwareGetOpenFileNameW@@9@4P6AHPEAUtagOFNW@@@ZEA; int (*`IsolationAwareGetOpenFileNameW'::`2'::s_pfn)(tagOFNW *)
0x18000906f  mov     [rax+10h], rdi
0x180009073  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180009079  jnz     short loc_180009090
0x18000907b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180009081  jnz     short loc_180009090
0x180009083  lea     rcx, [rax+10h]; lpCookie
0x180009087  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000908c  test    eax, eax
0x18000908e  jz      short loc_180009103
0x180009090  test    rbx, rbx
0x180009093  jnz     short loc_1800090B0
0x180009095  lea     rcx, aGetopenfilenam; "GetOpenFileNameW"
0x18000909c  call    CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY
0x1800090a1  mov     rbx, rax
0x1800090a4  test    rax, rax
0x1800090a7  jz      short loc_1800090C1
0x1800090a9  mov     cs:?s_pfn@?1??IsolationAwareGetOpenFileNameW@@9@4P6AHPEAUtagOFNW@@@ZEA, rax; int (*`IsolationAwareGetOpenFileNameW'::`2'::s_pfn)(tagOFNW *)
0x1800090b0  mov     rcx, rsi
0x1800090b3  mov     rax, rbx
0x1800090b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bb  mov     edi, eax
0x1800090bd  mov     [rsp+38h+var_18], eax
0x1800090c1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800090c8  jz      short loc_1800090D3
0x1800090ca  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800090d1  jnz     short loc_180009101
0x1800090d3  test    edi, edi
0x1800090d5  jnz     short loc_1800090E4
0x1800090d7  lea     esi, [rdi+1]
0x1800090da  call    cs:__imp_GetLastError
0x1800090e0  mov     ebx, eax
0x1800090e2  jmp     short loc_1800090E8
0x1800090e4  xor     esi, esi
0x1800090e6  xor     ebx, ebx
0x1800090e8  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800090ed  xor     ecx, ecx; dwFlags
0x1800090ef  call    cs:__imp_DeactivateActCtx
0x1800090f5  test    esi, esi
0x1800090f7  jz      short loc_180009101
0x1800090f9  mov     ecx, ebx; dwErrCode
0x1800090fb  call    cs:__imp_SetLastError
0x180009101  mov     eax, edi
0x180009103  mov     rbx, [rsp+38h+arg_0]
0x180009108  mov     rsi, [rsp+38h+arg_10]
0x18000910d  add     rsp, 30h
0x180009111  pop     rdi
0x180009112  retn
0x180022a21  push    rbx
0x180022a23  push    rbp
0x180022a24  push    rdi
0x180022a25  sub     rsp, 20h
0x180022a29  mov     rbp, rdx
0x180022a2c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180022a33  jz      short loc_180022A3E
0x180022a35  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180022a3c  jnz     short loc_180022A70
0x180022a3e  cmp     dword ptr [rbp+20h], 0
0x180022a42  jnz     short loc_180022A53
0x180022a44  mov     edi, 1
0x180022a49  call    cs:__imp_GetLastError
0x180022a4f  mov     ebx, eax
0x180022a51  jmp     short loc_180022A57
0x180022a53  xor     edi, edi
0x180022a55  xor     ebx, ebx
0x180022a57  mov     rdx, [rbp+48h]; ulCookie
0x180022a5b  xor     ecx, ecx; dwFlags
0x180022a5d  call    cs:__imp_DeactivateActCtx
0x180022a63  test    edi, edi
0x180022a65  jz      short loc_180022A70
0x180022a67  mov     ecx, ebx; dwErrCode
0x180022a69  call    cs:__imp_SetLastError
0x180022a6f  nop
0x180022a70  add     rsp, 20h
0x180022a74  pop     rdi
0x180022a75  pop     rbp
0x180022a76  pop     rbx
0x180022a77  retn
```
