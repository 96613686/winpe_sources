# CKsOutputPin2::SetMediaType(CMediaType const *)

- ea: `0x1800315e0`
- end: `0x18003183d`
- name: `?SetMediaType@CKsOutputPin2@@UEAAJPEBVCMediaType@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(CKsOutputPin2 *this, const struct CMediaType *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001b190`
- `0x18001bb40`
- `0x18001bbf8`
- `0x18001f620`
- `0x18002dcc8`
- `0x18002dd70`
- `0x1800315e0`
- `0x180031844`
- `0x180031d00`
- `0x180031e14`
- `0x180031e78`
- `0x18003e22c`
- `0x18003f6ac`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18003174b`
- `ole32!CoTaskMemAlloc` at `0x18003174b`
- `ole32!CoTaskMemFree` at `0x18003172b`
- `ole32!CoTaskMemFree` at `0x18003172b`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::SetMediaType(CKsOutputPin2 *this, const struct CMediaType *a2, __int64 a3)
{
  int MediaTypeArrays; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  void *v8; // rsi
  struct _AMMediaType *v9; // rax
  struct CMediaType *v10; // rsi
  char *v11; // rcx
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-38h] BYREF

  MediaTypeArrays = 0;
  v13 = 0;
  pv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      "CKsOutputPin2::SetMediaType");
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      SetMediaType_Enter,
      a3,
      1,
      v15);
  if ( *((_QWORD *)this + 70) )
  {
    v6 = *((_QWORD *)this + 71);
    *((_QWORD *)this + 70) = 0;
    if ( v6 )
    {
      *((_QWORD *)this + 71) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  OpenDataHandler(
    a2,
    (LPUNKNOWN)(((unsigned __int64)this + 24) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (IUnknown **)this + 70,
    (LPVOID *)this + 71);
  if ( *((_DWORD *)this + 300) || (MediaTypeArrays = CKsOutputPin2::CreateMediaTypeArrays(this), MediaTypeArrays >= 0) )
  {
    if ( *((_DWORD *)this + 286) )
    {
      MediaTypeArrays = InitializeDataFormat(a2, 0, &pv, &v13);
      if ( MediaTypeArrays < 0 )
        goto LABEL_26;
      v8 = pv;
      MediaTypeArrays = CKsOutputPin2::SetPluginMediaType(this, (union KSDATAFORMAT *)pv, 0);
      if ( MediaTypeArrays < 0 )
      {
        if ( v8 )
          CoTaskMemFree(v8);
        goto LABEL_26;
      }
      if ( !*((_QWORD *)this + 65) )
        goto LABEL_25;
      v9 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
      v10 = (struct CMediaType *)v9;
      if ( v9 )
      {
        MediaTypeArrays = ConvertKsMediaTypeToAmMediaType(*((union KSDATAFORMAT **)this + 152), v9);
        if ( MediaTypeArrays >= 0 )
          MediaTypeArrays = SetMediaType(*((char **)this + 65), v10);
      }
      else
      {
        MediaTypeArrays = -2147024882;
      }
      DeleteMediaType(v10);
    }
    else
    {
      v11 = (char *)*((_QWORD *)this + 65);
      if ( v11 )
      {
        MediaTypeArrays = SetMediaType(v11, a2);
        if ( MediaTypeArrays < 0 )
          goto LABEL_29;
      }
    }
    if ( MediaTypeArrays >= 0 )
LABEL_25:
      MediaTypeArrays = CBasePin::SetMediaType((CBasePin *)this, a2);
LABEL_26:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        v7,
        (unsigned int)"CKsOutputPin2::SetMediaType",
        MediaTypeArrays);
  }
LABEL_29:
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      SetMediaType_Exit,
      v7,
      1,
      v15);
  return (unsigned int)MediaTypeArrays;
}

```

## disassembly

```asm
0x1800315e0  mov     [rsp+arg_10], rbx
0x1800315e5  mov     [rsp+arg_18], rbp
0x1800315ea  push    rsi
0x1800315eb  push    rdi
0x1800315ec  push    r12
0x1800315ee  sub     rsp, 60h
0x1800315f2  mov     rax, cs:__security_cookie
0x1800315f9  xor     rax, rsp
0x1800315fc  mov     [rsp+78h+var_28], rax
0x180031601  xor     ebx, ebx
0x180031603  mov     rbp, rdx
0x180031606  mov     [rsp+78h+var_48], ebx
0x18003160a  mov     rdi, rcx
0x18003160d  mov     [rsp+78h+pv], rbx
0x180031612  mov     rcx, cs:WPP_GLOBAL_Control
0x180031619  lea     r12, WPP_GLOBAL_Control
0x180031620  cmp     rcx, r12
0x180031623  jz      short loc_180031645
0x180031625  cmp     byte ptr [rcx+19h], 2
0x180031629  jb      short loc_180031645
0x18003162b  mov     rcx, [rcx+10h]
0x18003162f  lea     edx, [rbx+18h]
0x180031632  lea     r9, aCksoutputpin2S; "CKsOutputPin2::SetMediaType"
0x180031639  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x180031640  call    WPP_SF_s
0x180031645  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x18003164c  jz      short loc_180031671
0x18003164e  lea     rax, [rsp+78h+var_38]
0x180031653  mov     r9d, 1
0x180031659  lea     rdx, SetMediaType_Enter
0x180031660  mov     [rsp+78h+var_58], rax
0x180031665  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x18003166c  call    McGenEventWrite_EventWriteTransfer
0x180031671  lea     rsi, [rdi+230h]
0x180031678  cmp     [rsi], rbx
0x18003167b  jz      short loc_18003169F
0x18003167d  mov     rcx, [rdi+238h]
0x180031684  mov     [rsi], rbx
0x180031687  test    rcx, rcx
0x18003168a  jz      short loc_18003169F
0x18003168c  mov     [rdi+238h], rbx
0x180031693  mov     rax, [rcx]
0x180031696  mov     rax, [rax+10h]
0x18003169a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003169f  lea     rcx, [rdi+18h]
0x1800316a3  mov     rax, rdi
0x1800316a6  neg     rax
0x1800316a9  lea     r9, [rdi+238h]; struct IUnknown **
0x1800316b0  mov     r8, rsi; struct IKsDataTypeHandler **
0x1800316b3  sbb     rdx, rdx
0x1800316b6  and     rdx, rcx; pUnkOuter
0x1800316b9  mov     rcx, rbp; rclsid
0x1800316bc  call    ?OpenDataHandler@@YAXPEBVCMediaType@@PEAUIUnknown@@PEAPEAUIKsDataTypeHandler@@PEAPEAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x1800316c1  cmp     [rdi+4B0h], ebx
0x1800316c7  jnz     short loc_1800316DB
0x1800316c9  mov     rcx, rdi; this
0x1800316cc  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QEAAJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x1800316d1  mov     ebx, eax
0x1800316d3  test    eax, eax
0x1800316d5  js      loc_1800317EC
0x1800316db  cmp     dword ptr [rdi+478h], 0
0x1800316e2  jz      loc_180031796
0x1800316e8  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800316ed  xor     edx, edx; unsigned int
0x1800316ef  lea     r8, [rsp+78h+pv]; void **
0x1800316f4  mov     rcx, rbp; struct CMediaType *
0x1800316f7  call    ?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x1800316fc  mov     ebx, eax
0x1800316fe  test    eax, eax
0x180031700  js      loc_1800317C1
0x180031706  mov     rsi, [rsp+78h+pv]
0x18003170b  xor     r8d, r8d; int
0x18003170e  mov     rdx, rsi; union KSDATAFORMAT *
0x180031711  mov     rcx, rdi; this
0x180031714  call    ?SetPluginMediaType@CKsOutputPin2@@QEAAJPEATKSDATAFORMAT@@H@Z; CKsOutputPin2::SetPluginMediaType(KSDATAFORMAT *,int)
0x180031719  mov     ebx, eax
0x18003171b  test    eax, eax
0x18003171d  jns     short loc_18003173C
0x18003171f  test    rsi, rsi
0x180031722  jz      loc_1800317C1
0x180031728  mov     rcx, rsi; pv
0x18003172b  call    cs:__imp_CoTaskMemFree
0x180031732  nop     dword ptr [rax+rax+00h]
0x180031737  jmp     loc_1800317C1
0x18003173c  cmp     qword ptr [rdi+208h], 0
0x180031744  jz      short loc_1800317B4
0x180031746  mov     ecx, 58h ; 'X'; cb
0x18003174b  call    cs:__imp_CoTaskMemAlloc
0x180031752  nop     dword ptr [rax+rax+00h]
0x180031757  mov     rsi, rax
0x18003175a  test    rax, rax
0x18003175d  jnz     short loc_180031766
0x18003175f  mov     ebx, 8007000Eh
0x180031764  jmp     short loc_18003178C
0x180031766  mov     rcx, [rdi+4C0h]; union KSDATAFORMAT *
0x18003176d  mov     rdx, rsi; struct _AMMediaType *
0x180031770  call    ?ConvertKsMediaTypeToAmMediaType@@YAJPEATKSDATAFORMAT@@PEAU_AMMediaType@@@Z; ConvertKsMediaTypeToAmMediaType(KSDATAFORMAT *,_AMMediaType *)
0x180031775  mov     ebx, eax
0x180031777  test    eax, eax
0x180031779  js      short loc_18003178C
0x18003177b  mov     rcx, [rdi+208h]; hFile
0x180031782  mov     rdx, rsi; struct CMediaType *
0x180031785  call    ?SetMediaType@@YAJPEAXPEBVCMediaType@@@Z; SetMediaType(void *,CMediaType const *)
0x18003178a  mov     ebx, eax
0x18003178c  mov     rcx, rsi; pv
0x18003178f  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180031794  jmp     short loc_1800317B0
0x180031796  mov     rcx, [rdi+208h]; hFile
0x18003179d  test    rcx, rcx
0x1800317a0  jz      short loc_1800317B0
0x1800317a2  mov     rdx, rbp; struct CMediaType *
0x1800317a5  call    ?SetMediaType@@YAJPEAXPEBVCMediaType@@@Z; SetMediaType(void *,CMediaType const *)
0x1800317aa  mov     ebx, eax
0x1800317ac  test    eax, eax
0x1800317ae  js      short loc_1800317EC
0x1800317b0  test    ebx, ebx
0x1800317b2  js      short loc_1800317C1
0x1800317b4  mov     rdx, rbp; struct CMediaType *
0x1800317b7  mov     rcx, rdi; this
0x1800317ba  call    ?SetMediaType@CBasePin@@UEAAJPEBVCMediaType@@@Z; CBasePin::SetMediaType(CMediaType const *)
0x1800317bf  mov     ebx, eax
0x1800317c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317c8  cmp     rcx, r12
0x1800317cb  jz      short loc_1800317EC
0x1800317cd  cmp     byte ptr [rcx+19h], 2
0x1800317d1  jb      short loc_1800317EC
0x1800317d3  mov     rcx, [rcx+10h]
0x1800317d7  lea     r9, aCksoutputpin2S; "CKsOutputPin2::SetMediaType"
0x1800317de  mov     edx, 19h
0x1800317e3  mov     dword ptr [rsp+78h+var_58], ebx
0x1800317e7  call    WPP_SF_sd
0x1800317ec  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x1800317f3  jz      short loc_180031818
0x1800317f5  lea     rax, [rsp+78h+var_38]
0x1800317fa  mov     r9d, 1
0x180031800  lea     rdx, SetMediaType_Exit
0x180031807  mov     [rsp+78h+var_58], rax
0x18003180c  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x180031813  call    McGenEventWrite_EventWriteTransfer
0x180031818  mov     eax, ebx
0x18003181a  mov     rcx, [rsp+78h+var_28]
0x18003181f  xor     rcx, rsp; StackCookie
0x180031822  call    __security_check_cookie
0x180031827  lea     r11, [rsp+78h+var_18]
0x18003182c  mov     rbx, [r11+30h]
0x180031830  mov     rbp, [r11+38h]
0x180031834  mov     rsp, r11
0x180031837  pop     r12
0x180031839  pop     rdi
0x18003183a  pop     rsi
0x18003183b  retn
```
