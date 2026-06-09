# CMFApi::FindEncodersByLuid(_GUID,unsigned __int64,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)

- ea: `0x1800db510`
- end: `0x1800db89d`
- name: `?FindEncodersByLuid@CMFApi@@QEAAJU_GUID@@_KPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@2PEAPEAPEAUIMFActivate@@PEAI@Z`
- size: `909`
- prototype: `__int64 __fastcall(CMFApi *__hidden this, struct _GUID *, unsigned __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFActivate ***, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800da1b0`

## callees

- `0x18002e600`
- `0x180033da0`
- `0x1800db510`
- `0x1800dc9c0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800db682`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800db682`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db6d4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db765`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db7da`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db81a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db6d4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db765`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db7da`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800db81a`

## string_xrefs

- `0x1800db5ca`: `onecoreuap\termsrv\rdp\win\codecs\common\cmfapi.cpp`
- `0x1800db6df`: `_pfnMFCreateAttributes failed`

## pseudocode

```c
__int64 __fastcall CMFApi::FindEncodersByLuid(
        __int64 (__fastcall **this)(__int64 *, __int64, __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *),
        EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a4,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a5,
        struct IMFActivate ***a6,
        unsigned int *a7)
{
  int v9; // esi
  int ActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  __int64 (__fastcall *v13)(__int64 *, __int64, __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *); // rax
  __int64 v14; // rbx
  unsigned int v15; // edi
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D8h]
  __int64 v22; // [rsp+48h] [rbp-C0h] BYREF
  int v23; // [rsp+50h] [rbp-B8h] BYREF
  _DWORD v24[3]; // [rsp+54h] [rbp-B4h] BYREF
  __int64 EventDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor_8; // [rsp+68h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+78h] [rbp-90h] BYREF
  char *v28; // [rsp+88h] [rbp-80h]
  int v29; // [rsp+90h] [rbp-78h]
  int v30; // [rsp+94h] [rbp-74h]
  const char *v31; // [rsp+98h] [rbp-70h]
  __int64 v32; // [rsp+A0h] [rbp-68h]
  _DWORD *v33; // [rsp+A8h] [rbp-60h]
  __int64 v34; // [rsp+B0h] [rbp-58h]
  const char *v35; // [rsp+B8h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-48h]
  int *v37; // [rsp+C8h] [rbp-40h]
  __int64 v38; // [rsp+D0h] [rbp-38h]
  const char *v39; // [rsp+D8h] [rbp-30h]
  __int64 v40; // [rsp+E0h] [rbp-28h]
  const char *v41; // [rsp+E8h] [rbp-20h]
  __int64 v42; // [rsp+F0h] [rbp-18h]

  EventDescriptor = a3;
  v22 = 0;
  if ( !a6 )
  {
    v9 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v23 = 508;
      v41 = "pppActivates - NULL pointer";
      v24[0] = -2147467261;
      v39 = "FindEncodersByLuid";
      v42 = 28;
      v37 = &v23;
      v40 = 19;
      v35 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cmfapi.cpp";
      v38 = 4;
      v33 = v24;
      v31 = "Error condition failed";
      v27.Ptr = (ULONGLONG)off_1801B76D0;
      v36 = 52;
      v34 = 4;
      v32 = 23;
      *(_QWORD *)&EventDescriptor_8.Id = 0x20B000000LL;
      EventDescriptor_8.Keyword = 0;
      v27.Size = *(unsigned __int16 *)off_1801B76D0;
      v28 = byte_1801A9B7B;
      v27.Reserved = 2;
      v29 = 75;
      v30 = 1;
      v24[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1801B76E8, &EventDescriptor_8, 0, 0, 8u, &v27);
    }
    goto LABEL_24;
  }
  v9 = this[18](&v22, 1, a3, a4);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v11 = 27;
    v12 = "_pfnMFCreateAttributes failed";
    goto LABEL_9;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, __int64))(*(_QWORD *)v22 + 208LL))(
         v22,
         MFT_ENUM_ADAPTER_LUID,
         &EventDescriptor,
         8);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v11 = 28;
    v12 = "spMFTAttributes->SetBlob failed";
    goto LABEL_9;
  }
  v13 = this[16];
  EventDescriptor_8 = *a2;
  v9 = ((__int64 (__fastcall *)(EVENT_DESCRIPTOR *, __int64, _QWORD, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, __int64, struct IMFActivate ***, unsigned int *))v13)(
         &EventDescriptor_8,
         87,
         0,
         a5,
         v22,
         a6,
         a7);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v11 = 29;
    v12 = "_pfnMFTEnum2 failed";
LABEL_9:
    LODWORD(UserData) = v9;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)&WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids,
      ActivityIdPrefix,
      (__int64)v12,
      UserData);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v14 = EventDescriptor;
    v15 = *a7;
    v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    WPP_SF_DdiD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v16, v15, v14, v9);
  }
LABEL_24:
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64, EVENT_DESCRIPTOR *, __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *))(*(_QWORD *)v19 + 16LL))(
      v19,
      a2,
      a3,
      a4);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800db510  mov     r11, rsp
0x1800db513  push    rbp
0x1800db514  push    rsi
0x1800db515  push    r13
0x1800db517  lea     rbp, [r11-38h]
0x1800db51b  sub     rsp, 120h
0x1800db522  mov     rax, cs:__security_cookie
0x1800db529  xor     rax, rsp
0x1800db52c  mov     [rbp+30h+var_40], rax
0x1800db530  mov     [r11+20h], rbx
0x1800db534  xor     r13d, r13d
0x1800db537  mov     [r11-20h], rdi
0x1800db53b  mov     rbx, rcx
0x1800db53e  mov     rdi, [rbp+30h+arg_30]
0x1800db542  mov     [r11-28h], r12
0x1800db546  mov     r12, [rbp+30h+arg_20]
0x1800db54a  mov     [r11-30h], r14
0x1800db54e  mov     r14, [rbp+30h+arg_28]
0x1800db552  mov     [r11-38h], r15
0x1800db556  mov     r15, rdx
0x1800db559  mov     qword ptr [rsp+130h+EventDescriptor.Id], r8
0x1800db55e  mov     qword ptr [rsp+130h+var_F0], r13
0x1800db563  test    r14, r14
0x1800db566  jnz     loc_1800DB68D
0x1800db56c  mov     eax, cs:dword_1801B76C8
0x1800db572  mov     esi, 80004003h
0x1800db577  cmp     eax, 2
0x1800db57a  jbe     loc_1800DB840
0x1800db580  mov     [rsp+130h+var_E8], 1FCh
0x1800db588  lea     rax, aPppactivatesNu; "pppActivates - NULL pointer"
0x1800db58f  mov     [rbp+30h+var_50], rax
0x1800db593  lea     rcx, _TraceLoggingMetadata
0x1800db59a  mov     [rsp+4Ch], esi
0x1800db59e  lea     rax, aFindencodersby; "FindEncodersByLuid"
0x1800db5a5  mov     [rbp+30h+var_60], rax
0x1800db5a9  lea     rdx, [rsp+130h+EventDescriptor.Keyword]; EventDescriptor
0x1800db5ae  mov     [rbp+30h+var_48], 1Ch
0x1800db5b6  lea     rax, [rsp+130h+var_E8]
0x1800db5bb  mov     [rbp+30h+var_70], rax
0x1800db5bf  xor     r9d, r9d; RelatedActivityId
0x1800db5c2  mov     [rbp+30h+var_58], 13h
0x1800db5ca  lea     rax, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800db5d1  mov     [rbp+30h+var_80], rax
0x1800db5d5  xor     r8d, r8d; ActivityId
0x1800db5d8  mov     [rbp+30h+var_68], 4
0x1800db5e0  lea     rax, [rsp+4Ch]
0x1800db5e5  mov     [rbp+30h+var_90], rax
0x1800db5e9  lea     rax, aErrorCondition; "Error condition failed"
0x1800db5f0  mov     [rbp+30h+var_A0], rax
0x1800db5f4  movzx   eax, cs:word_1801A9B71
0x1800db5fb  mov     dword ptr [rsp+130h+EventDescriptor.Keyword+4], eax
0x1800db5ff  mov     rax, cs:off_1801B76D0
0x1800db606  mov     [rsp+130h+var_C0.Ptr], rax
0x1800db60b  mov     [rbp+30h+var_78], 34h ; '4'
0x1800db613  mov     [rbp+30h+var_88], 4
0x1800db61b  mov     [rbp+30h+var_98], 17h
0x1800db623  mov     dword ptr [rsp+130h+EventDescriptor.Keyword], 0B000000h
0x1800db62b  mov     [rsp+130h+var_C8], r13
0x1800db630  movzx   eax, word ptr [rax]
0x1800db633  mov     [rsp+130h+var_C0.Size], eax
0x1800db637  lea     rax, byte_1801A9B7B
0x1800db63e  mov     [rbp+30h+var_B0], rax
0x1800db642  lea     rax, _TraceLoggingMetadataEnd
0x1800db649  sub     eax, ecx
0x1800db64b  mov     dword ptr [rsp+130h+var_C0.0Ch], 2
0x1800db653  mov     [rbp+30h+var_A8], 4Bh ; 'K'
0x1800db65a  mov     [rbp+30h+var_A4], 1
0x1800db661  mov     dword ptr [rsp+130h+var_E0], eax
0x1800db665  mov     eax, dword ptr [rsp+130h+var_E0]
0x1800db669  mov     rcx, cs:qword_1801B76E8; RegHandle
0x1800db670  lea     rax, [rsp+130h+var_C0]
0x1800db675  mov     [rsp+130h+UserData], rax; UserData
0x1800db67a  mov     [rsp+130h+UserDataCount], 8; UserDataCount
0x1800db682  call    cs:__imp_EventWriteTransfer
0x1800db688  jmp     loc_1800DB840
0x1800db68d  mov     rax, [rbx+90h]
0x1800db694  lea     rcx, [rsp+130h+var_F0]
0x1800db699  mov     edx, 1
0x1800db69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db6a3  mov     esi, eax
0x1800db6a5  test    eax, eax
0x1800db6a7  jns     short loc_1800DB70E
0x1800db6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db6b0  lea     rax, WPP_GLOBAL_Control
0x1800db6b7  cmp     rcx, rax
0x1800db6ba  jz      loc_1800DB840
0x1800db6c0  test    byte ptr [rcx+1Ch], 8
0x1800db6c4  jz      loc_1800DB840
0x1800db6ca  cmp     byte ptr [rcx+19h], 2
0x1800db6ce  jb      loc_1800DB840
0x1800db6d4  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800db6da  mov     edx, 1Bh
0x1800db6df  lea     rcx, aPfnmfcreateatt_0; "_pfnMFCreateAttributes failed"
0x1800db6e6  mov     dword ptr [rsp+130h+UserData], esi
0x1800db6ea  lea     r8, WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids
0x1800db6f1  mov     qword ptr [rsp+130h+UserDataCount], rcx
0x1800db6f6  mov     r9d, eax
0x1800db6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db700  mov     rcx, [rcx+10h]
0x1800db704  call    WPP_SF_DsD
0x1800db709  jmp     loc_1800DB840
0x1800db70e  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1800db713  lea     r8, [rsp+130h+EventDescriptor]
0x1800db718  mov     r9d, 8
0x1800db71e  lea     rdx, MFT_ENUM_ADAPTER_LUID
0x1800db725  mov     rax, [rcx]
0x1800db728  mov     rax, [rax+0D0h]
0x1800db72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db734  mov     esi, eax
0x1800db736  test    eax, eax
0x1800db738  jns     short loc_1800DB77C
0x1800db73a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db741  lea     rax, WPP_GLOBAL_Control
0x1800db748  cmp     rcx, rax
0x1800db74b  jz      loc_1800DB840
0x1800db751  test    byte ptr [rcx+1Ch], 8
0x1800db755  jz      loc_1800DB840
0x1800db75b  cmp     byte ptr [rcx+19h], 2
0x1800db75f  jb      loc_1800DB840
0x1800db765  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800db76b  mov     edx, 1Ch
0x1800db770  lea     rcx, aSpmftattribute; "spMFTAttributes->SetBlob failed"
0x1800db777  jmp     loc_1800DB6E6
0x1800db77c  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1800db781  mov     r9, r12
0x1800db784  movups  xmm0, xmmword ptr [r15]
0x1800db788  mov     rax, [rbx+80h]
0x1800db78f  xor     r8d, r8d
0x1800db792  mov     [rsp+30h], rdi
0x1800db797  mov     edx, 57h ; 'W'
0x1800db79c  mov     [rsp+130h+UserData], r14
0x1800db7a1  mov     qword ptr [rsp+130h+UserDataCount], rcx
0x1800db7a6  lea     rcx, [rsp+130h+EventDescriptor.Keyword]
0x1800db7ab  movaps  xmmword ptr [rsp+130h+EventDescriptor.Keyword], xmm0
0x1800db7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db7b5  mov     esi, eax
0x1800db7b7  test    eax, eax
0x1800db7b9  jns     short loc_1800DB7F1
0x1800db7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db7c2  lea     rax, WPP_GLOBAL_Control
0x1800db7c9  cmp     rcx, rax
0x1800db7cc  jz      short loc_1800DB840
0x1800db7ce  test    byte ptr [rcx+1Ch], 8
0x1800db7d2  jz      short loc_1800DB840
0x1800db7d4  cmp     byte ptr [rcx+19h], 2
0x1800db7d8  jb      short loc_1800DB840
0x1800db7da  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800db7e0  mov     edx, 1Dh
0x1800db7e5  lea     rcx, aPfnmftenum2Fai; "_pfnMFTEnum2 failed"
0x1800db7ec  jmp     loc_1800DB6E6
0x1800db7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db7f8  lea     rax, WPP_GLOBAL_Control
0x1800db7ff  cmp     rcx, rax
0x1800db802  jz      short loc_1800DB840
0x1800db804  test    dword ptr [rcx+1Ch], 100h
0x1800db80b  jz      short loc_1800DB840
0x1800db80d  cmp     byte ptr [rcx+19h], 5
0x1800db811  jb      short loc_1800DB840
0x1800db813  mov     rbx, qword ptr [rsp+130h+EventDescriptor.Id]
0x1800db818  mov     edi, [rdi]
0x1800db81a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800db820  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db827  mov     r9d, eax
0x1800db82a  mov     [rsp+30h], esi
0x1800db82e  mov     [rsp+130h+UserData], rbx
0x1800db833  mov     [rsp+130h+UserDataCount], edi
0x1800db837  mov     rcx, [rcx+10h]
0x1800db83b  call    WPP_SF_DdiD
0x1800db840  mov     rcx, qword ptr [rsp+130h+var_F0]
0x1800db845  mov     r15, [rsp+130h+var_30]
0x1800db84d  mov     r14, [rsp+130h+var_28]
0x1800db855  mov     r12, [rsp+130h+var_20]
0x1800db85d  mov     rdi, [rsp+118h]
0x1800db865  mov     rbx, [rsp+130h+arg_18]
0x1800db86d  test    rcx, rcx
0x1800db870  jz      short loc_1800DB883
0x1800db872  mov     qword ptr [rsp+130h+var_F0], r13
0x1800db877  mov     rax, [rcx]
0x1800db87a  mov     rax, [rax+10h]
0x1800db87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db883  mov     eax, esi
0x1800db885  mov     rcx, [rbp+30h+var_40]
0x1800db889  xor     rcx, rsp; StackCookie
0x1800db88c  call    __security_check_cookie
0x1800db891  add     rsp, 120h
0x1800db898  pop     r13
0x1800db89a  pop     rsi
0x1800db89b  pop     rbp
0x1800db89c  retn
```
