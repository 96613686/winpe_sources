# DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::~DXGIAdapterCacheHealthActivity(void)

- ea: `0x14000672c`
- end: `0x140006849`
- name: `??1DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@QEAA@XZ`
- size: `285`
- prototype: `void __fastcall(DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000e174`
- `0x140011a2e`

## callees

- `0x140002578`
- `0x140002d4c`
- `0x140005f4c`
- `0x140005fc4`
- `0x14000672c`
- `0x140009e44`
- `0x14000fa00`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400067c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400067c0`

## pseudocode

```c
void __fastcall DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::~DXGIAdapterCacheHealthActivity(
        DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *this)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  void *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[160]; // [rsp+30h] [rbp-A8h] BYREF

  *(_QWORD *)this = &DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::`vftable';
  if ( !*((_QWORD *)this + 35) )
    goto LABEL_13;
  wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    SRWLock);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( v2 && *v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
      {
        v4 = (void *)*((_QWORD *)this + 35);
        if ( v4 )
        {
          wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
          operator delete(v4, 0x110u);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v5 == 1 )
    {
      v6 = -2147024322;
      if ( (int)v5[22] < 0 )
        v6 = v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset_0(v10, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v10, v8);
      }
      if ( (int)v5[18] >= 0 )
        v5[18] = v6;
      v5[62] = v7 - 1;
      (*(void (__fastcall **)(DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x14000672c  mov     [rsp+arg_8], rbx
0x140006731  mov     [rsp+arg_10], rsi
0x140006736  push    rdi
0x140006737  sub     rsp, 0D0h
0x14000673e  mov     rbx, rcx
0x140006741  lea     rax, ??_7DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@6B@; const DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::`vftable'
0x140006748  mov     [rcx], rax
0x14000674b  cmp     qword ptr [rcx+118h], 0
0x140006753  jz      short loc_1400067CB
0x140006755  lea     rdx, [rsp+0D8h+SRWLock]
0x14000675a  call    ?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000675f  mov     rcx, [rbx+118h]
0x140006766  test    rcx, rcx
0x140006769  jz      short loc_140006775
0x14000676b  cmp     dword ptr [rcx], 1
0x14000676e  jnz     short loc_140006775
0x140006770  mov     sil, 1
0x140006773  jmp     short loc_1400067B6
0x140006775  xor     sil, sil
0x140006778  test    rcx, rcx
0x14000677b  jz      short loc_1400067B6
0x14000677d  or      eax, 0FFFFFFFFh
0x140006780  lock xadd [rcx], eax
0x140006784  cmp     eax, 1
0x140006787  jnz     short loc_1400067AB
0x140006789  mov     rdi, [rbx+118h]
0x140006790  test    rdi, rdi
0x140006793  jz      short loc_1400067AB
0x140006795  lea     rcx, [rdi+8]
0x140006799  call    ??1?$ActivityData@VDXGIAdapterCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000679e  mov     edx, 110h; unsigned __int64
0x1400067a3  mov     rcx, rdi; void *
0x1400067a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400067ab  mov     qword ptr [rbx+118h], 0
0x1400067b6  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x1400067bb  test    rcx, rcx
0x1400067be  jz      short loc_1400067C6
0x1400067c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400067c6  test    sil, sil
0x1400067c9  jz      short loc_140006810
0x1400067cb  mov     rcx, [rbx+110h]
0x1400067d2  cmp     dword ptr [rcx], 1
0x1400067d5  jnz     short loc_140006810
0x1400067d7  mov     eax, 8007023Eh
0x1400067dc  cmp     dword ptr [rcx+58h], 0
0x1400067e0  cmovl   eax, [rcx+58h]
0x1400067e4  mov     edx, [rcx+0F8h]
0x1400067ea  cmp     edx, 1
0x1400067ed  jl      short loc_14000682C
0x1400067ef  cmp     dword ptr [rcx+48h], 0
0x1400067f3  jl      short loc_1400067F8
0x1400067f5  mov     [rcx+48h], eax
0x1400067f8  lea     eax, [rdx-1]
0x1400067fb  mov     [rcx+0F8h], eax
0x140006801  mov     rax, [rbx]
0x140006804  mov     rcx, rbx
0x140006807  mov     rax, [rax+8]
0x14000680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006810  mov     rcx, rbx
0x140006813  lea     r11, [rsp+0D8h+var_8]
0x14000681b  mov     rbx, [r11+18h]
0x14000681f  mov     rsi, [r11+20h]
0x140006823  mov     rsp, r11
0x140006826  pop     rdi
0x140006827  jmp     ??1?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000682c  xor     edx, edx; Val
0x14000682e  mov     r8d, 98h; Size
0x140006834  lea     rcx, [rsp+0D8h+var_A8]; void *
0x140006839  call    memset_0
0x14000683e  lea     rcx, [rsp+0D8h+var_A8]; this
0x140006843  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
