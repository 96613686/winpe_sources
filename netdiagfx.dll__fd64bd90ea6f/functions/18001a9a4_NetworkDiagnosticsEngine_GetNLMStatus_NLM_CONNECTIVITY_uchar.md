# NetworkDiagnosticsEngine::GetNLMStatus(NLM_CONNECTIVITY *,uchar *)

- ea: `0x18001a9a4`
- end: `0x18001ad8c`
- name: `?GetNLMStatus@NetworkDiagnosticsEngine@@AEAAJPEAW4NLM_CONNECTIVITY@@PEAE@Z`
- size: `1000`
- prototype: `__int64 __fastcall(NetworkDiagnosticsEngine *__hidden this, enum NLM_CONNECTIVITY *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x18001a9a4`
- `0x18001bf9c`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001aba5`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001aba5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aa47`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aa47`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a9db`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a9db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001aa6c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001aae7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ac9f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ad66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001aa6c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001aae7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ac9f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ad66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NetworkDiagnosticsEngine::GetNLMStatus(
        NetworkDiagnosticsEngine *this,
        enum NLM_CONNECTIVITY *a2,
        unsigned __int8 *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // edi
  HRESULT v8; // eax
  LPVOID v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  LPVOID v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // edi
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // ebx
  __int64 v20; // rcx
  LPVOID v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  LPVOID v26; // rcx
  int ppv; // [rsp+20h] [rbp-39h]
  int ppva; // [rsp+20h] [rbp-39h]
  LPVOID v29; // [rsp+30h] [rbp-29h] BYREF
  __int64 v30; // [rsp+38h] [rbp-21h] BYREF
  char v31; // [rsp+40h] [rbp-19h]
  __int64 v32; // [rsp+48h] [rbp-11h] BYREF
  __int64 v33; // [rsp+50h] [rbp-9h] BYREF
  __int64 v34; // [rsp+58h] [rbp-1h] BYREF
  int v35; // [rsp+60h] [rbp+7h] BYREF
  int v36; // [rsp+64h] [rbp+Bh] BYREF
  NET_LUID InterfaceLuid; // [rsp+68h] [rbp+Fh] BYREF
  GUID InterfaceGuid; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v29 = 0;
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"net\\diagnostics\\netdiagfx\\svc\\engine\\networkdiagnosticsengine.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    return v6;
  }
  v31 = 1;
  v8 = CoCreateInstance(
         &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
         0,
         1u,
         &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
         &v29);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"net\\diagnostics\\netdiagfx\\svc\\engine\\networkdiagnosticsengine.cpp",
      (const char *)(unsigned int)v8,
      ppva);
    CoUninitialize();
    v9 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v6;
  }
  v30 = 0;
  v36 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v29 + 56LL))(v29, 1, &v30);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"net\\diagnostics\\netdiagfx\\svc\\engine\\networkdiagnosticsengine.cpp",
      (const char *)(unsigned int)v10,
      ppva);
    v11 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    CoUninitialize();
    v12 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v6;
  }
  if ( v30 )
  {
    v34 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v30 + 64LL))(
            v30,
            1,
            &v34,
            &v36) )
    {
      while ( 1 )
      {
        v33 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 104LL))(v34, &v33) )
        {
          v13 = v33;
          if ( v33 )
            break;
        }
LABEL_31:
        v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v30 + 64LL))(
                v30,
                1,
                &v34,
                &v36);
        v17 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        if ( v16 )
          goto LABEL_34;
      }
      v32 = 0;
      v35 = 0;
      while ( 1 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v13 + 64LL))(
               v13,
               1,
               &v32,
               &v35) )
        {
          v15 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          goto LABEL_31;
        }
        InterfaceGuid = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v32 + 96LL))(v32, &InterfaceGuid);
        v6 = v14;
        if ( v14 < 0 )
          break;
        InterfaceLuid.Value = 0;
        if ( !ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid) )
        {
          if ( *((unsigned __int16 *)&InterfaceLuid.Info + 3) == 6 )
          {
            *a3 |= 1u;
          }
          else if ( *((unsigned __int16 *)&InterfaceLuid.Info + 3) == 71 )
          {
            *a3 |= 2u;
          }
          else if ( (unsigned int)*((unsigned __int16 *)&InterfaceLuid.Info + 3) - 243 <= 1 )
          {
            *a3 |= 4u;
          }
        }
        v13 = v33;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"net\\diagnostics\\netdiagfx\\svc\\engine\\networkdiagnosticsengine.cpp",
        (const char *)(unsigned int)v14,
        ppva);
      v22 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      CoUninitialize();
      v26 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return v6;
    }
LABEL_34:
    v18 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  v19 = (*(__int64 (__fastcall **)(LPVOID, enum NLM_CONNECTIVITY *))(*(_QWORD *)v29 + 104LL))(v29, a2);
  v20 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  CoUninitialize();
  v21 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return v19;
}

```

## disassembly

```asm
0x18001a9a4  mov     [rsp-8+arg_0], rbx
0x18001a9a9  push    rbp
0x18001a9aa  push    rsi
0x18001a9ab  push    rdi
0x18001a9ac  push    r14
0x18001a9ae  push    r15
0x18001a9b0  lea     rbp, [rsp-37h]
0x18001a9b5  sub     rsp, 90h
0x18001a9bc  mov     rax, cs:__security_cookie
0x18001a9c3  xor     rax, rsp
0x18001a9c6  mov     [rbp+57h+var_30], rax
0x18001a9ca  mov     rbx, r8
0x18001a9cd  mov     rsi, rdx
0x18001a9d0  xor     r14d, r14d
0x18001a9d3  mov     [rbp+57h+var_80], r14
0x18001a9d7  xor     edx, edx; dwCoInit
0x18001a9d9  xor     ecx, ecx; pvReserved
0x18001a9db  call    cs:__imp_CoInitializeEx
0x18001a9e1  mov     edi, eax
0x18001a9e3  test    eax, eax
0x18001a9e5  jns     short loc_18001AA21
0x18001a9e7  mov     rcx, [rbp+5Fh]; this
0x18001a9eb  mov     r9d, eax; char *
0x18001a9ee  lea     r8, aNetDiagnostics; "net\\diagnostics\\netdiagfx\\svc\\engin"...
0x18001a9f5  mov     edx, 120h; void *
0x18001a9fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9ff  nop
0x18001aa00  mov     rcx, [rbp+57h+var_80]
0x18001aa04  test    rcx, rcx
0x18001aa07  jz      short loc_18001AA1A
0x18001aa09  mov     [rbp+57h+var_80], r14
0x18001aa0d  mov     rax, [rcx]
0x18001aa10  mov     rax, [rax+10h]
0x18001aa14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa19  nop
0x18001aa1a  mov     eax, edi
0x18001aa1c  jmp     loc_18001ACC2
0x18001aa21  mov     r15d, 1
0x18001aa27  mov     [rbp+57h+var_70], r15b
0x18001aa2b  lea     rax, [rbp+57h+var_80]
0x18001aa2f  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x18001aa34  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18001aa3b  mov     r8d, r15d; dwClsContext
0x18001aa3e  xor     edx, edx; pUnkOuter
0x18001aa40  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x18001aa47  call    cs:__imp_CoCreateInstance
0x18001aa4d  mov     edi, eax
0x18001aa4f  test    eax, eax
0x18001aa51  jns     short loc_18001AA8F
0x18001aa53  mov     rcx, [rbp+5Fh]; this
0x18001aa57  mov     r9d, eax; char *
0x18001aa5a  lea     r8, aNetDiagnostics; "net\\diagnostics\\netdiagfx\\svc\\engin"...
0x18001aa61  mov     edx, 128h; void *
0x18001aa66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa6b  nop
0x18001aa6c  call    cs:__imp_CoUninitialize
0x18001aa72  nop
0x18001aa73  mov     rcx, [rbp+57h+var_80]
0x18001aa77  test    rcx, rcx
0x18001aa7a  jz      short loc_18001AA8D
0x18001aa7c  mov     [rbp+57h+var_80], r14
0x18001aa80  mov     rax, [rcx]
0x18001aa83  mov     rax, [rax+10h]
0x18001aa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa8c  nop
0x18001aa8d  jmp     short loc_18001AA1A
0x18001aa8f  mov     [rbp+57h+var_78], r14
0x18001aa93  mov     [rbp+57h+var_4C], r14d
0x18001aa97  mov     rcx, [rbp+57h+var_80]
0x18001aa9b  mov     rax, [rcx]
0x18001aa9e  lea     r8, [rbp+57h+var_78]
0x18001aaa2  mov     edx, r15d
0x18001aaa5  mov     rax, [rax+38h]
0x18001aaa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaae  mov     edi, eax
0x18001aab0  test    eax, eax
0x18001aab2  jns     short loc_18001AB0D
0x18001aab4  mov     rcx, [rbp+5Fh]; this
0x18001aab8  mov     r9d, eax; char *
0x18001aabb  lea     r8, aNetDiagnostics; "net\\diagnostics\\netdiagfx\\svc\\engin"...
0x18001aac2  mov     edx, 12Fh; void *
0x18001aac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aacc  nop
0x18001aacd  mov     rcx, [rbp+57h+var_78]
0x18001aad1  test    rcx, rcx
0x18001aad4  jz      short loc_18001AAE7
0x18001aad6  mov     [rbp+57h+var_78], r14
0x18001aada  mov     rax, [rcx]
0x18001aadd  mov     rax, [rax+10h]
0x18001aae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aae6  nop
0x18001aae7  call    cs:__imp_CoUninitialize
0x18001aaed  nop
0x18001aaee  mov     rcx, [rbp+57h+var_80]
0x18001aaf2  test    rcx, rcx
0x18001aaf5  jz      short loc_18001AB08
0x18001aaf7  mov     [rbp+57h+var_80], r14
0x18001aafb  mov     rax, [rcx]
0x18001aafe  mov     rax, [rax+10h]
0x18001ab02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab07  nop
0x18001ab08  jmp     loc_18001AA1A
0x18001ab0d  mov     rcx, [rbp+57h+var_78]
0x18001ab11  test    rcx, rcx
0x18001ab14  jz      loc_18001AC70
0x18001ab1a  mov     [rbp+57h+var_58], r14
0x18001ab1e  mov     rax, [rcx]
0x18001ab21  lea     r9, [rbp+57h+var_4C]
0x18001ab25  lea     r8, [rbp+57h+var_58]
0x18001ab29  mov     edx, r15d
0x18001ab2c  mov     rax, [rax+40h]
0x18001ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab35  test    eax, eax
0x18001ab37  jnz     loc_18001AC56
0x18001ab3d  mov     [rbp+57h+var_60], r14
0x18001ab41  mov     rcx, [rbp+57h+var_58]
0x18001ab45  mov     rax, [rcx]
0x18001ab48  lea     rdx, [rbp+57h+var_60]
0x18001ab4c  mov     rax, [rax+68h]
0x18001ab50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab55  test    eax, eax
0x18001ab57  jnz     loc_18001AC17
0x18001ab5d  mov     rcx, [rbp+57h+var_60]
0x18001ab61  test    rcx, rcx
0x18001ab64  jz      loc_18001AC17
0x18001ab6a  mov     [rbp+57h+var_68], r14
0x18001ab6e  mov     [rbp+57h+var_50], r14d
0x18001ab72  jmp     short loc_18001ABDE
0x18001ab74  xorps   xmm0, xmm0
0x18001ab77  movups  xmmword ptr [rbp+57h+InterfaceGuid.Data1], xmm0
0x18001ab7b  mov     rcx, [rbp+57h+var_68]
0x18001ab7f  mov     rax, [rcx]
0x18001ab82  lea     rdx, [rbp+57h+InterfaceGuid]
0x18001ab86  mov     rax, [rax+60h]
0x18001ab8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab8f  mov     edi, eax
0x18001ab91  test    eax, eax
0x18001ab93  js      loc_18001ACE5
0x18001ab99  mov     qword ptr [rbp+57h+InterfaceLuid], r14
0x18001ab9d  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18001aba1  lea     rcx, [rbp+57h+InterfaceGuid]; InterfaceGuid
0x18001aba5  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18001abab  test    eax, eax
0x18001abad  jnz     short loc_18001ABDA
0x18001abaf  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x18001abb3  shr     rax, 30h
0x18001abb7  sub     eax, 6
0x18001abba  jz      short loc_18001ABD7
0x18001abbc  sub     eax, 41h ; 'A'
0x18001abbf  jz      short loc_18001ABD2
0x18001abc1  sub     eax, 0ACh
0x18001abc6  jz      short loc_18001ABCD
0x18001abc8  cmp     eax, 1
0x18001abcb  jnz     short loc_18001ABDA
0x18001abcd  or      byte ptr [rbx], 4
0x18001abd0  jmp     short loc_18001ABDA
0x18001abd2  or      byte ptr [rbx], 2
0x18001abd5  jmp     short loc_18001ABDA
0x18001abd7  or      [rbx], r15b
0x18001abda  mov     rcx, [rbp+57h+var_60]
0x18001abde  mov     rax, [rcx]
0x18001abe1  lea     r9, [rbp+57h+var_50]
0x18001abe5  lea     r8, [rbp+57h+var_68]
0x18001abe9  mov     edx, r15d
0x18001abec  mov     rax, [rax+40h]
0x18001abf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf5  test    eax, eax
0x18001abf7  jz      loc_18001AB74
0x18001abfd  mov     rcx, [rbp+57h+var_68]
0x18001ac01  test    rcx, rcx
0x18001ac04  jz      short loc_18001AC17
0x18001ac06  mov     [rbp+57h+var_68], r14
0x18001ac0a  mov     rax, [rcx]
0x18001ac0d  mov     rax, [rax+10h]
0x18001ac11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac16  nop
0x18001ac17  mov     rcx, [rbp+57h+var_78]
0x18001ac1b  mov     rax, [rcx]
0x18001ac1e  lea     r9, [rbp+57h+var_4C]
0x18001ac22  lea     r8, [rbp+57h+var_58]
0x18001ac26  mov     edx, r15d
0x18001ac29  mov     rax, [rax+40h]
0x18001ac2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac32  mov     edi, eax
0x18001ac34  mov     rcx, [rbp+57h+var_60]
0x18001ac38  test    rcx, rcx
0x18001ac3b  jz      short loc_18001AC4E
0x18001ac3d  mov     [rbp+57h+var_60], r14
0x18001ac41  mov     rdx, [rcx]
0x18001ac44  mov     rax, [rdx+10h]
0x18001ac48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac4d  nop
0x18001ac4e  test    edi, edi
0x18001ac50  jz      loc_18001AB3D
0x18001ac56  mov     rcx, [rbp+57h+var_58]
0x18001ac5a  test    rcx, rcx
0x18001ac5d  jz      short loc_18001AC70
0x18001ac5f  mov     [rbp+57h+var_58], r14
0x18001ac63  mov     rax, [rcx]
0x18001ac66  mov     rax, [rax+10h]
0x18001ac6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac6f  nop
0x18001ac70  mov     rcx, [rbp+57h+var_80]
0x18001ac74  mov     rax, [rcx]
0x18001ac77  mov     rdx, rsi
0x18001ac7a  mov     rax, [rax+68h]
0x18001ac7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac83  mov     ebx, eax
0x18001ac85  mov     rcx, [rbp+57h+var_78]
0x18001ac89  test    rcx, rcx
0x18001ac8c  jz      short loc_18001AC9F
0x18001ac8e  mov     [rbp+57h+var_78], r14
0x18001ac92  mov     rdx, [rcx]
0x18001ac95  mov     rax, [rdx+10h]
0x18001ac99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac9e  nop
0x18001ac9f  call    cs:__imp_CoUninitialize
0x18001aca5  nop
0x18001aca6  mov     rcx, [rbp+57h+var_80]
0x18001acaa  test    rcx, rcx
0x18001acad  jz      short loc_18001ACC0
0x18001acaf  mov     [rbp+57h+var_80], r14
0x18001acb3  mov     rax, [rcx]
0x18001acb6  mov     rax, [rax+10h]
0x18001acba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acbf  nop
0x18001acc0  mov     eax, ebx
0x18001acc2  mov     rcx, [rbp+57h+var_30]
0x18001acc6  xor     rcx, rsp; StackCookie
0x18001acc9  call    __security_check_cookie
0x18001acce  mov     rbx, [rsp+0B0h+arg_0]
0x18001acd6  add     rsp, 90h
0x18001acdd  pop     r15
0x18001acdf  pop     r14
0x18001ace1  pop     rdi
0x18001ace2  pop     rsi
0x18001ace3  pop     rbp
0x18001ace4  retn
0x18001ace5  mov     rcx, [rbp+5Fh]; this
0x18001ace9  mov     r9d, edi; char *
0x18001acec  lea     r8, aNetDiagnostics; "net\\diagnostics\\netdiagfx\\svc\\engin"...
0x18001acf3  mov     edx, 14Dh; void *
0x18001acf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001acfd  nop
0x18001acfe  mov     rcx, [rbp+57h+var_68]
0x18001ad02  test    rcx, rcx
0x18001ad05  jz      short loc_18001AD18
0x18001ad07  mov     [rbp+57h+var_68], r14
0x18001ad0b  mov     rax, [rcx]
0x18001ad0e  mov     rax, [rax+10h]
0x18001ad12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad17  nop
0x18001ad18  mov     rcx, [rbp+57h+var_60]
0x18001ad1c  test    rcx, rcx
0x18001ad1f  jz      short loc_18001AD32
0x18001ad21  mov     [rbp+57h+var_60], r14
0x18001ad25  mov     rax, [rcx]
0x18001ad28  mov     rax, [rax+10h]
0x18001ad2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad31  nop
0x18001ad32  mov     rcx, [rbp+57h+var_58]
0x18001ad36  test    rcx, rcx
0x18001ad39  jz      short loc_18001AD4C
0x18001ad3b  mov     [rbp+57h+var_58], r14
0x18001ad3f  mov     rax, [rcx]
0x18001ad42  mov     rax, [rax+10h]
0x18001ad46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad4b  nop
0x18001ad4c  mov     rcx, [rbp+57h+var_78]
0x18001ad50  test    rcx, rcx
0x18001ad53  jz      short loc_18001AD66
0x18001ad55  mov     [rbp+57h+var_78], r14
0x18001ad59  mov     rax, [rcx]
0x18001ad5c  mov     rax, [rax+10h]
0x18001ad60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad65  nop
0x18001ad66  call    cs:__imp_CoUninitialize
0x18001ad6c  nop
0x18001ad6d  mov     rcx, [rbp+57h+var_80]
0x18001ad71  test    rcx, rcx
0x18001ad74  jz      short loc_18001AD87
0x18001ad76  mov     [rbp+57h+var_80], r14
0x18001ad7a  mov     rax, [rcx]
0x18001ad7d  mov     rax, [rax+10h]
0x18001ad81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad86  nop
0x18001ad87  jmp     loc_18001AA1A
```
