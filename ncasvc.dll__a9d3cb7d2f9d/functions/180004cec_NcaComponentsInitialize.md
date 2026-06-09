# NcaComponentsInitialize

- ea: `0x180004cec`
- end: `0x180004dac`
- name: `NcaComponentsInitialize`
- size: `192`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800026d0`
- `0x180004400`

## callees

- `0x1800033bc`
- `0x180004cec`
- `0x180004db4`
- `0x180004f04`
- `0x180004f34`
- `0x18001e010`

## string_xrefs

- `0x180004d4a`: `NcaComponentsInitialize`
- `0x180004d90`: `NcaComponentsInitialize`

## pseudocode

```c
__int64 __fastcall NcaComponentsInitialize(unsigned int a1, __int64 a2)
{
  unsigned int v4; // ebx
  unsigned int i; // edi
  int v6; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  for ( i = 0; i < a1; ++i )
  {
    v6 = (*(__int64 (**)(void))(a2 + 16LL * i))();
    v4 = v6;
    if ( v6 < 0 )
    {
      NcaReportReturnError("NcaComponentsInitialize", (unsigned int)v6);
      NcaComponentsShutdown(i, a2);
      break;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids, v4);
  if ( (v4 & 0x80000000) != 0 )
    return (unsigned int)NcaReportReturnError("NcaComponentsInitialize", v4);
  return v4;
}

```

## disassembly

```asm
0x180004cec  push    rbx
0x180004cee  push    rbp
0x180004cef  push    rsi
0x180004cf0  push    rdi
0x180004cf1  push    r14
0x180004cf3  sub     rsp, 20h
0x180004cf7  mov     rsi, rdx
0x180004cfa  mov     ebp, ecx
0x180004cfc  xor     ebx, ebx
0x180004cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d05  lea     r14, WPP_GLOBAL_Control
0x180004d0c  cmp     rcx, r14
0x180004d0f  jz      short loc_180004D2A
0x180004d11  test    byte ptr [rcx+1Ch], 8
0x180004d15  jz      short loc_180004D2A
0x180004d17  mov     rcx, [rcx+10h]
0x180004d1b  lea     edx, [rbx+2Bh]
0x180004d1e  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004d25  call    WPP_SF_
0x180004d2a  xor     edi, edi
0x180004d2c  cmp     edi, ebp
0x180004d2e  jnb     short loc_180004D60
0x180004d30  mov     eax, edi
0x180004d32  add     rax, rax
0x180004d35  mov     rax, [rsi+rax*8]
0x180004d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3e  mov     ebx, eax
0x180004d40  test    eax, eax
0x180004d42  js      short loc_180004D48
0x180004d44  inc     edi
0x180004d46  jmp     short loc_180004D2C
0x180004d48  mov     edx, eax
0x180004d4a  lea     rcx, aNcacomponentsi; "NcaComponentsInitialize"
0x180004d51  call    NcaReportReturnError
0x180004d56  mov     rdx, rsi
0x180004d59  mov     ecx, edi
0x180004d5b  call    NcaComponentsShutdown
0x180004d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d67  cmp     rcx, r14
0x180004d6a  jz      short loc_180004D8A
0x180004d6c  test    byte ptr [rcx+1Ch], 8
0x180004d70  jz      short loc_180004D8A
0x180004d72  mov     rcx, [rcx+10h]
0x180004d76  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004d7d  mov     edx, 2Ch ; ','
0x180004d82  mov     r9d, ebx
0x180004d85  call    WPP_SF_d
0x180004d8a  test    ebx, ebx
0x180004d8c  jns     short loc_180004D9E
0x180004d8e  mov     edx, ebx
0x180004d90  lea     rcx, aNcacomponentsi; "NcaComponentsInitialize"
0x180004d97  call    NcaReportReturnError
0x180004d9c  mov     ebx, eax
0x180004d9e  mov     eax, ebx
0x180004da0  add     rsp, 20h
0x180004da4  pop     r14
0x180004da6  pop     rdi
0x180004da7  pop     rsi
0x180004da8  pop     rbp
0x180004da9  pop     rbx
0x180004daa  retn
```
