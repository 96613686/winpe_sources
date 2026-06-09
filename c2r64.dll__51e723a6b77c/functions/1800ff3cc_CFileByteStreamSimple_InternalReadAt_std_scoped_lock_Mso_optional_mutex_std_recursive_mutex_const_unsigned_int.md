# CFileByteStreamSimple::InternalReadAt(std::scoped_lock<Mso::optional_mutex<std::recursive_mutex>> const &,unsigned __int64,uchar *,ulong,ulong *,CProgressCalc *)

- ea: `0x1800ff3cc`
- end: `0x1800ff72e`
- name: `?InternalReadAt@CFileByteStreamSimple@@IEAAJAEBV?$scoped_lock@U?$optional_mutex@Vrecursive_mutex@std@@@Mso@@@std@@_KPEAEKPEAKPEAVCProgressCalc@@@Z`
- size: `866`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800feaa0`
- `0x1800ff9c0`

## callees

- `0x18000adf0`
- `0x1800365dc`
- `0x18003e690`
- `0x1800fe78c`
- `0x1800ff3cc`
- `0x180103bf4`
- `0x180105534`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ff4ef`
- `KERNEL32!GetLastError` at `0x1800ff52d`
- `KERNEL32!GetLastError` at `0x1800ff4ef`
- `KERNEL32!GetLastError` at `0x1800ff52d`
- `KERNEL32!ReadFile` at `0x1800ff4d7`
- `KERNEL32!ReadFile` at `0x1800ff4d7`

## string_xrefs

- `0x1800ff639`: `cbRead`
- `0x1800ff60d`: `lastErrorFromReadFile`

## pseudocode

```c
__int64 __fastcall CFileByteStreamSimple::InternalReadAt(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        unsigned int a5,
        _DWORD *a6,
        CProgressHelper *a7)
{
  char *v7; // r12
  char *v8; // r14
  CProgressHelper *v10; // rcx
  unsigned int v11; // edi
  unsigned int v12; // ebx
  DWORD v13; // esi
  unsigned int *v14; // r9
  BOOL OverlappedResult; // r12d
  DWORD LastError; // eax
  signed int v17; // eax
  __int64 v18; // rcx
  const char *v20; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  char *v23; // [rsp+68h] [rbp-98h]
  struct _OVERLAPPED Overlapped; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v25[2]; // [rsp+90h] [rbp-70h] BYREF
  DWORD v26; // [rsp+A0h] [rbp-60h]
  __int16 v27; // [rsp+A4h] [rbp-5Ch]
  __int128 v28; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-48h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  _QWORD v31[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v32; // [rsp+D8h] [rbp-28h]
  __int16 v33; // [rsp+DCh] [rbp-24h]
  __int128 v34; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  _QWORD v37[2]; // [rsp+100h] [rbp+0h] BYREF
  int v38; // [rsp+110h] [rbp+10h]
  __int16 v39; // [rsp+114h] [rbp+14h]
  __int128 v40; // [rsp+118h] [rbp+18h] BYREF
  __int64 v41; // [rsp+128h] [rbp+28h]
  __int64 v42; // [rsp+130h] [rbp+30h]
  _QWORD v43[2]; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v44; // [rsp+148h] [rbp+48h]
  __int16 v45; // [rsp+14Ch] [rbp+4Ch]
  __int128 v46; // [rsp+150h] [rbp+50h] BYREF
  __int64 v47; // [rsp+160h] [rbp+60h]
  __int64 v48; // [rsp+168h] [rbp+68h]
  _QWORD v49[2]; // [rsp+170h] [rbp+70h] BYREF
  bool v50; // [rsp+180h] [rbp+80h]
  __int16 v51; // [rsp+182h] [rbp+82h]
  __int128 v52; // [rsp+188h] [rbp+88h] BYREF
  __int64 v53; // [rsp+198h] [rbp+98h]
  __int64 v54; // [rsp+1A0h] [rbp+A0h]

  v7 = a4;
  v23 = a4;
  v8 = (char *)a3;
  v10 = a7;
  v20 = (const char *)a7;
  NumberOfBytesRead = 0;
  v11 = a5;
  if ( !*(_DWORD *)(a1 + 52) || a5 < 0x40000 )
  {
    v13 = a5;
    if ( a5 >= 0x10000 )
      v13 = 0x10000;
    while ( 1 )
    {
      Overlapped.Internal = 0;
      Overlapped.InternalHigh = 0;
      Overlapped.Pointer = v8;
      Overlapped.hEvent = 0;
      v12 = CProgressHelper::HrContinue(v10);
      if ( (v12 & 0x80000000) != 0 )
        return v12;
      OverlappedResult = ReadFile(*(HANDLE *)(a1 + 40), v7, v13, &NumberOfBytesRead, &Overlapped);
      LastError = 0;
      LODWORD(v22) = 0;
      if ( !OverlappedResult )
      {
        LastError = GetLastError();
        LODWORD(v22) = LastError;
      }
      if ( !*(_DWORD *)(a1 + 52) )
        goto LABEL_13;
      if ( OverlappedResult )
        goto LABEL_17;
      if ( LastError == 997 )
        break;
LABEL_14:
      v17 = GetLastError();
      v12 = v17;
      if ( v17 > 0 )
        v12 = (unsigned __int16)v17 | 0x80070000;
      if ( v12 )
        return v12;
LABEL_17:
      v18 = NumberOfBytesRead;
      *a6 += NumberOfBytesRead;
      v8 += v18;
      v7 = &v23[v18];
      v23 += v18;
      v11 -= v18;
      if ( !v11 )
        return v12;
      if ( v13 != (_DWORD)v18 )
      {
        v49[0] = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
        v49[1] = "m_fOverlapped";
        v50 = *(_DWORD *)(a1 + 52) != 0;
        v51 = 4;
        v52 = 0;
        v53 = 0;
        v54 = 7;
        LOWORD(v52) = 0;
        v43[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v43[1] = "cbData";
        v44 = v11;
        v45 = 4;
        v46 = 0;
        v47 = 0;
        v48 = 7;
        LOWORD(v46) = 0;
        v37[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v37[1] = "lastErrorFromReadFile";
        v38 = v22;
        v39 = 4;
        v40 = 0;
        v41 = 0;
        v42 = 7;
        LOWORD(v40) = 0;
        v31[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v31[1] = "cbRead";
        v32 = v18;
        v33 = 4;
        v34 = 0;
        v35 = 0;
        v36 = 7;
        LOWORD(v34) = 0;
        v25[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
        v25[1] = "dwChunkSize";
        v26 = v13;
        v27 = 4;
        v28 = 0;
        v29 = 0;
        v30 = 7;
        LOWORD(v28) = 0;
        v20 = "Unexpected dwChunkSize";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<bool>>(
          v18,
          (unsigned int)&Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable',
          7,
          4,
          (__int64)&v20,
          (__int64)v25,
          (__int64)v31,
          (__int64)v37,
          (__int64)v43,
          (__int64)v49);
        std::wstring::~wstring(&v28);
        std::wstring::~wstring(&v34);
        std::wstring::~wstring(&v40);
        std::wstring::~wstring(&v46);
        std::wstring::~wstring(&v52);
        return (unsigned int)-2147418113;
      }
      v13 = 0x10000;
      if ( v11 < 0x10000 )
        v13 = v11;
      v10 = (CProgressHelper *)v20;
    }
    OverlappedResult = Mso::StreamPlatform::Details::TryGetOverlappedResult(
                         *(Mso::StreamPlatform::Details **)(a1 + 40),
                         &Overlapped,
                         (struct _OVERLAPPED *)&NumberOfBytesRead,
                         v14);
LABEL_13:
    if ( OverlappedResult )
      goto LABEL_17;
    goto LABEL_14;
  }
  _mm_lfence();
  v22 = 0;
  Overlapped.Internal = (ULONG_PTR)&Mso::StreamPlatform::Details::CIOReadDispatcher::`vftable';
  Overlapped.Pointer = a4;
  Overlapped.InternalHigh = 0;
  Overlapped.hEvent = a7;
  v12 = sub_1800365DC(*(HANDLE *)(a1 + 40), a3, a5, &v22, (__int64 *)&Overlapped);
  *a6 += v22;
  return v12;
}

```

## disassembly

```asm
0x1800ff3cc  mov     [rsp-8+arg_8], rbx
0x1800ff3d1  push    rbp
0x1800ff3d2  push    rsi
0x1800ff3d3  push    rdi
0x1800ff3d4  push    r12
0x1800ff3d6  push    r13
0x1800ff3d8  push    r14
0x1800ff3da  push    r15
0x1800ff3dc  lea     rbp, [rsp-0B0h]
0x1800ff3e4  sub     rsp, 1B0h
0x1800ff3eb  mov     rax, cs:__security_cookie
0x1800ff3f2  xor     rax, rsp
0x1800ff3f5  mov     [rbp+0E0h+var_38], rax
0x1800ff3fc  mov     r12, r9
0x1800ff3ff  mov     [rsp+1E0h+var_178], r9
0x1800ff404  mov     r14, r8
0x1800ff407  mov     r15, rcx
0x1800ff40a  mov     r13, [rbp+0E0h+arg_28]
0x1800ff411  mov     rcx, [rbp+0E0h+arg_30]; this
0x1800ff418  mov     [rsp+1E0h+var_190], rcx
0x1800ff41d  xor     r10d, r10d
0x1800ff420  mov     [rsp+1E0h+NumberOfBytesRead], r10d
0x1800ff425  mov     edi, [rbp+0E0h+arg_20]
0x1800ff42b  cmp     [r15+34h], r10d
0x1800ff42f  jz      short loc_1800FF487
0x1800ff431  cmp     edi, 40000h
0x1800ff437  jb      short loc_1800FF487
0x1800ff439  lfence
0x1800ff43c  mov     [rsp+1E0h+var_180], r10
0x1800ff441  lea     rax, ??_7CIOReadDispatcher@Details@StreamPlatform@Mso@@6B@; const Mso::StreamPlatform::Details::CIOReadDispatcher::`vftable'
0x1800ff448  mov     [rsp+1E0h+Overlapped.Internal], rax
0x1800ff44d  mov     qword ptr [rbp+0E0h+Overlapped.10h], r9
0x1800ff451  mov     [rsp+1E0h+Overlapped.InternalHigh], r10
0x1800ff456  mov     [rbp+0E0h+Overlapped.hEvent], rcx
0x1800ff45a  mov     r8d, edi
0x1800ff45d  lea     rax, [rsp+1E0h+Overlapped]
0x1800ff462  mov     [rsp+1E0h+lpOverlapped], rax; __int64
0x1800ff467  lea     r9, [rsp+1E0h+var_180]
0x1800ff46c  mov     rdx, r14
0x1800ff46f  mov     rcx, [r15+28h]; hFile
0x1800ff473  call    sub_1800365DC
0x1800ff478  mov     ebx, eax
0x1800ff47a  mov     ecx, dword ptr [rsp+1E0h+var_180]
0x1800ff47e  add     [r13+0], ecx
0x1800ff482  jmp     loc_1800FF702
0x1800ff487  mov     esi, edi
0x1800ff489  mov     eax, 10000h
0x1800ff48e  cmp     edi, eax
0x1800ff490  cmovnb  esi, eax
0x1800ff493  mov     [rsp+1E0h+Overlapped.Internal], r10
0x1800ff498  mov     [rsp+1E0h+Overlapped.InternalHigh], r10
0x1800ff49d  mov     dword ptr [rbp+0E0h+Overlapped.10h], r14d
0x1800ff4a1  mov     rax, r14
0x1800ff4a4  shr     rax, 20h
0x1800ff4a8  mov     dword ptr [rbp+0E0h+Overlapped.10h+4], eax
0x1800ff4ab  mov     [rbp+0E0h+Overlapped.hEvent], r10
0x1800ff4af  call    ?HrContinue@CProgressHelper@@QEAAJXZ; CProgressHelper::HrContinue(void)
0x1800ff4b4  mov     ebx, eax
0x1800ff4b6  test    eax, eax
0x1800ff4b8  js      loc_1800FF702
0x1800ff4be  lea     rax, [rsp+1E0h+Overlapped]
0x1800ff4c3  mov     [rsp+1E0h+lpOverlapped], rax; lpOverlapped
0x1800ff4c8  lea     r9, [rsp+1E0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800ff4cd  mov     r8d, esi; nNumberOfBytesToRead
0x1800ff4d0  mov     rdx, r12; lpBuffer
0x1800ff4d3  mov     rcx, [r15+28h]; hFile
0x1800ff4d7  call    cs:__imp_ReadFile
0x1800ff4dd  mov     r12d, eax
0x1800ff4e0  xor     r10d, r10d
0x1800ff4e3  mov     eax, r10d
0x1800ff4e6  mov     dword ptr [rsp+1E0h+var_180], eax
0x1800ff4ea  test    r12d, r12d
0x1800ff4ed  jnz     short loc_1800FF4FC
0x1800ff4ef  call    cs:__imp_GetLastError
0x1800ff4f5  mov     dword ptr [rsp+1E0h+var_180], eax
0x1800ff4f9  xor     r10d, r10d
0x1800ff4fc  cmp     [r15+34h], r10d
0x1800ff500  jz      short loc_1800FF528
0x1800ff502  test    r12d, r12d
0x1800ff505  jnz     short loc_1800FF54D
0x1800ff507  cmp     eax, 3E5h
0x1800ff50c  jnz     short loc_1800FF52D
0x1800ff50e  lea     r8, [rsp+1E0h+NumberOfBytesRead]; struct _OVERLAPPED *
0x1800ff513  lea     rdx, [rsp+1E0h+Overlapped]; void *
0x1800ff518  mov     rcx, [r15+28h]; this
0x1800ff51c  call    ?TryGetOverlappedResult@Details@StreamPlatform@Mso@@YA_NPEAXAEAU_OVERLAPPED@@AEAK@Z; Mso::StreamPlatform::Details::TryGetOverlappedResult(void *,_OVERLAPPED &,ulong &)
0x1800ff521  movzx   r12d, al
0x1800ff525  xor     r10d, r10d
0x1800ff528  test    r12d, r12d
0x1800ff52b  jnz     short loc_1800FF54D
0x1800ff52d  call    cs:__imp_GetLastError
0x1800ff533  mov     ebx, eax
0x1800ff535  xor     r10d, r10d
0x1800ff538  test    eax, eax
0x1800ff53a  jle     short loc_1800FF545
0x1800ff53c  movzx   ebx, ax
0x1800ff53f  or      ebx, 80070000h
0x1800ff545  test    ebx, ebx
0x1800ff547  jnz     loc_1800FF702
0x1800ff54d  mov     ecx, [rsp+1E0h+NumberOfBytesRead]
0x1800ff551  add     [r13+0], ecx
0x1800ff555  add     r14, rcx
0x1800ff558  mov     r12, [rsp+1E0h+var_178]
0x1800ff55d  add     r12, rcx
0x1800ff560  mov     [rsp+1E0h+var_178], r12
0x1800ff565  sub     edi, ecx
0x1800ff567  jz      loc_1800FF702
0x1800ff56d  cmp     esi, ecx
0x1800ff56f  jnz     short loc_1800FF587
0x1800ff571  mov     eax, 10000h
0x1800ff576  mov     esi, eax
0x1800ff578  cmp     edi, eax
0x1800ff57a  cmovb   esi, edi
0x1800ff57d  mov     rcx, [rsp+1E0h+var_190]
0x1800ff582  jmp     loc_1800FF493
0x1800ff587  lea     rax, ??_7?$ClassifiedStructuredObject@_N@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable'
0x1800ff58e  mov     [rbp+0E0h+var_70], rax
0x1800ff592  lea     rax, aMFoverlapped; "m_fOverlapped"
0x1800ff599  mov     [rbp+0E0h+var_68], rax
0x1800ff59d  cmp     [r15+34h], r10d
0x1800ff5a1  setnz   [rbp+0E0h+var_60]
0x1800ff5a8  mov     r9d, 4
0x1800ff5ae  mov     [rbp+0E0h+var_5E], r9w
0x1800ff5b6  xorps   xmm0, xmm0
0x1800ff5b9  movups  [rbp+0E0h+var_58], xmm0
0x1800ff5c0  mov     [rbp+0E0h+var_48], r10
0x1800ff5c7  lea     r8d, [r9+3]
0x1800ff5cb  mov     [rbp+0E0h+var_40], r8
0x1800ff5d2  mov     word ptr [rbp+0E0h+var_58], r10w
0x1800ff5da  lea     rdx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800ff5e1  mov     [rbp+0E0h+var_A8], rdx
0x1800ff5e5  lea     rax, aCbdata; "cbData"
0x1800ff5ec  mov     [rbp+0E0h+var_A0], rax
0x1800ff5f0  mov     [rbp+0E0h+var_98], edi
0x1800ff5f3  mov     [rbp+0E0h+var_94], r9w
0x1800ff5f8  movups  [rbp+0E0h+var_90], xmm0
0x1800ff5fc  mov     [rbp+0E0h+var_80], r10
0x1800ff600  mov     [rbp+0E0h+var_78], r8
0x1800ff604  mov     word ptr [rbp+0E0h+var_90], r10w
0x1800ff609  mov     [rbp+0E0h+var_E0], rdx
0x1800ff60d  lea     rax, aLasterrorfromr; "lastErrorFromReadFile"
0x1800ff614  mov     [rbp+0E0h+var_D8], rax
0x1800ff618  mov     eax, dword ptr [rsp+1E0h+var_180]
0x1800ff61c  mov     [rbp+0E0h+var_D0], eax
0x1800ff61f  mov     [rbp+0E0h+var_CC], r9w
0x1800ff624  movups  [rbp+0E0h+var_C8], xmm0
0x1800ff628  mov     [rbp+0E0h+var_B8], r10
0x1800ff62c  mov     [rbp+0E0h+var_B0], r8
0x1800ff630  mov     word ptr [rbp+0E0h+var_C8], r10w
0x1800ff635  mov     [rbp+0E0h+var_118], rdx
0x1800ff639  lea     rax, aCbread; "cbRead"
0x1800ff640  mov     [rbp+0E0h+var_110], rax
0x1800ff644  mov     [rbp+0E0h+var_108], ecx
0x1800ff647  mov     [rbp+0E0h+var_104], r9w
0x1800ff64c  movups  [rbp+0E0h+var_100], xmm0
0x1800ff650  mov     [rbp+0E0h+var_F0], r10
0x1800ff654  mov     [rbp+0E0h+var_E8], r8
0x1800ff658  mov     word ptr [rbp+0E0h+var_100], r10w
0x1800ff65d  mov     [rbp+0E0h+var_150], rdx
0x1800ff661  lea     rax, aDwchunksize; "dwChunkSize"
0x1800ff668  mov     [rbp+0E0h+var_148], rax
0x1800ff66c  mov     [rbp+0E0h+var_140], esi
0x1800ff66f  mov     [rbp+0E0h+var_13C], r9w
0x1800ff674  movups  [rbp+0E0h+var_138], xmm0
0x1800ff678  mov     [rbp+0E0h+var_128], r10
0x1800ff67c  mov     [rbp+0E0h+var_120], r8
0x1800ff680  mov     word ptr [rbp+0E0h+var_138], r10w
0x1800ff685  lea     rax, aUnexpectedDwch; "Unexpected dwChunkSize"
0x1800ff68c  mov     [rsp+1E0h+var_190], rax
0x1800ff691  lea     rax, [rbp+0E0h+var_70]
0x1800ff695  mov     [rsp+1E0h+var_198], rax
0x1800ff69a  lea     rax, [rbp+0E0h+var_A8]
0x1800ff69e  mov     [rsp+1E0h+var_1A0], rax
0x1800ff6a3  lea     rax, [rbp+0E0h+var_E0]
0x1800ff6a7  mov     [rsp+1E0h+var_1A8], rax
0x1800ff6ac  lea     rax, [rbp+0E0h+var_118]
0x1800ff6b0  mov     [rsp+1E0h+var_1B0], rax
0x1800ff6b5  lea     rax, [rbp+0E0h+var_150]
0x1800ff6b9  mov     [rsp+1E0h+var_1B8], rax
0x1800ff6be  lea     rax, [rsp+1E0h+var_190]
0x1800ff6c3  mov     [rsp+1E0h+lpOverlapped], rax
0x1800ff6c8  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U123@U123@U123@U?$ClassifiedStructuredObject@_N@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@444$$QEAU?$ClassifiedStructuredObject@_N@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<bool>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<bool> &&)
0x1800ff6cd  lea     rcx, [rbp+0E0h+var_138]; void *
0x1800ff6d1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ff6d6  lea     rcx, [rbp+0E0h+var_100]; void *
0x1800ff6da  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ff6df  lea     rcx, [rbp+0E0h+var_C8]; void *
0x1800ff6e3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ff6e8  lea     rcx, [rbp+0E0h+var_90]; void *
0x1800ff6ec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ff6f1  lea     rcx, [rbp+0E0h+var_58]; void *
0x1800ff6f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ff6fd  mov     ebx, 8000FFFFh
0x1800ff702  mov     eax, ebx
0x1800ff704  mov     rcx, [rbp+0E0h+var_38]
0x1800ff70b  xor     rcx, rsp; StackCookie
0x1800ff70e  call    __security_check_cookie
0x1800ff713  mov     rbx, [rsp+1E0h+arg_8]
0x1800ff71b  add     rsp, 1B0h
0x1800ff722  pop     r15
0x1800ff724  pop     r14
0x1800ff726  pop     r13
0x1800ff728  pop     r12
0x1800ff72a  pop     rdi
0x1800ff72b  pop     rsi
0x1800ff72c  pop     rbp
0x1800ff72d  retn
```
