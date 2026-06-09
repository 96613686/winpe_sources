# RdpEdpPolicyManager::CreateInstance(RdpEdpPolicyManager * *)

- ea: `0x1800d8838`
- end: `0x1800d8a3a`
- name: `?CreateInstance@RdpEdpPolicyManager@@SAJPEAPEAV1@@Z`
- size: `514`
- prototype: `__int64 __fastcall(struct RdpEdpPolicyManager **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d0710`

## callees

- `0x180033964`
- `0x1800d8838`
- `0x1800d8bbc`
- `0x1800d8ccc`
- `0x1800d8d20`
- `0x18014d010`

## import_xrefs

- `RDPBASE!TRC_TraceBufferW` at `0x1800d8887`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8976`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8a07`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8887`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8976`
- `RDPBASE!TRC_TraceBufferW` at `0x1800d8a07`

## string_xrefs

- `0x1800d8867`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1800d8959`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1800d89e4`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x1800d8872`: `RdpEdpPolicyManager::CreateInstance`
- `0x1800d896a`: `RdpEdpPolicyManager::CreateInstance`
- `0x1800d89f0`: `RdpEdpPolicyManager::CreateInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RdpEdpPolicyManager::CreateInstance(struct RdpEdpPolicyManager **a1)
{
  unsigned int v2; // edi
  RdpEdpPolicyManager *v3; // rax
  RdpEdpPolicyManager *v4; // rbx
  int v5; // eax
  RdpEdpPolicyManager *v6; // rcx
  int IsProtectionEnabled; // eax
  int v9; // [rsp+60h] [rbp+8h] BYREF
  RdpEdpPolicyManager *v10; // [rsp+68h] [rbp+10h] BYREF
  RdpEdpPolicyManager *v11; // [rsp+70h] [rbp+18h]

  v10 = 0;
  v9 = 0;
  if ( !a1 )
  {
    TRC_TraceBufferW(
      3,
      512,
      134,
      L"RdpEdpPolicyManager::CreateInstance",
      L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
      0,
      L"Unexpected NULL pointer");
    v2 = -2147467261;
LABEL_13:
    v4 = 0;
    goto LABEL_14;
  }
  *a1 = 0;
  v3 = (RdpEdpPolicyManager *)operator new(0x58u);
  v4 = v3;
  v11 = v3;
  if ( !v3 )
  {
    TRC_TraceBufferW(
      3,
      512,
      138,
      L"RdpEdpPolicyManager::CreateInstance",
      L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
      0,
      L"OOM on RdpEdpPolicyManager");
    v2 = -2147024882;
    goto LABEL_13;
  }
  *((_DWORD *)v3 + 6) = -607474739;
  *((_QWORD *)v3 + 2) = "RdpEdpPolicyManager";
  *((_DWORD *)v3 + 7) = 1;
  *(_QWORD *)v3 = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v3 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 4) = v3;
  *(_QWORD *)v3 = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v3 + 1) = &RdpEdpPolicyManager::`vftable'{for `CTSObject'};
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  *((_QWORD *)v3 + 9) = 0;
  *((_QWORD *)v3 + 10) = 0;
  v10 = v3;
  Microsoft::WRL::ComPtr<RdpEdpPolicyManager>::InternalAddRef(&v10);
  v10 = v4;
  v5 = RdpEdpPolicyManager::InitializeInstance(v4);
  v2 = v5;
  if ( v5 >= 0 )
  {
    IsProtectionEnabled = RdpEdpPolicyManager::IsProtectionEnabled(v6, &v9);
    v2 = IsProtectionEnabled;
    if ( IsProtectionEnabled >= 0 )
    {
      if ( !v9 )
      {
        (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)v4 + 4) + 16LL))(*((_QWORD **)v4 + 4));
        return 1;
      }
      Microsoft::WRL::ComPtr<RdpEdpPolicyManager>::InternalAddRef(&v10);
      *a1 = v4;
      v2 = 0;
    }
    else
    {
      TRC_TraceBufferW(
        3,
        512,
        144,
        L"RdpEdpPolicyManager::CreateInstance",
        L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        L"IsProtectionEnabled failed. hr[0x%x]",
        IsProtectionEnabled);
    }
  }
  else
  {
    TRC_TraceBufferW(
      3,
      512,
      141,
      L"RdpEdpPolicyManager::CreateInstance",
      L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
      0,
      L"InitializeInstance failed. hr[0x%x]",
      v5);
  }
LABEL_14:
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)v4 + 4) + 16LL))(*((_QWORD **)v4 + 4));
  return v2;
}

```

## disassembly

```asm
0x1800d8838  mov     r11, rsp
0x1800d883b  mov     [r11+20h], rbx
0x1800d883f  push    rbp
0x1800d8840  push    rsi
0x1800d8841  push    rdi
0x1800d8842  sub     rsp, 40h
0x1800d8846  mov     rsi, rcx
0x1800d8849  xor     ebp, ebp
0x1800d884b  mov     [r11+10h], rbp
0x1800d884f  mov     [rsp+58h+arg_0], ebp
0x1800d8853  test    rcx, rcx
0x1800d8856  jnz     short loc_1800D8897
0x1800d8858  lea     rax, aUnexpectedNull; "Unexpected NULL pointer"
0x1800d885f  mov     [r11-28h], rax
0x1800d8863  mov     [r11-30h], rbp
0x1800d8867  lea     rax, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1800d886e  mov     [r11-38h], rax
0x1800d8872  lea     r9, aRdpedppolicyma_2; "RdpEdpPolicyManager::CreateInstance"
0x1800d8879  mov     edx, 200h
0x1800d887e  lea     ecx, [rsi+3]
0x1800d8881  mov     r8d, 86h
0x1800d8887  call    cs:__imp_TRC_TraceBufferW
0x1800d888d  mov     edi, 80004003h
0x1800d8892  jmp     loc_1800D8A12
0x1800d8897  mov     [rcx], rbp
0x1800d889a  mov     ecx, 58h ; 'X'; Size
0x1800d889f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d88a4  mov     rbx, rax
0x1800d88a7  mov     [rsp+58h+arg_10], rax
0x1800d88ac  test    rax, rax
0x1800d88af  jz      loc_1800D89D3
0x1800d88b5  mov     dword ptr [rax+18h], 0DBCAABCDh
0x1800d88bc  lea     rax, aRdpedppolicyma_1; "RdpEdpPolicyManager"
0x1800d88c3  mov     [rbx+10h], rax
0x1800d88c7  mov     dword ptr [rbx+1Ch], 1
0x1800d88ce  lea     rax, ??_7CClipLevelCallback@@6BINonDelegatingUnknown@@@; const CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'}
0x1800d88d5  mov     [rbx], rax
0x1800d88d8  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x1800d88df  mov     [rbx+8], rax
0x1800d88e3  mov     [rbx+28h], ebp
0x1800d88e6  mov     [rbx+20h], rbx
0x1800d88ea  lea     rax, ??_7CClipLevelCallback@@6BINonDelegatingUnknown@@@; const CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'}
0x1800d88f1  mov     [rbx], rax
0x1800d88f4  lea     rax, ??_7RdpEdpPolicyManager@@6BCTSObject@@@; const RdpEdpPolicyManager::`vftable'{for `CTSObject'}
0x1800d88fb  mov     [rbx+8], rax
0x1800d88ff  mov     [rbx+30h], rbp
0x1800d8903  mov     [rbx+38h], rbp
0x1800d8907  mov     [rbx+40h], rbp
0x1800d890b  mov     [rbx+48h], rbp
0x1800d890f  mov     [rbx+50h], rbp
0x1800d8913  test    rbx, rbx
0x1800d8916  jz      loc_1800D89D3
0x1800d891c  mov     [rsp+58h+arg_8], rbx
0x1800d8921  lea     rcx, [rsp+58h+arg_8]
0x1800d8926  call    ?InternalAddRef@?$ComPtr@VRdpEdpPolicyManager@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<RdpEdpPolicyManager>::InternalAddRef(void)
0x1800d892b  mov     [rsp+58h+arg_8], rbx
0x1800d8930  mov     rcx, rbx; this
0x1800d8933  call    ?InitializeInstance@RdpEdpPolicyManager@@AEAAJXZ; RdpEdpPolicyManager::InitializeInstance(void)
0x1800d8938  mov     edi, eax
0x1800d893a  test    eax, eax
0x1800d893c  jns     short loc_1800D8981
0x1800d893e  mov     [rsp+58h+var_20], eax
0x1800d8942  lea     rax, aInitializeinst_0; "InitializeInstance failed. hr[0x%x]"
0x1800d8949  mov     r8d, 8Dh
0x1800d894f  mov     [rsp+58h+var_28], rax
0x1800d8954  mov     [rsp+58h+var_30], rbp
0x1800d8959  lea     rax, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1800d8960  mov     ecx, 3
0x1800d8965  mov     edx, 200h
0x1800d896a  lea     r9, aRdpedppolicyma_2; "RdpEdpPolicyManager::CreateInstance"
0x1800d8971  mov     [rsp+58h+var_38], rax
0x1800d8976  call    cs:__imp_TRC_TraceBufferW
0x1800d897c  jmp     loc_1800D8A15
0x1800d8981  lea     rdx, [rsp+58h+arg_0]; int *
0x1800d8986  call    ?IsProtectionEnabled@RdpEdpPolicyManager@@AEAAJPEAH@Z; RdpEdpPolicyManager::IsProtectionEnabled(int *)
0x1800d898b  mov     edi, eax
0x1800d898d  test    eax, eax
0x1800d898f  jns     short loc_1800D89A4
0x1800d8991  mov     [rsp+58h+var_20], eax
0x1800d8995  lea     rax, aIsprotectionen; "IsProtectionEnabled failed. hr[0x%x]"
0x1800d899c  mov     r8d, 90h
0x1800d89a2  jmp     short loc_1800D894F
0x1800d89a4  cmp     [rsp+58h+arg_0], ebp
0x1800d89a8  jnz     short loc_1800D89C2
0x1800d89aa  mov     rcx, [rbx+20h]
0x1800d89ae  mov     rdx, [rcx]
0x1800d89b1  mov     rax, [rdx+10h]
0x1800d89b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d89ba  nop
0x1800d89bb  mov     eax, 1
0x1800d89c0  jmp     short loc_1800D8A2D
0x1800d89c2  lea     rcx, [rsp+58h+arg_8]
0x1800d89c7  call    ?InternalAddRef@?$ComPtr@VRdpEdpPolicyManager@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<RdpEdpPolicyManager>::InternalAddRef(void)
0x1800d89cc  mov     [rsi], rbx
0x1800d89cf  mov     edi, ebp
0x1800d89d1  jmp     short loc_1800D8A15
0x1800d89d3  lea     rax, aOomOnRdpedppol; "OOM on RdpEdpPolicyManager"
0x1800d89da  mov     [rsp+58h+var_28], rax
0x1800d89df  mov     [rsp+58h+var_30], rbp
0x1800d89e4  lea     rax, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x1800d89eb  mov     [rsp+58h+var_38], rax
0x1800d89f0  lea     r9, aRdpedppolicyma_2; "RdpEdpPolicyManager::CreateInstance"
0x1800d89f7  mov     edx, 200h
0x1800d89fc  mov     ecx, 3
0x1800d8a01  mov     r8d, 8Ah
0x1800d8a07  call    cs:__imp_TRC_TraceBufferW
0x1800d8a0d  mov     edi, 8007000Eh
0x1800d8a12  mov     rbx, rbp
0x1800d8a15  test    rbx, rbx
0x1800d8a18  jz      short loc_1800D8A2B
0x1800d8a1a  mov     rcx, [rbx+20h]
0x1800d8a1e  mov     rax, [rcx]
0x1800d8a21  mov     rax, [rax+10h]
0x1800d8a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8a2a  nop
0x1800d8a2b  mov     eax, edi
0x1800d8a2d  mov     rbx, [rsp+58h+arg_18]
0x1800d8a32  add     rsp, 40h
0x1800d8a36  pop     rdi
0x1800d8a37  pop     rsi
0x1800d8a38  pop     rbp
0x1800d8a39  retn
```
