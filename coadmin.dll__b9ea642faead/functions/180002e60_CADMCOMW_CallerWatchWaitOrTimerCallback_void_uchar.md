# CADMCOMW::CallerWatchWaitOrTimerCallback(void *,uchar)

- ea: `0x180002e60`
- end: `0x180002f5b`
- name: `?CallerWatchWaitOrTimerCallback@CADMCOMW@@CAXPEAXE@Z`
- size: `251`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002e60`
- `0x18000455c`

## import_xrefs

- `ole32!CoUninitialize` at `0x180002f0a`
- `ole32!CoUninitialize` at `0x180002f0a`
- `ole32!CoInitializeEx` at `0x180002e82`
- `ole32!CoInitializeEx` at `0x180002e82`
- `IisRTL!PuDbgPrint` at `0x180002f00`
- `IisRTL!PuDbgPrint` at `0x180002f4a`
- `IisRTL!PuDbgPrint` at `0x180002f00`
- `IisRTL!PuDbgPrint` at `0x180002f4a`

## string_xrefs

- `0x180002ef4`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180002f43`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180002eed`: `CADMCOMW::CallerWatchWaitOrTimerCallback`
- `0x180002f31`: `CADMCOMW::CallerWatchWaitOrTimerCallback`

## pseudocode

```c
void __fastcall CADMCOMW::CallerWatchWaitOrTimerCallback(CADMCOMW *a1, char a2)
{
  HRESULT v3; // eax
  BOOL v4; // ebx
  int v5; // eax
  HRESULT v6; // [rsp+28h] [rbp-10h]
  int v7; // [rsp+28h] [rbp-10h]
  int v8; // [rsp+28h] [rbp-10h]

  if ( !a1 || a2 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v8 = -2147024809;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        7405,
        "CADMCOMW::CallerWatchWaitOrTimerCallback",
        "Invalid args.\n",
        v8);
    }
  }
  else
  {
    v3 = CoInitializeEx(0, 0);
    v4 = v3 >= 0;
    if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147417850 )
    {
      v5 = CADMCOMW::DisconnectOrphaned(a1, 0);
      if ( v5 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        v7 = v5;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          7443,
          "CADMCOMW::CallerWatchWaitOrTimerCallback",
          "DisconnectOrphaned() failed hr=0x%08x.\n",
          v7);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      v6 = v3;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        7429,
        "CADMCOMW::CallerWatchWaitOrTimerCallback",
        "CoInitializeEx() failed hr=0x%08x.\n",
        v6);
    }
    if ( v4 )
      CoUninitialize();
  }
}

```

## disassembly

```asm
0x180002e60  mov     [rsp+arg_0], rbx
0x180002e65  push    rdi
0x180002e66  sub     rsp, 30h
0x180002e6a  mov     rdi, rcx
0x180002e6d  test    rcx, rcx
0x180002e70  jz      loc_180002F12
0x180002e76  test    dl, dl
0x180002e78  jnz     loc_180002F12
0x180002e7e  xor     edx, edx; dwCoInit
0x180002e80  xor     ecx, ecx; pvReserved
0x180002e82  call    cs:__imp_CoInitializeEx
0x180002e88  mov     edx, 80000000h
0x180002e8d  mov     ebx, eax
0x180002e8f  not     ebx
0x180002e91  shr     ebx, 1Fh
0x180002e94  lea     ecx, [rax+rdx]
0x180002e97  test    edx, ecx
0x180002e99  jnz     short loc_180002EBE
0x180002e9b  cmp     eax, 80010106h
0x180002ea0  jz      short loc_180002EBE
0x180002ea2  test    byte ptr cs:g_dwDebugFlags, 3
0x180002ea9  jz      short loc_180002F06
0x180002eab  mov     [rsp+38h+var_10], eax
0x180002eaf  mov     r8d, 1D05h
0x180002eb5  lea     rax, aCoinitializeex; "CoInitializeEx() failed hr=0x%08x.\n"
0x180002ebc  jmp     short loc_180002EE6
0x180002ebe  xor     edx, edx; int
0x180002ec0  mov     rcx, rdi; this
0x180002ec3  call    ?DisconnectOrphaned@CADMCOMW@@AEAAJH@Z; CADMCOMW::DisconnectOrphaned(int)
0x180002ec8  test    eax, eax
0x180002eca  jns     short loc_180002F06
0x180002ecc  test    byte ptr cs:g_dwDebugFlags, 3
0x180002ed3  jz      short loc_180002F06
0x180002ed5  mov     [rsp+38h+var_10], eax
0x180002ed9  mov     r8d, 1D13h
0x180002edf  lea     rax, aDisconnectorph; "DisconnectOrphaned() failed hr=0x%08x."...
0x180002ee6  mov     rcx, cs:g_pDebug
0x180002eed  lea     r9, aCadmcomwCaller; "CADMCOMW::CallerWatchWaitOrTimerCallbac"...
0x180002ef4  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180002efb  mov     [rsp+38h+var_18], rax
0x180002f00  call    cs:__imp_PuDbgPrint
0x180002f06  test    ebx, ebx
0x180002f08  jz      short loc_180002F50
0x180002f0a  call    cs:__imp_CoUninitialize
0x180002f10  jmp     short loc_180002F50
0x180002f12  test    byte ptr cs:g_dwDebugFlags, 3
0x180002f19  jz      short loc_180002F50
0x180002f1b  mov     rcx, cs:g_pDebug
0x180002f22  lea     rax, aInvalidArgs; "Invalid args.\n"
0x180002f29  mov     [rsp+38h+var_10], 80070057h
0x180002f31  lea     r9, aCadmcomwCaller; "CADMCOMW::CallerWatchWaitOrTimerCallbac"...
0x180002f38  mov     r8d, 1CEDh
0x180002f3e  mov     [rsp+38h+var_18], rax
0x180002f43  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180002f4a  call    cs:__imp_PuDbgPrint
0x180002f50  mov     rbx, [rsp+38h+arg_0]
0x180002f55  add     rsp, 30h
0x180002f59  pop     rdi
0x180002f5a  retn
```
