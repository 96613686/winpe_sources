# DXVAMFTCommon::xEnsureFrameManager(void)

- ea: `0x18004d088`
- end: `0x18004d12d`
- name: `?xEnsureFrameManager@DXVAMFTCommon@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040020`

## callees

- `0x180041668`
- `0x180044d78`
- `0x18004ac0c`
- `0x18004b3d4`
- `0x18004d088`
- `0x180054570`

## pseudocode

```c
__int64 __fastcall DXVAMFTCommon::xEnsureFrameManager(DXVAMFTCommon *this)
{
  CDXVAFrameManager **v1; // rdi
  __int64 result; // rax
  bool v4; // al
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v1 = (CDXVAFrameManager **)((char *)this + 392);
  if ( !*((_QWORD *)this + 49) )
  {
    v5 = 0;
    v6 = 0;
    Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease((__int64 *)this + 49);
    result = Microsoft::WRL::Details::MakeAndInitialize<CDXVAFrameManagerGenericDecode,CDXVAFrameManagerGenericDecode,std::nullptr_t,std::nullptr_t>(
               v1,
               &v6,
               &v5);
    if ( (_DWORD)result )
      return result;
    if ( g_wppLevels >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, this);
    if ( *((_QWORD *)this + 47) )
      v4 = DXVAConfigurationBase::ArrayOfTexturesPreferred((DXVAConfigurationBase *)(*((_QWORD *)this + 44) + 40LL));
    else
      v4 = 0;
    CDXVAFrameManager::SetArrayOfTexturesPreferred(*v1, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18004d088  mov     [rsp+arg_10], rbx
0x18004d08d  push    rdi
0x18004d08e  sub     rsp, 20h
0x18004d092  lea     rdi, [rcx+188h]
0x18004d099  mov     rbx, rcx
0x18004d09c  cmp     qword ptr [rdi], 0
0x18004d0a0  jnz     short loc_18004D120
0x18004d0a2  mov     rcx, rdi
0x18004d0a5  mov     [rsp+28h+arg_0], 0
0x18004d0ae  mov     [rsp+28h+arg_8], 0
0x18004d0b7  call    ?InternalRelease@?$ComPtr@VCDXVAFrameManagerGenericDecode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease(void)
0x18004d0bc  lea     r8, [rsp+28h+arg_0]
0x18004d0c1  mov     rcx, rdi
0x18004d0c4  lea     rdx, [rsp+28h+arg_8]
0x18004d0c9  call    ??$MakeAndInitialize@VCDXVAFrameManagerGenericDecode@@V1@$$T$$T@Details@WRL@Microsoft@@YAJPEAPEAVCDXVAFrameManagerGenericDecode@@$$QEA$$T1@Z
0x18004d0ce  test    eax, eax
0x18004d0d0  jnz     short loc_18004D122
0x18004d0d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18004d0d9  jb      short loc_18004D0F8
0x18004d0db  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d0e2  lea     edx, [rax+21h]
0x18004d0e5  mov     r9, rbx
0x18004d0e8  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004d0ef  mov     rcx, [rcx+10h]
0x18004d0f3  call    WPP_SF_q
0x18004d0f8  cmp     qword ptr [rbx+178h], 0
0x18004d100  jnz     short loc_18004D106
0x18004d102  xor     al, al
0x18004d104  jmp     short loc_18004D116
0x18004d106  mov     rcx, [rbx+160h]
0x18004d10d  add     rcx, 28h ; '('; this
0x18004d111  call    ?ArrayOfTexturesPreferred@DXVAConfigurationBase@@QEBA?B_NXZ; DXVAConfigurationBase::ArrayOfTexturesPreferred(void)
0x18004d116  mov     rcx, [rdi]; this
0x18004d119  mov     dl, al; bool
0x18004d11b  call    ?SetArrayOfTexturesPreferred@CDXVAFrameManager@@UEAAX_N@Z; CDXVAFrameManager::SetArrayOfTexturesPreferred(bool)
0x18004d120  xor     eax, eax
0x18004d122  mov     rbx, [rsp+28h+arg_10]
0x18004d127  add     rsp, 20h
0x18004d12b  pop     rdi
0x18004d12c  retn
```
