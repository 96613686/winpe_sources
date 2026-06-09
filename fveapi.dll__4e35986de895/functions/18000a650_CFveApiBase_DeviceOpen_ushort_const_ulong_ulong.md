# CFveApiBase::DeviceOpen(ushort const *,ulong,ulong)

- ea: `0x18000a650`
- end: `0x18000aad5`
- name: `?DeviceOpen@CFveApiBase@@MEAAJPEBGKK@Z`
- size: `1157`
- prototype: `int(CFveApiBase *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180005410`
- `0x180009b20`
- `0x18000a650`
- `0x18000aae0`
- `0x18000b0d0`
- `0x18000ba30`
- `0x18007d9a0`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aac4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aac4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a799`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a80c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a799`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a80c`

## pseudocode

```c
__int64 __fastcall CFveApiBase::DeviceOpen(CFveApiBase *this, const unsigned __int16 *a2, unsigned int a3, DWORD a4)
{
  __int64 FileW; // r12
  __int64 v7; // r15
  unsigned __int16 *v8; // rsi
  unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // r13
  int LastHresultError; // edi
  int v12; // eax
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  int v18; // [rsp+44h] [rbp-2A4h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-2A0h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-298h] BYREF
  DWORD dwDesiredAccess; // [rsp+58h] [rbp-290h]
  LPVOID lpMem; // [rsp+60h] [rbp-288h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-280h] BYREF
  unsigned int v24; // [rsp+70h] [rbp-278h]
  unsigned __int16 *v25; // [rsp+78h] [rbp-270h]
  __int64 v26; // [rsp+80h] [rbp-268h]
  __int64 v27; // [rsp+88h] [rbp-260h]
  WCHAR FileName[264]; // [rsp+90h] [rbp-258h] BYREF

  dwDesiredAccess = a4;
  v24 = a3;
  memset_0(FileName, 0, 0x208u);
  FileW = -1;
  v7 = -1;
  v18 = -1;
  v19 = -1;
  v8 = 0;
  v20 = 0;
  v9 = 0;
  lpMem = 0;
  v10 = 0;
  lpFileName = 0;
  if ( a2 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(CFveApiBase *))(*(_QWORD *)this + 104LL))(this) )
      (*(void (__fastcall **)(CFveApiBase *))(*(_QWORD *)this + 32LL))(this);
    LastHresultError = CFveApiBase::ResolveVolumeName(a2, v24, (unsigned __int16 **)&lpMem);
    v9 = (unsigned __int16 *)lpMem;
    if ( LastHresultError >= 0 )
    {
      LastHresultError = CFveApiBase::VolumeNameToCdoInfo((LPCWSTR)lpMem, (enum _FVE_DEVICE_TYPE *)&v18, &v19, &v20);
      if ( LastHresultError < 0 )
        goto LABEL_18;
      if ( v18 != 2 )
        goto LABEL_7;
      if ( (*((_BYTE *)this + 364) & 1) != 0 )
        goto LABEL_7;
      v12 = CFveApiBase::ResolveCsvRedirectedVolumeName(v9, (unsigned __int16 **)&lpFileName);
      LastHresultError = v12;
      if ( v12 < 0 )
        goto LABEL_18;
      if ( v12 )
        goto LABEL_7;
      v10 = v9;
      v25 = v9;
      v9 = (unsigned __int16 *)lpFileName;
      lpMem = (LPVOID)lpFileName;
      lpFileName = 0;
      v18 = -1;
      v19 = -1;
      CFveApiBase::FastFree(v20);
      v20 = 0;
      LastHresultError = CFveApiBase::VolumeNameToCdoInfo(v9, (enum _FVE_DEVICE_TYPE *)&v18, &v19, &v20);
      if ( LastHresultError >= 0 )
      {
LABEL_7:
        v8 = v20;
        LastHresultError = StringCchPrintfW(FileName, 0x104u, L"%s\\SEI", v20);
        if ( LastHresultError >= 0 )
        {
          FileW = (__int64)CreateFileW(FileName, dwDesiredAccess, 3u, 0, 3u, 0, 0);
          v26 = FileW;
          if ( FileW == -1
            || (LastHresultError = StringCchPrintfW(FileName, 0x104u, L"%s\\HEI", v8), LastHresultError >= 0)
            && (v7 = (__int64)CreateFileW(FileName, dwDesiredAccess, 3u, 0, 3u, 0, 0), v27 = v7, v7 == -1) )
          {
            LastHresultError = GetLastHresultError();
          }
        }
      }
      else
      {
LABEL_18:
        v8 = v20;
      }
    }
  }
  else
  {
    LastHresultError = -2147024809;
  }
  if ( LastHresultError == -2144272310 )
  {
    LastHresultError = 0;
  }
  else if ( LastHresultError < 0 )
  {
    goto LABEL_30;
  }
  *((_DWORD *)this + 90) = v18;
  *((_DWORD *)this + 92) = v19;
  v13 = (void *)*((_QWORD *)this + 47);
  if ( v13 )
  {
    CFveApiBase::FastFree(v13);
    *((_QWORD *)this + 47) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 48);
  if ( v14 )
  {
    CFveApiBase::FastFree(v14);
    *((_QWORD *)this + 48) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 49);
  if ( v15 )
  {
    CFveApiBase::FastFree(v15);
    *((_QWORD *)this + 49) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 115);
  if ( v16 )
    CFveApiBase::FastFree(v16);
  *((_QWORD *)this + 47) = v9;
  v9 = 0;
  *((_QWORD *)this + 48) = v8;
  v8 = 0;
  *((_QWORD *)this + 115) = v10;
  v10 = 0;
  *((_QWORD *)this + 116) = FileW;
  FileW = -1;
  *((_QWORD *)this + 117) = v7;
  v7 = -1;
LABEL_30:
  if ( v9 && !HeapFree(CFveApiBase::_ProcessHeap, 0, v9) )
    GetLastHresultError();
  if ( v10 )
    CFveApiBase::FastFree(v10);
  if ( lpFileName )
    CFveApiBase::FastFree((void *)lpFileName);
  if ( v8 && !HeapFree(CFveApiBase::_ProcessHeap, 0, v8) )
    GetLastHresultError();
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v7 != -1 )
    CloseHandle((HANDLE)v7);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18000a650  push    rbx
0x18000a652  push    rsi
0x18000a653  push    rdi
0x18000a654  push    r12
0x18000a656  push    r13
0x18000a658  push    r14
0x18000a65a  push    r15
0x18000a65c  sub     rsp, 2B0h
0x18000a663  mov     rax, cs:__security_cookie
0x18000a66a  xor     rax, rsp
0x18000a66d  mov     [rsp+2E8h+var_48], rax
0x18000a675  mov     [rsp+2E8h+dwDesiredAccess], r9d
0x18000a67a  mov     [rsp+2E8h+var_278], r8d
0x18000a67f  mov     rdi, rdx
0x18000a682  mov     rbx, rcx
0x18000a685  xor     edx, edx; Val
0x18000a687  mov     r8d, 208h; Size
0x18000a68d  lea     rcx, [rsp+2E8h+FileName]; void *
0x18000a695  call    memset_0
0x18000a69a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000a6a1  mov     r15, r12
0x18000a6a4  mov     [rsp+2E8h+var_2A4], r12d
0x18000a6a9  mov     [rsp+2E8h+var_2A0], 0FFFFFFFFh
0x18000a6b1  xor     esi, esi
0x18000a6b3  mov     [rsp+2E8h+var_298], rsi
0x18000a6b8  xor     r14d, r14d
0x18000a6bb  mov     [rsp+2E8h+lpMem], r14
0x18000a6c0  xor     r13d, r13d
0x18000a6c3  mov     [rsp+2E8h+lpFileName], rsi
0x18000a6c8  test    rdi, rdi
0x18000a6cb  jz      loc_18000A84D
0x18000a6d1  mov     rax, [rbx]
0x18000a6d4  mov     rcx, rbx
0x18000a6d7  mov     rax, [rax+68h]
0x18000a6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e0  test    al, al
0x18000a6e2  jnz     loc_18000A85B
0x18000a6e8  lea     r8, [rsp+2E8h+lpMem]; unsigned __int16 **
0x18000a6ed  mov     edx, [rsp+2E8h+var_278]; unsigned int
0x18000a6f1  mov     rcx, rdi; unsigned __int16 *
0x18000a6f4  call    ?ResolveVolumeName@CFveApiBase@@SAJPEBGKPEAPEAG@Z; CFveApiBase::ResolveVolumeName(ushort const *,ulong,ushort * *)
0x18000a6f9  mov     edi, eax
0x18000a6fb  mov     [rsp+2E8h+var_2A8], eax
0x18000a6ff  mov     r14, [rsp+2E8h+lpMem]
0x18000a704  test    eax, eax
0x18000a706  js      loc_18000A901
0x18000a70c  lea     r9, [rsp+2E8h+var_298]; unsigned __int16 **
0x18000a711  lea     r8, [rsp+2E8h+var_2A0]; unsigned int *
0x18000a716  lea     rdx, [rsp+2E8h+var_2A4]; enum _FVE_DEVICE_TYPE *
0x18000a71b  mov     rcx, r14; lpFileName
0x18000a71e  call    ?VolumeNameToCdoInfo@CFveApiBase@@SAJPEBGPEAW4_FVE_DEVICE_TYPE@@PEAKPEAPEAG@Z; CFveApiBase::VolumeNameToCdoInfo(ushort const *,_FVE_DEVICE_TYPE *,ulong *,ushort * *)
0x18000a723  mov     edi, eax
0x18000a725  mov     [rsp+2E8h+var_2A8], eax
0x18000a729  test    eax, eax
0x18000a72b  js      loc_18000A8FC
0x18000a731  cmp     [rsp+2E8h+var_2A4], 2
0x18000a736  jz      loc_18000A86F
0x18000a73c  mov     rsi, [rsp+2E8h+var_298]
0x18000a741  mov     r9, rsi
0x18000a744  lea     r8, aSSei; "%s\\SEI"
0x18000a74b  mov     edx, 104h; unsigned __int64
0x18000a750  lea     rcx, [rsp+2E8h+FileName]; unsigned __int16 *
0x18000a758  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a75d  mov     edi, eax
0x18000a75f  mov     [rsp+2E8h+var_2A8], eax
0x18000a763  test    eax, eax
0x18000a765  js      loc_18000A901
0x18000a76b  mov     [rsp+2E8h+hTemplateFile], 0; hTemplateFile
0x18000a774  mov     [rsp+2E8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000a77c  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a784  xor     r9d, r9d; lpSecurityAttributes
0x18000a787  mov     r8d, 3; dwShareMode
0x18000a78d  mov     edx, [rsp+2E8h+dwDesiredAccess]; dwDesiredAccess
0x18000a791  lea     rcx, [rsp+2E8h+FileName]; lpFileName
0x18000a799  call    cs:__imp_CreateFileW
0x18000a7a0  nop     dword ptr [rax+rax+00h]
0x18000a7a5  mov     r12, rax
0x18000a7a8  mov     [rsp+2E8h+var_268], rax
0x18000a7b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a7b4  jz      loc_18000A83D
0x18000a7ba  mov     r9, rsi
0x18000a7bd  lea     r8, aSHei; "%s\\HEI"
0x18000a7c4  mov     edx, 104h; unsigned __int64
0x18000a7c9  lea     rcx, [rsp+2E8h+FileName]; unsigned __int16 *
0x18000a7d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a7d6  mov     edi, eax
0x18000a7d8  mov     [rsp+2E8h+var_2A8], eax
0x18000a7dc  test    eax, eax
0x18000a7de  js      loc_18000A901
0x18000a7e4  xor     eax, eax
0x18000a7e6  mov     [rsp+2E8h+hTemplateFile], rax; hTemplateFile
0x18000a7eb  mov     [rsp+2E8h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000a7ef  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a7f7  xor     r9d, r9d; lpSecurityAttributes
0x18000a7fa  mov     r8d, 3; dwShareMode
0x18000a800  mov     edx, [rsp+2E8h+dwDesiredAccess]; dwDesiredAccess
0x18000a804  lea     rcx, [rsp+2E8h+FileName]; lpFileName
0x18000a80c  call    cs:__imp_CreateFileW
0x18000a813  nop     dword ptr [rax+rax+00h]
0x18000a818  mov     r15, rax
0x18000a81b  mov     [rsp+2E8h+var_260], rax
0x18000a823  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a827  jnz     loc_18000A901
0x18000a82d  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000a832  mov     edi, eax
0x18000a834  mov     [rsp+2E8h+var_2A8], eax
0x18000a838  jmp     loc_18000A901
0x18000a83d  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000a842  mov     edi, eax
0x18000a844  mov     [rsp+2E8h+var_2A8], eax
0x18000a848  jmp     loc_18000A901
0x18000a84d  mov     edi, 80070057h
0x18000a852  mov     [rsp+2E8h+var_2A8], edi
0x18000a856  jmp     loc_18000A901
0x18000a85b  mov     rax, [rbx]
0x18000a85e  mov     rcx, rbx
0x18000a861  mov     rax, [rax+20h]
0x18000a865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a86a  jmp     loc_18000A6E8
0x18000a86f  test    byte ptr [rbx+16Ch], 1
0x18000a876  jnz     loc_18000A73C
0x18000a87c  lea     rdx, [rsp+2E8h+lpFileName]; unsigned __int16 **
0x18000a881  mov     rcx, r14; unsigned __int16 *
0x18000a884  call    ?ResolveCsvRedirectedVolumeName@CFveApiBase@@SAJPEBGPEAPEAG@Z; CFveApiBase::ResolveCsvRedirectedVolumeName(ushort const *,ushort * *)
0x18000a889  mov     edi, eax
0x18000a88b  mov     [rsp+2E8h+var_2A8], eax
0x18000a88f  test    eax, eax
0x18000a891  js      short loc_18000A8FC
0x18000a893  jnz     loc_18000A73C
0x18000a899  mov     r13, r14
0x18000a89c  mov     [rsp+2E8h+var_270], r14
0x18000a8a1  mov     r14, [rsp+2E8h+lpFileName]
0x18000a8a6  mov     [rsp+2E8h+lpMem], r14
0x18000a8ab  mov     [rsp+2E8h+lpFileName], 0
0x18000a8b4  mov     [rsp+2E8h+var_2A4], 0FFFFFFFFh
0x18000a8bc  mov     [rsp+2E8h+var_2A0], 0FFFFFFFFh
0x18000a8c4  mov     rcx, [rsp+2E8h+var_298]; lpMem
0x18000a8c9  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000a8ce  mov     [rsp+2E8h+var_298], 0
0x18000a8d7  lea     r9, [rsp+2E8h+var_298]; unsigned __int16 **
0x18000a8dc  lea     r8, [rsp+2E8h+var_2A0]; unsigned int *
0x18000a8e1  lea     rdx, [rsp+2E8h+var_2A4]; enum _FVE_DEVICE_TYPE *
0x18000a8e6  mov     rcx, r14; lpFileName
0x18000a8e9  call    ?VolumeNameToCdoInfo@CFveApiBase@@SAJPEBGPEAW4_FVE_DEVICE_TYPE@@PEAKPEAPEAG@Z; CFveApiBase::VolumeNameToCdoInfo(ushort const *,_FVE_DEVICE_TYPE *,ulong *,ushort * *)
0x18000a8ee  mov     edi, eax
0x18000a8f0  mov     [rsp+2E8h+var_2A8], eax
0x18000a8f4  test    eax, eax
0x18000a8f6  jns     loc_18000A73C
0x18000a8fc  mov     rsi, [rsp+2E8h+var_298]
0x18000a901  cmp     edi, 8031004Ah
0x18000a907  jz      loc_18000AA3C
0x18000a90d  test    edi, edi
0x18000a90f  js      loc_18000A99E
0x18000a915  mov     eax, [rsp+2E8h+var_2A4]
0x18000a919  mov     [rbx+168h], eax
0x18000a91f  mov     eax, [rsp+2E8h+var_2A0]
0x18000a923  mov     [rbx+170h], eax
0x18000a929  mov     rcx, [rbx+178h]; lpMem
0x18000a930  test    rcx, rcx
0x18000a933  jnz     loc_18000AA43
0x18000a939  mov     rcx, [rbx+180h]; lpMem
0x18000a940  test    rcx, rcx
0x18000a943  jnz     loc_18000AA58
0x18000a949  mov     rcx, [rbx+188h]; lpMem
0x18000a950  test    rcx, rcx
0x18000a953  jnz     loc_18000AA6D
0x18000a959  mov     rcx, [rbx+398h]; lpMem
0x18000a960  test    rcx, rcx
0x18000a963  jnz     loc_18000AA82
0x18000a969  mov     [rbx+178h], r14
0x18000a970  xor     r14d, r14d
0x18000a973  mov     [rbx+180h], rsi
0x18000a97a  xor     esi, esi
0x18000a97c  mov     [rbx+398h], r13
0x18000a983  xor     r13d, r13d
0x18000a986  mov     [rbx+3A0h], r12
0x18000a98d  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000a994  mov     [rbx+3A8h], r15
0x18000a99b  mov     r15, r12
0x18000a99e  test    r14, r14
0x18000a9a1  jz      short loc_18000A9C3
0x18000a9a3  mov     r8, r14; lpMem
0x18000a9a6  xor     edx, edx; dwFlags
0x18000a9a8  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x18000a9af  call    cs:__imp_HeapFree
0x18000a9b6  nop     dword ptr [rax+rax+00h]
0x18000a9bb  test    eax, eax
0x18000a9bd  jz      loc_18000AA8C
0x18000a9c3  test    r13, r13
0x18000a9c6  jnz     loc_18000AA96
0x18000a9cc  mov     rcx, [rsp+2E8h+lpFileName]; lpMem
0x18000a9d1  test    rcx, rcx
0x18000a9d4  jnz     loc_18000AAA3
0x18000a9da  test    rsi, rsi
0x18000a9dd  jnz     short loc_18000AA19
0x18000a9df  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000a9e3  jnz     loc_18000AAAD
0x18000a9e9  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000a9ed  jnz     loc_18000AAC1
0x18000a9f3  mov     eax, edi
0x18000a9f5  mov     rcx, [rsp+2E8h+var_48]
0x18000a9fd  xor     rcx, rsp; StackCookie
0x18000aa00  call    __security_check_cookie
0x18000aa05  add     rsp, 2B0h
0x18000aa0c  pop     r15
0x18000aa0e  pop     r14
0x18000aa10  pop     r13
0x18000aa12  pop     r12
0x18000aa14  pop     rdi
0x18000aa15  pop     rsi
0x18000aa16  pop     rbx
0x18000aa17  retn
0x18000aa19  mov     r8, rsi; lpMem
0x18000aa1c  xor     edx, edx; dwFlags
0x18000aa1e  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x18000aa25  call    cs:__imp_HeapFree
0x18000aa2c  nop     dword ptr [rax+rax+00h]
0x18000aa31  test    eax, eax
0x18000aa33  jnz     short loc_18000A9DF
0x18000aa35  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000aa3a  jmp     short loc_18000A9DF
0x18000aa3c  xor     edi, edi
0x18000aa3e  jmp     loc_18000A915
0x18000aa43  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000aa48  mov     qword ptr [rbx+178h], 0
0x18000aa53  jmp     loc_18000A939
0x18000aa58  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000aa5d  mov     qword ptr [rbx+180h], 0
0x18000aa68  jmp     loc_18000A949
0x18000aa6d  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000aa72  mov     qword ptr [rbx+188h], 0
0x18000aa7d  jmp     loc_18000A959
0x18000aa82  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000aa87  jmp     loc_18000A969
0x18000aa8c  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000aa91  jmp     loc_18000A9C3
0x18000aa96  mov     rcx, r13; lpMem
0x18000aa99  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000aa9e  jmp     loc_18000A9CC
0x18000aaa3  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000aaa8  jmp     loc_18000A9DA
0x18000aaad  mov     rcx, r12; hObject
0x18000aab0  call    cs:__imp_CloseHandle
0x18000aab7  nop     dword ptr [rax+rax+00h]
0x18000aabc  jmp     loc_18000A9E9
0x18000aac1  mov     rcx, r15; hObject
0x18000aac4  call    cs:__imp_CloseHandle
0x18000aacb  nop     dword ptr [rax+rax+00h]
0x18000aad0  jmp     loc_18000A9F3
0x18011f700  push    rbp
0x18011f702  sub     rsp, 40h
0x18011f706  mov     rbp, rdx
0x18011f709  add     rsp, 40h
0x18011f70d  pop     rbp
0x18011f70e  retn
```
