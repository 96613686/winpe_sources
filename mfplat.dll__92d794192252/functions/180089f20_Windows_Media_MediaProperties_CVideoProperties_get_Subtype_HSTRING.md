# Windows::Media::MediaProperties::CVideoProperties::get_Subtype(HSTRING__ * *)

- ea: `0x180089f20`
- end: `0x18008a261`
- name: `?get_Subtype@CVideoProperties@MediaProperties@Media@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `833`
- prototype: `int(Windows::Media::MediaProperties::CVideoProperties *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18002146c`
- `0x180024390`
- `0x180035e28`
- `0x180089f20`
- `0x18008a268`
- `0x1800c791c`
- `0x1801200d0`
- `0x180121575`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180089f54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180089f54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a0c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a0c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008a005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008a088`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008a005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008a088`

## pseudocode

```c
__int64 __fastcall Windows::Media::MediaProperties::CVideoProperties::get_Subtype(
        Windows::Media::MediaProperties::CVideoProperties *this,
        HSTRING *a2)
{
  Microsoft::WRL::Wrappers::SRWLock *p_Lock; // r15
  HRESULT String; // edi
  Windows::Media::MediaProperties::CMediaPropertySet *ptr; // rcx
  Windows::Media::MediaProperties::CMediaPropertySet_vtbl *v7; // rax
  int v8; // ebx
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v11; // r8d
  unsigned int i; // ebx
  __int64 v14; // r14
  CallStackTracing *v15; // rcx
  CallStackTracing *v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-40h] BYREF
  int v18; // [rsp+28h] [rbp-38h]
  struct _GUID v19; // [rsp+30h] [rbp-30h] BYREF
  struct _GUID Buf1; // [rsp+40h] [rbp-20h] BYREF

  p_Lock = &this->_Lock;
  AcquireSRWLockExclusive(&this->_Lock.SRWLock_);
  v17 = 0;
  v18 = 0;
  if ( a2 )
  {
    String = 0;
    *a2 = 0;
    ptr = this->_spProperties.ptr_;
    v7 = ptr->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<_GUID,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,IInspectable *> *>,Microsoft::WRL::CloakedIid<Windows::Media::MediaProperties::IMediaPropertySetInternal>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<_GUID,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,IInspectable *> *>,Microsoft::WRL::CloakedIid<Windows::Media::MediaProperties::IMediaPropertySetInternal>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<_GUID,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,IInspectable *> *>,Microsoft::WRL::CloakedIid<Windows::Media::MediaProperties::IMediaPropertySetInternal>,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IMap<_GUID,IInspectable *>::Windows::Foundation::Collections::IMap_impl<_GUID,IInspectable *>::IInspectable::IUnknown::__vftable;
    Buf1 = (struct _GUID)(unsigned __int64)&v17;
    v19 = MF_MT_SUBTYPE;
    v8 = ((__int64 (__fastcall *)(Windows::Media::MediaProperties::CMediaPropertySet *, struct _GUID *, unsigned __int8 *))v7->Lookup)(
           ptr,
           &v19,
           Buf1.Data4);
    RoVariant::Attach(*(RoVariant **)&Buf1.Data1, *(struct IInspectable **)Buf1.Data4);
    if ( v8 >= 0 )
    {
      Buf1 = 0;
      if ( GetGuid((const struct RoVariant *)&v17, &Buf1) < 0
        || !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        String = WindowsCreateString(L"Unknown", 7u, a2);
        if ( String < 0 )
        {
          v9 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v9 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v9 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v9->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
            if ( ThreadRelativeContext->m_result != String )
            {
              v11 = 311;
LABEL_24:
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "Windows::Media::MediaProperties::CVideoProperties::get_Subtype",
                v11,
                String);
            }
          }
        }
      }
      else
      {
        if ( !this->_fSubtypeIsGuid )
        {
          for ( i = 0; i < 0x1A; ++i )
          {
            v14 = 32LL * i;
            if ( !memcmp_0((char *)&details::s_arrVideoSubtype + v14, &Buf1, 0x10u) )
            {
              if ( WindowsCreateString(
                     *(PCNZWCH *)((char *)&details::s_arrVideoSubtype + v14 + 16),
                     *(_DWORD *)((char *)&details::s_arrVideoSubtype + v14 + 24),
                     a2) < 0 )
                break;
              goto LABEL_13;
            }
          }
        }
        v19 = Buf1;
        String = HSTRINGFromGUID(&v19, a2);
        if ( String < 0 )
        {
          v16 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v16 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v16->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v16);
            if ( ThreadRelativeContext->m_result != String )
            {
              v11 = 315;
              goto LABEL_24;
            }
          }
        }
      }
    }
  }
  else
  {
    v15 = CallStackTracing::s_wpInstance;
    String = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v15->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
      if ( ThreadRelativeContext->m_result != -2147467261 )
      {
        v11 = 303;
        goto LABEL_24;
      }
    }
  }
LABEL_13:
  if ( v17 && ((v18 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (**)(void))(*(_QWORD *)v17 + 16LL))();
  if ( p_Lock )
    ReleaseSRWLockExclusive(&p_Lock->SRWLock_);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180089f20  mov     [rsp-28h+arg_10], rbx
0x180089f25  mov     [rsp-28h+arg_18], rsi
0x180089f2a  push    rbp
0x180089f2b  push    rdi
0x180089f2c  push    r13
0x180089f2e  push    r14
0x180089f30  push    r15
0x180089f32  mov     rbp, rsp
0x180089f35  sub     rsp, 60h
0x180089f39  mov     rax, cs:__security_cookie
0x180089f40  xor     rax, rsp
0x180089f43  mov     [rbp+var_10], rax
0x180089f47  lea     r15, [rcx+38h]
0x180089f4b  mov     r14, rcx
0x180089f4e  mov     rcx, r15; SRWLock
0x180089f51  mov     rsi, rdx
0x180089f54  call    cs:__imp_AcquireSRWLockExclusive
0x180089f5a  mov     [rbp+var_40], 0
0x180089f62  mov     [rbp+var_38], 0
0x180089f69  test    rsi, rsi
0x180089f6c  jz      loc_18008A14C
0x180089f72  xor     edi, edi
0x180089f74  lea     rdx, [rbp+var_40]
0x180089f78  mov     [rsi], rdi
0x180089f7b  lea     r8, [rbp+Buf1+8]
0x180089f7f  mov     rcx, [r14+30h]
0x180089f83  movups  xmm0, xmmword ptr cs:MF_MT_SUBTYPE.Data1
0x180089f8a  mov     rax, [rcx]
0x180089f8d  mov     qword ptr [rbp+Buf1], rdx
0x180089f91  lea     rdx, [rbp+var_30]
0x180089f95  mov     qword ptr [rbp+Buf1+8], rdi
0x180089f99  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x180089f9e  mov     rax, [rax+30h]
0x180089fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089fa7  mov     rdx, qword ptr [rbp+Buf1+8]; struct IInspectable *
0x180089fab  mov     ebx, eax
0x180089fad  mov     rcx, qword ptr [rbp+Buf1]; this
0x180089fb1  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180089fb6  shr     ebx, 1Fh
0x180089fb9  xor     bl, 1
0x180089fbc  jz      loc_18008A096
0x180089fc2  xorps   xmm0, xmm0
0x180089fc5  lea     rdx, [rbp+Buf1]; struct _GUID *
0x180089fc9  lea     rcx, [rbp+var_40]; struct RoVariant *
0x180089fcd  movups  [rbp+Buf1], xmm0
0x180089fd1  call    ?GetGuid@@YAJAEBVRoVariant@@PEAU_GUID@@@Z; GetGuid(RoVariant const &,_GUID *)
0x180089fd6  test    eax, eax
0x180089fd8  js      short loc_180089FF6
0x180089fda  lea     r8d, [rdi+10h]; Size
0x180089fde  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180089fe5  lea     rcx, [rbp+Buf1]; Buf1
0x180089fe9  call    memcmp_0
0x180089fee  test    eax, eax
0x180089ff0  jnz     loc_18008A0ED
0x180089ff6  mov     r8, rsi; string
0x180089ff9  lea     rcx, ?Media_Unknown@@3QBGB; "Unknown"
0x18008a000  mov     edx, 7; length
0x18008a005  call    cs:__imp_WindowsCreateString
0x18008a00b  mov     edi, eax
0x18008a00d  test    eax, eax
0x18008a00f  jns     loc_18008A096
0x18008a015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a01c  test    rcx, rcx
0x18008a01f  jnz     short loc_18008A05D
0x18008a021  mov     rax, cs:stru_1801FC290.__vftable
0x18008a028  lea     r8, stru_1801FC290
0x18008a02f  mov     edx, 7F0h
0x18008a034  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a03b  mov     rcx, r8
0x18008a03e  mov     rax, [rax+8]
0x18008a042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a047  test    eax, eax
0x18008a049  jnz     loc_18008A231
0x18008a04f  lea     rcx, stru_1801F8A30; this
0x18008a056  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a05d  cmp     byte ptr [rcx+8], 0
0x18008a061  jz      short loc_18008A096
0x18008a063  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a068  cmp     [rax+7CCh], edi
0x18008a06e  jz      short loc_18008A096
0x18008a070  mov     r8d, 137h
0x18008a076  jmp     loc_18008A135
0x18008a07b  mov     edx, [r14+r13+18h]; length
0x18008a080  mov     r8, rsi; string
0x18008a083  mov     rcx, [r14+r13+10h]; sourceString
0x18008a088  call    cs:__imp_WindowsCreateString
0x18008a08e  test    eax, eax
0x18008a090  js      loc_18008A23D
0x18008a096  mov     rcx, [rbp+var_40]
0x18008a09a  test    rcx, rcx
0x18008a09d  jz      short loc_18008A0B8
0x18008a09f  mov     eax, [rbp+var_38]
0x18008a0a2  add     eax, 0FFFFFFFDh
0x18008a0a5  test    eax, 0FFFFFFFBh
0x18008a0aa  jnz     short loc_18008A0B8
0x18008a0ac  mov     rax, [rcx]
0x18008a0af  mov     rax, [rax+10h]
0x18008a0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a0b8  test    r15, r15
0x18008a0bb  jz      short loc_18008A0C6
0x18008a0bd  mov     rcx, r15; SRWLock
0x18008a0c0  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a0c6  mov     eax, edi
0x18008a0c8  mov     rcx, [rbp+var_10]
0x18008a0cc  xor     rcx, rsp; StackCookie
0x18008a0cf  call    __security_check_cookie
0x18008a0d4  lea     r11, [rsp+60h+var_s0]
0x18008a0d9  mov     rbx, [r11+40h]
0x18008a0dd  mov     rsi, [r11+48h]
0x18008a0e1  mov     rsp, r11
0x18008a0e4  pop     r15
0x18008a0e6  pop     r14
0x18008a0e8  pop     r13
0x18008a0ea  pop     rdi
0x18008a0eb  pop     rbp
0x18008a0ec  retn
0x18008a0ed  cmp     [r14+40h], dil
0x18008a0f1  jnz     loc_18008A23D
0x18008a0f7  xor     ebx, ebx
0x18008a0f9  lea     r13, ?s_arrVideoSubtype@details@@3QBUGuidNameMappingEntry@1@B; details::GuidNameMappingEntry const near * const details::s_arrVideoSubtype
0x18008a100  cmp     ebx, 1Ah
0x18008a103  jnb     loc_18008A23D
0x18008a109  mov     r14d, ebx
0x18008a10c  lea     rdx, [rbp+Buf1]; Buf2
0x18008a110  shl     r14, 5
0x18008a114  mov     r8d, 10h; Size
0x18008a11a  lea     rcx, [r14+r13]; Buf1
0x18008a11e  call    memcmp_0
0x18008a123  test    eax, eax
0x18008a125  jz      loc_18008A07B
0x18008a12b  inc     ebx
0x18008a12d  jmp     short loc_18008A100
0x18008a12f  mov     r8d, 12Fh; int
0x18008a135  mov     r9d, edi; int
0x18008a138  lea     rdx, aWindowsMediaMe_59; "Windows::Media::MediaProperties::CVideo"...
0x18008a13f  mov     rcx, rax; this
0x18008a142  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008a147  jmp     loc_18008A096
0x18008a14c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a153  mov     edi, 80004003h
0x18008a158  test    rcx, rcx
0x18008a15b  jnz     short loc_18008A195
0x18008a15d  mov     rax, cs:stru_1801FC290.__vftable
0x18008a164  lea     r8, stru_1801FC290
0x18008a16b  mov     edx, 7F0h
0x18008a170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a177  mov     rcx, r8
0x18008a17a  mov     rax, [rax+8]
0x18008a17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a183  test    eax, eax
0x18008a185  jnz     short loc_18008A1B5
0x18008a187  lea     rcx, stru_1801F8A30; this
0x18008a18e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a195  cmp     byte ptr [rcx+8], 0
0x18008a199  jz      loc_18008A096
0x18008a19f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a1a4  cmp     [rax+7CCh], edi
0x18008a1aa  jz      loc_18008A096
0x18008a1b0  jmp     loc_18008A12F
0x18008a1b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a1bc  jmp     short loc_18008A195
0x18008a1be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a1c5  test    rcx, rcx
0x18008a1c8  jnz     short loc_18008A202
0x18008a1ca  mov     rcx, cs:stru_1801FC290.__vftable
0x18008a1d1  lea     r8, stru_1801FC290
0x18008a1d8  mov     edx, 7F0h
0x18008a1dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a1e4  mov     rax, [rcx+8]
0x18008a1e8  mov     rcx, r8
0x18008a1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1f0  test    eax, eax
0x18008a1f2  jnz     short loc_18008A228
0x18008a1f4  lea     rcx, stru_1801F8A30; this
0x18008a1fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a202  cmp     byte ptr [rcx+8], 0
0x18008a206  jz      loc_18008A096
0x18008a20c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a211  cmp     [rax+7CCh], edi
0x18008a217  jz      loc_18008A096
0x18008a21d  mov     r8d, 13Bh
0x18008a223  jmp     loc_18008A135
0x18008a228  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a22f  jmp     short loc_18008A202
0x18008a231  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a238  jmp     loc_18008A05D
0x18008a23d  movaps  xmm0, [rbp+Buf1]
0x18008a241  lea     rcx, [rbp+var_30]; struct _GUID
0x18008a245  mov     rdx, rsi; HSTRING *
0x18008a248  movdqa  xmmword ptr [rbp+var_30.Data1], xmm0
0x18008a24d  call    ?HSTRINGFromGUID@@YAJU_GUID@@PEAPEAUHSTRING__@@@Z; HSTRINGFromGUID(_GUID,HSTRING__ * *)
0x18008a252  mov     edi, eax
0x18008a254  test    eax, eax
0x18008a256  jns     loc_18008A096
0x18008a25c  jmp     loc_18008A1BE
```
