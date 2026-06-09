# EapLm::Peer::EapMethodConfig::GetConfigBlobAndUserBlob(uint,_EapCredential,TempBuffer<0> &,TempBuffer<0> &)

- ea: `0x18001c520`
- end: `0x18001c728`
- name: `?GetConfigBlobAndUserBlob@EapMethodConfig@Peer@EapLm@@UEAAXIU_EapCredential@@AEAV?$TempBuffer@$0A@@@1@Z`
- size: `520`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800017a0`
- `0x1800126f8`
- `0x18001549c`
- `0x1800154dc`
- `0x1800177bc`
- `0x18001c520`
- `0x18002e494`
- `0x180034010`

## string_xrefs

- `0x18001c661`: `EapPeerGetConfigBlobAndUserBlob`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::EapMethodConfig::GetConfigBlobAndUserBlob(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *v9; // rax
  __int64 (__fastcall *v10)(_QWORD, _BYTE *, _OWORD *, unsigned int *, const void **, unsigned int *, const void **, struct _EAP_ERROR **); // r10
  void (__fastcall *v11)(const void *); // rdi
  void (__fastcall *v12)(struct _EAP_ERROR *); // r15
  unsigned int v13; // eax
  const wchar_t *v14; // rdx
  unsigned int v16; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v17; // [rsp+54h] [rbp-124h] BYREF
  const void *v18; // [rsp+58h] [rbp-120h] BYREF
  const void *v19; // [rsp+60h] [rbp-118h] BYREF
  struct _EAP_ERROR *v20; // [rsp+68h] [rbp-110h] BYREF
  void (__fastcall *v21)(const void *); // [rsp+70h] [rbp-108h]
  _BYTE v22[20]; // [rsp+80h] [rbp-F8h] BYREF
  int v23; // [rsp+98h] [rbp-E0h]
  _OWORD v24[2]; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-B8h]
  _BYTE v26[96]; // [rsp+D0h] [rbp-A8h] BYREF

  v20 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  if ( EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 232), 1) != 1
    || (v9 = *(_QWORD **)(a1 + 232),
        (v10 = (__int64 (__fastcall *)(_QWORD, _BYTE *, _OWORD *, unsigned int *, const void **, unsigned int *, const void **, struct _EAP_ERROR **))v9[27]) == 0) )
  {
    v22[8] = *(_BYTE *)(a1 + 16);
    *(_DWORD *)&v22[12] = *(_DWORD *)(a1 + 20);
    *(_DWORD *)&v22[16] = *(_DWORD *)(a1 + 24);
    if ( v22[8] != 0xFE )
      *(_QWORD *)&v22[12] = 0;
    *(_QWORD *)v22 = &EapHost::EapMethodType::`vftable';
    v23 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v22, 0x80420020);
  }
  v11 = (void (__fastcall *)(const void *))v9[29];
  v21 = v11;
  v12 = (void (__fastcall *)(struct _EAP_ERROR *))v9[28];
  v24[0] = *(_OWORD *)a3;
  v24[1] = *(_OWORD *)(a3 + 16);
  v25 = *(_QWORD *)(a3 + 32);
  *(_OWORD *)v22 = *(_OWORD *)(a1 + 16);
  v13 = v10(a2, v22, v24, &v16, &v18, &v17, &v19, &v20);
  if ( v13 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v26, v20, v13);
    v12(v20);
    EapHost::EapException::Throw(L"EapPeerGetConfigBlobAndUserBlob", v14, (const struct EapHost::EapError *)v26);
  }
  try
  {
    TempBuffer<0>::Assign(a4, v16, v18);
    TempBuffer<0>::Assign(a5, v17, v19);
  }
  catch ( std::bad_alloc )
  {
    v21(v18);
    v21(v19);
    throw;
  }
  TempBuffer<0>::Assign(a4, v16, v18);
  TempBuffer<0>::Assign(a5, v17, v19);
}

```

## disassembly

```asm
0x18001c520  push    rbx
0x18001c522  push    rsi
0x18001c523  push    rdi
0x18001c524  push    r12
0x18001c526  push    r13
0x18001c528  push    r14
0x18001c52a  push    r15
0x18001c52c  sub     rsp, 140h
0x18001c533  mov     rax, cs:__security_cookie
0x18001c53a  xor     rax, rsp
0x18001c53d  mov     [rsp+178h+var_48], rax
0x18001c545  mov     r14, r9
0x18001c548  mov     r12, r8
0x18001c54b  mov     r13d, edx
0x18001c54e  mov     rbx, rcx
0x18001c551  mov     rsi, [rsp+178h+arg_20]
0x18001c559  xor     edi, edi
0x18001c55b  mov     [rsp+178h+var_110], rdi
0x18001c560  mov     [rsp+178h+var_128], edi
0x18001c564  mov     [rsp+178h+var_120], rdi
0x18001c569  mov     [rsp+178h+var_124], edi
0x18001c56d  mov     [rsp+178h+var_118], rdi
0x18001c572  mov     dl, 1; bool
0x18001c574  mov     rcx, [rcx+0E8h]; this
0x18001c57b  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001c580  cmp     al, 1
0x18001c582  jnz     loc_18001C6CE
0x18001c588  mov     rax, [rbx+0E8h]
0x18001c58f  mov     r10, [rax+0D8h]
0x18001c596  test    r10, r10
0x18001c599  jz      loc_18001C6CE
0x18001c59f  mov     rdi, [rax+0E8h]
0x18001c5a6  mov     [rsp+178h+var_108], rdi
0x18001c5ab  mov     r15, [rax+0E0h]
0x18001c5b2  movups  xmm0, xmmword ptr [r12]
0x18001c5b7  movaps  [rsp+178h+var_D8], xmm0
0x18001c5bf  movups  xmm1, xmmword ptr [r12+10h]
0x18001c5c5  movaps  [rsp+178h+var_C8], xmm1
0x18001c5cd  movsd   xmm0, qword ptr [r12+20h]
0x18001c5d4  movsd   [rsp+178h+var_B8], xmm0
0x18001c5dd  movups  xmm1, xmmword ptr [rbx+10h]
0x18001c5e1  movdqu  [rsp+178h+var_F8], xmm1
0x18001c5ea  lea     rax, [rsp+178h+var_110]
0x18001c5ef  mov     [rsp+178h+var_140], rax
0x18001c5f4  lea     rax, [rsp+178h+var_118]
0x18001c5f9  mov     [rsp+178h+var_148], rax
0x18001c5fe  lea     rax, [rsp+178h+var_124]
0x18001c603  mov     [rsp+178h+var_150], rax
0x18001c608  lea     rax, [rsp+178h+var_120]
0x18001c60d  mov     [rsp+178h+var_158], rax
0x18001c612  lea     r9, [rsp+178h+var_128]
0x18001c617  lea     r8, [rsp+178h+var_D8]
0x18001c61f  lea     rdx, [rsp+178h+var_F8]
0x18001c627  mov     ecx, r13d
0x18001c62a  mov     rax, r10
0x18001c62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c632  test    eax, eax
0x18001c634  jz      short loc_18001C66E
0x18001c636  mov     r8d, eax; unsigned int
0x18001c639  mov     rdx, [rsp+178h+var_110]; struct _EAP_ERROR *
0x18001c63e  lea     rcx, [rsp+178h+var_A8]; this
0x18001c646  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001c64b  nop
0x18001c64c  mov     rcx, [rsp+178h+var_110]
0x18001c651  mov     rax, r15
0x18001c654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c659  lea     r8, [rsp+178h+var_A8]; struct EapHost::EapError *
0x18001c661  lea     rcx, aEappeergetconf; "EapPeerGetConfigBlobAndUserBlob"
0x18001c668  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001c66e  mov     edx, [rsp+178h+var_128]
0x18001c672  mov     r8, [rsp+178h+var_120]
0x18001c677  mov     rcx, r14
0x18001c67a  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001c67f  mov     edx, [rsp+178h+var_124]
0x18001c683  mov     r8, [rsp+178h+var_118]
0x18001c688  mov     rcx, rsi
0x18001c68b  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001c690  nop
0x18001c691  mov     rcx, [rsp+178h+var_120]
0x18001c696  mov     rax, rdi
0x18001c699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c69e  mov     rcx, [rsp+178h+var_118]
0x18001c6a3  mov     rax, rdi
0x18001c6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6ab  mov     rcx, [rsp+178h+var_48]
0x18001c6b3  xor     rcx, rsp; StackCookie
0x18001c6b6  call    __security_check_cookie
0x18001c6bb  add     rsp, 140h
0x18001c6c2  pop     r15
0x18001c6c4  pop     r14
0x18001c6c6  pop     r13
0x18001c6c8  pop     r12
0x18001c6ca  pop     rdi
0x18001c6cb  pop     rsi
0x18001c6cc  pop     rbx
0x18001c6cd  retn
0x18001c6ce  mov     cl, [rbx+10h]
0x18001c6d1  mov     byte ptr [rsp+178h+var_F8+8], cl
0x18001c6d8  mov     eax, [rbx+14h]
0x18001c6db  mov     dword ptr [rsp+178h+var_F8+0Ch], eax
0x18001c6e2  mov     eax, [rbx+18h]
0x18001c6e5  mov     [rsp+178h+var_E8], eax
0x18001c6ec  cmp     cl, 0FEh
0x18001c6ef  jz      short loc_18001C6F9
0x18001c6f1  mov     qword ptr [rsp+178h+var_F8+0Ch], rdi
0x18001c6f9  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001c700  mov     qword ptr [rsp+178h+var_F8], rax
0x18001c708  mov     eax, [rbx+1Ch]
0x18001c70b  mov     [rsp+178h+var_E0], eax
0x18001c712  mov     ecx, 80420020h; unsigned int
0x18001c717  mov     r8d, ecx; unsigned int
0x18001c71a  lea     rdx, [rsp+178h+var_F8]; struct EapHost::EapMethodType *
0x18001c722  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
