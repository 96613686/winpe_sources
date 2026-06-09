# InternalCreateLocalMetaFile

- ea: `0x180075218`
- end: `0x1800754d9`
- name: `InternalCreateLocalMetaFile`
- size: `705`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18007d950`
- `0x1800939c0`

## callees

- `0x180031580`
- `0x18003261c`
- `0x180033420`
- `0x180035440`
- `0x180035f10`
- `0x180075218`
- `0x180090870`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800752fc`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800752fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180075290`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007540f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180075290`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007540f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007545a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800754ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007545a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800754ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180075499`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180075499`
- `GDI32!DeleteDC` at `0x180075471`
- `GDI32!DeleteDC` at `0x180075471`
- `win32u!NtGdiGetServerMetaFileBits` at `0x180075274`
- `win32u!NtGdiGetServerMetaFileBits` at `0x1800752d3`
- `win32u!NtGdiGetServerMetaFileBits` at `0x180075274`
- `win32u!NtGdiGetServerMetaFileBits` at `0x1800752d3`

## pseudocode

```c
__int64 __fastcall InternalCreateLocalMetaFile(__int64 a1, int a2)
{
  UINT ServerMetaFileBits; // eax
  UINT v5; // r14d
  unsigned int *v6; // rax
  unsigned int *v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int *v11; // rcx
  __int64 v12; // rax
  unsigned int *v13; // rcx
  HENHMETAFILE v14; // r12
  HDC hdcRef; // r13
  UINT WinMetaFileBits; // eax
  UINT v17; // r15d
  BYTE *v18; // rax
  BYTE *v19; // r14
  __int64 v20; // rax
  LONG v22; // [rsp+40h] [rbp-20h] BYREF
  LONG v23; // [rsp+44h] [rbp-1Ch] BYREF
  METAFILEPICT MFP; // [rsp+48h] [rbp-18h] BYREF
  int v25; // [rsp+B0h] [rbp+50h] BYREF
  LONG v26; // [rsp+B8h] [rbp+58h] BYREF

  v25 = 0;
  v26 = 0;
  v22 = 0;
  v23 = 0;
  if ( !gbDisableMetaFiles )
  {
    if ( a1 )
    {
      ServerMetaFileBits = NtGdiGetServerMetaFileBits(a1, 0, 0, 0, 0, 0, 0);
      v5 = ServerMetaFileBits;
      if ( ServerMetaFileBits )
      {
        v6 = (unsigned int *)LocalAlloc(0, ServerMetaFileBits);
        v7 = v6;
        if ( v6 )
        {
          v8 = 0;
          if ( (unsigned int)NtGdiGetServerMetaFileBits(a1, v5, v6, &v25, &v26, &v22, &v23) != v5 )
            goto LABEL_31;
          v9 = 0;
          if ( a2 == 1599096397 )
          {
            v9 = (__int64)GlobalAlloc(0, 0x18u);
            if ( !v9 )
              goto LABEL_31;
          }
          if ( v25 == 1480934989 )
          {
            if ( a2 == 1599096397 )
            {
              *(_DWORD *)v9 = 8;
              *(_DWORD *)(v9 + 4) = v7[8] - v7[6];
              *(_DWORD *)(v9 + 8) = v7[9] - v7[7];
              v12 = SetEnhMetaFileBitsAlt(v7);
              v13 = 0;
              v14 = (HENHMETAFILE)v12;
              if ( !v12 )
                v13 = v7;
              v7 = v13;
              hdcRef = CreateICA("DISPLAY", 0, 0, 0);
              WinMetaFileBits = GetWinMetaFileBits(v14, 0, 0, 8, hdcRef);
              v17 = WinMetaFileBits;
              if ( WinMetaFileBits )
              {
                v18 = (BYTE *)LocalAlloc(0, WinMetaFileBits);
                v19 = v18;
                if ( v18 )
                {
                  if ( GetWinMetaFileBits(v14, v17, v18, 8, hdcRef) == v17
                    && (v20 = SetMetaFileBitsAlt(v19), (*(_QWORD *)(v9 + 16) = v20) != 0) )
                  {
                    v8 = v9;
                  }
                  else
                  {
                    LocalFree(v19);
                  }
                }
              }
              DeleteEnhMetaFile(v14);
              DeleteDC(hdcRef);
LABEL_25:
              if ( v8 )
                goto LABEL_30;
              goto LABEL_28;
            }
            v8 = SetEnhMetaFileBitsAlt(v7);
            if ( v8 )
              return v8;
          }
          else if ( v25 == 1599096397 )
          {
            if ( a2 == 1599096397 )
            {
              *(_DWORD *)v9 = v26;
              *(_DWORD *)(v9 + 4) = v22;
              *(_DWORD *)(v9 + 8) = v23;
              v10 = SetMetaFileBitsAlt(v7);
              *(_QWORD *)(v9 + 16) = v10;
              v11 = 0;
              if ( !v10 )
                v11 = v7;
              v7 = v11;
              v8 = v9 & -(__int64)(v10 != 0);
            }
            else
            {
              MFP.mm = v26;
              MFP.xExt = v22;
              MFP.yExt = v23;
              *(&MFP.yExt + 1) = 0;
              MFP.hMF = 0;
              v8 = (__int64)SetWinMetaFileBits(v5, (const BYTE *)v7, 0, &MFP);
            }
            goto LABEL_25;
          }
LABEL_28:
          if ( v9 )
            GlobalFree((HGLOBAL)v9);
LABEL_30:
          if ( v7 )
LABEL_31:
            LocalFree(v7);
          return v8;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180075218  mov     rax, rsp
0x18007521b  mov     [rax+8], rbx
0x18007521f  push    rbp
0x180075220  push    rsi
0x180075221  push    rdi
0x180075222  push    r12
0x180075224  push    r13
0x180075226  push    r14
0x180075228  push    r15
0x18007522a  mov     rbp, rsp
0x18007522d  sub     rsp, 60h
0x180075231  xor     r13d, r13d
0x180075234  mov     r15d, edx
0x180075237  cmp     cs:gbDisableMetaFiles, r13d
0x18007523e  mov     rbx, rcx
0x180075241  mov     [rbp+arg_10], r13d
0x180075245  mov     [rbp+arg_18], r13d
0x180075249  mov     [rbp+var_20], r13d
0x18007524d  mov     [rbp+var_1C], r13d
0x180075251  jnz     loc_1800754BE
0x180075257  test    rcx, rcx
0x18007525a  jz      loc_1800754BE
0x180075260  mov     [rax-68h], r13
0x180075264  xor     r9d, r9d
0x180075267  mov     [rax-70h], r13
0x18007526b  xor     r8d, r8d
0x18007526e  xor     edx, edx
0x180075270  mov     [rax-78h], r13
0x180075274  call    cs:__imp_NtGdiGetServerMetaFileBits
0x18007527b  nop     dword ptr [rax+rax+00h]
0x180075280  mov     r14d, eax
0x180075283  test    eax, eax
0x180075285  jz      loc_1800754BE
0x18007528b  mov     edx, r14d; uBytes
0x18007528e  xor     ecx, ecx; uFlags
0x180075290  call    cs:__imp_LocalAlloc
0x180075297  nop     dword ptr [rax+rax+00h]
0x18007529c  mov     rdi, rax
0x18007529f  test    rax, rax
0x1800752a2  jz      loc_1800754BE
0x1800752a8  lea     rax, [rbp+var_1C]
0x1800752ac  mov     r8, rdi
0x1800752af  mov     [rsp+60h+var_30], rax
0x1800752b4  lea     r9, [rbp+arg_10]
0x1800752b8  lea     rax, [rbp+var_20]
0x1800752bc  mov     edx, r14d
0x1800752bf  mov     [rsp+60h+var_38], rax
0x1800752c4  mov     rcx, rbx
0x1800752c7  lea     rax, [rbp+arg_18]
0x1800752cb  mov     esi, r13d
0x1800752ce  mov     [rsp+60h+hdcRef], rax
0x1800752d3  call    cs:__imp_NtGdiGetServerMetaFileBits
0x1800752da  nop     dword ptr [rax+rax+00h]
0x1800752df  cmp     eax, r14d
0x1800752e2  jnz     loc_1800754AA
0x1800752e8  mov     r12d, 5F50464Dh
0x1800752ee  mov     ebx, r13d
0x1800752f1  cmp     r15d, r12d
0x1800752f4  jnz     short loc_180075314
0x1800752f6  lea     edx, [r13+18h]; dwBytes
0x1800752fa  xor     ecx, ecx; uFlags
0x1800752fc  call    cs:__imp_GlobalAlloc
0x180075303  nop     dword ptr [rax+rax+00h]
0x180075308  mov     rbx, rax
0x18007530b  test    rax, rax
0x18007530e  jz      loc_1800754AA
0x180075314  cmp     [rbp+arg_10], 5845464Dh
0x18007531b  jz      short loc_180075395
0x18007531d  cmp     [rbp+arg_10], r12d
0x180075321  jnz     loc_180075491
0x180075327  mov     eax, [rbp+arg_18]
0x18007532a  cmp     r15d, r12d
0x18007532d  jnz     short loc_180075364
0x18007532f  mov     [rbx], eax
0x180075331  mov     rcx, rdi
0x180075334  mov     eax, [rbp+var_20]
0x180075337  mov     [rbx+4], eax
0x18007533a  mov     eax, [rbp+var_1C]
0x18007533d  mov     [rbx+8], eax
0x180075340  call    SetMetaFileBitsAlt
0x180075345  test    rax, rax
0x180075348  mov     [rbx+10h], rax
0x18007534c  mov     rcx, r13
0x18007534f  cmovz   rcx, rdi
0x180075353  neg     rax
0x180075356  mov     rdi, rcx
0x180075359  sbb     rsi, rsi
0x18007535c  and     rsi, rbx
0x18007535f  jmp     loc_18007547D
0x180075364  mov     [rbp+MFP.mm], eax
0x180075367  lea     r9, [rbp+MFP]; lpMFP
0x18007536b  mov     eax, [rbp+var_20]
0x18007536e  xor     r8d, r8d; hdcRef
0x180075371  mov     [rbp+MFP.xExt], eax
0x180075374  mov     rdx, rdi; lpMeta16Data
0x180075377  mov     eax, [rbp+var_1C]
0x18007537a  mov     ecx, r14d; nSize
0x18007537d  mov     [rbp+MFP.yExt], eax
0x180075380  mov     dword ptr [rbp+MFP+0Ch], r13d
0x180075384  mov     [rbp+MFP.hMF], r13
0x180075388  call    SetWinMetaFileBits
0x18007538d  mov     rsi, rax
0x180075390  jmp     loc_18007547D
0x180075395  xor     r9d, r9d
0x180075398  xor     r8d, r8d
0x18007539b  xor     edx, edx
0x18007539d  mov     rcx, rdi; unsigned int *
0x1800753a0  cmp     r15d, r12d
0x1800753a3  jnz     loc_180075484
0x1800753a9  lea     r14d, [r9+8]
0x1800753ad  mov     [rbx], r14d
0x1800753b0  mov     eax, [rdi+20h]
0x1800753b3  sub     eax, [rdi+18h]
0x1800753b6  mov     [rbx+4], eax
0x1800753b9  mov     eax, [rdi+24h]
0x1800753bc  sub     eax, [rdi+1Ch]
0x1800753bf  mov     [rbx+8], eax
0x1800753c2  call    SetEnhMetaFileBitsAlt
0x1800753c7  test    rax, rax
0x1800753ca  mov     rcx, r13
0x1800753cd  mov     r12, rax
0x1800753d0  cmovz   rcx, rdi
0x1800753d4  xor     r9d, r9d; pdm
0x1800753d7  mov     rdi, rcx
0x1800753da  xor     r8d, r8d; pszPort
0x1800753dd  lea     rcx, String1; "DISPLAY"
0x1800753e4  xor     edx, edx; pszDevice
0x1800753e6  call    CreateICA
0x1800753eb  mov     r9d, r14d; iMapMode
0x1800753ee  mov     [rsp+60h+hdcRef], rax; hdcRef
0x1800753f3  xor     r8d, r8d; pData16
0x1800753f6  xor     edx, edx; cbData16
0x1800753f8  mov     rcx, r12; hemf
0x1800753fb  mov     r13, rax
0x1800753fe  call    GetWinMetaFileBits
0x180075403  mov     r15d, eax
0x180075406  test    eax, eax
0x180075408  jz      short loc_180075466
0x18007540a  mov     edx, r15d; uBytes
0x18007540d  xor     ecx, ecx; uFlags
0x18007540f  call    cs:__imp_LocalAlloc
0x180075416  nop     dword ptr [rax+rax+00h]
0x18007541b  mov     r14, rax
0x18007541e  test    rax, rax
0x180075421  jz      short loc_180075466
0x180075423  mov     r9d, 8; iMapMode
0x180075429  mov     [rsp+60h+hdcRef], r13; hdcRef
0x18007542e  mov     r8, rax; pData16
0x180075431  mov     edx, r15d; cbData16
0x180075434  mov     rcx, r12; hemf
0x180075437  call    GetWinMetaFileBits
0x18007543c  cmp     eax, r15d
0x18007543f  jnz     short loc_180075457
0x180075441  mov     rcx, r14
0x180075444  call    SetMetaFileBitsAlt
0x180075449  mov     [rbx+10h], rax
0x18007544d  test    rax, rax
0x180075450  jz      short loc_180075457
0x180075452  mov     rsi, rbx
0x180075455  jmp     short loc_180075466
0x180075457  mov     rcx, r14; hMem
0x18007545a  call    cs:__imp_LocalFree
0x180075461  nop     dword ptr [rax+rax+00h]
0x180075466  mov     rcx, r12; hmf
0x180075469  call    DeleteEnhMetaFile
0x18007546e  mov     rcx, r13; hdc
0x180075471  call    cs:__imp_DeleteDC
0x180075478  nop     dword ptr [rax+rax+00h]
0x18007547d  test    rsi, rsi
0x180075480  jz      short loc_180075491
0x180075482  jmp     short loc_1800754A5
0x180075484  call    SetEnhMetaFileBitsAlt
0x180075489  mov     rsi, rax
0x18007548c  test    rax, rax
0x18007548f  jnz     short loc_1800754B9
0x180075491  test    rbx, rbx
0x180075494  jz      short loc_1800754A5
0x180075496  mov     rcx, rbx; hMem
0x180075499  call    cs:__imp_GlobalFree
0x1800754a0  nop     dword ptr [rax+rax+00h]
0x1800754a5  test    rdi, rdi
0x1800754a8  jz      short loc_1800754B9
0x1800754aa  mov     rcx, rdi; hMem
0x1800754ad  call    cs:__imp_LocalFree
0x1800754b4  nop     dword ptr [rax+rax+00h]
0x1800754b9  mov     rax, rsi
0x1800754bc  jmp     short loc_1800754C0
0x1800754be  xor     eax, eax
0x1800754c0  mov     rbx, [rsp+60h+arg_0]
0x1800754c8  add     rsp, 60h
0x1800754cc  pop     r15
0x1800754ce  pop     r14
0x1800754d0  pop     r13
0x1800754d2  pop     r12
0x1800754d4  pop     rdi
0x1800754d5  pop     rsi
0x1800754d6  pop     rbp
0x1800754d7  retn
```
