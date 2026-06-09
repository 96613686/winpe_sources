# CShaderResourceView::CLS::FinalConstruct(CContext *,CShaderResourceView::TConstructorArgs const *)

- ea: `0x18003a3e0`
- end: `0x18003a96d`
- name: `?FinalConstruct@CLS@CShaderResourceView@@QEAAXPEAVCContext@@PEBUTConstructorArgs@2@@Z`
- size: `1421`
- prototype: `void(CShaderResourceView::CLS *__hidden this, struct CContext *, const struct CShaderResourceView::TConstructorArgs *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180081130`

## callees

- `0x18001e2a0`
- `0x180022400`
- `0x18002bd20`
- `0x18002cb9c`
- `0x18003a380`
- `0x18003a3b0`
- `0x18003a3e0`
- `0x18003a974`
- `0x18003ab30`
- `0x18003ad4c`
- `0x18003b310`
- `0x18003b420`
- `0x18003b720`
- `0x18003dcd4`
- `0x180082124`
- `0x180095fc4`
- `0x1800960f8`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a4a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a4a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CShaderResourceView::CLS::FinalConstruct(
        CShaderResourceView::CLS *this,
        struct CContext *a2,
        const struct CShaderResourceView::TConstructorArgs *a3)
{
  __int64 v6; // rdx
  struct CContext *v7; // rcx
  __int64 Dependent; // rax
  _QWORD *v9; // r13
  _QWORD *v10; // rsi
  __int64 v11; // r13
  int v12; // r12d
  __int64 v13; // rdi
  char *v14; // r8
  CDevice *v15; // rdx
  bool IsDDIWDDM2_0BuildVersion5OrEarlier; // al
  _QWORD *v17; // r9
  char *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r15
  __int64 v21; // rdi
  int v22; // ecx
  _BYTE *v23; // rax
  bool v24; // al
  int v25; // r12d
  struct CDevice *v26; // rbx
  unsigned __int8 v27; // al
  CDevice *v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  bool v31; // zf
  bool v32; // r15
  int v33; // r12d
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // [rsp+30h] [rbp-69h] BYREF
  __int128 v44; // [rsp+38h] [rbp-61h]
  __int128 v45; // [rsp+48h] [rbp-51h]
  _QWORD v46[7]; // [rsp+58h] [rbp-41h] BYREF
  void **pExceptionObject; // [rsp+90h] [rbp-9h] BYREF
  __int128 v48; // [rsp+98h] [rbp-1h]
  __int64 v49; // [rsp+100h] [rbp+67h]
  __int16 v50; // [rsp+101h] [rbp+68h]
  char v51; // [rsp+103h] [rbp+6Ah]

  v6 = *(_QWORD *)(*(_QWORD *)this + 208LL);
  if ( a2 )
    v7 = a2;
  else
    v7 = *(struct CContext **)(*(_QWORD *)(*(_QWORD *)this + 160LL) + 1080LL);
  Dependent = CContext::AllocateDependentCLS<CResource<ID3D11Resource>>(v7, v6);
  if ( !Dependent )
  {
    *((_QWORD *)&v48 + 1) = 0;
    *(_QWORD *)&v48 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  *((_QWORD *)this + 2) = Dependent + 16;
  v9 = *(_QWORD **)this;
  if ( !a2 )
  {
    v19 = v9[20];
    v20 = *(_QWORD *)(v19 + 1080);
    v49 = v20;
    v21 = *((_QWORD *)a3 + 3);
    if ( !v21 )
      v21 = v9[21];
    v22 = *(_DWORD *)(*(_QWORD *)(v19 + 1232) + 1248LL) >> 31;
    v23 = (_BYTE *)*((_QWORD *)a3 + 4);
    v24 = v23 && *v23;
    if ( (_BYTE)v22 || v24 )
    {
      v25 = 3;
      if ( (_BYTE)v22 )
      {
        v32 = 0;
        v33 = -2005270523;
        if ( !v24 )
        {
LABEL_34:
          ThrowFailure(v33);
          *((_BYTE *)this + 11) &= ~1u;
          *((_BYTE *)this + 11) |= v32;
          CDeviceChild<ID3D11ShaderResourceView1>::AllocateCLSOffset(v9, v34, (char *)this + 48);
          return;
        }
        v20 = v49;
        v25 = 3;
      }
    }
    else
    {
      v25 = 1;
    }
    v26 = *(struct CDevice **)(*(_QWORD *)this + 160LL);
    if ( v26 && *((_BYTE *)v26 + 1352) )
    {
      CLockOwnerChild<CDevice,0>::UCAddUse((char *)v26 + 248);
      CDDISync::CFreeThreadedLock::Enter(v26);
    }
    else
    {
      v26 = 0;
    }
    DDIImmCtxMT::DDIImmCtxMT((__int64)v46, v20, 2);
    v27 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 160LL) + 1112LL);
    if ( v27 < 7u )
    {
      if ( (v27 & 0xFC) == 0 && v27 != 1 )
      {
        if ( v27 < 3u )
        {
          CSafeDDISRView::CSafeDDISRView((CSafeDDISRView *)&v43, a3);
          if ( v25 == 1 )
            v41 = v46[0] + 1480LL;
          else
            v41 = *(_QWORD *)(v46[0] + 39672LL);
          (*(void (__fastcall **)(__int64, __int64 *, char *, __int64))(v41 + 496))(
            v20 + 40768,
            &v43,
            (char *)this + 48,
            v21);
          if ( v25 == 1 )
            v42 = v46[0] + 1480LL;
          else
            v42 = *(_QWORD *)(v46[0] + 39672LL);
          v31 = *(_QWORD *)(v42 + 496) == (_QWORD)&CContext::DDI_ResizeTilePool_DR;
        }
        else
        {
          CSafeDDISRView1::CSafeDDISRView1((CSafeDDISRView1 *)&v43, a3);
          if ( v25 == 1 )
            v37 = v46[0] + 1480LL;
          else
            v37 = *(_QWORD *)(v46[0] + 39672LL);
          (*(void (__fastcall **)(__int64, __int64 *, char *, __int64))(v37 + 496))(
            v20 + 40768,
            &v43,
            (char *)this + 48,
            v21);
          if ( v25 == 1 )
            v38 = v46[0] + 1480LL;
          else
            v38 = *(_QWORD *)(v46[0] + 39672LL);
          v31 = *(_QWORD *)(v38 + 496) == (_QWORD)&CContext::DDI_ResizeTilePool_DR;
        }
LABEL_32:
        v32 = !v31;
        v33 = *(_DWORD *)(v46[5] + 4LL);
        DDIImmCtxMT::~DDIImmCtxMT((DDIImmCtxMT *)v46);
        if ( v26 )
        {
          CDDISync::CFreeThreadedLock::Leave(v26);
          CLockOwnerChild<CDevice,0>::UCReleaseUse((char *)v26 + 248);
        }
        goto LABEL_34;
      }
    }
    else if ( !CDevice::IsDDIWDDM2_0BuildVersion0(*(CDevice **)(*(_QWORD *)this + 160LL)) )
    {
      if ( CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(v28) )
      {
        CSafeDDISRViewWDDM2_0::CSafeDDISRViewWDDM2_0((CSafeDDISRViewWDDM2_0 *)&v43, a3);
        if ( v25 == 1 )
          v39 = v46[0] + 1480LL;
        else
          v39 = *(_QWORD *)(v46[0] + 39672LL);
        (*(void (__fastcall **)(__int64, __int64 *, char *, __int64))(v39 + 1328))(
          v20 + 40768,
          &v43,
          (char *)this + 48,
          v21);
        if ( v25 == 1 )
          v40 = v46[0] + 1480LL;
        else
          v40 = *(_QWORD *)(v46[0] + 39672LL);
        v31 = *(_QWORD *)(v40 + 1328) == (_QWORD)&CContext::DDI_ResizeTilePool_DR;
      }
      else
      {
        CSafeDDISRViewWDDM2_0::CSafeDDISRViewWDDM2_0((CSafeDDISRViewWDDM2_0 *)&v43, a3);
        if ( v25 == 1 )
          v29 = v46[0] + 1480LL;
        else
          v29 = *(_QWORD *)(v46[0] + 39672LL);
        (*(void (__fastcall **)(__int64, __int64 *, char *, __int64))(v29 + 496))(
          v20 + 40768,
          &v43,
          (char *)this + 48,
          v21);
        if ( v25 == 1 )
          v30 = v46[0] + 1480LL;
        else
          v30 = *(_QWORD *)(v46[0] + 39672LL);
        v31 = *(_QWORD *)(v30 + 496) == (_QWORD)&CContext::DDI_ResizeTilePool_DR;
      }
      goto LABEL_32;
    }
    CSafeDDISRView11::CSafeDDISRView11((CSafeDDISRView11 *)&v43, a3);
    if ( v25 == 1 )
      v35 = v46[0] + 1480LL;
    else
      v35 = *(_QWORD *)(v46[0] + 39672LL);
    (*(void (__fastcall **)(__int64, __int64 *, char *, __int64))(v35 + 496))(v20 + 40768, &v43, (char *)this + 48, v21);
    if ( v25 == 1 )
      v36 = v46[0] + 1480LL;
    else
      v36 = *(_QWORD *)(v46[0] + 39672LL);
    v31 = *(_QWORD *)(v36 + 496) == (_QWORD)&CContext::DDI_ResizeTilePool_DR;
    goto LABEL_32;
  }
  v10 = v9 + 38;
  v11 = CContext::GetCLS<CResource<ID3D11Resource>>(a2, v9[26]) + 56;
  pExceptionObject = (void **)a2;
  v12 = *((_DWORD *)a2 + 922);
  LODWORD(v48) = v12;
  v13 = *(_QWORD *)((char *)a2 + 3692);
  *(_QWORD *)((char *)&v48 + 4) = v13;
  *((_DWORD *)a2 + 922) = GetCurrentThreadId();
  *((_BYTE *)a2 + 3692) = 2;
  *(_WORD *)((char *)a2 + 3693) = v50;
  *((_BYTE *)a2 + 3695) = v51;
  *((_DWORD *)a2 + 924) = 0;
  v14 = (char *)this + 48;
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 160LL) + 1112LL) < 7u
    || CDevice::IsDDIWDDM2_0BuildVersion0(*(CDevice **)(*(_QWORD *)this + 160LL)) )
  {
    v18 = (char *)a2 + 40768;
    v17 = v10;
    v43 = v11;
    v44 = 0;
    *(_QWORD *)&v45 = 0;
  }
  else
  {
    IsDDIWDDM2_0BuildVersion5OrEarlier = CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(v15);
    v43 = v11;
    v17 = v10;
    v18 = (char *)a2 + 40768;
    v44 = 0;
    v45 = 0;
    if ( IsDDIWDDM2_0BuildVersion5OrEarlier )
    {
      (*((void (__fastcall **)(char *, __int64 *, char *, _QWORD *))a2 + 351))(v18, &v43, v14, v10);
      goto LABEL_10;
    }
  }
  (*((void (__fastcall **)(char *, __int64 *, char *, _QWORD *))a2 + 247))(v18, &v43, v14, v17);
LABEL_10:
  if ( *((int *)a2 + 924) >= 0 )
    *((_BYTE *)this + 11) |= 1u;
  *((_DWORD *)a2 + 922) = v12;
  *(_QWORD *)((char *)a2 + 3692) = v13;
}

```

## disassembly

```asm
0x18003a3e0  push    rbp
0x18003a3e2  push    rbx
0x18003a3e3  push    rsi
0x18003a3e4  push    rdi
0x18003a3e5  push    r12
0x18003a3e7  push    r13
0x18003a3e9  push    r14
0x18003a3eb  push    r15
0x18003a3ed  lea     rbp, [rsp-1Fh]
0x18003a3f2  sub     rsp, 0B8h
0x18003a3f9  mov     rsi, r8
0x18003a3fc  mov     r15, rdx
0x18003a3ff  mov     r14, rcx
0x18003a402  mov     rax, [rcx]
0x18003a405  mov     rdx, [rax+0D0h]
0x18003a40c  test    r15, r15
0x18003a40f  jnz     loc_18003A76A
0x18003a415  mov     rax, [rax+0A0h]
0x18003a41c  mov     rcx, [rax+438h]
0x18003a423  call    ??$AllocateDependentCLS@V?$CResource@UID3D11Resource@@@@@CContext@@QEAAPEAUCLS@?$CResource@UID3D11Resource@@@@PEAV2@@Z; CContext::AllocateDependentCLS<CResource<ID3D11Resource>>(CResource<ID3D11Resource> *)
0x18003a428  test    rax, rax
0x18003a42b  jnz     short loc_18003A45B
0x18003a42d  xorps   xmm0, xmm0
0x18003a430  movups  [rbp+57h+var_58], xmm0
0x18003a434  lea     rax, aBadAllocation; "bad allocation"
0x18003a43b  mov     qword ptr [rbp+57h+var_58], rax
0x18003a43f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18003a446  mov     [rbp+57h+pExceptionObject], rax
0x18003a44a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18003a451  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003a455  call    _CxxThrowException_0
0x18003a45b  add     rax, 10h
0x18003a45f  mov     [r14+10h], rax
0x18003a463  mov     r13, [r14]
0x18003a466  test    r15, r15
0x18003a469  jz      loc_18003A56F
0x18003a46f  lea     rsi, [r13+130h]
0x18003a476  mov     rdx, [r13+0D0h]
0x18003a47d  mov     rcx, r15
0x18003a480  call    ??$GetCLS@V?$CResource@UID3D11Resource@@@@@CContext@@QEAAPEAUCLS@?$CResource@UID3D11Resource@@@@PEAV2@@Z; CContext::GetCLS<CResource<ID3D11Resource>>(CResource<ID3D11Resource> *)
0x18003a485  lea     r13, [rax+38h]
0x18003a489  mov     [rbp+57h+pExceptionObject], r15
0x18003a48d  mov     r12d, [r15+0E68h]
0x18003a494  mov     dword ptr [rbp+57h+var_58], r12d
0x18003a498  mov     rdi, [r15+0E6Ch]
0x18003a49f  mov     qword ptr [rbp+57h+var_58+4], rdi
0x18003a4a3  call    cs:__imp_GetCurrentThreadId
0x18003a4a9  mov     [r15+0E68h], eax
0x18003a4b0  mov     byte ptr [r15+0E6Ch], 2
0x18003a4b8  movzx   eax, [rbp+57h+arg_1]
0x18003a4bc  mov     [r15+0E6Dh], ax
0x18003a4c4  movzx   eax, [rbp+57h+arg_3]
0x18003a4c8  mov     [r15+0E6Fh], al
0x18003a4cf  xor     ebx, ebx
0x18003a4d1  mov     [r15+0E70h], ebx
0x18003a4d8  mov     rax, [r14]
0x18003a4db  mov     rdx, [rax+0A0h]
0x18003a4e2  movzx   eax, byte ptr [rdx+458h]
0x18003a4e9  lea     r8, [r14+30h]
0x18003a4ed  cmp     al, 7
0x18003a4ef  jb      loc_18003A746
0x18003a4f5  mov     rcx, rdx; this
0x18003a4f8  call    ?IsDDIWDDM2_0BuildVersion0@CDevice@@QEAA_NXZ; CDevice::IsDDIWDDM2_0BuildVersion0(void)
0x18003a4fd  test    al, al
0x18003a4ff  jnz     loc_18003A746
0x18003a505  mov     rcx, rdx; this
0x18003a508  call    ?IsDDIWDDM2_0BuildVersion5OrEarlier@CDevice@@QEAA_NXZ; CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(void)
0x18003a50d  xorps   xmm0, xmm0
0x18003a510  mov     [rbp+57h+var_C0], r13
0x18003a514  mov     r9, rsi
0x18003a517  lea     rdx, [rbp+57h+var_C0]
0x18003a51b  lea     rcx, [r15+9F40h]
0x18003a522  movups  [rbp+57h+var_B8], xmm0
0x18003a526  movups  [rbp+57h+var_A8], xmm0
0x18003a52a  test    al, al
0x18003a52c  jnz     loc_18003A7EE
0x18003a532  mov     rax, [r15+7B8h]
0x18003a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a53e  cmp     dword ptr [r15+0E70h], 0
0x18003a546  jl      short loc_18003A54D
0x18003a548  or      byte ptr [r14+0Bh], 1
0x18003a54d  mov     [r15+0E68h], r12d
0x18003a554  mov     [r15+0E6Ch], rdi
0x18003a55b  add     rsp, 0B8h
0x18003a562  pop     r15
0x18003a564  pop     r14
0x18003a566  pop     r13
0x18003a568  pop     r12
0x18003a56a  pop     rdi
0x18003a56b  pop     rsi
0x18003a56c  pop     rbx
0x18003a56d  pop     rbp
0x18003a56e  retn
0x18003a56f  mov     rax, [r13+0A0h]
0x18003a576  mov     r15, [rax+438h]
0x18003a57d  mov     [rbp+67h], r15
0x18003a581  mov     rdi, [rsi+18h]
0x18003a585  test    rdi, rdi
0x18003a588  jnz     short loc_18003A591
0x18003a58a  mov     rdi, [r13+0A8h]
0x18003a591  mov     rax, [rax+4D0h]
0x18003a598  mov     ecx, [rax+4E0h]
0x18003a59e  shr     ecx, 1Fh
0x18003a5a1  mov     rax, [rsi+20h]
0x18003a5a5  test    rax, rax
0x18003a5a8  jz      short loc_18003A5B3
0x18003a5aa  cmp     byte ptr [rax], 0
0x18003a5ad  jnz     loc_18003A8CD
0x18003a5b3  xor     al, al
0x18003a5b5  test    cl, cl
0x18003a5b7  jnz     loc_18003A704
0x18003a5bd  test    al, al
0x18003a5bf  jnz     loc_18003A704
0x18003a5c5  mov     r12d, 1
0x18003a5cb  mov     rbx, [r14]
0x18003a5ce  mov     rbx, [rbx+0A0h]
0x18003a5d5  test    rbx, rbx
0x18003a5d8  jz      short loc_18003A5E7
0x18003a5da  cmp     byte ptr [rbx+548h], 0
0x18003a5e1  jnz     loc_18003A6E7
0x18003a5e7  xor     ebx, ebx
0x18003a5e9  mov     [rbp+67h], rbx
0x18003a5ed  mov     r8b, 2
0x18003a5f0  mov     rdx, r15
0x18003a5f3  lea     rcx, [rbp+57h+var_98]
0x18003a5f7  call    ??0DDIImmCtxMT@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z; DDIImmCtxMT::DDIImmCtxMT(CContext *,EErrorBehavior)
0x18003a5fc  nop
0x18003a5fd  mov     rax, [r14]
0x18003a600  mov     rdx, [rax+0A0h]
0x18003a607  movzx   eax, byte ptr [rdx+458h]
0x18003a60e  cmp     al, 7
0x18003a610  jb      loc_18003A772
0x18003a616  mov     rcx, rdx; this
0x18003a619  call    ?IsDDIWDDM2_0BuildVersion0@CDevice@@QEAA_NXZ; CDevice::IsDDIWDDM2_0BuildVersion0(void)
0x18003a61e  test    al, al
0x18003a620  jnz     loc_18003A77A
0x18003a626  mov     rcx, rdx; this
0x18003a629  call    ?IsDDIWDDM2_0BuildVersion5OrEarlier@CDevice@@QEAA_NXZ; CDevice::IsDDIWDDM2_0BuildVersion5OrEarlier(void)
0x18003a62e  mov     rdx, rsi; struct SD3D11_3LayeredShaderResourceViewCreationArgs *
0x18003a631  lea     rcx, [rbp+57h+var_C0]; this
0x18003a635  test    al, al
0x18003a637  jnz     loc_18003A86F
0x18003a63d  call    ??0CSafeDDISRViewWDDM2_0@@QEAA@AEBUSD3D11_3LayeredShaderResourceViewCreationArgs@@@Z; CSafeDDISRViewWDDM2_0::CSafeDDISRViewWDDM2_0(SD3D11_3LayeredShaderResourceViewCreationArgs const &)
0x18003a642  mov     rax, [rbp+57h+var_98]
0x18003a646  cmp     r12d, 1
0x18003a64a  jnz     loc_18003A72E
0x18003a650  add     rax, 5C8h
0x18003a656  lea     r8, [r14+30h]
0x18003a65a  lea     rcx, [r15+9F40h]
0x18003a661  mov     r9, rdi
0x18003a664  lea     rdx, [rbp+57h+var_C0]
0x18003a668  mov     rax, [rax+1F0h]
0x18003a66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a674  mov     rax, [rbp+57h+var_98]
0x18003a678  cmp     r12d, 1
0x18003a67c  jnz     loc_18003A73A
0x18003a682  add     rax, 5C8h
0x18003a688  lea     rcx, ?DDI_ResizeTilePool_DR@CContext@@SAXUD3D10DDI_HDEVICE@@UD3D10DDI_HRESOURCE@@_K@Z; CContext::DDI_ResizeTilePool_DR(D3D10DDI_HDEVICE,D3D10DDI_HRESOURCE,unsigned __int64)
0x18003a68f  cmp     [rax+1F0h], rcx
0x18003a696  setnz   r15b
0x18003a69a  mov     rax, [rbp+57h+var_70]
0x18003a69e  mov     r12d, [rax+4]
0x18003a6a2  lea     rcx, [rbp+57h+var_98]; this
0x18003a6a6  call    ??1DDIImmCtxMT@@QEAA@XZ; DDIImmCtxMT::~DDIImmCtxMT(void)
0x18003a6ab  nop
0x18003a6ac  test    rbx, rbx
0x18003a6af  jz      short loc_18003A6C5
0x18003a6b1  mov     rcx, rbx; struct CDevice *
0x18003a6b4  call    ?Leave@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CFreeThreadedLock::Leave(CDevice *)
0x18003a6b9  lea     rcx, [rbx+0F8h]
0x18003a6c0  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18003a6c5  mov     ecx, r12d; int
0x18003a6c8  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18003a6cd  and     byte ptr [r14+0Bh], 0FEh
0x18003a6d2  or      [r14+0Bh], r15b
0x18003a6d6  lea     r8, [r14+30h]
0x18003a6da  mov     rcx, r13
0x18003a6dd  call    ?AllocateCLSOffset@?$CDeviceChild@UID3D11ShaderResourceView1@@@@QEAAXW4D3D11DDI_HANDLETYPE@@PEAX_K@Z; CDeviceChild<ID3D11ShaderResourceView1>::AllocateCLSOffset(D3D11DDI_HANDLETYPE,void *,unsigned __int64)
0x18003a6e2  jmp     loc_18003A55B
0x18003a6e7  mov     [rbp+67h], rbx
0x18003a6eb  lea     rcx, [rbx+0F8h]
0x18003a6f2  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18003a6f7  mov     rcx, rbx; struct CDevice *
0x18003a6fa  call    ?Enter@CFreeThreadedLock@CDDISync@@SAXPEAVCDevice@@@Z; CDDISync::CFreeThreadedLock::Enter(CDevice *)
0x18003a6ff  jmp     loc_18003A5ED
0x18003a704  mov     r12d, 3
0x18003a70a  test    cl, cl
0x18003a70c  jz      loc_18003A5CB
0x18003a712  xor     r15b, r15b
0x18003a715  mov     r12d, 887A0005h
0x18003a71b  test    al, al
0x18003a71d  jz      short loc_18003A6C5
0x18003a71f  mov     r15, [rbp+67h]
0x18003a723  mov     r12d, 3
0x18003a729  jmp     loc_18003A5CB
0x18003a72e  mov     rax, [rax+9AF8h]
0x18003a735  jmp     loc_18003A656
0x18003a73a  mov     rax, [rax+9AF8h]
0x18003a741  jmp     loc_18003A688
0x18003a746  xorps   xmm0, xmm0
0x18003a749  lea     rcx, [r15+9F40h]
0x18003a750  lea     rdx, [rbp+57h+var_C0]
0x18003a754  mov     r9, rsi
0x18003a757  mov     [rbp+57h+var_C0], r13
0x18003a75b  movups  [rbp+57h+var_B8], xmm0
0x18003a75f  xor     eax, eax
0x18003a761  mov     qword ptr [rbp+57h+var_A8], rax
0x18003a765  jmp     loc_18003A532
0x18003a76a  mov     rcx, r15
0x18003a76d  jmp     loc_18003A423
0x18003a772  test    al, 0FCh
0x18003a774  jz      loc_18003A7FA
0x18003a77a  mov     rdx, rsi; struct SD3D11_3LayeredShaderResourceViewCreationArgs *
0x18003a77d  lea     rcx, [rbp+57h+var_C0]; this
0x18003a781  call    ??0CSafeDDISRView11@@QEAA@AEBUSD3D11_3LayeredShaderResourceViewCreationArgs@@@Z; CSafeDDISRView11::CSafeDDISRView11(SD3D11_3LayeredShaderResourceViewCreationArgs const &)
0x18003a786  mov     rax, [rbp+57h+var_98]
0x18003a78a  cmp     r12d, 1
0x18003a78e  jnz     short loc_18003A7D8
0x18003a790  add     rax, 5C8h
0x18003a796  lea     r8, [r14+30h]
0x18003a79a  lea     rcx, [r15+9F40h]
0x18003a7a1  mov     r9, rdi
0x18003a7a4  lea     rdx, [rbp+57h+var_C0]
0x18003a7a8  mov     rax, [rax+1F0h]
0x18003a7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7b4  cmp     r12d, 1
0x18003a7b8  jnz     short loc_18003A7E1
0x18003a7ba  mov     rcx, [rbp+57h+var_98]
0x18003a7be  add     rcx, 5C8h
0x18003a7c5  lea     rax, ?DDI_ResizeTilePool_DR@CContext@@SAXUD3D10DDI_HDEVICE@@UD3D10DDI_HRESOURCE@@_K@Z; CContext::DDI_ResizeTilePool_DR(D3D10DDI_HDEVICE,D3D10DDI_HRESOURCE,unsigned __int64)
0x18003a7cc  cmp     [rcx+1F0h], rax
0x18003a7d3  jmp     loc_18003A696
0x18003a7d8  mov     rax, [rax+9AF8h]
0x18003a7df  jmp     short loc_18003A796
0x18003a7e1  mov     rax, [rbp+57h+var_98]
0x18003a7e5  mov     rcx, [rax+9AF8h]
0x18003a7ec  jmp     short loc_18003A7C5
0x18003a7ee  mov     rax, [r15+0AF8h]
0x18003a7f5  jmp     loc_18003A539
0x18003a7fa  cmp     al, 1
0x18003a7fc  jz      loc_18003A77A
0x18003a802  mov     rdx, rsi; struct SD3D11_3LayeredShaderResourceViewCreationArgs *
0x18003a805  lea     rcx, [rbp+57h+var_C0]; this
0x18003a809  cmp     al, 3
0x18003a80b  jb      loc_18003A8D4
0x18003a811  call    ??0CSafeDDISRView1@@QEAA@AEBUSD3D11_3LayeredShaderResourceViewCreationArgs@@@Z; CSafeDDISRView1::CSafeDDISRView1(SD3D11_3LayeredShaderResourceViewCreationArgs const &)
0x18003a816  mov     rax, [rbp+57h+var_98]
0x18003a81a  cmp     r12d, 1
0x18003a81e  jnz     loc_18003A942
0x18003a824  add     rax, 5C8h
0x18003a82a  lea     r8, [r14+30h]
0x18003a82e  lea     rcx, [r15+9F40h]
0x18003a835  mov     r9, rdi
0x18003a838  lea     rdx, [rbp+57h+var_C0]
0x18003a83c  mov     rax, [rax+1F0h]
0x18003a843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a848  mov     rax, [rbp+57h+var_98]
0x18003a84c  cmp     r12d, 1
0x18003a850  jnz     loc_18003A94E
0x18003a856  add     rax, 5C8h
0x18003a85c  lea     rcx, ?DDI_ResizeTilePool_DR@CContext@@SAXUD3D10DDI_HDEVICE@@UD3D10DDI_HRESOURCE@@_K@Z; CContext::DDI_ResizeTilePool_DR(D3D10DDI_HDEVICE,D3D10DDI_HRESOURCE,unsigned __int64)
0x18003a863  cmp     [rax+1F0h], rcx
0x18003a86a  jmp     loc_18003A696
0x18003a86f  call    ??0CSafeDDISRViewWDDM2_0@@QEAA@AEBUSD3D11_3LayeredShaderResourceViewCreationArgs@@@Z; CSafeDDISRViewWDDM2_0::CSafeDDISRViewWDDM2_0(SD3D11_3LayeredShaderResourceViewCreationArgs const &)
0x18003a874  mov     rax, [rbp+57h+var_98]
0x18003a878  cmp     r12d, 1
0x18003a87c  jnz     loc_18003A92A
0x18003a882  add     rax, 5C8h
0x18003a888  lea     r8, [r14+30h]
0x18003a88c  lea     rcx, [r15+9F40h]
0x18003a893  mov     r9, rdi
0x18003a896  lea     rdx, [rbp+57h+var_C0]
0x18003a89a  mov     rax, [rax+530h]
0x18003a8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8a6  mov     rax, [rbp+57h+var_98]
0x18003a8aa  cmp     r12d, 1
0x18003a8ae  jnz     loc_18003A936
0x18003a8b4  add     rax, 5C8h
0x18003a8ba  lea     rcx, ?DDI_ResizeTilePool_DR@CContext@@SAXUD3D10DDI_HDEVICE@@UD3D10DDI_HRESOURCE@@_K@Z; CContext::DDI_ResizeTilePool_DR(D3D10DDI_HDEVICE,D3D10DDI_HRESOURCE,unsigned __int64)
0x18003a8c1  cmp     [rax+530h], rcx
0x18003a8c8  jmp     loc_18003A696
0x18003a8cd  mov     al, 1
0x18003a8cf  jmp     loc_18003A5B5
0x18003a8d4  call    ??0CSafeDDISRView@@QEAA@AEBUSD3D11_3LayeredShaderResourceViewCreationArgs@@@Z; CSafeDDISRView::CSafeDDISRView(SD3D11_3LayeredShaderResourceViewCreationArgs const &)
0x18003a8d9  mov     rax, [rbp+57h+var_98]
0x18003a8dd  cmp     r12d, 1
0x18003a8e1  jnz     short loc_18003A95A
0x18003a8e3  add     rax, 5C8h
0x18003a8e9  lea     r8, [r14+30h]
0x18003a8ed  lea     rcx, [r15+9F40h]
0x18003a8f4  mov     r9, rdi
0x18003a8f7  lea     rdx, [rbp+57h+var_C0]
0x18003a8fb  mov     rax, [rax+1F0h]
0x18003a902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a907  mov     rax, [rbp+57h+var_98]
0x18003a90b  cmp     r12d, 1
0x18003a90f  jnz     short loc_18003A963
0x18003a911  add     rax, 5C8h
0x18003a917  lea     rcx, ?DDI_ResizeTilePool_DR@CContext@@SAXUD3D10DDI_HDEVICE@@UD3D10DDI_HRESOURCE@@_K@Z; CContext::DDI_ResizeTilePool_DR(D3D10DDI_HDEVICE,D3D10DDI_HRESOURCE,unsigned __int64)
0x18003a91e  cmp     [rax+1F0h], rcx
  ... truncated ...
```
