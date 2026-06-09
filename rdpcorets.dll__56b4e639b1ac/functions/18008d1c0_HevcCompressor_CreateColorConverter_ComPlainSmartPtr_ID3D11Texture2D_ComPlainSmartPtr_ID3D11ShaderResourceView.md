# HevcCompressor::CreateColorConverter(ComPlainSmartPtr<ID3D11Texture2D>,ComPlainSmartPtr<ID3D11ShaderResourceView>,int,int,int)

- ea: `0x18008d1c0`
- end: `0x18008d928`
- name: `?CreateColorConverter@HevcCompressor@@IEAAJV?$ComPlainSmartPtr@UID3D11Texture2D@@@@V?$ComPlainSmartPtr@UID3D11ShaderResourceView@@@@HHH@Z`
- size: `1896`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18008f990`

## callees

- `0x180009628`
- `0x18002e600`
- `0x180033964`
- `0x180033da0`
- `0x1800598d0`
- `0x18008d1c0`
- `0x1800dca30`
- `0x1800de820`
- `0x1800de8c0`
- `0x1800e5560`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008d70b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008d70b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d39b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d64d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d745`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d78c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d82a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d865`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d39b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d64d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d745`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d78c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d82a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008d865`

## pseudocode

```c
__int64 __fastcall HevcCompressor::CreateColorConverter(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        int a6)
{
  int v6; // eax
  __int64 *v7; // r14
  int v8; // esi
  __int64 *v10; // r13
  ColorConversionRGB2YUVXVP *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // esi
  int v15; // r14d
  int v16; // r15d
  int v17; // r12d
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  int ActivityIdPrefix; // eax
  int v23; // edx
  const char *v24; // rcx
  unsigned int v25; // edi
  ColorConversionRGB2YUVShader *v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // esi
  int v30; // r14d
  int v31; // r15d
  int v32; // r12d
  int v33; // r13d
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  int v38; // ecx
  ColorConversionRGB2NV12CPU_AVC420 *v39; // rax
  ColorConversionRGB2NV12CPU_AVC420 *v40; // rax
  int v41; // eax
  int v42; // edx
  ColorConversionRGB2IYUVCPU_AVC420 *v43; // rax
  ColorConversionRGB2IYUVCPU_AVC420 *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-A1h]
  int v50; // [rsp+68h] [rbp-69h]
  int v51; // [rsp+6Ch] [rbp-65h]
  __int64 v53; // [rsp+78h] [rbp-59h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-51h] BYREF
  __int64 v55; // [rsp+90h] [rbp-41h]
  __int64 v56; // [rsp+98h] [rbp-39h]
  __int64 v57; // [rsp+A0h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v58; // [rsp+A8h] [rbp-29h] BYREF
  int *v59; // [rsp+B8h] [rbp-19h]
  int v60; // [rsp+C0h] [rbp-11h]
  int v61; // [rsp+C4h] [rbp-Dh]
  const char *v62; // [rsp+C8h] [rbp-9h]
  __int64 v63; // [rsp+D0h] [rbp-1h]

  v6 = a4;
  v7 = a3;
  v8 = *(_DWORD *)(a1 + 152);
  v10 = (__int64 *)a2;
  v50 = a4;
  v53 = a2;
  v51 = v8;
  if ( *(_QWORD *)(a1 + 56) )
  {
    *(_DWORD *)(a1 + 156) = 0;
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v63 = 10;
      v62 = "Test code";
      *(_DWORD *)&EventDescriptor.Level = 3;
      v58.Ptr = (ULONGLONG)off_1801B76D0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v58.Size = *(unsigned __int16 *)off_1801B76D0;
      v59 = &dword_1801A1824;
      v58.Reserved = 2;
      v60 = 29;
      v61 = 1;
      EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 3u, &v58);
    }
    goto LABEL_41;
  }
  if ( (_DWORD)a4 )
  {
    v11 = (ColorConversionRGB2YUVXVP *)operator new(0x70u);
    if ( v11 )
    {
      v12 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 56LL);
      v53 = v12;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v13 = *v10;
      v14 = *(_DWORD *)(a1 + 104);
      v15 = *(_DWORD *)(a1 + 100);
      v16 = *(_DWORD *)(a1 + 88);
      v17 = *(_DWORD *)(a1 + 84);
      v57 = v13;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v18 = *(_QWORD *)(a1 + 288);
      v55 = v18;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      v19 = *(_QWORD *)(a1 + 280);
      v56 = v19;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      v20 = *(_QWORD *)(a1 + 320);
      *(_QWORD *)&EventDescriptor.Id = v20;
      if ( v20 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 32) + 8LL))(*(_QWORD *)(v20 + 32));
      v21 = ColorConversionRGB2YUVXVP::ColorConversionRGB2YUVXVP(
              v11,
              (__int64)&v57,
              v17,
              v16,
              v15,
              v14,
              a5,
              (__int64)&v53);
      *(_QWORD *)(a1 + 56) = v21;
      if ( v21 )
      {
        *(_DWORD *)(a1 + 368) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          *(_QWORD *)&EventDescriptor.Id = "Using XVP color converter";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            a1,
            (unsigned __int8 *)byte_1801A186B,
            (__int64)a3,
            a4,
            (const char **)&EventDescriptor);
        }
LABEL_40:
        v8 = v51;
        v7 = a3;
        goto LABEL_41;
      }
      v7 = a3;
    }
    else
    {
      *(_QWORD *)(a1 + 56) = 0;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v23 = 69;
    v24 = "ColorConversionRGB2YUVXVP";
    goto LABEL_23;
  }
  if ( v8 )
    goto LABEL_42;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 64) + 96LL))(*(_QWORD *)(a1 + 64))
    && (*(_DWORD *)(a1 + 436) || !a6)
    && !*(_DWORD *)(a1 + 172) )
  {
    v26 = (ColorConversionRGB2YUVShader *)operator new(0x88u);
    if ( v26 )
    {
      v27 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 56LL);
      *(_QWORD *)&EventDescriptor.Id = v27;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      v28 = *(_QWORD *)(a1 + 320);
      v29 = *(_DWORD *)(a1 + 436);
      v30 = *(_DWORD *)(a1 + 104);
      v31 = *(_DWORD *)(a1 + 100);
      v32 = *(_DWORD *)(a1 + 88);
      v33 = *(_DWORD *)(a1 + 84);
      v56 = *a3;
      v55 = v28;
      if ( v28 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v28 + 32) + 8LL))(*(_QWORD *)(v28 + 32));
      v34 = ColorConversionRGB2YUVShader::ColorConversionRGB2YUVShader(
              v26,
              v33,
              v32,
              v31,
              v30,
              a5,
              v29,
              (__int64)&EventDescriptor);
      *(_QWORD *)(a1 + 56) = v34;
      if ( v34 )
      {
        v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 40LL))(v34);
        *(_DWORD *)(a1 + 368) = v35;
        if ( v35 && (unsigned int)dword_1801B76C8 > 4 )
        {
          *(_QWORD *)&EventDescriptor.Id = "Using hardware (RDP shader) color converter";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            a1,
            (unsigned __int8 *)&dword_1801A1894,
            (__int64)a3,
            a4,
            (const char **)&EventDescriptor);
        }
        v10 = (__int64 *)v53;
        goto LABEL_40;
      }
      v10 = (__int64 *)v53;
      v7 = a3;
    }
    else
    {
      *(_QWORD *)(a1 + 56) = 0;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v23 = 70;
    v24 = "ColorConversionRGB2YUVShader";
    goto LABEL_23;
  }
LABEL_41:
  v6 = v50;
LABEL_42:
  v25 = 0;
  if ( !*(_DWORD *)(a1 + 368) && !v6 )
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      *(_QWORD *)&EventDescriptor.Id = "Can't use hardware or XVP color converter, try RDP software conversion.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (unsigned __int8 *)word_1801A1842,
        (__int64)a3,
        a4,
        (const char **)&EventDescriptor);
    }
    v36 = *(_QWORD *)(a1 + 56);
    if ( v36 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 32LL))(v36, 1);
      *(_QWORD *)(a1 + 56) = 0;
    }
    if ( !v8 )
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 64) + 88LL))(*(_QWORD *)(a1 + 64));
      v38 = *(_DWORD *)(a1 + 432);
      if ( v37 )
      {
        if ( !v38 )
        {
          v39 = (ColorConversionRGB2NV12CPU_AVC420 *)operator new(0x50u);
          if ( v39 )
          {
            v40 = ColorConversionRGB2NV12CPU_AVC420::ColorConversionRGB2NV12CPU_AVC420(
                    v39,
                    (struct AdvanceFeatureMap *)(a1 + 216),
                    *(_DWORD *)(a1 + 84),
                    *(_DWORD *)(a1 + 88),
                    *(_DWORD *)(a1 + 100),
                    *(_DWORD *)(a1 + 104),
                    *(_DWORD *)(a1 + 372));
            *(_QWORD *)(a1 + 56) = v40;
            if ( v40 )
              goto LABEL_88;
          }
          else
          {
            *(_QWORD *)(a1 + 56) = 0;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_24;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v23 = 71;
          v24 = "ColorConversionRGB2NV12CPU_AVC420";
          goto LABEL_23;
        }
        v25 = -2147418113;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_85;
        }
        v41 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v42 = 72;
LABEL_84:
        LODWORD(UserData) = -2147418113;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
          v41,
          (__int64)"RDP custom color conversion not available for standard HEVC 444",
          UserData);
        goto LABEL_85;
      }
      if ( v38 )
      {
        v25 = -2147418113;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_85;
        }
        v41 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v42 = 74;
        goto LABEL_84;
      }
      v43 = (ColorConversionRGB2IYUVCPU_AVC420 *)operator new(0x50u);
      if ( v43 )
      {
        v44 = ColorConversionRGB2IYUVCPU_AVC420::ColorConversionRGB2IYUVCPU_AVC420(
                v43,
                (struct AdvanceFeatureMap *)(a1 + 216),
                *(_DWORD *)(a1 + 84),
                *(_DWORD *)(a1 + 88),
                *(_DWORD *)(a1 + 100),
                *(_DWORD *)(a1 + 104),
                *(_DWORD *)(a1 + 372),
                *(_DWORD *)(a1 + 376));
        *(_QWORD *)(a1 + 56) = v44;
        if ( v44 )
          goto LABEL_88;
      }
      else
      {
        *(_QWORD *)(a1 + 56) = 0;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v23 = 73;
      v24 = "ColorConversionRGB2IYUVCPU_AVC420";
LABEL_23:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        (unsigned int)WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
        ActivityIdPrefix,
        (__int64)v24);
LABEL_24:
      v25 = -2147024882;
LABEL_85:
      v45 = *(_QWORD *)(a1 + 56);
      if ( v45 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 32LL))(v45, 1);
      *(_QWORD *)(a1 + 56) = 0;
    }
  }
LABEL_88:
  v46 = *v10;
  if ( *v10 )
  {
    *v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = *v7;
  if ( *v7 )
  {
    *v7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  return v25;
}

```

## disassembly

```asm
0x18008d1c0  mov     r11, rsp
0x18008d1c3  push    rbp
0x18008d1c4  push    rdi
0x18008d1c5  push    r14
0x18008d1c7  push    r15
0x18008d1c9  lea     rbp, [r11-4Fh]
0x18008d1cd  sub     rsp, 0F8h
0x18008d1d4  mov     rax, cs:__security_cookie
0x18008d1db  xor     rax, rsp
0x18008d1de  mov     [rbp+47h+var_40], rax
0x18008d1e2  mov     [r11+20h], rbx
0x18008d1e6  xor     r15d, r15d
0x18008d1e9  mov     eax, r9d
0x18008d1ec  mov     [r11-28h], rsi
0x18008d1f0  mov     r14, r8
0x18008d1f3  mov     esi, [rcx+98h]
0x18008d1f9  mov     rbx, rcx
0x18008d1fc  mov     [r11-30h], r12
0x18008d200  mov     [r11-38h], r13
0x18008d204  mov     r13, rdx
0x18008d207  mov     [rbp+47h+var_B0], eax
0x18008d20a  mov     [rbp+47h+var_A8], r8
0x18008d20e  mov     [rbp+47h+var_A0], rdx
0x18008d212  mov     [rbp+47h+var_AC], esi
0x18008d215  cmp     [rcx+38h], r15
0x18008d219  jnz     loc_18008D664
0x18008d21f  test    eax, eax
0x18008d221  jz      loc_18008D3D6
0x18008d227  mov     ecx, 70h ; 'p'; Size
0x18008d22c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d231  mov     rdi, rax
0x18008d234  test    rax, rax
0x18008d237  jz      loc_18008D36F
0x18008d23d  mov     rcx, [rbx+40h]
0x18008d241  mov     rcx, [rcx+38h]
0x18008d245  mov     [rbp+47h+var_A0], rcx
0x18008d249  test    rcx, rcx
0x18008d24c  jz      short loc_18008D25A
0x18008d24e  mov     rdx, [rcx]
0x18008d251  mov     rax, [rdx+8]
0x18008d255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d25a  mov     rcx, [r13+0]
0x18008d25e  mov     esi, [rbx+68h]
0x18008d261  mov     r14d, [rbx+64h]
0x18008d265  mov     r15d, [rbx+58h]
0x18008d269  mov     r12d, [rbx+54h]
0x18008d26d  mov     [rbp+47h+var_78], rcx
0x18008d271  test    rcx, rcx
0x18008d274  jz      short loc_18008D282
0x18008d276  mov     rax, [rcx]
0x18008d279  mov     rax, [rax+8]
0x18008d27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d282  mov     rcx, [rbx+120h]
0x18008d289  mov     [rbp+47h+var_88], rcx
0x18008d28d  test    rcx, rcx
0x18008d290  jz      short loc_18008D29E
0x18008d292  mov     rax, [rcx]
0x18008d295  mov     rax, [rax+8]
0x18008d299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d29e  mov     rcx, [rbx+118h]
0x18008d2a5  mov     [rbp+47h+var_80], rcx
0x18008d2a9  test    rcx, rcx
0x18008d2ac  jz      short loc_18008D2BA
0x18008d2ae  mov     rax, [rcx]
0x18008d2b1  mov     rax, [rax+8]
0x18008d2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d2ba  mov     rcx, [rbx+140h]
0x18008d2c1  mov     qword ptr [rbp+47h+EventDescriptor.Id], rcx
0x18008d2c5  test    rcx, rcx
0x18008d2c8  jz      short loc_18008D2DA
0x18008d2ca  mov     rcx, [rcx+20h]
0x18008d2ce  mov     rax, [rcx]
0x18008d2d1  mov     rax, [rax+8]
0x18008d2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d2da  lea     rax, [rbp+47h+var_A0]
0x18008d2de  mov     rcx, rdi; this
0x18008d2e1  mov     [rsp+50h], rax; __int64
0x18008d2e6  lea     r9, [rbp+47h+var_88]
0x18008d2ea  mov     eax, [rbp+47h+arg_20]
0x18008d2ed  lea     r8, [rbp+47h+var_80]
0x18008d2f1  mov     [rsp+110h+var_C8], eax; int
0x18008d2f5  lea     rdx, [rbp+47h+EventDescriptor]
0x18008d2f9  mov     [rsp+110h+var_D0], esi; int
0x18008d2fd  lea     rax, [rbp+47h+var_78]
0x18008d301  mov     [rsp+110h+var_D8], r14d; int
0x18008d306  mov     [rsp+110h+var_E0], r15d; int
0x18008d30b  mov     dword ptr [rsp+110h+UserData], r12d; int
0x18008d310  mov     qword ptr [rsp+110h+UserDataCount], rax; __int64
0x18008d315  call    ??0ColorConversionRGB2YUVXVP@@QEAA@V?$ComPlainSmartPtr@VCMFApi@@@@V?$ComPlainSmartPtr@UIMFMediaType@@@@1V?$ComPlainSmartPtr@UID3D11Texture2D@@@@IIIIHV?$ComPlainSmartPtr@UIMFTransform@@@@@Z; ColorConversionRGB2YUVXVP::ColorConversionRGB2YUVXVP(ComPlainSmartPtr<CMFApi>,ComPlainSmartPtr<IMFMediaType>,ComPlainSmartPtr<IMFMediaType>,ComPlainSmartPtr<ID3D11Texture2D>,uint,uint,uint,uint,int,ComPlainSmartPtr<IMFTransform>)
0x18008d31a  mov     [rbx+38h], rax
0x18008d31e  mov     rdx, rax
0x18008d321  test    rax, rax
0x18008d324  jz      short loc_18008D375
0x18008d326  mov     rcx, [rax]
0x18008d329  mov     rax, [rcx+28h]
0x18008d32d  mov     rcx, rdx
0x18008d330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d335  mov     [rbx+170h], eax
0x18008d33b  mov     eax, cs:dword_1801B76C8
0x18008d341  cmp     eax, 4
0x18008d344  jbe     loc_18008D521
0x18008d34a  lea     rax, aUsingXvpColorC; "Using XVP color converter"
0x18008d351  mov     qword ptr [rbp+47h+EventDescriptor.Id], rax
0x18008d355  lea     rdx, byte_1801A186B
0x18008d35c  lea     rax, [rbp+47h+EventDescriptor]
0x18008d360  mov     qword ptr [rsp+110h+UserDataCount], rax
0x18008d365  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008d36a  jmp     loc_18008D521
0x18008d36f  mov     [rbx+38h], r15
0x18008d373  jmp     short loc_18008D37C
0x18008d375  mov     r14, [rbp+47h+var_A8]
0x18008d379  xor     r15d, r15d
0x18008d37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d383  lea     rax, WPP_GLOBAL_Control
0x18008d38a  cmp     rcx, rax
0x18008d38d  jz      short loc_18008D3CC
0x18008d38f  test    byte ptr [rcx+1Ch], 8
0x18008d393  jz      short loc_18008D3CC
0x18008d395  cmp     byte ptr [rcx+19h], 2
0x18008d399  jb      short loc_18008D3CC
0x18008d39b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008d3a1  mov     edx, 45h ; 'E'
0x18008d3a6  lea     rcx, aColorconversio; "ColorConversionRGB2YUVXVP"
0x18008d3ad  mov     qword ptr [rsp+110h+UserDataCount], rcx
0x18008d3b2  lea     r8, WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids
0x18008d3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d3c0  mov     r9d, eax
0x18008d3c3  mov     rcx, [rcx+10h]
0x18008d3c7  call    WPP_SF_Ds
0x18008d3cc  mov     edi, 8007000Eh
0x18008d3d1  jmp     loc_18008D89E
0x18008d3d6  test    esi, esi
0x18008d3d8  jnz     loc_18008D52E
0x18008d3de  mov     rcx, [rcx+40h]
0x18008d3e2  mov     rax, [rcx]
0x18008d3e5  mov     rax, [rax+60h]
0x18008d3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d3ee  test    eax, eax
0x18008d3f0  jz      loc_18008D52B
0x18008d3f6  cmp     [rbx+1B4h], r15d
0x18008d3fd  jnz     short loc_18008D409
0x18008d3ff  cmp     [rbp+47h+arg_28], r15d
0x18008d403  jnz     loc_18008D52B
0x18008d409  cmp     [rbx+0ACh], r15d
0x18008d410  jnz     loc_18008D52B
0x18008d416  mov     ecx, 88h; Size
0x18008d41b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d420  mov     rdi, rax
0x18008d423  test    rax, rax
0x18008d426  jz      loc_18008D611
0x18008d42c  mov     rcx, [rbx+40h]
0x18008d430  mov     rcx, [rcx+38h]
0x18008d434  mov     qword ptr [rbp+47h+EventDescriptor.Id], rcx
0x18008d438  test    rcx, rcx
0x18008d43b  jz      short loc_18008D449
0x18008d43d  mov     rdx, [rcx]
0x18008d440  mov     rax, [rdx+8]
0x18008d444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d449  mov     rcx, [rbx+140h]
0x18008d450  mov     rax, [rbp+47h+var_A8]
0x18008d454  mov     esi, [rbx+1B4h]
0x18008d45a  mov     r14d, [rbx+68h]
0x18008d45e  mov     r15d, [rbx+64h]
0x18008d462  mov     rax, [rax]
0x18008d465  mov     r12d, [rbx+58h]
0x18008d469  mov     r13d, [rbx+54h]
0x18008d46d  mov     [rbp+47h+var_80], rax
0x18008d471  mov     [rbp+47h+var_88], rcx
0x18008d475  test    rcx, rcx
0x18008d478  jz      short loc_18008D48A
0x18008d47a  mov     rcx, [rcx+20h]
0x18008d47e  mov     rax, [rcx]
0x18008d481  mov     rax, [rax+8]
0x18008d485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d48a  mov     r8, [rbp+47h+var_80]
0x18008d48e  lea     rax, [rbp+47h+EventDescriptor]
0x18008d492  mov     [rsp+50h], rax; __int64
0x18008d497  lea     r9, [rbx+0D8h]
0x18008d49e  mov     eax, [rbp+47h+arg_20]
0x18008d4a1  lea     rdx, [rbp+47h+var_88]
0x18008d4a5  mov     [rsp+110h+var_C8], esi; int
0x18008d4a9  mov     rcx, rdi; this
0x18008d4ac  mov     [rsp+110h+var_D0], eax; int
0x18008d4b0  mov     [rsp+110h+var_D8], r14d; int
0x18008d4b5  mov     [rsp+110h+var_E0], r15d; int
0x18008d4ba  mov     dword ptr [rsp+110h+UserData], r12d; int
0x18008d4bf  mov     [rsp+110h+UserDataCount], r13d; int
0x18008d4c4  call    ??0ColorConversionRGB2YUVShader@@QEAA@V?$ComPlainSmartPtr@VCMFApi@@@@PEAUID3D11ShaderResourceView@@AEAVAdvanceFeatureMap@@IIIIHHV?$ComPlainSmartPtr@UIMFTransform@@@@@Z; ColorConversionRGB2YUVShader::ColorConversionRGB2YUVShader(ComPlainSmartPtr<CMFApi>,ID3D11ShaderResourceView *,AdvanceFeatureMap &,uint,uint,uint,uint,int,int,ComPlainSmartPtr<IMFTransform>)
0x18008d4c9  mov     [rbx+38h], rax
0x18008d4cd  mov     rdx, rax
0x18008d4d0  test    rax, rax
0x18008d4d3  jz      loc_18008D617
0x18008d4d9  mov     rcx, [rax]
0x18008d4dc  mov     rax, [rcx+28h]
0x18008d4e0  mov     rcx, rdx
0x18008d4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d4e8  mov     [rbx+170h], eax
0x18008d4ee  test    eax, eax
0x18008d4f0  jz      short loc_18008D51D
0x18008d4f2  mov     eax, cs:dword_1801B76C8
0x18008d4f8  cmp     eax, 4
0x18008d4fb  jbe     short loc_18008D51D
0x18008d4fd  lea     rax, aUsingHardwareR; "Using hardware (RDP shader) color conve"...
0x18008d504  mov     qword ptr [rbp+47h+EventDescriptor.Id], rax
0x18008d508  lea     rdx, dword_1801A1894
0x18008d50f  lea     rax, [rbp+47h+EventDescriptor]
0x18008d513  mov     qword ptr [rsp+110h+UserDataCount], rax
0x18008d518  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008d51d  mov     r13, [rbp+47h+var_A0]
0x18008d521  mov     esi, [rbp+47h+var_AC]
0x18008d524  xor     r15d, r15d
0x18008d527  mov     r14, [rbp+47h+var_A8]
0x18008d52b  mov     eax, [rbp+47h+var_B0]
0x18008d52e  cmp     dword ptr [rbx+170h], 0
0x18008d535  mov     edi, r15d
0x18008d538  jnz     loc_18008D8BC
0x18008d53e  test    eax, eax
0x18008d540  jnz     loc_18008D8BC
0x18008d546  mov     eax, cs:dword_1801B76C8
0x18008d54c  cmp     eax, 4
0x18008d54f  jbe     short loc_18008D571
0x18008d551  lea     rax, aCanTUseHardwar; "Can't use hardware or XVP color convert"...
0x18008d558  mov     qword ptr [rbp+47h+EventDescriptor.Id], rax
0x18008d55c  lea     rdx, word_1801A1842
0x18008d563  lea     rax, [rbp+47h+EventDescriptor]
0x18008d567  mov     qword ptr [rsp+110h+UserDataCount], rax
0x18008d56c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008d571  mov     rcx, [rbx+38h]
0x18008d575  test    rcx, rcx
0x18008d578  jz      short loc_18008D58F
0x18008d57a  mov     rax, [rcx]
0x18008d57d  mov     edx, 1
0x18008d582  mov     rax, [rax+20h]
0x18008d586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d58b  mov     [rbx+38h], r15
0x18008d58f  test    esi, esi
0x18008d591  jnz     loc_18008D8BC
0x18008d597  mov     rcx, [rbx+40h]
0x18008d59b  mov     rax, [rcx]
0x18008d59e  mov     rax, [rax+58h]
0x18008d5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d5a7  mov     ecx, [rbx+1B0h]
0x18008d5ad  test    eax, eax
0x18008d5af  jz      loc_18008D79C
0x18008d5b5  test    ecx, ecx
0x18008d5b7  jnz     loc_18008D75C
0x18008d5bd  mov     ecx, 50h ; 'P'; Size
0x18008d5c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008d5c7  test    rax, rax
0x18008d5ca  jz      loc_18008D716
0x18008d5d0  mov     ecx, [rbx+174h]
0x18008d5d6  lea     rdx, [rbx+0D8h]; struct AdvanceFeatureMap *
0x18008d5dd  mov     r9d, [rbx+58h]; unsigned int
0x18008d5e1  mov     r8d, [rbx+54h]; unsigned int
0x18008d5e5  mov     [rsp+110h+var_E0], ecx; int
0x18008d5e9  mov     ecx, [rbx+68h]
0x18008d5ec  mov     dword ptr [rsp+110h+UserData], ecx; unsigned int
0x18008d5f0  mov     ecx, [rbx+64h]
0x18008d5f3  mov     [rsp+110h+UserDataCount], ecx; unsigned int
0x18008d5f7  mov     rcx, rax; this
0x18008d5fa  call    ??0ColorConversionRGB2NV12CPU_AVC420@@QEAA@AEAVAdvanceFeatureMap@@IIIIH@Z; ColorConversionRGB2NV12CPU_AVC420::ColorConversionRGB2NV12CPU_AVC420(AdvanceFeatureMap &,uint,uint,uint,uint,int)
0x18008d5ff  mov     [rbx+38h], rax
0x18008d603  test    rax, rax
0x18008d606  jnz     loc_18008D8BC
0x18008d60c  jmp     loc_18008D71A
0x18008d611  mov     [rbx+38h], r15
0x18008d615  jmp     short loc_18008D622
0x18008d617  mov     r13, [rbp+47h+var_A0]
0x18008d61b  xor     r15d, r15d
0x18008d61e  mov     r14, [rbp+47h+var_A8]
0x18008d622  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d629  lea     rax, WPP_GLOBAL_Control
0x18008d630  cmp     rcx, rax
0x18008d633  jz      loc_18008D3CC
0x18008d639  test    byte ptr [rcx+1Ch], 8
0x18008d63d  jz      loc_18008D3CC
0x18008d643  cmp     byte ptr [rcx+19h], 2
0x18008d647  jb      loc_18008D3CC
0x18008d64d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008d653  mov     edx, 46h ; 'F'
0x18008d658  lea     rcx, aColorconversio_7; "ColorConversionRGB2YUVShader"
0x18008d65f  jmp     loc_18008D3AD
0x18008d664  mov     [rcx+9Ch], r15d
0x18008d66b  mov     eax, cs:dword_1801B76C8
0x18008d671  cmp     eax, 3
0x18008d674  jbe     loc_18008D52B
0x18008d67a  lea     rax, aTestCode; "Test code"
0x18008d681  mov     [rbp+47h+var_48], 0Ah
0x18008d689  mov     [rbp+47h+var_50], rax
0x18008d68d  lea     rcx, _TraceLoggingMetadata
0x18008d694  movzx   eax, cs:word_1801A181A
0x18008d69b  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18008d69f  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18008d6a2  xor     r9d, r9d; RelatedActivityId
0x18008d6a5  mov     rax, cs:off_1801B76D0
0x18008d6ac  xor     r8d, r8d; ActivityId
0x18008d6af  mov     [rbp+47h+var_70.Ptr], rax
0x18008d6b3  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x18008d6ba  mov     [rbp+47h+EventDescriptor.Keyword], r15
0x18008d6be  movzx   eax, word ptr [rax]
  ... truncated ...
```
