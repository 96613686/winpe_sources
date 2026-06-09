# PerfDiagShared::GetVersionInfo(ushort *,unsigned __int64,ushort *,unsigned __int64,ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18003169c`
- end: `0x18003191c`
- name: `?GetVersionInfo@PerfDiagShared@@YAJPEAG_K01PEBG0101@Z`
- size: `640`
- prototype: `__int64 __fastcall(PerfDiagShared *__hidden this, unsigned __int16 *, PerfDiagShared *, unsigned __int16 *, LPCWSTR lptstrFilename, PerfDiagShared *, unsigned __int16 *, PerfDiagShared *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c3e64`

## callees

- `0x18001933c`
- `0x18003169c`
- `0x180056c14`
- `0x1800ced4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031741`
- `VERSION!GetFileVersionInfoSizeW` at `0x1800316e1`
- `VERSION!GetFileVersionInfoSizeW` at `0x1800316e1`
- `VERSION!VerQueryValueW` at `0x180031772`
- `VERSION!VerQueryValueW` at `0x180031772`
- `VERSION!GetFileVersionInfoW` at `0x180031737`
- `VERSION!GetFileVersionInfoW` at `0x180031737`

## string_xrefs

- `0x1800318dd`: `CompanyName`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::GetVersionInfo(
        PerfDiagShared *this,
        unsigned __int16 *a2,
        PerfDiagShared *a3,
        unsigned __int16 *a4,
        LPCWSTR lptstrFilename,
        PerfDiagShared *a6,
        unsigned __int16 *a7,
        PerfDiagShared *a8,
        unsigned __int16 *a9)
{
  char v9; // r15
  DWORD FileVersionInfoSizeW; // eax
  DWORD v15; // edi
  signed int v16; // eax
  unsigned int v17; // ebx
  char v19; // al
  void *v20; // rbx
  unsigned int v21; // edi
  signed int LastError; // eax
  unsigned __int64 v23; // rcx
  __int64 v24; // rax
  PerfDiagShared *v25; // rsi
  PerfDiagShared *v26; // rsi
  const struct PerfDiagShared::tagLANGANDCODEPAGE *v27; // [rsp+28h] [rbp-20h]
  const struct PerfDiagShared::tagLANGANDCODEPAGE *v28; // [rsp+28h] [rbp-20h]
  unsigned int puLen; // [rsp+30h] [rbp-18h] BYREF
  DWORD dwHandle; // [rsp+34h] [rbp-14h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-10h] BYREF
  LPVOID lpData; // [rsp+90h] [rbp+48h] BYREF

  v9 = 0;
  if ( !this || !a2 )
    return 2147500035LL;
  lpData = 0;
  dwHandle = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, &dwHandle);
  v15 = FileVersionInfoSizeW;
  if ( FileVersionInfoSizeW )
  {
    v19 = ATL::CAutoVectorPtr<unsigned char>::Allocate(&lpData, FileVersionInfoSizeW);
    v20 = lpData;
    if ( v19 )
    {
      if ( GetFileVersionInfoW(lptstrFilename, 0, v15, lpData)
        && (lpBuffer = 0, puLen = 0, VerQueryValueW(v20, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen)) )
      {
        if ( puLen >= 4 )
        {
          v23 = (unsigned __int64)puLen >> 2;
          LODWORD(lpData) = *(_DWORD *)lpBuffer;
          v24 = 1;
          if ( v23 > 1 )
          {
            while ( *((_WORD *)lpBuffer + 2 * v24) != 1033 )
            {
              if ( ++v24 >= v23 )
                goto LABEL_21;
            }
            LODWORD(lpData) = *((_DWORD *)lpBuffer + v24);
          }
LABEL_21:
          v21 = 0;
          if ( PerfDiagShared::GetVersionInfoValue(
                 this,
                 a2,
                 (unsigned __int64)v20,
                 L"FileVersion",
                 (const unsigned __int16 *)&lpData,
                 v27) < 0 )
          {
            if ( PerfDiagShared::GetVersionInfoValue(
                   this,
                   a2,
                   (unsigned __int64)v20,
                   L"ProductVersion",
                   (const unsigned __int16 *)&lpData,
                   v28) >= 0 )
            {
              v9 = 1;
            }
            else
            {
              *(_WORD *)this = 0;
              v21 = 1;
            }
          }
          if ( a3
            && a4
            && (v9
             || PerfDiagShared::GetVersionInfoValue(
                  a3,
                  a4,
                  (unsigned __int64)v20,
                  L"FileDescription",
                  (const unsigned __int16 *)&lpData,
                  v28) < 0)
            && PerfDiagShared::GetVersionInfoValue(
                 a3,
                 a4,
                 (unsigned __int64)v20,
                 L"ProductName",
                 (const unsigned __int16 *)&lpData,
                 v28) < 0 )
          {
            *(_WORD *)a3 = 0;
            v21 = 1;
          }
          v25 = a6;
          if ( a6
            && a7
            && PerfDiagShared::GetVersionInfoValue(
                 a6,
                 a7,
                 (unsigned __int64)v20,
                 L"ProductName",
                 (const unsigned __int16 *)&lpData,
                 v28) < 0 )
          {
            *(_WORD *)v25 = 0;
            v21 = 1;
          }
          v26 = a8;
          if ( a8
            && a9
            && PerfDiagShared::GetVersionInfoValue(
                 a8,
                 a9,
                 (unsigned __int64)v20,
                 L"CompanyName",
                 (const unsigned __int16 *)&lpData,
                 v28) < 0 )
          {
            *(_WORD *)v26 = 0;
            v21 = 1;
          }
        }
        else
        {
          v21 = -2147024883;
        }
      }
      else
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v21 = -2147024882;
    }
    operator delete(v20);
    return v21;
  }
  else
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    operator delete(0);
    return v17;
  }
}

```

## disassembly

```asm
0x18003169c  push    rbp
0x18003169e  push    rbx
0x18003169f  push    rsi
0x1800316a0  push    rdi
0x1800316a1  push    r12
0x1800316a3  push    r13
0x1800316a5  push    r14
0x1800316a7  push    r15
0x1800316a9  mov     rbp, rsp
0x1800316ac  sub     rsp, 48h
0x1800316b0  xor     r15d, r15d
0x1800316b3  mov     r13, r9
0x1800316b6  mov     r14, r8
0x1800316b9  mov     r12, rdx
0x1800316bc  mov     rsi, rcx
0x1800316bf  test    rcx, rcx
0x1800316c2  jz      loc_180031906
0x1800316c8  test    rdx, rdx
0x1800316cb  jz      loc_180031906
0x1800316d1  mov     rcx, [rbp+lptstrFilename]; lptstrFilename
0x1800316d5  lea     rdx, [rbp+dwHandle]; lpdwHandle
0x1800316d9  mov     [rbp+lpData], r15
0x1800316dd  mov     [rbp+dwHandle], r15d
0x1800316e1  call    cs:__imp_GetFileVersionInfoSizeW
0x1800316e7  mov     edi, eax
0x1800316e9  test    eax, eax
0x1800316eb  jnz     short loc_180031710
0x1800316ed  call    cs:__imp_GetLastError
0x1800316f3  mov     ebx, eax
0x1800316f5  test    eax, eax
0x1800316f7  jle     short loc_180031702
0x1800316f9  movzx   ebx, ax
0x1800316fc  or      ebx, 80070000h
0x180031702  xor     ecx, ecx; Block
0x180031704  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031709  mov     eax, ebx
0x18003170b  jmp     loc_18003190B
0x180031710  mov     rdx, rdi
0x180031713  lea     rcx, [rbp+lpData]
0x180031717  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18003171c  mov     rbx, [rbp+lpData]
0x180031720  test    al, al
0x180031722  jnz     short loc_18003172B
0x180031724  mov     edi, 8007000Eh
0x180031729  jmp     short loc_180031787
0x18003172b  mov     rcx, [rbp+lptstrFilename]; lptstrFilename
0x18003172f  mov     r9, rbx; lpData
0x180031732  mov     r8d, edi; dwLen
0x180031735  xor     edx, edx; dwHandle
0x180031737  call    cs:__imp_GetFileVersionInfoW
0x18003173d  test    eax, eax
0x18003173f  jnz     short loc_180031758
0x180031741  call    cs:__imp_GetLastError
0x180031747  mov     edi, eax
0x180031749  test    eax, eax
0x18003174b  jle     short loc_180031787
0x18003174d  movzx   edi, ax
0x180031750  or      edi, 80070000h
0x180031756  jmp     short loc_180031787
0x180031758  lea     r9, [rbp+puLen]; puLen
0x18003175c  mov     [rbp+lpBuffer], r15
0x180031760  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180031764  mov     [rbp+puLen], r15d
0x180031768  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18003176f  mov     rcx, rbx; pBlock
0x180031772  call    cs:__imp_VerQueryValueW
0x180031778  test    eax, eax
0x18003177a  jz      short loc_180031741
0x18003177c  cmp     [rbp+puLen], 4
0x180031780  jnb     short loc_180031796
0x180031782  mov     edi, 8007000Dh
0x180031787  mov     rcx, rbx; Block
0x18003178a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003178f  mov     eax, edi
0x180031791  jmp     loc_18003190B
0x180031796  mov     rdx, [rbp+lpBuffer]
0x18003179a  mov     ecx, [rbp+puLen]
0x18003179d  shr     rcx, 2
0x1800317a1  mov     eax, [rdx]
0x1800317a3  mov     dword ptr [rbp+lpData], eax
0x1800317a6  mov     eax, 1
0x1800317ab  cmp     rcx, rax
0x1800317ae  jbe     short loc_1800317CD
0x1800317b0  mov     r8d, 409h
0x1800317b6  cmp     [rdx+rax*4], r8w
0x1800317bb  jz      short loc_1800317C7
0x1800317bd  inc     rax
0x1800317c0  cmp     rax, rcx
0x1800317c3  jb      short loc_1800317B0
0x1800317c5  jmp     short loc_1800317CD
0x1800317c7  mov     eax, [rdx+rax*4]
0x1800317ca  mov     dword ptr [rbp+lpData], eax
0x1800317cd  lea     rax, [rbp+lpData]
0x1800317d1  mov     r8, rbx; unsigned __int64
0x1800317d4  lea     r9, aFileversion; "FileVersion"
0x1800317db  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800317e0  mov     rdx, r12; unsigned __int16 *
0x1800317e3  mov     rcx, rsi; this
0x1800317e6  mov     edi, r15d
0x1800317e9  call    ?GetVersionInfoValue@PerfDiagShared@@YAJPEAG_KPEBXPEBGAEBUtagLANGANDCODEPAGE@1@@Z; PerfDiagShared::GetVersionInfoValue(ushort *,unsigned __int64,void const *,ushort const *,PerfDiagShared::tagLANGANDCODEPAGE const &)
0x1800317ee  test    eax, eax
0x1800317f0  jns     short loc_180031821
0x1800317f2  lea     rax, [rbp+lpData]
0x1800317f6  mov     r8, rbx; unsigned __int64
0x1800317f9  lea     r9, aProductversion; "ProductVersion"
0x180031800  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180031805  mov     rdx, r12; unsigned __int16 *
0x180031808  mov     rcx, rsi; this
0x18003180b  call    ?GetVersionInfoValue@PerfDiagShared@@YAJPEAG_KPEBXPEBGAEBUtagLANGANDCODEPAGE@1@@Z; PerfDiagShared::GetVersionInfoValue(ushort *,unsigned __int64,void const *,ushort const *,PerfDiagShared::tagLANGANDCODEPAGE const &)
0x180031810  test    eax, eax
0x180031812  jns     short loc_18003181E
0x180031814  xor     eax, eax
0x180031816  mov     [rsi], ax
0x180031819  lea     edi, [rax+1]
0x18003181c  jmp     short loc_180031821
0x18003181e  mov     r15b, 1
0x180031821  test    r14, r14
0x180031824  jz      short loc_18003187D
0x180031826  test    r13, r13
0x180031829  jz      short loc_18003187D
0x18003182b  test    r15b, r15b
0x18003182e  jnz     short loc_180031852
0x180031830  lea     rax, [rbp+lpData]
0x180031834  mov     r8, rbx; unsigned __int64
0x180031837  lea     r9, aFiledescriptio; "FileDescription"
0x18003183e  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180031843  mov     rdx, r13; unsigned __int16 *
0x180031846  mov     rcx, r14; this
0x180031849  call    ?GetVersionInfoValue@PerfDiagShared@@YAJPEAG_KPEBXPEBGAEBUtagLANGANDCODEPAGE@1@@Z; PerfDiagShared::GetVersionInfoValue(ushort *,unsigned __int64,void const *,ushort const *,PerfDiagShared::tagLANGANDCODEPAGE const &)
0x18003184e  test    eax, eax
0x180031850  jns     short loc_18003187D
0x180031852  lea     rax, [rbp+lpData]
0x180031856  mov     r8, rbx; unsigned __int64
0x180031859  lea     r9, aProductname; "ProductName"
0x180031860  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180031865  mov     rdx, r13; unsigned __int16 *
0x180031868  mov     rcx, r14; this
0x18003186b  call    ?GetVersionInfoValue@PerfDiagShared@@YAJPEAG_KPEBXPEBGAEBUtagLANGANDCODEPAGE@1@@Z; PerfDiagShared::GetVersionInfoValue(ushort *,unsigned __int64,void const *,ushort const *,PerfDiagShared::tagLANGANDCODEPAGE const &)
0x180031870  test    eax, eax
0x180031872  jns     short loc_18003187D
0x180031874  xor     eax, eax
0x180031876  mov     [r14], ax
0x18003187a  lea     edi, [rax+1]
0x18003187d  mov     rsi, [rbp+arg_28]
0x180031881  test    rsi, rsi
0x180031884  jz      short loc_1800318B6
0x180031886  mov     rdx, [rbp+arg_30]; unsigned __int16 *
0x18003188a  test    rdx, rdx
0x18003188d  jz      short loc_1800318B6
0x18003188f  lea     rax, [rbp+lpData]
0x180031893  mov     r8, rbx; unsigned __int64
0x180031896  lea     r9, aProductname; "ProductName"
0x18003189d  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800318a2  mov     rcx, rsi; this
0x1800318a5  call    ?GetVersionInfoValue@PerfDiagShared@@YAJPEAG_KPEBXPEBGAEBUtagLANGANDCODEPAGE@1@@Z; PerfDiagShared::GetVersionInfoValue(ushort *,unsigned __int64,void const *,ushort const *,PerfDiagShared::tagLANGANDCODEPAGE const &)
0x1800318aa  test    eax, eax
0x1800318ac  jns     short loc_1800318B6
0x1800318ae  xor     eax, eax
0x1800318b0  mov     [rsi], ax
0x1800318b3  lea     edi, [rax+1]
0x1800318b6  mov     rsi, [rbp+arg_38]
0x1800318bd  test    rsi, rsi
0x1800318c0  jz      loc_180031787
0x1800318c6  mov     rdx, [rbp+arg_40]; unsigned __int16 *
0x1800318cd  test    rdx, rdx
0x1800318d0  jz      loc_180031787
0x1800318d6  lea     rax, [rbp+lpData]
0x1800318da  mov     r8, rbx; unsigned __int64
0x1800318dd  lea     r9, aCompanyname; "CompanyName"
0x1800318e4  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800318e9  mov     rcx, rsi; this
0x1800318ec  call    ?GetVersionInfoValue@PerfDiagShared@@YAJPEAG_KPEBXPEBGAEBUtagLANGANDCODEPAGE@1@@Z; PerfDiagShared::GetVersionInfoValue(ushort *,unsigned __int64,void const *,ushort const *,PerfDiagShared::tagLANGANDCODEPAGE const &)
0x1800318f1  test    eax, eax
0x1800318f3  jns     loc_180031787
0x1800318f9  xor     eax, eax
0x1800318fb  mov     [rsi], ax
0x1800318fe  lea     edi, [rax+1]
0x180031901  jmp     loc_180031787
0x180031906  mov     eax, 80004003h
0x18003190b  add     rsp, 48h
0x18003190f  pop     r15
0x180031911  pop     r14
0x180031913  pop     r13
0x180031915  pop     r12
0x180031917  pop     rdi
0x180031918  pop     rsi
0x180031919  pop     rbx
0x18003191a  pop     rbp
0x18003191b  retn
```
