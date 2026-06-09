# CorDllMainWorkerForThunk(HINSTANCE__ *)

- ea: `0x180029090`
- end: `0x18002910d`
- name: `?CorDllMainWorkerForThunk@@YAJPEAUHINSTANCE__@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800227f4`

## callees

- `0x180029090`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800290cf`
- `KERNEL32!GetProcAddress` at `0x1800290cf`

## string_xrefs

- `0x1800290c8`: `CorDllMainForThunk`

## pseudocode

```c
__int64 __fastcall CorDllMainWorkerForThunk(HINSTANCE a1)
{
  FARPROC ProcAddress; // rax
  int RealDll; // ebx
  HMODULE hModule; // [rsp+38h] [rbp+10h] BYREF

  ProcAddress = (FARPROC)g_pCorDllMainForThunk;
  RealDll = 0;
  if ( g_pCorDllMainForThunk
    || ((hModule = 0, RealDll = GetRealDll(&hModule, 1), RealDll < 0)
      ? (ProcAddress = (FARPROC)g_pCorDllMainForThunk)
      : (FARPROC)(ProcAddress = GetProcAddress(hModule, "CorDllMainForThunk"),
                  g_pCorDllMainForThunk = (void (*)(HINSTANCE, HINSTANCE))ProcAddress),
        ProcAddress) )
  {
    ((void (__fastcall *)(HINSTANCE, HMODULE))ProcAddress)(a1, g_hShimMod);
  }
  else
  {
    return (unsigned int)-2146232575;
  }
  return (unsigned int)RealDll;
}

```

## disassembly

```asm
0x180029090  mov     [rsp+arg_0], rbx
0x180029095  push    rdi
0x180029096  sub     rsp, 20h
0x18002909a  mov     rax, cs:?g_pCorDllMainForThunk@@3P6AXPEAUHINSTANCE__@@0@ZEA; void (*g_pCorDllMainForThunk)(HINSTANCE__ *,HINSTANCE__ *)
0x1800290a1  xor     ebx, ebx
0x1800290a3  mov     rdi, rcx
0x1800290a6  test    rax, rax
0x1800290a9  jnz     short loc_1800290F1
0x1800290ab  lea     edx, [rbx+1]; int
0x1800290ae  mov     [rsp+28h+hModule], rbx
0x1800290b3  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x1800290b8  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x1800290bd  mov     ebx, eax
0x1800290bf  test    eax, eax
0x1800290c1  js      short loc_1800290DE
0x1800290c3  mov     rcx, [rsp+28h+hModule]; hModule
0x1800290c8  lea     rdx, aCordllmainfort; "CorDllMainForThunk"
0x1800290cf  call    cs:__imp_GetProcAddress
0x1800290d5  mov     cs:?g_pCorDllMainForThunk@@3P6AXPEAUHINSTANCE__@@0@ZEA, rax; void (*g_pCorDllMainForThunk)(HINSTANCE__ *,HINSTANCE__ *)
0x1800290dc  jmp     short loc_1800290E5
0x1800290de  mov     rax, cs:?g_pCorDllMainForThunk@@3P6AXPEAUHINSTANCE__@@0@ZEA; void (*g_pCorDllMainForThunk)(HINSTANCE__ *,HINSTANCE__ *)
0x1800290e5  test    rax, rax
0x1800290e8  jnz     short loc_1800290F1
0x1800290ea  mov     ebx, 80131701h
0x1800290ef  jmp     short loc_180029100
0x1800290f1  mov     rdx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimMod
0x1800290f8  mov     rcx, rdi
0x1800290fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029100  mov     eax, ebx
0x180029102  mov     rbx, [rsp+28h+arg_0]
0x180029107  add     rsp, 20h
0x18002910b  pop     rdi
0x18002910c  retn
```
