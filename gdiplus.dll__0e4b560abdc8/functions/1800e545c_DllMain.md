# DllMain

- ea: `0x1800e545c`
- end: `0x1800e54f1`
- name: `DllMain`
- size: `149`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800e91f8`

## callees

- `0x1800e545c`
- `0x1800e54f8`
- `0x1800e552c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800e54ad`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800e54ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800e548f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800e548f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e54cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e54cb`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DllInstance = hinstDLL;
      McGenEventRegister_EventRegister(hinstDLL, fdwReason, lpvReserved);
      InitializeCriticalSection(&GdiplusStartupCriticalSection::critSec);
      GdiplusStartupCriticalSection::initialized = 1;
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    if ( GdiplusStartupCriticalSection::initialized )
    {
      DeleteCriticalSection(&GdiplusStartupCriticalSection::critSec);
      GdiplusStartupCriticalSection::initialized = 0;
    }
    McGenEventUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x1800e545c  mov     [rsp+arg_8], rbx
0x1800e5461  mov     [rsp+arg_0], rcx
0x1800e5466  push    rdi
0x1800e5467  sub     rsp, 20h
0x1800e546b  mov     rbx, rcx
0x1800e546e  mov     edi, 1
0x1800e5473  test    edx, edx
0x1800e5475  jz      short loc_1800E54BB
0x1800e5477  cmp     edx, edi
0x1800e5479  jnz     short loc_1800E54E3
0x1800e547b  mov     cs:?DllInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * DllInstance
0x1800e5482  call    McGenEventRegister_EventRegister
0x1800e5487  nop
0x1800e5488  lea     rcx, ?critSec@GdiplusStartupCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e548f  call    cs:__imp_InitializeCriticalSection
0x1800e5496  nop     dword ptr [rax+rax+00h]
0x1800e549b  mov     cs:?initialized@GdiplusStartupCriticalSection@@0HA, edi; int GdiplusStartupCriticalSection::initialized
0x1800e54a1  jmp     short loc_1800E54AA
0x1800e54a3  xor     edi, edi
0x1800e54a5  mov     rbx, [rsp+28h+arg_0]
0x1800e54aa  mov     rcx, rbx; hLibModule
0x1800e54ad  call    cs:__imp_DisableThreadLibraryCalls
0x1800e54b4  nop     dword ptr [rax+rax+00h]
0x1800e54b9  jmp     short loc_1800E54E3
0x1800e54bb  cmp     cs:?initialized@GdiplusStartupCriticalSection@@0HA, 0; int GdiplusStartupCriticalSection::initialized
0x1800e54c2  jz      short loc_1800E54DE
0x1800e54c4  lea     rcx, ?critSec@GdiplusStartupCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e54cb  call    cs:__imp_DeleteCriticalSection
0x1800e54d2  nop     dword ptr [rax+rax+00h]
0x1800e54d7  and     cs:?initialized@GdiplusStartupCriticalSection@@0HA, 0; int GdiplusStartupCriticalSection::initialized
0x1800e54de  call    McGenEventUnregister_EventUnregister
0x1800e54e3  mov     eax, edi
0x1800e54e5  mov     rbx, [rsp+28h+arg_8]
0x1800e54ea  add     rsp, 20h
0x1800e54ee  pop     rdi
0x1800e54ef  retn
0x1801741c5  push    rbp
0x1801741c7  sub     rsp, 20h
0x1801741cb  mov     rbp, rdx
0x1801741ce  mov     rax, [rcx]
0x1801741d1  xor     ecx, ecx
0x1801741d3  cmp     dword ptr [rax], 0C0000017h
0x1801741d9  setz    cl
0x1801741dc  mov     eax, ecx
0x1801741de  add     rsp, 20h
0x1801741e2  pop     rbp
0x1801741e3  retn
```
