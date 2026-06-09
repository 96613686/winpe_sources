# GetLayoutInit(HDC__ *)

- ea: `0x180090560`
- end: `0x1800905e3`
- name: `?GetLayoutInit@@YAKPEAUHDC__@@@Z`
- size: `131`
- prototype: `unsigned int __fastcall(HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180090560`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x180090583`
- `KERNEL32!GetModuleHandleA` at `0x180090583`
- `KERNEL32!EnterCriticalSection` at `0x180090570`
- `KERNEL32!EnterCriticalSection` at `0x180090570`
- `KERNEL32!LeaveCriticalSection` at `0x1800905ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800905ce`
- `KERNEL32!GetProcAddress` at `0x18009059e`
- `KERNEL32!GetProcAddress` at `0x18009059e`

## string_xrefs

- `0x18009057c`: `GDI32.DLL`

## pseudocode

```c
__int64 __fastcall GetLayoutInit(HDC a1)
{
  HMODULE ModuleHandleA; // rax
  unsigned int (*ProcAddress)(HDC); // rax
  unsigned int v4; // ebx

  EnterCriticalSection(&g_CriticalSection);
  ModuleHandleA = GetModuleHandleA("GDI32.DLL");
  if ( !ModuleHandleA || (ProcAddress = (unsigned int (*)(HDC))GetProcAddress(ModuleHandleA, "GetLayout")) == 0 )
    ProcAddress = (unsigned int (*)(HDC))CDisplay::GetYScroll;
  CW32System::_pfnGetLayout = ProcAddress;
  v4 = ((__int64 (__fastcall *)(HDC))ProcAddress)(a1);
  LeaveCriticalSection(&g_CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x180090560  push    rbx
0x180090562  sub     rsp, 20h
0x180090566  mov     rbx, rcx
0x180090569  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180090570  call    cs:__imp_EnterCriticalSection
0x180090577  nop     dword ptr [rax+rax+00h]
0x18009057c  lea     rcx, aGdi32Dll_0; "GDI32.DLL"
0x180090583  call    cs:__imp_GetModuleHandleA
0x18009058a  nop     dword ptr [rax+rax+00h]
0x18009058f  test    rax, rax
0x180090592  jz      short loc_1800905AF
0x180090594  lea     rdx, aGetlayout; "GetLayout"
0x18009059b  mov     rcx, rax; hModule
0x18009059e  call    cs:__imp_GetProcAddress
0x1800905a5  nop     dword ptr [rax+rax+00h]
0x1800905aa  test    rax, rax
0x1800905ad  jnz     short loc_1800905B6
0x1800905af  lea     rax, ?GetYScroll@CDisplay@@UEBAJXZ; CDisplay::GetYScroll(void)
0x1800905b6  mov     rcx, rbx
0x1800905b9  mov     cs:?_pfnGetLayout@CW32System@@2P6AKPEAUHDC__@@@ZEA, rax; ulong (*CW32System::_pfnGetLayout)(HDC__ *)
0x1800905c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905c5  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800905cc  mov     ebx, eax
0x1800905ce  call    cs:__imp_LeaveCriticalSection
0x1800905d5  nop     dword ptr [rax+rax+00h]
0x1800905da  mov     eax, ebx
0x1800905dc  add     rsp, 20h
0x1800905e0  pop     rbx
0x1800905e1  retn
```
