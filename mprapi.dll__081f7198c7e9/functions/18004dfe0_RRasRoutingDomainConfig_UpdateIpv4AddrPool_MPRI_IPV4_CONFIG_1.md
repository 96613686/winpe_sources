# RRasRoutingDomainConfig::UpdateIpv4AddrPool(_MPRI_IPV4_CONFIG_1 *)

- ea: `0x18004dfe0`
- end: `0x18004e2f3`
- name: `?UpdateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV4_CONFIG_1@@@Z`
- size: `787`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _MPRI_IPV4_CONFIG_1 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18004c944`
- `0x18004d60c`

## callees

- `0x18004dfe0`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x180051112`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e28b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e28b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e141`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e299`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e299`

## string_xrefs

- `0x18004e231`: `%s: No IPv4 address pool configured.`
- `0x18004e083`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`
- `0x18004e172`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`
- `0x18004e22a`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`
- `0x18004e0c5`: `RRasRoutingDomainConfig::UpdateIpv4AddrPool`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::UpdateIpv4AddrPool(
        RRasRoutingDomainConfig *this,
        struct _MPRI_IPV4_CONFIG_1 *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v5; // edx
  __int64 v6; // r9
  unsigned int v7; // r8d
  size_t v8; // r14
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  void *v11; // rsi
  GUID *v12; // r9
  GUID *v13; // r9
  void *v14; // r14
  HANDLE v15; // rax
  unsigned int v16; // ebx
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+7Ch] [rbp-84h]
  GUID v25; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+94h] [rbp-6Ch]
  __int128 v28; // [rsp+A4h] [rbp-5Ch]
  int v29; // [rsp+B4h] [rbp-4Ch]
  int v30; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v18 = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"RRasRoutingDomainConfig::UpdateIpv4AddrPool",
      &v18,
      v4,
      (struct _GUID *)((char *)this + 516));
  v5 = *((_DWORD *)a2 + 1);
  if ( v5 )
  {
    if ( *((_QWORD *)a2 + 1) )
    {
      v7 = 0;
      while ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL * v7 + 4) > *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL * v7) )
      {
        if ( ++v7 >= v5 )
        {
          v8 = 8 * v5;
          ProcessHeap = GetProcessHeap();
          v10 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v8);
          v11 = v10;
          if ( v10 )
          {
            memcpy_0(v10, *((const void **)a2 + 1), v8);
            goto LABEL_24;
          }
          if ( (_QWORD)xmmword_180078C60 )
          {
            LOWORD(v30) = 0;
            v25 = GUID_NULL;
            LOWORD(v26) = 0;
            FormatRRASErrorString(&v30, L"%s: Malloc failed.", L"RRasRoutingDomainConfig::UpdateIpv4AddrPool");
            v12 = &v25;
            if ( this != (RRasRoutingDomainConfig *)-516LL )
              v12 = (GUID *)((char *)this + 516);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_180078C60,
              &v30,
              v12,
              0,
              &v26);
          }
          v18 = 8;
          goto LABEL_27;
        }
      }
      v18 = 87;
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_27;
      v6 = 3364;
      goto LABEL_7;
    }
    v18 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      v6 = 3358;
LABEL_7:
      LOWORD(v30) = 0;
      FormatRRASErrorString(
        &v30,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasRoutingDomainConfig::UpdateIpv4AddrPool",
        v6);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v30);
    }
  }
  else
  {
    v11 = 0;
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v30) = 0;
      v25 = GUID_NULL;
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v30,
        L"%s: No IPv4 address pool configured.",
        L"RRasRoutingDomainConfig::UpdateIpv4AddrPool");
      v13 = &v25;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v13 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C60,
        &v30,
        v13,
        0,
        &v26);
    }
LABEL_24:
    v14 = (void *)*((_QWORD *)this + 74);
    if ( v14 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
      *((_QWORD *)this + 74) = 0;
    }
    *((_QWORD *)this + 73) = 0;
    *((_DWORD *)this + 147) = *((_DWORD *)a2 + 1);
    *((_QWORD *)this + 74) = v11;
  }
LABEL_27:
  v16 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v16;
}

```

## disassembly

```asm
0x18004dfe0  mov     [rsp-8+arg_10], rbx
0x18004dfe5  push    rbp
0x18004dfe6  push    rsi
0x18004dfe7  push    rdi
0x18004dfe8  push    r14
0x18004dfea  push    r15
0x18004dfec  lea     rbp, [rsp-7D0h]
0x18004dff4  sub     rsp, 8D0h
0x18004dffb  mov     rax, cs:__security_cookie
0x18004e002  xor     rax, rsp
0x18004e005  mov     [rbp+7F0h+var_30], rax
0x18004e00c  mov     rdi, rdx
0x18004e00f  mov     rbx, rcx
0x18004e012  xor     r15d, r15d
0x18004e015  mov     [rsp+8F0h+var_8B0], r15d
0x18004e01a  mov     [rbp+7F0h+var_830], r15d
0x18004e01e  xor     edx, edx; Val
0x18004e020  mov     r8d, 7FCh; Size
0x18004e026  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18004e02a  call    memset_0
0x18004e02f  mov     [rbp+7F0h+var_860], r15d
0x18004e033  xorps   xmm0, xmm0
0x18004e036  xor     eax, eax
0x18004e038  movups  [rbp+7F0h+var_85C], xmm0
0x18004e03c  movups  [rbp+7F0h+var_84C], xmm0
0x18004e040  mov     [rbp+7F0h+var_83C], eax
0x18004e043  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18004e049  mov     [rsp+8F0h+var_8A8], r15
0x18004e04e  xorps   xmm1, xmm1
0x18004e051  movdqu  [rsp+8F0h+var_890], xmm1
0x18004e057  mov     [rsp+8F0h+var_880], r15
0x18004e05c  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18004e064  mov     [rsp+8F0h+var_874], r15d
0x18004e069  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x18004e070  jz      short loc_18004E094
0x18004e072  lea     rax, [rbx+204h]
0x18004e079  mov     [rsp+8F0h+var_8D0], rax; struct _GUID *
0x18004e07e  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18004e083  lea     rdx, aRrasroutingdom_20; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x18004e08a  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18004e08f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004e094  mov     edx, [rdi+4]
0x18004e097  test    edx, edx
0x18004e099  jz      loc_18004E208
0x18004e09f  cmp     [rdi+8], r15
0x18004e0a3  jnz     short loc_18004E0FF
0x18004e0a5  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x18004e0ad  cmp     qword ptr cs:xmmword_180078C50, r15
0x18004e0b4  jz      loc_18004E2BD
0x18004e0ba  mov     r9d, 0D1Eh
0x18004e0c0  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004e0c5  lea     r8, aRrasroutingdom_19; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x18004e0cc  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004e0d3  lea     rcx, [rbp+7F0h+var_830]
0x18004e0d7  call    FormatRRASErrorString
0x18004e0dc  lea     r8, [rbp+7F0h+var_830]
0x18004e0e0  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004e0e7  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004e0ee  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0fa  jmp     loc_18004E2BD
0x18004e0ff  test    edx, edx
0x18004e101  jz      loc_18004E208
0x18004e107  mov     r8d, r15d
0x18004e10a  mov     r9, [rdi+8]
0x18004e10e  mov     ecx, r8d
0x18004e111  mov     eax, [r9+rcx*8]
0x18004e115  cmp     [r9+rcx*8+4], eax
0x18004e11a  jbe     loc_18004E1E8
0x18004e120  inc     r8d
0x18004e123  cmp     r8d, edx
0x18004e126  jb      short loc_18004E10E
0x18004e128  lea     r14d, ds:0[rdx*8]
0x18004e130  call    cs:__imp_GetProcessHeap
0x18004e136  mov     rcx, rax; hHeap
0x18004e139  mov     r8d, r14d; dwBytes
0x18004e13c  mov     edx, 8; dwFlags
0x18004e141  call    cs:__imp_HeapAlloc
0x18004e147  mov     rsi, rax
0x18004e14a  test    rax, rax
0x18004e14d  jnz     loc_18004E1D4
0x18004e153  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004e15a  jz      short loc_18004E1C7
0x18004e15c  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004e161  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004e168  movdqu  [rbp+7F0h+var_870], xmm0
0x18004e16d  mov     word ptr [rbp+7F0h+var_860], r15w
0x18004e172  lea     r8, aRrasroutingdom_20; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x18004e179  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x18004e180  lea     rcx, [rbp+7F0h+var_830]
0x18004e184  call    FormatRRASErrorString
0x18004e189  lea     rcx, [rbx+204h]
0x18004e190  lea     r9, [rbp+7F0h+var_870]
0x18004e194  test    rcx, rcx
0x18004e197  cmovnz  r9, rcx
0x18004e19b  lea     rax, [rbp+7F0h+var_860]
0x18004e19f  mov     [rsp+8F0h+var_8C8], rax
0x18004e1a4  mov     [rsp+8F0h+var_8D0], r15
0x18004e1a9  lea     r8, [rbp+7F0h+var_830]
0x18004e1ad  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004e1b4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004e1bb  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004e1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1c7  mov     [rsp+8F0h+var_8B0], 8
0x18004e1cf  jmp     loc_18004E2BD
0x18004e1d4  mov     r8, r14; Size
0x18004e1d7  mov     rdx, [rdi+8]; Src
0x18004e1db  mov     rcx, rax; void *
0x18004e1de  call    memcpy_0
0x18004e1e3  jmp     loc_18004E27F
0x18004e1e8  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x18004e1f0  cmp     qword ptr cs:xmmword_180078C50, r15
0x18004e1f7  jz      loc_18004E2BD
0x18004e1fd  mov     r9d, 0D24h
0x18004e203  jmp     loc_18004E0C0
0x18004e208  mov     rsi, r15
0x18004e20b  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004e212  jz      short loc_18004E27F
0x18004e214  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004e219  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004e220  movdqu  [rbp+7F0h+var_870], xmm0
0x18004e225  mov     word ptr [rbp+7F0h+var_860], r15w
0x18004e22a  lea     r8, aRrasroutingdom_20; "RRasRoutingDomainConfig::UpdateIpv4Addr"...
0x18004e231  lea     rdx, aSNoIpv4Address_0; "%s: No IPv4 address pool configured."
0x18004e238  lea     rcx, [rbp+7F0h+var_830]
0x18004e23c  call    FormatRRASErrorString
0x18004e241  lea     rcx, [rbx+204h]
0x18004e248  lea     r9, [rbp+7F0h+var_870]
0x18004e24c  test    rcx, rcx
0x18004e24f  cmovnz  r9, rcx
0x18004e253  lea     rax, [rbp+7F0h+var_860]
0x18004e257  mov     [rsp+8F0h+var_8C8], rax
0x18004e25c  mov     [rsp+8F0h+var_8D0], r15
0x18004e261  lea     r8, [rbp+7F0h+var_830]
0x18004e265  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004e26c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004e273  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004e27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e27f  mov     r14, [rbx+250h]
0x18004e286  test    r14, r14
0x18004e289  jz      short loc_18004E2A6
0x18004e28b  call    cs:__imp_GetProcessHeap
0x18004e291  mov     r8, r14; lpMem
0x18004e294  xor     edx, edx; dwFlags
0x18004e296  mov     rcx, rax; hHeap
0x18004e299  call    cs:__imp_HeapFree
0x18004e29f  mov     [rbx+250h], r15
0x18004e2a6  mov     [rbx+248h], r15
0x18004e2ad  mov     eax, [rdi+4]
0x18004e2b0  mov     [rbx+24Ch], eax
0x18004e2b6  mov     [rbx+250h], rsi
0x18004e2bd  mov     ebx, [rsp+8F0h+var_8B0]
0x18004e2c1  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18004e2c6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004e2cb  mov     eax, ebx
0x18004e2cd  mov     rcx, [rbp+7F0h+var_30]
0x18004e2d4  xor     rcx, rsp; StackCookie
0x18004e2d7  call    __security_check_cookie
0x18004e2dc  mov     rbx, [rsp+8F0h+arg_10]
0x18004e2e4  add     rsp, 8D0h
0x18004e2eb  pop     r15
0x18004e2ed  pop     r14
0x18004e2ef  pop     rdi
0x18004e2f0  pop     rsi
0x18004e2f1  pop     rbp
0x18004e2f2  retn
```
