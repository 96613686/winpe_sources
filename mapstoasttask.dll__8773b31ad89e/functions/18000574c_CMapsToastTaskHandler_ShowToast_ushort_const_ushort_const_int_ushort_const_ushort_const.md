# CMapsToastTaskHandler::ShowToast(ushort const *,ushort const *,int,ushort const *,ushort const *)

- ea: `0x18000574c`
- end: `0x180005c24`
- name: `?ShowToast@CMapsToastTaskHandler@@AEAAJPEBG0H00@Z`
- size: `1240`
- prototype: `__int64 __fastcall(CMapsToastTaskHandler *this, const unsigned __int16 *, const unsigned __int16 *, char, PCWSTR, const unsigned __int16 *sourceString)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x1800015b0`
- `0x180002ed4`
- `0x180004adc`
- `0x18000574c`
- `0x18000a010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180005815`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000596e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180005815`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000596e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800057bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005841`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800057bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005841`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005a9c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800057f9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000587f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800057f9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000587f`

## string_xrefs

- `0x18000580c`: `CMapsToastTaskHandler::ShowToast`
- `0x180005965`: `CMapsToastTaskHandler::ShowToast`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ShowToast(
        CMapsToastTaskHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        PCWSTR a5,
        const unsigned __int16 *sourceString)
{
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int ActivationFactory; // eax
  int v14; // r8d
  unsigned int v15; // ebx
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  __int64 v19; // rbx
  __int64 v20; // r14
  __int64 v21; // rcx
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdx
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  int v28; // r8d
  __int64 *v29; // rbx
  __int64 v30; // r14
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  __int64 v34; // rdx
  unsigned int v35; // r8d
  __int64 *v36; // rbx
  __int64 v37; // r14
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  struct Windows::Data::Xml::Dom::IXmlDocument *v41; // rcx
  __int64 *v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 *v48; // [rsp+20h] [rbp-59h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64 **); // [rsp+28h] [rbp-51h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v50; // [rsp+30h] [rbp-49h] BYREF
  __int64 v51; // [rsp+38h] [rbp-41h] BYREF
  __int64 v52; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v53[2]; // [rsp+48h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-21h] BYREF
  HSTRING string; // [rsp+70h] [rbp-9h] BYREF

  v53[0] = 0;
  v53[1] = 0;
  v52 = 0;
  v51 = 0;
  v49 = 0;
  v48 = 0;
  v50 = 0;
  string = 0;
  v10 = WindowsCreateStringReference(
          L"Windows.UI.Notifications.ToastNotificationManager",
          0x31u,
          &hstringHeader,
          &string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, v53);
  if ( ActivationFactory < 0 )
  {
    v14 = 337;
LABEL_4:
    v15 = ZTraceReportPropagation(ActivationFactory, "CMapsToastTaskHandler::ShowToast", v14, this);
    goto LABEL_40;
  }
  string = 0;
  v16 = WindowsCreateStringReference(L"Windows.UI.Notifications.ToastNotification", 0x2Au, &hstringHeader, &string);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v51);
  if ( ActivationFactory < 0 )
  {
    v14 = 341;
    goto LABEL_4;
  }
  ActivationFactory = CMapsToastTaskHandler::CreateToastXml(this, a2, a3, &v50);
  if ( ActivationFactory < 0 )
  {
    v14 = 344;
    goto LABEL_4;
  }
  v19 = v53[0];
  v20 = *(_QWORD *)v53[0];
  v21 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  string = 0;
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( sourceString[v23] );
  if ( v23 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, 0);
    __debugbreak();
  }
  if ( (int)v23 + 1 < (unsigned int)v23 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, 0);
    __debugbreak();
  }
  v24 = WindowsCreateStringReference(sourceString, v23, &hstringHeader, &string);
  if ( v24 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
    __debugbreak();
  }
  v27 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(v20 + 56))(v19, string, &v52);
  if ( v27 < 0 )
  {
    v28 = 347;
LABEL_19:
    v15 = ZTraceReportPropagation(v27, "CMapsToastTaskHandler::ShowToast", v28, this);
    goto LABEL_40;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD))(*(_QWORD *)v51 + 48LL))(
          v51,
          v50,
          &v49);
  if ( v27 < 0 )
  {
    v28 = 348;
    goto LABEL_19;
  }
  v27 = (**v49)(v49, &GUID_9dfb9fd1_143a_490e_90bf_b9fba7132de7, &v48);
  if ( v27 < 0 )
  {
    v28 = 351;
    goto LABEL_19;
  }
  v29 = v48;
  v30 = *v48;
  string = 0;
  v31 = WindowsCreateStringReference(L"MSMapsGroup", 0xBu, &hstringHeader, &string);
  if ( v31 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
    __debugbreak();
  }
  v27 = (*(__int64 (__fastcall **)(__int64 *, HSTRING))(v30 + 64))(v29, string);
  if ( v27 < 0 )
  {
    v28 = 352;
    goto LABEL_19;
  }
  if ( a5 )
  {
    v36 = v48;
    v37 = *v48;
    string = 0;
    do
      ++v22;
    while ( a5[v22] );
    if ( v22 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v34, v35);
      __debugbreak();
    }
    if ( (int)v22 + 1 < (unsigned int)v22 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v34, v35);
      __debugbreak();
    }
    v38 = WindowsCreateStringReference(a5, v22, &hstringHeader, &string);
    if ( v38 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
      JUMPOUT(0x180005C23LL);
    }
    v27 = (*(__int64 (__fastcall **)(__int64 *, HSTRING))(v37 + 48))(v36, string);
    if ( v27 < 0 )
    {
      v28 = 355;
      goto LABEL_19;
    }
  }
  LOBYTE(v34) = a4;
  v27 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v48 + 80))(v48, v34);
  if ( v27 < 0 )
  {
    v28 = 357;
    goto LABEL_19;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 **)))(*(_QWORD *)v52 + 48LL))(
          v52,
          v49);
  if ( v27 < 0 )
  {
    v28 = 360;
    goto LABEL_19;
  }
  v15 = 0;
LABEL_40:
  v41 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
  }
  v43 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v43)[2])(v43);
  }
  v44 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v53[0];
  if ( v53[0] )
  {
    v53[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return v15;
}

```

## disassembly

```asm
0x18000574c  push    rbp
0x18000574e  push    rbx
0x18000574f  push    rsi
0x180005750  push    rdi
0x180005751  push    r12
0x180005753  push    r13
0x180005755  push    r14
0x180005757  push    r15
0x180005759  lea     rbp, [rsp-0Fh]
0x18000575e  sub     rsp, 88h
0x180005765  mov     rax, cs:__security_cookie
0x18000576c  xor     rax, rsp
0x18000576f  mov     [rbp+47h+var_48], rax
0x180005773  mov     r13d, r9d
0x180005776  mov     r14, r8
0x180005779  mov     rsi, rdx
0x18000577c  mov     rdi, rcx
0x18000577f  mov     r12, [rbp+47h+arg_20]
0x180005783  mov     r15, [rbp+47h+sourceString]
0x180005787  xor     ebx, ebx
0x180005789  mov     [rbp+47h+var_78], rbx
0x18000578d  mov     [rbp+47h+var_70], rbx
0x180005791  mov     [rbp+47h+var_80], rbx
0x180005795  mov     [rbp+47h+var_88], rbx
0x180005799  mov     [rbp+47h+var_98], rbx
0x18000579d  mov     [rbp+47h+var_A0], rbx
0x1800057a1  mov     [rbp+47h+var_90], rbx
0x1800057a5  mov     [rbp+47h+string], rbx
0x1800057a9  lea     r9, [rbp+47h+string]; string
0x1800057ad  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x1800057b1  lea     edx, [rbx+31h]; length
0x1800057b4  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x1800057bb  call    cs:__imp_WindowsCreateStringReference
0x1800057c1  test    eax, eax
0x1800057c3  js      loc_180005BE6
0x1800057c9  mov     rbx, [rbp+47h+string]
0x1800057cd  mov     rcx, [rbp+47h+var_78]
0x1800057d1  test    rcx, rcx
0x1800057d4  jz      short loc_1800057EB
0x1800057d6  mov     [rbp+47h+var_78], 0
0x1800057de  mov     rax, [rcx]
0x1800057e1  mov     rax, [rax+10h]
0x1800057e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ea  nop
0x1800057eb  lea     r8, [rbp+47h+var_78]
0x1800057ef  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x1800057f6  mov     rcx, rbx
0x1800057f9  call    cs:__imp_RoGetActivationFactory
0x1800057ff  test    eax, eax
0x180005801  jns     short loc_180005825
0x180005803  mov     r8d, 151h
0x180005809  mov     r9, rdi
0x18000580c  lea     rdx, aCmapstoasttask_4; "CMapsToastTaskHandler::ShowToast"
0x180005813  mov     ecx, eax
0x180005815  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000581b  mov     ebx, eax
0x18000581d  xor     r15d, r15d
0x180005820  jmp     loc_180005B12
0x180005825  mov     [rbp+47h+string], 0
0x18000582d  lea     r9, [rbp+47h+string]; string
0x180005831  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x180005835  mov     edx, 2Ah ; '*'; length
0x18000583a  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotification@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x180005841  call    cs:__imp_WindowsCreateStringReference
0x180005847  test    eax, eax
0x180005849  js      loc_180005BEE
0x18000584f  mov     rbx, [rbp+47h+string]
0x180005853  mov     rcx, [rbp+47h+var_88]
0x180005857  test    rcx, rcx
0x18000585a  jz      short loc_180005871
0x18000585c  mov     [rbp+47h+var_88], 0
0x180005864  mov     rax, [rcx]
0x180005867  mov     rax, [rax+10h]
0x18000586b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005870  nop
0x180005871  lea     r8, [rbp+47h+var_88]
0x180005875  lea     rdx, _GUID_04124b20_82c6_4229_b109_fd9ed4662b53
0x18000587c  mov     rcx, rbx
0x18000587f  call    cs:__imp_RoGetActivationFactory
0x180005885  test    eax, eax
0x180005887  jns     short loc_180005894
0x180005889  mov     r8d, 155h
0x18000588f  jmp     loc_180005809
0x180005894  mov     rcx, [rbp+47h+var_90]
0x180005898  test    rcx, rcx
0x18000589b  jz      short loc_1800058B2
0x18000589d  mov     [rbp+47h+var_90], 0
0x1800058a5  mov     rax, [rcx]
0x1800058a8  mov     rax, [rax+10h]
0x1800058ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b1  nop
0x1800058b2  lea     r9, [rbp+47h+var_90]; struct Windows::Data::Xml::Dom::IXmlDocument **
0x1800058b6  mov     r8, r14; unsigned __int16 *
0x1800058b9  mov     rdx, rsi; unsigned __int16 *
0x1800058bc  mov     rcx, rdi; this
0x1800058bf  call    ?CreateToastXml@CMapsToastTaskHandler@@AEAAJPEBG0PEAPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; CMapsToastTaskHandler::CreateToastXml(ushort const *,ushort const *,Windows::Data::Xml::Dom::IXmlDocument * *)
0x1800058c4  xor     r8d, r8d
0x1800058c7  test    eax, eax
0x1800058c9  jns     short loc_1800058D6
0x1800058cb  mov     r8d, 158h
0x1800058d1  jmp     loc_180005809
0x1800058d6  mov     rbx, [rbp+47h+var_78]
0x1800058da  mov     r14, [rbx]
0x1800058dd  mov     rcx, [rbp+47h+var_80]
0x1800058e1  test    rcx, rcx
0x1800058e4  jz      short loc_1800058F9
0x1800058e6  mov     [rbp+47h+var_80], r8
0x1800058ea  mov     rax, [rcx]
0x1800058ed  mov     rax, [rax+10h]
0x1800058f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f6  xor     r8d, r8d; unsigned int
0x1800058f9  mov     [rbp+47h+string], r8
0x1800058fd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005901  mov     rdx, rsi
0x180005904  inc     rdx; int
0x180005907  cmp     [r15+rdx*2], r8w
0x18000590c  jnz     short loc_180005904
0x18000590e  mov     eax, 0FFFFFFFFh
0x180005913  cmp     rdx, rax
0x180005916  ja      loc_180005BDB
0x18000591c  lea     eax, [rdx+1]
0x18000591f  cmp     eax, edx
0x180005921  jb      loc_180005BF6
0x180005927  lea     r9, [rbp+47h+string]; string
0x18000592b  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18000592f  mov     rcx, r15; sourceString
0x180005932  call    cs:__imp_WindowsCreateStringReference
0x180005938  xor     r15d, r15d
0x18000593b  test    eax, eax
0x18000593d  js      loc_180005C01
0x180005943  lea     r8, [rbp+47h+var_80]
0x180005947  mov     rdx, [rbp+47h+string]
0x18000594b  mov     rcx, rbx
0x18000594e  mov     rax, [r14+38h]
0x180005952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005957  nop
0x180005958  test    eax, eax
0x18000595a  jns     short loc_18000597B
0x18000595c  mov     r8d, 15Bh
0x180005962  mov     r9, rdi
0x180005965  lea     rdx, aCmapstoasttask_4; "CMapsToastTaskHandler::ShowToast"
0x18000596c  mov     ecx, eax
0x18000596e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180005974  mov     ebx, eax
0x180005976  jmp     loc_180005B12
0x18000597b  mov     rbx, [rbp+47h+var_88]
0x18000597f  mov     rax, [rbx]
0x180005982  mov     r14, [rax+30h]
0x180005986  mov     rdx, [rbp+47h+var_98]
0x18000598a  test    rdx, rdx
0x18000598d  jz      short loc_1800059A3
0x18000598f  mov     [rbp+47h+var_98], r15
0x180005993  mov     rcx, [rdx]
0x180005996  mov     rax, [rcx+10h]
0x18000599a  mov     rcx, rdx
0x18000599d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a2  nop
0x1800059a3  lea     r8, [rbp+47h+var_98]
0x1800059a7  mov     rdx, [rbp+47h+var_90]
0x1800059ab  mov     rcx, rbx
0x1800059ae  mov     rax, r14
0x1800059b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b6  test    eax, eax
0x1800059b8  jns     short loc_1800059C2
0x1800059ba  mov     r8d, 15Ch
0x1800059c0  jmp     short loc_180005962
0x1800059c2  mov     rbx, [rbp+47h+var_98]
0x1800059c6  mov     rax, [rbx]
0x1800059c9  mov     r14, [rax]
0x1800059cc  mov     rdx, [rbp+47h+var_A0]
0x1800059d0  test    rdx, rdx
0x1800059d3  jz      short loc_1800059E9
0x1800059d5  mov     [rbp+47h+var_A0], r15
0x1800059d9  mov     rcx, [rdx]
0x1800059dc  mov     rax, [rcx+10h]
0x1800059e0  mov     rcx, rdx
0x1800059e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e8  nop
0x1800059e9  lea     r8, [rbp+47h+var_A0]
0x1800059ed  lea     rdx, _GUID_9dfb9fd1_143a_490e_90bf_b9fba7132de7
0x1800059f4  mov     rcx, rbx
0x1800059f7  mov     rax, r14
0x1800059fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ff  nop
0x180005a00  test    eax, eax
0x180005a02  jns     short loc_180005A0F
0x180005a04  mov     r8d, 15Fh
0x180005a0a  jmp     loc_180005962
0x180005a0f  mov     rbx, [rbp+47h+var_A0]
0x180005a13  mov     r14, [rbx]
0x180005a16  mov     [rbp+47h+string], r15
0x180005a1a  lea     r9, [rbp+47h+string]; string
0x180005a1e  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x180005a22  mov     edx, 0Bh; length
0x180005a27  lea     rcx, aMsmapsgroup; "MSMapsGroup"
0x180005a2e  call    cs:__imp_WindowsCreateStringReference
0x180005a34  test    eax, eax
0x180005a36  js      loc_180005C09
0x180005a3c  mov     rdx, [rbp+47h+string]
0x180005a40  mov     rcx, rbx
0x180005a43  mov     rax, [r14+40h]
0x180005a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a4c  nop
0x180005a4d  test    eax, eax
0x180005a4f  jns     short loc_180005A5C
0x180005a51  mov     r8d, 160h
0x180005a57  jmp     loc_180005962
0x180005a5c  test    r12, r12
0x180005a5f  jz      short loc_180005ACA
0x180005a61  mov     rbx, [rbp+47h+var_A0]
0x180005a65  mov     r14, [rbx]
0x180005a68  mov     [rbp+47h+string], r15
0x180005a6c  inc     rsi
0x180005a6f  cmp     [r12+rsi*2], r15w
0x180005a74  jnz     short loc_180005A6C
0x180005a76  mov     eax, 0FFFFFFFFh
0x180005a7b  cmp     rsi, rax
0x180005a7e  ja      loc_180005BD0
0x180005a84  lea     eax, [rsi+1]
0x180005a87  cmp     eax, esi
0x180005a89  jb      loc_180005C11
0x180005a8f  lea     r9, [rbp+47h+string]; string
0x180005a93  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x180005a97  mov     edx, esi; length
0x180005a99  mov     rcx, r12; sourceString
0x180005a9c  call    cs:__imp_WindowsCreateStringReference
0x180005aa2  test    eax, eax
0x180005aa4  js      loc_180005C1C
0x180005aaa  mov     rdx, [rbp+47h+string]
0x180005aae  mov     rcx, rbx
0x180005ab1  mov     rax, [r14+30h]
0x180005ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aba  nop
0x180005abb  test    eax, eax
0x180005abd  jns     short loc_180005ACA
0x180005abf  mov     r8d, 163h
0x180005ac5  jmp     loc_180005962
0x180005aca  mov     rcx, [rbp+47h+var_A0]
0x180005ace  mov     rax, [rcx]
0x180005ad1  mov     dl, r13b
0x180005ad4  mov     rax, [rax+50h]
0x180005ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005add  test    eax, eax
0x180005adf  jns     short loc_180005AEC
0x180005ae1  mov     r8d, 165h
0x180005ae7  jmp     loc_180005962
0x180005aec  mov     rcx, [rbp+47h+var_80]
0x180005af0  mov     rax, [rcx]
0x180005af3  mov     rdx, [rbp+47h+var_98]
0x180005af7  mov     rax, [rax+30h]
0x180005afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b00  test    eax, eax
0x180005b02  jns     short loc_180005B0F
0x180005b04  mov     r8d, 168h
0x180005b0a  jmp     loc_180005962
0x180005b0f  mov     ebx, r15d
0x180005b12  mov     rcx, [rbp+47h+var_90]
0x180005b16  test    rcx, rcx
0x180005b19  jz      short loc_180005B2C
0x180005b1b  mov     [rbp+47h+var_90], r15
0x180005b1f  mov     rax, [rcx]
0x180005b22  mov     rax, [rax+10h]
0x180005b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2b  nop
0x180005b2c  mov     rcx, [rbp+47h+var_A0]
0x180005b30  test    rcx, rcx
0x180005b33  jz      short loc_180005B46
0x180005b35  mov     [rbp+47h+var_A0], r15
0x180005b39  mov     rax, [rcx]
0x180005b3c  mov     rax, [rax+10h]
0x180005b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b45  nop
0x180005b46  mov     rcx, [rbp+47h+var_98]
0x180005b4a  test    rcx, rcx
0x180005b4d  jz      short loc_180005B60
0x180005b4f  mov     [rbp+47h+var_98], r15
0x180005b53  mov     rax, [rcx]
0x180005b56  mov     rax, [rax+10h]
0x180005b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b5f  nop
0x180005b60  mov     rcx, [rbp+47h+var_88]
0x180005b64  test    rcx, rcx
0x180005b67  jz      short loc_180005B7A
0x180005b69  mov     [rbp+47h+var_88], r15
0x180005b6d  mov     rax, [rcx]
0x180005b70  mov     rax, [rax+10h]
0x180005b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b79  nop
0x180005b7a  mov     rcx, [rbp+47h+var_80]
0x180005b7e  test    rcx, rcx
0x180005b81  jz      short loc_180005B94
0x180005b83  mov     [rbp+47h+var_80], r15
0x180005b87  mov     rax, [rcx]
0x180005b8a  mov     rax, [rax+10h]
0x180005b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b93  nop
0x180005b94  mov     rcx, [rbp+47h+var_78]
0x180005b98  test    rcx, rcx
0x180005b9b  jz      short loc_180005BAE
0x180005b9d  mov     [rbp+47h+var_78], r15
  ... truncated ...
```
