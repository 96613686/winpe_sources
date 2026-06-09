# CDDisplayManager::CreateDDisplayDeviceAndTarget(_LUID,uint,Windows::Devices::Display::Core::IDisplayDevice * *,Windows::Devices::Display::Core::IDisplayTarget * *)

- ea: `0x180282350`
- end: `0x1802827c9`
- name: `?CreateDDisplayDeviceAndTarget@CDDisplayManager@@QEAAJU_LUID@@IPEAPEAUIDisplayDevice@Core@Display@Devices@Windows@@PEAPEAUIDisplayTarget@4567@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(CDDisplayManager *__hidden this, struct _LUID, unsigned int, struct Windows::Devices::Display::Core::IDisplayDevice **, struct Windows::Devices::Display::Core::IDisplayTarget **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802545b4`

## callees

- `0x18000a254`
- `0x18001cc60`
- `0x180042854`
- `0x180228490`
- `0x180282350`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802823ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802823ea`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180282410`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180282410`

## pseudocode

```c
__int64 __fastcall CDDisplayManager::CreateDDisplayDeviceAndTarget(
        CDDisplayManager *this,
        struct _LUID a2,
        int a3,
        struct Windows::Devices::Display::Core::IDisplayDevice **a4,
        struct Windows::Devices::Display::Core::IDisplayTarget **a5)
{
  int v5; // esi
  LONG HighPart; // r12d
  DWORD LowPart; // edi
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int ActivationFactory; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rbx
  char v17; // r15
  unsigned int i; // r14d
  __int64 v19; // rsi
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // eax
  struct Windows::Devices::Display::Core::IDisplayDevice *v23; // rax
  struct Windows::Devices::Display::Core::IDisplayTarget *v24; // rax
  int v26[2]; // [rsp+20h] [rbp-81h] BYREF
  __int64 v27; // [rsp+28h] [rbp-79h] BYREF
  __int64 v28; // [rsp+30h] [rbp-71h] BYREF
  struct Windows::Devices::Display::Core::IDisplayTarget *v29; // [rsp+38h] [rbp-69h] BYREF
  __int64 v30; // [rsp+40h] [rbp-61h] BYREF
  __int64 v31; // [rsp+48h] [rbp-59h] BYREF
  __int64 v32; // [rsp+50h] [rbp-51h] BYREF
  unsigned int v33; // [rsp+58h] [rbp-49h] BYREF
  int v34; // [rsp+5Ch] [rbp-45h] BYREF
  struct Windows::Devices::Display::Core::IDisplayDevice *v35; // [rsp+60h] [rbp-41h] BYREF
  HSTRING v36; // [rsp+68h] [rbp-39h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-31h] BYREF
  HSTRING string[3]; // [rsp+78h] [rbp-29h] BYREF
  struct Windows::Devices::Display::Core::IDisplayDevice **v39; // [rsp+90h] [rbp-11h]
  struct Windows::Devices::Display::Core::IDisplayTarget **v40; // [rsp+98h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v5 = 0;
  *a4 = 0;
  HighPart = a2.HighPart;
  v39 = a4;
  LowPart = a2.LowPart;
  *a5 = 0;
  v40 = a5;
  if ( a3 != -1 )
  {
    string[0] = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    v9 = WindowsCreateStringReference(L"Windows.Devices.Display.Core.DisplayManager", 0x2Bu, &hstringHeader, string);
    if ( (v9 & 0x80000000) != 0 )
    {
      v10 = 151;
      goto LABEL_3;
    }
    v37 = 0;
    ActivationFactory = RoGetActivationFactory(string[0], &GUID_00000035_0000_0000_c000_000000000046, &v37);
    v9 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v27 = 0;
      v12 = (**v37)(v37, &GUID_2b6b9446_b999_5535_9d69_53f092c780a1, &v27);
      v9 = v12;
      if ( v12 >= 0 )
      {
        *(_QWORD *)v26 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v27 + 48LL))(v27, 0, v26);
        v9 = v13;
        if ( v13 >= 0 )
        {
          v28 = 0;
          v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v26 + 48LL))(*(_QWORD *)v26, &v28);
          v9 = v14;
          if ( v14 >= 0 )
          {
            v33 = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 56LL))(v28, &v33);
            v9 = v14;
            if ( v14 >= 0 )
            {
              v16 = 0;
              v29 = 0;
              v31 = 0;
              v17 = 0;
              for ( i = 0; ; ++i )
              {
                if ( i >= v33 )
                {
                  if ( v17 )
                  {
LABEL_46:
                    v35 = 0;
                    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct Windows::Devices::Display::Core::IDisplayDevice **))(**(_QWORD **)v26 + 112LL))(
                            *(_QWORD *)v26,
                            v16,
                            &v35);
                    v9 = v22;
                    if ( v22 >= 0 )
                    {
                      v23 = v35;
                      v35 = 0;
                      *v39 = v23;
                      v24 = v29;
                      v29 = 0;
                      *v40 = v24;
                      wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v35);
                      goto LABEL_49;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xCE,
                      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
                      (const char *)(unsigned int)v22,
                      v26[0]);
                    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v35);
                  }
                  else
                  {
                    v9 = -2147024809;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xC9,
                      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
                      (const char *)0x80070057LL,
                      v26[0]);
                  }
                  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v29);
                  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v31);
                  goto LABEL_17;
                }
                if ( v17 )
                  goto LABEL_46;
                v30 = 0;
                v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 48LL))(v28, i, &v30);
                if ( v5 < 0 )
                  break;
                v34 = 0;
                v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 64LL))(v30, &v34);
                if ( v5 < 0 )
                {
                  v21 = 179;
                  goto LABEL_41;
                }
                if ( v34 == a3 )
                {
                  v32 = 0;
                  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v32);
                  if ( v5 < 0 )
                  {
                    v20 = 184;
                    goto LABEL_37;
                  }
                  v36 = 0;
                  v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL))(v32, &v36);
                  if ( v5 < 0 )
                  {
                    v20 = 187;
LABEL_37:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v20,
                      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
                      (const char *)(unsigned int)v5,
                      v26[0]);
                    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v32);
                    goto LABEL_38;
                  }
                  string[1] = v36;
                  string[2] = (HSTRING)__PAIR64__(HighPart, LowPart);
                  if ( (HSTRING)__PAIR64__(HighPart, LowPart) == v36 )
                  {
                    v19 = v16;
                    v17 = 1;
                    v16 = v32;
                    v31 = v32;
                    if ( v32 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
                    if ( v19 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                    wil::com_ptr_t<IBitmapSource,wil::err_returncode_policy>::operator=<CSystemMemoryBitmap,wil::err_returncode_policy,void>(
                      &v29,
                      &v30);
                  }
                  wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v32);
                }
                wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v30);
                v5 = 0;
              }
              v21 = 176;
LABEL_41:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v21,
                (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
                (const char *)(unsigned int)v5,
                v26[0]);
LABEL_38:
              wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v30);
LABEL_49:
              wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v29);
              wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v31);
              wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v28);
              wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(v26);
              wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v27);
              v9 = v5;
              goto LABEL_50;
            }
            v15 = 167;
          }
          else
          {
            v15 = 164;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
            (const char *)(unsigned int)v14,
            v26[0]);
LABEL_17:
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v28);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA1,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
            (const char *)(unsigned int)v13,
            v26[0]);
        }
        wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(v26);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
          (const char *)(unsigned int)v12,
          v26[0]);
      }
      wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v27);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v26[0]);
    }
LABEL_50:
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v37);
    return v9;
  }
  v9 = -2147024809;
  v10 = 143;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\global\\globalddisplaymanager.cpp",
    (const char *)v9,
    v26[0]);
  return v9;
}

```

## disassembly

```asm
0x180282350  mov     [rsp-8+arg_0], rbx
0x180282355  push    rbp
0x180282356  push    rsi
0x180282357  push    rdi
0x180282358  push    r12
0x18028235a  push    r13
0x18028235c  push    r14
0x18028235e  push    r15
0x180282360  lea     rbp, [rsp-1Fh]
0x180282365  sub     rsp, 0C0h
0x18028236c  mov     rax, cs:__security_cookie
0x180282373  xor     rax, rsp
0x180282376  mov     [rbp+4Fh+var_38], rax
0x18028237a  mov     rax, [rbp+4Fh+arg_20]
0x18028237e  xor     esi, esi
0x180282380  mov     r12, rdx
0x180282383  mov     qword ptr [r9], 0
0x18028238a  shr     r12, 20h
0x18028238e  mov     r13d, r8d
0x180282391  mov     [rbp+4Fh+var_60], r9
0x180282395  mov     rdi, rdx
0x180282398  mov     [rax], rsi
0x18028239b  mov     [rbp+4Fh+var_58], rax
0x18028239f  cmp     r8d, 0FFFFFFFFh
0x1802823a3  jnz     short loc_1802823C7
0x1802823a5  mov     ebx, 80070057h
0x1802823aa  mov     edx, 8Fh; void *
0x1802823af  mov     rcx, [rbp+57h]; this
0x1802823b3  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802823ba  mov     r9d, ebx; char *
0x1802823bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802823c2  jmp     loc_1802827A0
0x1802823c7  xor     eax, eax
0x1802823c9  mov     [rbp+4Fh+string], rsi
0x1802823cd  xorps   xmm0, xmm0
0x1802823d0  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+10h], rax
0x1802823d4  lea     r9, [rbp+4Fh+string]; string
0x1802823d8  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1802823dc  lea     edx, [rax+2Bh]; length
0x1802823df  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayManager@@3QBGB; "Windows.Devices.Display.Core.DisplayMan"...
0x1802823e6  movups  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x1802823ea  call    cs:__imp_WindowsCreateStringReference
0x1802823f0  mov     ebx, eax
0x1802823f2  test    eax, eax
0x1802823f4  jns     short loc_1802823FD
0x1802823f6  mov     edx, 97h
0x1802823fb  jmp     short loc_1802823AF
0x1802823fd  mov     rcx, [rbp+4Fh+string]
0x180282401  lea     r8, [rbp+4Fh+var_80]
0x180282405  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18028240c  mov     [rbp+4Fh+var_80], rsi
0x180282410  call    cs:__imp_RoGetActivationFactory
0x180282416  mov     ebx, eax
0x180282418  test    eax, eax
0x18028241a  jns     short loc_180282439
0x18028241c  mov     rcx, [rbp+57h]; this
0x180282420  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282427  mov     r9d, eax; char *
0x18028242a  mov     edx, 9Ah; void *
0x18028242f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282434  jmp     loc_180282797
0x180282439  mov     rcx, [rbp+4Fh+var_80]
0x18028243d  lea     r8, [rbp+4Fh+var_C8]
0x180282441  mov     [rbp+4Fh+var_C8], rsi
0x180282445  lea     rdx, _GUID_2b6b9446_b999_5535_9d69_53f092c780a1
0x18028244c  mov     rax, [rcx]
0x18028244f  mov     rax, [rax]
0x180282452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282457  mov     ebx, eax
0x180282459  test    eax, eax
0x18028245b  jns     short loc_180282483
0x18028245d  mov     rcx, [rbp+57h]; this
0x180282461  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282468  mov     r9d, eax; char *
0x18028246b  mov     edx, 9Dh; void *
0x180282470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282475  lea     rcx, [rbp+4Fh+var_C8]
0x180282479  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028247e  jmp     loc_180282797
0x180282483  mov     rcx, [rbp+4Fh+var_C8]
0x180282487  lea     r8, [rsp+0F0h+var_D0]
0x18028248c  mov     qword ptr [rsp+0F0h+var_D0], rsi; int
0x180282491  xor     edx, edx
0x180282493  mov     rax, [rcx]
0x180282496  mov     rax, [rax+30h]
0x18028249a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028249f  mov     ebx, eax
0x1802824a1  test    eax, eax
0x1802824a3  jns     short loc_1802824C9
0x1802824a5  mov     rcx, [rbp+57h]; this
0x1802824a9  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802824b0  mov     r9d, eax; char *
0x1802824b3  mov     edx, 0A1h; void *
0x1802824b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802824bd  lea     rcx, [rsp+0F0h+var_D0]
0x1802824c2  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802824c7  jmp     short loc_180282475
0x1802824c9  mov     rcx, qword ptr [rsp+0F0h+var_D0]
0x1802824ce  lea     rdx, [rbp+4Fh+var_C0]
0x1802824d2  mov     [rbp+4Fh+var_C0], rsi
0x1802824d6  mov     rax, [rcx]
0x1802824d9  mov     rax, [rax+30h]
0x1802824dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802824e2  mov     ebx, eax
0x1802824e4  test    eax, eax
0x1802824e6  jns     short loc_18028250B
0x1802824e8  mov     edx, 0A4h; void *
0x1802824ed  mov     rcx, [rbp+57h]; this
0x1802824f1  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802824f8  mov     r9d, eax; char *
0x1802824fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282500  lea     rcx, [rbp+4Fh+var_C0]
0x180282504  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282509  jmp     short loc_1802824BD
0x18028250b  mov     rcx, [rbp+4Fh+var_C0]
0x18028250f  lea     rdx, [rbp+4Fh+var_98]
0x180282513  mov     [rbp+4Fh+var_98], esi
0x180282516  mov     rax, [rcx]
0x180282519  mov     rax, [rax+38h]
0x18028251d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282522  mov     ebx, eax
0x180282524  test    eax, eax
0x180282526  jns     short loc_18028252F
0x180282528  mov     edx, 0A7h
0x18028252d  jmp     short loc_1802824ED
0x18028252f  mov     rbx, rsi
0x180282532  mov     [rbp+4Fh+var_B8], rsi
0x180282536  mov     [rbp+4Fh+var_A8], rbx
0x18028253a  mov     r15b, sil
0x18028253d  mov     r14d, esi
0x180282540  cmp     r14d, [rbp+4Fh+var_98]
0x180282544  jnb     loc_1802826C2
0x18028254a  test    r15b, r15b
0x18028254d  jnz     loc_1802826FB
0x180282553  mov     rcx, [rbp+4Fh+var_C0]
0x180282557  lea     r8, [rbp+4Fh+var_B0]
0x18028255b  mov     [rbp+4Fh+var_B0], rsi
0x18028255f  mov     edx, r14d
0x180282562  mov     rax, [rcx]
0x180282565  mov     rax, [rax+30h]
0x180282569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028256e  mov     esi, eax
0x180282570  test    eax, eax
0x180282572  js      loc_1802826BB
0x180282578  mov     rcx, [rbp+4Fh+var_B0]
0x18028257c  lea     rdx, [rbp+4Fh+var_94]
0x180282580  mov     [rbp+4Fh+var_94], 0
0x180282587  mov     rax, [rcx]
0x18028258a  mov     rax, [rax+40h]
0x18028258e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282593  mov     esi, eax
0x180282595  test    eax, eax
0x180282597  js      loc_1802826A1
0x18028259d  cmp     [rbp+4Fh+var_94], r13d
0x1802825a1  jnz     loc_180282658
0x1802825a7  mov     rcx, [rbp+4Fh+var_B0]
0x1802825ab  lea     rdx, [rbp+4Fh+var_A0]
0x1802825af  mov     [rbp+4Fh+var_A0], 0
0x1802825b7  mov     rax, [rcx]
0x1802825ba  mov     rax, [rax+30h]
0x1802825be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802825c3  mov     esi, eax
0x1802825c5  test    eax, eax
0x1802825c7  js      loc_18028269A
0x1802825cd  mov     rcx, [rbp+4Fh+var_A0]
0x1802825d1  lea     rdx, [rbp+4Fh+var_88]
0x1802825d5  mov     [rbp+4Fh+var_88], 0
0x1802825dd  mov     rax, [rcx]
0x1802825e0  mov     rax, [rax+30h]
0x1802825e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802825e9  mov     esi, eax
0x1802825eb  test    eax, eax
0x1802825ed  js      short loc_18028266B
0x1802825ef  mov     eax, dword ptr [rbp+4Fh+var_88]
0x1802825f2  mov     ecx, dword ptr [rbp+4Fh+var_88+4]
0x1802825f5  mov     dword ptr [rbp+4Fh+var_70], eax
0x1802825f8  mov     dword ptr [rbp+4Fh+var_70+4], ecx
0x1802825fb  mov     rax, [rbp+4Fh+var_70]
0x1802825ff  mov     dword ptr [rbp+4Fh+var_68], edi
0x180282602  mov     dword ptr [rbp+4Fh+var_68+4], r12d
0x180282606  cmp     [rbp+4Fh+var_68], rax
0x18028260a  jnz     short loc_18028264F
0x18028260c  mov     rsi, rbx
0x18028260f  mov     r15b, 1
0x180282612  mov     rbx, [rbp+4Fh+var_A0]
0x180282616  mov     [rbp+4Fh+var_A8], rbx
0x18028261a  test    rbx, rbx
0x18028261d  jz      short loc_18028262E
0x18028261f  mov     rax, [rbx]
0x180282622  mov     rcx, rbx
0x180282625  mov     rax, [rax+8]
0x180282629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028262e  test    rsi, rsi
0x180282631  jz      short loc_180282642
0x180282633  mov     rax, [rsi]
0x180282636  mov     rcx, rsi
0x180282639  mov     rax, [rax+10h]
0x18028263d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282642  lea     rdx, [rbp+4Fh+var_B0]
0x180282646  lea     rcx, [rbp+4Fh+var_B8]
0x18028264a  call    ??$?4VCSystemMemoryBitmap@@Uerr_returncode_policy@wil@@X@?$com_ptr_t@VIBitmapSource@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV?$com_ptr_t@VCSystemMemoryBitmap@@Uerr_returncode_policy@wil@@@1@@Z; wil::com_ptr_t<IBitmapSource,wil::err_returncode_policy>::operator=<CSystemMemoryBitmap,wil::err_returncode_policy,void>(wil::com_ptr_t<CSystemMemoryBitmap,wil::err_returncode_policy> const &)
0x18028264f  lea     rcx, [rbp+4Fh+var_A0]
0x180282653  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282658  lea     rcx, [rbp+4Fh+var_B0]
0x18028265c  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282661  inc     r14d
0x180282664  xor     esi, esi
0x180282666  jmp     loc_180282540
0x18028266b  mov     edx, 0BBh; void *
0x180282670  mov     rcx, [rbp+57h]; this
0x180282674  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x18028267b  mov     r9d, esi; char *
0x18028267e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282683  lea     rcx, [rbp+4Fh+var_A0]
0x180282687  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028268c  lea     rcx, [rbp+4Fh+var_B0]
0x180282690  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282695  jmp     loc_180282767
0x18028269a  mov     edx, 0B8h
0x18028269f  jmp     short loc_180282670
0x1802826a1  mov     edx, 0B3h; void *
0x1802826a6  mov     rcx, [rbp+57h]; this
0x1802826aa  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802826b1  mov     r9d, esi; char *
0x1802826b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802826b9  jmp     short loc_18028268C
0x1802826bb  mov     edx, 0B0h
0x1802826c0  jmp     short loc_1802826A6
0x1802826c2  test    r15b, r15b
0x1802826c5  jnz     short loc_1802826FB
0x1802826c7  mov     rcx, [rbp+57h]; this
0x1802826cb  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802826d2  mov     ebx, 80070057h
0x1802826d7  mov     edx, 0C9h; void *
0x1802826dc  mov     r9d, ebx; char *
0x1802826df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802826e4  lea     rcx, [rbp+4Fh+var_B8]
0x1802826e8  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802826ed  lea     rcx, [rbp+4Fh+var_A8]
0x1802826f1  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802826f6  jmp     loc_180282500
0x1802826fb  mov     rcx, qword ptr [rsp+0F0h+var_D0]
0x180282700  lea     r8, [rbp+4Fh+var_90]
0x180282704  mov     [rbp+4Fh+var_90], rsi
0x180282708  mov     rdx, rbx
0x18028270b  mov     rax, [rcx]
0x18028270e  mov     rax, [rax+70h]
0x180282712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282717  mov     ebx, eax
0x180282719  test    eax, eax
0x18028271b  jns     short loc_180282740
0x18028271d  mov     rcx, [rbp+57h]; this
0x180282721  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282728  mov     r9d, eax; char *
0x18028272b  mov     edx, 0CEh; void *
0x180282730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282735  lea     rcx, [rbp+4Fh+var_90]
0x180282739  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028273e  jmp     short loc_1802826E4
0x180282740  mov     rax, [rbp+4Fh+var_90]
0x180282744  mov     rcx, [rbp+4Fh+var_60]
0x180282748  mov     [rbp+4Fh+var_90], rsi
0x18028274c  mov     [rcx], rax
0x18028274f  mov     rax, [rbp+4Fh+var_B8]
0x180282753  mov     rcx, [rbp+4Fh+var_58]
0x180282757  mov     [rbp+4Fh+var_B8], rsi
0x18028275b  mov     [rcx], rax
0x18028275e  lea     rcx, [rbp+4Fh+var_90]
0x180282762  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282767  lea     rcx, [rbp+4Fh+var_B8]
0x18028276b  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282770  lea     rcx, [rbp+4Fh+var_A8]
0x180282774  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282779  lea     rcx, [rbp+4Fh+var_C0]
0x18028277d  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282782  lea     rcx, [rsp+0F0h+var_D0]
0x180282787  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028278c  lea     rcx, [rbp+4Fh+var_C8]
0x180282790  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282795  mov     ebx, esi
0x180282797  lea     rcx, [rbp+4Fh+var_80]
0x18028279b  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802827a0  mov     eax, ebx
0x1802827a2  mov     rcx, [rbp+4Fh+var_38]
0x1802827a6  xor     rcx, rsp; StackCookie
0x1802827a9  call    __security_check_cookie
0x1802827ae  mov     rbx, [rsp+0F0h+arg_0]
0x1802827b6  add     rsp, 0C0h
0x1802827bd  pop     r15
0x1802827bf  pop     r14
0x1802827c1  pop     r13
0x1802827c3  pop     r12
0x1802827c5  pop     rdi
0x1802827c6  pop     rsi
0x1802827c7  pop     rbp
0x1802827c8  retn
```
