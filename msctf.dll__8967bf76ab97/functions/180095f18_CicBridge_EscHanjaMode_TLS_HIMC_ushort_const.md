# CicBridge::EscHanjaMode(TLS *,HIMC__ *,ushort const *)

- ea: `0x180095f18`
- end: `0x180096199`
- name: `?EscHanjaMode@CicBridge@@AEAA_JPEAVTLS@@PEAUHIMC__@@PEBG@Z`
- size: `641`
- prototype: `__int64(CicBridge *__hidden this, struct TLS *, HIMC, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800def7c`

## callees

- `0x1800139a4`
- `0x1800185f0`
- `0x180018640`
- `0x18001a460`
- `0x18001cc80`
- `0x18002ac80`
- `0x18003c94c`
- `0x1800454c0`
- `0x180045520`
- `0x180063a2c`
- `0x18006fb68`
- `0x180095f18`
- `0x1800e0048`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096007`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096007`
- `IMM32!ImmSetConversionStatus` at `0x18009608d`
- `IMM32!ImmSetConversionStatus` at `0x18009608d`
- `ext-ms-win-imm-l1-1-0!ImmSetCompositionStringW` at `0x180096046`
- `ext-ms-win-imm-l1-1-0!ImmSetCompositionStringW` at `0x180096072`
- `ext-ms-win-imm-l1-1-0!ImmSetCompositionStringW` at `0x180096046`
- `ext-ms-win-imm-l1-1-0!ImmSetCompositionStringW` at `0x180096072`

## pseudocode

```c
__int64 __fastcall CicBridge::EscHanjaMode(CicBridge *this, struct TLS *a2, HIMC a3, unsigned __int16 *a4)
{
  __int64 v7; // r15
  struct tagRECONVERTSTRING *v8; // r14
  __int64 v9; // rsi
  __int64 v10; // rdi
  unsigned int v11; // ebx
  struct tagRECONVERTSTRING *v12; // rax
  BOOL v13; // eax
  BOOL v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v20; // [rsp+30h] [rbp-79h] BYREF
  __int64 v21; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v22[8]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v23; // [rsp+48h] [rbp-61h]
  HIMC v24; // [rsp+50h] [rbp-59h]
  int v25; // [rsp+58h] [rbp-51h]
  void **v26; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v27; // [rsp+68h] [rbp-41h]
  int v28; // [rsp+78h] [rbp-31h]
  _BYTE v29[8]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v30; // [rsp+88h] [rbp-21h]
  int v31; // [rsp+90h] [rbp-19h]
  int v32; // [rsp+B0h] [rbp+7h]
  int v33; // [rsp+B8h] [rbp+Fh]
  int v34; // [rsp+110h] [rbp+67h]

  CicTrace(8u, "CicBridge::EscHanjaMode");
  IMCLock::IMCLock((IMCLock *)v22, a3);
  v7 = v23;
  v8 = 0;
  if ( v23 && v25 >= 0 )
  {
    InternalIMCCLock::InternalIMCCLock((InternalIMCCLock *)&v26, *(HIMCC *)(v23 + 392));
    v26 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
    if ( v27 && v28 >= 0 )
    {
      v9 = *v27;
      v10 = 1;
      if ( !*v27 )
        goto LABEL_8;
      if ( (*(_BYTE *)(v9 + 196) & 1) == 0 )
      {
        *(_DWORD *)(v9 + 216) |= 1u;
LABEL_8:
        CWReconvertString::CWReconvertString((CWReconvertString *)v29, v24, 0, 0);
        v32 = 1;
        v33 = 1;
        CompData<unsigned short>::WriteCompData((CVoidStructArray *)v29, a4, 1);
        v34 = 0;
        v11 = 2 * v31 + 32;
        if ( 2 * v31 != -32 )
        {
          v12 = (struct tagRECONVERTSTRING *)LocalAlloc(0x40u, v11);
          v8 = v12;
          if ( v12 )
          {
            v34 = 1;
            CWReconvertString::ReadCompData((CWReconvertString *)v29, v12, v11);
          }
        }
        v13 = ImmSetCompositionStringW(a3, 0x20000u, v8, v11, 0, 0);
        v10 = v13;
        if ( v13 )
        {
          v14 = ImmSetCompositionStringW(a3, 0x10000u, v8, v11, 0, 0);
          v10 = v14;
          if ( v14 )
            v10 = ImmSetConversionStatus(a3, *(_DWORD *)(v7 + 28) | 0x40, *(_DWORD *)(v7 + 32));
        }
        if ( v9 )
        {
          if ( a2 )
            v15 = *((_QWORD *)a2 + 2);
          else
            v15 = 0;
          ATL::CComPtrBase<IUIManager>::CComPtrBase<IUIManager>(&v21, v15);
          v16 = v21;
          if ( v21 )
          {
            ATL::CComQIPtr<ITfContext_P,&__s_GUID const _GUID_2dee47c8_704d_42a0_9983_ffeed659b64d>::CComQIPtr<ITfContext_P,&__s_GUID const _GUID_2dee47c8_704d_42a0_9983_ffeed659b64d>(
              &v20,
              *(_QWORD *)(v9 + 48));
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 128LL))(v16);
            else
              CicTrace(2u, "CicBridge::EscHanjaMode. QueryInterface is failed");
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20, v17);
          }
          else
          {
            CicTrace(2u, "CicBridge::EscHanjaMode. ptls or ptim_P==NULL");
          }
          *(_DWORD *)(v9 + 216) &= ~1u;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21, v18);
        }
        if ( v34 )
          cicMemFree(v8);
        cicMemFree(v30);
      }
    }
    else
    {
      CicTrace(2u, "CicBridge::EscHanjaMode. imc_ctfime==NULL");
      v10 = 0;
    }
    InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v26);
    IMCLock::~IMCLock((IMCLock *)v22);
    return v10;
  }
  CicTrace(2u, "CicBridge::EscHanjaMode. imc==NULL");
  IMCLock::~IMCLock((IMCLock *)v22);
  return 0;
}

```

## disassembly

```asm
0x180095f18  mov     [rsp-8+arg_0], rcx
0x180095f1d  push    rbp
0x180095f1e  push    rbx
0x180095f1f  push    rsi
0x180095f20  push    rdi
0x180095f21  push    r12
0x180095f23  push    r13
0x180095f25  push    r14
0x180095f27  push    r15
0x180095f29  lea     rbp, [rsp-1Fh]
0x180095f2e  sub     rsp, 0C8h
0x180095f35  mov     r13, rdx
0x180095f38  mov     ecx, 8; unsigned int
0x180095f3d  lea     rdx, aCicbridgeEscha_1; "CicBridge::EscHanjaMode"
0x180095f44  mov     rbx, r9
0x180095f47  mov     r12, r8
0x180095f4a  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180095f4f  mov     rdx, r12; HIMC
0x180095f52  lea     rcx, [rbp+57h+var_C0]; this
0x180095f56  call    ??0IMCLock@@QEAA@PEAUHIMC__@@@Z; IMCLock::IMCLock(HIMC__ *)
0x180095f5b  mov     r15, [rbp+57h+var_B8]
0x180095f5f  xor     r14d, r14d
0x180095f62  test    r15, r15
0x180095f65  jz      loc_180096169
0x180095f6b  cmp     [rbp+57h+var_A8], r14d
0x180095f6f  jl      loc_180096169
0x180095f75  mov     rdx, [r15+188h]; HIMCC
0x180095f7c  lea     rcx, [rbp+57h+var_A0]; this
0x180095f80  call    ??0InternalIMCCLock@@QEAA@PEAUHIMCC__@@@Z; InternalIMCCLock::InternalIMCCLock(HIMCC__ *)
0x180095f85  mov     rsi, [rbp+57h+var_98]
0x180095f89  lea     rax, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x180095f90  mov     [rbp+57h+var_A0], rax
0x180095f94  test    rsi, rsi
0x180095f97  jz      loc_18009613E
0x180095f9d  cmp     [rbp+57h+var_88], r14d
0x180095fa1  jl      loc_18009613E
0x180095fa7  mov     rsi, [rsi]
0x180095faa  lea     edi, [r14+1]
0x180095fae  test    rsi, rsi
0x180095fb1  jz      short loc_180095FC6
0x180095fb3  test    [rsi+0C4h], dil
0x180095fba  jnz     loc_180096152
0x180095fc0  or      [rsi+0D8h], edi
0x180095fc6  mov     rdx, [rbp+57h+var_B0]; HIMC
0x180095fca  lea     rcx, [rbp+57h+var_80]; this
0x180095fce  xor     r9d, r9d; unsigned int
0x180095fd1  xor     r8d, r8d; struct tagRECONVERTSTRING *
0x180095fd4  call    ??0CWReconvertString@@QEAA@PEAUHIMC__@@PEAUtagRECONVERTSTRING@@K@Z; CWReconvertString::CWReconvertString(HIMC__ *,tagRECONVERTSTRING *,ulong)
0x180095fd9  mov     r8d, edi; int
0x180095fdc  mov     [rbp+57h+var_50], edi
0x180095fdf  mov     rdx, rbx; Src
0x180095fe2  mov     [rbp+57h+var_48], edi
0x180095fe5  lea     rcx, [rbp+57h+var_80]; this
0x180095fe9  call    ?WriteCompData@?$CompData@G@@QEAAKPEBGK@Z; CompData<ushort>::WriteCompData(ushort const *,ulong)
0x180095fee  mov     eax, [rbp+57h+var_70]
0x180095ff1  mov     dword ptr [rbp+57h+arg_0], r14d
0x180095ff5  lea     ebx, ds:20h[rax*2]
0x180095ffc  test    ebx, ebx
0x180095ffe  jz      short loc_180096027
0x180096000  mov     edx, ebx; uBytes
0x180096002  mov     ecx, 40h ; '@'; uFlags
0x180096007  call    cs:__imp_LocalAlloc
0x18009600d  mov     r14, rax
0x180096010  test    rax, rax
0x180096013  jz      short loc_180096027
0x180096015  mov     r8d, ebx; unsigned int
0x180096018  mov     dword ptr [rbp+57h+arg_0], edi
0x18009601b  mov     rdx, rax; struct tagRECONVERTSTRING *
0x18009601e  lea     rcx, [rbp+57h+var_80]; this
0x180096022  call    ?ReadCompData@CWReconvertString@@QEAA?BKPEAUtagRECONVERTSTRING@@K@Z; CWReconvertString::ReadCompData(tagRECONVERTSTRING *,ulong)
0x180096027  mov     [rsp+100h+dwReadLen], 0; dwReadLen
0x18009602f  mov     r9d, ebx; dwCompLen
0x180096032  mov     r8, r14; lpComp
0x180096035  mov     [rsp+100h+lpRead], 0; lpRead
0x18009603e  mov     edx, 20000h; dwIndex
0x180096043  mov     rcx, r12; HIMC
0x180096046  call    cs:__imp_ImmSetCompositionStringW
0x18009604c  movsxd  rdi, eax
0x18009604f  test    eax, eax
0x180096051  jz      short loc_180096096
0x180096053  mov     [rsp+100h+dwReadLen], 0; dwReadLen
0x18009605b  mov     r9d, ebx; dwCompLen
0x18009605e  mov     r8, r14; lpComp
0x180096061  mov     [rsp+100h+lpRead], 0; lpRead
0x18009606a  mov     edx, 10000h; dwIndex
0x18009606f  mov     rcx, r12; HIMC
0x180096072  call    cs:__imp_ImmSetCompositionStringW
0x180096078  movsxd  rdi, eax
0x18009607b  test    eax, eax
0x18009607d  jz      short loc_180096096
0x18009607f  mov     edx, [r15+1Ch]
0x180096083  mov     rcx, r12; HIMC
0x180096086  mov     r8d, [r15+20h]; DWORD
0x18009608a  or      edx, 40h; DWORD
0x18009608d  call    cs:__imp_ImmSetConversionStatus
0x180096093  movsxd  rdi, eax
0x180096096  test    rsi, rsi
0x180096099  jz      loc_180096125
0x18009609f  test    r13, r13
0x1800960a2  jz      short loc_1800960AA
0x1800960a4  mov     rdx, [r13+10h]
0x1800960a8  jmp     short loc_1800960AC
0x1800960aa  xor     edx, edx
0x1800960ac  lea     rcx, [rbp+57h+var_C8]
0x1800960b0  call    ??0?$CComPtrBase@UIUIManager@@@ATL@@IEAA@PEAUIUIManager@@@Z; ATL::CComPtrBase<IUIManager>::CComPtrBase<IUIManager>(IUIManager *)
0x1800960b5  mov     rbx, [rbp+57h+var_C8]
0x1800960b9  test    rbx, rbx
0x1800960bc  jz      short loc_180096104
0x1800960be  mov     rdx, [rsi+30h]
0x1800960c2  lea     rcx, [rbp+57h+var_D0]
0x1800960c6  call    ??0?$CComQIPtr@UITfContext_P@@$1?_GUID_2dee47c8_704d_42a0_9983_ffeed659b64d@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ITfContext_P,&__s_GUID const _GUID_2dee47c8_704d_42a0_9983_ffeed659b64d>::CComQIPtr<ITfContext_P,&__s_GUID const _GUID_2dee47c8_704d_42a0_9983_ffeed659b64d>(IUnknown *)
0x1800960cb  mov     rdx, [rbp+57h+var_D0]
0x1800960cf  test    rdx, rdx
0x1800960d2  jz      short loc_1800960E8
0x1800960d4  mov     rax, [rbx]
0x1800960d7  mov     rcx, rbx
0x1800960da  mov     rax, [rax+80h]
0x1800960e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800960e6  jmp     short loc_1800960F9
0x1800960e8  lea     rdx, aCicbridgeEscha_0; "CicBridge::EscHanjaMode. QueryInterface"...
0x1800960ef  mov     ecx, 2; unsigned int
0x1800960f4  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x1800960f9  lea     rcx, [rbp+57h+var_D0]
0x1800960fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180096102  jmp     short loc_180096115
0x180096104  lea     rdx, aCicbridgeEscha; "CicBridge::EscHanjaMode. ptls or ptim_P"...
0x18009610b  mov     ecx, 2; unsigned int
0x180096110  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180096115  and     dword ptr [rsi+0D8h], 0FFFFFFFEh
0x18009611c  lea     rcx, [rbp+57h+var_C8]
0x180096120  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180096125  cmp     dword ptr [rbp+57h+arg_0], 0
0x180096129  jz      short loc_180096133
0x18009612b  mov     rcx, r14
0x18009612e  call    cicMemFree
0x180096133  mov     rcx, [rbp+57h+var_78]
0x180096137  call    cicMemFree
0x18009613c  jmp     short loc_180096152
0x18009613e  lea     rdx, aCicbridgeEscha_3; "CicBridge::EscHanjaMode. imc_ctfime==NU"...
0x180096145  mov     ecx, 2; unsigned int
0x18009614a  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18009614f  mov     rdi, r14
0x180096152  lea     rcx, [rbp+57h+var_A0]; this
0x180096156  call    ??1InternalIMCCLock@@UEAA@XZ; InternalIMCCLock::~InternalIMCCLock(void)
0x18009615b  lea     rcx, [rbp+57h+var_C0]; this
0x18009615f  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180096164  mov     rax, rdi
0x180096167  jmp     short loc_180096185
0x180096169  lea     rdx, aCicbridgeEscha_2; "CicBridge::EscHanjaMode. imc==NULL"
0x180096170  mov     ecx, 2; unsigned int
0x180096175  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x18009617a  lea     rcx, [rbp+57h+var_C0]; this
0x18009617e  call    ??1IMCLock@@UEAA@XZ; IMCLock::~IMCLock(void)
0x180096183  xor     eax, eax
0x180096185  add     rsp, 0C8h
0x18009618c  pop     r15
0x18009618e  pop     r14
0x180096190  pop     r13
0x180096192  pop     r12
0x180096194  pop     rdi
0x180096195  pop     rsi
0x180096196  pop     rbx
0x180096197  pop     rbp
0x180096198  retn
```
