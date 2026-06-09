# CSession::Init(COleScript *,IActiveScriptSite *,ThreadGlobals *)

- ea: `0x18003ff3c`
- end: `0x1800400f7`
- name: `?Init@CSession@@IEAAJPEAVCOleScript@@PEAUIActiveScriptSite@@PEAVThreadGlobals@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct COleScript *, struct IActiveScriptSite *, struct ThreadGlobals *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003fa28`

## callees

- `0x18000c430`
- `0x18003ff3c`
- `0x180040100`
- `0x1800585d0`
- `0x180062938`
- `0x18007fc18`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003ffe6`
- `OLEAUT32!__imp_VariantInit` at `0x18003ffe6`
- `KERNEL32!GetEnvironmentVariableW` at `0x18004005a`
- `KERNEL32!GetEnvironmentVariableW` at `0x18004005a`
- `ole32!CLSIDFromString` at `0x180040074`
- `ole32!CLSIDFromString` at `0x180040074`

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
0x18003ff3c  mov     [rsp+arg_18], rbx
0x18003ff41  push    rsi
0x18003ff42  push    rdi
0x18003ff43  push    r14
0x18003ff45  sub     rsp, 0A0h
0x18003ff4c  mov     rax, cs:__security_cookie
0x18003ff53  xor     rax, rsp
0x18003ff56  mov     [rsp+0B8h+var_28], rax
0x18003ff5e  mov     rbx, rcx
0x18003ff61  mov     rdi, r9
0x18003ff64  add     rcx, 378h; this
0x18003ff6b  mov     r14, r8
0x18003ff6e  mov     rsi, rdx
0x18003ff71  lea     rax, [rbx+198h]
0x18003ff78  mov     [rcx+20h], rax
0x18003ff7c  mov     dword ptr [rcx+28h], 14h
0x18003ff83  mov     qword ptr [rcx+2Ch], 18h
0x18003ff8b  call    ?LinkToGc@IScavengerBase@@QEAAXXZ; IScavengerBase::LinkToGc(void)
0x18003ff90  mov     [rbx+3D8h], rdi
0x18003ff97  test    byte ptr [rsi+3A0h], 1
0x18003ff9e  jnz     loc_1800400A8
0x18003ffa4  lea     rcx, [rbx+48h]; struct GlobalBinder **
0x18003ffa8  mov     rdx, rbx; struct CSession *
0x18003ffab  call    ?Create@GlobalBinder@@SAJPEAPEAV1@PEAVCSession@@@Z; GlobalBinder::Create(GlobalBinder * *,CSession *)
0x18003ffb0  test    eax, eax
0x18003ffb2  js      short loc_18004000B
0x18003ffb4  mov     [rbx+28h], rsi
0x18003ffb8  lea     rdi, [rbx+428h]
0x18003ffbf  mov     rax, [r14]
0x18003ffc2  lea     rdx, IID_IActiveScriptSiteInterruptPoll
0x18003ffc9  mov     r8, rdi
0x18003ffcc  mov     rcx, r14
0x18003ffcf  mov     rax, [rax]
0x18003ffd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffd7  test    eax, eax
0x18003ffd9  js      loc_1800400EB
0x18003ffdf  lea     rcx, [rbx+4B8h]; pvarg
0x18003ffe6  call    cs:__imp_VariantInit
0x18003ffed  nop     dword ptr [rax+rax+00h]
0x18003fff2  mov     rax, [rbx+28h]
0x18003fff6  mov     dword ptr [rbx+4D0h], 1
0x180040000  cmp     dword ptr [rax+2B0h], 0
0x180040007  jz      short loc_180040030
0x180040009  xor     eax, eax
0x18004000b  mov     rcx, [rsp+0B8h+var_28]
0x180040013  xor     rcx, rsp; StackCookie
0x180040016  call    __security_check_cookie
0x18004001b  mov     rbx, [rsp+0B8h+arg_18]
0x180040023  add     rsp, 0A0h
0x18004002a  pop     r14
0x18004002c  pop     rdi
0x18004002d  pop     rsi
0x18004002e  retn
0x180040030  xor     edx, edx; Val
0x180040032  lea     rcx, [rsp+0B8h+Buffer]; void *
0x180040037  lea     r8d, [rdx+4Eh]; Size
0x18004003b  call    memset_0
0x180040040  xorps   xmm0, xmm0
0x180040043  lea     rdx, [rsp+0B8h+Buffer]; lpBuffer
0x180040048  mov     r8d, 27h ; '''; nSize
0x18004004e  lea     rcx, Name; "JS_PROFILER"
0x180040055  movups  xmmword ptr [rsp+0B8h+pclsid.Data1], xmm0
0x18004005a  call    cs:__imp_GetEnvironmentVariableW
0x180040061  nop     dword ptr [rax+rax+00h]
0x180040066  test    eax, eax
0x180040068  jz      short loc_180040009
0x18004006a  lea     rdx, [rsp+0B8h+pclsid]; pclsid
0x18004006f  lea     rcx, [rsp+0B8h+Buffer]; lpsz
0x180040074  call    cs:__imp_CLSIDFromString
0x18004007b  nop     dword ptr [rax+rax+00h]
0x180040080  test    eax, eax
0x180040082  js      short loc_180040009
0x180040084  lea     rcx, [rbx+8]; ppv
0x180040088  mov     [rsp+0B8h+var_98], 0; unsigned int
0x180040090  mov     r9d, 3; unsigned int
0x180040096  lea     r8, [rsp+0B8h+pclsid]; struct _GUID *
0x18004009b  mov     rdx, rsi; struct COleScript *
0x18004009e  call    ?CreateAndInitializeProfiler@EEToProfInterfaceImpl@@QEAAJPEAVCOleScript@@AEBU_GUID@@KK@Z; EEToProfInterfaceImpl::CreateAndInitializeProfiler(COleScript *,_GUID const &,ulong,ulong)
0x1800400a3  jmp     loc_180040009
0x1800400a8  test    rdi, rdi
0x1800400ab  jz      short loc_1800400CF
0x1800400ad  mov     ecx, 58h ; 'X'; Size
0x1800400b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800400b7  test    rax, rax
0x1800400ba  jz      short loc_1800400CF
0x1800400bc  mov     r8d, 1; int
0x1800400c2  mov     rdx, rdi; struct ThreadGlobals *
0x1800400c5  mov     rcx, rax; this
0x1800400c8  call    ??0VarStack@@IEAA@PEAVThreadGlobals@@H@Z; VarStack::VarStack(ThreadGlobals *,int)
0x1800400cd  jmp     short loc_1800400D1
0x1800400cf  xor     eax, eax
0x1800400d1  mov     [rbx+4E0h], rax
0x1800400d8  test    rax, rax
0x1800400db  jnz     loc_18003FFA4
0x1800400e1  mov     eax, 8007000Eh
0x1800400e6  jmp     loc_18004000B
0x1800400eb  mov     qword ptr [rdi], 0
0x1800400f2  jmp     loc_18003FFDF
```
