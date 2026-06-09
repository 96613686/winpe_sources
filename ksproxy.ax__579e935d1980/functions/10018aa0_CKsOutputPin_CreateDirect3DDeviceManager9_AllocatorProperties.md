# CKsOutputPin::CreateDirect3DDeviceManager9(_AllocatorProperties *)

- ea: `0x10018aa0`
- end: `0x10018e58`
- name: `?CreateDirect3DDeviceManager9@CKsOutputPin@@UAGJPAU_AllocatorProperties@@@Z`
- size: `952`
- prototype: `int(CKsOutputPin *__hidden this, struct _AllocatorProperties *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x10018aa0`
- `0x1002c393`
- `0x1002c59f`
- `0x1002d510`
- `0x1003aba0`
- `0x1003b5e4`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x10018c9a`
- `USER32!GetDesktopWindow` at `0x10018cbd`
- `USER32!GetDesktopWindow` at `0x10018c9a`
- `USER32!GetDesktopWindow` at `0x10018cbd`
- `d3d9!Direct3DCreate9Ex` at `0x10018b26`
- `d3d9!Direct3DCreate9Ex` at `0x10018b26`

## pseudocode

```c
int __stdcall CKsOutputPin::CreateDirect3DDeviceManager9(CKsOutputPin *this, struct _AllocatorProperties *a2)
{
  CKsOutputPin *v2; // esi
  unsigned int *p_m_IoThreadId; // ebx
  unsigned int m_IoThreadId; // ecx
  int v5; // eax
  int v6; // edi
  PVOID *v7; // ecx
  int PresentationParametersFromMediaType; // eax
  unsigned int m_IoThreadSemaphore; // edx
  int v10; // eax
  int v11; // eax
  int v12; // edi
  int (__thiscall *v13)(_DWORD, int *, unsigned int, int, HWND, int, unsigned __int8 *, _DWORD, int *); // esi
  HWND DesktopWindow; // eax
  int v15; // ecx
  int v16; // eax
  int DXVA2DeviceManager; // eax
  unsigned int *v19; // [esp+40h] [ebp-198h]
  int *v20; // [esp+44h] [ebp-194h]
  int *v21; // [esp+4Ch] [ebp-18Ch] BYREF
  int v22; // [esp+50h] [ebp-188h] BYREF
  unsigned int p_m_DataTypeHandler; // [esp+54h] [ebp-184h] BYREF
  CKsOutputPin *v24; // [esp+58h] [ebp-180h]
  struct CMediaType v25; // [esp+5Ch] [ebp-17Ch] BYREF
  int v26; // [esp+BCh] [ebp-11Ch]

  v2 = this;
  v24 = this;
  v21 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(0x3Cu, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
  p_m_IoThreadId = &this->m_IoThreadId;
  v25.majortype.Data1 = 0;
  m_IoThreadId = this->m_IoThreadId;
  *(_DWORD *)&v25.majortype.Data2 = 0;
  if ( m_IoThreadId )
  {
    *p_m_IoThreadId = 0;
    (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)m_IoThreadId + 8))(
      *(_DWORD *)(*(_DWORD *)m_IoThreadId + 8),
      m_IoThreadId);
    v2 = v24;
  }
  v5 = Direct3DCreate9Ex(31, &v21);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( a2->cbBuffer > 0 )
    {
      ((void (__thiscall *)(HRESULT (__thiscall *)(struct CKsOutputPin *), CKsOutputPin *))v2->BreakConnect)(
        v2->BreakConnect,
        v2);
      PresentationParametersFromMediaType = GetPresentationParametersFromMediaType(
                                              &v25,
                                              (unsigned int)&v25.majortype.Data2,
                                              (unsigned int *)v25.majortype.Data4,
                                              &p_m_DataTypeHandler,
                                              v19,
                                              v20);
      v6 = PresentationParametersFromMediaType;
      if ( PresentationParametersFromMediaType >= 0 )
      {
        memset(&v25.majortype.Data4[4], 0, 0x38u);
        m_IoThreadSemaphore = (unsigned int)v24->m_IoThreadSemaphore;
        if ( m_IoThreadSemaphore == -1 )
          m_IoThreadSemaphore = 0;
        v10 = *v21;
        p_m_DataTypeHandler = m_IoThreadSemaphore;
        v11 = (*(int (__thiscall **)(_DWORD, int *, unsigned int, int, unsigned __int8 **))(v10 + 56))(
                *(_DWORD *)(v10 + 56),
                v21,
                m_IoThreadSemaphore,
                1,
                &v25.pbFormat);
        v6 = v11;
        if ( v11 >= 0 )
        {
          v12 = v26;
          *(_DWORD *)&v25.majortype.Data4[4] = v25.majortype.Data1;
          *(_DWORD *)v25.subtype.Data4 = 1;
          v25.subtype.Data1 = *(_DWORD *)&v25.majortype.Data2;
          v25.formattype.Data1 = 1;
          v25.bTemporalCompression = 1;
          *(_DWORD *)&v25.subtype.Data2 = 0;
          v25.lSampleSize = (unsigned int)GetDesktopWindow();
          v25.cbFormat = 0;
          *(_DWORD *)&v25.formattype.Data4[4] = 16;
          v13 = *(int (__thiscall **)(_DWORD, int *, unsigned int, int, HWND, int, unsigned __int8 *, _DWORD, int *))(*v21 + 80);
          DesktopWindow = GetDesktopWindow();
          v15 = 38;
          if ( (v12 & 0x10000) != 0 )
            v15 = 70;
          v16 = v13(v13, v21, p_m_DataTypeHandler, 1, DesktopWindow, v15, &v25.majortype.Data4[4], 0, &v22);
          v6 = v16;
          if ( v16 >= 0 )
          {
            p_m_DataTypeHandler = (unsigned int)&v24->m_DataTypeHandler;
            DXVA2DeviceManager = CreateDXVA2DeviceManager((int)p_m_IoThreadId, (int)&v24->m_DataTypeHandler);
            v6 = DXVA2DeviceManager;
            if ( DXVA2DeviceManager >= 0 )
            {
              v6 = (*(int (__thiscall **)(_DWORD, unsigned int, int, _DWORD))(*(_DWORD *)*p_m_IoThreadId + 12))(
                     *(_DWORD *)(*(_DWORD *)*p_m_IoThreadId + 12),
                     *p_m_IoThreadId,
                     v22,
                     *(_DWORD *)p_m_DataTypeHandler);
              if ( v6 >= 0 )
                goto LABEL_40;
              if ( *p_m_IoThreadId )
              {
                (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)*p_m_IoThreadId + 8))(
                  *(_DWORD *)(*(_DWORD *)*p_m_IoThreadId + 8),
                  *p_m_IoThreadId);
                *p_m_IoThreadId = 0;
              }
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_q(
                  0x43u,
                  &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v6);
                goto LABEL_40;
              }
            }
            else
            {
              *p_m_IoThreadId = 0;
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_q(
                  0x42u,
                  &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  DXVA2DeviceManager);
                goto LABEL_40;
              }
            }
          }
          else
          {
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_q(
                0x41u,
                &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v16);
              goto LABEL_40;
            }
          }
        }
        else
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_q(0x40u, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v11);
            goto LABEL_40;
          }
        }
      }
      else
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_q(
            0x3Fu,
            &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            PresentationParametersFromMediaType);
          goto LABEL_40;
        }
      }
    }
    else
    {
      v6 = -2147467259;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(0x3Eu, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
        goto LABEL_40;
      }
    }
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_q(0x3Du, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v5);
LABEL_40:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v21 )
  {
    (*(void (__thiscall **)(_DWORD, int *))(*v21 + 8))(*(_DWORD *)(*v21 + 8), v21);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v22 + 8))(*(_DWORD *)(*(_DWORD *)v22 + 8), v22);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v22 = 0;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 3u )
    WPP_SF_q(0x44u, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)v7 + 2), v6);
  return v6;
}

```

## disassembly

```asm
0x10018aa0  mov     edi, edi
0x10018aa2  push    ebp
0x10018aa3  mov     ebp, esp
0x10018aa5  and     esp, 0FFFFFFF8h
0x10018aa8  sub     esp, 18Ch
0x10018aae  mov     eax, ___security_cookie
0x10018ab3  xor     eax, esp
0x10018ab5  mov     [esp+18Ch+var_4], eax
0x10018abc  push    ebx
0x10018abd  push    esi; unsigned int *
0x10018abe  mov     esi, [ebp+this]
0x10018ac1  push    edi; struct IDirect3DDeviceManager9 **
0x10018ac2  xor     edi, edi
0x10018ac4  mov     [esp+198h+var_180], esi
0x10018ac8  mov     [esp+198h+var_18C], edi
0x10018acc  mov     [esp+198h+var_188], edi
0x10018ad0  mov     eax, _WPP_GLOBAL_Control
0x10018ad5  cmp     eax, offset _WPP_GLOBAL_Control
0x10018ada  jz      short loc_10018AF5
0x10018adc  cmp     byte ptr [eax+19h], 3
0x10018ae0  jb      short loc_10018AF5
0x10018ae2  push    dword ptr [eax+14h]
0x10018ae5  mov     edx, offset _WPP_673e2124b19330a2d80119fad92a0606_Traceguids; MessageGuid
0x10018aea  push    dword ptr [eax+10h]; LoggerHandle
0x10018aed  push    3Ch ; '<'
0x10018aef  pop     ecx; MessageNumber
0x10018af0  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10018af5  lea     ebx, [esi+174h]
0x10018afb  mov     [esp+198h+var_17C.majortype.Data1], edi
0x10018aff  mov     ecx, [ebx]
0x10018b01  mov     dword ptr [esp+198h+var_17C.majortype.Data2], edi
0x10018b05  test    ecx, ecx
0x10018b07  jz      short loc_10018B1F
0x10018b09  mov     [ebx], edi
0x10018b0b  mov     eax, [ecx]
0x10018b0d  push    ecx
0x10018b0e  mov     esi, [eax+8]
0x10018b11  mov     ecx, esi; this
0x10018b13  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018b19  call    esi
0x10018b1b  mov     esi, [esp+198h+var_180]
0x10018b1f  lea     eax, [esp+198h+var_18C]
0x10018b23  push    eax
0x10018b24  push    1Fh
0x10018b26  call    ds:__imp__Direct3DCreate9Ex@8; Direct3DCreate9Ex(x,x)
0x10018b2c  mov     edi, eax
0x10018b2e  test    edi, edi
0x10018b30  jns     short loc_10018B5C
0x10018b32  mov     ecx, _WPP_GLOBAL_Control
0x10018b38  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018b3e  jz      loc_10018DD1
0x10018b44  cmp     byte ptr [ecx+19h], 3
0x10018b48  jb      loc_10018DD1
0x10018b4e  push    edi
0x10018b4f  push    dword ptr [ecx+14h]
0x10018b52  push    dword ptr [ecx+10h]
0x10018b55  push    3Dh ; '='
0x10018b57  jmp     loc_10018DC0
0x10018b5c  mov     eax, [ebp+arg_4]
0x10018b5f  mov     edi, [eax+4]
0x10018b62  test    edi, edi
0x10018b64  jg      short loc_10018B9F
0x10018b66  mov     edi, 80004005h
0x10018b6b  mov     ecx, _WPP_GLOBAL_Control
0x10018b71  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018b77  jz      loc_10018DD1
0x10018b7d  cmp     byte ptr [ecx+19h], 3
0x10018b81  jb      loc_10018DD1
0x10018b87  push    dword ptr [ecx+14h]
0x10018b8a  mov     edx, offset _WPP_673e2124b19330a2d80119fad92a0606_Traceguids; MessageGuid
0x10018b8f  push    dword ptr [ecx+10h]; LoggerHandle
0x10018b92  push    3Eh ; '>'
0x10018b94  pop     ecx; MessageNumber
0x10018b95  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10018b9a  jmp     loc_10018DCB
0x10018b9f  mov     eax, [esi]
0x10018ba1  push    esi
0x10018ba2  mov     esi, [eax+2Ch]
0x10018ba5  mov     ecx, esi; this
0x10018ba7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018bad  call    esi
0x10018baf  lea     ecx, [esp+198h+var_184]
0x10018bb3  mov     edx, edi
0x10018bb5  push    ecx; unsigned int *
0x10018bb6  lea     ecx, [esp+19Ch+var_17C.majortype.Data4]
0x10018bba  push    ecx; unsigned int *
0x10018bbb  lea     ecx, [esp+1A0h+var_17C.majortype.Data2]
0x10018bbf  push    ecx; unsigned int
0x10018bc0  lea     ecx, [esp+1A4h+var_17C]
0x10018bc4  push    ecx; struct CMediaType *
0x10018bc5  mov     ecx, eax
0x10018bc7  call    ?GetPresentationParametersFromMediaType@@YGJPAVCMediaType@@KPAK11PAH@Z; GetPresentationParametersFromMediaType(CMediaType *,ulong,ulong *,ulong *,ulong *,int *)
0x10018bcc  mov     edi, eax
0x10018bce  test    edi, edi
0x10018bd0  jns     short loc_10018BFC
0x10018bd2  mov     ecx, _WPP_GLOBAL_Control
0x10018bd8  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018bde  jz      loc_10018DD1
0x10018be4  cmp     byte ptr [ecx+19h], 3
0x10018be8  jb      loc_10018DD1
0x10018bee  push    edi
0x10018bef  push    dword ptr [ecx+14h]
0x10018bf2  push    dword ptr [ecx+10h]
0x10018bf5  push    3Fh ; '?'
0x10018bf7  jmp     loc_10018DC0
0x10018bfc  push    38h ; '8'; Size
0x10018bfe  lea     eax, [esp+19Ch+var_17C.majortype.Data4+4]
0x10018c02  push    0; Val
0x10018c04  push    eax; void *
0x10018c05  call    _memset
0x10018c0a  mov     eax, [esp+1A4h+var_180]
0x10018c0e  add     esp, 0Ch
0x10018c11  mov     ecx, [esp+198h+var_18C]
0x10018c15  mov     edx, [eax+170h]
0x10018c1b  xor     eax, eax
0x10018c1d  cmp     edx, 0FFFFFFFFh
0x10018c20  cmovz   edx, eax
0x10018c23  mov     eax, [ecx]
0x10018c25  mov     [esp+198h+var_184], edx
0x10018c29  mov     esi, [eax+38h]
0x10018c2c  lea     eax, [esp+198h+var_17C.pbFormat]
0x10018c30  push    eax
0x10018c31  push    1
0x10018c33  push    edx
0x10018c34  push    ecx
0x10018c35  mov     ecx, esi; this
0x10018c37  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018c3d  call    esi
0x10018c3f  mov     edi, eax
0x10018c41  test    edi, edi
0x10018c43  jns     short loc_10018C6F
0x10018c45  mov     ecx, _WPP_GLOBAL_Control
0x10018c4b  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018c51  jz      loc_10018DD1
0x10018c57  cmp     byte ptr [ecx+19h], 3
0x10018c5b  jb      loc_10018DD1
0x10018c61  push    edi
0x10018c62  push    dword ptr [ecx+14h]
0x10018c65  push    dword ptr [ecx+10h]
0x10018c68  push    40h ; '@'
0x10018c6a  jmp     loc_10018DC0
0x10018c6f  mov     eax, [esp+198h+var_17C.majortype.Data1]
0x10018c73  xor     ecx, ecx
0x10018c75  mov     edi, [esp+198h+var_11C]
0x10018c79  inc     ecx
0x10018c7a  mov     dword ptr [esp+198h+var_17C.majortype.Data4+4], eax
0x10018c7e  mov     eax, dword ptr [esp+198h+var_17C.majortype.Data2]
0x10018c82  mov     dword ptr [esp+198h+var_17C.subtype.Data4], ecx
0x10018c86  mov     [esp+198h+var_17C.subtype.Data1], eax
0x10018c8a  mov     [esp+198h+var_17C.formattype.Data1], ecx
0x10018c8e  mov     [esp+198h+var_17C.bTemporalCompression], ecx
0x10018c92  mov     dword ptr [esp+198h+var_17C.subtype.Data2], 0
0x10018c9a  call    ds:__imp__GetDesktopWindow@0; GetDesktopWindow()
0x10018ca0  mov     [esp+198h+var_17C.lSampleSize], eax
0x10018ca4  mov     eax, [esp+198h+var_18C]
0x10018ca8  mov     [esp+198h+var_17C.cbFormat], 0
0x10018cb0  mov     dword ptr [esp+198h+var_17C.formattype.Data4+4], 10h
0x10018cb8  mov     eax, [eax]
0x10018cba  mov     esi, [eax+50h]
0x10018cbd  call    ds:__imp__GetDesktopWindow@0; GetDesktopWindow()
0x10018cc3  lea     ecx, [esp+198h+var_188]
0x10018cc7  test    edi, 10000h
0x10018ccd  push    ecx
0x10018cce  push    0
0x10018cd0  lea     ecx, [esp+1A0h+var_17C.majortype.Data4+4]
0x10018cd4  push    ecx
0x10018cd5  push    26h ; '&'
0x10018cd7  pop     ecx
0x10018cd8  push    46h ; 'F'
0x10018cda  pop     edx
0x10018cdb  cmovnz  ecx, edx
0x10018cde  push    ecx
0x10018cdf  push    eax
0x10018ce0  push    1
0x10018ce2  push    [esp+1B0h+var_184]
0x10018ce6  mov     ecx, esi; this
0x10018ce8  push    [esp+1B4h+var_18C]
0x10018cec  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018cf2  call    esi
0x10018cf4  mov     edi, eax
0x10018cf6  test    edi, edi
0x10018cf8  jns     short loc_10018D24
0x10018cfa  mov     ecx, _WPP_GLOBAL_Control
0x10018d00  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018d06  jz      loc_10018DD1
0x10018d0c  cmp     byte ptr [ecx+19h], 3
0x10018d10  jb      loc_10018DD1
0x10018d16  push    edi
0x10018d17  push    dword ptr [ecx+14h]
0x10018d1a  push    dword ptr [ecx+10h]
0x10018d1d  push    41h ; 'A'
0x10018d1f  jmp     loc_10018DC0
0x10018d24  mov     eax, [esp+198h+var_180]
0x10018d28  mov     ecx, ebx
0x10018d2a  add     eax, 178h
0x10018d2f  mov     edx, eax
0x10018d31  mov     [esp+198h+var_184], eax
0x10018d35  call    ?CreateDXVA2DeviceManager@@YGJPAPAUIDirect3DDeviceManager9@@PAI@Z; CreateDXVA2DeviceManager(IDirect3DDeviceManager9 * *,uint *)
0x10018d3a  mov     edi, eax
0x10018d3c  test    edi, edi
0x10018d3e  jns     short loc_10018D65
0x10018d40  mov     dword ptr [ebx], 0
0x10018d46  mov     ecx, _WPP_GLOBAL_Control
0x10018d4c  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018d52  jz      short loc_10018DD1
0x10018d54  cmp     byte ptr [ecx+19h], 3
0x10018d58  jb      short loc_10018DD1
0x10018d5a  push    edi
0x10018d5b  push    dword ptr [ecx+14h]
0x10018d5e  push    dword ptr [ecx+10h]
0x10018d61  push    42h ; 'B'
0x10018d63  jmp     short loc_10018DC0
0x10018d65  mov     ecx, [ebx]
0x10018d67  mov     eax, [ecx]
0x10018d69  mov     esi, [eax+0Ch]
0x10018d6c  mov     eax, [esp+198h+var_184]
0x10018d70  push    dword ptr [eax]
0x10018d72  push    [esp+19Ch+var_188]
0x10018d76  push    ecx
0x10018d77  mov     ecx, esi; this
0x10018d79  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018d7f  call    esi
0x10018d81  mov     edi, eax
0x10018d83  test    edi, edi
0x10018d85  jns     short loc_10018DCB
0x10018d87  mov     ecx, [ebx]
0x10018d89  test    ecx, ecx
0x10018d8b  jz      short loc_10018DA3
0x10018d8d  mov     eax, [ecx]
0x10018d8f  push    ecx
0x10018d90  mov     esi, [eax+8]
0x10018d93  mov     ecx, esi; this
0x10018d95  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018d9b  call    esi
0x10018d9d  mov     dword ptr [ebx], 0
0x10018da3  mov     ecx, _WPP_GLOBAL_Control
0x10018da9  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018daf  jz      short loc_10018DD1
0x10018db1  cmp     byte ptr [ecx+19h], 3
0x10018db5  jb      short loc_10018DD1
0x10018db7  push    edi; char
0x10018db8  push    dword ptr [ecx+14h]
0x10018dbb  push    dword ptr [ecx+10h]; LoggerHandle
0x10018dbe  push    43h ; 'C'
0x10018dc0  mov     edx, offset _WPP_673e2124b19330a2d80119fad92a0606_Traceguids; MessageGuid
0x10018dc5  pop     ecx; MessageNumber
0x10018dc6  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10018dcb  mov     ecx, _WPP_GLOBAL_Control
0x10018dd1  mov     edx, [esp+198h+var_18C]
0x10018dd5  test    edx, edx
0x10018dd7  jz      short loc_10018DF7
0x10018dd9  mov     eax, [edx]
0x10018ddb  push    edx
0x10018ddc  mov     esi, [eax+8]
0x10018ddf  mov     ecx, esi; this
0x10018de1  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018de7  call    esi
0x10018de9  mov     ecx, _WPP_GLOBAL_Control
0x10018def  mov     [esp+198h+var_18C], 0
0x10018df7  mov     edx, [esp+198h+var_188]
0x10018dfb  test    edx, edx
0x10018dfd  jz      short loc_10018E1D
0x10018dff  mov     eax, [edx]
0x10018e01  push    edx
0x10018e02  mov     esi, [eax+8]
0x10018e05  mov     ecx, esi; this
0x10018e07  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10018e0d  call    esi
0x10018e0f  mov     ecx, _WPP_GLOBAL_Control
0x10018e15  mov     [esp+198h+var_188], 0
0x10018e1d  cmp     ecx, offset _WPP_GLOBAL_Control
0x10018e23  jz      short loc_10018E3F
0x10018e25  cmp     byte ptr [ecx+19h], 3
0x10018e29  jb      short loc_10018E3F
0x10018e2b  push    edi; char
0x10018e2c  push    dword ptr [ecx+14h]
0x10018e2f  mov     edx, offset _WPP_673e2124b19330a2d80119fad92a0606_Traceguids; MessageGuid
0x10018e34  push    dword ptr [ecx+10h]; LoggerHandle
0x10018e37  push    44h ; 'D'
0x10018e39  pop     ecx; MessageNumber
0x10018e3a  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10018e3f  mov     ecx, [esp+198h+var_4]
0x10018e46  mov     eax, edi
0x10018e48  pop     edi
0x10018e49  pop     esi
0x10018e4a  pop     ebx
0x10018e4b  xor     ecx, esp; StackCookie
0x10018e4d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10018e52  mov     esp, ebp
0x10018e54  pop     ebp
0x10018e55  retn    8
```
