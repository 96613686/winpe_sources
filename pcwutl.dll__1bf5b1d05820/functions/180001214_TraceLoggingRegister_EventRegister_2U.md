# TraceLoggingRegister_EventRegister_2U

- ea: `0x180001214`
- end: `0x180001331`
- name: `TraceLoggingRegister_EventRegister_2U`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800171d0`

## callees

- `0x180001214`
- `0x1800191f0`
- `0x18001a010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180001279`
- `ADVAPI32!EventRegister` at `0x180001279`
- `KERNEL32!GetModuleHandleExW` at `0x1800012b7`
- `KERNEL32!GetModuleHandleExW` at `0x1800012cf`
- `KERNEL32!GetModuleHandleExW` at `0x1800012b7`
- `KERNEL32!GetModuleHandleExW` at `0x1800012cf`
- `KERNEL32!FreeLibrary` at `0x18000130c`
- `KERNEL32!FreeLibrary` at `0x18000130c`
- `KERNEL32!GetProcAddress` at `0x1800012e5`
- `KERNEL32!GetProcAddress` at `0x1800012e5`

## string_xrefs

- `0x1800012a2`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800012c8`: `advapi32.dll`

## pseudocode

```c
__int64 TraceLoggingRegister_EventRegister_2U()
{
  signed int v0; // eax
  unsigned int v1; // ebx
  void *v2; // rdi
  unsigned int v3; // esi
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  ProviderId = (GUID)*((_OWORD *)off_180026108 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_180026128 = 0;
  v0 = EventRegister(&ProviderId, tlgEnableCallback, &dword_180026100, &RegHandle);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  else
  {
    v2 = off_180026108;
    phModule = 0;
    v3 = *(unsigned __int16 *)off_180026108;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "EventSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(ULONGLONG, __int64, void *, _QWORD))ProcAddress)(RegHandle, 2, v2, v3);
      FreeLibrary(phModule);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180001214  mov     [rsp+arg_0], rbx
0x180001219  mov     [rsp+arg_8], rsi
0x18000121e  push    rdi
0x18000121f  sub     rsp, 50h
0x180001223  mov     rax, cs:__security_cookie
0x18000122a  xor     rax, rsp
0x18000122d  mov     [rsp+58h+var_10], rax
0x180001232  cmp     cs:RegHandle, 0
0x18000123a  mov     rax, cs:off_180026108; "9"
0x180001241  movups  xmm0, xmmword ptr [rax-10h]
0x180001245  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18000124b  jz      short loc_180001254
0x18000124d  mov     ecx, 5
0x180001252  int     29h; Win8: RtlFailFast(ecx)
0x180001254  xorps   xmm0, xmm0
0x180001257  lea     r9, RegHandle; RegHandle
0x18000125e  lea     r8, dword_180026100; CallbackContext
0x180001265  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000126c  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x180001271  movdqu  cs:xmmword_180026128, xmm0
0x180001279  call    cs:__imp_EventRegister
0x18000127f  mov     ebx, eax
0x180001281  test    eax, eax
0x180001283  jz      short loc_180001296
0x180001285  jle     loc_180001312
0x18000128b  movzx   ebx, ax
0x18000128e  or      ebx, 80070000h
0x180001294  jmp     short loc_180001312
0x180001296  mov     rdi, cs:off_180026108; "9"
0x18000129d  lea     r8, [rsp+58h+phModule]; phModule
0x1800012a2  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1800012a9  mov     [rsp+58h+phModule], 0
0x1800012b2  xor     ecx, ecx; dwFlags
0x1800012b4  movzx   esi, word ptr [rdi]
0x1800012b7  call    cs:__imp_GetModuleHandleExW
0x1800012bd  test    eax, eax
0x1800012bf  jnz     short loc_1800012D9
0x1800012c1  lea     r8, [rsp+58h+phModule]; phModule
0x1800012c6  xor     ecx, ecx; dwFlags
0x1800012c8  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x1800012cf  call    cs:__imp_GetModuleHandleExW
0x1800012d5  test    eax, eax
0x1800012d7  jz      short loc_180001312
0x1800012d9  mov     rcx, [rsp+58h+phModule]; hModule
0x1800012de  lea     rdx, ProcName; "EventSetInformation"
0x1800012e5  call    cs:__imp_GetProcAddress
0x1800012eb  test    rax, rax
0x1800012ee  jz      short loc_180001307
0x1800012f0  mov     rcx, cs:RegHandle
0x1800012f7  mov     r9d, esi
0x1800012fa  mov     r8, rdi
0x1800012fd  mov     edx, 2
0x180001302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001307  mov     rcx, [rsp+58h+phModule]; hLibModule
0x18000130c  call    cs:__imp_FreeLibrary
0x180001312  mov     eax, ebx
0x180001314  mov     rcx, [rsp+58h+var_10]
0x180001319  xor     rcx, rsp; StackCookie
0x18000131c  call    __security_check_cookie
0x180001321  mov     rbx, [rsp+58h+arg_0]
0x180001326  mov     rsi, [rsp+58h+arg_8]
0x18000132b  add     rsp, 50h
0x18000132f  pop     rdi
0x180001330  retn
```
