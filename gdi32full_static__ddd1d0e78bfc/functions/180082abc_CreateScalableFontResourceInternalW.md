# CreateScalableFontResourceInternalW

- ea: `0x180082abc`
- end: `0x180083056`
- name: `CreateScalableFontResourceInternalW`
- size: `1434`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180083060`

## callees

- `0x18007f800`
- `0x180080604`
- `0x180082abc`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082fcc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082fcc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180082ffa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180082ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008300d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083024`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008300d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083024`
- `ntdll!RtlFreeHeap` at `0x180082caf`
- `ntdll!RtlFreeHeap` at `0x180082caf`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180082c5c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180082c5c`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180082e4c`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180082e9b`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180082f37`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180082e4c`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180082e9b`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180082f37`
- `win32u!NtGdiMakeFontDir` at `0x180082c85`
- `win32u!NtGdiMakeFontDir` at `0x180082c85`

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
      Buffer[0] = xmmword_1800C1F90;
      Buffer[2] = xmmword_1800C1FB0;
      Buffer[1] = xmmword_1800C1FA0;
      Buffer[4] = xmmword_1800C1FD0;
      Buffer[3] = xmmword_1800C1FC0;
      qmemcpy(v42, "is is a TrueType font, not a pro", 32);
      *(_OWORD *)v45 = xmmword_1800C1F16;
      v58 = (unsigned int)(FontDir + 15) >> 12;
      v42[2] = xmmword_1800C2000;
      v44 = v23 + 122 + v20 + 1;
      *(_OWORD *)&v45[10] = *(__int128 *)((char *)&xmmword_1800C1F16 + 10);
      v51 = v23 + 122 + v20 + 1 - 124;
      v54 = xmmword_1800C1F40;
      v55 = 0x180070004LL;
      v59 = xmmword_1800C1F5E;
      v53 = 0;
      v50 = v23 + 122;
      v49 = v23 + 122;
      v52 = (unsigned __int8)((unsigned __int16)(v44 + 132) >> 8);
      *(_OWORD *)v60 = xmmword_1800C1F6E;
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
0x180082abc  push    rbp
0x180082abe  push    rbx
0x180082abf  push    rsi
0x180082ac0  push    rdi
0x180082ac1  push    r12
0x180082ac3  push    r13
0x180082ac5  push    r14
0x180082ac7  push    r15
0x180082ac9  lea     rbp, [rsp-818h]
0x180082ad1  sub     rsp, 918h
0x180082ad8  mov     rax, cs:__security_cookie
0x180082adf  xor     rax, rsp
0x180082ae2  mov     [rbp+850h+var_50], rax
0x180082ae9  xor     r13d, r13d
0x180082aec  mov     [rsp+950h+lpFileName], rdx
0x180082af1  mov     r10, r8
0x180082af4  mov     rax, rdx
0x180082af7  mov     esi, ecx
0x180082af9  test    r8, r8
0x180082afc  jz      loc_180083030
0x180082b02  test    rax, rax
0x180082b05  jz      loc_180083030
0x180082b0b  lea     r11d, [r13+1]
0x180082b0f  mov     edi, 206h
0x180082b14  lea     rdx, [rbp+850h+DosPathName]
0x180082b1b  lea     ebx, [r13+5Ch]
0x180082b1f  test    r9, r9
0x180082b22  jz      short loc_180082B86
0x180082b24  mov     r8, r9
0x180082b27  movzx   eax, word ptr [r8]
0x180082b2b  add     r8, 2
0x180082b2f  mov     [rdx], ax
0x180082b32  test    ax, ax
0x180082b35  jz      short loc_180082B56
0x180082b37  add     rdx, 2
0x180082b3b  lea     rcx, [rbp+850h+DosPathName]
0x180082b42  mov     rax, rdx
0x180082b45  sub     rax, rcx
0x180082b48  and     rax, 0FFFFFFFFFFFFFFFEh
0x180082b4c  cmp     rax, rdi
0x180082b4f  jl      short loc_180082B27
0x180082b51  jmp     loc_180083030
0x180082b56  sub     r8, r9
0x180082b59  sar     r8, 1
0x180082b5c  lea     r14d, [r8-1]
0x180082b60  test    r14d, r14d
0x180082b63  jz      short loc_180082B89
0x180082b65  lea     eax, [r14-1]
0x180082b69  cmp     [rbp+rax*2+850h+DosPathName], bx
0x180082b71  jz      short loc_180082B81
0x180082b73  mov     [rdx], bx
0x180082b76  mov     r14d, r8d
0x180082b79  add     rdx, 2
0x180082b7d  mov     [rdx], r13w
0x180082b81  mov     r11d, r13d
0x180082b84  jmp     short loc_180082B89
0x180082b86  mov     r14d, r13d
0x180082b89  mov     rcx, r10
0x180082b8c  movzx   eax, word ptr [rcx]
0x180082b8f  add     rcx, 2
0x180082b93  mov     [rdx], ax
0x180082b96  test    ax, ax
0x180082b99  jz      short loc_180082BBA
0x180082b9b  add     rdx, 2
0x180082b9f  lea     r8, [rbp+850h+DosPathName]
0x180082ba6  mov     rax, rdx
0x180082ba9  sub     rax, r8
0x180082bac  and     rax, 0FFFFFFFFFFFFFFFEh
0x180082bb0  cmp     rax, rdi
0x180082bb3  jl      short loc_180082B8C
0x180082bb5  jmp     loc_180083030
0x180082bba  sub     rcx, r10
0x180082bbd  sar     rcx, 1
0x180082bc0  add     r14d, ecx
0x180082bc3  mov     eax, r14d
0x180082bc6  jz      short loc_180082BD6
0x180082bc8  cmp     [rdx], bx
0x180082bcb  jz      short loc_180082BD6
0x180082bcd  sub     rdx, 2
0x180082bd1  add     eax, 0FFFFFFFFh
0x180082bd4  jnz     short loc_180082BC8
0x180082bd6  add     rdx, 2
0x180082bda  mov     edi, r14d
0x180082bdd  sub     edi, eax
0x180082bdf  mov     [rsp+950h+UnicodeString], rdx
0x180082be4  mov     eax, r13d
0x180082be7  mov     rcx, rdx
0x180082bea  jz      short loc_180082C0C
0x180082bec  mov     r8d, 1
0x180082bf2  cmp     word ptr [rdx], 2Eh ; '.'
0x180082bf6  jz      short loc_180082C03
0x180082bf8  add     eax, r8d
0x180082bfb  add     rdx, 2
0x180082bff  cmp     eax, edi
0x180082c01  jb      short loc_180082BF2
0x180082c03  mov     ebx, 8
0x180082c08  cmp     eax, ebx
0x180082c0a  jnb     short loc_180082C0E
0x180082c0c  mov     ebx, eax
0x180082c0e  test    r11d, r11d
0x180082c11  jz      short loc_180082C18
0x180082c13  mov     r15d, r13d
0x180082c16  jmp     short loc_180082C2B
0x180082c18  lea     rax, [rbp+850h+DosPathName]
0x180082c1f  mov     r15, rcx
0x180082c22  sub     r15, rax
0x180082c25  mov     r14d, edi
0x180082c28  sar     r15, 1
0x180082c2b  mov     r12d, 0FBh
0x180082c31  lea     rcx, [rbp+850h+Src]; void *
0x180082c38  mov     r8d, r12d; Size
0x180082c3b  xor     edx, edx; Val
0x180082c3d  call    memset_0
0x180082c42  xorps   xmm0, xmm0
0x180082c45  lea     rdx, [rsp+950h+NtPathName]; NtPathName
0x180082c4a  xor     r9d, r9d; DirectoryInfo
0x180082c4d  lea     rcx, [rbp+850h+DosPathName]; DosPathName
0x180082c54  xor     r8d, r8d; NtFileNamePart
0x180082c57  movups  xmmword ptr [rsp+950h+NtPathName.Length], xmm0
0x180082c5c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180082c63  nop     dword ptr [rax+rax+00h]
0x180082c68  movzx   eax, [rsp+950h+NtPathName.Length]
0x180082c6d  lea     rdx, [rbp+850h+Src]
0x180082c74  mov     r9, [rsp+950h+NtPathName.Buffer]
0x180082c79  add     eax, 2
0x180082c7c  mov     r8d, r12d
0x180082c7f  mov     [rsp+950h+UnicodeSize], eax
0x180082c83  mov     ecx, esi
0x180082c85  call    cs:__imp_NtGdiMakeFontDir
0x180082c8c  nop     dword ptr [rax+rax+00h]
0x180082c91  mov     r12d, eax
0x180082c94  cmp     [rsp+950h+NtPathName.Buffer], r13
0x180082c99  jz      short loc_180082CBB
0x180082c9b  mov     rcx, gs:60h
0x180082ca4  xor     edx, edx; Flags
0x180082ca6  mov     r8, [rsp+950h+NtPathName.Buffer]; P
0x180082cab  mov     rcx, [rcx+30h]; HeapHandle
0x180082caf  call    cs:__imp_RtlFreeHeap
0x180082cb6  nop     dword ptr [rax+rax+00h]
0x180082cbb  test    r12d, r12d
0x180082cbe  jz      loc_180083030
0x180082cc4  lea     rcx, [rbp+850h+var_2EA]
0x180082ccb  mov     edx, 1
0x180082cd0  mov     al, [rcx]
0x180082cd2  add     rcx, rdx
0x180082cd5  test    al, al
0x180082cd7  jnz     short loc_180082CD0
0x180082cd9  mov     qword ptr [rsp+950h+NtPathName.Length], rcx
0x180082cde  xor     esi, esi
0x180082ce0  jmp     short loc_180082CE8
0x180082ce2  add     rcx, rdx
0x180082ce5  add     r13d, edx
0x180082ce8  cmp     [rcx], sil
0x180082ceb  jnz     short loc_180082CE2
0x180082ced  xor     edx, edx; Val
0x180082cef  lea     rcx, [rbp+850h+MbString]; void *
0x180082cf3  mov     r8d, 48Ch; Size
0x180082cf9  call    memset_0
0x180082cfe  mov     eax, cs:dword_1800C1F10
0x180082d04  lea     ecx, [r12+0Fh]
0x180082d09  movaps  xmm0, cs:xmmword_1800C1F90
0x180082d10  lea     edx, [rdi+1]
0x180082d13  movaps  xmm1, cs:xmmword_1800C1FA0
0x180082d1a  xor     r8d, r8d; ResultSize
0x180082d1d  mov     r9, [rsp+950h+UnicodeString]; UnicodeString
0x180082d22  mov     [rbp+850h+var_870], eax
0x180082d25  mov     eax, cs:dword_1800C1F32
0x180082d2b  mov     [rbp+850h+var_84E], eax
0x180082d2e  mov     eax, cs:dword_1800C1F58
0x180082d34  mov     [rbp+850h+var_828], eax
0x180082d37  mov     eax, ecx
0x180082d39  shr     eax, 4
0x180082d3c  mov     [rbp+850h+var_824], al
0x180082d3f  movaps  [rsp+950h+Buffer], xmm0
0x180082d44  movaps  xmm0, cs:xmmword_1800C1FB0
0x180082d4b  movaps  [rbp+850h+var_8D0], xmm0
0x180082d4f  movaps  xmm0, cs:xmmword_1800C1FD0
0x180082d56  movaps  [rsp+950h+var_8E0], xmm1
0x180082d5b  movaps  xmm1, cs:xmmword_1800C1FC0
0x180082d62  movaps  [rbp+850h+var_8B0], xmm0
0x180082d66  movaps  xmm0, cs:xmmword_1800C1FF0
0x180082d6d  movaps  [rbp+850h+var_8C0], xmm1
0x180082d71  movaps  xmm1, cs:xmmword_1800C1FE0
0x180082d78  movaps  [rbp+850h+var_890], xmm0
0x180082d7c  movups  xmm0, cs:xmmword_1800C1F16
0x180082d83  shr     ecx, 0Ch
0x180082d86  movaps  [rbp+850h+var_8A0], xmm1
0x180082d8a  movaps  xmm1, cs:xmmword_1800C2000
0x180082d91  movups  xmmword ptr [rbp+850h+var_86A], xmm0
0x180082d95  mov     [rbp+850h+var_823], cl
0x180082d98  lea     ecx, [rbx+7Ah]
0x180082d9b  movaps  xmm0, cs:xmmword_1800C1F40
0x180082da2  add     dx, cx
0x180082da5  movzx   eax, cx
0x180082da8  movaps  [rbp+850h+var_880], xmm1
0x180082dac  movaps  xmm1, cs:xmmword_1800C1F16+0Ah
0x180082db3  shr     ax, 8
0x180082db7  mov     byte ptr [rbp+850h+var_846+1], al
0x180082dba  mov     byte ptr [rbp+850h+var_848+1], al
0x180082dbd  movzx   eax, dx
0x180082dc0  shr     ax, 8
0x180082dc4  mov     byte ptr [rbp+850h+var_86C+1], al
0x180082dc7  mov     eax, 84h
0x180082dcc  mov     byte ptr [rbp+850h+var_86C], dl
0x180082dcf  add     dx, ax
0x180082dd2  movups  xmmword ptr [rbp+850h+var_86A+0Ah], xmm1
0x180082dd6  lea     eax, [r13+0Ch]
0x180082dda  mov     [rbp+850h+var_844], dl
0x180082ddd  movsd   xmm1, cs:qword_1800C1F50
0x180082de5  movdqu  [rbp+850h+var_840], xmm0
0x180082dea  shr     eax, 8
0x180082ded  movups  xmm0, cs:xmmword_1800C1F5E
0x180082df4  shr     dx, 8
0x180082df8  movsd   [rbp+850h+var_830], xmm1
0x180082dfd  movups  xmm1, cs:xmmword_1800C1F6E
0x180082e04  mov     byte ptr [rbp+850h+var_850+1], al
0x180082e07  lea     eax, ds:2[rbx*2]
0x180082e0e  movups  [rbp+850h+var_822], xmm0
0x180082e12  mov     [rbp+850h+var_842], si
0x180082e16  lea     esi, [r13+0Ch]
0x180082e1a  movsd   xmm0, qword ptr cs:xmmword_1800C1F6E+0Eh
0x180082e22  mov     byte ptr [rbp+850h+var_846], cl
0x180082e25  mov     byte ptr [rbp+850h+var_848], cl
0x180082e28  lea     rcx, [rbp+850h+MbString]; MbString
0x180082e2c  mov     [rbp+850h+var_843], dl
0x180082e2f  lea     edx, [rbx+1]; MbSize
0x180082e32  movups  xmmword ptr [rbp+850h+var_812], xmm1
0x180082e36  mov     [rsp+950h+UnicodeSize], eax; UnicodeSize
0x180082e3a  mov     [rbp+850h+var_84A], 74h ; 't'
0x180082e40  movsd   qword ptr [rbp+850h+var_812+0Eh], xmm0
0x180082e45  mov     byte ptr [rbp+850h+var_850], sil
0x180082e49  mov     [rbp+850h+var_7FC], bl
0x180082e4c  call    cs:__imp_RtlUnicodeToMultiByteN
0x180082e53  nop     dword ptr [rax+rax+00h]
0x180082e58  mov     eax, ebx
0x180082e5a  xor     edx, edx
0x180082e5c  mov     r9, [rsp+950h+UnicodeString]; UnicodeString
0x180082e61  xor     r8d, r8d; ResultSize
0x180082e64  mov     [rbp+rax+850h+MbString], dl
0x180082e68  lea     eax, [rdx+1]
0x180082e6b  movzx   ecx, bl
0x180082e6e  mov     [rbp+rcx+850h+MbString], dl
0x180082e72  lea     rbx, [rbp+rcx+850h+var_7FA]
0x180082e77  mov     [rbx], dl
0x180082e79  add     rbx, rax
0x180082e7c  mov     [rbx], dl
0x180082e7e  add     rbx, rax
0x180082e81  mov     [rbx], dl
0x180082e83  add     rbx, rax
0x180082e86  mov     [rbx], dl
0x180082e88  add     rbx, rax
0x180082e8b  lea     eax, [rdi+rdi]
0x180082e8e  mov     edx, edi; MbSize
0x180082e90  mov     [rsp+950h+UnicodeSize], eax; UnicodeSize
0x180082e94  lea     rcx, [rbx+1]; MbString
0x180082e98  mov     [rbx], dil
0x180082e9b  call    cs:__imp_RtlUnicodeToMultiByteN
0x180082ea2  nop     dword ptr [rax+rax+00h]
0x180082ea7  lea     eax, [rdi-1]
0x180082eaa  movzx   ecx, dil
0x180082eae  xor     edx, edx
0x180082eb0  mov     r8d, r13d; Size
0x180082eb3  lea     rdi, [rbx+2]
0x180082eb7  mov     [rax+rbx+1], dl
0x180082ebb  add     rdi, rcx
0x180082ebe  mov     [rcx+rbx+1], dl
0x180082ec2  lea     eax, [rdx+1]
0x180082ec5  mov     ebx, r13d
0x180082ec8  mov     [rdi], dl
0x180082eca  add     rdi, rax
0x180082ecd  mov     [rdi], dl
0x180082ecf  add     rdi, rax
0x180082ed2  mov     [rdi], dl
0x180082ed4  add     rdi, rax
0x180082ed7  mov     rdx, qword ptr [rsp+950h+NtPathName.Length]; Src
0x180082edc  mov     [rdi], sil
0x180082edf  lea     rcx, [rdi+9]; void *
0x180082ee3  mov     rax, cs:qword_1800C1F00
0x180082eea  mov     [rdi+1], rax
0x180082eee  call    memcpy_0
0x180082ef3  xor     eax, eax
0x180082ef5  xor     esi, esi
0x180082ef7  mov     r13d, 80h
0x180082efd  mov     [rdi+rbx+9], rax
0x180082f02  mov     [rbp+850h+var_6F0], 0C3h
0x180082f0b  cmp     r14d, r13d
0x180082f0e  ja      loc_180083030
0x180082f14  movsxd  rax, r15d
0x180082f17  lea     ecx, [r14+r14]
0x180082f1b  mov     [rsp+950h+UnicodeSize], ecx; UnicodeSize
0x180082f1f  lea     r9, [rbp+850h+DosPathName]
0x180082f26  xor     r8d, r8d; ResultSize
0x180082f29  lea     rcx, [rbp+850h+var_4F0]; MbString
0x180082f30  mov     edx, r14d; MbSize
0x180082f33  lea     r9, [r9+rax*2]; UnicodeString
0x180082f37  call    cs:__imp_RtlUnicodeToMultiByteN
0x180082f3e  nop     dword ptr [rax+rax+00h]
0x180082f43  lea     eax, [r14-1]
0x180082f47  xor     edx, edx; Val
0x180082f49  lea     rdi, [rbp+850h+var_4F0]
  ... truncated ...
```
