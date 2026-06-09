# GenExecuteReadMemoryFailureCallback(_MINIDUMP_STATE *,unsigned __int64,ulong,long)

- ea: `0x1800197d4`
- end: `0x1800198ac`
- name: `?GenExecuteReadMemoryFailureCallback@@YAHPEAU_MINIDUMP_STATE@@_KKJ@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, unsigned __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc78`

## callees

- `0x1800021f4`
- `0x1800197d4`
- `0x18002c010`

## string_xrefs

- `0x18001987b`: `Memory read failure at %I64x:%x ignored by callback\n`

## pseudocode

```c
__int64 __fastcall GenExecuteReadMemoryFailureCallback(struct _MINIDUMP_STATE *a1, __int64 a2, int a3, int a4)
{
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned int (__fastcall *v11)(__int64, int *, _OWORD *); // rax
  _OWORD v12[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+74h] [rbp-8Ch]
  int v16; // [rsp+7Ch] [rbp-84h]
  __int64 v17; // [rsp+80h] [rbp-80h]
  int v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+8Ch] [rbp-74h]
  _BYTE v20[1312]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v20, 0, 0x500u);
  if ( !*((_QWORD *)a1 + 8) )
    return 0;
  v9 = *((_QWORD *)a1 + 10);
  v15 = *(_QWORD *)a1;
  v14 = *((_DWORD *)a1 + 2);
  v19 = a4;
  v13 = 0;
  memset(v12, 0, sizeof(v12));
  v10 = 1;
  v16 = 14;
  v11 = (unsigned int (__fastcall *)(__int64, int *, _OWORD *))*((_QWORD *)a1 + 8);
  LODWORD(v12[0]) = 1;
  v17 = a2;
  v18 = a3;
  if ( !v11(v9, &v14, v12) || LODWORD(v12[0]) )
    return 0;
  else
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "Memory read failure at %I64x:%x ignored by callback\n",
      a2,
      a3);
  return v10;
}

```

## disassembly

```asm
0x1800197d4  push    rbp
0x1800197d6  push    rbx
0x1800197d7  push    rsi
0x1800197d8  push    rdi
0x1800197d9  push    r14
0x1800197db  lea     rbp, [rsp-490h]
0x1800197e3  sub     rsp, 590h
0x1800197ea  mov     esi, r8d
0x1800197ed  mov     r14, rdx
0x1800197f0  mov     rdi, rcx
0x1800197f3  xor     edx, edx; Val
0x1800197f5  mov     r8d, 500h; Size
0x1800197fb  lea     rcx, [rbp+4B0h+var_520]; void *
0x1800197ff  mov     ebx, r9d
0x180019802  call    memset_0
0x180019807  cmp     qword ptr [rdi+40h], 0
0x18001980c  jnz     short loc_180019815
0x18001980e  xor     eax, eax
0x180019810  jmp     loc_18001989E
0x180019815  mov     rax, [rdi]
0x180019818  lea     r8, [rsp+5B0h+var_580]
0x18001981d  mov     rcx, [rdi+50h]
0x180019821  lea     rdx, [rsp+5B0h+var_540]
0x180019826  mov     [rsp+5B0h+var_53C], rax
0x18001982b  xorps   xmm0, xmm0
0x18001982e  mov     eax, [rdi+8]
0x180019831  mov     [rsp+5B0h+var_540], eax
0x180019835  xor     eax, eax
0x180019837  mov     [rbp+4B0h+var_524], ebx
0x18001983a  mov     [rsp+5B0h+var_550], eax
0x18001983e  movups  [rsp+5B0h+var_580], xmm0
0x180019843  lea     ebx, [rax+1]
0x180019846  mov     [rsp+5B0h+var_534], 0Eh
0x18001984e  mov     rax, [rdi+40h]
0x180019852  mov     dword ptr [rsp+5B0h+var_580], ebx
0x180019856  mov     [rbp+4B0h+var_530], r14
0x18001985a  mov     [rbp+4B0h+var_528], esi
0x18001985d  movups  [rsp+5B0h+var_570], xmm0
0x180019862  movups  [rsp+5B0h+var_560], xmm0
0x180019867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001986c  test    eax, eax
0x18001986e  jz      short loc_18001989A
0x180019870  cmp     dword ptr [rsp+5B0h+var_580], 0
0x180019875  jnz     short loc_18001989A
0x180019877  mov     rcx, [rdi+28h]
0x18001987b  lea     r8, aMemoryReadFail; "Memory read failure at %I64x:%x ignored"...
0x180019882  mov     r9, r14
0x180019885  mov     [rsp+5B0h+var_590], esi
0x180019889  lea     edx, [rbx+3]
0x18001988c  mov     rax, [rcx]
0x18001988f  mov     rax, [rax+8]
0x180019893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019898  jmp     short loc_18001989C
0x18001989a  xor     ebx, ebx
0x18001989c  mov     eax, ebx
0x18001989e  add     rsp, 590h
0x1800198a5  pop     r14
0x1800198a7  pop     rdi
0x1800198a8  pop     rsi
0x1800198a9  pop     rbx
0x1800198aa  pop     rbp
0x1800198ab  retn
```
