# ShellShim_CorDllMainWorker(HINSTANCE__ *,ulong,void *)

- ea: `0x1800226f0`
- end: `0x1800227ee`
- name: `?ShellShim_CorDllMainWorker@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002efb4`

## callees

- `0x180001c10`
- `0x1800226f0`
- `0x180028fe8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180022760`
- `KERNEL32!GetProcAddress` at `0x1800227ad`
- `KERNEL32!GetProcAddress` at `0x180022760`
- `KERNEL32!GetProcAddress` at `0x1800227ad`

## string_xrefs

- `0x180022759`: `CorDllMainWorker_RetAddr`
- `0x1800227a6`: `CorDllMainWorker`

## pseudocode

```c
__int64 __fastcall ShellShim_CorDllMainWorker(HINSTANCE a1, unsigned int a2, void *a3)
{
  int ShimImpl; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
    return CorDllMainWorker(a1, a2, a3);
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfCorDllMainWorker_RetAddr == (int (*)(HINSTANCE, unsigned int, void *, void *))-1LL )
    g_pfCorDllMainWorker_RetAddr = (int (*)(HINSTANCE, unsigned int, void *, void *))GetProcAddress(
                                                                                       hModule,
                                                                                       "CorDllMainWorker_RetAddr");
  if ( g_pfCorDllMainWorker_RetAddr )
    return ((__int64 (__fastcall *)(HINSTANCE, _QWORD, void *, void *))g_pfCorDllMainWorker_RetAddr)(
             a1,
             a2,
             a3,
             retaddr);
  if ( g_pfCorDllMainWorker == (int (*)(HINSTANCE, unsigned int, void *))-1LL )
    g_pfCorDllMainWorker = (int (*)(HINSTANCE, unsigned int, void *))GetProcAddress(hModule, "CorDllMainWorker");
  if ( !g_pfCorDllMainWorker )
    return 0;
  else
    return ((__int64 (__fastcall *)(HINSTANCE, _QWORD, void *))g_pfCorDllMainWorker)(a1, a2, a3);
}

```

## disassembly

```asm
0x1800226f0  mov     rax, rsp
0x1800226f3  mov     [rax+8], rbx
0x1800226f7  mov     [rax+10h], rsi
0x1800226fb  push    rdi
0x1800226fc  sub     rsp, 30h
0x180022700  mov     rsi, rcx
0x180022703  mov     qword ptr [rax+20h], 0
0x18002270b  lea     rcx, [rax+20h]
0x18002270f  mov     rbx, r8
0x180022712  mov     edi, edx
0x180022714  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180022719  cmp     eax, 1
0x18002271c  jz      loc_1800227DC
0x180022722  cmp     eax, 3
0x180022725  jnz     short loc_180022739
0x180022727  mov     r8, rbx; void *
0x18002272a  mov     edx, edi; unsigned int
0x18002272c  mov     rcx, rsi; HINSTANCE
0x18002272f  call    ?CorDllMainWorker@@YAHPEAUHINSTANCE__@@KPEAX@Z; CorDllMainWorker(HINSTANCE__ *,ulong,void *)
0x180022734  jmp     loc_1800227DE
0x180022739  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x18002273f  test    eax, eax
0x180022741  jnz     loc_1800227DC
0x180022747  mov     rax, cs:?g_pfCorDllMainWorker_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA; int (*g_pfCorDllMainWorker_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x18002274e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022752  jnz     short loc_18002276D
0x180022754  mov     rcx, [rsp+38h+hModule]; hModule
0x180022759  lea     rdx, aCordllmainwork_1; "CorDllMainWorker_RetAddr"
0x180022760  call    cs:__imp_GetProcAddress
0x180022766  mov     cs:?g_pfCorDllMainWorker_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA, rax; int (*g_pfCorDllMainWorker_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x18002276d  mov     rax, cs:?g_pfCorDllMainWorker_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA; int (*g_pfCorDllMainWorker_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x180022774  test    rax, rax
0x180022777  jz      short loc_180022794
0x180022779  mov     rax, cs:?g_pfCorDllMainWorker_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA; int (*g_pfCorDllMainWorker_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x180022780  mov     r8, rbx
0x180022783  mov     r9, [rsp+38h]
0x180022788  mov     edx, edi
0x18002278a  mov     rcx, rsi
0x18002278d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022792  jmp     short loc_1800227DE
0x180022794  mov     rax, cs:?g_pfCorDllMainWorker@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pfCorDllMainWorker)(HINSTANCE__ *,ulong,void *)
0x18002279b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002279f  jnz     short loc_1800227BA
0x1800227a1  mov     rcx, [rsp+38h+hModule]; hModule
0x1800227a6  lea     rdx, aCordllmainwork_2; "CorDllMainWorker"
0x1800227ad  call    cs:__imp_GetProcAddress
0x1800227b3  mov     cs:?g_pfCorDllMainWorker@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA, rax; int (*g_pfCorDllMainWorker)(HINSTANCE__ *,ulong,void *)
0x1800227ba  mov     rax, cs:?g_pfCorDllMainWorker@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pfCorDllMainWorker)(HINSTANCE__ *,ulong,void *)
0x1800227c1  test    rax, rax
0x1800227c4  jz      short loc_1800227DC
0x1800227c6  mov     rax, cs:?g_pfCorDllMainWorker@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pfCorDllMainWorker)(HINSTANCE__ *,ulong,void *)
0x1800227cd  mov     r8, rbx
0x1800227d0  mov     edx, edi
0x1800227d2  mov     rcx, rsi
0x1800227d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227da  jmp     short loc_1800227DE
0x1800227dc  xor     eax, eax
0x1800227de  mov     rbx, [rsp+38h+arg_0]
0x1800227e3  mov     rsi, [rsp+38h+arg_8]
0x1800227e8  add     rsp, 30h
0x1800227ec  pop     rdi
0x1800227ed  retn
```
