# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000c150`
- end: `0x18000c1a0`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `27`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a380`
- `0x18000ac8c`
- `0x18000c1a8`
- `0x18000f184`
- `0x18000f2c8`
- `0x18000f57c`
- `0x18000f77c`
- `0x180010520`
- `0x18001064c`
- `0x180011698`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180013578`
- `0x180013aac`
- `0x180013ba0`
- `0x1800142dc`
- `0x1800147b4`
- `0x1800148c4`
- `0x1800158ac`
- `0x180015a7b`
- `0x180015c13`
- `0x180015ce1`
- `0x180015ee1`

## callees

- `0x18000c150`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000c195`
- `ntdll!EtwEventWriteTransfer` at `0x18000c195`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r9d

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
  return EtwEventWriteTransfer(*a1, a2, 0);
}

```

## disassembly

```asm
0x18000c150  sub     rsp, 38h
0x18000c154  mov     r8, [rcx+8]
0x18000c158  mov     r10d, 2
0x18000c15e  mov     rax, [rsp+38h+arg_20]
0x18000c163  test    r8, r8
0x18000c166  jnz     short loc_18000C170
0x18000c168  mov     [rax], r8
0x18000c16b  xor     r9d, r9d
0x18000c16e  jmp     short loc_18000C17A
0x18000c170  mov     [rax], r8
0x18000c173  mov     r9d, r10d
0x18000c176  movzx   r8d, word ptr [r8]
0x18000c17a  mov     [rax+8], r8d
0x18000c17e  xor     r8d, r8d
0x18000c181  mov     [rax+0Ch], r9d
0x18000c185  xor     r9d, r9d
0x18000c188  mov     rcx, [rcx]
0x18000c18b  mov     [rsp+38h+var_10], rax
0x18000c190  mov     [rsp+38h+var_18], r10d
0x18000c195  call    cs:__imp_EtwEventWriteTransfer
0x18000c19b  add     rsp, 38h
0x18000c19f  retn
```
