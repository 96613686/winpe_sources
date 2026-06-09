# LaunchApplication(__MIDL___MIDL_itf_mscoree_0000_0000_0001,Dfdll::CString &,ushort const *,uint)

- ea: `0x180003168`
- end: `0x18000352d`
- name: `?LaunchApplication@@YAJW4__MIDL___MIDL_itf_mscoree_0000_0000_0001@@AEAVCString@Dfdll@@PEBGI@Z`
- size: `965`
- prototype: `__int64 __fastcall(int, __int64, HKEY, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000444c`
- `0x180004580`

## callees

- `0x180003168`
- `0x1800036c8`
- `0x180012b30`
- `0x180012bd0`
- `0x18001ecdd`
- `0x18001efd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000333e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000333e`
- `ADVAPI32!RegCloseKey` at `0x180003367`
- `ADVAPI32!RegCloseKey` at `0x1800033fe`
- `ADVAPI32!RegCloseKey` at `0x180003367`
- `ADVAPI32!RegCloseKey` at `0x1800033fe`
- `KERNEL32!CloseHandle` at `0x18000347d`
- `KERNEL32!CloseHandle` at `0x180003491`
- `KERNEL32!CloseHandle` at `0x18000347d`
- `KERNEL32!CloseHandle` at `0x180003491`

## pseudocode

```c
__int64 __fastcall LaunchApplication(int a1, __int64 a2, HKEY a3, unsigned int a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct std::nothrow_t *v10; // rdx
  signed __int64 v11; // r9
  __int16 v12; // ax
  const struct std::nothrow_t *v13; // rax
  _QWORD *v14; // rdi
  HKEY v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // ebx
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall *v23)(__int64, __int64, _QWORD, _QWORD, int, HKEY *, HANDLE *); // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v24; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+88h] [rbp-78h] BYREF
  void **v27; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h]
  void **v29; // [rsp+A0h] [rbp-60h]
  void **v30; // [rsp+A8h] [rbp-58h]
  void *v31; // [rsp+B0h] [rbp-50h]
  int v32; // [rsp+B8h] [rbp-48h]
  int v33; // [rsp+C0h] [rbp-40h]
  HANDLE hObject[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v35; // [rsp+D8h] [rbp-28h]
  _BYTE v36[528]; // [rsp+E0h] [rbp-20h] BYREF

  v23 = 0;
  v24 = 0;
  v8 = 0;
  v21 = 0;
  v9 = 260;
  v26 = 260;
  v10 = (const struct std::nothrow_t *)v36;
  v11 = (char *)L"v4.0.30319" - v36;
  do
  {
    if ( v9 == -2147483386 )
      break;
    v12 = *(_WORD *)((char *)v10 + v11);
    if ( !v12 )
      break;
    *(_WORD *)v10 = v12;
    v10 = (const struct std::nothrow_t *)((char *)v10 + 2);
    --v9;
  }
  while ( v9 );
  v13 = (const struct std::nothrow_t *)((char *)v10 - 2);
  if ( v9 )
    v13 = v10;
  *(_WORD *)v13 = 0;
  if ( v9 )
  {
    v24 = 0;
    if ( (int)CLRCreateInstance_0(&CLSID_CLRMetaHostPolicy, &IID_ICLRMetaHostPolicy, &v24, v11) >= 0 )
    {
      v14 = v24;
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
      if ( (*(int (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD, _BYTE *, int *, _QWORD, _QWORD, _QWORD, GUID *, __int64 *))(*v14 + 24LL))(
             v14,
             0,
             0,
             0,
             v36,
             &v26,
             0,
             0,
             0,
             &IID_ICLRRuntimeInfo,
             &v21) >= 0 )
        (*(void (__fastcall **)(__int64, const char *, __int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, HKEY *, HANDLE *)))(*(_QWORD *)v21 + 64LL))(
          v21,
          "CorLaunchApplication",
          &v23);
    }
    v8 = v21;
  }
  *(_OWORD *)hObject = 0;
  v35 = 0;
  if ( v23 )
  {
    v22 = 0;
    v27 = &Dfdll::CRegKey::`vftable';
    hKey = 0;
    v29 = &Dfdll::CString::`vftable';
    v31 = 0;
    v32 = 0;
    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
    v33 = 0;
    phkResult = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            Dfdll::Constants::Strings::MachineDeploymentFrameworkRegistryKey,
            0,
            0x2001Fu,
            &phkResult) )
    {
      v15 = phkResult;
      if ( hKey )
        RegCloseKey(hKey);
      hKey = v15;
      Dfdll::CRegKey::QueryValue((Dfdll::CRegKey *)&v27, Dfdll::Constants::Strings::ClickOnceHost, &v22);
      if ( v22 == 1 )
      {
        a1 = 1;
      }
      else if ( v22 == 2 )
      {
        a1 = 2;
      }
    }
    v16 = *(_QWORD *)(a2 + 16);
    v17 = a1 | a4;
    if ( a3 )
    {
      phkResult = a3;
      v18 = v23(v17, v16, 0, 0, 1, &phkResult, hObject);
    }
    else
    {
      v18 = v23(v17, v16, 0, 0, 0, 0, hObject);
    }
    v19 = v18;
    v27 = &Dfdll::CRegKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    hKey = 0;
    v29 = &Dfdll::CString::`vftable';
    v30 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v31 )
      operator delete(v31, v10);
    if ( v23 )
    {
      v23 = 0;
      if ( v19 >= 0 )
      {
        if ( (unsigned __int64)hObject[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(hObject[1]);
        if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(hObject[0]);
        v19 = 0;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v24 )
          (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
      }
      else
      {
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v24 )
          (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
      }
      return (unsigned int)v19;
    }
    v8 = v21;
  }
  v19 = -2147024769;
  if ( v8 )
    (*(void (__fastcall **)(__int64, const struct std::nothrow_t *, __int64, signed __int64))(*(_QWORD *)v8 + 16LL))(
      v8,
      v10,
      v9,
      v11);
  if ( v24 )
    (*(void (__fastcall **)(_QWORD *, _QWORD, __int64, signed __int64))(*v24 + 16LL))(v24, *v24, v9, v11);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180003168  mov     [rsp-8+arg_10], rbx
0x18000316d  push    rbp
0x18000316e  push    rsi
0x18000316f  push    rdi
0x180003170  push    r12
0x180003172  push    r13
0x180003174  push    r14
0x180003176  push    r15
0x180003178  lea     rbp, [rsp-200h]
0x180003180  sub     rsp, 300h
0x180003187  mov     rax, cs:__security_cookie
0x18000318e  xor     rax, rsp
0x180003191  mov     [rbp+230h+var_40], rax
0x180003198  mov     esi, r9d
0x18000319b  mov     r14, r8
0x18000319e  mov     r15, rdx
0x1800031a1  mov     ebx, ecx
0x1800031a3  xor     r12d, r12d
0x1800031a6  mov     [rsp+330h+var_2C0], r12
0x1800031ab  mov     [rsp+330h+var_2B8], r12
0x1800031b0  mov     ecx, r12d
0x1800031b3  mov     [rsp+330h+var_2D0], rcx
0x1800031b8  mov     r8d, 104h
0x1800031be  mov     [rbp+230h+var_2A8], r8d
0x1800031c2  lea     rdx, [rbp+230h+var_250]
0x1800031c6  lea     r9, aV4030319; "v4.0.30319"
0x1800031cd  lea     rax, [rbp+230h+var_250]
0x1800031d1  sub     r9, rax
0x1800031d4  lea     r10d, [r12+2]
0x1800031d9  lea     rax, [r8+7FFFFEFAh]
0x1800031e0  test    rax, rax
0x1800031e3  jz      short loc_1800031FB
0x1800031e5  movzx   eax, word ptr [r9+rdx]
0x1800031ea  test    ax, ax
0x1800031ed  jz      short loc_1800031FB
0x1800031ef  mov     [rdx], ax
0x1800031f2  add     rdx, r10
0x1800031f5  sub     r8, 1
0x1800031f9  jnz     short loc_1800031D9
0x1800031fb  lea     rax, [rdx-2]
0x1800031ff  test    r8, r8
0x180003202  cmovnz  rax, rdx
0x180003206  mov     [rax], r12w
0x18000320a  jz      loc_1800032CC
0x180003210  mov     [rsp+330h+var_2B8], r12
0x180003215  lea     r8, [rsp+330h+var_2B8]
0x18000321a  lea     rdx, IID_ICLRMetaHostPolicy
0x180003221  lea     rcx, CLSID_CLRMetaHostPolicy
0x180003228  call    CLRCreateInstance_0
0x18000322d  test    eax, eax
0x18000322f  js      loc_1800032C7
0x180003235  mov     rdi, [rsp+330h+var_2B8]
0x18000323a  mov     rcx, [rsp+330h+var_2D0]
0x18000323f  test    rcx, rcx
0x180003242  jz      short loc_180003251
0x180003244  mov     rax, [rcx]
0x180003247  mov     rax, [rax+10h]
0x18000324b  call    cs:__guard_dispatch_icall_fptr
0x180003251  mov     [rsp+330h+var_2D0], r12
0x180003256  mov     rax, [rdi]
0x180003259  lea     rcx, [rsp+330h+var_2D0]
0x18000325e  mov     [rsp+330h+var_2E0], rcx
0x180003263  lea     rcx, IID_ICLRRuntimeInfo
0x18000326a  mov     [rsp+330h+var_2E8], rcx
0x18000326f  mov     [rsp+330h+var_2F0], r12
0x180003274  mov     [rsp+330h+var_2F8], r12
0x180003279  mov     [rsp+330h+var_300], r12
0x18000327e  lea     rcx, [rbp+230h+var_2A8]
0x180003282  mov     [rsp+330h+var_308], rcx
0x180003287  lea     rcx, [rbp+230h+var_250]
0x18000328b  mov     [rsp+330h+phkResult], rcx
0x180003290  xor     r9d, r9d
0x180003293  xor     r8d, r8d
0x180003296  xor     edx, edx
0x180003298  mov     rcx, rdi
0x18000329b  mov     rax, [rax+18h]
0x18000329f  call    cs:__guard_dispatch_icall_fptr
0x1800032a5  test    eax, eax
0x1800032a7  js      short loc_1800032C7
0x1800032a9  mov     rcx, [rsp+330h+var_2D0]
0x1800032ae  mov     rax, [rcx]
0x1800032b1  lea     r8, [rsp+330h+var_2C0]
0x1800032b6  lea     rdx, aCorlaunchappli; "CorLaunchApplication"
0x1800032bd  mov     rax, [rax+40h]
0x1800032c1  call    cs:__guard_dispatch_icall_fptr
0x1800032c7  mov     rcx, [rsp+330h+var_2D0]
0x1800032cc  xorps   xmm0, xmm0
0x1800032cf  xor     eax, eax
0x1800032d1  movups  xmmword ptr [rbp+230h+hObject], xmm0
0x1800032d5  mov     [rbp+230h+var_258], rax
0x1800032d9  cmp     [rsp+330h+var_2C0], r12
0x1800032de  jz      loc_1800034D1
0x1800032e4  mov     [rsp+330h+var_2C8], r12d
0x1800032e9  lea     r13, ??_7CRegKey@Dfdll@@6B@; const Dfdll::CRegKey::`vftable'
0x1800032f0  mov     [rbp+230h+var_2A0], r13
0x1800032f4  mov     [rbp+230h+hKey], r12
0x1800032f8  lea     rdi, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x1800032ff  mov     [rbp+230h+var_290], rdi
0x180003303  mov     [rbp+230h+var_280], r12
0x180003307  mov     [rbp+230h+var_278], r12d
0x18000330b  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180003312  mov     [rbp+230h+var_288], rax
0x180003316  mov     [rbp+230h+var_270], r12d
0x18000331a  mov     [rbp+230h+var_2B0], r12
0x18000331e  lea     rax, [rbp+230h+var_2B0]
0x180003322  mov     [rsp+330h+phkResult], rax; phkResult
0x180003327  mov     r9d, 2001Fh; samDesired
0x18000332d  xor     r8d, r8d; ulOptions
0x180003330  mov     rdx, cs:?MachineDeploymentFrameworkRegistryKey@Strings@Constants@Dfdll@@3QEAGEA; lpSubKey
0x180003337  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000333e  call    cs:__imp_RegOpenKeyExW
0x180003344  test    eax, eax
0x180003346  jz      short loc_18000335A
0x180003348  movzx   ecx, ax
0x18000334b  or      ecx, 80070000h
0x180003351  test    eax, eax
0x180003353  cmovle  ecx, eax
0x180003356  test    ecx, ecx
0x180003358  js      short loc_1800033A7
0x18000335a  mov     rdi, [rbp+230h+var_2B0]
0x18000335e  mov     rcx, [rbp+230h+hKey]; hKey
0x180003362  test    rcx, rcx
0x180003365  jz      short loc_18000336D
0x180003367  call    cs:__imp_RegCloseKey
0x18000336d  mov     [rbp+230h+hKey], rdi
0x180003371  lea     r8, [rsp+330h+var_2C8]; unsigned int *
0x180003376  mov     rdx, cs:?ClickOnceHost@Strings@Constants@Dfdll@@3QEAGEA; unsigned __int16 *
0x18000337d  lea     rcx, [rbp+230h+var_2A0]; this
0x180003381  call    ?QueryValue@CRegKey@Dfdll@@QEAAJPEBGAEAK@Z; Dfdll::CRegKey::QueryValue(ushort const *,ulong &)
0x180003386  lea     rdi, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x18000338d  cmp     [rsp+330h+var_2C8], 1
0x180003392  jnz     short loc_18000339B
0x180003394  mov     ebx, 1
0x180003399  jmp     short loc_1800033A7
0x18000339b  mov     eax, 2
0x1800033a0  cmp     [rsp+330h+var_2C8], eax
0x1800033a4  cmovz   ebx, eax
0x1800033a7  or      esi, ebx
0x1800033a9  mov     rdx, [r15+10h]
0x1800033ad  lea     rax, [rbp+230h+hObject]
0x1800033b1  xor     r9d, r9d
0x1800033b4  xor     r8d, r8d
0x1800033b7  mov     ecx, esi
0x1800033b9  mov     [rsp+330h+var_300], rax
0x1800033be  test    r14, r14
0x1800033c1  jnz     short loc_1800033CF
0x1800033c3  mov     [rsp+330h+var_308], r12
0x1800033c8  mov     dword ptr [rsp+330h+phkResult], r12d
0x1800033cd  jmp     short loc_1800033E4
0x1800033cf  mov     [rbp+230h+var_2B0], r14
0x1800033d3  lea     rax, [rbp+230h+var_2B0]
0x1800033d7  mov     [rsp+330h+var_308], rax
0x1800033dc  mov     dword ptr [rsp+330h+phkResult], 1
0x1800033e4  mov     rax, [rsp+330h+var_2C0]
0x1800033e9  call    cs:__guard_dispatch_icall_fptr
0x1800033ef  mov     ebx, eax
0x1800033f1  mov     [rbp+230h+var_2A0], r13
0x1800033f5  mov     rcx, [rbp+230h+hKey]; hKey
0x1800033f9  test    rcx, rcx
0x1800033fc  jz      short loc_180003404
0x1800033fe  call    cs:__imp_RegCloseKey
0x180003404  mov     [rbp+230h+hKey], r12
0x180003408  mov     [rbp+230h+var_290], rdi
0x18000340c  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180003413  mov     [rbp+230h+var_288], rax
0x180003417  mov     rcx, [rbp+230h+var_280]; void *
0x18000341b  test    rcx, rcx
0x18000341e  jz      short loc_180003426
0x180003420  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003425  nop
0x180003426  cmp     [rsp+330h+var_2C0], r12
0x18000342b  jz      loc_1800034CC
0x180003431  mov     [rsp+330h+var_2C0], r12
0x180003436  test    ebx, ebx
0x180003438  jns     short loc_18000346F
0x18000343a  mov     rcx, [rsp+330h+var_2D0]
0x18000343f  test    rcx, rcx
0x180003442  jz      short loc_180003452
0x180003444  mov     rax, [rcx]
0x180003447  mov     rax, [rax+10h]
0x18000344b  call    cs:__guard_dispatch_icall_fptr
0x180003451  nop
0x180003452  mov     rcx, [rsp+330h+var_2B8]
0x180003457  test    rcx, rcx
0x18000345a  jz      short loc_18000346A
0x18000345c  mov     rax, [rcx]
0x18000345f  mov     rax, [rax+10h]
0x180003463  call    cs:__guard_dispatch_icall_fptr
0x180003469  nop
0x18000346a  jmp     loc_180003501
0x18000346f  mov     rcx, [rbp+230h+hObject+8]; hObject
0x180003473  lea     rax, [rcx-1]
0x180003477  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000347b  ja      short loc_180003483
0x18000347d  call    cs:__imp_CloseHandle
0x180003483  mov     rcx, [rbp+230h+hObject]; hObject
0x180003487  lea     rax, [rcx-1]
0x18000348b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000348f  ja      short loc_180003497
0x180003491  call    cs:__imp_CloseHandle
0x180003497  mov     ebx, r12d
0x18000349a  mov     rcx, [rsp+330h+var_2D0]
0x18000349f  test    rcx, rcx
0x1800034a2  jz      short loc_1800034B2
0x1800034a4  mov     rax, [rcx]
0x1800034a7  mov     rax, [rax+10h]
0x1800034ab  call    cs:__guard_dispatch_icall_fptr
0x1800034b1  nop
0x1800034b2  mov     rcx, [rsp+330h+var_2B8]
0x1800034b7  test    rcx, rcx
0x1800034ba  jz      short loc_1800034CA
0x1800034bc  mov     rax, [rcx]
0x1800034bf  mov     rax, [rax+10h]
0x1800034c3  call    cs:__guard_dispatch_icall_fptr
0x1800034c9  nop
0x1800034ca  jmp     short loc_180003501
0x1800034cc  mov     rcx, [rsp+330h+var_2D0]
0x1800034d1  mov     ebx, 8007007Fh
0x1800034d6  test    rcx, rcx
0x1800034d9  jz      short loc_1800034E9
0x1800034db  mov     rax, [rcx]
0x1800034de  mov     rax, [rax+10h]
0x1800034e2  call    cs:__guard_dispatch_icall_fptr
0x1800034e8  nop
0x1800034e9  mov     rcx, [rsp+330h+var_2B8]
0x1800034ee  test    rcx, rcx
0x1800034f1  jz      short loc_180003501
0x1800034f3  mov     rdx, [rcx]
0x1800034f6  mov     rax, [rdx+10h]
0x1800034fa  call    cs:__guard_dispatch_icall_fptr
0x180003500  nop
0x180003501  mov     eax, ebx
0x180003503  mov     rcx, [rbp+230h+var_40]
0x18000350a  xor     rcx, rsp; StackCookie
0x18000350d  call    __security_check_cookie
0x180003512  mov     rbx, [rsp+330h+arg_10]
0x18000351a  add     rsp, 300h
0x180003521  pop     r15
0x180003523  pop     r14
0x180003525  pop     r13
0x180003527  pop     r12
0x180003529  pop     rdi
0x18000352a  pop     rsi
0x18000352b  pop     rbp
0x18000352c  retn
```
