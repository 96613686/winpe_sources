# InternetHost::QueryCustomPolicy(_GUID const &,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x1800c9b40`
- end: `0x1800c9dd1`
- name: `?QueryCustomPolicy@InternetHost@@UEAAJAEBU_GUID@@PEAPEAEPEAKPEAEKK@Z`
- size: `657`
- prototype: `__int64 __fastcall(InternetHost *this, const _GUID *guidKey, unsigned __int8 **ppPolicy, unsigned int *pcbPolicy, unsigned __int8 *pContext, unsigned int cbContext, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009490`
- `0x18000d7d0`
- `0x1800bfa7c`
- `0x1800c4bd4`
- `0x1800c9b40`
- `0x1800cada0`
- `0x18011ff54`
- `0x18012037c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c9d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c9d77`

## pseudocode

```c
__int64 __fastcall InternetHost::QueryCustomPolicy(
        InternetHost *this,
        const _GUID *guidKey,
        unsigned __int8 **ppPolicy,
        unsigned int *pcbPolicy,
        unsigned __int8 *pContext,
        unsigned int cbContext,
        unsigned int dwReserved)
{
  IInternetHostSecurityManager *HostSecurityManager; // rax
  int Pointer; // ebx
  int v14; // esi
  SecurityInfo::SecurityEnum securitySetting; // ecx
  unsigned int v16; // r15d
  unsigned __int8 *v17; // rdi
  IInternetSecurityManager *p; // rcx
  __int64 v19; // rax
  const _GUID *v20; // r8
  unsigned __int8 *v21; // rax
  IUnknown *v22; // [rsp+20h] [rbp-91h]
  IUnknown *v23; // [rsp+20h] [rbp-91h]
  bool fAllow; // [rsp+50h] [rbp-61h] BYREF
  _reference<IInternetSecurityManager> pSecMgr; // [rsp+58h] [rbp-59h] BYREF
  _reference<IInternetHostSecurityManager> pHostSecMgr; // [rsp+60h] [rbp-51h] BYREF
  const _GUID *v27; // [rsp+68h] [rbp-49h]
  _GUID v28; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int8 rgbContext[32]; // [rsp+80h] [rbp-31h] BYREF

  *(_QWORD *)&v28.Data1 = pContext;
  fAllow = 0;
  pSecMgr._p = 0;
  pHostSecMgr._p = 0;
  v27 = guidKey;
  HostSecurityManager = SecurityInfo::getHostSecurityManager(&this->SecurityInfo);
  assign(&pHostSecMgr._p, HostSecurityManager);
  if ( pHostSecMgr._p )
  {
    Pointer = pHostSecMgr._p->QueryCustomPolicy(
                pHostSecMgr._p,
                guidKey,
                ppPolicy,
                pcbPolicy,
                pContext,
                cbContext,
                dwReserved);
$Cleanup_7:
    release(&pHostSecMgr._p);
    release(&pSecMgr._p);
    return (unsigned int)Pointer;
  }
  if ( ppPolicy && pcbPolicy )
  {
    *ppPolicy = 0;
    Pointer = -2147467259;
    *pcbPolicy = 0;
    v14 = 3;
    securitySetting = this->_securitySetting;
    if ( securitySetting == AllowAll )
      goto LABEL_30;
    if ( securitySetting != CheckSecurity )
      goto LABEL_32;
    v16 = 32;
    v17 = rgbContext;
    if ( *(_QWORD *)&v28.Data1 )
    {
      v16 = cbContext;
      v17 = *(unsigned __int8 **)&v28.Data1;
    }
    p = 0;
    pSecMgr._p = 0;
    if ( this->_pISecMgr._pPointer )
    {
      Pointer = __gitpointer::_getPointer(this->_pISecMgr._pPointer, &pSecMgr._p);
      if ( Pointer < 0 )
      {
LABEL_14:
        if ( Pointer != -2146697199 && Pointer != -2147023728 )
          goto $Cleanup_7;
        v19 = *(_QWORD *)&v27->Data1 - *(_QWORD *)&GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data1;
        if ( *(_QWORD *)&v27->Data1 == *(_QWORD *)&GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data1 )
          v19 = *(_QWORD *)v27->Data4 - *(_QWORD *)GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data4;
        if ( v19 )
          goto LABEL_32;
        if ( v16 != 32 )
        {
          Pointer = -2147024809;
          goto $Cleanup_7;
        }
        if ( !*((_QWORD *)v17 + 2) )
          goto $Cleanup_7;
        Pointer = InternetHost::IsAllowableAction(this, 0x1203u, &fAllow);
        if ( Pointer < 0 )
          goto $Cleanup_7;
        if ( !fAllow )
        {
          if ( !*((_DWORD *)v17 + 6)
            || *((_DWORD *)v17 + 6) == 1
            && (v22 = (IUnknown *)*((_QWORD *)v17 + 2),
                v28 = *(_GUID *)v17,
                InternetHost::CheckSafety(this, SAFETY_INIT, v20, &v28, v22)) )
          {
            v23 = (IUnknown *)*((_QWORD *)v17 + 2);
            v28 = *(_GUID *)v17;
            if ( InternetHost::CheckSafety(this, SAFETY_SCRIPT, v20, &v28, v23) )
              v14 = 0;
          }
          goto LABEL_31;
        }
LABEL_30:
        v14 = 0;
LABEL_31:
        Pointer = 0;
LABEL_32:
        v21 = (unsigned __int8 *)CoTaskMemAlloc(4u);
        *ppPolicy = v21;
        if ( v21 )
        {
          *(_DWORD *)v21 = v14;
          *pcbPolicy = 4;
        }
        else
        {
          Pointer = -2147024882;
        }
        goto $Cleanup_7;
      }
      p = pSecMgr._p;
    }
    Pointer = p->QueryCustomPolicy(p, this->_sSecureBaseURL._p->_pwsz, v27, ppPolicy, pcbPolicy, v17, v16, dwReserved);
    goto LABEL_14;
  }
  release(&pHostSecMgr._p);
  release(&pSecMgr._p);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800c9b40  push    rbp
0x1800c9b42  push    rbx
0x1800c9b43  push    rsi
0x1800c9b44  push    rdi
0x1800c9b45  push    r12
0x1800c9b47  push    r13
0x1800c9b49  push    r14
0x1800c9b4b  push    r15
0x1800c9b4d  lea     rbp, [rsp-7]
0x1800c9b52  sub     rsp, 0B8h
0x1800c9b59  mov     rax, cs:__security_cookie
0x1800c9b60  xor     rax, rsp
0x1800c9b63  mov     [rbp+3Fh+var_50], rax
0x1800c9b67  mov     rbx, [rbp+3Fh+arg_20]
0x1800c9b6b  xor     r15d, r15d
0x1800c9b6e  mov     r13, this
0x1800c9b71  mov     qword ptr [rbp+3Fh+var_80], rbx
0x1800c9b75  add     this, 10h; this
0x1800c9b79  mov     [rbp+3Fh+fAllow], r15b
0x1800c9b7d  mov     [rbp+3Fh+pSecMgr._p], r15
0x1800c9b81  mov     r14, pcbPolicy
0x1800c9b84  mov     [rbp+3Fh+pHostSecMgr._p], r15
0x1800c9b88  mov     r12, ppPolicy
0x1800c9b8b  mov     rsi, guidKey
0x1800c9b8e  mov     [rbp+3Fh+var_88], guidKey
0x1800c9b92  call    ?getHostSecurityManager@SecurityInfo@@QEBAPEAUIInternetHostSecurityManager@@XZ; SecurityInfo::getHostSecurityManager(void)
0x1800c9b97  mov     guidKey, rax; pref
0x1800c9b9a  lea     this, [rbp+3Fh+pHostSecMgr]; ppref
0x1800c9b9e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800c9ba3  mov     this, [rbp+3Fh+pHostSecMgr._p]
0x1800c9ba7  test    this, this
0x1800c9baa  jz      short loc_1800C9BF3
0x1800c9bac  mov     r10d, [rbp+3Fh+arg_30]
0x1800c9bb0  mov     pcbPolicy, r14
0x1800c9bb3  mov     rax, [this]
0x1800c9bb6  mov     ppPolicy, r12
0x1800c9bb9  mov     [rsp+0F0h+var_C0], r10d
0x1800c9bbe  mov     guidKey, rsi
0x1800c9bc1  mov     r10d, [rbp+3Fh+arg_28]
0x1800c9bc5  mov     dword ptr [rsp+0F0h+var_C8], r10d
0x1800c9bca  mov     rax, [rax+28h]
0x1800c9bce  mov     [rsp+0F0h+var_D0], rbx
0x1800c9bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9bd8  mov     ebx, eax
0x1800c9bda  lea     this, [rbp+3Fh+pHostSecMgr]; ppref
0x1800c9bde  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800c9be3  lea     this, [rbp+3Fh+pSecMgr]; ppref
0x1800c9be7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800c9bec  mov     eax, ebx
0x1800c9bee  jmp     loc_1800C9DB1
0x1800c9bf3  test    r12, r12
0x1800c9bf6  jz      loc_1800C9D9A
0x1800c9bfc  test    r14, r14
0x1800c9bff  jz      loc_1800C9D9A
0x1800c9c05  mov     [r12], r15
0x1800c9c09  mov     ebx, 80004005h
0x1800c9c0e  mov     [r14], r15d
0x1800c9c11  mov     esi, 3
0x1800c9c16  mov     ecx, [r13+10h]
0x1800c9c1a  test    ecx, ecx
0x1800c9c1c  jz      loc_1800C9D6A
0x1800c9c22  cmp     ecx, 1
0x1800c9c25  jnz     loc_1800C9D70
0x1800c9c2b  mov     rax, qword ptr [rbp+3Fh+var_80]
0x1800c9c2f  lea     r15d, [rsi+1Dh]
0x1800c9c33  test    rax, rax
0x1800c9c36  lea     rdi, [rbp+3Fh+rgbContext]
0x1800c9c3a  cmovnz  r15d, [rbp+3Fh+arg_28]
0x1800c9c3f  cmovnz  rdi, rax
0x1800c9c43  xor     ecx, ecx
0x1800c9c45  mov     [rbp+3Fh+pSecMgr._p], this
0x1800c9c49  cmp     [r13+20h], this
0x1800c9c4d  jz      short loc_1800C9C66
0x1800c9c4f  mov     this, [r13+20h]; this
0x1800c9c53  lea     guidKey, [rbp+3Fh+pSecMgr]; pptr
0x1800c9c57  call    ?_getPointer@__gitpointer@@QEBAJPEAPEAUIUnknown@@@Z; __gitpointer::_getPointer(IUnknown * *)
0x1800c9c5c  mov     ebx, eax
0x1800c9c5e  test    eax, eax
0x1800c9c60  js      short loc_1800C9C9B
0x1800c9c62  mov     this, [rbp+3Fh+pSecMgr._p]
0x1800c9c66  mov     rax, [this]
0x1800c9c69  mov     pcbPolicy, r12
0x1800c9c6c  mov     guidKey, [r13+18h]
0x1800c9c70  mov     r8d, [rbp+3Fh+arg_30]
0x1800c9c74  mov     [rsp+0F0h+var_B8], r8d
0x1800c9c79  mov     rax, [rax+40h]
0x1800c9c7d  mov     guidKey, [guidKey+18h]
0x1800c9c81  mov     ppPolicy, [rbp+3Fh+var_88]
0x1800c9c85  mov     [rsp+0F0h+var_C0], r15d
0x1800c9c8a  mov     [rsp+0F0h+var_C8], rdi
0x1800c9c8f  mov     [rsp+0F0h+var_D0], r14
0x1800c9c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9c99  mov     ebx, eax
0x1800c9c9b  cmp     ebx, 800C0011h
0x1800c9ca1  jz      short loc_1800C9CAF
0x1800c9ca3  cmp     ebx, 80070490h
0x1800c9ca9  jnz     $Cleanup_7
0x1800c9caf  mov     this, [rbp+3Fh+var_88]
0x1800c9cb3  mov     rax, [this]
0x1800c9cb6  sub     rax, qword ptr cs:GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data1
0x1800c9cbd  jnz     short loc_1800C9CCA
0x1800c9cbf  mov     rax, [this+8]
0x1800c9cc3  sub     rax, qword ptr cs:GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data4
0x1800c9cca  test    rax, rax
0x1800c9ccd  jnz     loc_1800C9D70
0x1800c9cd3  cmp     r15d, 20h ; ' '
0x1800c9cd7  jz      short loc_1800C9CE3
0x1800c9cd9  mov     ebx, 80070057h
0x1800c9cde  jmp     $Cleanup_7
0x1800c9ce3  xor     r15d, r15d
0x1800c9ce6  cmp     [rdi+10h], r15
0x1800c9cea  jz      $Cleanup_7
0x1800c9cf0  lea     ppPolicy, [rbp+3Fh+fAllow]; pfAllow
0x1800c9cf4  mov     edx, 1203h; dwAction
0x1800c9cf9  mov     this, r13; this
0x1800c9cfc  call    ?IsAllowableAction@InternetHost@@IEAAJKPEA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x1800c9d01  mov     ebx, eax
0x1800c9d03  test    eax, eax
0x1800c9d05  js      $Cleanup_7
0x1800c9d0b  cmp     [rbp+3Fh+fAllow], r15b
0x1800c9d0f  jnz     short loc_1800C9D6A
0x1800c9d11  cmp     [rdi+18h], r15d
0x1800c9d15  jz      short loc_1800C9D40
0x1800c9d17  cmp     dword ptr [rdi+18h], 1
0x1800c9d1b  jnz     short loc_1800C9D6D
0x1800c9d1d  movups  xmm0, xmmword ptr [rdi]
0x1800c9d20  mov     rax, [rdi+10h]
0x1800c9d24  lea     pcbPolicy, [rbp+3Fh+var_80]
0x1800c9d28  xor     edx, edx
0x1800c9d2a  mov     [rsp+0F0h+var_D0], rax
0x1800c9d2f  mov     this, r13
0x1800c9d32  movdqu  [rbp+3Fh+var_80], xmm0
0x1800c9d37  call    ?CheckSafety@InternetHost@@IEAA_NW4SAFETYOPERATION@@AEBU_GUID@@U3@PEAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1800c9d3c  test    al, al
0x1800c9d3e  jz      short loc_1800C9D6D
0x1800c9d40  movups  xmm0, xmmword ptr [rdi]
0x1800c9d43  mov     rax, [rdi+10h]
0x1800c9d47  lea     pcbPolicy, [rbp+3Fh+var_80]
0x1800c9d4b  mov     edx, 1
0x1800c9d50  mov     [rsp+0F0h+var_D0], rax
0x1800c9d55  mov     this, r13
0x1800c9d58  movdqu  [rbp+3Fh+var_80], xmm0
0x1800c9d5d  call    ?CheckSafety@InternetHost@@IEAA_NW4SAFETYOPERATION@@AEBU_GUID@@U3@PEAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1800c9d62  test    al, al
0x1800c9d64  cmovnz  esi, r15d
0x1800c9d68  jmp     short loc_1800C9D6D
0x1800c9d6a  mov     esi, r15d
0x1800c9d6d  mov     ebx, r15d
0x1800c9d70  mov     edi, 4
0x1800c9d75  mov     ecx, edi; cb
0x1800c9d77  call    cs:__imp_CoTaskMemAlloc
0x1800c9d7d  mov     [r12], rax
0x1800c9d81  test    rax, rax
0x1800c9d84  jz      short loc_1800C9D90
0x1800c9d86  mov     [rax], esi
0x1800c9d88  mov     [r14], edi
0x1800c9d8b  jmp     $Cleanup_7
0x1800c9d90  mov     ebx, 8007000Eh
0x1800c9d95  jmp     $Cleanup_7
0x1800c9d9a  lea     this, [rbp+3Fh+pHostSecMgr]; ppref
0x1800c9d9e  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800c9da3  lea     this, [rbp+3Fh+pSecMgr]; ppref
0x1800c9da7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800c9dac  mov     eax, 80004003h
0x1800c9db1  mov     this, [rbp+3Fh+var_50]
0x1800c9db5  xor     this, rsp; StackCookie
0x1800c9db8  call    __security_check_cookie
0x1800c9dbd  add     rsp, 0B8h
0x1800c9dc4  pop     r15
0x1800c9dc6  pop     r14
0x1800c9dc8  pop     r13
0x1800c9dca  pop     r12
0x1800c9dcc  pop     rdi
0x1800c9dcd  pop     rsi
0x1800c9dce  pop     rbx
0x1800c9dcf  pop     rbp
0x1800c9dd0  retn
```
