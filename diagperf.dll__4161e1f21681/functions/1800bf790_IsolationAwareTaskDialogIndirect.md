# IsolationAwareTaskDialogIndirect

- ea: `0x1800bf790`
- end: `0x1800bf846`
- name: `IsolationAwareTaskDialogIndirect`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800beef4`

## callees

- `0x1800bf43c`
- `0x1800bf468`
- `0x1800bf6f0`
- `0x1800bf790`
- `0x1800d6010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x1800bf83c`
- `KERNEL32!DeactivateActCtx` at `0x1800d53d8`
- `KERNEL32!DeactivateActCtx` at `0x1800bf83c`
- `KERNEL32!DeactivateActCtx` at `0x1800d53d8`

## string_xrefs

- `0x1800bf7eb`: `TaskDialogIndirect`

## pseudocode

```c
__int64 __fastcall IsolationAwareTaskDialogIndirect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  ULONG_PTR ulCookie; // [rsp+70h] [rbp+18h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
  }
  if ( !v7 )
  {
    v9 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))v9;
    if ( !v9 )
    {
      v10 = CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
      goto LABEL_10;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = v9;
  }
  v10 = v7(a1, a2, 0, a4);
LABEL_10:
  v11 = v10;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return v11;
}

```

## disassembly

```asm
0x1800bf790  mov     [rsp+ulCookie], r8
0x1800bf795  push    rbx
0x1800bf796  push    rsi
0x1800bf797  push    rdi
0x1800bf798  push    r14
0x1800bf79a  sub     rsp, 38h
0x1800bf79e  mov     rdi, r9
0x1800bf7a1  mov     rsi, rdx
0x1800bf7a4  mov     r14, rcx
0x1800bf7a7  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x1800bf7ae  mov     [rsp+58h+ulCookie], 0
0x1800bf7b7  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800bf7be  jnz     short loc_1800BF7E6
0x1800bf7c0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800bf7c7  jnz     short loc_1800BF7E6
0x1800bf7c9  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x1800bf7ce  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800bf7d3  test    eax, eax
0x1800bf7d5  jnz     short loc_1800BF7E6
0x1800bf7d7  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x1800bf7dc  add     rsp, 38h
0x1800bf7e0  pop     r14
0x1800bf7e2  pop     rdi
0x1800bf7e3  pop     rsi
0x1800bf7e4  pop     rbx
0x1800bf7e5  retn
0x1800bf7e6  test    rbx, rbx
0x1800bf7e9  jnz     short loc_1800BF80D
0x1800bf7eb  lea     rcx, aTaskdialogindi; "TaskDialogIndirect"
0x1800bf7f2  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800bf7f7  mov     rbx, rax
0x1800bf7fa  test    rax, rax
0x1800bf7fd  jnz     short loc_1800BF806
0x1800bf7ff  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x1800bf804  jmp     short loc_1800BF821
0x1800bf806  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x1800bf80d  mov     r9, rdi
0x1800bf810  xor     r8d, r8d
0x1800bf813  mov     rdx, rsi
0x1800bf816  mov     rcx, r14
0x1800bf819  mov     rax, rbx
0x1800bf81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf821  mov     ebx, eax
0x1800bf823  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800bf82a  jz      short loc_1800BF835
0x1800bf82c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800bf833  jnz     short loc_1800BF842
0x1800bf835  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x1800bf83a  xor     ecx, ecx; dwFlags
0x1800bf83c  call    cs:__imp_DeactivateActCtx
0x1800bf842  mov     eax, ebx
0x1800bf844  jmp     short loc_1800BF7DC
0x1800d53b7  push    rbp
0x1800d53b9  sub     rsp, 30h
0x1800d53bd  mov     rbp, rdx
0x1800d53c0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800d53c7  jz      short loc_1800D53D2
0x1800d53c9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800d53d0  jnz     short loc_1800D53DF
0x1800d53d2  mov     rdx, [rbp+70h]; ulCookie
0x1800d53d6  xor     ecx, ecx; dwFlags
0x1800d53d8  call    cs:__imp_DeactivateActCtx
0x1800d53de  nop
0x1800d53df  add     rsp, 30h
0x1800d53e3  pop     rbp
0x1800d53e4  retn
```
