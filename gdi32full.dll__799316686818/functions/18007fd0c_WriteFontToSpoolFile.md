# WriteFontToSpoolFile

- ea: `0x18007fd0c`
- end: `0x180080080`
- name: `WriteFontToSpoolFile`
- size: `884`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057840`
- `0x18008025c`

## callees

- `0x180039ae4`
- `0x18006b00c`
- `0x18007ac50`
- `0x18007ba24`
- `0x18007fd0c`
- `0x18008decc`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007fdf4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007ff81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007fdf4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007ff81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007fea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007fea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080034`
- `win32u!NtGdiGetUFIPathname` at `0x18007fdad`
- `win32u!NtGdiGetUFIPathname` at `0x18007fe30`
- `win32u!NtGdiGetUFIPathname` at `0x18007fdad`
- `win32u!NtGdiGetUFIPathname` at `0x18007fe30`

## pseudocode

```c
_BOOL8 __fastcall WriteFontToSpoolFile(__int64 a1, __int64 a2, int a3)
{
  int v3; // r13d
  BOOL v7; // esi
  unsigned int v8; // eax
  void *v9; // rbx
  BOOL v10; // edi
  int v11; // eax
  WCHAR *v13; // rbx
  int v14; // ecx
  __int64 v15; // rdi
  unsigned int v17; // eax
  __int64 v18; // r14
  _DWORD *v19; // rax
  _DWORD *v20; // r15
  char *v21; // rsi
  char *v22; // r12
  __int64 v23; // rbx
  __int64 v24; // rcx
  SIZE_T *p_uBytes; // [rsp+30h] [rbp-D0h]
  HLOCAL v26; // [rsp+38h] [rbp-C8h]
  SIZE_T uBytes; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  void *FileHandle[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h]
  _OWORD v34[2]; // [rsp+90h] [rbp-70h] BYREF
  void *Src[10]; // [rsp+B0h] [rbp-50h]
  WCHAR SourceString[784]; // [rsp+100h] [rbp+0h] BYREF

  v3 = 0;
  v31 = a1;
  p_uBytes = &uBytes;
  v29 = 0;
  uBytes = 0;
  v28 = 0;
  v7 = 0;
  *(_OWORD *)FileHandle = 0;
  v33 = 0;
  v34[0] = 0;
  if ( !(unsigned int)NtGdiGetUFIPathname(a2, &v29, SourceString, (char *)&uBytes + 4, a3, &v28) )
    return v7;
  v8 = HIDWORD(uBytes);
  if ( HIDWORD(uBytes) == 1 )
  {
    if ( v28 )
    {
      v26 = LocalAlloc(0, (unsigned int)uBytes);
      v10 = v26 != 0;
      LODWORD(p_uBytes) = 0;
      v9 = v26;
      if ( !(unsigned int)NtGdiGetUFIPathname(a2, 0, 0, 0, a3, 0) )
        goto LABEL_12;
    }
    else
    {
      v9 = 0;
      v10 = bMapFileUNICODEClideSide(SourceString, FileHandle, SHIDWORD(uBytes)) != 0;
    }
    if ( !v10 )
      return v7;
    DWORD1(v34[0]) = HIDWORD(uBytes);
    LODWORD(v34[0]) = 0;
    if ( v28 )
    {
      v11 = uBytes;
    }
    else
    {
      v11 = DWORD2(v33);
      v9 = (void *)v33;
      LODWORD(uBytes) = DWORD2(v33);
    }
    DWORD2(v34[0]) = v11;
    LOBYTE(v7) = (unsigned int)WriteFontDataAsEMFComment(a1, 2, v34, 16, v9, v11, (_DWORD)p_uBytes) != 0;
    if ( !v28 )
    {
      vUnmapFileClideSide(FileHandle);
      return v7;
    }
    if ( !v9 )
      return v7;
LABEL_12:
    LocalFree(v9);
    return v7;
  }
  if ( HIDWORD(uBytes) > 3 )
    return 0;
  v13 = SourceString;
  LODWORD(uBytes) = 0;
  v14 = 1;
  LODWORD(v15) = 0;
  while ( (unsigned int)v15 < v8 )
  {
    if ( !v14 )
      goto LABEL_36;
    if ( !(unsigned int)bMapFileUNICODEClideSide(v13, (PHANDLE)&v34[2 * (unsigned int)v15 + 1], 1) )
    {
      v8 = HIDWORD(uBytes);
      v14 = 0;
      break;
    }
    while ( *v13++ )
      ;
    v17 = (unsigned int)Src[4 * (unsigned int)v15 + 1];
    if ( v17 < 0xFFFFFFFC )
    {
      if ( (unsigned int)uBytes + ((v17 + 3) & 0xFFFFFFFC) >= (unsigned int)uBytes )
      {
        LODWORD(uBytes) = uBytes + ((v17 + 3) & 0xFFFFFFFC);
        v14 = 1;
        goto LABEL_26;
      }
      LODWORD(uBytes) = -1;
    }
    v14 = 0;
LABEL_26:
    v8 = HIDWORD(uBytes);
    LODWORD(v15) = v15 + 1;
  }
  if ( v14 )
  {
    v18 = (4 * v8 + 15) & 0xFFFFFFF8;
    v30 = (4 * v8 + 15) & 0xFFFFFFF8;
    if ( (int)v18 + (int)uBytes >= (unsigned int)v18 )
    {
      v19 = LocalAlloc(0, (unsigned int)(v18 + uBytes));
      v20 = v19;
      if ( v19 )
      {
        v21 = (char *)v19 + v18;
        v22 = (char *)v19 + v18;
        memset_0(v19, 0, (unsigned int)v18);
        v15 = 0;
        if ( HIDWORD(uBytes) )
        {
          do
          {
            v23 = 4LL * (unsigned int)v15;
            v3 += (LODWORD(Src[v23 + 1]) + 3) & 0xFFFFFFFC;
            v20[v15 + 2] = v3;
            memcpy_0(v22, Src[v23], LODWORD(Src[v23 + 1]));
            v15 = (unsigned int)(v15 + 1);
            v22 += (LODWORD(Src[v23 + 1]) + 3) & 0xFFFFFFFC;
          }
          while ( (unsigned int)v15 < HIDWORD(uBytes) );
          LODWORD(v18) = v30;
        }
        v24 = v31;
        *v20 = 0;
        v20[1] = HIDWORD(uBytes);
        v7 = WriteFontDataAsEMFComment(v24, 4, v20, (unsigned int)v18, v21, uBytes, (unsigned int)&uBytes) != 0;
        LocalFree(v20);
      }
    }
  }
LABEL_36:
  while ( (_DWORD)v15 )
  {
    LODWORD(v15) = v15 - 1;
    vUnmapFileClideSide(&v34[2 * (unsigned int)v15 + 1]);
  }
  return v7;
}

```

## disassembly

```asm
0x18007fd0c  mov     [rsp-8+arg_18], rbx
0x18007fd11  push    rbp
0x18007fd12  push    rsi
0x18007fd13  push    rdi
0x18007fd14  push    r12
0x18007fd16  push    r13
0x18007fd18  push    r14
0x18007fd1a  push    r15
0x18007fd1c  lea     rbp, [rsp-630h]
0x18007fd24  sub     rsp, 730h
0x18007fd2b  mov     rax, cs:__security_cookie
0x18007fd32  xor     rax, rsp
0x18007fd35  mov     [rbp+660h+var_40], rax
0x18007fd3c  xor     r13d, r13d
0x18007fd3f  mov     [rsp+760h+var_6F8], rcx
0x18007fd44  mov     [rsp+760h+var_718], r13
0x18007fd49  lea     rax, [rsp+760h+uBytes]
0x18007fd4e  mov     [rsp+760h+var_720], r13
0x18007fd53  lea     r9, [rsp+760h+uBytes+4]
0x18007fd58  xorps   xmm0, xmm0
0x18007fd5b  mov     [rsp+760h+var_728], r13
0x18007fd60  mov     [rsp+760h+var_730], rax
0x18007fd65  mov     r14, rdx
0x18007fd68  lea     rax, [rsp+760h+var_708]
0x18007fd6d  mov     [rsp+760h+var_704], r13d
0x18007fd72  mov     [rsp+760h+var_738], rax
0x18007fd77  lea     rdx, [rsp+760h+var_704]
0x18007fd7c  mov     dword ptr [rsp+760h+var_740], r8d
0x18007fd81  mov     r15d, r8d
0x18007fd84  mov     r12, rcx
0x18007fd87  mov     dword ptr [rsp+760h+uBytes+4], r13d
0x18007fd8c  lea     r8, [rbp+660h+SourceString]
0x18007fd90  mov     dword ptr [rsp+760h+uBytes], r13d
0x18007fd95  mov     rcx, r14
0x18007fd98  mov     [rsp+760h+var_708], r13d
0x18007fd9d  mov     esi, r13d
0x18007fda0  movups  xmmword ptr [rsp+760h+FileHandle], xmm0
0x18007fda5  movups  [rbp+660h+var_6E0], xmm0
0x18007fda9  movups  [rbp+660h+var_6D0], xmm0
0x18007fdad  call    cs:__imp_NtGdiGetUFIPathname
0x18007fdb3  test    eax, eax
0x18007fdb5  jz      loc_180080054
0x18007fdbb  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x18007fdbf  cmp     eax, 1
0x18007fdc2  jnz     loc_18007FEBA
0x18007fdc8  cmp     [rsp+760h+var_708], r13d
0x18007fdcd  jnz     short loc_18007FDEE
0x18007fdcf  mov     r8d, eax
0x18007fdd2  lea     rdx, [rsp+760h+FileHandle]; FileHandle
0x18007fdd7  lea     rcx, [rbp+660h+SourceString]; SourceString
0x18007fddb  mov     ebx, r13d
0x18007fdde  call    bMapFileUNICODEClideSide
0x18007fde3  test    eax, eax
0x18007fde5  mov     edi, r13d
0x18007fde8  setnz   dil
0x18007fdec  jmp     short loc_18007FE3A
0x18007fdee  mov     edx, dword ptr [rsp+760h+uBytes]; uBytes
0x18007fdf2  xor     ecx, ecx; uFlags
0x18007fdf4  call    cs:__imp_LocalAlloc
0x18007fdfa  mov     [rsp+760h+var_718], r13
0x18007fdff  mov     edi, r13d
0x18007fe02  mov     [rsp+760h+var_720], r13
0x18007fe07  test    rax, rax
0x18007fe0a  mov     [rsp+760h+var_728], rax
0x18007fe0f  mov     rcx, r14
0x18007fe12  setnz   dil
0x18007fe16  mov     [rsp+760h+var_730], r13
0x18007fe1b  xor     r9d, r9d
0x18007fe1e  mov     [rsp+760h+var_738], r13
0x18007fe23  xor     r8d, r8d
0x18007fe26  mov     dword ptr [rsp+760h+var_740], r15d
0x18007fe2b  xor     edx, edx
0x18007fe2d  mov     rbx, rax
0x18007fe30  call    cs:__imp_NtGdiGetUFIPathname
0x18007fe36  test    eax, eax
0x18007fe38  jz      short loc_18007FE9D
0x18007fe3a  test    edi, edi
0x18007fe3c  jz      loc_180080054
0x18007fe42  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x18007fe46  mov     dword ptr [rbp+660h+var_6D0+4], eax
0x18007fe49  mov     dword ptr [rbp+660h+var_6D0], r13d
0x18007fe4d  cmp     [rsp+760h+var_708], r13d
0x18007fe52  jnz     short loc_18007FE61
0x18007fe54  mov     eax, dword ptr [rbp+660h+var_6E0+8]
0x18007fe57  mov     rbx, qword ptr [rbp+660h+var_6E0]
0x18007fe5b  mov     dword ptr [rsp+760h+uBytes], eax
0x18007fe5f  jmp     short loc_18007FE65
0x18007fe61  mov     eax, dword ptr [rsp+760h+uBytes]
0x18007fe65  mov     r9d, 10h
0x18007fe6b  mov     dword ptr [rsp+760h+var_738], eax
0x18007fe6f  lea     r8, [rbp+660h+var_6D0]
0x18007fe73  mov     dword ptr [rbp+660h+var_6D0+8], eax
0x18007fe76  mov     rcx, r12
0x18007fe79  mov     [rsp+760h+var_740], rbx
0x18007fe7e  lea     edx, [r9-0Eh]
0x18007fe82  call    WriteFontDataAsEMFComment
0x18007fe87  test    eax, eax
0x18007fe89  setnz   sil
0x18007fe8d  cmp     [rsp+760h+var_708], r13d
0x18007fe92  jz      short loc_18007FEAB
0x18007fe94  test    rbx, rbx
0x18007fe97  jz      loc_180080054
0x18007fe9d  mov     rcx, rbx; hMem
0x18007fea0  call    cs:__imp_LocalFree
0x18007fea6  jmp     loc_180080054
0x18007feab  lea     rcx, [rsp+760h+FileHandle]
0x18007feb0  call    vUnmapFileClideSide
0x18007feb5  jmp     loc_180080054
0x18007feba  cmp     eax, 3
0x18007febd  jbe     short loc_18007FEC6
0x18007febf  xor     eax, eax
0x18007fec1  jmp     loc_180080056
0x18007fec6  lea     rbx, [rbp+660h+SourceString]
0x18007feca  mov     dword ptr [rsp+760h+uBytes], r13d
0x18007fecf  mov     ecx, 1
0x18007fed4  mov     edi, r13d
0x18007fed7  mov     r15d, 0FFFFFFFCh
0x18007fedd  cmp     edi, eax
0x18007fedf  jnb     short loc_18007FF54
0x18007fee1  test    ecx, ecx
0x18007fee3  jz      loc_180080050
0x18007fee9  mov     r14d, edi
0x18007feec  lea     rdx, [rbp+660h+var_6C0]
0x18007fef0  shl     r14, 5
0x18007fef4  mov     r8d, 1
0x18007fefa  add     rdx, r14; FileHandle
0x18007fefd  mov     rcx, rbx; SourceString
0x18007ff00  call    bMapFileUNICODEClideSide
0x18007ff05  test    eax, eax
0x18007ff07  jz      short loc_18007FF4D
0x18007ff09  movzx   eax, word ptr [rbx]
0x18007ff0c  add     rbx, 2
0x18007ff10  test    ax, ax
0x18007ff13  jnz     short loc_18007FF09
0x18007ff15  mov     eax, dword ptr [rbp+r14+660h+Size]
0x18007ff1a  cmp     eax, r15d
0x18007ff1d  jnb     short loc_18007FF42
0x18007ff1f  lea     edx, [rax+3]
0x18007ff22  and     edx, r15d
0x18007ff25  add     edx, dword ptr [rsp+760h+uBytes]
0x18007ff29  cmp     edx, dword ptr [rsp+760h+uBytes]
0x18007ff2d  jb      short loc_18007FF3A
0x18007ff2f  mov     dword ptr [rsp+760h+uBytes], edx
0x18007ff33  mov     ecx, 1
0x18007ff38  jmp     short loc_18007FF45
0x18007ff3a  mov     dword ptr [rsp+760h+uBytes], 0FFFFFFFFh
0x18007ff42  mov     ecx, r13d
0x18007ff45  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x18007ff49  inc     edi
0x18007ff4b  jmp     short loc_18007FEDD
0x18007ff4d  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x18007ff51  mov     ecx, r13d
0x18007ff54  test    ecx, ecx
0x18007ff56  jz      loc_180080050
0x18007ff5c  mov     ecx, dword ptr [rsp+760h+uBytes]
0x18007ff60  lea     r14d, ds:0Fh[rax*4]
0x18007ff68  and     r14d, 0FFFFFFF8h
0x18007ff6c  add     ecx, r14d
0x18007ff6f  mov     [rsp+760h+var_700], r14d
0x18007ff74  cmp     ecx, r14d
0x18007ff77  jb      loc_180080050
0x18007ff7d  mov     edx, ecx; uBytes
0x18007ff7f  xor     ecx, ecx; uFlags
0x18007ff81  call    cs:__imp_LocalAlloc
0x18007ff87  mov     r15, rax
0x18007ff8a  test    rax, rax
0x18007ff8d  jz      loc_180080050
0x18007ff93  lea     rsi, [r14+rax]
0x18007ff97  mov     r8d, r14d; Size
0x18007ff9a  xor     edx, edx; Val
0x18007ff9c  mov     rcx, rax; void *
0x18007ff9f  mov     r12, rsi
0x18007ffa2  call    memset_0
0x18007ffa7  xor     edi, edi
0x18007ffa9  cmp     dword ptr [rsp+760h+uBytes+4], edi
0x18007ffad  jbe     short loc_18007FFF9
0x18007ffaf  mov     r14d, 0FFFFFFFCh
0x18007ffb5  mov     ebx, edi
0x18007ffb7  mov     rcx, r12; void *
0x18007ffba  shl     rbx, 5
0x18007ffbe  mov     eax, dword ptr [rbp+rbx+660h+Size]
0x18007ffc2  add     eax, 3
0x18007ffc5  and     eax, r14d
0x18007ffc8  add     r13d, eax
0x18007ffcb  mov     [r15+rdi*4+8], r13d
0x18007ffd0  mov     r8d, dword ptr [rbp+rbx+660h+Size]; Size
0x18007ffd5  mov     rdx, [rbp+rbx+660h+Src]; Src
0x18007ffda  call    memcpy_0
0x18007ffdf  mov     eax, dword ptr [rbp+rbx+660h+Size]
0x18007ffe3  inc     edi
0x18007ffe5  add     eax, 3
0x18007ffe8  and     rax, r14
0x18007ffeb  add     r12, rax
0x18007ffee  cmp     edi, dword ptr [rsp+760h+uBytes+4]
0x18007fff2  jb      short loc_18007FFB5
0x18007fff4  mov     r14d, [rsp+760h+var_700]
0x18007fff9  mov     rcx, [rsp+760h+var_6F8]
0x18007fffe  xor     r13d, r13d
0x180080001  mov     [r15], r13d
0x180080004  mov     r9d, r14d
0x180080007  mov     eax, dword ptr [rsp+760h+uBytes+4]
0x18008000b  mov     r8, r15
0x18008000e  mov     [r15+4], eax
0x180080012  mov     eax, dword ptr [rsp+760h+uBytes]
0x180080016  lea     edx, [r13+4]
0x18008001a  mov     dword ptr [rsp+760h+var_738], eax
0x18008001e  mov     [rsp+760h+var_740], rsi
0x180080023  call    WriteFontDataAsEMFComment
0x180080028  test    eax, eax
0x18008002a  mov     esi, r13d
0x18008002d  mov     rcx, r15; hMem
0x180080030  setnz   sil
0x180080034  call    cs:__imp_LocalFree
0x18008003a  jmp     short loc_180080050
0x18008003c  dec     edi
0x18008003e  lea     rax, [rbp+660h+var_6C0]
0x180080042  mov     ecx, edi
0x180080044  shl     rcx, 5
0x180080048  add     rcx, rax
0x18008004b  call    vUnmapFileClideSide
0x180080050  test    edi, edi
0x180080052  jnz     short loc_18008003C
0x180080054  mov     eax, esi
0x180080056  mov     rcx, [rbp+660h+var_40]
0x18008005d  xor     rcx, rsp; StackCookie
0x180080060  call    __security_check_cookie
0x180080065  mov     rbx, [rsp+760h+arg_18]
0x18008006d  add     rsp, 730h
0x180080074  pop     r15
0x180080076  pop     r14
0x180080078  pop     r13
0x18008007a  pop     r12
0x18008007c  pop     rdi
0x18008007d  pop     rsi
0x18008007e  pop     rbp
0x18008007f  retn
```
