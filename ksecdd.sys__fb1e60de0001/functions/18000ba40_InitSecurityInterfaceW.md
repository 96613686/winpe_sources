# InitSecurityInterfaceW

- ea: `0x18000ba40`
- end: `0x18000ba91`
- name: `InitSecurityInterfaceW`
- size: `81`
- prototype: `PSecurityFunctionTableW __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001a68`
- `0x180007bd8`
- `0x18000ba40`

## pseudocode

```c
PSecurityFunctionTableW __stdcall InitSecurityInterfaceW()
{
  int v0; // eax

  v0 = IsOkayToExec();
  if ( v0 >= 0 )
    return &SecTable;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, WPP_0ebe48186e1433b1f5fd0d9fb5800d5f_Traceguids, (unsigned int)v0);
  return 0;
}

```

## disassembly

```asm
0x18000ba40  sub     rsp, 28h
0x18000ba44  call    IsOkayToExec
0x18000ba49  test    eax, eax
0x18000ba4b  jns     short loc_18000BA84
0x18000ba4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba54  lea     rdx, WPP_GLOBAL_Control
0x18000ba5b  cmp     rcx, rdx
0x18000ba5e  jz      short loc_18000BA80
0x18000ba60  mov     edx, [rcx+2Ch]
0x18000ba63  test    dl, 1
0x18000ba66  jz      short loc_18000BA80
0x18000ba68  mov     rcx, [rcx+18h]
0x18000ba6c  lea     r8, WPP_0ebe48186e1433b1f5fd0d9fb5800d5f_Traceguids
0x18000ba73  mov     edx, 0Bh
0x18000ba78  mov     r9d, eax
0x18000ba7b  call    WPP_SF_D
0x18000ba80  xor     eax, eax
0x18000ba82  jmp     short loc_18000BA8B
0x18000ba84  lea     rax, ?SecTable@@3U_SECURITY_FUNCTION_TABLE_W@@A; _SECURITY_FUNCTION_TABLE_W SecTable
0x18000ba8b  add     rsp, 28h
0x18000ba8f  retn
```
