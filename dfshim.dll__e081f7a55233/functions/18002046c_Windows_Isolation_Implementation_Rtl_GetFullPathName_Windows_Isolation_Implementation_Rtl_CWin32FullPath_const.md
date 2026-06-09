# Windows::Isolation::Implementation::Rtl::GetFullPathName(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,_LUNICODE_STRING &)

- ea: `0x18002046c`
- end: `0x1800207f4`
- name: `?GetFullPathName@Rtl@Implementation@Isolation@Windows@@YAJAEBVCWin32FullPath@1234@AEAU_LUNICODE_STRING@@@Z`
- size: `904`
- prototype: `__int64 __fastcall(Windows::Isolation::Implementation::Rtl *__hidden this, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800d8c4c`

## callees

- `0x1800069e5`
- `0x180006a81`
- `0x180006a8d`
- `0x180013e50`
- `0x180018b30`
- `0x18002046c`
- `0x18003f260`
- `0x180049e7c`
- `0x1800567b4`
- `0x1800b97c0`
- `0x1800fe440`

## import_xrefs

- `api-ms-win-core-file-l1-2-2!AreFileApisANSI` at `0x18002060c`
- `api-ms-win-core-file-l1-2-2!AreFileApisANSI` at `0x18002060c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800206d3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002075a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800206d3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002075a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180020521`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800205d5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180020521`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800205d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002050b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800205bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800206be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020745`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002050b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800205bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800206be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020745`

## string_xrefs

- `0x18002053c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::GetFullPathName(
        Windows::Isolation::Implementation::Rtl *this,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a2,
        struct _LUNICODE_STRING *a3)
{
  bool v5; // zf
  int v6; // ebx
  void *v7; // rcx
  unsigned __int64 v8; // rbx
  char *v9; // r14
  CHAR *v10; // rdi
  DWORD FullPathNameA; // eax
  __int64 v12; // r8
  DWORD v13; // ecx
  DWORD LastError_0; // eax
  int v15; // r9d
  unsigned __int64 v16; // r13
  UINT ACP_0; // eax
  unsigned int v18; // edx
  unsigned __int64 v19; // rbx
  char *v20; // r14
  WCHAR *v21; // rdi
  DWORD FullPathNameW; // ecx
  unsigned __int64 v23; // rax
  __int64 v24; // rbx
  LPWSTR v25; // xmm1_8
  __int128 v27; // [rsp+20h] [rbp-30h] BYREF
  LPWSTR v28; // [rsp+30h] [rbp-20h]
  __int64 v29; // [rsp+38h] [rbp-18h] BYREF
  DWORD nBufferLength[2]; // [rsp+40h] [rbp-10h]
  LPSTR lpBuffer; // [rsp+48h] [rbp-8h]
  unsigned __int64 v32; // [rsp+90h] [rbp+40h] BYREF
  __int64 v33; // [rsp+98h] [rbp+48h] BYREF

  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  v5 = *((_DWORD *)this + 14) == 1;
  v27 = 0u;
  v28 = 0;
  if ( v5 )
  {
    *(_QWORD *)nBufferLength = 0;
    v29 = 0;
    lpBuffer = 0;
    v6 = RtlAllocateLBlob(260, &v29, a3);
    if ( v6 < 0 )
    {
LABEL_3:
      v7 = lpBuffer;
      goto LABEL_53;
    }
    v8 = *(_QWORD *)nBufferLength;
    if ( *(_QWORD *)nBufferLength <= 0xFFFFFFFF )
    {
      v9 = (char *)this + 48;
      v10 = lpBuffer;
      if ( *((_DWORD *)this + 14) != 1 || !*(_QWORD *)v9 )
        RaiseException(0xC00000E5, 1u, 0, 0);
      FullPathNameA = GetFullPathNameA(*(LPCSTR *)(*(_QWORD *)v9 + 16LL), v8 - 1, v10, 0);
      v13 = FullPathNameA;
      if ( !FullPathNameA )
      {
        LastError_0 = GetLastError_0();
        v6 = isowin32_ConvertWin32ErrorToNtStatus(LastError_0);
        Windows::ErrorHandling::COM::ReportNtErrorOrigination(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
          (const char *)0x4F,
          v6,
          v15);
LABEL_10:
        if ( !v10 )
          return (unsigned int)v6;
        v7 = v10;
LABEL_54:
        IsolationFreeStringRoutine(v7);
        return (unsigned int)v6;
      }
      v16 = FullPathNameA + 1;
      if ( v16 < v8 )
        goto LABEL_21;
      if ( v10 )
      {
        *(_QWORD *)nBufferLength = 0;
        v29 = 0;
        lpBuffer = 0;
        IsolationFreeStringRoutine(v10);
      }
      v6 = RtlAllocateLBlob(v16, &v29, v12);
      if ( v6 < 0 )
        goto LABEL_3;
      if ( *(_QWORD *)nBufferLength <= 0xFFFFFFFF )
      {
        v10 = lpBuffer;
        if ( *((_DWORD *)this + 14) != 1 || !*(_QWORD *)v9 )
          RaiseException(0xC00000E5, 1u, 0, 0);
        v13 = GetFullPathNameA(*(LPCSTR *)(*(_QWORD *)v9 + 16LL), nBufferLength[0], v10, 0);
LABEL_21:
        v33 = 0;
        v6 = *(_DWORD *)BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(
                          &v32,
                          v13,
                          1,
                          &v33);
        if ( v6 < 0 )
          goto LABEL_10;
        v29 = v33;
        if ( AreFileApisANSI() )
          ACP_0 = GetACP_0();
        else
          ACP_0 = GetOEMCP_0();
        v6 = isowin32_MultiByteToWideChar(ACP_0, v18, (const struct _LBLOB *)&v29, (struct _LUNICODE_STRING *)&v27);
        if ( v6 < 0 )
        {
          if ( v10 )
            IsolationFreeStringRoutine(v10);
          goto LABEL_29;
        }
        if ( v10 )
          IsolationFreeStringRoutine(v10);
LABEL_51:
        v6 = 0;
        v25 = v28;
        *(_OWORD *)a2 = v27;
        *((_QWORD *)a2 + 2) = v25;
        return (unsigned int)v6;
      }
    }
    v6 = -1073741675;
    goto LABEL_3;
  }
  v6 = RtlAllocateLUnicodeString(520, &v27);
  if ( v6 >= 0 )
  {
    v19 = *((_QWORD *)&v27 + 1) >> 1;
    if ( *((_QWORD *)&v27 + 1) >> 1 > 0xFFFFFFFF )
    {
      v7 = v28;
      v6 = -1073741675;
      if ( !v28 )
        return (unsigned int)v6;
      goto LABEL_53;
    }
    v20 = (char *)this + 48;
    v21 = v28;
    if ( *((_DWORD *)this + 14) != 2 || !*(_QWORD *)v20 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    FullPathNameW = GetFullPathNameW(*(LPCWSTR *)(*(_QWORD *)v20 + 16LL), v19, v21, 0);
    v23 = FullPathNameW + 1;
    v32 = v23;
    if ( v23 < v19 )
      goto LABEL_46;
    if ( v21 )
    {
      v27 = 0u;
      v28 = 0;
      IsolationFreeStringRoutine(v21);
      v23 = v32;
    }
    v6 = RtlAllocateLUnicodeString(2 * v23, &v27);
    if ( v6 < 0 )
      goto LABEL_29;
    v24 = *((_QWORD *)&v27 + 1) >> 1;
    if ( *((_QWORD *)&v27 + 1) >> 1 <= 0xFFFFFFFF )
    {
      v21 = v28;
      if ( *((_DWORD *)this + 14) != 2 || !*(_QWORD *)v20 )
        RaiseException(0xC00000E5, 1u, 0, 0);
      FullPathNameW = GetFullPathNameW(*(LPCWSTR *)(*(_QWORD *)v20 + 16LL), v24, v21, 0);
LABEL_46:
      v33 = 0;
      v6 = *(_DWORD *)BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(
                        &v32,
                        FullPathNameW,
                        2,
                        &v33);
      if ( v6 < 0 )
      {
        if ( !v21 )
          return (unsigned int)v6;
        v7 = v21;
        goto LABEL_54;
      }
      *(_QWORD *)&v27 = v33;
      goto LABEL_51;
    }
    v6 = -1073741675;
  }
LABEL_29:
  v7 = v28;
LABEL_53:
  if ( v7 )
    goto LABEL_54;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002046c  mov     [rsp-38h+arg_10], rbx
0x180020471  push    rbp
0x180020472  push    rsi
0x180020473  push    rdi
0x180020474  push    r12
0x180020476  push    r13
0x180020478  push    r14
0x18002047a  push    r15
0x18002047c  mov     rbp, rsp
0x18002047f  sub     rsp, 50h
0x180020483  xor     r13d, r13d
0x180020486  mov     r12, rdx
0x180020489  mov     [rdx], r13
0x18002048c  mov     rsi, rcx
0x18002048f  mov     [rdx+8], r13
0x180020493  mov     [rdx+10h], r13
0x180020497  cmp     dword ptr [rcx+38h], 1
0x18002049b  mov     qword ptr [rbp+var_30+8], r13
0x18002049f  mov     qword ptr [rbp+var_30], r13
0x1800204a3  mov     [rbp+var_20], r13
0x1800204a7  jnz     loc_18002066D
0x1800204ad  lea     rdx, [rbp+var_18]
0x1800204b1  mov     qword ptr [rbp+nBufferLength], r13
0x1800204b5  mov     ecx, 104h
0x1800204ba  mov     [rbp+var_18], r13
0x1800204be  mov     [rbp+lpBuffer], r13
0x1800204c2  call    RtlAllocateLBlob
0x1800204c7  mov     ebx, eax
0x1800204c9  test    eax, eax
0x1800204cb  jns     short loc_1800204D6
0x1800204cd  mov     rcx, [rbp+lpBuffer]
0x1800204d1  jmp     loc_1800207D0
0x1800204d6  mov     rbx, qword ptr [rbp+nBufferLength]
0x1800204da  mov     r15d, 0FFFFFFFFh
0x1800204e0  cmp     rbx, r15
0x1800204e3  ja      loc_18002061D
0x1800204e9  cmp     dword ptr [rsi+38h], 1
0x1800204ed  lea     r14, [rsi+30h]
0x1800204f1  mov     rdi, [rbp+lpBuffer]
0x1800204f5  jnz     short loc_1800204FC
0x1800204f7  cmp     [r14], r13
0x1800204fa  jnz     short loc_180020511
0x1800204fc  xor     r9d, r9d; lpArguments
0x1800204ff  xor     r8d, r8d; nNumberOfArguments
0x180020502  mov     ecx, 0C00000E5h; dwExceptionCode
0x180020507  lea     edx, [r9+1]; dwExceptionFlags
0x18002050b  call    cs:__imp_RaiseException
0x180020511  mov     rcx, [r14]
0x180020514  lea     edx, [rbx-1]; nBufferLength
0x180020517  xor     r9d, r9d; lpFilePart
0x18002051a  mov     r8, rdi; lpBuffer
0x18002051d  mov     rcx, [rcx+10h]; lpFileName
0x180020521  call    cs:__imp_GetFullPathNameA
0x180020527  mov     ecx, eax
0x180020529  test    eax, eax
0x18002052b  jnz     short loc_180020560
0x18002052d  call    GetLastError_0
0x180020532  mov     ecx, eax; unsigned int
0x180020534  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180020539  mov     r8d, eax; int
0x18002053c  lea     rcx, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180020543  mov     edx, 4Fh ; 'O'; char *
0x180020548  mov     ebx, eax
0x18002054a  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x18002054f  test    rdi, rdi
0x180020552  jz      loc_1800207DA
0x180020558  mov     rcx, rdi
0x18002055b  jmp     loc_1800207D5
0x180020560  lea     r13d, [rax+1]
0x180020564  cmp     r13, rbx
0x180020567  jb      short loc_1800205DD
0x180020569  xor     eax, eax
0x18002056b  test    rdi, rdi
0x18002056e  jz      short loc_180020584
0x180020570  mov     rcx, rdi; lpMem
0x180020573  mov     qword ptr [rbp+nBufferLength], rax
0x180020577  mov     [rbp+var_18], rax
0x18002057b  mov     [rbp+lpBuffer], rax
0x18002057f  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020584  lea     rdx, [rbp+var_18]
0x180020588  mov     rcx, r13
0x18002058b  call    RtlAllocateLBlob
0x180020590  mov     ebx, eax
0x180020592  test    eax, eax
0x180020594  js      loc_1800204CD
0x18002059a  cmp     qword ptr [rbp+nBufferLength], r15
0x18002059e  ja      short loc_18002061D
0x1800205a0  cmp     dword ptr [rsi+38h], 1
0x1800205a4  mov     rdi, [rbp+lpBuffer]
0x1800205a8  jnz     short loc_1800205B0
0x1800205aa  cmp     qword ptr [r14], 0
0x1800205ae  jnz     short loc_1800205C5
0x1800205b0  xor     r9d, r9d; lpArguments
0x1800205b3  xor     r8d, r8d; nNumberOfArguments
0x1800205b6  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800205bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800205bf  call    cs:__imp_RaiseException
0x1800205c5  mov     rcx, [r14]
0x1800205c8  xor     r9d, r9d; lpFilePart
0x1800205cb  mov     edx, [rbp+nBufferLength]; nBufferLength
0x1800205ce  mov     r8, rdi; lpBuffer
0x1800205d1  mov     rcx, [rcx+10h]; lpFileName
0x1800205d5  call    cs:__imp_GetFullPathNameA
0x1800205db  mov     ecx, eax
0x1800205dd  mov     edx, ecx
0x1800205df  lea     r9, [rbp+arg_8]
0x1800205e3  lea     rcx, [rbp+arg_0]
0x1800205e7  mov     [rbp+arg_8], 0
0x1800205ef  mov     r8d, 1
0x1800205f5  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x1800205fa  mov     ebx, [rax]
0x1800205fc  test    ebx, ebx
0x1800205fe  js      loc_18002054F
0x180020604  mov     rax, [rbp+arg_8]
0x180020608  mov     [rbp+var_18], rax
0x18002060c  call    cs:__imp_AreFileApisANSI
0x180020612  test    eax, eax
0x180020614  jz      short loc_180020627
0x180020616  call    GetACP_0
0x18002061b  jmp     short loc_18002062C
0x18002061d  mov     ebx, 0C0000095h
0x180020622  jmp     loc_1800204CD
0x180020627  call    GetOEMCP_0
0x18002062c  lea     r9, [rbp+var_30]; struct _LUNICODE_STRING *
0x180020630  mov     ecx, eax; CodePage
0x180020632  lea     r8, [rbp+var_18]; struct _LBLOB *
0x180020636  call    ?isowin32_MultiByteToWideChar@@YAJKKAEBU_LBLOB@@AEAU_LUNICODE_STRING@@@Z; isowin32_MultiByteToWideChar(ulong,ulong,_LBLOB const &,_LUNICODE_STRING &)
0x18002063b  mov     ebx, eax
0x18002063d  test    eax, eax
0x18002063f  jns     short loc_180020657
0x180020641  test    rdi, rdi
0x180020644  jz      short loc_18002064E
0x180020646  mov     rcx, rdi; lpMem
0x180020649  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18002064e  mov     rcx, [rbp+var_20]
0x180020652  jmp     loc_1800207D0
0x180020657  test    rdi, rdi
0x18002065a  jz      loc_1800207A9
0x180020660  mov     rcx, rdi; lpMem
0x180020663  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020668  jmp     loc_1800207A9
0x18002066d  lea     rdx, [rbp+var_30]
0x180020671  mov     ecx, 208h
0x180020676  call    RtlAllocateLUnicodeString
0x18002067b  mov     ebx, eax
0x18002067d  test    eax, eax
0x18002067f  js      short loc_18002064E
0x180020681  mov     rbx, qword ptr [rbp+var_30+8]
0x180020685  mov     r15d, 0FFFFFFFFh
0x18002068b  shr     rbx, 1
0x18002068e  cmp     rbx, r15
0x180020691  ja      loc_1800207C2
0x180020697  cmp     dword ptr [rsi+38h], 2
0x18002069b  lea     r14, [rsi+30h]
0x18002069f  mov     rdi, [rbp+var_20]
0x1800206a3  mov     r13d, 0C00000E5h
0x1800206a9  jnz     short loc_1800206B1
0x1800206ab  cmp     qword ptr [r14], 0
0x1800206af  jnz     short loc_1800206C4
0x1800206b1  xor     r9d, r9d; lpArguments
0x1800206b4  xor     r8d, r8d; nNumberOfArguments
0x1800206b7  mov     ecx, r13d; dwExceptionCode
0x1800206ba  lea     edx, [r9+1]; dwExceptionFlags
0x1800206be  call    cs:__imp_RaiseException
0x1800206c4  mov     rcx, [r14]
0x1800206c7  xor     r9d, r9d; lpFilePart
0x1800206ca  mov     r8, rdi; lpBuffer
0x1800206cd  mov     edx, ebx; nBufferLength
0x1800206cf  mov     rcx, [rcx+10h]; lpFileName
0x1800206d3  call    cs:__imp_GetFullPathNameW
0x1800206d9  mov     ecx, eax
0x1800206db  inc     eax
0x1800206dd  mov     [rbp+arg_0], rax
0x1800206e1  cmp     rax, rbx
0x1800206e4  jb      short loc_180020762
0x1800206e6  xor     ecx, ecx
0x1800206e8  test    rdi, rdi
0x1800206eb  jz      short loc_180020705
0x1800206ed  mov     qword ptr [rbp+var_30+8], rcx
0x1800206f1  mov     qword ptr [rbp+var_30], rcx
0x1800206f5  mov     [rbp+var_20], rcx
0x1800206f9  mov     rcx, rdi; lpMem
0x1800206fc  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020701  mov     rax, [rbp+arg_0]
0x180020705  lea     rcx, [rax+rax]
0x180020709  lea     rdx, [rbp+var_30]
0x18002070d  call    RtlAllocateLUnicodeString
0x180020712  mov     ebx, eax
0x180020714  test    eax, eax
0x180020716  js      loc_18002064E
0x18002071c  mov     rbx, qword ptr [rbp+var_30+8]
0x180020720  shr     rbx, 1
0x180020723  cmp     rbx, r15
0x180020726  ja      short loc_180020797
0x180020728  cmp     dword ptr [rsi+38h], 2
0x18002072c  mov     rdi, [rbp+var_20]
0x180020730  jnz     short loc_180020738
0x180020732  cmp     qword ptr [r14], 0
0x180020736  jnz     short loc_18002074B
0x180020738  xor     r9d, r9d; lpArguments
0x18002073b  xor     r8d, r8d; nNumberOfArguments
0x18002073e  mov     ecx, r13d; dwExceptionCode
0x180020741  lea     edx, [r9+1]; dwExceptionFlags
0x180020745  call    cs:__imp_RaiseException
0x18002074b  mov     rcx, [r14]
0x18002074e  xor     r9d, r9d; lpFilePart
0x180020751  mov     r8, rdi; lpBuffer
0x180020754  mov     edx, ebx; nBufferLength
0x180020756  mov     rcx, [rcx+10h]; lpFileName
0x18002075a  call    cs:__imp_GetFullPathNameW
0x180020760  mov     ecx, eax
0x180020762  mov     edx, ecx
0x180020764  lea     r9, [rbp+arg_8]
0x180020768  lea     rcx, [rbp+arg_0]
0x18002076c  mov     [rbp+arg_8], 0
0x180020774  mov     r8d, 2
0x18002077a  mov     rsi, rdi
0x18002077d  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x180020782  mov     ebx, [rax]
0x180020784  test    ebx, ebx
0x180020786  jns     short loc_1800207A1
0x180020788  test    rdi, rdi
0x18002078b  jz      short loc_1800207DA
0x18002078d  test    rdi, rdi
0x180020790  jz      short loc_1800207DA
0x180020792  mov     rcx, rdi
0x180020795  jmp     short loc_1800207D5
0x180020797  mov     ebx, 0C0000095h
0x18002079c  jmp     loc_18002064E
0x1800207a1  mov     rax, [rbp+arg_8]
0x1800207a5  mov     qword ptr [rbp+var_30], rax
0x1800207a9  movups  xmm0, [rbp+var_30]
0x1800207ad  xor     ebx, ebx
0x1800207af  movsd   xmm1, [rbp+var_20]
0x1800207b4  movups  xmmword ptr [r12], xmm0
0x1800207b9  movsd   qword ptr [r12+10h], xmm1
0x1800207c0  jmp     short loc_1800207DA
0x1800207c2  mov     rcx, [rbp+var_20]; lpMem
0x1800207c6  mov     ebx, 0C0000095h
0x1800207cb  test    rcx, rcx
0x1800207ce  jz      short loc_1800207DA
0x1800207d0  test    rcx, rcx
0x1800207d3  jz      short loc_1800207DA
0x1800207d5  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800207da  mov     eax, ebx
0x1800207dc  mov     rbx, [rsp+50h+arg_10]
0x1800207e4  add     rsp, 50h
0x1800207e8  pop     r15
0x1800207ea  pop     r14
0x1800207ec  pop     r13
0x1800207ee  pop     r12
0x1800207f0  pop     rdi
0x1800207f1  pop     rsi
0x1800207f2  pop     rbp
0x1800207f3  retn
```
