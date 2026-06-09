# MotionTurboJpeg::CMJPGMFTTypeHandler::Init(MotionTurboJpeg::CMJPGMFTDataHandler *)

- ea: `0x1800412ac`
- end: `0x18004143c`
- name: `?Init@CMJPGMFTTypeHandler@MotionTurboJpeg@@QEAAJPEAVCMJPGMFTDataHandler@2@@Z`
- size: `400`
- prototype: `__int64 __fastcall(MotionTurboJpeg::CMJPGMFTTypeHandler *__hidden this, struct MotionTurboJpeg::CMJPGMFTDataHandler *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041444`

## callees

- `0x180014a38`
- `0x180020598`
- `0x180021aa4`
- `0x180024220`
- `0x1800412ac`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180041307`
- `MFPlat!MFCreateMediaType` at `0x180041307`

## pseudocode

```c
__int64 __fastcall MotionTurboJpeg::CMJPGMFTTypeHandler::Init(
        MotionTurboJpeg::CMJPGMFTTypeHandler *this,
        struct MotionTurboJpeg::CMJPGMFTDataHandler *a2)
{
  int v3; // ecx
  unsigned int inited; // ebx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rsi
  IMFMediaType *v8; // r15
  __int64 v9; // rcx
  __int64 v10; // rcx
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-38h] BYREF
  _DWORD v13[2]; // [rsp+38h] [rbp-30h] BYREF
  _DWORD v14[4]; // [rsp+40h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 13) = a2;
  v13[0] = 1196444237;
  inited = CMFTSimpleTypeHandler::InitAvailableInputTypeArray(this, 1u);
  if ( !inited )
  {
    v7 = 0;
    while ( 1 )
    {
      ppMFType = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
      inited = MFCreateMediaType(&ppMFType);
      if ( inited )
        break;
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Video);
      if ( inited )
        break;
      v14[0] = v13[v7];
      v14[1] = 0x100000;
      v14[2] = -1442840448;
      v14[3] = 1905997824;
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _DWORD *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_SUBTYPE,
                 v14);
      if ( inited )
        break;
      if ( (unsigned int)v7 < *((_DWORD *)this + 4) )
      {
        v8 = ppMFType;
        v9 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * (unsigned int)v7);
        if ( v9 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * (unsigned int)v7) = 0;
        }
        *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * (unsigned int)v7) = v8;
        v10 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * (unsigned int)v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        *(_DWORD *)(*((_QWORD *)this + 3) + 16LL * (unsigned int)v7 + 8) = 1;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
      v7 = (unsigned int)(v7 + 1);
      if ( (_DWORD)v7 )
        goto LABEL_13;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  }
LABEL_13:
  if ( (unsigned int)dword_18009C028 > 5 )
  {
    v13[0] = inited;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)qword_180093CA0,
      v5,
      v6,
      (__int64)v13);
  }
  return inited;
}

```

## disassembly

```asm
0x1800412ac  push    rbp
0x1800412ae  push    rbx
0x1800412af  push    rsi
0x1800412b0  push    rdi
0x1800412b1  push    r14
0x1800412b3  push    r15
0x1800412b5  mov     rbp, rsp
0x1800412b8  sub     rsp, 68h
0x1800412bc  mov     rax, cs:__security_cookie
0x1800412c3  xor     rax, rsp
0x1800412c6  mov     [rbp+var_18], rax
0x1800412ca  mov     [rcx+8], rdx
0x1800412ce  mov     rdi, rcx
0x1800412d1  mov     [rcx+68h], rdx
0x1800412d5  mov     edx, 1; unsigned int
0x1800412da  mov     [rbp+var_30], 47504A4Dh
0x1800412e1  call    ?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)
0x1800412e6  mov     ebx, eax
0x1800412e8  test    eax, eax
0x1800412ea  jnz     loc_1800413FE
0x1800412f0  xor     esi, esi
0x1800412f2  lea     rcx, [rbp+ppMFType]
0x1800412f6  mov     [rbp+ppMFType], 0
0x1800412fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041303  lea     rcx, [rbp+ppMFType]; ppMFType
0x180041307  call    cs:__imp_MFCreateMediaType
0x18004130d  mov     ebx, eax
0x18004130f  test    eax, eax
0x180041311  jnz     loc_1800413F5
0x180041317  mov     rcx, [rbp+ppMFType]
0x18004131b  lea     r8, MFMediaType_Video
0x180041322  lea     rdx, MF_MT_MAJOR_TYPE
0x180041329  mov     rax, [rcx]
0x18004132c  mov     rax, [rax+0C0h]
0x180041333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041338  mov     ebx, eax
0x18004133a  test    eax, eax
0x18004133c  jnz     loc_1800413F5
0x180041342  mov     rcx, [rbp+ppMFType]
0x180041346  lea     r8, [rbp+var_28]
0x18004134a  mov     eax, [rbp+rsi*4+var_30]
0x18004134e  lea     rdx, MF_MT_SUBTYPE
0x180041355  mov     [rbp+var_28], eax
0x180041358  mov     [rbp+var_24], 100000h
0x18004135f  mov     [rbp+var_20], 0AA000080h
0x180041366  mov     [rbp+var_1C], 719B3800h
0x18004136d  mov     rax, [rcx]
0x180041370  mov     r14d, esi
0x180041373  mov     rax, [rax+0C0h]
0x18004137a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004137f  mov     ebx, eax
0x180041381  test    eax, eax
0x180041383  jnz     short loc_1800413F5
0x180041385  cmp     esi, [rdi+10h]
0x180041388  jnb     short loc_1800413DF
0x18004138a  mov     rax, [rdi+18h]
0x18004138e  add     r14, r14
0x180041391  mov     r15, [rbp+ppMFType]
0x180041395  mov     rcx, [rax+r14*8]
0x180041399  test    rcx, rcx
0x18004139c  jz      short loc_1800413B6
0x18004139e  mov     rax, [rcx]
0x1800413a1  mov     rax, [rax+10h]
0x1800413a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413aa  mov     rax, [rdi+18h]
0x1800413ae  mov     qword ptr [rax+r14*8], 0
0x1800413b6  mov     rax, [rdi+18h]
0x1800413ba  mov     [rax+r14*8], r15
0x1800413be  mov     rax, [rdi+18h]
0x1800413c2  mov     rcx, [rax+r14*8]
0x1800413c6  mov     rax, [rcx]
0x1800413c9  mov     rax, [rax+8]
0x1800413cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413d2  mov     rax, [rdi+18h]
0x1800413d6  mov     dword ptr [rax+r14*8+8], 1
0x1800413df  lea     rcx, [rbp+ppMFType]
0x1800413e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800413e8  inc     esi
0x1800413ea  cmp     esi, 1
0x1800413ed  jb      loc_1800412F2
0x1800413f3  jmp     short loc_1800413FE
0x1800413f5  lea     rcx, [rbp+ppMFType]
0x1800413f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800413fe  mov     eax, cs:dword_18009C028
0x180041404  cmp     eax, 5
0x180041407  jbe     short loc_180041421
0x180041409  lea     rax, [rbp+var_30]
0x18004140d  mov     [rbp+var_30], ebx
0x180041410  lea     rdx, qword_180093CA0
0x180041417  mov     [rsp+68h+var_48], rax
0x18004141c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180041421  mov     eax, ebx
0x180041423  mov     rcx, [rbp+var_18]
0x180041427  xor     rcx, rsp; StackCookie
0x18004142a  call    __security_check_cookie
0x18004142f  add     rsp, 68h
0x180041433  pop     r15
0x180041435  pop     r14
0x180041437  pop     rdi
0x180041438  pop     rsi
0x180041439  pop     rbx
0x18004143a  pop     rbp
0x18004143b  retn
```
