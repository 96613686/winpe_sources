# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180008300`
- end: `0x180008359`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004920`
- `0x180006c60`
- `0x180007f60`
- `0x180008000`
- `0x180008360`
- `0x1800083b0`
- `0x18000841c`
- `0x18001199c`
- `0x1800146ac`
- `0x1800193c0`
- `0x180019d00`
- `0x18001ac4c`
- `0x18001b234`
- `0x180029e7c`
- `0x18002c4f8`
- `0x18002f15c`
- `0x18002f234`
- `0x18002f2c8`
- `0x18002f348`
- `0x18002f3f4`
- `0x18003576c`
- `0x180035868`
- `0x1800359bc`
- `0x180035ab0`
- `0x18003ae5c`

## callees

- `0x180008300`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180008339`
- `ntdll!EtwEventWriteTransfer` at `0x180008339`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18004C0A8;
  if ( qword_18004C0A8 )
  {
    *(_QWORD *)a5 = qword_18004C0A8;
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
0x180008300  sub     rsp, 38h
0x180008304  mov     rcx, cs:qword_18004C0A8
0x18000830b  mov     rax, [rsp+38h+arg_20]
0x180008310  test    rcx, rcx
0x180008313  jnz     short loc_18000834B
0x180008315  mov     [rax], rcx
0x180008318  xor     r8d, r8d
0x18000831b  mov     [rax+8], ecx
0x18000831e  mov     [rax+0Ch], r8d
0x180008322  xor     r8d, r8d
0x180008325  mov     rcx, cs:ETW_LOG_DPAPI_PROVIDER_Context
0x18000832c  mov     [rsp+38h+var_10], rax
0x180008331  mov     [rsp+38h+var_18], r9d
0x180008336  xor     r9d, r9d
0x180008339  call    cs:__imp_EtwEventWriteTransfer
0x180008340  nop     dword ptr [rax+rax+00h]
0x180008345  add     rsp, 38h
0x180008349  retn
0x18000834b  mov     [rax], rcx
0x18000834e  mov     r8d, 2
0x180008354  movzx   ecx, word ptr [rcx]
0x180008357  jmp     short loc_18000831B
```
