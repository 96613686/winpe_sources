# sub_1802FFEE0

- ea: `0x1802ffee0`
- end: `0x180300182`
- name: `sub_1802FFEE0`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180301260`

## callees

- `0x1801ad7d0`
- `0x1801ae334`
- `0x1801ae380`
- `0x1801df5ec`
- `0x1802145c0`
- `0x18028c720`
- `0x18028ccb0`
- `0x18028d360`
- `0x18028dff0`
- `0x1802946b0`
- `0x1802a31b0`
- `0x1802fdcf0`
- `0x1802ff550`
- `0x1802ffee0`
- `0x18037b520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1803000a0`
- `KERNEL32!GetLastError` at `0x1803000a0`
- `KERNEL32!CreateEventW` at `0x1802fff3b`
- `KERNEL32!CreateEventW` at `0x1802fff3b`
- `KERNEL32!WaitForSingleObject` at `0x180300096`
- `KERNEL32!WaitForSingleObject` at `0x180300096`

## string_xrefs

- `0x1802fff51`: `C:\__w\1\vcpkg\buildtrees\oneauth\src\07f7dcfee3-22beed4695.clean\msal\source\windows\broker\WAMSynchronousWrapper.cpp`
- `0x18030005d`: `C:\__w\1\vcpkg\buildtrees\oneauth\src\07f7dcfee3-22beed4695.clean\msal\source\windows\broker\WAMSynchronousWrapper.cpp`

## pseudocode

```c
_QWORD *__fastcall sub_1802FFEE0(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE EventW; // rdi
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rbx
  int v12; // eax
  int v13; // eax
  DWORD LastError; // [rsp+20h] [rbp-C8h]
  __int128 v16; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-A8h]
  int v18; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-98h] BYREF
  _QWORD v20[6]; // [rsp+58h] [rbp-90h] BYREF
  __int64 v21; // [rsp+88h] [rbp-60h] BYREF

  v20[2] = a1;
  v20[1] = a4;
  v18 = 1;
  sub_1801AE334(word_18064C612);
  sub_1802A31B0(509149975, a4);
  EventW = CreateEventW(0, 0, 0, 0);
  v20[3] = EventW;
  LODWORD(v16) = 346;
  *((_QWORD *)&v16 + 1) = "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth\\src\\07f7dcfee3-22beed4695.clean\\msal\\source\\window"
                          "s\\broker\\WAMSynchronousWrapper.cpp";
  v17 = 0;
  if ( !EventW )
    sub_1802946B0(&v16);
  *(_QWORD *)&v16 = EventW;
  *((_QWORD *)&v16 + 1) = a4;
  v9 = sub_1801AD7D0(32);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)(v9 + 8) = 1;
    *(_OWORD *)(v9 + 16) = v16;
    _InterlockedIncrement(&dword_1805FC348);
    *(_QWORD *)v9 = ___7__delegate_U__AsyncOperationCompletedHandler_UFindAllAccountsResult_Core_Web_Authentication_Security_Windows_winrt___Foundation_Windows_winrt__V_lambda_1___2__Abi_GetAllAccounts__A0xf07e5453_Msai__YA_AUFindAllAccountsResult_Core_Web_Authentication_Security_34_AEBUWebAccountProvider_Credentials_Security_34_AEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEBV__shared_ptr_VTelemetryInternal_Msai___std___Z__impl_winrt__6B_;
  }
  else
  {
    v10 = 0;
  }
  v20[0] = v10;
  v21 = *(_QWORD *)sub_18028DFF0(&v18, a3);
  *(_QWORD *)&v16 = a2;
  *((_QWORD *)&v16 + 1) = &v21;
  v20[4] = &qword_1805FC1C8;
  _InterlockedIncrement64(&qword_1805FC1C8);
  if ( qword_1805FC1C0 )
  {
    sub_1802FF550(&v16, &v19, &qword_1805FC1C0);
    _InterlockedDecrement64(&qword_1805FC1C8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1805FC1C8);
    sub_1802FDCF0(&qword_1805FC1C0, &v19, &v16);
  }
  sub_18028C720(&v18);
  sub_1802A31B0(509149976, a4);
  LODWORD(v16) = 364;
  *((_QWORD *)&v16 + 1) = "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth\\src\\07f7dcfee3-22beed4695.clean\\msal\\source\\window"
                          "s\\broker\\WAMSynchronousWrapper.cpp";
  v17 = 0;
  v11 = v19;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 48LL))(v19, v10);
  if ( v12 < 0 )
  {
    _mm_lfence();
    sub_18028CCB0((unsigned int)v12, &v16);
  }
  if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    sub_1802145C0(
      4,
      372,
      (unsigned int)"Abi_GetAllAccounts",
      (unsigned int)"WaitForSingleObject for ABI failed with error 0x%08lX",
      LastError);
    sub_1802A31B0(509122766, a4);
  }
  sub_1802A31B0(509149977, a4);
  _mm_lfence();
  *a1 = 0;
  v18 = 15;
  LODWORD(v16) = 377;
  *((_QWORD *)&v16 + 1) = "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth\\src\\07f7dcfee3-22beed4695.clean\\msal\\source\\window"
                          "s\\broker\\WAMSynchronousWrapper.cpp";
  v17 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v11 + 64LL))(v11, a1);
  _mm_lfence();
  if ( v13 < 0 )
    sub_18028CCB0((unsigned int)v13, &v16);
  if ( v11 )
    sub_18028D360(&v19);
  if ( v10 )
    sub_18028D360(v20);
  CloseHandle(EventW);
  return a1;
}

```

## disassembly

```asm
0x1802ffee0  push    rbx
0x1802ffee2  push    rsi
0x1802ffee3  push    rdi
0x1802ffee4  push    r12
0x1802ffee6  push    r13
0x1802ffee8  push    r14
0x1802ffeea  push    r15
0x1802ffeec  mov     eax, 0B0h
0x1802ffef1  call    __alloca_probe
0x1802ffef6  sub     rsp, rax
0x1802ffef9  mov     r14, r9
0x1802ffefc  mov     rbx, r8
0x1802ffeff  mov     r12, rdx
0x1802fff02  mov     r15, rcx
0x1802fff05  mov     [rsp+0E8h+var_80], rcx
0x1802fff0a  mov     [rsp+0E8h+var_88], r9
0x1802fff0f  mov     [rsp+0E8h+var_A0], 1
0x1802fff17  lea     rcx, word_18064C612
0x1802fff1e  call    sub_1801AE334
0x1802fff23  nop
0x1802fff24  mov     rdx, r14
0x1802fff27  mov     ecx, 1E590317h
0x1802fff2c  call    sub_1802A31B0
0x1802fff31  xor     r9d, r9d; lpName
0x1802fff34  xor     r8d, r8d; bInitialState
0x1802fff37  xor     edx, edx; bManualReset
0x1802fff39  xor     ecx, ecx; lpEventAttributes
0x1802fff3b  call    cs:__imp_CreateEventW
0x1802fff41  mov     rdi, rax
0x1802fff44  mov     [rsp+0E8h+var_78], rax
0x1802fff49  mov     dword ptr [rsp+0E8h+var_B8], 15Ah
0x1802fff51  lea     rax, aCW1VcpkgBuildt; "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth"...
0x1802fff58  mov     qword ptr [rsp+0E8h+var_B8+8], rax
0x1802fff5d  xor     r13d, r13d
0x1802fff60  mov     [rsp+0E8h+var_A8], r13
0x1802fff65  test    rdi, rdi
0x1802fff68  jz      loc_180300159
0x1802fff6e  mov     qword ptr [rsp+0E8h+var_B8], rdi
0x1802fff73  mov     qword ptr [rsp+0E8h+var_B8+8], r14
0x1802fff78  mov     ecx, 20h ; ' '
0x1802fff7d  call    sub_1801AD7D0
0x1802fff82  mov     rsi, rax
0x1802fff85  test    rax, rax
0x1802fff88  jz      short loc_1802FFFAD
0x1802fff8a  mov     dword ptr [rax+8], 1
0x1802fff91  movups  xmm0, [rsp+0E8h+var_B8]
0x1802fff96  movups  xmmword ptr [rax+10h], xmm0
0x1802fff9a  lock inc cs:dword_1805FC348
0x1802fffa1  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UFindAllAccountsResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@V_lambda_1_@?2??Abi_GetAllAccounts@?A0xf07e5453@Msai@@YA?AUFindAllAccountsResult@Core@Web@Authentication@Security@34@AEBUWebAccountProvider@Credentials@Security@34@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@VTelemetryInternal@Msai@@@std@@@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Authentication::Web::Core::FindAllAccountsResult>,`Msai::`anonymous namespace'::Abi_GetAllAccounts(winrt::Windows::Security::Credentials::WebAccountProvider const &,std::string const &,std::shared_ptr<Msai::TelemetryInternal> const &)'::`3'::_lambda_1_>::`vftable'
0x1802fffa8  mov     [rsi], rax
0x1802fffab  jmp     short loc_1802FFFB0
0x1802fffad  mov     rsi, r13
0x1802fffb0  mov     [rsp+0E8h+var_90], rsi
0x1802fffb5  mov     rdx, rbx
0x1802fffb8  lea     rcx, [rsp+0E8h+var_A0]
0x1802fffbd  call    sub_18028DFF0
0x1802fffc2  nop
0x1802fffc3  mov     rax, [rax]
0x1802fffc6  mov     [rsp+0E8h+var_60], rax
0x1802fffce  mov     qword ptr [rsp+0E8h+var_B8], r12
0x1802fffd3  lea     rax, [rsp+0E8h+var_60]
0x1802fffdb  mov     qword ptr [rsp+0E8h+var_B8+8], rax
0x1802fffe0  lea     rax, qword_1805FC1C8
0x1802fffe7  mov     [rsp+0E8h+var_70], rax
0x1802fffec  lock inc cs:qword_1805FC1C8
0x1802ffff4  cmp     cs:qword_1805FC1C0, 0
0x1802ffffc  jz      short loc_18030001F
0x1802ffffe  lea     r8, qword_1805FC1C0
0x180300005  lea     rdx, [rsp+0E8h+var_98]
0x18030000a  lea     rcx, [rsp+0E8h+var_B8]
0x18030000f  call    sub_1802FF550
0x180300014  nop
0x180300015  lock dec cs:qword_1805FC1C8
0x18030001d  jmp     short loc_18030003E
0x18030001f  lock dec cs:qword_1805FC1C8
0x180300027  lea     r8, [rsp+0E8h+var_B8]
0x18030002c  lea     rdx, [rsp+0E8h+var_98]
0x180300031  lea     rcx, qword_1805FC1C0
0x180300038  call    sub_1802FDCF0
0x18030003d  nop
0x18030003e  lea     rcx, [rsp+0E8h+var_A0]
0x180300043  call    sub_18028C720
0x180300048  mov     rdx, r14
0x18030004b  mov     ecx, 1E590318h
0x180300050  call    sub_1802A31B0
0x180300055  mov     dword ptr [rsp+0E8h+var_B8], 16Ch
0x18030005d  lea     r12, aCW1VcpkgBuildt; "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth"...
0x180300064  mov     qword ptr [rsp+0E8h+var_B8+8], r12
0x180300069  mov     [rsp+0E8h+var_A8], r13
0x18030006e  mov     rbx, [rsp+0E8h+var_98]
0x180300073  mov     rax, [rbx]
0x180300076  mov     rdx, rsi
0x180300079  mov     rcx, rbx
0x18030007c  mov     rax, [rax+30h]
0x180300080  call    cs:__guard_dispatch_icall_fptr
0x180300086  test    eax, eax
0x180300088  js      loc_180300164
0x18030008e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180300093  mov     rcx, rdi; hHandle
0x180300096  call    cs:__imp_WaitForSingleObject
0x18030009c  test    eax, eax
0x18030009e  jz      short loc_1803000D4
0x1803000a0  call    cs:__imp_GetLastError
0x1803000a6  mov     [rsp+0E8h+var_C8], eax
0x1803000aa  lea     r9, aWaitforsingleo_0; "WaitForSingleObject for ABI failed with"...
0x1803000b1  lea     r8, aAbiGetallaccou; "Abi_GetAllAccounts"
0x1803000b8  mov     edx, 174h
0x1803000bd  mov     ecx, 4
0x1803000c2  call    sub_1802145C0
0x1803000c7  mov     rdx, r14
0x1803000ca  mov     ecx, 1E5898CEh
0x1803000cf  call    sub_1802A31B0
0x1803000d4  mov     rdx, r14
0x1803000d7  mov     ecx, 1E590319h
0x1803000dc  call    sub_1802A31B0
0x1803000e1  lfence
0x1803000e4  mov     [r15], r13
0x1803000e7  mov     [rsp+0E8h+var_A0], 0Fh
0x1803000ef  mov     dword ptr [rsp+0E8h+var_B8], 179h
0x1803000f7  mov     qword ptr [rsp+0E8h+var_B8+8], r12
0x1803000fc  mov     [rsp+0E8h+var_A8], r13
0x180300101  mov     rax, [rbx]
0x180300104  mov     rdx, r15
0x180300107  mov     rcx, rbx
0x18030010a  mov     rax, [rax+40h]
0x18030010e  call    cs:__guard_dispatch_icall_fptr
0x180300114  lfence
0x180300117  test    eax, eax
0x180300119  js      short loc_180300174
0x18030011b  test    rbx, rbx
0x18030011e  jz      short loc_18030012B
0x180300120  lea     rcx, [rsp+0E8h+var_98]
0x180300125  call    sub_18028D360
0x18030012a  nop
0x18030012b  test    rsi, rsi
0x18030012e  jz      short loc_18030013B
0x180300130  lea     rcx, [rsp+0E8h+var_90]
0x180300135  call    sub_18028D360
0x18030013a  nop
0x18030013b  mov     rcx, rdi; hObject
0x18030013e  call    CloseHandle
0x180300143  mov     rax, r15
0x180300146  add     rsp, 0B0h
0x18030014d  pop     r15
0x18030014f  pop     r14
0x180300151  pop     r13
0x180300153  pop     r12
0x180300155  pop     rdi
0x180300156  pop     rsi
0x180300157  pop     rbx
0x180300158  retn
0x180300159  lea     rcx, [rsp+0E8h+var_B8]
0x18030015e  call    sub_1802946B0
0x180300164  lfence
0x180300167  lea     rdx, [rsp+0E8h+var_B8]
0x18030016c  mov     ecx, eax
0x18030016e  call    sub_18028CCB0
0x180300174  lea     rdx, [rsp+0E8h+var_B8]
0x180300179  mov     ecx, eax
0x18030017b  call    sub_18028CCB0
```
