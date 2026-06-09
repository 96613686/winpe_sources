# CPnpxPairingHandler::Initialize(IFunctionInstance *,_GUID const &,void * *)

- ea: `0x18000ded0`
- end: `0x18000e0fc`
- name: `?Initialize@CPnpxPairingHandler@@UEAAJPEAUIFunctionInstance@@AEBU_GUID@@PEAPEAX@Z`
- size: `556`
- prototype: `__int64 __fastcall(CPnpxPairingHandler *__hidden this, struct IFunctionInstance *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000bce4`
- `0x18000bd30`
- `0x18000ded0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000df9b`
- `KERNEL32!GetLastError` at `0x18000df9b`
- `KERNEL32!CreateEventW` at `0x18000df8c`
- `KERNEL32!CreateEventW` at `0x18000df8c`
- `ole32!CoCreateInstance` at `0x18000dfde`
- `ole32!CoCreateInstance` at `0x18000dfde`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::Initialize(
        CPnpxPairingHandler *this,
        struct IFunctionInstance *a2,
        const struct _GUID *a3,
        void **a4)
{
  _BYTE *v8; // rcx
  unsigned int v9; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  bool v15; // cf
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  ppv = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
LABEL_25:
    v13 = *((_QWORD *)this + 12);
    if ( v13 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 16LL))(*((_QWORD *)this + 12));
      *((_QWORD *)this + 12) = 0;
      v8 = WPP_GLOBAL_Control;
    }
    v14 = 0;
    v15 = v8[25] < 2u;
    goto LABEL_30;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    goto LABEL_25;
  }
  if ( *(_QWORD *)&GUID_0db7eb30_afb5_4173_909b_1d971772f5da.Data1 != *(_QWORD *)&a3->Data1
    || *(_QWORD *)GUID_0db7eb30_afb5_4173_909b_1d971772f5da.Data4 != *(_QWORD *)a3->Data4 )
  {
    v9 = -2147467262;
    goto LABEL_25;
  }
  if ( *((_QWORD *)this + 10) )
  {
    v9 = -2147023649;
    goto LABEL_25;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 14) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 )
      goto LABEL_16;
  }
  v9 = CoCreateInstance(
         (const IID *const)&SID_PNPXAssociation,
         0,
         0x17u,
         &GUID_4c81ed02_1b04_43f2_a451_69966cbcd1c2,
         &ppv);
  if ( v9
    || (v9 = (*(__int64 (__fastcall **)(LPVOID, struct IFunctionInstance *, GUID *, char *))(*(_QWORD *)ppv + 24LL))(
               ppv,
               a2,
               &GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77,
               (char *)this + 96)) != 0 )
  {
LABEL_16:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( *((struct IFunctionInstance **)this + 10) != a2 )
  {
    ((void (__fastcall *)(struct IFunctionInstance *))a2->lpVtbl->AddRef)(a2);
    v12 = *((_QWORD *)this + 10);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 10) = a2;
  }
  (*(void (__fastcall **)(CPnpxPairingHandler *))(*(_QWORD *)this + 8LL))(this);
  *a4 = (void *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  v8 = WPP_GLOBAL_Control;
  v14 = 0;
  v15 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
LABEL_30:
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v14) = !v15;
    if ( v14 )
      WPP_SF_sqd(*((_QWORD *)v8 + 2), 15, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v9;
}

```

## disassembly

```asm
0x18000ded0  mov     [rsp+arg_0], rbx
0x18000ded5  mov     [rsp+arg_10], rsi
0x18000deda  push    rdi
0x18000dedb  push    r14
0x18000dedd  push    r15
0x18000dedf  sub     rsp, 30h
0x18000dee3  mov     r14, r9
0x18000dee6  mov     rbx, r8
0x18000dee9  mov     rsi, rdx
0x18000deec  mov     rdi, rcx
0x18000deef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000def6  lea     r15, WPP_GLOBAL_Control
0x18000defd  cmp     rcx, r15
0x18000df00  jz      short loc_18000DF29
0x18000df02  cmp     byte ptr [rcx+19h], 4
0x18000df06  jb      short loc_18000DF29
0x18000df08  mov     rcx, [rcx+10h]
0x18000df0c  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000df13  mov     edx, 0Eh
0x18000df18  mov     [rsp+48h+ppv], rdi
0x18000df1d  call    WPP_SF_sq
0x18000df22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df29  mov     [rsp+48h+arg_8], 0
0x18000df32  test    rsi, rsi
0x18000df35  jnz     short loc_18000DF41
0x18000df37  mov     ebx, 80070057h
0x18000df3c  jmp     loc_18000E06D
0x18000df41  test    r14, r14
0x18000df44  jnz     short loc_18000DF50
0x18000df46  mov     ebx, 80004003h
0x18000df4b  jmp     loc_18000E06D
0x18000df50  mov     rax, qword ptr cs:_GUID_0db7eb30_afb5_4173_909b_1d971772f5da.Data1
0x18000df57  cmp     rax, [rbx]
0x18000df5a  jnz     loc_18000E068
0x18000df60  mov     rax, qword ptr cs:_GUID_0db7eb30_afb5_4173_909b_1d971772f5da.Data4
0x18000df67  cmp     rax, [rbx+8]
0x18000df6b  jnz     loc_18000E068
0x18000df71  cmp     qword ptr [rdi+50h], 0
0x18000df76  jz      short loc_18000DF82
0x18000df78  mov     ebx, 800704DFh
0x18000df7d  jmp     loc_18000E06D
0x18000df82  xor     r9d, r9d; lpName
0x18000df85  xor     r8d, r8d; bInitialState
0x18000df88  xor     edx, edx; bManualReset
0x18000df8a  xor     ecx, ecx; lpEventAttributes
0x18000df8c  call    cs:__imp_CreateEventW
0x18000df92  mov     [rdi+70h], rax
0x18000df96  test    rax, rax
0x18000df99  jnz     short loc_18000DFC0
0x18000df9b  call    cs:__imp_GetLastError
0x18000dfa1  mov     ebx, eax
0x18000dfa3  test    eax, eax
0x18000dfa5  jle     short loc_18000DFB0
0x18000dfa7  movzx   ebx, ax
0x18000dfaa  or      ebx, 80070000h
0x18000dfb0  test    ebx, ebx
0x18000dfb2  jz      short loc_18000DFC0
0x18000dfb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfbb  jmp     loc_18000E06D
0x18000dfc0  xor     edx, edx; pUnkOuter
0x18000dfc2  lea     rax, [rsp+48h+arg_8]
0x18000dfc7  lea     r9, _GUID_4c81ed02_1b04_43f2_a451_69966cbcd1c2; riid
0x18000dfce  mov     [rsp+48h+ppv], rax; ppv
0x18000dfd3  lea     rcx, SID_PNPXAssociation; rclsid
0x18000dfda  lea     r8d, [rdx+17h]; dwClsContext
0x18000dfde  call    cs:__imp_CoCreateInstance
0x18000dfe4  mov     ebx, eax
0x18000dfe6  test    eax, eax
0x18000dfe8  jnz     short loc_18000DFB4
0x18000dfea  mov     rcx, [rsp+48h+arg_8]
0x18000dfef  lea     r9, [rdi+60h]
0x18000dff3  lea     r8, _GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77
0x18000dffa  mov     rdx, rsi
0x18000dffd  mov     rax, [rcx]
0x18000e000  mov     rax, [rax+18h]
0x18000e004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e009  mov     ebx, eax
0x18000e00b  test    eax, eax
0x18000e00d  jnz     short loc_18000DFB4
0x18000e00f  cmp     [rdi+50h], rsi
0x18000e013  jz      short loc_18000E03D
0x18000e015  mov     rax, [rsi]
0x18000e018  mov     rcx, rsi
0x18000e01b  mov     rax, [rax+8]
0x18000e01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e024  mov     rcx, [rdi+50h]
0x18000e028  test    rcx, rcx
0x18000e02b  jz      short loc_18000E039
0x18000e02d  mov     rax, [rcx]
0x18000e030  mov     rax, [rax+10h]
0x18000e034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e039  mov     [rdi+50h], rsi
0x18000e03d  mov     rax, [rdi]
0x18000e040  mov     rcx, rdi
0x18000e043  mov     rax, [rax+8]
0x18000e047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e04c  mov     rax, rdi
0x18000e04f  lea     rdx, [rdi+8]
0x18000e053  neg     rax
0x18000e056  sbb     rcx, rcx
0x18000e059  and     rcx, rdx
0x18000e05c  mov     [r14], rcx
0x18000e05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e066  jmp     short loc_18000E098
0x18000e068  mov     ebx, 80004002h
0x18000e06d  mov     rdx, [rdi+60h]
0x18000e071  test    rdx, rdx
0x18000e074  jz      short loc_18000E094
0x18000e076  mov     rax, [rdx]
0x18000e079  mov     rcx, rdx
0x18000e07c  mov     rax, [rax+10h]
0x18000e080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e085  mov     qword ptr [rdi+60h], 0
0x18000e08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e094  test    ebx, ebx
0x18000e096  jnz     short loc_18000E0A0
0x18000e098  xor     eax, eax
0x18000e09a  cmp     byte ptr [rcx+19h], 4
0x18000e09e  jmp     short loc_18000E0A6
0x18000e0a0  xor     eax, eax
0x18000e0a2  cmp     byte ptr [rcx+19h], 2
0x18000e0a6  setnb   al
0x18000e0a9  cmp     rcx, r15
0x18000e0ac  jz      short loc_18000E0D0
0x18000e0ae  test    eax, eax
0x18000e0b0  jz      short loc_18000E0D0
0x18000e0b2  mov     rcx, [rcx+10h]
0x18000e0b6  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e0bd  mov     edx, 0Fh
0x18000e0c2  mov     [rsp+48h+var_20], ebx
0x18000e0c6  mov     [rsp+48h+ppv], rdi
0x18000e0cb  call    WPP_SF_sqd
0x18000e0d0  mov     rcx, [rsp+48h+arg_8]
0x18000e0d5  test    rcx, rcx
0x18000e0d8  jz      short loc_18000E0E6
0x18000e0da  mov     rax, [rcx]
0x18000e0dd  mov     rax, [rax+10h]
0x18000e0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e6  mov     rsi, [rsp+48h+arg_10]
0x18000e0eb  mov     eax, ebx
0x18000e0ed  mov     rbx, [rsp+48h+arg_0]
0x18000e0f2  add     rsp, 30h
0x18000e0f6  pop     r15
0x18000e0f8  pop     r14
0x18000e0fa  pop     rdi
0x18000e0fb  retn
```
