# GetAppCompatString(unsigned __int64 *,char *,bool)

- ea: `0x1800647a0`
- end: `0x180064dd4`
- name: `?GetAppCompatString@@YAHPEA_KPEAD_N@Z`
- size: `1588`
- prototype: `__int64 __fastcall(unsigned __int64 *, char *, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001ca00`
- `0x18008cf94`

## callees

- `0x180034c9c`
- `0x180035040`
- `0x180057b20`
- `0x1800647a0`
- `0x18006f908`
- `0x180075fa0`
- `0x180076440`
- `0x180076f08`
- `0x180076f20`
- `0x18007bf63`
- `0x180092048`
- `0x180092260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180064853`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180064853`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064d10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064d87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064d10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064d87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006481b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006481b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ad1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064b86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ad1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064b86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064ac3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064b78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064ac3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800648b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800648b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18006498b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180064c77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18006498b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180064c77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064cbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064cbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180064956`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180064956`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800648a9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800648a9`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180064891`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180064891`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAppCompatString(unsigned __int64 *a1, char *a2, char a3)
{
  char v3; // r15
  char *v4; // rsi
  unsigned __int64 *v5; // r14
  DWORD ModuleFileNameA; // edi
  HANDLE FileA; // rax
  void *v8; // rbx
  DWORD FileSize; // esi
  unsigned __int64 v10; // rdx
  const char *v11; // rcx
  HKEY v12; // rsi
  unsigned __int64 v13; // rdi
  size_t v14; // r15
  size_t v15; // r15
  size_t v16; // r13
  char **v17; // rax
  size_t v18; // r12
  char **v19; // rbx
  char *v20; // rbx
  __int64 v21; // rbx
  unsigned __int64 v22; // rdx
  _QWORD *v23; // r14
  SIZE_T v24; // rdi
  HANDLE v25; // rax
  LPVOID v26; // rax
  unsigned __int64 v27; // r15
  char *v28; // rbx
  _BYTE *v29; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r14d
  char *v32; // rbx
  char *v33; // rcx
  char **v34; // rcx
  char **v35; // r8
  bool v37; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  char v39; // [rsp+48h] [rbp-B8h]
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  _RTL_CRITICAL_SECTION *v43; // [rsp+60h] [rbp-A0h]
  char v44; // [rsp+68h] [rbp-98h]
  void *v45; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v46; // [rsp+78h] [rbp-88h]
  CHAR pExceptionObject[32]; // [rsp+80h] [rbp-80h] BYREF
  CHAR Filename[272]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR SubKey[272]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v50[272]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = a3;
  v39 = a3;
  v4 = a2;
  v45 = a2;
  v5 = a1;
  v46 = a1;
  if ( !a1 )
    return 0;
  if ( a2 && *a1 )
    *a2 = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::GetImpl'::`2'::impl);
  v43 = &CriticalSection;
  EnterCriticalSection(&CriticalSection);
  v44 = 1;
  if ( g_AttemptReadString )
  {
    v13 = g_ShimmedAppCompatStringBufferLength;
    v32 = g_ShimmedAppCompatString;
    goto LABEL_71;
  }
  Type = 0;
  cbData = 0;
  ModuleFileNameA = GetModuleFileNameA(0, Filename, 0x104u);
  if ( !ModuleFileNameA )
    goto LABEL_15;
  Filename[260] = 0;
  FileA = CreateFileA(Filename, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v8 = FileA;
  if ( FileA == (HANDLE)-1LL )
    goto LABEL_15;
  FileSize = GetFileSize(FileA, 0);
  CloseHandle(v8);
  v10 = ModuleFileNameA + 1;
  if ( v10 > 0x105
    || (StringCchCopyA(v50, v10, Filename),
        phkResult = 0,
        memset_0(SubKey, 0, 0x105u),
        v41 = 261,
        v37 = 0,
        !FindAppRegKey(v11, SubKey, &v41, &v37, v50, FileSize))
    || RegOpenKeyExA((HKEY)(-(__int64)v37 - 2147483646), SubKey, 0, 1u, &phkResult) )
  {
LABEL_15:
    v12 = 0;
  }
  else
  {
    v12 = phkResult;
    if ( phkResult && (RegQueryValueExA(phkResult, "D3DBehaviors", 0, &Type, 0, &cbData) || Type != 1) )
      cbData = 0;
  }
  v13 = g_ShimmedAppCompatStringBufferLength;
  if ( g_ShimmedAppCompatStringBufferLength + cbData < g_ShimmedAppCompatStringBufferLength )
    cbData = 0;
  v14 = g_ShimmedAppCompatStringBufferLength + cbData;
  if ( v14 )
  {
    v15 = v14 - 1;
    v16 = Size;
    if ( v15 <= Size )
    {
      Size = v15;
      v17 = &g_CompatStringCache;
      if ( (unsigned __int64)qword_180109990 > 0xF )
        v17 = (char **)g_CompatStringCache;
      *((_BYTE *)v17 + v15) = 0;
      goto LABEL_50;
    }
    v18 = v15 - Size;
    v41 = qword_180109990;
    if ( v15 - Size <= qword_180109990 - Size )
    {
      Size = v15;
      v19 = &g_CompatStringCache;
      if ( (unsigned __int64)qword_180109990 > 0xF )
        v19 = (char **)g_CompatStringCache;
      v20 = (char *)v19 + v16;
      memset_0(v20, 0, v15 - v16);
      v20[v18] = 0;
      goto LABEL_50;
    }
    v21 = 0x7FFFFFFFFFFFFFFFLL;
    if ( 0x7FFFFFFFFFFFFFFFLL - Size < v18 )
      std::_Xlen_string();
    if ( (v15 | 0xF) > 0x7FFFFFFFFFFFFFFFLL
      || (v22 = (unsigned __int64)qword_180109990 >> 1,
          qword_180109990 > 0x7FFFFFFFFFFFFFFFLL - ((unsigned __int64)qword_180109990 >> 1)) )
    {
      v24 = 0x8000000000000027uLL;
    }
    else
    {
      v21 = v15 | 0xF;
      if ( (v15 | 0xF) < v22 + qword_180109990 )
        v21 = v22 + qword_180109990;
      v23 = (_QWORD *)(v21 + 1);
      if ( v21 == -1 )
        goto LABEL_40;
      if ( (unsigned __int64)v23 < 0x1000 )
      {
        ProcessHeap = GetProcessHeap();
        v23 = HeapAlloc(ProcessHeap, 0, v21 + 1);
        if ( !v23 )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
          throw (std::bad_alloc *)pExceptionObject;
        }
        goto LABEL_39;
      }
      v24 = v21 + 40;
      if ( v21 + 40 < (unsigned __int64)(v21 + 1) )
        std::_Throw_bad_array_new_length();
    }
    v25 = GetProcessHeap();
    v26 = HeapAlloc(v25, 0, v24);
    if ( !v26 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v23 = (_QWORD *)(((unsigned __int64)v26 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v23 - 1) = v26;
LABEL_39:
    v13 = g_ShimmedAppCompatStringBufferLength;
LABEL_40:
    Size = v15;
    qword_180109990 = v21;
    v43 = (_RTL_CRITICAL_SECTION *)((char *)v23 + v15);
    v27 = v41;
    if ( v41 <= 0xF )
    {
      memcpy_0(v23, &g_CompatStringCache, v16);
      memset_0((char *)v23 + v16, 0, v18);
      *((_BYTE *)v23 + v16 + v18) = 0;
    }
    else
    {
      v28 = g_CompatStringCache;
      memcpy_0(v23, g_CompatStringCache, v16);
      memset_0((char *)v23 + v16, 0, v18);
      LOBYTE(v43->DebugInfo) = 0;
      if ( v27 + 1 < 0x1000 )
      {
        operator delete(v28, v27 + 1);
        v13 = g_ShimmedAppCompatStringBufferLength;
      }
      else
      {
        v29 = (_BYTE *)*((_QWORD *)v28 - 1);
        if ( (unsigned __int64)(v28 - v29 - 8) > 0x1F )
          __fastfail(5u);
        operator delete(v29, v27 + 40);
        v13 = g_ShimmedAppCompatStringBufferLength;
      }
    }
    g_CompatStringCache = (char *)v23;
  }
LABEL_50:
  v31 = 0;
  v32 = g_ShimmedAppCompatString;
  if ( v13 && g_ShimmedAppCompatString )
  {
    v33 = (char *)&g_CompatStringCache;
    if ( (unsigned __int64)qword_180109990 > 0xF )
      v33 = g_CompatStringCache;
    if ( (int)StringCchCopyA(v33, v13, g_ShimmedAppCompatString) >= 0 )
    {
      v31 = v13;
      g_bCompatStringExists = 1;
    }
  }
  if ( v12 )
  {
    if ( cbData )
    {
      v34 = &g_CompatStringCache;
      if ( (unsigned __int64)qword_180109990 > 0xF )
        v34 = (char **)g_CompatStringCache;
      if ( !RegQueryValueExA(v12, "D3DBehaviors", 0, &Type, (LPBYTE)v34 + v31, &cbData) && Type == 1 && cbData )
      {
        if ( v31 )
        {
          v35 = &g_CompatStringCache;
          if ( (unsigned __int64)qword_180109990 > 0xF )
            v35 = (char **)g_CompatStringCache;
          *((_BYTE *)v35 + v31 - 1) = 59;
        }
        g_bCompatStringExists = 1;
      }
    }
    RegCloseKey(v12);
    v13 = g_ShimmedAppCompatStringBufferLength;
    v32 = g_ShimmedAppCompatString;
  }
  g_AttemptReadString = 1;
  v4 = (char *)v45;
  v5 = v46;
  v3 = v39;
LABEL_71:
  if ( !g_bCompatStringExists )
  {
LABEL_74:
    LeaveCriticalSection(&CriticalSection);
    return 0;
  }
  if ( v3 )
  {
    if ( !v13 )
      goto LABEL_74;
  }
  else
  {
    v13 = Size + 1;
    v32 = (char *)&g_CompatStringCache;
    if ( (unsigned __int64)qword_180109990 > 0xF )
      v32 = g_CompatStringCache;
  }
  if ( v13 && v32 && v4 && *v5 >= v13 )
    memcpy_0(v4, v32, v13);
  *v5 = v13;
  LeaveCriticalSection(&CriticalSection);
  return 1;
}

```

## disassembly

```asm
0x1800647a0  mov     [rsp-8+arg_10], rbx
0x1800647a5  push    rbp
0x1800647a6  push    rsi
0x1800647a7  push    rdi
0x1800647a8  push    r12
0x1800647aa  push    r13
0x1800647ac  push    r14
0x1800647ae  push    r15
0x1800647b0  lea     rbp, [rsp-2E0h]
0x1800647b8  sub     rsp, 3E0h
0x1800647bf  mov     rax, cs:__security_cookie
0x1800647c6  xor     rax, rsp
0x1800647c9  mov     [rbp+310h+var_40], rax
0x1800647d0  movzx   r15d, r8b
0x1800647d4  mov     [rsp+410h+var_3C8], r8b
0x1800647d9  mov     rsi, rdx
0x1800647dc  mov     [rsp+410h+var_3A0], rdx
0x1800647e1  mov     r14, rcx
0x1800647e4  mov     [rsp+410h+var_398], rcx
0x1800647e9  test    rcx, rcx
0x1800647ec  jz      loc_180064D16
0x1800647f2  test    rdx, rdx
0x1800647f5  jz      short loc_180064800
0x1800647f7  cmp     qword ptr [rcx], 1
0x1800647fb  jb      short loc_180064800
0x1800647fd  mov     byte ptr [rdx], 0
0x180064800  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DXGI_CompatShimLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DXGI_CompatShimLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DXGI_CompatShimLogging> `wil::Feature<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::GetImpl(void)'::`2'::impl
0x180064807  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DXGI_CompatShimLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DXGI_CompatShimLogging>::__private_IsEnabled(void)
0x18006480c  lea     r13, CriticalSection
0x180064813  mov     [rsp+410h+var_3B0], r13
0x180064818  mov     rcx, r13; lpCriticalSection
0x18006481b  call    cs:__imp_EnterCriticalSection
0x180064821  mov     [rsp+410h+var_3A8], 1
0x180064826  lea     r12, ?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x18006482d  cmp     cs:?g_AttemptReadString@@3HA, 0; int g_AttemptReadString
0x180064834  jnz     loc_180064CEC
0x18006483a  xor     r15d, r15d
0x18006483d  mov     [rsp+410h+Type], r15d
0x180064842  mov     [rsp+410h+cbData], r15d
0x180064847  mov     r8d, 104h; nSize
0x18006484d  lea     rdx, [rbp+310h+Filename]; lpFilename
0x180064851  xor     ecx, ecx; hModule
0x180064853  call    cs:__imp_GetModuleFileNameA
0x180064859  mov     edi, eax
0x18006485b  test    eax, eax
0x18006485d  jz      loc_1800649A3
0x180064863  mov     [rbp+310h+var_26C], r15b
0x18006486a  mov     [rsp+410h+hTemplateFile], r15; hTemplateFile
0x18006486f  mov     [rsp+410h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180064877  mov     [rsp+410h+dwCreationDisposition], 3; dwCreationDisposition
0x18006487f  xor     r9d, r9d; lpSecurityAttributes
0x180064882  mov     edx, 80000000h; dwDesiredAccess
0x180064887  mov     r8d, 7; dwShareMode
0x18006488d  lea     rcx, [rbp+310h+Filename]; lpFileName
0x180064891  call    cs:__imp_CreateFileA
0x180064897  mov     rbx, rax
0x18006489a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006489e  jz      loc_1800649A3
0x1800648a4  xor     edx, edx; lpFileSizeHigh
0x1800648a6  mov     rcx, rax; hFile
0x1800648a9  call    cs:__imp_GetFileSize
0x1800648af  mov     esi, eax
0x1800648b1  mov     rcx, rbx; hObject
0x1800648b4  call    cs:__imp_CloseHandle
0x1800648ba  lea     edx, [rdi+1]; unsigned __int64
0x1800648bd  cmp     rdx, 105h
0x1800648c4  ja      loc_1800649A3
0x1800648ca  lea     r8, [rbp+310h+Filename]; char *
0x1800648ce  lea     rcx, [rbp+310h+var_150]; char *
0x1800648d5  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800648da  mov     [rsp+410h+phkResult], r15
0x1800648df  xor     edx, edx; Val
0x1800648e1  mov     r8d, 105h; Size
0x1800648e7  lea     rcx, [rbp+310h+SubKey]; void *
0x1800648ee  call    memset_0
0x1800648f3  mov     [rsp+410h+var_3C0], 105h
0x1800648fc  mov     [rsp+410h+var_3D0], r15b
0x180064901  mov     [rsp+410h+dwFlagsAndAttributes], esi; unsigned int
0x180064905  lea     rax, [rbp+310h+var_150]
0x18006490c  mov     qword ptr [rsp+410h+dwCreationDisposition], rax; char *
0x180064911  lea     r9, [rsp+410h+var_3D0]; bool *
0x180064916  lea     r8, [rsp+410h+var_3C0]; unsigned __int64 *
0x18006491b  lea     rdx, [rbp+310h+SubKey]; char *
0x180064922  call    ?FindAppRegKey@@YA_NPEBDPEADPEA_KPEA_N0I@Z; FindAppRegKey(char const *,char *,unsigned __int64 *,bool *,char const *,uint)
0x180064927  test    al, al
0x180064929  jz      short loc_1800649A3
0x18006492b  movzx   eax, [rsp+410h+var_3D0]
0x180064930  neg     al
0x180064932  sbb     rcx, rcx
0x180064935  add     rcx, 0FFFFFFFF80000002h; hKey
0x18006493c  lea     rax, [rsp+410h+phkResult]
0x180064941  mov     qword ptr [rsp+410h+dwCreationDisposition], rax; phkResult
0x180064946  mov     r9d, 1; samDesired
0x18006494c  xor     r8d, r8d; ulOptions
0x18006494f  lea     rdx, [rbp+310h+SubKey]; lpSubKey
0x180064956  call    cs:__imp_RegOpenKeyExA
0x18006495c  test    eax, eax
0x18006495e  jnz     short loc_1800649A3
0x180064960  mov     rsi, [rsp+410h+phkResult]
0x180064965  test    rsi, rsi
0x180064968  jz      short loc_1800649A6
0x18006496a  lea     rax, [rsp+410h+cbData]
0x18006496f  mov     qword ptr [rsp+410h+dwFlagsAndAttributes], rax; lpcbData
0x180064974  mov     qword ptr [rsp+410h+dwCreationDisposition], r15; lpData
0x180064979  lea     r9, [rsp+410h+Type]; lpType
0x18006497e  xor     r8d, r8d; lpReserved
0x180064981  lea     rdx, aD3dbehaviors; "D3DBehaviors"
0x180064988  mov     rcx, rsi; hKey
0x18006498b  call    cs:__imp_RegQueryValueExA
0x180064991  test    eax, eax
0x180064993  jnz     short loc_18006499C
0x180064995  cmp     [rsp+410h+Type], 1
0x18006499a  jz      short loc_1800649A6
0x18006499c  mov     [rsp+410h+cbData], r15d
0x1800649a1  jmp     short loc_1800649A6
0x1800649a3  mov     rsi, r15
0x1800649a6  mov     eax, [rsp+410h+cbData]
0x1800649aa  mov     rdi, cs:?g_ShimmedAppCompatStringBufferLength@@3_KA; unsigned __int64 g_ShimmedAppCompatStringBufferLength
0x1800649b1  add     rax, rdi
0x1800649b4  cmp     rax, rdi
0x1800649b7  jnb     short loc_1800649BE
0x1800649b9  mov     [rsp+410h+cbData], r15d
0x1800649be  mov     r15d, [rsp+410h+cbData]
0x1800649c3  add     r15, rdi
0x1800649c6  jz      loc_180064BEA
0x1800649cc  dec     r15
0x1800649cf  mov     r13, cs:Size
0x1800649d6  cmp     r15, r13
0x1800649d9  ja      short loc_1800649FF
0x1800649db  mov     cs:Size, r15
0x1800649e2  mov     rax, r12
0x1800649e5  cmp     cs:qword_180109990, 0Fh
0x1800649ed  cmova   rax, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x1800649f5  mov     byte ptr [r15+rax], 0
0x1800649fa  jmp     loc_180064BE3
0x1800649ff  mov     r12, r15
0x180064a02  sub     r12, r13
0x180064a05  mov     r14, cs:qword_180109990
0x180064a0c  mov     [rsp+410h+var_3C0], r14
0x180064a11  mov     rax, r14
0x180064a14  sub     rax, r13
0x180064a17  cmp     r12, rax
0x180064a1a  ja      short loc_180064A50
0x180064a1c  mov     cs:Size, r15
0x180064a23  lea     rbx, ?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x180064a2a  cmp     r14, 0Fh
0x180064a2e  cmova   rbx, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x180064a36  add     rbx, r13
0x180064a39  mov     r8, r12; Size
0x180064a3c  xor     edx, edx; Val
0x180064a3e  mov     rcx, rbx; void *
0x180064a41  call    memset_0
0x180064a46  mov     byte ptr [r12+rbx], 0
0x180064a4b  jmp     loc_180064BDC
0x180064a50  mov     rbx, 7FFFFFFFFFFFFFFFh
0x180064a5a  mov     rax, rbx
0x180064a5d  sub     rax, r13
0x180064a60  cmp     rax, r12
0x180064a63  jb      loc_180064DCE
0x180064a69  mov     rcx, r15
0x180064a6c  or      rcx, 0Fh
0x180064a70  cmp     rcx, rbx
0x180064a73  ja      short loc_180064AB9
0x180064a75  mov     rdx, r14
0x180064a78  shr     rdx, 1
0x180064a7b  mov     rax, rbx
0x180064a7e  sub     rax, rdx
0x180064a81  cmp     r14, rax
0x180064a84  ja      short loc_180064AB9
0x180064a86  lea     rax, [rdx+r14]
0x180064a8a  mov     rbx, rcx
0x180064a8d  cmp     rcx, rax
0x180064a90  cmovb   rbx, rax
0x180064a94  lea     r14, [rbx+1]
0x180064a98  test    r14, r14
0x180064a9b  jz      short loc_180064AF3
0x180064a9d  cmp     r14, 1000h
0x180064aa4  jb      loc_180064B78
0x180064aaa  lea     rdi, [r14+27h]
0x180064aae  cmp     rdi, r14
0x180064ab1  jbe     loc_180064DAE
0x180064ab7  jmp     short loc_180064AC3
0x180064ab9  mov     rdi, 8000000000000027h
0x180064ac3  call    cs:__imp_GetProcessHeap
0x180064ac9  mov     rcx, rax; hHeap
0x180064acc  mov     r8, rdi; dwBytes
0x180064acf  xor     edx, edx; dwFlags
0x180064ad1  call    cs:__imp_HeapAlloc
0x180064ad7  test    rax, rax
0x180064ada  jz      loc_180064D94
0x180064ae0  lea     r14, [rax+27h]
0x180064ae4  and     r14, 0FFFFFFFFFFFFFFE0h
0x180064ae8  mov     [r14-8], rax
0x180064aec  mov     rdi, cs:?g_ShimmedAppCompatStringBufferLength@@3_KA; unsigned __int64 g_ShimmedAppCompatStringBufferLength
0x180064af3  mov     cs:Size, r15
0x180064afa  mov     cs:qword_180109990, rbx
0x180064b01  lea     rbx, [r14+r13]
0x180064b05  lea     rax, [r12+rbx]
0x180064b09  mov     [rsp+410h+var_3B0], rax
0x180064b0e  mov     r15, [rsp+410h+var_3C0]
0x180064b13  mov     r8, r13; Size
0x180064b16  mov     rcx, r14; void *
0x180064b19  cmp     r15, 0Fh
0x180064b1d  jbe     loc_180064BB5
0x180064b23  mov     rbx, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x180064b2a  mov     rdx, rbx; Src
0x180064b2d  call    memcpy_0
0x180064b32  mov     r8, r12; Size
0x180064b35  xor     edx, edx; Val
0x180064b37  lea     rcx, [r14+r13]; void *
0x180064b3b  call    memset_0
0x180064b40  mov     rax, [rsp+410h+var_3B0]
0x180064b45  mov     byte ptr [rax], 0
0x180064b48  lea     rdx, [r15+1]; unsigned __int64
0x180064b4c  cmp     rdx, 1000h
0x180064b53  jb      short loc_180064BA4
0x180064b55  mov     rcx, [rbx-8]; void *
0x180064b59  sub     rbx, rcx
0x180064b5c  sub     rbx, 8
0x180064b60  cmp     rbx, 1Fh
0x180064b64  ja      short loc_180064B9D
0x180064b66  add     rdx, 27h ; '''; unsigned __int64
0x180064b6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180064b6f  mov     rdi, cs:?g_ShimmedAppCompatStringBufferLength@@3_KA; unsigned __int64 g_ShimmedAppCompatStringBufferLength
0x180064b76  jmp     short loc_180064BD5
0x180064b78  call    cs:__imp_GetProcessHeap
0x180064b7e  mov     rcx, rax; hHeap
0x180064b81  mov     r8, r14; dwBytes
0x180064b84  xor     edx, edx; dwFlags
0x180064b86  call    cs:__imp_HeapAlloc
0x180064b8c  mov     r14, rax
0x180064b8f  test    rax, rax
0x180064b92  jz      loc_180064DB4
0x180064b98  jmp     loc_180064AEC
0x180064b9d  mov     ecx, 5
0x180064ba2  int     29h; Win8: RtlFailFast(ecx)
0x180064ba4  mov     rcx, rbx; void *
0x180064ba7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180064bac  mov     rdi, cs:?g_ShimmedAppCompatStringBufferLength@@3_KA; unsigned __int64 g_ShimmedAppCompatStringBufferLength
0x180064bb3  jmp     short loc_180064BD5
0x180064bb5  lea     rdx, ?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; Src
0x180064bbc  call    memcpy_0
0x180064bc1  mov     r8, r12; Size
0x180064bc4  xor     edx, edx; Val
0x180064bc6  mov     rcx, rbx; void *
0x180064bc9  call    memset_0
0x180064bce  lea     rax, [r12+rbx]
0x180064bd2  mov     byte ptr [rax], 0
0x180064bd5  mov     cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A, r14; std::string g_CompatStringCache
0x180064bdc  lea     r12, ?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x180064be3  lea     r13, CriticalSection
0x180064bea  xor     r14d, r14d
0x180064bed  mov     rbx, cs:?g_ShimmedAppCompatString@@3PEBDEB; char const * const g_ShimmedAppCompatString
0x180064bf4  test    rdi, rdi
0x180064bf7  jz      short loc_180064C2D
0x180064bf9  test    rbx, rbx
0x180064bfc  jz      short loc_180064C2D
0x180064bfe  mov     rcx, r12
0x180064c01  cmp     cs:qword_180109990, 0Fh
0x180064c09  cmova   rcx, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; char *
0x180064c11  mov     r8, rbx; char *
0x180064c14  mov     rdx, rdi; unsigned __int64
0x180064c17  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180064c1c  test    eax, eax
0x180064c1e  js      short loc_180064C2D
0x180064c20  mov     r14d, edi
0x180064c23  mov     cs:?g_bCompatStringExists@@3HA, 1; int g_bCompatStringExists
0x180064c2d  test    rsi, rsi
0x180064c30  jz      loc_180064CD0
0x180064c36  cmp     [rsp+410h+cbData], 0
0x180064c3b  jz      short loc_180064CB9
0x180064c3d  mov     rcx, r12
0x180064c40  cmp     cs:qword_180109990, 0Fh
0x180064c48  cmova   rcx, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x180064c50  mov     eax, r14d
0x180064c53  add     rax, rcx
0x180064c56  lea     rcx, [rsp+410h+cbData]
0x180064c5b  mov     qword ptr [rsp+410h+dwFlagsAndAttributes], rcx; lpcbData
0x180064c60  mov     qword ptr [rsp+410h+dwCreationDisposition], rax; lpData
0x180064c65  lea     r9, [rsp+410h+Type]; lpType
0x180064c6a  xor     r8d, r8d; lpReserved
0x180064c6d  lea     rdx, aD3dbehaviors; "D3DBehaviors"
0x180064c74  mov     rcx, rsi; hKey
0x180064c77  call    cs:__imp_RegQueryValueExA
0x180064c7d  test    eax, eax
0x180064c7f  jnz     short loc_180064CB9
0x180064c81  cmp     [rsp+410h+Type], 1
0x180064c86  jnz     short loc_180064CB9
0x180064c88  cmp     [rsp+410h+cbData], eax
0x180064c8c  jz      short loc_180064CB9
0x180064c8e  test    r14d, r14d
0x180064c91  jz      short loc_180064CAF
0x180064c93  mov     r8, r12
0x180064c96  cmp     cs:qword_180109990, 0Fh
0x180064c9e  cmova   r8, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x180064ca6  lea     eax, [r14-1]
0x180064caa  mov     byte ptr [rax+r8], 3Bh ; ';'
0x180064caf  mov     cs:?g_bCompatStringExists@@3HA, 1; int g_bCompatStringExists
0x180064cb9  mov     rcx, rsi; hKey
0x180064cbc  call    cs:__imp_RegCloseKey
  ... truncated ...
```
