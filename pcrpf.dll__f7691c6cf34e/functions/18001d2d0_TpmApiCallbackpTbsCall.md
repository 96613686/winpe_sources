# TpmApiCallbackpTbsCall

- ea: `0x18001d2d0`
- end: `0x18001d3cc`
- name: `TpmApiCallbackpTbsCall`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d2d0`

## import_xrefs

- `tbs!Tbsip_Submit_Command_NonBlocking` at `0x18001d3af`
- `tbs!Tbsip_Submit_Command_NonBlocking` at `0x18001d3af`

## pseudocode

```c
__int64 __fastcall TpmApiCallbackpTbsCall(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rcx
  __int64 v8; // r8

  if ( !a1 )
    return 2150170890LL;
  if ( !a3 )
    return 2150170884LL;
  if ( !a4 )
    return 2150170883LL;
  v7 = a1 ^ 0x1D9C0E3A;
  if ( !a5 )
    return 2150170883LL;
  if ( !v7 )
    return 2150170884LL;
  if ( *(_DWORD *)v7 != 541278548 )
    return 2150170901LL;
  if ( ((*(_DWORD *)(v7 + 4) - 24) & 0xFFFFFFF7) != 0 )
    return 2150170901LL;
  if ( *(_DWORD *)(v7 + 8) )
    return 2150170901LL;
  v8 = *(unsigned int *)(v7 + 12);
  if ( (unsigned int)v8 < 0x80000000 )
    return Tbsip_Submit_Command_NonBlocking(*(_QWORD *)(v7 + 16), 0, v8, a3, a2, a5, a4);
  else
    return 2150170901LL;
}

```

## disassembly

```asm
0x18001d2d0  sub     rsp, 68h
0x18001d2d4  mov     r10, r8
0x18001d2d7  mov     r11d, edx
0x18001d2da  test    rcx, rcx
0x18001d2dd  jnz     short loc_18001D2E9
0x18001d2df  mov     eax, 8029010Ah
0x18001d2e4  jmp     loc_18001D3C6
0x18001d2e9  test    r10, r10
0x18001d2ec  jnz     short loc_18001D2F8
0x18001d2ee  mov     eax, 80290104h
0x18001d2f3  jmp     loc_18001D3C6
0x18001d2f8  test    r9, r9
0x18001d2fb  jnz     short loc_18001D307
0x18001d2fd  mov     eax, 80290103h
0x18001d302  jmp     loc_18001D3C6
0x18001d307  xor     rcx, 1D9C0E3Ah
0x18001d30e  mov     rdx, [rsp+68h+arg_20]
0x18001d316  test    rdx, rdx
0x18001d319  jz      short loc_18001D2FD
0x18001d31b  test    rcx, rcx
0x18001d31e  jnz     short loc_18001D32E
0x18001d320  mov     eax, 80290104h
0x18001d325  mov     [rsp+68h+var_28], eax
0x18001d329  jmp     loc_18001D3C6
0x18001d32e  cmp     dword ptr [rcx], 20434154h
0x18001d334  jz      short loc_18001D344
0x18001d336  mov     eax, 80290115h
0x18001d33b  mov     [rsp+68h+var_28], eax
0x18001d33f  jmp     loc_18001D3C6
0x18001d344  mov     eax, [rcx+4]
0x18001d347  sub     eax, 18h
0x18001d34a  test    eax, 0FFFFFFF7h
0x18001d34f  jz      short loc_18001D35C
0x18001d351  mov     eax, 80290115h
0x18001d356  mov     [rsp+68h+var_28], eax
0x18001d35a  jmp     short loc_18001D3C6
0x18001d35c  cmp     dword ptr [rcx+8], 0
0x18001d360  jz      short loc_18001D36D
0x18001d362  mov     eax, 80290115h
0x18001d367  mov     [rsp+68h+var_28], eax
0x18001d36b  jmp     short loc_18001D3C6
0x18001d36d  mov     r8d, [rcx+0Ch]
0x18001d371  cmp     r8d, 80000000h
0x18001d378  jb      short loc_18001D385
0x18001d37a  mov     eax, 80290115h
0x18001d37f  mov     [rsp+68h+var_28], eax
0x18001d383  jmp     short loc_18001D3C6
0x18001d385  mov     rcx, [rcx+10h]
0x18001d389  mov     [rsp+68h+var_18], rcx
0x18001d38e  mov     [rsp+68h+var_24], 0
0x18001d396  mov     [rsp+68h+var_20], r8d
0x18001d39b  mov     [rsp+68h+var_38], r9
0x18001d3a0  mov     [rsp+68h+var_40], rdx
0x18001d3a5  mov     [rsp+68h+var_48], r11d
0x18001d3aa  mov     r9, r10
0x18001d3ad  xor     edx, edx
0x18001d3af  call    cs:__imp_Tbsip_Submit_Command_NonBlocking
0x18001d3b6  nop     dword ptr [rax+rax+00h]
0x18001d3bb  jmp     short loc_18001D3C6
0x18001d3bd  mov     eax, 8029010Ah
0x18001d3c2  mov     [rsp+68h+var_28], eax
0x18001d3c6  add     rsp, 68h
0x18001d3ca  retn
0x18005789d  push    rbp
0x18005789f  sub     rsp, 40h
0x1800578a3  mov     rbp, rdx
0x1800578a6  mov     rax, [rcx]
0x1800578a9  cmp     dword ptr [rax], 0C0000005h
0x1800578af  jz      short loc_1800578C5
0x1800578b1  cmp     dword ptr [rax], 80000002h
0x1800578b7  jz      short loc_1800578C5
0x1800578b9  cmp     dword ptr [rax], 0C0000008h
0x1800578bf  jz      short loc_1800578C5
0x1800578c1  xor     eax, eax
0x1800578c3  jmp     short loc_1800578CA
0x1800578c5  mov     eax, 1
0x1800578ca  add     rsp, 40h
0x1800578ce  pop     rbp
0x1800578cf  retn
```
