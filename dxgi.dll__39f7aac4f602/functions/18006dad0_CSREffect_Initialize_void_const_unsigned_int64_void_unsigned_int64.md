# CSREffect::Initialize(void * const,unsigned __int64,void *,unsigned __int64)

- ea: `0x18006dad0`
- end: `0x18006deb7`
- name: `?Initialize@CSREffect@@UEAAJQEAX_KPEAX1@Z`
- size: `999`
- prototype: `__int64 __fastcall(CSREffect *__hidden this, void *const, unsigned __int64, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180014750`
- `0x18001b22c`
- `0x18003ba90`
- `0x180067d2c`
- `0x18006d9c0`
- `0x18006dad0`
- `0x18006dec0`
- `0x18006e2d0`
- `0x180075fa0`
- `0x180080ebc`
- `0x180091e70`
- `0x1800ae5c4`
- `0x1800b3554`
- `0x1800b614c`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006dba7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006de18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006de37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006de6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006dba7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006de18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006de37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006de6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006db1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006db1b`

## string_xrefs

- `0x18006db7c`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffect.cpp`
- `0x18006dc05`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffect.cpp`
- `0x18006ddf3`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffect.cpp`
- `0x18006de4f`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffect.cpp`
- `0x18006de82`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffect.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSREffect::Initialize(CSREffect *this, _DWORD *a2, __int64 a3, void *a4, unsigned __int64 a5)
{
  RTL_SRWLOCK *v9; // rbx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // esi
  __int64 v14; // rdx
  __int64 result; // rax
  __int64 v16; // rcx
  int v17; // eax
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  CSREffectDx12 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int128 *v23; // rax
  __int128 *v24; // rcx
  __int64 v25; // r8
  BOOL v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  int wnf_subscription; // eax
  RTL_SRWLOCK *v30; // rcx
  char *v31; // rdi
  struct wil::details::wnf_subscription_state_base *v32; // rdx
  int v33; // [rsp+20h] [rbp-D8h]
  __int64 v34; // [rsp+30h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+38h] [rbp-C0h] BYREF
  _BYTE v36[8]; // [rsp+48h] [rbp-B0h] BYREF
  _QWORD v37[14]; // [rsp+50h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( !a2 || !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffect.cpp",
      (const char *)0x80070057LL,
      v33);
    return 2147942487LL;
  }
  v9 = (RTL_SRWLOCK *)((char *)this + 40);
  SRWLock[0] = (PSRWLOCK)((char *)this + 40);
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  SRWLock[1] = v9;
  if ( a3 != 72 || a5 != 44 )
  {
    v11 = 208;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffect.cpp",
      (const char *)0x80070057LL,
      v33);
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    return 2147942487LL;
  }
  v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a2;
  if ( !*(_QWORD *)a2 )
  {
    v11 = 209;
    goto LABEL_48;
  }
  v34 = 0;
  v12 = (**v10)(v10, &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed, &v34);
  try
  {
    v13 = v12;
    if ( v12 >= 0 )
    {
      v33 = 44;
      v13 = CSREffectDx12::CheckSupport(*((unsigned int *)this + 4), a2, 72, a4);
      if ( v13 >= 0 )
      {
        v16 = *((_QWORD *)this + 65);
        if ( v16 )
        {
          v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 40LL))(v16);
          v18 = retaddr;
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xE0,
              (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffect.cpp",
              (const char *)(unsigned int)v17,
              44);
          v19 = *((_QWORD *)this + 65);
          *((_QWORD *)this + 65) = 0;
          if ( v19 )
            std::default_delete<CHDRConverterImpl>::operator()(v18);
        }
        v20 = (CSREffectDx12 *)operator new(0x100u);
        if ( v20 )
          v20 = CSREffectDx12::CSREffectDx12(v20, *((_BYTE *)this + 12));
        v22 = *((_QWORD *)this + 65);
        *((_QWORD *)this + 65) = v20;
        if ( v22 )
          std::default_delete<CHDRConverterImpl>::operator()(v21);
        if ( *((_QWORD *)this + 64) != *(_QWORD *)a2 )
          *((_QWORD *)this + 64) = *(_QWORD *)a2;
        v13 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, void *))(**((_QWORD **)this + 65) + 16LL))(
                *((_QWORD *)this + 65),
                a2,
                a4);
        if ( v13 >= 0 )
        {
          v23 = (__int128 *)((char *)this + 256);
          v24 = &xmmword_18010C300;
          v25 = 2;
          do
          {
            *v23 = *v24;
            v23[1] = v24[1];
            v23[2] = v24[2];
            v23[3] = v24[3];
            v23[4] = v24[4];
            v23[5] = v24[5];
            v23[6] = v24[6];
            v23[7] = v24[7];
            v23 += 8;
            v24 += 8;
            --v25;
          }
          while ( v25 );
          *((_DWORD *)this + 72) = g_AutoSRConfig;
          *((_DWORD *)this + 73) = *(&g_AutoSRConfig + 1);
          v26 = a2[9] == 29 || a2[9] == 91 || a2[9] == 93;
          *((_DWORD *)this + 74) = v26;
          v13 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, __int64))(**((_QWORD **)this + 65) + 32LL))(
                  *((_QWORD *)this + 65),
                  (char *)this + 256,
                  0,
                  128);
          if ( v13 >= 0 )
          {
            v37[0] = off_1800D13C0;
            v37[1] = this;
            v37[13] = v37;
            SRWLock[0] = 0;
            wnf_subscription = wil::details::make_wnf_subscription_state<DXGI_EFFECT_CONFIG>(v27, v36, v28, SRWLock);
            v30 = 0;
            if ( wnf_subscription >= 0 )
              v30 = SRWLock[0];
            SRWLock[0] = v30;
            v31 = (char *)this + 48;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
              v31,
              SRWLock);
            if ( SRWLock[0] )
              wil::details::delete_wnf_subscription_state((wil::details *)SRWLock[0], v32);
            wistd::function<void (AUTOHDR_STRENGTH_WNF const &)>::~function<void (AUTOHDR_STRENGTH_WNF const &)>(v36);
            wil::details::in1diag3::Log_HrIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>,0>(
              retaddr,
              294,
              "onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffect.cpp",
              2147500037LL,
              v31,
              "Failed to subscribe to slider WNF",
              v34);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
            if ( v9 )
              ReleaseSRWLockExclusive(v9);
            return 0;
          }
          v14 = 274;
        }
        else
        {
          v14 = 251;
        }
      }
      else
      {
        v14 = 215;
      }
    }
    else
    {
      v14 = 213;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffect.cpp",
      (const char *)(unsigned int)v13,
      v33);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    result = (unsigned int)v13;
  }
  catch ( std::bad_alloc )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18006dad0  push    rbx
0x18006dad2  push    rsi
0x18006dad3  push    rdi
0x18006dad4  push    r14
0x18006dad6  push    r15
0x18006dad8  sub     rsp, 0D0h
0x18006dadf  mov     rax, cs:__security_cookie
0x18006dae6  xor     rax, rsp
0x18006dae9  mov     [rsp+0F8h+var_38], rax
0x18006daf1  mov     r15, r9
0x18006daf4  mov     rsi, r8
0x18006daf7  mov     r14, rdx
0x18006dafa  mov     rdi, rcx
0x18006dafd  test    rdx, rdx
0x18006db00  jz      loc_18006DE74
0x18006db06  test    r9, r9
0x18006db09  jz      loc_18006DE74
0x18006db0f  lea     rbx, [rcx+28h]
0x18006db13  mov     [rsp+0F8h+SRWLock], rbx
0x18006db18  mov     rcx, rbx; SRWLock
0x18006db1b  call    cs:__imp_AcquireSRWLockExclusive
0x18006db21  mov     [rsp+0F8h+var_B8], rbx
0x18006db26  cmp     rsi, 48h ; 'H'
0x18006db2a  jnz     loc_18006DE44
0x18006db30  cmp     [rsp+0F8h+arg_20], 2Ch ; ','
0x18006db39  jnz     loc_18006DE44
0x18006db3f  mov     rcx, [r14]
0x18006db42  test    rcx, rcx
0x18006db45  jnz     short loc_18006DB51
0x18006db47  mov     edx, 0D1h
0x18006db4c  jmp     loc_18006DE49
0x18006db51  mov     [rsp+0F8h+var_C8], 0
0x18006db5a  mov     rax, [rcx]
0x18006db5d  lea     r8, [rsp+0F8h+var_C8]
0x18006db62  lea     rdx, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x18006db69  mov     rax, [rax]
0x18006db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db71  mov     esi, eax
0x18006db73  test    eax, eax
0x18006db75  jns     short loc_18006DBB4
0x18006db77  mov     edx, 0D5h; void *
0x18006db7c  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18006db83  mov     r9d, esi; char *
0x18006db86  mov     rcx, [rsp+0F8h]; this
0x18006db8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006db93  nop
0x18006db94  lea     rcx, [rsp+0F8h+var_C8]
0x18006db99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006db9e  nop
0x18006db9f  test    rbx, rbx
0x18006dba2  jz      short loc_18006DBAD
0x18006dba4  mov     rcx, rbx; SRWLock
0x18006dba7  call    cs:__imp_ReleaseSRWLockExclusive
0x18006dbad  mov     eax, esi
0x18006dbaf  jmp     loc_18006DE98
0x18006dbb4  mov     qword ptr [rsp+0F8h+var_D8], 2Ch ; ','; int
0x18006dbbd  mov     r9, r15
0x18006dbc0  mov     r8d, 48h ; 'H'
0x18006dbc6  mov     rdx, r14
0x18006dbc9  mov     ecx, [rdi+10h]
0x18006dbcc  call    ?CheckSupport@CSREffectDx12@@SAJW4DXGI_EFFECT_TYPE@@QEAX_KPEAX2@Z; CSREffectDx12::CheckSupport(DXGI_EFFECT_TYPE,void * const,unsigned __int64,void *,unsigned __int64)
0x18006dbd1  mov     esi, eax
0x18006dbd3  test    eax, eax
0x18006dbd5  jns     short loc_18006DBDE
0x18006dbd7  mov     edx, 0D7h
0x18006dbdc  jmp     short loc_18006DB7C
0x18006dbde  mov     rcx, [rdi+208h]
0x18006dbe5  test    rcx, rcx
0x18006dbe8  jz      short loc_18006DC33
0x18006dbea  mov     rax, [rcx]
0x18006dbed  mov     rax, [rax+28h]
0x18006dbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dbf6  mov     rcx, [rsp+0F8h]; this
0x18006dbfe  test    eax, eax
0x18006dc00  jns     short loc_18006DC16
0x18006dc02  mov     r9d, eax; char *
0x18006dc05  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18006dc0c  mov     edx, 0E0h; void *
0x18006dc11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006dc16  mov     rdx, [rdi+208h]
0x18006dc1d  mov     qword ptr [rdi+208h], 0
0x18006dc28  test    rdx, rdx
0x18006dc2b  jz      short loc_18006DC33
0x18006dc2d  call    ??R?$default_delete@VCHDRConverterImpl@@@std@@QEBAXPEAVCHDRConverterImpl@@@Z; std::default_delete<CHDRConverterImpl>::operator()(CHDRConverterImpl *)
0x18006dc32  nop
0x18006dc33  mov     ecx, 100h; dwBytes
0x18006dc38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006dc3d  test    rax, rax
0x18006dc40  jz      short loc_18006DC4D
0x18006dc42  mov     dl, [rdi+0Ch]; bool
0x18006dc45  mov     rcx, rax; this
0x18006dc48  call    ??0CSREffectDx12@@QEAA@_N@Z; CSREffectDx12::CSREffectDx12(bool)
0x18006dc4d  mov     rdx, [rdi+208h]
0x18006dc54  mov     [rdi+208h], rax
0x18006dc5b  test    rdx, rdx
0x18006dc5e  jz      short loc_18006DC66
0x18006dc60  call    ??R?$default_delete@VCHDRConverterImpl@@@std@@QEBAXPEAVCHDRConverterImpl@@@Z; std::default_delete<CHDRConverterImpl>::operator()(CHDRConverterImpl *)
0x18006dc65  nop
0x18006dc66  mov     rax, [r14]
0x18006dc69  cmp     [rdi+200h], rax
0x18006dc70  jz      short loc_18006DC79
0x18006dc72  mov     [rdi+200h], rax
0x18006dc79  mov     rcx, [rdi+208h]
0x18006dc80  mov     rax, [rcx]
0x18006dc83  mov     r8, r15
0x18006dc86  mov     rdx, r14
0x18006dc89  mov     rax, [rax+10h]
0x18006dc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc92  mov     esi, eax
0x18006dc94  test    eax, eax
0x18006dc96  jns     short loc_18006DCA2
0x18006dc98  mov     edx, 0FBh
0x18006dc9d  jmp     loc_18006DB7C
0x18006dca2  lea     rdx, [rdi+100h]
0x18006dca9  mov     rax, rdx
0x18006dcac  lea     rcx, xmmword_18010C300
0x18006dcb3  mov     r8d, 2
0x18006dcb9  lea     r9d, [r8+7Eh]
0x18006dcbd  movups  xmm0, xmmword ptr [rcx]
0x18006dcc0  movups  xmmword ptr [rax], xmm0
0x18006dcc3  movups  xmm1, xmmword ptr [rcx+10h]
0x18006dcc7  movups  xmmword ptr [rax+10h], xmm1
0x18006dccb  movups  xmm0, xmmword ptr [rcx+20h]
0x18006dccf  movups  xmmword ptr [rax+20h], xmm0
0x18006dcd3  movups  xmm1, xmmword ptr [rcx+30h]
0x18006dcd7  movups  xmmword ptr [rax+30h], xmm1
0x18006dcdb  movups  xmm0, xmmword ptr [rcx+40h]
0x18006dcdf  movups  xmmword ptr [rax+40h], xmm0
0x18006dce3  movups  xmm1, xmmword ptr [rcx+50h]
0x18006dce7  movups  xmmword ptr [rax+50h], xmm1
0x18006dceb  movups  xmm0, xmmword ptr [rcx+60h]
0x18006dcef  movups  xmmword ptr [rax+60h], xmm0
0x18006dcf3  movups  xmm1, xmmword ptr [rcx+70h]
0x18006dcf7  movups  xmmword ptr [rax+70h], xmm1
0x18006dcfb  add     rax, r9
0x18006dcfe  add     rcx, r9
0x18006dd01  sub     r8, 1
0x18006dd05  jnz     short loc_18006DCBD
0x18006dd07  movzx   eax, byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A; AutoSRConfig g_AutoSRConfig
0x18006dd0e  mov     [rdi+120h], eax
0x18006dd14  movzx   eax, byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+1; AutoSRConfig g_AutoSRConfig
0x18006dd1b  mov     [rdi+124h], eax
0x18006dd21  cmp     dword ptr [r14+24h], 1Dh
0x18006dd26  jz      short loc_18006DD3A
0x18006dd28  cmp     dword ptr [r14+24h], 5Bh ; '['
0x18006dd2d  jz      short loc_18006DD3A
0x18006dd2f  cmp     dword ptr [r14+24h], 5Dh ; ']'
0x18006dd34  jz      short loc_18006DD3A
0x18006dd36  xor     eax, eax
0x18006dd38  jmp     short loc_18006DD3F
0x18006dd3a  mov     eax, 1
0x18006dd3f  mov     [rdx+28h], eax
0x18006dd42  mov     rcx, [rdi+208h]
0x18006dd49  mov     rax, [rcx]
0x18006dd4c  mov     rax, [rax+20h]
0x18006dd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd55  mov     esi, eax
0x18006dd57  test    eax, eax
0x18006dd59  jns     short loc_18006DD65
0x18006dd5b  mov     edx, 112h
0x18006dd60  jmp     loc_18006DB7C
0x18006dd65  lea     rax, off_1800D13C0
0x18006dd6c  mov     [rsp+0F8h+var_A8], rax
0x18006dd71  mov     [rsp+0F8h+var_A0], rdi
0x18006dd76  lea     rax, [rsp+0F8h+var_A8]
0x18006dd7b  mov     [rsp+0F8h+var_40], rax
0x18006dd83  mov     [rsp+0F8h+SRWLock], 0
0x18006dd8c  lea     r9, [rsp+0F8h+SRWLock]
0x18006dd91  lea     rdx, [rsp+0F8h+var_B0]
0x18006dd96  call    ??$make_wnf_subscription_state@UDXGI_EFFECT_CONFIG@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUDXGI_EFFECT_CONFIG@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@UDXGI_EFFECT_CONFIG@@@01@@Z; wil::details::make_wnf_subscription_state<DXGI_EFFECT_CONFIG>(_WNF_STATE_NAME const &,wistd::function<void (DXGI_EFFECT_CONFIG const &)> &&,ulong,wil::details::wnf_subscription_state<DXGI_EFFECT_CONFIG> * *)
0x18006dd9b  xor     ecx, ecx
0x18006dd9d  test    eax, eax
0x18006dd9f  cmovns  rcx, [rsp+0F8h+SRWLock]
0x18006dda5  mov     [rsp+0F8h+SRWLock], rcx
0x18006ddaa  add     rdi, 30h ; '0'
0x18006ddae  lea     rdx, [rsp+0F8h+SRWLock]
0x18006ddb3  mov     rcx, rdi
0x18006ddb6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18006ddbb  mov     rcx, [rsp+0F8h+SRWLock]; this
0x18006ddc0  test    rcx, rcx
0x18006ddc3  jz      short loc_18006DDCA
0x18006ddc5  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18006ddca  lea     rcx, [rsp+0F8h+var_B0]
0x18006ddcf  call    ??1?$function@$$A6AXAEBUAUTOHDR_STRENGTH_WNF@@@Z@wistd@@QEAA@XZ; wistd::function<void (AUTOHDR_STRENGTH_WNF const &)>::~function<void (AUTOHDR_STRENGTH_WNF const &)>(void)
0x18006ddd4  mov     rcx, [rsp+0F8h]
0x18006dddc  lea     rax, aFailedToSubscr; "Failed to subscribe to slider WNF"
0x18006dde3  mov     [rsp+0F8h+var_D0], rax
0x18006dde8  mov     qword ptr [rsp+0F8h+var_D8], rdi
0x18006dded  mov     r9d, 80004005h
0x18006ddf3  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18006ddfa  mov     edx, 126h
0x18006ddff  call    ??$Log_HrIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Log_HrIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>,0>(void *,uint,char const *,long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> const &,char const *,...)
0x18006de04  nop
0x18006de05  lea     rcx, [rsp+0F8h+var_C8]
0x18006de0a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006de0f  nop
0x18006de10  test    rbx, rbx
0x18006de13  jz      short loc_18006DE1E
0x18006de15  mov     rcx, rbx; SRWLock
0x18006de18  call    cs:__imp_ReleaseSRWLockExclusive
0x18006de1e  xor     eax, eax
0x18006de20  jmp     short loc_18006DE98
0x18006de22  lea     rcx, [rsp+0F8h+var_C8]
0x18006de27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006de2c  nop
0x18006de2d  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x18006de32  test    rcx, rcx
0x18006de35  jz      short loc_18006DE3D
0x18006de37  call    cs:__imp_ReleaseSRWLockExclusive
0x18006de3d  mov     eax, 8007000Eh
0x18006de42  jmp     short loc_18006DE98
0x18006de44  mov     edx, 0D0h; void *
0x18006de49  mov     r9d, 80070057h; char *
0x18006de4f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18006de56  mov     rcx, [rsp+0F8h]; this
0x18006de5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006de63  nop
0x18006de64  test    rbx, rbx
0x18006de67  jz      short loc_18006DE93
0x18006de69  mov     rcx, rbx; SRWLock
0x18006de6c  call    cs:__imp_ReleaseSRWLockExclusive
0x18006de72  jmp     short loc_18006DE93
0x18006de74  mov     rcx, [rsp+0F8h]; this
0x18006de7c  mov     r9d, 80070057h; char *
0x18006de82  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x18006de89  mov     edx, 0C4h; void *
0x18006de8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006de93  mov     eax, 80070057h
0x18006de98  mov     rcx, [rsp+0F8h+var_38]
0x18006dea0  xor     rcx, rsp; StackCookie
0x18006dea3  call    __security_check_cookie
0x18006dea8  add     rsp, 0D0h
0x18006deaf  pop     r15
0x18006deb1  pop     r14
0x18006deb3  pop     rdi
0x18006deb4  pop     rsi
0x18006deb5  pop     rbx
0x18006deb6  retn
```
