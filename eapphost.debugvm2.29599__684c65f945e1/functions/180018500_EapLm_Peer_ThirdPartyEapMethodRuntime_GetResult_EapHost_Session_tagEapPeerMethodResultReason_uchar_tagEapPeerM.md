# EapLm::Peer::ThirdPartyEapMethodRuntime::GetResult(EapHost::Session &,tagEapPeerMethodResultReason,uchar,tagEapPeerMethodResult &,EapHost::EapMethodType &)

- ea: `0x180018500`
- end: `0x18001872c`
- name: `?GetResult@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@W4tagEapPeerMethodResultReason@@EAEAUtagEapPeerMethodResult@@AEAVEapMethodType@5@@Z`
- size: `556`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *__hidden this, struct Session *, enum tagEapPeerMethodResultReason, unsigned __int8, struct tagEapPeerMethodResult *, struct EapHost::EapMethodType *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x180003fec`
- `0x18000404c`
- `0x18000a09c`
- `0x180011f8c`
- `0x1800122ec`
- `0x180014d8c`
- `0x180017b78`
- `0x180018500`
- `0x18001d9bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001869e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800186b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800186d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001869e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800186b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800186d0`

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
0x180018500  mov     rax, rsp
0x180018503  mov     [rax+8], rbx
0x180018507  push    rbp
0x180018508  push    rsi
0x180018509  push    rdi
0x18001850a  push    r14
0x18001850c  push    r15
0x18001850e  lea     rbp, [rsp-70h]
0x180018513  sub     rsp, 170h
0x18001851a  movaps  xmmword ptr [rax-38h], xmm6
0x18001851e  movaps  xmmword ptr [rax-48h], xmm7
0x180018522  movaps  xmmword ptr [rax-58h], xmm8
0x180018527  movaps  xmmword ptr [rax-68h], xmm9
0x18001852c  movaps  xmmword ptr [rax-78h], xmm10
0x180018531  mov     rax, cs:__security_cookie
0x180018538  xor     rax, rsp
0x18001853b  mov     [rbp+90h+var_80], rax
0x18001853f  movzx   esi, r9b
0x180018543  mov     edi, r8d
0x180018546  mov     rbx, rdx
0x180018549  mov     r14, [rbp+90h+arg_20]
0x180018550  mov     r15, [rbp+90h+arg_28]
0x180018557  lea     rax, WPP_GLOBAL_Control
0x18001855e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018565  cmp     rcx, rax
0x180018568  jz      short loc_180018592
0x18001856a  test    byte ptr [rcx+1Ch], 4
0x18001856e  jz      short loc_180018592
0x180018570  mov     edx, 15h
0x180018575  mov     dword ptr [rsp+190h+var_168], esi
0x180018579  mov     dword ptr [rsp+190h+var_170], r8d
0x18001857e  mov     r9d, [rbx+38h]
0x180018582  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018589  mov     rcx, [rcx+10h]
0x18001858d  call    WPP_SF_ddd
0x180018592  mov     [rsp+190h+var_150], 0
0x18001859b  mov     [rbp+90h+var_F0], 0
0x18001859f  xor     eax, eax
0x1800185a1  mov     [rbp+90h+var_EF], ax
0x1800185a5  mov     [rbp+90h+var_ED], al
0x1800185a8  mov     [rbp+90h+var_EC], rax
0x1800185ac  mov     [rbp+90h+var_E4], eax
0x1800185af  xor     edx, edx; Val
0x1800185b1  lea     r8d, [rax+50h]; Size
0x1800185b5  lea     rcx, [rsp+190h+var_140]; void *
0x1800185ba  call    memset_0
0x1800185bf  mov     [rbp+90h+var_F8], 1
0x1800185c3  mov     rcx, [rbx+50h]
0x1800185c7  mov     rax, [rcx]
0x1800185ca  lea     rdx, [rsp+190h+var_150]
0x1800185cf  mov     [rsp+190h+var_160], rdx
0x1800185d4  lea     rdx, [rbp+90h+var_F0]
0x1800185d8  mov     [rsp+190h+var_168], rdx
0x1800185dd  lea     rdx, [rsp+190h+var_140]
0x1800185e2  mov     [rsp+190h+var_170], rdx
0x1800185e7  mov     r9b, sil
0x1800185ea  mov     r8d, edi
0x1800185ed  mov     edx, [rbx+40h]
0x1800185f0  mov     rax, [rax+40h]
0x1800185f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185f9  test    eax, eax
0x1800185fb  jns     short loc_180018619
0x1800185fd  mov     r8d, eax; unsigned int
0x180018600  mov     rdx, [rsp+190h+var_150]; struct _EAP_ERROR *
0x180018605  lea     rcx, [rbp+90h+var_E0]; this
0x180018609  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001860e  nop
0x18001860f  lea     rcx, [rbp+90h+var_E0]; struct EapHost::EapError *
0x180018613  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x180018619  lea     rdx, [rsp+190h+var_140]
0x18001861e  lea     rcx, [rbp+90h+var_E0]; void *
0x180018622  call    ??0?$crt_ref@UtagEapPeerMethodResult@@@@QEAA@AEBUtagEapPeerMethodResult@@@Z; crt_ref<tagEapPeerMethodResult>::crt_ref<tagEapPeerMethodResult>(tagEapPeerMethodResult const &)
0x180018627  movups  xmm6, xmmword ptr [rax]
0x18001862a  movups  xmm7, xmmword ptr [rax+10h]
0x18001862e  movups  xmm8, xmmword ptr [rax+20h]
0x180018633  movups  xmm9, xmmword ptr [rax+30h]
0x180018638  movsd   xmm10, qword ptr [rax+40h]
0x18001863e  mov     ebx, 48h ; 'H'
0x180018643  mov     r8d, ebx; Size
0x180018646  xor     edx, edx; Val
0x180018648  mov     rcx, rax; void *
0x18001864b  call    memset_0
0x180018650  movups  xmmword ptr [r14], xmm6
0x180018654  movups  xmmword ptr [r14+10h], xmm7
0x180018659  movups  xmmword ptr [r14+20h], xmm8
0x18001865e  movups  xmmword ptr [r14+30h], xmm9
0x180018663  movsd   qword ptr [r14+40h], xmm10
0x180018669  lea     rcx, [rbp+90h+var_E0]; void *
0x18001866d  call    ??$Free@VHeapAllocator@@@@YAXAEAUtagEapPeerMethodResult@@@Z; Free<HeapAllocator>(tagEapPeerMethodResult &)
0x180018672  mov     al, [rbp+90h+var_F0]
0x180018675  mov     [r15+8], al
0x180018679  mov     eax, dword ptr [rbp+90h+var_EC]
0x18001867c  mov     [r15+0Ch], eax
0x180018680  mov     eax, dword ptr [rbp+90h+var_EC+4]
0x180018683  mov     [r15+10h], eax
0x180018687  mov     eax, [rbp+90h+var_E4]
0x18001868a  mov     [r15+18h], eax
0x18001868e  mov     rcx, [rsp+190h+pv]; pv
0x180018693  call    cs:__imp_CoTaskMemFree
0x180018699  mov     rcx, [rsp+190h+var_120]; pv
0x18001869e  call    cs:__imp_CoTaskMemFree
0x1800186a4  mov     rcx, [rsp+190h+var_118]
0x1800186a9  test    rcx, rcx
0x1800186ac  jz      short loc_1800186BE
0x1800186ae  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x1800186b3  mov     rcx, [rsp+190h+var_118]; pv
0x1800186b8  call    cs:__imp_CoTaskMemFree
0x1800186be  mov     rcx, [rbp+90h+var_110]; void *
0x1800186c2  test    rcx, rcx
0x1800186c5  jz      short loc_1800186D6
0x1800186c7  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x1800186cc  mov     rcx, [rbp+90h+var_110]; pv
0x1800186d0  call    cs:__imp_CoTaskMemFree
0x1800186d6  mov     r8, rbx; Size
0x1800186d9  xor     edx, edx; Val
0x1800186db  lea     rcx, [rsp+190h+var_140]; void *
0x1800186e0  call    memset_0
0x1800186e5  nop
0x1800186e6  lea     rcx, [rsp+190h+var_150]
0x1800186eb  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x1800186f0  mov     rcx, [rbp+90h+var_80]
0x1800186f4  xor     rcx, rsp; StackCookie
0x1800186f7  call    __security_check_cookie
0x1800186fc  lea     r11, [rsp+190h+var_20]
0x180018704  mov     rbx, [r11+30h]
0x180018708  movaps  xmm6, xmmword ptr [r11-10h]
0x18001870d  movaps  xmm7, xmmword ptr [r11-20h]
0x180018712  movaps  xmm8, xmmword ptr [r11-30h]
0x180018717  movaps  xmm9, xmmword ptr [r11-40h]
0x18001871c  movaps  xmm10, xmmword ptr [r11-50h]
0x180018721  mov     rsp, r11
0x180018724  pop     r15
0x180018726  pop     r14
0x180018728  pop     rdi
0x180018729  pop     rsi
0x18001872a  pop     rbp
0x18001872b  retn
```
