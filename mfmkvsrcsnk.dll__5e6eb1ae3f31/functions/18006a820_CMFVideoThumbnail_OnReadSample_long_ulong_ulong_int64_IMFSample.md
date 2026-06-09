# CMFVideoThumbnail::OnReadSample(long,ulong,ulong,__int64,IMFSample *)

- ea: `0x18006a820`
- end: `0x18006a984`
- name: `?OnReadSample@CMFVideoThumbnail@@UEAAJJKK_JPEAUIMFSample@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, int, unsigned int, unsigned int, __int64, struct IMFSample *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180052754`
- `0x18006a820`
- `0x18006c300`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a85a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a85a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a956`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a956`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a942`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006a942`

## string_xrefs

- `0x18006a866`: `CMFVideoThumbnail::OnReadSample`

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
  if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
    WPP_SF_qqDDi(*((_QWORD *)WPP_GLOBAL_Control + 17));
  SetEvent(*((HANDLE *)this + 44));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return 0;
}

```

## disassembly

```asm
0x18006a820  mov     [rsp+arg_8], rbx
0x18006a825  mov     [rsp+arg_10], rbp
0x18006a82a  push    rsi
0x18006a82b  push    rdi
0x18006a82c  push    r12
0x18006a82e  push    r14
0x18006a830  push    r15
0x18006a832  sub     rsp, 60h
0x18006a836  mov     rax, cs:__security_cookie
0x18006a83d  xor     rax, rsp
0x18006a840  mov     [rsp+88h+var_30], rax
0x18006a845  mov     rbp, [rsp+88h+arg_28]
0x18006a84d  mov     rsi, rcx
0x18006a850  add     rcx, 18h; lpCriticalSection
0x18006a854  mov     r14d, r9d
0x18006a857  mov     r15d, edx
0x18006a85a  call    cs:__imp_EnterCriticalSection
0x18006a860  mov     r8d, 116h; int
0x18006a866  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::OnReadSample"
0x18006a86d  lea     rcx, [rsp+88h+var_48]; this
0x18006a872  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006a877  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006a87e  cmp     byte ptr [rcx+8], 0
0x18006a882  jz      short loc_18006A8E0
0x18006a884  cmp     qword ptr [rsi+180h], 0
0x18006a88c  jz      short loc_18006A8E0
0x18006a88e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a893  mov     rdx, [rsi+180h]
0x18006a89a  mov     rdi, rax
0x18006a89d  mov     rcx, [rdx]
0x18006a8a0  mov     rax, [rcx+128h]
0x18006a8a7  mov     rcx, rdx
0x18006a8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8af  mov     r8, [rsi+180h]
0x18006a8b6  lea     rdx, [rsp+88h+var_40]
0x18006a8bb  mov     ebx, eax
0x18006a8bd  mov     rcx, [r8]
0x18006a8c0  mov     rax, [rcx+118h]
0x18006a8c7  mov     rcx, r8
0x18006a8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8cf  movups  xmm0, xmmword ptr [rax]
0x18006a8d2  mov     [rdi+7E0h], ebx
0x18006a8d8  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006a8e0  lea     rcx, [rsi+10h]; struct IUnknown **
0x18006a8e4  cmp     [rcx], rbp
0x18006a8e7  jz      short loc_18006A8F1
0x18006a8e9  mov     rdx, rbp; struct IUnknown *
0x18006a8ec  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18006a8f1  lea     r9, [rsi-10h]
0x18006a8f5  mov     [rsi+16Ch], r14d
0x18006a8fc  mov     [r9+178h], r15d
0x18006a903  cmp     cs:byte_1800D78D3, 20h ; ' '
0x18006a90a  jb      short loc_18006A93B
0x18006a90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a913  mov     rax, [rsp+88h+arg_20]
0x18006a91b  mov     [rsp+88h+var_50], rax
0x18006a920  mov     [rsp+88h+var_58], r14d
0x18006a925  mov     rcx, [rcx+88h]
0x18006a92c  mov     [rsp+88h+var_60], r15d
0x18006a931  mov     [rsp+88h+var_68], rbp
0x18006a936  call    WPP_SF_qqDDi
0x18006a93b  mov     rcx, [rsi+160h]; hEvent
0x18006a942  call    cs:__imp_SetEvent
0x18006a948  lea     rcx, [rsp+88h+var_48]; this
0x18006a94d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006a952  lea     rcx, [rsi+18h]; lpCriticalSection
0x18006a956  call    cs:__imp_LeaveCriticalSection
0x18006a95c  xor     eax, eax
0x18006a95e  mov     rcx, [rsp+88h+var_30]
0x18006a963  xor     rcx, rsp; StackCookie
0x18006a966  call    __security_check_cookie
0x18006a96b  lea     r11, [rsp+88h+var_28]
0x18006a970  mov     rbx, [r11+38h]
0x18006a974  mov     rbp, [r11+40h]
0x18006a978  mov     rsp, r11
0x18006a97b  pop     r15
0x18006a97d  pop     r14
0x18006a97f  pop     r12
0x18006a981  pop     rdi
0x18006a982  pop     rsi
0x18006a983  retn
```
