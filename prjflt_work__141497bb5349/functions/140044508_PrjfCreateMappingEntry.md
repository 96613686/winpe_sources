# PrjfCreateMappingEntry

- ea: `0x140044508`
- end: `0x14004478e`
- name: `PrjfCreateMappingEntry`
- size: `646`
- prototype: `__int64 __fastcall(char *Src, int, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140045694`

## callees

- `0x14000bb80`
- `0x14000d008`
- `0x140010360`
- `0x140013588`
- `0x140044508`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044703`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044703`
- `ntoskrnl!ExAllocatePool2` at `0x14004466e`
- `ntoskrnl!ExAllocatePool2` at `0x14004466e`

## pseudocode

```c
__int64 __fastcall PrjfCreateMappingEntry(char *Src, int a2, _OWORD *a3)
{
  _OWORD *v3; // rsi
  int v4; // ebx
  int v6; // edx
  unsigned int v7; // edi
  char v8; // r10
  __int64 v9; // rdx
  void *Pool2; // rax
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  __int16 v17; // [rsp+30h] [rbp-58h]
  char v18; // [rsp+48h] [rbp-40h]
  char v19; // [rsp+58h] [rbp-30h]
  _WORD v20[2]; // [rsp+70h] [rbp-18h] BYREF
  int v21; // [rsp+74h] [rbp-14h]
  char *v22; // [rsp+78h] [rbp-10h]

  v3 = a3;
  v20[0] = *((_WORD *)Src + 1);
  v4 = a2;
  v20[1] = v20[0];
  v22 = Src + 4;
  v21 = 0;
  if ( a2 == -1 )
  {
    v6 = -1073741811;
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v8 = xmmword_14001A3D0 & 0x80;
    if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = -1;
      v18 = 53;
      v17 = 25;
LABEL_5:
      LOBYTE(v6) = v8;
      WPP_RECORDER_AND_TRACE_SF_sDdDZ(
        519,
        v6,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        7,
        v17,
        (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
        v18,
        13,
        v19,
        (__int64)v20);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( a2 && (a2 & 0xFFFFE000) != 0 )
  {
    v6 = -1073741811;
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v8 = xmmword_14001A3D0 & 0x80;
    if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = v4;
      v18 = 66;
      v17 = 26;
      goto LABEL_5;
    }
LABEL_16:
    if ( *(_QWORD *)v3 )
    {
      ExFreePoolWithTag(*(PVOID *)v3, 0x6D6E4A50u);
      *(_QWORD *)v3 = 0;
    }
    return v7;
  }
  v9 = *(unsigned __int16 *)Src;
  *a3 = 0;
  Pool2 = (void *)ExAllocatePool2(258, v9, 1835944528);
  *(_QWORD *)v3 = Pool2;
  if ( !Pool2 )
  {
    if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = BYTE2(xmmword_14001A3D0) & 0x10;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        532,
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        20,
        27,
        (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
        83);
    }
    v7 = -1073741670;
    goto LABEL_16;
  }
  memmove(Pool2, Src, *(unsigned __int16 *)Src);
  if ( (v4 & 1) != 0 )
  {
    if ( SBYTE8(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = BYTE8(xmmword_14001A3D0) & 0x80;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDDDZ(v14, v13, v15, *((_QWORD *)WPP_GLOBAL_Control + 8));
    }
    v4 = 1;
  }
  *((_DWORD *)v3 + 2) = v4;
  return 0;
}

```

## disassembly

```asm
0x140044508  mov     [rsp+arg_0], rbx
0x14004450d  mov     [rsp+arg_8], rsi
0x140044512  push    rdi
0x140044513  sub     rsp, 80h
0x14004451a  movzx   eax, word ptr [rcx+2]
0x14004451e  mov     rsi, r8
0x140044521  mov     [rsp+88h+var_18], ax
0x140044526  mov     ebx, edx
0x140044528  mov     [rsp+88h+var_16], ax
0x14004452d  lea     rax, [rcx+4]
0x140044531  mov     [rsp+88h+var_10], rax
0x140044536  mov     rdi, rcx
0x140044539  mov     [rsp+88h+var_14], 0
0x140044541  cmp     edx, 0FFFFFFFFh
0x140044544  jnz     loc_1400445E0
0x14004454a  mov     edx, 0C000000Dh
0x14004454f  mov     edi, edx
0x140044551  mov     r10b, byte ptr cs:xmmword_14001A3D0
0x140044558  lea     rax, WPP_RECORDER_INITIALIZED
0x14004455f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044566  setnz   r8b
0x14004456a  and     r10b, 80h
0x14004456e  jnz     short loc_140044579
0x140044570  test    r8b, r8b
0x140044573  jz      loc_1400446F6
0x140044579  lea     rax, [rsp+88h+var_18]
0x14004457e  mov     [rsp+88h+var_28], rax
0x140044583  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004458a  mov     dword ptr [rsp+88h+var_30], 0FFFFFFFFh
0x140044592  mov     [rsp+88h+var_38], edx
0x140044596  mov     dword ptr [rsp+88h+var_40], 235h
0x14004459e  mov     [rsp+88h+var_48], rax
0x1400445a3  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x1400445aa  mov     [rsp+88h+var_50], rax
0x1400445af  mov     [rsp+88h+var_58], 19h
0x1400445b6  mov     r9, cs:WPP_GLOBAL_Control
0x1400445bd  mov     ecx, 207h
0x1400445c2  mov     [rsp+88h+var_60], 7
0x1400445ca  mov     dl, r10b
0x1400445cd  mov     [rsp+88h+var_68], 2
0x1400445d2  mov     r9, [r9+40h]
0x1400445d6  call    WPP_RECORDER_AND_TRACE_SF_sDdDZ
0x1400445db  jmp     loc_1400446F6
0x1400445e0  test    ebx, ebx
0x1400445e2  jz      short loc_140044659
0x1400445e4  test    ebx, 0FFFFE000h
0x1400445ea  jz      short loc_140044659
0x1400445ec  mov     edx, 0C000000Dh
0x1400445f1  mov     edi, edx
0x1400445f3  mov     r10b, byte ptr cs:xmmword_14001A3D0
0x1400445fa  lea     rax, WPP_RECORDER_INITIALIZED
0x140044601  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044608  setnz   r8b
0x14004460c  and     r10b, 80h
0x140044610  jnz     short loc_14004461B
0x140044612  test    r8b, r8b
0x140044615  jz      loc_1400446F6
0x14004461b  lea     rax, [rsp+88h+var_18]
0x140044620  mov     [rsp+88h+var_28], rax
0x140044625  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004462c  mov     dword ptr [rsp+88h+var_30], ebx
0x140044630  mov     [rsp+88h+var_38], edx
0x140044634  mov     dword ptr [rsp+88h+var_40], 242h
0x14004463c  mov     [rsp+88h+var_48], rax
0x140044641  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044648  mov     [rsp+88h+var_50], rax
0x14004464d  mov     [rsp+88h+var_58], 1Ah
0x140044654  jmp     loc_1400445B6
0x140044659  movzx   edx, word ptr [rcx]
0x14004465c  xorps   xmm0, xmm0
0x14004465f  movups  xmmword ptr [r8], xmm0
0x140044663  mov     r8d, 6D6E4A50h
0x140044669  mov     ecx, 102h
0x14004466e  call    cs:__imp_ExAllocatePool2
0x140044675  nop     dword ptr [rax+rax+00h]
0x14004467a  mov     [rsi], rax
0x14004467d  test    rax, rax
0x140044680  jnz     loc_140044718
0x140044686  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14004468c  lea     rax, WPP_RECORDER_INITIALIZED
0x140044693  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004469a  setnz   r8b
0x14004469e  and     dl, 10h
0x1400446a1  jnz     short loc_1400446A8
0x1400446a3  test    r8b, r8b
0x1400446a6  jz      short loc_1400446F1
0x1400446a8  mov     r9, cs:WPP_GLOBAL_Control
0x1400446af  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400446b6  mov     dword ptr [rsp+88h+var_40], 253h
0x1400446be  mov     ecx, 214h
0x1400446c3  mov     [rsp+88h+var_48], rax
0x1400446c8  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x1400446cf  mov     [rsp+88h+var_50], rax
0x1400446d4  mov     r9, [r9+40h]
0x1400446d8  mov     [rsp+88h+var_58], 1Bh
0x1400446df  mov     [rsp+88h+var_60], 14h
0x1400446e7  mov     [rsp+88h+var_68], 2
0x1400446ec  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400446f1  mov     edi, 0C000009Ah
0x1400446f6  mov     rcx, [rsi]; P
0x1400446f9  test    rcx, rcx
0x1400446fc  jz      short loc_140044776
0x1400446fe  mov     edx, 6D6E4A50h; Tag
0x140044703  call    cs:__imp_ExFreePoolWithTag
0x14004470a  nop     dword ptr [rax+rax+00h]
0x14004470f  mov     qword ptr [rsi], 0
0x140044716  jmp     short loc_140044776
0x140044718  movzx   r8d, word ptr [rdi]; Size
0x14004471c  mov     rdx, rdi; Src
0x14004471f  mov     rcx, rax; void *
0x140044722  call    memmove
0x140044727  test    bl, 1
0x14004472a  jz      short loc_140044771
0x14004472c  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x140044732  lea     rax, WPP_RECORDER_INITIALIZED
0x140044739  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044740  setnz   r8b
0x140044744  and     dl, 80h
0x140044747  jnz     short loc_14004474E
0x140044749  test    r8b, r8b
0x14004474c  jz      short loc_14004476C
0x14004474e  mov     r9, cs:WPP_GLOBAL_Control
0x140044755  lea     rax, [rsp+88h+var_18]
0x14004475a  mov     [rsp+88h+var_28], rax
0x14004475f  mov     [rsp+88h+var_38], ebx
0x140044763  mov     r9, [r9+40h]
0x140044767  call    WPP_RECORDER_AND_TRACE_SF_sDDDZ
0x14004476c  mov     ebx, 1
0x140044771  mov     [rsi+8], ebx
0x140044774  xor     edi, edi
0x140044776  lea     r11, [rsp+88h+var_8]
0x14004477e  mov     eax, edi
0x140044780  mov     rbx, [r11+10h]
0x140044784  mov     rsi, [r11+18h]
0x140044788  mov     rsp, r11
0x14004478b  pop     rdi
0x14004478c  retn
```
