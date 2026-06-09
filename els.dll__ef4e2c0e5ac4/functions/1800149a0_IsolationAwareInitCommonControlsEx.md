# IsolationAwareInitCommonControlsEx

- ea: `0x1800149a0`
- end: `0x180014a63`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001435c`

## callees

- `0x18000911c`
- `0x180014868`
- `0x1800149a0`
- `0x180021158`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014a2a`
- `KERNEL32!GetLastError` at `0x180014a2a`
- `KERNEL32!SetLastError` at `0x180014a4b`
- `KERNEL32!SetLastError` at `0x180014a4b`
- `KERNEL32!DeactivateActCtx` at `0x180014a3f`
- `KERNEL32!DeactivateActCtx` at `0x180014a3f`

## string_xrefs

- `0x1800149e5`: `InitCommonControlsEx`

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
0x1800149a0  mov     rax, rsp
0x1800149a3  mov     [rax+8], rbx
0x1800149a7  mov     [rax+18h], rsi
0x1800149ab  push    rdi
0x1800149ac  sub     rsp, 30h
0x1800149b0  mov     rsi, rcx
0x1800149b3  xor     edi, edi
0x1800149b5  mov     [rax-18h], edi
0x1800149b8  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x1800149bf  mov     [rax+10h], rdi
0x1800149c3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x1800149c9  jnz     short loc_1800149E0
0x1800149cb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x1800149d1  jnz     short loc_1800149E0
0x1800149d3  lea     rcx, [rax+10h]; lpCookie
0x1800149d7  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800149dc  test    eax, eax
0x1800149de  jz      short loc_180014A53
0x1800149e0  test    rbx, rbx
0x1800149e3  jnz     short loc_180014A00
0x1800149e5  lea     rcx, aInitcommoncont_0; "InitCommonControlsEx"
0x1800149ec  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800149f1  mov     rbx, rax
0x1800149f4  test    rax, rax
0x1800149f7  jz      short loc_180014A11
0x1800149f9  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x180014a00  mov     rcx, rsi
0x180014a03  mov     rax, rbx
0x180014a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0b  mov     edi, eax
0x180014a0d  mov     [rsp+38h+var_18], eax
0x180014a11  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180014a18  jz      short loc_180014A23
0x180014a1a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180014a21  jnz     short loc_180014A51
0x180014a23  test    edi, edi
0x180014a25  jnz     short loc_180014A34
0x180014a27  lea     esi, [rdi+1]
0x180014a2a  call    cs:__imp_GetLastError
0x180014a30  mov     ebx, eax
0x180014a32  jmp     short loc_180014A38
0x180014a34  xor     esi, esi
0x180014a36  xor     ebx, ebx
0x180014a38  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180014a3d  xor     ecx, ecx; dwFlags
0x180014a3f  call    cs:__imp_DeactivateActCtx
0x180014a45  test    esi, esi
0x180014a47  jz      short loc_180014A51
0x180014a49  mov     ecx, ebx; dwErrCode
0x180014a4b  call    cs:__imp_SetLastError
0x180014a51  mov     eax, edi
0x180014a53  mov     rbx, [rsp+38h+arg_0]
0x180014a58  mov     rsi, [rsp+38h+arg_10]
0x180014a5d  add     rsp, 30h
0x180014a61  pop     rdi
0x180014a62  retn
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
