# CSetLauncherWorkItem::Execute(void)

- ea: `0x18000d2c0`
- end: `0x18000d387`
- name: `?Execute@CSetLauncherWorkItem@@UEAAXXZ`
- size: `199`
- prototype: `void __fastcall(CSetLauncherWorkItem *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x18000d2c0`
- `0x18000d3d0`
- `0x180011010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18000d2e5`
- `ole32!CoInitializeEx` at `0x18000d2e5`
- `ole32!CoUninitialize` at `0x18000d315`
- `ole32!CoUninitialize` at `0x18000d315`

## string_xrefs

- `0x18000d351`: `drivers\wdm\usbpw\creator\lib\utils\ccominitializer.cpp`

## pseudocode

```c
void __fastcall CSetLauncherWorkItem::Execute(CSetLauncherWorkItem *this)
{
  HRESULT v2; // eax
  int v3; // edi
  _BYTE pExceptionObject[8]; // [rsp+30h] [rbp-18h] BYREF
  const ATL::CAtlException *v5; // [rsp+38h] [rbp-10h] BYREF

  v2 = CoInitializeEx(0, 2u);
  try
  {
    v3 = v2;
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_2ca43871affc3b5315d93f9e24c1d3fb_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\creator\\lib\\utils\\ccominitializer.cpp",
          34,
          v2);
      ATL::CAtlException::CAtlException((ATL::CAtlException *)pExceptionObject, v3);
      throw (ATL::CAtlException *)pExceptionObject;
    }
    CSetLauncherWorkItem::SetLauncher(*((_BYTE *)this + 24), (HWND *)this + 4);
    (*(void (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(
      *((_QWORD *)this + 1),
      (char *)this + 24,
      0);
    CoUninitialize();
  }
  catch ( const ATL::CAtlException *v5 )
  {
    (*(void (__fastcall **)(_QWORD, const ATL::CAtlException *, _QWORD))(**((_QWORD **)this + 1) + 48LL))(
      *((_QWORD *)this + 1),
      v5,
      0);
  }
}

```

## disassembly

```asm
0x18000d2c0  mov     [rsp+arg_10], rbx
0x18000d2c5  mov     [rsp+arg_0], rcx
0x18000d2ca  push    rdi
0x18000d2cb  sub     rsp, 40h
0x18000d2cf  mov     rbx, rcx
0x18000d2d2  lea     rax, ??_7CComInitializer@utils@@6B@; const utils::CComInitializer::`vftable'
0x18000d2d9  mov     [rsp+48h+arg_8], rax
0x18000d2de  mov     edx, 2; dwCoInit
0x18000d2e3  xor     ecx, ecx; pvReserved
0x18000d2e5  call    cs:__imp_CoInitializeEx
0x18000d2eb  mov     edi, eax
0x18000d2ed  test    eax, eax
0x18000d2ef  js      short loc_18000D327
0x18000d2f1  lea     rdx, [rbx+20h]; struct ATL::CWindow *
0x18000d2f5  mov     cl, [rbx+18h]; bool
0x18000d2f8  call    ?SetLauncher@CSetLauncherWorkItem@@SAX_NAEBVCWindow@ATL@@@Z; CSetLauncherWorkItem::SetLauncher(bool,ATL::CWindow const &)
0x18000d2fd  mov     rcx, [rbx+8]
0x18000d301  mov     rax, [rcx]
0x18000d304  xor     r8d, r8d
0x18000d307  lea     rdx, [rbx+18h]
0x18000d30b  mov     rax, [rax+38h]
0x18000d30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d314  nop
0x18000d315  call    cs:__imp_CoUninitialize
0x18000d31b  nop
0x18000d31c  mov     rbx, [rsp+48h+arg_10]
0x18000d321  add     rsp, 40h
0x18000d325  pop     rdi
0x18000d326  retn
0x18000d327  lea     rax, WPP_GLOBAL_Control
0x18000d32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d335  cmp     rcx, rax
0x18000d338  jz      short loc_18000D368
0x18000d33a  test    byte ptr [rcx+1Ch], 1
0x18000d33e  jz      short loc_18000D368
0x18000d340  mov     edx, 0Ah
0x18000d345  mov     [rsp+48h+var_20], edi
0x18000d349  mov     [rsp+48h+var_28], 22h ; '"'
0x18000d351  lea     r9, aDriversWdmUsbp; "drivers\\wdm\\usbpw\\creator\\lib\\util"...
0x18000d358  lea     r8, WPP_2ca43871affc3b5315d93f9e24c1d3fb_Traceguids
0x18000d35f  mov     rcx, [rcx+10h]
0x18000d363  call    WPP_SF_sdD
0x18000d368  mov     edx, edi; int
0x18000d36a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000d36f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000d374  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000d37b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000d380  call    _CxxThrowException_0
```
