# OneTimeThreadInit

- ea: `0x1800140e4`
- end: `0x18001419f`
- name: `OneTimeThreadInit`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180013e88`
- `0x180014458`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800093d0`
- `0x180013448`
- `0x180013d20`
- `0x1800140e4`
- `0x1800142e0`
- `0x180014548`
- `0x180015f28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014120`
- `KERNEL32!GetLastError` at `0x180014120`
- `KERNEL32!TlsSetValue` at `0x180014116`
- `KERNEL32!TlsSetValue` at `0x180014116`

## pseudocode

```c
int OneTimeThreadInit()
{
  __int64 Value; // rax
  RPC_BINDING_HANDLE LocalQMBind; // rax
  CFreeRPCHandles *v2; // rcx
  DWORD LastError; // ebx
  CFreeRPCHandles *v4; // rcx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  LPVOID lpTlsValue; // [rsp+50h] [rbp+8h] BYREF

  Value = RtpTlsGetValue();
  if ( !Value )
  {
    LocalQMBind = RTpGetLocalQMBind();
    lpTlsValue = LocalQMBind;
    try
    {
      CFreeRPCHandles::Add(v2, LocalQMBind);
    }
    catch ( exception )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids);
      RpcBindingFree(&lpTlsValue);
      LogIllegalPoint((wchar_t *)L"rt/rtmain", 0x4B2u);
      throw;
    }
    LODWORD(Value) = TlsSetValue(g_hBindIndex, lpTlsValue);
    if ( !(_DWORD)Value )
    {
      LastError = GetLastError();
      CFreeRPCHandles::Remove(v4, lpTlsValue);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids, LastError);
      if ( LastError )
        LogMsgNTStatus(LastError, (wchar_t *)L"rt/rtmain", 0x4B6u);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, LastError);
      throw (bad_win32_error *)pExceptionObject;
    }
  }
  return Value;
}

```

## disassembly

```asm
0x1800140e4  push    rbx
0x1800140e6  sub     rsp, 40h
0x1800140ea  call    RtpTlsGetValue
0x1800140ef  test    rax, rax
0x1800140f2  jnz     loc_180014199
0x1800140f8  call    ?RTpGetLocalQMBind@@YAPEAXXZ; RTpGetLocalQMBind(void)
0x1800140fd  mov     [rsp+48h+lpTlsValue], rax
0x180014102  mov     rdx, rax; void *
0x180014105  call    ?Add@CFreeRPCHandles@@QEAAXPEAX@Z; CFreeRPCHandles::Add(void *)
0x18001410a  nop
0x18001410b  mov     rdx, [rsp+48h+lpTlsValue]; lpTlsValue
0x180014110  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x180014116  call    cs:__imp_TlsSetValue
0x18001411c  test    eax, eax
0x18001411e  jnz     short loc_180014199
0x180014120  call    cs:__imp_GetLastError
0x180014126  mov     ebx, eax
0x180014128  mov     rdx, [rsp+48h+lpTlsValue]; void *
0x18001412d  call    ?Remove@CFreeRPCHandles@@QEAAXPEAX@Z; CFreeRPCHandles::Remove(void *)
0x180014132  lea     rax, WPP_GLOBAL_Control
0x180014139  mov     rcx, cs:WPP_GLOBAL_Control
0x180014140  cmp     rcx, rax
0x180014143  jz      short loc_180014163
0x180014145  test    byte ptr [rcx+1Ch], 1
0x180014149  jz      short loc_180014163
0x18001414b  mov     edx, 0Ch
0x180014150  mov     r9d, ebx
0x180014153  lea     r8, WPP_bc0cb783392d342e13dc1fb31d1d3002_Traceguids
0x18001415a  mov     rcx, [rcx+10h]
0x18001415e  call    WPP_SF_d
0x180014163  test    ebx, ebx
0x180014165  jz      short loc_18001417B
0x180014167  mov     r8d, 4B6h; unsigned __int16
0x18001416d  lea     rdx, aRtRtmain; "rt/rtmain"
0x180014174  mov     ecx, ebx; int
0x180014176  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001417b  mov     edx, ebx; unsigned int
0x18001417d  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180014182  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180014187  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001418e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180014193  call    _CxxThrowException_0
0x180014199  add     rsp, 40h
0x18001419d  pop     rbx
0x18001419e  retn
```
