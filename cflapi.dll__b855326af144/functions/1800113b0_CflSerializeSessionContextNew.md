# CflSerializeSessionContextNew

- ea: `0x1800113b0`
- end: `0x18001152c`
- name: `CflSerializeSessionContextNew`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000cf3c`
- `0x18000d8d8`
- `0x1800113b0`
- `0x18002b264`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001140e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001140e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011426`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011426`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001142c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001142c`

## string_xrefs

- `0x18001149f`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflSerializeSessionContextNew(
        CflApiNew *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  unsigned int v7; // r15d
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int v16[2]; // [rsp+20h] [rbp-3D8h]
  unsigned __int16 *v17; // [rsp+28h] [rbp-3D0h]
  unsigned __int16 **v18; // [rsp+38h] [rbp-3C0h]
  DWORD dwSize[4]; // [rsp+40h] [rbp-3B8h] BYREF
  _QWORD v20[42]; // [rsp+50h] [rbp-3A8h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v7 = (unsigned int)a4;
  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "CflSerializeSessionContextActivity");
  v20[0] = &CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable';
  CflApiTraceProvider::CflSerializeSessionContextActivity::StartActivity(
    (CflApiTraceProvider::CflSerializeSessionContextActivity *)v20,
    ExeName,
    CommandLineW);
  LODWORD(v17) = (_DWORD)a6;
  v13 = CflApiNew::SerializeSessionContext(this, a2, a3, (const unsigned __int8 *)v7, a5, v17, a7, v18);
  v14 = v13;
  if ( v13 >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20);
    v20[0] = &CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v20);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v13,
      v16[0]);
    v20[0] = &CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v20);
    return v14;
  }
}

```

## disassembly

```asm
0x1800113b0  push    rbx
0x1800113b2  push    rsi
0x1800113b3  push    rdi
0x1800113b4  push    r12
0x1800113b6  push    r13
0x1800113b8  push    r14
0x1800113ba  push    r15
0x1800113bc  sub     rsp, 3C0h
0x1800113c3  mov     rax, cs:__security_cookie
0x1800113ca  xor     rax, rsp
0x1800113cd  mov     [rsp+3F8h+var_48], rax
0x1800113d5  mov     r15d, r9d
0x1800113d8  mov     r14, r8
0x1800113db  mov     rsi, rdx
0x1800113de  mov     rdi, rcx
0x1800113e1  mov     r12, qword ptr [rsp+3F8h+arg_20]
0x1800113e9  mov     r13, qword ptr [rsp+3F8h+arg_30]
0x1800113f1  xor     edx, edx; Val
0x1800113f3  mov     r8d, 20Ah; Size
0x1800113f9  lea     rcx, [rsp+3F8h+ExeName]; void *
0x180011401  call    memset_0
0x180011406  mov     [rsp+3F8h+dwSize], 105h
0x18001140e  call    cs:__imp_GetCurrentProcess
0x180011414  mov     rcx, rax; hProcess
0x180011417  lea     r9, [rsp+3F8h+dwSize]; lpdwSize
0x18001141c  lea     r8, [rsp+3F8h+ExeName]; lpExeName
0x180011424  xor     edx, edx; dwFlags
0x180011426  call    cs:__imp_QueryFullProcessImageNameW
0x18001142c  call    cs:__imp_GetCommandLineW
0x180011432  mov     rbx, rax
0x180011435  lea     rdx, aCflserializese_1; "CflSerializeSessionContextActivity"
0x18001143c  lea     rcx, [rsp+3F8h+var_3A8]
0x180011441  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011446  lea     rax, ??_7CflSerializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable'
0x18001144d  mov     [rsp+3F8h+var_3A8], rax
0x180011452  mov     r8, rbx; unsigned __int16 *
0x180011455  lea     rdx, [rsp+3F8h+ExeName]; unsigned __int16 *
0x18001145d  lea     rcx, [rsp+3F8h+var_3A8]; this
0x180011462  call    ?StartActivity@CflSerializeSessionContextActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflSerializeSessionContextActivity::StartActivity(ushort const *,ushort const *)
0x180011467  nop
0x180011468  mov     qword ptr [rsp+3F8h+var_3C8], r13; unsigned int
0x18001146d  mov     eax, dword ptr [rsp+3F8h+arg_28]
0x180011474  mov     dword ptr [rsp+3F8h+var_3D0], eax; unsigned __int16 *
0x180011478  mov     qword ptr [rsp+3F8h+var_3D8], r12; int
0x18001147d  mov     r9d, r15d; unsigned __int8 *
0x180011480  mov     r8, r14; unsigned __int16 *
0x180011483  mov     rdx, rsi; struct _GUID *
0x180011486  mov     rcx, rdi; this
0x180011489  call    ?SerializeSessionContext@CflApiNew@@YAJPEBU_GUID@@PEBGPEBEK1KPEAPEAG@Z; CflApiNew::SerializeSessionContext(_GUID const *,ushort const *,uchar const *,ulong,ushort const *,ulong,ushort * *)
0x18001148e  mov     ebx, eax
0x180011490  test    eax, eax
0x180011492  jns     short loc_1800114D5
0x180011494  mov     rcx, [rsp+3F8h]; this
0x18001149c  mov     r9d, eax; char *
0x18001149f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x1800114a6  mov     edx, 15Dh; void *
0x1800114ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114b0  nop
0x1800114b1  lea     rax, ??_7CflSerializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable'
0x1800114b8  mov     [rsp+3F8h+var_3A8], rax
0x1800114bd  lea     rcx, [rsp+3F8h+var_3A8]
0x1800114c2  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800114c7  lea     rcx, [rsp+3F8h+var_3A8]
0x1800114cc  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800114d1  mov     eax, ebx
0x1800114d3  jmp     short loc_180011508
0x1800114d5  lea     rcx, [rsp+3F8h+var_3A8]
0x1800114da  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800114df  nop
0x1800114e0  lea     rax, ??_7CflSerializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable'
0x1800114e7  mov     [rsp+3F8h+var_3A8], rax
0x1800114ec  lea     rcx, [rsp+3F8h+var_3A8]
0x1800114f1  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800114f6  lea     rcx, [rsp+3F8h+var_3A8]
0x1800114fb  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011500  xor     eax, eax
0x180011502  jmp     short loc_180011508
0x180011504  mov     eax, [rsp+3F8h+dwSize]
0x180011508  mov     rcx, [rsp+3F8h+var_48]
0x180011510  xor     rcx, rsp; StackCookie
0x180011513  call    __security_check_cookie
0x180011518  add     rsp, 3C0h
0x18001151f  pop     r15
0x180011521  pop     r14
0x180011523  pop     r13
0x180011525  pop     r12
0x180011527  pop     rdi
0x180011528  pop     rsi
0x180011529  pop     rbx
0x18001152a  retn
```
