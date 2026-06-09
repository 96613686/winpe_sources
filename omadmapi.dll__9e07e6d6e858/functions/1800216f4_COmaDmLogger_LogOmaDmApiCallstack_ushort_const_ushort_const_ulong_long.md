# COmaDmLogger::LogOmaDmApiCallstack(ushort const *,ushort const *,ulong,long)

- ea: `0x1800216f4`
- end: `0x180021a17`
- name: `?LogOmaDmApiCallstack@COmaDmLogger@@QEAAXPEBG0KJ@Z`
- size: `803`
- prototype: `void __fastcall(COmaDmLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019684`

## callees

- `0x18000171c`
- `0x1800031b0`
- `0x18000320c`
- `0x180004d7c`
- `0x1800216f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002179b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002179b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800217c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800217c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217e1`
- `ntdll!RtlCaptureStackBackTrace` at `0x18002176a`
- `ntdll!RtlCaptureStackBackTrace` at `0x18002176a`
- `DMCmnUtils!CopyString` at `0x18002181c`
- `DMCmnUtils!CopyString` at `0x18002181c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall COmaDmLogger::LogOmaDmApiCallstack(
        COmaDmLogger *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  int v7; // r15d
  __int64 i; // rdi
  void **v9; // rsi
  void *v10; // r14
  DWORD LastError; // ebx
  const unsigned __int16 *v12; // rcx
  __int64 *v13; // r8
  __int64 *v14; // r9
  __int64 *v15; // r10
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // edx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // ecx
  HMODULE phModule; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-B8h]
  __int64 *v29; // [rsp+50h] [rbp-B0h]
  PVOID BackTrace[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  WCHAR Filename[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  HMODULE *p_phModule; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  const wchar_t *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v39; // [rsp+C0h] [rbp-40h]
  int v40; // [rsp+C8h] [rbp-38h]
  int v41; // [rsp+CCh] [rbp-34h]
  __int64 *v42; // [rsp+D0h] [rbp-30h]
  int v43; // [rsp+D8h] [rbp-28h]
  int v44; // [rsp+DCh] [rbp-24h]
  __int64 *v45; // [rsp+E0h] [rbp-20h]
  int v46; // [rsp+E8h] [rbp-18h]
  int v47; // [rsp+ECh] [rbp-14h]
  __int64 *v48; // [rsp+F0h] [rbp-10h]
  int v49; // [rsp+F8h] [rbp-8h]
  int v50; // [rsp+FCh] [rbp-4h]
  const unsigned __int16 *v51; // [rsp+100h] [rbp+0h]
  int v52; // [rsp+108h] [rbp+8h]
  int v53; // [rsp+10Ch] [rbp+Ch]

  *(_OWORD *)BackTrace = 0;
  v31 = 0;
  `eh vector constructor iterator'(
    &v27,
    8u,
    3u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  v7 = 1;
  if ( RtlCaptureStackBackTrace(4u, 3u, BackTrace, 0) )
  {
    for ( i = 0; i != 3; ++i )
    {
      phModule = 0;
      if ( GetModuleHandleExW(6u, (LPCWSTR)BackTrace[i], &phModule)
        && phModule
        && GetModuleFileNameW(phModule, Filename, 0x104u) )
      {
        v9 = (void **)&(&v27)[i];
        v10 = *v9;
        if ( *v9 )
        {
          LastError = GetLastError();
          LocalFree(v10);
          SetLastError(LastError);
        }
        *v9 = 0;
        CopyString(Filename, 0xFFFFFFFF, (unsigned __int16 **)&(&v27)[i]);
      }
    }
  }
  if ( (unsigned int)dword_1800320D0 > 5
    && (qword_1800320E0 & 0x400000000000LL) != 0
    && (qword_1800320E8 & 0x400000000000LL) == qword_1800320E8 )
  {
    v12 = (const unsigned __int16 *)((char *)this + 16);
    v13 = v29;
    v14 = v28;
    v15 = v27;
    LODWORD(phModule) = a5;
    v26 = 0x2000000;
    v16 = -1;
    if ( this == (COmaDmLogger *)-16LL )
    {
      v12 = &dword_1800273FC;
    }
    else
    {
      v17 = -1;
      do
        ++v17;
      while ( *((_BYTE *)v12 + v17) );
      v7 = v17 + 1;
    }
    v51 = v12;
    v52 = v7;
    v53 = 0;
    v18 = 2;
    if ( v29 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)v29 + v19) );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v13 = &qword_1800289F0;
      v20 = 2;
    }
    v48 = v13;
    v49 = v20;
    v50 = 0;
    if ( v28 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)v28 + v21) );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v14 = &qword_1800289F0;
      v22 = 2;
    }
    v45 = v14;
    v46 = v22;
    v47 = 0;
    if ( v27 )
    {
      v23 = -1;
      do
        ++v23;
      while ( *((_WORD *)v27 + v23) );
      v24 = 2 * v23 + 2;
    }
    else
    {
      v15 = &qword_1800289F0;
      v24 = 2;
    }
    v42 = v15;
    v43 = v24;
    v44 = 0;
    if ( a3 )
    {
      do
        ++v16;
      while ( a3[v16] );
      v18 = 2 * v16 + 2;
    }
    else
    {
      a3 = (const unsigned __int16 *)&qword_1800289F0;
    }
    v39 = a3;
    v40 = v18;
    v41 = 0;
    v37 = L"OmaDmInitiateSession_Internal";
    v38 = 60;
    p_phModule = &phModule;
    v36 = 4;
    v33 = &v26;
    v34 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800320D0, byte_18002B2C1, 0, 0, 10, Filename, phModule, v26);
  }
  `eh vector destructor iterator'(
    &v27,
    8u,
    3u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
}

```

## disassembly

```asm
0x1800216f4  push    rbp
0x1800216f6  push    rbx
0x1800216f7  push    rsi
0x1800216f8  push    rdi
0x1800216f9  push    r12
0x1800216fb  push    r13
0x1800216fd  push    r14
0x1800216ff  push    r15
0x180021701  lea     rbp, [rsp-198h]
0x180021709  sub     rsp, 298h
0x180021710  mov     rax, cs:__security_cookie
0x180021717  xor     rax, rsp
0x18002171a  mov     [rbp+1D0h+var_50], rax
0x180021721  mov     r12, r8
0x180021724  mov     r13, rcx
0x180021727  xorps   xmm0, xmm0
0x18002172a  xor     eax, eax
0x18002172c  movups  xmmword ptr [rsp+2D0h+BackTrace], xmm0
0x180021731  mov     [rsp+2D0h+var_268], rax
0x180021736  lea     rdi, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002173d  mov     [rsp+2D0h+var_2B0], rdi; void (*)(void *)
0x180021742  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180021749  lea     edx, [rax+8]; unsigned __int64
0x18002174c  lea     r8d, [rax+3]; unsigned __int64
0x180021750  lea     rcx, [rsp+2D0h+var_290]; void *
0x180021755  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002175a  nop
0x18002175b  xor     r9d, r9d; BackTraceHash
0x18002175e  lea     r8, [rsp+2D0h+BackTrace]; BackTrace
0x180021763  lea     edx, [r9+3]; FramesToCapture
0x180021767  lea     ecx, [rdx+1]; FramesToSkip
0x18002176a  call    cs:__imp_RtlCaptureStackBackTrace
0x180021771  nop     dword ptr [rax+rax+00h]
0x180021776  xor     ebx, ebx
0x180021778  lea     r15d, [rbx+1]
0x18002177c  test    ax, ax
0x18002177f  jz      loc_18002183C
0x180021785  mov     edi, ebx
0x180021787  mov     [rsp+2D0h+phModule], rbx
0x18002178c  lea     r8, [rsp+2D0h+phModule]; phModule
0x180021791  mov     rdx, [rsp+rdi*8+2D0h+BackTrace]; lpModuleName
0x180021796  mov     ecx, 6; dwFlags
0x18002179b  call    cs:__imp_GetModuleHandleExW
0x1800217a2  nop     dword ptr [rax+rax+00h]
0x1800217a7  test    eax, eax
0x1800217a9  jz      short loc_180021828
0x1800217ab  mov     rcx, [rsp+2D0h+phModule]; hModule
0x1800217b0  test    rcx, rcx
0x1800217b3  jz      short loc_180021828
0x1800217b5  mov     r8d, 104h; nSize
0x1800217bb  lea     rdx, [rsp+2D0h+Filename]; lpFilename
0x1800217c0  call    cs:__imp_GetModuleFileNameW
0x1800217c7  nop     dword ptr [rax+rax+00h]
0x1800217cc  test    eax, eax
0x1800217ce  jz      short loc_180021828
0x1800217d0  lea     rsi, [rsp+2D0h+var_290]
0x1800217d5  lea     rsi, [rsi+rdi*8]
0x1800217d9  mov     r14, [rsi]
0x1800217dc  test    r14, r14
0x1800217df  jz      short loc_18002180E
0x1800217e1  call    cs:__imp_GetLastError
0x1800217e8  nop     dword ptr [rax+rax+00h]
0x1800217ed  mov     ebx, eax
0x1800217ef  mov     rcx, r14; hMem
0x1800217f2  call    cs:__imp_LocalFree
0x1800217f9  nop     dword ptr [rax+rax+00h]
0x1800217fe  mov     ecx, ebx; dwErrCode
0x180021800  call    cs:__imp_SetLastError
0x180021807  nop     dword ptr [rax+rax+00h]
0x18002180c  xor     ebx, ebx
0x18002180e  mov     [rsi], rbx
0x180021811  mov     r8, rsi
0x180021814  or      edx, 0FFFFFFFFh
0x180021817  lea     rcx, [rsp+2D0h+Filename]
0x18002181c  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180021823  nop     dword ptr [rax+rax+00h]
0x180021828  add     rdi, r15
0x18002182b  cmp     rdi, 3
0x18002182f  jnz     loc_180021787
0x180021835  lea     rdi, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002183c  mov     eax, cs:dword_1800320D0
0x180021842  cmp     eax, 5
0x180021845  jbe     loc_1800219DD
0x18002184b  mov     rcx, cs:qword_1800320E8
0x180021852  mov     rax, cs:qword_1800320E0
0x180021859  mov     rdx, 400000000000h
0x180021863  test    rdx, rax
0x180021866  jz      loc_1800219DD
0x18002186c  mov     rax, rcx
0x18002186f  and     rax, rdx
0x180021872  cmp     rax, rcx
0x180021875  jnz     loc_1800219DD
0x18002187b  lea     rcx, [r13+10h]
0x18002187f  mov     r8, [rsp+2D0h+var_280]
0x180021884  mov     r9, [rsp+2D0h+var_288]
0x180021889  mov     r10, [rsp+2D0h+var_290]
0x18002188e  mov     eax, [rbp+1D0h+arg_20]
0x180021894  mov     dword ptr [rsp+2D0h+phModule], eax
0x180021898  mov     [rsp+2D0h+var_298], 2000000h
0x1800218a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800218a5  test    rcx, rcx
0x1800218a8  jz      short loc_1800218BB
0x1800218aa  mov     rdx, rax
0x1800218ad  inc     rdx
0x1800218b0  cmp     [rcx+rdx], bl
0x1800218b3  jnz     short loc_1800218AD
0x1800218b5  lea     r15d, [rdx+1]
0x1800218b9  jmp     short loc_1800218C2
0x1800218bb  lea     rcx, dword_1800273FC
0x1800218c2  mov     [rbp+1D0h+var_1D0], rcx
0x1800218c6  mov     [rbp+1D0h+var_1C8], r15d
0x1800218ca  mov     [rbp+1D0h+var_1C4], ebx
0x1800218cd  lea     r11, qword_1800289F0
0x1800218d4  mov     edx, 2
0x1800218d9  test    r8, r8
0x1800218dc  jz      short loc_1800218F4
0x1800218de  mov     rcx, rax
0x1800218e1  inc     rcx
0x1800218e4  cmp     [r8+rcx*2], bx
0x1800218e9  jnz     short loc_1800218E1
0x1800218eb  lea     ecx, ds:2[rcx*2]
0x1800218f2  jmp     short loc_1800218F9
0x1800218f4  mov     r8, r11
0x1800218f7  mov     ecx, edx
0x1800218f9  mov     [rbp+1D0h+var_1E0], r8
0x1800218fd  mov     [rbp+1D0h+var_1D8], ecx
0x180021900  mov     [rbp+1D0h+var_1D4], ebx
0x180021903  test    r9, r9
0x180021906  jz      short loc_18002191E
0x180021908  mov     rcx, rax
0x18002190b  inc     rcx
0x18002190e  cmp     [r9+rcx*2], bx
0x180021913  jnz     short loc_18002190B
0x180021915  lea     ecx, ds:2[rcx*2]
0x18002191c  jmp     short loc_180021923
0x18002191e  mov     r9, r11
0x180021921  mov     ecx, edx
0x180021923  mov     [rbp+1D0h+var_1F0], r9
0x180021927  mov     [rbp+1D0h+var_1E8], ecx
0x18002192a  mov     [rbp+1D0h+var_1E4], ebx
0x18002192d  test    r10, r10
0x180021930  jz      short loc_180021948
0x180021932  mov     rcx, rax
0x180021935  inc     rcx
0x180021938  cmp     [r10+rcx*2], bx
0x18002193d  jnz     short loc_180021935
0x18002193f  lea     ecx, ds:2[rcx*2]
0x180021946  jmp     short loc_18002194D
0x180021948  mov     r10, r11
0x18002194b  mov     ecx, edx
0x18002194d  mov     [rbp+1D0h+var_200], r10
0x180021951  mov     [rbp+1D0h+var_1F8], ecx
0x180021954  mov     [rbp+1D0h+var_1F4], ebx
0x180021957  test    r12, r12
0x18002195a  jz      short loc_18002196F
0x18002195c  inc     rax
0x18002195f  cmp     [r12+rax*2], bx
0x180021964  jnz     short loc_18002195C
0x180021966  lea     edx, ds:2[rax*2]
0x18002196d  jmp     short loc_180021972
0x18002196f  mov     r12, r11
0x180021972  mov     [rbp+1D0h+var_210], r12
0x180021976  mov     [rbp+1D0h+var_208], edx
0x180021979  mov     [rbp+1D0h+var_204], ebx
0x18002197c  lea     rax, aOmadminitiates_7; "OmaDmInitiateSession_Internal"
0x180021983  mov     [rbp+1D0h+var_220], rax
0x180021987  mov     [rbp+1D0h+var_218], 3Ch ; '<'
0x18002198f  lea     rax, [rsp+2D0h+phModule]
0x180021994  mov     [rbp+1D0h+var_230], rax
0x180021998  mov     [rbp+1D0h+var_228], 4
0x1800219a0  lea     rax, [rsp+2D0h+var_298]
0x1800219a5  mov     [rbp+1D0h+var_240], rax
0x1800219a9  mov     [rbp+1D0h+var_238], 8
0x1800219b1  lea     rax, [rsp+2D0h+Filename]
0x1800219b6  mov     [rsp+2D0h+var_2A8], rax
0x1800219bb  mov     dword ptr [rsp+2D0h+var_2B0], 0Ah
0x1800219c3  xor     r9d, r9d
0x1800219c6  xor     r8d, r8d
0x1800219c9  lea     rdx, byte_18002B2C1
0x1800219d0  lea     rcx, dword_1800320D0
0x1800219d7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800219dc  nop
0x1800219dd  mov     r9, rdi; void (*)(void *)
0x1800219e0  mov     edx, 8; unsigned __int64
0x1800219e5  lea     r8d, [rdx-5]; unsigned __int64
0x1800219e9  lea     rcx, [rsp+2D0h+var_290]; void *
0x1800219ee  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800219f3  mov     rcx, [rbp+1D0h+var_50]
0x1800219fa  xor     rcx, rsp; StackCookie
0x1800219fd  call    __security_check_cookie
0x180021a02  add     rsp, 298h
0x180021a09  pop     r15
0x180021a0b  pop     r14
0x180021a0d  pop     r13
0x180021a0f  pop     r12
0x180021a11  pop     rdi
0x180021a12  pop     rsi
0x180021a13  pop     rbx
0x180021a14  pop     rbp
0x180021a15  retn
```
