# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelOfferEx(_GUID const &,_GUID const &,uint,Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IFileIoChannelEvents * *)

- ea: `0x180033690`
- end: `0x180033a6f`
- name: `?OnChannelOfferEx@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJAEBU_GUID@@0IPEAUIFileIoChannel@34@PEAPEAUIFileIoChannelEvents@34@@Z`
- size: `991`
- prototype: `int(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, struct Rdp::Avenc::IFileIoChannel *, struct Rdp::Avenc::IFileIoChannelEvents **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800080cc`
- `0x18000d420`
- `0x18000e848`
- `0x18000ec04`
- `0x1800199cc`
- `0x180021ad0`
- `0x18002224c`
- `0x1800240b8`
- `0x180033690`
- `0x180089010`

## string_xrefs

- `0x180033a48`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800336ef`: `Failed to open property store`
- `0x180033922`: `Failed to open property store`
- `0x18003372e`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x180033961`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x1800337d2`: `Failed to start FileIo graphics read channel`
- `0x180033774`: `Failed to start FileIo graphics write channel`
- `0x180033a5c`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`
- `0x1800336fe`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x180033931`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::OnChannelOfferEx(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const char *a4,
        struct Rdp::Avenc::IFileIoChannel *a5,
        struct Rdp::Avenc::IFileIoChannelEvents **a6)
{
  unsigned int v6; // r14d
  struct Rdp::Avenc::IFileIoChannel *v8; // rbx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r9d
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  struct Rdp::Avenc::IFileIoChannel *v21; // rbx
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // r9d
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rsi
  __int64 result; // rax
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-48h]
  char *v31; // [rsp+28h] [rbp-40h]
  char *v32; // [rsp+28h] [rbp-40h]
  char *v33; // [rsp+28h] [rbp-40h]
  char *v34; // [rsp+28h] [rbp-40h]
  char *v35; // [rsp+28h] [rbp-40h]
  Rdp::Utils::Props *v36; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v37[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v6 = (unsigned int)a4;
    v36 = 0;
    if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_AvencFileIoChannelGraphics )
    {
      v8 = a5;
      v9 = *(_QWORD *)a5;
      v36 = 0;
      v10 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *, Rdp::Utils::Props **))(v9 + 24))(a5, &v36);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        (const char *)v10,
        (int)"Failed to open property store",
        v31);
      v12 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v36,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)0x1000,
              v11);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        (const char *)v12,
        (int)"Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length",
        v32);
      v13 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v8 + 32LL))(v8);
      if ( v6 < 2 )
      {
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
          (const char *)v13,
          (int)"Failed to start FileIo graphics read channel",
          v33);
        v37[0] = 0;
        v15 = (**(__int64 (__fastcall ***)(struct Rdp::Avenc::IFileIoChannel *, GUID *, _QWORD *))v8)(
                v8,
                &GUID_ce09a263_f536_42c9_9acc_85b5652a904f,
                v37);
        if ( v15 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v15,
            v30);
        v16 = v37[0];
        v17 = 0;
        v37[0] = 0;
        v18 = *((_QWORD *)this + 25);
        *((_QWORD *)this + 25) = v16;
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v17 = v37[0];
        }
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v19 = std::make_unique<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel * &,0>(
                v37,
                &a5);
        std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,0>(
          (char *)this + 176,
          v19);
        std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>(v37);
      }
      else
      {
        if ( v6 != 2 )
        {
          v29 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
          LODWORD(v33) = v6;
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x18A,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
            v29,
            (int)"Unknown graphics channel instance id: %d",
            v33);
        }
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
          (const char *)v13,
          (int)"Failed to start FileIo graphics write channel",
          v33);
        v14 = *((_QWORD *)this + 24);
        *((_QWORD *)this + 24) = v8;
        if ( v8 )
          (*(void (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v8 + 8LL))(v8);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      if ( this == (Rdp::Avenc::SinkWriter::CSinkWriterProcessor *)88 )
      {
        *a6 = 0;
      }
      else
      {
        v20 = (**((__int64 (__fastcall ***)(char *, GUID *, struct Rdp::Avenc::IFileIoChannelEvents **))this - 11))(
                (char *)this - 88,
                &GUID_0a6e23a0_618a_40d9_ad98_e1b064f18ccb,
                a6);
        if ( v20 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x61F,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/com.h",
            (const char *)(unsigned int)v20,
            v30);
      }
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_AvencFileIoChannelCursor.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_AvencFileIoChannelCursor.Data4 )
      {
        return 2147500037LL;
      }
      v21 = a5;
      v22 = *(_QWORD *)a5;
      v36 = 0;
      v23 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *, Rdp::Utils::Props **))(v22 + 24))(a5, &v36);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        (const char *)v23,
        (int)"Failed to open property store",
        v31);
      v25 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v36,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)0x1000,
              v24);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        (const char *)v25,
        (int)"Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length",
        v34);
      v26 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v21 + 32LL))(v21);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        (const char *)v26,
        (int)"Failed to start FileIo cursor channel",
        v35);
      v27 = *((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = v21;
      if ( v21 )
        (*(void (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    if ( v36 )
      (*(void (__fastcall **)(Rdp::Utils::Props *))(*(_QWORD *)v36 + 16LL))(v36);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1AD,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180033690  mov     r11, rsp
0x180033693  push    rbx
0x180033694  push    rsi
0x180033695  push    rdi
0x180033696  push    r14
0x180033698  sub     rsp, 48h
0x18003369c  mov     r14d, r9d
0x18003369f  mov     rdi, rcx
0x1800336a2  mov     qword ptr [r11-38h], 0
0x1800336aa  mov     rax, [rdx]
0x1800336ad  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data1
0x1800336b4  jnz     loc_1800338D7
0x1800336ba  mov     rax, [rdx+8]
0x1800336be  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data4
0x1800336c5  jnz     loc_1800338D7
0x1800336cb  mov     rbx, [r11+28h]
0x1800336cf  mov     rax, [rbx]
0x1800336d2  mov     qword ptr [r11-38h], 0
0x1800336da  lea     rdx, [r11-38h]
0x1800336de  mov     rcx, rbx
0x1800336e1  mov     rax, [rax+18h]
0x1800336e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336ea  mov     rcx, [rsp+68h]; this
0x1800336ef  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x1800336f6  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800336fb  mov     r9d, eax; char *
0x1800336fe  lea     rsi, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180033705  mov     r8, rsi; unsigned int
0x180033708  mov     edx, 160h; void *
0x18003370d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033712  mov     r8d, 1000h; struct _tagpropertykey *
0x180033718  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x18003371f  mov     rcx, [rsp+68h+var_38]; this
0x180033724  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180033729  mov     rcx, [rsp+68h]; this
0x18003372e  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x180033735  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003373a  mov     r9d, eax; char *
0x18003373d  mov     r8, rsi; unsigned int
0x180033740  mov     edx, 16Ah; void *
0x180033745  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003374a  mov     rax, [rbx]
0x18003374d  mov     rcx, rbx
0x180033750  mov     rax, [rax+20h]
0x180033754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033759  mov     ecx, r14d
0x18003375c  test    r14d, r14d
0x18003375f  jz      short loc_1800337CD
0x180033761  sub     ecx, 1
0x180033764  jz      short loc_1800337CD
0x180033766  cmp     ecx, 1
0x180033769  jnz     loc_180033A15
0x18003376f  mov     rcx, [rsp+68h]; this
0x180033774  lea     rdx, aFailedToStartF; "Failed to start FileIo graphics write c"...
0x18003377b  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180033780  mov     r9d, eax; char *
0x180033783  mov     r8, rsi; unsigned int
0x180033786  mov     edx, 183h; void *
0x18003378b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033790  nop
0x180033791  mov     rsi, [rdi+0C0h]
0x180033798  mov     [rdi+0C0h], rbx
0x18003379f  test    rbx, rbx
0x1800337a2  jz      short loc_1800337B3
0x1800337a4  mov     rax, [rbx]
0x1800337a7  mov     rcx, rbx
0x1800337aa  mov     rax, [rax+8]
0x1800337ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337b3  test    rsi, rsi
0x1800337b6  jz      short loc_1800337C8
0x1800337b8  mov     rax, [rsi]
0x1800337bb  mov     rcx, rsi
0x1800337be  mov     rax, [rax+10h]
0x1800337c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337c7  nop
0x1800337c8  jmp     loc_18003388E
0x1800337cd  mov     rcx, [rsp+68h]; this
0x1800337d2  lea     rdx, aFailedToStartF_1; "Failed to start FileIo graphics read ch"...
0x1800337d9  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800337de  mov     r9d, eax; char *
0x1800337e1  mov     r8, rsi; unsigned int
0x1800337e4  mov     edx, 177h; void *
0x1800337e9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800337ee  mov     [rsp+68h+var_30], 0
0x1800337f7  mov     rax, [rbx]
0x1800337fa  lea     r8, [rsp+68h+var_30]
0x1800337ff  lea     rdx, _GUID_ce09a263_f536_42c9_9acc_85b5652a904f
0x180033806  mov     rcx, rbx
0x180033809  mov     rax, [rax]
0x18003380c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033811  mov     rcx, [rsp+68h]; this
0x180033816  test    eax, eax
0x180033818  js      loc_180033A45
0x18003381e  mov     rax, [rsp+68h+var_30]
0x180033823  xor     ecx, ecx
0x180033825  mov     [rsp+68h+var_30], rcx
0x18003382a  mov     rdx, [rdi+0C8h]
0x180033831  mov     [rdi+0C8h], rax
0x180033838  test    rdx, rdx
0x18003383b  jz      short loc_180033851
0x18003383d  mov     rax, [rdx]
0x180033840  mov     rcx, rdx
0x180033843  mov     rax, [rax+10h]
0x180033847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003384c  mov     rcx, [rsp+68h+var_30]
0x180033851  test    rcx, rcx
0x180033854  jz      short loc_180033863
0x180033856  mov     rax, [rcx]
0x180033859  mov     rax, [rax+10h]
0x18003385d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033862  nop
0x180033863  lea     rdx, [rsp+68h+arg_20]
0x18003386b  lea     rcx, [rsp+68h+var_30]
0x180033870  call    ??$make_unique@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@AEAPEAUIFileIoChannel@Avenc@3@$0A@@std@@YA?AV?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@0@AEAPEAUIFileIoChannel@Avenc@Rdp@@@Z; std::make_unique<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel * &,0>(Rdp::Avenc::IFileIoChannel * &)
0x180033875  lea     rcx, [rdi+0B0h]
0x18003387c  mov     rdx, rax
0x18003387f  call    ??$?4U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@$0A@@?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,0>(std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>> &&)
0x180033884  lea     rcx, [rsp+68h+var_30]
0x180033889  call    ??1?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>(void)
0x18003388e  lea     rcx, [rdi-58h]
0x180033892  test    rcx, rcx
0x180033895  jz      short loc_1800338C3
0x180033897  mov     rax, [rcx]
0x18003389a  mov     r8, [rsp+68h+arg_28]
0x1800338a2  lea     rdx, _GUID_0a6e23a0_618a_40d9_ad98_e1b064f18ccb
0x1800338a9  mov     rax, [rax]
0x1800338ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338b1  mov     rcx, [rsp+68h]; this
0x1800338b6  test    eax, eax
0x1800338b8  js      loc_180033A59
0x1800338be  jmp     loc_1800339E5
0x1800338c3  mov     rax, [rsp+68h+arg_28]
0x1800338cb  mov     qword ptr [rax], 0
0x1800338d2  jmp     loc_1800339E5
0x1800338d7  mov     rax, [rdx]
0x1800338da  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data1
0x1800338e1  jnz     loc_180033A00
0x1800338e7  mov     rax, [rdx+8]
0x1800338eb  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data4
0x1800338f2  jnz     loc_180033A00
0x1800338f8  mov     rbx, [rsp+68h+arg_20]
0x180033900  mov     rax, [rbx]
0x180033903  mov     [rsp+68h+var_38], 0
0x18003390c  lea     rdx, [rsp+68h+var_38]
0x180033911  mov     rcx, rbx
0x180033914  mov     rax, [rax+18h]
0x180033918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003391d  mov     rcx, [rsp+68h]; this
0x180033922  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x180033929  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003392e  mov     r9d, eax; char *
0x180033931  lea     rsi, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180033938  mov     r8, rsi; unsigned int
0x18003393b  mov     edx, 193h; void *
0x180033940  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033945  mov     r8d, 1000h; struct _tagpropertykey *
0x18003394b  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180033952  mov     rcx, [rsp+68h+var_38]; this
0x180033957  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18003395c  mov     rcx, [rsp+68h]; this
0x180033961  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x180033968  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003396d  mov     r9d, eax; char *
0x180033970  mov     r8, rsi; unsigned int
0x180033973  mov     edx, 19Dh; void *
0x180033978  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003397d  mov     rax, [rbx]
0x180033980  mov     rcx, rbx
0x180033983  mov     rax, [rax+20h]
0x180033987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003398c  mov     rcx, [rsp+68h]; this
0x180033991  lea     rdx, aFailedToStartF_2; "Failed to start FileIo cursor channel"
0x180033998  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003399d  mov     r9d, eax; char *
0x1800339a0  mov     r8, rsi; unsigned int
0x1800339a3  mov     edx, 1A3h; void *
0x1800339a8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800339ad  nop
0x1800339ae  mov     rsi, [rdi+0D0h]
0x1800339b5  mov     [rdi+0D0h], rbx
0x1800339bc  test    rbx, rbx
0x1800339bf  jz      short loc_1800339D0
0x1800339c1  mov     rax, [rbx]
0x1800339c4  mov     rcx, rbx
0x1800339c7  mov     rax, [rax+8]
0x1800339cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339d0  test    rsi, rsi
0x1800339d3  jz      short loc_1800339E5
0x1800339d5  mov     rax, [rsi]
0x1800339d8  mov     rcx, rsi
0x1800339db  mov     rax, [rax+10h]
0x1800339df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339e4  nop
0x1800339e5  mov     rcx, [rsp+68h+var_38]
0x1800339ea  test    rcx, rcx
0x1800339ed  jz      short loc_1800339FC
0x1800339ef  mov     rax, [rcx]
0x1800339f2  mov     rax, [rax+10h]
0x1800339f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339fb  nop
0x1800339fc  xor     eax, eax
0x1800339fe  jmp     short loc_180033A0B
0x180033a00  mov     eax, 80004005h
0x180033a05  jmp     short loc_180033A0B
0x180033a07  mov     eax, dword ptr [rsp+68h+var_38]
0x180033a0b  add     rsp, 48h
0x180033a0f  pop     r14
0x180033a11  pop     rdi
0x180033a12  pop     rsi
0x180033a13  pop     rbx
0x180033a14  retn
0x180033a15  mov     ecx, 8000FFFFh
0x180033a1a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180033a1f  mov     r9d, eax; char *
0x180033a22  mov     rcx, [rsp+68h]; this
0x180033a27  mov     dword ptr [rsp+68h+var_40], r14d; char *
0x180033a2c  lea     rax, aUnknownGraphic; "Unknown graphics channel instance id: %"...
0x180033a33  mov     qword ptr [rsp+68h+var_48], rax; int
0x180033a38  mov     r8, rsi; unsigned int
0x180033a3b  mov     edx, 18Ah; void *
0x180033a40  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033a45  mov     r9d, eax; char *
0x180033a48  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180033a4f  mov     edx, 1CBEh; void *
0x180033a54  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033a59  mov     r9d, eax; char *
0x180033a5c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180033a63  mov     edx, 61Fh; void *
0x180033a68  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
