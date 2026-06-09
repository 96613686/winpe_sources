# CMediaServerCollectionChangeListener::AddClientRef(void)

- ea: `0x180002c00`
- end: `0x18000309e`
- name: `?AddClientRef@CMediaServerCollectionChangeListener@@QEAAXXZ`
- size: `1182`
- prototype: `void __fastcall(CMediaServerCollectionChangeListener *__hidden this)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001bf0`
- `0x1800024f0`
- `0x180008fb0`
- `0x18000dcf8`
- `0x180022a48`

## callees

- `0x180001710`
- `0x180001750`
- `0x180001840`
- `0x180002c00`
- `0x1800030b0`
- `0x180003310`
- `0x180003530`
- `0x18000e0dc`
- `0x180011954`
- `0x18001e6f4`
- `0x180022124`
- `0x1800221d0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180002cb6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180002cb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002dc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002dc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ed5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ef9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CMediaServerCollectionChangeListener::AddClientRef(CMediaServerCollectionChangeListener *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // r12
  DWORD CurrentThreadId; // r15d
  unsigned int v5; // r14d
  void *v6; // rax
  __int64 v7; // rbx
  int v8; // r14d
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  _QWORD *v12; // rbx
  _QWORD *v13; // rax
  _QWORD *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 *v17; // rax
  __int64 v18; // rcx
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-41h] BYREF
  __int64 v21; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  struct _RTL_CRITICAL_SECTION *v23; // [rsp+50h] [rbp-29h]
  char v24; // [rsp+58h] [rbp-21h]
  __int64 v25; // [rsp+60h] [rbp-19h] BYREF
  char v26; // [rsp+68h] [rbp-11h] BYREF
  char v27; // [rsp+E0h] [rbp+67h] BYREF
  int v28; // [rsp+E8h] [rbp+6Fh] BYREF
  CMediaServerCollectionChangeListener *pAptType; // [rsp+F0h] [rbp+77h] BYREF
  int v30; // [rsp+F8h] [rbp+7Fh] BYREF

  v28 = 0;
  v21 = 0;
  v20 = 0;
  v27 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v23 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v24 = 1;
  if ( ++*((_DWORD *)this + 60) == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids, this);
    }
    v3 = lambda_f816bfa758d2843652e7617bbf76d0ba_::_lambda_f816bfa758d2843652e7617bbf76d0ba_(
           (unsigned int)&v26,
           (_DWORD)this,
           (unsigned int)&v28,
           (unsigned int)&v27,
           (__int64)&v21,
           (__int64)&v20);
    CurrentThreadId = GetCurrentThreadId();
    LODWORD(pAptType) = 0;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    if ( CoGetApartmentType((APTTYPE *)&pAptType, pAptQualifier) < 0
      || !(_DWORD)pAptType
      || (v5 = 4, (_DWORD)pAptType == 3) )
    {
      v5 = 0;
    }
    v30 = 0;
    v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = (__int64)v6;
    if ( v6 )
    {
      Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v6);
      *(_OWORD *)(v7 + 16) = *(_OWORD *)v3;
      *(_OWORD *)(v7 + 32) = *(_OWORD *)(v3 + 16);
      *(_QWORD *)(v7 + 48) = *(_QWORD *)(v3 + 32);
      *(_QWORD *)v7 = &off_180036B60;
      *(_QWORD *)(v7 + 56) = &v30;
    }
    else
    {
      v7 = 0;
    }
    string = (HSTRING)v7;
    v8 = SHTaskPoolQueueTask(v5, 0x20u, CurrentThreadId, 0, v7, 0);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v8 >= 0 )
      v8 = v30;
    v28 = v8;
  }
  LeaveCriticalSection(v2);
  v9 = 0;
  if ( v28 >= 0 )
  {
    while ( v9 < v20 )
    {
      *(_QWORD *)pAptQualifier = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, APTTYPEQUALIFIER *))(*(_QWORD *)v21 + 48LL))(
              v21,
              v9,
              pAptQualifier);
      if ( v28 >= 0 )
      {
        v30 = 0;
        v28 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)pAptQualifier + 176LL))(
                *(_QWORD *)pAptQualifier,
                &v30);
        if ( v28 >= 0 && v30 == 2 )
        {
          string = 0;
          v28 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)pAptQualifier + 80LL))(
                  *(_QWORD *)pAptQualifier,
                  &string);
          if ( v28 >= 0 )
          {
            LODWORD(pAptType) = (*(int (__fastcall **)(_QWORD, CMediaServerCollectionChangeListener **))(**(_QWORD **)pAptQualifier + 192LL))(
                                  *(_QWORD *)pAptQualifier,
                                  &pAptType) < 0;
            v23 = v2;
            EnterCriticalSection(v2);
            v24 = 1;
            v28 = CMediaServerCollectionChangeListener::_AddDeviceToMap(
                    this,
                    string,
                    *(_QWORD *)pAptQualifier,
                    (unsigned int)pAptType);
            LeaveCriticalSection(v2);
            v24 = 0;
          }
          if ( string )
            WindowsDeleteString(string);
        }
      }
      v10 = *(_QWORD *)pAptQualifier;
      if ( *(_QWORD *)pAptQualifier )
      {
        *(_QWORD *)pAptQualifier = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      if ( v28 < 0 )
        break;
      ++v9;
    }
  }
  if ( v27 )
  {
    v23 = v2;
    EnterCriticalSection(v2);
    v24 = 1;
    v11 = v28;
    if ( v28 < 0 )
    {
LABEL_31:
      LeaveCriticalSection(v2);
      CMediaServerCollectionChangeListener::ReleaseClientRef(this);
      goto LABEL_32;
    }
    if ( !*((_QWORD *)this + 26) )
    {
      v12 = 0;
      v13 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( v13 )
      {
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>(v13);
        *v14 = &CDeviceArrivalDelegate::`vftable'{for `Windows::Media::Streaming::IDeviceControllerFinderHandler'};
        v14[1] = &CDeviceDepartureDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
        v14[6] = this;
        Microsoft::WRL::ComPtr<CMediaServerCollectionChangeListener>::InternalAddRef();
        v12 = v14;
      }
      v15 = *((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = v12;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( !*((_QWORD *)this + 26) )
        goto LABEL_28;
      v11 = v28;
    }
    if ( v11 < 0 )
      goto LABEL_31;
    if ( !*((_QWORD *)this + 27) )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 31) + 72LL))(*((_QWORD *)this + 31));
      v28 = v11;
    }
    if ( v11 < 0 )
      goto LABEL_31;
    if ( !*((_QWORD *)this + 28) )
    {
      pAptType = this;
      v17 = (__int64 *)Microsoft::WRL::Details::Make<CDeviceDepartureDelegate,CMediaServerCollectionChangeListener *>(
                         &v30,
                         &pAptType);
      v18 = 0;
      if ( &v25 != v17 )
      {
        v18 = *v17;
        *v17 = 0;
      }
      v25 = *((_QWORD *)this + 28);
      *((_QWORD *)this + 28) = v18;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v30);
      if ( !*((_QWORD *)this + 28) )
      {
LABEL_28:
        v28 = -2147024882;
        goto LABEL_31;
      }
      v11 = v28;
    }
    if ( v11 >= 0 && !*((_QWORD *)this + 29) )
      v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 31) + 88LL))(*((_QWORD *)this + 31));
    goto LABEL_31;
  }
LABEL_32:
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
}

```

## disassembly

```asm
0x180002c00  push    rbp
0x180002c02  push    rbx
0x180002c03  push    rsi
0x180002c04  push    rdi
0x180002c05  push    r12
0x180002c07  push    r13
0x180002c09  push    r14
0x180002c0b  push    r15
0x180002c0d  lea     rbp, [rsp-1Fh]
0x180002c12  sub     rsp, 98h
0x180002c19  mov     rdi, rcx
0x180002c1c  xor     r13d, r13d
0x180002c1f  mov     [rbp+57h+arg_8], r13d
0x180002c23  mov     [rbp+57h+var_90], r13
0x180002c27  mov     [rbp+57h+var_98], r13d
0x180002c2b  mov     [rbp+57h+arg_0], r13b
0x180002c2f  lea     rsi, [rcx+60h]
0x180002c33  mov     [rbp+57h+var_80], rsi
0x180002c37  mov     rcx, rsi; lpCriticalSection
0x180002c3a  call    cs:__imp_EnterCriticalSection
0x180002c40  mov     [rbp+57h+var_78], 1
0x180002c44  inc     dword ptr [rdi+0F0h]
0x180002c4a  cmp     dword ptr [rdi+0F0h], 1
0x180002c51  jnz     loc_180002D30
0x180002c57  lea     rax, WPP_GLOBAL_Control
0x180002c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c65  cmp     rcx, rax
0x180002c68  jz      short loc_180002C74
0x180002c6a  test    byte ptr [rcx+1Ch], 40h
0x180002c6e  jnz     loc_180002F6C
0x180002c74  lea     rax, [rbp+57h+var_98]
0x180002c78  mov     qword ptr [rsp+0D0h+var_A8], rax
0x180002c7d  lea     rax, [rbp+57h+var_90]
0x180002c81  mov     [rsp+0D0h+var_B0], rax
0x180002c86  lea     r9, [rbp+57h+arg_0]
0x180002c8a  lea     r8, [rbp+57h+arg_8]
0x180002c8e  mov     rdx, rdi
0x180002c91  lea     rcx, [rbp+57h+var_68]
0x180002c95  call    _lambda_f816bfa758d2843652e7617bbf76d0ba____lambda_f816bfa758d2843652e7617bbf76d0ba_
0x180002c9a  mov     r12, rax
0x180002c9d  call    cs:__imp_GetCurrentThreadId
0x180002ca3  mov     r15d, eax
0x180002ca6  mov     dword ptr [rbp+57h+pAptType], r13d
0x180002caa  mov     [rbp+57h+pAptQualifier], r13d
0x180002cae  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x180002cb2  lea     rcx, [rbp+57h+pAptType]; pAptType
0x180002cb6  call    cs:__imp_CoGetApartmentType
0x180002cbc  test    eax, eax
0x180002cbe  jns     loc_180002F1B
0x180002cc4  mov     r14d, r13d
0x180002cc7  mov     [rbp+57h+arg_18], r13d
0x180002ccb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002cd2  mov     ecx, 40h ; '@'; unsigned __int64
0x180002cd7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002cdc  mov     rbx, rax
0x180002cdf  test    rax, rax
0x180002ce2  jnz     loc_180002F93
0x180002ce8  mov     rbx, r13
0x180002ceb  mov     [rbp+57h+string], rbx
0x180002cef  mov     qword ptr [rsp+0D0h+var_A8], r13; pAptType
0x180002cf4  mov     [rsp+0D0h+var_B0], rbx; __int64
0x180002cf9  xor     r9d, r9d; int
0x180002cfc  mov     r8d, r15d; int
0x180002cff  mov     edx, 20h ; ' '; int
0x180002d04  mov     ecx, r14d; int
0x180002d07  call    SHTaskPoolQueueTask
0x180002d0c  mov     r14d, eax
0x180002d0f  test    rbx, rbx
0x180002d12  jz      short loc_180002D24
0x180002d14  mov     rcx, [rbx]
0x180002d17  mov     rax, [rcx+10h]
0x180002d1b  mov     rcx, rbx
0x180002d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d23  nop
0x180002d24  test    r14d, r14d
0x180002d27  cmovns  r14d, [rbp+57h+arg_18]
0x180002d2c  mov     [rbp+57h+arg_8], r14d
0x180002d30  mov     rcx, rsi; lpCriticalSection
0x180002d33  call    cs:__imp_LeaveCriticalSection
0x180002d39  mov     ebx, r13d
0x180002d3c  cmp     [rbp+57h+arg_8], ebx
0x180002d3f  jl      short loc_180002DB1
0x180002d41  cmp     ebx, [rbp+57h+var_98]
0x180002d44  jnb     short loc_180002DB1
0x180002d46  mov     qword ptr [rbp+57h+pAptQualifier], r13
0x180002d4a  mov     rcx, [rbp+57h+var_90]
0x180002d4e  mov     rax, [rcx]
0x180002d51  lea     r8, [rbp+57h+pAptQualifier]
0x180002d55  mov     edx, ebx
0x180002d57  mov     rax, [rax+30h]
0x180002d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d60  mov     [rbp+57h+arg_8], eax
0x180002d63  test    eax, eax
0x180002d65  js      short loc_180002D8D
0x180002d67  mov     [rbp+57h+arg_18], r13d
0x180002d6b  mov     rcx, qword ptr [rbp+57h+pAptQualifier]
0x180002d6f  mov     rax, [rcx]
0x180002d72  lea     rdx, [rbp+57h+arg_18]
0x180002d76  mov     rax, [rax+0B0h]
0x180002d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d82  mov     [rbp+57h+arg_8], eax
0x180002d85  test    eax, eax
0x180002d87  jns     loc_180002E7F
0x180002d8d  mov     rcx, qword ptr [rbp+57h+pAptQualifier]
0x180002d91  test    rcx, rcx
0x180002d94  jz      short loc_180002DA7
0x180002d96  mov     qword ptr [rbp+57h+pAptQualifier], r13
0x180002d9a  mov     rax, [rcx]
0x180002d9d  mov     rax, [rax+10h]
0x180002da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da6  nop
0x180002da7  cmp     [rbp+57h+arg_8], 0
0x180002dab  jge     loc_180002FD1
0x180002db1  cmp     [rbp+57h+arg_0], 0
0x180002db5  jz      loc_180002E51
0x180002dbb  mov     [rbp+57h+var_80], rsi
0x180002dbf  mov     rcx, rsi; lpCriticalSection
0x180002dc2  call    cs:__imp_EnterCriticalSection
0x180002dc8  mov     [rbp+57h+var_78], 1
0x180002dcc  mov     eax, [rbp+57h+arg_8]
0x180002dcf  test    eax, eax
0x180002dd1  js      short loc_180002E3F
0x180002dd3  mov     rdx, [rdi+0D0h]
0x180002dda  test    rdx, rdx
0x180002ddd  jnz     short loc_180002E37
0x180002ddf  mov     rbx, r13
0x180002de2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002de9  mov     ecx, 38h ; '8'; unsigned __int64
0x180002dee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002df3  mov     r14, rax
0x180002df6  test    rax, rax
0x180002df9  jnz     loc_180002F3A
0x180002dff  mov     rcx, [rdi+0D0h]
0x180002e06  mov     [rdi+0D0h], rbx
0x180002e0d  test    rcx, rcx
0x180002e10  jz      short loc_180002E1F
0x180002e12  mov     rax, [rcx]
0x180002e15  mov     rax, [rax+10h]
0x180002e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1e  nop
0x180002e1f  mov     rdx, [rdi+0D0h]
0x180002e26  test    rdx, rdx
0x180002e29  jnz     short loc_180002E34
0x180002e2b  mov     [rbp+57h+arg_8], 8007000Eh
0x180002e32  jmp     short loc_180002E3F
0x180002e34  mov     eax, [rbp+57h+arg_8]
0x180002e37  test    eax, eax
0x180002e39  jns     loc_180002FD8
0x180002e3f  mov     rcx, rsi; lpCriticalSection
0x180002e42  call    cs:__imp_LeaveCriticalSection
0x180002e48  mov     rcx, rdi; this
0x180002e4b  call    ?ReleaseClientRef@CMediaServerCollectionChangeListener@@QEAAXXZ; CMediaServerCollectionChangeListener::ReleaseClientRef(void)
0x180002e50  nop
0x180002e51  mov     rcx, [rbp+57h+var_90]
0x180002e55  test    rcx, rcx
0x180002e58  jz      short loc_180002E6B
0x180002e5a  mov     [rbp+57h+var_90], r13
0x180002e5e  mov     rax, [rcx]
0x180002e61  mov     rax, [rax+10h]
0x180002e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6a  nop
0x180002e6b  add     rsp, 98h
0x180002e72  pop     r15
0x180002e74  pop     r14
0x180002e76  pop     r13
0x180002e78  pop     r12
0x180002e7a  pop     rdi
0x180002e7b  pop     rsi
0x180002e7c  pop     rbx
0x180002e7d  pop     rbp
0x180002e7e  retn
0x180002e7f  cmp     [rbp+57h+arg_18], 2
0x180002e83  jnz     loc_180002D8D
0x180002e89  mov     [rbp+57h+string], r13
0x180002e8d  mov     rcx, qword ptr [rbp+57h+pAptQualifier]
0x180002e91  mov     rax, [rcx]
0x180002e94  lea     rdx, [rbp+57h+string]
0x180002e98  mov     rax, [rax+50h]
0x180002e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea1  mov     [rbp+57h+arg_8], eax
0x180002ea4  test    eax, eax
0x180002ea6  js      short loc_180002F03
0x180002ea8  mov     dword ptr [rbp+57h+pAptType], r13d
0x180002eac  mov     rcx, qword ptr [rbp+57h+pAptQualifier]
0x180002eb0  mov     rax, [rcx]
0x180002eb3  lea     rdx, [rbp+57h+pAptType]
0x180002eb7  mov     rax, [rax+0C0h]
0x180002ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec3  test    eax, eax
0x180002ec5  jns     short loc_180002ECE
0x180002ec7  mov     dword ptr [rbp+57h+pAptType], 1
0x180002ece  mov     [rbp+57h+var_80], rsi
0x180002ed2  mov     rcx, rsi; lpCriticalSection
0x180002ed5  call    cs:__imp_EnterCriticalSection
0x180002edb  mov     [rbp+57h+var_78], 1
0x180002edf  mov     r9d, dword ptr [rbp+57h+pAptType]
0x180002ee3  mov     r8, qword ptr [rbp+57h+pAptQualifier]
0x180002ee7  mov     rdx, [rbp+57h+string]
0x180002eeb  mov     rcx, rdi
0x180002eee  call    ?_AddDeviceToMap@CMediaServerCollectionChangeListener@@AEAAJPEAUHSTRING__@@PEAUIBasicDevice@Streaming@Media@Windows@@W4ConnectionStatus@456@@Z; CMediaServerCollectionChangeListener::_AddDeviceToMap(HSTRING__ *,Windows::Media::Streaming::IBasicDevice *,Windows::Media::Streaming::ConnectionStatus)
0x180002ef3  mov     [rbp+57h+arg_8], eax
0x180002ef6  mov     rcx, rsi; lpCriticalSection
0x180002ef9  call    cs:__imp_LeaveCriticalSection
0x180002eff  mov     [rbp+57h+var_78], 0
0x180002f03  mov     rcx, [rbp+57h+string]; string
0x180002f07  test    rcx, rcx
0x180002f0a  jz      loc_180002D8D
0x180002f10  call    cs:__imp_WindowsDeleteString
0x180002f16  jmp     loc_180002D8D
0x180002f1b  mov     ecx, dword ptr [rbp+57h+pAptType]
0x180002f1e  test    ecx, ecx
0x180002f20  jz      loc_180002CC4
0x180002f26  cmp     ecx, 3
0x180002f29  mov     r14d, 4
0x180002f2f  jnz     loc_180002CC7
0x180002f35  jmp     loc_180002CC4
0x180002f3a  mov     rcx, r14
0x180002f3d  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDeviceControllerFinderHandler@Streaming@Media@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Media::Streaming::IDeviceControllerFinderHandler,Microsoft::WRL::FtmBase>(void)
0x180002f42  lea     rax, ??_7CDeviceArrivalDelegate@@6BIDeviceControllerFinderHandler@Streaming@Media@Windows@@@; const CDeviceArrivalDelegate::`vftable'{for `Windows::Media::Streaming::IDeviceControllerFinderHandler'}
0x180002f49  mov     [r14], rax
0x180002f4c  lea     rax, ??_7CDeviceDepartureDelegate@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDeviceDepartureDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180002f53  mov     [r14+8], rax
0x180002f57  lea     rcx, [r14+30h]
0x180002f5b  mov     [rcx], rdi
0x180002f5e  call    ?InternalAddRef@?$ComPtr@VCMediaServerCollectionChangeListener@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CMediaServerCollectionChangeListener>::InternalAddRef(void)
0x180002f63  nop
0x180002f64  mov     rbx, r14
0x180002f67  jmp     loc_180002DFF
0x180002f6c  cmp     byte ptr [rcx+19h], 4
0x180002f70  jb      loc_180002C74
0x180002f76  mov     edx, 11h
0x180002f7b  mov     r9, rdi
0x180002f7e  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180002f85  mov     rcx, [rcx+10h]
0x180002f89  call    WPP_SF_q
0x180002f8e  jmp     loc_180002C74
0x180002f93  mov     rcx, rbx
0x180002f96  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180002f9b  movups  xmm0, xmmword ptr [r12]
0x180002fa0  movups  xmmword ptr [rbx+10h], xmm0
0x180002fa4  movups  xmm1, xmmword ptr [r12+10h]
0x180002faa  movups  xmmword ptr [rbx+20h], xmm1
0x180002fae  movsd   xmm0, qword ptr [r12+20h]
0x180002fb5  movsd   qword ptr [rbx+30h], xmm0
0x180002fba  lea     rax, off_180036B60
0x180002fc1  mov     [rbx], rax
0x180002fc4  lea     rax, [rbp+57h+arg_18]
0x180002fc8  mov     [rbx+38h], rax
0x180002fcc  jmp     loc_180002CEB
0x180002fd1  inc     ebx
0x180002fd3  jmp     loc_180002D41
0x180002fd8  lea     r8, [rdi+0D8h]
0x180002fdf  cmp     qword ptr [r8], 0
0x180002fe3  jnz     short loc_180002FFB
0x180002fe5  mov     rcx, [rdi+0F8h]
0x180002fec  mov     rax, [rcx]
0x180002fef  mov     rax, [rax+48h]
0x180002ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff8  mov     [rbp+57h+arg_8], eax
0x180002ffb  test    eax, eax
0x180002ffd  js      loc_180002E3F
0x180003003  mov     rdx, [rdi+0E0h]
0x18000300a  test    rdx, rdx
0x18000300d  jnz     short loc_180003069
0x18000300f  mov     [rbp+57h+pAptType], rdi
0x180003013  lea     rdx, [rbp+57h+pAptType]
0x180003017  lea     rcx, [rbp+57h+arg_18]
0x18000301b  call    ??$Make@VCDeviceDepartureDelegate@@PEAVCMediaServerCollectionChangeListener@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDeviceDepartureDelegate@@@12@$$QEAPEAVCMediaServerCollectionChangeListener@@@Z; Microsoft::WRL::Details::Make<CDeviceDepartureDelegate,CMediaServerCollectionChangeListener *>(CMediaServerCollectionChangeListener * &&)
0x180003020  mov     rcx, r13
0x180003023  lea     rdx, [rbp+57h+var_70]
0x180003027  cmp     rdx, rax
0x18000302a  jz      short loc_180003032
0x18000302c  mov     rcx, [rax]
0x18000302f  mov     [rax], r13
0x180003032  mov     rax, [rdi+0E0h]
0x180003039  mov     [rbp+57h+var_70], rax
0x18000303d  mov     [rdi+0E0h], rcx
0x180003044  lea     rcx, [rbp+57h+var_70]
0x180003048  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000304d  lea     rcx, [rbp+57h+arg_18]
0x180003051  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003056  mov     rdx, [rdi+0E0h]
0x18000305d  test    rdx, rdx
0x180003060  jz      loc_180002E2B
0x180003066  mov     eax, [rbp+57h+arg_8]
0x180003069  test    eax, eax
0x18000306b  js      loc_180002E3F
0x180003071  lea     r8, [rdi+0E8h]
0x180003078  cmp     qword ptr [r8], 0
0x18000307c  jnz     loc_180002E3F
0x180003082  mov     rcx, [rdi+0F8h]
0x180003089  mov     rax, [rcx]
0x18000308c  mov     rax, [rax+58h]
0x180003090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003095  mov     [rbp+57h+arg_8], eax
0x180003098  jmp     loc_180002E3F
```
