# RRasRoutingDomainConfig::CreateLoopbackInterface(void)

- ea: `0x18003ae88`
- end: `0x18003b088`
- name: `?CreateLoopbackInterface@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `512`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18003bd5c`

## callees

- `0x18002223c`
- `0x18003a874`
- `0x18003ae88`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `USER32!LoadStringW` at `0x18003af70`
- `USER32!LoadStringW` at `0x18003af70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003af4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003af4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003af79`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003af79`

## string_xrefs

- `0x18003af48`: `mprmsg.dll`
- `0x18003af2f`: `RRasRoutingDomainConfig::CreateLoopbackInterface`
- `0x18003af94`: `RRasRoutingDomainConfig::CreateLoopbackInterface`
- `0x18003b019`: `RRasRoutingDomainConfig::CreateLoopbackInterface`
- `0x18003af9b`: `%s: Failed to load mprmsg.dll`
- `0x18003b020`: `%s: CreateInterfaceEntry failed for loopback: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CreateLoopbackInterface(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  HMODULE Library; // rax
  HMODULE v4; // rbx
  unsigned int InterfaceEntry; // ebx
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v9; // [rsp+30h] [rbp-D0h]
  __int128 v10; // [rsp+40h] [rbp-C0h]
  __int64 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+5Ch] [rbp-A4h]
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v16[2044]; // [rsp+264h] [rbp+164h] BYREF

  v7 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"RRasRoutingDomainConfig::CreateLoopbackInterface",
      &v7,
      v2);
  Library = LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    LoadStringW(Library, 0x4A39u, Buffer, 256);
    FreeLibrary(v4);
  }
  else
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"%s: Failed to load mprmsg.dll", L"RRasRoutingDomainConfig::CreateLoopbackInterface");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v15);
    }
    StringCchCopyW(Buffer, 0x100u, L"loopback");
  }
  InterfaceEntry = RRasRoutingDomainConfig::CreateInterfaceEntry(this, (BYTE *)Buffer, ROUTER_IF_TYPE_LOOPBACK, 0);
  v7 = InterfaceEntry;
  if ( InterfaceEntry && (_QWORD)xmmword_180071090 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(
      &v15,
      L"%s: CreateInterfaceEntry failed for loopback: %d.",
      L"RRasRoutingDomainConfig::CreateLoopbackInterface",
      InterfaceEntry);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v15);
    InterfaceEntry = v7;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return InterfaceEntry;
}

```

## disassembly

```asm
0x18003ae88  mov     [rsp-8+arg_8], rbx
0x18003ae8d  mov     [rsp-8+arg_10], rdi
0x18003ae92  push    rbp
0x18003ae93  lea     rbp, [rsp-970h]
0x18003ae9b  sub     rsp, 0A70h
0x18003aea2  mov     rax, cs:__security_cookie
0x18003aea9  xor     rax, rsp
0x18003aeac  mov     [rbp+970h+var_10], rax
0x18003aeb3  mov     rdi, rcx
0x18003aeb6  mov     [rsp+0A70h+var_A50], 0
0x18003aebe  xor     edx, edx; Val
0x18003aec0  mov     r8d, 200h; Size
0x18003aec6  lea     rcx, [rsp+0A70h+Buffer]; void *
0x18003aecb  call    memset_0
0x18003aed0  xor     eax, eax
0x18003aed2  mov     [rbp+970h+var_810], eax
0x18003aed8  xor     edx, edx; Val
0x18003aeda  mov     r8d, 7FCh; Size
0x18003aee0  lea     rcx, [rbp+970h+var_80C]; void *
0x18003aee7  call    memset_0
0x18003aeec  xorps   xmm0, xmm0
0x18003aeef  movdqu  [rsp+0A70h+var_A40], xmm0
0x18003aef5  mov     [rsp+0A70h+var_A48], 0
0x18003aefe  xorps   xmm1, xmm1
0x18003af01  movdqu  [rsp+0A70h+var_A30], xmm1
0x18003af07  mov     [rsp+0A70h+var_A20], 0
0x18003af10  mov     [rsp+0A70h+var_A18], 0FFFFFFFFh
0x18003af18  mov     [rsp+0A70h+var_A14], 0
0x18003af20  cmp     qword ptr cs:xmmword_180071090+8, 0
0x18003af28  jz      short loc_18003AF40
0x18003af2a  lea     r8, [rsp+0A70h+var_A50]; unsigned int *
0x18003af2f  lea     rdx, aRrasroutingdom_3; "RRasRoutingDomainConfig::CreateLoopback"...
0x18003af36  lea     rcx, [rsp+0A70h+var_A48]; this
0x18003af3b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003af40  xor     edx, edx; hFile
0x18003af42  mov     r8d, 800h; dwFlags
0x18003af48  lea     rcx, LibFileName; "mprmsg.dll"
0x18003af4f  call    cs:__imp_LoadLibraryExW
0x18003af55  mov     rbx, rax
0x18003af58  test    rax, rax
0x18003af5b  jz      short loc_18003AF81
0x18003af5d  mov     r9d, 100h; cchBufferMax
0x18003af63  lea     r8, [rsp+0A70h+Buffer]; lpBuffer
0x18003af68  mov     edx, 4A39h; uID
0x18003af6d  mov     rcx, rax; hInstance
0x18003af70  call    cs:__imp_LoadStringW
0x18003af76  mov     rcx, rbx; hLibModule
0x18003af79  call    cs:__imp_FreeLibrary
0x18003af7f  jmp     short loc_18003AFE5
0x18003af81  cmp     qword ptr cs:xmmword_180071090, 0
0x18003af89  jz      short loc_18003AFCF
0x18003af8b  xor     eax, eax
0x18003af8d  mov     word ptr [rbp+970h+var_810], ax
0x18003af94  lea     r8, aRrasroutingdom_3; "RRasRoutingDomainConfig::CreateLoopback"...
0x18003af9b  lea     rdx, aSFailedToLoadM; "%s: Failed to load mprmsg.dll"
0x18003afa2  lea     rcx, [rbp+970h+var_810]
0x18003afa9  call    FormatRRASErrorString
0x18003afae  lea     r8, [rbp+970h+var_810]
0x18003afb5  mov     rdx, qword ptr cs:xmmword_180071090
0x18003afbc  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003afc3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003afca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afcf  lea     r8, aLoopback; "loopback"
0x18003afd6  mov     edx, 100h; cchDest
0x18003afdb  lea     rcx, [rsp+0A70h+Buffer]; pszDest
0x18003afe0  call    StringCchCopyW
0x18003afe5  xor     r9d, r9d; struct _DIM_COMPARTMENT_INTERFACE *
0x18003afe8  lea     r8d, [r9+5]; enum _ROUTER_INTERFACE_TYPE
0x18003afec  lea     rdx, [rsp+0A70h+Buffer]; lpData
0x18003aff1  mov     rcx, rdi; this
0x18003aff4  call    ?CreateInterfaceEntry@RRasRoutingDomainConfig@@QEAAKPEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z; RRasRoutingDomainConfig::CreateInterfaceEntry(ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)
0x18003aff9  mov     ebx, eax
0x18003affb  mov     [rsp+0A70h+var_A50], eax
0x18003afff  test    eax, eax
0x18003b001  jz      short loc_18003B058
0x18003b003  cmp     qword ptr cs:xmmword_180071090, 0
0x18003b00b  jz      short loc_18003B058
0x18003b00d  xor     eax, eax
0x18003b00f  mov     word ptr [rbp+970h+var_810], ax
0x18003b016  mov     r9d, ebx
0x18003b019  lea     r8, aRrasroutingdom_3; "RRasRoutingDomainConfig::CreateLoopback"...
0x18003b020  lea     rdx, aSCreateinterfa; "%s: CreateInterfaceEntry failed for loo"...
0x18003b027  lea     rcx, [rbp+970h+var_810]
0x18003b02e  call    FormatRRASErrorString
0x18003b033  lea     r8, [rbp+970h+var_810]
0x18003b03a  mov     rdx, qword ptr cs:xmmword_180071090
0x18003b041  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003b048  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b054  mov     ebx, [rsp+0A70h+var_A50]
0x18003b058  lea     rcx, [rsp+0A70h+var_A48]; this
0x18003b05d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003b062  mov     eax, ebx
0x18003b064  mov     rcx, [rbp+970h+var_10]
0x18003b06b  xor     rcx, rsp; StackCookie
0x18003b06e  call    __security_check_cookie
0x18003b073  lea     r11, [rsp+0A70h+var_s0]
0x18003b07b  mov     rbx, [r11+18h]
0x18003b07f  mov     rdi, [r11+20h]
0x18003b083  mov     rsp, r11
0x18003b086  pop     rbp
0x18003b087  retn
```
