# CDDisplayManager::CreateDDisplayDeviceAndTarget(_LUID,uint,Windows::Devices::Display::Core::IDisplayDevice * *,Windows::Devices::Display::Core::IDisplayTarget * *)

- ea: `0x180282370`
- end: `0x1802827e9`
- name: `?CreateDDisplayDeviceAndTarget@CDDisplayManager@@QEAAJU_LUID@@IPEAPEAUIDisplayDevice@Core@Display@Devices@Windows@@PEAPEAUIDisplayTarget@4567@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(CDDisplayManager *__hidden this, struct _LUID, unsigned int, struct Windows::Devices::Display::Core::IDisplayDevice **, struct Windows::Devices::Display::Core::IDisplayTarget **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802545d4`

## callees

- `0x180026eac`
- `0x18002ddfc`
- `0x18004fce4`
- `0x1802284b0`
- `0x180282370`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18028240a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18028240a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180282430`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180282430`

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
0x180282370  mov     [rsp-8+arg_0], rbx
0x180282375  push    rbp
0x180282376  push    rsi
0x180282377  push    rdi
0x180282378  push    r12
0x18028237a  push    r13
0x18028237c  push    r14
0x18028237e  push    r15
0x180282380  lea     rbp, [rsp-1Fh]
0x180282385  sub     rsp, 0C0h
0x18028238c  mov     rax, cs:__security_cookie
0x180282393  xor     rax, rsp
0x180282396  mov     [rbp+4Fh+var_38], rax
0x18028239a  mov     rax, [rbp+4Fh+arg_20]
0x18028239e  xor     esi, esi
0x1802823a0  mov     r12, rdx
0x1802823a3  mov     qword ptr [r9], 0
0x1802823aa  shr     r12, 20h
0x1802823ae  mov     r13d, r8d
0x1802823b1  mov     [rbp+4Fh+var_60], r9
0x1802823b5  mov     rdi, rdx
0x1802823b8  mov     [rax], rsi
0x1802823bb  mov     [rbp+4Fh+var_58], rax
0x1802823bf  cmp     r8d, 0FFFFFFFFh
0x1802823c3  jnz     short loc_1802823E7
0x1802823c5  mov     ebx, 80070057h
0x1802823ca  mov     edx, 8Fh; void *
0x1802823cf  mov     rcx, [rbp+57h]; this
0x1802823d3  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802823da  mov     r9d, ebx; char *
0x1802823dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802823e2  jmp     loc_1802827C0
0x1802823e7  xor     eax, eax
0x1802823e9  mov     [rbp+4Fh+string], rsi
0x1802823ed  xorps   xmm0, xmm0
0x1802823f0  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+10h], rax
0x1802823f4  lea     r9, [rbp+4Fh+string]; string
0x1802823f8  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1802823fc  lea     edx, [rax+2Bh]; length
0x1802823ff  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayManager@@3QBGB; "Windows.Devices.Display.Core.DisplayMan"...
0x180282406  movups  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x18028240a  call    cs:__imp_WindowsCreateStringReference
0x180282410  mov     ebx, eax
0x180282412  test    eax, eax
0x180282414  jns     short loc_18028241D
0x180282416  mov     edx, 97h
0x18028241b  jmp     short loc_1802823CF
0x18028241d  mov     rcx, [rbp+4Fh+string]
0x180282421  lea     r8, [rbp+4Fh+var_80]
0x180282425  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18028242c  mov     [rbp+4Fh+var_80], rsi
0x180282430  call    cs:__imp_RoGetActivationFactory
0x180282436  mov     ebx, eax
0x180282438  test    eax, eax
0x18028243a  jns     short loc_180282459
0x18028243c  mov     rcx, [rbp+57h]; this
0x180282440  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282447  mov     r9d, eax; char *
0x18028244a  mov     edx, 9Ah; void *
0x18028244f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282454  jmp     loc_1802827B7
0x180282459  mov     rcx, [rbp+4Fh+var_80]
0x18028245d  lea     r8, [rbp+4Fh+var_C8]
0x180282461  mov     [rbp+4Fh+var_C8], rsi
0x180282465  lea     rdx, _GUID_2b6b9446_b999_5535_9d69_53f092c780a1
0x18028246c  mov     rax, [rcx]
0x18028246f  mov     rax, [rax]
0x180282472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282477  mov     ebx, eax
0x180282479  test    eax, eax
0x18028247b  jns     short loc_1802824A3
0x18028247d  mov     rcx, [rbp+57h]; this
0x180282481  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282488  mov     r9d, eax; char *
0x18028248b  mov     edx, 9Dh; void *
0x180282490  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282495  lea     rcx, [rbp+4Fh+var_C8]
0x180282499  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028249e  jmp     loc_1802827B7
0x1802824a3  mov     rcx, [rbp+4Fh+var_C8]
0x1802824a7  lea     r8, [rsp+0F0h+var_D0]
0x1802824ac  mov     qword ptr [rsp+0F0h+var_D0], rsi; int
0x1802824b1  xor     edx, edx
0x1802824b3  mov     rax, [rcx]
0x1802824b6  mov     rax, [rax+30h]
0x1802824ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802824bf  mov     ebx, eax
0x1802824c1  test    eax, eax
0x1802824c3  jns     short loc_1802824E9
0x1802824c5  mov     rcx, [rbp+57h]; this
0x1802824c9  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802824d0  mov     r9d, eax; char *
0x1802824d3  mov     edx, 0A1h; void *
0x1802824d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802824dd  lea     rcx, [rsp+0F0h+var_D0]
0x1802824e2  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802824e7  jmp     short loc_180282495
0x1802824e9  mov     rcx, qword ptr [rsp+0F0h+var_D0]
0x1802824ee  lea     rdx, [rbp+4Fh+var_C0]
0x1802824f2  mov     [rbp+4Fh+var_C0], rsi
0x1802824f6  mov     rax, [rcx]
0x1802824f9  mov     rax, [rax+30h]
0x1802824fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282502  mov     ebx, eax
0x180282504  test    eax, eax
0x180282506  jns     short loc_18028252B
0x180282508  mov     edx, 0A4h; void *
0x18028250d  mov     rcx, [rbp+57h]; this
0x180282511  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282518  mov     r9d, eax; char *
0x18028251b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282520  lea     rcx, [rbp+4Fh+var_C0]
0x180282524  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282529  jmp     short loc_1802824DD
0x18028252b  mov     rcx, [rbp+4Fh+var_C0]
0x18028252f  lea     rdx, [rbp+4Fh+var_98]
0x180282533  mov     [rbp+4Fh+var_98], esi
0x180282536  mov     rax, [rcx]
0x180282539  mov     rax, [rax+38h]
0x18028253d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282542  mov     ebx, eax
0x180282544  test    eax, eax
0x180282546  jns     short loc_18028254F
0x180282548  mov     edx, 0A7h
0x18028254d  jmp     short loc_18028250D
0x18028254f  mov     rbx, rsi
0x180282552  mov     [rbp+4Fh+var_B8], rsi
0x180282556  mov     [rbp+4Fh+var_A8], rbx
0x18028255a  mov     r15b, sil
0x18028255d  mov     r14d, esi
0x180282560  cmp     r14d, [rbp+4Fh+var_98]
0x180282564  jnb     loc_1802826E2
0x18028256a  test    r15b, r15b
0x18028256d  jnz     loc_18028271B
0x180282573  mov     rcx, [rbp+4Fh+var_C0]
0x180282577  lea     r8, [rbp+4Fh+var_B0]
0x18028257b  mov     [rbp+4Fh+var_B0], rsi
0x18028257f  mov     edx, r14d
0x180282582  mov     rax, [rcx]
0x180282585  mov     rax, [rax+30h]
0x180282589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028258e  mov     esi, eax
0x180282590  test    eax, eax
0x180282592  js      loc_1802826DB
0x180282598  mov     rcx, [rbp+4Fh+var_B0]
0x18028259c  lea     rdx, [rbp+4Fh+var_94]
0x1802825a0  mov     [rbp+4Fh+var_94], 0
0x1802825a7  mov     rax, [rcx]
0x1802825aa  mov     rax, [rax+40h]
0x1802825ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802825b3  mov     esi, eax
0x1802825b5  test    eax, eax
0x1802825b7  js      loc_1802826C1
0x1802825bd  cmp     [rbp+4Fh+var_94], r13d
0x1802825c1  jnz     loc_180282678
0x1802825c7  mov     rcx, [rbp+4Fh+var_B0]
0x1802825cb  lea     rdx, [rbp+4Fh+var_A0]
0x1802825cf  mov     [rbp+4Fh+var_A0], 0
0x1802825d7  mov     rax, [rcx]
0x1802825da  mov     rax, [rax+30h]
0x1802825de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802825e3  mov     esi, eax
0x1802825e5  test    eax, eax
0x1802825e7  js      loc_1802826BA
0x1802825ed  mov     rcx, [rbp+4Fh+var_A0]
0x1802825f1  lea     rdx, [rbp+4Fh+var_88]
0x1802825f5  mov     [rbp+4Fh+var_88], 0
0x1802825fd  mov     rax, [rcx]
0x180282600  mov     rax, [rax+30h]
0x180282604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282609  mov     esi, eax
0x18028260b  test    eax, eax
0x18028260d  js      short loc_18028268B
0x18028260f  mov     eax, dword ptr [rbp+4Fh+var_88]
0x180282612  mov     ecx, dword ptr [rbp+4Fh+var_88+4]
0x180282615  mov     dword ptr [rbp+4Fh+var_70], eax
0x180282618  mov     dword ptr [rbp+4Fh+var_70+4], ecx
0x18028261b  mov     rax, [rbp+4Fh+var_70]
0x18028261f  mov     dword ptr [rbp+4Fh+var_68], edi
0x180282622  mov     dword ptr [rbp+4Fh+var_68+4], r12d
0x180282626  cmp     [rbp+4Fh+var_68], rax
0x18028262a  jnz     short loc_18028266F
0x18028262c  mov     rsi, rbx
0x18028262f  mov     r15b, 1
0x180282632  mov     rbx, [rbp+4Fh+var_A0]
0x180282636  mov     [rbp+4Fh+var_A8], rbx
0x18028263a  test    rbx, rbx
0x18028263d  jz      short loc_18028264E
0x18028263f  mov     rax, [rbx]
0x180282642  mov     rcx, rbx
0x180282645  mov     rax, [rax+8]
0x180282649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028264e  test    rsi, rsi
0x180282651  jz      short loc_180282662
0x180282653  mov     rax, [rsi]
0x180282656  mov     rcx, rsi
0x180282659  mov     rax, [rax+10h]
0x18028265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282662  lea     rdx, [rbp+4Fh+var_B0]
0x180282666  lea     rcx, [rbp+4Fh+var_B8]
0x18028266a  call    ??$?4VCSystemMemoryBitmap@@Uerr_returncode_policy@wil@@X@?$com_ptr_t@VIBitmapSource@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV?$com_ptr_t@VCSystemMemoryBitmap@@Uerr_returncode_policy@wil@@@1@@Z; wil::com_ptr_t<IBitmapSource,wil::err_returncode_policy>::operator=<CSystemMemoryBitmap,wil::err_returncode_policy,void>(wil::com_ptr_t<CSystemMemoryBitmap,wil::err_returncode_policy> const &)
0x18028266f  lea     rcx, [rbp+4Fh+var_A0]
0x180282673  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282678  lea     rcx, [rbp+4Fh+var_B0]
0x18028267c  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282681  inc     r14d
0x180282684  xor     esi, esi
0x180282686  jmp     loc_180282560
0x18028268b  mov     edx, 0BBh; void *
0x180282690  mov     rcx, [rbp+57h]; this
0x180282694  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x18028269b  mov     r9d, esi; char *
0x18028269e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802826a3  lea     rcx, [rbp+4Fh+var_A0]
0x1802826a7  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802826ac  lea     rcx, [rbp+4Fh+var_B0]
0x1802826b0  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802826b5  jmp     loc_180282787
0x1802826ba  mov     edx, 0B8h
0x1802826bf  jmp     short loc_180282690
0x1802826c1  mov     edx, 0B3h; void *
0x1802826c6  mov     rcx, [rbp+57h]; this
0x1802826ca  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802826d1  mov     r9d, esi; char *
0x1802826d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802826d9  jmp     short loc_1802826AC
0x1802826db  mov     edx, 0B0h
0x1802826e0  jmp     short loc_1802826C6
0x1802826e2  test    r15b, r15b
0x1802826e5  jnz     short loc_18028271B
0x1802826e7  mov     rcx, [rbp+57h]; this
0x1802826eb  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x1802826f2  mov     ebx, 80070057h
0x1802826f7  mov     edx, 0C9h; void *
0x1802826fc  mov     r9d, ebx; char *
0x1802826ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282704  lea     rcx, [rbp+4Fh+var_B8]
0x180282708  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028270d  lea     rcx, [rbp+4Fh+var_A8]
0x180282711  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282716  jmp     loc_180282520
0x18028271b  mov     rcx, qword ptr [rsp+0F0h+var_D0]
0x180282720  lea     r8, [rbp+4Fh+var_90]
0x180282724  mov     [rbp+4Fh+var_90], rsi
0x180282728  mov     rdx, rbx
0x18028272b  mov     rax, [rcx]
0x18028272e  mov     rax, [rax+70h]
0x180282732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180282737  mov     ebx, eax
0x180282739  test    eax, eax
0x18028273b  jns     short loc_180282760
0x18028273d  mov     rcx, [rbp+57h]; this
0x180282741  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180282748  mov     r9d, eax; char *
0x18028274b  mov     edx, 0CEh; void *
0x180282750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180282755  lea     rcx, [rbp+4Fh+var_90]
0x180282759  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18028275e  jmp     short loc_180282704
0x180282760  mov     rax, [rbp+4Fh+var_90]
0x180282764  mov     rcx, [rbp+4Fh+var_60]
0x180282768  mov     [rbp+4Fh+var_90], rsi
0x18028276c  mov     [rcx], rax
0x18028276f  mov     rax, [rbp+4Fh+var_B8]
0x180282773  mov     rcx, [rbp+4Fh+var_58]
0x180282777  mov     [rbp+4Fh+var_B8], rsi
0x18028277b  mov     [rcx], rax
0x18028277e  lea     rcx, [rbp+4Fh+var_90]
0x180282782  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282787  lea     rcx, [rbp+4Fh+var_B8]
0x18028278b  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282790  lea     rcx, [rbp+4Fh+var_A8]
0x180282794  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180282799  lea     rcx, [rbp+4Fh+var_C0]
0x18028279d  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802827a2  lea     rcx, [rsp+0F0h+var_D0]
0x1802827a7  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802827ac  lea     rcx, [rbp+4Fh+var_C8]
0x1802827b0  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802827b5  mov     ebx, esi
0x1802827b7  lea     rcx, [rbp+4Fh+var_80]
0x1802827bb  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802827c0  mov     eax, ebx
0x1802827c2  mov     rcx, [rbp+4Fh+var_38]
0x1802827c6  xor     rcx, rsp; StackCookie
0x1802827c9  call    __security_check_cookie
0x1802827ce  mov     rbx, [rsp+0F0h+arg_0]
0x1802827d6  add     rsp, 0C0h
0x1802827dd  pop     r15
0x1802827df  pop     r14
0x1802827e1  pop     r13
0x1802827e3  pop     r12
0x1802827e5  pop     rdi
0x1802827e6  pop     rsi
0x1802827e7  pop     rbp
0x1802827e8  retn
```
