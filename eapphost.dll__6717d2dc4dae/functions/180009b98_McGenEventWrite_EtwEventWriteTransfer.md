# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180009b98`
- end: `0x180009be5`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009bec`
- `0x180009d00`
- `0x180011064`
- `0x1800113a0`
- `0x180011958`
- `0x1800119d4`
- `0x18001a2f0`
- `0x18001ac7c`
- `0x18001c534`
- `0x18001c610`
- `0x18001c6b4`
- `0x18001c78c`
- `0x18001c828`
- `0x18001c8b4`
- `0x18001c95c`
- `0x18001fdfc`
- `0x180025760`
- `0x180025b18`
- `0x180028f64`
- `0x18002e39c`
- `0x1800359f6`
- `0x180035b77`
- `0x180035eac`
- `0x1800361a5`

## callees

- `0x180009b98`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180009bda`
- `ntdll!EtwEventWriteTransfer` at `0x180009bda`

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
0x180009b98  sub     rsp, 38h
0x180009b9c  mov     r8, [rcx+8]
0x180009ba0  mov     rax, [rsp+38h+arg_20]
0x180009ba5  test    r8, r8
0x180009ba8  jnz     short loc_180009BB2
0x180009baa  mov     [rax], r8
0x180009bad  xor     r10d, r10d
0x180009bb0  jmp     short loc_180009BBF
0x180009bb2  mov     [rax], r8
0x180009bb5  mov     r10d, 2
0x180009bbb  movzx   r8d, word ptr [r8]
0x180009bbf  mov     [rax+8], r8d
0x180009bc3  xor     r8d, r8d
0x180009bc6  mov     [rsp+38h+var_10], rax
0x180009bcb  mov     [rax+0Ch], r10d
0x180009bcf  mov     rcx, [rcx]
0x180009bd2  mov     [rsp+38h+var_18], r9d
0x180009bd7  xor     r9d, r9d
0x180009bda  call    cs:__imp_EtwEventWriteTransfer
0x180009be0  add     rsp, 38h
0x180009be4  retn
```
