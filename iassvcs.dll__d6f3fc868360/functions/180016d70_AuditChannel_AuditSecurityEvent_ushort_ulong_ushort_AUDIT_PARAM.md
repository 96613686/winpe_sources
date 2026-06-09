# AuditChannel::AuditSecurityEvent(ushort,ulong,ushort,_AUDIT_PARAM *)

- ea: `0x180016d70`
- end: `0x180016de5`
- name: `?AuditSecurityEvent@AuditChannel@@UEAAJGKGPEAU_AUDIT_PARAM@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(AuditChannel *this, struct IErrorInfo *, unsigned int, unsigned __int16, struct _AUDIT_PARAM *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800137b0`
- `0x180016d70`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall AuditChannel::AuditSecurityEvent(
        AuditChannel *this,
        struct IErrorInfo *a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct _AUDIT_PARAM *a5)
{
  _QWORD *v5; // rbx
  unsigned __int16 v8; // r14
  __int64 result; // rax

  v5 = (_QWORD *)*((_QWORD *)this + 9);
  v8 = (unsigned __int16)a2;
  while ( v5 != *((_QWORD **)this + 10) )
  {
    if ( !*v5 )
      _com_issue_error(-2147467261, a2);
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct _AUDIT_PARAM *))(*(_QWORD *)*v5 + 32LL))(
               *v5,
               v8,
               a3,
               a4,
               a5);
    if ( (int)result < 0 )
      return result;
    ++v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180016d70  push    rbx
0x180016d72  push    rbp
0x180016d73  push    rsi
0x180016d74  push    rdi
0x180016d75  push    r14
0x180016d77  push    r15
0x180016d79  sub     rsp, 38h
0x180016d7d  mov     rbx, [rcx+48h]
0x180016d81  movzx   esi, r9w
0x180016d85  mov     r15, [rsp+68h+arg_20]
0x180016d8d  mov     ebp, r8d
0x180016d90  movzx   r14d, dx
0x180016d94  mov     rdi, rcx
0x180016d97  cmp     rbx, [rdi+50h]
0x180016d9b  jz      short loc_180016DCB
0x180016d9d  mov     rcx, [rbx]
0x180016da0  test    rcx, rcx
0x180016da3  jz      short loc_180016DDA
0x180016da5  mov     rax, [rcx]
0x180016da8  movzx   r9d, si
0x180016dac  mov     r8d, ebp
0x180016daf  mov     [rsp+68h+var_48], r15
0x180016db4  movzx   edx, r14w
0x180016db8  mov     rax, [rax+20h]
0x180016dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dc1  test    eax, eax
0x180016dc3  js      short loc_180016DCD
0x180016dc5  add     rbx, 8
0x180016dc9  jmp     short loc_180016D97
0x180016dcb  xor     eax, eax
0x180016dcd  add     rsp, 38h
0x180016dd1  pop     r15
0x180016dd3  pop     r14
0x180016dd5  pop     rdi
0x180016dd6  pop     rsi
0x180016dd7  pop     rbp
0x180016dd8  pop     rbx
0x180016dd9  retn
0x180016dda  mov     ecx, 80004003h; int
0x180016ddf  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
