# CFmIfsEngine::FormatEx2(ushort const *,__MIDL___MIDL_itf_cfmifs_0000_0000_0002,ushort const *,__MIDL___MIDL_itf_cfmifs_0000_0000_0010 *,IFmIfsClient *)

- ea: `0x180002280`
- end: `0x180002552`
- name: `?FormatEx2@CFmIfsEngine@@UEAAJPEBGW4__MIDL___MIDL_itf_cfmifs_0000_0000_0002@@0PEAU__MIDL___MIDL_itf_cfmifs_0000_0000_0010@@PEAUIFmIfsClient@@@Z`
- size: `722`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002280`
- `0x180002558`
- `0x180006002`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000249c`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000249c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000247a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000247a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800024b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800024b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002487`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002487`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800022fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000231b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002338`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002355`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002372`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000238f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002414`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000242f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800022fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000231b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002338`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002355`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002372`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000238f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002414`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000242f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002470`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002470`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800022de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800022de`

## string_xrefs

- `0x1800022d5`: `FMIFS.DLL`
- `0x180002311`: `EnableVolumeCompression`

## pseudocode

```c
__int64 __fastcall CFmIfsEngine::FormatEx2(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, __int64 a6)
{
  int v10; // eax
  signed int v11; // ebx
  HMODULE Library; // rax
  HMODULE v13; // rdi
  signed int LastError; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  HMODULE hLibModule; // [rsp+30h] [rbp-69h] BYREF
  FARPROC ProcAddress; // [rsp+50h] [rbp-49h]

  memset_0(&hLibModule, 0, 0x68u);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  *(_BYTE *)(a1 + 72) = 0;
  v11 = v10;
  if ( v10 < 0 )
    goto LABEL_20;
  Library = LoadLibraryExW(L"FMIFS.DLL", 0, 0);
  hLibModule = Library;
  v13 = Library;
  if ( Library )
  {
    if ( GetProcAddress(Library, "ChkdskEx") )
    {
      if ( GetProcAddress(v13, "EnableVolumeCompression") )
      {
        if ( GetProcAddress(v13, "EnableVolumeIntegrity") )
        {
          ProcAddress = GetProcAddress(v13, "FormatEx2");
          if ( ProcAddress )
          {
            if ( GetProcAddress(v13, "GetDefaultFileSystem") )
            {
              if ( GetProcAddress(v13, "QueryCorruptionState") )
              {
                if ( GetProcAddress(v13, "QueryFileSystemName") )
                {
                  if ( GetProcAddress(v13, "GetFirstCorruptionInfo") )
                  {
                    if ( GetProcAddress(v13, "GetNextCorruptionInfo") )
                    {
                      if ( GetProcAddress(v13, "GetCorruptionInfoClose") )
                      {
                        if ( GetProcAddress(v13, "FreeCorruptionInfo") )
                        {
                          v11 = 0;
                          if ( GetProcAddress(v13, "SetLabel") )
                          {
LABEL_26:
                            if ( v11 < 0 )
                              goto LABEL_21;
                            goto LABEL_27;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 < 0 )
  {
    if ( v13 )
    {
      UnLoadFMIFS((struct FMIFSLib *)&hLibModule);
LABEL_20:
      v13 = hLibModule;
      goto LABEL_21;
    }
    goto LABEL_26;
  }
LABEL_27:
  if ( *(_QWORD *)(a1 + 64) != a6 )
  {
    if ( a6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6);
    v16 = *(_QWORD *)(a1 + 64);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *(_QWORD *)(a1 + 64) = a6;
  }
  ((void (__fastcall *)(__int64, _QWORD, __int64, __int64, void *))ProcAddress)(
    a2,
    a3,
    a4,
    a5,
    &CFmIfsEngine::_FmIfsCallback);
  v17 = *(_QWORD *)(a1 + 64);
  if ( v17 )
  {
    *(_QWORD *)(a1 + 64) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
LABEL_21:
  if ( !FreeLibrary(v13) )
    GetLastError();
  AcquireSRWLockExclusive(&g_srwTLSChkDskThreadData);
  if ( !--g_cTLSChkDskThreadData )
  {
    TlsFree(g_iTLSChkDskThreadData);
    g_iTLSChkDskThreadData = 0;
  }
  ReleaseSRWLockExclusive(&g_srwTLSChkDskThreadData);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180002280  push    rbp
0x180002282  push    rbx
0x180002283  push    rsi
0x180002284  push    rdi
0x180002285  push    r12
0x180002287  push    r13
0x180002289  push    r14
0x18000228b  push    r15
0x18000228d  lea     rbp, [rsp-0Fh]
0x180002292  sub     rsp, 0A8h
0x180002299  mov     r13, rdx
0x18000229c  mov     r12d, r8d
0x18000229f  xor     edx, edx; Val
0x1800022a1  mov     r14, rcx
0x1800022a4  lea     rcx, [rbp+47h+hLibModule]; void *
0x1800022a8  mov     r15, r9
0x1800022ab  lea     r8d, [rdx+68h]; Size
0x1800022af  call    memset_0
0x1800022b4  mov     rax, [r14]
0x1800022b7  mov     rcx, r14
0x1800022ba  mov     rax, [rax+28h]
0x1800022be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c3  mov     byte ptr [r14+48h], 0
0x1800022c8  mov     ebx, eax
0x1800022ca  test    eax, eax
0x1800022cc  js      loc_180002469
0x1800022d2  xor     r8d, r8d; dwFlags
0x1800022d5  lea     rcx, LibFileName; "FMIFS.DLL"
0x1800022dc  xor     edx, edx; hFile
0x1800022de  call    cs:__imp_LoadLibraryExW
0x1800022e4  mov     [rbp+47h+hLibModule], rax
0x1800022e8  mov     rdi, rax
0x1800022eb  test    rax, rax
0x1800022ee  jz      loc_180002442
0x1800022f4  lea     rdx, ProcName; "ChkdskEx"
0x1800022fb  mov     rcx, rax; hModule
0x1800022fe  call    cs:__imp_GetProcAddress
0x180002304  mov     [rbp+47h+var_A8], rax
0x180002308  test    rax, rax
0x18000230b  jz      loc_180002442
0x180002311  lea     rdx, aEnablevolumeco; "EnableVolumeCompression"
0x180002318  mov     rcx, rdi; hModule
0x18000231b  call    cs:__imp_GetProcAddress
0x180002321  mov     [rbp+47h+var_A0], rax
0x180002325  test    rax, rax
0x180002328  jz      loc_180002442
0x18000232e  lea     rdx, aEnablevolumein; "EnableVolumeIntegrity"
0x180002335  mov     rcx, rdi; hModule
0x180002338  call    cs:__imp_GetProcAddress
0x18000233e  mov     [rbp+47h+var_98], rax
0x180002342  test    rax, rax
0x180002345  jz      loc_180002442
0x18000234b  lea     rdx, aFormatex2; "FormatEx2"
0x180002352  mov     rcx, rdi; hModule
0x180002355  call    cs:__imp_GetProcAddress
0x18000235b  mov     [rbp+47h+var_90], rax
0x18000235f  test    rax, rax
0x180002362  jz      loc_180002442
0x180002368  lea     rdx, aGetdefaultfile; "GetDefaultFileSystem"
0x18000236f  mov     rcx, rdi; hModule
0x180002372  call    cs:__imp_GetProcAddress
0x180002378  mov     [rbp+47h+var_88], rax
0x18000237c  test    rax, rax
0x18000237f  jz      loc_180002442
0x180002385  lea     rdx, aQuerycorruptio; "QueryCorruptionState"
0x18000238c  mov     rcx, rdi; hModule
0x18000238f  call    cs:__imp_GetProcAddress
0x180002395  mov     [rbp+47h+var_80], rax
0x180002399  test    rax, rax
0x18000239c  jz      loc_180002442
0x1800023a2  lea     rdx, aQueryfilesyste; "QueryFileSystemName"
0x1800023a9  mov     rcx, rdi; hModule
0x1800023ac  call    cs:__imp_GetProcAddress
0x1800023b2  mov     [rbp+47h+var_78], rax
0x1800023b6  test    rax, rax
0x1800023b9  jz      loc_180002442
0x1800023bf  lea     rdx, aGetfirstcorrup; "GetFirstCorruptionInfo"
0x1800023c6  mov     rcx, rdi; hModule
0x1800023c9  call    cs:__imp_GetProcAddress
0x1800023cf  mov     [rbp+47h+var_70], rax
0x1800023d3  test    rax, rax
0x1800023d6  jz      short loc_180002442
0x1800023d8  lea     rdx, aGetnextcorrupt; "GetNextCorruptionInfo"
0x1800023df  mov     rcx, rdi; hModule
0x1800023e2  call    cs:__imp_GetProcAddress
0x1800023e8  mov     [rbp+47h+var_68], rax
0x1800023ec  test    rax, rax
0x1800023ef  jz      short loc_180002442
0x1800023f1  lea     rdx, aGetcorruptioni; "GetCorruptionInfoClose"
0x1800023f8  mov     rcx, rdi; hModule
0x1800023fb  call    cs:__imp_GetProcAddress
0x180002401  mov     [rbp+47h+var_60], rax
0x180002405  test    rax, rax
0x180002408  jz      short loc_180002442
0x18000240a  lea     rdx, aFreecorruption; "FreeCorruptionInfo"
0x180002411  mov     rcx, rdi; hModule
0x180002414  call    cs:__imp_GetProcAddress
0x18000241a  mov     [rbp+47h+var_58], rax
0x18000241e  test    rax, rax
0x180002421  jz      short loc_180002442
0x180002423  lea     rdx, aSetlabel; "SetLabel"
0x18000242a  mov     rcx, rdi; hModule
0x18000242d  xor     ebx, ebx
0x18000242f  call    cs:__imp_GetProcAddress
0x180002435  mov     [rbp+47h+var_50], rax
0x180002439  test    rax, rax
0x18000243c  jnz     loc_1800024CF
0x180002442  call    cs:__imp_GetLastError
0x180002448  mov     ebx, eax
0x18000244a  test    eax, eax
0x18000244c  jle     short loc_180002457
0x18000244e  movzx   ebx, ax
0x180002451  or      ebx, 80070000h
0x180002457  test    ebx, ebx
0x180002459  jns     short loc_1800024D3
0x18000245b  test    rdi, rdi
0x18000245e  jz      short loc_1800024CF
0x180002460  lea     rcx, [rbp+47h+hLibModule]; struct FMIFSLib *
0x180002464  call    ?UnLoadFMIFS@@YAJPEAUFMIFSLib@@@Z; UnLoadFMIFS(FMIFSLib *)
0x180002469  mov     rdi, [rbp+47h+hLibModule]
0x18000246d  mov     rcx, rdi; hLibModule
0x180002470  call    cs:__imp_FreeLibrary
0x180002476  test    eax, eax
0x180002478  jnz     short loc_180002480
0x18000247a  call    cs:__imp_GetLastError
0x180002480  lea     rcx, ?g_srwTLSChkDskThreadData@@3U_RTL_SRWLOCK@@A; SRWLock
0x180002487  call    cs:__imp_AcquireSRWLockExclusive
0x18000248d  sub     cs:?g_cTLSChkDskThreadData@@3JA, 1; long g_cTLSChkDskThreadData
0x180002494  jnz     short loc_1800024AC
0x180002496  mov     ecx, cs:?g_iTLSChkDskThreadData@@3KA; dwTlsIndex
0x18000249c  call    cs:__imp_TlsFree
0x1800024a2  mov     cs:?g_iTLSChkDskThreadData@@3KA, 0; ulong g_iTLSChkDskThreadData
0x1800024ac  lea     rcx, ?g_srwTLSChkDskThreadData@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800024b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800024b9  mov     eax, ebx
0x1800024bb  add     rsp, 0A8h
0x1800024c2  pop     r15
0x1800024c4  pop     r14
0x1800024c6  pop     r13
0x1800024c8  pop     r12
0x1800024ca  pop     rdi
0x1800024cb  pop     rsi
0x1800024cc  pop     rbx
0x1800024cd  pop     rbp
0x1800024ce  retn
0x1800024cf  test    ebx, ebx
0x1800024d1  js      short loc_18000246D
0x1800024d3  mov     rsi, [rbp+47h+arg_28]
0x1800024d7  cmp     [r14+40h], rsi
0x1800024db  jz      short loc_18000250A
0x1800024dd  test    rsi, rsi
0x1800024e0  jz      short loc_1800024F1
0x1800024e2  mov     rax, [rsi]
0x1800024e5  mov     rcx, rsi
0x1800024e8  mov     rax, [rax+8]
0x1800024ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f1  mov     rcx, [r14+40h]
0x1800024f5  test    rcx, rcx
0x1800024f8  jz      short loc_180002506
0x1800024fa  mov     rax, [rcx]
0x1800024fd  mov     rax, [rax+10h]
0x180002501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002506  mov     [r14+40h], rsi
0x18000250a  mov     r9, [rbp+47h+arg_20]
0x18000250e  lea     rax, ?_FmIfsCallback@CFmIfsEngine@@CAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z; CFmIfsEngine::_FmIfsCallback(_FMIFS_PACKET_TYPE,ulong,void *)
0x180002515  mov     [rsp+0E0h+var_C0], rax
0x18000251a  mov     r8, r15
0x18000251d  mov     rax, [rbp+47h+var_90]
0x180002521  mov     edx, r12d
0x180002524  mov     rcx, r13
0x180002527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252c  mov     rcx, [r14+40h]
0x180002530  test    rcx, rcx
0x180002533  jz      loc_18000246D
0x180002539  mov     qword ptr [r14+40h], 0
0x180002541  mov     rax, [rcx]
0x180002544  mov     rax, [rax+10h]
0x180002548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000254d  jmp     loc_18000246D
```
