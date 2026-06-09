# CStandardInterfaceHandler::KsProcessMediaSamples(IKsDataTypeHandler *,IMediaSample * *,long *,KSIOOPERATION,_KSSTREAM_SEGMENT * *)

- ea: `0x10033c90`
- end: `0x10034137`
- name: `?KsProcessMediaSamples@CStandardInterfaceHandler@@UAGJPAUIKsDataTypeHandler@@PAPAUIMediaSample@@PAJW4KSIOOPERATION@@PAPAU_KSSTREAM_SEGMENT@@@Z`
- size: `1191`
- prototype: `int(CStandardInterfaceHandler *__hidden this, struct IKsDataTypeHandler *, struct IMediaSample **, int *, enum KSIOOPERATION, struct _KSSTREAM_SEGMENT **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x1002d510`
- `0x10033b0a`
- `0x10033c90`
- `0x100346f3`
- `0x1003473f`
- `0x1003a6fd`
- `0x1003a72c`
- `0x1003af9d`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10033ce6`
- `KERNEL32!GetLastError` at `0x10033fcd`
- `KERNEL32!GetLastError` at `0x10033ce6`
- `KERNEL32!GetLastError` at `0x10033fcd`
- `KERNEL32!SetEvent` at `0x10033ff3`
- `KERNEL32!SetEvent` at `0x1003411f`
- `KERNEL32!SetEvent` at `0x10033ff3`
- `KERNEL32!SetEvent` at `0x1003411f`
- `KERNEL32!CreateEventW` at `0x10033cd9`
- `KERNEL32!CreateEventW` at `0x10033cd9`
- `KERNEL32!CloseHandle` at `0x100340fb`
- `KERNEL32!CloseHandle` at `0x100340fb`
- `KERNEL32!DeviceIoControl` at `0x10033fbf`
- `KERNEL32!DeviceIoControl` at `0x10033fbf`

## pseudocode

```c
int __stdcall CStandardInterfaceHandler::KsProcessMediaSamples(
        CStandardInterfaceHandler *this,
        struct IKsDataTypeHandler *a2,
        struct IMediaSample **a3,
        int *a4,
        enum KSIOOPERATION a5,
        struct _KSSTREAM_SEGMENT **a6)
{
  char *v6; // edi
  unsigned int v8; // esi
  HANDLE EventW; // eax
  signed int LastError; // eax
  CStandardInterfaceHandler *v11; // eax
  int v12; // edx
  void *v13; // eax
  int v14; // ecx
  int v15; // esi
  int v16; // ebx
  int v17; // ecx
  void (__thiscall *v18)(_DWORD, _DWORD, int, int, _DWORD); // ecx
  int v19; // ecx
  struct IMediaSample *v20; // ecx
  DWORD v21; // eax
  signed int v22; // eax
  int v23; // ebx
  void (__thiscall *v24)(_DWORD, _DWORD, _DWORD, int, _DWORD, int); // ecx
  int v25; // ebx
  void (__thiscall *v26)(_DWORD, _DWORD, _DWORD, int, _DWORD, int); // ecx
  int v27; // ecx
  int v28; // [esp-4h] [ebp-64h]
  struct IMediaSample *v29; // [esp+8h] [ebp-58h]
  struct VRAM_SURFACE_INFO **v30; // [esp+Ch] [ebp-54h]
  int v31; // [esp+18h] [ebp-48h]
  int i; // [esp+18h] [ebp-48h]
  int j; // [esp+18h] [ebp-48h]
  int v34; // [esp+1Ch] [ebp-44h]
  int SampleProperties; // [esp+20h] [ebp-40h]
  DWORD nOutBufferSize; // [esp+28h] [ebp-38h]
  DWORD BytesReturned; // [esp+2Ch] [ebp-34h] BYREF
  _DWORD v38[4]; // [esp+30h] [ebp-30h] BYREF
  __int64 v39; // [esp+40h] [ebp-20h]
  __int64 v40; // [esp+48h] [ebp-18h]
  int v41; // [esp+58h] [ebp-8h]
  int v42; // [esp+5Ch] [ebp-4h]

  *a6 = 0;
  v6 = (char *)operator new(0x130u);
  if ( !v6 )
  {
    *a4 = 0;
    return -2147024882;
  }
  if ( *a4 <= 64 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_DWORD *)v6 + 3) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v8 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v8 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_q(0xBu, &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v8);
      goto LABEL_10;
    }
    ((void (__thiscall *)(unsigned int (__stdcall *)(struct CStandardInterfaceHandler *), CStandardInterfaceHandler *))this->NonDelegatingAddRef)(
      this->NonDelegatingAddRef,
      this);
    *((_DWORD *)v6 + 1) = a2;
    v11 = this;
    if ( this == (CStandardInterfaceHandler *)12 )
      v11 = 0;
    *(_DWORD *)v6 = v11;
    *((_DWORD *)v6 + 2) = a5;
    if ( a2 )
    {
      ((void (__thiscall *)(HRESULT (__stdcall *)(IKsDataTypeHandler *, unsigned int *), struct IKsDataTypeHandler *, char *))a2->KsQueryExtendedSize)(
        a2->KsQueryExtendedSize,
        a2,
        v6 + 276);
      if ( *((_DWORD *)v6 + 69) )
      {
        (*(void (__thiscall **)(_DWORD, _DWORD))(**((_DWORD **)v6 + 1) + 4))(
          *(_DWORD *)(**((_DWORD **)v6 + 1) + 4),
          *((_DWORD *)v6 + 1));
        v12 = *((_DWORD *)v6 + 69);
        goto LABEL_19;
      }
      *((_DWORD *)v6 + 1) = 0;
    }
    else
    {
      *((_DWORD *)v6 + 69) = 0;
    }
    v12 = 0;
LABEL_19:
    *((_DWORD *)v6 + 68) = *a4;
    nOutBufferSize = *a4 * (v12 + 48);
    v13 = operator new[](nOutBufferSize);
    *((_DWORD *)v6 + 70) = v13;
    if ( !v13 )
    {
      v14 = *((_DWORD *)v6 + 1);
      if ( v14 )
        (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)v14 + 8))(
          *(_DWORD *)(*(_DWORD *)v14 + 8),
          *((_DWORD *)v6 + 1));
      ((void (__thiscall *)(unsigned int (__stdcall *)(struct CStandardInterfaceHandler *), CStandardInterfaceHandler *))this->NonDelegatingRelease)(
        this->NonDelegatingRelease,
        this);
      v8 = -2147024882;
LABEL_55:
      CloseHandle(*((HANDLE *)v6 + 3));
      operator delete(v6, 0x130u);
      *a4 = 0;
      return v8;
    }
    memset(v13, 0, nOutBufferSize);
    v15 = 0;
    v16 = *((_DWORD *)v6 + 70);
    v31 = 0;
    if ( *a4 > 0 )
    {
      while ( 1 )
      {
        v17 = 4 * v15;
        v34 = v15;
        if ( *((_DWORD *)v6 + 69) )
        {
          v28 = *(int *)((char *)a3 + v17);
          v18 = *(void (__thiscall **)(_DWORD, _DWORD, int, int, _DWORD))(**((_DWORD **)v6 + 1) + 20);
          v18(v18, *((_DWORD *)v6 + 1), v28, v16, *((_DWORD *)v6 + 2));
          v15 = v31;
          v17 = v34 * 4;
        }
        else
        {
          v34 = v15;
        }
        SampleProperties = GetSampleProperties(*(_DWORD ***)((char *)a3 + v17), v38);
        if ( SampleProperties < 0 )
          break;
        *(_DWORD *)(v16 + 44) = v38[2];
        *(_DWORD *)v16 = *((_DWORD *)v6 + 69) + 48;
        *(_DWORD *)(v16 + 4) = v38[1];
        v19 = HIDWORD(v39);
        *(_DWORD *)(v16 + 8) = v39;
        *(_DWORD *)(v16 + 12) = v19;
        *(_DWORD *)(v16 + 16) = 1;
        *(_DWORD *)(v16 + 20) = 1;
        *(_QWORD *)(v16 + 24) = v40 - v39;
        *(_DWORD *)(v16 + 40) = v41;
        *(_DWORD *)(v16 + 32) = v42;
        if ( IsD3DMediaSample(v29) )
        {
          SampleProperties = GetVramSurfaceInfo(v29, v30);
          if ( SampleProperties < 0 )
          {
            if ( v15 )
            {
              v23 = -48 - *((_DWORD *)v6 + 69) + v16;
              for ( i = v15 - 1; i >= 0; --i )
              {
                v24 = *(void (__thiscall **)(_DWORD, _DWORD, _DWORD, int, _DWORD, int))(**((_DWORD **)v6 + 1) + 12);
                v24(v24, *((_DWORD *)v6 + 1), *(_DWORD *)&v6[4 * i + 16], v23, *((_DWORD *)v6 + 2), 1);
                v23 += -48 - *((_DWORD *)v6 + 69);
              }
            }
            goto LABEL_52;
          }
          *(_DWORD *)(v16 + 44) |= 0xC00u;
          *(_DWORD *)(v16 + 40) = 0;
          *(_DWORD *)(v16 + 32) = 168;
        }
        if ( a5 == KsIoOperation_Write )
          *(_DWORD *)(v16 + 36) = v38[3];
        v20 = a3[v34];
        *(_DWORD *)&v6[4 * v15 + 16] = v20;
        if ( !*((_DWORD *)v6 + 2) )
        {
          ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), struct IMediaSample *))v20->AddRef)(
            v20->AddRef,
            v20);
          v15 = v31;
        }
        v16 += *((_DWORD *)v6 + 69) + 48;
        v31 = ++v15;
        if ( v15 >= *a4 )
          goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(0xCu, &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
      if ( v15 )
      {
        v25 = -48 - *((_DWORD *)v6 + 69) + v16;
        for ( j = v15 - 1; j >= 0; --j )
        {
          v26 = *(void (__thiscall **)(_DWORD, _DWORD, _DWORD, int, _DWORD, int))(**((_DWORD **)v6 + 1) + 12);
          v26(v26, *((_DWORD *)v6 + 1), *(_DWORD *)&v6[4 * j + 16], v25, *((_DWORD *)v6 + 2), 1);
          v25 += -48 - *((_DWORD *)v6 + 69);
        }
      }
LABEL_52:
      operator delete(*((void **)v6 + 70), 0x30u);
      v27 = *((_DWORD *)v6 + 1);
      if ( v27 )
        (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)v27 + 8))(
          *(_DWORD *)(*(_DWORD *)v27 + 8),
          *((_DWORD *)v6 + 1));
      ((void (__thiscall *)(unsigned int (__stdcall *)(struct CStandardInterfaceHandler *), CStandardInterfaceHandler *))this->NonDelegatingRelease)(
        this->NonDelegatingRelease,
        this);
      v8 = SampleProperties;
      goto LABEL_55;
    }
LABEL_36:
    *((_DWORD *)v6 + 75) = *((_DWORD *)v6 + 3);
    (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)&this->m_ClsID.Data2 + 52))(
      *(_DWORD *)(**(_DWORD **)&this->m_ClsID.Data2 + 52),
      *(_DWORD *)&this->m_ClsID.Data2);
    v21 = 3096599;
    if ( a5 == KsIoOperation_Write )
      v21 = 3112979;
    if ( DeviceIoControl(
           *(HANDLE *)this->m_ClsID.Data4,
           v21,
           0,
           0,
           *((LPVOID *)v6 + 70),
           nOutBufferSize,
           &BytesReturned,
           (LPOVERLAPPED)(v6 + 284)) )
    {
      SetEvent(*((HANDLE *)v6 + 75));
    }
    else
    {
      v22 = GetLastError();
      v8 = (unsigned __int16)v22 | 0x80070000;
      if ( v22 <= 0 )
        v8 = v22;
      if ( v8 != -2147023899 )
      {
        SetEvent(*((HANDLE *)v6 + 75));
LABEL_58:
        *a6 = (struct _KSSTREAM_SEGMENT *)v6;
        return v8;
      }
    }
    v8 = 0;
    goto LABEL_58;
  }
  v8 = -2147024809;
LABEL_10:
  *a4 = 0;
  operator delete(v6, 0x130u);
  return v8;
}

```

## disassembly

```asm
0x10033c90  mov     edi, edi
0x10033c92  push    ebp
0x10033c93  mov     ebp, esp
0x10033c95  and     esp, 0FFFFFFF8h
0x10033c98  mov     eax, [ebp+arg_14]
0x10033c9b  sub     esp, 4Ch
0x10033c9e  push    ebx
0x10033c9f  push    esi; struct VRAM_SURFACE_INFO **
0x10033ca0  push    edi; struct IMediaSample *
0x10033ca1  xor     esi, esi
0x10033ca3  push    130h; Size
0x10033ca8  mov     [eax], esi
0x10033caa  call    ??2@YAPAXI@Z; operator new(uint)
0x10033caf  mov     edi, eax
0x10033cb1  pop     ecx
0x10033cb2  test    edi, edi
0x10033cb4  jnz     short loc_10033CC5
0x10033cb6  mov     eax, [ebp+arg_C]
0x10033cb9  mov     [eax], esi
0x10033cbb  mov     eax, 8007000Eh
0x10033cc0  jmp     loc_1003412E
0x10033cc5  mov     ebx, [ebp+arg_C]
0x10033cc8  cmp     dword ptr [ebx], 40h ; '@'
0x10033ccb  jle     short loc_10033CD4
0x10033ccd  mov     esi, 80070057h
0x10033cd2  jmp     short loc_10033D1A
0x10033cd4  push    esi; lpName
0x10033cd5  push    esi; bInitialState
0x10033cd6  push    1; bManualReset
0x10033cd8  push    esi; lpEventAttributes
0x10033cd9  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10033cdf  mov     [edi+0Ch], eax
0x10033ce2  test    eax, eax
0x10033ce4  jnz     short loc_10033D32
0x10033ce6  call    ds:__imp__GetLastError@0; GetLastError()
0x10033cec  movzx   esi, ax
0x10033cef  or      esi, 80070000h
0x10033cf5  test    eax, eax
0x10033cf7  cmovle  esi, eax
0x10033cfa  mov     eax, _WPP_GLOBAL_Control
0x10033cff  cmp     eax, offset _WPP_GLOBAL_Control
0x10033d04  jz      short loc_10033D1A
0x10033d06  push    esi; char
0x10033d07  push    dword ptr [eax+14h]
0x10033d0a  mov     edx, offset _WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids; MessageGuid
0x10033d0f  push    dword ptr [eax+10h]; LoggerHandle
0x10033d12  push    0Bh
0x10033d14  pop     ecx; MessageNumber
0x10033d15  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10033d1a  push    130h; unsigned int
0x10033d1f  push    edi; Block
0x10033d20  mov     dword ptr [ebx], 0
0x10033d26  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10033d2b  pop     ecx
0x10033d2c  pop     ecx
0x10033d2d  jmp     loc_1003412C
0x10033d32  mov     ebx, [ebp+this]
0x10033d35  push    ebx
0x10033d36  mov     eax, [ebx]
0x10033d38  mov     esi, [eax+4]
0x10033d3b  mov     ecx, esi; this
0x10033d3d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033d43  call    esi
0x10033d45  mov     edx, [ebp+arg_4]
0x10033d48  xor     ecx, ecx
0x10033d4a  cmp     ebx, 0Ch
0x10033d4d  mov     [edi+4], edx
0x10033d50  mov     eax, ebx
0x10033d52  cmovz   eax, ecx
0x10033d55  lea     ecx, [edi+114h]
0x10033d5b  mov     [edi], eax
0x10033d5d  mov     eax, [ebp+arg_10]
0x10033d60  mov     [edi+8], eax
0x10033d63  test    edx, edx
0x10033d65  jz      short loc_10033DA5
0x10033d67  mov     eax, [edx]
0x10033d69  push    ecx
0x10033d6a  push    edx
0x10033d6b  mov     esi, [eax+18h]
0x10033d6e  mov     ecx, esi; this
0x10033d70  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033d76  call    esi
0x10033d78  cmp     dword ptr [edi+114h], 0
0x10033d7f  jz      short loc_10033D9C
0x10033d81  mov     eax, [edi+4]
0x10033d84  push    eax
0x10033d85  mov     ecx, [eax]
0x10033d87  mov     esi, [ecx+4]
0x10033d8a  mov     ecx, esi; this
0x10033d8c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033d92  call    esi
0x10033d94  mov     edx, [edi+114h]
0x10033d9a  jmp     short loc_10033DAD
0x10033d9c  mov     dword ptr [edi+4], 0
0x10033da3  jmp     short loc_10033DAB
0x10033da5  mov     dword ptr [ecx], 0
0x10033dab  xor     edx, edx
0x10033dad  mov     ecx, [ebp+arg_C]
0x10033db0  lea     esi, [edx+30h]
0x10033db3  mov     eax, [ecx]
0x10033db5  mov     [edi+110h], eax
0x10033dbb  imul    esi, [ecx]
0x10033dbe  push    esi; unsigned int
0x10033dbf  mov     [esp+5Ch+nOutBufferSize], esi
0x10033dc3  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10033dc8  mov     [edi+118h], eax
0x10033dce  pop     ecx
0x10033dcf  test    eax, eax
0x10033dd1  jnz     short loc_10033E04
0x10033dd3  mov     ecx, [edi+4]
0x10033dd6  test    ecx, ecx
0x10033dd8  jz      short loc_10033DEA
0x10033dda  mov     eax, [ecx]
0x10033ddc  push    ecx
0x10033ddd  mov     esi, [eax+8]
0x10033de0  mov     ecx, esi; this
0x10033de2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033de8  call    esi
0x10033dea  mov     eax, [ebx]
0x10033dec  push    ebx
0x10033ded  mov     esi, [eax+8]
0x10033df0  mov     ecx, esi; this
0x10033df2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033df8  call    esi
0x10033dfa  mov     esi, 8007000Eh
0x10033dff  jmp     loc_100340F8
0x10033e04  push    esi; Size
0x10033e05  push    0; Val
0x10033e07  push    eax; void *
0x10033e08  call    _memset
0x10033e0d  mov     eax, [ebp+arg_C]
0x10033e10  xor     esi, esi
0x10033e12  mov     ebx, [edi+118h]
0x10033e18  add     esp, 0Ch
0x10033e1b  mov     [esp+58h+var_48], esi
0x10033e1f  cmp     [eax], esi
0x10033e21  jle     loc_10033F71
0x10033e27  mov     ecx, esi
0x10033e29  shl     ecx, 2
0x10033e2c  cmp     dword ptr [edi+114h], 0
0x10033e33  mov     [esp+58h+var_44], ecx
0x10033e37  jz      short loc_10033E5F
0x10033e39  mov     eax, [edi+4]
0x10033e3c  push    dword ptr [edi+8]
0x10033e3f  mov     edx, [ebp+arg_8]
0x10033e42  push    ebx
0x10033e43  mov     esi, [eax]
0x10033e45  push    dword ptr [ecx+edx]
0x10033e48  mov     ecx, [esi+14h]; this
0x10033e4b  push    eax
0x10033e4c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033e52  call    dword ptr [esi+14h]
0x10033e55  mov     esi, [esp+58h+var_48]
0x10033e59  mov     ecx, [esp+58h+var_44]
0x10033e5d  jmp     short loc_10033E63
0x10033e5f  mov     [esp+58h+var_44], ecx
0x10033e63  mov     eax, [ebp+arg_8]
0x10033e66  lea     edx, [esp+58h+var_30]
0x10033e6a  mov     ecx, [eax+ecx]
0x10033e6d  call    ?GetSampleProperties@@YGJPAUIMediaSample@@PAUtagAM_SAMPLE2_PROPERTIES@@@Z; GetSampleProperties(IMediaSample *,tagAM_SAMPLE2_PROPERTIES *)
0x10033e72  mov     [esp+58h+var_40], eax
0x10033e76  test    eax, eax
0x10033e78  js      loc_10034052
0x10033e7e  mov     eax, [esp+58h+var_28]
0x10033e82  mov     [ebx+2Ch], eax
0x10033e85  mov     eax, [edi+114h]
0x10033e8b  add     eax, 30h ; '0'
0x10033e8e  mov     [ebx], eax
0x10033e90  mov     eax, [esp+58h+var_2C]
0x10033e94  mov     [ebx+4], eax
0x10033e97  mov     eax, dword ptr [esp+58h+var_20]
0x10033e9b  mov     ecx, dword ptr [esp+58h+var_20+4]
0x10033e9f  mov     [ebx+8], eax
0x10033ea2  xor     eax, eax
0x10033ea4  inc     eax
0x10033ea5  mov     [ebx+0Ch], ecx
0x10033ea8  mov     [ebx+10h], eax
0x10033eab  mov     [ebx+14h], eax
0x10033eae  mov     ecx, dword ptr [esp+58h+var_18]
0x10033eb2  sub     ecx, dword ptr [esp+58h+var_20]
0x10033eb6  mov     eax, dword ptr [esp+58h+var_18+4]
0x10033eba  sbb     eax, dword ptr [esp+58h+var_20+4]
0x10033ebe  mov     [ebx+18h], ecx
0x10033ec1  mov     ecx, [esp+58h+var_44]
0x10033ec5  mov     [ebx+1Ch], eax
0x10033ec8  mov     eax, [esp+58h+var_8]
0x10033ecc  mov     [ebx+28h], eax
0x10033ecf  mov     eax, [esp+58h+var_4]
0x10033ed3  mov     [ebx+20h], eax
0x10033ed6  mov     eax, [ebp+arg_8]
0x10033ed9  mov     ecx, [eax+ecx]
0x10033edc  call    ?IsD3DMediaSample@@YGHPAUIMediaSample@@@Z; IsD3DMediaSample(IMediaSample *)
0x10033ee1  test    eax, eax
0x10033ee3  jz      short loc_10033F21
0x10033ee5  mov     eax, [esp+58h+var_44]
0x10033ee9  lea     edx, [esp+58h+var_3C]
0x10033eed  mov     ecx, [ebp+arg_8]
0x10033ef0  mov     [esp+58h+var_3C], 0
0x10033ef8  mov     ecx, [ecx+eax]
0x10033efb  call    ?GetVramSurfaceInfo@@YGJPAUIMediaSample@@PAPAUVRAM_SURFACE_INFO@@@Z; GetVramSurfaceInfo(IMediaSample *,VRAM_SURFACE_INFO * *)
0x10033f00  mov     [esp+58h+var_40], eax
0x10033f04  test    eax, eax
0x10033f06  js      loc_10033FFE
0x10033f0c  mov     eax, [esp+58h+var_3C]
0x10033f10  or      dword ptr [ebx+2Ch], 0C00h
0x10033f17  mov     [ebx+28h], eax
0x10033f1a  mov     dword ptr [ebx+20h], 0A8h
0x10033f21  cmp     [ebp+arg_10], 0
0x10033f25  jnz     short loc_10033F2E
0x10033f27  mov     eax, [esp+58h+var_24]
0x10033f2b  mov     [ebx+24h], eax
0x10033f2e  mov     eax, [esp+58h+var_44]
0x10033f32  mov     ecx, [ebp+arg_8]
0x10033f35  mov     ecx, [ecx+eax]
0x10033f38  mov     [edi+esi*4+10h], ecx
0x10033f3c  cmp     dword ptr [edi+8], 0
0x10033f40  jnz     short loc_10033F56
0x10033f42  mov     eax, [ecx]
0x10033f44  push    ecx
0x10033f45  mov     esi, [eax+4]
0x10033f48  mov     ecx, esi; this
0x10033f4a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033f50  call    esi
0x10033f52  mov     esi, [esp+58h+var_48]
0x10033f56  mov     eax, [edi+114h]
0x10033f5c  add     eax, 30h ; '0'
0x10033f5f  add     ebx, eax
0x10033f61  mov     eax, [ebp+arg_C]
0x10033f64  inc     esi
0x10033f65  mov     [esp+58h+var_48], esi
0x10033f69  cmp     esi, [eax]
0x10033f6b  jl      loc_10033E27
0x10033f71  mov     ebx, [ebp+this]
0x10033f74  mov     eax, [edi+0Ch]
0x10033f77  mov     [edi+12Ch], eax
0x10033f7d  mov     eax, [ebx+14h]
0x10033f80  push    eax
0x10033f81  mov     ecx, [eax]
0x10033f83  mov     esi, [ecx+34h]
0x10033f86  mov     ecx, esi; this
0x10033f88  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033f8e  call    esi
0x10033f90  cmp     [ebp+arg_10], 0
0x10033f94  lea     eax, [edi+11Ch]
0x10033f9a  push    eax; lpOverlapped
0x10033f9b  lea     eax, [esp+5Ch+BytesReturned]
0x10033f9f  mov     ecx, 2F8013h
0x10033fa4  push    eax; lpBytesReturned
0x10033fa5  push    [esp+60h+nOutBufferSize]; nOutBufferSize
0x10033fa9  mov     eax, 2F4017h
0x10033fae  push    dword ptr [edi+118h]; lpOutBuffer
0x10033fb4  cmovz   eax, ecx
0x10033fb7  push    0; nInBufferSize
0x10033fb9  push    0; lpInBuffer
0x10033fbb  push    eax; dwIoControlCode
0x10033fbc  push    dword ptr [ebx+18h]; hDevice
0x10033fbf  call    ds:__imp__DeviceIoControl@32; DeviceIoControl(x,x,x,x,x,x,x,x)
0x10033fc5  test    eax, eax
0x10033fc7  jnz     loc_10034119
0x10033fcd  call    ds:__imp__GetLastError@0; GetLastError()
0x10033fd3  movzx   esi, ax
0x10033fd6  or      esi, 80070000h
0x10033fdc  test    eax, eax
0x10033fde  cmovle  esi, eax
0x10033fe1  cmp     esi, 800703E5h
0x10033fe7  jz      loc_10034125
0x10033fed  push    dword ptr [edi+12Ch]; hEvent
0x10033ff3  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10033ff9  jmp     loc_10034127
0x10033ffe  test    esi, esi
0x10034000  jz      loc_100340BB
0x10034006  push    0FFFFFFD0h
0x10034008  pop     eax
0x10034009  sub     eax, [edi+114h]
0x1003400f  add     ebx, eax
0x10034011  sub     esi, 1
0x10034014  mov     [esp+58h+var_48], esi
0x10034018  js      loc_100340BB
0x1003401e  mov     eax, [edi+4]
0x10034021  mov     ecx, [esp+58h+var_48]
0x10034025  push    1
0x10034027  push    dword ptr [edi+8]
0x1003402a  mov     esi, [eax]
0x1003402c  push    ebx
0x1003402d  push    dword ptr [edi+ecx*4+10h]
0x10034031  mov     ecx, [esi+0Ch]; this
0x10034034  push    eax
0x10034035  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003403b  call    dword ptr [esi+0Ch]
0x1003403e  push    0FFFFFFD0h
0x10034040  pop     eax
0x10034041  sub     eax, [edi+114h]
0x10034047  add     ebx, eax
0x10034049  sub     [esp+58h+var_48], 1
0x1003404e  jns     short loc_1003401E
0x10034050  jmp     short loc_100340BB
0x10034052  mov     eax, _WPP_GLOBAL_Control
0x10034057  cmp     eax, offset _WPP_GLOBAL_Control
0x1003405c  jz      short loc_10034071
0x1003405e  push    dword ptr [eax+14h]
  ... truncated ...
```
