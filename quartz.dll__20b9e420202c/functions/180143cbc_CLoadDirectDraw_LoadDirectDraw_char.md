# CLoadDirectDraw::LoadDirectDraw(char *)

- ea: `0x180143cbc`
- end: `0x180143dbf`
- name: `?LoadDirectDraw@CLoadDirectDraw@@QEAAJPEAD@Z`
- size: `259`
- prototype: `__int64 __fastcall(CLoadDirectDraw *__hidden this, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800a0e30`

## callees

- `0x18002d864`
- `0x180143cbc`
- `0x18014d0a0`
- `0x18014d15c`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x180143ce6`
- `KERNEL32!SetErrorMode` at `0x180143d15`
- `KERNEL32!SetErrorMode` at `0x180143ce6`
- `KERNEL32!SetErrorMode` at `0x180143d15`
- `KERNEL32!LoadLibraryExW` at `0x180143d03`
- `KERNEL32!LoadLibraryExW` at `0x180143d03`
- `KERNEL32!GetProcAddress` at `0x180143d35`
- `KERNEL32!GetProcAddress` at `0x180143d4f`
- `KERNEL32!GetProcAddress` at `0x180143d69`
- `KERNEL32!GetProcAddress` at `0x180143d35`
- `KERNEL32!GetProcAddress` at `0x180143d4f`
- `KERNEL32!GetProcAddress` at `0x180143d69`

## string_xrefs

- `0x180143cf4`: `DDRAW.DLL`
- `0x180143d2e`: `DirectDrawCreate`

## pseudocode

```c
__int64 __fastcall CLoadDirectDraw::LoadDirectDraw(CLoadDirectDraw *this, char *a2)
{
  HMODULE v5; // rcx
  UINT v6; // ebx
  FARPROC ProcAddress; // rbp
  FARPROC v8; // rbx
  FARPROC v9; // rax
  __int64 v10; // rax

  if ( *(_QWORD *)this )
    return 0;
  v5 = (HMODULE)*((_QWORD *)this + 1);
  if ( v5
    || (v6 = SetErrorMode(0x8000u),
        *((_QWORD *)this + 1) = LoadLibraryExW(L"DDRAW.DLL", 0, 0x800u),
        SetErrorMode(v6),
        (v5 = (HMODULE)*((_QWORD *)this + 1)) != 0) )
  {
    ProcAddress = GetProcAddress(v5, "DirectDrawCreate");
    v8 = GetProcAddress(*((HMODULE *)this + 1), "DirectDrawEnumerateA");
    v9 = GetProcAddress(*((HMODULE *)this + 1), "DirectDrawEnumerateExA");
    if ( ProcAddress && v8 )
    {
      v10 = v9 ? DirectDrawCreateFromDeviceEx(a2, ProcAddress, v9) : DirectDrawCreateFromDevice(a2, ProcAddress, v8);
      *(_QWORD *)this = v10;
      if ( v10 )
        return 0;
    }
    RELEASE<IDDVideoAcceleratorContainer>(this);
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180143cbc  push    rbx
0x180143cbe  push    rbp
0x180143cbf  push    rsi
0x180143cc0  push    rdi
0x180143cc1  sub     rsp, 28h
0x180143cc5  cmp     qword ptr [rcx], 0
0x180143cc9  mov     rsi, rdx
0x180143ccc  mov     rdi, rcx
0x180143ccf  jz      short loc_180143CD8
0x180143cd1  xor     eax, eax
0x180143cd3  jmp     loc_180143DB5
0x180143cd8  mov     rcx, [rcx+8]
0x180143cdc  test    rcx, rcx
0x180143cdf  jnz     short loc_180143D2E
0x180143ce1  mov     ecx, 8000h; uMode
0x180143ce6  call    cs:__imp_SetErrorMode
0x180143ced  nop     dword ptr [rax+rax+00h]
0x180143cf2  xor     edx, edx; hFile
0x180143cf4  lea     rcx, aDdrawDll_0; "DDRAW.DLL"
0x180143cfb  mov     r8d, 800h; dwFlags
0x180143d01  mov     ebx, eax
0x180143d03  call    cs:__imp_LoadLibraryExW
0x180143d0a  nop     dword ptr [rax+rax+00h]
0x180143d0f  mov     ecx, ebx; uMode
0x180143d11  mov     [rdi+8], rax
0x180143d15  call    cs:__imp_SetErrorMode
0x180143d1c  nop     dword ptr [rax+rax+00h]
0x180143d21  mov     rcx, [rdi+8]; hModule
0x180143d25  test    rcx, rcx
0x180143d28  jz      loc_180143DB0
0x180143d2e  lea     rdx, aDirectdrawcrea_0; "DirectDrawCreate"
0x180143d35  call    cs:__imp_GetProcAddress
0x180143d3c  nop     dword ptr [rax+rax+00h]
0x180143d41  mov     rcx, [rdi+8]; hModule
0x180143d45  lea     rdx, aDirectdrawenum_2; "DirectDrawEnumerateA"
0x180143d4c  mov     rbp, rax
0x180143d4f  call    cs:__imp_GetProcAddress
0x180143d56  nop     dword ptr [rax+rax+00h]
0x180143d5b  mov     rcx, [rdi+8]; hModule
0x180143d5f  lea     rdx, aDirectdrawenum_1; "DirectDrawEnumerateExA"
0x180143d66  mov     rbx, rax
0x180143d69  call    cs:__imp_GetProcAddress
0x180143d70  nop     dword ptr [rax+rax+00h]
0x180143d75  test    rbp, rbp
0x180143d78  jz      short loc_180143DA8
0x180143d7a  test    rbx, rbx
0x180143d7d  jz      short loc_180143DA8
0x180143d7f  mov     rdx, rbp
0x180143d82  mov     rcx, rsi
0x180143d85  test    rax, rax
0x180143d88  jz      short loc_180143D94
0x180143d8a  mov     r8, rax
0x180143d8d  call    DirectDrawCreateFromDeviceEx
0x180143d92  jmp     short loc_180143D9C
0x180143d94  mov     r8, rbx
0x180143d97  call    DirectDrawCreateFromDevice
0x180143d9c  mov     [rdi], rax
0x180143d9f  test    rax, rax
0x180143da2  jnz     loc_180143CD1
0x180143da8  mov     rcx, rdi
0x180143dab  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x180143db0  mov     eax, 80004002h
0x180143db5  add     rsp, 28h
0x180143db9  pop     rdi
0x180143dba  pop     rsi
0x180143dbb  pop     rbp
0x180143dbc  pop     rbx
0x180143dbd  retn
```
