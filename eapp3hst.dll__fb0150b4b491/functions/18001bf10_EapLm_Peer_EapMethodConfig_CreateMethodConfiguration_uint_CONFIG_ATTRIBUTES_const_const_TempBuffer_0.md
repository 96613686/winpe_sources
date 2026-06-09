# EapLm::Peer::EapMethodConfig::CreateMethodConfiguration(uint,_CONFIG_ATTRIBUTES const * const,TempBuffer<0> &)

- ea: `0x18001bf10`
- end: `0x18001c094`
- name: `?CreateMethodConfiguration@EapMethodConfig@Peer@EapLm@@UEAAXIQEBU_CONFIG_ATTRIBUTES@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800017a0`
- `0x1800126f8`
- `0x18001549c`
- `0x1800154dc`
- `0x1800177bc`
- `0x18001bf10`
- `0x18002e494`
- `0x180034010`

## string_xrefs

- `0x18001bffe`: `EapPeerGetConfigBlobAndUserBlob`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::EapMethodConfig::CreateMethodConfiguration(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v8; // rdx
  __int64 (__fastcall *v9)(_QWORD, _BYTE *, __int64, unsigned int *, const void **, struct _EAP_ERROR **); // rax
  void (__fastcall *v10)(const void *); // rdi
  void (__fastcall *v11)(struct _EAP_ERROR *); // r14
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  unsigned int v15; // [rsp+40h] [rbp-F8h] BYREF
  const void *v16; // [rsp+48h] [rbp-F0h] BYREF
  struct _EAP_ERROR *v17; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v18[20]; // [rsp+60h] [rbp-D8h] BYREF
  int v19; // [rsp+78h] [rbp-C0h]
  void (__fastcall *v20)(const void *); // [rsp+80h] [rbp-B8h]
  _BYTE v21[96]; // [rsp+90h] [rbp-A8h] BYREF

  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 240), 1) != 1
    || (v8 = *(_QWORD **)(a1 + 240),
        (v9 = (__int64 (__fastcall *)(_QWORD, _BYTE *, __int64, unsigned int *, const void **, struct _EAP_ERROR **))v8[27]) == 0) )
  {
    v18[8] = *(_BYTE *)(a1 + 16);
    *(_DWORD *)&v18[12] = *(_DWORD *)(a1 + 20);
    *(_DWORD *)&v18[16] = *(_DWORD *)(a1 + 24);
    if ( v18[8] != 0xFE )
      *(_QWORD *)&v18[12] = 0;
    *(_QWORD *)v18 = &EapHost::EapMethodType::`vftable';
    v19 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v18, 0x80420020);
  }
  v10 = (void (__fastcall *)(const void *))v8[29];
  v20 = v10;
  v11 = (void (__fastcall *)(struct _EAP_ERROR *))v8[28];
  *(_OWORD *)v18 = *(_OWORD *)(a1 + 16);
  v12 = v9(a2, v18, a3, &v15, &v16, &v17);
  if ( v12 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v21, v17, v12);
    v11(v17);
    EapHost::EapException::Throw(L"EapPeerGetConfigBlobAndUserBlob", v13, (const struct EapHost::EapError *)v21);
  }
  try
  {
    TempBuffer<0>::Assign(a4, v15, v16);
  }
  catch ( std::bad_alloc )
  {
    v20(v16);
    throw;
  }
  TempBuffer<0>::Assign(a4, v15, v16);
}

```

## disassembly

```asm
0x18001bf10  push    rbx
0x18001bf12  push    rsi
0x18001bf13  push    rdi
0x18001bf14  push    r12
0x18001bf16  push    r14
0x18001bf18  push    r15
0x18001bf1a  sub     rsp, 108h
0x18001bf21  mov     rax, cs:__security_cookie
0x18001bf28  xor     rax, rsp
0x18001bf2b  mov     [rsp+138h+var_48], rax
0x18001bf33  mov     rsi, r9
0x18001bf36  mov     r12, r8
0x18001bf39  mov     r15d, edx
0x18001bf3c  mov     rbx, rcx
0x18001bf3f  mov     [rsp+138h+var_E8], 0
0x18001bf48  mov     [rsp+138h+var_F8], 0
0x18001bf50  mov     [rsp+138h+var_F0], 0
0x18001bf59  mov     dl, 1; bool
0x18001bf5b  mov     rcx, [rcx+0F0h]; this
0x18001bf62  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001bf67  cmp     al, 1
0x18001bf69  jnz     loc_18001C04B
0x18001bf6f  mov     rdx, [rbx+0F0h]
0x18001bf76  mov     rax, [rdx+0D8h]
0x18001bf7d  test    rax, rax
0x18001bf80  jz      loc_18001C04B
0x18001bf86  mov     rdi, [rdx+0E8h]
0x18001bf8d  mov     [rsp+138h+var_B8], rdi
0x18001bf95  mov     r14, [rdx+0E0h]
0x18001bf9c  movups  xmm0, xmmword ptr [rbx+10h]
0x18001bfa0  movdqu  [rsp+138h+var_D8], xmm0
0x18001bfa6  lea     rcx, [rsp+138h+var_E8]
0x18001bfab  mov     [rsp+138h+var_110], rcx
0x18001bfb0  lea     rcx, [rsp+138h+var_F0]
0x18001bfb5  mov     [rsp+138h+var_118], rcx
0x18001bfba  lea     r9, [rsp+138h+var_F8]
0x18001bfbf  mov     r8, r12
0x18001bfc2  lea     rdx, [rsp+138h+var_D8]
0x18001bfc7  mov     ecx, r15d
0x18001bfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfcf  test    eax, eax
0x18001bfd1  jz      short loc_18001C00B
0x18001bfd3  mov     r8d, eax; unsigned int
0x18001bfd6  mov     rdx, [rsp+138h+var_E8]; struct _EAP_ERROR *
0x18001bfdb  lea     rcx, [rsp+138h+var_A8]; this
0x18001bfe3  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001bfe8  nop
0x18001bfe9  mov     rcx, [rsp+138h+var_E8]
0x18001bfee  mov     rax, r14
0x18001bff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bff6  lea     r8, [rsp+138h+var_A8]; struct EapHost::EapError *
0x18001bffe  lea     rcx, aEappeergetconf; "EapPeerGetConfigBlobAndUserBlob"
0x18001c005  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001c00b  mov     edx, [rsp+138h+var_F8]
0x18001c00f  mov     r8, [rsp+138h+var_F0]
0x18001c014  mov     rcx, rsi
0x18001c017  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001c01c  nop
0x18001c01d  mov     rcx, [rsp+138h+var_F0]
0x18001c022  mov     rax, rdi
0x18001c025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c02a  mov     rcx, [rsp+138h+var_48]
0x18001c032  xor     rcx, rsp; StackCookie
0x18001c035  call    __security_check_cookie
0x18001c03a  add     rsp, 108h
0x18001c041  pop     r15
0x18001c043  pop     r14
0x18001c045  pop     r12
0x18001c047  pop     rdi
0x18001c048  pop     rsi
0x18001c049  pop     rbx
0x18001c04a  retn
0x18001c04b  mov     cl, [rbx+10h]
0x18001c04e  mov     byte ptr [rsp+138h+var_D8+8], cl
0x18001c052  mov     eax, [rbx+14h]
0x18001c055  mov     dword ptr [rsp+138h+var_D8+0Ch], eax
0x18001c059  mov     eax, [rbx+18h]
0x18001c05c  mov     [rsp+138h+var_C8], eax
0x18001c060  cmp     cl, 0FEh
0x18001c063  jz      short loc_18001C06E
0x18001c065  mov     qword ptr [rsp+138h+var_D8+0Ch], 0
0x18001c06e  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001c075  mov     qword ptr [rsp+138h+var_D8], rax
0x18001c07a  mov     eax, [rbx+1Ch]
0x18001c07d  mov     [rsp+138h+var_C0], eax
0x18001c081  mov     ecx, 80420020h; unsigned int
0x18001c086  mov     r8d, ecx; unsigned int
0x18001c089  lea     rdx, [rsp+138h+var_D8]; struct EapHost::EapMethodType *
0x18001c08e  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
