# TestCreate

- ea: `0x18001a540`
- end: `0x18001a5f5`
- name: `TestCreate`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006a0c`
- `0x180019a18`

## callees

- `0x18001a540`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001a576`
- `KERNEL32!GetModuleHandleW` at `0x18001a576`
- `KERNEL32!GetProcAddress` at `0x18001a593`
- `KERNEL32!GetProcAddress` at `0x18001a593`

## string_xrefs

- `0x18001a56f`: `kernelbase.dll`
- `0x18001a589`: `TestCreate`

## pseudocode

```c
__int64 __fastcall TestCreate(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, _OWORD *a6)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *); // r10
  char v8; // di
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *))`TestCreate'::`2'::s_pfnTestCreate;
  v8 = a3;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_6;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)GetProcAddress(ModuleHandleW, "TestCreate");
  v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *))`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
  {
LABEL_6:
    LOBYTE(a3) = v8;
    return v6(a1, 0, a3, a4, a5, a6);
  }
  else
  {
    *a6 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18001a540  mov     [rsp+arg_0], rbx
0x18001a545  mov     [rsp+arg_8], rsi
0x18001a54a  push    rdi
0x18001a54b  sub     rsp, 40h
0x18001a54f  mov     r10, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001a556  mov     ebx, r9d
0x18001a559  mov     dil, r8b
0x18001a55c  mov     esi, ecx
0x18001a55e  test    r10, r10
0x18001a561  jnz     short loc_18001A5BE
0x18001a563  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001a56a  test    rax, rax
0x18001a56d  jnz     short loc_18001A589
0x18001a56f  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001a576  call    cs:__imp_GetModuleHandleW
0x18001a57d  nop     dword ptr [rax+rax+00h]
0x18001a582  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001a589  lea     rdx, aTestcreate; "TestCreate"
0x18001a590  mov     rcx, rax; hModule
0x18001a593  call    cs:__imp_GetProcAddress
0x18001a59a  nop     dword ptr [rax+rax+00h]
0x18001a59f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001a5a6  mov     r10, rax
0x18001a5a9  test    rax, rax
0x18001a5ac  jnz     short loc_18001A5BE
0x18001a5ae  mov     rax, [rsp+48h+arg_28]
0x18001a5b3  xorps   xmm0, xmm0
0x18001a5b6  movdqu  xmmword ptr [rax], xmm0
0x18001a5ba  xor     eax, eax
0x18001a5bc  jmp     short loc_18001A5E4
0x18001a5be  mov     rax, [rsp+48h+arg_28]
0x18001a5c3  mov     r9d, ebx
0x18001a5c6  mov     [rsp+48h+var_20], rax
0x18001a5cb  mov     r8b, dil
0x18001a5ce  mov     rax, [rsp+48h+arg_20]
0x18001a5d3  xor     edx, edx
0x18001a5d5  mov     [rsp+48h+var_28], rax
0x18001a5da  mov     ecx, esi
0x18001a5dc  mov     rax, r10
0x18001a5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e4  mov     rbx, [rsp+48h+arg_0]
0x18001a5e9  mov     rsi, [rsp+48h+arg_8]
0x18001a5ee  add     rsp, 40h
0x18001a5f2  pop     rdi
0x18001a5f3  retn
```
