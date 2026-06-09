# EapLm::Peer::ThirdPartyEapMethodRuntime::GetResult(EapHost::Session &,tagEapPeerMethodResultReason,uchar,tagEapPeerMethodResult &,EapHost::EapMethodType &)

- ea: `0x180028c90`
- end: `0x180028eb0`
- name: `?GetResult@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@W4tagEapPeerMethodResultReason@@EAEAUtagEapPeerMethodResult@@AEAVEapMethodType@5@@Z`
- size: `544`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *__hidden this, struct Session *, enum tagEapPeerMethodResultReason, unsigned __int8, struct tagEapPeerMethodResult *, struct EapHost::EapMethodType *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x18001330c`
- `0x180013dbc`
- `0x1800151ec`
- `0x180016604`
- `0x1800177bc`
- `0x180022d28`
- `0x180022d8c`
- `0x180027ce4`
- `0x180028c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e54`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::GetResult(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        struct Session *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct tagEapPeerMethodResult *a5,
        struct EapHost::EapMethodType *a6)
{
  unsigned int v7; // edi
  __int64 v9; // r9
  signed int v10; // eax
  _OWORD *v11; // rax
  __int128 v12; // xmm6
  __int128 v13; // xmm7
  __int128 v14; // xmm8
  __int128 v15; // xmm9
  __int64 v16; // xmm10_8
  struct _EAP_ERROR *v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[16]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h]
  LPVOID v20; // [rsp+70h] [rbp-90h]
  LPVOID v21; // [rsp+78h] [rbp-88h]
  LPVOID v22; // [rsp+80h] [rbp-80h]
  char v23; // [rsp+98h] [rbp-68h]
  char v24; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v25; // [rsp+A1h] [rbp-5Fh]
  char v26; // [rsp+A3h] [rbp-5Dh]
  __int64 v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+ACh] [rbp-54h]
  _BYTE v29[96]; // [rsp+B0h] [rbp-50h] BYREF

  v7 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((unsigned int *)a2 + 14), a3, a4);
  v17[0] = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v18, 0, 0x50u);
  v23 = 1;
  LOBYTE(v9) = a4;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _BYTE *, char *, struct _EAP_ERROR **))(**((_QWORD **)a2 + 10) + 64LL))(
          *((_QWORD *)a2 + 10),
          *((unsigned int *)a2 + 16),
          v7,
          v9,
          v18,
          &v24,
          v17);
  if ( v10 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v29, v17[0], v10);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v29);
  }
  v11 = (_OWORD *)crt_ref<tagEapPeerMethodResult>::crt_ref<tagEapPeerMethodResult>(v29);
  v12 = *v11;
  v13 = v11[1];
  v14 = v11[2];
  v15 = v11[3];
  v16 = *((_QWORD *)v11 + 8);
  memset_0(v11, 0, 0x48u);
  *(_OWORD *)&a5->fIsSuccess = v12;
  *(_OWORD *)&a5->pConnectionData = v13;
  *(_OWORD *)&a5->pUserData = v14;
  *(_OWORD *)&a5->pEapError = v15;
  *(_QWORD *)&a5->fSaveToCredMan = v16;
  Free<HeapAllocator>(v29);
  *((_BYTE *)a6 + 8) = v24;
  *(_QWORD *)((char *)a6 + 12) = v27;
  *((_DWORD *)a6 + 6) = v28;
  CoTaskMemFree(pv);
  CoTaskMemFree(v20);
  if ( v21 )
  {
    Free<TaskAllocator>((unsigned int *)v21);
    CoTaskMemFree(v21);
  }
  if ( v22 )
  {
    Free<TaskAllocator>((LPVOID *)v22);
    CoTaskMemFree(v22);
  }
  memset_0(v18, 0, 0x48u);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)v17);
}

```

## disassembly

```asm
0x180028c90  mov     rax, rsp
0x180028c93  mov     [rax+8], rbx
0x180028c97  push    rbp
0x180028c98  push    rsi
0x180028c99  push    rdi
0x180028c9a  push    r14
0x180028c9c  push    r15
0x180028c9e  lea     rbp, [rsp-70h]
0x180028ca3  sub     rsp, 170h
0x180028caa  movaps  xmmword ptr [rax-38h], xmm6
0x180028cae  movaps  xmmword ptr [rax-48h], xmm7
0x180028cb2  movaps  xmmword ptr [rax-58h], xmm8
0x180028cb7  movaps  xmmword ptr [rax-68h], xmm9
0x180028cbc  movaps  xmmword ptr [rax-78h], xmm10
0x180028cc1  mov     rax, cs:__security_cookie
0x180028cc8  xor     rax, rsp
0x180028ccb  mov     [rbp+90h+var_80], rax
0x180028ccf  movzx   esi, r9b
0x180028cd3  mov     edi, r8d
0x180028cd6  mov     rbx, rdx
0x180028cd9  mov     r14, [rbp+90h+arg_20]
0x180028ce0  mov     r15, [rbp+90h+arg_28]
0x180028ce7  lea     rax, WPP_GLOBAL_Control
0x180028cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cf5  cmp     rcx, rax
0x180028cf8  jz      short loc_180028D16
0x180028cfa  test    byte ptr [rcx+1Ch], 4
0x180028cfe  jz      short loc_180028D16
0x180028d00  mov     dword ptr [rsp+190h+var_168], esi
0x180028d04  mov     dword ptr [rsp+190h+var_170], r8d
0x180028d09  mov     r9d, [rdx+38h]
0x180028d0d  mov     rcx, [rcx+10h]
0x180028d11  call    WPP_SF_ddd
0x180028d16  mov     [rsp+190h+var_150], 0
0x180028d1f  mov     [rbp+90h+var_F0], 0
0x180028d23  xor     eax, eax
0x180028d25  mov     [rbp+90h+var_EF], ax
0x180028d29  mov     [rbp+90h+var_ED], al
0x180028d2c  mov     [rbp+90h+var_EC], rax
0x180028d30  mov     [rbp+90h+var_E4], eax
0x180028d33  xor     edx, edx; Val
0x180028d35  lea     r8d, [rax+50h]; Size
0x180028d39  lea     rcx, [rsp+190h+var_140]; void *
0x180028d3e  call    memset_0
0x180028d43  mov     [rbp+90h+var_F8], 1
0x180028d47  mov     rcx, [rbx+50h]
0x180028d4b  mov     rax, [rcx]
0x180028d4e  lea     rdx, [rsp+190h+var_150]
0x180028d53  mov     [rsp+190h+var_160], rdx
0x180028d58  lea     rdx, [rbp+90h+var_F0]
0x180028d5c  mov     [rsp+190h+var_168], rdx
0x180028d61  lea     rdx, [rsp+190h+var_140]
0x180028d66  mov     [rsp+190h+var_170], rdx
0x180028d6b  mov     r9b, sil
0x180028d6e  mov     r8d, edi
0x180028d71  mov     edx, [rbx+40h]
0x180028d74  mov     rax, [rax+40h]
0x180028d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d7d  test    eax, eax
0x180028d7f  jns     short loc_180028D9D
0x180028d81  mov     r8d, eax; unsigned int
0x180028d84  mov     rdx, [rsp+190h+var_150]; struct _EAP_ERROR *
0x180028d89  lea     rcx, [rbp+90h+var_E0]; this
0x180028d8d  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180028d92  nop
0x180028d93  lea     rcx, [rbp+90h+var_E0]; struct EapHost::EapError *
0x180028d97  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x180028d9d  lea     rdx, [rsp+190h+var_140]
0x180028da2  lea     rcx, [rbp+90h+var_E0]; void *
0x180028da6  call    ??0?$crt_ref@UtagEapPeerMethodResult@@@@QEAA@AEBUtagEapPeerMethodResult@@@Z; crt_ref<tagEapPeerMethodResult>::crt_ref<tagEapPeerMethodResult>(tagEapPeerMethodResult const &)
0x180028dab  movups  xmm6, xmmword ptr [rax]
0x180028dae  movups  xmm7, xmmword ptr [rax+10h]
0x180028db2  movups  xmm8, xmmword ptr [rax+20h]
0x180028db7  movups  xmm9, xmmword ptr [rax+30h]
0x180028dbc  movsd   xmm10, qword ptr [rax+40h]
0x180028dc2  mov     ebx, 48h ; 'H'
0x180028dc7  mov     r8d, ebx; Size
0x180028dca  xor     edx, edx; Val
0x180028dcc  mov     rcx, rax; void *
0x180028dcf  call    memset_0
0x180028dd4  movups  xmmword ptr [r14], xmm6
0x180028dd8  movups  xmmword ptr [r14+10h], xmm7
0x180028ddd  movups  xmmword ptr [r14+20h], xmm8
0x180028de2  movups  xmmword ptr [r14+30h], xmm9
0x180028de7  movsd   qword ptr [r14+40h], xmm10
0x180028ded  lea     rcx, [rbp+90h+var_E0]; void *
0x180028df1  call    ??$Free@VHeapAllocator@@@@YAXAEAUtagEapPeerMethodResult@@@Z; Free<HeapAllocator>(tagEapPeerMethodResult &)
0x180028df6  mov     al, [rbp+90h+var_F0]
0x180028df9  mov     [r15+8], al
0x180028dfd  mov     eax, dword ptr [rbp+90h+var_EC]
0x180028e00  mov     [r15+0Ch], eax
0x180028e04  mov     eax, dword ptr [rbp+90h+var_EC+4]
0x180028e07  mov     [r15+10h], eax
0x180028e0b  mov     eax, [rbp+90h+var_E4]
0x180028e0e  mov     [r15+18h], eax
0x180028e12  mov     rcx, [rsp+190h+pv]; pv
0x180028e17  call    cs:__imp_CoTaskMemFree
0x180028e1d  mov     rcx, [rsp+190h+var_120]; pv
0x180028e22  call    cs:__imp_CoTaskMemFree
0x180028e28  mov     rcx, [rsp+190h+var_118]
0x180028e2d  test    rcx, rcx
0x180028e30  jz      short loc_180028E42
0x180028e32  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x180028e37  mov     rcx, [rsp+190h+var_118]; pv
0x180028e3c  call    cs:__imp_CoTaskMemFree
0x180028e42  mov     rcx, [rbp+90h+var_110]; void *
0x180028e46  test    rcx, rcx
0x180028e49  jz      short loc_180028E5A
0x180028e4b  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180028e50  mov     rcx, [rbp+90h+var_110]; pv
0x180028e54  call    cs:__imp_CoTaskMemFree
0x180028e5a  mov     r8, rbx; Size
0x180028e5d  xor     edx, edx; Val
0x180028e5f  lea     rcx, [rsp+190h+var_140]; void *
0x180028e64  call    memset_0
0x180028e69  nop
0x180028e6a  lea     rcx, [rsp+190h+var_150]
0x180028e6f  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180028e74  mov     rcx, [rbp+90h+var_80]
0x180028e78  xor     rcx, rsp; StackCookie
0x180028e7b  call    __security_check_cookie
0x180028e80  lea     r11, [rsp+190h+var_20]
0x180028e88  mov     rbx, [r11+30h]
0x180028e8c  movaps  xmm6, xmmword ptr [r11-10h]
0x180028e91  movaps  xmm7, xmmword ptr [r11-20h]
0x180028e96  movaps  xmm8, xmmword ptr [r11-30h]
0x180028e9b  movaps  xmm9, xmmword ptr [r11-40h]
0x180028ea0  movaps  xmm10, xmmword ptr [r11-50h]
0x180028ea5  mov     rsp, r11
0x180028ea8  pop     r15
0x180028eaa  pop     r14
0x180028eac  pop     rdi
0x180028ead  pop     rsi
0x180028eae  pop     rbp
0x180028eaf  retn
```
