# DllUnregisterServer

- ea: `0x18002d34c`
- end: `0x18002d3e8`
- name: `DllUnregisterServer`
- size: `156`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800242e0`

## callees

- `0x18002a230`
- `0x18002d34c`
- `0x18002d658`
- `0x180041ac0`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d3ad`
- `KERNEL32!GetProcAddress` at `0x18002d3ad`

## string_xrefs

- `0x18002d3a6`: `DllUnregisterServerInternal`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
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
      ProcAddress = GetProcAddress(hModule, "DllUnregisterServerInternal");
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
0x18002d34c  sub     rsp, 258h
0x18002d353  mov     rax, cs:__security_cookie
0x18002d35a  xor     rax, rsp
0x18002d35d  mov     [rsp+258h+var_18], rax
0x18002d365  mov     edx, 1; int
0x18002d36a  mov     [rsp+258h+hModule], 0
0x18002d373  lea     rcx, [rsp+258h+hModule]; HINSTANCE *
0x18002d378  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x18002d37d  test    eax, eax
0x18002d37f  js      short loc_18002D3D0
0x18002d381  lea     r8, [rsp+258h+var_238]
0x18002d386  mov     [rsp+258h+var_238], 0
0x18002d38e  mov     edx, 104h
0x18002d393  lea     rcx, [rsp+258h+var_228]; void *
0x18002d398  call    GetCORSystemDirectory
0x18002d39d  test    eax, eax
0x18002d39f  js      short loc_18002D3D0
0x18002d3a1  mov     rcx, [rsp+258h+hModule]; hModule
0x18002d3a6  lea     rdx, aDllunregisters_1; "DllUnregisterServerInternal"
0x18002d3ad  call    cs:__imp_GetProcAddress
0x18002d3b3  test    rax, rax
0x18002d3b6  jz      short loc_18002D3CB
0x18002d3b8  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimMod
0x18002d3bf  lea     rdx, [rsp+258h+var_228]
0x18002d3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3c9  jmp     short loc_18002D3D0
0x18002d3cb  mov     eax, 80131701h
0x18002d3d0  mov     rcx, [rsp+258h+var_18]
0x18002d3d8  xor     rcx, rsp; StackCookie
0x18002d3db  call    __security_check_cookie
0x18002d3e0  add     rsp, 258h
0x18002d3e7  retn
```
