# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000dd70`
- end: `0x18000ddc9`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b00`
- `0x1800040a0`
- `0x180006230`
- `0x180006b50`
- `0x180006e40`
- `0x180007550`
- `0x180008d20`
- `0x180009340`
- `0x180009bc0`
- `0x18000a490`
- `0x18000b0e0`
- `0x18000b6a0`
- `0x18000da24`
- `0x18003a530`
- `0x18003a6b8`
- `0x18003a7ec`
- `0x18003a960`
- `0x18003ab50`
- `0x18003ae20`
- `0x18003afb0`
- `0x18003b2c8`

## callees

- `0x18000dd70`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000dda9`
- `ntdll!EtwEventWriteTransfer` at `0x18000dda9`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18007C058;
  if ( qword_18007C058 )
  {
    *(_QWORD *)a5 = qword_18007C058;
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
  return EtwEventWriteTransfer(MICROSOFT_WFP_PROVIDER_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x18000dd70  sub     rsp, 38h
0x18000dd74  mov     rcx, cs:qword_18007C058
0x18000dd7b  mov     rax, [rsp+38h+arg_20]
0x18000dd80  test    rcx, rcx
0x18000dd83  jnz     short loc_18000DDBB
0x18000dd85  mov     [rax], rcx
0x18000dd88  xor     r8d, r8d
0x18000dd8b  mov     [rax+8], ecx
0x18000dd8e  mov     [rax+0Ch], r8d
0x18000dd92  xor     r8d, r8d
0x18000dd95  mov     rcx, cs:MICROSOFT_WFP_PROVIDER_Context
0x18000dd9c  mov     [rsp+38h+var_10], rax
0x18000dda1  mov     [rsp+38h+var_18], r9d
0x18000dda6  xor     r9d, r9d
0x18000dda9  call    cs:__imp_EtwEventWriteTransfer
0x18000ddb0  nop     dword ptr [rax+rax+00h]
0x18000ddb5  add     rsp, 38h
0x18000ddb9  retn
0x18000ddbb  mov     [rax], rcx
0x18000ddbe  mov     r8d, 2
0x18000ddc4  movzx   ecx, word ptr [rcx]
0x18000ddc7  jmp     short loc_18000DD8B
```
