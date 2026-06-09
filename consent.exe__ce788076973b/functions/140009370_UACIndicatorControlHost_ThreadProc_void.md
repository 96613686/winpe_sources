# UACIndicatorControlHost::ThreadProc(void)

- ea: `0x140009370`
- end: `0x14000947c`
- name: `?ThreadProc@UACIndicatorControlHost@@AEAAXXZ`
- size: `268`
- prototype: `void __fastcall(UACIndicatorControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000eea0`

## callees

- `0x140009370`
- `0x14001f010`

## import_xrefs

- `USER32!GetMessageW` at `0x140009439`
- `USER32!GetMessageW` at `0x140009466`
- `USER32!GetMessageW` at `0x140009439`
- `USER32!GetMessageW` at `0x140009466`
- `USER32!DispatchMessageW` at `0x140009453`
- `USER32!DispatchMessageW` at `0x140009453`
- `USER32!TranslateMessage` at `0x140009448`
- `USER32!TranslateMessage` at `0x140009448`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009399`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009399`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x140009380`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x140009380`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009470`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009470`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400093f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400093f6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400093bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400093bf`

## string_xrefs

- `0x140009379`: `user32.dll`
- `0x14000938f`: `SetThreadDesktop`

## pseudocode

```c
void __fastcall UACIndicatorControlHost::ThreadProc(UACIndicatorControlHost *this)
{
  __int64 v1; // rbx
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)this;
  ModuleHandleA = GetModuleHandleA("user32.dll");
  if ( ModuleHandleA )
  {
    ProcAddress = GetProcAddress(ModuleHandleA, "SetThreadDesktop");
    if ( ProcAddress )
    {
      if ( ((unsigned int (__fastcall *)(__int64))ProcAddress)(v1) && CoInitializeEx(0, 2u) >= 0 )
      {
        ppv = 0;
        if ( CoCreateInstance(
               &GUID_b9bc2a50_43c3_41aa_a087_5db14e184bae,
               0,
               1u,
               &GUID_b9bc2a50_43c3_41aa_a085_5db14e184bae,
               &ppv) >= 0 )
        {
          if ( ppv )
          {
            if ( (*(int (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv) >= 0 )
            {
              memset(&Msg, 0, sizeof(Msg));
              while ( GetMessageW(&Msg, 0, 0, 0) )
              {
                TranslateMessage(&Msg);
                DispatchMessageW(&Msg);
              }
            }
          }
        }
        CoUninitialize();
      }
    }
  }
}

```

## disassembly

```asm
0x140009370  push    rbx
0x140009372  sub     rsp, 60h
0x140009376  mov     rbx, [rcx]
0x140009379  lea     rcx, aUser32Dll_0; "user32.dll"
0x140009380  call    cs:__imp_GetModuleHandleA
0x140009386  test    rax, rax
0x140009389  jz      loc_140009476
0x14000938f  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x140009396  mov     rcx, rax; hModule
0x140009399  call    cs:__imp_GetProcAddress
0x14000939f  test    rax, rax
0x1400093a2  jz      loc_140009476
0x1400093a8  mov     rcx, rbx
0x1400093ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093b0  test    eax, eax
0x1400093b2  jz      loc_140009476
0x1400093b8  mov     edx, 2; dwCoInit
0x1400093bd  xor     ecx, ecx; pvReserved
0x1400093bf  call    cs:__imp_CoInitializeEx
0x1400093c5  test    eax, eax
0x1400093c7  js      loc_140009476
0x1400093cd  lea     rax, [rsp+68h+arg_0]
0x1400093d2  mov     [rsp+68h+arg_0], 0
0x1400093db  lea     r9, _GUID_b9bc2a50_43c3_41aa_a085_5db14e184bae; riid
0x1400093e2  mov     [rsp+68h+ppv], rax; ppv
0x1400093e7  xor     edx, edx; pUnkOuter
0x1400093e9  lea     rcx, _GUID_b9bc2a50_43c3_41aa_a087_5db14e184bae; rclsid
0x1400093f0  mov     r8d, 1; dwClsContext
0x1400093f6  call    cs:__imp_CoCreateInstance
0x1400093fc  test    eax, eax
0x1400093fe  js      short loc_140009470
0x140009400  mov     rcx, [rsp+68h+arg_0]
0x140009405  test    rcx, rcx
0x140009408  jz      short loc_140009470
0x14000940a  mov     rax, [rcx]
0x14000940d  mov     rax, [rax+18h]
0x140009411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009416  test    eax, eax
0x140009418  js      short loc_140009470
0x14000941a  xorps   xmm0, xmm0
0x14000941d  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140009422  xor     r9d, r9d; wMsgFilterMax
0x140009425  xor     r8d, r8d; wMsgFilterMin
0x140009428  xor     edx, edx; hWnd
0x14000942a  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x14000942f  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x140009434  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x140009439  call    cs:__imp_GetMessageW
0x14000943f  test    eax, eax
0x140009441  jz      short loc_140009470
0x140009443  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140009448  call    cs:__imp_TranslateMessage
0x14000944e  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140009453  call    cs:__imp_DispatchMessageW
0x140009459  xor     r9d, r9d; wMsgFilterMax
0x14000945c  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140009461  xor     r8d, r8d; wMsgFilterMin
0x140009464  xor     edx, edx; hWnd
0x140009466  call    cs:__imp_GetMessageW
0x14000946c  test    eax, eax
0x14000946e  jnz     short loc_140009443
0x140009470  call    cs:__imp_CoUninitialize
0x140009476  add     rsp, 60h
0x14000947a  pop     rbx
0x14000947b  retn
```
