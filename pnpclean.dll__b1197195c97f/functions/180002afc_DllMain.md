# DllMain

- ea: `0x180002afc`
- end: `0x180002b50`
- name: `DllMain`
- size: `84`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001464`

## callees

- `0x180002afc`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180002b1e`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180002b1e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx

  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      *(_QWORD *)&g_hModule = hinstDLL;
      return !ATL::CAtlBaseModule::m_bInitFailed;
    }
  }
  else
  {
    *(_QWORD *)&g_hModule = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180002afc  mov     [rsp+arg_0], rbx
0x180002b01  push    rdi
0x180002b02  sub     rsp, 20h
0x180002b06  mov     rdi, rcx
0x180002b09  mov     eax, edx
0x180002b0b  mov     ebx, 1
0x180002b10  test    edx, edx
0x180002b12  jz      short loc_180002B38
0x180002b14  cmp     eax, ebx
0x180002b16  jz      short loc_180002B1E
0x180002b18  cmp     edx, ebx
0x180002b1a  jnz     short loc_180002B43
0x180002b1c  jmp     short loc_180002B2B
0x180002b1e  call    cs:__imp_DisableThreadLibraryCalls
0x180002b24  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hModule
0x180002b2b  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180002b32  jz      short loc_180002B43
0x180002b34  xor     ebx, ebx
0x180002b36  jmp     short loc_180002B43
0x180002b38  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hModule
0x180002b43  mov     eax, ebx
0x180002b45  mov     rbx, [rsp+28h+arg_0]
0x180002b4a  add     rsp, 20h
0x180002b4e  pop     rdi
0x180002b4f  retn
```
