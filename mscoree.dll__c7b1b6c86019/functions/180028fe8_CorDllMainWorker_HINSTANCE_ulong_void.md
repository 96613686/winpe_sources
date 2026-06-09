# CorDllMainWorker(HINSTANCE__ *,ulong,void *)

- ea: `0x180028fe8`
- end: `0x18002908a`
- name: `?CorDllMainWorker@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800226f0`

## callees

- `0x180028fe8`
- `0x180029b38`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002904e`
- `KERNEL32!GetProcAddress` at `0x18002904e`

## string_xrefs

- `0x180029047`: `_CorDllMain`

## pseudocode

```c
__int64 __fastcall CorDllMainWorker(CLRFullPath *a1, unsigned int a2, void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE hModule; // [rsp+48h] [rbp+20h] BYREF

  if ( (a2 || CLRFullPath::GetFullPath(a1))
    && ((ProcAddress = (FARPROC)g_pCorDllMain) != 0
     || (g_hMod || a2)
     && ((hModule = 0, (int)GetRealDll(&hModule, 1) < 0)
       ? (ProcAddress = (FARPROC)g_pCorDllMain)
       : (FARPROC)(ProcAddress = GetProcAddress(hModule, "_CorDllMain"),
                   g_pCorDllMain = (int (*)(HINSTANCE, unsigned int, void *))ProcAddress),
         ProcAddress)) )
  {
    return ((__int64 (__fastcall *)(CLRFullPath *, _QWORD, void *))ProcAddress)(a1, a2, a3);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180028fe8  mov     [rsp+arg_0], rbx
0x180028fed  mov     [rsp+arg_8], rsi
0x180028ff2  push    rdi
0x180028ff3  sub     rsp, 20h
0x180028ff7  mov     rdi, r8
0x180028ffa  mov     ebx, edx
0x180028ffc  mov     rsi, rcx
0x180028fff  test    edx, edx
0x180029001  jnz     short loc_18002900D
0x180029003  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x180029008  test    rax, rax
0x18002900b  jz      short loc_180029069
0x18002900d  mov     rax, cs:?g_pCorDllMain@@3P6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pCorDllMain)(HINSTANCE__ *,ulong,void *)
0x180029014  test    rax, rax
0x180029017  jnz     short loc_18002906D
0x180029019  cmp     cs:?g_hMod@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hMod
0x180029020  jnz     short loc_180029026
0x180029022  test    ebx, ebx
0x180029024  jz      short loc_180029069
0x180029026  mov     edx, 1; int
0x18002902b  mov     [rsp+28h+hModule], 0
0x180029034  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x180029039  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x18002903e  test    eax, eax
0x180029040  js      short loc_18002905D
0x180029042  mov     rcx, [rsp+28h+hModule]; hModule
0x180029047  lea     rdx, aCordllmain_0; "_CorDllMain"
0x18002904e  call    cs:__imp_GetProcAddress
0x180029054  mov     cs:?g_pCorDllMain@@3P6AHPEAUHINSTANCE__@@KPEAX@ZEA, rax; int (*g_pCorDllMain)(HINSTANCE__ *,ulong,void *)
0x18002905b  jmp     short loc_180029064
0x18002905d  mov     rax, cs:?g_pCorDllMain@@3P6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pCorDllMain)(HINSTANCE__ *,ulong,void *)
0x180029064  test    rax, rax
0x180029067  jnz     short loc_18002906D
0x180029069  xor     eax, eax
0x18002906b  jmp     short loc_18002907A
0x18002906d  mov     r8, rdi
0x180029070  mov     edx, ebx
0x180029072  mov     rcx, rsi
0x180029075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002907a  mov     rbx, [rsp+28h+arg_0]
0x18002907f  mov     rsi, [rsp+28h+arg_8]
0x180029084  add     rsp, 20h
0x180029088  pop     rdi
0x180029089  retn
```
