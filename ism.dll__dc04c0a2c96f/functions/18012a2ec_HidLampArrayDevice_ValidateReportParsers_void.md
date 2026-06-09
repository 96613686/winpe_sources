# HidLampArrayDevice::ValidateReportParsers(void)

- ea: `0x18012a2ec`
- end: `0x18012aeea`
- name: `?ValidateReportParsers@HidLampArrayDevice@@AEAAJXZ`
- size: `3070`
- prototype: `__int64 __fastcall(HidLampArrayDevice *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18008fbec`

## callees

- `0x18006ee00`
- `0x1800f0990`
- `0x18010c32c`
- `0x18010c350`
- `0x18010c734`
- `0x180120c4c`
- `0x180127220`
- `0x180127410`
- `0x180128538`
- `0x180128860`
- `0x180128974`
- `0x18012a2ec`
- `0x18012aef0`
- `0x18012af3c`
- `0x18012afa4`

## string_xrefs

- `0x18012a3d8`: `One or more ReportParsers are null.  LampArrayAttributes:%d, LampArrayControl:%d, LampAttributesRequest:%d, LampAttributesResponse:%d, LampMultiUpdate:%d, LampRangeUpdate:%d`
- `0x18012a72d`: `, LampMultiUpdate:`
- `0x18012a979`: `, LampMultiUpdate:`
- `0x18012aad8`: `, LampMultiUpdate:`
- `0x18012ac37`: `, LampMultiUpdate:`
- `0x18012ad9d`: `, LampMultiUpdate:`
- `0x18012a755`: `, LampRangeUpdate:`
- `0x18012a99e`: `, LampRangeUpdate:`
- `0x18012aafd`: `, LampRangeUpdate:`
- `0x18012ac5c`: `, LampRangeUpdate:`
- `0x18012adc2`: `, LampRangeUpdate:`

## pseudocode

```c
__int64 __fastcall HidLampArrayDevice::ValidateReportParsers(HidLampArrayDevice *this)
{
  __int64 v2; // rcx
  char v3; // si
  char v4; // al
  __int64 v5; // rax
  __int64 v6; // r9
  unsigned __int8 v7; // r14
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // ecx
  unsigned __int8 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r15
  __int64 v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rdx
  unsigned __int8 *v33; // rcx
  __int64 v34; // rax
  _DWORD *v35; // r8
  _QWORD *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v41; // rsi
  __int64 v42; // rdi
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // ecx
  __int64 v51; // rsi
  __int64 v52; // rdi
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  int v60; // ecx
  __int64 v61; // rsi
  __int64 v62; // rdi
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  int v70; // ecx
  __int64 v71; // rsi
  __int64 v72; // rdi
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  int v80; // ecx
  const char *v81; // rax
  char *v82; // [rsp+28h] [rbp-D8h]
  __int128 v83; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v84; // [rsp+70h] [rbp-90h]
  __int64 v85; // [rsp+78h] [rbp-88h] BYREF
  char *v86[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v87[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v88[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v89[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v90[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v91[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v92[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v93[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v94[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v95[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v96[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v97[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v98[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v99[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v100[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v101[32]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v2 = *((_QWORD *)this + 73);
  v3 = 1;
  if ( !v2
    || !*((_QWORD *)this + 74)
    || !*((_QWORD *)this + 75)
    || !*((_QWORD *)this + 76)
    || !*((_QWORD *)this + 77)
    || (v4 = 0, !*((_QWORD *)this + 78)) )
  {
    v4 = 1;
  }
  if ( v4 )
  {
    LODWORD(v82) = v2 == 0;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x354,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
      (const char *)0x80070057LL,
      (int)"One or more ReportParsers are null.  LampArrayAttributes:%d, LampArrayControl:%d, LampAttributesRequest:%d, L"
           "ampAttributesResponse:%d, LampMultiUpdate:%d, LampRangeUpdate:%d",
      v82,
      *((_QWORD *)this + 74) == 0,
      *((_QWORD *)this + 75) == 0,
      *((_QWORD *)this + 76) == 0,
      *((_QWORD *)this + 77) == 0,
      *((_QWORD *)this + 78) == 0);
  }
  else
  {
    v83 = 0;
    v84 = 0;
    std::vector<unsigned char>::_Buy_raw(&v83);
    v5 = v83;
    *(_DWORD *)v83 = 0;
    *(_WORD *)(v5 + 4) = 0;
    *((_QWORD *)&v83 + 1) = v5 + 6;
    v85 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v85);
    *(_BYTE *)v83 = *(_BYTE *)(*((_QWORD *)this + 73) + 16LL);
    *(_BYTE *)(v83 + 1) = *(_BYTE *)(*((_QWORD *)this + 74) + 16LL);
    *(_BYTE *)(v83 + 2) = *(_BYTE *)(*((_QWORD *)this + 75) + 16LL);
    *(_BYTE *)(v83 + 3) = *(_BYTE *)(*((_QWORD *)this + 76) + 16LL);
    *(_BYTE *)(v83 + 4) = *(_BYTE *)(*((_QWORD *)this + 77) + 16LL);
    *(_BYTE *)(v83 + 5) = *(_BYTE *)(*((_QWORD *)this + 78) + 16LL);
    LOBYTE(v6) = 0;
    std::_Sort_unchecked<unsigned char *,std::less<void>>(v83, *((_QWORD *)&v83 + 1), *((_QWORD *)&v83 + 1) - v83, v6);
    v7 = 0;
    v8 = 0;
    v9 = *((_QWORD *)&v83 + 1);
    v10 = v83;
    if ( *((_QWORD *)&v83 + 1) == (_QWORD)v83 )
    {
LABEL_17:
      v15 = *(int *)(*((_QWORD *)this + 73) + 56LL);
      if ( v15 == *(_QWORD *)(*((_QWORD *)this + 75) + 56LL)
        && v15 == *(_QWORD *)(*((_QWORD *)this + 76) + 56LL)
        && (_DWORD)v15 == *(_DWORD *)(*((_QWORD *)this + 77) + 192LL)
        && v15 == *(_QWORD *)(*((_QWORD *)this + 78) + 128LL) )
      {
        v3 = 0;
      }
      if ( v3 )
      {
        v16 = std::to_string(v95, *(_QWORD *)(*((_QWORD *)this + 78) + 128LL));
        v17 = std::to_string(v94, *(unsigned int *)(*((_QWORD *)this + 77) + 192LL));
        v18 = std::to_string(v93, *(_QWORD *)(*((_QWORD *)this + 76) + 56LL));
        v19 = std::to_string(v92, *(_QWORD *)(*((_QWORD *)this + 75) + 56LL));
        v20 = std::to_string(v91, *(_QWORD *)(*((_QWORD *)this + 73) + 56LL));
        v21 = std::string::string(v90, "LampCount logical max is not the same across reports.");
        v22 = std::operator+<char>(v89, v21, " LampArrayAttributes:");
        v23 = std::operator+<char>(v88, v22, v20);
        v24 = std::operator+<char>(v87, v23, ", LampAttributesRequest:");
        v25 = std::operator+<char>(v101, v24, v19);
        v26 = std::operator+<char>(v100, v25, ", LampAttributesResponse:");
        v27 = std::operator+<char>(v99, v26, v18);
        v28 = std::operator+<char>(v98, v27, ", LampMultiUpdate:");
        v29 = std::operator+<char>(v96, v28, v17);
        v30 = std::operator+<char>(v97, v29, ", LampRangeUpdate:");
        std::operator+<char>(v86, v30, v16);
        std::string::~string(v97);
        std::string::~string(v96);
        std::string::~string(v98);
        std::string::~string(v99);
        std::string::~string(v100);
        std::string::~string(v101);
        std::string::~string(v87);
        std::string::~string(v88);
        std::string::~string(v89);
        std::string::~string(v90);
        std::string::~string(v91);
        std::string::~string(v92);
        std::string::~string(v93);
        std::string::~string(v94);
        std::string::~string(v95);
        LampArrayTelemetry::GetInstance();
        LampArrayTelemetry::LogLampArrayHidReportFailure(
          v31,
          (unsigned int)v86,
          -2147024809,
          (_DWORD)this + 24,
          *((_WORD *)this + 269),
          *((_WORD *)this + 270),
          *((_WORD *)this + 271));
        v32 = 911;
      }
      else
      {
        v33 = (unsigned __int8 *)*((_QWORD *)this + 76);
        v34 = v33[632];
        v35 = (_DWORD *)*((_QWORD *)this + 77);
        if ( (_DWORD)v34 == v35[56] && (v36 = (_QWORD *)*((_QWORD *)this + 78), v34 == v36[34]) )
        {
          v37 = v33[704];
          if ( (_DWORD)v37 == v35[64] && v37 == v36[43] )
          {
            v38 = v33[776];
            if ( (_DWORD)v38 == v35[72] && v38 == v36[52] )
            {
              v39 = v33[848];
              if ( (_DWORD)v39 == v35[80] && v39 == v36[61] )
              {
                std::vector<unsigned char>::_Tidy(&v83);
                return 0;
              }
              v41 = std::to_string(v87, v36[61]);
              v42 = std::to_string(v88, *(unsigned int *)(*((_QWORD *)this + 77) + 320LL));
              v43 = std::to_string(v89, *(_QWORD *)(*((_QWORD *)this + 76) + 848LL));
              v44 = std::string::string(v90, "GainChannel logical max is not the same across reports.");
              v45 = std::operator+<char>(v91, v44, " LampAttributesResponse:");
              v46 = std::operator+<char>(v92, v45, v43);
              v47 = std::operator+<char>(v93, v46, ", LampMultiUpdate:");
              v48 = std::operator+<char>(v94, v47, v42);
              v49 = std::operator+<char>(v95, v48, ", LampRangeUpdate:");
              std::operator+<char>(v86, v49, v41);
              std::string::~string(v95);
              std::string::~string(v94);
              std::string::~string(v93);
              std::string::~string(v92);
              std::string::~string(v91);
              std::string::~string(v90);
              std::string::~string(v89);
              std::string::~string(v88);
              std::string::~string(v87);
              LampArrayTelemetry::GetInstance();
              LampArrayTelemetry::LogLampArrayHidReportFailure(
                v50,
                (unsigned int)v86,
                -2147024809,
                (_DWORD)this + 24,
                *((_WORD *)this + 269),
                *((_WORD *)this + 270),
                *((_WORD *)this + 271));
              v32 = 1003;
            }
            else
            {
              v51 = std::to_string(v87, v36[52]);
              v52 = std::to_string(v88, *(unsigned int *)(*((_QWORD *)this + 77) + 288LL));
              v53 = std::to_string(v89, *(_QWORD *)(*((_QWORD *)this + 76) + 776LL));
              v54 = std::string::string(v90, "BlueChannel logical max is not the same across reports.");
              v55 = std::operator+<char>(v91, v54, " LampAttributesResponse:");
              v56 = std::operator+<char>(v92, v55, v53);
              v57 = std::operator+<char>(v93, v56, ", LampMultiUpdate:");
              v58 = std::operator+<char>(v94, v57, v52);
              v59 = std::operator+<char>(v95, v58, ", LampRangeUpdate:");
              std::operator+<char>(v86, v59, v51);
              std::string::~string(v95);
              std::string::~string(v94);
              std::string::~string(v93);
              std::string::~string(v92);
              std::string::~string(v91);
              std::string::~string(v90);
              std::string::~string(v89);
              std::string::~string(v88);
              std::string::~string(v87);
              LampArrayTelemetry::GetInstance();
              LampArrayTelemetry::LogLampArrayHidReportFailure(
                v60,
                (unsigned int)v86,
                -2147024809,
                (_DWORD)this + 24,
                *((_WORD *)this + 269),
                *((_WORD *)this + 270),
                *((_WORD *)this + 271));
              v32 = 980;
            }
          }
          else
          {
            v61 = std::to_string(v87, v36[43]);
            v62 = std::to_string(v88, *(unsigned int *)(*((_QWORD *)this + 77) + 256LL));
            v63 = std::to_string(v89, *(_QWORD *)(*((_QWORD *)this + 76) + 704LL));
            v64 = std::string::string(v90, "GreenChannel logical max is not the same across reports.");
            v65 = std::operator+<char>(v91, v64, " LampAttributesResponse:");
            v66 = std::operator+<char>(v92, v65, v63);
            v67 = std::operator+<char>(v93, v66, ", LampMultiUpdate:");
            v68 = std::operator+<char>(v94, v67, v62);
            v69 = std::operator+<char>(v95, v68, ", LampRangeUpdate:");
            std::operator+<char>(v86, v69, v61);
            std::string::~string(v95);
            std::string::~string(v94);
            std::string::~string(v93);
            std::string::~string(v92);
            std::string::~string(v91);
            std::string::~string(v90);
            std::string::~string(v89);
            std::string::~string(v88);
            std::string::~string(v87);
            LampArrayTelemetry::GetInstance();
            LampArrayTelemetry::LogLampArrayHidReportFailure(
              v70,
              (unsigned int)v86,
              -2147024809,
              (_DWORD)this + 24,
              *((_WORD *)this + 269),
              *((_WORD *)this + 270),
              *((_WORD *)this + 271));
            v32 = 957;
          }
        }
        else
        {
          v71 = std::to_string(v87, *(_QWORD *)(*((_QWORD *)this + 78) + 272LL));
          v72 = std::to_string(v88, *(unsigned int *)(*((_QWORD *)this + 77) + 224LL));
          v73 = std::to_string(v89, *(_QWORD *)(*((_QWORD *)this + 76) + 632LL));
          v74 = std::string::string(v90, "RedChannel logical max is not the same across reports.");
          v75 = std::operator+<char>(v91, v74, " LampAttributesResponse:");
          v76 = std::operator+<char>(v92, v75, v73);
          v77 = std::operator+<char>(v93, v76, ", LampMultiUpdate:");
          v78 = std::operator+<char>(v94, v77, v72);
          v79 = std::operator+<char>(v95, v78, ", LampRangeUpdate:");
          std::operator+<char>(v86, v79, v71);
          std::string::~string(v95);
          std::string::~string(v94);
          std::string::~string(v93);
          std::string::~string(v92);
          std::string::~string(v91);
          std::string::~string(v90);
          std::string::~string(v89);
          std::string::~string(v88);
          std::string::~string(v87);
          LampArrayTelemetry::GetInstance();
          LampArrayTelemetry::LogLampArrayHidReportFailure(
            v80,
            (unsigned int)v86,
            -2147024809,
            (_DWORD)this + 24,
            *((_WORD *)this + 269),
            *((_WORD *)this + 270),
            *((_WORD *)this + 271));
          v32 = 934;
        }
      }
      v81 = (const char *)v86;
      if ( v86[3] > (char *)0xF )
        v81 = v86[0];
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v32,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
        (const char *)0x80070057LL,
        (int)"%hs",
        v81);
      std::string::~string(v86);
    }
    else
    {
      while ( 1 )
      {
        if ( v7 == *(_BYTE *)(v10 + v8) )
        {
          v11 = std::to_string(v97, v7);
          v12 = std::string::string(v96, "One or more LampArray HID reports have duplicate IDs: ");
          std::operator+<char>(v86, v12, v11);
          std::string::~string(v96);
          std::string::~string(v97);
          LampArrayTelemetry::GetInstance();
          LampArrayTelemetry::LogLampArrayHidReportFailure(
            v13,
            (unsigned int)v86,
            -2147024809,
            (_DWORD)this + 24,
            *((_WORD *)this + 269),
            *((_WORD *)this + 270),
            *((_WORD *)this + 271));
          std::string::~string(v86);
          v9 = *((_QWORD *)&v83 + 1);
          v10 = v83;
        }
        v14 = *(_BYTE *)(v10 + v8);
        if ( v7 == v14 )
          break;
        if ( ++v8 >= (unsigned __int64)(v9 - v10) )
          goto LABEL_17;
        v7 = v14;
      }
      LODWORD(v82) = v7;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
        (const char *)0x80070057LL,
        (int)"Reports have duplicate Id:%d",
        v82);
    }
    std::vector<unsigned char>::_Tidy(&v83);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18012a2ec  push    rbp
0x18012a2ee  push    rbx
0x18012a2ef  push    rsi
0x18012a2f0  push    rdi
0x18012a2f1  push    r12
0x18012a2f3  push    r13
0x18012a2f5  push    r14
0x18012a2f7  push    r15
0x18012a2f9  lea     rbp, [rsp-198h]
0x18012a301  sub     rsp, 298h
0x18012a308  mov     rax, cs:__security_cookie
0x18012a30f  xor     rax, rsp
0x18012a312  mov     [rbp+1D0h+var_50], rax
0x18012a319  mov     r13, rcx
0x18012a31c  mov     rcx, [rcx+248h]
0x18012a323  mov     esi, 1
0x18012a328  xor     ebx, ebx
0x18012a32a  test    rcx, rcx
0x18012a32d  jz      short loc_18012A35E
0x18012a32f  cmp     [r13+250h], rbx
0x18012a336  jz      short loc_18012A35E
0x18012a338  cmp     [r13+258h], rbx
0x18012a33f  jz      short loc_18012A35E
0x18012a341  cmp     [r13+260h], rbx
0x18012a348  jz      short loc_18012A35E
0x18012a34a  cmp     [r13+268h], rbx
0x18012a351  jz      short loc_18012A35E
0x18012a353  cmp     [r13+270h], rbx
0x18012a35a  mov     al, bl
0x18012a35c  jnz     short loc_18012A361
0x18012a35e  mov     al, sil
0x18012a361  test    al, al
0x18012a363  jz      loc_18012A403
0x18012a369  mov     r11d, ebx
0x18012a36c  cmp     [r13+270h], rbx
0x18012a373  setz    r11b
0x18012a377  mov     r10d, ebx
0x18012a37a  cmp     [r13+268h], rbx
0x18012a381  setz    r10b
0x18012a385  mov     r9d, ebx
0x18012a388  cmp     [r13+260h], rbx
0x18012a38f  setz    r9b
0x18012a393  mov     r8d, ebx
0x18012a396  cmp     [r13+258h], rbx
0x18012a39d  setz    r8b
0x18012a3a1  mov     edx, ebx
0x18012a3a3  cmp     [r13+250h], rbx
0x18012a3aa  setz    dl
0x18012a3ad  mov     eax, ebx
0x18012a3af  test    rcx, rcx
0x18012a3b2  setz    al
0x18012a3b5  mov     rcx, [rbp+1D8h]; this
0x18012a3bc  mov     [rsp+2D0h+var_280], r11d
0x18012a3c1  mov     [rsp+2D0h+var_288], r10d
0x18012a3c6  mov     [rsp+2D0h+var_290], r9d
0x18012a3cb  mov     [rsp+2D0h+var_298], r8d
0x18012a3d0  mov     [rsp+2D0h+var_2A0], edx
0x18012a3d4  mov     dword ptr [rsp+2D0h+var_2A8], eax; char *
0x18012a3d8  lea     rax, aOneOrMoreRepor; "One or more ReportParsers are null.  La"...
0x18012a3df  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18012a3e4  mov     r12d, 80070057h
0x18012a3ea  mov     r9d, r12d; char *
0x18012a3ed  lea     r8, aOnecoreuapWind_174; "onecoreuap\\windows\\moderncore\\inputv"...
0x18012a3f4  mov     edx, 354h; void *
0x18012a3f9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012a3fe  jmp     loc_18012AEC4
0x18012a403  xorps   xmm0, xmm0
0x18012a406  movdqu  [rsp+2D0h+var_270], xmm0
0x18012a40c  mov     [rsp+2D0h+var_260], rbx
0x18012a411  lea     rcx, [rsp+2D0h+var_270]
0x18012a416  call    ?_Buy_raw@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_raw(unsigned __int64)
0x18012a41b  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a420  xor     ecx, ecx
0x18012a422  mov     [rax], ecx
0x18012a424  mov     [rax+4], cx
0x18012a428  add     rax, 6
0x18012a42c  mov     qword ptr [rsp+2D0h+var_270+8], rax
0x18012a431  mov     [rsp+2D0h+var_258], rbx
0x18012a436  lea     rcx, [rsp+2D0h+var_258]
0x18012a43b  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18012a440  mov     rax, [r13+248h]
0x18012a447  mov     cl, [rax+10h]
0x18012a44a  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a44f  mov     [rax], cl
0x18012a451  mov     rax, [r13+250h]
0x18012a458  mov     cl, [rax+10h]
0x18012a45b  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a460  mov     [rax+1], cl
0x18012a463  mov     rax, [r13+258h]
0x18012a46a  mov     cl, [rax+10h]
0x18012a46d  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a472  mov     [rax+2], cl
0x18012a475  mov     rax, [r13+260h]
0x18012a47c  mov     cl, [rax+10h]
0x18012a47f  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a484  mov     [rax+3], cl
0x18012a487  mov     rax, [r13+268h]
0x18012a48e  mov     cl, [rax+10h]
0x18012a491  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a496  mov     [rax+4], cl
0x18012a499  mov     rax, [r13+270h]
0x18012a4a0  mov     cl, [rax+10h]
0x18012a4a3  mov     rax, qword ptr [rsp+2D0h+var_270]
0x18012a4a8  mov     [rax+5], cl
0x18012a4ab  mov     rdx, qword ptr [rsp+2D0h+var_270+8]
0x18012a4b0  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18012a4b5  mov     r9b, bl
0x18012a4b8  mov     r8, rdx
0x18012a4bb  sub     r8, rcx
0x18012a4be  call    ??$_Sort_unchecked@PEAEU?$less@X@std@@@std@@YAXPEAE0_JU?$less@X@0@@Z; std::_Sort_unchecked<uchar *,std::less<void>>(uchar *,uchar *,__int64,std::less<void>)
0x18012a4c3  mov     r14b, bl
0x18012a4c6  mov     rdi, rbx
0x18012a4c9  mov     rdx, qword ptr [rsp+2D0h+var_270+8]
0x18012a4ce  mov     r12d, 80070057h
0x18012a4d4  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18012a4d9  cmp     rdx, rcx
0x18012a4dc  jz      loc_18012A5DD
0x18012a4e2  movzx   r15d, r14b
0x18012a4e6  cmp     r14b, [rcx+rdi]
0x18012a4ea  jnz     loc_18012A58B
0x18012a4f0  mov     edx, r15d
0x18012a4f3  lea     rcx, [rbp+1D0h+var_F0]
0x18012a4fa  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x18012a4ff  mov     rbx, rax
0x18012a502  lea     rdx, aOneOrMoreLampa; "One or more LampArray HID reports have "...
0x18012a509  lea     rcx, [rbp+1D0h+var_110]
0x18012a510  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18012a515  mov     r8, rbx
0x18012a518  mov     rdx, rax
0x18012a51b  lea     rcx, [rbp+1D0h+var_250]
0x18012a51f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18012a524  lea     rcx, [rbp+1D0h+var_110]
0x18012a52b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a530  lea     rcx, [rbp+1D0h+var_F0]
0x18012a537  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a53c  call    ?GetInstance@LampArrayTelemetry@@SAPEAV1@XZ; LampArrayTelemetry::GetInstance(void)
0x18012a541  lea     r9, [r13+18h]
0x18012a545  movzx   eax, word ptr [r13+21Eh]
0x18012a54d  mov     word ptr [rsp+2D0h+var_2A0], ax
0x18012a552  movzx   eax, word ptr [r13+21Ch]
0x18012a55a  mov     word ptr [rsp+2D0h+var_2A8], ax
0x18012a55f  movzx   eax, word ptr [r13+21Ah]
0x18012a567  mov     word ptr [rsp+2D0h+var_2B0], ax
0x18012a56c  mov     r8d, r12d
0x18012a56f  lea     rdx, [rbp+1D0h+var_250]
0x18012a573  call    ?LogLampArrayHidReportFailure@LampArrayTelemetry@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JPEBGGGG@Z; LampArrayTelemetry::LogLampArrayHidReportFailure(std::string const &,long,ushort const *,ushort,ushort,ushort)
0x18012a578  lea     rcx, [rbp+1D0h+var_250]
0x18012a57c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a581  mov     rdx, qword ptr [rsp+2D0h+var_270+8]
0x18012a586  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18012a58b  mov     r8b, [rcx+rdi]
0x18012a58f  cmp     r14b, r8b
0x18012a592  jz      short loc_18012A5AA
0x18012a594  add     rdi, rsi
0x18012a597  mov     rax, rdx
0x18012a59a  sub     rax, rcx
0x18012a59d  cmp     rdi, rax
0x18012a5a0  jnb     short loc_18012A5DB
0x18012a5a2  mov     r14b, r8b
0x18012a5a5  jmp     loc_18012A4E2
0x18012a5aa  mov     rcx, [rbp+1D8h]; this
0x18012a5b1  mov     dword ptr [rsp+2D0h+var_2A8], r15d; char *
0x18012a5b6  lea     rax, aReportsHaveDup; "Reports have duplicate Id:%d"
0x18012a5bd  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18012a5c2  mov     r9d, r12d; char *
0x18012a5c5  lea     r8, aOnecoreuapWind_174; "onecoreuap\\windows\\moderncore\\inputv"...
0x18012a5cc  mov     edx, 371h; void *
0x18012a5d1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18012a5d6  jmp     loc_18012AEBA
0x18012a5db  xor     ebx, ebx
0x18012a5dd  mov     rax, [r13+248h]
0x18012a5e4  movsxd  rdx, dword ptr [rax+38h]
0x18012a5e8  mov     rax, [r13+258h]
0x18012a5ef  cmp     rdx, [rax+38h]
0x18012a5f3  jnz     short loc_18012A624
0x18012a5f5  mov     rax, [r13+260h]
0x18012a5fc  cmp     rdx, [rax+38h]
0x18012a600  jnz     short loc_18012A624
0x18012a602  mov     rax, [r13+268h]
0x18012a609  cmp     edx, [rax+0C0h]
0x18012a60f  jnz     short loc_18012A624
0x18012a611  mov     rax, [r13+270h]
0x18012a618  cmp     rdx, [rax+80h]
0x18012a61f  jnz     short loc_18012A624
0x18012a621  mov     sil, bl
0x18012a624  test    sil, sil
0x18012a627  jz      loc_18012A85C
0x18012a62d  mov     rdx, [r13+270h]
0x18012a634  mov     rdx, [rdx+80h]
0x18012a63b  lea     rcx, [rbp+1D0h+var_130]
0x18012a642  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J@Z; std::to_string(__int64)
0x18012a647  mov     r15, rax
0x18012a64a  mov     rdx, [r13+268h]
0x18012a651  mov     edx, [rdx+0C0h]
0x18012a657  lea     rcx, [rbp+1D0h+var_150]
0x18012a65e  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x18012a663  mov     r14, rax
0x18012a666  mov     rdx, [r13+260h]
0x18012a66d  mov     rdx, [rdx+38h]
0x18012a671  lea     rcx, [rbp+1D0h+var_170]
0x18012a675  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J@Z; std::to_string(__int64)
0x18012a67a  mov     rsi, rax
0x18012a67d  mov     rdx, [r13+258h]
0x18012a684  mov     rdx, [rdx+38h]
0x18012a688  lea     rcx, [rbp+1D0h+var_190]
0x18012a68c  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J@Z; std::to_string(__int64)
0x18012a691  mov     rdi, rax
0x18012a694  mov     rdx, [r13+248h]
0x18012a69b  mov     rdx, [rdx+38h]
0x18012a69f  lea     rcx, [rbp+1D0h+var_1B0]
0x18012a6a3  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J@Z; std::to_string(__int64)
0x18012a6a8  mov     rbx, rax
0x18012a6ab  lea     rdx, aLampcountLogic; "LampCount logical max is not the same a"...
0x18012a6b2  lea     rcx, [rbp+1D0h+var_1D0]
0x18012a6b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18012a6bb  mov     rdx, rax
0x18012a6be  lea     r8, aLamparrayattri_0; " LampArrayAttributes:"
0x18012a6c5  lea     rcx, [rbp+1D0h+var_1F0]
0x18012a6c9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18012a6ce  mov     r8, rbx
0x18012a6d1  mov     rdx, rax
0x18012a6d4  lea     rcx, [rbp+1D0h+var_210]
0x18012a6d8  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18012a6dd  mov     rdx, rax
0x18012a6e0  lea     r8, aLampattributes_1; ", LampAttributesRequest:"
0x18012a6e7  lea     rcx, [rbp+1D0h+var_230]
0x18012a6eb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18012a6f0  mov     r8, rdi
0x18012a6f3  mov     rdx, rax
0x18012a6f6  lea     rcx, [rbp+1D0h+var_70]
0x18012a6fd  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18012a702  mov     rdx, rax
0x18012a705  lea     r8, aLampattributes_0; ", LampAttributesResponse:"
0x18012a70c  lea     rcx, [rbp+1D0h+var_90]
0x18012a713  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18012a718  mov     r8, rsi
0x18012a71b  mov     rdx, rax
0x18012a71e  lea     rcx, [rbp+1D0h+var_B0]
0x18012a725  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18012a72a  mov     rdx, rax
0x18012a72d  lea     r8, aLampmultiupdat_4; ", LampMultiUpdate:"
0x18012a734  lea     rcx, [rbp+1D0h+var_D0]
0x18012a73b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18012a740  mov     r8, r14
0x18012a743  mov     rdx, rax
0x18012a746  lea     rcx, [rbp+1D0h+var_110]
0x18012a74d  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18012a752  mov     rdx, rax
0x18012a755  lea     r8, aLamprangeupdat_2; ", LampRangeUpdate:"
0x18012a75c  lea     rcx, [rbp+1D0h+var_F0]
0x18012a763  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18012a768  mov     r8, r15
0x18012a76b  mov     rdx, rax
0x18012a76e  lea     rcx, [rbp+1D0h+var_250]
0x18012a772  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18012a777  lea     rcx, [rbp+1D0h+var_F0]
0x18012a77e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a783  lea     rcx, [rbp+1D0h+var_110]
0x18012a78a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a78f  lea     rcx, [rbp+1D0h+var_D0]
0x18012a796  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a79b  lea     rcx, [rbp+1D0h+var_B0]
0x18012a7a2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7a7  lea     rcx, [rbp+1D0h+var_90]
0x18012a7ae  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7b3  lea     rcx, [rbp+1D0h+var_70]
0x18012a7ba  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7bf  lea     rcx, [rbp+1D0h+var_230]
0x18012a7c3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7c8  lea     rcx, [rbp+1D0h+var_210]
0x18012a7cc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7d1  lea     rcx, [rbp+1D0h+var_1F0]
0x18012a7d5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7da  lea     rcx, [rbp+1D0h+var_1D0]
0x18012a7de  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7e3  lea     rcx, [rbp+1D0h+var_1B0]
0x18012a7e7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7ec  lea     rcx, [rbp+1D0h+var_190]
0x18012a7f0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7f5  lea     rcx, [rbp+1D0h+var_170]
0x18012a7f9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a7fe  lea     rcx, [rbp+1D0h+var_150]
0x18012a805  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a80a  lea     rcx, [rbp+1D0h+var_130]
0x18012a811  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18012a816  call    ?GetInstance@LampArrayTelemetry@@SAPEAV1@XZ; LampArrayTelemetry::GetInstance(void)
0x18012a81b  lea     r9, [r13+18h]
0x18012a81f  movzx   eax, word ptr [r13+21Eh]
0x18012a827  mov     word ptr [rsp+2D0h+var_2A0], ax
0x18012a82c  movzx   eax, word ptr [r13+21Ch]
0x18012a834  mov     word ptr [rsp+2D0h+var_2A8], ax
0x18012a839  movzx   eax, word ptr [r13+21Ah]
0x18012a841  mov     word ptr [rsp+2D0h+var_2B0], ax
0x18012a846  mov     r8d, r12d
0x18012a849  lea     rdx, [rbp+1D0h+var_250]
0x18012a84d  call    ?LogLampArrayHidReportFailure@LampArrayTelemetry@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JPEBGGGG@Z; LampArrayTelemetry::LogLampArrayHidReportFailure(std::string const &,long,ushort const *,ushort,ushort,ushort)
0x18012a852  mov     edx, 38Fh
0x18012a857  jmp     loc_18012AE7C
0x18012a85c  mov     rcx, [r13+260h]
0x18012a863  movzx   eax, byte ptr [rcx+278h]
  ... truncated ...
```
