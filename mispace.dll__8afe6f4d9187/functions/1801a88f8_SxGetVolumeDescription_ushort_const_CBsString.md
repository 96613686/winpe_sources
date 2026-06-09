# SxGetVolumeDescription(ushort const *,CBsString *)

- ea: `0x1801a88f8`
- end: `0x1801a8c90`
- name: `?SxGetVolumeDescription@@YAJPEBGPEAVCBsString@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CBsString *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801312c0`

## callees

- `0x180006cf4`
- `0x1801a88f8`
- `0x1801a9414`
- `0x1801a9760`
- `0x1801a9974`
- `0x1801a9a04`
- `0x1801aae64`
- `0x1801aaf84`
- `0x1801ab1bc`
- `0x1801ab268`
- `0x1801ab4d0`
- `0x1801ab5c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a89d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a89d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a8c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a89e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a8ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a89e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a8ac2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801a8a36`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801a8a36`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a8aee`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1801a8aee`
- `ntdll!RtlSetThreadErrorMode` at `0x1801a8988`
- `ntdll!RtlSetThreadErrorMode` at `0x1801a8c61`
- `ntdll!RtlSetThreadErrorMode` at `0x1801a8988`
- `ntdll!RtlSetThreadErrorMode` at `0x1801a8c61`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetVolumeDescription", 572, 1);
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
0x1801a88f8  mov     [rsp-38h+arg_0], rbx
0x1801a88fd  push    rbp
0x1801a88fe  push    rsi
0x1801a88ff  push    rdi
0x1801a8900  push    r12
0x1801a8902  push    r13
0x1801a8904  push    r14
0x1801a8906  push    r15
0x1801a8908  mov     rbp, rsp
0x1801a890b  sub     rsp, 80h
0x1801a8912  mov     rbx, rdx
0x1801a8915  mov     r12, rcx
0x1801a8918  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a891f  lea     rax, WPP_GLOBAL_Control
0x1801a8926  cmp     rcx, rax
0x1801a8929  jz      short loc_1801A893D
0x1801a892b  test    dword ptr [rcx+1Ch], 20000000h
0x1801a8932  jz      short loc_1801A893D
0x1801a8934  mov     rcx, [rcx+10h]
0x1801a8938  call    WPP_SF_
0x1801a893d  mov     r9d, 1; unsigned __int16
0x1801a8943  lea     rdx, aSxgetvolumedes; "SxGetVolumeDescription"
0x1801a894a  mov     r8d, 23Ch; unsigned __int16
0x1801a8950  lea     rcx, [rbp+var_38]; this
0x1801a8954  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801a8959  xor     r13d, r13d
0x1801a895c  mov     [rbp+cchReturnLength], r13d
0x1801a8960  mov     r14d, r13d
0x1801a8963  mov     [rbp+FileSystemFlags], r13d
0x1801a8967  mov     esi, r13d
0x1801a896a  mov     [rbp+MaximumComponentLength], r13d
0x1801a896e  mov     [rbp+OldMode], r13d
0x1801a8972  test    rbx, rbx
0x1801a8975  jz      short loc_1801A897F
0x1801a8977  mov     rcx, rbx; this
0x1801a897a  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1801a897f  lea     rdx, [rbp+OldMode]; OldMode
0x1801a8983  mov     ecx, 10h; NewMode
0x1801a8988  call    cs:__imp_RtlSetThreadErrorMode
0x1801a898e  mov     ecx, eax
0x1801a8990  call    HRESULTFromNTSTATUS
0x1801a8995  mov     [rbp+var_38], eax
0x1801a8998  test    eax, eax
0x1801a899a  mov     eax, 24Ch
0x1801a899f  js      loc_1801A8C46
0x1801a89a5  mov     [rbp+var_34], ax
0x1801a89a9  mov     eax, 24Eh
0x1801a89ae  test    rbx, rbx
0x1801a89b1  jz      loc_1801A8C3F
0x1801a89b7  mov     edi, 20h ; ' '
0x1801a89bc  mov     ecx, edi; unsigned int
0x1801a89be  mov     [rbp+var_34], ax
0x1801a89c2  mov     [rbp+var_38], r13d
0x1801a89c6  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1801a89cb  mov     rcx, rsi; pv
0x1801a89ce  mov     edi, eax
0x1801a89d0  call    cs:__imp_CoTaskMemFree
0x1801a89d6  lea     eax, ds:2[rdi*2]
0x1801a89dd  mov     ecx, eax; cb
0x1801a89df  mov     r15d, eax
0x1801a89e2  call    cs:__imp_CoTaskMemAlloc
0x1801a89e8  mov     rsi, rax
0x1801a89eb  test    rax, rax
0x1801a89ee  mov     eax, 257h
0x1801a89f3  jz      loc_1801A8C36
0x1801a89f9  mov     r8d, r15d; Size
0x1801a89fc  mov     [rbp+var_38], r13d
0x1801a8a00  xor     edx, edx; Val
0x1801a8a02  mov     [rbp+var_34], ax
0x1801a8a06  mov     rcx, rsi; void *
0x1801a8a09  call    memset_0
0x1801a8a0e  mov     [rsp+80h+nFileSystemNameSize], r13d; nFileSystemNameSize
0x1801a8a13  lea     rax, [rbp+FileSystemFlags]
0x1801a8a17  mov     [rsp+80h+lpFileSystemNameBuffer], r13; lpFileSystemNameBuffer
0x1801a8a1c  xor     r9d, r9d; lpVolumeSerialNumber
0x1801a8a1f  mov     [rsp+80h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1801a8a24  mov     r8d, edi; nVolumeNameSize
0x1801a8a27  lea     rax, [rbp+MaximumComponentLength]
0x1801a8a2b  mov     rdx, rsi; lpVolumeNameBuffer
0x1801a8a2e  mov     rcx, r12; lpRootPathName
0x1801a8a31  mov     [rsp+80h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x1801a8a36  call    cs:__imp_GetVolumeInformationW
0x1801a8a3c  test    eax, eax
0x1801a8a3e  jnz     short loc_1801A8A75
0x1801a8a40  call    cs:__imp_GetLastError
0x1801a8a46  cmp     eax, 15h
0x1801a8a49  jz      short loc_1801A8A75
0x1801a8a4b  cmp     eax, 0EAh
0x1801a8a50  jnz     short loc_1801A8A5C
0x1801a8a52  mov     eax, 266h
0x1801a8a57  jmp     loc_1801A89BC
0x1801a8a5c  call    GetLastFailureAsHRESULT
0x1801a8a61  mov     [rbp+var_38], eax
0x1801a8a64  mov     eax, 266h
0x1801a8a69  mov     [rbp+var_30], 1
0x1801a8a70  jmp     loc_1801A8C46
0x1801a8a75  mov     [rsi+rdi*2], r13w
0x1801a8a7a  cmp     [rsi], r13w
0x1801a8a7e  jz      short loc_1801A8A9F
0x1801a8a80  mov     rdx, rsi; unsigned __int16 *
0x1801a8a83  mov     rcx, rbx; this
0x1801a8a86  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801a8a8b  mov     [rbp+var_38], eax
0x1801a8a8e  test    eax, eax
0x1801a8a90  mov     eax, 26Ch
0x1801a8a95  js      loc_1801A8C46
0x1801a8a9b  mov     [rbp+var_34], ax
0x1801a8a9f  mov     ecx, 40h ; '@'; unsigned int
0x1801a8aa4  mov     r15d, 27Ch
0x1801a8aaa  mov     [rbp+cchReturnLength], ecx
0x1801a8aad  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x1801a8ab2  mov     rcx, r14; pv
0x1801a8ab5  mov     edi, eax
0x1801a8ab7  call    cs:__imp_CoTaskMemFree
0x1801a8abd  mov     ecx, edi
0x1801a8abf  add     rcx, rcx; cb
0x1801a8ac2  call    cs:__imp_CoTaskMemAlloc
0x1801a8ac8  mov     r14, rax
0x1801a8acb  test    rax, rax
0x1801a8ace  mov     eax, 276h
0x1801a8ad3  jz      loc_1801A8C36
0x1801a8ad9  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x1801a8add  mov     [rbp+var_38], r13d
0x1801a8ae1  mov     r8d, edi; cchBufferLength
0x1801a8ae4  mov     [rbp+var_34], ax
0x1801a8ae8  mov     rdx, r14; lpszVolumePathNames
0x1801a8aeb  mov     rcx, r12; lpszVolumeName
0x1801a8aee  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1801a8af4  test    eax, eax
0x1801a8af6  jnz     short loc_1801A8B25
0x1801a8af8  call    cs:__imp_GetLastError
0x1801a8afe  cmp     eax, 0EAh
0x1801a8b03  jnz     short loc_1801A8B13
0x1801a8b05  mov     ecx, [rbp+cchReturnLength]
0x1801a8b08  mov     [rbp+var_38], r13d
0x1801a8b0c  mov     [rbp+var_34], r15w
0x1801a8b11  jmp     short loc_1801A8AAD
0x1801a8b13  call    GetLastFailureAsHRESULT
0x1801a8b18  mov     [rbp+var_38], eax
0x1801a8b1b  mov     [rbp+var_32], r15w
0x1801a8b20  jmp     loc_1801A8C4A
0x1801a8b25  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a8b29  inc     rax
0x1801a8b2c  cmp     [r14+rax*2], r13w
0x1801a8b31  jnz     short loc_1801A8B29
0x1801a8b33  test    rax, rax
0x1801a8b36  jz      loc_1801A8C13
0x1801a8b3c  cmp     [rsi], r13w
0x1801a8b40  jz      short loc_1801A8B65
0x1801a8b42  lea     rdx, asc_1802DE9F8; " "
0x1801a8b49  mov     rcx, rbx; this
0x1801a8b4c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801a8b51  mov     [rbp+var_38], eax
0x1801a8b54  test    eax, eax
0x1801a8b56  mov     eax, 28Ch
0x1801a8b5b  js      loc_1801A8C46
0x1801a8b61  mov     [rbp+var_34], ax
0x1801a8b65  lea     rdx, asc_1802DE9F4; "("
0x1801a8b6c  mov     rcx, rbx; this
0x1801a8b6f  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801a8b74  mov     [rbp+var_38], eax
0x1801a8b77  test    eax, eax
0x1801a8b79  mov     eax, 28Eh
0x1801a8b7e  js      loc_1801A8C46
0x1801a8b84  mov     [rbp+var_34], ax
0x1801a8b88  lea     r15d, [rax+6]
0x1801a8b8c  mov     rdi, r14
0x1801a8b8f  cmp     [rdi], r13w
0x1801a8b93  jz      short loc_1801A8BF4
0x1801a8b95  cmp     rdi, r14
0x1801a8b98  jz      short loc_1801A8BB9
0x1801a8b9a  lea     rdx, asc_1802C43D8; ", "
0x1801a8ba1  mov     rcx, rbx; this
0x1801a8ba4  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801a8ba9  mov     [rbp+var_38], eax
0x1801a8bac  test    eax, eax
0x1801a8bae  js      loc_1801A8B1B
0x1801a8bb4  mov     [rbp+var_34], r15w
0x1801a8bb9  mov     rdx, rdi; unsigned __int16 *
0x1801a8bbc  mov     rcx, rbx; this
0x1801a8bbf  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801a8bc4  mov     [rbp+var_38], eax
0x1801a8bc7  test    eax, eax
0x1801a8bc9  mov     eax, 296h
0x1801a8bce  js      short loc_1801A8C46
0x1801a8bd0  mov     rcx, rbx; this
0x1801a8bd3  mov     [rbp+var_34], ax
0x1801a8bd7  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1801a8bdc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a8be0  inc     rax
0x1801a8be3  cmp     [rdi+rax*2], r13w
0x1801a8be8  jnz     short loc_1801A8BE0
0x1801a8bea  lea     rdi, [rdi+rax*2]
0x1801a8bee  add     rdi, 2
0x1801a8bf2  jmp     short loc_1801A8B8F
0x1801a8bf4  lea     rdx, asc_1802DE9F0; ")"
0x1801a8bfb  mov     rcx, rbx; this
0x1801a8bfe  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1801a8c03  mov     [rbp+var_38], eax
0x1801a8c06  test    eax, eax
0x1801a8c08  mov     eax, 299h
0x1801a8c0d  js      short loc_1801A8C46
0x1801a8c0f  mov     [rbp+var_34], ax
0x1801a8c13  cmp     [rbx+8], r13d
0x1801a8c17  jnz     short loc_1801A8C4A
0x1801a8c19  mov     rdx, r12; unsigned __int16 *
0x1801a8c1c  mov     rcx, rbx; this
0x1801a8c1f  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801a8c24  mov     [rbp+var_38], eax
0x1801a8c27  test    eax, eax
0x1801a8c29  mov     eax, 29Eh
0x1801a8c2e  js      short loc_1801A8C46
0x1801a8c30  mov     [rbp+var_34], ax
0x1801a8c34  jmp     short loc_1801A8C4A
0x1801a8c36  mov     [rbp+var_38], 8007000Eh
0x1801a8c3d  jmp     short loc_1801A8C46
0x1801a8c3f  mov     [rbp+var_38], 80070057h
0x1801a8c46  mov     [rbp+var_32], ax
0x1801a8c4a  mov     rcx, r14; pv
0x1801a8c4d  call    cs:__imp_CoTaskMemFree
0x1801a8c53  mov     rcx, rsi; pv
0x1801a8c56  call    cs:__imp_CoTaskMemFree
0x1801a8c5c  mov     ecx, [rbp+OldMode]; NewMode
0x1801a8c5f  xor     edx, edx; OldMode
0x1801a8c61  call    cs:__imp_RtlSetThreadErrorMode
0x1801a8c67  mov     ebx, [rbp+var_38]
0x1801a8c6a  lea     rcx, [rbp+var_38]; this
0x1801a8c6e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801a8c73  mov     eax, ebx
0x1801a8c75  mov     rbx, [rsp+80h+arg_0]
0x1801a8c7d  add     rsp, 80h
0x1801a8c84  pop     r15
0x1801a8c86  pop     r14
0x1801a8c88  pop     r13
0x1801a8c8a  pop     r12
0x1801a8c8c  pop     rdi
0x1801a8c8d  pop     rsi
0x1801a8c8e  pop     rbp
0x1801a8c8f  retn
```
