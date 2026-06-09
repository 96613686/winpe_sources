# CreateScalableFontResourceInternalW

- ea: `0x18007de28`
- end: `0x18007e385`
- name: `CreateScalableFontResourceInternalW`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18007e390`

## callees

- `0x18007ac50`
- `0x18007ba24`
- `0x18007de28`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e314`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e314`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e33c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e33c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e35a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e35a`
- `ntdll!RtlFreeHeap` at `0x18007e00f`
- `ntdll!RtlFreeHeap` at `0x18007e00f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18007dfc8`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18007dfc8`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e1a6`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e1ef`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e285`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e1a6`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e1ef`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e285`
- `win32u!NtGdiMakeFontDir` at `0x18007dfeb`
- `win32u!NtGdiMakeFontDir` at `0x18007dfeb`

## pseudocode

```c
__int64 __fastcall CreateScalableFontResourceInternalW(unsigned int a1, const WCHAR *a2, WCHAR *a3, WCHAR *a4)
{
  unsigned int v4; // r13d
  int v7; // r11d
  WCHAR *v8; // rdx
  WCHAR *v9; // r8
  WCHAR v10; // ax
  __int64 v11; // r8
  int v12; // r14d
  WCHAR *v13; // rcx
  WCHAR v14; // ax
  __int64 v15; // rcx
  bool v16; // zf
  ULONG v17; // r14d
  ULONG v18; // eax
  const WCHAR *v19; // rdx
  ULONG v20; // edi
  unsigned int v21; // eax
  const WCHAR *v22; // rcx
  int v23; // ebx
  __int64 v24; // r15
  size_t FontDir; // r12
  char *v26; // rcx
  const WCHAR *v28; // r9
  CHAR *v29; // rbx
  __int64 v30; // rcx
  CHAR *v31; // rdi
  const void *v32; // rdx
  CHAR *v33; // rbx
  const WCHAR *v34; // rcx
  HANDLE FileW; // rax
  void *v36; // rbx
  PCWCH UnicodeString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h]
  _OWORD Buffer[5]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v42[3]; // [rsp+B0h] [rbp-50h] BYREF
  int v43; // [rsp+E0h] [rbp-20h]
  __int16 v44; // [rsp+E4h] [rbp-1Ch]
  _BYTE v45[26]; // [rsp+E6h] [rbp-1Ah]
  __int16 v46; // [rsp+100h] [rbp+0h]
  int v47; // [rsp+102h] [rbp+2h]
  __int16 v48; // [rsp+106h] [rbp+6h]
  __int16 v49; // [rsp+108h] [rbp+8h]
  __int16 v50; // [rsp+10Ah] [rbp+Ah]
  char v51; // [rsp+10Ch] [rbp+Ch]
  __int16 v52; // [rsp+10Dh] [rbp+Dh]
  char v53; // [rsp+10Fh] [rbp+Fh]
  __int128 v54; // [rsp+110h] [rbp+10h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+128h] [rbp+28h]
  char v57; // [rsp+12Ch] [rbp+2Ch]
  char v58; // [rsp+12Dh] [rbp+2Dh]
  __int128 v59; // [rsp+12Eh] [rbp+2Eh]
  _BYTE v60[22]; // [rsp+13Eh] [rbp+3Eh]
  char v61; // [rsp+154h] [rbp+54h]
  CHAR MbString[267]; // [rsp+155h] [rbp+55h] BYREF
  __int16 v63; // [rsp+260h] [rbp+160h]
  CHAR v64[400]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE Src[118]; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v66; // [rsp+666h] [rbp+566h] BYREF
  WCHAR DosPathName[264]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v4 = 0;
  lpFileName = a2;
  if ( a3 && a2 )
  {
    v7 = 1;
    v8 = DosPathName;
    if ( a4 )
    {
      v9 = a4;
      while ( 1 )
      {
        v10 = *v9++;
        *v8 = v10;
        if ( !v10 )
          break;
        if ( (__int64)(((char *)++v8 - (char *)DosPathName) & 0xFFFFFFFFFFFFFFFEuLL) >= 518 )
          return 0;
      }
      v11 = v9 - a4;
      v12 = v11 - 1;
      if ( (_DWORD)v11 != 1 )
      {
        if ( DosPathName[(unsigned int)(v11 - 2)] != 92 )
        {
          *v8 = 92;
          v12 = v11;
          *++v8 = 0;
        }
        v7 = 0;
      }
    }
    else
    {
      v12 = 0;
    }
    v13 = a3;
    while ( 1 )
    {
      v14 = *v13++;
      *v8 = v14;
      if ( !v14 )
        break;
      if ( (__int64)(((char *)++v8 - (char *)DosPathName) & 0xFFFFFFFFFFFFFFFEuLL) >= 518 )
        return 0;
    }
    v15 = v13 - a3;
    v16 = (_DWORD)v15 + v12 == 0;
    v17 = v15 + v12;
    v18 = v17;
    if ( !v16 )
    {
      do
      {
        if ( *v8 == 92 )
          break;
        --v8;
        --v18;
      }
      while ( v18 );
    }
    v19 = v8 + 1;
    v16 = v17 == v18;
    v20 = v17 - v18;
    UnicodeString = v19;
    v21 = 0;
    v22 = v19;
    if ( v16 )
      goto LABEL_24;
    do
    {
      if ( *v19 == 46 )
        break;
      ++v21;
      ++v19;
    }
    while ( v21 < v20 );
    v23 = 8;
    if ( v21 < 8 )
LABEL_24:
      v23 = v21;
    if ( v7 )
    {
      LODWORD(v24) = 0;
    }
    else
    {
      v17 = v20;
      v24 = v22 - DosPathName;
    }
    memset_0(Src, 0, 0xFBu);
    NtPathName = 0;
    RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0);
    FontDir = (unsigned int)NtGdiMakeFontDir(a1, Src, 251, NtPathName.Buffer, (unsigned int)NtPathName.Length + 2);
    if ( NtPathName.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    if ( (_DWORD)FontDir )
    {
      v26 = &v66;
      while ( *v26++ )
        ;
      *(_QWORD *)&NtPathName.Length = v26;
      while ( *v26 )
      {
        ++v26;
        ++v4;
      }
      memset_0(MbString, 0, 0x48Cu);
      v43 = 268780878;
      v47 = 4194368;
      v56 = 4718592;
      v57 = (unsigned int)(FontDir + 15) >> 4;
      Buffer[0] = xmmword_1800BEF70;
      Buffer[2] = xmmword_1800BEF90;
      Buffer[1] = xmmword_1800BEF80;
      Buffer[4] = xmmword_1800BEFB0;
      Buffer[3] = xmmword_1800BEFA0;
      qmemcpy(v42, "is is a TrueType font, not a pro", 32);
      *(_OWORD *)v45 = xmmword_1800BEEF6;
      v58 = (unsigned int)(FontDir + 15) >> 12;
      v42[2] = xmmword_1800BEFE0;
      v44 = v23 + 122 + v20 + 1;
      *(_OWORD *)&v45[10] = *(__int128 *)((char *)&xmmword_1800BEEF6 + 10);
      v51 = v23 + 122 + v20 + 1 - 124;
      v54 = xmmword_1800BEF20;
      v55 = 0x180070004LL;
      v59 = xmmword_1800BEF3E;
      v53 = 0;
      v50 = v23 + 122;
      v49 = v23 + 122;
      v52 = (unsigned __int8)((unsigned __int16)(v44 + 132) >> 8);
      *(_OWORD *)v60 = xmmword_1800BEF4E;
      v48 = 116;
      *(_QWORD *)&v60[14] = 0x524944544E4F4607LL;
      v46 = v4 + 12;
      v61 = v23;
      RtlUnicodeToMultiByteN(MbString, v23 + 1, 0, UnicodeString, 2 * v23 + 2);
      v28 = UnicodeString;
      MbString[v23] = 0;
      MbString[(unsigned __int8)v23] = 0;
      v29 = &MbString[(unsigned __int8)v23 + 1];
      *v29++ = 0;
      *v29++ = 0;
      *v29++ = 0;
      *v29++ = 0;
      *v29 = v20;
      RtlUnicodeToMultiByteN(v29 + 1, v20, 0, v28, 2 * v20);
      v30 = (unsigned __int8)v20;
      v29[v20] = 0;
      v31 = &v29[(unsigned __int8)v20 + 2];
      v29[v30 + 1] = 0;
      *v31++ = 0;
      *v31++ = 0;
      *v31++ = 0;
      v32 = *(const void **)&NtPathName.Length;
      *v31 = v4 + 12;
      *(_QWORD *)(v31 + 1) = 0x3A534552544E4F46LL;
      memcpy_0(v31 + 9, v32, v4);
      *(_QWORD *)&v31[v4 + 9] = 0;
      v63 = 195;
      if ( v17 <= 0x80 )
      {
        RtlUnicodeToMultiByteN(v64, v17, 0, &DosPathName[(int)v24], 2 * v17);
        v64[v17 - 1] = 0;
        memset_0(&v64[v17], 0, 128 - v17);
        v33 = &v64[v17 + 128 - v17];
        if ( (__int64)(FontDir + v33 - (CHAR *)Buffer) <= 1409 )
        {
          memcpy_0(v33, Src, FontDir);
          v34 = lpFileName;
          *(_OWORD *)&v33[FontDir] = 0;
          FileW = CreateFileW(v34, 0xC0000000, 1u, 0, 1u, 0x80u, 0);
          v36 = FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            LODWORD(UnicodeString) = 0;
            if ( WriteFile(FileW, Buffer, 0x581u, (LPDWORD)&UnicodeString, 0) && CloseHandle(v36) )
              return 1;
            CloseHandle(v36);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007de28  push    rbp
0x18007de2a  push    rbx
0x18007de2b  push    rsi
0x18007de2c  push    rdi
0x18007de2d  push    r12
0x18007de2f  push    r13
0x18007de31  push    r14
0x18007de33  push    r15
0x18007de35  lea     rbp, [rsp-818h]
0x18007de3d  sub     rsp, 918h
0x18007de44  mov     rax, cs:__security_cookie
0x18007de4b  xor     rax, rsp
0x18007de4e  mov     [rbp+850h+var_50], rax
0x18007de55  xor     r13d, r13d
0x18007de58  mov     [rsp+950h+lpFileName], rdx
0x18007de5d  mov     r10, r8
0x18007de60  mov     rax, rdx
0x18007de63  mov     esi, ecx
0x18007de65  test    r8, r8
0x18007de68  jz      loc_18007E360
0x18007de6e  test    rax, rax
0x18007de71  jz      loc_18007E360
0x18007de77  lea     r11d, [r13+1]
0x18007de7b  mov     edi, 206h
0x18007de80  lea     rdx, [rbp+850h+DosPathName]
0x18007de87  lea     ebx, [r13+5Ch]
0x18007de8b  test    r9, r9
0x18007de8e  jz      short loc_18007DEF2
0x18007de90  mov     r8, r9
0x18007de93  movzx   eax, word ptr [r8]
0x18007de97  add     r8, 2
0x18007de9b  mov     [rdx], ax
0x18007de9e  test    ax, ax
0x18007dea1  jz      short loc_18007DEC2
0x18007dea3  add     rdx, 2
0x18007dea7  lea     rcx, [rbp+850h+DosPathName]
0x18007deae  mov     rax, rdx
0x18007deb1  sub     rax, rcx
0x18007deb4  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007deb8  cmp     rax, rdi
0x18007debb  jl      short loc_18007DE93
0x18007debd  jmp     loc_18007E360
0x18007dec2  sub     r8, r9
0x18007dec5  sar     r8, 1
0x18007dec8  lea     r14d, [r8-1]
0x18007decc  test    r14d, r14d
0x18007decf  jz      short loc_18007DEF5
0x18007ded1  lea     eax, [r14-1]
0x18007ded5  cmp     [rbp+rax*2+850h+DosPathName], bx
0x18007dedd  jz      short loc_18007DEED
0x18007dedf  mov     [rdx], bx
0x18007dee2  mov     r14d, r8d
0x18007dee5  add     rdx, 2
0x18007dee9  mov     [rdx], r13w
0x18007deed  mov     r11d, r13d
0x18007def0  jmp     short loc_18007DEF5
0x18007def2  mov     r14d, r13d
0x18007def5  mov     rcx, r10
0x18007def8  movzx   eax, word ptr [rcx]
0x18007defb  add     rcx, 2
0x18007deff  mov     [rdx], ax
0x18007df02  test    ax, ax
0x18007df05  jz      short loc_18007DF26
0x18007df07  add     rdx, 2
0x18007df0b  lea     r8, [rbp+850h+DosPathName]
0x18007df12  mov     rax, rdx
0x18007df15  sub     rax, r8
0x18007df18  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007df1c  cmp     rax, rdi
0x18007df1f  jl      short loc_18007DEF8
0x18007df21  jmp     loc_18007E360
0x18007df26  sub     rcx, r10
0x18007df29  sar     rcx, 1
0x18007df2c  add     r14d, ecx
0x18007df2f  mov     eax, r14d
0x18007df32  jz      short loc_18007DF42
0x18007df34  cmp     [rdx], bx
0x18007df37  jz      short loc_18007DF42
0x18007df39  sub     rdx, 2
0x18007df3d  add     eax, 0FFFFFFFFh
0x18007df40  jnz     short loc_18007DF34
0x18007df42  add     rdx, 2
0x18007df46  mov     edi, r14d
0x18007df49  sub     edi, eax
0x18007df4b  mov     [rsp+950h+UnicodeString], rdx
0x18007df50  mov     eax, r13d
0x18007df53  mov     rcx, rdx
0x18007df56  jz      short loc_18007DF78
0x18007df58  mov     r8d, 1
0x18007df5e  cmp     word ptr [rdx], 2Eh ; '.'
0x18007df62  jz      short loc_18007DF6F
0x18007df64  add     eax, r8d
0x18007df67  add     rdx, 2
0x18007df6b  cmp     eax, edi
0x18007df6d  jb      short loc_18007DF5E
0x18007df6f  mov     ebx, 8
0x18007df74  cmp     eax, ebx
0x18007df76  jnb     short loc_18007DF7A
0x18007df78  mov     ebx, eax
0x18007df7a  test    r11d, r11d
0x18007df7d  jz      short loc_18007DF84
0x18007df7f  mov     r15d, r13d
0x18007df82  jmp     short loc_18007DF97
0x18007df84  lea     rax, [rbp+850h+DosPathName]
0x18007df8b  mov     r15, rcx
0x18007df8e  sub     r15, rax
0x18007df91  mov     r14d, edi
0x18007df94  sar     r15, 1
0x18007df97  mov     r12d, 0FBh
0x18007df9d  lea     rcx, [rbp+850h+Src]; void *
0x18007dfa4  mov     r8d, r12d; Size
0x18007dfa7  xor     edx, edx; Val
0x18007dfa9  call    memset_0
0x18007dfae  xorps   xmm0, xmm0
0x18007dfb1  lea     rdx, [rsp+950h+NtPathName]; NtPathName
0x18007dfb6  xor     r9d, r9d; DirectoryInfo
0x18007dfb9  lea     rcx, [rbp+850h+DosPathName]; DosPathName
0x18007dfc0  xor     r8d, r8d; NtFileNamePart
0x18007dfc3  movups  xmmword ptr [rsp+950h+NtPathName.Length], xmm0
0x18007dfc8  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18007dfce  movzx   eax, [rsp+950h+NtPathName.Length]
0x18007dfd3  lea     rdx, [rbp+850h+Src]
0x18007dfda  mov     r9, [rsp+950h+NtPathName.Buffer]
0x18007dfdf  add     eax, 2
0x18007dfe2  mov     r8d, r12d
0x18007dfe5  mov     [rsp+950h+UnicodeSize], eax
0x18007dfe9  mov     ecx, esi
0x18007dfeb  call    cs:__imp_NtGdiMakeFontDir
0x18007dff1  mov     r12d, eax
0x18007dff4  cmp     [rsp+950h+NtPathName.Buffer], r13
0x18007dff9  jz      short loc_18007E015
0x18007dffb  mov     rcx, gs:60h
0x18007e004  xor     edx, edx; Flags
0x18007e006  mov     r8, [rsp+950h+NtPathName.Buffer]; P
0x18007e00b  mov     rcx, [rcx+30h]; HeapHandle
0x18007e00f  call    cs:__imp_RtlFreeHeap
0x18007e015  test    r12d, r12d
0x18007e018  jz      loc_18007E360
0x18007e01e  lea     rcx, [rbp+850h+var_2EA]
0x18007e025  mov     edx, 1
0x18007e02a  mov     al, [rcx]
0x18007e02c  add     rcx, rdx
0x18007e02f  test    al, al
0x18007e031  jnz     short loc_18007E02A
0x18007e033  mov     qword ptr [rsp+950h+NtPathName.Length], rcx
0x18007e038  xor     esi, esi
0x18007e03a  jmp     short loc_18007E042
0x18007e03c  add     rcx, rdx
0x18007e03f  add     r13d, edx
0x18007e042  cmp     [rcx], sil
0x18007e045  jnz     short loc_18007E03C
0x18007e047  xor     edx, edx; Val
0x18007e049  lea     rcx, [rbp+850h+MbString]; void *
0x18007e04d  mov     r8d, 48Ch; Size
0x18007e053  call    memset_0
0x18007e058  mov     eax, cs:dword_1800BEEF0
0x18007e05e  lea     ecx, [r12+0Fh]
0x18007e063  movaps  xmm0, cs:xmmword_1800BEF70
0x18007e06a  lea     edx, [rdi+1]
0x18007e06d  movaps  xmm1, cs:xmmword_1800BEF80
0x18007e074  xor     r8d, r8d; ResultSize
0x18007e077  mov     r9, [rsp+950h+UnicodeString]; UnicodeString
0x18007e07c  mov     [rbp+850h+var_870], eax
0x18007e07f  mov     eax, cs:dword_1800BEF12
0x18007e085  mov     [rbp+850h+var_84E], eax
0x18007e088  mov     eax, cs:dword_1800BEF38
0x18007e08e  mov     [rbp+850h+var_828], eax
0x18007e091  mov     eax, ecx
0x18007e093  shr     eax, 4
0x18007e096  mov     [rbp+850h+var_824], al
0x18007e099  movaps  [rsp+950h+Buffer], xmm0
0x18007e09e  movaps  xmm0, cs:xmmword_1800BEF90
0x18007e0a5  movaps  [rbp+850h+var_8D0], xmm0
0x18007e0a9  movaps  xmm0, cs:xmmword_1800BEFB0
0x18007e0b0  movaps  [rsp+950h+var_8E0], xmm1
0x18007e0b5  movaps  xmm1, cs:xmmword_1800BEFA0
0x18007e0bc  movaps  [rbp+850h+var_8B0], xmm0
0x18007e0c0  movaps  xmm0, cs:xmmword_1800BEFD0
0x18007e0c7  movaps  [rbp+850h+var_8C0], xmm1
0x18007e0cb  movaps  xmm1, cs:xmmword_1800BEFC0
0x18007e0d2  movaps  [rbp+850h+var_890], xmm0
0x18007e0d6  movups  xmm0, cs:xmmword_1800BEEF6
0x18007e0dd  shr     ecx, 0Ch
0x18007e0e0  movaps  [rbp+850h+var_8A0], xmm1
0x18007e0e4  movaps  xmm1, cs:xmmword_1800BEFE0
0x18007e0eb  movups  xmmword ptr [rbp+850h+var_86A], xmm0
0x18007e0ef  mov     [rbp+850h+var_823], cl
0x18007e0f2  lea     ecx, [rbx+7Ah]
0x18007e0f5  movaps  xmm0, cs:xmmword_1800BEF20
0x18007e0fc  add     dx, cx
0x18007e0ff  movzx   eax, cx
0x18007e102  movaps  [rbp+850h+var_880], xmm1
0x18007e106  movaps  xmm1, cs:xmmword_1800BEEF6+0Ah
0x18007e10d  shr     ax, 8
0x18007e111  mov     byte ptr [rbp+850h+var_846+1], al
0x18007e114  mov     byte ptr [rbp+850h+var_848+1], al
0x18007e117  movzx   eax, dx
0x18007e11a  shr     ax, 8
0x18007e11e  mov     byte ptr [rbp+850h+var_86C+1], al
0x18007e121  mov     eax, 84h
0x18007e126  mov     byte ptr [rbp+850h+var_86C], dl
0x18007e129  add     dx, ax
0x18007e12c  movups  xmmword ptr [rbp+850h+var_86A+0Ah], xmm1
0x18007e130  lea     eax, [r13+0Ch]
0x18007e134  mov     [rbp+850h+var_844], dl
0x18007e137  movsd   xmm1, cs:qword_1800BEF30
0x18007e13f  movdqu  [rbp+850h+var_840], xmm0
0x18007e144  shr     eax, 8
0x18007e147  movups  xmm0, cs:xmmword_1800BEF3E
0x18007e14e  shr     dx, 8
0x18007e152  movsd   [rbp+850h+var_830], xmm1
0x18007e157  movups  xmm1, cs:xmmword_1800BEF4E
0x18007e15e  mov     byte ptr [rbp+850h+var_850+1], al
0x18007e161  lea     eax, ds:2[rbx*2]
0x18007e168  movups  [rbp+850h+var_822], xmm0
0x18007e16c  mov     [rbp+850h+var_842], si
0x18007e170  lea     esi, [r13+0Ch]
0x18007e174  movsd   xmm0, qword ptr cs:xmmword_1800BEF4E+0Eh
0x18007e17c  mov     byte ptr [rbp+850h+var_846], cl
0x18007e17f  mov     byte ptr [rbp+850h+var_848], cl
0x18007e182  lea     rcx, [rbp+850h+MbString]; MbString
0x18007e186  mov     [rbp+850h+var_843], dl
0x18007e189  lea     edx, [rbx+1]; MbSize
0x18007e18c  movups  xmmword ptr [rbp+850h+var_812], xmm1
0x18007e190  mov     [rsp+950h+UnicodeSize], eax; UnicodeSize
0x18007e194  mov     [rbp+850h+var_84A], 74h ; 't'
0x18007e19a  movsd   qword ptr [rbp+850h+var_812+0Eh], xmm0
0x18007e19f  mov     byte ptr [rbp+850h+var_850], sil
0x18007e1a3  mov     [rbp+850h+var_7FC], bl
0x18007e1a6  call    cs:__imp_RtlUnicodeToMultiByteN
0x18007e1ac  mov     eax, ebx
0x18007e1ae  xor     edx, edx
0x18007e1b0  mov     r9, [rsp+950h+UnicodeString]; UnicodeString
0x18007e1b5  xor     r8d, r8d; ResultSize
0x18007e1b8  mov     [rbp+rax+850h+MbString], dl
0x18007e1bc  lea     eax, [rdx+1]
0x18007e1bf  movzx   ecx, bl
0x18007e1c2  mov     [rbp+rcx+850h+MbString], dl
0x18007e1c6  lea     rbx, [rbp+rcx+850h+var_7FA]
0x18007e1cb  mov     [rbx], dl
0x18007e1cd  add     rbx, rax
0x18007e1d0  mov     [rbx], dl
0x18007e1d2  add     rbx, rax
0x18007e1d5  mov     [rbx], dl
0x18007e1d7  add     rbx, rax
0x18007e1da  mov     [rbx], dl
0x18007e1dc  add     rbx, rax
0x18007e1df  lea     eax, [rdi+rdi]
0x18007e1e2  mov     edx, edi; MbSize
0x18007e1e4  mov     [rsp+950h+UnicodeSize], eax; UnicodeSize
0x18007e1e8  lea     rcx, [rbx+1]; MbString
0x18007e1ec  mov     [rbx], dil
0x18007e1ef  call    cs:__imp_RtlUnicodeToMultiByteN
0x18007e1f5  lea     eax, [rdi-1]
0x18007e1f8  movzx   ecx, dil
0x18007e1fc  xor     edx, edx
0x18007e1fe  mov     r8d, r13d; Size
0x18007e201  lea     rdi, [rbx+2]
0x18007e205  mov     [rax+rbx+1], dl
0x18007e209  add     rdi, rcx
0x18007e20c  mov     [rcx+rbx+1], dl
0x18007e210  lea     eax, [rdx+1]
0x18007e213  mov     ebx, r13d
0x18007e216  mov     [rdi], dl
0x18007e218  add     rdi, rax
0x18007e21b  mov     [rdi], dl
0x18007e21d  add     rdi, rax
0x18007e220  mov     [rdi], dl
0x18007e222  add     rdi, rax
0x18007e225  mov     rdx, qword ptr [rsp+950h+NtPathName.Length]; Src
0x18007e22a  mov     [rdi], sil
0x18007e22d  lea     rcx, [rdi+9]; void *
0x18007e231  mov     rax, cs:qword_1800BEEE0
0x18007e238  mov     [rdi+1], rax
0x18007e23c  call    memcpy_0
0x18007e241  xor     eax, eax
0x18007e243  xor     esi, esi
0x18007e245  mov     r13d, 80h
0x18007e24b  mov     [rdi+rbx+9], rax
0x18007e250  mov     [rbp+850h+var_6F0], 0C3h
0x18007e259  cmp     r14d, r13d
0x18007e25c  ja      loc_18007E360
0x18007e262  movsxd  rax, r15d
0x18007e265  lea     ecx, [r14+r14]
0x18007e269  mov     [rsp+950h+UnicodeSize], ecx; UnicodeSize
0x18007e26d  lea     r9, [rbp+850h+DosPathName]
0x18007e274  xor     r8d, r8d; ResultSize
0x18007e277  lea     rcx, [rbp+850h+var_4F0]; MbString
0x18007e27e  mov     edx, r14d; MbSize
0x18007e281  lea     r9, [r9+rax*2]; UnicodeString
0x18007e285  call    cs:__imp_RtlUnicodeToMultiByteN
0x18007e28b  lea     eax, [r14-1]
0x18007e28f  xor     edx, edx; Val
0x18007e291  lea     rdi, [rbp+850h+var_4F0]
0x18007e298  mov     [rbp+rax+850h+var_4F0], sil
0x18007e2a0  mov     eax, r14d
0x18007e2a3  add     rdi, rax
0x18007e2a6  mov     eax, r13d
0x18007e2a9  sub     eax, r14d
0x18007e2ac  mov     rcx, rdi; void *
  ... truncated ...
```
