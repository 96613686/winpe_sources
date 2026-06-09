# CNG_GetBCryptHandle

- ea: `0x180005fa0`
- end: `0x180006084`
- name: `CNG_GetBCryptHandle`
- size: `228`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004454`
- `0x180006a70`
- `0x18001c690`
- `0x18001eb38`
- `0x18001ee20`

## callees

- `0x180005fa0`
- `0x18000d02c`
- `0x18000e120`
- `0x180015ef8`

## string_xrefs

- `0x18000602f`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`
- `0x18000606a`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`

## pseudocode

```c
__int64 __fastcall CNG_GetBCryptHandle(char *a1, _QWORD *a2)
{
  __int64 v3; // rcx
  unsigned __int16 *v5; // r8
  int v6; // edx
  int v7; // eax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  unsigned int v11; // eax

  v3 = 0;
  do
  {
    v5 = (unsigned __int16 *)a1;
    do
    {
      v6 = *(unsigned __int16 *)((char *)v5 + (char *)off_1800210A0[v3] - a1);
      v7 = *v5 - v6;
      if ( v7 )
        break;
      ++v5;
    }
    while ( v6 );
    if ( !v7 )
    {
      v8 = (unsigned int)v3;
      if ( qword_18002ADC0[v3] || (v11 = I_OpenBCryptAlgHandle(v3), (v9 = v11) == 0) )
      {
        v9 = 0;
        *a2 = qword_18002ADC0[v8];
      }
      else
      {
        DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c", 106);
      }
      return v9;
    }
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 0x2B );
  v9 = -1073741275;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
      (unsigned int)"Status",
      37,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
      94);
  return v9;
}

```

## disassembly

```asm
0x180005fa0  push    rbx
0x180005fa2  push    rsi
0x180005fa3  push    rdi
0x180005fa4  push    r14
0x180005fa6  sub     rsp, 48h
0x180005faa  mov     r10, rcx
0x180005fad  lea     r14, __ImageBase
0x180005fb4  xor     ecx, ecx
0x180005fb6  mov     rsi, rdx
0x180005fb9  mov     r9, ds:rva off_1800210A0[r14+rcx*8]; "AES" ...
0x180005fc1  mov     r8, r10
0x180005fc4  sub     r9, r10
0x180005fc7  movzx   eax, word ptr [r8]
0x180005fcb  movzx   edx, word ptr [r8+r9]
0x180005fd0  sub     eax, edx
0x180005fd2  jnz     short loc_180005FDC
0x180005fd4  add     r8, 2
0x180005fd8  test    edx, edx
0x180005fda  jnz     short loc_180005FC7
0x180005fdc  test    eax, eax
0x180005fde  jnz     short loc_180006006
0x180005fe0  cmp     rva qword_18002ADC0[r14+rcx*8], 0
0x180005fe9  mov     edi, ecx
0x180005feb  jz      short loc_180006059
0x180005fed  mov     rax, rva qword_18002ADC0[r14+rdi*8]
0x180005ff5  xor     ebx, ebx
0x180005ff7  mov     [rsi], rax
0x180005ffa  mov     eax, ebx
0x180005ffc  add     rsp, 48h
0x180006000  pop     r14
0x180006002  pop     rdi
0x180006003  pop     rsi
0x180006004  pop     rbx
0x180006005  retn
0x180006006  inc     ecx
0x180006008  cmp     ecx, 2Bh ; '+'
0x18000600b  jb      short loc_180005FB9
0x18000600d  mov     ebx, 0C0000225h
0x180006012  mov     rcx, cs:WPP_GLOBAL_Control
0x180006019  lea     rax, WPP_GLOBAL_Control
0x180006020  cmp     rcx, rax
0x180006023  jz      short loc_180005FFA
0x180006025  test    byte ptr [rcx+1Ch], 1
0x180006029  jz      short loc_180005FFA
0x18000602b  mov     rcx, [rcx+10h]
0x18000602f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006036  mov     [rsp+68h+var_38], 5Eh ; '^'
0x18000603e  lea     r9, aStatus; "Status"
0x180006045  mov     [rsp+68h+var_40], r8
0x18000604a  mov     [rsp+68h+var_48], 0C0000225h
0x180006052  call    WPP_SF_sDsd
0x180006057  jmp     short loc_180005FFA
0x180006059  call    I_OpenBCryptAlgHandle
0x18000605e  mov     ebx, eax
0x180006060  test    eax, eax
0x180006062  jz      short loc_180005FED
0x180006064  mov     r9d, 6Ah ; 'j'
0x18000606a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006071  lea     rdx, aStatus; "Status"
0x180006078  mov     ecx, eax
0x18000607a  call    DebugTraceError
0x18000607f  jmp     loc_180005FFA
```
