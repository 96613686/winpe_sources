# PartitionInsertPatch(_PARTITION_EXTENSION *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x140004db8`
- end: `0x140004e3e`
- name: `?PartitionInsertPatch@@YAJPEAU_PARTITION_EXTENSION@@_K11@Z`
- size: `134`
- prototype: `__int64 __fastcall(struct _PARTITION_EXTENSION *, unsigned __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140005c50`
- `0x14000a21c`

## callees

- `0x140004db8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004de7`
- `ntoskrnl!ExAllocatePool2` at `0x140004de7`

## pseudocode

```c
__int64 __fastcall PartitionInsertPatch(struct _PARTITION_EXTENSION *a1, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rcx
  _QWORD *i; // rbx
  _QWORD *Pool2; // rax
  _QWORD *v10; // rdx
  unsigned int v11; // ecx

  v4 = (_QWORD *)((char *)a1 + 328);
  for ( i = (_QWORD *)*v4; i != v4 && i[2] <= a2; i = (_QWORD *)*i )
    ;
  Pool2 = (_QWORD *)ExAllocatePool2(66, 40, 1347448144);
  if ( Pool2 )
  {
    Pool2[2] = a2;
    Pool2[3] = a3;
    Pool2[4] = a4;
    v10 = (_QWORD *)i[1];
    if ( (_QWORD *)*v10 != i )
      __fastfail(3u);
    *Pool2 = i;
    v11 = 0;
    Pool2[1] = v10;
    *v10 = Pool2;
    i[1] = Pool2;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v11;
}

```

## disassembly

```asm
0x140004db8  push    rbx
0x140004dba  push    rbp
0x140004dbb  push    rsi
0x140004dbc  push    rdi
0x140004dbd  sub     rsp, 28h
0x140004dc1  add     rcx, 148h
0x140004dc8  mov     rsi, r9
0x140004dcb  mov     rbp, r8
0x140004dce  mov     rdi, rdx
0x140004dd1  mov     rbx, [rcx]
0x140004dd4  cmp     rbx, rcx
0x140004dd7  jnz     short loc_140004E14
0x140004dd9  mov     edx, 28h ; '('
0x140004dde  mov     r8d, 50506D50h
0x140004de4  lea     ecx, [rdx+1Ah]
0x140004de7  call    cs:__imp_ExAllocatePool2
0x140004dee  nop     dword ptr [rax+rax+00h]
0x140004df3  test    rax, rax
0x140004df6  jz      short loc_140004E1F
0x140004df8  mov     [rax+10h], rdi
0x140004dfc  mov     [rax+18h], rbp
0x140004e00  mov     [rax+20h], rsi
0x140004e04  mov     rdx, [rbx+8]
0x140004e08  cmp     [rdx], rbx
0x140004e0b  jz      short loc_140004E29
0x140004e0d  mov     ecx, 3
0x140004e12  int     29h; Win8: RtlFailFast(ecx)
0x140004e14  cmp     [rbx+10h], rdi
0x140004e18  ja      short loc_140004DD9
0x140004e1a  mov     rbx, [rbx]
0x140004e1d  jmp     short loc_140004DD4
0x140004e1f  mov     ecx, 0C000009Ah
0x140004e24  jmp     loc_140011D54
0x140004e29  mov     [rax], rbx
0x140004e2c  xor     ecx, ecx
0x140004e2e  mov     [rax+8], rdx
0x140004e32  mov     [rdx], rax
0x140004e35  mov     [rbx+8], rax
0x140004e39  jmp     loc_140011D54
0x140011d54  mov     eax, ecx
0x140011d56  add     rsp, 28h
0x140011d5a  pop     rdi
0x140011d5b  pop     rsi
0x140011d5c  pop     rbp
0x140011d5d  pop     rbx
0x140011d5e  retn
```
