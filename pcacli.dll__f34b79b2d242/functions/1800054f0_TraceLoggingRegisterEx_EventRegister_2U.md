# TraceLoggingRegisterEx_EventRegister_2U

- ea: `0x1800054f0`
- end: `0x180005618`
- name: `TraceLoggingRegisterEx_EventRegister_2U`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800050e0`

## callees

- `0x1800054f0`
- `0x18000820e`
- `0x180008286`
- `0x18000c030`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180005583`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000559b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180005583`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000559b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005548`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005548`

## string_xrefs

- `0x180005567`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x180005594`: `advapi32.dll`

## pseudocode

```c
__int64 TraceLoggingRegisterEx_EventRegister_2U()
{
  signed int v0; // ebx
  void *v1; // rdi
  unsigned int v2; // esi
  FARPROC EventSetInformation; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  ProviderId = (GUID)*((_OWORD *)off_180014050 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_180014070 = 0;
  v0 = EventRegister(&ProviderId, tlgEnableCallback, &dword_180014048, &RegHandle);
  if ( v0 )
  {
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  else
  {
    v1 = off_180014050;
    phModule = 0;
    v2 = *(unsigned __int16 *)off_180014050;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
    {
      EventSetInformation = GetProcAddress_0(phModule, "EventSetInformation");
      if ( EventSetInformation )
        ((void (__fastcall *)(ULONGLONG, __int64, void *, _QWORD))EventSetInformation)(RegHandle, 2, v1, v2);
      FreeLibrary_0(phModule);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800054f0  push    rbx
0x1800054f2  sub     rsp, 50h
0x1800054f6  mov     rax, cs:__security_cookie
0x1800054fd  xor     rax, rsp
0x180005500  mov     [rsp+58h+var_10], rax
0x180005505  cmp     cs:RegHandle, 0
0x18000550d  mov     rax, cs:off_180014050; "9"
0x180005514  movups  xmm0, xmmword ptr [rax-10h]
0x180005518  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18000551d  jnz     loc_18000560C
0x180005523  xorps   xmm0, xmm0
0x180005526  lea     r9, RegHandle; RegHandle
0x18000552d  lea     r8, dword_180014048; CallbackContext
0x180005534  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000553b  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x180005540  movdqu  cs:xmmword_180014070, xmm0
0x180005548  call    cs:__imp_EventRegister
0x18000554e  mov     ebx, eax
0x180005550  test    eax, eax
0x180005552  jnz     loc_1800055FD
0x180005558  mov     [rsp+58h+arg_0], rsi
0x18000555d  lea     r8, [rsp+58h+phModule]; phModule
0x180005562  mov     [rsp+58h+arg_8], rdi
0x180005567  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x18000556e  mov     rdi, cs:off_180014050; "9"
0x180005575  xor     ecx, ecx; dwFlags
0x180005577  mov     [rsp+58h+phModule], 0
0x180005580  movzx   esi, word ptr [rdi]
0x180005583  call    cs:__imp_GetModuleHandleExW
0x180005589  test    eax, eax
0x18000558b  jnz     short loc_1800055C4
0x18000558d  lea     r8, [rsp+58h+phModule]; phModule
0x180005592  xor     ecx, ecx; dwFlags
0x180005594  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x18000559b  call    cs:__imp_GetModuleHandleExW
0x1800055a1  test    eax, eax
0x1800055a3  jnz     short loc_1800055C4
0x1800055a5  mov     rsi, [rsp+58h+arg_0]
0x1800055aa  mov     rdi, [rsp+58h+arg_8]
0x1800055af  mov     eax, ebx
0x1800055b1  mov     rcx, [rsp+58h+var_10]
0x1800055b6  xor     rcx, rsp; StackCookie
0x1800055b9  call    __security_check_cookie
0x1800055be  add     rsp, 50h
0x1800055c2  pop     rbx
0x1800055c3  retn
0x1800055c4  mov     rcx, [rsp+58h+phModule]; hModule
0x1800055c9  lea     rdx, aEventsetinform; "EventSetInformation"
0x1800055d0  call    GetProcAddress_0
0x1800055d5  test    rax, rax
0x1800055d8  jz      short loc_1800055F1
0x1800055da  mov     rcx, cs:RegHandle
0x1800055e1  mov     r9d, esi
0x1800055e4  mov     r8, rdi
0x1800055e7  mov     edx, 2
0x1800055ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f1  mov     rcx, [rsp+58h+phModule]; hLibModule
0x1800055f6  call    FreeLibrary_0
0x1800055fb  jmp     short loc_1800055A5
0x1800055fd  test    ebx, ebx
0x1800055ff  jle     short loc_1800055AF
0x180005601  movzx   ebx, bx
0x180005604  or      ebx, 80070000h
0x18000560a  jmp     short loc_1800055AF
0x18000560c  mov     ecx, 5
0x180005611  int     29h; Win8: RtlFailFast(ecx)
0x180005613  jmp     loc_180005523
```
