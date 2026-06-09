# DllMain

- ea: `0x180008ed4`
- end: `0x180008fa1`
- name: `DllMain`
- size: `205`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002324`

## callees

- `0x180008ed4`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180008ef4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180008ef4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008f84`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008f84`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008f60`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008f60`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008f41`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008f41`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  REGHANDLE v3; // rcx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      ProviderId = (GUID)*((_OWORD *)off_180052178 - 1);
      if ( RegHandle )
        __fastfail(5u);
      xmmword_180052198 = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180052170, &RegHandle) )
        EventSetInformation(
          RegHandle,
          2,
          off_180052178,
          *(unsigned __int16 *)off_180052178,
          *(_QWORD *)&ProviderId.Data1,
          *(_QWORD *)ProviderId.Data4);
    }
  }
  else
  {
    v3 = RegHandle;
    dword_180052170 = 0;
    RegHandle = 0;
    EventUnregister(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x180008ed4  sub     rsp, 48h
0x180008ed8  mov     rax, cs:__security_cookie
0x180008edf  xor     rax, rsp
0x180008ee2  mov     [rsp+48h+var_18], rax
0x180008ee7  test    edx, edx
0x180008ee9  jz      short loc_180008F68
0x180008eeb  cmp     edx, 1
0x180008eee  jnz     loc_180008F8A
0x180008ef4  call    cs:__imp_DisableThreadLibraryCalls
0x180008efa  cmp     cs:RegHandle, 0
0x180008f02  mov     rax, cs:off_180052178
0x180008f09  movups  xmm0, xmmword ptr [rax-10h]
0x180008f0d  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180008f13  jz      short loc_180008F1C
0x180008f15  mov     ecx, 5
0x180008f1a  int     29h; Win8: RtlFailFast(ecx)
0x180008f1c  xorps   xmm0, xmm0
0x180008f1f  lea     r9, RegHandle; RegHandle
0x180008f26  lea     r8, dword_180052170; CallbackContext
0x180008f2d  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008f34  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180008f39  movdqu  cs:xmmword_180052198, xmm0
0x180008f41  call    cs:__imp_EventRegister
0x180008f47  test    eax, eax
0x180008f49  jnz     short loc_180008F8A
0x180008f4b  mov     r8, cs:off_180052178
0x180008f52  lea     edx, [rax+2]
0x180008f55  mov     rcx, cs:RegHandle
0x180008f5c  movzx   r9d, word ptr [r8]
0x180008f60  call    cs:__imp_EventSetInformation
0x180008f66  jmp     short loc_180008F8A
0x180008f68  mov     rcx, cs:RegHandle; RegHandle
0x180008f6f  mov     cs:dword_180052170, 0
0x180008f79  mov     cs:RegHandle, 0
0x180008f84  call    cs:__imp_EventUnregister
0x180008f8a  mov     eax, 1
0x180008f8f  mov     rcx, [rsp+48h+var_18]
0x180008f94  xor     rcx, rsp; StackCookie
0x180008f97  call    __security_check_cookie
0x180008f9c  add     rsp, 48h
0x180008fa0  retn
```
