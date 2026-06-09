# GetDeviceRegistrationInfo

- ea: `0x18000da60`
- end: `0x18000de89`
- name: `GetDeviceRegistrationInfo`
- size: `1065`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800026d0`
- `0x1800054bc`
- `0x18000b0f4`
- `0x18000da60`
- `0x18003c6d4`
- `0x18003c758`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dbb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dbb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de29`

## string_xrefs

- `0x18000dcb2`: `DiscoveryServiceFullURL`
- `0x18000dab7`: `onecoreuap\admin\enterprisemgmt\enrollactivities\mdmregistration\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeviceRegistrationInfo(int a1, __int64 a2)
{
  int EnrollmentString; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v6; // rcx
  HLOCAL v7; // rbx
  HLOCAL v8; // rdi
  int EnrollmentType; // r14d
  __int64 v10; // [rsp+20h] [rbp-60h] BYREF
  __int64 v11; // [rsp+28h] [rbp-58h] BYREF
  struct _GUID v12; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-40h] BYREF
  HLOCAL v14; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v15; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a1 != 1 )
    return 2147942487LL;
  v11 = 0;
  v10 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\mdmregistration\\dllmain.cpp",
      (const char *)0x80070057LL,
      v10);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return 2147942487LL;
  }
  EnrollmentString = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(off_1800704F8 + 32LL))(
                       &off_1800704F8,
                       8289,
                       &v11);
  if ( EnrollmentString < 0 )
  {
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)EnrollmentString;
  }
  EnrollmentString = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, &v10);
  if ( EnrollmentString < 0 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)EnrollmentString;
  }
  if ( !EnrollmentString )
  {
    v15 = 0;
    EnrollmentString = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v10 + 24LL))(v10, &v15);
    if ( EnrollmentString < 0 )
    {
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)EnrollmentString;
    }
    hMem[0] = 0;
    v12 = v15;
    EnrollmentString = EEDBManager::GetEnrollmentString(&v12, L"UPN", (unsigned __int16 **)hMem);
    if ( EnrollmentString < 0 )
    {
      LocalFree(hMem[0]);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)EnrollmentString;
    }
    v14 = 0;
    v12 = v15;
    EnrollmentString = EEDBManager::GetEnrollmentString(&v12, L"DiscoveryServiceFullURL", (unsigned __int16 **)&v14);
    if ( EnrollmentString < 0 )
    {
      LocalFree(v14);
      LocalFree(hMem[0]);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)EnrollmentString;
    }
    *(_QWORD *)&v12.Data1 = 8;
    *(_QWORD *)v12.Data4 = 16;
    v7 = hMem[0];
    v8 = v14;
    hMem[1] = v14;
    EnrollmentType = SerialiseResults__MANAGEMENT_REGISTRATION_INFO_(v6, hMem, &v12, a2);
    if ( EnrollmentType >= 0 )
    {
      v12 = v15;
      EnrollmentType = EEDBManager::GetEnrollmentType(&v12, (enum EnrollmentEnrollType *)(*(_QWORD *)a2 + 4LL));
      if ( EnrollmentType >= 0 )
      {
        **(_DWORD **)a2 = 1;
        LocalFree(v8);
        LocalFree(v7);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        goto LABEL_53;
      }
      LocalFree(v8);
      LocalFree(v7);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    else
    {
      LocalFree(v8);
      LocalFree(v7);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return (unsigned int)EnrollmentType;
  }
  ProcessHeap = GetProcessHeap();
  *(_QWORD *)a2 = HeapAlloc(ProcessHeap, 8u, 0x18u);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_53:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x18000da60  mov     [rsp-18h+arg_0], rbx
0x18000da65  mov     [rsp-18h+arg_10], rsi
0x18000da6a  push    rbp
0x18000da6b  push    rdi
0x18000da6c  push    r14
0x18000da6e  mov     rbp, rsp
0x18000da71  sub     rsp, 80h
0x18000da78  mov     rax, cs:__security_cookie
0x18000da7f  xor     rax, rsp
0x18000da82  mov     [rbp+var_10], rax
0x18000da86  mov     rsi, rdx
0x18000da89  cmp     ecx, 1
0x18000da8c  jz      short loc_18000DA98
0x18000da8e  mov     eax, 80070057h
0x18000da93  jmp     loc_18000DE64
0x18000da98  mov     [rbp+var_58], 0
0x18000daa0  mov     [rbp+var_60], 0
0x18000daa8  test    rsi, rsi
0x18000daab  jnz     short loc_18000DAF7
0x18000daad  mov     rcx, [rbp+18h]; this
0x18000dab1  mov     r9d, 80070057h; char *
0x18000dab7  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18000dabe  mov     edx, 2D3h; void *
0x18000dac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dac8  nop
0x18000dac9  mov     rcx, [rbp+var_60]
0x18000dacd  test    rcx, rcx
0x18000dad0  jz      short loc_18000DADF
0x18000dad2  mov     rax, [rcx]
0x18000dad5  mov     rax, [rax+10h]
0x18000dad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dade  nop
0x18000dadf  mov     rcx, [rbp+var_58]
0x18000dae3  test    rcx, rcx
0x18000dae6  jz      short loc_18000DAF5
0x18000dae8  mov     rax, [rcx]
0x18000daeb  mov     rax, [rax+10h]
0x18000daef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf4  nop
0x18000daf5  jmp     short loc_18000DA8E
0x18000daf7  mov     rax, cs:off_1800704F8
0x18000dafe  lea     r8, [rbp+var_58]
0x18000db02  mov     edx, 2061h
0x18000db07  lea     rcx, off_1800704F8
0x18000db0e  mov     rax, [rax+20h]
0x18000db12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db17  mov     ebx, eax
0x18000db19  test    eax, eax
0x18000db1b  jns     short loc_18000DB50
0x18000db1d  mov     rcx, [rbp+var_60]
0x18000db21  test    rcx, rcx
0x18000db24  jz      short loc_18000DB33
0x18000db26  mov     rdx, [rcx]
0x18000db29  mov     rax, [rdx+10h]
0x18000db2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db32  nop
0x18000db33  mov     rcx, [rbp+var_58]
0x18000db37  test    rcx, rcx
0x18000db3a  jz      short loc_18000DB49
0x18000db3c  mov     rax, [rcx]
0x18000db3f  mov     rax, [rax+10h]
0x18000db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db48  nop
0x18000db49  mov     eax, ebx
0x18000db4b  jmp     loc_18000DE64
0x18000db50  mov     rcx, [rbp+var_58]
0x18000db54  mov     rax, [rcx]
0x18000db57  lea     rdx, [rbp+var_60]
0x18000db5b  mov     rax, [rax+18h]
0x18000db5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db64  mov     ebx, eax
0x18000db66  test    eax, eax
0x18000db68  jns     short loc_18000DB98
0x18000db6a  mov     rcx, [rbp+var_60]
0x18000db6e  test    rcx, rcx
0x18000db71  jz      short loc_18000DB80
0x18000db73  mov     rdx, [rcx]
0x18000db76  mov     rax, [rdx+10h]
0x18000db7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7f  nop
0x18000db80  mov     rcx, [rbp+var_58]
0x18000db84  test    rcx, rcx
0x18000db87  jz      short loc_18000DB96
0x18000db89  mov     rax, [rcx]
0x18000db8c  mov     rax, [rax+10h]
0x18000db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db95  nop
0x18000db96  jmp     short loc_18000DB49
0x18000db98  test    ebx, ebx
0x18000db9a  jz      short loc_18000DBDE
0x18000db9c  call    cs:__imp_GetProcessHeap
0x18000dba3  nop     dword ptr [rax+rax+00h]
0x18000dba8  mov     rcx, rax; hHeap
0x18000dbab  mov     edx, 8; dwFlags
0x18000dbb0  lea     r8d, [rdx+10h]; dwBytes
0x18000dbb4  call    cs:__imp_HeapAlloc
0x18000dbbb  nop     dword ptr [rax+rax+00h]
0x18000dbc0  mov     [rsi], rax
0x18000dbc3  mov     rcx, [rbp+var_60]
0x18000dbc7  test    rcx, rcx
0x18000dbca  jz      short loc_18000DBD9
0x18000dbcc  mov     rax, [rcx]
0x18000dbcf  mov     rax, [rax+10h]
0x18000dbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd8  nop
0x18000dbd9  jmp     loc_18000DE4C
0x18000dbde  xorps   xmm0, xmm0
0x18000dbe1  movups  [rbp+var_20], xmm0
0x18000dbe5  mov     rcx, [rbp+var_60]
0x18000dbe9  mov     rax, [rcx]
0x18000dbec  lea     rdx, [rbp+var_20]
0x18000dbf0  mov     rax, [rax+18h]
0x18000dbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf9  mov     ebx, eax
0x18000dbfb  test    eax, eax
0x18000dbfd  jns     short loc_18000DC30
0x18000dbff  mov     rcx, [rbp+var_60]
0x18000dc03  test    rcx, rcx
0x18000dc06  jz      short loc_18000DC15
0x18000dc08  mov     rdx, [rcx]
0x18000dc0b  mov     rax, [rdx+10h]
0x18000dc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc14  nop
0x18000dc15  mov     rcx, [rbp+var_58]
0x18000dc19  test    rcx, rcx
0x18000dc1c  jz      short loc_18000DC2B
0x18000dc1e  mov     rax, [rcx]
0x18000dc21  mov     rax, [rax+10h]
0x18000dc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc2a  nop
0x18000dc2b  jmp     loc_18000DB49
0x18000dc30  mov     [rbp+hMem], 0
0x18000dc38  movaps  xmm0, [rbp+var_20]
0x18000dc3c  movdqa  xmmword ptr [rbp+var_50.Data1], xmm0
0x18000dc41  lea     r8, [rbp+hMem]; unsigned __int16 **
0x18000dc45  lea     rdx, aUpn; "UPN"
0x18000dc4c  lea     rcx, [rbp+var_50]; struct _GUID
0x18000dc50  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18000dc55  mov     ebx, eax
0x18000dc57  test    eax, eax
0x18000dc59  jns     short loc_18000DC9D
0x18000dc5b  mov     rcx, [rbp+hMem]; hMem
0x18000dc5f  call    cs:__imp_LocalFree
0x18000dc66  nop     dword ptr [rax+rax+00h]
0x18000dc6b  nop
0x18000dc6c  mov     rcx, [rbp+var_60]
0x18000dc70  test    rcx, rcx
0x18000dc73  jz      short loc_18000DC82
0x18000dc75  mov     rdx, [rcx]
0x18000dc78  mov     rax, [rdx+10h]
0x18000dc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc81  nop
0x18000dc82  mov     rcx, [rbp+var_58]
0x18000dc86  test    rcx, rcx
0x18000dc89  jz      short loc_18000DC98
0x18000dc8b  mov     rax, [rcx]
0x18000dc8e  mov     rax, [rax+10h]
0x18000dc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc97  nop
0x18000dc98  jmp     loc_18000DB49
0x18000dc9d  mov     [rbp+var_30], 0
0x18000dca5  movaps  xmm0, [rbp+var_20]
0x18000dca9  movdqa  xmmword ptr [rbp+var_50.Data1], xmm0
0x18000dcae  lea     r8, [rbp+var_30]; unsigned __int16 **
0x18000dcb2  lea     rdx, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18000dcb9  lea     rcx, [rbp+var_50]; struct _GUID
0x18000dcbd  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18000dcc2  mov     ebx, eax
0x18000dcc4  test    eax, eax
0x18000dcc6  jns     short loc_18000DD1A
0x18000dcc8  mov     rcx, [rbp+var_30]; hMem
0x18000dccc  call    cs:__imp_LocalFree
0x18000dcd3  nop     dword ptr [rax+rax+00h]
0x18000dcd8  mov     rcx, [rbp+hMem]; hMem
0x18000dcdc  call    cs:__imp_LocalFree
0x18000dce3  nop     dword ptr [rax+rax+00h]
0x18000dce8  nop
0x18000dce9  mov     rcx, [rbp+var_60]
0x18000dced  test    rcx, rcx
0x18000dcf0  jz      short loc_18000DCFF
0x18000dcf2  mov     rdx, [rcx]
0x18000dcf5  mov     rax, [rdx+10h]
0x18000dcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcfe  nop
0x18000dcff  mov     rcx, [rbp+var_58]
0x18000dd03  test    rcx, rcx
0x18000dd06  jz      short loc_18000DD15
0x18000dd08  mov     rax, [rcx]
0x18000dd0b  mov     rax, [rax+10h]
0x18000dd0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd14  nop
0x18000dd15  jmp     loc_18000DB49
0x18000dd1a  mov     qword ptr [rbp+var_50.Data1], 8
0x18000dd22  mov     qword ptr [rbp+var_50.Data4], 10h
0x18000dd2a  mov     rbx, [rbp+hMem]
0x18000dd2e  mov     [rbp+hMem], rbx
0x18000dd32  mov     rdi, [rbp+var_30]
0x18000dd36  mov     [rbp+var_38], rdi
0x18000dd3a  mov     r9, rsi
0x18000dd3d  lea     r8, [rbp+var_50]
0x18000dd41  lea     rdx, [rbp+hMem]
0x18000dd45  call    SerialiseResults__MANAGEMENT_REGISTRATION_INFO___; SerialiseResults__MANAGEMENT_REGISTRATION_INFO_
0x18000dd4a  mov     r14d, eax
0x18000dd4d  test    eax, eax
0x18000dd4f  jns     short loc_18000DDA4
0x18000dd51  mov     rcx, rdi; hMem
0x18000dd54  call    cs:__imp_LocalFree
0x18000dd5b  nop     dword ptr [rax+rax+00h]
0x18000dd60  mov     rcx, rbx; hMem
0x18000dd63  call    cs:__imp_LocalFree
0x18000dd6a  nop     dword ptr [rax+rax+00h]
0x18000dd6f  nop
0x18000dd70  mov     rcx, [rbp+var_60]
0x18000dd74  test    rcx, rcx
0x18000dd77  jz      short loc_18000DD86
0x18000dd79  mov     rdx, [rcx]
0x18000dd7c  mov     rax, [rdx+10h]
0x18000dd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd85  nop
0x18000dd86  mov     rcx, [rbp+var_58]
0x18000dd8a  test    rcx, rcx
0x18000dd8d  jz      short loc_18000DD9C
0x18000dd8f  mov     rax, [rcx]
0x18000dd92  mov     rax, [rax+10h]
0x18000dd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd9b  nop
0x18000dd9c  mov     eax, r14d
0x18000dd9f  jmp     loc_18000DE64
0x18000dda4  movaps  xmm0, [rbp+var_20]
0x18000dda8  movdqa  xmmword ptr [rbp+var_50.Data1], xmm0
0x18000ddad  mov     rdx, [rsi]
0x18000ddb0  add     rdx, 4; enum EnrollmentEnrollType *
0x18000ddb4  lea     rcx, [rbp+var_50]; struct _GUID
0x18000ddb8  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x18000ddbd  mov     r14d, eax
0x18000ddc0  mov     rcx, rdi; hMem
0x18000ddc3  test    eax, eax
0x18000ddc5  jns     short loc_18000DE11
0x18000ddc7  call    cs:__imp_LocalFree
0x18000ddce  nop     dword ptr [rax+rax+00h]
0x18000ddd3  mov     rcx, rbx; hMem
0x18000ddd6  call    cs:__imp_LocalFree
0x18000dddd  nop     dword ptr [rax+rax+00h]
0x18000dde2  nop
0x18000dde3  mov     rcx, [rbp+var_60]
0x18000dde7  test    rcx, rcx
0x18000ddea  jz      short loc_18000DDF9
0x18000ddec  mov     rdx, [rcx]
0x18000ddef  mov     rax, [rdx+10h]
0x18000ddf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf8  nop
0x18000ddf9  mov     rcx, [rbp+var_58]
0x18000ddfd  test    rcx, rcx
0x18000de00  jz      short loc_18000DE0F
0x18000de02  mov     rax, [rcx]
0x18000de05  mov     rax, [rax+10h]
0x18000de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0e  nop
0x18000de0f  jmp     short loc_18000DD9C
0x18000de11  mov     rax, [rsi]
0x18000de14  mov     dword ptr [rax], 1
0x18000de1a  call    cs:__imp_LocalFree
0x18000de21  nop     dword ptr [rax+rax+00h]
0x18000de26  mov     rcx, rbx; hMem
0x18000de29  call    cs:__imp_LocalFree
0x18000de30  nop     dword ptr [rax+rax+00h]
0x18000de35  nop
0x18000de36  mov     rcx, [rbp+var_60]
0x18000de3a  test    rcx, rcx
0x18000de3d  jz      short loc_18000DE4C
0x18000de3f  mov     rax, [rcx]
0x18000de42  mov     rax, [rax+10h]
0x18000de46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de4b  nop
0x18000de4c  mov     rcx, [rbp+var_58]
0x18000de50  test    rcx, rcx
0x18000de53  jz      short loc_18000DE62
0x18000de55  mov     rax, [rcx]
0x18000de58  mov     rax, [rax+10h]
0x18000de5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de61  nop
0x18000de62  xor     eax, eax
0x18000de64  mov     rcx, [rbp+var_10]
0x18000de68  xor     rcx, rsp; StackCookie
0x18000de6b  call    __security_check_cookie
0x18000de70  lea     r11, [rsp+80h+var_s0]
0x18000de78  mov     rbx, [r11+20h]
0x18000de7c  mov     rsi, [r11+30h]
0x18000de80  mov     rsp, r11
0x18000de83  pop     r14
0x18000de85  pop     rdi
0x18000de86  pop     rbp
0x18000de87  retn
```
