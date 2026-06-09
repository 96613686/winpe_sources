# utils::CHelpPane::Open(ATL::CComBSTR)

- ea: `0x18000ef8c`
- end: `0x18000f141`
- name: `?Open@CHelpPane@utils@@SAXVCComBSTR@ATL@@@Z`
- size: `437`
- prototype: `void __fastcall(BSTR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a710`
- `0x18000a85c`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x180008ac8`
- `0x18000b9d0`
- `0x18000ef8c`
- `0x180011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000f01e`
- `ole32!CoCreateInstance` at `0x18000f01e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f086`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f086`

## pseudocode

```c
void __fastcall utils::CHelpPane::Open(BSTR *a1)
{
  _QWORD *v2; // rcx
  HRESULT v3; // eax
  int v4; // edi
  int v5; // eax
  int v6; // edi
  int v7; // [rsp+28h] [rbp-20h]
  HRESULT v8; // [rsp+28h] [rbp-20h]
  char pExceptionObject; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_20695b01bfe0397a200d376e1354f798_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
      WPP_SF_S(v2[2], 11, &WPP_20695b01bfe0397a200d376e1354f798_Traceguids, *a1);
  }
  ppv = 0;
  v3 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = v3;
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_20695b01bfe0397a200d376e1354f798_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\chelppane.cpp",
        49,
        v8);
    }
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v4);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 24LL))(ppv, *a1);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = v5;
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_20695b01bfe0397a200d376e1354f798_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\chelppane.cpp",
        50,
        v7);
    }
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v6);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_20695b01bfe0397a200d376e1354f798_Traceguids);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  SysFreeString(*a1);
}

```

## disassembly

```asm
0x18000ef8c  mov     [rsp+arg_18], rbx
0x18000ef91  mov     [rsp+arg_0], rcx
0x18000ef96  push    rbp
0x18000ef97  push    rsi
0x18000ef98  push    rdi
0x18000ef99  sub     rsp, 30h
0x18000ef9d  mov     rbx, rcx
0x18000efa0  lea     rsi, WPP_GLOBAL_Control
0x18000efa7  lea     rbp, WPP_20695b01bfe0397a200d376e1354f798_Traceguids
0x18000efae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efb5  cmp     rcx, rsi
0x18000efb8  jz      short loc_18000EFF7
0x18000efba  test    byte ptr [rcx+1Ch], 8
0x18000efbe  jz      short loc_18000EFD8
0x18000efc0  mov     edx, 0Ah
0x18000efc5  mov     r8, rbp
0x18000efc8  mov     rcx, [rcx+10h]
0x18000efcc  call    WPP_SF_
0x18000efd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efd8  cmp     rcx, rsi
0x18000efdb  jz      short loc_18000EFF7
0x18000efdd  test    byte ptr [rcx+1Ch], 4
0x18000efe1  jz      short loc_18000EFF7
0x18000efe3  mov     edx, 0Bh
0x18000efe8  mov     r9, [rbx]
0x18000efeb  mov     r8, rbp
0x18000efee  mov     rcx, [rcx+10h]
0x18000eff2  call    WPP_SF_S
0x18000eff7  mov     [rsp+48h+arg_10], 0
0x18000f000  lea     rax, [rsp+48h+arg_10]
0x18000f005  mov     [rsp+48h+ppv], rax; ppv
0x18000f00a  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18000f011  xor     edx, edx; pUnkOuter
0x18000f013  lea     r8d, [rdx+1]; dwClsContext
0x18000f017  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18000f01e  call    cs:__imp_CoCreateInstance
0x18000f024  mov     edi, eax
0x18000f026  test    eax, eax
0x18000f028  js      loc_18000F0ED
0x18000f02e  mov     rcx, [rsp+48h+arg_10]
0x18000f033  mov     rax, [rcx]
0x18000f036  mov     rdx, [rbx]
0x18000f039  mov     rax, [rax+18h]
0x18000f03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f042  mov     edi, eax
0x18000f044  test    eax, eax
0x18000f046  js      short loc_18000F099
0x18000f048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f04f  cmp     rcx, rsi
0x18000f052  jz      short loc_18000F06C
0x18000f054  test    byte ptr [rcx+1Ch], 8
0x18000f058  jz      short loc_18000F06C
0x18000f05a  mov     edx, 0Eh
0x18000f05f  mov     r8, rbp
0x18000f062  mov     rcx, [rcx+10h]
0x18000f066  call    WPP_SF_
0x18000f06b  nop
0x18000f06c  mov     rcx, [rsp+48h+arg_10]
0x18000f071  test    rcx, rcx
0x18000f074  jz      short loc_18000F083
0x18000f076  mov     rax, [rcx]
0x18000f079  mov     rax, [rax+10h]
0x18000f07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f082  nop
0x18000f083  mov     rcx, [rbx]; bstrString
0x18000f086  call    cs:__imp_SysFreeString
0x18000f08c  mov     rbx, [rsp+48h+arg_18]
0x18000f091  add     rsp, 30h
0x18000f095  pop     rdi
0x18000f096  pop     rsi
0x18000f097  pop     rbp
0x18000f098  retn
0x18000f099  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0a0  cmp     rcx, rsi
0x18000f0a3  jz      short loc_18000F0CF
0x18000f0a5  test    byte ptr [rcx+1Ch], 1
0x18000f0a9  jz      short loc_18000F0CF
0x18000f0ab  mov     edx, 0Dh
0x18000f0b0  mov     [rsp+48h+var_20], edi
0x18000f0b4  mov     dword ptr [rsp+48h+ppv], 32h ; '2'
0x18000f0bc  lea     r9, aDriversWdmUsbp_8; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000f0c3  mov     r8, rbp
0x18000f0c6  mov     rcx, [rcx+10h]
0x18000f0ca  call    WPP_SF_sdD
0x18000f0cf  mov     edx, edi; int
0x18000f0d1  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000f0d6  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000f0db  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000f0e2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f0e7  call    _CxxThrowException_0
0x18000f0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0f4  cmp     rcx, rsi
0x18000f0f7  jz      short loc_18000F123
0x18000f0f9  test    byte ptr [rcx+1Ch], 1
0x18000f0fd  jz      short loc_18000F123
0x18000f0ff  mov     edx, 0Ch
0x18000f104  mov     [rsp+48h+var_20], edi
0x18000f108  mov     dword ptr [rsp+48h+ppv], 31h ; '1'
0x18000f110  lea     r9, aDriversWdmUsbp_8; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000f117  mov     r8, rbp
0x18000f11a  mov     rcx, [rcx+10h]
0x18000f11e  call    WPP_SF_sdD
0x18000f123  mov     edx, edi; int
0x18000f125  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000f12a  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000f12f  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000f136  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f13b  call    _CxxThrowException_0
```
