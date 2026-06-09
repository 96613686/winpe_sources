# URLMONRequest::_MtaAsyncCallUrlMonStart(void)

- ea: `0x180099f24`
- end: `0x18009a070`
- name: `?_MtaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ`
- size: `332`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180093060`

## callees

- `0x180099f24`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180099f72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180099f72`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009a007`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009a007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099f7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180099fa0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180099fa0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180099ff7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180099ff7`

## pseudocode

```c
__int64 __fastcall URLMONRequest::_MtaAsyncCallUrlMonStart(URLMONRequest *this)
{
  signed int LastError; // eax
  signed int v3; // ebx
  _TP_WORK *ThreadpoolWork; // rsi
  IURLRequestSite *pRequestSite; // rcx
  HINSTANCE__ *hModule; // [rsp+38h] [rbp+10h] BYREF

  hModule = 0;
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x2Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  if ( GetModuleHandleExW(4u, (LPCWSTR)URLMONRequest::s_MtaWorkItemCallUrlMonStart, &hModule)
    && (ThreadpoolWork = CreateThreadpoolWork(URLMONRequest::s_MtaWorkItemCallUrlMonStart, this, 0)) != 0 )
  {
    v3 = 0;
    pRequestSite = this->_pRequestSite;
    this->_hModule = hModule;
    hModule = 0;
    pRequestSite->AddRef(pRequestSite);
    if ( (xmmword_1801F6C20 & 8) != 0 )
      WPP_SF_q(0x403u, 0x2Bu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hModule )
  {
    FreeLibrary(hModule);
    hModule = 0;
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v3 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0x2Cu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180099f24  mov     [rsp+arg_0], rbx
0x180099f29  mov     [rsp+arg_10], rsi
0x180099f2e  push    rdi
0x180099f2f  sub     rsp, 20h
0x180099f33  mov     rdi, this
0x180099f36  mov     [rsp+28h+hModule], 0
0x180099f3f  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180099f46  jz      short loc_180099F61
0x180099f48  mov     edx, 2Ah ; '*'; id
0x180099f4d  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180099f54  mov     ecx, 403h; LevelKeyword
0x180099f59  mov     r9, rdi; _a1
0x180099f5c  call    WPP_SF_q
0x180099f61  lea     r8, [rsp+28h+hModule]; phModule
0x180099f66  mov     ecx, 4; dwFlags
0x180099f6b  lea     rdx, ?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x180099f72  call    cs:__imp_GetModuleHandleExW
0x180099f78  test    eax, eax
0x180099f7a  jnz     short loc_180099F93
0x180099f7c  call    cs:__imp_GetLastError
0x180099f82  mov     ebx, eax
0x180099f84  test    eax, eax
0x180099f86  jle     short $CleanUp_126
0x180099f88  movzx   ebx, ax
0x180099f8b  or      ebx, 80070000h
0x180099f91  jmp     short $CleanUp_126
0x180099f93  xor     r8d, r8d; pcbe
0x180099f96  lea     this, ?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180099f9d  mov     rdx, rdi; pv
0x180099fa0  call    cs:__imp_CreateThreadpoolWork
0x180099fa6  mov     rsi, rax
0x180099fa9  test    rax, rax
0x180099fac  jz      short loc_180099F7C
0x180099fae  mov     rax, [rsp+28h+hModule]
0x180099fb3  xor     ebx, ebx
0x180099fb5  mov     this, [rdi+0A0h]
0x180099fbc  mov     [rdi+230h], rax
0x180099fc3  mov     [rsp+28h+hModule], rbx
0x180099fc8  mov     rax, [this]
0x180099fcb  mov     rax, [rax+8]
0x180099fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099fd4  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180099fdb  jz      short loc_180099FF4
0x180099fdd  lea     edx, [rbx+2Bh]; id
0x180099fe0  mov     ecx, 403h; LevelKeyword
0x180099fe5  mov     r9, rdi; _a1
0x180099fe8  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180099fef  call    WPP_SF_q
0x180099ff4  mov     this, rsi; pwk
0x180099ff7  call    cs:__imp_SubmitThreadpoolWork
0x180099ffd  mov     this, [rsp+28h+hModule]; hLibModule
0x18009a002  test    this, this
0x18009a005  jz      short loc_18009A016
0x18009a007  call    cs:__imp_FreeLibrary
0x18009a00d  mov     [rsp+28h+hModule], 0
0x18009a016  mov     r10d, ebx; __annotation("TMF:",
0x18009a019  sar     r10d, 1Fh
0x18009a01d  lea     eax, ds:4[r10*2]
0x18009a025  movsxd  this, eax
0x18009a028  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009a02f  test    byte ptr [rax+this*8], 8
0x18009a033  jz      short loc_18009A05E
0x18009a035  add     r10w, 2
0x18009a03a  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009a041  movzx   ecx, r10w
0x18009a045  mov     eax, 200h
0x18009a04a  imul    ecx, eax
0x18009a04d  mov     edx, 2Ch ; ','; id
0x18009a052  mov     r9d, ebx; _a1
0x18009a055  or      cx, 3; LevelKeyword
0x18009a059  call    WPP_SF_d
0x18009a05e  mov     rsi, [rsp+28h+arg_10]
0x18009a063  mov     eax, ebx
0x18009a065  mov     rbx, [rsp+28h+arg_0]
0x18009a06a  add     rsp, 20h
0x18009a06e  pop     rdi
0x18009a06f  retn
```
