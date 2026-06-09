# IsolationAwareTaskDialogIndirect

- ea: `0x180002a80`
- end: `0x180002b6a`
- name: `IsolationAwareTaskDialogIndirect`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003110`

## callees

- `0x180002918`
- `0x1800029e0`
- `0x180002a80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002b5d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d16f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180002b5d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b06`

## string_xrefs

- `0x180002af2`: `TaskDialogIndirect`

## pseudocode

```c
signed int __fastcall IsolationAwareTaskDialogIndirect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  signed int result; // eax
  __int64 v9; // rax
  signed int LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+70h] [rbp+18h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    result = GetLastError();
    if ( !result )
      result = 1359;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !v7 )
  {
    v9 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = v9;
  }
  LastError = v7(a1, a2, 0, a4);
LABEL_17:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return LastError;
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+ulCookie], r8
0x180002a85  push    rbx
0x180002a86  push    rsi
0x180002a87  push    rdi
0x180002a88  push    r14
0x180002a8a  sub     rsp, 38h
0x180002a8e  mov     rdi, r9
0x180002a91  mov     rsi, rdx
0x180002a94  mov     r14, rcx
0x180002a97  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x180002a9e  mov     [rsp+58h+ulCookie], 0
0x180002aa7  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180002aae  jnz     short loc_180002AED
0x180002ab0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002ab7  jnz     short loc_180002AED
0x180002ab9  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x180002abe  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180002ac3  test    eax, eax
0x180002ac5  jnz     short loc_180002AED
0x180002ac7  call    cs:__imp_GetLastError
0x180002acd  mov     ecx, 54Fh
0x180002ad2  test    eax, eax
0x180002ad4  cmovz   eax, ecx
0x180002ad7  test    eax, eax
0x180002ad9  jle     short loc_180002AE3
0x180002adb  movzx   eax, ax
0x180002ade  or      eax, 80070000h
0x180002ae3  add     rsp, 38h
0x180002ae7  pop     r14
0x180002ae9  pop     rdi
0x180002aea  pop     rsi
0x180002aeb  pop     rbx
0x180002aec  retn
0x180002aed  test    rbx, rbx
0x180002af0  jnz     short loc_180002B2E
0x180002af2  lea     rcx, aTaskdialogindi; "TaskDialogIndirect"
0x180002af9  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180002afe  mov     rbx, rax
0x180002b01  test    rax, rax
0x180002b04  jnz     short loc_180002B27
0x180002b06  call    cs:__imp_GetLastError
0x180002b0c  mov     ebx, eax
0x180002b0e  mov     ecx, 54Fh
0x180002b13  test    eax, eax
0x180002b15  cmovz   ebx, ecx
0x180002b18  test    ebx, ebx
0x180002b1a  jle     short loc_180002B44
0x180002b1c  movzx   ebx, bx
0x180002b1f  or      ebx, 80070000h
0x180002b25  jmp     short loc_180002B44
0x180002b27  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x180002b2e  mov     r9, rdi
0x180002b31  xor     r8d, r8d
0x180002b34  mov     rdx, rsi
0x180002b37  mov     rcx, r14
0x180002b3a  mov     rax, rbx
0x180002b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b42  mov     ebx, eax
0x180002b44  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180002b4b  jz      short loc_180002B56
0x180002b4d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002b54  jnz     short loc_180002B63
0x180002b56  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x180002b5b  xor     ecx, ecx; dwFlags
0x180002b5d  call    cs:__imp_DeactivateActCtx
0x180002b63  mov     eax, ebx
0x180002b65  jmp     loc_180002AE3
0x18000d14e  push    rbp
0x18000d150  sub     rsp, 30h
0x18000d154  mov     rbp, rdx
0x18000d157  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000d15e  jz      short loc_18000D169
0x18000d160  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000d167  jnz     short loc_18000D176
0x18000d169  mov     rdx, [rbp+70h]; ulCookie
0x18000d16d  xor     ecx, ecx; dwFlags
0x18000d16f  call    cs:__imp_DeactivateActCtx
0x18000d175  nop
0x18000d176  add     rsp, 30h
0x18000d17a  pop     rbp
0x18000d17b  retn
```
