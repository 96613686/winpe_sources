# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180005b24`
- end: `0x180005b76`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005b7c`
- `0x180073ed8`
- `0x1800974b0`
- `0x1800a3c88`
- `0x1800bc2d0`
- `0x1800bc354`
- `0x1800bc3d8`
- `0x1800cc27c`
- `0x1800cc318`
- `0x1800ce724`

## callees

- `0x180005b24`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180005b5d`
- `ntdll!EtwEventWriteTransfer` at `0x180005b5d`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180228288;
  if ( qword_180228288 )
  {
    *(_QWORD *)a5 = qword_180228288;
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
  return EtwEventWriteTransfer(Direct3D11EtwProviderGuid_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180005b24  sub     rsp, 38h
0x180005b28  mov     rcx, cs:qword_180228288
0x180005b2f  mov     rax, [rsp+38h+arg_20]
0x180005b34  test    rcx, rcx
0x180005b37  jnz     short loc_180005B68
0x180005b39  mov     [rax], rcx
0x180005b3c  xor     r8d, r8d
0x180005b3f  mov     [rax+8], ecx
0x180005b42  mov     [rax+0Ch], r8d
0x180005b46  xor     r8d, r8d
0x180005b49  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x180005b50  mov     [rsp+38h+var_10], rax
0x180005b55  mov     [rsp+38h+var_18], r9d
0x180005b5a  xor     r9d, r9d
0x180005b5d  call    cs:__imp_EtwEventWriteTransfer
0x180005b63  add     rsp, 38h
0x180005b67  retn
0x180005b68  mov     [rax], rcx
0x180005b6b  mov     r8d, 2
0x180005b71  movzx   ecx, word ptr [rcx]
0x180005b74  jmp     short loc_180005B3F
```
