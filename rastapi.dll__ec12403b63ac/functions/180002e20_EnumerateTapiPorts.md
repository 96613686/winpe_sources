# EnumerateTapiPorts

- ea: `0x180002e20`
- end: `0x180003081`
- name: `EnumerateTapiPorts`
- size: `609`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000212c`
- `0x180002e20`
- `0x18000d92c`
- `0x18000de88`
- `0x180016498`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fa2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000302f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000302f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180002fe3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180002fe3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000307a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000307a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002f21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002ff6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002f21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002ff6`
- `ext-ms-win-ras-tapi32-l1-1-1!lineInitializeExA` at `0x180002edf`
- `ext-ms-win-ras-tapi32-l1-1-1!lineInitializeExA` at `0x180002edf`
- `ext-ms-win-ras-tapi32-l1-1-1!lineShutdown` at `0x180002eff`
- `ext-ms-win-ras-tapi32-l1-1-1!lineShutdown` at `0x18000304d`
- `ext-ms-win-ras-tapi32-l1-1-1!lineShutdown` at `0x180002eff`
- `ext-ms-win-ras-tapi32-l1-1-1!lineShutdown` at `0x18000304d`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x180003023`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x180003023`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180003007`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180003007`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x180003011`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x180003011`

## string_xrefs

- `0x180002e90`: `RemoteAccess`
- `0x180002fb4`: `EnumerateTapiPorts: dwCreateTapiPortsPerLine failed (0x%x)`
- `0x180002fd6`: `rastapi.dll`

## pseudocode

```c
__int64 __fastcall EnumerateTapiPorts(_DWORD *Parameter)
{
  unsigned __int16 i; // bx
  HMODULE Library; // rax
  void *v5; // rcx
  HMODULE v6; // rbx
  int MessageA; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-39h] BYREF
  DWORD dwNumDevs; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v10; // [rsp+4Ch] [rbp-2Dh] BYREF
  DWORD dwAPIVersion; // [rsp+50h] [rbp-29h] BYREF
  struct lineinitializeexparams_tag LineInitializeExParams; // [rsp+58h] [rbp-21h] BYREF
  MSG Msg; // [rsp+78h] [rbp-1h] BYREF

  dwNumDevs = 0;
  dwAPIVersion = 0x20000;
  v10 = 0;
  hMem = 0;
  memset(&Msg, 0, sizeof(Msg));
  RasTapiTrace("EnumerateTapiPorts");
  *(_QWORD *)&LineInitializeExParams.dwNeededSize = 0;
  LineInitializeExParams.Handles.hEvent = 0;
  LineInitializeExParams.dwCompletionKey = 0;
  LineInitializeExParams.dwOptions = 1;
  LineInitializeExParams.dwTotalSize = 28;
  if ( !lineInitializeExA(
          &RasLine,
          RasInstance,
          (LINECALLBACK)RasTapiCallback,
          "RemoteAccess",
          &dwNumDevs,
          &dwAPIVersion,
          &LineInitializeExParams) )
  {
    g_dwNumTapiLines = dwNumDevs;
    RasTapiTrace("EnumerateTapiPorts: Number of Tapi lines = %d");
    for ( i = 0; i < (unsigned int)g_dwNumTapiLines; ++i )
    {
      if ( (unsigned int)dwCreateTapiPortsPerLine(
                           i,
                           0,
                           (_DWORD *)((unsigned __int64)&v10 & -(__int64)(Parameter[2] != 0)),
                           (HLOCAL *)((unsigned __int64)&hMem & -(__int64)(Parameter[2] != 0))) )
      {
        RasTapiTrace("EnumerateTapiPorts: dwCreateTapiPortsPerLine failed (0x%x)");
      }
      else if ( Parameter[2] )
      {
        AddNewPortsPerLine(hMem, v10);
        LocalFree(hMem);
        hMem = 0;
      }
    }
    dwGetNumberOfRings();
    Library = LoadLibraryExA("rastapi.dll", 0, 0x800u);
    v5 = *(void **)Parameter;
    v6 = Library;
    g_fDllLoaded = 1;
    SetEvent(v5);
    while ( 1 )
    {
      MessageA = GetMessageA(&Msg, 0, 0, 0);
      if ( !MessageA )
        goto LABEL_17;
      if ( MessageA == -1 )
        break;
      TranslateMessage(&Msg);
      DispatchMessageA(&Msg);
    }
    GetLastError();
    RasTapiTrace("GetMessage failed and returned -1. rc=0x%x");
LABEL_17:
    if ( RasLine )
    {
      lineShutdown(RasLine);
      RasLine = 0;
    }
    RasTapiTrace("EnumerateTapiPorts done");
    RasTapiTrace(" ");
    FreeLibraryAndExitThread(v6, 0);
  }
  RasTapiTrace("EnumerateTapiPorts: lineInitializeEx Failed");
  if ( RasLine )
    lineShutdown(RasLine);
  RasLine = 0;
  SetEvent(*(HANDLE *)Parameter);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180002e20  push    rbp
0x180002e22  push    rbx
0x180002e23  push    rdi
0x180002e24  push    r14
0x180002e26  lea     rbp, [rsp-3Fh]
0x180002e2b  sub     rsp, 0B8h
0x180002e32  mov     rax, cs:__security_cookie
0x180002e39  xor     rax, rsp
0x180002e3c  mov     [rbp+57h+var_28], rax
0x180002e40  xorps   xmm0, xmm0
0x180002e43  mov     [rbp+57h+dwNumDevs], 0
0x180002e4a  xorps   xmm1, xmm1
0x180002e4d  mov     [rbp+57h+dwAPIVersion], 20000h
0x180002e54  xor     eax, eax
0x180002e56  mov     rdi, rcx
0x180002e59  movups  xmmword ptr [rbp+57h+LineInitializeExParams.dwTotalSize], xmm1
0x180002e5d  lea     rcx, aEnumeratetapip_0; "EnumerateTapiPorts"
0x180002e64  mov     [rbp+57h+var_84], eax
0x180002e67  movups  xmmword ptr [rbp+57h+LineInitializeExParams.dwOptions], xmm1
0x180002e6b  mov     [rbp+57h+hMem], rax
0x180002e6f  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180002e73  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180002e77  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180002e7b  call    RasTapiTrace
0x180002e80  mov     rdx, cs:RasInstance; hInstance
0x180002e87  lea     rax, [rbp+57h+LineInitializeExParams]
0x180002e8b  mov     [rsp+0D0h+lpLineInitializeExParams], rax; lpLineInitializeExParams
0x180002e90  lea     r9, szFriendlyAppName; "RemoteAccess"
0x180002e97  lea     rax, [rbp+57h+dwAPIVersion]
0x180002e9b  mov     qword ptr [rbp+57h+LineInitializeExParams.dwNeededSize], 0
0x180002ea3  mov     [rsp+0D0h+lpdwAPIVersion], rax; lpdwAPIVersion
0x180002ea8  lea     r8, RasTapiCallback; lpfnCallback
0x180002eaf  lea     rax, [rbp+57h+dwNumDevs]
0x180002eb3  mov     qword ptr [rbp+57h+LineInitializeExParams.Handles], 0
0x180002ebb  mov     r14d, 1
0x180002ec1  mov     [rsp+0D0h+lpdwNumDevs], rax; lpdwNumDevs
0x180002ec6  lea     rcx, RasLine; lphLineApp
0x180002ecd  mov     [rbp+57h+LineInitializeExParams.dwCompletionKey], 0
0x180002ed4  mov     [rbp+57h+LineInitializeExParams.dwOptions], r14d
0x180002ed8  mov     [rbp+57h+LineInitializeExParams.dwTotalSize], 1Ch
0x180002edf  call    cs:__imp_lineInitializeExA
0x180002ee5  test    eax, eax
0x180002ee7  jz      short loc_180002F43
0x180002ee9  lea     rcx, aEnumeratetapip; "EnumerateTapiPorts: lineInitializeEx Fa"...
0x180002ef0  call    RasTapiTrace
0x180002ef5  mov     ecx, cs:RasLine; hLineApp
0x180002efb  test    ecx, ecx
0x180002efd  jz      short loc_180002F05
0x180002eff  call    cs:__imp_lineShutdown
0x180002f05  mov     rcx, [rbp+57h+hMem]; hMem
0x180002f09  test    rcx, rcx
0x180002f0c  jz      short loc_180002F14
0x180002f0e  call    cs:__imp_LocalFree
0x180002f14  mov     cs:RasLine, 0
0x180002f1e  mov     rcx, [rdi]; hEvent
0x180002f21  call    cs:__imp_SetEvent
0x180002f27  or      eax, 0FFFFFFFFh
0x180002f2a  mov     rcx, [rbp+57h+var_28]
0x180002f2e  xor     rcx, rsp; StackCookie
0x180002f31  call    __security_check_cookie
0x180002f36  add     rsp, 0B8h
0x180002f3d  pop     r14
0x180002f3f  pop     rdi
0x180002f40  pop     rbx
0x180002f41  pop     rbp
0x180002f42  retn
0x180002f43  mov     edx, [rbp+57h+dwNumDevs]
0x180002f46  lea     rcx, aEnumeratetapip_3; "EnumerateTapiPorts: Number of Tapi line"...
0x180002f4d  mov     cs:g_dwNumTapiLines, edx
0x180002f53  call    RasTapiTrace
0x180002f58  xor     ebx, ebx
0x180002f5a  cmp     cs:g_dwNumTapiLines, ebx
0x180002f60  jbe     short loc_180002FCF
0x180002f62  mov     ecx, [rdi+8]
0x180002f65  mov     eax, ecx
0x180002f67  neg     eax
0x180002f69  lea     rax, [rbp+57h+hMem]
0x180002f6d  sbb     r9, r9
0x180002f70  and     r9, rax
0x180002f73  lea     rax, [rbp+57h+var_84]
0x180002f77  neg     ecx
0x180002f79  movzx   ecx, bx
0x180002f7c  sbb     r8, r8
0x180002f7f  xor     edx, edx
0x180002f81  and     r8, rax
0x180002f84  call    dwCreateTapiPortsPerLine
0x180002f89  test    eax, eax
0x180002f8b  jnz     short loc_180002FB2
0x180002f8d  cmp     [rdi+8], eax
0x180002f90  jz      short loc_180002FC0
0x180002f92  mov     edx, [rbp+57h+var_84]
0x180002f95  mov     rcx, [rbp+57h+hMem]
0x180002f99  call    AddNewPortsPerLine
0x180002f9e  mov     rcx, [rbp+57h+hMem]; hMem
0x180002fa2  call    cs:__imp_LocalFree
0x180002fa8  mov     [rbp+57h+hMem], 0
0x180002fb0  jmp     short loc_180002FC0
0x180002fb2  mov     edx, eax
0x180002fb4  lea     rcx, aEnumeratetapip_2; "EnumerateTapiPorts: dwCreateTapiPortsPe"...
0x180002fbb  call    RasTapiTrace
0x180002fc0  add     bx, r14w
0x180002fc4  movzx   eax, bx
0x180002fc7  cmp     eax, cs:g_dwNumTapiLines
0x180002fcd  jb      short loc_180002F62
0x180002fcf  call    dwGetNumberOfRings
0x180002fd4  xor     edx, edx; hFile
0x180002fd6  lea     rcx, LibFileName; "rastapi.dll"
0x180002fdd  mov     r8d, 800h; dwFlags
0x180002fe3  call    cs:__imp_LoadLibraryExA
0x180002fe9  mov     rcx, [rdi]; hEvent
0x180002fec  mov     rbx, rax
0x180002fef  mov     cs:g_fDllLoaded, r14d
0x180002ff6  call    cs:__imp_SetEvent
0x180002ffc  jmp     short loc_180003017
0x180002ffe  cmp     eax, 0FFFFFFFFh
0x180003001  jz      short loc_18000302F
0x180003003  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180003007  call    cs:__imp_TranslateMessage
0x18000300d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180003011  call    cs:__imp_DispatchMessageA
0x180003017  xor     r9d, r9d; wMsgFilterMax
0x18000301a  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18000301e  xor     r8d, r8d; wMsgFilterMin
0x180003021  xor     edx, edx; hWnd
0x180003023  call    cs:__imp_GetMessageA
0x180003029  test    eax, eax
0x18000302b  jnz     short loc_180002FFE
0x18000302d  jmp     short loc_180003043
0x18000302f  call    cs:__imp_GetLastError
0x180003035  mov     edx, eax
0x180003037  lea     rcx, aGetmessageFail; "GetMessage failed and returned -1. rc=0"...
0x18000303e  call    RasTapiTrace
0x180003043  mov     ecx, cs:RasLine; hLineApp
0x180003049  test    ecx, ecx
0x18000304b  jz      short loc_18000305D
0x18000304d  call    cs:__imp_lineShutdown
0x180003053  mov     cs:RasLine, 0
0x18000305d  lea     rcx, aEnumeratetapip_1; "EnumerateTapiPorts done"
0x180003064  call    RasTapiTrace
0x180003069  lea     rcx, asc_18002C0B8; " "
0x180003070  call    RasTapiTrace
0x180003075  xor     edx, edx; dwExitCode
0x180003077  mov     rcx, rbx; hLibModule
0x18000307a  call    cs:__imp_FreeLibraryAndExitThread
```
