# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180001e78`
- end: `0x180001ecc`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800015a0`
- `0x18000163c`
- `0x1800016e0`
- `0x18000175c`
- `0x18000180c`
- `0x180001894`
- `0x180001930`
- `0x1800019b4`
- `0x180001ac0`
- `0x180001bb8`
- `0x180001c24`
- `0x180001ca4`
- `0x180001d04`
- `0x180001d8c`
- `0x180001e00`
- `0x18000fae0`
- `0x18000fbe4`
- `0x1800108f0`
- `0x180018524`
- `0x18001bbe0`
- `0x18001c8b4`
- `0x18001ca14`
- `0x180020b68`
- `0x18002a810`

## callees

- `0x180001e78`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180001eab`
- `ntdll!EtwEventWriteTransfer` at `0x180001eab`

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
0x180001e78  sub     rsp, 38h
0x180001e7c  mov     r8, [rcx+8]
0x180001e80  mov     rax, [rsp+38h+arg_20]
0x180001e85  test    r8, r8
0x180001e88  jnz     short loc_180001EBD
0x180001e8a  mov     [rax], r8
0x180001e8d  xor     r10d, r10d
0x180001e90  mov     [rax+8], r8d
0x180001e94  xor     r8d, r8d
0x180001e97  mov     [rsp+38h+var_10], rax
0x180001e9c  mov     [rax+0Ch], r10d
0x180001ea0  mov     rcx, [rcx]
0x180001ea3  mov     [rsp+38h+var_18], r9d
0x180001ea8  xor     r9d, r9d
0x180001eab  call    cs:__imp_EtwEventWriteTransfer
0x180001eb2  nop     dword ptr [rax+rax+00h]
0x180001eb7  add     rsp, 38h
0x180001ebb  retn
0x180001ebd  mov     [rax], r8
0x180001ec0  mov     r10d, 2
0x180001ec6  movzx   r8d, word ptr [r8]
0x180001eca  jmp     short loc_180001E90
```
