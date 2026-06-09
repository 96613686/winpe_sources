# sub_1802FFBF0

- ea: `0x1802ffbf0`
- end: `0x1802ffed5`
- name: `sub_1802FFBF0`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803010b0`

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
- `0x1802fd9b0`
- `0x1802ff3d0`
- `0x1802ffbf0`
- `0x18037b520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802ffddd`
- `KERNEL32!GetLastError` at `0x1802ffddd`
- `KERNEL32!CreateEventW` at `0x1802ffc4b`
- `KERNEL32!CreateEventW` at `0x1802ffc4b`
- `KERNEL32!WaitForSingleObject` at `0x1802ffdd3`
- `KERNEL32!WaitForSingleObject` at `0x1802ffdd3`

## string_xrefs

- `0x1802ffc64`: `C:\__w\1\vcpkg\buildtrees\oneauth\src\07f7dcfee3-22beed4695.clean\msal\source\windows\broker\WAMSynchronousWrapper.cpp`
- `0x1802ffcf1`: `https://login.microsoft.com`

## pseudocode

```c
_QWORD *__fastcall sub_1802FFBF0(_QWORD *a1, __int64 a2, __int64 a3)
{
  HANDLE EventW; // rax
  void *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rdi
  int v11; // eax
  int v12; // eax
  DWORD LastError; // [rsp+20h] [rbp-E8h]
  __int128 v15; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C8h]
  int v17; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v19[2]; // [rsp+58h] [rbp-B0h] BYREF
  _DWORD *v20; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD v21[4]; // [rsp+70h] [rbp-98h] BYREF
  const wchar_t *v22; // [rsp+80h] [rbp-88h]
  _QWORD *v23; // [rsp+88h] [rbp-80h]
  HANDLE v24; // [rsp+90h] [rbp-78h]
  __int64 *v25; // [rsp+98h] [rbp-70h]
  __int64 v26; // [rsp+A8h] [rbp-60h] BYREF

  v23 = a1;
  v19[1] = a3;
  v17 = 1;
  sub_1801AE334(word_18064C612);
  sub_1802A31B0(509149970, a3);
  EventW = CreateEventW(0, 0, 0, 0);
  v7 = EventW;
  v24 = EventW;
  LODWORD(v15) = 282;
  *((_QWORD *)&v15 + 1) = "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth\\src\\07f7dcfee3-22beed4695.clean\\msal\\source\\window"
                          "s\\broker\\WAMSynchronousWrapper.cpp";
  v16 = 0;
  if ( !EventW )
    sub_1802946B0(&v15);
  *(_QWORD *)&v15 = EventW;
  *((_QWORD *)&v15 + 1) = a3;
  v8 = sub_1801AD7D0(32);
  v9 = v8;
  if ( v8 )
  {
    *(_DWORD *)(v8 + 8) = 1;
    *(_OWORD *)(v8 + 16) = v15;
    _InterlockedIncrement(&dword_1805FC348);
    *(_QWORD *)v8 = ___7__delegate_U__AsyncOperationCompletedHandler_UWebAccountProvider_Credentials_Security_Windows_winrt___Foundation_Windows_winrt__V_lambda_1___2__Abi_GetAccountProvider__A0xf07e5453_Msai__YA_AUWebAccountProvider_Credentials_Security_34_AEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEBV__shared_ptr_VTelemetryInternal_Msai___std___Z__impl_winrt__6B_;
  }
  else
  {
    v9 = 0;
  }
  v19[0] = v9;
  v26 = *(_QWORD *)sub_18028DFF0(&v17, a2);
  v21[0] = 1;
  v21[1] = 27;
  v22 = L"https://login.microsoft.com";
  v20 = v21;
  *(_QWORD *)&v15 = &v20;
  *((_QWORD *)&v15 + 1) = &v26;
  v25 = &qword_1805FC188;
  _InterlockedIncrement64(&qword_1805FC188);
  if ( qword_1805FC180 )
  {
    sub_1802FF3D0(&v15, &v18, &qword_1805FC180);
    _InterlockedDecrement64(&qword_1805FC188);
  }
  else
  {
    _InterlockedDecrement64(&qword_1805FC188);
    sub_1802FD9B0(&qword_1805FC180, &v18, &v15);
  }
  sub_18028C720(&v17);
  LODWORD(v15) = 299;
  *((_QWORD *)&v15 + 1) = "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth\\src\\07f7dcfee3-22beed4695.clean\\msal\\source\\window"
                          "s\\broker\\WAMSynchronousWrapper.cpp";
  v16 = 0;
  v10 = v18;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 48LL))(v18, v9);
  if ( v11 < 0 )
  {
    _mm_lfence();
    sub_18028CCB0((unsigned int)v11, &v15);
  }
  sub_1802A31B0(509149971, a3);
  if ( WaitForSingleObject(v7, 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    sub_1802145C0(
      4,
      307,
      (unsigned int)"Abi_GetAccountProvider",
      (unsigned int)"WaitForSingleObject for ABI failed with error 0x%08lX",
      LastError);
    sub_1802A31B0(509122762, a3);
  }
  sub_1802A31B0(509149972, a3);
  _mm_lfence();
  *a1 = 0;
  v17 = 15;
  LODWORD(v15) = 313;
  *((_QWORD *)&v15 + 1) = "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth\\src\\07f7dcfee3-22beed4695.clean\\msal\\source\\window"
                          "s\\broker\\WAMSynchronousWrapper.cpp";
  v16 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 64LL))(v10, a1);
  if ( v12 < 0 )
  {
    _mm_lfence();
    sub_18028CCB0((unsigned int)v12, &v15);
  }
  if ( !*a1 )
    sub_1802A31B0(509149973, a3);
  _mm_lfence();
  if ( v10 )
    sub_18028D360(&v18);
  if ( v9 )
    sub_18028D360(v19);
  CloseHandle(v7);
  return a1;
}

```

## disassembly

```asm
0x1802ffbf0  push    rbx
0x1802ffbf2  push    rsi
0x1802ffbf3  push    rdi
0x1802ffbf4  push    r12
0x1802ffbf6  push    r13
0x1802ffbf8  push    r14
0x1802ffbfa  push    r15
0x1802ffbfc  mov     eax, 0D0h
0x1802ffc01  call    __alloca_probe
0x1802ffc06  sub     rsp, rax
0x1802ffc09  mov     r14, r8
0x1802ffc0c  mov     rdi, rdx
0x1802ffc0f  mov     r15, rcx
0x1802ffc12  mov     [rsp+108h+var_80], rcx
0x1802ffc1a  mov     [rsp+108h+var_A8], r8
0x1802ffc1f  mov     [rsp+108h+var_C0], 1
0x1802ffc27  lea     rcx, word_18064C612
0x1802ffc2e  call    sub_1801AE334
0x1802ffc33  nop
0x1802ffc34  mov     rdx, r14
0x1802ffc37  mov     ecx, 1E590312h
0x1802ffc3c  call    sub_1802A31B0
0x1802ffc41  xor     r9d, r9d; lpName
0x1802ffc44  xor     r8d, r8d; bInitialState
0x1802ffc47  xor     edx, edx; bManualReset
0x1802ffc49  xor     ecx, ecx; lpEventAttributes
0x1802ffc4b  call    cs:__imp_CreateEventW
0x1802ffc51  mov     rbx, rax
0x1802ffc54  mov     [rsp+108h+var_78], rax
0x1802ffc5c  mov     dword ptr [rsp+108h+var_D8], 11Ah
0x1802ffc64  lea     r13, aCW1VcpkgBuildt; "C:\\__w\\1\\vcpkg\\buildtrees\\oneauth"...
0x1802ffc6b  mov     qword ptr [rsp+108h+var_D8+8], r13
0x1802ffc70  xor     r12d, r12d
0x1802ffc73  mov     [rsp+108h+var_C8], r12
0x1802ffc78  test    rax, rax
0x1802ffc7b  jz      loc_1802FFEA9
0x1802ffc81  mov     qword ptr [rsp+108h+var_D8], rbx
0x1802ffc86  mov     qword ptr [rsp+108h+var_D8+8], r14
0x1802ffc8b  mov     ecx, 20h ; ' '
0x1802ffc90  call    sub_1801AD7D0
0x1802ffc95  mov     rsi, rax
0x1802ffc98  test    rax, rax
0x1802ffc9b  jz      short loc_1802FFCC0
0x1802ffc9d  mov     dword ptr [rax+8], 1
0x1802ffca4  movups  xmm0, [rsp+108h+var_D8]
0x1802ffca9  movups  xmmword ptr [rax+10h], xmm0
0x1802ffcad  lock inc cs:dword_1805FC348
0x1802ffcb4  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UWebAccountProvider@Credentials@Security@Windows@winrt@@@Foundation@Windows@winrt@@V_lambda_1_@?2??Abi_GetAccountProvider@?A0xf07e5453@Msai@@YA?AUWebAccountProvider@Credentials@Security@34@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@VTelemetryInternal@Msai@@@std@@@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Security::Credentials::WebAccountProvider>,`Msai::`anonymous namespace'::Abi_GetAccountProvider(std::string const &,std::shared_ptr<Msai::TelemetryInternal> const &)'::`3'::_lambda_1_>::`vftable'
0x1802ffcbb  mov     [rsi], rax
0x1802ffcbe  jmp     short loc_1802FFCC3
0x1802ffcc0  mov     rsi, r12
0x1802ffcc3  mov     [rsp+108h+var_B0], rsi
0x1802ffcc8  mov     rdx, rdi
0x1802ffccb  lea     rcx, [rsp+108h+var_C0]
0x1802ffcd0  call    sub_18028DFF0
0x1802ffcd5  nop
0x1802ffcd6  mov     rax, [rax]
0x1802ffcd9  mov     [rsp+108h+var_60], rax
0x1802ffce1  mov     [rsp+108h+var_98], 1
0x1802ffce9  mov     [rsp+108h+var_94], 1Bh
0x1802ffcf1  lea     rax, aHttpsLoginMicr_0; "https://login.microsoft.com"
0x1802ffcf8  mov     [rsp+108h+var_88], rax
0x1802ffd00  lea     rax, [rsp+108h+var_98]
0x1802ffd05  mov     [rsp+108h+var_A0], rax
0x1802ffd0a  lea     rax, [rsp+108h+var_A0]
0x1802ffd0f  mov     qword ptr [rsp+108h+var_D8], rax
0x1802ffd14  lea     rax, [rsp+108h+var_60]
0x1802ffd1c  mov     qword ptr [rsp+108h+var_D8+8], rax
0x1802ffd21  lea     rax, qword_1805FC188
0x1802ffd28  mov     [rsp+108h+var_70], rax
0x1802ffd30  lock inc cs:qword_1805FC188
0x1802ffd38  cmp     cs:qword_1805FC180, 0
0x1802ffd40  jz      short loc_1802FFD63
0x1802ffd42  lea     r8, qword_1805FC180
0x1802ffd49  lea     rdx, [rsp+108h+var_B8]
0x1802ffd4e  lea     rcx, [rsp+108h+var_D8]
0x1802ffd53  call    sub_1802FF3D0
0x1802ffd58  nop
0x1802ffd59  lock dec cs:qword_1805FC188
0x1802ffd61  jmp     short loc_1802FFD82
0x1802ffd63  lock dec cs:qword_1805FC188
0x1802ffd6b  lea     r8, [rsp+108h+var_D8]
0x1802ffd70  lea     rdx, [rsp+108h+var_B8]
0x1802ffd75  lea     rcx, qword_1805FC180
0x1802ffd7c  call    sub_1802FD9B0
0x1802ffd81  nop
0x1802ffd82  lea     rcx, [rsp+108h+var_C0]
0x1802ffd87  call    sub_18028C720
0x1802ffd8c  mov     dword ptr [rsp+108h+var_D8], 12Bh
0x1802ffd94  mov     qword ptr [rsp+108h+var_D8+8], r13
0x1802ffd99  mov     [rsp+108h+var_C8], r12
0x1802ffd9e  mov     rdi, [rsp+108h+var_B8]
0x1802ffda3  mov     rax, [rdi]
0x1802ffda6  mov     rdx, rsi
0x1802ffda9  mov     rcx, rdi
0x1802ffdac  mov     rax, [rax+30h]
0x1802ffdb0  call    cs:__guard_dispatch_icall_fptr
0x1802ffdb6  test    eax, eax
0x1802ffdb8  js      loc_1802FFEB4
0x1802ffdbe  mov     rdx, r14
0x1802ffdc1  mov     ecx, 1E590313h
0x1802ffdc6  call    sub_1802A31B0
0x1802ffdcb  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1802ffdd0  mov     rcx, rbx; hHandle
0x1802ffdd3  call    cs:__imp_WaitForSingleObject
0x1802ffdd9  test    eax, eax
0x1802ffddb  jz      short loc_1802FFE11
0x1802ffddd  call    cs:__imp_GetLastError
0x1802ffde3  mov     [rsp+108h+var_E8], eax
0x1802ffde7  lea     r9, aWaitforsingleo_0; "WaitForSingleObject for ABI failed with"...
0x1802ffdee  lea     r8, aAbiGetaccountp; "Abi_GetAccountProvider"
0x1802ffdf5  mov     edx, 133h
0x1802ffdfa  mov     ecx, 4
0x1802ffdff  call    sub_1802145C0
0x1802ffe04  mov     rdx, r14
0x1802ffe07  mov     ecx, 1E5898CAh
0x1802ffe0c  call    sub_1802A31B0
0x1802ffe11  mov     rdx, r14
0x1802ffe14  mov     ecx, 1E590314h
0x1802ffe19  call    sub_1802A31B0
0x1802ffe1e  lfence
0x1802ffe21  mov     [r15], r12
0x1802ffe24  mov     [rsp+108h+var_C0], 0Fh
0x1802ffe2c  mov     dword ptr [rsp+108h+var_D8], 139h
0x1802ffe34  mov     qword ptr [rsp+108h+var_D8+8], r13
0x1802ffe39  mov     [rsp+108h+var_C8], r12
0x1802ffe3e  mov     rax, [rdi]
0x1802ffe41  mov     rdx, r15
0x1802ffe44  mov     rcx, rdi
0x1802ffe47  mov     rax, [rax+40h]
0x1802ffe4b  call    cs:__guard_dispatch_icall_fptr
0x1802ffe51  test    eax, eax
0x1802ffe53  js      short loc_1802FFEC4
0x1802ffe55  cmp     qword ptr [r15], 0
0x1802ffe59  jnz     short loc_1802FFE68
0x1802ffe5b  mov     rdx, r14
0x1802ffe5e  mov     ecx, 1E590315h
0x1802ffe63  call    sub_1802A31B0
0x1802ffe68  lfence
0x1802ffe6b  test    rdi, rdi
0x1802ffe6e  jz      short loc_1802FFE7B
0x1802ffe70  lea     rcx, [rsp+108h+var_B8]
0x1802ffe75  call    sub_18028D360
0x1802ffe7a  nop
0x1802ffe7b  test    rsi, rsi
0x1802ffe7e  jz      short loc_1802FFE8B
0x1802ffe80  lea     rcx, [rsp+108h+var_B0]
0x1802ffe85  call    sub_18028D360
0x1802ffe8a  nop
0x1802ffe8b  mov     rcx, rbx; hObject
0x1802ffe8e  call    CloseHandle
0x1802ffe93  mov     rax, r15
0x1802ffe96  add     rsp, 0D0h
0x1802ffe9d  pop     r15
0x1802ffe9f  pop     r14
0x1802ffea1  pop     r13
0x1802ffea3  pop     r12
0x1802ffea5  pop     rdi
0x1802ffea6  pop     rsi
0x1802ffea7  pop     rbx
0x1802ffea8  retn
0x1802ffea9  lea     rcx, [rsp+108h+var_D8]
0x1802ffeae  call    sub_1802946B0
0x1802ffeb4  lfence
0x1802ffeb7  lea     rdx, [rsp+108h+var_D8]
0x1802ffebc  mov     ecx, eax
0x1802ffebe  call    sub_18028CCB0
0x1802ffec4  lfence
0x1802ffec7  lea     rdx, [rsp+108h+var_D8]
0x1802ffecc  mov     ecx, eax
0x1802ffece  call    sub_18028CCB0
```
