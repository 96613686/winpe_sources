# CThreadMgrEventSink_DIMCallBack::DIMCallback(uint,ITfDocumentMgr *,ITfDocumentMgr *,void *)

- ea: `0x18001de50`
- end: `0x18001e2b8`
- name: `?DIMCallback@CThreadMgrEventSink_DIMCallBack@@CAJIPEAUITfDocumentMgr@@0PEAX@Z`
- size: `1128`
- prototype: `static int(unsigned int, struct ITfDocumentMgr *, struct ITfDocumentMgr *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001cc80`
- `0x18001de50`
- `0x18001e560`
- `0x18001f16c`
- `0x18005990c`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001de94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001de94`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001df34`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001df34`
- `USER32!GetFocus` at `0x18001df1b`
- `USER32!GetFocus` at `0x18001df1b`
- `OLEAUT32!__imp_VariantClear` at `0x18001e1f5`
- `OLEAUT32!__imp_VariantClear` at `0x18001e1f5`
- `IMM32!ImmGetAppCompatFlags` at `0x18001df06`
- `IMM32!ImmGetAppCompatFlags` at `0x18001df06`

## string_xrefs

- `0x18001de68`: `CThreadMgrEventSink_DIMCallBack`
- `0x18001e10c`: `CThreadMgrEventSink_DIMCallBack::DIMCallback. TLS==NULL`
- `0x18001e1a9`: `CThreadMgrEventSink_DIMCallBack::DIMCallback. IID_ITfConfigureSystemKeystrokeFeed==NULL`
- `0x18001e22c`: `CThreadMgrEventSink_DIMCallBack::DIMCallback. ptim_P==NULL`
- `0x18001e216`: `CThreadMgrEventSink_DIMCallBack::CTFDetection. EnableSystemKeystrokeFeed==NULL`
- `0x18001e200`: `CThreadMgrEventSink_DIMCallBack::CTFDetection. DisableSystemKeystrokeFeed==NULL`
- `0x18001e242`: `CThreadMgrEventSink_DIMCallBack::DIMCallback. cicBridge == NULL`

## pseudocode

```c
__int64 __fastcall CThreadMgrEventSink_DIMCallBack::DIMCallback(
        int a1,
        struct ITfDocumentMgr *a2,
        struct ITfDocumentMgr *a3,
        void *a4)
{
  _QWORD *Value; // rax
  _QWORD *v8; // rdi
  __int64 v9; // r14
  int v10; // r15d
  HWND Focus; // r12
  CicBridge *v12; // r14
  struct ITfDocumentMgrVtbl *lpVtbl; // rax
  __int64 v14; // rcx
  int v15; // eax
  LONGLONG llVal; // rcx
  __int64 v17; // rax
  int v18; // edi
  HWND v20; // rax
  __int64 v21; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+28h] [rbp-28h] BYREF
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF

  CicTrace(8u, "CThreadMgrEventSink_DIMCallBack", a3, a4);
  if ( a1 != 2 )
    return 0;
  if ( TLS::dwTLSIndex == -1 || (Value = TlsGetValue(TLS::dwTLSIndex), (v8 = Value) == 0) )
  {
    CicTrace(2u, "CThreadMgrEventSink_DIMCallBack::DIMCallback. TLS==NULL");
    return 2147500037LL;
  }
  else
  {
    v9 = Value[2];
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      v21 = 0;
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v9)(v9, &GUID_0d2c969a_bc9c_437c_84ee_951c49b1a764, &v21);
      if ( v21 )
      {
        if ( !a2 || (unsigned int)CicBridge::IsOwnDim(a2) )
        {
          *((_DWORD *)v8 + 6) &= ~1u;
          v10 = 0;
        }
        else
        {
          v10 = 1;
          *((_DWORD *)v8 + 6) |= 1u;
        }
        if ( (ImmGetAppCompatFlags(0) & 0xD000000) != 0 )
        {
          Focus = GetFocus();
          if ( Focus && FindAtomW(L"_AIMM12_PROCESS_ATOM_") && (unsigned int)MsimtfIsWindowFiltered(Focus) )
          {
            v10 = 1;
            *((_DWORD *)v8 + 7) |= 1u;
          }
          else
          {
            *((_DWORD *)v8 + 7) &= ~1u;
          }
        }
        if ( (v8[4] & 1) != 0 )
        {
          if ( !v10 )
          {
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21) )
              CicTrace(2u, "CThreadMgrEventSink_DIMCallBack::CTFDetection. DisableSystemKeystrokeFeed==NULL");
            *((_DWORD *)v8 + 8) &= ~1u;
          }
        }
        else if ( v10 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21) )
            CicTrace(2u, "CThreadMgrEventSink_DIMCallBack::CTFDetection. EnableSystemKeystrokeFeed==NULL");
          *((_DWORD *)v8 + 8) |= 1u;
        }
      }
      else
      {
        CicTrace(2u, "CThreadMgrEventSink_DIMCallBack::DIMCallback. IID_ITfConfigureSystemKeystrokeFeed==NULL");
      }
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      CicTrace(2u, "CThreadMgrEventSink_DIMCallBack::DIMCallback. ptim_P==NULL");
    }
    if ( a2 && (unsigned int)CicBridge::IsOwnDim(a2) || !a3 || !(unsigned int)CicBridge::IsOwnDim(a3) )
      return 0;
    v12 = (CicBridge *)*v8;
    if ( *v8 )
    {
      lpVtbl = a3->lpVtbl;
      v21 = 0;
      v23 = 0;
      ((void (__fastcall *)(struct ITfDocumentMgr *, GUID *, __int64 *))lpVtbl->QueryInterface)(
        a3,
        &GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c,
        &v23);
      v14 = 0;
      v22 = 0;
      if ( v23 )
      {
        if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v23 + 24LL))(
               v23,
               &GUID_COMPARTMENT_TRANSITORYEXTENSION_PARENT,
               &v22) < 0 )
        {
LABEL_31:
          v14 = v22;
          goto LABEL_32;
        }
        v14 = v22;
        if ( v22 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          v15 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v22 + 32LL))(v22, &pvarg);
          llVal = pvarg.llVal;
          if ( v15 >= 0 && pvarg.vt == 13 && pvarg.llVal )
          {
            (**(void (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
              pvarg.llVal,
              &GUID_4c074926_9ddd_4d5e_bdc9_1be08660be14,
              &v21);
            llVal = pvarg.llVal;
          }
          if ( pvarg.vt != 11 )
          {
            if ( pvarg.vt == 13 )
            {
              if ( llVal )
                (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 16LL))(llVal);
            }
            else
            {
              switch ( pvarg.vt )
              {
                case 0u:
                case 1u:
                case 2u:
                case 3u:
                case 4u:
                case 5u:
                case 6u:
                case 7u:
                case 0x10u:
                case 0x11u:
                case 0x12u:
                case 0x13u:
                case 0x14u:
                case 0x15u:
                case 0x16u:
                case 0x17u:
                  goto LABEL_31;
                default:
                  VariantClear(&pvarg);
                  break;
              }
            }
          }
          goto LABEL_31;
        }
      }
LABEL_32:
      v17 = v21;
      v18 = -2147467259;
      if ( v21 )
        v18 = 0;
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v17 = v21;
      }
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        v17 = v21;
      }
      if ( v18 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
        if ( a2 )
        {
          v20 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
          CicBridge::DropBackingStore(v12, v20);
        }
        v17 = v21;
      }
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      return 0;
    }
    CicTrace(2u, "CThreadMgrEventSink_DIMCallBack::DIMCallback. cicBridge == NULL");
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18001de50  mov     [rsp-28h+arg_10], rbx
0x18001de55  push    rbp
0x18001de56  push    rsi
0x18001de57  push    rdi
0x18001de58  push    r13
0x18001de5a  push    r14
0x18001de5c  mov     rbp, rsp
0x18001de5f  sub     rsp, 50h
0x18001de63  mov     rbx, rdx
0x18001de66  mov     edi, ecx
0x18001de68  lea     rdx, aCthreadmgreven_2; "CThreadMgrEventSink_DIMCallBack"
0x18001de6f  mov     ecx, 8; unsigned int
0x18001de74  mov     rsi, r8
0x18001de77  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001de7c  cmp     edi, 2
0x18001de7f  jnz     loc_18001E0F6
0x18001de85  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x18001de8b  cmp     ecx, 0FFFFFFFFh
0x18001de8e  jz      loc_18001E10C
0x18001de94  call    cs:__imp_TlsGetValue
0x18001de9a  mov     rdi, rax
0x18001de9d  test    rax, rax
0x18001dea0  jz      loc_18001E10C
0x18001dea6  mov     r14, [rax+10h]
0x18001deaa  xor     r13d, r13d
0x18001dead  test    r14, r14
0x18001deb0  jz      loc_18001E22C
0x18001deb6  mov     rcx, [r14]
0x18001deb9  mov     rax, [rcx+8]
0x18001debd  mov     rcx, r14
0x18001dec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dec5  mov     [rbp+var_30], r13
0x18001dec9  lea     r8, [rbp+var_30]
0x18001decd  mov     rax, [r14]
0x18001ded0  lea     rdx, _GUID_0d2c969a_bc9c_437c_84ee_951c49b1a764
0x18001ded7  mov     rcx, r14
0x18001deda  mov     rax, [rax]
0x18001dedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dee2  cmp     [rbp+var_30], r13
0x18001dee6  jz      loc_18001E1A9
0x18001deec  mov     [rsp+50h+arg_8], r15
0x18001def4  test    rbx, rbx
0x18001def7  jnz     loc_18001E124
0x18001defd  and     dword ptr [rdi+18h], 0FFFFFFFEh
0x18001df01  mov     r15d, r13d
0x18001df04  xor     ecx, ecx
0x18001df06  call    cs:__imp_ImmGetAppCompatFlags
0x18001df0c  test    eax, 0D000000h
0x18001df11  jz      short loc_18001DF65
0x18001df13  mov     [rsp+50h+arg_0], r12
0x18001df1b  call    cs:__imp_GetFocus
0x18001df21  mov     r12, rax
0x18001df24  test    rax, rax
0x18001df27  jz      loc_18001E1BF
0x18001df2d  lea     rcx, aAimm12ProcessA; "_AIMM12_PROCESS_ATOM_"
0x18001df34  call    cs:__imp_FindAtomW
0x18001df3a  test    ax, ax
0x18001df3d  jz      loc_18001E1BF
0x18001df43  mov     rcx, r12
0x18001df46  call    MsimtfIsWindowFiltered
0x18001df4b  test    eax, eax
0x18001df4d  jz      loc_18001E1BF
0x18001df53  mov     r15d, 1
0x18001df59  or      [rdi+1Ch], r15d
0x18001df5d  mov     r12, [rsp+50h+arg_0]
0x18001df65  test    byte ptr [rdi+20h], 1
0x18001df69  jnz     loc_18001E143
0x18001df6f  test    r15d, r15d
0x18001df72  jnz     loc_18001E18C
0x18001df78  mov     r15, [rsp+50h+arg_8]
0x18001df80  mov     rcx, [rbp+var_30]
0x18001df84  test    rcx, rcx
0x18001df87  jz      short loc_18001DF95
0x18001df89  mov     rax, [rcx]
0x18001df8c  mov     rax, [rax+10h]
0x18001df90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df95  mov     rax, [r14]
0x18001df98  mov     rcx, r14
0x18001df9b  mov     rax, [rax+10h]
0x18001df9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa4  test    rbx, rbx
0x18001dfa7  jz      short loc_18001DFB9
0x18001dfa9  mov     rcx, rbx; struct ITfDocumentMgr *
0x18001dfac  call    ?IsOwnDim@CicBridge@@SAHPEAUITfDocumentMgr@@@Z; CicBridge::IsOwnDim(ITfDocumentMgr *)
0x18001dfb1  test    eax, eax
0x18001dfb3  jnz     loc_18001E0F6
0x18001dfb9  test    rsi, rsi
0x18001dfbc  jz      loc_18001E0F6
0x18001dfc2  mov     rcx, rsi; struct ITfDocumentMgr *
0x18001dfc5  call    ?IsOwnDim@CicBridge@@SAHPEAUITfDocumentMgr@@@Z; CicBridge::IsOwnDim(ITfDocumentMgr *)
0x18001dfca  test    eax, eax
0x18001dfcc  jz      loc_18001E0F6
0x18001dfd2  mov     r14, [rdi]
0x18001dfd5  test    r14, r14
0x18001dfd8  jz      loc_18001E242
0x18001dfde  mov     rax, [rsi]
0x18001dfe1  lea     r8, [rbp+var_20]
0x18001dfe5  lea     rdx, _GUID_7dcf57ac_18ad_438b_824d_979bffb74b7c
0x18001dfec  mov     [rbp+var_30], r13
0x18001dff0  mov     rcx, rsi
0x18001dff3  mov     [rbp+var_20], r13
0x18001dff7  mov     rax, [rax]
0x18001dffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfff  mov     r9, [rbp+var_20]
0x18001e003  mov     rcx, r13
0x18001e006  mov     [rbp+var_28], rcx
0x18001e00a  test    r9, r9
0x18001e00d  jz      loc_18001E096
0x18001e013  mov     rax, [r9]
0x18001e016  lea     r8, [rbp+var_28]
0x18001e01a  lea     rdx, GUID_COMPARTMENT_TRANSITORYEXTENSION_PARENT
0x18001e021  mov     rcx, r9
0x18001e024  mov     rax, [rax+18h]
0x18001e028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e02d  test    eax, eax
0x18001e02f  js      short loc_18001E092; jumptable 000000018001E276 cases 0-7,16-23
0x18001e031  mov     rcx, [rbp+var_28]
0x18001e035  test    rcx, rcx
0x18001e038  jz      short loc_18001E096
0x18001e03a  xor     eax, eax
0x18001e03c  lea     rdx, [rbp+pvarg]
0x18001e040  mov     qword ptr [rbp+pvarg+10h], rax
0x18001e044  xorps   xmm0, xmm0
0x18001e047  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001e04b  mov     rax, [rcx]
0x18001e04e  mov     rax, [rax+20h]
0x18001e052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e057  mov     rcx, qword ptr [rbp+pvarg+8]
0x18001e05b  test    eax, eax
0x18001e05d  js      short loc_18001E085
0x18001e05f  cmp     word ptr [rbp+pvarg], 0Dh
0x18001e064  jnz     short loc_18001E085
0x18001e066  test    rcx, rcx
0x18001e069  jz      short loc_18001E085
0x18001e06b  mov     rax, [rcx]
0x18001e06e  lea     r8, [rbp+var_30]
0x18001e072  lea     rdx, _GUID_4c074926_9ddd_4d5e_bdc9_1be08660be14
0x18001e079  mov     rax, [rax]
0x18001e07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e081  mov     rcx, qword ptr [rbp+pvarg+8]
0x18001e085  movzx   eax, word ptr [rbp+pvarg]
0x18001e089  cmp     eax, 0Bh
0x18001e08c  jnz     loc_18001E16D
0x18001e092  mov     rcx, [rbp+var_28]; jumptable 000000018001E276 cases 0-7,16-23
0x18001e096  mov     rax, [rbp+var_30]
0x18001e09a  mov     edi, 80004005h
0x18001e09f  test    rax, rax
0x18001e0a2  cmovnz  edi, r13d
0x18001e0a6  test    rcx, rcx
0x18001e0a9  jz      short loc_18001E0BB
0x18001e0ab  mov     rax, [rcx]
0x18001e0ae  mov     rax, [rax+10h]
0x18001e0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b7  mov     rax, [rbp+var_30]
0x18001e0bb  mov     r9, [rbp+var_20]
0x18001e0bf  test    r9, r9
0x18001e0c2  jz      short loc_18001E0D7
0x18001e0c4  mov     rax, [r9]
0x18001e0c7  mov     rcx, r9
0x18001e0ca  mov     rax, [rax+10h]
0x18001e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0d3  mov     rax, [rbp+var_30]
0x18001e0d7  test    edi, edi
0x18001e0d9  jns     loc_18001E1C8
0x18001e0df  test    rax, rax
0x18001e0e2  jz      short loc_18001E0F6
0x18001e0e4  mov     rcx, [rax]
0x18001e0e7  mov     rdx, [rcx+10h]
0x18001e0eb  mov     rcx, rax
0x18001e0ee  mov     rax, rdx
0x18001e0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0f6  xor     eax, eax
0x18001e0f8  mov     rbx, [rsp+50h+arg_10]
0x18001e100  add     rsp, 50h
0x18001e104  pop     r14
0x18001e106  pop     r13
0x18001e108  pop     rdi
0x18001e109  pop     rsi
0x18001e10a  pop     rbp
0x18001e10b  retn
0x18001e10c  lea     rdx, aCthreadmgreven_3; "CThreadMgrEventSink_DIMCallBack::DIMCal"...
0x18001e113  mov     ecx, 2; unsigned int
0x18001e118  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e11d  mov     eax, 80004005h
0x18001e122  jmp     short loc_18001E0F8
0x18001e124  mov     rcx, rbx; struct ITfDocumentMgr *
0x18001e127  call    ?IsOwnDim@CicBridge@@SAHPEAUITfDocumentMgr@@@Z; CicBridge::IsOwnDim(ITfDocumentMgr *)
0x18001e12c  test    eax, eax
0x18001e12e  jnz     loc_18001DEFD
0x18001e134  mov     r15d, 1
0x18001e13a  or      [rdi+18h], r15d
0x18001e13e  jmp     loc_18001DF04
0x18001e143  test    r15d, r15d
0x18001e146  jnz     loc_18001DF78
0x18001e14c  mov     rcx, [rbp+var_30]
0x18001e150  mov     rax, [rcx]
0x18001e153  mov     rax, [rax+18h]
0x18001e157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e15c  test    eax, eax
0x18001e15e  jnz     loc_18001E200
0x18001e164  and     dword ptr [rdi+20h], 0FFFFFFFEh
0x18001e168  jmp     loc_18001DF78
0x18001e16d  cmp     eax, 0Dh
0x18001e170  jnz     short loc_18001E1EC
0x18001e172  test    rcx, rcx
0x18001e175  jz      loc_18001E092; jumptable 000000018001E276 cases 0-7,16-23
0x18001e17b  mov     rax, [rcx]
0x18001e17e  mov     rax, [rax+10h]
0x18001e182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e187  jmp     loc_18001E092; jumptable 000000018001E276 cases 0-7,16-23
0x18001e18c  mov     rcx, [rbp+var_30]
0x18001e190  mov     rax, [rcx]
0x18001e193  mov     rax, [rax+20h]
0x18001e197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e19c  test    eax, eax
0x18001e19e  jnz     short loc_18001E216
0x18001e1a0  or      dword ptr [rdi+20h], 1
0x18001e1a4  jmp     loc_18001DF78
0x18001e1a9  lea     rdx, aCthreadmgreven_4; "CThreadMgrEventSink_DIMCallBack::DIMCal"...
0x18001e1b0  mov     ecx, 2; unsigned int
0x18001e1b5  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e1ba  jmp     loc_18001DF80
0x18001e1bf  and     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x18001e1c3  jmp     loc_18001DF5D
0x18001e1c8  mov     rcx, [rax]
0x18001e1cb  mov     rdx, [rcx+28h]
0x18001e1cf  mov     rcx, rax
0x18001e1d2  mov     rax, rdx
0x18001e1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1da  test    rbx, rbx
0x18001e1dd  jnz     loc_18001E278
0x18001e1e3  mov     rax, [rbp+var_30]
0x18001e1e7  jmp     loc_18001E0DF
0x18001e1ec  cmp     eax, 17h; switch 24 cases
0x18001e1ef  jbe     short loc_18001E25D
0x18001e1f1  lea     rcx, [rbp+pvarg]; jumptable 000000018001E276 default case, cases 8-15
0x18001e1f5  call    cs:__imp_VariantClear
0x18001e1fb  jmp     loc_18001E092; jumptable 000000018001E276 cases 0-7,16-23
0x18001e200  lea     rdx, aCthreadmgreven_1; "CThreadMgrEventSink_DIMCallBack::CTFDet"...
0x18001e207  mov     ecx, 2; unsigned int
0x18001e20c  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e211  jmp     loc_18001E164
0x18001e216  lea     rdx, aCthreadmgreven; "CThreadMgrEventSink_DIMCallBack::CTFDet"...
0x18001e21d  mov     ecx, 2; unsigned int
0x18001e222  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e227  jmp     loc_18001E1A0
0x18001e22c  lea     rdx, aCthreadmgreven_5; "CThreadMgrEventSink_DIMCallBack::DIMCal"...
0x18001e233  mov     ecx, 2; unsigned int
0x18001e238  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e23d  jmp     loc_18001DFA4
0x18001e242  lea     rdx, aCthreadmgreven_0; "CThreadMgrEventSink_DIMCallBack::DIMCal"...
0x18001e249  mov     ecx, 2; unsigned int
0x18001e24e  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18001e253  mov     eax, 80004005h
0x18001e258  jmp     loc_18001E0F8
0x18001e25d  lea     rdx, __ImageBase
0x18001e264  movzx   eax, ds:(byte_18001E2A0 - 180000000h)[rdx+rax]
0x18001e26c  mov     ecx, ds:(jpt_18001E276 - 180000000h)[rdx+rax*4]
0x18001e273  add     rcx, rdx
0x18001e276  jmp     rcx; switch jump
0x18001e278  mov     rcx, [rbp+var_30]
0x18001e27c  mov     rax, [rcx]
0x18001e27f  mov     rax, [rax+18h]
0x18001e283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e288  mov     rdx, rax; HWND
0x18001e28b  mov     rcx, r14; this
0x18001e28e  call    ?DropBackingStore@CicBridge@@QEAAXPEAUHWND__@@@Z; CicBridge::DropBackingStore(HWND__ *)
0x18001e293  jmp     loc_18001E1E3
```
