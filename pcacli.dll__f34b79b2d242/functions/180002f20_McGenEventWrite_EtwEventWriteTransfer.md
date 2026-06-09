# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180002f20`
- end: `0x180002f75`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001870`
- `0x180001bd0`
- `0x1800085e0`

## callees

- `0x180002f20`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180002f5c`
- `ntdll!EtwEventWriteTransfer` at `0x180002f5c`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180014008;
  if ( qword_180014008 )
  {
    *(_QWORD *)a5 = qword_180014008;
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
  return EtwEventWriteTransfer(AE_PCA_ETW_LOG_Context, a2, 0, 0, 1, a5);
}

```

## disassembly

```asm
0x180002f20  sub     rsp, 38h
0x180002f24  mov     rcx, cs:qword_180014008
0x180002f2b  mov     rax, [rsp+38h+arg_20]
0x180002f30  test    rcx, rcx
0x180002f33  jnz     short loc_180002F67
0x180002f35  mov     [rax], rcx
0x180002f38  xor     r8d, r8d
0x180002f3b  mov     [rax+8], ecx
0x180002f3e  xor     r9d, r9d
0x180002f41  mov     [rax+0Ch], r8d
0x180002f45  xor     r8d, r8d
0x180002f48  mov     rcx, cs:AE_PCA_ETW_LOG_Context
0x180002f4f  mov     [rsp+38h+var_10], rax
0x180002f54  mov     [rsp+38h+var_18], 1
0x180002f5c  call    cs:__imp_EtwEventWriteTransfer
0x180002f62  add     rsp, 38h
0x180002f66  retn
0x180002f67  mov     [rax], rcx
0x180002f6a  mov     r8d, 2
0x180002f70  movzx   ecx, word ptr [rcx]
0x180002f73  jmp     short loc_180002F3B
```
