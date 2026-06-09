# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180014cbc`
- end: `0x180014d0e`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014d14`
- `0x18001bf24`
- `0x180027ba0`
- `0x180027c5c`

## callees

- `0x180014cbc`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180014d03`
- `ntdll!EtwEventWriteTransfer` at `0x180014d03`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180052078;
  if ( qword_180052078 )
  {
    *(_QWORD *)a5 = qword_180052078;
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
  return EtwEventWriteTransfer(DOT3SVC_EVT_GUID_Context, a2, 0);
}

```

## disassembly

```asm
0x180014cbc  sub     rsp, 38h
0x180014cc0  mov     rcx, cs:qword_180052078
0x180014cc7  mov     rax, [rsp+38h+arg_20]
0x180014ccc  test    rcx, rcx
0x180014ccf  jnz     short loc_180014CD9
0x180014cd1  mov     [rax], rcx
0x180014cd4  xor     r8d, r8d
0x180014cd7  jmp     short loc_180014CE5
0x180014cd9  mov     [rax], rcx
0x180014cdc  mov     r8d, 2
0x180014ce2  movzx   ecx, word ptr [rcx]
0x180014ce5  mov     [rax+8], ecx
0x180014ce8  mov     [rax+0Ch], r8d
0x180014cec  xor     r8d, r8d
0x180014cef  mov     rcx, cs:DOT3SVC_EVT_GUID_Context
0x180014cf6  mov     [rsp+38h+var_10], rax
0x180014cfb  mov     [rsp+38h+var_18], r9d
0x180014d00  xor     r9d, r9d
0x180014d03  call    cs:__imp_EtwEventWriteTransfer
0x180014d09  add     rsp, 38h
0x180014d0d  retn
```
