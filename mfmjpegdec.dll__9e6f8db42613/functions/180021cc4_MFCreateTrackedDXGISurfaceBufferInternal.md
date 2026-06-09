# MFCreateTrackedDXGISurfaceBufferInternal

- ea: `0x180021cc4`
- end: `0x180021f65`
- name: `MFCreateTrackedDXGISurfaceBufferInternal`
- size: `673`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, struct IUnknown *@<rdx>, unsigned int@<r8d>, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004897c`
- `0x1800492f0`
- `0x18004e4ec`
- `0x18004f9d0`

## callees

- `0x180020598`
- `0x180021cc4`
- `0x1800231fc`
- `0x18005936c`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021da4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021e66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021da4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021e66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ef2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021d5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021e1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021ee2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021d5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021e1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021ee2`

## string_xrefs

- `0x180021f41`: `MFCreateTrackedDXGISurfaceBufferInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MFCreateTrackedDXGISurfaceBufferInternal(
        struct _GUID *a1,
        struct IUnknown *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rax
  int Instance; // ebx
  CallStackTracing *v10; // rdi
  CallStackContext *v11; // rsi
  DWORD LastError; // ebp
  CallStackContext *Value; // rax
  CallStackTracing *v14; // rcx
  __int64 v15; // rax
  int v16; // r8d
  __int64 v17; // r9
  CallStackTracing *v18; // rdi
  DWORD v19; // ebp
  CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax
  CallStackTracing *v23; // rdi
  DWORD v24; // ebp
  CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  struct IMFMediaBuffer *v29[7]; // [rsp+30h] [rbp-38h] BYREF

  v29[0] = 0;
  v8 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_696442be_a72e_4059_bc79_5b5c98040fad.Data1;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_696442be_a72e_4059_bc79_5b5c98040fad.Data1 )
    v8 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_696442be_a72e_4059_bc79_5b5c98040fad.Data4;
  if ( !v8 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
    Instance = CMFD3D12Buffer::CreateInstance(a1, a2, a3, v29);
    if ( Instance < 0 )
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v11 = (CallStackTracing *)((char *)v10 + 208);
        LastError = GetLastError();
        Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v10 + 3));
        if ( Value )
        {
          v11 = Value;
        }
        else if ( !GetLastError() )
        {
          v14 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v14 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v15 = (**(__int64 (__fastcall ***)(CallStackTracing *))v14)(v14);
          if ( v15 )
            v11 = (CallStackContext *)v15;
        }
        SetLastError(LastError);
        if ( *((_DWORD *)v11 + 499) != Instance )
        {
          v16 = 30;
LABEL_43:
          CallStackContext::TraceFailure(v11, "MFCreateTrackedDXGISurfaceBufferInternal", v16, Instance);
          goto LABEL_44;
        }
      }
      goto LABEL_44;
    }
LABEL_30:
    Instance = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, GUID *, __int64))v29[0]->lpVtbl->QueryInterface)(
                 v29[0],
                 &GUID_b3963187_f0c6_4996_93e5_2265739cf1af,
                 a5);
    if ( Instance < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v11 = (CallStackTracing *)((char *)v23 + 208);
        v24 = GetLastError();
        v25 = (CallStackContext *)TlsGetValue(*((_DWORD *)v23 + 3));
        if ( v25 )
        {
          v11 = v25;
        }
        else if ( !GetLastError() )
        {
          v26 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
          if ( v27 )
            v11 = (CallStackContext *)v27;
        }
        SetLastError(v24);
        if ( *((_DWORD *)v11 + 499) != Instance )
        {
          v16 = 43;
          goto LABEL_43;
        }
      }
    }
    goto LABEL_44;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
  Instance = CMFDX11SurfaceBuffer::CreateInstance(a1, a2, a3, v17, v29);
  if ( Instance >= 0 )
    goto LABEL_30;
  v18 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)&qword_18009CF60;
    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v11 = (CallStackTracing *)((char *)v18 + 208);
    v19 = GetLastError();
    v20 = (CallStackContext *)TlsGetValue(*((_DWORD *)v18 + 3));
    if ( v20 )
    {
      v11 = v20;
    }
    else if ( !GetLastError() )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
      if ( v22 )
        v11 = (CallStackContext *)v22;
    }
    SetLastError(v19);
    if ( *((_DWORD *)v11 + 499) != Instance )
    {
      v16 = 40;
      goto LABEL_43;
    }
  }
LABEL_44:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180021cc4  push    rbx
0x180021cc6  push    rbp
0x180021cc7  push    rsi
0x180021cc8  push    rdi
0x180021cc9  sub     rsp, 48h
0x180021ccd  mov     edi, r8d
0x180021cd0  mov     rsi, rdx
0x180021cd3  mov     rbx, rcx
0x180021cd6  mov     [rsp+68h+var_38], 0
0x180021cdf  mov     rax, [rcx]
0x180021ce2  sub     rax, qword ptr cs:_GUID_696442be_a72e_4059_bc79_5b5c98040fad.Data1
0x180021ce9  jnz     short loc_180021CF6
0x180021ceb  mov     rax, [rcx+8]
0x180021cef  sub     rax, qword ptr cs:_GUID_696442be_a72e_4059_bc79_5b5c98040fad.Data4
0x180021cf6  lea     rcx, [rsp+68h+var_38]
0x180021cfb  test    rax, rax
0x180021cfe  jnz     loc_180021DC1
0x180021d04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021d09  lea     r9, [rsp+68h+var_38]; struct IMFMediaBuffer **
0x180021d0e  mov     r8d, edi; unsigned int
0x180021d11  mov     rdx, rsi; struct IUnknown *
0x180021d14  mov     rcx, rbx; struct _GUID *
0x180021d17  call    ?CreateInstance@CMFD3D12Buffer@@SAJAEBU_GUID@@PEAUIUnknown@@IPEAPEAUIMFMediaBuffer@@@Z; CMFD3D12Buffer::CreateInstance(_GUID const &,IUnknown *,uint,IMFMediaBuffer * *)
0x180021d1c  mov     ebx, eax
0x180021d1e  test    eax, eax
0x180021d20  jns     loc_180021E83
0x180021d26  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021d2d  test    rdi, rdi
0x180021d30  jnz     short loc_180021D40
0x180021d32  lea     rdi, qword_18009CF60
0x180021d39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180021d40  cmp     byte ptr [rdi+8], 0
0x180021d44  jz      loc_180021F50
0x180021d4a  lea     rsi, [rdi+0D0h]
0x180021d51  call    cs:__imp_GetLastError
0x180021d57  mov     ebp, eax
0x180021d59  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180021d5c  call    cs:__imp_TlsGetValue
0x180021d62  test    rax, rax
0x180021d65  jz      short loc_180021D6C
0x180021d67  mov     rsi, rax
0x180021d6a  jmp     short loc_180021DA2
0x180021d6c  call    cs:__imp_GetLastError
0x180021d72  test    eax, eax
0x180021d74  jnz     short loc_180021DA2
0x180021d76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021d7d  test    rcx, rcx
0x180021d80  jnz     short loc_180021D90
0x180021d82  lea     rcx, qword_18009CF60
0x180021d89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021d90  mov     rax, [rcx]
0x180021d93  mov     rax, [rax]
0x180021d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d9b  test    rax, rax
0x180021d9e  cmovnz  rsi, rax
0x180021da2  mov     ecx, ebp; dwErrCode
0x180021da4  call    cs:__imp_SetLastError
0x180021daa  cmp     [rsi+7CCh], ebx
0x180021db0  jz      loc_180021F50
0x180021db6  mov     r8d, 1Eh
0x180021dbc  jmp     loc_180021F3E
0x180021dc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021dc6  lea     rax, [rsp+68h+var_38]
0x180021dcb  mov     [rsp+68h+var_48], rax; struct IMFMediaBuffer **
0x180021dd0  mov     r8d, edi; unsigned int
0x180021dd3  mov     rdx, rsi; struct IUnknown *
0x180021dd6  mov     rcx, rbx; struct _GUID *
0x180021dd9  call    ?CreateInstance@CMFDX11SurfaceBuffer@@SAJAEBU_GUID@@PEAUIUnknown@@IHPEAPEAUIMFMediaBuffer@@@Z; CMFDX11SurfaceBuffer::CreateInstance(_GUID const &,IUnknown *,uint,int,IMFMediaBuffer * *)
0x180021dde  mov     ebx, eax
0x180021de0  test    eax, eax
0x180021de2  jns     loc_180021E83
0x180021de8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021def  test    rdi, rdi
0x180021df2  jnz     short loc_180021E02
0x180021df4  lea     rdi, qword_18009CF60
0x180021dfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180021e02  cmp     byte ptr [rdi+8], 0
0x180021e06  jz      loc_180021F50
0x180021e0c  lea     rsi, [rdi+0D0h]
0x180021e13  call    cs:__imp_GetLastError
0x180021e19  mov     ebp, eax
0x180021e1b  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180021e1e  call    cs:__imp_TlsGetValue
0x180021e24  test    rax, rax
0x180021e27  jz      short loc_180021E2E
0x180021e29  mov     rsi, rax
0x180021e2c  jmp     short loc_180021E64
0x180021e2e  call    cs:__imp_GetLastError
0x180021e34  test    eax, eax
0x180021e36  jnz     short loc_180021E64
0x180021e38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021e3f  test    rcx, rcx
0x180021e42  jnz     short loc_180021E52
0x180021e44  lea     rcx, qword_18009CF60
0x180021e4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021e52  mov     rax, [rcx]
0x180021e55  mov     rax, [rax]
0x180021e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e5d  test    rax, rax
0x180021e60  cmovnz  rsi, rax
0x180021e64  mov     ecx, ebp; dwErrCode
0x180021e66  call    cs:__imp_SetLastError
0x180021e6c  cmp     [rsi+7CCh], ebx
0x180021e72  jz      loc_180021F50
0x180021e78  mov     r8d, 28h ; '('
0x180021e7e  jmp     loc_180021F3E
0x180021e83  mov     rcx, [rsp+68h+var_38]
0x180021e88  mov     rax, [rcx]
0x180021e8b  mov     r8, [rsp+68h+arg_20]
0x180021e93  lea     rdx, _GUID_b3963187_f0c6_4996_93e5_2265739cf1af
0x180021e9a  mov     rax, [rax]
0x180021e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ea2  mov     ebx, eax
0x180021ea4  test    eax, eax
0x180021ea6  jns     loc_180021F50
0x180021eac  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021eb3  test    rdi, rdi
0x180021eb6  jnz     short loc_180021EC6
0x180021eb8  lea     rdi, qword_18009CF60
0x180021ebf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180021ec6  cmp     byte ptr [rdi+8], 0
0x180021eca  jz      loc_180021F50
0x180021ed0  lea     rsi, [rdi+0D0h]
0x180021ed7  call    cs:__imp_GetLastError
0x180021edd  mov     ebp, eax
0x180021edf  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180021ee2  call    cs:__imp_TlsGetValue
0x180021ee8  test    rax, rax
0x180021eeb  jz      short loc_180021EF2
0x180021eed  mov     rsi, rax
0x180021ef0  jmp     short loc_180021F28
0x180021ef2  call    cs:__imp_GetLastError
0x180021ef8  test    eax, eax
0x180021efa  jnz     short loc_180021F28
0x180021efc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021f03  test    rcx, rcx
0x180021f06  jnz     short loc_180021F16
0x180021f08  lea     rcx, qword_18009CF60
0x180021f0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021f16  mov     rax, [rcx]
0x180021f19  mov     rax, [rax]
0x180021f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f21  test    rax, rax
0x180021f24  cmovnz  rsi, rax
0x180021f28  mov     ecx, ebp; dwErrCode
0x180021f2a  call    cs:__imp_SetLastError
0x180021f30  cmp     [rsi+7CCh], ebx
0x180021f36  jz      short loc_180021F50
0x180021f38  mov     r8d, 2Bh ; '+'; int
0x180021f3e  mov     r9d, ebx; int
0x180021f41  lea     rdx, aMfcreatetracke; "MFCreateTrackedDXGISurfaceBufferInterna"...
0x180021f48  mov     rcx, rsi; this
0x180021f4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021f50  lea     rcx, [rsp+68h+var_38]
0x180021f55  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021f5a  mov     eax, ebx
0x180021f5c  add     rsp, 48h
0x180021f60  pop     rdi
0x180021f61  pop     rsi
0x180021f62  pop     rbp
0x180021f63  pop     rbx
0x180021f64  retn
```
