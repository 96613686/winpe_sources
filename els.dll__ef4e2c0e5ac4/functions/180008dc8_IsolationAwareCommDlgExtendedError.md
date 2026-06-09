# IsolationAwareCommDlgExtendedError

- ea: `0x180008dc8`
- end: `0x180008e85`
- name: `IsolationAwareCommDlgExtendedError`
- size: `189`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007bd8`

## callees

- `0x180008d1c`
- `0x180008dc8`
- `0x18000911c`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008e4c`
- `KERNEL32!GetLastError` at `0x18002298c`
- `KERNEL32!GetLastError` at `0x180008e4c`
- `KERNEL32!GetLastError` at `0x18002298c`
- `KERNEL32!SetLastError` at `0x180008e6d`
- `KERNEL32!SetLastError` at `0x1800229ac`
- `KERNEL32!SetLastError` at `0x180008e6d`
- `KERNEL32!SetLastError` at `0x1800229ac`
- `KERNEL32!DeactivateActCtx` at `0x180008e61`
- `KERNEL32!DeactivateActCtx` at `0x1800229a0`
- `KERNEL32!DeactivateActCtx` at `0x180008e61`
- `KERNEL32!DeactivateActCtx` at `0x1800229a0`

## string_xrefs

- `0x180008e0a`: `CommDlgExtendedError`

## pseudocode

```c
__int64 __fastcall IsolationAwareCommDlgExtendedError(__int64 a1)
{
  unsigned int v1; // edi
  __int64 (__fastcall *v2)(__int64); // rbx
  __int64 result; // rax
  __int64 v4; // rax
  int v5; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  v2 = (__int64 (__fastcall *)(__int64))`IsolationAwareCommDlgExtendedError'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v2 )
  {
    v4 = CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY("CommDlgExtendedError");
    v2 = (__int64 (__fastcall *)(__int64))v4;
    if ( !v4 )
      goto LABEL_8;
    `IsolationAwareCommDlgExtendedError'::`2'::s_pfn = v4;
  }
  v1 = v2(a1);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v1 )
    {
      v5 = 0;
      LastError = 0;
    }
    else
    {
      v5 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v5 )
      SetLastError(LastError);
  }
  return v1;
}

```

## disassembly

```asm
0x180008dc8  mov     rax, rsp
0x180008dcb  mov     [rax+10h], rbx
0x180008dcf  mov     [rax+18h], rsi
0x180008dd3  push    rdi
0x180008dd4  sub     rsp, 30h
0x180008dd8  xor     edi, edi
0x180008dda  mov     [rax-18h], edi
0x180008ddd  mov     rbx, cs:?s_pfn@?1??IsolationAwareCommDlgExtendedError@@9@4P6AKXZEA; ulong (*`IsolationAwareCommDlgExtendedError'::`2'::s_pfn)(void)
0x180008de4  mov     [rax+8], rdi
0x180008de8  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180008dee  jnz     short loc_180008E05
0x180008df0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180008df6  jnz     short loc_180008E05
0x180008df8  lea     rcx, [rax+8]; lpCookie
0x180008dfc  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180008e01  test    eax, eax
0x180008e03  jz      short loc_180008E75
0x180008e05  test    rbx, rbx
0x180008e08  jnz     short loc_180008E25
0x180008e0a  lea     rcx, aCommdlgextende; "CommDlgExtendedError"
0x180008e11  call    CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY
0x180008e16  mov     rbx, rax
0x180008e19  test    rax, rax
0x180008e1c  jz      short loc_180008E33
0x180008e1e  mov     cs:?s_pfn@?1??IsolationAwareCommDlgExtendedError@@9@4P6AKXZEA, rax; ulong (*`IsolationAwareCommDlgExtendedError'::`2'::s_pfn)(void)
0x180008e25  mov     rax, rbx
0x180008e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e2d  mov     edi, eax
0x180008e2f  mov     [rsp+38h+var_18], eax
0x180008e33  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180008e3a  jz      short loc_180008E45
0x180008e3c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180008e43  jnz     short loc_180008E73
0x180008e45  test    edi, edi
0x180008e47  jnz     short loc_180008E56
0x180008e49  lea     esi, [rdi+1]
0x180008e4c  call    cs:__imp_GetLastError
0x180008e52  mov     ebx, eax
0x180008e54  jmp     short loc_180008E5A
0x180008e56  xor     esi, esi
0x180008e58  xor     ebx, ebx
0x180008e5a  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180008e5f  xor     ecx, ecx; dwFlags
0x180008e61  call    cs:__imp_DeactivateActCtx
0x180008e67  test    esi, esi
0x180008e69  jz      short loc_180008E73
0x180008e6b  mov     ecx, ebx; dwErrCode
0x180008e6d  call    cs:__imp_SetLastError
0x180008e73  mov     eax, edi
0x180008e75  mov     rbx, [rsp+38h+arg_8]
0x180008e7a  mov     rsi, [rsp+38h+arg_10]
0x180008e7f  add     rsp, 30h
0x180008e83  pop     rdi
0x180008e84  retn
0x180022964  push    rbx
0x180022966  push    rbp
0x180022967  push    rdi
0x180022968  sub     rsp, 20h
0x18002296c  mov     rbp, rdx
0x18002296f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180022976  jz      short loc_180022981
0x180022978  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002297f  jnz     short loc_1800229B3
0x180022981  cmp     dword ptr [rbp+20h], 0
0x180022985  jnz     short loc_180022996
0x180022987  mov     edi, 1
0x18002298c  call    cs:__imp_GetLastError
0x180022992  mov     ebx, eax
0x180022994  jmp     short loc_18002299A
0x180022996  xor     edi, edi
0x180022998  xor     ebx, ebx
0x18002299a  mov     rdx, [rbp+40h]; ulCookie
0x18002299e  xor     ecx, ecx; dwFlags
0x1800229a0  call    cs:__imp_DeactivateActCtx
0x1800229a6  test    edi, edi
0x1800229a8  jz      short loc_1800229B3
0x1800229aa  mov     ecx, ebx; dwErrCode
0x1800229ac  call    cs:__imp_SetLastError
0x1800229b2  nop
0x1800229b3  add     rsp, 20h
0x1800229b7  pop     rdi
0x1800229b8  pop     rbp
0x1800229b9  pop     rbx
0x1800229ba  retn
```
