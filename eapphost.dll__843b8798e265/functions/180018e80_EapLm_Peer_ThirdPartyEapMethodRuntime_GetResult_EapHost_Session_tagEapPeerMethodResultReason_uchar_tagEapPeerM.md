# EapLm::Peer::ThirdPartyEapMethodRuntime::GetResult(EapHost::Session &,tagEapPeerMethodResultReason,uchar,tagEapPeerMethodResult &,EapHost::EapMethodType &)

- ea: `0x180018e80`
- end: `0x1800190c5`
- name: `?GetResult@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@W4tagEapPeerMethodResultReason@@EAEAUtagEapPeerMethodResult@@AEAVEapMethodType@5@@Z`
- size: `581`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *__hidden this, struct Session *, enum tagEapPeerMethodResultReason, unsigned __int8, struct tagEapPeerMethodResult *, struct EapHost::EapMethodType *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x1800040f4`
- `0x180004160`
- `0x18000a528`
- `0x180012704`
- `0x180012a6c`
- `0x1800155c8`
- `0x180018498`
- `0x180018e80`
- `0x18001e4ac`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019024`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019062`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::GetResult(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        struct Session *a2,
        unsigned int a3,
        unsigned __int8 a4,
        struct tagEapPeerMethodResult *a5,
        struct EapHost::EapMethodType *a6)
{
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

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_0e79d599408d37b150a6010943369b1e_Traceguids,
      *((unsigned int *)a2 + 14),
      a3,
      a4);
  }
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
          a3,
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
    Free<TaskAllocator>();
    CoTaskMemFree(v21);
  }
  if ( v22 )
  {
    Free<TaskAllocator>(v22);
    CoTaskMemFree(v22);
  }
  memset_0(v18, 0, 0x48u);
  com_ptr<_EAP_ERROR>::Clear(v17);
}

```

## disassembly

```asm
0x180018e80  mov     rax, rsp
0x180018e83  mov     [rax+8], rbx
0x180018e87  push    rbp
0x180018e88  push    rsi
0x180018e89  push    rdi
0x180018e8a  push    r14
0x180018e8c  push    r15
0x180018e8e  lea     rbp, [rsp-70h]
0x180018e93  sub     rsp, 170h
0x180018e9a  movaps  xmmword ptr [rax-38h], xmm6
0x180018e9e  movaps  xmmword ptr [rax-48h], xmm7
0x180018ea2  movaps  xmmword ptr [rax-58h], xmm8
0x180018ea7  movaps  xmmword ptr [rax-68h], xmm9
0x180018eac  movaps  xmmword ptr [rax-78h], xmm10
0x180018eb1  mov     rax, cs:__security_cookie
0x180018eb8  xor     rax, rsp
0x180018ebb  mov     [rbp+90h+var_80], rax
0x180018ebf  movzx   esi, r9b
0x180018ec3  mov     edi, r8d
0x180018ec6  mov     rbx, rdx
0x180018ec9  mov     r14, [rbp+90h+arg_20]
0x180018ed0  mov     r15, [rbp+90h+arg_28]
0x180018ed7  lea     rax, WPP_GLOBAL_Control
0x180018ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ee5  cmp     rcx, rax
0x180018ee8  jz      short loc_180018F12
0x180018eea  test    byte ptr [rcx+1Ch], 4
0x180018eee  jz      short loc_180018F12
0x180018ef0  mov     edx, 15h
0x180018ef5  mov     dword ptr [rsp+190h+var_168], esi
0x180018ef9  mov     dword ptr [rsp+190h+var_170], r8d
0x180018efe  mov     r9d, [rbx+38h]
0x180018f02  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018f09  mov     rcx, [rcx+10h]
0x180018f0d  call    WPP_SF_ddd
0x180018f12  mov     [rsp+190h+var_150], 0
0x180018f1b  mov     [rbp+90h+var_F0], 0
0x180018f1f  xor     eax, eax
0x180018f21  mov     [rbp+90h+var_EF], ax
0x180018f25  mov     [rbp+90h+var_ED], al
0x180018f28  mov     [rbp+90h+var_EC], rax
0x180018f2c  mov     [rbp+90h+var_E4], eax
0x180018f2f  xor     edx, edx; Val
0x180018f31  lea     r8d, [rax+50h]; Size
0x180018f35  lea     rcx, [rsp+190h+var_140]; void *
0x180018f3a  call    memset_0
0x180018f3f  mov     [rbp+90h+var_F8], 1
0x180018f43  mov     rcx, [rbx+50h]
0x180018f47  mov     rax, [rcx]
0x180018f4a  lea     rdx, [rsp+190h+var_150]
0x180018f4f  mov     [rsp+190h+var_160], rdx
0x180018f54  lea     rdx, [rbp+90h+var_F0]
0x180018f58  mov     [rsp+190h+var_168], rdx
0x180018f5d  lea     rdx, [rsp+190h+var_140]
0x180018f62  mov     [rsp+190h+var_170], rdx
0x180018f67  mov     r9b, sil
0x180018f6a  mov     r8d, edi
0x180018f6d  mov     edx, [rbx+40h]
0x180018f70  mov     rax, [rax+40h]
0x180018f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f79  test    eax, eax
0x180018f7b  jns     short loc_180018F99
0x180018f7d  mov     r8d, eax; unsigned int
0x180018f80  mov     rdx, [rsp+190h+var_150]; struct _EAP_ERROR *
0x180018f85  lea     rcx, [rbp+90h+var_E0]; this
0x180018f89  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180018f8e  nop
0x180018f8f  lea     rcx, [rbp+90h+var_E0]; struct EapHost::EapError *
0x180018f93  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x180018f99  lea     rdx, [rsp+190h+var_140]
0x180018f9e  lea     rcx, [rbp+90h+var_E0]; void *
0x180018fa2  call    ??0?$crt_ref@UtagEapPeerMethodResult@@@@QEAA@AEBUtagEapPeerMethodResult@@@Z; crt_ref<tagEapPeerMethodResult>::crt_ref<tagEapPeerMethodResult>(tagEapPeerMethodResult const &)
0x180018fa7  movups  xmm6, xmmword ptr [rax]
0x180018faa  movups  xmm7, xmmword ptr [rax+10h]
0x180018fae  movups  xmm8, xmmword ptr [rax+20h]
0x180018fb3  movups  xmm9, xmmword ptr [rax+30h]
0x180018fb8  movsd   xmm10, qword ptr [rax+40h]
0x180018fbe  mov     ebx, 48h ; 'H'
0x180018fc3  mov     r8d, ebx; Size
0x180018fc6  xor     edx, edx; Val
0x180018fc8  mov     rcx, rax; void *
0x180018fcb  call    memset_0
0x180018fd0  movups  xmmword ptr [r14], xmm6
0x180018fd4  movups  xmmword ptr [r14+10h], xmm7
0x180018fd9  movups  xmmword ptr [r14+20h], xmm8
0x180018fde  movups  xmmword ptr [r14+30h], xmm9
0x180018fe3  movsd   qword ptr [r14+40h], xmm10
0x180018fe9  lea     rcx, [rbp+90h+var_E0]; void *
0x180018fed  call    ??$Free@VHeapAllocator@@@@YAXAEAUtagEapPeerMethodResult@@@Z; Free<HeapAllocator>(tagEapPeerMethodResult &)
0x180018ff2  mov     al, [rbp+90h+var_F0]
0x180018ff5  mov     [r15+8], al
0x180018ff9  mov     eax, dword ptr [rbp+90h+var_EC]
0x180018ffc  mov     [r15+0Ch], eax
0x180019000  mov     eax, dword ptr [rbp+90h+var_EC+4]
0x180019003  mov     [r15+10h], eax
0x180019007  mov     eax, [rbp+90h+var_E4]
0x18001900a  mov     [r15+18h], eax
0x18001900e  mov     rcx, [rsp+190h+pv]; pv
0x180019013  call    cs:__imp_CoTaskMemFree
0x18001901a  nop     dword ptr [rax+rax+00h]
0x18001901f  mov     rcx, [rsp+190h+var_120]; pv
0x180019024  call    cs:__imp_CoTaskMemFree
0x18001902b  nop     dword ptr [rax+rax+00h]
0x180019030  mov     rcx, [rsp+190h+var_118]
0x180019035  test    rcx, rcx
0x180019038  jz      short loc_180019050
0x18001903a  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x18001903f  mov     rcx, [rsp+190h+var_118]; pv
0x180019044  call    cs:__imp_CoTaskMemFree
0x18001904b  nop     dword ptr [rax+rax+00h]
0x180019050  mov     rcx, [rbp+90h+var_110]; void *
0x180019054  test    rcx, rcx
0x180019057  jz      short loc_18001906E
0x180019059  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x18001905e  mov     rcx, [rbp+90h+var_110]; pv
0x180019062  call    cs:__imp_CoTaskMemFree
0x180019069  nop     dword ptr [rax+rax+00h]
0x18001906e  mov     r8, rbx; Size
0x180019071  xor     edx, edx; Val
0x180019073  lea     rcx, [rsp+190h+var_140]; void *
0x180019078  call    memset_0
0x18001907d  nop
0x18001907e  lea     rcx, [rsp+190h+var_150]
0x180019083  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180019088  mov     rcx, [rbp+90h+var_80]
0x18001908c  xor     rcx, rsp; StackCookie
0x18001908f  call    __security_check_cookie
0x180019094  lea     r11, [rsp+190h+var_20]
0x18001909c  mov     rbx, [r11+30h]
0x1800190a0  movaps  xmm6, xmmword ptr [r11-10h]
0x1800190a5  movaps  xmm7, xmmword ptr [r11-20h]
0x1800190aa  movaps  xmm8, xmmword ptr [r11-30h]
0x1800190af  movaps  xmm9, xmmword ptr [r11-40h]
0x1800190b4  movaps  xmm10, xmmword ptr [r11-50h]
0x1800190b9  mov     rsp, r11
0x1800190bc  pop     r15
0x1800190be  pop     r14
0x1800190c0  pop     rdi
0x1800190c1  pop     rsi
0x1800190c2  pop     rbp
0x1800190c3  retn
```
