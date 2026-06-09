# CreateDXVA2DeviceManager(IDirect3DDeviceManager9 * *,uint *)

- ea: `0x1002c59f`
- end: `0x1002c64d`
- name: `?CreateDXVA2DeviceManager@@YGJPAPAUIDirect3DDeviceManager9@@PAI@Z`
- size: `174`
- prototype: `int __cdecl(struct IDirect3DDeviceManager9 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x10018aa0`

## callees

- `0x1002c59f`
- `0x1002d510`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1002c616`
- `KERNEL32!GetProcAddress` at `0x1002c616`
- `KERNEL32!LoadLibraryExA` at `0x1002c5fb`
- `KERNEL32!LoadLibraryExA` at `0x1002c5fb`

## string_xrefs

- `0x1002c5b4`: `DXVA2.DLL`
- `0x1002c5cd`: `DXVA2CreateDirect3DDeviceManager9`

## pseudocode

```c
int __fastcall CreateDXVA2DeviceManager(int a1, int a2)
{
  int v2; // eax
  CD3DSurfaceAllocator *ProcAddress; // esi
  HMODULE Library; // eax
  CHAR ProcName[36]; // [esp+10h] [ebp-34h] BYREF
  CHAR LibFileName[12]; // [esp+34h] [ebp-10h] BYREF

  v2 = a1;
  strcpy(LibFileName, "DXVA2.DLL");
  strcpy(ProcName, "DXVA2CreateDirect3DDeviceManager9");
  if ( !a1 || !a2 )
    return -2147024809;
  ProcAddress = dword_1003D384;
  if ( !dword_1003D384 )
  {
    Library = (HMODULE)hModule;
    if ( !hModule )
    {
      Library = LoadLibraryExA(LibFileName, 0, 0x800u);
      hModule = Library;
      if ( !Library )
        return -2147467259;
    }
    ProcAddress = (CD3DSurfaceAllocator *)GetProcAddress(Library, ProcName);
    dword_1003D384 = ProcAddress;
    if ( !ProcAddress )
      return -2147467259;
    v2 = a1;
  }
  return ((int (__thiscall *)(CD3DSurfaceAllocator *, int, int))ProcAddress)(ProcAddress, a2, v2);
}

```

## disassembly

```asm
0x1002c59f  mov     edi, edi
0x1002c5a1  push    ebp
0x1002c5a2  mov     ebp, esp
0x1002c5a4  sub     esp, 38h
0x1002c5a7  mov     eax, ___security_cookie
0x1002c5ac  xor     eax, ebp
0x1002c5ae  mov     [ebp+var_4], eax
0x1002c5b1  push    ebx
0x1002c5b2  push    esi
0x1002c5b3  push    edi
0x1002c5b4  mov     esi, offset aDxva2Dll; "DXVA2.DLL"
0x1002c5b9  lea     edi, [ebp+LibFileName]
0x1002c5bc  mov     eax, ecx
0x1002c5be  mov     ebx, edx
0x1002c5c0  mov     [ebp+var_38], eax
0x1002c5c3  push    8
0x1002c5c5  movsd
0x1002c5c6  pop     ecx
0x1002c5c7  movsd
0x1002c5c8  movsw
0x1002c5ca  lea     edi, [ebp+ProcName]
0x1002c5cd  mov     esi, offset aDxva2createdir; "DXVA2CreateDirect3DDeviceManager9"
0x1002c5d2  rep movsd
0x1002c5d4  movsw
0x1002c5d6  test    eax, eax
0x1002c5d8  jz      short loc_1002C639
0x1002c5da  test    ebx, ebx
0x1002c5dc  jz      short loc_1002C639
0x1002c5de  mov     esi, dword_1003D384
0x1002c5e4  test    esi, esi
0x1002c5e6  jnz     short loc_1002C62B
0x1002c5e8  mov     eax, hModule
0x1002c5ed  test    eax, eax
0x1002c5ef  jnz     short loc_1002C611
0x1002c5f1  push    800h; dwFlags
0x1002c5f6  push    eax; hFile
0x1002c5f7  lea     eax, [ebp+LibFileName]
0x1002c5fa  push    eax; lpLibFileName
0x1002c5fb  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x1002c601  mov     hModule, eax
0x1002c606  test    eax, eax
0x1002c608  jnz     short loc_1002C611
0x1002c60a  mov     eax, 80004005h
0x1002c60f  jmp     short loc_1002C63E
0x1002c611  lea     ecx, [ebp+ProcName]
0x1002c614  push    ecx; lpProcName
0x1002c615  push    eax; hModule
0x1002c616  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1002c61c  mov     esi, eax
0x1002c61e  mov     dword_1003D384, esi
0x1002c624  test    esi, esi
0x1002c626  jz      short loc_1002C60A
0x1002c628  mov     eax, [ebp+var_38]
0x1002c62b  push    eax
0x1002c62c  push    ebx
0x1002c62d  mov     ecx, esi; this
0x1002c62f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c635  call    esi ; dword_1003D384
0x1002c637  jmp     short loc_1002C63E
0x1002c639  mov     eax, 80070057h
0x1002c63e  mov     ecx, [ebp+var_4]
0x1002c641  pop     edi
0x1002c642  pop     esi
0x1002c643  xor     ecx, ebp; StackCookie
0x1002c645  pop     ebx
0x1002c646  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002c64b  leave
0x1002c64c  retn
```
