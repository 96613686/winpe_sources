# InternetHost::QueryCustomPolicy(_GUID const &,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x1800cb440`
- end: `0x1800cb6d8`
- name: `?QueryCustomPolicy@InternetHost@@UEAAJAEBU_GUID@@PEAPEAEPEAKPEAEKK@Z`
- size: `664`
- prototype: `HRESULT __fastcall(InternetHost *this, const _GUID *guidKey, unsigned __int8 **ppPolicy, unsigned int *pcbPolicy, unsigned __int8 *pContext, unsigned int cbContext, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015a80`
- `0x180019e20`
- `0x1800c11b4`
- `0x1800c6384`
- `0x1800cb440`
- `0x1800cc6c0`
- `0x1801229dc`
- `0x180122e1c`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cb677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cb677`

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
  HostSecurityMgrWrapper *HostSecurityManager; // rax
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
0x1800cb440  push    rbp
0x1800cb442  push    rbx
0x1800cb443  push    rsi
0x1800cb444  push    rdi
0x1800cb445  push    r12
0x1800cb447  push    r13
0x1800cb449  push    r14
0x1800cb44b  push    r15
0x1800cb44d  lea     rbp, [rsp-7]
0x1800cb452  sub     rsp, 0B8h
0x1800cb459  mov     rax, cs:__security_cookie
0x1800cb460  xor     rax, rsp
0x1800cb463  mov     [rbp+3Fh+var_50], rax
0x1800cb467  mov     rbx, [rbp+3Fh+arg_20]
0x1800cb46b  xor     r15d, r15d
0x1800cb46e  mov     r13, this
0x1800cb471  mov     qword ptr [rbp+3Fh+var_80], rbx
0x1800cb475  add     this, 10h; this
0x1800cb479  mov     [rbp+3Fh+fAllow], r15b
0x1800cb47d  mov     [rbp+3Fh+pSecMgr._p], r15
0x1800cb481  mov     r14, pcbPolicy
0x1800cb484  mov     [rbp+3Fh+pHostSecMgr._p], r15
0x1800cb488  mov     r12, ppPolicy
0x1800cb48b  mov     rsi, guidKey
0x1800cb48e  mov     [rbp+3Fh+var_88], guidKey
0x1800cb492  call    ?getHostSecurityManager@SecurityInfo@@QEBAPEAUIInternetHostSecurityManager@@XZ; SecurityInfo::getHostSecurityManager(void)
0x1800cb497  mov     guidKey, rax; pref
0x1800cb49a  lea     this, [rbp+3Fh+pHostSecMgr]; ppref
0x1800cb49e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800cb4a3  mov     this, [rbp+3Fh+pHostSecMgr._p]
0x1800cb4a7  test    this, this
0x1800cb4aa  jz      short loc_1800CB4F3
0x1800cb4ac  mov     r10d, [rbp+3Fh+arg_30]
0x1800cb4b0  mov     pcbPolicy, r14
0x1800cb4b3  mov     rax, [this]
0x1800cb4b6  mov     ppPolicy, r12
0x1800cb4b9  mov     [rsp+0F0h+var_C0], r10d
0x1800cb4be  mov     guidKey, rsi
0x1800cb4c1  mov     r10d, [rbp+3Fh+arg_28]
0x1800cb4c5  mov     dword ptr [rsp+0F0h+var_C8], r10d
0x1800cb4ca  mov     rax, [rax+28h]
0x1800cb4ce  mov     [rsp+0F0h+var_D0], rbx
0x1800cb4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb4d8  mov     ebx, eax
0x1800cb4da  lea     this, [rbp+3Fh+pHostSecMgr]; ppref
0x1800cb4de  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800cb4e3  lea     this, [rbp+3Fh+pSecMgr]; ppref
0x1800cb4e7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800cb4ec  mov     eax, ebx
0x1800cb4ee  jmp     loc_1800CB6B7
0x1800cb4f3  test    r12, r12
0x1800cb4f6  jz      loc_1800CB6A0
0x1800cb4fc  test    r14, r14
0x1800cb4ff  jz      loc_1800CB6A0
0x1800cb505  mov     [r12], r15
0x1800cb509  mov     ebx, 80004005h
0x1800cb50e  mov     [r14], r15d
0x1800cb511  mov     esi, 3
0x1800cb516  mov     ecx, [r13+10h]
0x1800cb51a  test    ecx, ecx
0x1800cb51c  jz      loc_1800CB66A
0x1800cb522  cmp     ecx, 1
0x1800cb525  jnz     loc_1800CB670
0x1800cb52b  mov     rax, qword ptr [rbp+3Fh+var_80]
0x1800cb52f  lea     r15d, [rsi+1Dh]
0x1800cb533  test    rax, rax
0x1800cb536  lea     rdi, [rbp+3Fh+rgbContext]
0x1800cb53a  cmovnz  r15d, [rbp+3Fh+arg_28]
0x1800cb53f  cmovnz  rdi, rax
0x1800cb543  xor     ecx, ecx
0x1800cb545  mov     [rbp+3Fh+pSecMgr._p], this
0x1800cb549  cmp     [r13+20h], this
0x1800cb54d  jz      short loc_1800CB566
0x1800cb54f  mov     this, [r13+20h]; this
0x1800cb553  lea     guidKey, [rbp+3Fh+pSecMgr]; pptr
0x1800cb557  call    ?_getPointer@__gitpointer@@QEBAJPEAPEAUIUnknown@@@Z; __gitpointer::_getPointer(IUnknown * *)
0x1800cb55c  mov     ebx, eax
0x1800cb55e  test    eax, eax
0x1800cb560  js      short loc_1800CB59B
0x1800cb562  mov     this, [rbp+3Fh+pSecMgr._p]
0x1800cb566  mov     rax, [this]
0x1800cb569  mov     pcbPolicy, r12
0x1800cb56c  mov     guidKey, [r13+18h]
0x1800cb570  mov     r8d, [rbp+3Fh+arg_30]
0x1800cb574  mov     [rsp+0F0h+var_B8], r8d
0x1800cb579  mov     rax, [rax+40h]
0x1800cb57d  mov     guidKey, [guidKey+18h]
0x1800cb581  mov     ppPolicy, [rbp+3Fh+var_88]
0x1800cb585  mov     [rsp+0F0h+var_C0], r15d
0x1800cb58a  mov     [rsp+0F0h+var_C8], rdi
0x1800cb58f  mov     [rsp+0F0h+var_D0], r14
0x1800cb594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb599  mov     ebx, eax
0x1800cb59b  cmp     ebx, 800C0011h
0x1800cb5a1  jz      short loc_1800CB5AF
0x1800cb5a3  cmp     ebx, 80070490h
0x1800cb5a9  jnz     $Cleanup_7
0x1800cb5af  mov     this, [rbp+3Fh+var_88]
0x1800cb5b3  mov     rax, [this]
0x1800cb5b6  sub     rax, qword ptr cs:GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data1
0x1800cb5bd  jnz     short loc_1800CB5CA
0x1800cb5bf  mov     rax, [this+8]
0x1800cb5c3  sub     rax, qword ptr cs:GUID_CUSTOM_CONFIRMOBJECTSAFETY.Data4
0x1800cb5ca  test    rax, rax
0x1800cb5cd  jnz     loc_1800CB670
0x1800cb5d3  cmp     r15d, 20h ; ' '
0x1800cb5d7  jz      short loc_1800CB5E3
0x1800cb5d9  mov     ebx, 80070057h
0x1800cb5de  jmp     $Cleanup_7
0x1800cb5e3  xor     r15d, r15d
0x1800cb5e6  cmp     [rdi+10h], r15
0x1800cb5ea  jz      $Cleanup_7
0x1800cb5f0  lea     ppPolicy, [rbp+3Fh+fAllow]; pfAllow
0x1800cb5f4  mov     edx, 1203h; dwAction
0x1800cb5f9  mov     this, r13; this
0x1800cb5fc  call    ?IsAllowableAction@InternetHost@@IEAAJKPEA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x1800cb601  mov     ebx, eax
0x1800cb603  test    eax, eax
0x1800cb605  js      $Cleanup_7
0x1800cb60b  cmp     [rbp+3Fh+fAllow], r15b
0x1800cb60f  jnz     short loc_1800CB66A
0x1800cb611  cmp     [rdi+18h], r15d
0x1800cb615  jz      short loc_1800CB640
0x1800cb617  cmp     dword ptr [rdi+18h], 1
0x1800cb61b  jnz     short loc_1800CB66D
0x1800cb61d  movups  xmm0, xmmword ptr [rdi]
0x1800cb620  mov     rax, [rdi+10h]
0x1800cb624  lea     pcbPolicy, [rbp+3Fh+var_80]
0x1800cb628  xor     edx, edx
0x1800cb62a  mov     [rsp+0F0h+var_D0], rax
0x1800cb62f  mov     this, r13
0x1800cb632  movdqu  [rbp+3Fh+var_80], xmm0
0x1800cb637  call    ?CheckSafety@InternetHost@@IEAA_NW4SAFETYOPERATION@@AEBU_GUID@@U3@PEAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1800cb63c  test    al, al
0x1800cb63e  jz      short loc_1800CB66D
0x1800cb640  movups  xmm0, xmmword ptr [rdi]
0x1800cb643  mov     rax, [rdi+10h]
0x1800cb647  lea     pcbPolicy, [rbp+3Fh+var_80]
0x1800cb64b  mov     edx, 1
0x1800cb650  mov     [rsp+0F0h+var_D0], rax
0x1800cb655  mov     this, r13
0x1800cb658  movdqu  [rbp+3Fh+var_80], xmm0
0x1800cb65d  call    ?CheckSafety@InternetHost@@IEAA_NW4SAFETYOPERATION@@AEBU_GUID@@U3@PEAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1800cb662  test    al, al
0x1800cb664  cmovnz  esi, r15d
0x1800cb668  jmp     short loc_1800CB66D
0x1800cb66a  mov     esi, r15d
0x1800cb66d  mov     ebx, r15d
0x1800cb670  mov     edi, 4
0x1800cb675  mov     ecx, edi; cb
0x1800cb677  call    cs:__imp_CoTaskMemAlloc
0x1800cb67e  nop     dword ptr [rax+rax+00h]
0x1800cb683  mov     [r12], rax
0x1800cb687  test    rax, rax
0x1800cb68a  jz      short loc_1800CB696
0x1800cb68c  mov     [rax], esi
0x1800cb68e  mov     [r14], edi
0x1800cb691  jmp     $Cleanup_7
0x1800cb696  mov     ebx, 8007000Eh
0x1800cb69b  jmp     $Cleanup_7
0x1800cb6a0  lea     this, [rbp+3Fh+pHostSecMgr]; ppref
0x1800cb6a4  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800cb6a9  lea     this, [rbp+3Fh+pSecMgr]; ppref
0x1800cb6ad  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800cb6b2  mov     eax, 80004003h
0x1800cb6b7  mov     this, [rbp+3Fh+var_50]
0x1800cb6bb  xor     this, rsp; StackCookie
0x1800cb6be  call    __security_check_cookie
0x1800cb6c3  add     rsp, 0B8h
0x1800cb6ca  pop     r15
0x1800cb6cc  pop     r14
0x1800cb6ce  pop     r13
0x1800cb6d0  pop     r12
0x1800cb6d2  pop     rdi
0x1800cb6d3  pop     rsi
0x1800cb6d4  pop     rbx
0x1800cb6d5  pop     rbp
0x1800cb6d6  retn
```
