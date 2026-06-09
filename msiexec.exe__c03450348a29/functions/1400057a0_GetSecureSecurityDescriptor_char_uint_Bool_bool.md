# GetSecureSecurityDescriptor(char * *,uint *,Bool,bool)

- ea: `0x1400057a0`
- end: `0x140005803`
- name: `?GetSecureSecurityDescriptor@@YAKPEAPEADPEAIW4Bool@@_N@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400078f0`

## callees

- `0x1400057a0`
- `0x14000580c`

## pseudocode

```c
__int64 __fastcall GetSecureSecurityDescriptor(_QWORD *a1, _DWORD *a2)
{
  __int64 result; // rax

  if ( !byte_140010F00 )
  {
    result = GetSecurityDescriptor(&unk_1400112E0, (DWORD *)&dword_14001019C, 1);
    if ( (_DWORD)result )
      return result;
    byte_140010F00 = 1;
  }
  *a1 = &unk_1400112E0;
  *a2 = dword_14001019C;
  return 0;
}

```

## disassembly

```asm
0x1400057a0  mov     [rsp+arg_0], rbx
0x1400057a5  mov     [rsp+arg_8], rsi
0x1400057aa  push    rdi
0x1400057ab  sub     rsp, 20h
0x1400057af  cmp     cs:byte_140010F00, 0
0x1400057b6  lea     rsi, unk_1400112E0
0x1400057bd  mov     rbx, rdx
0x1400057c0  mov     rdi, rcx
0x1400057c3  jnz     short loc_1400057E6
0x1400057c5  xor     r9d, r9d
0x1400057c8  lea     rdx, dword_14001019C
0x1400057cf  mov     rcx, rsi
0x1400057d2  lea     r8d, [r9+1]
0x1400057d6  call    ?GetSecurityDescriptor@@YAKPEADAEAKW4sdSecurityDescriptor@@W4Bool@@@Z; GetSecurityDescriptor(char *,ulong &,sdSecurityDescriptor,Bool)
0x1400057db  test    eax, eax
0x1400057dd  jnz     short loc_1400057F3
0x1400057df  mov     cs:byte_140010F00, 1
0x1400057e6  mov     [rdi], rsi
0x1400057e9  mov     eax, cs:dword_14001019C
0x1400057ef  mov     [rbx], eax
0x1400057f1  xor     eax, eax
0x1400057f3  mov     rbx, [rsp+28h+arg_0]
0x1400057f8  mov     rsi, [rsp+28h+arg_8]
0x1400057fd  add     rsp, 20h
0x140005801  pop     rdi
0x140005802  retn
```
