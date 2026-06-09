# SetupAutoLogWithTraceLevel(ushort const *,ushort const *,int,int)

- ea: `0x180006250`
- end: `0x1800064d4`
- name: `?SetupAutoLogWithTraceLevel@@YAJPEBG0HH@Z`
- size: `644`
- prototype: `__int64 __fastcall(wchar_t *String1, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006200`

## callees

- `0x180004f58`
- `0x180005a14`
- `0x180005f0c`
- `0x180006250`
- `0x1800064dc`
- `0x18000776c`
- `0x180007810`
- `0x1800243c4`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800062e0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800062e0`

## string_xrefs

- `0x1800062f4`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006370`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x180006468`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`
- `0x1800064a9`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
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
  int v16; // r9d
  int v17; // eax
  int v18; // r8d
  int v19; // eax
  unsigned int v20; // ebx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  int ppvb; // [rsp+20h] [rbp-58h]
  int ppvc; // [rsp+20h] [rbp-58h]
  _QWORD v25[9]; // [rsp+30h] [rbp-48h] BYREF
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
        v25[0] = v27;
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
          v25[0] = v27;
          if ( v27 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
          LOBYTE(v16) = a3 == 1;
          v17 = SetupAllAutoLogForArea(
                  (unsigned int)v25,
                  (_DWORD)String1,
                  (unsigned int)L"Software\\OSData\\Microsoft\\DiagnosticLogCSP",
                  v16,
                  a4);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v18,
              v16,
              (__int64)String1,
              v17,
              v25[0]);
        }
        v25[0] = v27;
        if ( v27 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 8LL))(v27);
        LOBYTE(v16) = a3 == 1;
        v19 = SetupAllAutoLogForArea(
                (unsigned int)v25,
                (_DWORD)String1,
                (unsigned int)L"Software\\Microsoft\\DiagnosticLogCSP",
                v16,
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
0x180006250  push    rbx
0x180006252  push    rsi
0x180006253  push    rdi
0x180006254  push    r12
0x180006256  push    r14
0x180006258  push    r15
0x18000625a  sub     rsp, 48h
0x18000625e  mov     r15d, r9d
0x180006261  mov     r14d, r8d
0x180006264  mov     rdi, rdx
0x180006267  mov     rbx, rcx
0x18000626a  xor     r12d, r12d
0x18000626d  test    rcx, rcx
0x180006270  jz      loc_18000649C
0x180006276  cmp     [rcx], r12w
0x18000627a  jz      loc_18000649C
0x180006280  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x180006287  mov     rcx, cs:WPP_GLOBAL_Control
0x18000628e  cmp     rcx, rax
0x180006291  jz      short loc_1800062AA
0x180006293  test    byte ptr [rcx+1Ch], 2
0x180006297  jz      short loc_1800062AA
0x180006299  mov     [rsp+78h+ppv], rdx
0x18000629e  mov     r9, rbx
0x1800062a1  mov     rcx, [rcx+10h]
0x1800062a5  call    WPP_SF_SS
0x1800062aa  mov     [rsp+78h+arg_0], r12
0x1800062b2  lea     rcx, [rsp+78h+arg_0]
0x1800062ba  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x1800062bf  lea     rax, [rsp+78h+arg_0]
0x1800062c7  mov     [rsp+78h+ppv], rax; int
0x1800062cc  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800062d3  xor     edx, edx; pUnkOuter
0x1800062d5  lea     r8d, [rdx+1]; dwClsContext
0x1800062d9  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800062e0  call    cs:__imp_CoCreateInstance
0x1800062e6  mov     esi, eax
0x1800062e8  test    eax, eax
0x1800062ea  jns     short loc_18000631A
0x1800062ec  mov     rcx, [rsp+78h]; this
0x1800062f1  mov     r9d, eax; char *
0x1800062f4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800062fb  mov     edx, 139h; void *
0x180006300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006305  nop
0x180006306  lea     rcx, [rsp+78h+arg_0]
0x18000630e  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006313  mov     eax, esi
0x180006315  jmp     loc_1800064C5
0x18000631a  test    rdi, rdi
0x18000631d  jz      short loc_180006396
0x18000631f  cmp     r14d, 1
0x180006323  setz    sil
0x180006327  mov     rcx, [rsp+78h+arg_0]
0x18000632f  mov     [rsp+78h+var_48], rcx
0x180006334  test    rcx, rcx
0x180006337  jz      short loc_180006346
0x180006339  mov     rax, [rcx]
0x18000633c  mov     rax, [rax+8]
0x180006340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006345  nop
0x180006346  mov     dword ptr [rsp+78h+ppv], r15d; int
0x18000634b  mov     r9b, sil
0x18000634e  mov     r8, rdi
0x180006351  mov     rdx, rbx
0x180006354  lea     rcx, [rsp+78h+var_48]
0x180006359  call    ?SetupOneAutoLog@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupOneAutoLog(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x18000635e  mov     ebx, eax
0x180006360  test    eax, eax
0x180006362  jns     loc_18000648B
0x180006368  mov     rcx, [rsp+78h]; this
0x18000636d  mov     r9d, eax; char *
0x180006370  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180006377  mov     edx, 13Dh; void *
0x18000637c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006381  nop
0x180006382  lea     rcx, [rsp+78h+arg_0]
0x18000638a  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x18000638f  mov     eax, ebx
0x180006391  jmp     loc_1800064C5
0x180006396  lea     rdx, aDeviceprovisio; "DeviceProvisioning"
0x18000639d  mov     rcx, rbx; String1
0x1800063a0  call    wcscmp_0
0x1800063a5  test    eax, eax
0x1800063a7  jnz     short loc_180006417
0x1800063a9  cmp     r14d, 1
0x1800063ad  setz    dil
0x1800063b1  mov     rcx, [rsp+78h+arg_0]
0x1800063b9  mov     [rsp+78h+var_48], rcx
0x1800063be  test    rcx, rcx
0x1800063c1  jz      short loc_1800063D0
0x1800063c3  mov     rax, [rcx]
0x1800063c6  mov     rax, [rax+8]
0x1800063ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063cf  nop
0x1800063d0  mov     dword ptr [rsp+78h+ppv], r15d
0x1800063d5  mov     r9b, dil
0x1800063d8  lea     r8, aSoftwareOsdata; "Software\\OSData\\Microsoft\\Diagnostic"...
0x1800063df  mov     rdx, rbx
0x1800063e2  lea     rcx, [rsp+78h+var_48]
0x1800063e7  call    ?SetupAllAutoLogForArea@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupAllAutoLogForArea(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x1800063ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800063f3  lea     rdx, WPP_GLOBAL_Control
0x1800063fa  cmp     rcx, rdx
0x1800063fd  jz      short loc_180006417
0x1800063ff  test    byte ptr [rcx+1Ch], 2
0x180006403  jz      short loc_180006417
0x180006405  mov     [rsp+78h+var_50], eax
0x180006409  mov     [rsp+78h+ppv], rbx
0x18000640e  mov     rcx, [rcx+10h]
0x180006412  call    WPP_SF_SSd
0x180006417  cmp     r14d, 1
0x18000641b  setz    dil
0x18000641f  mov     rcx, [rsp+78h+arg_0]
0x180006427  mov     [rsp+78h+var_48], rcx
0x18000642c  test    rcx, rcx
0x18000642f  jz      short loc_18000643E
0x180006431  mov     rax, [rcx]
0x180006434  mov     rax, [rax+8]
0x180006438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000643d  nop
0x18000643e  mov     dword ptr [rsp+78h+ppv], r15d; int
0x180006443  mov     r9b, dil
0x180006446  lea     r8, aSoftwareMicros; "Software\\Microsoft\\DiagnosticLogCSP"
0x18000644d  mov     rdx, rbx
0x180006450  lea     rcx, [rsp+78h+var_48]
0x180006455  call    ?SetupAllAutoLogForArea@@YAJV?$ComPtr@UIConfigManager2@@@WRL@Microsoft@@PEBG1_NH@Z; SetupAllAutoLogForArea(Microsoft::WRL::ComPtr<IConfigManager2>,ushort const *,ushort const *,bool,int)
0x18000645a  mov     ebx, eax
0x18000645c  test    eax, eax
0x18000645e  jns     short loc_18000648B
0x180006460  mov     rcx, [rsp+78h]; this
0x180006465  mov     r9d, eax; char *
0x180006468  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000646f  mov     edx, 154h; void *
0x180006474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006479  nop
0x18000647a  lea     rcx, [rsp+78h+arg_0]
0x180006482  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006487  mov     eax, ebx
0x180006489  jmp     short loc_1800064C5
0x18000648b  lea     rcx, [rsp+78h+arg_0]
0x180006493  call    ?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)
0x180006498  xor     eax, eax
0x18000649a  jmp     short loc_1800064C5
0x18000649c  mov     rcx, [rsp+78h]; this
0x1800064a1  mov     ebx, 80070057h
0x1800064a6  mov     r9d, ebx; char *
0x1800064a9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800064b0  mov     edx, 130h; void *
0x1800064b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064ba  mov     eax, ebx
0x1800064bc  jmp     short loc_1800064C5
0x1800064be  mov     eax, dword ptr [rsp+78h+arg_0]
0x1800064c5  add     rsp, 48h
0x1800064c9  pop     r15
0x1800064cb  pop     r14
0x1800064cd  pop     r12
0x1800064cf  pop     rdi
0x1800064d0  pop     rsi
0x1800064d1  pop     rbx
0x1800064d2  retn
```
