# RasDisconnect

- ea: `0x180006144`
- end: `0x180006273`
- name: `RasDisconnect`
- size: `303`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ee0`
- `0x180003fa0`

## callees

- `0x180005778`
- `0x180006144`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800061d2`
- `msvcrt!_wcsicmp` at `0x1800061d2`
- `KERNEL32!LocalFree` at `0x180006246`
- `KERNEL32!LocalFree` at `0x180006246`
- `RASAPI32!RasHangUpW` at `0x1800061e1`
- `RASAPI32!RasHangUpW` at `0x1800061e1`
- `rtutils!TracePrintfExA` at `0x180006219`
- `rtutils!TracePrintfExA` at `0x180006219`

## pseudocode

```c
__int64 __fastcall RasDisconnect(wchar_t *String2)
{
  int v3; // eax
  _BYTE *v4; // rdi
  int v5; // ebx
  unsigned int v6; // ecx
  unsigned int v7; // ebp
  int v8; // r12d
  __int64 v9; // r14
  DWORD v10; // eax
  DWORD v11; // r15d
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  hMem = 0;
  v12 = 0;
  if ( !String2 )
    return 2147942487LL;
  v3 = EnumerateRasConnections(&hMem, &v12);
  v4 = hMem;
  v5 = v3;
  if ( !v3 )
  {
    v6 = v12;
    if ( !v12 )
      goto LABEL_15;
    v7 = 0;
    v8 = 1;
    do
    {
      v9 = 1388LL * v7;
      if ( (v4[v9 + 1360] & 1) != 0 )
      {
        if ( !_wcsicmp((const wchar_t *)&v4[v9 + 12], String2) )
        {
          v10 = RasHangUpW(*(HRASCONN *)&v4[v9 + 4]);
          v11 = v10;
          if ( v10 )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "RasHangUp failed for Entry:%S, SubEntry:%d and returned %d\n",
                (const wchar_t *)&v4[v9 + 12],
                *(_DWORD *)&v4[v9 + 1340],
                v10);
            v8 = 0;
            v5 = v11;
          }
        }
        v6 = v12;
      }
      ++v7;
    }
    while ( v7 < v6 );
    if ( v8 )
LABEL_15:
      *((_DWORD *)String2 + 130) = 0;
  }
  if ( v4 )
    LocalFree(v4);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006144  mov     [rsp+arg_10], rbx
0x180006149  push    rbp
0x18000614a  push    rsi
0x18000614b  push    rdi
0x18000614c  push    r12
0x18000614e  push    r13
0x180006150  push    r14
0x180006152  push    r15
0x180006154  sub     rsp, 30h
0x180006158  mov     [rsp+68h+hMem], 0
0x180006161  mov     rsi, rcx
0x180006164  mov     [rsp+68h+arg_0], 0
0x18000616c  test    rcx, rcx
0x18000616f  jnz     short loc_18000617B
0x180006171  mov     eax, 80070057h
0x180006176  jmp     loc_18000625B
0x18000617b  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x180006180  lea     rcx, [rsp+68h+hMem]; struct tagRASCONNW **
0x180006185  call    ?EnumerateRasConnections@@YAKPEAPEAUtagRASCONNW@@PEAK@Z; EnumerateRasConnections(tagRASCONNW * *,ulong *)
0x18000618a  mov     rdi, [rsp+68h+hMem]
0x18000618f  mov     ebx, eax
0x180006191  test    eax, eax
0x180006193  jnz     loc_18000623E
0x180006199  mov     ecx, [rsp+68h+arg_0]
0x18000619d  test    ecx, ecx
0x18000619f  jz      loc_180006234
0x1800061a5  xor     ebp, ebp
0x1800061a7  lea     r12d, [rax+1]
0x1800061ab  test    ecx, ecx
0x1800061ad  jz      loc_180006234
0x1800061b3  mov     eax, ebp
0x1800061b5  imul    r14, rax, 56Ch
0x1800061bc  test    byte ptr [r14+rdi+550h], 1
0x1800061c5  jz      short loc_180006229
0x1800061c7  lea     r13, [r14+rdi]
0x1800061cb  mov     rdx, rsi; String2
0x1800061ce  lea     rcx, [r13+0Ch]; String1
0x1800061d2  call    cs:__imp__wcsicmp
0x1800061d8  test    eax, eax
0x1800061da  jnz     short loc_180006225
0x1800061dc  mov     rcx, [r14+rdi+4]; HRASCONN
0x1800061e1  call    cs:__imp_RasHangUpW
0x1800061e7  mov     r15d, eax
0x1800061ea  test    eax, eax
0x1800061ec  jz      short loc_180006225
0x1800061ee  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800061f4  cmp     ecx, 0FFFFFFFFh
0x1800061f7  jz      short loc_18000621F
0x1800061f9  mov     edx, [r14+rdi+53Ch]
0x180006201  lea     r9, [r13+0Ch]
0x180006205  mov     [rsp+68h+var_40], eax
0x180006209  lea     r8, aRashangupFaile; "RasHangUp failed for Entry:%S, SubEntry"...
0x180006210  mov     [rsp+68h+var_48], edx
0x180006214  mov     edx, 0Ch; dwFlags
0x180006219  call    cs:__imp_TracePrintfExA
0x18000621f  xor     r12d, r12d
0x180006222  mov     ebx, r15d
0x180006225  mov     ecx, [rsp+68h+arg_0]
0x180006229  inc     ebp
0x18000622b  cmp     ebp, ecx
0x18000622d  jb      short loc_1800061B3
0x18000622f  test    r12d, r12d
0x180006232  jz      short loc_18000623E
0x180006234  mov     dword ptr [rsi+208h], 0
0x18000623e  test    rdi, rdi
0x180006241  jz      short loc_18000624C
0x180006243  mov     rcx, rdi; hMem
0x180006246  call    cs:__imp_LocalFree
0x18000624c  test    ebx, ebx
0x18000624e  jle     short loc_180006259
0x180006250  movzx   ebx, bx
0x180006253  or      ebx, 80070000h
0x180006259  mov     eax, ebx
0x18000625b  mov     rbx, [rsp+68h+arg_10]
0x180006263  add     rsp, 30h
0x180006267  pop     r15
0x180006269  pop     r14
0x18000626b  pop     r13
0x18000626d  pop     r12
0x18000626f  pop     rdi
0x180006270  pop     rsi
0x180006271  pop     rbp
0x180006272  retn
```
