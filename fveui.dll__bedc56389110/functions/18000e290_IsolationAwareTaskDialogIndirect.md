# IsolationAwareTaskDialogIndirect

- ea: `0x18000e290`
- end: `0x18000e34d`
- name: `IsolationAwareTaskDialogIndirect`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c924`
- `0x18000ccb0`

## callees

- `0x18000df68`
- `0x18000df94`
- `0x18000e1e8`
- `0x18000e290`
- `0x18002d010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000e343`
- `KERNEL32!DeactivateActCtx` at `0x18002c75f`
- `KERNEL32!DeactivateActCtx` at `0x18000e343`
- `KERNEL32!DeactivateActCtx` at `0x18002c75f`

## string_xrefs

- `0x18000e2f2`: `TaskDialogIndirect`

## pseudocode

```c
__int64 __fastcall IsolationAwareTaskDialogIndirect(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, __int64, _QWORD, _QWORD); // rbx
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  ULONG_PTR ulCookie; // [rsp+58h] [rbp+20h] BYREF

  v4 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
  }
  if ( !v4 )
  {
    v6 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))v6;
    if ( !v6 )
    {
      v7 = CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
      goto LABEL_10;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = v6;
  }
  v7 = v4(a1, a2, 0, 0);
LABEL_10:
  v8 = v7;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return v8;
}

```

## disassembly

```asm
0x18000e290  mov     rax, rsp
0x18000e293  mov     [rax+8], rbx
0x18000e297  mov     [rax+10h], rsi
0x18000e29b  mov     [rax+20h], r9
0x18000e29f  push    rdi
0x18000e2a0  sub     rsp, 30h
0x18000e2a4  mov     rdi, rdx
0x18000e2a7  mov     rsi, rcx
0x18000e2aa  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000e2b1  mov     qword ptr [rax+20h], 0
0x18000e2b9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e2c0  jnz     short loc_18000E2ED
0x18000e2c2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e2c9  jnz     short loc_18000E2ED
0x18000e2cb  lea     rcx, [rax+20h]; lpCookie
0x18000e2cf  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e2d4  test    eax, eax
0x18000e2d6  jnz     short loc_18000E2ED
0x18000e2d8  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000e2dd  mov     rbx, [rsp+38h+arg_0]
0x18000e2e2  mov     rsi, [rsp+38h+arg_8]
0x18000e2e7  add     rsp, 30h
0x18000e2eb  pop     rdi
0x18000e2ec  retn
0x18000e2ed  test    rbx, rbx
0x18000e2f0  jnz     short loc_18000E314
0x18000e2f2  lea     rcx, aTaskdialogindi; "TaskDialogIndirect"
0x18000e2f9  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000e2fe  mov     rbx, rax
0x18000e301  test    rax, rax
0x18000e304  jnz     short loc_18000E30D
0x18000e306  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000e30b  jmp     short loc_18000E328
0x18000e30d  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000e314  xor     r9d, r9d
0x18000e317  xor     r8d, r8d
0x18000e31a  mov     rdx, rdi
0x18000e31d  mov     rcx, rsi
0x18000e320  mov     rax, rbx
0x18000e323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e328  mov     ebx, eax
0x18000e32a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e331  jz      short loc_18000E33C
0x18000e333  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e33a  jnz     short loc_18000E349
0x18000e33c  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000e341  xor     ecx, ecx; dwFlags
0x18000e343  call    cs:__imp_DeactivateActCtx
0x18000e349  mov     eax, ebx
0x18000e34b  jmp     short loc_18000E2DD
0x18002c73e  push    rbp
0x18002c740  sub     rsp, 30h
0x18002c744  mov     rbp, rdx
0x18002c747  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002c74e  jz      short loc_18002C759
0x18002c750  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002c757  jnz     short loc_18002C766
0x18002c759  mov     rdx, [rbp+58h]; ulCookie
0x18002c75d  xor     ecx, ecx; dwFlags
0x18002c75f  call    cs:__imp_DeactivateActCtx
0x18002c765  nop
0x18002c766  add     rsp, 30h
0x18002c76a  pop     rbp
0x18002c76b  retn
```
