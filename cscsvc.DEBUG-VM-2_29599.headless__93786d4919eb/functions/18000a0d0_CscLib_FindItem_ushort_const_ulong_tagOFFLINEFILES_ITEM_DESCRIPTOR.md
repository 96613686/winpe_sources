# CscLib_FindItem(ushort const *,ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR *)

- ea: `0x18000a0d0`
- end: `0x18000a6c2`
- name: `?CscLib_FindItem@@YAJPEBGKPEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z`
- size: `1522`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)`
- caller_count: `12`
- callee_count: `13`
- tags: `reparse_path, loader_planting`

## callers

- `0x180008980`
- `0x180031808`
- `0x18003b08c`
- `0x180045354`
- `0x180045ad0`
- `0x18004612c`
- `0x18004a15c`
- `0x18004a4c8`
- `0x180065b0c`
- `0x180065c6c`
- `0x180066f68`
- `0x1800670e4`

## callees

- `0x1800068b0`
- `0x180007280`
- `0x1800074b0`
- `0x18000a0d0`
- `0x18000a6c8`
- `0x180036394`
- `0x180039610`
- `0x180039fb4`
- `0x18003c460`
- `0x18003c4e8`
- `0x18003c560`
- `0x18003e928`
- `0x180044a84`

## import_xrefs

- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x18000a362`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x18000a362`
- `ntdll!RtlInitUnicodeString` at `0x18000a17f`
- `ntdll!RtlInitUnicodeString` at `0x18000a34c`
- `ntdll!RtlInitUnicodeString` at `0x18000a17f`
- `ntdll!RtlInitUnicodeString` at `0x18000a34c`
- `ntdll!NtClose` at `0x18000a2d1`
- `ntdll!NtClose` at `0x18000a2d1`

## pseudocode

```c
__int64 __fastcall CscLib_FindItem(PCWSTR SourceString, int a2, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *a3)
{
  signed int v6; // r14d
  unsigned int v7; // ecx
  __m128i v8; // xmm6
  __int128 v9; // xmm9
  __int128 v10; // xmm10
  __int128 v11; // xmm11
  __m128i v12; // xmm8
  __int128 v13; // xmm7
  __int128 v14; // xmm12
  __int128 v15; // xmm13
  int v16; // edi
  int v17; // r9d
  int v18; // ebx
  __int64 v19; // xmm14_8
  int v20; // ebx
  const WCHAR *v21; // rdx
  __int64 v22; // rcx
  _WORD *v23; // r8
  __int64 v24; // r9
  _WORD *v25; // rcx
  __m128i v26; // xmm0
  __m128i v27; // xmm6
  __m128i v28; // xmm0
  int v30; // eax
  HANDLE Handle; // [rsp+48h] [rbp-C0h] BYREF
  int v32; // [rsp+50h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v33; // [rsp+58h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString_8[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-60h]
  _OWORD v36[3]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v37; // [rsp+E8h] [rbp-20h]
  __m128i v38; // [rsp+F0h] [rbp-18h]
  __int128 v39; // [rsp+100h] [rbp-8h]
  __int128 v40; // [rsp+110h] [rbp+8h]
  __int128 v41; // [rsp+120h] [rbp+18h]
  __m128i v42; // [rsp+130h] [rbp+28h]

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
      (_DWORD)SourceString,
      a2);
  v6 = a2 & 0xFFFFFFFE;
  memset_0(a3, 0, 0x300u);
  DestinationString_8[0] = 0;
  RtlInitUnicodeString(DestinationString_8, SourceString);
  v7 = (unsigned int)v6 >> 31;
  v35 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( (v6 & 2) == 0 )
  {
    LOBYTE(v7) = (v6 < 0) | 8;
    if ( (v6 & 0x10) != 0 )
      LOBYTE(v7) = v6 < 0;
  }
  v16 = 0;
  Handle = 0;
  if ( !CscUmpLibraryState )
  {
    v18 = -1073741436;
    goto LABEL_17;
  }
  v17 = ((v7 & 1) << 11) + 131074;
  if ( (v7 & 8) != 0 )
    v17 = (((v7 & 1) << 11) + 131074) | 0x80000;
  v18 = CscDriverOpenItemWithDispositionEx(&Handle, 0, DestinationString_8, v17, 1048704, 7u, 1u, 0);
  if ( v18 < 0
    || (v32 = 0,
        memset_0(v36, 0, 0x88u),
        *(_QWORD *)&v33.Length = 0x200000008LL,
        v18 = CscDriverpFsControlEx(Handle, 8u, v36, 0x88u),
        v18 < 0) )
  {
    v19 = v35;
  }
  else
  {
    v13 = v36[0];
    v14 = v36[1];
    v15 = v36[2];
    v19 = v37;
    v8 = v38;
    v9 = v39;
    v10 = v40;
    v11 = v41;
    v12 = v42;
  }
  if ( Handle )
    NtClose(Handle);
  if ( v18 < 0 )
  {
    if ( v18 != -1073741772
      && v18 != -1073741808
      && v18 != -1073741766
      && v18 != -1073741756
      && v18 != -1073741634
      && v18 != -1073741436 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
          (_DWORD)SourceString,
          v18);
      v16 = ResultFromNtStatus(v18);
      if ( v16 >= 0 )
        goto LABEL_37;
LABEL_18:
      memset_0(a3, 0, 0x300u);
      goto LABEL_37;
    }
LABEL_17:
    v16 = -2147024894;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
        (unsigned int)v18,
        -2147024894);
    goto LABEL_18;
  }
  v20 = _mm_cvtsi128_si32(v8);
  if ( (v6 & 0x10) == 0 && (v20 & 0x800000) != 0 )
  {
    v16 = -2147024894;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_640353d05de230bd321f309b7bf8540c_Traceguids, 2147942402LL);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_640353d05de230bd321f309b7bf8540c_Traceguids);
  v33 = 0;
  RtlInitUnicodeString(&v33, SourceString);
  LODWORD(Handle) = 0;
  if ( RtlGetLengthWithoutLastFullDosOrNtPathElement(0, &v33.Length, (PULONG)&Handle) < 0 )
    v21 = SourceString;
  else
    v21 = &SourceString[(unsigned int)Handle];
  v22 = 2147483646;
  v23 = (_WORD *)((char *)a3 + 214);
  v24 = 261;
  do
  {
    if ( !v22 )
      break;
    if ( !*v21 )
      break;
    *v23++ = *v21++;
    --v22;
    --v24;
  }
  while ( v24 );
  v25 = v23 - 1;
  v26 = v8;
  v27 = _mm_srli_si128(v8, 8);
  v28 = _mm_srli_si128(v26, 4);
  if ( v24 )
    v25 = v23;
  *v25 = 0;
  *(_DWORD *)a3 |= 7u;
  *((_DWORD *)a3 + 2) = _mm_cvtsi128_si32(v28);
  *((_DWORD *)a3 + 1) = v20;
  *((_BYTE *)a3 + 212) = _mm_cvtsi128_si32(_mm_srli_si128(v12, 8));
  *((_DWORD *)a3 + 3) = _mm_cvtsi128_si32(v27);
  *((_OWORD *)a3 + 1) = v9;
  *((_BYTE *)a3 + 213) = _mm_cvtsi128_si32(_mm_srli_si128(v12, 9));
  *(_OWORD *)((char *)a3 + 72) = v13;
  *((_OWORD *)a3 + 2) = v10;
  *(_OWORD *)((char *)a3 + 88) = v14;
  *((_OWORD *)a3 + 3) = v11;
  *((_QWORD *)a3 + 8) = v12.m128i_i64[0];
  *(_OWORD *)((char *)a3 + 104) = v15;
  *((_QWORD *)a3 + 15) = v19;
  if ( (v6 & 2) != 0 && (*(_BYTE *)a3 & 0x10) == 0 )
  {
    LODWORD(Handle) = 0;
    v32 = 0;
    if ( (int)CscLib_QueryItemConnectionState(
                SourceString,
                (v6 & 0x40000000) == 0,
                0,
                (enum _CSC_CONNECT_STATE *)&Handle,
                (enum _CSC_HANDLE_STATE *)&v32) >= 0 )
    {
      v30 = (int)Handle;
      *(_DWORD *)a3 |= 0x10u;
      *((_DWORD *)a3 + 51) = v30;
      *((_DWORD *)a3 + 52) = v32;
    }
  }
  if ( (v6 & 4) != 0 && (*(_BYTE *)a3 & 0x20) == 0 )
  {
    CscLib_FillInLocalDirtyByteCount(SourceString, *(union _LARGE_INTEGER *)((char *)a3 + 112), a3);
    *(_DWORD *)a3 |= 0x20u;
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
      (_DWORD)SourceString,
      v6,
      v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000a0d0  mov     r11, rsp
0x18000a0d3  push    rbp
0x18000a0d4  push    rdi
0x18000a0d5  push    r12
0x18000a0d7  push    r14
0x18000a0d9  lea     rbp, [r11-118h]
0x18000a0e0  sub     rsp, 1F8h
0x18000a0e7  mov     rax, cs:__security_cookie
0x18000a0ee  xor     rax, rsp
0x18000a0f1  mov     [rbp+110h+var_D0], rax
0x18000a0f5  mov     [r11-28h], rsi
0x18000a0f9  mov     r14d, edx
0x18000a0fc  mov     [r11-30h], r13
0x18000a100  mov     rsi, r8
0x18000a103  mov     [r11-38h], r15
0x18000a107  mov     r12, rcx
0x18000a10a  movaps  xmmword ptr [r11-48h], xmm6
0x18000a10f  movaps  xmmword ptr [r11-58h], xmm7
0x18000a114  movaps  xmmword ptr [r11-68h], xmm8
0x18000a119  movaps  xmmword ptr [r11-78h], xmm9
0x18000a11e  movaps  xmmword ptr [r11-88h], xmm10
0x18000a126  movaps  xmmword ptr [r11-98h], xmm11
0x18000a12e  movaps  xmmword ptr [r11-0A8h], xmm12
0x18000a136  movaps  xmmword ptr [r11-0B8h], xmm13
0x18000a13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a145  lea     r13, WPP_GLOBAL_Control
0x18000a14c  cmp     rcx, r13
0x18000a14f  jz      short loc_18000A15B
0x18000a151  test    byte ptr [rcx+1Ch], 8
0x18000a155  jnz     loc_18000A607
0x18000a15b  xor     edx, edx; Val
0x18000a15d  mov     r8d, 300h; Size
0x18000a163  mov     rcx, rsi; void *
0x18000a166  and     r14d, 0FFFFFFFEh
0x18000a16a  call    memset_0
0x18000a16f  xorps   xmm0, xmm0
0x18000a172  lea     rcx, [rsp+210h+DestinationString.Buffer]; DestinationString
0x18000a177  mov     rdx, r12; SourceString
0x18000a17a  movups  xmmword ptr [rsp+210h+DestinationString.Buffer], xmm0
0x18000a17f  call    cs:__imp_RtlInitUnicodeString
0x18000a185  xor     eax, eax
0x18000a187  mov     ecx, r14d
0x18000a18a  shr     ecx, 1Fh
0x18000a18d  mov     r15d, r14d
0x18000a190  mov     [rbp+110h+var_170], rax
0x18000a194  xorps   xmm6, xmm6
0x18000a197  xorps   xmm9, xmm9
0x18000a19b  xorps   xmm10, xmm10
0x18000a19f  xorps   xmm11, xmm11
0x18000a1a3  xorps   xmm8, xmm8
0x18000a1a7  xorps   xmm7, xmm7
0x18000a1aa  xorps   xmm12, xmm12
0x18000a1ae  xorps   xmm13, xmm13
0x18000a1b2  and     r15d, 2
0x18000a1b6  jnz     short loc_18000A1C4
0x18000a1b8  mov     eax, ecx
0x18000a1ba  or      ecx, 8
0x18000a1bd  test    r14b, 10h
0x18000a1c1  cmovnz  ecx, eax
0x18000a1c4  xor     edi, edi
0x18000a1c6  mov     [rsp+210h+arg_8], rbx
0x18000a1ce  cmp     cs:CscUmpLibraryState, edi
0x18000a1d4  movaps  [rsp+210h+var_C8+8], xmm14
0x18000a1dd  mov     [rsp+210h+Handle], rdi
0x18000a1e2  jz      loc_18000A311
0x18000a1e8  mov     r9d, ecx
0x18000a1eb  mov     [rsp+210h+var_1D8], edi; int
0x18000a1ef  and     r9d, 1
0x18000a1f3  mov     [rsp+210h+var_1E0], 1; ULONG
0x18000a1fb  shl     r9d, 0Bh
0x18000a1ff  lea     r8, [rsp+210h+DestinationString.Buffer]
0x18000a204  add     r9d, 20002h
0x18000a20b  mov     dword ptr [rsp+210h+var_1E8], 7; ULONG
0x18000a213  mov     eax, r9d
0x18000a216  mov     [rsp+210h+var_1F0], 100080h; int
0x18000a21e  bts     eax, 13h
0x18000a222  test    cl, 8
0x18000a225  lea     rcx, [rsp+210h+Handle]; FileHandle
0x18000a22a  cmovnz  r9d, eax
0x18000a22e  xor     edx, edx
0x18000a230  call    CscDriverOpenItemWithDispositionEx
0x18000a235  mov     ebx, eax
0x18000a237  test    eax, eax
0x18000a239  js      loc_18000A573
0x18000a23f  xor     edx, edx; Val
0x18000a241  mov     dword ptr [rsp+210h+var_1C8.Length], edi
0x18000a245  mov     r8d, 88h; Size
0x18000a24b  lea     rcx, [rbp+110h+var_160]; void *
0x18000a24f  call    memset_0
0x18000a254  mov     rcx, [rsp+210h+Handle]; FileHandle
0x18000a259  lea     rax, [rbp+110h+var_160]
0x18000a25d  mov     [rsp+210h+var_1E0], 88h; ULONG
0x18000a265  lea     r9, [rsp+210h+var_1C8.Buffer]
0x18000a26a  mov     [rsp+210h+var_1E8], rax; PVOID
0x18000a26f  lea     r8, [rsp+210h+var_1C8]
0x18000a274  mov     [rsp+210h+var_1F0], 8; ULONG
0x18000a27c  mov     dword ptr [rsp+210h+var_1C8.Buffer], 8
0x18000a284  mov     dword ptr [rsp+210h+var_1C8.Buffer+4], 2
0x18000a28c  call    CscDriverpFsControlEx
0x18000a291  mov     ebx, eax
0x18000a293  test    eax, eax
0x18000a295  js      loc_18000A573
0x18000a29b  movaps  xmm7, [rbp+110h+var_160]
0x18000a29f  movaps  xmm12, [rbp+110h+var_150]
0x18000a2a4  movaps  xmm13, [rbp+110h+var_140]
0x18000a2a9  movsd   xmm14, [rbp+110h+var_130]
0x18000a2af  movups  xmm6, [rbp+110h+var_128]
0x18000a2b3  movups  xmm9, [rbp+110h+var_118]
0x18000a2b8  movups  xmm10, [rbp+110h+var_108]
0x18000a2bd  movups  xmm11, [rbp+110h+var_F8]
0x18000a2c2  movups  xmm8, [rbp+110h+var_E8]
0x18000a2c7  mov     rcx, [rsp+210h+Handle]; Handle
0x18000a2cc  test    rcx, rcx
0x18000a2cf  jz      short loc_18000A2D7
0x18000a2d1  call    cs:__imp_NtClose
0x18000a2d7  test    ebx, ebx
0x18000a2d9  jns     short loc_18000A318
0x18000a2db  cmp     ebx, 0C0000034h
0x18000a2e1  jnz     loc_18000A64B
0x18000a2e7  mov     edi, 80070002h
0x18000a2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2f3  cmp     rcx, r13
0x18000a2f6  jnz     loc_18000A5D8
0x18000a2fc  xor     edx, edx; Val
0x18000a2fe  mov     r8d, 300h; Size
0x18000a304  mov     rcx, rsi; void *
0x18000a307  call    memset_0
0x18000a30c  jmp     loc_18000A46A
0x18000a311  mov     ebx, 0C0000184h
0x18000a316  jmp     short loc_18000A2E7
0x18000a318  movd    ebx, xmm6
0x18000a31c  test    r14b, 10h
0x18000a320  jz      loc_18000A52A
0x18000a326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a32d  cmp     rcx, r13
0x18000a330  jz      short loc_18000A33C
0x18000a332  test    byte ptr [rcx+1Ch], 8
0x18000a336  jnz     loc_18000A629
0x18000a33c  xorps   xmm0, xmm0
0x18000a33f  lea     rcx, [rsp+210h+var_1C8.Buffer]; DestinationString
0x18000a344  mov     rdx, r12; SourceString
0x18000a347  movups  xmmword ptr [rsp+210h+var_1C8.Buffer], xmm0
0x18000a34c  call    cs:__imp_RtlInitUnicodeString
0x18000a352  lea     r8, [rsp+210h+Handle]; LengthOut
0x18000a357  mov     dword ptr [rsp+210h+Handle], edi
0x18000a35b  lea     rdx, [rsp+210h+var_1C8.Buffer]; Path
0x18000a360  xor     ecx, ecx; Flags
0x18000a362  call    cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement
0x18000a368  test    eax, eax
0x18000a36a  js      loc_18000A643
0x18000a370  mov     eax, dword ptr [rsp+210h+Handle]
0x18000a374  lea     rdx, [r12+rax*2]
0x18000a378  mov     ecx, 7FFFFFFEh
0x18000a37d  lea     r8, [rsi+0D6h]
0x18000a384  mov     r9d, 105h
0x18000a38a  nop     word ptr [rax+rax+00h]
0x18000a390  test    rcx, rcx
0x18000a393  jz      short loc_18000A3B2
0x18000a395  movzx   eax, word ptr [rdx]
0x18000a398  test    ax, ax
0x18000a39b  jz      short loc_18000A3B2
0x18000a39d  mov     [r8], ax
0x18000a3a1  add     rdx, 2
0x18000a3a5  add     r8, 2
0x18000a3a9  dec     rcx
0x18000a3ac  sub     r9, 1
0x18000a3b0  jnz     short loc_18000A390
0x18000a3b2  test    r9, r9
0x18000a3b5  lea     rcx, [r8-2]
0x18000a3b9  movdqa  xmm0, xmm6
0x18000a3bd  psrldq  xmm6, 8
0x18000a3c2  psrldq  xmm0, 4
0x18000a3c7  cmovnz  rcx, r8
0x18000a3cb  xor     eax, eax
0x18000a3cd  mov     [rcx], ax
0x18000a3d0  or      dword ptr [rsi], 7
0x18000a3d3  movd    dword ptr [rsi+8], xmm0
0x18000a3d8  movdqa  xmm0, xmm8
0x18000a3dd  psrldq  xmm0, 8
0x18000a3e2  movd    eax, xmm0
0x18000a3e6  movdqa  xmm0, xmm8
0x18000a3eb  psrldq  xmm0, 9
0x18000a3f0  mov     [rsi+4], ebx
0x18000a3f3  mov     [rsi+0D4h], al
0x18000a3f9  movd    eax, xmm0
0x18000a3fd  movd    dword ptr [rsi+0Ch], xmm6
0x18000a402  movups  xmmword ptr [rsi+10h], xmm9
0x18000a407  mov     [rsi+0D5h], al
0x18000a40d  movups  xmmword ptr [rsi+48h], xmm7
0x18000a411  movups  xmmword ptr [rsi+20h], xmm10
0x18000a416  movups  xmmword ptr [rsi+58h], xmm12
0x18000a41b  movups  xmmword ptr [rsi+30h], xmm11
0x18000a420  movsd   qword ptr [rsi+40h], xmm8
0x18000a426  movups  xmmword ptr [rsi+68h], xmm13
0x18000a42b  movsd   qword ptr [rsi+78h], xmm14
0x18000a431  test    r15d, r15d
0x18000a434  jnz     loc_18000A57E
0x18000a43a  test    r14b, 4
0x18000a43e  jz      short loc_18000A46A
0x18000a440  test    byte ptr [rsi], 20h
0x18000a443  jnz     short loc_18000A46A
0x18000a445  mov     rdx, [rsi+70h]; union _LARGE_INTEGER
0x18000a449  mov     r8, rsi; struct tagOFFLINEFILES_ITEM_DESCRIPTOR *
0x18000a44c  mov     rcx, r12; SourceString
0x18000a44f  call    ?CscLib_FillInLocalDirtyByteCount@@YAXPEBGT_LARGE_INTEGER@@PEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z; CscLib_FillInLocalDirtyByteCount(ushort const *,_LARGE_INTEGER,tagOFFLINEFILES_ITEM_DESCRIPTOR *)
0x18000a454  or      dword ptr [rsi], 20h
0x18000a457  jmp     short loc_18000A46A
0x18000a459  mov     ecx, ebx; int
0x18000a45b  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000a460  mov     edi, eax
0x18000a462  test    eax, eax
0x18000a464  js      loc_18000A2FC
0x18000a46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a471  movaps  xmm14, [rsp+210h+var_C8+8]
0x18000a47a  cmp     rcx, r13
0x18000a47d  mov     r13, [rsp+210h+var_28]
0x18000a485  movaps  xmm13, [rsp+210h+var_B8+8]
0x18000a48e  movaps  xmm12, [rsp+210h+var_A8+8]
0x18000a497  movaps  xmm11, [rsp+210h+var_98+8]
0x18000a4a0  movaps  xmm10, [rsp+210h+var_88+8]
0x18000a4a9  movaps  xmm9, [rsp+210h+var_78+8]
0x18000a4b2  movaps  xmm8, [rsp+210h+var_68+8]
0x18000a4bb  movaps  xmm7, [rsp+210h+var_58+8]
0x18000a4c3  movaps  xmm6, [rsp+210h+var_48+8]
0x18000a4cb  mov     r15, [rsp+210h+var_30]
0x18000a4d3  mov     rsi, [rsp+1F0h]
0x18000a4db  mov     rbx, [rsp+210h+arg_8]
0x18000a4e3  jnz     short loc_18000A501
0x18000a4e5  mov     eax, edi
0x18000a4e7  mov     rcx, [rbp+110h+var_D0]
0x18000a4eb  xor     rcx, rsp; StackCookie
0x18000a4ee  call    __security_check_cookie
0x18000a4f3  add     rsp, 1F8h
0x18000a4fa  pop     r14
0x18000a4fc  pop     r12
0x18000a4fe  pop     rdi
0x18000a4ff  pop     rbp
0x18000a500  retn
0x18000a501  test    byte ptr [rcx+1Ch], 8
0x18000a505  jz      short loc_18000A4E5
0x18000a507  mov     rcx, [rcx+10h]
0x18000a50b  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000a512  mov     edx, 14h
0x18000a517  mov     dword ptr [rsp+210h+var_1E8], edi
0x18000a51b  mov     r9, r12
0x18000a51e  mov     [rsp+210h+var_1F0], r14d
0x18000a523  call    WPP_SF_SdD
0x18000a528  jmp     short loc_18000A4E5
0x18000a52a  bt      ebx, 17h
0x18000a52e  jnb     loc_18000A326
0x18000a534  mov     edi, 80070002h
0x18000a539  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a540  cmp     rcx, r13
0x18000a543  jz      loc_18000A2FC
0x18000a549  test    byte ptr [rcx+1Ch], 8
0x18000a54d  jz      loc_18000A2FC
0x18000a553  mov     rcx, [rcx+10h]
0x18000a557  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000a55e  mov     edx, 10h
0x18000a563  mov     r9d, 80070002h
0x18000a569  call    WPP_SF_d
0x18000a56e  jmp     loc_18000A2FC
0x18000a573  movsd   xmm14, [rbp+110h+var_170]
0x18000a579  jmp     loc_18000A2C7
0x18000a57e  test    byte ptr [rsi], 10h
0x18000a581  jnz     loc_18000A43A
0x18000a587  mov     edx, r14d
0x18000a58a  mov     dword ptr [rsp+210h+Handle], edi
0x18000a58e  shr     edx, 1Eh
0x18000a591  lea     rax, [rsp+210h+var_1C8]
0x18000a596  not     edx
0x18000a598  mov     dword ptr [rsp+210h+var_1C8.Length], edi
0x18000a59c  and     edx, 1; int
0x18000a59f  mov     qword ptr [rsp+210h+var_1F0], rax; enum _CSC_HANDLE_STATE *
0x18000a5a4  lea     r9, [rsp+210h+Handle]; enum _CSC_CONNECT_STATE *
0x18000a5a9  xor     r8d, r8d; int
0x18000a5ac  mov     rcx, r12; SourceString
0x18000a5af  call    ?CscLib_QueryItemConnectionState@@YAJPEBGHHPEAW4_CSC_CONNECT_STATE@@PEAW4_CSC_HANDLE_STATE@@@Z; CscLib_QueryItemConnectionState(ushort const *,int,int,_CSC_CONNECT_STATE *,_CSC_HANDLE_STATE *)
0x18000a5b4  test    eax, eax
0x18000a5b6  js      loc_18000A43A
0x18000a5bc  mov     eax, dword ptr [rsp+210h+Handle]
0x18000a5c0  or      dword ptr [rsi], 10h
0x18000a5c3  mov     [rsi+0CCh], eax
0x18000a5c9  mov     eax, dword ptr [rsp+210h+var_1C8.Length]
0x18000a5cd  mov     [rsi+0D0h], eax
0x18000a5d3  jmp     loc_18000A43A
0x18000a5d8  test    byte ptr [rcx+1Ch], 8
0x18000a5dc  jz      loc_18000A2FC
0x18000a5e2  mov     rcx, [rcx+10h]
0x18000a5e6  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000a5ed  mov     edx, 12h
0x18000a5f2  mov     [rsp+210h+var_1F0], 80070002h
0x18000a5fa  mov     r9d, ebx
0x18000a5fd  call    WPP_SF_dd
0x18000a602  jmp     loc_18000A2FC
0x18000a607  mov     rcx, [rcx+10h]
0x18000a60b  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000a612  mov     edx, 0Fh
0x18000a617  mov     [rsp+210h+var_1F0], r14d
0x18000a61c  mov     r9, r12
  ... truncated ...
```
