# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x1400061dc`
- end: `0x1400062b0`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `69`
- callee_count: `7`
- tags: ``

## callers

- `0x140001150`
- `0x140001200`
- `0x140001270`
- `0x1400012e0`
- `0x140001350`
- `0x1400013c0`
- `0x140001430`
- `0x1400014a0`
- `0x140001510`
- `0x140001580`
- `0x1400015f0`
- `0x140001660`
- `0x1400054e8`
- `0x140005954`
- `0x140006818`
- `0x1400070f0`
- `0x140007bf8`
- `0x1400088a0`
- `0x1400090ec`
- `0x14000a610`
- `0x14000b3f8`
- `0x14000b4f4`
- `0x14000b7e0`
- `0x14000baf8`
- `0x14000c308`
- `0x14000c5cc`
- `0x14000cdb0`
- `0x14000d134`
- `0x14000d384`
- `0x14000d9a8`
- `0x14000ea0c`
- `0x14000f4f4`
- `0x1400102e0`
- `0x140010378`
- `0x14001088c`
- `0x140012cb4`
- `0x140013c8c`
- `0x140014910`
- `0x140014af0`
- `0x140014ea4`
- `0x140015b18`
- `0x140015dfc`
- `0x14001604c`
- `0x1400165b4`
- `0x140016a04`
- `0x1400176b4`
- `0x140017cb0`
- `0x1400180b8`
- `0x1400196f4`
- `0x14001a28c`

## callees

- `0x14000274e`
- `0x140005c58`
- `0x140005e1c`
- `0x140005ea0`
- `0x1400060c4`
- `0x1400061dc`
- `0x14002c40c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006256`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006256`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r15
  char *v9; // rcx
  char *v10; // rdx
  __int64 v11; // r14

  v3 = (int)a3;
  if ( !(_DWORD)a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  if ( !a2 )
    goto LABEL_16;
  v7 = ((__int64)a2 - *a1) >> 1;
  v8 = *(unsigned int *)(*a1 - 16);
  if ( (int)((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v9 = (char *)*a1;
  v10 = (char *)v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
  {
    ATL::CSimpleStringT<unsigned short,0>::CopyChars(v9, v3, a2, v3);
  }
  else if ( v11 )
  {
    if ( v9 && (v10 = &v9[2 * v7]) != 0 )
    {
      memmove_0(v9, v10, 2 * v3);
    }
    else
    {
      *(_DWORD *)_o__errno(v9, v10, a3) = 22;
      invalid_parameter_noinfo();
    }
  }
  if ( (int)v3 < 0 || (int)v3 > *(_DWORD *)(*a1 - 12) )
LABEL_16:
    ATL::AtlThrowImpl(0x80070057);
  *(_DWORD *)(*a1 - 16) = v3;
  result = 0;
  *(_WORD *)(v11 + *a1) = 0;
  return result;
}

```

## disassembly

```asm
0x1400061dc  push    rbx
0x1400061de  push    rbp
0x1400061df  push    rsi
0x1400061e0  push    rdi
0x1400061e1  push    r14
0x1400061e3  push    r15
0x1400061e5  sub     rsp, 28h
0x1400061e9  movsxd  rbx, r8d
0x1400061ec  mov     rbp, rdx
0x1400061ef  mov     rdi, rcx
0x1400061f2  test    r8d, r8d
0x1400061f5  jnz     short loc_140006209
0x1400061f7  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400061fc  add     rsp, 28h
0x140006200  pop     r15
0x140006202  pop     r14
0x140006204  pop     rdi
0x140006205  pop     rsi
0x140006206  pop     rbp
0x140006207  pop     rbx
0x140006208  retn
0x140006209  test    rbp, rbp
0x14000620c  jz      loc_1400062A5
0x140006212  mov     rax, [rcx]
0x140006215  mov     rsi, rbp
0x140006218  sub     rsi, rax
0x14000621b  mov     ecx, 1
0x140006220  sar     rsi, 1
0x140006223  sub     ecx, [rax-8]
0x140006226  mov     r15d, [rax-10h]
0x14000622a  mov     eax, [rax-0Ch]
0x14000622d  sub     eax, ebx
0x14000622f  or      ecx, eax
0x140006231  jge     short loc_14000623D
0x140006233  mov     edx, ebx
0x140006235  mov     rcx, rdi
0x140006238  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000623d  mov     rcx, [rdi]; void *
0x140006240  mov     rdx, rbx
0x140006243  lea     r14, [rbx+rbx]
0x140006247  cmp     rsi, r15
0x14000624a  ja      short loc_14000627C
0x14000624c  test    r14, r14
0x14000624f  jz      short loc_140006287
0x140006251  test    rcx, rcx
0x140006254  jnz     short loc_140006269
0x140006256  call    cs:__imp__o__errno
0x14000625c  mov     dword ptr [rax], 16h
0x140006262  call    _invalid_parameter_noinfo
0x140006267  jmp     short loc_140006287
0x140006269  lea     rdx, [rcx+rsi*2]; Src
0x14000626d  test    rdx, rdx
0x140006270  jz      short loc_140006256
0x140006272  mov     r8, r14; Size
0x140006275  call    memmove_0
0x14000627a  jmp     short loc_140006287
0x14000627c  mov     r9d, ebx
0x14000627f  mov     r8, rbp
0x140006282  call    ?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z; ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)
0x140006287  test    ebx, ebx
0x140006289  js      short loc_1400062A5
0x14000628b  mov     rax, [rdi]
0x14000628e  cmp     ebx, [rax-0Ch]
0x140006291  jg      short loc_1400062A5
0x140006293  mov     [rax-10h], ebx
0x140006296  xor     eax, eax
0x140006298  mov     rcx, [rdi]
0x14000629b  mov     [r14+rcx], ax
0x1400062a0  jmp     loc_1400061FC
0x1400062a5  mov     ecx, 80070057h; unsigned int
0x1400062aa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
