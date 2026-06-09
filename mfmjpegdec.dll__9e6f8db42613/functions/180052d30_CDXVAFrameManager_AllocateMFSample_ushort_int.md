# CDXVAFrameManager::AllocateMFSample(ushort,int)

- ea: `0x180052d30`
- end: `0x180052f52`
- name: `?AllocateMFSample@CDXVAFrameManager@@UEAAPEAUIMFSample@@GH@Z`
- size: `546`
- prototype: `struct IMFSample *__fastcall(CDXVAFrameManager *__hidden this, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff0c`

## callees

- `0x180020598`
- `0x1800485dc`
- `0x18004a11c`
- `0x18004aae4`
- `0x1800526c4`
- `0x1800528c0`
- `0x180052d30`
- `0x180053b38`
- `0x180054bdc`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d9a`
- `MFPlat!MFCreateSample` at `0x180052e35`
- `MFPlat!MFCreateSample` at `0x180052e35`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct IMFSample *__fastcall CDXVAFrameManager::AllocateMFSample(CDXVAFrameManager *this, unsigned __int16 a2, int a3)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  unsigned __int8 *v7; // rbx
  IMFSample *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  char *v12; // [rsp+48h] [rbp-8h] BYREF
  IMFSample *ppIMFSample; // [rsp+88h] [rbp+38h] BYREF

  v3 = a3;
  v4 = a2;
  if ( g_wppLevels >= 4u )
    WPP_SF_ddq(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids, a2, a3, this);
  if ( (_DWORD)v3 == -1 )
    return 0;
  ppIMFSample = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v12 = (char *)this + 24;
  v7 = (unsigned __int8 *)((v4 << 6) + *((_QWORD *)this + v3 + 33));
  if ( *(_QWORD *)v7 )
  {
    v11 = 0;
    if ( (unsigned int)Microsoft::WRL::ComPtr<IMFTrackedBuffer>::As<IMFMediaBuffer>(v7, &v11)
      || (Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&ppIMFSample), MFCreateSample(&ppIMFSample))
      || ((unsigned int (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, v11) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v7 + 40LL))(*(_QWORD *)v7, 1) )
      {
        ((void (__fastcall *)(IMFSample *, GUID *, _QWORD))ppIMFSample->lpVtbl->SetUINT32)(
          ppIMFSample,
          &DXVA_INTERNAL_SAMPLE_INDEX,
          (unsigned int)v4);
        v7[16] = 1;
        v7[56] = 0;
        *((_WORD *)v7 + 4) = v4;
        v10 = *((_QWORD *)v7 + 3);
        if ( v10 )
          ((void (__fastcall *)(IMFSample *, __int64 *))ppIMFSample->lpVtbl->SetUnknown)(ppIMFSample, MF_SA_HISTOGRAM);
        if ( g_wppLevels >= 4u )
          WPP_SF_qqdq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v9,
            v10,
            ppIMFSample,
            *(_QWORD *)v7,
            *((unsigned __int16 *)v7 + 4),
            this);
        CDXVAFrameManager::ForceCleanup(this, v4);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
    v8 = ppIMFSample;
    ppIMFSample = 0;
  }
  else
  {
    if ( g_wppLevels >= 4u )
      WPP_SF_dddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids,
        v7[56],
        v7[16],
        v7[32],
        this);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
    v8 = 0;
  }
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&ppIMFSample);
  return v8;
}

```

## disassembly

```asm
0x180052d30  mov     rax, rsp
0x180052d33  mov     [rax+8], rbx
0x180052d37  mov     [rax+10h], rsi
0x180052d3b  push    rbp
0x180052d3c  push    rdi
0x180052d3d  push    r14
0x180052d3f  mov     rbp, rsp
0x180052d42  sub     rsp, 50h
0x180052d46  movsxd  rsi, r8d
0x180052d49  movzx   r14d, dx
0x180052d4d  mov     rdi, rcx
0x180052d50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180052d57  jb      short loc_180052D7F
0x180052d59  mov     r9d, r14d
0x180052d5c  mov     edx, 1Bh
0x180052d61  mov     [rax-40h], rcx
0x180052d65  mov     [rax-48h], esi
0x180052d68  lea     r8, WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids
0x180052d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d76  mov     rcx, [rcx+10h]
0x180052d7a  call    WPP_SF_ddq
0x180052d7f  cmp     esi, 0FFFFFFFFh
0x180052d82  jnz     short loc_180052D8B
0x180052d84  xor     eax, eax
0x180052d86  jmp     loc_180052F3F
0x180052d8b  mov     [rbp+ppIMFSample], 0
0x180052d93  lea     rbx, [rdi+18h]
0x180052d97  mov     rcx, rbx; lpCriticalSection
0x180052d9a  call    cs:__imp_EnterCriticalSection
0x180052da0  mov     [rbp+var_8], rbx
0x180052da4  mov     rcx, r14
0x180052da7  shl     rcx, 6
0x180052dab  mov     rbx, [rdi+rsi*8+108h]
0x180052db3  add     rbx, rcx
0x180052db6  cmp     qword ptr [rbx], 0
0x180052dba  jnz     short loc_180052E0C
0x180052dbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180052dc3  jb      short loc_180052DFC
0x180052dc5  movzx   eax, byte ptr [rbx+20h]
0x180052dc9  movzx   ecx, byte ptr [rbx+10h]
0x180052dcd  movzx   r9d, byte ptr [rbx+38h]
0x180052dd2  mov     edx, 1Ch
0x180052dd7  mov     [rsp+50h+var_20], rdi
0x180052ddc  mov     [rsp+50h+var_28], eax
0x180052de0  mov     dword ptr [rsp+50h+var_30], ecx
0x180052de4  lea     r8, WPP_2ae34273ea0c3e44748ef5ee268f3ee0_Traceguids
0x180052deb  mov     rcx, cs:WPP_GLOBAL_Control
0x180052df2  mov     rcx, [rcx+10h]
0x180052df6  call    WPP_SF_dddq
0x180052dfb  nop
0x180052dfc  lea     rcx, [rbp+var_8]
0x180052e00  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180052e05  xor     ebx, ebx
0x180052e07  jmp     loc_180052F33
0x180052e0c  mov     [rbp+var_10], 0
0x180052e14  lea     rdx, [rbp+var_10]
0x180052e18  mov     rcx, rbx
0x180052e1b  call    ??$As@UIMFMediaBuffer@@@?$ComPtr@UIMFTrackedBuffer@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMFTrackedBuffer>::As<IMFMediaBuffer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFMediaBuffer>>)
0x180052e20  test    eax, eax
0x180052e22  jnz     loc_180052F14
0x180052e28  lea     rcx, [rbp+ppIMFSample]
0x180052e2c  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180052e31  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180052e35  call    cs:__imp_MFCreateSample
0x180052e3b  test    eax, eax
0x180052e3d  jnz     loc_180052F14
0x180052e43  mov     rcx, [rbp+ppIMFSample]
0x180052e47  mov     rax, [rcx]
0x180052e4a  mov     rdx, [rbp+var_10]
0x180052e4e  mov     rax, [rax+150h]
0x180052e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e5a  test    eax, eax
0x180052e5c  jnz     loc_180052F14
0x180052e62  lea     rcx, [rbp+var_10]
0x180052e66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052e6b  mov     rcx, [rbx]
0x180052e6e  mov     rax, [rcx]
0x180052e71  mov     edx, 1
0x180052e76  mov     rax, [rax+28h]
0x180052e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e7f  test    eax, eax
0x180052e81  jnz     loc_180052F1E
0x180052e87  mov     rcx, [rbp+ppIMFSample]
0x180052e8b  mov     rax, [rcx]
0x180052e8e  mov     r8d, r14d
0x180052e91  lea     rdx, ?DXVA_INTERNAL_SAMPLE_INDEX@@3U_GUID@@B; _GUID const DXVA_INTERNAL_SAMPLE_INDEX
0x180052e98  mov     rax, [rax+0A8h]
0x180052e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ea4  mov     byte ptr [rbx+10h], 1
0x180052ea8  mov     byte ptr [rbx+38h], 0
0x180052eac  mov     [rbx+8], r14w
0x180052eb1  mov     r8, [rbx+18h]
0x180052eb5  test    r8, r8
0x180052eb8  jz      short loc_180052ED4
0x180052eba  mov     rcx, [rbp+ppIMFSample]
0x180052ebe  mov     rax, [rcx]
0x180052ec1  lea     rdx, MF_SA_HISTOGRAM
0x180052ec8  mov     rax, [rax+0D8h]
0x180052ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ed4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180052edb  jb      short loc_180052F06
0x180052edd  movzx   eax, word ptr [rbx+8]
0x180052ee1  mov     [rsp+50h+var_20], rdi
0x180052ee6  mov     [rsp+50h+var_28], eax
0x180052eea  mov     rax, [rbx]
0x180052eed  mov     [rsp+50h+var_30], rax
0x180052ef2  mov     r9, [rbp+ppIMFSample]
0x180052ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180052efd  mov     rcx, [rcx+10h]
0x180052f01  call    WPP_SF_qqdq
0x180052f06  movzx   edx, r14w; unsigned __int16
0x180052f0a  mov     rcx, rdi; this
0x180052f0d  call    ?ForceCleanup@CDXVAFrameManager@@IEAAXG@Z; CDXVAFrameManager::ForceCleanup(ushort)
0x180052f12  jmp     short loc_180052F1E
0x180052f14  lea     rcx, [rbp+var_10]
0x180052f18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052f1d  nop
0x180052f1e  lea     rcx, [rbp+var_8]
0x180052f22  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180052f27  mov     rbx, [rbp+ppIMFSample]
0x180052f2b  mov     [rbp+ppIMFSample], 0
0x180052f33  lea     rcx, [rbp+ppIMFSample]
0x180052f37  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180052f3c  mov     rax, rbx
0x180052f3f  mov     rbx, [rsp+50h+arg_0]
0x180052f44  mov     rsi, [rsp+50h+arg_8]
0x180052f49  add     rsp, 50h
0x180052f4d  pop     r14
0x180052f4f  pop     rdi
0x180052f50  pop     rbp
0x180052f51  retn
```
