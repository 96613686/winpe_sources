# CMFVideoThumbnail::OnReadSample(long,ulong,ulong,__int64,IMFSample *)

- ea: `0x18006d550`
- end: `0x18006d6c7`
- name: `?OnReadSample@CMFVideoThumbnail@@UEAAJJKK_JPEAUIMFSample@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, int, unsigned int, unsigned int, __int64, struct IMFSample *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180054a9c`
- `0x18006d550`
- `0x18006f110`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d58a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d58a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d692`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d692`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006d678`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006d678`

## string_xrefs

- `0x18006d59c`: `CMFVideoThumbnail::OnReadSample`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::OnReadSample(
        CMFVideoThumbnail *this,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        struct IUnknown *a6)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 v11; // xmm0
  _BYTE v13[8]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v14[16]; // [rsp+48h] [rbp-40h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v13, "CMFVideoThumbnail::OnReadSample", 278);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 48) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 296LL))(*((_QWORD *)this + 48));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 48) + 280LL))(
                       *((_QWORD *)this + 48),
                       v14);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v11;
  }
  if ( *((struct IUnknown **)this + 2) != a6 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 2, a6);
  *((_DWORD *)this + 91) = a4;
  *((_DWORD *)this + 90) = a2;
  if ( (unsigned __int8)byte_1800DC8D3 >= 0x20u )
    WPP_SF_qqDDi(*((_QWORD *)WPP_GLOBAL_Control + 17));
  SetEvent(*((HANDLE *)this + 44));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return 0;
}

```

## disassembly

```asm
0x18006d550  mov     [rsp+arg_8], rbx
0x18006d555  mov     [rsp+arg_10], rbp
0x18006d55a  push    rsi
0x18006d55b  push    rdi
0x18006d55c  push    r12
0x18006d55e  push    r14
0x18006d560  push    r15
0x18006d562  sub     rsp, 60h
0x18006d566  mov     rax, cs:__security_cookie
0x18006d56d  xor     rax, rsp
0x18006d570  mov     [rsp+88h+var_30], rax
0x18006d575  mov     rbp, [rsp+88h+arg_28]
0x18006d57d  mov     rsi, rcx
0x18006d580  add     rcx, 18h; lpCriticalSection
0x18006d584  mov     r14d, r9d
0x18006d587  mov     r15d, edx
0x18006d58a  call    cs:__imp_EnterCriticalSection
0x18006d591  nop     dword ptr [rax+rax+00h]
0x18006d596  mov     r8d, 116h; int
0x18006d59c  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::OnReadSample"
0x18006d5a3  lea     rcx, [rsp+88h+var_48]; this
0x18006d5a8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006d5ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006d5b4  cmp     byte ptr [rcx+8], 0
0x18006d5b8  jz      short loc_18006D616
0x18006d5ba  cmp     qword ptr [rsi+180h], 0
0x18006d5c2  jz      short loc_18006D616
0x18006d5c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d5c9  mov     rdx, [rsi+180h]
0x18006d5d0  mov     rdi, rax
0x18006d5d3  mov     rcx, [rdx]
0x18006d5d6  mov     rax, [rcx+128h]
0x18006d5dd  mov     rcx, rdx
0x18006d5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5e5  mov     r8, [rsi+180h]
0x18006d5ec  lea     rdx, [rsp+88h+var_40]
0x18006d5f1  mov     ebx, eax
0x18006d5f3  mov     rcx, [r8]
0x18006d5f6  mov     rax, [rcx+118h]
0x18006d5fd  mov     rcx, r8
0x18006d600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d605  movups  xmm0, xmmword ptr [rax]
0x18006d608  mov     [rdi+7E0h], ebx
0x18006d60e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006d616  lea     rcx, [rsi+10h]; struct IUnknown **
0x18006d61a  cmp     [rcx], rbp
0x18006d61d  jz      short loc_18006D627
0x18006d61f  mov     rdx, rbp; struct IUnknown *
0x18006d622  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18006d627  lea     r9, [rsi-10h]
0x18006d62b  mov     [rsi+16Ch], r14d
0x18006d632  mov     [r9+178h], r15d
0x18006d639  cmp     cs:byte_1800DC8D3, 20h ; ' '
0x18006d640  jb      short loc_18006D671
0x18006d642  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d649  mov     rax, [rsp+88h+arg_20]
0x18006d651  mov     [rsp+88h+var_50], rax
0x18006d656  mov     [rsp+88h+var_58], r14d
0x18006d65b  mov     rcx, [rcx+88h]
0x18006d662  mov     [rsp+88h+var_60], r15d
0x18006d667  mov     [rsp+88h+var_68], rbp
0x18006d66c  call    WPP_SF_qqDDi
0x18006d671  mov     rcx, [rsi+160h]; hEvent
0x18006d678  call    cs:__imp_SetEvent
0x18006d67f  nop     dword ptr [rax+rax+00h]
0x18006d684  lea     rcx, [rsp+88h+var_48]; this
0x18006d689  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006d68e  lea     rcx, [rsi+18h]; lpCriticalSection
0x18006d692  call    cs:__imp_LeaveCriticalSection
0x18006d699  nop     dword ptr [rax+rax+00h]
0x18006d69e  xor     eax, eax
0x18006d6a0  mov     rcx, [rsp+88h+var_30]
0x18006d6a5  xor     rcx, rsp; StackCookie
0x18006d6a8  call    __security_check_cookie
0x18006d6ad  lea     r11, [rsp+88h+var_28]
0x18006d6b2  mov     rbx, [r11+38h]
0x18006d6b6  mov     rbp, [r11+40h]
0x18006d6ba  mov     rsp, r11
0x18006d6bd  pop     r15
0x18006d6bf  pop     r14
0x18006d6c1  pop     r12
0x18006d6c3  pop     rdi
0x18006d6c4  pop     rsi
0x18006d6c5  retn
```
