# CPalettePacker::DecodePalette(HPALETTE__ * *,uchar *,uint)

- ea: `0x180147530`
- end: `0x18014775a`
- name: `?DecodePalette@CPalettePacker@@QEAAJPEAPEAUHPALETTE__@@PEAEI@Z`
- size: `554`
- prototype: `__int64 __fastcall(CPalettePacker *this, HPALETTE *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18013f438`

## callees

- `0x1800091a8`
- `0x180059838`
- `0x1800598d0`
- `0x180147530`
- `0x1801479a4`
- `0x18014c328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801476c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801476c8`
- `RDPBASE!TSAlloc` at `0x18014763d`
- `RDPBASE!TSAlloc` at `0x18014763d`
- `RDPBASE!TSFree` at `0x1801476e4`
- `RDPBASE!TSFree` at `0x1801476e4`
- `GDI32!CreatePalette` at `0x1801476ba`
- `GDI32!CreatePalette` at `0x1801476ba`
- `GDI32!DeleteObject` at `0x180147740`
- `GDI32!DeleteObject` at `0x180147740`

## pseudocode

```c
__int64 __fastcall CPalettePacker::DecodePalette(
        CPalettePacker *this,
        HPALETTE *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  LOGPALETTE *v15; // rax
  LOGPALETTE *v16; // rsi
  unsigned int v17; // eax
  HPALETTE Palette; // rax
  signed int LastError; // eax

  *a2 = 0;
  if ( a4 < 4 )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 15;
LABEL_33:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids,
        CurrentThreadActivityIdPrefix);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v9 = a4 >> 2;
  v10 = 4LL * ((a4 >> 2) - 1);
  if ( v10 > 0xFFFFFFFF )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 16;
      goto LABEL_33;
    }
LABEL_34:
    if ( *a2 )
    {
      DeleteObject(*a2);
      *a2 = 0;
    }
    return v6;
  }
  v11 = v10 + 8;
  if ( v10 + 8 < v10 || v11 < 8 )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 17;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddi(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v12, v9, v11);
  }
  v15 = (LOGPALETTE *)TSAlloc(v11);
  v16 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids,
        v17,
        (__int64)"LOGPALETTE");
    }
    v6 = -2147024882;
    goto LABEL_34;
  }
  v15->palVersion = 768;
  v15->palNumEntries = v9;
  memcpy_0(v15->palPalEntry, a3, 4LL * v9);
  Palette = CreatePalette(v16);
  *a2 = Palette;
  if ( Palette )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  TSFree(v16);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_34;
  return v6;
}

```

## disassembly

```asm
0x180147530  push    rbx
0x180147532  push    rbp
0x180147533  push    rsi
0x180147534  push    rdi
0x180147535  push    r14
0x180147537  sub     rsp, 30h
0x18014753b  mov     qword ptr [rdx], 0
0x180147542  mov     ebx, r9d
0x180147545  mov     rbp, r8
0x180147548  mov     r14, rdx
0x18014754b  cmp     r9d, 4
0x18014754f  jnb     short loc_180147590
0x180147551  mov     ebx, 834503E9h
0x180147556  mov     rax, cs:WPP_GLOBAL_Control
0x18014755d  lea     rdi, WPP_GLOBAL_Control
0x180147564  cmp     rax, rdi
0x180147567  jz      loc_180147738
0x18014756d  test    byte ptr [rax+1Ch], 1
0x180147571  jz      loc_180147738
0x180147577  cmp     byte ptr [rax+19h], 2
0x18014757b  jb      loc_180147738
0x180147581  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180147586  mov     edx, 0Fh
0x18014758b  jmp     loc_18014771E
0x180147590  shr     ebx, 2
0x180147593  mov     eax, 0FFFFFFFFh
0x180147598  lea     ecx, [rbx-1]
0x18014759b  shl     rcx, 2
0x18014759f  cmp     rcx, rax
0x1801475a2  jbe     short loc_1801475E3
0x1801475a4  mov     ebx, 834503E9h
0x1801475a9  mov     rax, cs:WPP_GLOBAL_Control
0x1801475b0  lea     rdi, WPP_GLOBAL_Control
0x1801475b7  cmp     rax, rdi
0x1801475ba  jz      loc_180147738
0x1801475c0  test    byte ptr [rax+1Ch], 1
0x1801475c4  jz      loc_180147738
0x1801475ca  cmp     byte ptr [rax+19h], 2
0x1801475ce  jb      loc_180147738
0x1801475d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801475d9  mov     edx, 10h
0x1801475de  jmp     loc_18014771E
0x1801475e3  lea     rsi, [rcx+8]
0x1801475e7  cmp     rsi, rcx
0x1801475ea  jb      loc_1801476F0
0x1801475f0  cmp     rsi, 8
0x1801475f4  jb      loc_1801476F0
0x1801475fa  mov     rax, cs:WPP_GLOBAL_Control
0x180147601  lea     rdi, WPP_GLOBAL_Control
0x180147608  cmp     rax, rdi
0x18014760b  jz      short loc_18014763A
0x18014760d  test    byte ptr [rax+1Ch], 1
0x180147611  jz      short loc_18014763A
0x180147613  cmp     byte ptr [rax+19h], 5
0x180147617  jb      short loc_18014763A
0x180147619  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014761e  mov     rcx, cs:WPP_GLOBAL_Control
0x180147625  mov     r9d, eax
0x180147628  mov     [rsp+58h+var_30], rsi
0x18014762d  mov     dword ptr [rsp+58h+var_38], ebx
0x180147631  mov     rcx, [rcx+10h]
0x180147635  call    WPP_SF_Ddi
0x18014763a  mov     rcx, rsi
0x18014763d  call    cs:__imp_TSAlloc
0x180147643  mov     rsi, rax
0x180147646  test    rax, rax
0x180147649  jnz     short loc_18014769B
0x18014764b  mov     rax, cs:WPP_GLOBAL_Control
0x180147652  cmp     rax, rdi
0x180147655  jz      short loc_180147691
0x180147657  test    byte ptr [rax+1Ch], 8
0x18014765b  jz      short loc_180147691
0x18014765d  cmp     byte ptr [rax+19h], 2
0x180147661  jb      short loc_180147691
0x180147663  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180147668  lea     rcx, aLogpalette; "LOGPALETTE"
0x18014766f  mov     r9d, eax
0x180147672  mov     [rsp+58h+var_38], rcx
0x180147677  lea     edx, [rsi+13h]
0x18014767a  mov     rcx, cs:WPP_GLOBAL_Control
0x180147681  lea     r8, WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids
0x180147688  mov     rcx, [rcx+10h]
0x18014768c  call    WPP_SF_Ds
0x180147691  mov     ebx, 8007000Eh
0x180147696  jmp     loc_180147738
0x18014769b  mov     r8d, ebx
0x18014769e  lea     rcx, [rax+4]; void *
0x1801476a2  shl     r8, 2; Size
0x1801476a6  mov     rdx, rbp; Src
0x1801476a9  mov     word ptr [rax], 300h
0x1801476ae  mov     [rax+2], bx
0x1801476b2  call    memcpy_0
0x1801476b7  mov     rcx, rsi; plpal
0x1801476ba  call    cs:__imp_CreatePalette
0x1801476c0  mov     [r14], rax
0x1801476c3  test    rax, rax
0x1801476c6  jnz     short loc_1801476DF
0x1801476c8  call    cs:__imp_GetLastError
0x1801476ce  mov     ebx, eax
0x1801476d0  test    eax, eax
0x1801476d2  jle     short loc_1801476E1
0x1801476d4  movzx   ebx, ax
0x1801476d7  or      ebx, 80070000h
0x1801476dd  jmp     short loc_1801476E1
0x1801476df  xor     ebx, ebx
0x1801476e1  mov     rcx, rsi
0x1801476e4  call    cs:__imp_?TSFree@@YAXPEAX@Z; TSFree(void *)
0x1801476ea  test    ebx, ebx
0x1801476ec  jns     short loc_18014774D
0x1801476ee  jmp     short loc_180147738
0x1801476f0  mov     ebx, 834503E9h
0x1801476f5  mov     rax, cs:WPP_GLOBAL_Control
0x1801476fc  lea     rdi, WPP_GLOBAL_Control
0x180147703  cmp     rax, rdi
0x180147706  jz      short loc_180147738
0x180147708  test    byte ptr [rax+1Ch], 1
0x18014770c  jz      short loc_180147738
0x18014770e  cmp     byte ptr [rax+19h], 2
0x180147712  jb      short loc_180147738
0x180147714  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180147719  mov     edx, 11h
0x18014771e  mov     rcx, cs:WPP_GLOBAL_Control
0x180147725  lea     r8, WPP_e1e4df426ec7323cceab6958fb61bb06_Traceguids
0x18014772c  mov     r9d, eax
0x18014772f  mov     rcx, [rcx+10h]
0x180147733  call    WPP_SF_d
0x180147738  mov     rcx, [r14]; ho
0x18014773b  test    rcx, rcx
0x18014773e  jz      short loc_18014774D
0x180147740  call    cs:__imp_DeleteObject
0x180147746  mov     qword ptr [r14], 0
0x18014774d  mov     eax, ebx
0x18014774f  add     rsp, 30h
0x180147753  pop     r14
0x180147755  pop     rdi
0x180147756  pop     rsi
0x180147757  pop     rbp
0x180147758  pop     rbx
0x180147759  retn
```
