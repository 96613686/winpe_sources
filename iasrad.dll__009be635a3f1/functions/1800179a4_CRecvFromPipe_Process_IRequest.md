# CRecvFromPipe::Process(IRequest *)

- ea: `0x1800179a4`
- end: `0x1800181e0`
- name: `?Process@CRecvFromPipe@@QEAAJPEAUIRequest@@@Z`
- size: `2108`
- prototype: `__int64 __fastcall(CRecvFromPipe *__hidden this, struct IRequest *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000d140`

## callees

- `0x1800094e4`
- `0x180012988`
- `0x1800168a8`
- `0x180016efc`
- `0x180017544`
- `0x1800179a4`
- `0x1800186b8`
- `0x18001b898`
- `0x18001c7f0`
- `0x18001d31c`
- `0x1800283c0`
- `0x18002860c`
- `0x180028a18`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `iassvcs!IASReportEvent` at `0x18001813c`
- `iassvcs!IASReportEvent` at `0x18002ee25`
- `iassvcs!IASReportEvent` at `0x18002ee79`
- `iassvcs!IASReportEvent` at `0x18001813c`
- `iassvcs!IASReportEvent` at `0x18002ee25`
- `iassvcs!IASReportEvent` at `0x18002ee79`
- `WS2_32!__imp_ntohs` at `0x1800180c6`
- `WS2_32!__imp_ntohs` at `0x18002ede1`
- `WS2_32!__imp_ntohs` at `0x1800180c6`
- `WS2_32!__imp_ntohs` at `0x18002ede1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001816b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001816b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017f1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017f1a`

## string_xrefs

- `0x180018045`: `Unable to remove attribute in request received from backend`

## pseudocode

```c
__int64 __fastcall CRecvFromPipe::Process(CPreProcessor **this, struct IRequest *a2)
{
  struct CPacketRadius *v4; // rsi
  unsigned int v5; // edi
  LPVOID *v6; // r14
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  CEventLogResult *v9; // rcx
  CEventLogResult *v10; // r15
  struct IAttributesRaw *v11; // r12
  CRecvFromPipe *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // r9
  __int64 v16; // rcx
  unsigned int i; // ebx
  unsigned int v19; // [rsp+60h] [rbp-78h] BYREF
  struct IAttributesRaw *v20; // [rsp+68h] [rbp-70h] BYREF
  unsigned int v21; // [rsp+70h] [rbp-68h]
  struct CPacketRadius *v22; // [rsp+78h] [rbp-60h] BYREF
  unsigned int v23; // [rsp+80h] [rbp-58h] BYREF
  int v24; // [rsp+84h] [rbp-54h] BYREF
  unsigned int v25; // [rsp+88h] [rbp-50h] BYREF
  int v26; // [rsp+8Ch] [rbp-4Ch]
  __int64 v27; // [rsp+90h] [rbp-48h] BYREF
  struct CPacketRadius *v28; // [rsp+98h] [rbp-40h] BYREF
  unsigned int *v29; // [rsp+A0h] [rbp-38h] BYREF
  LPVOID *v30; // [rsp+A8h] [rbp-30h]
  unsigned __int16 v31; // [rsp+F0h] [rbp+18h] BYREF
  int started; // [rsp+F8h] [rbp+20h] BYREF

  started = 0;
  v19 = 0;
  v20 = 0;
  v27 = 0;
  v4 = 0;
  v22 = 0;
  v25 = 0;
  v24 = 0;
  v5 = 0;
  v6 = 0;
  v30 = 0;
  v28 = 0;
  v21 = 0;
  started = ((__int64 (__fastcall *)(struct IRequest *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_6bc096ba_0ce6_11d1_baae_00c04fc2e20d,
              &v27);
  if ( started < 0 )
  {
    v7 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to obtain request state in request received from backend");
      v8 = 11;
LABEL_6:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
      goto LABEL_93;
    }
    goto LABEL_93;
  }
  started = ((__int64 (__fastcall *)(struct IRequest *, GUID *, struct IAttributesRaw **))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_6bc096a8_0ce6_11d1_baae_00c04fc2e20d,
              &v20);
  if ( started >= 0 )
  {
    started = (*(__int64 (__fastcall **)(__int64, struct CPacketRadius **))(*(_QWORD *)v27 + 32LL))(v27, &v28);
    if ( started < 0 )
    {
      v7 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to obtain information from request state received from backend");
        v8 = 13;
        goto LABEL_6;
      }
      goto LABEL_93;
    }
    v4 = v28;
    v22 = v28;
    if ( !v28 )
    {
      started = CRecvFromPipe::GeneratePacketRadius((CRecvFromPipe *)this, &v22, v20);
      v4 = v22;
      if ( started < 0 )
        goto LABEL_93;
    }
    started = ((__int64 (__fastcall *)(struct IRequest *, unsigned int *))a2->lpVtbl->GetIDsOfNames)(a2, &v25);
    if ( started < 0 )
    {
      v7 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to obtain response code in request recieved from backend");
        v8 = 14;
        goto LABEL_6;
      }
      goto LABEL_93;
    }
    v10 = this[9];
    v11 = v20;
    v31 = 0;
    v23 = 0;
    v29 = 0;
    if ( (int)CEventLogResult::AnalyzeAccessResponse(v9, a2, &v31, &v23, (const unsigned int **)&v29) >= 0 )
      CEventLogResult::LogResult(v10, a2, v11, v31, v23, v29);
    started = CRecvFromPipe::SplitAttributes(v12, v20);
    if ( started < 0 )
    {
      v7 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to split IAS attribute received from backend");
        v8 = 15;
        goto LABEL_6;
      }
      goto LABEL_93;
    }
    started = VSAFilter::radiusFromIAS(this[6], v20, 0);
    if ( started < 0 )
    {
      v7 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to convert IAS attribute to Radius VSAs in request received from backend");
        v8 = 16;
        goto LABEL_6;
      }
      goto LABEL_93;
    }
    started = ((__int64 (__fastcall *)(struct IRequest *, int *))a2->lpVtbl->Invoke)(a2, &v24);
    if ( started < 0 )
    {
      v7 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to obtain reason code in request recieved from backend");
        v8 = 17;
        goto LABEL_6;
      }
      goto LABEL_93;
    }
    if ( v24 )
    {
      if ( v24 == 3 )
      {
        v21 = 1;
      }
      else if ( v24 == 80 )
      {
        v21 = 6;
      }
    }
    v13 = 0;
    v26 = 0;
    v7 = v25;
    if ( v25 )
    {
      v7 = v25 - 1;
      if ( v25 == 1 )
      {
        v5 = 2;
        goto LABEL_61;
      }
      v7 = v25 - 2;
      if ( v25 == 2 )
      {
        v5 = 3;
        goto LABEL_61;
      }
      v7 = v25 - 3;
      if ( v25 == 3 )
      {
        v5 = 11;
        goto LABEL_61;
      }
      v7 = v25 - 4;
      if ( v25 == 4 )
      {
        v5 = 5;
        goto LABEL_61;
      }
      v7 = v25 - 5;
      if ( v25 == 5 )
      {
        v13 = 3221225495LL;
LABEL_60:
        v26 = v13;
        goto LABEL_61;
      }
      if ( v25 == 999 )
      {
        v5 = **((unsigned __int8 **)v4 + 3);
LABEL_61:
        started = v13;
        if ( (int)v13 >= 0 )
        {
          started = CTunnelPassword::Process(v7, v13, v20, v4);
          if ( started >= 0 )
          {
            started = CRecvFromPipe::InjectSignature(v7, v5, v20);
            if ( started >= 0 )
            {
              started = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *))(*(_QWORD *)v20 + 48LL))(
                          v20,
                          &v19);
              if ( started >= 0 )
              {
                if ( v19 <= 0xFFFFFFF )
                {
                  v6 = (LPVOID *)CoTaskMemAlloc(16LL * v19);
                  v30 = v6;
                  if ( v6 )
                  {
                    started = (*(__int64 (__fastcall **)(struct IAttributesRaw *, unsigned int *, LPVOID *, _QWORD, _QWORD))(*(_QWORD *)v20 + 56LL))(
                                v20,
                                &v19,
                                v6,
                                0,
                                0);
                    if ( started >= 0 )
                    {
                      started = (*(__int64 (__fastcall **)(struct IAttributesRaw *, _QWORD, LPVOID *))(*(_QWORD *)v20 + 32LL))(
                                  v20,
                                  v19,
                                  v6);
                      if ( started >= 0 )
                      {
                        started = CPacketRadius::BuildOutPacket(v4, v5, v6, v19);
                        if ( started >= 0 )
                          started = CPreProcessor::StartOutProcessing(this[2], v4);
                      }
                      else
                      {
                        v7 = (unsigned __int64)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                        {
                          WppDbgPrint("Unable to remove attribute in request received from backend");
                          v8 = 22;
                          goto LABEL_6;
                        }
                      }
                    }
                    else
                    {
                      v7 = (unsigned __int64)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                      {
                        WppDbgPrint("Unable to get attribute in request received from backend");
                        v8 = 21;
                        goto LABEL_6;
                      }
                    }
                  }
                  else
                  {
                    v7 = (unsigned __int64)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                    {
                      WppDbgPrint("Unable to allocate memory for attribute postion array while processing request recieved from backend");
                      WPP_SF_s(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        20,
                        WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids,
                        "NPSRAD");
                    }
                    started = -2147024882;
                  }
                }
                else
                {
                  v7 = (unsigned __int64)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                  {
                    WppDbgPrint("Large attribute count caused integer overflow");
                    WPP_SF_s(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      19,
                      WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids,
                      "NPSRAD");
                  }
                  started = -2147024362;
                }
              }
              else
              {
                v7 = (unsigned __int64)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
                {
                  WppDbgPrint("Unable to obtain attribute count in request received from backend");
                  v8 = 18;
                  goto LABEL_6;
                }
              }
            }
          }
        }
        goto LABEL_93;
      }
    }
    v13 = 2147500037LL;
    goto LABEL_60;
  }
  v7 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to obtain Attributes interface in request received from backend");
    v8 = 12;
    goto LABEL_6;
  }
LABEL_93:
  if ( started < 0 )
  {
    if ( started == -1073741801 && v4 )
      CReportEvent::Process(
        v7,
        v21,
        **((unsigned __int8 **)v4 + 3),
        *((unsigned __int16 *)v4 + 16),
        *((_QWORD *)v4 + 10));
    else
      IASReportEvent(3221225484LL, 0, 4, 0, &started);
  }
  else
  {
    CReportEvent::Process(v7, 3, **((unsigned __int8 **)v4 + 3), *((unsigned __int16 *)v4 + 16), *((_QWORD *)v4 + 10));
    v14 = *((_QWORD *)v4 + 10);
    v15 = ntohs(*(_WORD *)(*((_QWORD *)v4 + 5) + 2LL));
    CReportEvent::Process(v16, 3, **((unsigned __int8 **)v4 + 5), v15, v14);
  }
  if ( v6 )
  {
    for ( i = 0; i < v19; ++i )
      IASAttributeRelease(v6[2 * i + 1]);
    CoTaskMemFree(v6);
  }
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v20 )
    (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v4 )
    (**(void (__fastcall ***)(struct CPacketRadius *, __int64))v4)(v4, 1);
  _InterlockedDecrement(&g_lPacketCount);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800179a4  mov     r11, rsp
0x1800179a7  mov     [r11+8], rbx
0x1800179ab  mov     [r11+10h], rsi
0x1800179af  push    rdi
0x1800179b0  push    r12
0x1800179b2  push    r13
0x1800179b4  push    r14
0x1800179b6  push    r15
0x1800179b8  sub     rsp, 90h
0x1800179bf  mov     rbx, rdx
0x1800179c2  mov     r13, rcx
0x1800179c5  xor     r15d, r15d
0x1800179c8  mov     [r11+20h], r15d
0x1800179cc  mov     [r11-78h], r15d
0x1800179d0  mov     [r11-70h], r15
0x1800179d4  mov     [r11-48h], r15
0x1800179d8  mov     esi, r15d
0x1800179db  mov     [r11-60h], r15
0x1800179df  mov     [r11-50h], r15d
0x1800179e3  mov     [r11-54h], r15d
0x1800179e7  mov     edi, r15d
0x1800179ea  mov     r14d, r15d
0x1800179ed  mov     [r11-30h], r15
0x1800179f1  mov     [r11-40h], r15
0x1800179f5  mov     [r11-68h], r15d
0x1800179f9  mov     rax, [rdx]
0x1800179fc  lea     r8, [r11-48h]
0x180017a00  lea     rdx, _GUID_6bc096ba_0ce6_11d1_baae_00c04fc2e20d
0x180017a07  mov     rcx, rbx
0x180017a0a  mov     rax, [rax]
0x180017a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a12  mov     [rsp+0B8h+arg_18], eax
0x180017a19  test    eax, eax
0x180017a1b  jns     short loc_180017A7E
0x180017a1d  lea     rax, WPP_GLOBAL_Control
0x180017a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a2b  cmp     rcx, rax
0x180017a2e  jz      loc_18001808B
0x180017a34  cmp     byte ptr [rcx+19h], 2
0x180017a38  jb      loc_18001808B
0x180017a3e  test    dword ptr [rcx+1Ch], 100h
0x180017a45  jz      loc_18001808B
0x180017a4b  lea     rcx, aUnableToObtain_1; "Unable to obtain request state in reque"...
0x180017a52  call    WppDbgPrint
0x180017a57  lea     edx, [r15+0Bh]
0x180017a5b  lea     r9, aNpsrad; "NPSRAD"
0x180017a62  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180017a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a70  mov     rcx, [rcx+10h]
0x180017a74  call    WPP_SF_s
0x180017a79  jmp     loc_18001808B
0x180017a7e  mov     rax, [rbx]
0x180017a81  lea     r8, [rsp+0B8h+var_70]
0x180017a86  lea     rdx, _GUID_6bc096a8_0ce6_11d1_baae_00c04fc2e20d
0x180017a8d  mov     rcx, rbx
0x180017a90  mov     rax, [rax]
0x180017a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a98  mov     [rsp+0B8h+arg_18], eax
0x180017a9f  test    eax, eax
0x180017aa1  jns     short loc_180017AE7
0x180017aa3  lea     rax, WPP_GLOBAL_Control
0x180017aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ab1  cmp     rcx, rax
0x180017ab4  jz      loc_18001808B
0x180017aba  cmp     byte ptr [rcx+19h], 2
0x180017abe  jb      loc_18001808B
0x180017ac4  test    dword ptr [rcx+1Ch], 100h
0x180017acb  jz      loc_18001808B
0x180017ad1  lea     rcx, aUnableToObtain_13; "Unable to obtain Attributes interface i"...
0x180017ad8  call    WppDbgPrint
0x180017add  mov     edx, 0Ch
0x180017ae2  jmp     loc_180017A5B
0x180017ae7  mov     rcx, [rsp+0B8h+var_48]
0x180017aec  mov     rax, [rcx]
0x180017aef  lea     rdx, [rsp+0B8h+var_40]
0x180017af4  mov     rax, [rax+20h]
0x180017af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017afd  mov     [rsp+0B8h+arg_18], eax
0x180017b04  test    eax, eax
0x180017b06  jns     short loc_180017B4C
0x180017b08  lea     rax, WPP_GLOBAL_Control
0x180017b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b16  cmp     rcx, rax
0x180017b19  jz      loc_18001808B
0x180017b1f  cmp     byte ptr [rcx+19h], 2
0x180017b23  jb      loc_18001808B
0x180017b29  test    dword ptr [rcx+1Ch], 100h
0x180017b30  jz      loc_18001808B
0x180017b36  lea     rcx, aUnableToObtain_14; "Unable to obtain information from reque"...
0x180017b3d  call    WppDbgPrint
0x180017b42  mov     edx, 0Dh
0x180017b47  jmp     loc_180017A5B
0x180017b4c  mov     rsi, [rsp+0B8h+var_40]
0x180017b51  mov     [rsp+0B8h+var_60], rsi
0x180017b56  test    rsi, rsi
0x180017b59  jnz     short loc_180017B81
0x180017b5b  mov     r8, [rsp+0B8h+var_70]; struct IAttributesRaw *
0x180017b60  lea     rdx, [rsp+0B8h+var_60]; struct CPacketRadius **
0x180017b65  mov     rcx, r13; this
0x180017b68  call    ?GeneratePacketRadius@CRecvFromPipe@@AEAAJPEAPEAVCPacketRadius@@PEAUIAttributesRaw@@@Z; CRecvFromPipe::GeneratePacketRadius(CPacketRadius * *,IAttributesRaw *)
0x180017b6d  mov     [rsp+0B8h+arg_18], eax
0x180017b74  mov     rsi, [rsp+0B8h+var_60]
0x180017b79  test    eax, eax
0x180017b7b  js      loc_18001808B
0x180017b81  mov     rax, [rbx]
0x180017b84  lea     rdx, [rsp+0B8h+var_50]
0x180017b89  mov     rcx, rbx
0x180017b8c  mov     rax, [rax+28h]
0x180017b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b95  mov     [rsp+0B8h+arg_18], eax
0x180017b9c  test    eax, eax
0x180017b9e  jns     short loc_180017BE4
0x180017ba0  lea     rax, WPP_GLOBAL_Control
0x180017ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bae  cmp     rcx, rax
0x180017bb1  jz      loc_18001808B
0x180017bb7  cmp     byte ptr [rcx+19h], 2
0x180017bbb  jb      loc_18001808B
0x180017bc1  test    dword ptr [rcx+1Ch], 100h
0x180017bc8  jz      loc_18001808B
0x180017bce  lea     rcx, aUnableToObtain_15; "Unable to obtain response code in reque"...
0x180017bd5  call    WppDbgPrint
0x180017bda  mov     edx, 0Eh
0x180017bdf  jmp     loc_180017A5B
0x180017be4  mov     r15, [r13+48h]
0x180017be8  mov     r12, [rsp+0B8h+var_70]
0x180017bed  xor     eax, eax
0x180017bef  mov     [rsp+0B8h+arg_10], ax
0x180017bf7  mov     [rsp+0B8h+var_58], eax
0x180017bfb  mov     [rsp+0B8h+var_38], rax
0x180017c03  lea     rax, [rsp+0B8h+var_38]
0x180017c0b  mov     [rsp+0B8h+var_98], rax; unsigned int **
0x180017c10  lea     r9, [rsp+0B8h+var_58]; unsigned int *
0x180017c15  lea     r8, [rsp+0B8h+arg_10]; unsigned __int16 *
0x180017c1d  mov     rdx, rbx; struct IRequest *
0x180017c20  call    ?AnalyzeAccessResponse@CEventLogResult@@AEAAJPEAUIRequest@@AEAGAEAKAEAPEBK@Z; CEventLogResult::AnalyzeAccessResponse(IRequest *,ushort &,ulong &,ulong const * &)
0x180017c25  test    eax, eax
0x180017c27  js      short loc_180017C55
0x180017c29  mov     rax, [rsp+0B8h+var_38]
0x180017c31  mov     [rsp+0B8h+var_90], rax; unsigned int *
0x180017c36  mov     eax, [rsp+0B8h+var_58]
0x180017c3a  mov     dword ptr [rsp+0B8h+var_98], eax; unsigned int
0x180017c3e  movzx   r9d, [rsp+0B8h+arg_10]; unsigned __int16
0x180017c47  mov     r8, r12; struct IAttributesRaw *
0x180017c4a  mov     rdx, rbx; struct IRequest *
0x180017c4d  mov     rcx, r15; this
0x180017c50  call    ?LogResult@CEventLogResult@@AEAAJPEAUIRequest@@PEAUIAttributesRaw@@GKPEBK@Z; CEventLogResult::LogResult(IRequest *,IAttributesRaw *,ushort,ulong,ulong const *)
0x180017c55  mov     rdx, [rsp+0B8h+var_70]; struct IAttributesRaw *
0x180017c5a  call    ?SplitAttributes@CRecvFromPipe@@AEAAJPEAUIAttributesRaw@@@Z; CRecvFromPipe::SplitAttributes(IAttributesRaw *)
0x180017c5f  mov     [rsp+0B8h+arg_18], eax
0x180017c66  xor     r15d, r15d
0x180017c69  test    eax, eax
0x180017c6b  jns     short loc_180017CB0
0x180017c6d  lea     rax, WPP_GLOBAL_Control
0x180017c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c7b  cmp     rcx, rax
0x180017c7e  jz      loc_18001808B
0x180017c84  cmp     byte ptr [rcx+19h], 2
0x180017c88  jb      loc_18001808B
0x180017c8e  test    dword ptr [rcx+1Ch], 100h
0x180017c95  jz      loc_18001808B
0x180017c9b  lea     rcx, aUnableToSplitI; "Unable to split IAS attribute received "...
0x180017ca2  call    WppDbgPrint
0x180017ca7  lea     edx, [r15+0Fh]
0x180017cab  jmp     loc_180017A5B
0x180017cb0  xor     r8d, r8d; int
0x180017cb3  mov     rdx, [rsp+0B8h+var_70]; struct IAttributesRaw *
0x180017cb8  mov     rcx, [r13+30h]; this
0x180017cbc  call    ?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z; VSAFilter::radiusFromIAS(IAttributesRaw *,int)
0x180017cc1  mov     [rsp+0B8h+arg_18], eax
0x180017cc8  test    eax, eax
0x180017cca  jns     short loc_180017D10
0x180017ccc  lea     rax, WPP_GLOBAL_Control
0x180017cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cda  cmp     rcx, rax
0x180017cdd  jz      loc_18001808B
0x180017ce3  cmp     byte ptr [rcx+19h], 2
0x180017ce7  jb      loc_18001808B
0x180017ced  test    dword ptr [rcx+1Ch], 100h
0x180017cf4  jz      loc_18001808B
0x180017cfa  lea     rcx, aUnableToConver; "Unable to convert IAS attribute to Radi"...
0x180017d01  call    WppDbgPrint
0x180017d06  mov     edx, 10h
0x180017d0b  jmp     loc_180017A5B
0x180017d10  mov     rax, [rbx]
0x180017d13  lea     rdx, [rsp+0B8h+var_54]
0x180017d18  mov     rcx, rbx
0x180017d1b  mov     rax, [rax+30h]
0x180017d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d24  mov     [rsp+0B8h+arg_18], eax
0x180017d2b  test    eax, eax
0x180017d2d  jns     short loc_180017D73
0x180017d2f  lea     rax, WPP_GLOBAL_Control
0x180017d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d3d  cmp     rcx, rax
0x180017d40  jz      loc_18001808B
0x180017d46  cmp     byte ptr [rcx+19h], 2
0x180017d4a  jb      loc_18001808B
0x180017d50  test    dword ptr [rcx+1Ch], 100h
0x180017d57  jz      loc_18001808B
0x180017d5d  lea     rcx, aUnableToObtain_4; "Unable to obtain reason code in request"...
0x180017d64  call    WppDbgPrint
0x180017d69  mov     edx, 11h
0x180017d6e  jmp     loc_180017A5B
0x180017d73  mov     eax, [rsp+0B8h+var_54]
0x180017d77  test    eax, eax
0x180017d79  jz      short loc_180017D97
0x180017d7b  cmp     eax, 3
0x180017d7e  jz      short loc_180017D8F
0x180017d80  cmp     eax, 50h ; 'P'
0x180017d83  jnz     short loc_180017D97
0x180017d85  mov     [rsp+0B8h+var_68], 6
0x180017d8d  jmp     short loc_180017D97
0x180017d8f  mov     [rsp+0B8h+var_68], 1
0x180017d97  mov     edx, r15d
0x180017d9a  mov     [rsp+0B8h+var_4C], edx
0x180017d9e  mov     ecx, [rsp+0B8h+var_50]
0x180017da2  test    ecx, ecx
0x180017da4  jz      short loc_180017DF3
0x180017da6  sub     ecx, 1
0x180017da9  jz      short loc_180017DEC
0x180017dab  sub     ecx, 1
0x180017dae  jz      short loc_180017DE5
0x180017db0  sub     ecx, 1
0x180017db3  jz      short loc_180017DDE
0x180017db5  sub     ecx, 1
0x180017db8  jz      short loc_180017DD7
0x180017dba  sub     ecx, 1
0x180017dbd  jz      short loc_180017DD0
0x180017dbf  cmp     ecx, 3E2h
0x180017dc5  jnz     short loc_180017DF3
0x180017dc7  mov     rax, [rsi+18h]
0x180017dcb  movzx   edi, byte ptr [rax]
0x180017dce  jmp     short loc_180017DFC
0x180017dd0  mov     edx, 0C0000017h
0x180017dd5  jmp     short loc_180017DF8
0x180017dd7  mov     edi, 5
0x180017ddc  jmp     short loc_180017DFC
0x180017dde  mov     edi, 0Bh
0x180017de3  jmp     short loc_180017DFC
0x180017de5  mov     edi, 3
0x180017dea  jmp     short loc_180017DFC
0x180017dec  mov     edi, 2
0x180017df1  jmp     short loc_180017DFC
0x180017df3  mov     edx, 80004005h
0x180017df8  mov     [rsp+0B8h+var_4C], edx
0x180017dfc  mov     [rsp+0B8h+arg_18], edx
0x180017e03  test    edx, edx
0x180017e05  js      loc_18001808B
0x180017e0b  mov     r9, rsi
0x180017e0e  mov     r8, [rsp+0B8h+var_70]
0x180017e13  call    ?Process@CTunnelPassword@@QEAAJW4_packettype_@@PEAUIAttributesRaw@@PEAVCPacketRadius@@@Z; CTunnelPassword::Process(_packettype_,IAttributesRaw *,CPacketRadius *)
0x180017e18  mov     [rsp+0B8h+arg_18], eax
0x180017e1f  test    eax, eax
0x180017e21  js      loc_18001808B
0x180017e27  mov     r8, [rsp+0B8h+var_70]
0x180017e2c  mov     edx, edi
0x180017e2e  call    ?InjectSignature@CRecvFromPipe@@AEAAJW4_packettype_@@PEAUIAttributesRaw@@@Z; CRecvFromPipe::InjectSignature(_packettype_,IAttributesRaw *)
0x180017e33  mov     [rsp+0B8h+arg_18], eax
0x180017e3a  test    eax, eax
0x180017e3c  js      loc_18001808B
0x180017e42  mov     rcx, [rsp+0B8h+var_70]
0x180017e47  mov     rax, [rcx]
0x180017e4a  lea     rdx, [rsp+0B8h+var_78]
0x180017e4f  mov     rax, [rax+30h]
0x180017e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e58  mov     [rsp+0B8h+arg_18], eax
0x180017e5f  test    eax, eax
0x180017e61  jns     short loc_180017EA7
0x180017e63  lea     rax, WPP_GLOBAL_Control
0x180017e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e71  cmp     rcx, rax
0x180017e74  jz      loc_18001808B
0x180017e7a  cmp     byte ptr [rcx+19h], 2
0x180017e7e  jb      loc_18001808B
0x180017e84  test    dword ptr [rcx+1Ch], 100h
0x180017e8b  jz      loc_18001808B
0x180017e91  lea     rcx, aUnableToObtain; "Unable to obtain attribute count in req"...
0x180017e98  call    WppDbgPrint
0x180017e9d  mov     edx, 12h
0x180017ea2  jmp     loc_180017A5B
0x180017ea7  cmp     [rsp+0B8h+var_78], 0FFFFFFFh
0x180017eaf  jbe     short loc_180017F12
0x180017eb1  lea     rax, WPP_GLOBAL_Control
0x180017eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ebf  cmp     rcx, rax
0x180017ec2  jz      short loc_180017F02
0x180017ec4  cmp     byte ptr [rcx+19h], 2
0x180017ec8  jb      short loc_180017F02
0x180017eca  test    dword ptr [rcx+1Ch], 100h
0x180017ed1  jz      short loc_180017F02
0x180017ed3  lea     rcx, aLargeAttribute; "Large attribute count caused integer ov"...
0x180017eda  call    WppDbgPrint
0x180017edf  mov     edx, 13h
0x180017ee4  lea     r9, aNpsrad; "NPSRAD"
0x180017eeb  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180017ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ef9  mov     rcx, [rcx+10h]
0x180017efd  call    WPP_SF_s
0x180017f02  mov     [rsp+0B8h+arg_18], 80070216h
  ... truncated ...
```
