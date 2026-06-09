# CMVUISelection2::Provision(void)

- ea: `0x180029e90`
- end: `0x18002a189`
- name: `?Provision@CMVUISelection2@@UEAAJXZ`
- size: `761`
- prototype: `__int64 __fastcall(CMVUISelection2 *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1800076a4`
- `0x180026620`
- `0x180029e90`
- `0x180034fe0`
- `0x1800355a4`
- `0x18003b946`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029f3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002a041`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002a0dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029f3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002a041`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002a0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029f22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002a028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002a0c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029f22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002a028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002a0c3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180029f5e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180029f5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMVUISelection2::Provision(CMVUISelection2 *this)
{
  __int64 v1; // rdx
  __int64 result; // rax
  _QWORD *v3; // rdx
  __int64 v4; // rcx
  int v5; // ebx
  const char *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING); // rdi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64); // rdi
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19[2]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v20; // [rsp+28h] [rbp-80h] BYREF
  HSTRING v21; // [rsp+30h] [rbp-78h] BYREF
  HSTRING_HEADER v22; // [rsp+38h] [rbp-70h] BYREF
  HSTRING string; // [rsp+70h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
  {
    v3 = (_QWORD *)(v1 + 8);
    if ( v3[3] >= 8u )
      v3 = (_QWORD *)*v3;
    try
    {
      v4 = KnownUiccs::Find((__int64)&v21, (__int64)v3);
      KnownUicc::SetUIStatus(v4);
      KnownUicc::~KnownUicc((void **)&v21);
      if ( WindowsCreateStringReference(
             L"Windows.Management.Provisioning.PackageManager",
             0x2Eu,
             &hstringHeader,
             &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      *(_QWORD *)v19 = 0;
      v20 = 0;
      v5 = RoActivateInstance(string, &v20);
      if ( v5 >= 0 )
      {
        if ( !memcmp_0(&GUID_f6efa550_3514_4bed_800b_a2f68e0972b3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
        {
          *(_QWORD *)v19 = v20;
        }
        else
        {
          v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, int *))v20)(
                 v20,
                 &GUID_f6efa550_3514_4bed_800b_a2f68e0972b3,
                 v19);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      if ( v5 >= 0 )
      {
        v8 = *(_QWORD *)v19;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING))(**(_QWORD **)v19 + 88LL);
        if ( WindowsCreateStringReference(L"ProfileChange", 0xDu, &v22, &v21) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v10 = v9(v8, v21);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v13 = *(_QWORD *)v19;
          v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(**(_QWORD **)v19 + 80LL);
          if ( WindowsCreateStringReference(L"ProfileChange", 0xDu, &v22, &v21) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v15 = v14(v13, v21, 8);
          v16 = v15;
          if ( v15 >= 0 )
          {
            v18 = *(_QWORD *)v19;
            if ( *(_QWORD *)v19 )
            {
              *(_QWORD *)v19 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DC,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
              (const char *)(unsigned int)v15,
              v19[0]);
            v17 = *(_QWORD *)v19;
            if ( *(_QWORD *)v19 )
            {
              *(_QWORD *)v19 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            result = v16;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DA,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
            (const char *)(unsigned int)v10,
            v19[0]);
          v12 = *(_QWORD *)v19;
          if ( *(_QWORD *)v19 )
          {
            *(_QWORD *)v19 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D7,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
          (const char *)(unsigned int)v5,
          v19[0]);
        v7 = *(_QWORD *)v19;
        if ( *(_QWORD *)v19 )
        {
          *(_QWORD *)v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        result = (unsigned int)v5;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x1DF,
                             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
                             v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)0x8007139FLL,
      v19[0]);
    return 2147947423LL;
  }
  return result;
}

```

## disassembly

```asm
0x180029e90  mov     [rsp+arg_8], rbx
0x180029e95  push    rdi
0x180029e96  sub     rsp, 0A0h
0x180029e9d  mov     rax, cs:__security_cookie
0x180029ea4  xor     rax, rsp
0x180029ea7  mov     [rsp+0A8h+var_18], rax
0x180029eaf  mov     rdx, [rcx+18h]
0x180029eb3  test    rdx, rdx
0x180029eb6  jnz     short loc_180029EE0
0x180029eb8  mov     rcx, [rsp+0A8h]; this
0x180029ec0  mov     ebx, 8007139Fh
0x180029ec5  mov     r9d, ebx; char *
0x180029ec8  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180029ecf  mov     edx, 1CDh; void *
0x180029ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ed9  mov     eax, ebx
0x180029edb  jmp     loc_18002A167
0x180029ee0  add     rdx, 8
0x180029ee4  cmp     qword ptr [rdx+18h], 8
0x180029ee9  jb      short loc_180029EEE
0x180029eeb  mov     rdx, [rdx]
0x180029eee  lea     rcx, [rsp+0A8h+var_78]
0x180029ef3  call    ?Find@KnownUiccs@@SA?AUKnownUicc@@PEBG@Z; KnownUiccs::Find(ushort const *)
0x180029ef8  nop
0x180029ef9  mov     rcx, rax
0x180029efc  call    ?SetUIStatus@KnownUicc@@QEAAXW4__MIDL___MIDL_itf_mvengine_0000_0000_0002@@@Z; KnownUicc::SetUIStatus(__MIDL___MIDL_itf_mvengine_0000_0000_0002)
0x180029f01  nop
0x180029f02  lea     rcx, [rsp+0A8h+var_78]; this
0x180029f07  call    ??1KnownUicc@@QEAA@XZ; KnownUicc::~KnownUicc(void)
0x180029f0c  lea     r9, [rsp+0A8h+string]; string
0x180029f11  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x180029f16  mov     edx, 2Eh ; '.'; length
0x180029f1b  lea     rcx, ?RuntimeClass_Windows_Management_Provisioning_PackageManager@@3QBGB; "Windows.Management.Provisioning.Package"...
0x180029f22  call    cs:__imp_WindowsCreateStringReference
0x180029f28  test    eax, eax
0x180029f2a  jns     short loc_180029F42
0x180029f2c  xor     r9d, r9d; lpArguments
0x180029f2f  xor     r8d, r8d; nNumberOfArguments
0x180029f32  lea     edx, [r9+1]; dwExceptionFlags
0x180029f36  mov     ecx, 0C000000Dh; dwExceptionCode
0x180029f3b  call    cs:__imp_RaiseException
0x180029f41  nop
0x180029f42  mov     qword ptr [rsp+0A8h+var_88], 0; int
0x180029f4b  mov     [rsp+0A8h+var_80], 0
0x180029f54  lea     rdx, [rsp+0A8h+var_80]
0x180029f59  mov     rcx, [rsp+0A8h+string]
0x180029f5e  call    cs:__imp_RoActivateInstance
0x180029f64  mov     ebx, eax
0x180029f66  test    eax, eax
0x180029f68  js      short loc_180029FBE
0x180029f6a  mov     r8d, 10h; Size
0x180029f70  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180029f77  lea     rcx, _GUID_f6efa550_3514_4bed_800b_a2f68e0972b3; Buf1
0x180029f7e  call    memcmp_0
0x180029f83  mov     rcx, [rsp+0A8h+var_80]
0x180029f88  test    eax, eax
0x180029f8a  jnz     short loc_180029F93
0x180029f8c  mov     qword ptr [rsp+0A8h+var_88], rcx
0x180029f91  jmp     short loc_180029FBE
0x180029f93  mov     rax, [rcx]
0x180029f96  lea     r8, [rsp+0A8h+var_88]
0x180029f9b  lea     rdx, _GUID_f6efa550_3514_4bed_800b_a2f68e0972b3
0x180029fa2  mov     rax, [rax]
0x180029fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029faa  mov     ebx, eax
0x180029fac  mov     rcx, [rsp+0A8h+var_80]
0x180029fb1  mov     rax, [rcx]
0x180029fb4  mov     rax, [rax+10h]
0x180029fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fbd  nop
0x180029fbe  test    ebx, ebx
0x180029fc0  jns     short loc_18002A006
0x180029fc2  mov     rcx, [rsp+0A8h]; this
0x180029fca  mov     r9d, ebx; char *
0x180029fcd  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180029fd4  mov     edx, 1D7h; void *
0x180029fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fde  nop
0x180029fdf  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x180029fe4  test    rcx, rcx
0x180029fe7  jz      short loc_180029FFF
0x180029fe9  mov     qword ptr [rsp+0A8h+var_88], 0
0x180029ff2  mov     rax, [rcx]
0x180029ff5  mov     rax, [rax+10h]
0x180029ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ffe  nop
0x180029fff  mov     eax, ebx
0x18002a001  jmp     loc_18002A167
0x18002a006  mov     rbx, qword ptr [rsp+0A8h+var_88]
0x18002a00b  mov     rax, [rbx]
0x18002a00e  mov     rdi, [rax+58h]
0x18002a012  lea     r9, [rsp+0A8h+var_78]; string
0x18002a017  lea     r8, [rsp+0A8h+var_70]; hstringHeader
0x18002a01c  mov     edx, 0Dh; length
0x18002a021  lea     rcx, sourceString; "ProfileChange"
0x18002a028  call    cs:__imp_WindowsCreateStringReference
0x18002a02e  test    eax, eax
0x18002a030  jns     short loc_18002A047
0x18002a032  xor     r9d, r9d; lpArguments
0x18002a035  xor     r8d, r8d; nNumberOfArguments
0x18002a038  lea     edx, [r9+1]; dwExceptionFlags
0x18002a03c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002a041  call    cs:__imp_RaiseException
0x18002a047  mov     rdx, [rsp+0A8h+var_78]
0x18002a04c  mov     rcx, rbx
0x18002a04f  mov     rax, rdi
0x18002a052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a057  mov     ebx, eax
0x18002a059  test    eax, eax
0x18002a05b  jns     short loc_18002A0A1
0x18002a05d  mov     rcx, [rsp+0A8h]; this
0x18002a065  mov     r9d, eax; char *
0x18002a068  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a06f  mov     edx, 1DAh; void *
0x18002a074  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a079  nop
0x18002a07a  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x18002a07f  test    rcx, rcx
0x18002a082  jz      short loc_18002A09A
0x18002a084  mov     qword ptr [rsp+0A8h+var_88], 0
0x18002a08d  mov     rax, [rcx]
0x18002a090  mov     rax, [rax+10h]
0x18002a094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a099  nop
0x18002a09a  mov     eax, ebx
0x18002a09c  jmp     loc_18002A167
0x18002a0a1  mov     rbx, qword ptr [rsp+0A8h+var_88]
0x18002a0a6  mov     rax, [rbx]
0x18002a0a9  mov     rdi, [rax+50h]
0x18002a0ad  lea     r9, [rsp+0A8h+var_78]; string
0x18002a0b2  lea     r8, [rsp+0A8h+var_70]; hstringHeader
0x18002a0b7  mov     edx, 0Dh; length
0x18002a0bc  lea     rcx, sourceString; "ProfileChange"
0x18002a0c3  call    cs:__imp_WindowsCreateStringReference
0x18002a0c9  test    eax, eax
0x18002a0cb  jns     short loc_18002A0E2
0x18002a0cd  xor     r9d, r9d; lpArguments
0x18002a0d0  xor     r8d, r8d; nNumberOfArguments
0x18002a0d3  lea     edx, [r9+1]; dwExceptionFlags
0x18002a0d7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002a0dc  call    cs:__imp_RaiseException
0x18002a0e2  mov     r8d, 8
0x18002a0e8  mov     rdx, [rsp+0A8h+var_78]
0x18002a0ed  mov     rcx, rbx
0x18002a0f0  mov     rax, rdi
0x18002a0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0f8  mov     ebx, eax
0x18002a0fa  test    eax, eax
0x18002a0fc  jns     short loc_18002A13F
0x18002a0fe  mov     rcx, [rsp+0A8h]; this
0x18002a106  mov     r9d, eax; char *
0x18002a109  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a110  mov     edx, 1DCh; void *
0x18002a115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a11a  nop
0x18002a11b  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x18002a120  test    rcx, rcx
0x18002a123  jz      short loc_18002A13B
0x18002a125  mov     qword ptr [rsp+0A8h+var_88], 0
0x18002a12e  mov     rax, [rcx]
0x18002a131  mov     rax, [rax+10h]
0x18002a135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a13a  nop
0x18002a13b  mov     eax, ebx
0x18002a13d  jmp     short loc_18002A167
0x18002a13f  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x18002a144  test    rcx, rcx
0x18002a147  jz      short loc_18002A15F
0x18002a149  mov     qword ptr [rsp+0A8h+var_88], 0
0x18002a152  mov     rax, [rcx]
0x18002a155  mov     rax, [rax+10h]
0x18002a159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a15e  nop
0x18002a15f  xor     eax, eax
0x18002a161  jmp     short loc_18002A167
0x18002a163  mov     eax, [rsp+0A8h+var_88]
0x18002a167  mov     rcx, [rsp+0A8h+var_18]
0x18002a16f  xor     rcx, rsp; StackCookie
0x18002a172  call    __security_check_cookie
0x18002a177  mov     rbx, [rsp+0A8h+arg_8]
0x18002a17f  add     rsp, 0A0h
0x18002a186  pop     rdi
0x18002a187  retn
```
