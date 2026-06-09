# TestCreate

- ea: `0x180019640`
- end: `0x1800196e8`
- name: `TestCreate`
- size: `168`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, unsigned int, __int64, _OWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018a48`
- `0x180018c48`

## callees

- `0x180019640`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180019676`
- `KERNEL32!GetModuleHandleW` at `0x180019676`
- `KERNEL32!GetProcAddress` at `0x18001968d`
- `KERNEL32!GetProcAddress` at `0x18001968d`

## string_xrefs

- `0x18001966f`: `kernelbase.dll`
- `0x180019683`: `TestCreate`

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
0x180019640  mov     [rsp+arg_0], rbx
0x180019645  mov     [rsp+arg_8], rsi
0x18001964a  push    rdi
0x18001964b  sub     rsp, 40h
0x18001964f  mov     r10, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180019656  mov     ebx, r9d
0x180019659  mov     dil, r8b
0x18001965c  mov     esi, ecx
0x18001965e  test    r10, r10
0x180019661  jnz     short loc_1800196B2
0x180019663  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001966a  test    rax, rax
0x18001966d  jnz     short loc_180019683
0x18001966f  lea     rcx, ModuleName; "kernelbase.dll"
0x180019676  call    cs:__imp_GetModuleHandleW
0x18001967c  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180019683  lea     rdx, aTestcreate; "TestCreate"
0x18001968a  mov     rcx, rax; hModule
0x18001968d  call    cs:__imp_GetProcAddress
0x180019693  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18001969a  mov     r10, rax
0x18001969d  test    rax, rax
0x1800196a0  jnz     short loc_1800196B2
0x1800196a2  mov     rax, [rsp+48h+arg_28]
0x1800196a7  xorps   xmm0, xmm0
0x1800196aa  movdqu  xmmword ptr [rax], xmm0
0x1800196ae  xor     eax, eax
0x1800196b0  jmp     short loc_1800196D8
0x1800196b2  mov     rax, [rsp+48h+arg_28]
0x1800196b7  mov     r9d, ebx
0x1800196ba  mov     [rsp+48h+var_20], rax
0x1800196bf  mov     r8b, dil
0x1800196c2  mov     rax, [rsp+48h+arg_20]
0x1800196c7  xor     edx, edx
0x1800196c9  mov     [rsp+48h+var_28], rax
0x1800196ce  mov     ecx, esi
0x1800196d0  mov     rax, r10
0x1800196d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196d8  mov     rbx, [rsp+48h+arg_0]
0x1800196dd  mov     rsi, [rsp+48h+arg_8]
0x1800196e2  add     rsp, 40h
0x1800196e6  pop     rdi
0x1800196e7  retn
```
