# DllRegisterServer

- ea: `0x18002d2a8`
- end: `0x18002d344`
- name: `DllRegisterServer`
- size: `156`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180024200`

## callees

- `0x18002a230`
- `0x18002d2a8`
- `0x18002d658`
- `0x180041ac0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d309`
- `KERNEL32!GetProcAddress` at `0x18002d309`

## string_xrefs

- `0x18002d302`: `DllRegisterServerInternal`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  FARPROC ProcAddress; // rax
  HMODULE hModule; // [rsp+28h] [rbp-230h] BYREF
  _BYTE v3[528]; // [rsp+30h] [rbp-228h] BYREF

  hModule = 0;
  result = GetRealDll(&hModule, 1);
  if ( result >= 0 )
  {
    result = GetCORSystemDirectory(v3);
    if ( result >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "DllRegisterServerInternal");
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(HMODULE, _BYTE *))ProcAddress)(g_hShimMod, v3);
      else
        return -2146232575;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d2a8  sub     rsp, 258h
0x18002d2af  mov     rax, cs:__security_cookie
0x18002d2b6  xor     rax, rsp
0x18002d2b9  mov     [rsp+258h+var_18], rax
0x18002d2c1  mov     edx, 1; int
0x18002d2c6  mov     [rsp+258h+hModule], 0
0x18002d2cf  lea     rcx, [rsp+258h+hModule]; HINSTANCE *
0x18002d2d4  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x18002d2d9  test    eax, eax
0x18002d2db  js      short loc_18002D32C
0x18002d2dd  lea     r8, [rsp+258h+var_238]
0x18002d2e2  mov     [rsp+258h+var_238], 0
0x18002d2ea  mov     edx, 104h
0x18002d2ef  lea     rcx, [rsp+258h+var_228]; void *
0x18002d2f4  call    GetCORSystemDirectory
0x18002d2f9  test    eax, eax
0x18002d2fb  js      short loc_18002D32C
0x18002d2fd  mov     rcx, [rsp+258h+hModule]; hModule
0x18002d302  lea     rdx, aDllregisterser_0; "DllRegisterServerInternal"
0x18002d309  call    cs:__imp_GetProcAddress
0x18002d30f  test    rax, rax
0x18002d312  jz      short loc_18002D327
0x18002d314  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimMod
0x18002d31b  lea     rdx, [rsp+258h+var_228]
0x18002d320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d325  jmp     short loc_18002D32C
0x18002d327  mov     eax, 80131701h
0x18002d32c  mov     rcx, [rsp+258h+var_18]
0x18002d334  xor     rcx, rsp; StackCookie
0x18002d337  call    __security_check_cookie
0x18002d33c  add     rsp, 258h
0x18002d343  retn
```
