# CMapsToastTaskHandler::SetTemplateText(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,uint)

- ea: `0x1800053e0`
- end: `0x180005744`
- name: `?SetTemplateText@CMapsToastTaskHandler@@AEAAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBGI@Z`
- size: `868`
- prototype: `__int64 __fastcall(CMapsToastTaskHandler *this, struct Windows::Data::Xml::Dom::IXmlDocument *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002ed4`

## callees

- `0x1800015b0`
- `0x180004adc`
- `0x1800053e0`
- `0x180005d40`
- `0x18000a010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180005465`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180005465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800054f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800054f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005583`

## string_xrefs

- `0x18000545c`: `CMapsToastTaskHandler::SetTemplateText`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::SetTemplateText(
        CMapsToastTaskHandler *this,
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int v8; // eax
  int v9; // r8d
  unsigned int v10; // ebx
  unsigned int v11; // r8d
  _QWORD *v12; // rsi
  __int64 v13; // r15
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rdx
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // edx
  unsigned int v20; // r8d
  __int64 (__fastcall **v21)(_QWORD, _QWORD, _QWORD); // rsi
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, __int64, __int64 *); // rsi
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  __int64 v34; // [rsp+20h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-D8h] BYREF
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v38; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR sourceString[264]; // [rsp+70h] [rbp-90h] BYREF

  v38 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v37 = 0;
  v8 = (**(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, _QWORD **))a2)(
         a2,
         &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b,
         &v38);
  if ( v8 < 0 )
  {
    v9 = 380;
LABEL_3:
    v10 = ZTraceReportPropagation(v8, "CMapsToastTaskHandler::SetTemplateText", v9, this);
    goto LABEL_27;
  }
  v8 = StringCchPrintfW(sourceString, 0x104u, L"/toast/visual/binding/text[number(@id) = '%d']", a4);
  if ( v8 < 0 )
  {
    v9 = 383;
    goto LABEL_3;
  }
  v12 = v38;
  v13 = *v38;
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( sourceString[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v15, v11);
    __debugbreak();
  }
  if ( (int)v15 + 1 < (unsigned int)v15 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v15, v11);
    __debugbreak();
  }
  v16 = WindowsCreateStringReference(sourceString, v15, &hstringHeader, string);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    __debugbreak();
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v13 + 48))(v12, string[0], &v36);
  if ( v8 < 0 )
  {
    v9 = 386;
    goto LABEL_3;
  }
  v21 = *(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
  string[0] = 0;
  do
    ++v14;
  while ( a3[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v20);
    __debugbreak();
  }
  if ( (int)v14 + 1 < (unsigned int)v14 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v20);
    __debugbreak();
  }
  v22 = WindowsCreateStringReference(a3, v14, &hstringHeader, string);
  if ( v22 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
    JUMPOUT(0x180005743LL);
  }
  v8 = ((__int64 (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *, HSTRING, _QWORD))v21)[11](
         a2,
         string[0],
         &v35);
  if ( v8 < 0 )
  {
    v9 = 387;
    goto LABEL_3;
  }
  v8 = (**v35)(v35, &GUID_1c741d59_2122_47d5_a856_83f3d4214875, &v34);
  if ( v8 < 0 )
  {
    v9 = 388;
    goto LABEL_3;
  }
  v25 = v36;
  v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 176LL);
  v27 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v8 = v26(v25, v34, &v37);
  if ( v8 < 0 )
  {
    v9 = 389;
    goto LABEL_3;
  }
  v10 = 0;
LABEL_27:
  v28 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v35;
  if ( v35 )
  {
    v35 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v30)[2])(v30);
  }
  v31 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
  }
  return v10;
}

```

## disassembly

```asm
0x1800053e0  push    rbp
0x1800053e2  push    rbx
0x1800053e3  push    rsi
0x1800053e4  push    rdi
0x1800053e5  push    r12
0x1800053e7  push    r13
0x1800053e9  push    r14
0x1800053eb  push    r15
0x1800053ed  lea     rbp, [rsp-198h]
0x1800053f5  sub     rsp, 298h
0x1800053fc  mov     rax, cs:__security_cookie
0x180005403  xor     rax, rsp
0x180005406  mov     [rbp+1D0h+var_50], rax
0x18000540d  mov     ebx, r9d
0x180005410  mov     r12, r8
0x180005413  mov     r14, rdx
0x180005416  mov     rdi, rcx
0x180005419  xor     r13d, r13d
0x18000541c  mov     [rsp+2D0h+var_290], r13
0x180005421  mov     [rsp+2D0h+var_2A0], r13
0x180005426  mov     [rsp+2D0h+var_2A8], r13
0x18000542b  mov     [rsp+2D0h+var_2B0], r13
0x180005430  mov     [rsp+2D0h+var_298], r13
0x180005435  mov     rax, [rdx]
0x180005438  lea     r8, [rsp+2D0h+var_290]
0x18000543d  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x180005444  mov     rcx, r14
0x180005447  mov     rax, [rax]
0x18000544a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544f  test    eax, eax
0x180005451  jns     short loc_180005472
0x180005453  mov     r8d, 17Ch
0x180005459  mov     r9, rdi
0x18000545c  lea     rdx, aCmapstoasttask_1; "CMapsToastTaskHandler::SetTemplateText"
0x180005463  mov     ecx, eax
0x180005465  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000546b  mov     ebx, eax
0x18000546d  jmp     loc_180005657
0x180005472  mov     r9d, ebx
0x180005475  lea     r8, aToastVisualBin_0; "/toast/visual/binding/text[number(@id) "...
0x18000547c  mov     edx, 104h; unsigned __int64
0x180005481  lea     rcx, [rsp+2D0h+sourceString]; unsigned __int16 *
0x180005486  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000548b  test    eax, eax
0x18000548d  jns     short loc_180005497
0x18000548f  mov     r8d, 17Fh
0x180005495  jmp     short loc_180005459
0x180005497  mov     rsi, [rsp+2D0h+var_290]
0x18000549c  mov     r15, [rsi]
0x18000549f  mov     rcx, [rsp+2D0h+var_2A0]
0x1800054a4  test    rcx, rcx
0x1800054a7  jz      short loc_1800054BB
0x1800054a9  mov     [rsp+2D0h+var_2A0], r13
0x1800054ae  mov     rax, [rcx]
0x1800054b1  mov     rax, [rax+10h]
0x1800054b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ba  nop
0x1800054bb  lea     rax, [rsp+2D0h+sourceString]
0x1800054c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800054c4  mov     rdx, rbx
0x1800054c7  inc     rdx; int
0x1800054ca  cmp     [rax+rdx*2], r13w
0x1800054cf  jnz     short loc_1800054C7
0x1800054d1  mov     eax, 0FFFFFFFFh
0x1800054d6  cmp     rdx, rax
0x1800054d9  ja      loc_180005713
0x1800054df  lea     eax, [rdx+1]
0x1800054e2  cmp     eax, edx
0x1800054e4  jb      loc_18000571E
0x1800054ea  lea     r9, [rsp+2D0h+string]; string
0x1800054ef  lea     r8, [rsp+2D0h+hstringHeader]; hstringHeader
0x1800054f4  lea     rcx, [rsp+2D0h+sourceString]; sourceString
0x1800054f9  call    cs:__imp_WindowsCreateStringReference
0x1800054ff  test    eax, eax
0x180005501  js      loc_180005729
0x180005507  lea     r8, [rsp+2D0h+var_2A0]
0x18000550c  mov     rdx, [rsp+2D0h+string]
0x180005511  mov     rcx, rsi
0x180005514  mov     rax, [r15+30h]
0x180005518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551d  nop
0x18000551e  test    eax, eax
0x180005520  jns     short loc_18000552D
0x180005522  mov     r8d, 182h
0x180005528  jmp     loc_180005459
0x18000552d  mov     rsi, [r14]
0x180005530  mov     rcx, [rsp+2D0h+var_2A8]
0x180005535  test    rcx, rcx
0x180005538  jz      short loc_18000554C
0x18000553a  mov     [rsp+2D0h+var_2A8], r13
0x18000553f  mov     rax, [rcx]
0x180005542  mov     rax, [rax+10h]
0x180005546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554b  nop
0x18000554c  mov     [rsp+2D0h+string], r13
0x180005551  inc     rbx
0x180005554  cmp     [r12+rbx*2], r13w
0x180005559  jnz     short loc_180005551
0x18000555b  mov     eax, 0FFFFFFFFh
0x180005560  cmp     rbx, rax
0x180005563  ja      loc_180005708
0x180005569  lea     eax, [rbx+1]
0x18000556c  cmp     eax, ebx
0x18000556e  jb      loc_180005731
0x180005574  lea     r9, [rsp+2D0h+string]; string
0x180005579  lea     r8, [rsp+2D0h+hstringHeader]; hstringHeader
0x18000557e  mov     edx, ebx; length
0x180005580  mov     rcx, r12; sourceString
0x180005583  call    cs:__imp_WindowsCreateStringReference
0x180005589  test    eax, eax
0x18000558b  js      loc_18000573C
0x180005591  lea     r8, [rsp+2D0h+var_2A8]
0x180005596  mov     rdx, [rsp+2D0h+string]
0x18000559b  mov     rcx, r14
0x18000559e  mov     rax, [rsi+58h]
0x1800055a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a7  nop
0x1800055a8  test    eax, eax
0x1800055aa  jns     short loc_1800055B7
0x1800055ac  mov     r8d, 183h
0x1800055b2  jmp     loc_180005459
0x1800055b7  mov     rbx, [rsp+2D0h+var_2A8]
0x1800055bc  mov     rax, [rbx]
0x1800055bf  mov     rsi, [rax]
0x1800055c2  mov     rcx, [rsp+2D0h+var_2B0]
0x1800055c7  test    rcx, rcx
0x1800055ca  jz      short loc_1800055DE
0x1800055cc  mov     [rsp+2D0h+var_2B0], r13
0x1800055d1  mov     rdx, [rcx]
0x1800055d4  mov     rax, [rdx+10h]
0x1800055d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055dd  nop
0x1800055de  lea     r8, [rsp+2D0h+var_2B0]
0x1800055e3  lea     rdx, _GUID_1c741d59_2122_47d5_a856_83f3d4214875
0x1800055ea  mov     rcx, rbx
0x1800055ed  mov     rax, rsi
0x1800055f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f5  nop
0x1800055f6  test    eax, eax
0x1800055f8  jns     short loc_180005605
0x1800055fa  mov     r8d, 184h
0x180005600  jmp     loc_180005459
0x180005605  mov     rbx, [rsp+2D0h+var_2A0]
0x18000560a  mov     rax, [rbx]
0x18000560d  mov     rsi, [rax+0B0h]
0x180005614  mov     rcx, [rsp+2D0h+var_298]
0x180005619  test    rcx, rcx
0x18000561c  jz      short loc_180005630
0x18000561e  mov     [rsp+2D0h+var_298], r13
0x180005623  mov     rdx, [rcx]
0x180005626  mov     rax, [rdx+10h]
0x18000562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562f  nop
0x180005630  lea     r8, [rsp+2D0h+var_298]
0x180005635  mov     rdx, [rsp+2D0h+var_2B0]
0x18000563a  mov     rcx, rbx
0x18000563d  mov     rax, rsi
0x180005640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005645  test    eax, eax
0x180005647  jns     short loc_180005654
0x180005649  mov     r8d, 185h
0x18000564f  jmp     loc_180005459
0x180005654  mov     ebx, r13d
0x180005657  mov     rcx, [rsp+2D0h+var_298]
0x18000565c  test    rcx, rcx
0x18000565f  jz      short loc_180005673
0x180005661  mov     [rsp+2D0h+var_298], r13
0x180005666  mov     rax, [rcx]
0x180005669  mov     rax, [rax+10h]
0x18000566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005672  nop
0x180005673  mov     rcx, [rsp+2D0h+var_2B0]
0x180005678  test    rcx, rcx
0x18000567b  jz      short loc_18000568F
0x18000567d  mov     [rsp+2D0h+var_2B0], r13
0x180005682  mov     rax, [rcx]
0x180005685  mov     rax, [rax+10h]
0x180005689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568e  nop
0x18000568f  mov     rcx, [rsp+2D0h+var_2A8]
0x180005694  test    rcx, rcx
0x180005697  jz      short loc_1800056AB
0x180005699  mov     [rsp+2D0h+var_2A8], r13
0x18000569e  mov     rax, [rcx]
0x1800056a1  mov     rax, [rax+10h]
0x1800056a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056aa  nop
0x1800056ab  mov     rcx, [rsp+2D0h+var_2A0]
0x1800056b0  test    rcx, rcx
0x1800056b3  jz      short loc_1800056C7
0x1800056b5  mov     [rsp+2D0h+var_2A0], r13
0x1800056ba  mov     rax, [rcx]
0x1800056bd  mov     rax, [rax+10h]
0x1800056c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c6  nop
0x1800056c7  mov     rcx, [rsp+2D0h+var_290]
0x1800056cc  test    rcx, rcx
0x1800056cf  jz      short loc_1800056E3
0x1800056d1  mov     [rsp+2D0h+var_290], r13
0x1800056d6  mov     rax, [rcx]
0x1800056d9  mov     rax, [rax+10h]
0x1800056dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e2  nop
0x1800056e3  mov     eax, ebx
0x1800056e5  mov     rcx, [rbp+1D0h+var_50]
0x1800056ec  xor     rcx, rsp; StackCookie
0x1800056ef  call    __security_check_cookie
0x1800056f4  add     rsp, 298h
0x1800056fb  pop     r15
0x1800056fd  pop     r14
0x1800056ff  pop     r13
0x180005701  pop     r12
0x180005703  pop     rdi
0x180005704  pop     rsi
0x180005705  pop     rbx
0x180005706  pop     rbp
0x180005707  retn
0x180005708  mov     ecx, 80070216h; this
0x18000570d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005712  int     3; Trap to Debugger
0x180005713  mov     ecx, 80070216h; this
0x180005718  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000571d  int     3; Trap to Debugger
0x18000571e  mov     ecx, 80070216h; this
0x180005723  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005728  int     3; Trap to Debugger
0x180005729  mov     ecx, eax; this
0x18000572b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005730  int     3; Trap to Debugger
0x180005731  mov     ecx, 80070216h; this
0x180005736  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000573b  int     3; Trap to Debugger
0x18000573c  mov     ecx, eax; this
0x18000573e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
