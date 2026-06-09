# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x1800053e0`
- end: `0x180005432`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004660`
- `0x180004710`
- `0x180004f40`
- `0x180004fa0`
- `0x180006bd0`
- `0x18001ba00`
- `0x18001d108`
- `0x18002275c`
- `0x1800235a4`
- `0x180027d10`
- `0x180027dec`
- `0x18002aa00`

## callees

- `0x1800053e0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180005419`
- `ntdll!EtwEventWriteTransfer` at `0x180005419`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18003A038;
  if ( qword_18003A038 )
  {
    *(_QWORD *)a5 = qword_18003A038;
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
  return EtwEventWriteTransfer(ONEX_PROVIDER_ID_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x1800053e0  sub     rsp, 38h
0x1800053e4  mov     rcx, cs:qword_18003A038
0x1800053eb  mov     rax, [rsp+38h+arg_20]
0x1800053f0  test    rcx, rcx
0x1800053f3  jnz     short loc_180005424
0x1800053f5  mov     [rax], rcx
0x1800053f8  xor     r8d, r8d
0x1800053fb  mov     [rax+8], ecx
0x1800053fe  mov     [rax+0Ch], r8d
0x180005402  xor     r8d, r8d
0x180005405  mov     rcx, cs:ONEX_PROVIDER_ID_Context
0x18000540c  mov     [rsp+38h+var_10], rax
0x180005411  mov     [rsp+38h+var_18], r9d
0x180005416  xor     r9d, r9d
0x180005419  call    cs:__imp_EtwEventWriteTransfer
0x18000541f  add     rsp, 38h
0x180005423  retn
0x180005424  mov     [rax], rcx
0x180005427  mov     r8d, 2
0x18000542d  movzx   ecx, word ptr [rcx]
0x180005430  jmp     short loc_1800053FB
```
