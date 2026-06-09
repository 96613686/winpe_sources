# SrvCryptCreateContext

- ea: `0x180005f80`
- end: `0x180006007`
- name: `SrvCryptCreateContext`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180005f80`
- `0x18000a268`

## string_xrefs

- `0x180005fc0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005ff0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptCreateContext(void *a1, __int64 *a2)
{
  int Context; // eax
  unsigned int v3; // ebx

  if ( a2 )
  {
    Context = SrvCreateContext(a1, a2);
    v3 = Context;
    if ( Context < 0 )
      DebugTraceError(
        (unsigned int)Context,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        454);
  }
  else
  {
    v3 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        189);
  }
  return v3;
}

```

## disassembly

```asm
0x180005f80  push    rbx
0x180005f82  sub     rsp, 40h
0x180005f86  test    rdx, rdx
0x180005f89  jz      short loc_180005F9E
0x180005f8b  call    SrvCreateContext
0x180005f90  mov     ebx, eax
0x180005f92  test    eax, eax
0x180005f94  js      short loc_180005FEA
0x180005f96  mov     eax, ebx
0x180005f98  add     rsp, 40h
0x180005f9c  pop     rbx
0x180005f9d  retn
0x180005f9e  mov     ebx, 80090027h
0x180005fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005faa  lea     rax, WPP_GLOBAL_Control
0x180005fb1  cmp     rcx, rax
0x180005fb4  jz      short loc_180005F96
0x180005fb6  test    byte ptr [rcx+1Ch], 1
0x180005fba  jz      short loc_180005F96
0x180005fbc  mov     rcx, [rcx+10h]
0x180005fc0  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fc7  mov     [rsp+48h+var_18], 1BDh
0x180005fcf  lea     r9, aStatus; "Status"
0x180005fd6  mov     [rsp+48h+var_20], r8
0x180005fdb  mov     [rsp+48h+var_28], 80090027h
0x180005fe3  call    WPP_SF_sDsd
0x180005fe8  jmp     short loc_180005F96
0x180005fea  mov     r9d, 1C6h
0x180005ff0  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005ff7  lea     rdx, aStatus; "Status"
0x180005ffe  mov     ecx, eax
0x180006000  call    DebugTraceError
0x180006005  jmp     short loc_180005F96
```
