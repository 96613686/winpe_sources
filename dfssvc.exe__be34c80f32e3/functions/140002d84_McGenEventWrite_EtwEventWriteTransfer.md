# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x140002d84`
- end: `0x140002ddf`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `91`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140002de8`
- `0x140002ebc`
- `0x140002fb4`
- `0x1400030e4`
- `0x140003200`
- `0x140003370`
- `0x140003620`
- `0x140003910`
- `0x140003f60`
- `0x140004200`
- `0x1400044a0`
- `0x1400048b0`
- `0x140004b10`
- `0x140004d80`
- `0x140005030`
- `0x140005590`
- `0x140005800`
- `0x14000b714`
- `0x14000b7bc`
- `0x140016c40`
- `0x140018108`
- `0x14001b5ac`
- `0x14001b7e8`
- `0x14001e5dc`
- `0x14001edcc`
- `0x14002654c`
- `0x1400339d8`
- `0x140033a80`
- `0x1400346b4`
- `0x14004a1e8`

## callees

- `0x140002d84`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x140002dcd`
- `ntdll!EtwEventWriteTransfer` at `0x140002dcd`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // eax
  int v7; // r8d

  v5 = (unsigned __int16 *)qword_140070178;
  v6 = 0;
  if ( qword_140070178 )
  {
    *(_QWORD *)a5 = qword_140070178;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v7 = 0;
  }
  *(_DWORD *)(a5 + 8) = v7;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(ServiceCtrlGuid_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x140002d84  sub     rsp, 38h
0x140002d88  mov     r8, cs:qword_140070178
0x140002d8f  xor     eax, eax
0x140002d91  mov     rcx, [rsp+38h+arg_20]
0x140002d96  test    r8, r8
0x140002d99  jnz     short loc_140002DA3
0x140002d9b  mov     [rcx], rax
0x140002d9e  mov     r8d, eax
0x140002da1  jmp     short loc_140002DAF
0x140002da3  mov     [rcx], r8
0x140002da6  mov     eax, 2
0x140002dab  movzx   r8d, word ptr [r8]
0x140002daf  mov     [rcx+8], r8d
0x140002db3  xor     r8d, r8d
0x140002db6  mov     [rsp+38h+var_10], rcx
0x140002dbb  mov     [rcx+0Ch], eax
0x140002dbe  mov     rcx, cs:ServiceCtrlGuid_Context
0x140002dc5  mov     [rsp+38h+var_18], r9d
0x140002dca  xor     r9d, r9d
0x140002dcd  call    cs:__imp_EtwEventWriteTransfer
0x140002dd4  nop     dword ptr [rax+rax+00h]
0x140002dd9  add     rsp, 38h
0x140002ddd  retn
```
