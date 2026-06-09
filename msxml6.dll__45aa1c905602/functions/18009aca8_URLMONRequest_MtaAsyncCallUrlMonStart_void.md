# URLMONRequest::_MtaAsyncCallUrlMonStart(void)

- ea: `0x18009aca8`
- end: `0x18009ae17`
- name: `?_MtaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ`
- size: `367`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180093030`

## callees

- `0x18009aca8`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009acf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18009acf6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009ada7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009ada7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ad06`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18009ad34`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18009ad34`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009ad91`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009ad91`

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
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x2Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  if ( GetModuleHandleExW(4u, (LPCWSTR)URLMONRequest::s_MtaWorkItemCallUrlMonStart, &hModule)
    && (ThreadpoolWork = CreateThreadpoolWork(URLMONRequest::s_MtaWorkItemCallUrlMonStart, this, 0)) != 0 )
  {
    v3 = 0;
    pRequestSite = this->_pRequestSite;
    this->_hModule = hModule;
    hModule = 0;
    pRequestSite->AddRef(pRequestSite);
    if ( (xmmword_1801FAD20 & 8) != 0 )
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
0x18009aca8  mov     [rsp+arg_0], rbx
0x18009acad  mov     [rsp+arg_10], rsi
0x18009acb2  push    rdi
0x18009acb3  sub     rsp, 20h
0x18009acb7  mov     rdi, this
0x18009acba  mov     [rsp+28h+hModule], 0
0x18009acc3  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18009acca  jz      short loc_18009ACE5
0x18009accc  mov     edx, 2Ah ; '*'; id
0x18009acd1  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009acd8  mov     ecx, 403h; LevelKeyword
0x18009acdd  mov     r9, rdi; _a1
0x18009ace0  call    WPP_SF_q
0x18009ace5  lea     r8, [rsp+28h+hModule]; phModule
0x18009acea  mov     ecx, 4; dwFlags
0x18009acef  lea     rdx, ?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x18009acf6  call    cs:__imp_GetModuleHandleExW
0x18009acfd  nop     dword ptr [rax+rax+00h]
0x18009ad02  test    eax, eax
0x18009ad04  jnz     short loc_18009AD27
0x18009ad06  call    cs:__imp_GetLastError
0x18009ad0d  nop     dword ptr [rax+rax+00h]
0x18009ad12  mov     ebx, eax
0x18009ad14  test    eax, eax
0x18009ad16  jle     $CleanUp_124
0x18009ad1c  movzx   ebx, ax
0x18009ad1f  or      ebx, 80070000h
0x18009ad25  jmp     short $CleanUp_124
0x18009ad27  xor     r8d, r8d; pcbe
0x18009ad2a  lea     this, ?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18009ad31  mov     rdx, rdi; pv
0x18009ad34  call    cs:__imp_CreateThreadpoolWork
0x18009ad3b  nop     dword ptr [rax+rax+00h]
0x18009ad40  mov     rsi, rax
0x18009ad43  test    rax, rax
0x18009ad46  jz      short loc_18009AD06
0x18009ad48  mov     rax, [rsp+28h+hModule]
0x18009ad4d  xor     ebx, ebx
0x18009ad4f  mov     this, [rdi+0A0h]
0x18009ad56  mov     [rdi+230h], rax
0x18009ad5d  mov     [rsp+28h+hModule], rbx
0x18009ad62  mov     rax, [this]
0x18009ad65  mov     rax, [rax+8]
0x18009ad69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad6e  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18009ad75  jz      short loc_18009AD8E
0x18009ad77  lea     edx, [rbx+2Bh]; id
0x18009ad7a  mov     ecx, 403h; LevelKeyword
0x18009ad7f  mov     r9, rdi; _a1
0x18009ad82  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009ad89  call    WPP_SF_q
0x18009ad8e  mov     this, rsi; pwk
0x18009ad91  call    cs:__imp_SubmitThreadpoolWork
0x18009ad98  nop     dword ptr [rax+rax+00h]
0x18009ad9d  mov     this, [rsp+28h+hModule]; hLibModule
0x18009ada2  test    this, this
0x18009ada5  jz      short loc_18009ADBC
0x18009ada7  call    cs:__imp_FreeLibrary
0x18009adae  nop     dword ptr [rax+rax+00h]
0x18009adb3  mov     [rsp+28h+hModule], 0
0x18009adbc  mov     r10d, ebx; __annotation("TMF:",
0x18009adbf  sar     r10d, 1Fh
0x18009adc3  lea     eax, ds:4[r10*2]
0x18009adcb  movsxd  this, eax
0x18009adce  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009add5  test    byte ptr [rax+this*8], 8
0x18009add9  jz      short loc_18009AE04
0x18009addb  add     r10w, 2
0x18009ade0  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009ade7  movzx   ecx, r10w
0x18009adeb  mov     eax, 200h
0x18009adf0  imul    ecx, eax
0x18009adf3  mov     edx, 2Ch ; ','; id
0x18009adf8  mov     r9d, ebx; _a1
0x18009adfb  or      cx, 3; LevelKeyword
0x18009adff  call    WPP_SF_d
0x18009ae04  mov     rsi, [rsp+28h+arg_10]
0x18009ae09  mov     eax, ebx
0x18009ae0b  mov     rbx, [rsp+28h+arg_0]
0x18009ae10  add     rsp, 20h
0x18009ae14  pop     rdi
0x18009ae15  retn
```
