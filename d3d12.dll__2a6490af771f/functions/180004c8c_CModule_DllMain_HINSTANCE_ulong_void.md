# CModule::DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180004c8c`
- end: `0x1800050bb`
- name: `?DllMain@CModule@@QEAAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `1071`
- prototype: `int(CModule *__hidden this, HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004ba8`

## callees

- `0x180004c8c`
- `0x180006c20`
- `0x18000ae80`
- `0x18000b410`
- `0x18000ff90`
- `0x180013750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004d93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004d93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180004d2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180004d2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004fc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004fc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d68`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004f41`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004f70`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000507b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004f41`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004f70`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000507b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000506a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000506a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180004e71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180004e71`

## string_xrefs

- `0x180004fbb`: `D3D12SDKPath`

## pseudocode

```c
__int64 __fastcall CModule::DllMain(CModule *this, HINSTANCE a2, int a3, void *a4)
{
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  FARPROC ProcAddress; // rax
  unsigned int *v12; // rbx
  HANDLE v13; // rax
  WCHAR *v14; // rdi
  unsigned int v15; // ebp
  DWORD ModuleFileNameW; // eax
  DWORD v17; // ecx
  bool v18; // zf
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // r14
  DWORD v22; // ebx
  DWORD v23; // eax
  DWORD v24; // ecx
  __int64 v25; // rcx
  int i; // eax
  unsigned int v27; // ebx
  WCHAR *v28; // r14
  UINT v29; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // r8d
  unsigned int v34; // ecx
  unsigned int v35; // eax
  HANDLE v36; // rax
  WCHAR *v37; // rax
  HANDLE v38; // rax
  WCHAR *v39; // rax
  HANDLE v40; // rax
  const char **v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r9
  HANDLE v44; // rax
  WCHAR *v45; // rax
  const char *v46; // [rsp+28h] [rbp-80h]
  HMODULE phModule; // [rsp+38h] [rbp-70h] BYREF
  int v48[4]; // [rsp+40h] [rbp-68h] BYREF
  __m128i si128; // [rsp+50h] [rbp-58h]
  __m128i v50; // [rsp+60h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( !a3 )
  {
    if ( !a4 )
    {
      v6 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
    }
    return 1;
  }
  if ( a3 != 1 )
    return 1;
  phModule = 0;
  if ( GetModuleHandleExA(2u, 0, &phModule) )
  {
    ProcAddress = GetProcAddress(phModule, "D3D12SDKVersion");
    v12 = (unsigned int *)ProcAddress;
    if ( ProcAddress )
    {
      HIDWORD(qword_18001E828) = *(_DWORD *)ProcAddress;
      v41 = (const char **)GetProcAddress(phModule, "D3D12SDKPath");
      if ( !v41 )
      {
        *(__m128i *)v48 = _mm_load_si128((const __m128i *)&_xmm);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v50 = _mm_load_si128((const __m128i *)&_xmm);
        CJournal::RecordJournal(v42, -2005008381, (const char *)v48, v43, 1);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x96,
          (unsigned int)"Microsoft.Direct3DUndocked\\src\\D3D\\module.cpp",
          (const char *)0x887E0003LL,
          (int)v48,
          v46);
        return 0;
      }
      if ( (int)CModule::SetSDKVersion((CModule *)&g_Module, *v12, *v41) < 0 )
        return 0;
    }
    v13 = GetProcessHeap();
    v14 = (WCHAR *)HeapAlloc(v13, 0, 0x208u);
    if ( v14 )
    {
      v15 = 260;
      while ( 1 )
      {
        if ( v15 >= 2 )
        {
          ModuleFileNameW = GetModuleFileNameW(0, v14, v15 - 2);
          v17 = ModuleFileNameW;
          LODWORD(qword_18001E818) = ModuleFileNameW;
          if ( ModuleFileNameW != v15 - 2 )
            break;
        }
        v15 += 260;
        v36 = GetProcessHeap();
        v37 = (WCHAR *)HeapReAlloc(v36, 0, v14, 2LL * v15);
        if ( !v37 )
        {
LABEL_40:
          v40 = GetProcessHeap();
          HeapFree(v40, 0, v14);
          return 0;
        }
        v14 = v37;
      }
      if ( ModuleFileNameW )
      {
        do
        {
          if ( v14[v17] == 92 )
            break;
          v18 = v17-- == 1;
          LODWORD(qword_18001E818) = v17;
        }
        while ( !v18 );
      }
      v19 = v17 + 1;
      LODWORD(qword_18001E818) = v19;
      v14[v19] = 0;
      v20 = qword_18001E818 + 1;
      LODWORD(qword_18001E818) = qword_18001E818 + 1;
      while ( 1 )
      {
        if ( v15 - v20 >= 2 )
        {
          v21 = v20;
          v22 = v15 - v20 - 2;
          v23 = GetModuleFileNameW(a2, &v14[v20], v22);
          v24 = v23;
          HIDWORD(qword_18001E818) = v23;
          if ( v23 != v22 )
            break;
        }
        v15 += 260;
        v38 = GetProcessHeap();
        v39 = (WCHAR *)HeapReAlloc(v38, 0, v14, 2LL * v15);
        if ( !v39 )
          goto LABEL_40;
        v14 = v39;
        v20 = qword_18001E818;
      }
      if ( v23 )
      {
        do
        {
          if ( v14[v21 + v24] == 92 )
            break;
          v18 = v24-- == 1;
          HIDWORD(qword_18001E818) = v24;
        }
        while ( !v18 );
      }
      v25 = v24 + 1;
      HIDWORD(qword_18001E818) = v25;
      v14[v21 + v25] = 0;
      for ( i = ++HIDWORD(qword_18001E818); ; i = HIDWORD(qword_18001E818) )
      {
        v27 = v15 - i - qword_18001E818;
        if ( v27 >= 2 )
        {
          v28 = &v14[(unsigned int)(qword_18001E818 + i)];
          v29 = v27 - 2;
          SystemDirectoryW = GetSystemDirectoryW(v28, v29);
          LODWORD(qword_18001E820) = SystemDirectoryW;
          if ( SystemDirectoryW < v29 )
            break;
        }
        v15 += 260;
        v44 = GetProcessHeap();
        v45 = (WCHAR *)HeapReAlloc(v44, 0, v14, 2LL * v15);
        if ( !v45 )
          goto LABEL_40;
        v14 = v45;
      }
      if ( v28[SystemDirectoryW] || SystemDirectoryW <= 1 )
      {
        *v28 = 0;
        LODWORD(qword_18001E820) = 1;
        v33 = 1;
      }
      else
      {
        v31 = SystemDirectoryW - 1;
        LODWORD(qword_18001E820) = SystemDirectoryW - 1;
        if ( v28[v31] != 92 )
        {
          LODWORD(qword_18001E820) = SystemDirectoryW;
          v28[SystemDirectoryW] = 92;
          LODWORD(v31) = qword_18001E820;
        }
        v32 = (unsigned int)(v31 + 1);
        LODWORD(qword_18001E820) = v32;
        v28[v32] = 0;
        LODWORD(qword_18001E820) = qword_18001E820 + 1;
        v33 = qword_18001E820;
      }
      lpMem = v14;
      v34 = qword_18001E818;
      *(&lpMem + 1) = &v14[(unsigned int)qword_18001E818];
      qword_18001E810 = (__int64)&v14[(unsigned int)qword_18001E818 + (unsigned __int64)HIDWORD(qword_18001E818)];
      v35 = qword_18001E818;
      if ( (unsigned int)qword_18001E818 <= HIDWORD(qword_18001E818) )
        v35 = HIDWORD(qword_18001E818);
      if ( v35 > v33 )
      {
        if ( (unsigned int)qword_18001E818 <= HIDWORD(qword_18001E818) )
          v34 = HIDWORD(qword_18001E818);
      }
      else
      {
        v34 = v33;
      }
      HIDWORD(qword_18001E820) = v34;
      return 1;
    }
  }
  else
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, v8, v9, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180004c8c  mov     [rsp+arg_0], rbx
0x180004c91  mov     [rsp+arg_10], rbp
0x180004c96  push    rdi
0x180004c97  push    r12
0x180004c99  push    r13
0x180004c9b  push    r14
0x180004c9d  push    r15
0x180004c9f  sub     rsp, 80h
0x180004ca6  mov     rax, cs:__security_cookie
0x180004cad  xor     rax, rsp
0x180004cb0  mov     [rsp+0A8h+var_38], rax
0x180004cb5  mov     r15, rdx
0x180004cb8  xor     r12d, r12d
0x180004cbb  test    r8d, r8d
0x180004cbe  jz      short loc_180004CF5
0x180004cc0  cmp     r8d, 1
0x180004cc4  jz      short loc_180004D1C
0x180004cc6  mov     eax, 1
0x180004ccb  mov     rcx, [rsp+0A8h+var_38]
0x180004cd0  xor     rcx, rsp; StackCookie
0x180004cd3  call    __security_check_cookie
0x180004cd8  lea     r11, [rsp+0A8h+var_28]
0x180004ce0  mov     rbx, [r11+30h]
0x180004ce4  mov     rbp, [r11+40h]
0x180004ce8  mov     rsp, r11
0x180004ceb  pop     r15
0x180004ced  pop     r14
0x180004cef  pop     r13
0x180004cf1  pop     r12
0x180004cf3  pop     rdi
0x180004cf4  retn
0x180004cf5  test    r9, r9
0x180004cf8  jnz     short loc_180004CC6
0x180004cfa  mov     rbx, qword ptr cs:lpMem
0x180004d01  test    rbx, rbx
0x180004d04  jz      short loc_180004CC6
0x180004d06  call    cs:__imp_GetProcessHeap
0x180004d0c  mov     r8, rbx; lpMem
0x180004d0f  xor     edx, edx; dwFlags
0x180004d11  mov     rcx, rax; hHeap
0x180004d14  call    cs:__imp_HeapFree
0x180004d1a  jmp     short loc_180004CC6
0x180004d1c  mov     [rsp+0A8h+phModule], r12
0x180004d21  lea     r8, [rsp+0A8h+phModule]; phModule
0x180004d26  xor     edx, edx; lpModuleName
0x180004d28  lea     ecx, [rdx+2]; dwFlags
0x180004d2b  call    cs:__imp_GetModuleHandleExA
0x180004d31  test    eax, eax
0x180004d33  jz      loc_180004F89
0x180004d39  lea     rdx, ProcName; "D3D12SDKVersion"
0x180004d40  mov     rcx, [rsp+0A8h+phModule]; hModule
0x180004d45  call    cs:__imp_GetProcAddress
0x180004d4b  mov     rbx, rax
0x180004d4e  test    rax, rax
0x180004d51  jnz     loc_180004FB3
0x180004d57  call    cs:__imp_GetProcessHeap
0x180004d5d  mov     rcx, rax; hHeap
0x180004d60  xor     edx, edx; dwFlags
0x180004d62  mov     r8d, 208h; dwBytes
0x180004d68  call    cs:__imp_HeapAlloc
0x180004d6e  mov     rdi, rax
0x180004d71  test    rax, rax
0x180004d74  jz      loc_180004FAC
0x180004d7a  mov     ebp, 104h
0x180004d7f  cmp     ebp, 2
0x180004d82  jb      loc_180004F25
0x180004d88  lea     ebx, [rbp-2]
0x180004d8b  mov     r8d, ebx; nSize
0x180004d8e  mov     rdx, rdi; lpFilename
0x180004d91  xor     ecx, ecx; hModule
0x180004d93  call    cs:__imp_GetModuleFileNameW
0x180004d99  mov     ecx, eax
0x180004d9b  mov     dword ptr cs:qword_18001E818, eax
0x180004da1  cmp     eax, ebx
0x180004da3  jz      loc_180004F25
0x180004da9  mov     r13d, 5Ch ; '\'
0x180004daf  test    eax, eax
0x180004db1  jz      short loc_180004DC7
0x180004db3  mov     eax, ecx
0x180004db5  cmp     [rdi+rax*2], r13w
0x180004dba  jz      short loc_180004DC7
0x180004dbc  add     ecx, 0FFFFFFFFh
0x180004dbf  mov     dword ptr cs:qword_18001E818, ecx
0x180004dc5  jnz     short loc_180004DB3
0x180004dc7  inc     ecx
0x180004dc9  mov     dword ptr cs:qword_18001E818, ecx
0x180004dcf  mov     [rdi+rcx*2], r12w
0x180004dd4  mov     eax, dword ptr cs:qword_18001E818
0x180004dda  inc     eax
0x180004ddc  mov     dword ptr cs:qword_18001E818, eax
0x180004de2  mov     ebx, ebp
0x180004de4  sub     ebx, eax
0x180004de6  cmp     ebx, 2
0x180004de9  jb      loc_180004F54
0x180004def  mov     r14d, eax
0x180004df2  add     ebx, 0FFFFFFFEh
0x180004df5  lea     rdx, [rdi+r14*2]; lpFilename
0x180004df9  mov     r8d, ebx; nSize
0x180004dfc  mov     rcx, r15; hModule
0x180004dff  call    cs:__imp_GetModuleFileNameW
0x180004e05  mov     ecx, eax
0x180004e07  mov     dword ptr cs:qword_18001E818+4, eax
0x180004e0d  cmp     eax, ebx
0x180004e0f  jz      loc_180004F54
0x180004e15  test    eax, eax
0x180004e17  jz      short loc_180004E30
0x180004e19  mov     eax, ecx
0x180004e1b  add     rax, r14
0x180004e1e  cmp     [rdi+rax*2], r13w
0x180004e23  jz      short loc_180004E30
0x180004e25  add     ecx, 0FFFFFFFFh
0x180004e28  mov     dword ptr cs:qword_18001E818+4, ecx
0x180004e2e  jnz     short loc_180004E19
0x180004e30  inc     ecx
0x180004e32  mov     dword ptr cs:qword_18001E818+4, ecx
0x180004e38  add     rcx, r14
0x180004e3b  mov     [rdi+rcx*2], r12w
0x180004e40  mov     eax, dword ptr cs:qword_18001E818+4
0x180004e46  inc     eax
0x180004e48  mov     dword ptr cs:qword_18001E818+4, eax
0x180004e4e  mov     ebx, ebp
0x180004e50  sub     ebx, eax
0x180004e52  mov     ecx, dword ptr cs:qword_18001E818
0x180004e58  sub     ebx, ecx
0x180004e5a  cmp     ebx, 2
0x180004e5d  jb      loc_18000505F
0x180004e63  add     eax, ecx
0x180004e65  lea     r14, [rdi+rax*2]
0x180004e69  add     ebx, 0FFFFFFFEh
0x180004e6c  mov     edx, ebx; uSize
0x180004e6e  mov     rcx, r14; lpBuffer
0x180004e71  call    cs:__imp_GetSystemDirectoryW
0x180004e77  mov     edx, eax
0x180004e79  mov     dword ptr cs:qword_18001E820, edx
0x180004e7f  cmp     eax, ebx
0x180004e81  jnb     loc_18000505F
0x180004e87  cmp     [r14+rdx*2], r12w
0x180004e8c  jnz     loc_180005098
0x180004e92  cmp     edx, 1
0x180004e95  jbe     loc_180005098
0x180004e9b  lea     ecx, [rdx-1]
0x180004e9e  mov     dword ptr cs:qword_18001E820, ecx
0x180004ea4  cmp     [r14+rcx*2], r13w
0x180004ea9  jz      short loc_180004EBC
0x180004eab  mov     dword ptr cs:qword_18001E820, edx
0x180004eb1  mov     [r14+rdx*2], r13w
0x180004eb6  mov     ecx, dword ptr cs:qword_18001E820
0x180004ebc  inc     ecx
0x180004ebe  mov     dword ptr cs:qword_18001E820, ecx
0x180004ec4  mov     [r14+rcx*2], r12w
0x180004ec9  mov     eax, dword ptr cs:qword_18001E820
0x180004ecf  inc     eax
0x180004ed1  mov     dword ptr cs:qword_18001E820, eax
0x180004ed7  mov     r8d, eax
0x180004eda  mov     qword ptr cs:lpMem, rdi
0x180004ee1  mov     ecx, dword ptr cs:qword_18001E818
0x180004ee7  lea     rax, [rdi+rcx*2]
0x180004eeb  mov     qword ptr cs:lpMem+8, rax
0x180004ef2  mov     edx, dword ptr cs:qword_18001E818+4
0x180004ef8  lea     rax, [rcx+rdx]
0x180004efc  lea     rax, [rdi+rax*2]
0x180004f00  mov     cs:qword_18001E810, rax
0x180004f07  mov     eax, ecx
0x180004f09  cmp     ecx, edx
0x180004f0b  cmovbe  eax, edx
0x180004f0e  cmp     eax, r8d
0x180004f11  ja      loc_1800050B1
0x180004f17  mov     ecx, r8d
0x180004f1a  mov     dword ptr cs:qword_18001E820+4, ecx
0x180004f20  jmp     loc_180004CC6
0x180004f25  add     ebp, 104h
0x180004f2b  mov     ebx, ebp
0x180004f2d  add     rbx, rbx
0x180004f30  call    cs:__imp_GetProcessHeap
0x180004f36  mov     rcx, rax; hHeap
0x180004f39  mov     r9, rbx; dwBytes
0x180004f3c  mov     r8, rdi; lpMem
0x180004f3f  xor     edx, edx; dwFlags
0x180004f41  call    cs:__imp_HeapReAlloc
0x180004f47  test    rax, rax
0x180004f4a  jz      short loc_180004F98
0x180004f4c  mov     rdi, rax
0x180004f4f  jmp     loc_180004D7F
0x180004f54  add     ebp, 104h
0x180004f5a  mov     ebx, ebp
0x180004f5c  add     rbx, rbx
0x180004f5f  call    cs:__imp_GetProcessHeap
0x180004f65  mov     rcx, rax; hHeap
0x180004f68  mov     r9, rbx; dwBytes
0x180004f6b  mov     r8, rdi; lpMem
0x180004f6e  xor     edx, edx; dwFlags
0x180004f70  call    cs:__imp_HeapReAlloc
0x180004f76  test    rax, rax
0x180004f79  jz      short loc_180004F98
0x180004f7b  mov     rdi, rax
0x180004f7e  mov     eax, dword ptr cs:qword_18001E818
0x180004f84  jmp     loc_180004DE2
0x180004f89  mov     rcx, [rsp+0A8h]; this
0x180004f91  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180004f96  jmp     short loc_180004FAC
0x180004f98  call    cs:__imp_GetProcessHeap
0x180004f9e  mov     rcx, rax; hHeap
0x180004fa1  mov     r8, rdi; lpMem
0x180004fa4  xor     edx, edx; dwFlags
0x180004fa6  call    cs:__imp_HeapFree
0x180004fac  xor     eax, eax
0x180004fae  jmp     loc_180004CCB
0x180004fb3  mov     ecx, [rax]
0x180004fb5  mov     dword ptr cs:qword_18001E828+4, ecx
0x180004fbb  lea     rdx, aD3d12sdkpath; "D3D12SDKPath"
0x180004fc2  mov     rcx, [rsp+0A8h+phModule]; hModule
0x180004fc7  call    cs:__imp_GetProcAddress
0x180004fcd  test    rax, rax
0x180004fd0  jnz     short loc_180005041
0x180004fd2  movdqa  xmm0, cs:__xmm@4b4453323144334420676e697373694d
0x180004fda  movdqu  xmmword ptr [rsp+0A8h+var_68], xmm0
0x180004fe0  movdqa  xmm1, cs:__xmm@747369646572206d6f72662068746150
0x180004fe8  movdqu  [rsp+0A8h+var_58], xmm1
0x180004fee  movdqa  xmm0, cs:__xmm@002e6e6f69746172756769666e6f6320
0x180004ff6  movdqu  [rsp+0A8h+var_48], xmm0
0x180004ffc  mov     [rsp+0A8h+var_88], 1
0x180005004  lea     r8, [rsp+0A8h+var_68]
0x180005009  mov     edx, 887E0003h
0x18000500e  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x180005013  mov     rcx, [rsp+0A8h]; this
0x18000501b  lea     rax, [rsp+0A8h+var_68]
0x180005020  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180005025  mov     r9d, 887E0003h; char *
0x18000502b  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\D3D\\m"...
0x180005032  mov     edx, 96h; void *
0x180005037  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000503c  jmp     loc_180004FAC
0x180005041  mov     r8, [rax]; char *
0x180005044  mov     edx, [rbx]; unsigned int
0x180005046  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18000504d  call    ?SetSDKVersion@CModule@@QEAAJIPEBD@Z; CModule::SetSDKVersion(uint,char const *)
0x180005052  test    eax, eax
0x180005054  js      loc_180004FAC
0x18000505a  jmp     loc_180004D57
0x18000505f  add     ebp, 104h
0x180005065  mov     ebx, ebp
0x180005067  add     rbx, rbx
0x18000506a  call    cs:__imp_GetProcessHeap
0x180005070  mov     rcx, rax; hHeap
0x180005073  mov     r9, rbx; dwBytes
0x180005076  mov     r8, rdi; lpMem
0x180005079  xor     edx, edx; dwFlags
0x18000507b  call    cs:__imp_HeapReAlloc
0x180005081  test    rax, rax
0x180005084  jz      loc_180004F98
0x18000508a  mov     rdi, rax
0x18000508d  mov     eax, dword ptr cs:qword_18001E818+4
0x180005093  jmp     loc_180004E4E
0x180005098  mov     [r14], r12w
0x18000509c  mov     dword ptr cs:qword_18001E820, 1
0x1800050a6  mov     r8d, 1
0x1800050ac  jmp     loc_180004EDA
0x1800050b1  cmp     ecx, edx
0x1800050b3  cmovbe  ecx, edx
0x1800050b6  jmp     loc_180004F1A
```
