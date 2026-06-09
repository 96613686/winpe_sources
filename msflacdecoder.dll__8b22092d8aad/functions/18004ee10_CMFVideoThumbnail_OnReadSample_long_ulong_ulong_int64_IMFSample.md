# CMFVideoThumbnail::OnReadSample(long,ulong,ulong,__int64,IMFSample *)

- ea: `0x18004ee10`
- end: `0x18004ef74`
- name: `?OnReadSample@CMFVideoThumbnail@@UEAAJJKK_JPEAUIMFSample@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, int, unsigned int, unsigned int, __int64, struct IMFSample *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001e80`
- `0x180017e64`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x18004c890`
- `0x18004ee10`
- `0x180050944`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004ef32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004ef32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ee4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ee4a`

## string_xrefs

- `0x18004ee56`: `CMFVideoThumbnail::OnReadSample`

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
  if ( _MFControlLevel_CTRLGUID_MF_CORE_SOURCES::GetLevel() >= 0x20u )
    WPP_SF_qqDDi(*((_QWORD *)WPP_GLOBAL_Control + 17));
  SetEvent(*((HANDLE *)this + 44));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return 0;
}

```

## disassembly

```asm
0x18004ee10  mov     [rsp+arg_8], rbx
0x18004ee15  mov     [rsp+arg_10], rbp
0x18004ee1a  push    rsi
0x18004ee1b  push    rdi
0x18004ee1c  push    r12
0x18004ee1e  push    r14
0x18004ee20  push    r15
0x18004ee22  sub     rsp, 60h
0x18004ee26  mov     rax, cs:__security_cookie
0x18004ee2d  xor     rax, rsp
0x18004ee30  mov     [rsp+88h+var_30], rax
0x18004ee35  mov     rbp, [rsp+88h+arg_28]
0x18004ee3d  mov     rsi, rcx
0x18004ee40  add     rcx, 18h; lpCriticalSection
0x18004ee44  mov     r14d, r9d
0x18004ee47  mov     r15d, edx
0x18004ee4a  call    cs:__imp_EnterCriticalSection
0x18004ee50  mov     r8d, 116h; int
0x18004ee56  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::OnReadSample"
0x18004ee5d  lea     rcx, [rsp+88h+var_48]; this
0x18004ee62  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ee67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004ee6e  cmp     byte ptr [rcx+8], 0
0x18004ee72  jz      short loc_18004EED0
0x18004ee74  cmp     qword ptr [rsi+180h], 0
0x18004ee7c  jz      short loc_18004EED0
0x18004ee7e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ee83  mov     rdx, [rsi+180h]
0x18004ee8a  mov     rdi, rax
0x18004ee8d  mov     rcx, [rdx]
0x18004ee90  mov     rax, [rcx+128h]
0x18004ee97  mov     rcx, rdx
0x18004ee9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee9f  mov     r8, [rsi+180h]
0x18004eea6  lea     rdx, [rsp+88h+var_40]
0x18004eeab  mov     ebx, eax
0x18004eead  mov     rcx, [r8]
0x18004eeb0  mov     rax, [rcx+118h]
0x18004eeb7  mov     rcx, r8
0x18004eeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eebf  movups  xmm0, xmmword ptr [rax]
0x18004eec2  mov     [rdi+7E0h], ebx
0x18004eec8  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004eed0  lea     rcx, [rsi+10h]; struct IUnknown **
0x18004eed4  cmp     [rcx], rbp
0x18004eed7  jz      short loc_18004EEE1
0x18004eed9  mov     rdx, rbp; struct IUnknown *
0x18004eedc  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004eee1  lea     r9, [rsi-10h]
0x18004eee5  mov     [rsi+16Ch], r14d
0x18004eeec  mov     [r9+178h], r15d
0x18004eef3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_SOURCES@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_SOURCES::GetLevel(void)
0x18004eef8  cmp     al, 20h ; ' '
0x18004eefa  jb      short loc_18004EF2B
0x18004eefc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef03  mov     rax, [rsp+88h+arg_20]
0x18004ef0b  mov     [rsp+88h+var_50], rax
0x18004ef10  mov     [rsp+88h+var_58], r14d
0x18004ef15  mov     rcx, [rcx+88h]
0x18004ef1c  mov     [rsp+88h+var_60], r15d
0x18004ef21  mov     [rsp+88h+var_68], rbp
0x18004ef26  call    WPP_SF_qqDDi
0x18004ef2b  mov     rcx, [rsi+160h]; hEvent
0x18004ef32  call    cs:__imp_SetEvent
0x18004ef38  lea     rcx, [rsp+88h+var_48]; this
0x18004ef3d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004ef42  lea     rcx, [rsi+18h]; lpCriticalSection
0x18004ef46  call    cs:__imp_LeaveCriticalSection
0x18004ef4c  xor     eax, eax
0x18004ef4e  mov     rcx, [rsp+88h+var_30]
0x18004ef53  xor     rcx, rsp; StackCookie
0x18004ef56  call    __security_check_cookie
0x18004ef5b  lea     r11, [rsp+88h+var_28]
0x18004ef60  mov     rbx, [r11+38h]
0x18004ef64  mov     rbp, [r11+40h]
0x18004ef68  mov     rsp, r11
0x18004ef6b  pop     r15
0x18004ef6d  pop     r14
0x18004ef6f  pop     r12
0x18004ef71  pop     rdi
0x18004ef72  pop     rsi
0x18004ef73  retn
```
