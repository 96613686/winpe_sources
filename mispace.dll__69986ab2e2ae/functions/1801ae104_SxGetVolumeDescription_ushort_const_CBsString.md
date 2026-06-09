# SxGetVolumeDescription(ushort const *,CBsString *)

- ea: `0x1801ae104`
- end: `0x1801ae4e5`
- name: `?SxGetVolumeDescription@@YAJPEBGPEAVCBsString@@@Z`
- size: `993`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CBsString *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180135320`

## callees

- `0x180006dd4`
- `0x1801ae104`
- `0x1801aecd4`
- `0x1801af024`
- `0x1801af258`
- `0x1801af2f4`
- `0x1801b081c`
- `0x1801b093c`
- `0x1801b0b88`
- `0x1801b0c38`
- `0x1801b0ec0`
- `0x1801b0fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae334`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae1e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae48f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae49e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae1e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae48f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae49e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae2f2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801ae254`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801ae254`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801ae324`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801ae324`
- `ntdll!RtlSetThreadErrorMode` at `0x1801ae194`
- `ntdll!RtlSetThreadErrorMode` at `0x1801ae4af`
- `ntdll!RtlSetThreadErrorMode` at `0x1801ae194`
- `ntdll!RtlSetThreadErrorMode` at `0x1801ae4af`

## pseudocode

```c
__int64 __fastcall SxGetVolumeDescription(const unsigned __int16 *a1, struct CBsString *this)
{
  unsigned __int16 *v4; // r14
  _WORD *v5; // rsi
  unsigned int v6; // eax
  __int16 v7; // ax
  __int64 v8; // rdi
  DWORD LastError; // eax
  DWORD v10; // ecx
  __int16 v11; // r15
  DWORD v12; // edi
  __int64 v13; // rax
  const unsigned __int16 *i; // rdi
  unsigned __int16 v15; // dx
  __int64 v16; // rax
  unsigned int v17; // ebx
  DWORD MaximumComponentLength; // [rsp+40h] [rbp-40h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-38h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-34h]
  __int16 v22; // [rsp+4Eh] [rbp-32h]
  int v23; // [rsp+50h] [rbp-30h]
  DWORD cchReturnLength; // [rsp+C8h] [rbp+48h] BYREF
  ULONG OldMode; // [rsp+D0h] [rbp+50h] BYREF
  DWORD FileSystemFlags; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetVolumeDescription", 0x23Cu, 1u);
  cchReturnLength = 0;
  v4 = 0;
  FileSystemFlags = 0;
  v5 = 0;
  MaximumComponentLength = 0;
  OldMode = 0;
  if ( this )
    CBsString::Empty(this);
  v6 = RtlSetThreadErrorMode(0x10u, &OldMode);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v6);
  v7 = 588;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v21 = 588;
    v7 = 590;
    if ( this )
    {
      LODWORD(v8) = 32;
      while ( 1 )
      {
        v21 = v7;
        LastFailureAsHRESULT = 0;
        v8 = SxScaledGrowth(v8);
        CoTaskMemFree(v5);
        v5 = CoTaskMemAlloc((unsigned int)(2 * v8 + 2));
        v7 = 599;
        if ( !v5 )
          break;
        LastFailureAsHRESULT = 0;
        v21 = 599;
        memset_0(v5, 0, (unsigned int)(2 * v8 + 2));
        if ( GetVolumeInformationW(a1, v5, v8, 0, &MaximumComponentLength, &FileSystemFlags, 0, 0)
          || (LastError = GetLastError(), LastError == 21) )
        {
          v5[v8] = 0;
          if ( *v5 )
          {
            LastFailureAsHRESULT = CBsString::Append(this, v5);
            v7 = 620;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_48;
            v21 = 620;
          }
          v10 = 64;
          v11 = 636;
          cchReturnLength = 64;
          while ( 1 )
          {
            v12 = SxScaledGrowth(v10);
            CoTaskMemFree(v4);
            v4 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v12);
            v7 = 630;
            if ( !v4 )
              goto LABEL_46;
            LastFailureAsHRESULT = 0;
            v21 = 630;
            if ( GetVolumePathNamesForVolumeNameW(a1, v4, v12, &cchReturnLength) )
            {
              v13 = -1;
              do
                ++v13;
              while ( v4[v13] );
              if ( v13 )
              {
                if ( *v5 )
                {
                  LastFailureAsHRESULT = CBsString::Append(this, L" ");
                  v7 = 652;
                  if ( LastFailureAsHRESULT < 0 )
                    goto LABEL_48;
                  v21 = 652;
                }
                LastFailureAsHRESULT = CBsString::Append(this, L"(");
                v7 = 654;
                if ( LastFailureAsHRESULT < 0 )
                  goto LABEL_48;
                v21 = 654;
                v11 = 660;
                for ( i = v4; *i; i += v16 + 1 )
                {
                  if ( i != v4 )
                  {
                    LastFailureAsHRESULT = CBsString::Append(this, L", ");
                    if ( LastFailureAsHRESULT < 0 )
                      goto LABEL_24;
                    v21 = 660;
                  }
                  LastFailureAsHRESULT = CBsString::Append(this, i);
                  v7 = 662;
                  if ( LastFailureAsHRESULT < 0 )
                    goto LABEL_48;
                  v21 = 662;
                  CBsString::UnTrailing(this, v15);
                  v16 = -1;
                  do
                    ++v16;
                  while ( i[v16] );
                }
                LastFailureAsHRESULT = CBsString::Append(this, L")");
                v7 = 665;
                if ( LastFailureAsHRESULT < 0 )
                  goto LABEL_48;
                v21 = 665;
              }
              if ( *((_DWORD *)this + 2) )
                goto LABEL_49;
              LastFailureAsHRESULT = CBsString::Set(this, a1);
              v7 = 670;
              if ( LastFailureAsHRESULT >= 0 )
              {
                v21 = 670;
                goto LABEL_49;
              }
              goto LABEL_48;
            }
            if ( GetLastError() != 234 )
            {
              LastFailureAsHRESULT = GetLastFailureAsHRESULT();
LABEL_24:
              v22 = v11;
              goto LABEL_49;
            }
            v10 = cchReturnLength;
            LastFailureAsHRESULT = 0;
            v21 = 636;
          }
        }
        if ( LastError != 234 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT();
          v7 = 614;
          v23 = 1;
          goto LABEL_48;
        }
        v7 = 614;
      }
LABEL_46:
      LastFailureAsHRESULT = -2147024882;
    }
    else
    {
      LastFailureAsHRESULT = -2147024809;
    }
  }
LABEL_48:
  v22 = v7;
LABEL_49:
  CoTaskMemFree(v4);
  CoTaskMemFree(v5);
  RtlSetThreadErrorMode(OldMode, 0);
  v17 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v17;
}

```

## disassembly

```asm
0x1801ae104  mov     [rsp-38h+arg_0], rbx
0x1801ae109  push    rbp
0x1801ae10a  push    rsi
0x1801ae10b  push    rdi
0x1801ae10c  push    r12
0x1801ae10e  push    r13
0x1801ae110  push    r14
0x1801ae112  push    r15
0x1801ae114  mov     rbp, rsp
0x1801ae117  sub     rsp, 80h
0x1801ae11e  mov     rbx, rdx
0x1801ae121  mov     r12, rcx
0x1801ae124  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ae12b  lea     rax, WPP_GLOBAL_Control
0x1801ae132  cmp     rcx, rax
0x1801ae135  jz      short loc_1801AE149
0x1801ae137  test    dword ptr [rcx+1Ch], 20000000h
0x1801ae13e  jz      short loc_1801AE149
0x1801ae140  mov     rcx, [rcx+10h]
0x1801ae144  call    WPP_SF_
0x1801ae149  mov     r9d, 1; unsigned __int16
0x1801ae14f  lea     rdx, aSxgetvolumedes; "SxGetVolumeDescription"
0x1801ae156  mov     r8d, 23Ch; unsigned __int16
0x1801ae15c  lea     rcx, [rbp+var_38]; this
0x1801ae160  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801ae165  xor     r13d, r13d
0x1801ae168  mov     [rbp+cchReturnLength], r13d
0x1801ae16c  mov     r14d, r13d
0x1801ae16f  mov     [rbp+FileSystemFlags], r13d
0x1801ae173  mov     esi, r13d
0x1801ae176  mov     [rbp+MaximumComponentLength], r13d
0x1801ae17a  mov     [rbp+OldMode], r13d
0x1801ae17e  test    rbx, rbx
0x1801ae181  jz      short loc_1801AE18B
0x1801ae183  mov     rcx, rbx; this
0x1801ae186  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1801ae18b  lea     rdx, [rbp+OldMode]; OldMode
0x1801ae18f  mov     ecx, 10h; NewMode
0x1801ae194  call    cs:__imp_RtlSetThreadErrorMode
0x1801ae19b  nop     dword ptr [rax+rax+00h]
0x1801ae1a0  mov     ecx, eax
0x1801ae1a2  call    HRESULTFromNTSTATUS
0x1801ae1a7  mov     [rbp+var_38], eax
0x1801ae1aa  test    eax, eax
0x1801ae1ac  mov     eax, 24Ch
0x1801ae1b1  js      loc_1801AE488
0x1801ae1b7  mov     [rbp+var_34], ax
0x1801ae1bb  mov     eax, 24Eh
0x1801ae1c0  test    rbx, rbx
0x1801ae1c3  jz      loc_1801AE481
0x1801ae1c9  mov     edi, 20h ; ' '
0x1801ae1ce  mov     ecx, edi; unsigned int
0x1801ae1d0  mov     [rbp+var_34], ax
0x1801ae1d4  mov     [rbp+var_38], r13d
0x1801ae1d8  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1801ae1dd  mov     rcx, rsi; pv
0x1801ae1e0  mov     edi, eax
0x1801ae1e2  call    cs:__imp_CoTaskMemFree
0x1801ae1e9  nop     dword ptr [rax+rax+00h]
0x1801ae1ee  lea     eax, ds:2[rdi*2]
0x1801ae1f5  mov     ecx, eax; cb
0x1801ae1f7  mov     r15d, eax
0x1801ae1fa  call    cs:__imp_CoTaskMemAlloc
0x1801ae201  nop     dword ptr [rax+rax+00h]
0x1801ae206  mov     rsi, rax
0x1801ae209  test    rax, rax
0x1801ae20c  mov     eax, 257h
0x1801ae211  jz      loc_1801AE478
0x1801ae217  mov     r8d, r15d; Size
0x1801ae21a  mov     [rbp+var_38], r13d
0x1801ae21e  xor     edx, edx; Val
0x1801ae220  mov     [rbp+var_34], ax
0x1801ae224  mov     rcx, rsi; void *
0x1801ae227  call    memset_0
0x1801ae22c  mov     [rsp+80h+nFileSystemNameSize], r13d; nFileSystemNameSize
0x1801ae231  lea     rax, [rbp+FileSystemFlags]
0x1801ae235  mov     [rsp+80h+lpFileSystemNameBuffer], r13; lpFileSystemNameBuffer
0x1801ae23a  xor     r9d, r9d; lpVolumeSerialNumber
0x1801ae23d  mov     [rsp+80h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1801ae242  mov     r8d, edi; nVolumeNameSize
0x1801ae245  lea     rax, [rbp+MaximumComponentLength]
0x1801ae249  mov     rdx, rsi; lpVolumeNameBuffer
0x1801ae24c  mov     rcx, r12; lpRootPathName
0x1801ae24f  mov     [rsp+80h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x1801ae254  call    cs:__imp_GetVolumeInformationW
0x1801ae25b  nop     dword ptr [rax+rax+00h]
0x1801ae260  test    eax, eax
0x1801ae262  jnz     short loc_1801AE29F
0x1801ae264  call    cs:__imp_GetLastError
0x1801ae26b  nop     dword ptr [rax+rax+00h]
0x1801ae270  cmp     eax, 15h
0x1801ae273  jz      short loc_1801AE29F
0x1801ae275  cmp     eax, 0EAh
0x1801ae27a  jnz     short loc_1801AE286
0x1801ae27c  mov     eax, 266h
0x1801ae281  jmp     loc_1801AE1CE
0x1801ae286  call    GetLastFailureAsHRESULT
0x1801ae28b  mov     [rbp+var_38], eax
0x1801ae28e  mov     eax, 266h
0x1801ae293  mov     [rbp+var_30], 1
0x1801ae29a  jmp     loc_1801AE488
0x1801ae29f  mov     [rsi+rdi*2], r13w
0x1801ae2a4  cmp     [rsi], r13w
0x1801ae2a8  jz      short loc_1801AE2C9
0x1801ae2aa  mov     rdx, rsi; unsigned __int16 *
0x1801ae2ad  mov     rcx, rbx; this
0x1801ae2b0  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801ae2b5  mov     [rbp+var_38], eax
0x1801ae2b8  test    eax, eax
0x1801ae2ba  mov     eax, 26Ch
0x1801ae2bf  js      loc_1801AE488
0x1801ae2c5  mov     [rbp+var_34], ax
0x1801ae2c9  mov     ecx, 40h ; '@'; unsigned int
0x1801ae2ce  mov     r15d, 27Ch
0x1801ae2d4  mov     [rbp+cchReturnLength], ecx
0x1801ae2d7  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1801ae2dc  mov     rcx, r14; pv
0x1801ae2df  mov     edi, eax
0x1801ae2e1  call    cs:__imp_CoTaskMemFree
0x1801ae2e8  nop     dword ptr [rax+rax+00h]
0x1801ae2ed  mov     ecx, edi
0x1801ae2ef  add     rcx, rcx; cb
0x1801ae2f2  call    cs:__imp_CoTaskMemAlloc
0x1801ae2f9  nop     dword ptr [rax+rax+00h]
0x1801ae2fe  mov     r14, rax
0x1801ae301  test    rax, rax
0x1801ae304  mov     eax, 276h
0x1801ae309  jz      loc_1801AE478
0x1801ae30f  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x1801ae313  mov     [rbp+var_38], r13d
0x1801ae317  mov     r8d, edi; cchBufferLength
0x1801ae31a  mov     [rbp+var_34], ax
0x1801ae31e  mov     rdx, r14; lpszVolumePathNames
0x1801ae321  mov     rcx, r12; lpszVolumeName
0x1801ae324  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1801ae32b  nop     dword ptr [rax+rax+00h]
0x1801ae330  test    eax, eax
0x1801ae332  jnz     short loc_1801AE367
0x1801ae334  call    cs:__imp_GetLastError
0x1801ae33b  nop     dword ptr [rax+rax+00h]
0x1801ae340  cmp     eax, 0EAh
0x1801ae345  jnz     short loc_1801AE355
0x1801ae347  mov     ecx, [rbp+cchReturnLength]
0x1801ae34a  mov     [rbp+var_38], r13d
0x1801ae34e  mov     [rbp+var_34], r15w
0x1801ae353  jmp     short loc_1801AE2D7
0x1801ae355  call    GetLastFailureAsHRESULT
0x1801ae35a  mov     [rbp+var_38], eax
0x1801ae35d  mov     [rbp+var_32], r15w
0x1801ae362  jmp     loc_1801AE48C
0x1801ae367  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ae36b  inc     rax
0x1801ae36e  cmp     [r14+rax*2], r13w
0x1801ae373  jnz     short loc_1801AE36B
0x1801ae375  test    rax, rax
0x1801ae378  jz      loc_1801AE455
0x1801ae37e  cmp     [rsi], r13w
0x1801ae382  jz      short loc_1801AE3A7
0x1801ae384  lea     rdx, asc_1802E5A44; " "
0x1801ae38b  mov     rcx, rbx; this
0x1801ae38e  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801ae393  mov     [rbp+var_38], eax
0x1801ae396  test    eax, eax
0x1801ae398  mov     eax, 28Ch
0x1801ae39d  js      loc_1801AE488
0x1801ae3a3  mov     [rbp+var_34], ax
0x1801ae3a7  lea     rdx, asc_1802E5A40; "("
0x1801ae3ae  mov     rcx, rbx; this
0x1801ae3b1  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801ae3b6  mov     [rbp+var_38], eax
0x1801ae3b9  test    eax, eax
0x1801ae3bb  mov     eax, 28Eh
0x1801ae3c0  js      loc_1801AE488
0x1801ae3c6  mov     [rbp+var_34], ax
0x1801ae3ca  lea     r15d, [rax+6]
0x1801ae3ce  mov     rdi, r14
0x1801ae3d1  cmp     [rdi], r13w
0x1801ae3d5  jz      short loc_1801AE436
0x1801ae3d7  cmp     rdi, r14
0x1801ae3da  jz      short loc_1801AE3FB
0x1801ae3dc  lea     rdx, asc_1802CB328; ", "
0x1801ae3e3  mov     rcx, rbx; this
0x1801ae3e6  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801ae3eb  mov     [rbp+var_38], eax
0x1801ae3ee  test    eax, eax
0x1801ae3f0  js      loc_1801AE35D
0x1801ae3f6  mov     [rbp+var_34], r15w
0x1801ae3fb  mov     rdx, rdi; unsigned __int16 *
0x1801ae3fe  mov     rcx, rbx; this
0x1801ae401  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801ae406  mov     [rbp+var_38], eax
0x1801ae409  test    eax, eax
0x1801ae40b  mov     eax, 296h
0x1801ae410  js      short loc_1801AE488
0x1801ae412  mov     rcx, rbx; this
0x1801ae415  mov     [rbp+var_34], ax
0x1801ae419  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1801ae41e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ae422  inc     rax
0x1801ae425  cmp     [rdi+rax*2], r13w
0x1801ae42a  jnz     short loc_1801AE422
0x1801ae42c  lea     rdi, [rdi+rax*2]
0x1801ae430  add     rdi, 2
0x1801ae434  jmp     short loc_1801AE3D1
0x1801ae436  lea     rdx, asc_1802E5A3C; ")"
0x1801ae43d  mov     rcx, rbx; this
0x1801ae440  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801ae445  mov     [rbp+var_38], eax
0x1801ae448  test    eax, eax
0x1801ae44a  mov     eax, 299h
0x1801ae44f  js      short loc_1801AE488
0x1801ae451  mov     [rbp+var_34], ax
0x1801ae455  cmp     [rbx+8], r13d
0x1801ae459  jnz     short loc_1801AE48C
0x1801ae45b  mov     rdx, r12; unsigned __int16 *
0x1801ae45e  mov     rcx, rbx; this
0x1801ae461  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801ae466  mov     [rbp+var_38], eax
0x1801ae469  test    eax, eax
0x1801ae46b  mov     eax, 29Eh
0x1801ae470  js      short loc_1801AE488
0x1801ae472  mov     [rbp+var_34], ax
0x1801ae476  jmp     short loc_1801AE48C
0x1801ae478  mov     [rbp+var_38], 8007000Eh
0x1801ae47f  jmp     short loc_1801AE488
0x1801ae481  mov     [rbp+var_38], 80070057h
0x1801ae488  mov     [rbp+var_32], ax
0x1801ae48c  mov     rcx, r14; pv
0x1801ae48f  call    cs:__imp_CoTaskMemFree
0x1801ae496  nop     dword ptr [rax+rax+00h]
0x1801ae49b  mov     rcx, rsi; pv
0x1801ae49e  call    cs:__imp_CoTaskMemFree
0x1801ae4a5  nop     dword ptr [rax+rax+00h]
0x1801ae4aa  mov     ecx, [rbp+OldMode]; NewMode
0x1801ae4ad  xor     edx, edx; OldMode
0x1801ae4af  call    cs:__imp_RtlSetThreadErrorMode
0x1801ae4b6  nop     dword ptr [rax+rax+00h]
0x1801ae4bb  mov     ebx, [rbp+var_38]
0x1801ae4be  lea     rcx, [rbp+var_38]; this
0x1801ae4c2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801ae4c7  mov     eax, ebx
0x1801ae4c9  mov     rbx, [rsp+80h+arg_0]
0x1801ae4d1  add     rsp, 80h
0x1801ae4d8  pop     r15
0x1801ae4da  pop     r14
0x1801ae4dc  pop     r13
0x1801ae4de  pop     r12
0x1801ae4e0  pop     rdi
0x1801ae4e1  pop     rsi
0x1801ae4e2  pop     rbp
0x1801ae4e3  retn
```
