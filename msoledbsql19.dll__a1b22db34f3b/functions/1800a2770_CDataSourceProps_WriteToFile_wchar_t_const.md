# CDataSourceProps::WriteToFile(wchar_t const *)

- ea: `0x1800a2770`
- end: `0x1800a2a30`
- name: `?WriteToFile@CDataSourceProps@@QEAAJPEB_W@Z`
- size: `704`
- prototype: `__int64 __fastcall(CDataSourceProps *__hidden this, const wchar_t *Path)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18009be80`

## callees

- `0x180003030`
- `0x180003d80`
- `0x18009de00`
- `0x18009fdc0`
- `0x1800a1190`
- `0x1800a1f30`
- `0x1800a2770`
- `0x1801355e0`
- `0x1801355f8`
- `0x180135660`
- `0x180135970`
- `0x180135a48`
- `0x1801a65e1`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800a28e6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800a28e6`
- `KERNEL32!GetLastError` at `0x1800a29a0`
- `KERNEL32!GetLastError` at `0x1800a29a0`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800a2978`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800a2978`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDataSourceProps::WriteToFile(CDataSourceProps *this, wchar_t *Path)
{
  int FullFileName; // ebx
  int v5; // eax
  __int64 v6; // r14
  unsigned int v7; // edi
  const wchar_t *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  const WCHAR *v11; // r8
  DWORD LastError; // ecx
  unsigned int v13; // eax
  __int128 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+30h] [rbp-D0h]
  _OWORD v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h]
  __int16 v19; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h]
  __int64 v21; // [rsp+80h] [rbp-80h]
  int v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+8Ch] [rbp-74h]
  __m128i si128; // [rsp+90h] [rbp-70h]
  _BYTE v25[1040]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  memset(v17, 0, sizeof(v17));
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  memset_0(v25, 0, 0x402u);
  v15 = 0;
  v16 = 0;
  CEXAutoBackupFile::CEXAutoBackupFile((CEXAutoBackupFile *)&v15);
  if ( (int)CDataSourceProps::GetConnectInfo(this, (struct tagOLEDB_DLGSTRUCT *)v17, 0) < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      FullFileName = bidTraceHR(off_180260410[0], 3690505, 2147500037LL);
    else
      FullFileName = -2147467259;
    goto LABEL_31;
  }
  FullFileName = GetFullFileName(Path, FileName, 0x104u, 0x40000000u);
  if ( FullFileName < 0 )
    goto LABEL_31;
  FullFileName = CEXAutoBackupFile::BackupFile((CEXAutoBackupFile *)&v15, FileName);
  if ( FullFileName >= 0 )
  {
    if ( (*(_BYTE *)(v20 + 312) & 1) == 0
      || (v6 = 1, _wcsicmp((const wchar_t *)(*(_QWORD *)(v21 + 32) + *(_QWORD *)(v20 + 320)), L"Yes")) )
    {
      v6 = 0;
    }
    v7 = 0;
    v8 = L"\t";
    while ( 1 )
    {
      v9 = *v8;
      v10 = v20 + 24 * v9;
      if ( (*(_BYTE *)v10 & 6) != 0 )
        v11 = ((_WORD)v9 == 2 || (_WORD)v9 == 30) && !v6
            ? 0LL
            : (const WCHAR *)(*(_QWORD *)(v21 + 32) + *(_QWORD *)(v10 + 8));
      else
        v11 = 0;
      if ( !WritePrivateProfileStringW(L"MSOLEDBSQL", (LPCWSTR)&g_rgLookup[64 * (unsigned __int64)*v8], v11, FileName) )
        break;
      ++v7;
      v8 += 3;
      if ( v7 >= 0x23 )
      {
        CEXAutoBackupFile::UndoBackup((CEXAutoBackupFile *)&v15);
        goto LABEL_28;
      }
    }
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 )
    {
      v13 = RemapError(LastError);
      v5 = bidTraceHR(off_180260410[0], 3758089, v13);
    }
    else
    {
      v5 = RemapError(LastError);
    }
    goto LABEL_27;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v5 = bidTraceHR(off_180260410[0], 3704841, 2147500037LL);
LABEL_27:
    FullFileName = v5;
    goto LABEL_28;
  }
  FullFileName = -2147467259;
LABEL_28:
  if ( v16 && *((_QWORD *)&v15 + 1) )
    CEXAutoBackupFile::RestoreFile((CEXAutoBackupFile *)&v15);
LABEL_31:
  CEXAutoBackupFile::~CEXAutoBackupFile((CEXAutoBackupFile *)&v15);
  CDlgATTRs::Uninitialize((CDlgATTRs *)&v19);
  return (unsigned int)FullFileName;
}

```

## disassembly

```asm
0x1800a2770  mov     [rsp-8+arg_10], rbx
0x1800a2775  push    rbp
0x1800a2776  push    rsi
0x1800a2777  push    rdi
0x1800a2778  push    r12
0x1800a277a  push    r13
0x1800a277c  push    r14
0x1800a277e  push    r15
0x1800a2780  lea     rbp, [rsp-5D0h]
0x1800a2788  sub     rsp, 6D0h
0x1800a278f  mov     rax, cs:__security_cookie
0x1800a2796  xor     rax, rsp
0x1800a2799  mov     [rbp+600h+var_40], rax
0x1800a27a0  mov     rdi, rdx
0x1800a27a3  mov     rbx, rcx
0x1800a27a6  xorps   xmm0, xmm0
0x1800a27a9  movdqa  [rsp+700h+var_6C0], xmm0
0x1800a27af  xorps   xmm1, xmm1
0x1800a27b2  movups  [rsp+700h+var_6B0], xmm1
0x1800a27b7  xor     r15d, r15d
0x1800a27ba  mov     [rsp+700h+var_6A0], r15
0x1800a27bf  mov     [rsp+700h+var_690], r15w
0x1800a27c5  mov     [rsp+700h+var_688], r15
0x1800a27ca  mov     [rbp+600h+var_680], r15
0x1800a27ce  mov     [rbp+600h+var_678], 0FFFFFFFFh
0x1800a27d5  mov     [rbp+600h+var_674], r15d
0x1800a27d9  movdqa  xmm0, cs:__xmm@00000000ffffffff00000000ffffffff
0x1800a27e1  movdqa  [rbp+600h+var_670], xmm0
0x1800a27e6  xor     edx, edx; Val
0x1800a27e8  mov     r8d, 402h; Size
0x1800a27ee  lea     rcx, [rbp+600h+var_660]; void *
0x1800a27f2  call    memset_0
0x1800a27f7  nop
0x1800a27f8  xorps   xmm0, xmm0
0x1800a27fb  xor     eax, eax
0x1800a27fd  movups  [rsp+700h+var_6E0], xmm0
0x1800a2802  mov     [rsp+700h+var_6D0], rax
0x1800a2807  lea     rcx, [rsp+700h+var_6E0]; this
0x1800a280c  call    ??0CEXAutoBackupFile@@QEAA@XZ; CEXAutoBackupFile::CEXAutoBackupFile(void)
0x1800a2811  nop
0x1800a2812  xor     r8d, r8d; bool *
0x1800a2815  lea     rdx, [rsp+700h+var_6C0]; struct tagOLEDB_DLGSTRUCT *
0x1800a281a  mov     rcx, rbx; this
0x1800a281d  call    ?GetConnectInfo@CDataSourceProps@@QEAAJPEAUtagOLEDB_DLGSTRUCT@@PEA_N@Z; CDataSourceProps::GetConnectInfo(tagOLEDB_DLGSTRUCT *,bool *)
0x1800a2822  test    eax, eax
0x1800a2824  jns     short loc_1800A2857
0x1800a2826  test    byte ptr cs:_bidGblFlags, 2
0x1800a282d  jz      short loc_1800A284D
0x1800a282f  mov     edx, 385009h
0x1800a2834  mov     r8d, 80004005h
0x1800a283a  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a2841  call    _bidTraceHR
0x1800a2846  mov     ebx, eax
0x1800a2848  jmp     loc_1800A29EE
0x1800a284d  mov     ebx, 80004005h
0x1800a2852  jmp     loc_1800A29EE
0x1800a2857  mov     r9d, 40000000h
0x1800a285d  mov     r8d, 104h
0x1800a2863  lea     rdx, [rbp+600h+FileName]; lpFileName
0x1800a286a  mov     rcx, rdi; Path
0x1800a286d  call    GetFullFileName
0x1800a2872  mov     ebx, eax
0x1800a2874  test    eax, eax
0x1800a2876  js      loc_1800A29EE
0x1800a287c  lea     rdx, [rbp+600h+FileName]; wchar_t *
0x1800a2883  lea     rcx, [rsp+700h+var_6E0]; this
0x1800a2888  call    ?BackupFile@CEXAutoBackupFile@@QEAAJPEB_W@Z; CEXAutoBackupFile::BackupFile(wchar_t const *)
0x1800a288d  mov     ebx, eax
0x1800a288f  test    eax, eax
0x1800a2891  jns     short loc_1800A28C2
0x1800a2893  test    byte ptr cs:_bidGblFlags, 2
0x1800a289a  jz      short loc_1800A28B8
0x1800a289c  mov     edx, 388809h
0x1800a28a1  mov     r8d, 80004005h
0x1800a28a7  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a28ae  call    _bidTraceHR
0x1800a28b3  jmp     loc_1800A29D1
0x1800a28b8  mov     ebx, 80004005h
0x1800a28bd  jmp     loc_1800A29D3
0x1800a28c2  mov     rcx, [rsp+700h+var_688]
0x1800a28c7  test    byte ptr [rcx+138h], 1
0x1800a28ce  jz      short loc_1800A28F6
0x1800a28d0  mov     rcx, [rcx+140h]
0x1800a28d7  mov     rax, [rbp+600h+var_680]
0x1800a28db  add     rcx, [rax+20h]; String1
0x1800a28df  lea     rdx, aYes_0; "Yes"
0x1800a28e6  call    cs:__imp__wcsicmp
0x1800a28ec  test    eax, eax
0x1800a28ee  mov     r14d, 1
0x1800a28f4  jz      short loc_1800A28F9
0x1800a28f6  mov     r14, r15
0x1800a28f9  mov     edi, r15d
0x1800a28fc  lea     rsi, asc_1801CCE84; "\t"
0x1800a2903  lea     rcx, ?g_rgLookup@@3QBUtagKeyLookup@@B; "Server"
0x1800a290a  mov     r12d, 2
0x1800a2910  mov     r13d, 1Eh
0x1800a2916  nop     word ptr [rax+rax+00000000h]
0x1800a2920  movzx   edx, word ptr [rsi]
0x1800a2923  mov     r10d, edx
0x1800a2926  shl     r10, 6
0x1800a292a  add     r10, rcx
0x1800a292d  lea     rcx, [rdx+rdx*2]
0x1800a2931  mov     rax, [rsp+700h+var_688]
0x1800a2936  lea     r8, [rax+rcx*8]
0x1800a293a  test    byte ptr [r8], 6
0x1800a293e  jnz     short loc_1800A2945
0x1800a2940  mov     r8, r15
0x1800a2943  jmp     short loc_1800A2967
0x1800a2945  cmp     r12w, dx
0x1800a2949  jz      short loc_1800A2951
0x1800a294b  cmp     r13w, dx
0x1800a294f  jnz     short loc_1800A295B
0x1800a2951  test    r14, r14
0x1800a2954  jnz     short loc_1800A295B
0x1800a2956  mov     r8, r15
0x1800a2959  jmp     short loc_1800A2967
0x1800a295b  mov     rax, [rbp+600h+var_680]
0x1800a295f  mov     r8, [r8+8]
0x1800a2963  add     r8, [rax+20h]; lpString
0x1800a2967  lea     r9, [rbp+600h+FileName]; lpFileName
0x1800a296e  mov     rdx, r10; lpKeyName
0x1800a2971  lea     rcx, AppName; "MSOLEDBSQL"
0x1800a2978  call    cs:__imp_WritePrivateProfileStringW
0x1800a297e  test    eax, eax
0x1800a2980  jz      short loc_1800A29A0
0x1800a2982  inc     edi
0x1800a2984  add     rsi, 6
0x1800a2988  cmp     edi, 23h ; '#'
0x1800a298b  lea     rcx, ?g_rgLookup@@3QBUtagKeyLookup@@B; "Server"
0x1800a2992  jb      short loc_1800A2920
0x1800a2994  lea     rcx, [rsp+700h+var_6E0]; this
0x1800a2999  call    ?UndoBackup@CEXAutoBackupFile@@QEAAJXZ; CEXAutoBackupFile::UndoBackup(void)
0x1800a299e  jmp     short loc_1800A29D3
0x1800a29a0  call    cs:__imp_GetLastError
0x1800a29a6  mov     ecx, eax; unsigned int
0x1800a29a8  test    byte ptr cs:_bidGblFlags, r12b
0x1800a29af  jz      short loc_1800A29CC
0x1800a29b1  call    ?RemapError@@YAJK@Z; RemapError(ulong)
0x1800a29b6  mov     r8d, eax
0x1800a29b9  mov     edx, 395809h
0x1800a29be  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a29c5  call    _bidTraceHR
0x1800a29ca  jmp     short loc_1800A29D1
0x1800a29cc  call    ?RemapError@@YAJK@Z; RemapError(ulong)
0x1800a29d1  mov     ebx, eax
0x1800a29d3  cmp     [rsp+700h+var_6D0], 0
0x1800a29d9  jz      short loc_1800A29EE
0x1800a29db  cmp     qword ptr [rsp+700h+var_6E0+8], 0
0x1800a29e1  jz      short loc_1800A29EE
0x1800a29e3  lea     rcx, [rsp+700h+var_6E0]; this
0x1800a29e8  call    ?RestoreFile@CEXAutoBackupFile@@QEAAJXZ; CEXAutoBackupFile::RestoreFile(void)
0x1800a29ed  nop
0x1800a29ee  lea     rcx, [rsp+700h+var_6E0]; this
0x1800a29f3  call    ??1CEXAutoBackupFile@@QEAA@XZ; CEXAutoBackupFile::~CEXAutoBackupFile(void)
0x1800a29f8  nop
0x1800a29f9  lea     rcx, [rsp+700h+var_690]; this
0x1800a29fe  call    ?Uninitialize@CDlgATTRs@@QEAAXXZ; CDlgATTRs::Uninitialize(void)
0x1800a2a03  nop
0x1800a2a04  mov     eax, ebx
0x1800a2a06  mov     rcx, [rbp+600h+var_40]
0x1800a2a0d  xor     rcx, rsp; StackCookie
0x1800a2a10  call    __security_check_cookie
0x1800a2a15  mov     rbx, [rsp+700h+arg_10]
0x1800a2a1d  add     rsp, 6D0h
0x1800a2a24  pop     r15
0x1800a2a26  pop     r14
0x1800a2a28  pop     r13
0x1800a2a2a  pop     r12
0x1800a2a2c  pop     rdi
0x1800a2a2d  pop     rsi
0x1800a2a2e  pop     rbp
0x1800a2a2f  retn
```
