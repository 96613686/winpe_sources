# RRasRoutingDomainConfig::CreateLoopbackInterface(void)

- ea: `0x180046644`
- end: `0x180046852`
- name: `?CreateLoopbackInterface@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `526`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047508`

## callees

- `0x180046014`
- `0x180046644`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180046715`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180046715`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004671e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004671e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800466f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800466f4`

## string_xrefs

- `0x1800466ed`: `mprmsg.dll`
- `0x1800466d4`: `RRasRoutingDomainConfig::CreateLoopbackInterface`
- `0x180046739`: `RRasRoutingDomainConfig::CreateLoopbackInterface`
- `0x1800467ec`: `RRasRoutingDomainConfig::CreateLoopbackInterface`
- `0x180046740`: `%s: Failed to load mprmsg.dll`
- `0x1800467f3`: `%s: CreateInterfaceEntry failed for loopback: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CreateLoopbackInterface(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  HMODULE Library; // rax
  struct _DIM_COMPARTMENT_INTERFACE *v4; // r9
  HMODULE v5; // rbx
  __int64 v6; // rdx
  const wchar_t *v7; // r8
  __int64 v8; // rcx
  WCHAR *v9; // rax
  WCHAR *v10; // rdx
  unsigned int InterfaceEntry; // eax
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+30h] [rbp-D0h]
  __int128 v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v23[2044]; // [rsp+264h] [rbp+164h] BYREF

  v14 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"RRasRoutingDomainConfig::CreateLoopbackInterface",
      &v14,
      v2);
  Library = LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    LoadStringW(Library, 0x4A39u, Buffer, 256);
    FreeLibrary(v5);
  }
  else
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, L"%s: Failed to load mprmsg.dll", L"RRasRoutingDomainConfig::CreateLoopbackInterface");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v22);
    }
    v6 = 2147483646;
    v7 = L"loopback";
    v8 = 256;
    v9 = Buffer;
    do
    {
      if ( !v6 )
        break;
      v4 = (struct _DIM_COMPARTMENT_INTERFACE *)*v7;
      if ( !(_WORD)v4 )
        break;
      *v9++ = (unsigned __int16)v4;
      ++v7;
      --v6;
      --v8;
    }
    while ( v8 );
    v10 = v9 - 1;
    if ( v8 )
      v10 = v9;
    *v10 = 0;
  }
  InterfaceEntry = RRasRoutingDomainConfig::CreateInterfaceEntry(this, (BYTE *)Buffer, ROUTER_IF_TYPE_LOOPBACK, v4);
  v12 = InterfaceEntry;
  v14 = InterfaceEntry;
  if ( InterfaceEntry && (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v22) = 0;
    FormatRRASErrorString(
      &v22,
      L"%s: CreateInterfaceEntry failed for loopback: %d.",
      L"RRasRoutingDomainConfig::CreateLoopbackInterface",
      InterfaceEntry);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v22);
    v12 = v14;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v12;
}

```

## disassembly

```asm
0x180046644  push    rbp
0x180046646  push    rbx
0x180046647  push    rsi
0x180046648  push    rdi
0x180046649  lea     rbp, [rsp-978h]
0x180046651  sub     rsp, 0A78h
0x180046658  mov     rax, cs:__security_cookie
0x18004665f  xor     rax, rsp
0x180046662  mov     [rbp+990h+var_30], rax
0x180046669  mov     rdi, rcx
0x18004666c  xor     esi, esi
0x18004666e  mov     [rsp+0A90h+var_A70], esi
0x180046672  xor     edx, edx; Val
0x180046674  mov     r8d, 200h; Size
0x18004667a  lea     rcx, [rsp+0A90h+Buffer]; void *
0x18004667f  call    memset_0
0x180046684  mov     [rbp+990h+var_830], esi
0x18004668a  xor     edx, edx; Val
0x18004668c  mov     r8d, 7FCh; Size
0x180046692  lea     rcx, [rbp+990h+var_82C]; void *
0x180046699  call    memset_0
0x18004669e  xorps   xmm0, xmm0
0x1800466a1  movdqu  [rsp+0A90h+var_A60], xmm0
0x1800466a7  mov     [rsp+0A90h+var_A68], rsi
0x1800466ac  xorps   xmm1, xmm1
0x1800466af  movdqu  [rsp+0A90h+var_A50], xmm1
0x1800466b5  mov     [rsp+0A90h+var_A40], rsi
0x1800466ba  mov     [rsp+0A90h+var_A38], 0FFFFFFFFh
0x1800466c2  mov     [rsp+0A90h+var_A34], esi
0x1800466c6  cmp     qword ptr cs:xmmword_180078C50+8, rsi
0x1800466cd  jz      short loc_1800466E5
0x1800466cf  lea     r8, [rsp+0A90h+var_A70]; unsigned int *
0x1800466d4  lea     rdx, aRrasroutingdom_3; "RRasRoutingDomainConfig::CreateLoopback"...
0x1800466db  lea     rcx, [rsp+0A90h+var_A68]; this
0x1800466e0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800466e5  xor     edx, edx; hFile
0x1800466e7  mov     r8d, 800h; dwFlags
0x1800466ed  lea     rcx, LibFileName; "mprmsg.dll"
0x1800466f4  call    cs:__imp_LoadLibraryExW
0x1800466fa  mov     rbx, rax
0x1800466fd  test    rax, rax
0x180046700  jz      short loc_180046729
0x180046702  mov     r9d, 100h; cchBufferMax
0x180046708  lea     r8, [rsp+0A90h+Buffer]; lpBuffer
0x18004670d  mov     edx, 4A39h; uID
0x180046712  mov     rcx, rax; hInstance
0x180046715  call    cs:__imp_LoadStringW
0x18004671b  mov     rcx, rbx; hLibModule
0x18004671e  call    cs:__imp_FreeLibrary
0x180046724  jmp     loc_1800467BC
0x180046729  cmp     qword ptr cs:xmmword_180078C50, rsi
0x180046730  jz      short loc_180046774
0x180046732  mov     word ptr [rbp+990h+var_830], si
0x180046739  lea     r8, aRrasroutingdom_3; "RRasRoutingDomainConfig::CreateLoopback"...
0x180046740  lea     rdx, aSFailedToLoadM; "%s: Failed to load mprmsg.dll"
0x180046747  lea     rcx, [rbp+990h+var_830]
0x18004674e  call    FormatRRASErrorString
0x180046753  lea     r8, [rbp+990h+var_830]
0x18004675a  mov     rdx, qword ptr cs:xmmword_180078C50
0x180046761  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180046768  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004676f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046774  mov     edx, 7FFFFFFEh
0x180046779  lea     r8, aLoopback; "loopback"
0x180046780  mov     ecx, 100h
0x180046785  lea     rax, [rsp+0A90h+Buffer]
0x18004678a  test    rdx, rdx
0x18004678d  jz      short loc_1800467AE
0x18004678f  movzx   r9d, word ptr [r8]; struct _DIM_COMPARTMENT_INTERFACE *
0x180046793  test    r9w, r9w
0x180046797  jz      short loc_1800467AE
0x180046799  mov     [rax], r9w
0x18004679d  add     rax, 2
0x1800467a1  add     r8, 2
0x1800467a5  dec     rdx
0x1800467a8  sub     rcx, 1
0x1800467ac  jnz     short loc_18004678A
0x1800467ae  lea     rdx, [rax-2]
0x1800467b2  test    rcx, rcx
0x1800467b5  cmovnz  rdx, rax
0x1800467b9  mov     [rdx], si
0x1800467bc  mov     r8d, 5; enum _ROUTER_INTERFACE_TYPE
0x1800467c2  lea     rdx, [rsp+0A90h+Buffer]; lpData
0x1800467c7  mov     rcx, rdi; this
0x1800467ca  call    ?CreateInterfaceEntry@RRasRoutingDomainConfig@@QEAAKPEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z; RRasRoutingDomainConfig::CreateInterfaceEntry(ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)
0x1800467cf  mov     ebx, eax
0x1800467d1  mov     [rsp+0A90h+var_A70], eax
0x1800467d5  test    eax, eax
0x1800467d7  jz      short loc_18004682B
0x1800467d9  cmp     qword ptr cs:xmmword_180078C50, rsi
0x1800467e0  jz      short loc_18004682B
0x1800467e2  mov     word ptr [rbp+990h+var_830], si
0x1800467e9  mov     r9d, eax
0x1800467ec  lea     r8, aRrasroutingdom_3; "RRasRoutingDomainConfig::CreateLoopback"...
0x1800467f3  lea     rdx, aSCreateinterfa; "%s: CreateInterfaceEntry failed for loo"...
0x1800467fa  lea     rcx, [rbp+990h+var_830]
0x180046801  call    FormatRRASErrorString
0x180046806  lea     r8, [rbp+990h+var_830]
0x18004680d  mov     rdx, qword ptr cs:xmmword_180078C50
0x180046814  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004681b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180046822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046827  mov     ebx, [rsp+0A90h+var_A70]
0x18004682b  lea     rcx, [rsp+0A90h+var_A68]; this
0x180046830  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180046835  mov     eax, ebx
0x180046837  mov     rcx, [rbp+990h+var_30]
0x18004683e  xor     rcx, rsp; StackCookie
0x180046841  call    __security_check_cookie
0x180046846  add     rsp, 0A78h
0x18004684d  pop     rdi
0x18004684e  pop     rsi
0x18004684f  pop     rbx
0x180046850  pop     rbp
0x180046851  retn
```
