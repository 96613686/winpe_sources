# SetupAutoLogWithTraceLevel(ushort const *,ushort const *,int,int)

- ea: `0x1800064a0`
- end: `0x18000672a`
- name: `?SetupAutoLogWithTraceLevel@@YAJPEBG0HH@Z`
- size: `650`
- prototype: `__int64 __fastcall(wchar_t *String1, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006450`

## callees

- `0x1800050e0`
- `0x180005c14`
- `0x180006138`
- `0x1800064a0`
- `0x180006730`
- `0x180007a9c`
- `0x180007b48`
- `0x180025284`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006530`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006530`

## string_xrefs

- `0x18000654a`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800065c6`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800066be`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800066ff`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetupAutoLogWithTraceLevel(wchar_t *String1, const unsigned __int16 *a2, int a3, int a4)
{
  HRESULT v8; // eax
  int v9; // r9d
  unsigned int v10; // esi
  unsigned int v11; // r8d
  const char *v12; // r9
  __int64 result; // rax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  unsigned int v20; // ebx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  int ppvb; // [rsp+20h] [rbp-58h]
  int ppvc; // [rsp+20h] [rbp-58h]
  __int64 v25[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  LPVOID v27; // [rsp+80h] [rbp+8h] BYREF

  try
  {
    if ( String1 && *String1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)String1, (__int64)a2);
      v27 = 0;
      Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v27);
      v8 = CoCreateInstance(
             &GUID_66d0db14_5638_475f_a386_629522d8c461,
             0,
             1u,
             &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
             &v27);
      v10 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
          (const char *)(unsigned int)v8,
          ppva);
        Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v27);
        return v10;
      }
      if ( a2 )
      {
        v25[0] = (__int64)v27;
        if ( v27 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
        LOBYTE(v9) = a3 == 1;
        v14 = SetupOneAutoLog((unsigned int)v25, (_DWORD)String1, (_DWORD)a2, v9, a4);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
            (const char *)(unsigned int)v14,
            ppvb);
          Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v27);
          return v15;
        }
      }
      else
      {
        if ( !wcscmp_0(String1, L"DeviceProvisioning") )
        {
          v25[0] = (__int64)v27;
          if ( v27 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
          v16 = SetupAllAutoLogForArea(
                  v25,
                  (__int64)String1,
                  (__int64)L"Software\\OSData\\Microsoft\\DiagnosticLogCSP",
                  a3 == 1,
                  a4);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v17,
              v18,
              (__int64)String1,
              v16,
              v25[0]);
        }
        v25[0] = (__int64)v27;
        if ( v27 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
        v19 = SetupAllAutoLogForArea(
                v25,
                (__int64)String1,
                (__int64)L"Software\\Microsoft\\DiagnosticLogCSP",
                a3 == 1,
                a4);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
            (const char *)(unsigned int)v19,
            ppvc);
          Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v27);
          return v20;
        }
      }
      Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(&v27);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
        (const char *)0x80070057LL,
        ppv);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x158, v11, v12);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x1800064a0  push    rbx
0x1800064a2  push    rsi
0x1800064a3  push    rdi
0x1800064a4  push    r12
0x1800064a6  push    r14
0x1800064a8  push    r15
0x1800064aa  sub     rsp, 48h
0x1800064ae  mov     r15d, r9d
0x1800064b1  mov     r14d, r8d
0x1800064b4  mov     rdi, rdx
0x1800064b7  mov     rbx, rcx
0x1800064ba  xor     r12d, r12d
0x1800064bd  test    rcx, rcx
0x1800064c0  jz      loc_1800066F2
0x1800064c6  cmp     [rcx], r12w
0x1800064ca  jz      loc_1800066F2
0x1800064d0  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800064d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064de  cmp     rcx, rax
0x1800064e1  jz      short loc_1800064FA
0x1800064e3  test    byte ptr [rcx+1Ch], 2
0x1800064e7  jz      short loc_1800064FA
0x1800064e9  mov     [rsp+78h+ppv], rdx
0x1800064ee  mov     r9, rbx
0x1800064f1  mov     rcx, [rcx+10h]
0x1800064f5  call    WPP_SF_SS
0x1800064fa  mov     [rsp+78h+arg_0], r12
0x180006502  lea     rcx, [rsp+78h+arg_0]
0x18000650a  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x18000650f  lea     rax, [rsp+78h+arg_0]
0x180006517  mov     [rsp+78h+ppv], rax; int
0x18000651c  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180006523  xor     edx, edx; pUnkOuter
0x180006525  lea     r8d, [rdx+1]; dwClsContext
0x180006529  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180006530  call    cs:__imp_CoCreateInstance
0x180006537  nop     dword ptr [rax+rax+00h]
0x18000653c  mov     esi, eax
0x18000653e  test    eax, eax
0x180006540  jns     short loc_180006570
0x180006542  mov     rcx, [rsp+78h]; this
0x180006547  mov     r9d, eax; char *
0x18000654a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006551  mov     edx, 139h; void *
0x180006556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000655b  nop
0x18000655c  lea     rcx, [rsp+78h+arg_0]
0x180006564  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006569  mov     eax, esi
0x18000656b  jmp     loc_18000671B
0x180006570  test    rdi, rdi
0x180006573  jz      short loc_1800065EC
0x180006575  cmp     r14d, 1
0x180006579  setz    sil
0x18000657d  mov     rcx, [rsp+78h+arg_0]
0x180006585  mov     [rsp+78h+var_48], rcx
0x18000658a  test    rcx, rcx
0x18000658d  jz      short loc_18000659C
0x18000658f  mov     rax, [rcx]
0x180006592  mov     rax, [rax+8]
0x180006596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659b  nop
0x18000659c  mov     dword ptr [rsp+78h+ppv], r15d; int
0x1800065a1  mov     r9b, sil
0x1800065a4  mov     r8, rdi
0x1800065a7  mov     rdx, rbx
0x1800065aa  lea     rcx, [rsp+78h+var_48]
0x1800065af  call    ?SetupOneAutoLog@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupOneAutoLog(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x1800065b4  mov     ebx, eax
0x1800065b6  test    eax, eax
0x1800065b8  jns     loc_1800066E1
0x1800065be  mov     rcx, [rsp+78h]; this
0x1800065c3  mov     r9d, eax; char *
0x1800065c6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800065cd  mov     edx, 13Dh; void *
0x1800065d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065d7  nop
0x1800065d8  lea     rcx, [rsp+78h+arg_0]
0x1800065e0  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800065e5  mov     eax, ebx
0x1800065e7  jmp     loc_18000671B
0x1800065ec  lea     rdx, aDeviceprovisio; "DeviceProvisioning"
0x1800065f3  mov     rcx, rbx; String1
0x1800065f6  call    wcscmp_0
0x1800065fb  test    eax, eax
0x1800065fd  jnz     short loc_18000666D
0x1800065ff  cmp     r14d, 1
0x180006603  setz    dil
0x180006607  mov     rcx, [rsp+78h+arg_0]
0x18000660f  mov     [rsp+78h+var_48], rcx
0x180006614  test    rcx, rcx
0x180006617  jz      short loc_180006626
0x180006619  mov     rax, [rcx]
0x18000661c  mov     rax, [rax+8]
0x180006620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006625  nop
0x180006626  mov     dword ptr [rsp+78h+ppv], r15d
0x18000662b  mov     r9b, dil
0x18000662e  lea     r8, aSoftwareOsdata; "Software\\OSData\\Microsoft\\Diagnostic"...
0x180006635  mov     rdx, rbx
0x180006638  lea     rcx, [rsp+78h+var_48]
0x18000663d  call    ?SetupAllAutoLogForArea@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupAllAutoLogForArea(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x180006642  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180006649  lea     rdx, WPP_GLOBAL_Control
0x180006650  cmp     rcx, rdx
0x180006653  jz      short loc_18000666D
0x180006655  test    byte ptr [rcx+1Ch], 2
0x180006659  jz      short loc_18000666D
0x18000665b  mov     [rsp+78h+var_50], eax
0x18000665f  mov     [rsp+78h+ppv], rbx
0x180006664  mov     rcx, [rcx+10h]
0x180006668  call    WPP_SF_SSd
0x18000666d  cmp     r14d, 1
0x180006671  setz    dil
0x180006675  mov     rcx, [rsp+78h+arg_0]
0x18000667d  mov     [rsp+78h+var_48], rcx
0x180006682  test    rcx, rcx
0x180006685  jz      short loc_180006694
0x180006687  mov     rax, [rcx]
0x18000668a  mov     rax, [rax+8]
0x18000668e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006693  nop
0x180006694  mov     dword ptr [rsp+78h+ppv], r15d; int
0x180006699  mov     r9b, dil
0x18000669c  lea     r8, aSoftwareMicros; "Software\\Microsoft\\DiagnosticLogCSP"
0x1800066a3  mov     rdx, rbx
0x1800066a6  lea     rcx, [rsp+78h+var_48]
0x1800066ab  call    ?SetupAllAutoLogForArea@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupAllAutoLogForArea(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x1800066b0  mov     ebx, eax
0x1800066b2  test    eax, eax
0x1800066b4  jns     short loc_1800066E1
0x1800066b6  mov     rcx, [rsp+78h]; this
0x1800066bb  mov     r9d, eax; char *
0x1800066be  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800066c5  mov     edx, 154h; void *
0x1800066ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066cf  nop
0x1800066d0  lea     rcx, [rsp+78h+arg_0]
0x1800066d8  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800066dd  mov     eax, ebx
0x1800066df  jmp     short loc_18000671B
0x1800066e1  lea     rcx, [rsp+78h+arg_0]
0x1800066e9  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800066ee  xor     eax, eax
0x1800066f0  jmp     short loc_18000671B
0x1800066f2  mov     rcx, [rsp+78h]; this
0x1800066f7  mov     ebx, 80070057h
0x1800066fc  mov     r9d, ebx; char *
0x1800066ff  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006706  mov     edx, 130h; void *
0x18000670b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006710  mov     eax, ebx
0x180006712  jmp     short loc_18000671B
0x180006714  mov     eax, dword ptr [rsp+78h+arg_0]
0x18000671b  add     rsp, 48h
0x18000671f  pop     r15
0x180006721  pop     r14
0x180006723  pop     r12
0x180006725  pop     rdi
0x180006726  pop     rsi
0x180006727  pop     rbx
0x180006728  retn
```
