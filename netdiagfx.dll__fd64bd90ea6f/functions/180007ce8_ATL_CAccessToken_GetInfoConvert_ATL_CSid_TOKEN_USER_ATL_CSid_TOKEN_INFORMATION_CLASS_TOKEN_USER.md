# ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)

- ea: `0x180007ce8`
- end: `0x180007e49`
- name: `??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z`
- size: `353`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000c478`

## callees

- `0x180005e54`
- `0x180007b48`
- `0x180007b78`
- `0x180007bec`
- `0x180007ce8`
- `0x180009ee4`
- `0x18002c840`
- `0x18002c900`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007d3b`
- `KERNEL32!GetLastError` at `0x180007d3b`
- `ADVAPI32!GetTokenInformation` at `0x180007d35`
- `ADVAPI32!GetTokenInformation` at `0x180007dc0`
- `ADVAPI32!GetTokenInformation` at `0x180007d35`
- `ADVAPI32!GetTokenInformation` at `0x180007dc0`

## pseudocode

```c
char __fastcall ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(__int64 a1, __int64 a2)
{
  char v4; // si
  unsigned __int64 v5; // rdx
  DWORD v6; // eax
  DWORD v7; // r9d
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  DWORD *p_TokenInformation; // rdi
  const struct _SID *v12; // rdi
  DWORD TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  __int64 v15; // [rsp+38h] [rbp+8h] BYREF

  if ( !a2 )
    return 0;
  TokenInformation = 0;
  v4 = 1;
  GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &TokenInformation);
  if ( GetLastError() != 122 )
    return 0;
  v15 = 0;
  v6 = TokenInformation;
  if ( TokenInformation <= 0x400 )
  {
    if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)TokenInformation, v5) )
    {
      v7 = TokenInformation;
      v8 = TokenInformation + 15LL;
      if ( v8 <= TokenInformation )
        v8 = 0xFFFFFFFFFFFFFF0LL;
      v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
      v10 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
      p_TokenInformation = &TokenInformation;
      goto LABEL_10;
    }
    v6 = TokenInformation;
  }
  p_TokenInformation = (DWORD *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::Allocate(
                                  &v15,
                                  v6);
  v7 = TokenInformation;
LABEL_10:
  if ( p_TokenInformation
    && GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, p_TokenInformation, v7, &TokenInformation) )
  {
    v12 = *(const struct _SID **)p_TokenInformation;
    if ( !*(_BYTE *)(a2 + 76) || (const struct _SID *)(a2 + 8) != v12 )
    {
      *(_DWORD *)(a2 + 80) = 7;
      ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 88);
      ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 96);
      ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 104);
      ATL::CSimpleStringT<unsigned short,0>::Empty(a2 + 112);
      *(_BYTE *)(a2 + 76) = 0;
      ATL::CSid::Copy((ATL::CSid *)a2, v12);
      *(_DWORD *)(a2 + 80) = 8;
    }
  }
  else
  {
    v4 = 0;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v15);
  return v4;
}

```

## disassembly

```asm
0x180007ce8  push    rbp
0x180007cea  push    rbx
0x180007ceb  push    rsi
0x180007cec  push    rdi
0x180007ced  push    r14
0x180007cef  sub     rsp, 50h
0x180007cf3  lea     rbp, [rsp+30h]
0x180007cf8  mov     rax, cs:__security_cookie
0x180007cff  xor     rax, rbp
0x180007d02  mov     [rbp+40h+var_30], rax
0x180007d06  mov     rbx, rdx
0x180007d09  mov     r14, rcx
0x180007d0c  test    rdx, rdx
0x180007d0f  jz      loc_180007E30
0x180007d15  mov     [rbp+40h+TokenInformation], 0
0x180007d1c  lea     rax, [rbp+40h+TokenInformation]
0x180007d20  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180007d25  xor     r9d, r9d; TokenInformationLength
0x180007d28  xor     r8d, r8d; TokenInformation
0x180007d2b  lea     esi, [r9+1]
0x180007d2f  mov     edx, esi; TokenInformationClass
0x180007d31  mov     rcx, [rcx+8]; TokenHandle
0x180007d35  call    cs:__imp_GetTokenInformation
0x180007d3b  call    cs:__imp_GetLastError
0x180007d41  cmp     eax, 7Ah ; 'z'
0x180007d44  jnz     loc_180007E30
0x180007d4a  mov     [rbp+40h+var_38], 0
0x180007d52  mov     eax, [rbp+40h+TokenInformation]
0x180007d55  cmp     eax, 400h
0x180007d5a  ja      short loc_180007D97
0x180007d5c  mov     ecx, eax; this
0x180007d5e  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180007d63  test    al, al
0x180007d65  jz      short loc_180007D94
0x180007d67  mov     r9d, [rbp+40h+TokenInformation]
0x180007d6b  lea     rcx, [r9+0Fh]
0x180007d6f  cmp     rcx, r9
0x180007d72  ja      short loc_180007D7E
0x180007d74  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180007d7e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180007d82  mov     rax, rcx
0x180007d85  call    _alloca_probe
0x180007d8a  sub     rsp, rcx
0x180007d8d  lea     rdi, [rsp+70h+TokenInformation]
0x180007d92  jmp     short loc_180007DA9
0x180007d94  mov     eax, [rbp+40h+TokenInformation]
0x180007d97  mov     edx, eax
0x180007d99  lea     rcx, [rbp+40h+var_38]
0x180007d9d  call    ?Allocate@?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180007da2  mov     rdi, rax
0x180007da5  mov     r9d, [rbp+40h+TokenInformation]; TokenInformationLength
0x180007da9  test    rdi, rdi
0x180007dac  jz      short loc_180007E1F
0x180007dae  lea     rax, [rbp+40h+TokenInformation]
0x180007db2  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180007db7  mov     r8, rdi; TokenInformation
0x180007dba  mov     edx, esi; TokenInformationClass
0x180007dbc  mov     rcx, [r14+8]; TokenHandle
0x180007dc0  call    cs:__imp_GetTokenInformation
0x180007dc6  test    eax, eax
0x180007dc8  jz      short loc_180007E1F
0x180007dca  mov     rdi, [rdi]
0x180007dcd  cmp     byte ptr [rbx+4Ch], 0
0x180007dd1  jz      short loc_180007DDC
0x180007dd3  lea     rax, [rbx+8]
0x180007dd7  cmp     rax, rdi
0x180007dda  jz      short loc_180007E22
0x180007ddc  mov     dword ptr [rbx+50h], 7
0x180007de3  lea     rcx, [rbx+58h]
0x180007de7  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180007dec  lea     rcx, [rbx+60h]
0x180007df0  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180007df5  lea     rcx, [rbx+68h]
0x180007df9  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180007dfe  lea     rcx, [rbx+70h]
0x180007e02  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180007e07  mov     byte ptr [rbx+4Ch], 0
0x180007e0b  mov     rdx, rdi; struct _SID *
0x180007e0e  mov     rcx, rbx; this
0x180007e11  call    ?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z; ATL::CSid::Copy(_SID const &)
0x180007e16  mov     dword ptr [rbx+50h], 8
0x180007e1d  jmp     short loc_180007E22
0x180007e1f  xor     sil, sil
0x180007e22  lea     rcx, [rbp+40h+var_38]
0x180007e26  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007e2b  mov     al, sil
0x180007e2e  jmp     short loc_180007E32
0x180007e30  xor     al, al
0x180007e32  mov     rcx, [rbp+40h+var_30]
0x180007e36  xor     rcx, rbp; StackCookie
0x180007e39  call    __security_check_cookie
0x180007e3e  lea     rsp, [rbp+20h]
0x180007e42  pop     r14
0x180007e44  pop     rdi
0x180007e45  pop     rsi
0x180007e46  pop     rbx
0x180007e47  pop     rbp
0x180007e48  retn
```
