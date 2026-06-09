# CSetLauncherWorkItem::SetLauncher(bool,ATL::CWindow const &)

- ea: `0x18000d3d0`
- end: `0x18000d68b`
- name: `?SetLauncher@CSetLauncherWorkItem@@SAX_NAEBVCWindow@ATL@@@Z`
- size: `699`
- prototype: `void __fastcall(unsigned __int8, HWND *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800091c0`
- `0x18000d2c0`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x180008b30`
- `0x18000ce60`
- `0x18000d038`
- `0x18000d3d0`
- `0x18000fb3c`
- `0x180011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000d424`
- `ole32!CoCreateInstance` at `0x18000d424`

## string_xrefs

- `0x18000d4e8`: `drivers\wdm\usbpw\launcher\dll\csetlauncherworkitem.cpp`
- `0x18000d545`: `drivers\wdm\usbpw\launcher\dll\csetlauncherworkitem.cpp`
- `0x18000d5a2`: `drivers\wdm\usbpw\launcher\dll\csetlauncherworkitem.cpp`
- `0x18000d5ff`: `drivers\wdm\usbpw\launcher\dll\csetlauncherworkitem.cpp`
- `0x18000d660`: `CLauncherIncompatibleMultipleBootDisksException()`

## pseudocode

```c
void __fastcall CSetLauncherWorkItem::SetLauncher(unsigned __int8 a1, HWND *a2)
{
  unsigned int v3; // edi
  const struct _GUID *v4; // rdx
  const struct _GUID *v5; // r8
  HRESULT v6; // eax
  int v7; // ebx
  HRESULT v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // ebx
  int v14; // ebx
  int v15; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp+20h] BYREF
  int v18; // [rsp+68h] [rbp+28h]

  v3 = a1;
  ppv = 0;
  v18 = 1;
  if ( utils::CProcess::IsCurrentProcessElevated() )
  {
    v6 = CoCreateInstance(&CLSID_PortableWorkspaceLauncher, 0, 0x17u, &GUID_ad6b3b23_c74a_4b2c_839f_c1149cb42e7f, &ppv);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_67ed24213b40381630c90dc80d77584c_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\csetlauncherworkitem.cpp",
          76,
          v6);
      ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v7);
      throw (ATL::CAtlException *)&pExceptionObject;
    }
  }
  else
  {
    v8 = CoCreateInstanceAsAdmin(*a2, v4, v5, &ppv);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_67ed24213b40381630c90dc80d77584c_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\csetlauncherworkitem.cpp",
          82,
          v8);
      ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v9);
      throw (ATL::CAtlException *)&pExceptionObject;
    }
  }
  if ( (_BYTE)v3 )
  {
    pExceptionObject = 2;
    v10 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 40LL))(ppv, &pExceptionObject);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_67ed24213b40381630c90dc80d77584c_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\csetlauncherworkitem.cpp",
          175,
          v10);
      ATL::CAtlException::CAtlException((ATL::CAtlException *)&v15, v11);
      throw (ATL::CAtlException *)&v15;
    }
    if ( pExceptionObject )
    {
      CLauncherIncompatibleMultipleBootDisksException::CLauncherIncompatibleMultipleBootDisksException((CLauncherIncompatibleMultipleBootDisksException *)&v15);
      v14 = v15;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_67ed24213b40381630c90dc80d77584c_Traceguids,
          (unsigned int)"CLauncherIncompatibleMultipleBootDisksException()",
          v15);
      v15 = v14;
      throw (CLauncherIncompatibleMultipleBootDisksException *)&v15;
    }
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v3);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_67ed24213b40381630c90dc80d77584c_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\csetlauncherworkitem.cpp",
        180,
        v12);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v13);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x18000d3d0  mov     [rsp-8+arg_0], rbx
0x18000d3d5  mov     [rsp-8+arg_8], rdi
0x18000d3da  push    rbp
0x18000d3db  mov     rbp, rsp
0x18000d3de  sub     rsp, 40h
0x18000d3e2  mov     rbx, rdx
0x18000d3e5  movzx   edi, cl
0x18000d3e8  mov     [rbp+arg_18], 0
0x18000d3ef  mov     [rbp+var_8], 0
0x18000d3f7  mov     [rbp+arg_18], 1
0x18000d3fe  call    ?IsCurrentProcessElevated@CProcess@utils@@SA_NXZ; utils::CProcess::IsCurrentProcessElevated(void)
0x18000d403  test    al, al
0x18000d405  jz      short loc_18000D436
0x18000d407  lea     rax, [rbp+var_8]
0x18000d40b  mov     [rsp+40h+ppv], rax; ppv
0x18000d410  lea     r9, _GUID_ad6b3b23_c74a_4b2c_839f_c1149cb42e7f; riid
0x18000d417  xor     edx, edx; pUnkOuter
0x18000d419  lea     r8d, [rdx+17h]; dwClsContext
0x18000d41d  lea     rcx, CLSID_PortableWorkspaceLauncher; rclsid
0x18000d424  call    cs:__imp_CoCreateInstance
0x18000d42a  mov     ebx, eax
0x18000d42c  test    eax, eax
0x18000d42e  js      loc_18000D51B
0x18000d434  jmp     short loc_18000D44C
0x18000d436  lea     r9, [rbp+var_8]; void **
0x18000d43a  mov     rcx, [rbx]; HWND
0x18000d43d  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18000d442  mov     ebx, eax
0x18000d444  test    eax, eax
0x18000d446  js      loc_18000D578
0x18000d44c  test    dil, dil
0x18000d44f  jz      short loc_18000D480
0x18000d451  mov     [rbp+pExceptionObject], 2
0x18000d458  mov     rcx, [rbp+var_8]
0x18000d45c  mov     rax, [rcx]
0x18000d45f  lea     rdx, [rbp+pExceptionObject]
0x18000d463  mov     rax, [rax+28h]
0x18000d467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d46c  mov     ebx, eax
0x18000d46e  test    eax, eax
0x18000d470  js      loc_18000D5D5
0x18000d476  cmp     [rbp+pExceptionObject], 0
0x18000d47a  jnz     loc_18000D632
0x18000d480  mov     rcx, [rbp+var_8]
0x18000d484  mov     rax, [rcx]
0x18000d487  mov     edx, edi
0x18000d489  mov     rax, [rax+20h]
0x18000d48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d492  mov     ebx, eax
0x18000d494  test    eax, eax
0x18000d496  js      short loc_18000D4BE
0x18000d498  mov     rcx, [rbp+var_8]
0x18000d49c  test    rcx, rcx
0x18000d49f  jz      short loc_18000D4AE
0x18000d4a1  mov     rax, [rcx]
0x18000d4a4  mov     rax, [rax+10h]
0x18000d4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4ad  nop
0x18000d4ae  mov     rbx, [rsp+40h+arg_0]
0x18000d4b3  mov     rdi, [rsp+40h+arg_8]
0x18000d4b8  add     rsp, 40h
0x18000d4bc  pop     rbp
0x18000d4bd  retn
0x18000d4be  lea     rdx, WPP_GLOBAL_Control
0x18000d4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4cc  cmp     rcx, rdx
0x18000d4cf  jz      short loc_18000D4FF
0x18000d4d1  test    byte ptr [rcx+1Ch], 1
0x18000d4d5  jz      short loc_18000D4FF
0x18000d4d7  mov     edx, 0Fh
0x18000d4dc  mov     [rsp+40h+var_18], ebx
0x18000d4e0  mov     dword ptr [rsp+40h+ppv], 0B4h
0x18000d4e8  lea     r9, aDriversWdmUsbp_12; "drivers\\wdm\\usbpw\\launcher\\dll\\cse"...
0x18000d4ef  lea     r8, WPP_67ed24213b40381630c90dc80d77584c_Traceguids
0x18000d4f6  mov     rcx, [rcx+10h]
0x18000d4fa  call    WPP_SF_sdD
0x18000d4ff  mov     edx, ebx; int
0x18000d501  lea     rcx, [rbp+pExceptionObject]; this
0x18000d505  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000d50a  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000d511  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d515  call    _CxxThrowException_0
0x18000d51b  lea     rdx, WPP_GLOBAL_Control
0x18000d522  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d529  cmp     rcx, rdx
0x18000d52c  jz      short loc_18000D55C
0x18000d52e  test    byte ptr [rcx+1Ch], 1
0x18000d532  jz      short loc_18000D55C
0x18000d534  mov     edx, 0Ah
0x18000d539  mov     [rsp+40h+var_18], ebx
0x18000d53d  mov     dword ptr [rsp+40h+ppv], 4Ch ; 'L'
0x18000d545  lea     r9, aDriversWdmUsbp_12; "drivers\\wdm\\usbpw\\launcher\\dll\\cse"...
0x18000d54c  lea     r8, WPP_67ed24213b40381630c90dc80d77584c_Traceguids
0x18000d553  mov     rcx, [rcx+10h]
0x18000d557  call    WPP_SF_sdD
0x18000d55c  mov     edx, ebx; int
0x18000d55e  lea     rcx, [rbp+pExceptionObject]; this
0x18000d562  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000d567  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000d56e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d572  call    _CxxThrowException_0
0x18000d578  lea     rdx, WPP_GLOBAL_Control
0x18000d57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d586  cmp     rcx, rdx
0x18000d589  jz      short loc_18000D5B9
0x18000d58b  test    byte ptr [rcx+1Ch], 1
0x18000d58f  jz      short loc_18000D5B9
0x18000d591  mov     edx, 0Bh
0x18000d596  mov     [rsp+40h+var_18], ebx
0x18000d59a  mov     dword ptr [rsp+40h+ppv], 52h ; 'R'
0x18000d5a2  lea     r9, aDriversWdmUsbp_12; "drivers\\wdm\\usbpw\\launcher\\dll\\cse"...
0x18000d5a9  lea     r8, WPP_67ed24213b40381630c90dc80d77584c_Traceguids
0x18000d5b0  mov     rcx, [rcx+10h]
0x18000d5b4  call    WPP_SF_sdD
0x18000d5b9  mov     edx, ebx; int
0x18000d5bb  lea     rcx, [rbp+pExceptionObject]; this
0x18000d5bf  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000d5c4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000d5cb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d5cf  call    _CxxThrowException_0
0x18000d5d5  lea     rdx, WPP_GLOBAL_Control
0x18000d5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5e3  cmp     rcx, rdx
0x18000d5e6  jz      short loc_18000D616
0x18000d5e8  test    byte ptr [rcx+1Ch], 1
0x18000d5ec  jz      short loc_18000D616
0x18000d5ee  mov     edx, 0Eh
0x18000d5f3  mov     [rsp+40h+var_18], ebx
0x18000d5f7  mov     dword ptr [rsp+40h+ppv], 0AFh
0x18000d5ff  lea     r9, aDriversWdmUsbp_12; "drivers\\wdm\\usbpw\\launcher\\dll\\cse"...
0x18000d606  lea     r8, WPP_67ed24213b40381630c90dc80d77584c_Traceguids
0x18000d60d  mov     rcx, [rcx+10h]
0x18000d611  call    WPP_SF_sdD
0x18000d616  mov     edx, ebx; int
0x18000d618  lea     rcx, [rbp+var_10]; this
0x18000d61c  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000d621  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000d628  lea     rcx, [rbp+var_10]; pExceptionObject
0x18000d62c  call    _CxxThrowException_0
0x18000d632  lea     rcx, [rbp+var_10]; this
0x18000d636  call    ??0CLauncherIncompatibleMultipleBootDisksException@@QEAA@XZ; CLauncherIncompatibleMultipleBootDisksException::CLauncherIncompatibleMultipleBootDisksException(void)
0x18000d63b  lea     rdx, WPP_GLOBAL_Control
0x18000d642  mov     ebx, [rbp+var_10]
0x18000d645  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d64c  cmp     rcx, rdx
0x18000d64f  jz      short loc_18000D677
0x18000d651  test    byte ptr [rcx+1Ch], 1
0x18000d655  jz      short loc_18000D677
0x18000d657  mov     edx, 0Dh
0x18000d65c  mov     dword ptr [rsp+40h+ppv], ebx
0x18000d660  lea     r9, aClauncherincom; "CLauncherIncompatibleMultipleBootDisksE"...
0x18000d667  lea     r8, WPP_67ed24213b40381630c90dc80d77584c_Traceguids
0x18000d66e  mov     rcx, [rcx+10h]
0x18000d672  call    WPP_SF_sd
0x18000d677  mov     [rbp+var_10], ebx
0x18000d67a  lea     rdx, _TI2?AVCLauncherIncompatibleMultipleBootDisksException@@; pThrowInfo
0x18000d681  lea     rcx, [rbp+var_10]; pExceptionObject
0x18000d685  call    _CxxThrowException_0
```
