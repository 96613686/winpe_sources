# Microsoft::IoT::ShellExtension::CCBTLauncher::ReLaunch(Microsoft::IoT::ShellExtension::CCBT &)

- ea: `0x180012f10`
- end: `0x18001327e`
- name: `?ReLaunch@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXAEAVCCBT@234@@Z`
- size: `878`
- prototype: `void(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this, struct Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800114f0`
- `0x180012c00`

## callees

- `0x180002b10`
- `0x18000357c`
- `0x180008358`
- `0x18000acf4`
- `0x18000f120`
- `0x18000f58c`
- `0x18000f968`
- `0x18000fe38`
- `0x180010100`
- `0x180011068`
- `0x180012f10`
- `0x1800150c0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012f8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012f8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::ReLaunch(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        struct Microsoft::IoT::ShellExtension::CCBT *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rsi
  float v7; // xmm0_4
  float v8; // xmm0_4
  unsigned __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // rbx
  __int64 v12; // rsi
  float v13; // xmm0_4
  float v14; // xmm0_4
  unsigned __int64 v15; // rax
  int v16; // ebx
  __int64 v17; // rsi
  __int64 v18; // rdi
  float v19; // xmm0_4
  float v20; // xmm0_4
  unsigned __int64 v21; // rax
  unsigned int v22; // eax
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  void *v25[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v26; // [rsp+40h] [rbp-C0h]
  int v27[2]; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v28; // [rsp+7Ch] [rbp-84h]
  _BYTE v29[8]; // [rsp+90h] [rbp-70h] BYREF
  void *v30[11]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[8]; // [rsp+F0h] [rbp-10h] BYREF
  void *v32; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6)) )
  {
    if ( Microsoft::IoT::ShellExtension::CCBT::CheckFailure(a2) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (void **)a2 + 6,
        0);
      *((_DWORD *)a2 + 14) = -2147483638;
      *((_QWORD *)a2 + 1) = GetTickCount64();
      *(GUID *)((char *)a2 + 60) = GUID_NULL;
      std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(
        (__int64)this + 136,
        (__int64)a2);
      Microsoft::IoT::ShellExtension::CCBT::CCBT(
        (Microsoft::IoT::ShellExtension::CCBT *)v25,
        (const struct Microsoft::IoT::ShellExtension::CCBT *)(*((_QWORD *)this + 18) - 88LL));
      *(_QWORD *)v23 = *(_QWORD *)v27;
      v4 = (__int64)v26;
      if ( v26 )
        v4 = *v26;
      v24 = v4;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskReactivation<unsigned short *,unsigned short *>(
        &v24,
        (__int64 *)v23);
      v5 = *((_QWORD *)this + 9);
      v6 = lambda_c03daee19112fcf77f71079884cb6bd0_::_lambda_c03daee19112fcf77f71079884cb6bd0_(v29, this, v25);
      if ( qword_1800262E8 < 0 )
        v7 = (float)(qword_1800262E8 & 1 | (unsigned int)((unsigned __int64)qword_1800262E8 >> 1))
           + (float)(qword_1800262E8 & 1 | (unsigned int)((unsigned __int64)qword_1800262E8 >> 1));
      else
        v7 = (float)(int)qword_1800262E8;
      v8 = powf(v7, (float)((float)dword_1800262F4 / (float)dword_1800262F8) * (float)(v28 - 1));
      v9 = 0;
      if ( v8 >= 9.223372e18 )
      {
        v8 = v8 - 9.223372e18;
        if ( v8 < 9.223372e18 )
          v9 = 0x8000000000000000uLL;
      }
      v10 = Microsoft::IoT::Utility::MTAThreadPool::QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___(
              v5,
              qword_1800262E0 + v9 + (unsigned int)(int)v8,
              v6);
      Microsoft::IoT::ShellExtension::CCBT::~CCBT(v30);
      if ( v10 < 0 )
      {
        v11 = *((_QWORD *)this + 9);
        v12 = lambda_c03daee19112fcf77f71079884cb6bd0_::_lambda_c03daee19112fcf77f71079884cb6bd0_(v31, this, v25);
        if ( qword_1800262E8 < 0 )
          v13 = (float)(qword_1800262E8 & 1 | (unsigned int)((unsigned __int64)qword_1800262E8 >> 1))
              + (float)(qword_1800262E8 & 1 | (unsigned int)((unsigned __int64)qword_1800262E8 >> 1));
        else
          v13 = (float)(int)qword_1800262E8;
        v14 = powf(v13, (float)((float)dword_1800262F4 / (float)dword_1800262F8) * (float)(v28 - 1));
        v15 = 0;
        if ( v14 >= 9.223372e18 )
        {
          v14 = v14 - 9.223372e18;
          if ( v14 < 9.223372e18 )
            v15 = 0x8000000000000000uLL;
        }
        v16 = Microsoft::IoT::Utility::MTAThreadPool::QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___(
                v11,
                qword_1800262E0 + v15 + (unsigned int)(int)v14,
                v12);
        v17 = *((_QWORD *)this + 9);
        v18 = lambda_c03daee19112fcf77f71079884cb6bd0_::_lambda_c03daee19112fcf77f71079884cb6bd0_(v29, this, v25);
        if ( qword_1800262E8 < 0 )
          v19 = (float)(qword_1800262E8 & 1 | (unsigned int)((unsigned __int64)qword_1800262E8 >> 1))
              + (float)(qword_1800262E8 & 1 | (unsigned int)((unsigned __int64)qword_1800262E8 >> 1));
        else
          v19 = (float)(int)qword_1800262E8;
        v20 = powf(v19, (float)((float)dword_1800262F4 / (float)dword_1800262F8) * (float)(v28 - 1));
        v21 = 0;
        if ( v20 >= 9.223372e18 )
        {
          v20 = v20 - 9.223372e18;
          if ( v20 < 9.223372e18 )
            v21 = 0x8000000000000000uLL;
        }
        v22 = Microsoft::IoT::Utility::MTAThreadPool::QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___(
                v17,
                qword_1800262E0 + v21 + (unsigned int)(int)v20,
                v18);
        if ( v16 != -2147023781 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x121,
            (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
            (const char *)v22,
            v23[0]);
        Microsoft::IoT::ShellExtension::CCBT::~CCBT(v30);
        Microsoft::IoT::ShellExtension::CCBT::~CCBT(&v32);
      }
      Microsoft::IoT::ShellExtension::CCBT::~CCBT(v25);
    }
  }
}

```

## disassembly

```asm
0x180012f10  mov     rax, rsp
0x180012f13  mov     [rax+18h], rbx
0x180012f17  mov     [rax+20h], rsi
0x180012f1b  push    rbp
0x180012f1c  push    rdi
0x180012f1d  push    r14
0x180012f1f  lea     rbp, [rsp-70h]
0x180012f24  sub     rsp, 170h
0x180012f2b  movaps  xmmword ptr [rax-28h], xmm6
0x180012f2f  mov     rax, cs:__security_cookie
0x180012f36  xor     rax, rsp
0x180012f39  mov     [rbp+80h+var_30], rax
0x180012f3d  mov     rbx, rdx
0x180012f40  mov     rdi, rcx
0x180012f43  mov     rcx, [rcx+30h]
0x180012f47  mov     rax, [rcx]
0x180012f4a  mov     rax, [rax+18h]
0x180012f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f53  test    al, al
0x180012f55  jnz     loc_180013255
0x180012f5b  mov     rcx, rbx; this
0x180012f5e  call    ?CheckFailure@CCBT@ShellExtension@IoT@Microsoft@@QEAA_NXZ; Microsoft::IoT::ShellExtension::CCBT::CheckFailure(void)
0x180012f63  test    al, al
0x180012f65  jz      short loc_180012F7C
0x180012f67  mov     rcx, [rdi+30h]
0x180012f6b  mov     rax, [rcx]
0x180012f6e  mov     rax, [rax+20h]
0x180012f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f77  jmp     loc_180013255
0x180012f7c  lea     rcx, [rbx+30h]
0x180012f80  xor     edx, edx
0x180012f82  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180012f87  mov     dword ptr [rbx+38h], 8000000Ah
0x180012f8e  call    cs:__imp_GetTickCount64
0x180012f94  mov     [rbx+8], rax
0x180012f98  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180012f9f  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x180012fa4  lea     rcx, [rdi+88h]
0x180012fab  mov     rdx, rbx
0x180012fae  call    ??$_Emplace_one_at_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x180012fb3  mov     rdx, [rdi+90h]
0x180012fba  sub     rdx, 58h ; 'X'; struct Microsoft::IoT::ShellExtension::CCBT *
0x180012fbe  lea     rcx, [rsp+180h+var_150]; this
0x180012fc3  call    ??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT const &)
0x180012fc8  nop
0x180012fc9  mov     rax, qword ptr [rsp+180h+var_128]
0x180012fce  mov     qword ptr [rsp+180h+var_160], rax; int
0x180012fd3  mov     rax, [rsp+180h+var_140]
0x180012fd8  test    rax, rax
0x180012fdb  jz      short loc_180012FE0
0x180012fdd  mov     rax, [rax]
0x180012fe0  mov     [rsp+180h+var_158], rax
0x180012fe5  lea     rdx, [rsp+180h+var_160]
0x180012fea  lea     rcx, [rsp+180h+var_158]
0x180012fef  call    ??$BackgroundTaskReactivation@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskReactivation<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180012ff4  mov     rbx, [rdi+48h]
0x180012ff8  lea     r8, [rsp+180h+var_150]
0x180012ffd  mov     rdx, rdi
0x180013000  lea     rcx, [rbp+80h+var_F0]
0x180013004  call    _lambda_c03daee19112fcf77f71079884cb6bd0____lambda_c03daee19112fcf77f71079884cb6bd0_
0x180013009  mov     rsi, rax
0x18001300c  mov     rcx, cs:qword_1800262E8
0x180013013  xorps   xmm0, xmm0
0x180013016  test    rcx, rcx
0x180013019  js      short loc_180013022
0x18001301b  cvtsi2ss xmm0, rcx
0x180013020  jmp     short loc_180013037
0x180013022  mov     rax, rcx
0x180013025  shr     rax, 1
0x180013028  and     ecx, 1
0x18001302b  or      rax, rcx
0x18001302e  cvtsi2ss xmm0, rax
0x180013033  addss   xmm0, xmm0; X
0x180013037  mov     eax, cs:dword_1800262F4
0x18001303d  xorps   xmm1, xmm1
0x180013040  cvtsi2ss xmm1, rax
0x180013045  mov     eax, cs:dword_1800262F8
0x18001304b  xorps   xmm2, xmm2
0x18001304e  cvtsi2ss xmm2, rax
0x180013053  divss   xmm1, xmm2
0x180013057  movzx   eax, [rsp+180h+var_104]
0x18001305c  dec     eax
0x18001305e  movd    xmm2, eax
0x180013062  cvtdq2ps xmm2, xmm2
0x180013065  mulss   xmm1, xmm2; Y
0x180013069  call    powf
0x18001306e  xor     eax, eax
0x180013070  mov     r14, 8000000000000000h
0x18001307a  movss   xmm6, cs:__real@5f000000
0x180013082  comiss  xmm0, xmm6
0x180013085  jb      short loc_180013093
0x180013087  subss   xmm0, xmm6
0x18001308b  comiss  xmm0, xmm6
0x18001308e  jnb     short loc_180013093
0x180013090  mov     rax, r14
0x180013093  cvttss2si rdx, xmm0
0x180013098  add     rdx, rax
0x18001309b  add     rdx, cs:qword_1800262E0
0x1800130a2  mov     r8, rsi
0x1800130a5  mov     rcx, rbx
0x1800130a8  call    Microsoft__IoT__Utility__MTAThreadPool__QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___
0x1800130ad  mov     ebx, eax
0x1800130af  lea     rcx, [rbp+80h+var_E8]; this
0x1800130b3  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x1800130b8  shr     ebx, 1Fh
0x1800130bb  test    bl, bl
0x1800130bd  jz      loc_18001324B
0x1800130c3  mov     rbx, [rdi+48h]
0x1800130c7  lea     r8, [rsp+180h+var_150]
0x1800130cc  mov     rdx, rdi
0x1800130cf  lea     rcx, [rbp+80h+var_90]
0x1800130d3  call    _lambda_c03daee19112fcf77f71079884cb6bd0____lambda_c03daee19112fcf77f71079884cb6bd0_
0x1800130d8  mov     rsi, rax
0x1800130db  mov     rcx, cs:qword_1800262E8
0x1800130e2  xorps   xmm0, xmm0
0x1800130e5  test    rcx, rcx
0x1800130e8  js      short loc_1800130F1
0x1800130ea  cvtsi2ss xmm0, rcx
0x1800130ef  jmp     short loc_180013106
0x1800130f1  mov     rax, rcx
0x1800130f4  shr     rax, 1
0x1800130f7  and     ecx, 1
0x1800130fa  or      rax, rcx
0x1800130fd  cvtsi2ss xmm0, rax
0x180013102  addss   xmm0, xmm0; X
0x180013106  mov     eax, cs:dword_1800262F4
0x18001310c  xorps   xmm1, xmm1
0x18001310f  cvtsi2ss xmm1, rax
0x180013114  mov     eax, cs:dword_1800262F8
0x18001311a  xorps   xmm2, xmm2
0x18001311d  cvtsi2ss xmm2, rax
0x180013122  divss   xmm1, xmm2
0x180013126  movzx   eax, [rsp+180h+var_104]
0x18001312b  dec     eax
0x18001312d  movd    xmm2, eax
0x180013131  cvtdq2ps xmm2, xmm2
0x180013134  mulss   xmm1, xmm2; Y
0x180013138  call    powf
0x18001313d  xor     eax, eax
0x18001313f  comiss  xmm0, xmm6
0x180013142  jb      short loc_180013150
0x180013144  subss   xmm0, xmm6
0x180013148  comiss  xmm0, xmm6
0x18001314b  jnb     short loc_180013150
0x18001314d  mov     rax, r14
0x180013150  cvttss2si rdx, xmm0
0x180013155  add     rdx, rax
0x180013158  add     rdx, cs:qword_1800262E0
0x18001315f  mov     r8, rsi
0x180013162  mov     rcx, rbx
0x180013165  call    Microsoft__IoT__Utility__MTAThreadPool__QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___
0x18001316a  mov     ebx, eax
0x18001316c  mov     rsi, [rdi+48h]
0x180013170  lea     r8, [rsp+180h+var_150]
0x180013175  mov     rdx, rdi
0x180013178  lea     rcx, [rbp+80h+var_F0]
0x18001317c  call    _lambda_c03daee19112fcf77f71079884cb6bd0____lambda_c03daee19112fcf77f71079884cb6bd0_
0x180013181  mov     rdi, rax
0x180013184  mov     rcx, cs:qword_1800262E8
0x18001318b  xorps   xmm0, xmm0
0x18001318e  test    rcx, rcx
0x180013191  js      short loc_18001319A
0x180013193  cvtsi2ss xmm0, rcx
0x180013198  jmp     short loc_1800131AF
0x18001319a  mov     rax, rcx
0x18001319d  shr     rax, 1
0x1800131a0  and     ecx, 1
0x1800131a3  or      rax, rcx
0x1800131a6  cvtsi2ss xmm0, rax
0x1800131ab  addss   xmm0, xmm0; X
0x1800131af  mov     eax, cs:dword_1800262F4
0x1800131b5  xorps   xmm1, xmm1
0x1800131b8  cvtsi2ss xmm1, rax
0x1800131bd  mov     eax, cs:dword_1800262F8
0x1800131c3  xorps   xmm2, xmm2
0x1800131c6  cvtsi2ss xmm2, rax
0x1800131cb  divss   xmm1, xmm2
0x1800131cf  movzx   eax, [rsp+180h+var_104]
0x1800131d4  dec     eax
0x1800131d6  movd    xmm2, eax
0x1800131da  cvtdq2ps xmm2, xmm2
0x1800131dd  mulss   xmm1, xmm2; Y
0x1800131e1  call    powf
0x1800131e6  xor     eax, eax
0x1800131e8  comiss  xmm0, xmm6
0x1800131eb  jb      short loc_1800131F9
0x1800131ed  subss   xmm0, xmm6
0x1800131f1  comiss  xmm0, xmm6
0x1800131f4  jnb     short loc_1800131F9
0x1800131f6  mov     rax, r14
0x1800131f9  cvttss2si rdx, xmm0
0x1800131fe  add     rdx, rax
0x180013201  add     rdx, cs:qword_1800262E0
0x180013208  mov     r8, rdi
0x18001320b  mov     rcx, rsi
0x18001320e  call    Microsoft__IoT__Utility__MTAThreadPool__QueueDelayedLambda__lambda_c03daee19112fcf77f71079884cb6bd0___
0x180013213  mov     rcx, [rbp+88h]; this
0x18001321a  cmp     ebx, 8007045Bh
0x180013220  jz      short loc_180013237
0x180013222  mov     r9d, eax; char *
0x180013225  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18001322c  mov     edx, 121h; void *
0x180013231  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180013237  lea     rcx, [rbp+80h+var_E8]; this
0x18001323b  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x180013240  nop
0x180013241  lea     rcx, [rbp+80h+var_88]; this
0x180013245  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x18001324a  nop
0x18001324b  lea     rcx, [rsp+180h+var_150]; this
0x180013250  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x180013255  mov     rcx, [rbp+80h+var_30]
0x180013259  xor     rcx, rsp; StackCookie
0x18001325c  call    __security_check_cookie
0x180013261  lea     r11, [rsp+180h+var_10]
0x180013269  mov     rbx, [r11+30h]
0x18001326d  mov     rsi, [r11+38h]
0x180013271  movaps  xmm6, xmmword ptr [r11-10h]
0x180013276  mov     rsp, r11
0x180013279  pop     r14
0x18001327b  pop     rdi
0x18001327c  pop     rbp
0x18001327d  retn
```
