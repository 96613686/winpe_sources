# DoWPCLogging(ushort const *,ushort const *,int)

- ea: `0x180066510`
- end: `0x180066853`
- name: `?DoWPCLogging@@YAJPEBG0H@Z`
- size: `835`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180021d38`
- `0x180066510`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066828`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066828`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066589`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006659c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066589`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006659c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066558`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066558`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006661c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006661c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066626`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066680`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066680`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800667fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800667fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006680b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006680b`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18006665f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18006665f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800666d1`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800666d1`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800666a8`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800666a8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180066722`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180066722`

## string_xrefs

- `0x18006658f`: `EventWrite`

## pseudocode

```c
__int64 __fastcall DoWPCLogging(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v5; // edi
  HMODULE Library; // rax
  HMODULE v7; // r12
  FARPROC ProcAddress; // rbx
  FARPROC v9; // r13
  FARPROC v10; // rax
  int v11; // eax
  signed int LastError; // eax
  void *v13; // rbx
  DWORD FileVersionInfoSize; // esi
  HANDLE ProcessHeap; // rax
  void *v16; // rax
  LPWSTR FileNameW; // rax
  __int64 v18; // rcx
  LPWSTR v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // eax
  HANDLE v24; // rax
  LPVOID lpData; // [rsp+20h] [rbp-E0h]
  DWORD dwHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int puLen; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall *v31)(__int64, const EVENT_DESCRIPTOR *, __int64, const unsigned __int16 **); // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+6Ch] [rbp-94h]
  LPWSTR v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 *v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+88h] [rbp-78h]
  int v40; // [rsp+8Ch] [rbp-74h]
  int *v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  WCHAR Filename[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v47[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v48; // [rsp+540h] [rbp+440h] BYREF

  v48 = a3;
  v5 = -2147467263;
  Library = LoadLibraryExW(L"advapi32", 0, 0);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "EventRegister");
    v9 = GetProcAddress(v7, "EventUnregister");
    v10 = GetProcAddress(v7, "EventWrite");
    v31 = (__int64 (__fastcall *)(__int64, const EVENT_DESCRIPTOR *, __int64, const unsigned __int16 **))v10;
    if ( ProcAddress && v9 && v10 )
    {
      if ( a1 && a2 )
      {
        v29 = 0;
        v11 = ((__int64 (__fastcall *)(const GUID *, _QWORD, _QWORD, __int64 *))ProcAddress)(&WPCPROV, 0, 0, &v29);
        v5 = v11;
        if ( v11 )
        {
          if ( v11 > 0 )
            v5 = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          Filename[0] = 0;
          if ( GetModuleFileNameW(0, Filename, 0x104u) )
          {
            v47[0] = 0;
            dwHandle = 0;
            v5 = 0;
            v13 = 0;
            FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, Filename, &dwHandle);
            if ( FileVersionInfoSize )
            {
              ProcessHeap = GetProcessHeap();
              v16 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSize);
              v13 = v16;
              if ( v16 )
              {
                if ( GetFileVersionInfoExW(3u, Filename, dwHandle, FileVersionInfoSize, v16) )
                {
                  puLen = 0;
                  lpBuffer = 0;
                  VerQueryValueW(v13, L"\\", &lpBuffer, &puLen);
                  if ( lpBuffer )
                  {
                    LODWORD(lpData) = *((unsigned __int16 *)lpBuffer + 4);
                    StringCchPrintfW(
                      v47,
                      0x104u,
                      L"%d.%d.%d.%d",
                      *((unsigned __int16 *)lpBuffer + 5),
                      lpData,
                      *((unsigned __int16 *)lpBuffer + 7),
                      *((unsigned __int16 *)lpBuffer + 6));
                  }
                }
              }
            }
            FileNameW = PathFindFileNameW(Filename);
            v18 = -1;
            v32 = a1;
            v19 = FileNameW;
            v20 = -1;
            do
              ++v20;
            while ( a1[v20] );
            v34 = 0;
            v33 = 2 * v20 + 2;
            v21 = -1;
            do
              ++v21;
            while ( v19[v21] );
            v35 = v19;
            v36 = 2 * v21 + 2;
            v37 = 0;
            v38 = v47;
            v22 = -1;
            do
              ++v22;
            while ( v47[v22] );
            v40 = 0;
            v39 = 2 * v22 + 2;
            v41 = &v48;
            v42 = 4;
            v43 = a2;
            do
              ++v18;
            while ( a2[v18] );
            v45 = 0;
            v44 = 2 * v18 + 2;
            v23 = v31(v29, &WPCEVENT_WEB_FILEDOWNLOAD, 5, &v32);
            if ( v23 )
            {
              if ( v23 > 0 )
                v5 = (unsigned __int16)v23 | 0x80070000;
              else
                v5 = v23;
            }
            v24 = GetProcessHeap();
            HeapFree(v24, 0, v13);
          }
          else
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
          }
          ((void (__fastcall *)(__int64))v9)(v29);
        }
      }
      else
      {
        v5 = -2147024809;
      }
    }
    FreeLibrary(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180066510  mov     [rsp-8+arg_10], r8d
0x180066515  push    rbp
0x180066516  push    rbx
0x180066517  push    rsi
0x180066518  push    rdi
0x180066519  push    r12
0x18006651b  push    r13
0x18006651d  push    r14
0x18006651f  push    r15
0x180066521  lea     rbp, [rsp-3E8h]
0x180066529  sub     rsp, 4E8h
0x180066530  mov     rax, cs:__security_cookie
0x180066537  xor     rax, rsp
0x18006653a  mov     [rbp+420h+var_50], rax
0x180066541  mov     r15, rdx
0x180066544  mov     r14, rcx
0x180066547  xor     edx, edx; hFile
0x180066549  lea     rcx, aAdvapi32; "advapi32"
0x180066550  xor     r8d, r8d; dwFlags
0x180066553  mov     edi, 80004001h
0x180066558  call    cs:__imp_LoadLibraryExW
0x18006655e  xor     esi, esi
0x180066560  mov     r12, rax
0x180066563  test    rax, rax
0x180066566  jz      loc_18006682E
0x18006656c  lea     rdx, aEventregister; "EventRegister"
0x180066573  mov     rcx, rax; hModule
0x180066576  call    cs:__imp_GetProcAddress
0x18006657c  lea     rdx, aEventunregiste; "EventUnregister"
0x180066583  mov     rcx, r12; hModule
0x180066586  mov     rbx, rax
0x180066589  call    cs:__imp_GetProcAddress
0x18006658f  lea     rdx, aEventwrite; "EventWrite"
0x180066596  mov     rcx, r12; hModule
0x180066599  mov     r13, rax
0x18006659c  call    cs:__imp_GetProcAddress
0x1800665a2  mov     [rsp+520h+var_4C8], rax
0x1800665a7  test    rbx, rbx
0x1800665aa  jz      loc_180066825
0x1800665b0  test    r13, r13
0x1800665b3  jz      loc_180066825
0x1800665b9  test    rax, rax
0x1800665bc  jz      loc_180066825
0x1800665c2  test    r14, r14
0x1800665c5  jz      loc_180066820
0x1800665cb  test    r15, r15
0x1800665ce  jz      loc_180066820
0x1800665d4  lea     r9, [rsp+520h+var_4D8]
0x1800665d9  mov     [rsp+520h+var_4D8], rsi
0x1800665de  xor     r8d, r8d
0x1800665e1  lea     rcx, WPCPROV
0x1800665e8  xor     edx, edx
0x1800665ea  mov     rax, rbx
0x1800665ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665f2  mov     edi, eax
0x1800665f4  test    eax, eax
0x1800665f6  jz      short loc_18006660C
0x1800665f8  jle     loc_180066825
0x1800665fe  movzx   edi, ax
0x180066601  or      edi, 80070000h
0x180066607  jmp     loc_180066825
0x18006660c  mov     r8d, 104h; nSize
0x180066612  mov     [rbp+420h+Filename], si
0x180066616  lea     rdx, [rbp+420h+Filename]; lpFilename
0x18006661a  xor     ecx, ecx; hModule
0x18006661c  call    cs:__imp_GetModuleFileNameW
0x180066622  test    eax, eax
0x180066624  jnz     short loc_180066644
0x180066626  call    cs:__imp_GetLastError
0x18006662c  mov     edi, eax
0x18006662e  test    eax, eax
0x180066630  jle     loc_180066811
0x180066636  movzx   edi, ax
0x180066639  or      edi, 80070000h
0x18006663f  jmp     loc_180066811
0x180066644  lea     r8, [rsp+520h+dwHandle]; lpdwHandle
0x180066649  mov     [rbp+420h+var_260], si
0x180066650  lea     rdx, [rbp+420h+Filename]; lpwstrFilename
0x180066654  mov     [rsp+520h+dwHandle], esi
0x180066658  mov     ecx, 1; dwFlags
0x18006665d  mov     edi, esi
0x18006665f  call    cs:__imp_GetFileVersionInfoSizeExW
0x180066665  xor     ebx, ebx
0x180066667  mov     esi, eax
0x180066669  test    eax, eax
0x18006666b  jz      loc_18006671C
0x180066671  call    cs:__imp_GetProcessHeap
0x180066677  mov     r8d, esi; dwBytes
0x18006667a  lea     edx, [rbx+8]; dwFlags
0x18006667d  mov     rcx, rax; hHeap
0x180066680  call    cs:__imp_HeapAlloc
0x180066686  mov     rbx, rax
0x180066689  test    rax, rax
0x18006668c  jz      loc_18006671C
0x180066692  mov     r8d, [rsp+520h+dwHandle]; dwHandle
0x180066697  lea     rdx, [rbp+420h+Filename]; lpwstrFilename
0x18006669b  mov     r9d, esi; dwLen
0x18006669e  mov     [rsp+520h+lpData], rax; lpData
0x1800666a3  mov     ecx, 3; dwFlags
0x1800666a8  call    cs:__imp_GetFileVersionInfoExW
0x1800666ae  xor     esi, esi
0x1800666b0  test    eax, eax
0x1800666b2  jz      short loc_18006671E
0x1800666b4  lea     r9, [rsp+520h+puLen]; puLen
0x1800666b9  mov     [rsp+520h+puLen], esi
0x1800666bd  lea     r8, [rsp+520h+lpBuffer]; lplpBuffer
0x1800666c2  mov     [rsp+520h+lpBuffer], rsi
0x1800666c7  lea     rdx, Delimiter; "\\"
0x1800666ce  mov     rcx, rbx; pBlock
0x1800666d1  call    cs:__imp_VerQueryValueW
0x1800666d7  mov     r9, [rsp+520h+lpBuffer]
0x1800666dc  test    r9, r9
0x1800666df  jz      short loc_18006671E
0x1800666e1  movzx   ecx, word ptr [r9+0Eh]
0x1800666e6  mov     edx, 104h; unsigned __int64
0x1800666eb  movzx   r8d, word ptr [r9+8]
0x1800666f0  movzx   eax, word ptr [r9+0Ch]
0x1800666f5  movzx   r9d, word ptr [r9+0Ah]
0x1800666fa  mov     [rsp+520h+var_4F0], eax
0x1800666fe  mov     [rsp+520h+var_4F8], ecx
0x180066702  lea     rcx, [rbp+420h+var_260]; unsigned __int16 *
0x180066709  mov     dword ptr [rsp+520h+lpData], r8d
0x18006670e  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180066715  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006671a  jmp     short loc_18006671E
0x18006671c  xor     esi, esi
0x18006671e  lea     rcx, [rbp+420h+Filename]; pszPath
0x180066722  call    cs:__imp_PathFindFileNameW
0x180066728  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006672c  mov     [rsp+520h+var_4C0], r14
0x180066731  mov     rdx, rax
0x180066734  mov     rax, rcx
0x180066737  inc     rax
0x18006673a  cmp     [r14+rax*2], si
0x18006673f  jnz     short loc_180066737
0x180066741  lea     eax, ds:2[rax*2]
0x180066748  mov     [rsp+520h+var_4B4], esi
0x18006674c  mov     [rsp+520h+var_4B8], eax
0x180066750  mov     rax, rcx
0x180066753  inc     rax
0x180066756  cmp     [rdx+rax*2], si
0x18006675a  jnz     short loc_180066753
0x18006675c  lea     eax, ds:2[rax*2]
0x180066763  mov     [rsp+520h+var_4B0], rdx
0x180066768  mov     [rsp+520h+var_4A8], eax
0x18006676c  lea     rdx, [rbp+420h+var_260]
0x180066773  lea     rax, [rbp+420h+var_260]
0x18006677a  mov     [rsp+520h+var_4A4], esi
0x18006677e  mov     [rbp+420h+var_4A0], rax
0x180066782  mov     rax, rcx
0x180066785  inc     rax
0x180066788  cmp     [rdx+rax*2], si
0x18006678c  jnz     short loc_180066785
0x18006678e  lea     eax, ds:2[rax*2]
0x180066795  mov     [rbp+420h+var_494], esi
0x180066798  mov     [rbp+420h+var_498], eax
0x18006679b  lea     rax, [rbp+420h+arg_10]
0x1800667a2  mov     [rbp+420h+var_490], rax
0x1800667a6  mov     [rbp+420h+var_488], 4
0x1800667ae  mov     [rbp+420h+var_480], r15
0x1800667b2  inc     rcx
0x1800667b5  cmp     [r15+rcx*2], si
0x1800667ba  jnz     short loc_1800667B2
0x1800667bc  lea     eax, ds:2[rcx*2]
0x1800667c3  mov     [rbp+420h+var_474], esi
0x1800667c6  mov     rcx, [rsp+520h+var_4D8]
0x1800667cb  lea     r9, [rsp+520h+var_4C0]
0x1800667d0  mov     [rbp+420h+var_478], eax
0x1800667d3  lea     rdx, WPCEVENT_WEB_FILEDOWNLOAD
0x1800667da  mov     rax, [rsp+520h+var_4C8]
0x1800667df  mov     r8d, 5
0x1800667e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667ea  test    eax, eax
0x1800667ec  jz      short loc_1800667FD
0x1800667ee  jg      short loc_1800667F4
0x1800667f0  mov     edi, eax
0x1800667f2  jmp     short loc_1800667FD
0x1800667f4  movzx   edi, ax
0x1800667f7  or      edi, 80070000h
0x1800667fd  call    cs:__imp_GetProcessHeap
0x180066803  mov     r8, rbx; lpMem
0x180066806  xor     edx, edx; dwFlags
0x180066808  mov     rcx, rax; hHeap
0x18006680b  call    cs:__imp_HeapFree
0x180066811  mov     rcx, [rsp+520h+var_4D8]
0x180066816  mov     rax, r13
0x180066819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006681e  jmp     short loc_180066825
0x180066820  mov     edi, 80070057h
0x180066825  mov     rcx, r12; hLibModule
0x180066828  call    cs:__imp_FreeLibrary
0x18006682e  mov     eax, edi
0x180066830  mov     rcx, [rbp+420h+var_50]
0x180066837  xor     rcx, rsp; StackCookie
0x18006683a  call    __security_check_cookie
0x18006683f  add     rsp, 4E8h
0x180066846  pop     r15
0x180066848  pop     r14
0x18006684a  pop     r13
0x18006684c  pop     r12
0x18006684e  pop     rdi
0x18006684f  pop     rsi
0x180066850  pop     rbx
0x180066851  pop     rbp
0x180066852  retn
```
