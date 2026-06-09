# MkvReader::GetByteStreamOriginName(ushort * *,uint *)

- ea: `0x1800458ac`
- end: `0x180045aaf`
- name: `?GetByteStreamOriginName@MkvReader@@QEAAJPEAPEAGPEAI@Z`
- size: `515`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180013248`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800458ac`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800459e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800459e5`

## string_xrefs

- `0x1800458d6`: `MkvReader::GetByteStreamOriginName`
- `0x18004598b`: `MkvReader::GetByteStreamOriginName`
- `0x180045a48`: `MkvReader::GetByteStreamOriginName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::GetByteStreamOriginName(MkvReader *this, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v23; // [rsp+50h] [rbp+8h] BYREF
  __int64 v24; // [rsp+68h] [rbp+20h] BYREF

  v24 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v23, "MkvReader::GetByteStreamOriginName", 89);
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  v7 = **v6;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v9 = v7(v6, &IID_IMFAttributes, &v24);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const IID *, unsigned __int16 **, unsigned int *))(*(_QWORD *)v24 + 104LL))(
           v24,
           &MF_BYTESTREAM_ORIGIN_NAME,
           a2,
           a3);
    if ( v9 < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::GetByteStreamOriginName", 90, v9);
      }
      if ( g_wppLevels )
      {
        v15 = 15;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v9 )
        CallStackContext::TraceFailure(v14, "MkvReader::GetByteStreamOriginName", 89, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 14;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v9);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800458ac  mov     rax, rsp
0x1800458af  mov     [rax+10h], rbx
0x1800458b3  mov     [rax+18h], rbp
0x1800458b7  push    rsi
0x1800458b8  push    rdi
0x1800458b9  push    r14
0x1800458bb  sub     rsp, 30h
0x1800458bf  mov     rbp, r8
0x1800458c2  mov     r14, rdx
0x1800458c5  mov     rsi, rcx
0x1800458c8  mov     qword ptr [rax+20h], 0
0x1800458d0  mov     r8d, 59h ; 'Y'; int
0x1800458d6  lea     rdx, aMkvreaderGetby; "MkvReader::GetByteStreamOriginName"
0x1800458dd  lea     rcx, [rax+8]; this
0x1800458e1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800458e6  nop
0x1800458e7  mov     rdi, [rsi+10h]
0x1800458eb  mov     rax, [rdi]
0x1800458ee  mov     rbx, [rax]
0x1800458f1  lea     rcx, [rsp+48h+arg_18]
0x1800458f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800458fb  lea     r8, [rsp+48h+arg_18]
0x180045900  lea     rdx, IID_IMFAttributes
0x180045907  mov     rcx, rdi
0x18004590a  mov     rax, rbx
0x18004590d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045912  mov     ebx, eax
0x180045914  test    eax, eax
0x180045916  jns     loc_1800459B1
0x18004591c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045923  test    rcx, rcx
0x180045926  jnz     short loc_18004596F
0x180045928  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004592f  nop     dword ptr [rax+rax+00h]
0x180045934  mov     rcx, rax
0x180045937  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004593e  test    rax, rax
0x180045941  jz      short loc_180045961
0x180045943  mov     rax, [rax]
0x180045946  mov     edx, 7F0h
0x18004594b  mov     rax, [rax+8]
0x18004594f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045954  test    eax, eax
0x180045956  jz      short loc_180045961
0x180045958  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004595f  jmp     short loc_18004596F
0x180045961  lea     rcx, qword_1800DBF70; this
0x180045968  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004596f  cmp     byte ptr [rcx+8], 0
0x180045973  jz      short loc_18004599A
0x180045975  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004597a  cmp     [rax+7CCh], ebx
0x180045980  jz      short loc_18004599A
0x180045982  mov     r9d, ebx; int
0x180045985  mov     r8d, 59h ; 'Y'; int
0x18004598b  lea     rdx, aMkvreaderGetby; "MkvReader::GetByteStreamOriginName"
0x180045992  mov     rcx, rax; this
0x180045995  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004599a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800459a1  jb      loc_180045A84
0x1800459a7  mov     edx, 0Eh
0x1800459ac  jmp     loc_180045A65
0x1800459b1  mov     rcx, [rsp+48h+arg_18]
0x1800459b6  mov     rax, [rcx]
0x1800459b9  mov     r9, rbp
0x1800459bc  mov     r8, r14
0x1800459bf  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x1800459c6  mov     rax, [rax+68h]
0x1800459ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459cf  mov     ebx, eax
0x1800459d1  test    eax, eax
0x1800459d3  jns     loc_180045A84
0x1800459d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800459e0  test    rcx, rcx
0x1800459e3  jnz     short loc_180045A2C
0x1800459e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800459ec  nop     dword ptr [rax+rax+00h]
0x1800459f1  mov     rcx, rax
0x1800459f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800459fb  test    rax, rax
0x1800459fe  jz      short loc_180045A1E
0x180045a00  mov     rax, [rax]
0x180045a03  mov     edx, 7F0h
0x180045a08  mov     rax, [rax+8]
0x180045a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a11  test    eax, eax
0x180045a13  jz      short loc_180045A1E
0x180045a15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a1c  jmp     short loc_180045A2C
0x180045a1e  lea     rcx, qword_1800DBF70; this
0x180045a25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a2c  cmp     byte ptr [rcx+8], 0
0x180045a30  jz      short loc_180045A57
0x180045a32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045a37  cmp     [rax+7CCh], ebx
0x180045a3d  jz      short loc_180045A57
0x180045a3f  mov     r9d, ebx; int
0x180045a42  mov     r8d, 5Ah ; 'Z'; int
0x180045a48  lea     rdx, aMkvreaderGetby; "MkvReader::GetByteStreamOriginName"
0x180045a4f  mov     rcx, rax; this
0x180045a52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045a57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045a5e  jb      short loc_180045A84
0x180045a60  mov     edx, 0Fh
0x180045a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a6c  mov     [rsp+48h+var_28], ebx
0x180045a70  mov     r9, rsi
0x180045a73  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180045a7a  mov     rcx, [rcx+10h]
0x180045a7e  call    WPP_SF_qD
0x180045a83  nop
0x180045a84  lea     rcx, [rsp+48h+arg_0]; this
0x180045a89  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045a8e  nop
0x180045a8f  lea     rcx, [rsp+48h+arg_18]
0x180045a94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045a99  mov     eax, ebx
0x180045a9b  mov     rbx, [rsp+48h+arg_8]
0x180045aa0  mov     rbp, [rsp+48h+arg_10]
0x180045aa5  add     rsp, 30h
0x180045aa9  pop     r14
0x180045aab  pop     rdi
0x180045aac  pop     rsi
0x180045aad  retn
```
