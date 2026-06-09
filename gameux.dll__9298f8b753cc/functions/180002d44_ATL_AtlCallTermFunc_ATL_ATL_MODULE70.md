# ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)

- ea: `0x180002d44`
- end: `0x180002db1`
- name: `?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z`
- size: `109`
- prototype: `void __fastcall(struct ATL::_ATL_MODULE70 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800011a0`
- `0x180003400`

## callees

- `0x18000125c`
- `0x180002d44`
- `0x180004010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180002d69`
- `KERNEL32!RaiseException` at `0x180002d69`

## pseudocode

```c
void __fastcall ATL::AtlCallTermFunc(struct ATL::_ATL_MODULE70 *a1)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rbx

  if ( !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    __debugbreak();
  }
  v2 = (_QWORD *)*((_QWORD *)a1 + 1);
  if ( v2 )
  {
    do
    {
      ((void (__fastcall *)(_QWORD))*v2)(v2[1]);
      v3 = (_QWORD *)v2[2];
      operator delete(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  *((_QWORD *)a1 + 1) = 0;
}

```

## disassembly

```asm
0x180002d44  mov     [rsp+arg_0], rbx
0x180002d49  mov     [rsp+arg_8], rsi
0x180002d4e  push    rdi
0x180002d4f  sub     rsp, 20h
0x180002d53  mov     rdi, rcx
0x180002d56  test    rcx, rcx
0x180002d59  jnz     short loc_180002D70
0x180002d5b  lea     edx, [rcx+1]; dwExceptionFlags
0x180002d5e  xor     r9d, r9d; lpArguments
0x180002d61  mov     ecx, 0C0000005h; dwExceptionCode
0x180002d66  xor     r8d, r8d; nNumberOfArguments
0x180002d69  call    cs:__imp_RaiseException
0x180002d6f  int     3; Trap to Debugger
0x180002d70  mov     rsi, [rcx+8]
0x180002d74  test    rsi, rsi
0x180002d77  jz      short loc_180002D99
0x180002d79  mov     rcx, [rsi+8]
0x180002d7d  mov     rax, [rsi]
0x180002d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d85  mov     rbx, [rsi+10h]
0x180002d89  mov     rcx, rsi; Block
0x180002d8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d91  mov     rsi, rbx
0x180002d94  test    rbx, rbx
0x180002d97  jnz     short loc_180002D79
0x180002d99  mov     rbx, [rsp+28h+arg_0]
0x180002d9e  mov     rsi, [rsp+28h+arg_8]
0x180002da3  mov     qword ptr [rdi+8], 0
0x180002dab  add     rsp, 20h
0x180002daf  pop     rdi
0x180002db0  retn
```
