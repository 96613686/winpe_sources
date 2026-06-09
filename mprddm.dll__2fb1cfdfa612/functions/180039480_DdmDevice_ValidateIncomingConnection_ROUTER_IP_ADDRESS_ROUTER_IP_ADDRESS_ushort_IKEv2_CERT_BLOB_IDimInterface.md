# DdmDevice::ValidateIncomingConnection(_ROUTER_IP_ADDRESS *,_ROUTER_IP_ADDRESS *,ushort *,_IKEv2_CERT_BLOB *,IDimInterface * *)

- ea: `0x180039480`
- end: `0x180039b15`
- name: `?ValidateIncomingConnection@DdmDevice@@QEAAKPEAU_ROUTER_IP_ADDRESS@@0PEAGPEAU_IKEv2_CERT_BLOB@@PEAPEAUIDimInterface@@@Z`
- size: `1685`
- prototype: `unsigned int __fastcall(DdmDevice *__hidden this, struct _ROUTER_IP_ADDRESS *, struct _ROUTER_IP_ADDRESS *, unsigned __int16 *, struct _IKEv2_CERT_BLOB *, struct IDimInterface **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800342d0`

## callees

- `0x180002bbe`
- `0x180007c50`
- `0x180025c98`
- `0x180039480`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003953e`
- `msvcrt!_itow_s` at `0x1800395d8`
- `msvcrt!_itow_s` at `0x1800396f4`
- `msvcrt!_itow_s` at `0x1800397cd`
- `msvcrt!_itow_s` at `0x180039944`
- `msvcrt!_itow_s` at `0x1800399f7`
- `msvcrt!_itow_s` at `0x18003953e`
- `msvcrt!_itow_s` at `0x1800395d8`
- `msvcrt!_itow_s` at `0x1800396f4`
- `msvcrt!_itow_s` at `0x1800397cd`
- `msvcrt!_itow_s` at `0x180039944`
- `msvcrt!_itow_s` at `0x1800399f7`

## string_xrefs

- `0x180039547`: `DdmDevice::ValidateIncomingConnection`
- `0x1800395e1`: `DdmDevice::ValidateIncomingConnection: Rejecting incoming connection, server offline. Error: %d`
- `0x180039a16`: `The interface %ws is already connected port=%d`

## pseudocode

```c
__int64 __fastcall DdmDevice::ValidateIncomingConnection(
        DdmDevice *this,
        struct _ROUTER_IP_ADDRESS *a2,
        struct _ROUTER_IP_ADDRESS *a3,
        unsigned __int16 *a4,
        struct _IKEv2_CERT_BLOB *a5,
        struct IDimInterface **a6)
{
  int *v10; // rdi
  int v11; // ecx
  int v13; // r14d
  int v14; // ecx
  int v15; // eax
  struct IDimInterface *v16; // rax
  struct IDimInterface *v17; // rdi
  int v18; // ecx
  unsigned int v19; // esi
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rbx
  bool v23; // zf
  struct IDimInterface *v24; // rcx
  __int64 (__fastcall *v25)(struct IDimInterface *, _BYTE *); // rax
  _BYTE *v26; // rdx
  __int128 *v27; // rax
  GUID v28; // xmm0
  char v29; // al
  int v30; // ecx
  int v31; // ecx
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rbx
  struct IDimInterface *v35; // rcx
  __int64 (__fastcall *v36)(struct IDimInterface *, _BYTE *); // rax
  _BYTE *v37; // rdx
  __int128 *v38; // rax
  int v39; // [rsp+40h] [rbp-C0h] BYREF
  struct IDimInterface **v40; // [rsp+48h] [rbp-B8h]
  __int128 v41; // [rsp+50h] [rbp-B0h] BYREF
  GUID Buf1; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v43[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v45[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v46[16]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Buffer[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v48; // [rsp+B4h] [rbp-4Ch]
  __int128 v49; // [rsp+C4h] [rbp-3Ch]
  int v50; // [rsp+D4h] [rbp-2Ch]
  int v51; // [rsp+E0h] [rbp-20h] BYREF
  char v52[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v40 = a6;
  v39 = 0;
  v51 = 0;
  Buf1 = GUID_NULL;
  memset_0(v52, 0, sizeof(v52));
  *(_DWORD *)Buffer = 0;
  v48 = 0;
  v50 = 0;
  v49 = 0;
  v41 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v51) = 0;
    v10 = (int *)((char *)this + 96);
    Buffer[0] = 0;
    if ( this && *v10 != -1 )
      _itow_s(*v10, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v51, L"%s (hport: %ld)", L"DdmDevice::ValidateIncomingConnection", *(_QWORD *)v10);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v51,
        (unsigned int)&v41,
        0,
        (__int64)Buffer);
  }
  if ( !(unsigned int)((__int64 (*)(void))qword_1800C86B0)() )
  {
    v13 = 1;
    v14 = (unsigned __int16)*((_DWORD *)this + 34);
    switch ( v14 )
    {
      case 16:
        v15 = 9;
        break;
      case 15:
        v15 = 7;
        break;
      case 9:
        v15 = 3;
        break;
      case 8:
        v15 = 1;
        break;
      default:
        v15 = -1;
        if ( v14 == 14 )
          v15 = 5;
        break;
    }
    v16 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, struct _ROUTER_IP_ADDRESS *, struct _ROUTER_IP_ADDRESS *, unsigned __int16 *, struct _IKEv2_CERT_BLOB *, int))(*(_QWORD *)g_pIDimInterfaceTable + 56LL))(
                                    g_pIDimInterfaceTable,
                                    a2,
                                    a3,
                                    a4,
                                    a5,
                                    v15);
    v17 = v16;
    if ( !v16 )
    {
      v13 = 0;
      if ( !dword_1800C8654 && *((char *)this + 132) >= 0 )
      {
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          v18 = *((_DWORD *)this + 24);
          LOWORD(v51) = 0;
          Buffer[0] = 0;
          if ( v18 != -1 )
            _itow_s(v18, Buffer, 0x14u, 10);
          FormatRRASErrorString(&v51, L"A client tried to connect on a router only port = %ld", *((_QWORD *)this + 12));
          if ( (byte_1800C8404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v51,
              (unsigned int)&v41,
              0,
              (__int64)Buffer);
        }
        return 913;
      }
LABEL_61:
      v19 = 0;
      if ( !v17 )
        return v19;
      if ( !v13 )
      {
LABEL_77:
        *v40 = v17;
        return v19;
      }
LABEL_75:
      (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 8LL))(v17);
      if ( v19 || !v17 )
        return v19;
      goto LABEL_77;
    }
    (**(void (__fastcall ***)(struct IDimInterface *))v16)(v16);
    if ( (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 72LL))(v17) != 3
      && (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 72LL))(v17) != 4 )
    {
      if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 104LL))(v17) & 4) != 0 )
      {
        v28 = *(GUID *)(*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL))(v17, v43);
        v39 = 0;
        Buf1 = v28;
        if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        {
          v29 = dword_1800C864C;
          v39 = dword_1800C864C;
        }
        else
        {
          GetRoutingDomainConfigData(&Buf1, 0x8000, 4, &v39);
          v29 = v39;
        }
        if ( (v29 & 0x24) == 0 )
        {
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v30 = *((_DWORD *)this + 24);
            LOWORD(v51) = 0;
            Buffer[0] = 0;
            if ( v30 != -1 )
              _itow_s(v30, Buffer, 0x14u, 10);
            FormatRRASErrorString(&v51, L"A router tried to connect on a client only port=%ld", *((_QWORD *)this + 12));
            if ( (byte_1800C8404 & 0x10) != 0 )
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDdmParamTraceInfo,
                (unsigned int)&v51,
                (unsigned int)&v41,
                0,
                (__int64)Buffer);
          }
          v19 = 914;
          goto LABEL_75;
        }
        if ( dword_1800C8654 )
          *((_DWORD *)this + 33) |= 0x40u;
        goto LABEL_61;
      }
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_48;
      v20 = *((_DWORD *)this + 24);
      LOWORD(v51) = 0;
      Buffer[0] = 0;
      if ( v20 != -1 )
        _itow_s(v20, Buffer, 0x14u, 10);
      v21 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 280LL))(v17);
      FormatRRASErrorString(&v51, L"The interface %ws is disabled", v21);
      if ( (byte_1800C8404 & 8) == 0 )
      {
LABEL_48:
        v19 = 916;
        goto LABEL_75;
      }
      v22 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 280LL))(v17);
      v23 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL))(v17, v44) == 0;
      v24 = v17;
      v25 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL);
      if ( v23 )
      {
        if ( !v25(v17, v46) )
        {
          v27 = &v41;
          goto LABEL_47;
        }
        v26 = v43;
        v24 = v17;
        v25 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL);
      }
      else
      {
        v26 = v45;
      }
      LODWORD(v27) = v25(v24, v26);
LABEL_47:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v51,
        (_DWORD)v27,
        v22,
        (__int64)Buffer);
      goto LABEL_48;
    }
    v19 = 901;
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_75;
    v31 = *((_DWORD *)this + 24);
    LOWORD(v51) = 0;
    Buffer[0] = 0;
    if ( v31 != -1 )
      _itow_s(v31, Buffer, 0x14u, 10);
    v32 = *((_QWORD *)this + 12);
    v33 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 280LL))(v17);
    FormatRRASErrorString(&v51, L"The interface %ws is already connected port=%d", v33, v32);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_75;
    v34 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v17 + 280LL))(v17);
    v23 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL))(v17, v43) == 0;
    v35 = v17;
    v36 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL);
    if ( v23 )
    {
      if ( !v36(v17, v45) )
      {
        v38 = &v41;
        goto LABEL_74;
      }
      v37 = v44;
      v35 = v17;
      v36 = *(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v17 + 360LL);
    }
    else
    {
      v37 = v46;
    }
    LODWORD(v38) = v36(v35, v37);
LABEL_74:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v51,
      (_DWORD)v38,
      v34,
      (__int64)Buffer);
    goto LABEL_75;
  }
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v51) = 0;
    Buffer[0] = 0;
    if ( this )
    {
      v11 = *((_DWORD *)this + 24);
      if ( v11 != -1 )
        _itow_s(v11, Buffer, 0x14u, 10);
    }
    FormatRRASErrorString(
      &v51,
      L"DdmDevice::ValidateIncomingConnection: Rejecting incoming connection, server offline. Error: %d",
      900);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v51,
        (unsigned int)&v41,
        0,
        (__int64)Buffer);
  }
  return 900;
}

```

## disassembly

```asm
0x180039480  push    rbp
0x180039482  push    rbx
0x180039483  push    rsi
0x180039484  push    rdi
0x180039485  push    r12
0x180039487  push    r13
0x180039489  push    r14
0x18003948b  push    r15
0x18003948d  lea     rbp, [rsp-7F8h]
0x180039495  sub     rsp, 8F8h
0x18003949c  mov     rax, cs:__security_cookie
0x1800394a3  xor     rax, rsp
0x1800394a6  mov     [rbp+830h+var_50], rax
0x1800394ad  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800394b4  mov     rax, [rbp+830h+arg_28]
0x1800394bb  mov     r15, r8
0x1800394be  mov     r13, [rbp+830h+arg_20]
0x1800394c5  mov     rsi, rdx
0x1800394c8  mov     rbx, rcx
0x1800394cb  mov     [rsp+930h+var_8E8], rax
0x1800394d0  xor     r14d, r14d
0x1800394d3  lea     rcx, [rbp+830h+var_84C]; void *
0x1800394d7  xor     edx, edx; Val
0x1800394d9  mov     [rsp+930h+var_8F0], r14d
0x1800394de  mov     r8d, 7FCh; Size
0x1800394e4  mov     [rbp+830h+var_850], r14d
0x1800394e8  movdqu  [rsp+930h+Buf1], xmm0
0x1800394ee  mov     r12, r9
0x1800394f1  call    memset_0
0x1800394f6  xorps   xmm0, xmm0
0x1800394f9  mov     dword ptr [rbp+830h+Buffer], r14d
0x1800394fd  xor     eax, eax
0x1800394ff  test    cs:byte_1800C8404, 10h
0x180039506  movups  [rbp+830h+var_87C], xmm0
0x18003950a  mov     [rbp+830h+var_85C], eax
0x18003950d  movups  [rbp+830h+var_86C], xmm0
0x180039511  movups  [rsp+930h+var_8E0], xmm0
0x180039516  jz      short loc_180039591
0x180039518  mov     word ptr [rbp+830h+var_850], r14w
0x18003951d  lea     rdi, [rbx+60h]
0x180039521  mov     [rbp+830h+Buffer], r14w
0x180039526  test    rbx, rbx
0x180039529  jz      short loc_180039544
0x18003952b  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18003952e  jz      short loc_180039544
0x180039530  mov     ecx, [rdi]; Value
0x180039532  lea     r9d, [r14+0Ah]; Radix
0x180039536  lea     r8d, [r14+14h]; BufferCount
0x18003953a  lea     rdx, [rbp+830h+Buffer]; Buffer
0x18003953e  call    cs:__imp__itow_s
0x180039544  mov     r9, [rdi]
0x180039547  lea     r8, aDdmdeviceValid_0; "DdmDevice::ValidateIncomingConnection"
0x18003954e  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x180039555  lea     rcx, [rbp+830h+var_850]
0x180039559  call    FormatRRASErrorString
0x18003955e  test    cs:byte_1800C8404, 10h
0x180039565  jz      short loc_180039591
0x180039567  lea     rax, [rbp+830h+Buffer]
0x18003956b  mov     [rsp+930h+var_908], rax
0x180039570  lea     r9, [rsp+930h+var_8E0]
0x180039575  lea     r8, [rbp+830h+var_850]
0x180039579  mov     [rsp+930h+var_910], r14
0x18003957e  lea     rdx, RasDdmParamTraceInfo
0x180039585  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003958c  call    McTemplateU0zjzz_EventWriteTransfer
0x180039591  mov     rax, cs:qword_1800C86B0
0x180039598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003959d  test    eax, eax
0x18003959f  jz      loc_18003962B
0x1800395a5  test    cs:byte_1800C8404, 10h
0x1800395ac  mov     edi, 384h
0x1800395b1  jz      short loc_180039624
0x1800395b3  mov     word ptr [rbp+830h+var_850], r14w
0x1800395b8  mov     [rbp+830h+Buffer], r14w
0x1800395bd  test    rbx, rbx
0x1800395c0  jz      short loc_1800395DE
0x1800395c2  mov     ecx, [rbx+60h]; Value
0x1800395c5  cmp     ecx, 0FFFFFFFFh
0x1800395c8  jz      short loc_1800395DE
0x1800395ca  mov     r9d, 0Ah; Radix
0x1800395d0  lea     rdx, [rbp+830h+Buffer]; Buffer
0x1800395d4  lea     r8d, [r9+0Ah]; BufferCount
0x1800395d8  call    cs:__imp__itow_s
0x1800395de  mov     r8d, edi
0x1800395e1  lea     rdx, aDdmdeviceValid; "DdmDevice::ValidateIncomingConnection: "...
0x1800395e8  lea     rcx, [rbp+830h+var_850]
0x1800395ec  call    FormatRRASErrorString
0x1800395f1  test    cs:byte_1800C8404, 10h
0x1800395f8  jz      short loc_180039624
0x1800395fa  lea     rdx, [rbp+830h+Buffer]
0x1800395fe  mov     [rsp+930h+var_908], rdx
0x180039603  lea     r9, [rsp+930h+var_8E0]
0x180039608  lea     rdx, RasDdmParamTraceInfo
0x18003960f  mov     [rsp+930h+var_910], r14
0x180039614  lea     r8, [rbp+830h+var_850]
0x180039618  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003961f  call    McTemplateU0zjzz_EventWriteTransfer
0x180039624  mov     eax, edi
0x180039626  jmp     loc_180039AF2
0x18003962b  mov     r10, cs:g_pIDimInterfaceTable
0x180039632  mov     r14d, 1
0x180039638  mov     ecx, [rbx+88h]
0x18003963e  movzx   ecx, cx
0x180039641  mov     rax, [r10]
0x180039644  mov     r11, [rax+38h]
0x180039648  cmp     ecx, 10h
0x18003964b  jnz     short loc_180039652
0x18003964d  lea     eax, [rcx-7]
0x180039650  jmp     short loc_180039684
0x180039652  cmp     ecx, 0Fh
0x180039655  jnz     short loc_18003965C
0x180039657  lea     eax, [rcx-8]
0x18003965a  jmp     short loc_180039684
0x18003965c  mov     eax, 9
0x180039661  cmp     ecx, eax
0x180039663  jnz     short loc_18003966C
0x180039665  mov     eax, 3
0x18003966a  jmp     short loc_180039684
0x18003966c  cmp     ecx, 8
0x18003966f  jnz     short loc_180039676
0x180039671  mov     eax, r14d
0x180039674  jmp     short loc_180039684
0x180039676  or      eax, 0FFFFFFFFh
0x180039679  mov     edi, 5
0x18003967e  cmp     ecx, 0Eh
0x180039681  cmovz   eax, edi
0x180039684  mov     dword ptr [rsp+930h+var_908], eax
0x180039688  mov     r9, r12
0x18003968b  mov     rax, r11
0x18003968e  mov     [rsp+930h+var_910], r13
0x180039693  mov     r8, r15
0x180039696  mov     rdx, rsi
0x180039699  mov     rcx, r10
0x18003969c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396a1  xor     r15d, r15d
0x1800396a4  mov     rdi, rax
0x1800396a7  test    rax, rax
0x1800396aa  jnz     loc_18003974B
0x1800396b0  cmp     cs:dword_1800C8654, r15d
0x1800396b7  mov     r14d, r15d
0x1800396ba  jnz     loc_1800399AB
0x1800396c0  test    byte ptr [rbx+84h], 80h
0x1800396c7  jnz     loc_1800399AB
0x1800396cd  test    cs:byte_1800C8404, 10h
0x1800396d4  jz      short loc_180039741
0x1800396d6  mov     ecx, [rbx+60h]; Value
0x1800396d9  mov     word ptr [rbp+830h+var_850], r15w
0x1800396de  mov     [rbp+830h+Buffer], r15w
0x1800396e3  cmp     ecx, 0FFFFFFFFh
0x1800396e6  jz      short loc_1800396FA
0x1800396e8  lea     r9d, [rax+0Ah]; Radix
0x1800396ec  lea     r8d, [rax+14h]; BufferCount
0x1800396f0  lea     rdx, [rbp+830h+Buffer]; Buffer
0x1800396f4  call    cs:__imp__itow_s
0x1800396fa  mov     r8, [rbx+60h]
0x1800396fe  lea     rdx, aAClientTriedTo; "A client tried to connect on a router o"...
0x180039705  lea     rcx, [rbp+830h+var_850]
0x180039709  call    FormatRRASErrorString
0x18003970e  test    cs:byte_1800C8404, 10h
0x180039715  jz      short loc_180039741
0x180039717  lea     rax, [rbp+830h+Buffer]
0x18003971b  mov     [rsp+930h+var_908], rax
0x180039720  lea     r9, [rsp+930h+var_8E0]
0x180039725  lea     r8, [rbp+830h+var_850]
0x180039729  mov     [rsp+930h+var_910], r15
0x18003972e  lea     rdx, RasDdmParamTraceInfo
0x180039735  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003973c  call    McTemplateU0zjzz_EventWriteTransfer
0x180039741  mov     esi, 391h
0x180039746  jmp     loc_180039AF0
0x18003974b  mov     rax, [rax]
0x18003974e  mov     rcx, rdi
0x180039751  mov     rax, [rax]
0x180039754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039759  mov     rax, [rdi]
0x18003975c  mov     rcx, rdi
0x18003975f  mov     rax, [rax+48h]
0x180039763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039768  cmp     eax, 3
0x18003976b  jz      loc_1800399C5
0x180039771  mov     rax, [rdi]
0x180039774  mov     rcx, rdi
0x180039777  mov     rax, [rax+48h]
0x18003977b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039780  cmp     eax, 4
0x180039783  jz      loc_1800399C5
0x180039789  mov     rax, [rdi]
0x18003978c  mov     rcx, rdi
0x18003978f  mov     rax, [rax+68h]
0x180039793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039798  test    al, 4
0x18003979a  jnz     loc_1800398A9
0x1800397a0  test    cs:byte_1800C8404, 8
0x1800397a7  jz      loc_18003989F
0x1800397ad  mov     ecx, [rbx+60h]; Value
0x1800397b0  mov     word ptr [rbp+830h+var_850], r15w
0x1800397b5  mov     [rbp+830h+Buffer], r15w
0x1800397ba  cmp     ecx, 0FFFFFFFFh
0x1800397bd  jz      short loc_1800397D3
0x1800397bf  mov     r9d, 0Ah; Radix
0x1800397c5  lea     rdx, [rbp+830h+Buffer]; Buffer
0x1800397c9  lea     r8d, [r9+0Ah]; BufferCount
0x1800397cd  call    cs:__imp__itow_s
0x1800397d3  mov     rax, [rdi]
0x1800397d6  mov     rcx, rdi
0x1800397d9  mov     rax, [rax+118h]
0x1800397e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397e5  mov     r8, rax
0x1800397e8  lea     rdx, aTheInterfaceWs_1; "The interface %ws is disabled"
0x1800397ef  lea     rcx, [rbp+830h+var_850]
0x1800397f3  call    FormatRRASErrorString
0x1800397f8  test    cs:byte_1800C8404, 8
0x1800397ff  jz      loc_18003989F
0x180039805  mov     rax, [rdi]
0x180039808  mov     rcx, rdi
0x18003980b  mov     rax, [rax+118h]
0x180039812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039817  mov     rcx, [rdi]
0x18003981a  lea     rdx, [rbp+830h+var_8B0]
0x18003981e  mov     rbx, rax
0x180039821  mov     rax, [rcx+168h]
0x180039828  mov     rcx, rdi
0x18003982b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039830  mov     rcx, [rdi]
0x180039833  test    rax, rax
0x180039836  mov     r8, [rcx+168h]
0x18003983d  mov     rcx, rdi
0x180039840  mov     rax, r8
0x180039843  jz      short loc_18003984B
0x180039845  lea     rdx, [rbp+830h+var_8A0]
0x180039849  jmp     short loc_18003986B
0x18003984b  lea     rdx, [rbp+830h+var_890]
0x18003984f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039854  test    rax, rax
0x180039857  jz      short loc_180039872
0x180039859  mov     rax, [rdi]
0x18003985c  lea     rdx, [rsp+930h+var_8C0]
0x180039861  mov     rcx, rdi
0x180039864  mov     rax, [rax+168h]
0x18003986b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039870  jmp     short loc_180039877
0x180039872  lea     rax, [rsp+930h+var_8E0]
0x180039877  lea     rcx, [rbp+830h+Buffer]
0x18003987b  mov     r9, rax
0x18003987e  mov     [rsp+930h+var_908], rcx
0x180039883  lea     r8, [rbp+830h+var_850]
0x180039887  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003988e  mov     [rsp+930h+var_910], rbx
0x180039893  lea     rdx, RasDdmParamTraceError
0x18003989a  call    McTemplateU0zjzz_EventWriteTransfer
0x18003989f  mov     esi, 394h
0x1800398a4  jmp     loc_180039AD0
0x1800398a9  mov     rax, [rdi]
0x1800398ac  lea     rdx, [rsp+930h+var_8C0]
0x1800398b1  mov     rcx, rdi
0x1800398b4  mov     rax, [rax+168h]
0x1800398bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398c0  mov     r8d, 10h; Size
0x1800398c6  lea     rdx, GUID_NULL; Buf2
0x1800398cd  lea     rcx, [rsp+930h+Buf1]; Buf1
0x1800398d2  movups  xmm0, xmmword ptr [rax]
0x1800398d5  mov     [rsp+930h+var_8F0], r15d
0x1800398da  movdqu  [rsp+930h+Buf1], xmm0
0x1800398e0  call    memcmp_0
0x1800398e5  test    eax, eax
0x1800398e7  jz      short loc_180039909
0x1800398e9  lea     r9, [rsp+930h+var_8F0]
0x1800398ee  mov     edx, 8000h
0x1800398f3  mov     r8d, 4
0x1800398f9  lea     rcx, [rsp+930h+Buf1]
0x1800398fe  call    GetRoutingDomainConfigData
0x180039903  mov     eax, [rsp+930h+var_8F0]
0x180039907  jmp     short loc_180039913
0x180039909  mov     eax, cs:dword_1800C864C
0x18003990f  mov     [rsp+930h+var_8F0], eax
0x180039913  test    al, 24h
0x180039915  jnz     loc_18003999B
0x18003991b  test    cs:byte_1800C8404, 10h
0x180039922  jz      short loc_180039991
0x180039924  mov     ecx, [rbx+60h]; Value
0x180039927  mov     word ptr [rbp+830h+var_850], r15w
0x18003992c  mov     [rbp+830h+Buffer], r15w
0x180039931  cmp     ecx, 0FFFFFFFFh
0x180039934  jz      short loc_18003994A
0x180039936  mov     r9d, 0Ah; Radix
0x18003993c  lea     rdx, [rbp+830h+Buffer]; Buffer
0x180039940  lea     r8d, [r9+0Ah]; BufferCount
0x180039944  call    cs:__imp__itow_s
0x18003994a  mov     r8, [rbx+60h]
0x18003994e  lea     rdx, aARouterTriedTo; "A router tried to connect on a client o"...
0x180039955  lea     rcx, [rbp+830h+var_850]
0x180039959  call    FormatRRASErrorString
0x18003995e  test    cs:byte_1800C8404, 10h
0x180039965  jz      short loc_180039991
0x180039967  lea     rax, [rbp+830h+Buffer]
0x18003996b  mov     [rsp+930h+var_908], rax
0x180039970  lea     r9, [rsp+930h+var_8E0]
0x180039975  lea     r8, [rbp+830h+var_850]
0x180039979  mov     [rsp+930h+var_910], r15
0x18003997e  lea     rdx, RasDdmParamTraceInfo
  ... truncated ...
```
