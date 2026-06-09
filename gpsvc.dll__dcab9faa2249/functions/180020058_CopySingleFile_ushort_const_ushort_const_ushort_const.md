# CopySingleFile(ushort const *,ushort const *,ushort const *)

- ea: `0x180020058`
- end: `0x1800204c3`
- name: `?CopySingleFile@@YAKPEBG00@Z`
- size: `1131`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001f24c`
- `0x18001f580`

## callees

- `0x180003770`
- `0x18000a504`
- `0x180020058`
- `0x1800204d0`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002033c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002033c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020142`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020278`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020142`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020278`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002048d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002049c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002048d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002049c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020353`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020353`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002032e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180020366`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002032e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180020366`

## string_xrefs

- `0x1800201b1`: `CopySingleFile: failed to do PathAppend %s with error: %d.`
- `0x1800201e7`: `CopySingleFile: failed to do PathAppend %s with error: %d.`
- `0x180020395`: `CopySingleFile: reached error in CopyFile from %s to %s with error: %d. Continue processing.`
- `0x1800203b0`: `CopySingleFile: reached error in CopyFile from %s to %s with error: %d. Continue processing.`
- `0x1800203d6`: `CopySingleFile: SetFileAttribute failed on retry of CopyFile from %s to %s with error: %d. Continue processing.`
- `0x180020405`: `CopySingleFile: SetFileAttribute failed on retry of CopyFile from %s to %s with error: %d. Continue processing.`
- `0x180020444`: `CopySingleFile: failed to CopyFile from %s to %s with error: %d.`
- `0x180020473`: `CopySingleFile: failed to CopyFile from %s to %s with error: %d.`

## pseudocode

```c
__int64 __fastcall CopySingleFile(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  WCHAR *v6; // rbx
  WCHAR *v7; // rdi
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rax
  size_t v10; // rdx
  unsigned __int64 v11; // rsi
  HRESULT v12; // eax
  size_t v13; // rdx
  HRESULT v14; // eax
  __int64 v15; // r10
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // r12
  int v18; // eax
  void (*v19)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v20; // r9
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r8
  HRESULT v23; // eax
  size_t v24; // rdx
  HRESULT v25; // eax
  size_t v26; // rdx
  HRESULT v27; // eax
  unsigned __int16 *v28; // r14
  int v29; // eax
  DWORD LastError; // ecx
  void (*v31)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v32; // rdx
  const unsigned __int16 *v33; // rdx
  __int64 v35; // [rsp+20h] [rbp-30h]
  size_t v36; // [rsp+30h] [rbp-20h] BYREF
  size_t v37; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v38; // [rsp+40h] [rbp-10h]
  unsigned __int16 *v39; // [rsp+48h] [rbp-8h]
  size_t v40; // [rsp+90h] [rbp+40h] BYREF
  size_t pcchLength; // [rsp+A8h] [rbp+58h] BYREF

  v6 = 0;
  v38 = 0;
  if ( !a1 || !a2 || !a3 )
    return 87;
  v37 = 0;
  v7 = 0;
  v39 = 0;
  pcchLength = 0;
  v40 = 0;
  v8 = 0x7FFFFFFF;
  v9 = a1;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = 0x7FFFFFFF - v8;
  if ( v8 )
  {
    v12 = StringLengthWorkerW(a3, v10, &pcchLength);
    if ( v12 >= 0 )
    {
      v14 = StringLengthWorkerW(L"\\", v13, &v40);
      if ( v14 >= 0 )
      {
        v16 = v15 + v40 + pcchLength + 2;
        v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16);
        if ( !v17 )
        {
          LODWORD(v11) = 14;
          goto LABEL_18;
        }
        v18 = StringCchPrintfW(v17, v16, L"%s%s%s", a1, L"\\", a3);
        if ( !v18 )
        {
          v7 = v17;
          v39 = v17;
LABEL_27:
          v40 = 0;
          v6 = 0;
          v38 = 0;
          v37 = 0;
          pcchLength = 0;
          v36 = 0;
          v23 = StringLengthWorkerW(a2, v10, &v37);
          LOWORD(v11) = v23;
          if ( v23 >= 0 )
          {
            v25 = StringLengthWorkerW(a3, v24, &pcchLength);
            LOWORD(v11) = v25;
            if ( v25 >= 0 )
            {
              v27 = StringLengthWorkerW(L"\\", v26, &v36);
              LOWORD(v11) = v27;
              if ( v27 >= 0 )
              {
                v11 = pcchLength + v36 + v37 + 2;
                v28 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v11);
                v40 = (size_t)v28;
                if ( !v28 )
                {
                  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
                  LODWORD(v11) = 14;
LABEL_35:
                  v20 = (unsigned int)v11;
                  if ( !*(_DWORD *)&g_dwDebugLevel )
                    goto LABEL_67;
                  v19 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v21 = a2;
                    goto LABEL_21;
                  }
                  if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                    goto LABEL_67;
                  v22 = a2;
LABEL_25:
                  RedirectDebugMsg(2u, L"CopySingleFile: failed to do PathAppend %s with error: %d.", v22, v20);
                  goto LABEL_67;
                }
                v29 = StringCchPrintfW(v28, v11, L"%s%s%s", a2, L"\\", a3);
                LOWORD(v11) = v29;
                if ( !v29 )
                {
                  v6 = v28;
                  v38 = v28;
                  LODWORD(v11) = 0;
                  goto LABEL_42;
                }
              }
            }
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v40);
          }
          LODWORD(v11) = (unsigned __int16)v11;
          if ( (_WORD)v11 )
            goto LABEL_35;
LABEL_42:
          if ( CopyFileW(v7, v6, 0) )
            goto LABEL_67;
          LODWORD(v11) = GetLastError();
          if ( (_DWORD)v11 != 5 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                LODWORD(v35) = v11;
                g_lpDebugMsg(2u, L"CopySingleFile: failed to CopyFile from %s to %s with error: %d.", v7, v6, v35);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                LODWORD(v35) = v11;
                RedirectDebugMsg(2u, L"CopySingleFile: failed to CopyFile from %s to %s with error: %d.", v7, v6, v35);
              }
            }
            goto LABEL_67;
          }
          if ( SetFileAttributesW(v6, 0x80u) )
          {
            if ( CopyFileW(v7, v6, 0) )
              goto LABEL_60;
            LastError = GetLastError();
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_60;
            v31 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v32 = L"CopySingleFile: reached error in CopyFile from %s to %s with error: %d. Continue processing.";
LABEL_55:
              v31(2u, v32, v7, v6, LastError);
              goto LABEL_60;
            }
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              goto LABEL_60;
            v33 = L"CopySingleFile: reached error in CopyFile from %s to %s with error: %d. Continue processing.";
          }
          else
          {
            LastError = GetLastError();
            if ( !*(_DWORD *)&g_dwDebugLevel )
            {
LABEL_60:
              LODWORD(v11) = 0;
              goto LABEL_67;
            }
            v31 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v32 = L"CopySingleFile: SetFileAttribute failed on retry of CopyFile from %s to %s with error: %d. Continue processing.";
              goto LABEL_55;
            }
            if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
              goto LABEL_60;
            v33 = L"CopySingleFile: SetFileAttribute failed on retry of CopyFile from %s to %s with error: %d. Continue processing.";
          }
          LODWORD(v35) = LastError;
          RedirectDebugMsg(2u, v33, v7, v6, v35);
          goto LABEL_60;
        }
        LODWORD(v11) = (unsigned __int16)v18;
        LocalFree(v17);
      }
      else
      {
        LODWORD(v11) = (unsigned __int16)v14;
      }
    }
    else
    {
      LODWORD(v11) = (unsigned __int16)v12;
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v37);
    }
  }
  else
  {
    LODWORD(v11) = 87;
  }
  if ( !(_DWORD)v11 )
    goto LABEL_27;
LABEL_18:
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v19 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v20 = (unsigned int)v11;
      v21 = a1;
LABEL_21:
      v19(2u, L"CopySingleFile: failed to do PathAppend %s with error: %d.", v21, v20);
      goto LABEL_67;
    }
    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      goto LABEL_67;
    v20 = (unsigned int)v11;
    v22 = a1;
    goto LABEL_25;
  }
LABEL_67:
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180020058  mov     [rsp-38h+arg_8], rbx
0x18002005d  push    rbp
0x18002005e  push    rsi
0x18002005f  push    rdi
0x180020060  push    r12
0x180020062  push    r13
0x180020064  push    r14
0x180020066  push    r15
0x180020068  mov     rbp, rsp
0x18002006b  sub     rsp, 50h
0x18002006f  mov     r15, r8
0x180020072  mov     r13, rdx
0x180020075  mov     r14, rcx
0x180020078  xor     r12d, r12d
0x18002007b  mov     ebx, r12d
0x18002007e  mov     [rbp+var_10], rbx
0x180020082  test    rcx, rcx
0x180020085  jz      loc_1800204A6
0x18002008b  test    rdx, rdx
0x18002008e  jz      loc_1800204A6
0x180020094  test    r8, r8
0x180020097  jz      loc_1800204A6
0x18002009d  mov     [rbp+var_18], r12
0x1800200a1  mov     edi, r12d
0x1800200a4  mov     [rbp+var_8], r12
0x1800200a8  mov     [rbp+pcchLength], r12
0x1800200ac  mov     [rbp+arg_0], r12
0x1800200b0  mov     edx, 7FFFFFFFh
0x1800200b5  mov     ecx, edx
0x1800200b7  mov     rax, r14
0x1800200ba  cmp     [rax], r12w
0x1800200be  jz      short loc_1800200CA
0x1800200c0  add     rax, 2
0x1800200c4  sub     rcx, 1
0x1800200c8  jnz     short loc_1800200BA
0x1800200ca  mov     rax, rcx
0x1800200cd  sub     rdx, rcx; cchMax
0x1800200d0  neg     rax
0x1800200d3  sbb     r10, r10
0x1800200d6  and     r10, rdx
0x1800200d9  test    rcx, rcx
0x1800200dc  jnz     short loc_1800200ED
0x1800200de  neg     rcx
0x1800200e1  sbb     esi, esi
0x1800200e3  not     esi
0x1800200e5  and     esi, 57h
0x1800200e8  jmp     loc_18002018E
0x1800200ed  lea     r8, [rbp+pcchLength]; pcchLength
0x1800200f1  mov     rcx, r15; psz
0x1800200f4  call    StringLengthWorkerW
0x1800200f9  test    eax, eax
0x1800200fb  jns     short loc_18002010E
0x1800200fd  movzx   esi, ax
0x180020100  lea     rcx, [rbp+var_18]
0x180020104  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180020109  jmp     loc_18002018E
0x18002010e  lea     r8, [rbp+arg_0]; pcchLength
0x180020112  lea     rcx, asc_1800C3A8C; "\\"
0x180020119  call    StringLengthWorkerW
0x18002011e  test    eax, eax
0x180020120  jns     short loc_180020127
0x180020122  movzx   esi, ax
0x180020125  jmp     short loc_18002018E
0x180020127  mov     rcx, [rbp+arg_0]
0x18002012b  add     rcx, r10
0x18002012e  mov     rsi, [rbp+pcchLength]
0x180020132  add     rsi, 2
0x180020136  add     rsi, rcx
0x180020139  lea     rdx, [rsi+rsi]; uBytes
0x18002013d  mov     ecx, 40h ; '@'; uFlags
0x180020142  call    cs:__imp_LocalAlloc
0x180020148  mov     r12, rax
0x18002014b  test    rax, rax
0x18002014e  jnz     short loc_180020155
0x180020150  lea     esi, [rax+0Eh]
0x180020153  jmp     short loc_180020192
0x180020155  mov     [rsp+50h+var_28], r15
0x18002015a  lea     rax, asc_1800C3A8C; "\\"
0x180020161  mov     [rsp+50h+var_30], rax
0x180020166  mov     r9, r14
0x180020169  lea     r8, aSSS; "%s%s%s"
0x180020170  mov     rdx, rsi; unsigned __int64
0x180020173  mov     rcx, r12; unsigned __int16 *
0x180020176  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002017b  test    eax, eax
0x18002017d  jz      short loc_1800201FD
0x18002017f  movzx   esi, ax
0x180020182  mov     rcx, r12; hMem
0x180020185  call    cs:__imp_LocalFree
0x18002018b  xor     r12d, r12d
0x18002018e  test    esi, esi
0x180020190  jz      short loc_180020207
0x180020192  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180020199  jz      loc_180020485
0x18002019f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800201a6  test    rax, rax
0x1800201a9  jz      short loc_1800201C7
0x1800201ab  mov     r9d, esi
0x1800201ae  mov     r8, r14
0x1800201b1  lea     rdx, aCopysinglefile_2; "CopySingleFile: failed to do PathAppend"...
0x1800201b8  mov     ecx, 2
0x1800201bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201c2  jmp     loc_180020485
0x1800201c7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800201ce  jz      loc_180020485
0x1800201d4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800201db  jz      loc_180020485
0x1800201e1  mov     r9d, esi
0x1800201e4  mov     r8, r14
0x1800201e7  lea     rdx, aCopysinglefile_2; "CopySingleFile: failed to do PathAppend"...
0x1800201ee  mov     ecx, 2; unsigned int
0x1800201f3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800201f8  jmp     loc_180020485
0x1800201fd  mov     rdi, r12
0x180020200  mov     [rbp+var_8], r12
0x180020204  xor     r12d, r12d
0x180020207  mov     [rbp+arg_0], r12
0x18002020b  mov     rbx, r12
0x18002020e  mov     [rbp+var_10], rbx
0x180020212  mov     [rbp+var_18], r12
0x180020216  mov     [rbp+pcchLength], r12
0x18002021a  mov     [rbp+var_20], r12
0x18002021e  lea     r8, [rbp+var_18]; pcchLength
0x180020222  mov     rcx, r13; psz
0x180020225  call    StringLengthWorkerW
0x18002022a  mov     esi, eax
0x18002022c  test    eax, eax
0x18002022e  js      loc_1800202CE
0x180020234  lea     r8, [rbp+pcchLength]; pcchLength
0x180020238  mov     rcx, r15; psz
0x18002023b  call    StringLengthWorkerW
0x180020240  mov     esi, eax
0x180020242  test    eax, eax
0x180020244  js      short loc_1800202C5
0x180020246  lea     r8, [rbp+var_20]; pcchLength
0x18002024a  lea     rcx, asc_1800C3A8C; "\\"
0x180020251  call    StringLengthWorkerW
0x180020256  mov     esi, eax
0x180020258  test    eax, eax
0x18002025a  js      short loc_1800202C5
0x18002025c  mov     r8, [rbp+var_20]
0x180020260  add     r8, [rbp+pcchLength]
0x180020264  mov     rsi, [rbp+var_18]
0x180020268  add     rsi, 2
0x18002026c  add     rsi, r8
0x18002026f  lea     rdx, [rsi+rsi]; uBytes
0x180020273  mov     ecx, 40h ; '@'; uFlags
0x180020278  call    cs:__imp_LocalAlloc
0x18002027e  mov     r14, rax
0x180020281  mov     [rbp+arg_0], rax
0x180020285  test    rax, rax
0x180020288  jnz     short loc_180020299
0x18002028a  lea     rcx, [rbp+arg_0]
0x18002028e  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180020293  lea     esi, [r14+0Eh]
0x180020297  jmp     short loc_1800202D5
0x180020299  mov     [rsp+50h+var_28], r15
0x18002029e  lea     rax, asc_1800C3A8C; "\\"
0x1800202a5  mov     [rsp+50h+var_30], rax
0x1800202aa  mov     r9, r13
0x1800202ad  lea     r8, aSSS; "%s%s%s"
0x1800202b4  mov     rdx, rsi; unsigned __int64
0x1800202b7  mov     rcx, r14; unsigned __int16 *
0x1800202ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800202bf  mov     esi, eax
0x1800202c1  test    eax, eax
0x1800202c3  jz      short loc_18002031B
0x1800202c5  lea     rcx, [rbp+arg_0]
0x1800202c9  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800202ce  movzx   esi, si
0x1800202d1  test    esi, esi
0x1800202d3  jz      short loc_180020325
0x1800202d5  mov     r9d, esi
0x1800202d8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800202df  jz      loc_180020485
0x1800202e5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800202ec  test    rax, rax
0x1800202ef  jz      short loc_1800202F9
0x1800202f1  mov     r8, r13
0x1800202f4  jmp     loc_1800201B1
0x1800202f9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180020300  jz      loc_180020485
0x180020306  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002030d  jz      loc_180020485
0x180020313  mov     r8, r13
0x180020316  jmp     loc_1800201E7
0x18002031b  mov     rbx, r14
0x18002031e  mov     [rbp+var_10], rbx
0x180020322  mov     esi, r12d
0x180020325  xor     r8d, r8d; bFailIfExists
0x180020328  mov     rdx, rbx; lpNewFileName
0x18002032b  mov     rcx, rdi; lpExistingFileName
0x18002032e  call    cs:__imp_CopyFileW
0x180020334  test    eax, eax
0x180020336  jnz     loc_180020485
0x18002033c  call    cs:__imp_GetLastError
0x180020342  mov     esi, eax
0x180020344  cmp     eax, 5
0x180020347  jnz     loc_180020425
0x18002034d  lea     edx, [rax+7Bh]; dwFileAttributes
0x180020350  mov     rcx, rbx; lpFileName
0x180020353  call    cs:__imp_SetFileAttributesW
0x180020359  test    eax, eax
0x18002035b  jz      short loc_1800203B9
0x18002035d  xor     r8d, r8d; bFailIfExists
0x180020360  mov     rdx, rbx; lpNewFileName
0x180020363  mov     rcx, rdi; lpExistingFileName
0x180020366  call    cs:__imp_CopyFileW
0x18002036c  test    eax, eax
0x18002036e  jnz     loc_180020420
0x180020374  call    cs:__imp_GetLastError
0x18002037a  mov     ecx, eax
0x18002037c  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180020383  jz      loc_180020420
0x180020389  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180020390  test    rax, rax
0x180020393  jz      short loc_18002039E
0x180020395  lea     rdx, aCopysinglefile; "CopySingleFile: reached error in CopyFi"...
0x18002039c  jmp     short loc_1800203DD
0x18002039e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800203a5  jz      short loc_180020420
0x1800203a7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800203ae  jz      short loc_180020420
0x1800203b0  lea     rdx, aCopysinglefile; "CopySingleFile: reached error in CopyFi"...
0x1800203b7  jmp     short loc_18002040C
0x1800203b9  call    cs:__imp_GetLastError
0x1800203bf  mov     ecx, eax
0x1800203c1  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800203c8  jz      short loc_180020420
0x1800203ca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800203d1  test    rax, rax
0x1800203d4  jz      short loc_1800203F3
0x1800203d6  lea     rdx, aCopysinglefile_0; "CopySingleFile: SetFileAttribute failed"...
0x1800203dd  mov     r8, rdi
0x1800203e0  mov     r9, rbx
0x1800203e3  mov     dword ptr [rsp+50h+var_30], ecx
0x1800203e7  mov     ecx, 2
0x1800203ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203f1  jmp     short loc_180020420
0x1800203f3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800203fa  jz      short loc_180020420
0x1800203fc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180020403  jz      short loc_180020420
0x180020405  lea     rdx, aCopysinglefile_0; "CopySingleFile: SetFileAttribute failed"...
0x18002040c  mov     dword ptr [rsp+50h+var_30], ecx
0x180020410  mov     r9, rbx
0x180020413  mov     r8, rdi
0x180020416  mov     ecx, 2; unsigned int
0x18002041b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180020420  mov     esi, r12d
0x180020423  jmp     short loc_180020485
0x180020425  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002042c  jz      short loc_180020485
0x18002042e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180020435  test    rax, rax
0x180020438  jz      short loc_180020457
0x18002043a  mov     dword ptr [rsp+50h+var_30], esi
0x18002043e  mov     r9, rbx
0x180020441  mov     r8, rdi
0x180020444  lea     rdx, aCopysinglefile_1; "CopySingleFile: failed to CopyFile from"...
0x18002044b  mov     ecx, 2
0x180020450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020455  jmp     short loc_180020485
0x180020457  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002045e  jz      short loc_180020485
0x180020460  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180020467  jz      short loc_180020485
0x180020469  mov     dword ptr [rsp+50h+var_30], esi
0x18002046d  mov     r9, rbx
0x180020470  mov     r8, rdi
0x180020473  lea     rdx, aCopysinglefile_1; "CopySingleFile: failed to CopyFile from"...
0x18002047a  mov     ecx, 2; unsigned int
0x18002047f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180020484  nop
0x180020485  test    rbx, rbx
0x180020488  jz      short loc_180020494
0x18002048a  mov     rcx, rbx; hMem
0x18002048d  call    cs:__imp_LocalFree
0x180020493  nop
0x180020494  test    rdi, rdi
0x180020497  jz      short loc_1800204A2
0x180020499  mov     rcx, rdi; hMem
0x18002049c  call    cs:__imp_LocalFree
0x1800204a2  mov     eax, esi
0x1800204a4  jmp     short loc_1800204AB
0x1800204a6  mov     eax, 57h ; 'W'
0x1800204ab  mov     rbx, [rsp+50h+arg_8]
0x1800204b3  add     rsp, 50h
0x1800204b7  pop     r15
0x1800204b9  pop     r14
0x1800204bb  pop     r13
0x1800204bd  pop     r12
0x1800204bf  pop     rdi
0x1800204c0  pop     rsi
0x1800204c1  pop     rbp
0x1800204c2  retn
```
