# AeComputeFileHashFromHandle

- ea: `0x1800640b4`
- end: `0x18006464b`
- name: `AeComputeFileHashFromHandle`
- size: `1431`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180063f60`

## callees

- `0x180005e40`
- `0x180063f04`
- `0x1800640b4`
- `0x180065d9c`
- `0x180066070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800641e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006425f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800641e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006425f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064621`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064621`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180064104`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180064104`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006424c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006424c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800641d6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800641d6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180064613`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180064613`

## string_xrefs

- `0x180064191`: `AeComputeFileHashFromHandle`
- `0x180064212`: `AeComputeFileHashFromHandle`
- `0x1800642d2`: `AeComputeFileHashFromHandle`
- `0x1800645f6`: `AeComputeFileHashFromHandle`

## pseudocode

```c
__int64 __fastcall AeComputeFileHashFromHandle(char *hFile, __int64 a2, int a3)
{
  __int64 v3; // r15
  HANDLE FileMappingW; // r14
  BYTE *v6; // rsi
  DWORD dwMaximumSizeLow; // ebx
  int v8; // r8d
  __int64 v9; // rax
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  signed int LastError; // ebx
  _WORD *v13; // rax
  int v14; // r8d
  _QWORD *v15; // rcx
  int v16; // edx
  int v17; // r8d
  BYTE v18; // cl
  BYTE v19; // cl
  BYTE v20; // cl
  BYTE v21; // cl
  BYTE v22; // cl
  BYTE v23; // cl
  BYTE v24; // cl
  BYTE v25; // cl
  BYTE v26; // cl
  BYTE v27; // cl
  BYTE v28; // cl
  BYTE v29; // cl
  BYTE v30; // cl
  BYTE v31; // cl
  BYTE v32; // cl
  BYTE v33; // cl
  BYTE v34; // cl
  BYTE v35; // cl
  BYTE v36; // cl
  BYTE v37; // cl
  BYTE v39[24]; // [rsp+48h] [rbp-50h] BYREF

  v3 = a2;
  FileMappingW = 0;
  v6 = 0;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a2 )
  {
    dwMaximumSizeLow = GetFileSize(hFile, 0);
    if ( !dwMaximumSizeLow )
    {
      v9 = 2147483646;
      v10 = L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709";
      v11 = 45;
      do
      {
        if ( !v9 )
          break;
        v8 = *v10;
        if ( !(_WORD)v8 )
          break;
        ++v10;
        *(_WORD *)v3 = v8;
        v3 += 2;
        --v9;
        --v11;
      }
      while ( v11 );
      LastError = v11 == 0 ? 0x8007007A : 0;
      v13 = (_WORD *)(v3 - 2);
      if ( v11 )
        v13 = (_WORD *)v3;
      *v13 = 0;
      if ( v11 )
      {
        LastError = 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v8, (unsigned int)"AeComputeFileHashFromHandle", LastError);
      }
      goto LABEL_38;
    }
    if ( dwMaximumSizeLow > 0x1E00000 )
      dwMaximumSizeLow = 31457280;
    FileMappingW = CreateFileMappingW(hFile, 0, 0x8000002u, 0, dwMaximumSizeLow, 0);
    if ( !FileMappingW )
    {
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 16;
LABEL_21:
        WPP_SF_sd(v15[2], v16, v14, (unsigned int)"AeComputeFileHashFromHandle", LastError);
        goto LABEL_22;
      }
      goto LABEL_22;
    }
    v6 = (BYTE *)MapViewOfFile(FileMappingW, 4u, 0, 0, dwMaximumSizeLow);
    if ( !v6 )
    {
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 17;
        goto LABEL_21;
      }
LABEL_22:
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_38;
    }
    memset(v39, 0, 22);
    LastError = ComputeSha1Hash(v6, dwMaximumSizeLow, &v39[2]);
    if ( LastError >= 0 )
    {
      *(_DWORD *)v3 = 3145776;
      *(_DWORD *)(v3 + 4) = 3145776;
      v18 = v39[2];
      *(_WORD *)(v3 + 8) = a0123456789abcd_0[(unsigned __int64)v39[2] >> 4];
      *(_WORD *)(v3 + 10) = a0123456789abcd_0[v18 & 0xF];
      v19 = v39[3];
      *(_WORD *)(v3 + 12) = a0123456789abcd_0[(unsigned __int64)v39[3] >> 4];
      *(_WORD *)(v3 + 14) = a0123456789abcd_0[v19 & 0xF];
      v20 = v39[4];
      *(_WORD *)(v3 + 16) = a0123456789abcd_0[(unsigned __int64)v39[4] >> 4];
      *(_WORD *)(v3 + 18) = a0123456789abcd_0[v20 & 0xF];
      v21 = v39[5];
      *(_WORD *)(v3 + 20) = a0123456789abcd_0[(unsigned __int64)v39[5] >> 4];
      *(_WORD *)(v3 + 22) = a0123456789abcd_0[v21 & 0xF];
      v22 = v39[6];
      *(_WORD *)(v3 + 24) = a0123456789abcd_0[(unsigned __int64)v39[6] >> 4];
      *(_WORD *)(v3 + 26) = a0123456789abcd_0[v22 & 0xF];
      v23 = v39[7];
      *(_WORD *)(v3 + 28) = a0123456789abcd_0[(unsigned __int64)v39[7] >> 4];
      *(_WORD *)(v3 + 30) = a0123456789abcd_0[v23 & 0xF];
      v24 = v39[8];
      *(_WORD *)(v3 + 32) = a0123456789abcd_0[(unsigned __int64)v39[8] >> 4];
      *(_WORD *)(v3 + 34) = a0123456789abcd_0[v24 & 0xF];
      v25 = v39[9];
      *(_WORD *)(v3 + 36) = a0123456789abcd_0[(unsigned __int64)v39[9] >> 4];
      *(_WORD *)(v3 + 38) = a0123456789abcd_0[v25 & 0xF];
      v26 = v39[10];
      *(_WORD *)(v3 + 40) = a0123456789abcd_0[(unsigned __int64)v39[10] >> 4];
      *(_WORD *)(v3 + 42) = a0123456789abcd_0[v26 & 0xF];
      v27 = v39[11];
      *(_WORD *)(v3 + 44) = a0123456789abcd_0[(unsigned __int64)v39[11] >> 4];
      *(_WORD *)(v3 + 46) = a0123456789abcd_0[v27 & 0xF];
      v28 = v39[12];
      *(_WORD *)(v3 + 48) = a0123456789abcd_0[(unsigned __int64)v39[12] >> 4];
      *(_WORD *)(v3 + 50) = a0123456789abcd_0[v28 & 0xF];
      v29 = v39[13];
      *(_WORD *)(v3 + 52) = a0123456789abcd_0[(unsigned __int64)v39[13] >> 4];
      *(_WORD *)(v3 + 54) = a0123456789abcd_0[v29 & 0xF];
      v30 = v39[14];
      *(_WORD *)(v3 + 56) = a0123456789abcd_0[(unsigned __int64)v39[14] >> 4];
      *(_WORD *)(v3 + 58) = a0123456789abcd_0[v30 & 0xF];
      v31 = v39[15];
      *(_WORD *)(v3 + 60) = a0123456789abcd_0[(unsigned __int64)v39[15] >> 4];
      *(_WORD *)(v3 + 62) = a0123456789abcd_0[v31 & 0xF];
      v32 = v39[16];
      *(_WORD *)(v3 + 64) = a0123456789abcd_0[(unsigned __int64)v39[16] >> 4];
      *(_WORD *)(v3 + 66) = a0123456789abcd_0[v32 & 0xF];
      v33 = v39[17];
      *(_WORD *)(v3 + 68) = a0123456789abcd_0[(unsigned __int64)v39[17] >> 4];
      *(_WORD *)(v3 + 70) = a0123456789abcd_0[v33 & 0xF];
      v34 = v39[18];
      *(_WORD *)(v3 + 72) = a0123456789abcd_0[(unsigned __int64)v39[18] >> 4];
      *(_WORD *)(v3 + 74) = a0123456789abcd_0[v34 & 0xF];
      v35 = v39[19];
      *(_WORD *)(v3 + 76) = a0123456789abcd_0[(unsigned __int64)v39[19] >> 4];
      *(_WORD *)(v3 + 78) = a0123456789abcd_0[v35 & 0xF];
      v36 = v39[20];
      *(_WORD *)(v3 + 80) = a0123456789abcd_0[(unsigned __int64)v39[20] >> 4];
      *(_WORD *)(v3 + 82) = a0123456789abcd_0[v36 & 0xF];
      v37 = v39[21];
      *(_WORD *)(v3 + 84) = a0123456789abcd_0[(unsigned __int64)v39[21] >> 4];
      *(_DWORD *)(v3 + 86) = a0123456789abcd_0[v37 & 0xF];
      LastError = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v17, (unsigned int)"AeComputeFileHashFromHandle", LastError);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, (unsigned int)"AeComputeFileHashFromHandle", 30);
    LastError = -2147024809;
  }
LABEL_38:
  if ( v6 )
    UnmapViewOfFile(v6);
  if ( FileMappingW )
    CloseHandle(FileMappingW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800640b4  mov     [rsp+arg_10], rbx
0x1800640b9  push    rsi
0x1800640ba  push    rdi
0x1800640bb  push    r13
0x1800640bd  push    r14
0x1800640bf  push    r15
0x1800640c1  sub     rsp, 70h
0x1800640c5  mov     rax, cs:__security_cookie
0x1800640cc  xor     rax, rsp
0x1800640cf  mov     [rsp+98h+var_38], rax
0x1800640d4  mov     r15, rdx
0x1800640d7  mov     r13, rcx
0x1800640da  xor     edi, edi
0x1800640dc  mov     r14d, edi
0x1800640df  mov     [rsp+98h+var_60], rdi
0x1800640e4  mov     esi, edi
0x1800640e6  mov     [rsp+98h+var_58], rdi
0x1800640eb  lea     rax, [rcx-1]
0x1800640ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800640f3  ja      loc_1800645D0
0x1800640f9  test    rdx, rdx
0x1800640fc  jz      loc_1800645D0
0x180064102  xor     edx, edx; lpFileSizeHigh
0x180064104  call    cs:__imp_GetFileSize
0x18006410a  mov     ebx, eax
0x18006410c  test    eax, eax
0x18006410e  jnz     loc_1800641AD
0x180064114  mov     eax, 7FFFFFFEh
0x180064119  lea     rdx, a0000da39a3ee5e; "0000da39a3ee5e6b4b0d3255bfef95601890afd"...
0x180064120  lea     ecx, [rdi+2Dh]
0x180064123  test    rax, rax
0x180064126  jz      short loc_180064147
0x180064128  movzx   r8d, word ptr [rdx]
0x18006412c  test    r8w, r8w
0x180064130  jz      short loc_180064147
0x180064132  add     rdx, 2
0x180064136  mov     [r15], r8w
0x18006413a  add     r15, 2
0x18006413e  dec     rax
0x180064141  sub     rcx, 1
0x180064145  jnz     short loc_180064123
0x180064147  mov     rax, rcx
0x18006414a  neg     rax
0x18006414d  sbb     ebx, ebx
0x18006414f  not     ebx
0x180064151  and     ebx, 8007007Ah
0x180064157  lea     rax, [r15-2]
0x18006415b  test    rcx, rcx
0x18006415e  cmovnz  rax, r15
0x180064162  mov     [rax], di
0x180064165  jnz     short loc_1800641A6
0x180064167  lea     rax, WPP_GLOBAL_Control
0x18006416e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064175  cmp     rcx, rax
0x180064178  jz      loc_18006460B
0x18006417e  test    byte ptr [rcx+1Ch], 1
0x180064182  jz      loc_18006460B
0x180064188  mov     edx, 0Fh
0x18006418d  mov     [rsp+98h+dwMaximumSizeLow], ebx
0x180064191  lea     r9, aAecomputefileh; "AeComputeFileHashFromHandle"
0x180064198  mov     rcx, [rcx+10h]
0x18006419c  call    WPP_SF_sd
0x1800641a1  jmp     loc_18006460B
0x1800641a6  mov     ebx, edi
0x1800641a8  jmp     loc_18006460B
0x1800641ad  test    ebx, ebx
0x1800641af  jz      loc_180064285
0x1800641b5  mov     eax, 1E00000h
0x1800641ba  cmp     ebx, eax
0x1800641bc  cmova   ebx, eax
0x1800641bf  mov     [rsp+98h+lpName], rdi; lpName
0x1800641c4  mov     [rsp+98h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800641c8  xor     r9d, r9d; dwMaximumSizeHigh
0x1800641cb  xor     edx, edx; lpFileMappingAttributes
0x1800641cd  mov     r8d, 8000002h; flProtect
0x1800641d3  mov     rcx, r13; hFile
0x1800641d6  call    cs:__imp_CreateFileMappingW
0x1800641dc  mov     r14, rax
0x1800641df  mov     [rsp+98h+var_60], rax
0x1800641e4  test    rax, rax
0x1800641e7  jnz     short loc_180064238
0x1800641e9  call    cs:__imp_GetLastError
0x1800641ef  mov     ebx, eax
0x1800641f1  lea     rax, WPP_GLOBAL_Control
0x1800641f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800641ff  cmp     rcx, rax
0x180064202  jz      short loc_180064222
0x180064204  test    byte ptr [rcx+1Ch], 1
0x180064208  jz      short loc_180064222
0x18006420a  lea     edx, [r14+10h]
0x18006420e  mov     [rsp+98h+dwMaximumSizeLow], ebx
0x180064212  lea     r9, aAecomputefileh; "AeComputeFileHashFromHandle"
0x180064219  mov     rcx, [rcx+10h]
0x18006421d  call    WPP_SF_sd
0x180064222  test    ebx, ebx
0x180064224  jle     loc_18006460B
0x18006422a  movzx   ebx, bx
0x18006422d  or      ebx, 80070000h
0x180064233  jmp     loc_18006460B
0x180064238  mov     eax, ebx
0x18006423a  mov     qword ptr [rsp+98h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18006423f  xor     r9d, r9d; dwFileOffsetLow
0x180064242  xor     r8d, r8d; dwFileOffsetHigh
0x180064245  lea     edx, [r9+4]; dwDesiredAccess
0x180064249  mov     rcx, r14; hFileMappingObject
0x18006424c  call    cs:__imp_MapViewOfFile
0x180064252  mov     rsi, rax
0x180064255  mov     [rsp+98h+var_58], rax
0x18006425a  test    rax, rax
0x18006425d  jnz     short loc_180064285
0x18006425f  call    cs:__imp_GetLastError
0x180064265  mov     ebx, eax
0x180064267  lea     rax, WPP_GLOBAL_Control
0x18006426e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064275  cmp     rcx, rax
0x180064278  jz      short loc_180064222
0x18006427a  test    byte ptr [rcx+1Ch], 1
0x18006427e  jz      short loc_180064222
0x180064280  lea     edx, [rsi+11h]
0x180064283  jmp     short loc_18006420E
0x180064285  xorps   xmm0, xmm0
0x180064288  xor     eax, eax
0x18006428a  movups  xmmword ptr [rsp+98h+var_50], xmm0
0x18006428f  mov     qword ptr [rsp+98h+var_50+0Eh], rax
0x180064294  lea     r8, [rsp+98h+var_50+2]; BYTE *
0x180064299  mov     edx, ebx; dwDataLen
0x18006429b  mov     rcx, rsi; pbData
0x18006429e  call    ComputeSha1Hash
0x1800642a3  mov     ebx, eax
0x1800642a5  mov     [rsp+98h+var_68], eax
0x1800642a9  test    eax, eax
0x1800642ab  jns     short loc_1800642E7
0x1800642ad  lea     rax, WPP_GLOBAL_Control
0x1800642b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800642bb  cmp     rcx, rax
0x1800642be  jz      short loc_1800642E2
0x1800642c0  test    byte ptr [rcx+1Ch], 1
0x1800642c4  jz      short loc_1800642E2
0x1800642c6  movzx   eax, bx
0x1800642c9  mov     edx, 12h
0x1800642ce  mov     [rsp+98h+dwMaximumSizeLow], eax
0x1800642d2  lea     r9, aAecomputefileh; "AeComputeFileHashFromHandle"
0x1800642d9  mov     rcx, [rcx+10h]
0x1800642dd  call    WPP_SF_sd
0x1800642e2  jmp     loc_18006460B
0x1800642e7  mov     dword ptr [r15], 300030h
0x1800642ee  mov     dword ptr [r15+4], 300030h
0x1800642f6  movzx   ecx, [rsp+98h+var_50+2]
0x1800642fb  mov     eax, ecx
0x1800642fd  shr     rax, 4
0x180064301  lea     r8, a0123456789abcd_0; "0123456789abcdef"
0x180064308  movzx   eax, word ptr [r8+rax*2]
0x18006430d  mov     [r15+8], ax
0x180064312  mov     edx, 0Fh
0x180064317  and     rcx, rdx
0x18006431a  movzx   eax, word ptr [r8+rcx*2]
0x18006431f  mov     [r15+0Ah], ax
0x180064324  movzx   ecx, [rsp+98h+var_50+3]
0x180064329  mov     eax, ecx
0x18006432b  shr     rax, 4
0x18006432f  movzx   eax, word ptr [r8+rax*2]
0x180064334  mov     [r15+0Ch], ax
0x180064339  and     rcx, rdx
0x18006433c  movzx   eax, word ptr [r8+rcx*2]
0x180064341  mov     [r15+0Eh], ax
0x180064346  movzx   ecx, [rsp+98h+var_50+4]
0x18006434b  mov     eax, ecx
0x18006434d  shr     rax, 4
0x180064351  movzx   eax, word ptr [r8+rax*2]
0x180064356  mov     [r15+10h], ax
0x18006435b  and     rcx, rdx
0x18006435e  movzx   eax, word ptr [r8+rcx*2]
0x180064363  mov     [r15+12h], ax
0x180064368  movzx   ecx, [rsp+98h+var_50+5]
0x18006436d  mov     eax, ecx
0x18006436f  shr     rax, 4
0x180064373  movzx   eax, word ptr [r8+rax*2]
0x180064378  mov     [r15+14h], ax
0x18006437d  and     rcx, rdx
0x180064380  movzx   eax, word ptr [r8+rcx*2]
0x180064385  mov     [r15+16h], ax
0x18006438a  movzx   ecx, [rsp+98h+var_50+6]
0x18006438f  mov     eax, ecx
0x180064391  shr     rax, 4
0x180064395  movzx   eax, word ptr [r8+rax*2]
0x18006439a  mov     [r15+18h], ax
0x18006439f  and     rcx, rdx
0x1800643a2  movzx   eax, word ptr [r8+rcx*2]
0x1800643a7  mov     [r15+1Ah], ax
0x1800643ac  movzx   ecx, [rsp+98h+var_50+7]
0x1800643b1  mov     eax, ecx
0x1800643b3  shr     rax, 4
0x1800643b7  movzx   eax, word ptr [r8+rax*2]
0x1800643bc  mov     [r15+1Ch], ax
0x1800643c1  and     rcx, rdx
0x1800643c4  movzx   eax, word ptr [r8+rcx*2]
0x1800643c9  mov     [r15+1Eh], ax
0x1800643ce  movzx   ecx, [rsp+98h+var_50+8]
0x1800643d3  mov     eax, ecx
0x1800643d5  shr     rax, 4
0x1800643d9  movzx   eax, word ptr [r8+rax*2]
0x1800643de  mov     [r15+20h], ax
0x1800643e3  and     rcx, rdx
0x1800643e6  movzx   eax, word ptr [r8+rcx*2]
0x1800643eb  mov     [r15+22h], ax
0x1800643f0  movzx   ecx, [rsp+98h+var_50+9]
0x1800643f5  mov     eax, ecx
0x1800643f7  shr     rax, 4
0x1800643fb  movzx   eax, word ptr [r8+rax*2]
0x180064400  mov     [r15+24h], ax
0x180064405  and     rcx, rdx
0x180064408  movzx   eax, word ptr [r8+rcx*2]
0x18006440d  mov     [r15+26h], ax
0x180064412  movzx   ecx, [rsp+98h+var_50+0Ah]
0x180064417  mov     eax, ecx
0x180064419  shr     rax, 4
0x18006441d  movzx   eax, word ptr [r8+rax*2]
0x180064422  mov     [r15+28h], ax
0x180064427  and     rcx, rdx
0x18006442a  movzx   eax, word ptr [r8+rcx*2]
0x18006442f  mov     [r15+2Ah], ax
0x180064434  movzx   ecx, [rsp+98h+var_50+0Bh]
0x180064439  mov     eax, ecx
0x18006443b  shr     rax, 4
0x18006443f  movzx   eax, word ptr [r8+rax*2]
0x180064444  mov     [r15+2Ch], ax
0x180064449  and     rcx, rdx
0x18006444c  movzx   eax, word ptr [r8+rcx*2]
0x180064451  mov     [r15+2Eh], ax
0x180064456  movzx   ecx, [rsp+98h+var_50+0Ch]
0x18006445b  mov     eax, ecx
0x18006445d  shr     rax, 4
0x180064461  movzx   eax, word ptr [r8+rax*2]
0x180064466  mov     [r15+30h], ax
0x18006446b  and     rcx, rdx
0x18006446e  movzx   eax, word ptr [r8+rcx*2]
0x180064473  mov     [r15+32h], ax
0x180064478  movzx   ecx, [rsp+98h+var_50+0Dh]
0x18006447d  mov     eax, ecx
0x18006447f  shr     rax, 4
0x180064483  movzx   eax, word ptr [r8+rax*2]
0x180064488  mov     [r15+34h], ax
0x18006448d  and     rcx, rdx
0x180064490  movzx   eax, word ptr [r8+rcx*2]
0x180064495  mov     [r15+36h], ax
0x18006449a  movzx   ecx, [rsp+98h+var_50+0Eh]
0x18006449f  mov     eax, ecx
0x1800644a1  shr     rax, 4
0x1800644a5  movzx   eax, word ptr [r8+rax*2]
0x1800644aa  mov     [r15+38h], ax
0x1800644af  and     rcx, rdx
0x1800644b2  movzx   eax, word ptr [r8+rcx*2]
0x1800644b7  mov     [r15+3Ah], ax
0x1800644bc  movzx   ecx, [rsp+98h+var_50+0Fh]
0x1800644c1  mov     eax, ecx
0x1800644c3  shr     rax, 4
0x1800644c7  movzx   eax, word ptr [r8+rax*2]
0x1800644cc  mov     [r15+3Ch], ax
0x1800644d1  and     rcx, rdx
0x1800644d4  movzx   eax, word ptr [r8+rcx*2]
0x1800644d9  mov     [r15+3Eh], ax
0x1800644de  movzx   ecx, [rsp+98h+var_40]
0x1800644e3  mov     eax, ecx
0x1800644e5  shr     rax, 4
0x1800644e9  movzx   eax, word ptr [r8+rax*2]
0x1800644ee  mov     [r15+40h], ax
0x1800644f3  and     rcx, rdx
0x1800644f6  movzx   eax, word ptr [r8+rcx*2]
0x1800644fb  mov     [r15+42h], ax
0x180064500  movzx   ecx, [rsp+98h+var_3F]
0x180064505  mov     eax, ecx
0x180064507  shr     rax, 4
0x18006450b  movzx   eax, word ptr [r8+rax*2]
0x180064510  mov     [r15+44h], ax
0x180064515  and     rcx, rdx
0x180064518  movzx   eax, word ptr [r8+rcx*2]
0x18006451d  mov     [r15+46h], ax
0x180064522  movzx   ecx, [rsp+98h+var_3E]
0x180064527  mov     eax, ecx
0x180064529  shr     rax, 4
0x18006452d  movzx   eax, word ptr [r8+rax*2]
0x180064532  mov     [r15+48h], ax
0x180064537  and     rcx, rdx
0x18006453a  movzx   eax, word ptr [r8+rcx*2]
0x18006453f  mov     [r15+4Ah], ax
0x180064544  movzx   ecx, [rsp+98h+var_3D]
0x180064549  mov     eax, ecx
0x18006454b  shr     rax, 4
0x18006454f  movzx   eax, word ptr [r8+rax*2]
0x180064554  mov     [r15+4Ch], ax
0x180064559  and     rcx, rdx
0x18006455c  movzx   eax, word ptr [r8+rcx*2]
0x180064561  mov     [r15+4Eh], ax
0x180064566  movzx   ecx, [rsp+98h+var_3C]
0x18006456b  mov     eax, ecx
0x18006456d  shr     rax, 4
0x180064571  movzx   eax, word ptr [r8+rax*2]
0x180064576  mov     [r15+50h], ax
0x18006457b  and     rcx, rdx
0x18006457e  movzx   eax, word ptr [r8+rcx*2]
  ... truncated ...
```
