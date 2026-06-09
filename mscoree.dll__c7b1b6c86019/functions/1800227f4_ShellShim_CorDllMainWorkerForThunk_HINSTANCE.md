# ShellShim_CorDllMainWorkerForThunk(HINSTANCE__ *)

- ea: `0x1800227f4`
- end: `0x1800228d5`
- name: `?ShellShim_CorDllMainWorkerForThunk@@YAJPEAUHINSTANCE__@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002f850`

## callees

- `0x180001c10`
- `0x1800227f4`
- `0x180029090`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180022852`
- `KERNEL32!GetProcAddress` at `0x18002289d`
- `KERNEL32!GetProcAddress` at `0x180022852`
- `KERNEL32!GetProcAddress` at `0x18002289d`

## string_xrefs

- `0x18002284b`: `CorDllMainWorkerForThunk_RetAddr`
- `0x180022896`: `CorDllMainWorkerForThunk`

## pseudocode

```c
__int64 __fastcall ShellShim_CorDllMainWorkerForThunk(HINSTANCE a1)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+38h] [rbp+10h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return CorDllMainWorkerForThunk(a1);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfCorDllMainWorkerForThunk_RetAddr == (int (*)(HINSTANCE, void *))-1LL )
    g_pfCorDllMainWorkerForThunk_RetAddr = (int (*)(HINSTANCE, void *))GetProcAddress(
                                                                         hModule,
                                                                         "CorDllMainWorkerForThunk_RetAddr");
  if ( g_pfCorDllMainWorkerForThunk_RetAddr )
    return ((__int64 (__fastcall *)(HINSTANCE, void *))g_pfCorDllMainWorkerForThunk_RetAddr)(a1, retaddr);
  if ( g_pfCorDllMainWorkerForThunk == (int (*)(HINSTANCE))-1LL )
    g_pfCorDllMainWorkerForThunk = (int (*)(HINSTANCE))GetProcAddress(hModule, "CorDllMainWorkerForThunk");
  if ( !g_pfCorDllMainWorkerForThunk )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(HINSTANCE))g_pfCorDllMainWorkerForThunk)(a1);
}

```

## disassembly

```asm
0x1800227f4  push    rbx
0x1800227f6  sub     rsp, 20h
0x1800227fa  mov     rbx, rcx
0x1800227fd  mov     [rsp+28h+hModule], 0
0x180022806  lea     rcx, [rsp+28h+hModule]
0x18002280b  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180022810  cmp     eax, 1
0x180022813  jz      loc_1800228CA
0x180022819  cmp     eax, 3
0x18002281c  jnz     short loc_18002282B
0x18002281e  mov     rcx, rbx; HINSTANCE
0x180022821  add     rsp, 20h
0x180022825  pop     rbx
0x180022826  jmp     ?CorDllMainWorkerForThunk@@YAJPEAUHINSTANCE__@@@Z; CorDllMainWorkerForThunk(HINSTANCE__ *)
0x18002282b  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180022831  test    eax, eax
0x180022833  jnz     loc_1800228CA
0x180022839  mov     rax, cs:?g_pfCorDllMainWorkerForThunk_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfCorDllMainWorkerForThunk_RetAddr)(HINSTANCE__ *,void *)
0x180022840  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022844  jnz     short loc_18002285F
0x180022846  mov     rcx, [rsp+28h+hModule]; hModule
0x18002284b  lea     rdx, aCordllmainwork_3; "CorDllMainWorkerForThunk_RetAddr"
0x180022852  call    cs:__imp_GetProcAddress
0x180022858  mov     cs:?g_pfCorDllMainWorkerForThunk_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA, rax; long (*g_pfCorDllMainWorkerForThunk_RetAddr)(HINSTANCE__ *,void *)
0x18002285f  mov     rax, cs:?g_pfCorDllMainWorkerForThunk_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfCorDllMainWorkerForThunk_RetAddr)(HINSTANCE__ *,void *)
0x180022866  test    rax, rax
0x180022869  jz      short loc_180022884
0x18002286b  mov     rax, cs:?g_pfCorDllMainWorkerForThunk_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfCorDllMainWorkerForThunk_RetAddr)(HINSTANCE__ *,void *)
0x180022872  mov     rcx, rbx
0x180022875  mov     rdx, [rsp+28h]
0x18002287a  add     rsp, 20h
0x18002287e  pop     rbx
0x18002287f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180022884  mov     rax, cs:?g_pfCorDllMainWorkerForThunk@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfCorDllMainWorkerForThunk)(HINSTANCE__ *)
0x18002288b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002288f  jnz     short loc_1800228AA
0x180022891  mov     rcx, [rsp+28h+hModule]; hModule
0x180022896  lea     rdx, aCordllmainwork_0; "CorDllMainWorkerForThunk"
0x18002289d  call    cs:__imp_GetProcAddress
0x1800228a3  mov     cs:?g_pfCorDllMainWorkerForThunk@@3R6AJPEAUHINSTANCE__@@@ZEA, rax; long (*g_pfCorDllMainWorkerForThunk)(HINSTANCE__ *)
0x1800228aa  mov     rax, cs:?g_pfCorDllMainWorkerForThunk@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfCorDllMainWorkerForThunk)(HINSTANCE__ *)
0x1800228b1  test    rax, rax
0x1800228b4  jz      short loc_1800228CA
0x1800228b6  mov     rax, cs:?g_pfCorDllMainWorkerForThunk@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfCorDllMainWorkerForThunk)(HINSTANCE__ *)
0x1800228bd  mov     rcx, rbx
0x1800228c0  add     rsp, 20h
0x1800228c4  pop     rbx
0x1800228c5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ca  mov     eax, 80131701h
0x1800228cf  add     rsp, 20h
0x1800228d3  pop     rbx
0x1800228d4  retn
```
