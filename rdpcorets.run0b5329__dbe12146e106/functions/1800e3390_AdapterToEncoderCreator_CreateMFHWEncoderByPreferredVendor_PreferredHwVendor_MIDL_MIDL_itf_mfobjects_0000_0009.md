# AdapterToEncoderCreator::CreateMFHWEncoderByPreferredVendor(PreferredHwVendor,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,ushort * &)

- ea: `0x1800e3390`
- end: `0x1800e3841`
- name: `?CreateMFHWEncoderByPreferredVendor@AdapterToEncoderCreator@@QEAAJW4PreferredHwVendor@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@AEAPEAG@Z`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800e3850`

## callees

- `0x1800015f0`
- `0x180033da0`
- `0x1800348e0`
- `0x180034970`
- `0x1800598d0`
- `0x1800da1b0`
- `0x1800e3390`
- `0x1800e3ff0`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e342b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e348a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e34c2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e342b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e348a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e34c2`

## string_xrefs

- `0x1800e364c`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e376a`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e37f4`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e3640`: `CreateMFHWEncoderByPreferredVendor`
- `0x1800e375a`: `CreateMFHWEncoderByPreferredVendor`
- `0x1800e37e8`: `CreateMFHWEncoderByPreferredVendor`

## pseudocode

```c
__int64 __fastcall AdapterToEncoderCreator::CreateMFHWEncoderByPreferredVendor(
        __int64 a1,
        int a2,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a3,
        struct IMFTransform **a4,
        unsigned __int16 **a5)
{
  int ActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  int HWEncoderByLuid; // ebx
  unsigned int v13; // esi
  unsigned int v14; // r14d
  unsigned __int64 v15; // r12
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  bool v22; // zf
  char *v23; // rdx
  const char *v24; // rax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, struct IDXGIAdapter4 **); // rcx
  struct IDXGIAdapter4 *v26; // rcx
  int v28; // [rsp+58h] [rbp-B0h] BYREF
  int v29; // [rsp+5Ch] [rbp-ACh] BYREF
  struct IMFTransform **v30; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 **v31; // [rsp+68h] [rbp-A0h] BYREF
  struct IDXGIAdapter4 *v32; // [rsp+70h] [rbp-98h] BYREF
  const char *v33; // [rsp+78h] [rbp-90h] BYREF
  const char *v34; // [rsp+80h] [rbp-88h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, struct IDXGIAdapter4 **); // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 Destination; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v37[256]; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v38; // [rsp+198h] [rbp+90h]
  _BYTE Source[24]; // [rsp+1C0h] [rbp+B8h] BYREF

  v30 = a4;
  v31 = a5;
  v32 = 0;
  v35 = 0;
  memset_0(v37, 0, 0x140u);
  v22 = *(_QWORD *)a1 == 0;
  Destination = 0;
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v10 = 20;
    v11 = "m_spMFApi";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids,
      ActivityIdPrefix,
      (__int64)v11);
LABEL_7:
    HWEncoderByLuid = -2147467261;
    goto LABEL_42;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v10 = 21;
    v11 = "pOutputType";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v10 = 22;
    v11 = "ppTransform";
    goto LABEL_6;
  }
  HWEncoderByLuid = -2147467259;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
           *(_QWORD *)(a1 + 8),
           v14,
           &v35) == -2005270526 )
    {
      if ( HWEncoderByLuid >= 0 && v13 == 1 )
      {
        HWEncoderByLuid = CMFApi::CreateHWEncoderByLuid(*(CMFApi **)a1, v15, a3, v30, v31);
        goto LABEL_42;
      }
LABEL_39:
      HWEncoderByLuid = -2147024463;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_42;
      v29 = 498;
      v31 = (unsigned __int16 **)"Adapter not found/supported or multiple adapters found";
      v23 = &byte_1801A9EDF;
      v30 = (struct IMFTransform **)"CreateMFHWEncoderByPreferredVendor";
      v34 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
      v24 = "Error condition failed";
LABEL_41:
      v33 = v24;
      v28 = HWEncoderByLuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (_DWORD)v23,
        v17,
        v18,
        (__int64)&v33,
        (__int64)&v28,
        (__int64)&v34,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31);
      goto LABEL_42;
    }
    HWEncoderByLuid = (**v35)(v35, &GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e, &v32);
    if ( HWEncoderByLuid < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_42;
      v29 = 453;
      v31 = (unsigned __int16 **)"Failed to QI DXGI Adapter.";
      v23 = byte_1801AA0E9;
      v30 = (struct IMFTransform **)"CreateMFHWEncoderByPreferredVendor";
      v34 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
      v24 = "Error HResult failed";
      goto LABEL_41;
    }
    HWEncoderByLuid = ((__int64 (__fastcall *)(struct IDXGIAdapter4 *, _BYTE *))v32->lpVtbl->GetDesc3)(v32, v37);
    if ( HWEncoderByLuid < 0 )
      break;
    ++v14;
    memcpy_s_0(&Destination, 8u, Source, 8u);
    switch ( a2 )
    {
      case 1:
        v22 = v38 == 32902;
        goto LABEL_24;
      case 3:
        v22 = v38 == 4318;
        goto LABEL_24;
      case 2:
        v22 = v38 == 4098;
        goto LABEL_24;
      case 4:
        v22 = v38 == 1297040209;
LABEL_24:
        if ( !v22 )
          goto LABEL_35;
LABEL_25:
        if ( (unsigned int)AdapterToEncoderCreator::IsDriverVersionBlocked(
                             (AdapterToEncoderCreator *)a1,
                             v32,
                             Destination,
                             v38) )
        {
          HWEncoderByLuid = -2147024463;
        }
        else if ( ++v13 == 1 )
        {
          v15 = Destination;
        }
        else if ( v13 > 1 )
        {
          goto LABEL_39;
        }
        break;
      default:
        if ( a2 != 5 || v38 == 5140 )
          goto LABEL_25;
LABEL_35:
        HWEncoderByLuid = -2147024463;
        break;
    }
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v28 = 456;
    v33 = "Failed to get description from DXGI adapter.";
    v29 = HWEncoderByLuid;
    v34 = "CreateMFHWEncoderByPreferredVendor";
    v30 = (struct IMFTransform **)"onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
    v31 = (unsigned __int16 **)"Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)&word_1801A9F36,
      v20,
      v21,
      (__int64)&v31,
      (__int64)&v29,
      (__int64)&v30,
      (__int64)&v28,
      (__int64)&v34,
      (__int64)&v33);
  }
LABEL_42:
  v25 = v35;
  if ( v35 )
  {
    v35 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IDXGIAdapter4 **)))(*v25)[2])(v25);
  }
  v26 = v32;
  if ( v32 )
  {
    v32 = 0;
    ((void (__fastcall *)(struct IDXGIAdapter4 *))v26->lpVtbl->Release)(v26);
  }
  return (unsigned int)HWEncoderByLuid;
}

```

## disassembly

```asm
0x1800e3390  mov     r11, rsp
0x1800e3393  push    rbp
0x1800e3394  push    rbx
0x1800e3395  lea     rbp, [r11-118h]
0x1800e339c  sub     rsp, 208h
0x1800e33a3  mov     rax, cs:__security_cookie
0x1800e33aa  xor     rax, rsp
0x1800e33ad  mov     [rbp+110h+var_40], rax
0x1800e33b4  mov     rax, [rbp+110h+arg_20]
0x1800e33bb  mov     rbx, r9
0x1800e33be  mov     [r11-18h], rdi
0x1800e33c2  mov     edi, edx
0x1800e33c4  mov     [r11-28h], r13
0x1800e33c8  xor     edx, edx; Val
0x1800e33ca  mov     [r11-38h], r15
0x1800e33ce  mov     r13, r8
0x1800e33d1  mov     r15, rcx
0x1800e33d4  mov     [rsp+210h+var_1B8], rbx
0x1800e33d9  lea     rcx, [rbp+110h+var_180]; void *
0x1800e33dd  mov     [rsp+210h+var_1B0], rax
0x1800e33e2  mov     r8d, 140h; Size
0x1800e33e8  mov     [rsp+210h+var_1A8], 0
0x1800e33f1  mov     [rbp+110h+var_190], 0
0x1800e33f9  call    memset_0
0x1800e33fe  cmp     qword ptr [r15], 0
0x1800e3402  mov     [rbp+110h+Destination], 0
0x1800e340a  jnz     short loc_1800E3466
0x1800e340c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3413  lea     rax, WPP_GLOBAL_Control
0x1800e341a  cmp     rcx, rax
0x1800e341d  jz      short loc_1800E345C
0x1800e341f  test    byte ptr [rcx+1Ch], 8
0x1800e3423  jz      short loc_1800E345C
0x1800e3425  cmp     byte ptr [rcx+19h], 2
0x1800e3429  jb      short loc_1800E345C
0x1800e342b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e3431  mov     edx, 14h
0x1800e3436  lea     rcx, aMSpmfapi; "m_spMFApi"
0x1800e343d  mov     [rsp+210h+var_1F0], rcx
0x1800e3442  lea     r8, WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids
0x1800e3449  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3450  mov     r9d, eax
0x1800e3453  mov     rcx, [rcx+10h]
0x1800e3457  call    WPP_SF_Ds
0x1800e345c  mov     ebx, 80004003h
0x1800e3461  jmp     loc_1800E36C1
0x1800e3466  test    r13, r13
0x1800e3469  jnz     short loc_1800E349E
0x1800e346b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3472  lea     rax, WPP_GLOBAL_Control
0x1800e3479  cmp     rcx, rax
0x1800e347c  jz      short loc_1800E345C
0x1800e347e  test    byte ptr [rcx+1Ch], 8
0x1800e3482  jz      short loc_1800E345C
0x1800e3484  cmp     byte ptr [rcx+19h], 2
0x1800e3488  jb      short loc_1800E345C
0x1800e348a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e3490  mov     edx, 15h
0x1800e3495  lea     rcx, aPoutputtype; "pOutputType"
0x1800e349c  jmp     short loc_1800E343D
0x1800e349e  test    rbx, rbx
0x1800e34a1  jnz     short loc_1800E34D9
0x1800e34a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e34aa  lea     rax, WPP_GLOBAL_Control
0x1800e34b1  cmp     rcx, rax
0x1800e34b4  jz      short loc_1800E345C
0x1800e34b6  test    byte ptr [rcx+1Ch], 8
0x1800e34ba  jz      short loc_1800E345C
0x1800e34bc  cmp     byte ptr [rcx+19h], 2
0x1800e34c0  jb      short loc_1800E345C
0x1800e34c2  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e34c8  mov     edx, 16h
0x1800e34cd  lea     rcx, aPptransform; "ppTransform"
0x1800e34d4  jmp     loc_1800E343D
0x1800e34d9  mov     [rsp+210h+arg_8], rsi
0x1800e34e1  mov     ebx, 80004005h
0x1800e34e6  mov     [rsp+210h+var_18], r12
0x1800e34ee  xor     esi, esi
0x1800e34f0  mov     [rsp+210h+var_28], r14
0x1800e34f8  xor     r14d, r14d
0x1800e34fb  xor     r12d, r12d
0x1800e34fe  xchg    ax, ax
0x1800e3500  mov     rcx, [r15+8]
0x1800e3504  lea     r8, [rbp+110h+var_190]
0x1800e3508  mov     edx, r14d
0x1800e350b  mov     rax, [rcx]
0x1800e350e  mov     rax, [rax+60h]
0x1800e3512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3517  cmp     eax, 887A0002h
0x1800e351c  jz      loc_1800E380C
0x1800e3522  mov     rcx, [rbp+110h+var_190]
0x1800e3526  lea     r8, [rsp+210h+var_1A8]
0x1800e352b  lea     rdx, _GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e
0x1800e3532  mov     rax, [rcx]
0x1800e3535  mov     rax, [rax]
0x1800e3538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e353d  mov     ebx, eax
0x1800e353f  test    eax, eax
0x1800e3541  js      loc_1800E37BE
0x1800e3547  mov     rcx, [rsp+210h+var_1A8]
0x1800e354c  lea     rdx, [rbp+110h+var_180]
0x1800e3550  mov     rax, [rcx]
0x1800e3553  mov     rax, [rax+90h]
0x1800e355a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e355f  mov     ebx, eax
0x1800e3561  test    eax, eax
0x1800e3563  js      loc_1800E3730
0x1800e3569  mov     r9d, 8; SourceSize
0x1800e356f  lea     r8, [rbp+110h+Source]; Source
0x1800e3576  mov     edx, r9d; DestinationSize
0x1800e3579  lea     rcx, [rbp+110h+Destination]; Destination
0x1800e357d  inc     r14d
0x1800e3580  call    memcpy_s_0
0x1800e3585  mov     r9d, [rbp+110h+var_80]; unsigned int
0x1800e358c  cmp     edi, 1
0x1800e358f  jnz     short loc_1800E35B9
0x1800e3591  cmp     r9d, 8086h
0x1800e3598  jnz     short loc_1800E35F1
0x1800e359a  mov     r8, [rbp+110h+Destination]; unsigned __int64
0x1800e359e  mov     rcx, r15; this
0x1800e35a1  mov     rdx, [rsp+210h+var_1A8]; struct IDXGIAdapter4 *
0x1800e35a6  call    ?IsDriverVersionBlocked@AdapterToEncoderCreator@@QEAAHPEAUIDXGIAdapter4@@_KI@Z; AdapterToEncoderCreator::IsDriverVersionBlocked(IDXGIAdapter4 *,unsigned __int64,uint)
0x1800e35ab  test    eax, eax
0x1800e35ad  jz      short loc_1800E35FB
0x1800e35af  mov     ebx, 800701B1h
0x1800e35b4  jmp     loc_1800E3500
0x1800e35b9  cmp     edi, 3
0x1800e35bc  jnz     short loc_1800E35C7
0x1800e35be  cmp     r9d, 10DEh
0x1800e35c5  jmp     short loc_1800E3598
0x1800e35c7  cmp     edi, 2
0x1800e35ca  jnz     short loc_1800E35D5
0x1800e35cc  cmp     r9d, 1002h
0x1800e35d3  jmp     short loc_1800E3598
0x1800e35d5  cmp     edi, 4
0x1800e35d8  jnz     short loc_1800E35E3
0x1800e35da  cmp     r9d, 4D4F4351h
0x1800e35e1  jmp     short loc_1800E3598
0x1800e35e3  cmp     edi, 5
0x1800e35e6  jnz     short loc_1800E359A
0x1800e35e8  cmp     r9d, 1414h
0x1800e35ef  jz      short loc_1800E359A
0x1800e35f1  mov     ebx, 800701B1h
0x1800e35f6  jmp     loc_1800E3500
0x1800e35fb  inc     esi
0x1800e35fd  cmp     esi, 1
0x1800e3600  jnz     short loc_1800E360B
0x1800e3602  mov     r12, [rbp+110h+Destination]
0x1800e3606  jmp     loc_1800E3500
0x1800e360b  jbe     loc_1800E3500
0x1800e3611  mov     eax, cs:dword_1801B76C8
0x1800e3617  mov     ebx, 800701B1h
0x1800e361c  cmp     eax, 2
0x1800e361f  jbe     loc_1800E36A9
0x1800e3625  lea     rax, aAdapterNotFoun; "Adapter not found/supported or multiple"...
0x1800e362c  mov     dword ptr [rsp+210h+var_1C0+4], 1F2h
0x1800e3634  mov     [rsp+210h+var_1B0], rax
0x1800e3639  lea     rdx, byte_1801A9EDF
0x1800e3640  lea     rax, aCreatemfhwenco_1; "CreateMFHWEncoderByPreferredVendor"
0x1800e3647  mov     [rsp+210h+var_1B8], rax
0x1800e364c  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e3653  mov     [rsp+210h+var_198], rax
0x1800e3658  lea     rax, aErrorCondition; "Error condition failed"
0x1800e365f  mov     [rsp+210h+var_1A0], rax
0x1800e3664  lea     rax, [rsp+210h+var_1B0]
0x1800e3669  mov     qword ptr [rsp+210h+var_1C8], rax
0x1800e366e  lea     rax, [rsp+210h+var_1B8]
0x1800e3673  mov     [rsp+210h+var_1D0], rax
0x1800e3678  lea     rax, [rsp+210h+var_1C0+4]
0x1800e367d  mov     [rsp+210h+var_1D8], rax
0x1800e3682  lea     rax, [rsp+210h+var_198]
0x1800e3687  mov     [rsp+210h+var_1E0], rax
0x1800e368c  lea     rax, [rsp+210h+var_1C0]
0x1800e3691  mov     [rsp+210h+var_1E8], rax
0x1800e3696  lea     rax, [rsp+210h+var_1A0]
0x1800e369b  mov     dword ptr [rsp+210h+var_1C0], ebx
0x1800e369f  mov     [rsp+210h+var_1F0], rax
0x1800e36a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e36a9  mov     r12, [rsp+210h+var_18]
0x1800e36b1  mov     rsi, [rsp+210h+arg_8]
0x1800e36b9  mov     r14, [rsp+210h+var_28]
0x1800e36c1  mov     rcx, [rbp+110h+var_190]
0x1800e36c5  mov     r15, [rsp+210h+var_30]
0x1800e36cd  mov     r13, [rsp+210h+var_20]
0x1800e36d5  mov     rdi, [rsp+200h]
0x1800e36dd  test    rcx, rcx
0x1800e36e0  jz      short loc_1800E36F6
0x1800e36e2  mov     [rbp+110h+var_190], 0
0x1800e36ea  mov     rax, [rcx]
0x1800e36ed  mov     rax, [rax+10h]
0x1800e36f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e36f6  mov     rcx, [rsp+210h+var_1A8]
0x1800e36fb  test    rcx, rcx
0x1800e36fe  jz      short loc_1800E3715
0x1800e3700  mov     [rsp+210h+var_1A8], 0
0x1800e3709  mov     rax, [rcx]
0x1800e370c  mov     rax, [rax+10h]
0x1800e3710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3715  mov     eax, ebx
0x1800e3717  mov     rcx, [rbp+110h+var_40]
0x1800e371e  xor     rcx, rsp; StackCookie
0x1800e3721  call    __security_check_cookie
0x1800e3726  add     rsp, 208h
0x1800e372d  pop     rbx
0x1800e372e  pop     rbp
0x1800e372f  retn
0x1800e3730  mov     eax, cs:dword_1801B76C8
0x1800e3736  cmp     eax, 2
0x1800e3739  jbe     loc_1800E36A9
0x1800e373f  lea     rax, aFailedToGetDes; "Failed to get description from DXGI ada"...
0x1800e3746  mov     dword ptr [rsp+210h+var_1C0], 1C8h
0x1800e374e  mov     [rsp+210h+var_1A0], rax
0x1800e3753  lea     rdx, word_1801A9F36
0x1800e375a  lea     rax, aCreatemfhwenco_1; "CreateMFHWEncoderByPreferredVendor"
0x1800e3761  mov     dword ptr [rsp+210h+var_1C0+4], ebx
0x1800e3765  mov     [rsp+210h+var_198], rax
0x1800e376a  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e3771  mov     [rsp+210h+var_1B8], rax
0x1800e3776  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e377d  mov     [rsp+210h+var_1B0], rax
0x1800e3782  lea     rax, [rsp+210h+var_1A0]
0x1800e3787  mov     qword ptr [rsp+210h+var_1C8], rax
0x1800e378c  lea     rax, [rsp+210h+var_198]
0x1800e3791  mov     [rsp+210h+var_1D0], rax
0x1800e3796  lea     rax, [rsp+210h+var_1C0]
0x1800e379b  mov     [rsp+210h+var_1D8], rax
0x1800e37a0  lea     rax, [rsp+210h+var_1B8]
0x1800e37a5  mov     [rsp+210h+var_1E0], rax
0x1800e37aa  lea     rax, [rsp+210h+var_1C0+4]
0x1800e37af  mov     [rsp+210h+var_1E8], rax
0x1800e37b4  lea     rax, [rsp+210h+var_1B0]
0x1800e37b9  jmp     loc_1800E369F
0x1800e37be  mov     eax, cs:dword_1801B76C8
0x1800e37c4  cmp     eax, 2
0x1800e37c7  jbe     loc_1800E36A9
0x1800e37cd  lea     rax, aFailedToQiDxgi; "Failed to QI DXGI Adapter."
0x1800e37d4  mov     dword ptr [rsp+210h+var_1C0+4], 1C5h
0x1800e37dc  mov     [rsp+210h+var_1B0], rax
0x1800e37e1  lea     rdx, byte_1801AA0E9
0x1800e37e8  lea     rax, aCreatemfhwenco_1; "CreateMFHWEncoderByPreferredVendor"
0x1800e37ef  mov     [rsp+210h+var_1B8], rax
0x1800e37f4  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e37fb  mov     [rsp+210h+var_198], rax
0x1800e3800  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e3807  jmp     loc_1800E365F
0x1800e380c  test    ebx, ebx
0x1800e380e  js      loc_1800E3611
0x1800e3814  cmp     esi, 1
0x1800e3817  jnz     loc_1800E3611
0x1800e381d  mov     rax, [rsp+210h+var_1B0]
0x1800e3822  mov     r8, r13; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800e3825  mov     r9, [rsp+210h+var_1B8]; struct IMFTransform **
0x1800e382a  mov     rdx, r12; unsigned __int64
0x1800e382d  mov     rcx, [r15]; this
0x1800e3830  mov     [rsp+210h+var_1F0], rax; unsigned __int16 **
0x1800e3835  call    ?CreateHWEncoderByLuid@CMFApi@@QEAAJ_KPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@AEAPEAG@Z; CMFApi::CreateHWEncoderByLuid(unsigned __int64,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,ushort * &)
0x1800e383a  mov     ebx, eax
0x1800e383c  jmp     loc_1800E36A9
```
