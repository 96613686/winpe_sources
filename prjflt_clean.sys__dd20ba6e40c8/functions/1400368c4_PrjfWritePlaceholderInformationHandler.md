# PrjfWritePlaceholderInformationHandler

- ea: `0x1400368c4`
- end: `0x140036efd`
- name: `PrjfWritePlaceholderInformationHandler`
- size: `1593`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x1400089d8`
- `0x14000d128`
- `0x140021f8c`
- `0x14002f494`
- `0x140033878`
- `0x1400368c4`
- `0x14003775c`
- `0x140037b8c`
- `0x140038b78`
- `0x1400395a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036ecd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036ecd`

## pseudocode

```c
__int64 __fastcall PrjfWritePlaceholderInformationHandler(
        PFLT_INSTANCE Instance,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 UnionContextByVirtualizationInstanceInfo; // r15
  PVOID v7; // r14
  __int64 v8; // rdx
  signed int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  _WORD *v12; // rax
  unsigned __int64 i; // rcx
  unsigned __int16 v14; // r13
  _WORD *v15; // rax
  int UnicodeString; // eax
  int v17; // eax
  int v18; // eax
  int SymlinkFromPlaceholderInfoMessage; // eax
  __int64 v20; // r14
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  int HardLink; // eax
  __int16 v27; // [rsp+30h] [rbp-69h]
  char v28; // [rsp+48h] [rbp-51h]
  char v29; // [rsp+50h] [rbp-49h]
  __int64 v30; // [rsp+60h] [rbp-39h] BYREF
  PVOID P; // [rsp+68h] [rbp-31h] BYREF
  __int64 v32; // [rsp+70h] [rbp-29h] BYREF
  __int128 v33; // [rsp+80h] [rbp-19h] BYREF
  PVOID v34[2]; // [rsp+90h] [rbp-9h] BYREF
  UNICODE_STRING SourceString; // [rsp+A0h] [rbp+7h] BYREF

  v32 = 0;
  P = 0;
  LODWORD(v30) = 0;
  UnionContextByVirtualizationInstanceInfo = 0;
  v7 = 0;
  SourceString = 0;
  *(_OWORD *)v34 = 0;
  v9 = PrjfValidatePlaceholderInformationMessage(a2, a4, &v32);
  if ( v9 < 0 )
    goto LABEL_58;
  UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(a2 + 8, Instance);
  if ( !UnionContextByVirtualizationInstanceInfo )
  {
    v9 = -1073741811;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        14,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        56,
        13);
    goto LABEL_58;
  }
  v10 = a2 + *(unsigned int *)(a2 + 88);
  if ( !v10 )
  {
    v9 = -1073741811;
LABEL_54:
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v29 = v9;
    v28 = 76;
    v27 = 15;
    goto LABEL_57;
  }
  v12 = (_WORD *)(a2 + *(unsigned int *)(a2 + 88));
  for ( i = (unsigned __int64)*(unsigned __int16 *)(a2 + 92) >> 1; i; --i )
  {
    if ( !*v12 )
      break;
    ++v12;
  }
  v8 = i == 0 ? 0xC000000D : 0;
  if ( !i )
  {
    v9 = i == 0 ? 0xC000000D : 0;
    goto LABEL_54;
  }
  v14 = *(_WORD *)(UnionContextByVirtualizationInstanceInfo + 40);
  v8 = 0x7FFF;
  *(_QWORD *)&v33 = *(_QWORD *)(UnionContextByVirtualizationInstanceInfo + 48);
  v11 = 0;
  v15 = (_WORD *)v10;
  SourceString = 0;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0 ? 0xC000000D : 0;
  if ( !v8 )
  {
    v8 = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v29 = v9;
    v28 = 84;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v27 = 16;
LABEL_57:
    WPP_RECORDER_AND_TRACE_SF_sDL(
      526,
      v8,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      v27,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      v28,
      v29);
    goto LABEL_58;
  }
  SourceString.Buffer = (PWSTR)v10;
  LOWORD(v8) = 2 * v8;
  SourceString.Length = -2 - v8;
  SourceString.MaximumLength = -(__int16)v8;
  if ( (unsigned __int16)(-2 - v8 + v14) < v14 )
  {
    v9 = -1073741675;
    WORD1(v34[0]) = -1;
    goto LABEL_58;
  }
  if ( (unsigned __int16)(v14 - v8) < 2u )
  {
    v9 = -1073741675;
    WORD1(v34[0]) = -1;
    goto LABEL_47;
  }
  WORD1(v34[0]) = v14 - v8;
  UnicodeString = PrjfAllocateUnicodeString(1953319504, v34, v10, 0);
  v9 = UnicodeString;
  if ( UnicodeString < 0 )
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v29 = UnicodeString;
    v28 = 106;
    v27 = 17;
    goto LABEL_57;
  }
  v17 = PrjfRelPathToFullPath(v34, v14, v33, SourceString.Buffer, SourceString.Length);
  v9 = v17;
  if ( v17 < 0 )
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v29 = v17;
    v28 = 118;
    v27 = 18;
    goto LABEL_57;
  }
  v18 = *(_DWORD *)(a2 + 4);
  if ( (v18 & 8) == 0 )
  {
    v10 = 16;
    if ( (v18 & 0x10) == 0 )
      goto LABEL_58;
    HardLink = PrjfCreateHardLink(Instance, v32, (const void **)v34);
    v9 = HardLink;
    if ( HardLink >= 0 )
      goto LABEL_58;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v29 = HardLink;
    v28 = -59;
    v27 = 22;
    goto LABEL_57;
  }
  if ( *(_DWORD *)(a2 + 104) )
  {
    SymlinkFromPlaceholderInfoMessage = PrjfCreateSymlinkFromPlaceholderInfoMessage(
                                          Instance,
                                          UnionContextByVirtualizationInstanceInfo,
                                          v34,
                                          a2);
    v9 = SymlinkFromPlaceholderInfoMessage;
    if ( SymlinkFromPlaceholderInfoMessage >= 0 )
      goto LABEL_58;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    v29 = SymlinkFromPlaceholderInfoMessage;
    v28 = -104;
    v27 = 19;
    goto LABEL_57;
  }
  v20 = *(unsigned int *)(a2 + 96);
  v33 = *(_OWORD *)(a2 + 8);
  v21 = PrjfCreatePrjReparseBuffer(
          &SourceString,
          &v33,
          v10,
          (_OWORD *)(v20 + a2 + 80),
          (WCHAR **)&P,
          (unsigned int *)&v30);
  v9 = v21;
  if ( v21 >= 0 )
  {
    v22 = v20 + a3;
    v23 = v20 + a2;
    v7 = P;
    v24 = PrjfCopyAsPlaceHolder(v23, v22, (__int64)v34, Instance, (__int64)P, v30, 1, *(_DWORD *)(a2 + 100));
    v9 = v24;
    if ( v24 < 0 )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDL(
          526,
          v8,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          21,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          182,
          v24);
    }
  }
  else
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        20,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        167,
        v21);
    v7 = P;
  }
LABEL_47:
  if ( v7 )
    ExFreePoolWithTag(v7, 0x69724A50u);
LABEL_58:
  if ( v34[1] )
    ExFreePoolWithTag(v34[1], 0x746D4A50u);
  if ( UnionContextByVirtualizationInstanceInfo )
    PrjfReleaseUnionContext((char *)UnionContextByVirtualizationInstanceInfo, v8, v10, v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400368c4  mov     [rsp-8+arg_10], r8
0x1400368c9  push    rbp
0x1400368ca  push    rbx
0x1400368cb  push    rsi
0x1400368cc  push    rdi
0x1400368cd  push    r12
0x1400368cf  push    r13
0x1400368d1  push    r14
0x1400368d3  push    r15
0x1400368d5  lea     rbp, [rsp-1Fh]
0x1400368da  sub     rsp, 0B8h
0x1400368e1  xor     r13d, r13d
0x1400368e4  lea     r8, [rbp+57h+var_80]
0x1400368e8  mov     rdi, rdx
0x1400368eb  mov     [rbp+57h+var_80], r13
0x1400368ef  mov     r12, rcx
0x1400368f2  mov     [rbp+57h+P], r13
0x1400368f6  xorps   xmm0, xmm0
0x1400368f9  mov     dword ptr [rbp+57h+var_90], r13d
0x1400368fd  xorps   xmm1, xmm1
0x140036900  mov     rcx, rdi
0x140036903  mov     edx, r9d
0x140036906  mov     r15d, r13d
0x140036909  mov     r14d, r13d
0x14003690c  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140036910  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x140036914  call    PrjfValidatePlaceholderInformationMessage
0x140036919  mov     ebx, eax
0x14003691b  test    eax, eax
0x14003691d  js      loc_140036EBF
0x140036923  lea     rcx, [rdi+8]
0x140036927  mov     rdx, r12
0x14003692a  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14003692f  mov     r15, rax
0x140036932  test    rax, rax
0x140036935  jnz     short loc_14003699E
0x140036937  mov     ebx, 0C000000Dh
0x14003693c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036942  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036949  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036950  setnz   r8b
0x140036954  and     dl, 40h
0x140036957  jnz     short loc_140036962
0x140036959  test    r8b, r8b
0x14003695c  jz      loc_140036EBF
0x140036962  mov     dword ptr [rsp+0F0h+var_A0], ebx
0x140036966  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003696d  mov     dword ptr [rsp+0F0h+var_A8], 238h
0x140036975  mov     eax, 0Eh
0x14003697a  mov     [rsp+0F0h+var_B0], r9
0x14003697f  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036986  mov     [rsp+0F0h+var_B8], r9
0x14003698b  mov     [rsp+0F0h+var_C0], ax
0x140036990  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140036994  mov     byte ptr [rsp+0F0h+var_D0], 2
0x140036999  jmp     loc_140036EAA
0x14003699e  mov     r8d, [rdi+58h]
0x1400369a2  mov     esi, 2
0x1400369a7  add     r8, rdi
0x1400369aa  jz      loc_140036E4B
0x1400369b0  movzx   ecx, word ptr [rdi+5Ch]
0x1400369b4  mov     rax, r8
0x1400369b7  shr     rcx, 1
0x1400369ba  jz      short loc_1400369CB
0x1400369bc  cmp     [rax], r13w
0x1400369c0  jz      short loc_1400369CB
0x1400369c2  add     rax, rsi
0x1400369c5  sub     rcx, 1
0x1400369c9  jnz     short loc_1400369BC
0x1400369cb  mov     rax, rcx
0x1400369ce  mov     ebx, 0C000000Dh
0x1400369d3  neg     rax
0x1400369d6  sbb     edx, edx
0x1400369d8  not     edx
0x1400369da  and     edx, ebx
0x1400369dc  test    rcx, rcx
0x1400369df  jnz     short loc_1400369E8
0x1400369e1  mov     ebx, edx
0x1400369e3  jmp     loc_140036E50
0x1400369e8  mov     rax, [r15+30h]
0x1400369ec  xorps   xmm0, xmm0
0x1400369ef  movzx   r13d, word ptr [r15+28h]
0x1400369f4  mov     edx, 7FFFh
0x1400369f9  mov     qword ptr [rbp+57h+var_70], rax
0x1400369fd  xor     r9d, r9d
0x140036a00  mov     rax, r8
0x140036a03  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140036a07  cmp     [rax], r9w
0x140036a0b  jz      short loc_140036A16
0x140036a0d  add     rax, rsi
0x140036a10  sub     rdx, 1
0x140036a14  jnz     short loc_140036A07
0x140036a16  mov     rax, rdx
0x140036a19  neg     rax
0x140036a1c  sbb     ecx, ecx
0x140036a1e  not     ecx
0x140036a20  and     ebx, ecx
0x140036a22  test    rdx, rdx
0x140036a25  jz      loc_140036DF5
0x140036a2b  mov     ecx, 0FFFEh
0x140036a30  mov     [rbp+57h+SourceString.Buffer], r8
0x140036a34  add     dx, dx
0x140036a37  sub     cx, dx
0x140036a3a  mov     [rbp+57h+SourceString.Length], cx
0x140036a3e  lea     eax, [rsi+rcx]
0x140036a41  mov     [rbp+57h+SourceString.MaximumLength], ax
0x140036a45  lea     eax, [rcx+r13]
0x140036a49  cmp     ax, r13w
0x140036a4d  jb      loc_140036DE2
0x140036a53  add     ax, si
0x140036a56  cmp     ax, si
0x140036a59  jb      loc_140036DB2
0x140036a5f  lea     rdx, [rbp+57h+var_60]
0x140036a63  mov     word ptr [rbp+57h+var_60+2], ax
0x140036a67  mov     ecx, 746D4A50h
0x140036a6c  call    PrjfAllocateUnicodeString
0x140036a71  mov     ebx, eax
0x140036a73  test    eax, eax
0x140036a75  jns     short loc_140036ACD
0x140036a77  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036a7d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036a84  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036a8b  setnz   r8b
0x140036a8f  and     dl, 40h
0x140036a92  jnz     short loc_140036A9D
0x140036a94  test    r8b, r8b
0x140036a97  jz      loc_140036EBF
0x140036a9d  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140036aa1  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036aa8  mov     dword ptr [rsp+0F0h+var_A8], 26Ah
0x140036ab0  mov     [rsp+0F0h+var_B0], r9
0x140036ab5  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036abc  mov     [rsp+0F0h+var_B8], r9
0x140036ac1  mov     [rsp+0F0h+var_C0], 11h
0x140036ac8  jmp     loc_140036E9D
0x140036acd  movzx   eax, [rbp+57h+SourceString.Length]
0x140036ad1  lea     rcx, [rbp+57h+var_60]
0x140036ad5  mov     r9, [rbp+57h+SourceString.Buffer]
0x140036ad9  movzx   edx, r13w
0x140036add  mov     r8, qword ptr [rbp+57h+var_70]
0x140036ae1  mov     word ptr [rsp+0F0h+var_D0], ax
0x140036ae6  call    PrjfRelPathToFullPath
0x140036aeb  xor     r13d, r13d
0x140036aee  mov     ebx, eax
0x140036af0  test    eax, eax
0x140036af2  jns     short loc_140036B4A
0x140036af4  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036afa  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036b01  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036b08  setnz   r8b
0x140036b0c  and     dl, 40h
0x140036b0f  jnz     short loc_140036B1A
0x140036b11  test    r8b, r8b
0x140036b14  jz      loc_140036EBF
0x140036b1a  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140036b1e  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036b25  mov     dword ptr [rsp+0F0h+var_A8], 276h
0x140036b2d  mov     [rsp+0F0h+var_B0], r9
0x140036b32  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036b39  mov     [rsp+0F0h+var_B8], r9
0x140036b3e  mov     [rsp+0F0h+var_C0], 12h
0x140036b45  jmp     loc_140036E9D
0x140036b4a  mov     eax, [rdi+4]
0x140036b4d  test    al, 8
0x140036b4f  jz      loc_140036D33
0x140036b55  cmp     [rdi+68h], r13d
0x140036b59  jz      short loc_140036BCD
0x140036b5b  mov     r9, rdi
0x140036b5e  lea     r8, [rbp+57h+var_60]
0x140036b62  mov     rdx, r15
0x140036b65  mov     rcx, r12
0x140036b68  call    PrjfCreateSymlinkFromPlaceholderInfoMessage
0x140036b6d  mov     ebx, eax
0x140036b6f  test    eax, eax
0x140036b71  jns     loc_140036EBF
0x140036b77  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036b7d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036b84  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036b8b  setnz   r8b
0x140036b8f  and     dl, 40h
0x140036b92  jnz     short loc_140036B9D
0x140036b94  test    r8b, r8b
0x140036b97  jz      loc_140036EBF
0x140036b9d  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140036ba1  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036ba8  mov     dword ptr [rsp+0F0h+var_A8], 298h
0x140036bb0  mov     [rsp+0F0h+var_B0], r9
0x140036bb5  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036bbc  mov     [rsp+0F0h+var_B8], r9
0x140036bc1  mov     [rsp+0F0h+var_C0], 13h
0x140036bc8  jmp     loc_140036E9D
0x140036bcd  mov     r14d, [rdi+60h]
0x140036bd1  lea     rax, [rbp+57h+var_90]
0x140036bd5  movups  xmm0, xmmword ptr [rdi+8]
0x140036bd9  mov     [rsp+0F0h+var_C8], rax; __int64
0x140036bde  lea     rdx, [rbp+57h+var_70]
0x140036be2  lea     rax, [rbp+57h+P]
0x140036be6  lea     r13, [r14+rdi]
0x140036bea  mov     [rsp+0F0h+var_D0], rax; __int64
0x140036bef  lea     r9, [r13+50h]
0x140036bf3  lea     rcx, [rbp+57h+SourceString]; SourceString
0x140036bf7  movdqu  [rbp+57h+var_70], xmm0
0x140036bfc  call    PrjfCreatePrjReparseBuffer
0x140036c01  mov     ebx, eax
0x140036c03  test    eax, eax
0x140036c05  jns     short loc_140036C7F
0x140036c07  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036c0d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036c14  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036c1b  setnz   r8b
0x140036c1f  and     dl, 40h
0x140036c22  jnz     short loc_140036C29
0x140036c24  test    r8b, r8b
0x140036c27  jz      short loc_140036C76
0x140036c29  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140036c2d  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036c34  mov     dword ptr [rsp+0F0h+var_A8], 2A7h
0x140036c3c  mov     ecx, 20Eh
0x140036c41  mov     [rsp+0F0h+var_B0], r9
0x140036c46  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036c4d  mov     [rsp+0F0h+var_B8], r9
0x140036c52  mov     r9, cs:WPP_GLOBAL_Control
0x140036c59  mov     [rsp+0F0h+var_C0], 14h
0x140036c60  mov     dword ptr [rsp+0F0h+var_C8], 0Eh
0x140036c68  mov     byte ptr [rsp+0F0h+var_D0], sil
0x140036c6d  mov     r9, [r9+40h]
0x140036c71  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140036c76  mov     r14, [rbp+57h+P]
0x140036c7a  jmp     loc_140036DC0
0x140036c7f  mov     eax, [rdi+64h]
0x140036c82  lea     r8, [rbp+57h+var_60]
0x140036c86  mov     rdx, [rbp+57h+arg_10]
0x140036c8a  mov     r9, r12
0x140036c8d  mov     dword ptr [rsp+0F0h+var_B8], eax
0x140036c91  add     rdx, r14
0x140036c94  mov     eax, dword ptr [rbp+57h+var_90]
0x140036c97  mov     rcx, r13
0x140036c9a  mov     r14, [rbp+57h+P]
0x140036c9e  mov     byte ptr [rsp+0F0h+var_C0], 1
0x140036ca3  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140036ca7  mov     [rsp+0F0h+var_D0], r14
0x140036cac  call    PrjfCopyAsPlaceHolder
0x140036cb1  mov     ebx, eax
0x140036cb3  test    eax, eax
0x140036cb5  jns     loc_140036DC0
0x140036cbb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036cc1  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036cc8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036ccf  setnz   r8b
0x140036cd3  and     dl, 40h
0x140036cd6  jnz     short loc_140036CE1
0x140036cd8  test    r8b, r8b
0x140036cdb  jz      loc_140036DC0
0x140036ce1  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140036ce5  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036cec  mov     dword ptr [rsp+0F0h+var_A8], 2B6h
0x140036cf4  mov     ecx, 20Eh
0x140036cf9  mov     [rsp+0F0h+var_B0], r9
0x140036cfe  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036d05  mov     [rsp+0F0h+var_B8], r9
0x140036d0a  mov     r9, cs:WPP_GLOBAL_Control
0x140036d11  mov     [rsp+0F0h+var_C0], 15h
0x140036d18  mov     dword ptr [rsp+0F0h+var_C8], 0Eh
0x140036d20  mov     byte ptr [rsp+0F0h+var_D0], sil
0x140036d25  mov     r9, [r9+40h]
0x140036d29  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140036d2e  jmp     loc_140036DC0
0x140036d33  mov     r8d, 10h
0x140036d39  test    r8b, al
0x140036d3c  jz      loc_140036EBF
0x140036d42  mov     rdx, [rbp+57h+var_80]
0x140036d46  lea     r8, [rbp+57h+var_60]
0x140036d4a  mov     rcx, r12; Instance
0x140036d4d  call    PrjfCreateHardLink
0x140036d52  mov     ebx, eax
0x140036d54  test    eax, eax
0x140036d56  jns     loc_140036EBF
0x140036d5c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140036d62  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036d69  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036d70  setnz   r8b
0x140036d74  and     dl, 40h
0x140036d77  jnz     short loc_140036D82
0x140036d79  test    r8b, r8b
0x140036d7c  jz      loc_140036EBF
0x140036d82  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140036d86  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140036d8d  mov     dword ptr [rsp+0F0h+var_A8], 2C5h
0x140036d95  mov     [rsp+0F0h+var_B0], r9
0x140036d9a  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140036da1  mov     [rsp+0F0h+var_B8], r9
0x140036da6  mov     [rsp+0F0h+var_C0], 16h
0x140036dad  jmp     loc_140036E9D
0x140036db2  mov     eax, 0FFFFh
0x140036db7  mov     ebx, 0C0000095h
0x140036dbc  mov     word ptr [rbp+57h+var_60+2], ax
0x140036dc0  test    r14, r14
0x140036dc3  jz      loc_140036EBF
0x140036dc9  mov     edx, 69724A50h; Tag
0x140036dce  mov     rcx, r14; P
  ... truncated ...
```
