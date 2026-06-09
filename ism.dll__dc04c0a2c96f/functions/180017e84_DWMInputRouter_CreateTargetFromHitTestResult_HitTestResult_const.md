# DWMInputRouter::CreateTargetFromHitTestResult(HitTestResult const &)

- ea: `0x180017e84`
- end: `0x180018185`
- name: `?CreateTargetFromHitTestResult@DWMInputRouter@@AEAA?AV?$ComPtr@UIInputTarget@@@WRL@Microsoft@@AEBUHitTestResult@@@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800179e0`

## callees

- `0x180012b74`
- `0x180017e84`
- `0x180018804`
- `0x18003b57c`
- `0x18008dcac`
- `0x18008ead4`
- `0x180094fc8`
- `0x1800f08d8`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180017f36`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180017f36`
- `CoreMessaging!CoreUICreate` at `0x1800180f5`
- `CoreMessaging!CoreUICreate` at `0x1800180f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall DWMInputRouter::CreateTargetFromHitTestResult(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  struct ISMBamos_AutoBamos::BamoConnection **v14; // rax
  struct InputSystemServerConnection *v15; // rcx
  Microsoft::Bamo::BaseBamoConnection *v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-20h]
  Microsoft::Bamo::BaseBamoConnection *v19; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF
  _QWORD *v22; // [rsp+88h] [rbp+48h]
  __int64 v23; // [rsp+98h] [rbp+58h] BYREF

  v22 = a2;
  v21 = a1;
  if ( !ISMStatics::s_inputSystemBamoConnection )
  {
    v21 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    v13 = CoreUICreate(&v21);
    if ( v13 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\ismstatics.cpp",
        (const char *)(unsigned int)v13,
        0);
    v14 = InputSystemServerConnection::Create(&v19, v21);
    v15 = *v14;
    *v14 = 0;
    ISMStatics::s_inputSystemBamoConnection = v15;
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::Bamo::BaseBamoConnection::Release(v16);
    }
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)ISMStatics::s_inputSystemBamoConnection + 31) + 8LL)
                                          + 152LL))(*((_QWORD *)ISMStatics::s_inputSystemBamoConnection + 31) + 8LL);
  InputSiteManager::GetInputSiteFromInputSinkHandle(v5, &v23, *(_QWORD *)(a3 + 8));
  *a2 = 0;
  v18 = 1;
  v6 = v23;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  *a2 = 0;
  v7 = malloc(0x88u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x88u);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v8[16] = 1;
    *(_QWORD *)v8 = &DWMInputTarget::`vftable'{for `IInputTarget'};
    *((_QWORD *)v8 + 1) = &DWMInputTarget::`vftable'{for `IDCompInputTarget'};
    *((_QWORD *)v8 + 2) = &DWMInputTarget::`vftable'{for `IDWMPnPTarget'};
    *((_QWORD *)v8 + 3) = &DWMInputTarget::`vftable'{for `IFocusInputTarget'};
    *((_QWORD *)v8 + 4) = &DWMInputTarget::`vftable'{for `IInputTarget2'};
    *((_QWORD *)v8 + 5) = &DWMInputTarget::`vftable'{for `IDWMSupportedInputTarget'};
    *((_QWORD *)v8 + 6) = &DWMInputTarget::`vftable'{for `IInputSiteTarget'};
    *((_QWORD *)v8 + 7) = &DWMInputTarget::`vftable'{for `RefCountedObject'};
    v8[18] = 0;
    *((_OWORD *)v8 + 5) = 0;
    *((_OWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 14) = 0;
    *((_QWORD *)v8 + 15) = v6;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *((_QWORD *)v8 + 16) = 0;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *a2 = v8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputtarget.cpp",
      (const char *)0x8007000ELL,
      1);
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( *(_BYTE *)(a3 + 88) )
  {
    v21 = 0;
    v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(
            *a2,
            &GUID_05b38163_1229_4e7b_a0fc_5b47c4e7b631,
            &v21);
    if ( v11 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x54F,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v11,
        v18);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 80LL))(v21, *(unsigned int *)(a3 + 92));
    v12 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  v9 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return a2;
}

```

## disassembly

```asm
0x180017e84  mov     [rsp-38h+arg_8], rdx
0x180017e89  mov     [rsp-38h+arg_0], rcx
0x180017e8e  push    rbp
0x180017e8f  push    rbx
0x180017e90  push    rsi
0x180017e91  push    rdi
0x180017e92  push    r13
0x180017e94  push    r14
0x180017e96  push    r15
0x180017e98  mov     rbp, rsp
0x180017e9b  sub     rsp, 40h
0x180017e9f  movaps  [rsp+40h+var_10], xmm6
0x180017ea4  mov     r14, r8
0x180017ea7  mov     rsi, rdx
0x180017eaa  xor     r15d, r15d
0x180017ead  mov     [rbp+var_20], r15d
0x180017eb1  cmp     cs:?s_inputSystemBamoConnection@ISMStatics@@0PEAVInputSystemServerConnection@@EA, r15; InputSystemServerConnection * ISMStatics::s_inputSystemBamoConnection
0x180017eb8  jz      loc_1800180E4
0x180017ebe  mov     rax, cs:?s_inputSystemBamoConnection@ISMStatics@@0PEAVInputSystemServerConnection@@EA; InputSystemServerConnection * ISMStatics::s_inputSystemBamoConnection
0x180017ec5  mov     rcx, [rax+0F8h]
0x180017ecc  add     rcx, 8
0x180017ed0  mov     rax, [rcx]
0x180017ed3  mov     rax, [rax+98h]
0x180017eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017edf  mov     r8, [r14+8]
0x180017ee3  lea     rdx, [rbp+arg_18]
0x180017ee7  mov     rcx, rax
0x180017eea  call    ?GetInputSiteFromInputSinkHandle@InputSiteManager@@QEAA?AV?$ComPtr@VInputSite@@@WRL@Microsoft@@PEAX@Z; InputSiteManager::GetInputSiteFromInputSinkHandle(void *)
0x180017eef  nop
0x180017ef0  mov     [rsi], r15
0x180017ef3  mov     [rbp+var_20], 1
0x180017efa  mov     rbx, [rbp+arg_18]
0x180017efe  test    rbx, rbx
0x180017f01  jz      short loc_180017F13
0x180017f03  mov     rax, [rbx]
0x180017f06  mov     rcx, rbx
0x180017f09  mov     rax, [rax+8]
0x180017f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f12  nop
0x180017f13  xorps   xmm6, xmm6
0x180017f16  xor     r13d, r13d
0x180017f19  test    rbx, rbx
0x180017f1c  jz      short loc_180017F2E
0x180017f1e  mov     rax, [rbx]
0x180017f21  mov     rcx, rbx
0x180017f24  mov     rax, [rax+8]
0x180017f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f2d  nop
0x180017f2e  mov     [rsi], r15
0x180017f31  mov     ecx, 88h; Size
0x180017f36  call    cs:__imp_malloc
0x180017f3c  mov     rdi, rax
0x180017f3f  test    rax, rax
0x180017f42  jz      loc_18001814F
0x180017f48  xor     edx, edx; Val
0x180017f4a  mov     r8d, 88h; Size
0x180017f50  mov     rcx, rax; void *
0x180017f53  call    memset_0
0x180017f58  nop
0x180017f59  test    rbx, rbx
0x180017f5c  jz      short loc_180017F6E
0x180017f5e  mov     rcx, [rbx]
0x180017f61  mov     rax, [rcx+8]
0x180017f65  mov     rcx, rbx
0x180017f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f6d  nop
0x180017f6e  mov     dword ptr [rdi+40h], 1
0x180017f75  lea     rax, ??_7DWMInputTarget@@6BIInputTarget@@@; const DWMInputTarget::`vftable'{for `IInputTarget'}
0x180017f7c  mov     [rdi], rax
0x180017f7f  lea     rax, ??_7DWMInputTarget@@6BIDCompInputTarget@@@; const DWMInputTarget::`vftable'{for `IDCompInputTarget'}
0x180017f86  mov     [rdi+8], rax
0x180017f8a  lea     rax, ??_7DWMInputTarget@@6BIDWMPnPTarget@@@; const DWMInputTarget::`vftable'{for `IDWMPnPTarget'}
0x180017f91  mov     [rdi+10h], rax
0x180017f95  lea     rax, ??_7DWMInputTarget@@6BIFocusInputTarget@@@; const DWMInputTarget::`vftable'{for `IFocusInputTarget'}
0x180017f9c  mov     [rdi+18h], rax
0x180017fa0  lea     rax, ??_7DWMInputTarget@@6BIInputTarget2@@@; const DWMInputTarget::`vftable'{for `IInputTarget2'}
0x180017fa7  mov     [rdi+20h], rax
0x180017fab  lea     rax, ??_7DWMInputTarget@@6BIDWMSupportedInputTarget@@@; const DWMInputTarget::`vftable'{for `IDWMSupportedInputTarget'}
0x180017fb2  mov     [rdi+28h], rax
0x180017fb6  lea     rax, ??_7DWMInputTarget@@6BIInputSiteTarget@@@; const DWMInputTarget::`vftable'{for `IInputSiteTarget'}
0x180017fbd  mov     [rdi+30h], rax
0x180017fc1  lea     rax, ??_7DWMInputTarget@@6BRefCountedObject@@@; const DWMInputTarget::`vftable'{for `RefCountedObject'}
0x180017fc8  mov     [rdi+38h], rax
0x180017fcc  mov     [rdi+48h], r15d
0x180017fd0  movups  xmmword ptr [rdi+50h], xmm6
0x180017fd4  movups  xmmword ptr [rdi+60h], xmm6
0x180017fd8  mov     [rdi+70h], r13
0x180017fdc  mov     [rdi+78h], rbx
0x180017fe0  test    rbx, rbx
0x180017fe3  jz      short loc_180017FF5
0x180017fe5  mov     rax, [rbx]
0x180017fe8  mov     rcx, rbx
0x180017feb  mov     rax, [rax+8]
0x180017fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff4  nop
0x180017ff5  mov     [rdi+80h], r15
0x180017ffc  test    rbx, rbx
0x180017fff  jz      short loc_180018011
0x180018001  mov     rax, [rbx]
0x180018004  mov     rcx, rbx
0x180018007  mov     rax, [rax+10h]
0x18001800b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018010  nop
0x180018011  mov     [rsi], rdi
0x180018014  test    rbx, rbx
0x180018017  jz      short loc_180018029
0x180018019  mov     rax, [rbx]
0x18001801c  mov     rcx, rbx
0x18001801f  mov     rax, [rax+10h]
0x180018023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018028  nop
0x180018029  test    rbx, rbx
0x18001802c  jz      short loc_18001803E
0x18001802e  mov     rax, [rbx]
0x180018031  mov     rcx, rbx
0x180018034  mov     rax, [rax+10h]
0x180018038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001803d  nop
0x18001803e  cmp     [r14+58h], r15b
0x180018042  jnz     short loc_180018075
0x180018044  mov     rcx, [rbp+arg_18]
0x180018048  test    rcx, rcx
0x18001804b  jz      short loc_18001805E
0x18001804d  mov     [rbp+arg_18], r15
0x180018051  mov     rax, [rcx]
0x180018054  mov     rax, [rax+10h]
0x180018058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001805d  nop
0x18001805e  mov     rax, rsi
0x180018061  movaps  xmm6, [rsp+40h+var_10]
0x180018066  add     rsp, 40h
0x18001806a  pop     r15
0x18001806c  pop     r14
0x18001806e  pop     r13
0x180018070  pop     rdi
0x180018071  pop     rsi
0x180018072  pop     rbx
0x180018073  pop     rbp
0x180018074  retn
0x180018075  mov     [rbp+arg_0], r15
0x180018079  mov     rcx, [rsi]
0x18001807c  mov     rax, [rcx]
0x18001807f  lea     r8, [rbp+arg_0]
0x180018083  lea     rdx, _GUID_05b38163_1229_4e7b_a0fc_5b47c4e7b631
0x18001808a  mov     rax, [rax]
0x18001808d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018092  nop
0x180018093  mov     rcx, [rbp+38h]; this
0x180018097  test    eax, eax
0x180018099  js      short loc_1800180CF
0x18001809b  mov     rcx, [rbp+arg_0]
0x18001809f  mov     rax, [rcx]
0x1800180a2  mov     edx, [r14+5Ch]
0x1800180a6  mov     rax, [rax+50h]
0x1800180aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180af  nop
0x1800180b0  mov     rcx, [rbp+arg_0]
0x1800180b4  test    rcx, rcx
0x1800180b7  jz      short loc_1800180CA
0x1800180b9  mov     [rbp+arg_0], r15
0x1800180bd  mov     rax, [rcx]
0x1800180c0  mov     rax, [rax+10h]
0x1800180c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180c9  nop
0x1800180ca  jmp     loc_180018044
0x1800180cf  mov     r9d, eax; char *
0x1800180d2  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800180d9  mov     edx, 54Fh; void *
0x1800180de  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800180e4  mov     [rbp+arg_0], r15
0x1800180e8  lea     rcx, [rbp+arg_0]
0x1800180ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800180f1  lea     rcx, [rbp+arg_0]
0x1800180f5  call    cs:__imp_CoreUICreate
0x1800180fb  mov     rcx, [rbp+38h]; this
0x1800180ff  test    eax, eax
0x180018101  js      short loc_180018170
0x180018103  mov     rdx, [rbp+arg_0]
0x180018107  lea     rcx, [rbp+var_18]
0x18001810b  call    ?Create@InputSystemServerConnection@@SA?AV?$ComPtr@VInputSystemServerConnection@@@WRL@Microsoft@@PEAUIMessageSession@@@Z; InputSystemServerConnection::Create(IMessageSession *)
0x180018110  mov     rcx, [rax]
0x180018113  mov     [rax], r15
0x180018116  mov     cs:?s_inputSystemBamoConnection@ISMStatics@@0PEAVInputSystemServerConnection@@EA, rcx; InputSystemServerConnection * ISMStatics::s_inputSystemBamoConnection
0x18001811d  mov     rcx, [rbp+var_18]; this
0x180018121  test    rcx, rcx
0x180018124  jz      short loc_180018130
0x180018126  mov     [rbp+var_18], r15
0x18001812a  call    ?Release@BaseBamoConnection@Bamo@Microsoft@@QEAAKXZ; Microsoft::Bamo::BaseBamoConnection::Release(void)
0x18001812f  nop
0x180018130  mov     rcx, [rbp+arg_0]
0x180018134  test    rcx, rcx
0x180018137  jz      short loc_18001814A
0x180018139  mov     [rbp+arg_0], r15
0x18001813d  mov     rax, [rcx]
0x180018140  mov     rax, [rax+10h]
0x180018144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018149  nop
0x18001814a  jmp     loc_180017EBE
0x18001814f  mov     rcx, [rbp+38h]; this
0x180018153  mov     r9d, 8007000Eh; char *
0x180018159  lea     r8, aOnecoreuapWind_17; "onecoreuap\\windows\\moderncore\\inputv"...
0x180018160  mov     edx, 6Eh ; 'n'; void *
0x180018165  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001816a  nop
0x18001816b  jmp     loc_180018014
0x180018170  mov     r9d, eax; char *
0x180018173  lea     r8, aOnecoreuapWind_136; "onecoreuap\\windows\\moderncore\\inputv"...
0x18001817a  mov     edx, 33h ; '3'; void *
0x18001817f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
