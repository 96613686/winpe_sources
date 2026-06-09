# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180014ecc`
- end: `0x180014f19`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014f20`
- `0x180016400`
- `0x18001647c`
- `0x180016518`
- `0x180016ec0`
- `0x18001729c`
- `0x180021fc4`
- `0x1800222e0`
- `0x18002bc04`
- `0x18002c728`
- `0x18002db9c`
- `0x18002dc78`
- `0x18002dd1c`
- `0x18002ddf4`
- `0x18002de9c`
- `0x180032f99`
- `0x18003311a`
- `0x1800333b4`
- `0x1800336ad`

## callees

- `0x180014ecc`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180014f0e`
- `ntdll!EtwEventWriteTransfer` at `0x180014f0e`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    *(_QWORD *)a5 = v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(*a1, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180014ecc  sub     rsp, 38h
0x180014ed0  mov     r8, [rcx+8]
0x180014ed4  mov     rax, [rsp+38h+arg_20]
0x180014ed9  test    r8, r8
0x180014edc  jnz     short loc_180014EE6
0x180014ede  mov     [rax], r8
0x180014ee1  xor     r10d, r10d
0x180014ee4  jmp     short loc_180014EF3
0x180014ee6  mov     [rax], r8
0x180014ee9  mov     r10d, 2
0x180014eef  movzx   r8d, word ptr [r8]
0x180014ef3  mov     [rax+8], r8d
0x180014ef7  xor     r8d, r8d
0x180014efa  mov     [rsp+38h+var_10], rax
0x180014eff  mov     [rax+0Ch], r10d
0x180014f03  mov     rcx, [rcx]
0x180014f06  mov     [rsp+38h+var_18], r9d
0x180014f0b  xor     r9d, r9d
0x180014f0e  call    cs:__imp_EtwEventWriteTransfer
0x180014f14  add     rsp, 38h
0x180014f18  retn
```
