# Avc420DrmCompressor::Compress(RdpSurface *,PixelMap *,IRdpBoundsAccumulator *,int,ulong,ulong,uchar *,uint *,RdpRect *,uint)

- ea: `0x180083ca0`
- end: `0x180084043`
- name: `?Compress@Avc420DrmCompressor@@UEAAJPEAVRdpSurface@@PEAVPixelMap@@PEAVIRdpBoundsAccumulator@@HKKPEAEPEAIPEAURdpRect@@I@Z`
- size: `931`
- prototype: `__int64 __usercall@<rax>(Avc420DrmCompressor *__hidden this@<rcx>, struct RdpSurface *@<rdx>, struct PixelMap *@<r8>, struct IRdpBoundsAccumulator *@<r9>, int, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, struct RdpRect *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002e600`
- `0x180033da0`
- `0x180080a70`
- `0x180083ca0`
- `0x180084050`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180083e07`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180083e07`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180083e8c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180083f3a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180083fa6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180083e8c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180083f3a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180083fa6`

## string_xrefs

- `0x180083d2b`: `Compress`
- `0x180083d56`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avc420drmcompressor.cpp`
- `0x180083d15`: `encryptor object is NULL, compressor not initialized`

## pseudocode

```c
__int64 __fastcall Avc420DrmCompressor::Compress(
        Avc420DrmCompressor *this,
        struct RdpSurface *a2,
        struct PixelMap *a3,
        struct IRdpBoundsAccumulator *a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int *a9,
        struct RdpRect *a10,
        unsigned int a11)
{
  int v12; // ebx
  unsigned int v13; // edi
  int ActivityIdPrefix; // eax
  int v15; // r14d
  __int64 v16; // rcx
  unsigned __int8 *v17; // r12
  int v18; // eax
  int v19; // edx
  const char *v20; // rcx
  __int64 v21; // rcx
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D8h]
  __int64 v24; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+70h] [rbp-98h] BYREF
  __int64 v26; // [rsp+78h] [rbp-90h] BYREF
  __int64 v27; // [rsp+80h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+98h] [rbp-70h] BYREF
  char *v30; // [rsp+A8h] [rbp-60h]
  int v31; // [rsp+B0h] [rbp-58h]
  int v32; // [rsp+B4h] [rbp-54h]
  const char *v33; // [rsp+B8h] [rbp-50h]
  __int64 v34; // [rsp+C0h] [rbp-48h]
  __int64 *v35; // [rsp+C8h] [rbp-40h]
  __int64 v36; // [rsp+D0h] [rbp-38h]
  const char *v37; // [rsp+D8h] [rbp-30h]
  __int64 v38; // [rsp+E0h] [rbp-28h]
  __int64 *v39; // [rsp+E8h] [rbp-20h]
  __int64 v40; // [rsp+F0h] [rbp-18h]
  const char *v41; // [rsp+F8h] [rbp-10h]
  __int64 v42; // [rsp+100h] [rbp-8h]
  const char *v43; // [rsp+108h] [rbp+0h]
  __int64 v44; // [rsp+110h] [rbp+8h]

  v25 = 0;
  if ( !*((_QWORD *)this + 60) )
  {
    v12 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v24) = 132;
      v43 = "encryptor object is NULL, compressor not initialized";
      LODWORD(v26) = -2147467261;
      v41 = "Compress";
      v44 = 53;
      v39 = &v24;
      v42 = 9;
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avc420drmcompressor.cpp";
      v40 = 4;
      v35 = &v26;
      v33 = "Error condition failed";
      *(_DWORD *)&EventDescriptor.Level = 2;
      v29.Ptr = (ULONGLONG)off_1801B76D0;
      v38 = 68;
      v36 = 4;
      v34 = 23;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v29.Size = *(unsigned __int16 *)off_1801B76D0;
      v30 = byte_18019F49B;
      v29.Reserved = 2;
      v31 = 78;
      v32 = 1;
      LODWORD(v27) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 8u, &v29);
    }
    goto LABEL_23;
  }
  v13 = *a9;
  v12 = Avc420Compressor::Compress(this, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      LODWORD(UserData) = v12;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_2fd84019dbbc3ac762ccb9482f5e5733_Traceguids,
        ActivityIdPrefix,
        (__int64)"Failed to encode frame",
        UserData);
    }
    goto LABEL_23;
  }
  v15 = 10 * *(_DWORD *)a8 + 4;
  v16 = *((_QWORD *)this + 60);
  v17 = &a8[v15];
  LODWORD(v24) = *a9 - v15;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, __int64 *))(*(_QWORD *)v16 + 24LL))(
          v16,
          v17,
          (unsigned int)v24,
          &v25);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v18 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v19 = 17;
    v20 = "Failed to encrypt frame";
LABEL_21:
    LODWORD(UserData) = v12;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      (unsigned int)&WPP_2fd84019dbbc3ac762ccb9482f5e5733_Traceguids,
      v18,
      (__int64)v20,
      UserData);
    goto LABEL_23;
  }
  v27 = v25;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
  v12 = Avc420DrmCompressor::FormatEncodedBuffer((__int64)v17, &v24, &v27, v13 - v15);
  if ( v12 >= 0 )
  {
    *a9 = v15 + v24;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v19 = 18;
    v20 = "Failed to format encoded buffer";
    goto LABEL_21;
  }
LABEL_23:
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64, struct RdpSurface *, struct PixelMap *, struct IRdpBoundsAccumulator *))(*(_QWORD *)v21 + 16LL))(
      v21,
      a2,
      a3,
      a4);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180083ca0  mov     r11, rsp
0x180083ca3  push    rbp
0x180083ca4  push    rbx
0x180083ca5  push    r13
0x180083ca7  lea     rbp, [r11-68h]
0x180083cab  sub     rsp, 150h
0x180083cb2  mov     rax, cs:__security_cookie
0x180083cb9  xor     rax, rsp
0x180083cbc  mov     [rbp+60h+var_50], rax
0x180083cc0  mov     [r11-20h], rsi
0x180083cc4  xor     r13d, r13d
0x180083cc7  mov     rsi, [rbp+60h+arg_40]
0x180083cce  mov     [r11-30h], r12
0x180083cd2  mov     r12, [rbp+60h+arg_38]
0x180083cd9  mov     [r11-40h], r15
0x180083cdd  mov     r15, rcx
0x180083ce0  mov     rcx, [rbp+60h+arg_48]
0x180083ce7  mov     [rsp+160h+var_F8], r13
0x180083cec  cmp     [r15+1E0h], r13
0x180083cf3  jnz     loc_180083E12
0x180083cf9  mov     eax, cs:dword_1801B76C8
0x180083cff  mov     ebx, 80004003h
0x180083d04  cmp     eax, 2
0x180083d07  jbe     loc_180083FF6
0x180083d0d  mov     dword ptr [rsp+160h+var_100], 84h
0x180083d15  lea     rax, aEncryptorObjec; "encryptor object is NULL, compressor no"...
0x180083d1c  mov     [rbp+60h+var_60], rax
0x180083d20  lea     rcx, _TraceLoggingMetadata
0x180083d27  mov     dword ptr [rsp+160h+var_F0], ebx
0x180083d2b  lea     rax, aCompress; "Compress"
0x180083d32  mov     [rbp+60h+var_70], rax
0x180083d36  lea     rdx, [rbp+60h+EventDescriptor]; EventDescriptor
0x180083d3a  mov     [rbp+60h+var_58], 35h ; '5'
0x180083d42  lea     rax, [rsp+160h+var_100]
0x180083d47  mov     [rbp+60h+var_80], rax
0x180083d4b  xor     r9d, r9d; RelatedActivityId
0x180083d4e  mov     [rbp+60h+var_68], 9
0x180083d56  lea     rax, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180083d5d  mov     [rbp+60h+var_90], rax
0x180083d61  xor     r8d, r8d; ActivityId
0x180083d64  mov     [rbp+60h+var_78], 4
0x180083d6c  lea     rax, [rsp+160h+var_F0]
0x180083d71  mov     [rbp+60h+var_A0], rax
0x180083d75  lea     rax, aErrorCondition; "Error condition failed"
0x180083d7c  mov     [rbp+60h+var_B0], rax
0x180083d80  movzx   eax, cs:word_18019F491
0x180083d87  mov     dword ptr [rbp+60h+EventDescriptor.Level], eax
0x180083d8a  mov     rax, cs:off_1801B76D0
0x180083d91  mov     [rbp+60h+var_D0.Ptr], rax
0x180083d95  mov     [rbp+60h+var_88], 44h ; 'D'
0x180083d9d  mov     [rbp+60h+var_98], 4
0x180083da5  mov     [rbp+60h+var_A8], 17h
0x180083dad  mov     dword ptr [rbp+60h+EventDescriptor.Id], 0B000000h
0x180083db4  mov     [rbp+60h+EventDescriptor.Keyword], r13
0x180083db8  movzx   eax, word ptr [rax]
0x180083dbb  mov     [rbp+60h+var_D0.Size], eax
0x180083dbe  lea     rax, byte_18019F49B
0x180083dc5  mov     [rbp+60h+var_C0], rax
0x180083dc9  lea     rax, _TraceLoggingMetadataEnd
0x180083dd0  sub     eax, ecx
0x180083dd2  mov     dword ptr [rbp+60h+var_D0.0Ch], 2
0x180083dd9  mov     [rbp+60h+var_B8], 4Eh ; 'N'
0x180083de0  mov     [rbp+60h+var_B4], 1
0x180083de7  mov     dword ptr [rsp+160h+var_E8], eax
0x180083deb  mov     eax, dword ptr [rsp+160h+var_E8]
0x180083def  mov     rcx, cs:qword_1801B76E8; RegHandle
0x180083df6  lea     rax, [rbp+60h+var_D0]
0x180083dfa  mov     [rsp+160h+UserData], rax; UserData
0x180083dff  mov     [rsp+160h+UserDataCount], 8; UserDataCount
0x180083e07  call    cs:__imp_EventWriteTransfer
0x180083e0d  jmp     loc_180083FF6
0x180083e12  mov     eax, [rbp+60h+arg_50]
0x180083e18  mov     [rsp+50h], eax; unsigned int
0x180083e1c  mov     eax, [rbp+60h+arg_30]
0x180083e22  mov     [rsp+160h+var_118], rcx; struct RdpRect *
0x180083e27  mov     rcx, r15; this
0x180083e2a  mov     [rsp+160h+var_120], rsi; unsigned int *
0x180083e2f  mov     [rsp+160h+var_128], r12; unsigned __int8 *
0x180083e34  mov     [rsp+160h+var_130], eax; unsigned int
0x180083e38  mov     eax, [rbp+60h+arg_28]
0x180083e3e  mov     dword ptr [rsp+160h+UserData], eax; unsigned int
0x180083e42  mov     eax, [rbp+60h+arg_20]
0x180083e48  mov     [rsp+160h+var_20], rdi
0x180083e50  mov     edi, [rsi]
0x180083e52  mov     [rsp+160h+UserDataCount], eax; int
0x180083e56  call    ?Compress@Avc420Compressor@@UEAAJPEAVRdpSurface@@PEAVPixelMap@@PEAVIRdpBoundsAccumulator@@HKKPEAEPEAIPEAURdpRect@@I@Z; Avc420Compressor::Compress(RdpSurface *,PixelMap *,IRdpBoundsAccumulator *,int,ulong,ulong,uchar *,uint *,RdpRect *,uint)
0x180083e5b  mov     ebx, eax
0x180083e5d  test    eax, eax
0x180083e5f  jns     short loc_180083EC6
0x180083e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e68  lea     rax, WPP_GLOBAL_Control
0x180083e6f  cmp     rcx, rax
0x180083e72  jz      loc_180083FEE
0x180083e78  test    byte ptr [rcx+1Ch], 8
0x180083e7c  jz      loc_180083FEE
0x180083e82  cmp     byte ptr [rcx+19h], 2
0x180083e86  jb      loc_180083FEE
0x180083e8c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180083e92  lea     rcx, aFailedToEncode; "Failed to encode frame"
0x180083e99  mov     dword ptr [rsp+160h+UserData], ebx
0x180083e9d  mov     qword ptr [rsp+160h+UserDataCount], rcx
0x180083ea2  lea     r8, WPP_2fd84019dbbc3ac762ccb9482f5e5733_Traceguids
0x180083ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180083eb0  mov     edx, 10h
0x180083eb5  mov     r9d, eax
0x180083eb8  mov     rcx, [rcx+10h]
0x180083ebc  call    WPP_SF_DsD
0x180083ec1  jmp     loc_180083FEE
0x180083ec6  mov     eax, [r12]
0x180083eca  lea     r9, [rsp+160h+var_F8]
0x180083ecf  mov     r8d, [rsi]
0x180083ed2  mov     [rsp+160h+var_30], r14
0x180083eda  lea     ecx, [rax+rax*4]
0x180083edd  lea     r14d, ds:4[rcx*2]
0x180083ee5  mov     rcx, [r15+1E0h]
0x180083eec  mov     eax, r14d
0x180083eef  sub     r8d, r14d
0x180083ef2  add     r12, rax
0x180083ef5  mov     dword ptr [rsp+160h+var_100], r8d
0x180083efa  mov     rdx, r12
0x180083efd  mov     rax, [rcx]
0x180083f00  mov     rax, [rax+18h]
0x180083f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083f09  mov     ebx, eax
0x180083f0b  test    eax, eax
0x180083f0d  jns     short loc_180083F4E
0x180083f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f16  lea     rax, WPP_GLOBAL_Control
0x180083f1d  cmp     rcx, rax
0x180083f20  jz      loc_180083FE6
0x180083f26  test    byte ptr [rcx+1Ch], 8
0x180083f2a  jz      loc_180083FE6
0x180083f30  cmp     byte ptr [rcx+19h], 2
0x180083f34  jb      loc_180083FE6
0x180083f3a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180083f40  mov     edx, 11h
0x180083f45  lea     rcx, aFailedToEncryp; "Failed to encrypt frame"
0x180083f4c  jmp     short loc_180083FB8
0x180083f4e  mov     rcx, [rsp+160h+var_F8]
0x180083f53  mov     [rsp+160h+var_E8], rcx
0x180083f58  test    rcx, rcx
0x180083f5b  jz      short loc_180083F69
0x180083f5d  mov     rax, [rcx]
0x180083f60  mov     rax, [rax+8]
0x180083f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083f69  sub     edi, r14d
0x180083f6c  lea     r8, [rsp+160h+var_E8]
0x180083f71  mov     r9d, edi
0x180083f74  lea     rdx, [rsp+160h+var_100]
0x180083f79  mov     rcx, r12
0x180083f7c  call    ?FormatEncodedBuffer@Avc420DrmCompressor@@CAJPEAEPEAIV?$ComPlainSmartPtr@VIDrmBuffer@@@@K@Z; Avc420DrmCompressor::FormatEncodedBuffer(uchar *,uint *,ComPlainSmartPtr<IDrmBuffer>,ulong)
0x180083f81  mov     ebx, eax
0x180083f83  test    eax, eax
0x180083f85  jns     short loc_180083FDD
0x180083f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f8e  lea     rax, WPP_GLOBAL_Control
0x180083f95  cmp     rcx, rax
0x180083f98  jz      short loc_180083FE6
0x180083f9a  test    byte ptr [rcx+1Ch], 8
0x180083f9e  jz      short loc_180083FE6
0x180083fa0  cmp     byte ptr [rcx+19h], 2
0x180083fa4  jb      short loc_180083FE6
0x180083fa6  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180083fac  mov     edx, 12h
0x180083fb1  lea     rcx, aFailedToFormat_0; "Failed to format encoded buffer"
0x180083fb8  mov     dword ptr [rsp+160h+UserData], ebx
0x180083fbc  lea     r8, WPP_2fd84019dbbc3ac762ccb9482f5e5733_Traceguids
0x180083fc3  mov     qword ptr [rsp+160h+UserDataCount], rcx
0x180083fc8  mov     r9d, eax
0x180083fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180083fd2  mov     rcx, [rcx+10h]
0x180083fd6  call    WPP_SF_DsD
0x180083fdb  jmp     short loc_180083FE6
0x180083fdd  mov     ecx, dword ptr [rsp+160h+var_100]
0x180083fe1  add     ecx, r14d
0x180083fe4  mov     [rsi], ecx
0x180083fe6  mov     r14, [rsp+160h+var_30]
0x180083fee  mov     rdi, [rsp+160h+var_20]
0x180083ff6  mov     rcx, [rsp+160h+var_F8]
0x180083ffb  mov     r15, [rsp+160h+var_38]
0x180084003  mov     r12, [rsp+160h+var_28]
0x18008400b  mov     rsi, [rsp+148h]
0x180084013  test    rcx, rcx
0x180084016  jz      short loc_180084029
0x180084018  mov     [rsp+160h+var_F8], r13
0x18008401d  mov     rax, [rcx]
0x180084020  mov     rax, [rax+10h]
0x180084024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084029  mov     eax, ebx
0x18008402b  mov     rcx, [rbp+60h+var_50]
0x18008402f  xor     rcx, rsp; StackCookie
0x180084032  call    __security_check_cookie
0x180084037  add     rsp, 150h
0x18008403e  pop     r13
0x180084040  pop     rbx
0x180084041  pop     rbp
0x180084042  retn
```
