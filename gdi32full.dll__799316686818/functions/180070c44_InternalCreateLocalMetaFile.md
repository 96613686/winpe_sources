# InternalCreateLocalMetaFile

- ea: `0x180070c44`
- end: `0x180070ece`
- name: `InternalCreateLocalMetaFile`
- size: `650`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180078c90`
- `0x18008e080`

## callees

- `0x1800281d0`
- `0x180028f18`
- `0x180029c30`
- `0x18002b5a0`
- `0x18002bbc8`
- `0x180070c44`
- `0x18008b130`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180070d16`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180070d16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070cb6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070e23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070cb6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070e23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070e68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070ea9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070e68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070ea9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180070e9b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180070e9b`
- `GDI32!DeleteDC` at `0x180070e79`
- `GDI32!DeleteDC` at `0x180070e79`
- `win32u!NtGdiGetServerMetaFileBits` at `0x180070ca0`
- `win32u!NtGdiGetServerMetaFileBits` at `0x180070cf3`
- `win32u!NtGdiGetServerMetaFileBits` at `0x180070ca0`
- `win32u!NtGdiGetServerMetaFileBits` at `0x180070cf3`

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
0x180070c44  mov     rax, rsp
0x180070c47  mov     [rax+8], rbx
0x180070c4b  push    rbp
0x180070c4c  push    rsi
0x180070c4d  push    rdi
0x180070c4e  push    r12
0x180070c50  push    r13
0x180070c52  push    r14
0x180070c54  push    r15
0x180070c56  mov     rbp, rsp
0x180070c59  sub     rsp, 60h
0x180070c5d  xor     r13d, r13d
0x180070c60  mov     r15d, edx
0x180070c63  cmp     cs:gbDisableMetaFiles, r13d
0x180070c6a  mov     rbx, rcx
0x180070c6d  mov     [rbp+arg_10], r13d
0x180070c71  mov     [rbp+arg_18], r13d
0x180070c75  mov     [rbp+var_20], r13d
0x180070c79  mov     [rbp+var_1C], r13d
0x180070c7d  jnz     loc_180070EB4
0x180070c83  test    rcx, rcx
0x180070c86  jz      loc_180070EB4
0x180070c8c  mov     [rax-68h], r13
0x180070c90  xor     r9d, r9d
0x180070c93  mov     [rax-70h], r13
0x180070c97  xor     r8d, r8d
0x180070c9a  xor     edx, edx
0x180070c9c  mov     [rax-78h], r13
0x180070ca0  call    cs:__imp_NtGdiGetServerMetaFileBits
0x180070ca6  mov     r14d, eax
0x180070ca9  test    eax, eax
0x180070cab  jz      loc_180070EB4
0x180070cb1  mov     edx, r14d; uBytes
0x180070cb4  xor     ecx, ecx; uFlags
0x180070cb6  call    cs:__imp_LocalAlloc
0x180070cbc  mov     rdi, rax
0x180070cbf  test    rax, rax
0x180070cc2  jz      loc_180070EB4
0x180070cc8  lea     rax, [rbp+var_1C]
0x180070ccc  mov     r8, rdi
0x180070ccf  mov     [rsp+60h+var_30], rax
0x180070cd4  lea     r9, [rbp+arg_10]
0x180070cd8  lea     rax, [rbp+var_20]
0x180070cdc  mov     edx, r14d
0x180070cdf  mov     [rsp+60h+var_38], rax
0x180070ce4  mov     rcx, rbx
0x180070ce7  lea     rax, [rbp+arg_18]
0x180070ceb  mov     esi, r13d
0x180070cee  mov     [rsp+60h+hdcRef], rax
0x180070cf3  call    cs:__imp_NtGdiGetServerMetaFileBits
0x180070cf9  cmp     eax, r14d
0x180070cfc  jnz     loc_180070EA6
0x180070d02  mov     r12d, 5F50464Dh
0x180070d08  mov     ebx, r13d
0x180070d0b  cmp     r15d, r12d
0x180070d0e  jnz     short loc_180070D28
0x180070d10  lea     edx, [r13+18h]; dwBytes
0x180070d14  xor     ecx, ecx; uFlags
0x180070d16  call    cs:__imp_GlobalAlloc
0x180070d1c  mov     rbx, rax
0x180070d1f  test    rax, rax
0x180070d22  jz      loc_180070EA6
0x180070d28  cmp     [rbp+arg_10], 5845464Dh
0x180070d2f  jz      short loc_180070DA9
0x180070d31  cmp     [rbp+arg_10], r12d
0x180070d35  jnz     loc_180070E93
0x180070d3b  mov     eax, [rbp+arg_18]
0x180070d3e  cmp     r15d, r12d
0x180070d41  jnz     short loc_180070D78
0x180070d43  mov     [rbx], eax
0x180070d45  mov     rcx, rdi
0x180070d48  mov     eax, [rbp+var_20]
0x180070d4b  mov     [rbx+4], eax
0x180070d4e  mov     eax, [rbp+var_1C]
0x180070d51  mov     [rbx+8], eax
0x180070d54  call    SetMetaFileBitsAlt
0x180070d59  test    rax, rax
0x180070d5c  mov     [rbx+10h], rax
0x180070d60  mov     rcx, r13
0x180070d63  cmovz   rcx, rdi
0x180070d67  neg     rax
0x180070d6a  mov     rdi, rcx
0x180070d6d  sbb     rsi, rsi
0x180070d70  and     rsi, rbx
0x180070d73  jmp     loc_180070E7F
0x180070d78  mov     [rbp+MFP.mm], eax
0x180070d7b  lea     r9, [rbp+MFP]; lpMFP
0x180070d7f  mov     eax, [rbp+var_20]
0x180070d82  xor     r8d, r8d; hdcRef
0x180070d85  mov     [rbp+MFP.xExt], eax
0x180070d88  mov     rdx, rdi; lpMeta16Data
0x180070d8b  mov     eax, [rbp+var_1C]
0x180070d8e  mov     ecx, r14d; nSize
0x180070d91  mov     [rbp+MFP.yExt], eax
0x180070d94  mov     dword ptr [rbp+MFP+0Ch], r13d
0x180070d98  mov     [rbp+MFP.hMF], r13
0x180070d9c  call    SetWinMetaFileBits
0x180070da1  mov     rsi, rax
0x180070da4  jmp     loc_180070E7F
0x180070da9  xor     r9d, r9d
0x180070dac  xor     r8d, r8d
0x180070daf  xor     edx, edx
0x180070db1  mov     rcx, rdi; unsigned int *
0x180070db4  cmp     r15d, r12d
0x180070db7  jnz     loc_180070E86
0x180070dbd  lea     r14d, [r9+8]
0x180070dc1  mov     [rbx], r14d
0x180070dc4  mov     eax, [rdi+20h]
0x180070dc7  sub     eax, [rdi+18h]
0x180070dca  mov     [rbx+4], eax
0x180070dcd  mov     eax, [rdi+24h]
0x180070dd0  sub     eax, [rdi+1Ch]
0x180070dd3  mov     [rbx+8], eax
0x180070dd6  call    SetEnhMetaFileBitsAlt
0x180070ddb  test    rax, rax
0x180070dde  mov     rcx, r13
0x180070de1  mov     r12, rax
0x180070de4  cmovz   rcx, rdi
0x180070de8  xor     r9d, r9d; pdm
0x180070deb  mov     rdi, rcx
0x180070dee  xor     r8d, r8d; pszPort
0x180070df1  lea     rcx, String1; "DISPLAY"
0x180070df8  xor     edx, edx; pszDevice
0x180070dfa  call    CreateICA
0x180070dff  mov     r9d, r14d; iMapMode
0x180070e02  mov     [rsp+60h+hdcRef], rax; hdcRef
0x180070e07  xor     r8d, r8d; pData16
0x180070e0a  xor     edx, edx; cbData16
0x180070e0c  mov     rcx, r12; hemf
0x180070e0f  mov     r13, rax
0x180070e12  call    GetWinMetaFileBits
0x180070e17  mov     r15d, eax
0x180070e1a  test    eax, eax
0x180070e1c  jz      short loc_180070E6E
0x180070e1e  mov     edx, r15d; uBytes
0x180070e21  xor     ecx, ecx; uFlags
0x180070e23  call    cs:__imp_LocalAlloc
0x180070e29  mov     r14, rax
0x180070e2c  test    rax, rax
0x180070e2f  jz      short loc_180070E6E
0x180070e31  mov     r9d, 8; iMapMode
0x180070e37  mov     [rsp+60h+hdcRef], r13; hdcRef
0x180070e3c  mov     r8, rax; pData16
0x180070e3f  mov     edx, r15d; cbData16
0x180070e42  mov     rcx, r12; hemf
0x180070e45  call    GetWinMetaFileBits
0x180070e4a  cmp     eax, r15d
0x180070e4d  jnz     short loc_180070E65
0x180070e4f  mov     rcx, r14
0x180070e52  call    SetMetaFileBitsAlt
0x180070e57  mov     [rbx+10h], rax
0x180070e5b  test    rax, rax
0x180070e5e  jz      short loc_180070E65
0x180070e60  mov     rsi, rbx
0x180070e63  jmp     short loc_180070E6E
0x180070e65  mov     rcx, r14; hMem
0x180070e68  call    cs:__imp_LocalFree
0x180070e6e  mov     rcx, r12; hmf
0x180070e71  call    DeleteEnhMetaFile
0x180070e76  mov     rcx, r13; hdc
0x180070e79  call    cs:__imp_DeleteDC
0x180070e7f  test    rsi, rsi
0x180070e82  jz      short loc_180070E93
0x180070e84  jmp     short loc_180070EA1
0x180070e86  call    SetEnhMetaFileBitsAlt
0x180070e8b  mov     rsi, rax
0x180070e8e  test    rax, rax
0x180070e91  jnz     short loc_180070EAF
0x180070e93  test    rbx, rbx
0x180070e96  jz      short loc_180070EA1
0x180070e98  mov     rcx, rbx; hMem
0x180070e9b  call    cs:__imp_GlobalFree
0x180070ea1  test    rdi, rdi
0x180070ea4  jz      short loc_180070EAF
0x180070ea6  mov     rcx, rdi; hMem
0x180070ea9  call    cs:__imp_LocalFree
0x180070eaf  mov     rax, rsi
0x180070eb2  jmp     short loc_180070EB6
0x180070eb4  xor     eax, eax
0x180070eb6  mov     rbx, [rsp+60h+arg_0]
0x180070ebe  add     rsp, 60h
0x180070ec2  pop     r15
0x180070ec4  pop     r14
0x180070ec6  pop     r13
0x180070ec8  pop     r12
0x180070eca  pop     rdi
0x180070ecb  pop     rsi
0x180070ecc  pop     rbp
0x180070ecd  retn
```
