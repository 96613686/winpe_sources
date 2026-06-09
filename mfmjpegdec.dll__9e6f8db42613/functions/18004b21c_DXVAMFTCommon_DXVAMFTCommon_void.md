# DXVAMFTCommon::~DXVAMFTCommon(void)

- ea: `0x18004b21c`
- end: `0x18004b2ed`
- name: `??1DXVAMFTCommon@@QEAA@XZ`
- size: `209`
- prototype: `void __fastcall(DXVAMFTCommon *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f408`

## callees

- `0x180020598`
- `0x180041668`
- `0x180043194`
- `0x180043324`
- `0x18004b21c`
- `0x1800533c0`
- `0x180070010`

## pseudocode

```c
void __fastcall DXVAMFTCommon::~DXVAMFTCommon(DXVAMFTCommon *this)
{
  __int64 *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &DXVAMFTCommon::`vftable';
  v2 = (__int64 *)((char *)this + 400);
  v3 = *((_QWORD *)this + 50);
  if ( v3 && *((_QWORD *)this + 52) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
    *((_QWORD *)this + 52) = 0;
  }
  v4 = *((_QWORD *)this + 49);
  if ( v4 )
    CDXVAFrameManager::Cleanup(v4, 2, 0);
  v5 = *((_QWORD *)this + 55);
  if ( v5 )
  {
    *((_QWORD *)this + 55) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
  Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease((char *)this + 392);
  utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit((char *)this + 352);
  wistd::unique_ptr<CGenericDXVAAllocatorDecode,wistd::default_delete<CGenericDXVAAllocatorDecode>>::reset(
    (char *)this + 8,
    0);
}

```

## disassembly

```asm
0x18004b21c  mov     [rsp+arg_0], rbx
0x18004b221  mov     [rsp+arg_8], rsi
0x18004b226  push    rdi
0x18004b227  sub     rsp, 20h
0x18004b22b  mov     rbx, rcx
0x18004b22e  lea     rax, ??_7DXVAMFTCommon@@6B@; const DXVAMFTCommon::`vftable'
0x18004b235  mov     [rcx], rax
0x18004b238  lea     rsi, [rcx+190h]
0x18004b23f  mov     rcx, [rsi]
0x18004b242  test    rcx, rcx
0x18004b245  jz      short loc_18004B26A
0x18004b247  mov     rdx, [rbx+1A0h]
0x18004b24e  test    rdx, rdx
0x18004b251  jz      short loc_18004B26A
0x18004b253  mov     rax, [rcx]
0x18004b256  mov     rax, [rax+18h]
0x18004b25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b25f  mov     qword ptr [rbx+1A0h], 0
0x18004b26a  lea     rdi, [rbx+188h]
0x18004b271  mov     rcx, [rdi]
0x18004b274  test    rcx, rcx
0x18004b277  jz      short loc_18004B288
0x18004b279  xor     r9d, r9d
0x18004b27c  xor     r8d, r8d
0x18004b27f  lea     edx, [r9+2]
0x18004b283  call    ?Cleanup@CDXVAFrameManager@@UEAAJW4FRAMEMGR_CLEANUP_STATE@@PEAI1@Z; CDXVAFrameManager::Cleanup(FRAMEMGR_CLEANUP_STATE,uint *,uint *)
0x18004b288  mov     rcx, [rbx+1B8h]
0x18004b28f  test    rcx, rcx
0x18004b292  jz      short loc_18004B2AB
0x18004b294  mov     qword ptr [rbx+1B8h], 0
0x18004b29f  mov     rax, [rcx]
0x18004b2a2  mov     rax, [rax+10h]
0x18004b2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2ab  lea     rcx, [rbx+198h]
0x18004b2b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b2b7  mov     rcx, rsi
0x18004b2ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b2bf  mov     rcx, rdi
0x18004b2c2  call    ?InternalRelease@?$ComPtr@VCDXVAFrameManagerGenericDecode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease(void)
0x18004b2c7  lea     rcx, [rbx+160h]
0x18004b2ce  call    ?_Uninit@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_Uninit(void)
0x18004b2d3  lea     rcx, [rbx+8]
0x18004b2d7  xor     edx, edx
0x18004b2d9  mov     rbx, [rsp+28h+arg_0]
0x18004b2de  mov     rsi, [rsp+28h+arg_8]
0x18004b2e3  add     rsp, 20h
0x18004b2e7  pop     rdi
0x18004b2e8  jmp     ?reset@?$unique_ptr@VCGenericDXVAAllocatorDecode@@U?$default_delete@VCGenericDXVAAllocatorDecode@@@wistd@@@wistd@@QEAAXPEAVCGenericDXVAAllocatorDecode@@@Z; wistd::unique_ptr<CGenericDXVAAllocatorDecode,wistd::default_delete<CGenericDXVAAllocatorDecode>>::reset(CGenericDXVAAllocatorDecode *)
```
