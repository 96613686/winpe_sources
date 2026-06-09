# CSession::Init(COleScript *,IActiveScriptSite *,ThreadGlobals *)

- ea: `0x180002598`
- end: `0x180002740`
- name: `?Init@CSession@@IEAAJPEAVCOleScript@@PEAUIActiveScriptSite@@PEAVThreadGlobals@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct COleScript *, struct IActiveScriptSite *, struct ThreadGlobals *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800020c8`

## callees

- `0x180002598`
- `0x180002748`
- `0x18000f1c0`
- `0x1800576a0`
- `0x1800616f8`
- `0x18007e2a4`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180002642`
- `OLEAUT32!__imp_VariantInit` at `0x180002642`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800026af`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800026af`
- `ole32!CLSIDFromString` at `0x1800026c3`
- `ole32!CLSIDFromString` at `0x1800026c3`

## pseudocode

```c
int __fastcall CSession::Init(
        CSession *this,
        struct COleScript *a2,
        struct IActiveScriptSite *a3,
        struct ThreadGlobals *a4)
{
  char *v6; // rcx
  int result; // eax
  __int64 v10; // rax
  VarStack *v11; // rax
  VarStack *v12; // rax
  CLSID pclsid; // [rsp+30h] [rbp-88h] BYREF
  WCHAR Buffer[40]; // [rsp+40h] [rbp-78h] BYREF

  v6 = (char *)this + 888;
  *((_QWORD *)v6 + 4) = (char *)this + 408;
  *((_DWORD *)v6 + 10) = 20;
  *(_QWORD *)(v6 + 44) = 24;
  IScavengerBase::LinkToGc((IScavengerBase *)v6);
  *((_QWORD *)this + 123) = a4;
  if ( (*((_BYTE *)a2 + 928) & 1) != 0 )
  {
    if ( a4 && (v11 = (VarStack *)operator new(0x58u)) != 0 )
      v12 = VarStack::VarStack(v11, a4, 1);
    else
      v12 = 0;
    *((_QWORD *)this + 156) = v12;
    if ( !v12 )
      return -2147024882;
  }
  result = GlobalBinder::Create((struct GlobalBinder **)this + 9, this);
  if ( result >= 0 )
  {
    *((_QWORD *)this + 5) = a2;
    if ( ((__int64 (__fastcall *)(struct IActiveScriptSite *, GUID *, char *))a3->lpVtbl->QueryInterface)(
           a3,
           &IID_IActiveScriptSiteInterruptPoll,
           (char *)this + 1064) < 0 )
      *((_QWORD *)this + 133) = 0;
    VariantInit((VARIANTARG *)((char *)this + 1208));
    v10 = *((_QWORD *)this + 5);
    *((_DWORD *)this + 308) = 1;
    if ( !*(_DWORD *)(v10 + 688) )
    {
      memset_0(Buffer, 0, 0x4Eu);
      pclsid = 0;
      if ( GetEnvironmentVariableW(L"JS_PROFILER", Buffer, 0x27u) )
      {
        if ( CLSIDFromString(Buffer, &pclsid) >= 0 )
          EEToProfInterfaceImpl::CreateAndInitializeProfiler((LPVOID *)this + 1, a2, &pclsid, 3u, 0);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002598  mov     [rsp+arg_18], rbx
0x18000259d  push    rsi
0x18000259e  push    rdi
0x18000259f  push    r14
0x1800025a1  sub     rsp, 0A0h
0x1800025a8  mov     rax, cs:__security_cookie
0x1800025af  xor     rax, rsp
0x1800025b2  mov     [rsp+0B8h+var_28], rax
0x1800025ba  mov     rbx, rcx
0x1800025bd  mov     rdi, r9
0x1800025c0  add     rcx, 378h; this
0x1800025c7  mov     r14, r8
0x1800025ca  mov     rsi, rdx
0x1800025cd  lea     rax, [rbx+198h]
0x1800025d4  mov     [rcx+20h], rax
0x1800025d8  mov     dword ptr [rcx+28h], 14h
0x1800025df  mov     qword ptr [rcx+2Ch], 18h
0x1800025e7  call    ?LinkToGc@IScavengerBase@@QEAAXXZ; IScavengerBase::LinkToGc(void)
0x1800025ec  mov     [rbx+3D8h], rdi
0x1800025f3  test    byte ptr [rsi+3A0h], 1
0x1800025fa  jnz     loc_1800026F1
0x180002600  lea     rcx, [rbx+48h]; struct GlobalBinder **
0x180002604  mov     rdx, rbx; struct CSession *
0x180002607  call    ?Create@GlobalBinder@@SAJPEAPEAV1@PEAVCSession@@@Z; GlobalBinder::Create(GlobalBinder * *,CSession *)
0x18000260c  test    eax, eax
0x18000260e  js      short loc_180002661
0x180002610  mov     [rbx+28h], rsi
0x180002614  lea     rdi, [rbx+428h]
0x18000261b  mov     rax, [r14]
0x18000261e  lea     rdx, IID_IActiveScriptSiteInterruptPoll
0x180002625  mov     r8, rdi
0x180002628  mov     rcx, r14
0x18000262b  mov     rax, [rax]
0x18000262e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002633  test    eax, eax
0x180002635  js      loc_180002734
0x18000263b  lea     rcx, [rbx+4B8h]; pvarg
0x180002642  call    cs:__imp_VariantInit
0x180002648  mov     rax, [rbx+28h]
0x18000264c  mov     dword ptr [rbx+4D0h], 1
0x180002656  cmp     dword ptr [rax+2B0h], 0
0x18000265d  jz      short loc_180002685
0x18000265f  xor     eax, eax
0x180002661  mov     rcx, [rsp+0B8h+var_28]
0x180002669  xor     rcx, rsp; StackCookie
0x18000266c  call    __security_check_cookie
0x180002671  mov     rbx, [rsp+0B8h+arg_18]
0x180002679  add     rsp, 0A0h
0x180002680  pop     r14
0x180002682  pop     rdi
0x180002683  pop     rsi
0x180002684  retn
0x180002685  xor     edx, edx; Val
0x180002687  lea     rcx, [rsp+0B8h+Buffer]; void *
0x18000268c  lea     r8d, [rdx+4Eh]; Size
0x180002690  call    memset_0
0x180002695  xorps   xmm0, xmm0
0x180002698  lea     rdx, [rsp+0B8h+Buffer]; lpBuffer
0x18000269d  mov     r8d, 27h ; '''; nSize
0x1800026a3  lea     rcx, Name; "JS_PROFILER"
0x1800026aa  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x1800026af  call    cs:__imp_GetEnvironmentVariableW
0x1800026b5  test    eax, eax
0x1800026b7  jz      short loc_18000265F
0x1800026b9  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x1800026be  lea     rcx, [rsp+0B8h+Buffer]; lpsz
0x1800026c3  call    cs:__imp_CLSIDFromString
0x1800026c9  test    eax, eax
0x1800026cb  js      short loc_18000265F
0x1800026cd  lea     rcx, [rbx+8]; ppv
0x1800026d1  mov     [rsp+0B8h+var_98], 0; unsigned int
0x1800026d9  mov     r9d, 3; unsigned int
0x1800026df  lea     r8, [rsp+0B8h+pclsid]; struct _GUID *
0x1800026e4  mov     rdx, rsi; struct COleScript *
0x1800026e7  call    ?CreateAndInitializeProfiler@EEToProfInterfaceImpl@@QEAAJPEAVCOleScript@@AEBU_GUID@@KK@Z; EEToProfInterfaceImpl::CreateAndInitializeProfiler(COleScript *,_GUID const &,ulong,ulong)
0x1800026ec  jmp     loc_18000265F
0x1800026f1  test    rdi, rdi
0x1800026f4  jz      short loc_180002718
0x1800026f6  mov     ecx, 58h ; 'X'; Size
0x1800026fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002700  test    rax, rax
0x180002703  jz      short loc_180002718
0x180002705  mov     r8d, 1; int
0x18000270b  mov     rdx, rdi; struct ThreadGlobals *
0x18000270e  mov     rcx, rax; this
0x180002711  call    ??0VarStack@@IEAA@PEAVThreadGlobals@@H@Z; VarStack::VarStack(ThreadGlobals *,int)
0x180002716  jmp     short loc_18000271A
0x180002718  xor     eax, eax
0x18000271a  mov     [rbx+4E0h], rax
0x180002721  test    rax, rax
0x180002724  jnz     loc_180002600
0x18000272a  mov     eax, 8007000Eh
0x18000272f  jmp     loc_180002661
0x180002734  mov     qword ptr [rdi], 0
0x18000273b  jmp     loc_18000263B
```
