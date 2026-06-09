# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000ace0`
- end: `0x18000ad34`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006100`
- `0x1800069e0`
- `0x180006d20`
- `0x180007090`
- `0x180007330`
- `0x1800075c0`
- `0x180007a80`
- `0x180007d40`
- `0x1800080c0`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`
- `0x180009b90`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`
- `0x18000a8f0`
- `0x18000bac0`
- `0x18000bd30`
- `0x18000bef4`
- `0x18000c500`

## callees

- `0x18000ace0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000ad22`
- `ntdll!EtwEventWriteTransfer` at `0x18000ad22`

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
0x18000ace0  sub     rsp, 38h
0x18000ace4  mov     r8, [rcx+8]
0x18000ace8  mov     rax, [rsp+38h+arg_20]
0x18000aced  test    r8, r8
0x18000acf0  jnz     short loc_18000ACFA
0x18000acf2  mov     [rax], r8
0x18000acf5  xor     r10d, r10d
0x18000acf8  jmp     short loc_18000AD07
0x18000acfa  mov     [rax], r8
0x18000acfd  mov     r10d, 2
0x18000ad03  movzx   r8d, word ptr [r8]
0x18000ad07  mov     [rax+8], r8d
0x18000ad0b  xor     r8d, r8d
0x18000ad0e  mov     [rsp+38h+var_10], rax
0x18000ad13  mov     [rax+0Ch], r10d
0x18000ad17  mov     rcx, [rcx]
0x18000ad1a  mov     [rsp+38h+var_18], r9d
0x18000ad1f  xor     r9d, r9d
0x18000ad22  call    cs:__imp_EtwEventWriteTransfer
0x18000ad29  nop     dword ptr [rax+rax+00h]
0x18000ad2e  add     rsp, 38h
0x18000ad32  retn
```
