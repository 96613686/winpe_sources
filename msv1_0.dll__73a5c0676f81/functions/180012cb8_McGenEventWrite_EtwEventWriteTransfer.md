# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180012cb8`
- end: `0x180012d0a`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012974`
- `0x180012bd8`

## callees

- `0x180012cb8`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180012cf1`
- `ntdll!EtwEventWriteTransfer` at `0x180012cf1`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180086198;
  if ( qword_180086198 )
  {
    *(_QWORD *)a5 = qword_180086198;
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
  return EtwEventWriteTransfer(ETW_LOG_DPAPI_PROVIDER_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180012cb8  sub     rsp, 38h
0x180012cbc  mov     rcx, cs:qword_180086198
0x180012cc3  mov     rax, [rsp+38h+arg_20]
0x180012cc8  test    rcx, rcx
0x180012ccb  jnz     short loc_180012CFC
0x180012ccd  mov     [rax], rcx
0x180012cd0  xor     r8d, r8d
0x180012cd3  mov     [rax+8], ecx
0x180012cd6  mov     [rax+0Ch], r8d
0x180012cda  xor     r8d, r8d
0x180012cdd  mov     rcx, cs:ETW_LOG_DPAPI_PROVIDER_Context
0x180012ce4  mov     [rsp+38h+var_10], rax
0x180012ce9  mov     [rsp+38h+var_18], r9d
0x180012cee  xor     r9d, r9d
0x180012cf1  call    cs:__imp_EtwEventWriteTransfer
0x180012cf7  add     rsp, 38h
0x180012cfb  retn
0x180012cfc  mov     [rax], rcx
0x180012cff  mov     r8d, 2
0x180012d05  movzx   ecx, word ptr [rcx]
0x180012d08  jmp     short loc_180012CD3
```
