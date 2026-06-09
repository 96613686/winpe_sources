# MkvReader::GetByteStreamOriginName(ushort * *,uint *)

- ea: `0x180043aa4`
- end: `0x180043c9a`
- name: `?GetByteStreamOriginName@MkvReader@@QEAAJPEAPEAGPEAI@Z`
- size: `502`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800129b8`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180043aa4`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043b20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043bd7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043b20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043bd7`

## string_xrefs

- `0x180043ace`: `MkvReader::GetByteStreamOriginName`
- `0x180043b7d`: `MkvReader::GetByteStreamOriginName`
- `0x180043c34`: `MkvReader::GetByteStreamOriginName`

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
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180043aa4  mov     rax, rsp
0x180043aa7  mov     [rax+10h], rbx
0x180043aab  mov     [rax+18h], rbp
0x180043aaf  push    rsi
0x180043ab0  push    rdi
0x180043ab1  push    r14
0x180043ab3  sub     rsp, 30h
0x180043ab7  mov     rbp, r8
0x180043aba  mov     r14, rdx
0x180043abd  mov     rsi, rcx
0x180043ac0  mov     qword ptr [rax+20h], 0
0x180043ac8  mov     r8d, 59h ; 'Y'; int
0x180043ace  lea     rdx, aMkvreaderGetby; "MkvReader::GetByteStreamOriginName"
0x180043ad5  lea     rcx, [rax+8]; this
0x180043ad9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180043ade  nop
0x180043adf  mov     rdi, [rsi+10h]
0x180043ae3  mov     rax, [rdi]
0x180043ae6  mov     rbx, [rax]
0x180043ae9  lea     rcx, [rsp+48h+arg_18]
0x180043aee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043af3  lea     r8, [rsp+48h+arg_18]
0x180043af8  lea     rdx, IID_IMFAttributes
0x180043aff  mov     rcx, rdi
0x180043b02  mov     rax, rbx
0x180043b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b0a  mov     ebx, eax
0x180043b0c  test    eax, eax
0x180043b0e  jns     loc_180043BA3
0x180043b14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043b1b  test    rcx, rcx
0x180043b1e  jnz     short loc_180043B61
0x180043b20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043b26  mov     rcx, rax
0x180043b29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043b30  test    rax, rax
0x180043b33  jz      short loc_180043B53
0x180043b35  mov     rax, [rax]
0x180043b38  mov     edx, 7F0h
0x180043b3d  mov     rax, [rax+8]
0x180043b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b46  test    eax, eax
0x180043b48  jz      short loc_180043B53
0x180043b4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043b51  jmp     short loc_180043B61
0x180043b53  lea     rcx, qword_1800D6F70; this
0x180043b5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043b61  cmp     byte ptr [rcx+8], 0
0x180043b65  jz      short loc_180043B8C
0x180043b67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043b6c  cmp     [rax+7CCh], ebx
0x180043b72  jz      short loc_180043B8C
0x180043b74  mov     r9d, ebx; int
0x180043b77  mov     r8d, 59h ; 'Y'; int
0x180043b7d  lea     rdx, aMkvreaderGetby; "MkvReader::GetByteStreamOriginName"
0x180043b84  mov     rcx, rax; this
0x180043b87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043b8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043b93  jb      loc_180043C70
0x180043b99  mov     edx, 0Eh
0x180043b9e  jmp     loc_180043C51
0x180043ba3  mov     rcx, [rsp+48h+arg_18]
0x180043ba8  mov     rax, [rcx]
0x180043bab  mov     r9, rbp
0x180043bae  mov     r8, r14
0x180043bb1  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x180043bb8  mov     rax, [rax+68h]
0x180043bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bc1  mov     ebx, eax
0x180043bc3  test    eax, eax
0x180043bc5  jns     loc_180043C70
0x180043bcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043bd2  test    rcx, rcx
0x180043bd5  jnz     short loc_180043C18
0x180043bd7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043bdd  mov     rcx, rax
0x180043be0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043be7  test    rax, rax
0x180043bea  jz      short loc_180043C0A
0x180043bec  mov     rax, [rax]
0x180043bef  mov     edx, 7F0h
0x180043bf4  mov     rax, [rax+8]
0x180043bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bfd  test    eax, eax
0x180043bff  jz      short loc_180043C0A
0x180043c01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043c08  jmp     short loc_180043C18
0x180043c0a  lea     rcx, qword_1800D6F70; this
0x180043c11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043c18  cmp     byte ptr [rcx+8], 0
0x180043c1c  jz      short loc_180043C43
0x180043c1e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043c23  cmp     [rax+7CCh], ebx
0x180043c29  jz      short loc_180043C43
0x180043c2b  mov     r9d, ebx; int
0x180043c2e  mov     r8d, 5Ah ; 'Z'; int
0x180043c34  lea     rdx, aMkvreaderGetby; "MkvReader::GetByteStreamOriginName"
0x180043c3b  mov     rcx, rax; this
0x180043c3e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043c43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043c4a  jb      short loc_180043C70
0x180043c4c  mov     edx, 0Fh
0x180043c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c58  mov     [rsp+48h+var_28], ebx
0x180043c5c  mov     r9, rsi
0x180043c5f  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180043c66  mov     rcx, [rcx+10h]
0x180043c6a  call    WPP_SF_qD
0x180043c6f  nop
0x180043c70  lea     rcx, [rsp+48h+arg_0]; this
0x180043c75  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180043c7a  nop
0x180043c7b  lea     rcx, [rsp+48h+arg_18]
0x180043c80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043c85  mov     eax, ebx
0x180043c87  mov     rbx, [rsp+48h+arg_8]
0x180043c8c  mov     rbp, [rsp+48h+arg_10]
0x180043c91  add     rsp, 30h
0x180043c95  pop     r14
0x180043c97  pop     rdi
0x180043c98  pop     rsi
0x180043c99  retn
```
