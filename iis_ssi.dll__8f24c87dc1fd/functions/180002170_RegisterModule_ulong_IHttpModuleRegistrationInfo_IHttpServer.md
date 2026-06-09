# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002170`
- end: `0x180002313`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002170`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021bb`
- `iisutil!PuCreateDebugPrintsObject` at `0x1800021a2`
- `iisutil!PuCreateDebugPrintsObject` at `0x1800021a2`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180002268`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800022a8`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180002268`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800022a8`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800022d8`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800022d8`

## string_xrefs

- `0x1800021b4`: `Unable to Create Debug Print Object \n`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 result; // rax
  ALLOC_CACHE_HANDLER *v8; // rax
  ALLOC_CACHE_HANDLER *v9; // rax
  void *v10; // rbx
  int v11; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+34h] [rbp-24h]
  int v13; // [rsp+38h] [rbp-20h]

  g_pDebug = PuCreateDebugPrintsObject("ssinc", 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  v5 = *(_QWORD *)a2;
  s_pGlobalInfo = a3;
  s_pSSIModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(v5 + 8))(a2);
  v6 = operator new(0x10u);
  if ( !v6 )
    return 2147942408LL;
  *v6 = &CIISModuleFactory::`vftable';
  v6[1] = &CIISHttpModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
             a2,
             v6,
             128,
             0);
  if ( (int)result < 0 )
    return result;
  v11 = 1;
  v13 = 1120;
  v12 = 100;
  v8 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( !v8 )
    goto LABEL_13;
  SSI_REQUEST::sm_pachSsiRequests = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                      v8,
                                      "SSI_REQUEST",
                                      (const struct ALLOC_CACHE_CONFIGURATION *)&v11,
                                      1);
  if ( SSI_REQUEST::sm_pachSsiRequests )
  {
    v11 = 1;
    v12 = 100;
    v13 = 784;
    v9 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
    if ( v9 )
    {
      SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                                   v9,
                                                   "SSI_INCLUDE_FILE",
                                                   (const struct ALLOC_CACHE_CONFIGURATION *)&v11,
                                                   1);
      if ( SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles )
        return 0;
    }
    else
    {
      SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles = 0;
    }
    v10 = SSI_REQUEST::sm_pachSsiRequests;
    if ( SSI_REQUEST::sm_pachSsiRequests )
    {
      ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)SSI_REQUEST::sm_pachSsiRequests);
      operator delete(v10);
LABEL_13:
      SSI_REQUEST::sm_pachSsiRequests = 0;
    }
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002170  mov     [rsp+arg_0], rbx
0x180002175  mov     [rsp+arg_10], rbp
0x18000217a  push    rdi
0x18000217b  sub     rsp, 50h
0x18000217f  mov     rax, cs:__security_cookie
0x180002186  xor     rax, rsp
0x180002189  mov     [rsp+58h+var_18], rax
0x18000218e  mov     rbx, rdx
0x180002191  lea     rcx, aSsinc; "ssinc"
0x180002198  mov     ebp, 1
0x18000219d  mov     rdi, r8
0x1800021a0  mov     edx, ebp
0x1800021a2  call    cs:__imp_PuCreateDebugPrintsObject
0x1800021a8  mov     cs:g_pDebug, rax
0x1800021af  test    rax, rax
0x1800021b2  jnz     short loc_1800021C1
0x1800021b4  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x1800021bb  call    cs:__imp_OutputDebugStringA
0x1800021c1  mov     rax, [rbx]
0x1800021c4  mov     rcx, rbx
0x1800021c7  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rdi; IHttpServer * s_pGlobalInfo
0x1800021ce  mov     rax, [rax+8]
0x1800021d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021d7  mov     ecx, 10h; Size
0x1800021dc  mov     cs:?s_pSSIModuleContext@@3PEAXEA, rax; void * s_pSSIModuleContext
0x1800021e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021e8  mov     rcx, rax
0x1800021eb  test    rax, rax
0x1800021ee  jz      loc_1800022F1
0x1800021f4  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800021fb  xor     r9d, r9d
0x1800021fe  mov     [rcx], rax
0x180002201  mov     r8d, 80h
0x180002207  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x18000220e  mov     [rcx+8], rax
0x180002212  mov     rdx, [rbx]
0x180002215  mov     rax, [rdx+10h]
0x180002219  mov     rdx, rcx
0x18000221c  mov     rcx, rbx
0x18000221f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002224  test    eax, eax
0x180002226  js      loc_1800022F6
0x18000222c  mov     edi, 100h
0x180002231  mov     [rsp+58h+var_28], ebp
0x180002235  mov     ebx, 64h ; 'd'
0x18000223a  mov     [rsp+58h+var_20], 460h
0x180002242  mov     ecx, edi; Size
0x180002244  mov     [rsp+58h+var_24], ebx
0x180002248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000224d  test    rax, rax
0x180002250  jz      loc_1800022E6
0x180002256  mov     r9d, ebp
0x180002259  lea     r8, [rsp+58h+var_28]
0x18000225e  lea     rdx, aSsiRequest; "SSI_REQUEST"
0x180002265  mov     rcx, rax
0x180002268  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000226e  mov     cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x180002275  test    rax, rax
0x180002278  jz      short loc_1800022F1
0x18000227a  mov     ecx, edi; Size
0x18000227c  mov     [rsp+58h+var_28], ebp
0x180002280  mov     [rsp+58h+var_24], ebx
0x180002284  mov     [rsp+58h+var_20], 310h
0x18000228c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002291  test    rax, rax
0x180002294  jz      short loc_1800022BE
0x180002296  mov     r9d, ebp
0x180002299  lea     r8, [rsp+58h+var_28]
0x18000229e  lea     rdx, aSsiIncludeFile; "SSI_INCLUDE_FILE"
0x1800022a5  mov     rcx, rax
0x1800022a8  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x1800022ae  mov     cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x1800022b5  test    rax, rax
0x1800022b8  jz      short loc_1800022C9
0x1800022ba  xor     eax, eax
0x1800022bc  jmp     short loc_1800022F6
0x1800022be  mov     cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x1800022c9  mov     rbx, cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x1800022d0  test    rbx, rbx
0x1800022d3  jz      short loc_1800022F1
0x1800022d5  mov     rcx, rbx
0x1800022d8  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x1800022de  mov     rcx, rbx; Block
0x1800022e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800022e6  mov     cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x1800022f1  mov     eax, 80070008h
0x1800022f6  mov     rcx, [rsp+58h+var_18]
0x1800022fb  xor     rcx, rsp; StackCookie
0x1800022fe  call    __security_check_cookie
0x180002303  mov     rbx, [rsp+58h+arg_0]
0x180002308  mov     rbp, [rsp+58h+arg_10]
0x18000230d  add     rsp, 50h
0x180002311  pop     rdi
0x180002312  retn
```
