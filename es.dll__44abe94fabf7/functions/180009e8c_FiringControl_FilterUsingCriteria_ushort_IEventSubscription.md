# FiringControl::FilterUsingCriteria(ushort *,IEventSubscription *)

- ea: `0x180009e8c`
- end: `0x18000a1de`
- name: `?FilterUsingCriteria@FiringControl@@IEAAJPEAGPEAUIEventSubscription@@@Z`
- size: `850`
- prototype: `__int64 __fastcall(FiringControl *__hidden this, unsigned __int16 *, struct IEventSubscription *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800098f0`
- `0x18001ae10`

## callees

- `0x180008938`
- `0x180009e8c`
- `0x18000fce0`
- `0x180018340`
- `0x18001c8f0`
- `0x18002eba4`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180009f67`
- `msvcrt!_itow_s` at `0x180009f67`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a13a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a145`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a150`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a15b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004387a`
- `OLEAUT32!__imp_SysFreeString` at `0x180043884`
- `OLEAUT32!__imp_SysFreeString` at `0x18004388e`
- `OLEAUT32!__imp_SysFreeString` at `0x180043898`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a13a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a145`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a150`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a15b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004387a`
- `OLEAUT32!__imp_SysFreeString` at `0x180043884`
- `OLEAUT32!__imp_SysFreeString` at `0x18004388e`
- `OLEAUT32!__imp_SysFreeString` at `0x180043898`

## string_xrefs

- `0x180009f1c`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009fb2`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009fe2`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000a011`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000a04e`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000a082`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000a0be`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
__int64 __fastcall FiringControl::FilterUsingCriteria(
        FiringControl *this,
        unsigned __int16 *a2,
        struct IEventSubscription *a3)
{
  int v6; // eax
  int v7; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // r9
  int v14; // eax
  unsigned __int16 *v15; // rdx
  struct IQueryPlan *v16; // rbx
  int Value; // [rsp+54h] [rbp-184h] BYREF
  __int64 v19; // [rsp+58h] [rbp-180h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-178h] BYREF
  BSTR v21; // [rsp+68h] [rbp-170h] BYREF
  BSTR v22; // [rsp+70h] [rbp-168h] BYREF
  BSTR v23[2]; // [rsp+78h] [rbp-160h] BYREF
  struct IQueryPlan *v24; // [rsp+88h] [rbp-150h] BYREF
  wchar_t Buffer[8]; // [rsp+90h] [rbp-148h] BYREF
  char v26; // [rsp+A1h] [rbp-137h]
  unsigned __int16 v27[120]; // [rsp+B0h] [rbp-128h] BYREF

  v24 = 0;
  Value = 0;
  v6 = QueryEngine::Compile(
         (QueryEngine *)v23,
         (const struct tagTableInfo *)(*((_QWORD *)this + 4) + 88LL),
         a2,
         &v24,
         &Value);
  v7 = v6;
  if ( v6 == -2147316576 || (unsigned int)(v6 + 2147220989) <= 1 )
  {
    bstrString = 0;
    v21 = 0;
    v22 = 0;
    v23[0] = 0;
    _itow_s(Value, Buffer, 0xCu, 10);
    v19 = 0;
    v8 = ((__int64 (__fastcall *)(struct IEventSubscription *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
           a3,
           &IID_IEventSubscription3,
           &v19);
    if ( v8 == -2147467262 )
    {
      v8 = 0;
      v19 = 0;
    }
    if ( v8 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x934u, 0x12u, v8);
    v9 = ((__int64 (__fastcall *)(struct IEventSubscription *, BSTR *))a3->lpVtbl->get_SubscriptionID)(a3, &bstrString);
    if ( v9 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x93Au, 0x12u, v9);
    v10 = ((__int64 (__fastcall *)(struct IEventSubscription *, BSTR *))a3->lpVtbl->get_SubscriptionName)(a3, v23);
    if ( v10 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x93Du, 0x12u, v10);
    if ( v19 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 392LL))(v19, &v21);
      if ( v11 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x942u, 0x12u, v11);
      v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 408LL))(v19, &v22);
      if ( v12 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x944u, 0x12u, v12);
      v14 = ConcatenateECID_PARTID_APPID_WSZ(bstrString, v21, v22, v13, v27);
      if ( v14 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x94Bu, 0x12u, v14);
      v15 = v27;
    }
    else
    {
      v15 = bstrString;
    }
    LogMessage_HR(0x12u, 0xC0001210, v7, 5u, v15, a2, Buffer, &a2[Value], v23[0]);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(bstrString);
    SysFreeString(v21);
    SysFreeString(v22);
    SysFreeString(v23[0]);
LABEL_25:
    if ( v7 < 0 )
      return (unsigned int)v7;
    goto LABEL_26;
  }
  if ( v6 < 0 )
  {
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x968u, 0x12u, v6);
    goto LABEL_25;
  }
LABEL_26:
  FrameQueryInterpreter::FrameQueryInterpreter(
    (FrameQueryInterpreter *)Buffer,
    *((struct ICallFrame **)this + 5),
    *((struct EventMethod **)this + 4));
  v16 = v24;
  v7 = (*(__int64 (__fastcall **)(struct IQueryPlan *, wchar_t *))(*(_QWORD *)v24 + 24LL))(v24, Buffer);
  (*(void (__fastcall **)(struct IQueryPlan *))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v7 >= 0 )
    return v26 == 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009e8c  push    rbx
0x180009e8e  push    rdi
0x180009e8f  push    r13
0x180009e91  push    r14
0x180009e93  push    r15
0x180009e95  sub     rsp, 1B0h
0x180009e9c  mov     rax, cs:__security_cookie
0x180009ea3  xor     rax, rsp
0x180009ea6  mov     [rsp+1D8h+var_38], rax
0x180009eae  mov     r14, r8
0x180009eb1  mov     r15, rdx
0x180009eb4  mov     r13, rcx
0x180009eb7  mov     [rsp+1D8h+var_150], 0
0x180009ec3  mov     [rsp+1D8h+Value], 0
0x180009ecb  mov     rdx, [rcx+20h]
0x180009ecf  add     rdx, 58h ; 'X'; struct tagTableInfo *
0x180009ed3  lea     rax, [rsp+1D8h+Value]
0x180009ed8  mov     [rsp+1D8h+var_1B8], rax; int *
0x180009edd  lea     r9, [rsp+1D8h+var_150]; struct IQueryPlan **
0x180009ee5  mov     r8, r15; unsigned __int16 *
0x180009ee8  lea     rcx, [rsp+1D8h+var_160]; this
0x180009eed  call    ?Compile@QueryEngine@@UEAAJPEBUtagTableInfo@@PEBGPEAPEAUIQueryPlan@@PEAH@Z; QueryEngine::Compile(tagTableInfo const *,ushort const *,IQueryPlan * *,int *)
0x180009ef2  mov     edi, eax
0x180009ef4  cmp     eax, 80028CA0h
0x180009ef9  jz      short loc_180009F2D
0x180009efb  lea     ecx, [rax+7FFBFDFDh]
0x180009f01  cmp     ecx, 1
0x180009f04  jbe     short loc_180009F2D
0x180009f06  test    eax, eax
0x180009f08  jns     loc_18000A165
0x180009f0e  mov     r8d, 12h; unsigned __int16
0x180009f14  mov     r9d, eax; int
0x180009f17  mov     edx, 968h; unsigned int
0x180009f1c  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009f23  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180009f28  jmp     loc_18000A161
0x180009f2d  mov     [rsp+1D8h+bstrString], 0
0x180009f36  mov     [rsp+1D8h+var_170], 0
0x180009f3f  mov     [rsp+1D8h+var_168], 0
0x180009f48  mov     [rsp+1D8h+var_160], 0
0x180009f51  mov     r9d, 0Ah; Radix
0x180009f57  lea     r8d, [r9+2]; BufferCount
0x180009f5b  lea     rdx, [rsp+1D8h+Buffer]; Buffer
0x180009f63  mov     ecx, [rsp+1D8h+Value]; Value
0x180009f67  call    cs:__imp__itow_s
0x180009f6d  mov     [rsp+1D8h+var_180], 0
0x180009f76  mov     rax, [r14]
0x180009f79  lea     r8, [rsp+1D8h+var_180]
0x180009f7e  lea     rdx, IID_IEventSubscription3
0x180009f85  mov     rcx, r14
0x180009f88  mov     rax, [rax]
0x180009f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f90  cmp     eax, 80004002h
0x180009f95  jnz     short loc_180009F9E
0x180009f97  xor     eax, eax
0x180009f99  mov     [rsp+1D8h+var_180], rax
0x180009f9e  mov     ebx, 12h
0x180009fa3  test    eax, eax
0x180009fa5  jns     short loc_180009FBF
0x180009fa7  mov     r8d, ebx; unsigned __int16
0x180009faa  mov     r9d, eax; int
0x180009fad  mov     edx, 934h; unsigned int
0x180009fb2  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009fb9  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180009fbe  nop
0x180009fbf  mov     rax, [r14]
0x180009fc2  lea     rdx, [rsp+1D8h+bstrString]
0x180009fc7  mov     rcx, r14
0x180009fca  mov     rax, [rax+38h]
0x180009fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd3  test    eax, eax
0x180009fd5  jns     short loc_180009FEE
0x180009fd7  mov     r8d, ebx; unsigned __int16
0x180009fda  mov     r9d, eax; int
0x180009fdd  mov     edx, 93Ah; unsigned int
0x180009fe2  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009fe9  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180009fee  mov     rax, [r14]
0x180009ff1  lea     rdx, [rsp+1D8h+var_160]
0x180009ff6  mov     rcx, r14
0x180009ff9  mov     rax, [rax+48h]
0x180009ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a002  test    eax, eax
0x18000a004  jns     short loc_18000A01D
0x18000a006  mov     r8d, ebx; unsigned __int16
0x18000a009  mov     r9d, eax; int
0x18000a00c  mov     edx, 93Dh; unsigned int
0x18000a011  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000a018  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a01d  mov     rcx, [rsp+1D8h+var_180]
0x18000a022  test    rcx, rcx
0x18000a025  jz      loc_18000A0D4
0x18000a02b  mov     rax, [rcx]
0x18000a02e  lea     rdx, [rsp+1D8h+var_170]
0x18000a033  mov     rax, [rax+188h]
0x18000a03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a03f  test    eax, eax
0x18000a041  jns     short loc_18000A05A
0x18000a043  mov     r8d, ebx; unsigned __int16
0x18000a046  mov     r9d, eax; int
0x18000a049  mov     edx, 942h; unsigned int
0x18000a04e  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000a055  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a05a  mov     rcx, [rsp+1D8h+var_180]
0x18000a05f  mov     rax, [rcx]
0x18000a062  lea     rdx, [rsp+1D8h+var_168]
0x18000a067  mov     rax, [rax+198h]
0x18000a06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a073  test    eax, eax
0x18000a075  jns     short loc_18000A08E
0x18000a077  mov     r8d, ebx; unsigned __int16
0x18000a07a  mov     r9d, eax; int
0x18000a07d  mov     edx, 944h; unsigned int
0x18000a082  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000a089  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a08e  lea     rax, [rsp+1D8h+var_128]
0x18000a096  mov     [rsp+1D8h+var_1B8], rax; unsigned __int16 *
0x18000a09b  mov     r8, [rsp+1D8h+var_168]; LPCOLESTR
0x18000a0a0  mov     rdx, [rsp+1D8h+var_170]; unsigned __int16 *
0x18000a0a5  mov     rcx, [rsp+1D8h+bstrString]; lpsz
0x18000a0aa  call    ?ConcatenateECID_PARTID_APPID_WSZ@@YAJPEAG00K0@Z; ConcatenateECID_PARTID_APPID_WSZ(ushort *,ushort *,ushort *,ulong,ushort *)
0x18000a0af  test    eax, eax
0x18000a0b1  jns     short loc_18000A0CA
0x18000a0b3  mov     r8d, ebx; unsigned __int16
0x18000a0b6  mov     r9d, eax; int
0x18000a0b9  mov     edx, 94Bh; unsigned int
0x18000a0be  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000a0c5  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000a0ca  lea     rdx, [rsp+1D8h+var_128]
0x18000a0d2  jmp     short loc_18000A0D9
0x18000a0d4  mov     rdx, [rsp+1D8h+bstrString]
0x18000a0d9  movsxd  rax, [rsp+1D8h+Value]
0x18000a0de  lea     rcx, [r15+rax*2]
0x18000a0e2  mov     rax, [rsp+1D8h+var_160]
0x18000a0e7  mov     [rsp+1D8h+var_198], rax
0x18000a0ec  mov     [rsp+1D8h+var_1A0], rcx
0x18000a0f1  lea     rax, [rsp+1D8h+Buffer]
0x18000a0f9  mov     [rsp+1D8h+var_1A8], rax
0x18000a0fe  mov     [rsp+1D8h+var_1B0], r15
0x18000a103  mov     [rsp+1D8h+var_1B8], rdx
0x18000a108  mov     r9d, 5; unsigned int
0x18000a10e  mov     r8d, edi; int
0x18000a111  mov     edx, 0C0001210h; unsigned int
0x18000a116  movzx   ecx, bx; unsigned __int16
0x18000a119  call    ?LogMessage_HR@@YAXGKJKZZ; LogMessage_HR(ushort,ulong,long,ulong,...)
0x18000a11e  nop
0x18000a11f  mov     rcx, [rsp+1D8h+var_180]
0x18000a124  test    rcx, rcx
0x18000a127  jz      short loc_18000A135
0x18000a129  mov     rax, [rcx]
0x18000a12c  mov     rax, [rax+10h]
0x18000a130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a135  mov     rcx, [rsp+1D8h+bstrString]; bstrString
0x18000a13a  call    cs:__imp_SysFreeString
0x18000a140  mov     rcx, [rsp+1D8h+var_170]; bstrString
0x18000a145  call    cs:__imp_SysFreeString
0x18000a14b  mov     rcx, [rsp+1D8h+var_168]; bstrString
0x18000a150  call    cs:__imp_SysFreeString
0x18000a156  mov     rcx, [rsp+1D8h+var_160]; bstrString
0x18000a15b  call    cs:__imp_SysFreeString
0x18000a161  test    edi, edi
0x18000a163  js      short loc_18000A1BC
0x18000a165  mov     r8, [r13+20h]; struct EventMethod *
0x18000a169  mov     rdx, [r13+28h]; struct ICallFrame *
0x18000a16d  lea     rcx, [rsp+1D8h+Buffer]; this
0x18000a175  call    ??0FrameQueryInterpreter@@QEAA@PEAUICallFrame@@AEAVEventMethod@@@Z; FrameQueryInterpreter::FrameQueryInterpreter(ICallFrame *,EventMethod &)
0x18000a17a  mov     rbx, [rsp+1D8h+var_150]
0x18000a182  mov     rax, [rbx]
0x18000a185  lea     rdx, [rsp+1D8h+Buffer]
0x18000a18d  mov     rcx, rbx
0x18000a190  mov     rax, [rax+18h]
0x18000a194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a199  mov     edi, eax
0x18000a19b  mov     rax, [rbx]
0x18000a19e  mov     rcx, rbx
0x18000a1a1  mov     rax, [rax+10h]
0x18000a1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1aa  test    edi, edi
0x18000a1ac  js      short loc_18000A1BC
0x18000a1ae  xor     edi, edi
0x18000a1b0  cmp     [rsp+1D8h+var_137], dil
0x18000a1b8  setz    dil
0x18000a1bc  mov     eax, edi
0x18000a1be  mov     rcx, [rsp+1D8h+var_38]
0x18000a1c6  xor     rcx, rsp; StackCookie
0x18000a1c9  call    __security_check_cookie
0x18000a1ce  add     rsp, 1B0h
0x18000a1d5  pop     r15
0x18000a1d7  pop     r14
0x18000a1d9  pop     r13
0x18000a1db  pop     rdi
0x18000a1dc  pop     rbx
0x18000a1dd  retn
0x180043857  push    rbp
0x180043859  sub     rsp, 50h
0x18004385d  mov     rbp, rdx
0x180043860  mov     rcx, [rbp+58h]
0x180043864  test    rcx, rcx
0x180043867  jz      short loc_180043876
0x180043869  mov     rax, [rcx]
0x18004386c  mov     rax, [rax+10h]
0x180043870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043875  nop
0x180043876  mov     rcx, [rbp+60h]; bstrString
0x18004387a  call    cs:__imp_SysFreeString
0x180043880  mov     rcx, [rbp+68h]; bstrString
0x180043884  call    cs:__imp_SysFreeString
0x18004388a  mov     rcx, [rbp+70h]; bstrString
0x18004388e  call    cs:__imp_SysFreeString
0x180043894  mov     rcx, [rbp+78h]; bstrString
0x180043898  call    cs:__imp_SysFreeString
0x18004389e  nop
0x18004389f  add     rsp, 50h
0x1800438a3  pop     rbp
0x1800438a4  retn
```
