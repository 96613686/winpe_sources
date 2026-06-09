# CreateDXVA2DeviceManager(IDirect3DDeviceManager9 * *,uint *)

- ea: `0x180035c90`
- end: `0x180035d89`
- name: `?CreateDXVA2DeviceManager@@YAJPEAPEAUIDirect3DDeviceManager9@@PEAI@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct IDirect3DDeviceManager9 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180029ee0`

## callees

- `0x18001f620`
- `0x180035c90`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180035d43`
- `KERNEL32!GetProcAddress` at `0x180035d43`
- `KERNEL32!LoadLibraryExA` at `0x180035d1c`
- `KERNEL32!LoadLibraryExA` at `0x180035d1c`

## string_xrefs

- `0x180035ca9`: `DXVA2.DLL`
- `0x180035cd5`: `DXVA2CreateDirect3DDeviceManager9`

## pseudocode

```c
__int64 __fastcall CreateDXVA2DeviceManager(struct IDirect3DDeviceManager9 **a1, unsigned int *a2)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  CHAR LibFileName[16]; // [rsp+20h] [rbp-48h] BYREF
  CHAR ProcName[40]; // [rsp+30h] [rbp-38h] BYREF

  strcpy(LibFileName, "DXVA2.DLL");
  strcpy(ProcName, "DXVA2CreateDirect3DDeviceManager9");
  if ( !a1 || !a2 )
    return 2147942487LL;
  ProcAddress = (FARPROC)qword_180051550;
  if ( qword_180051550 )
    return ((__int64 (__fastcall *)(unsigned int *, struct IDirect3DDeviceManager9 **))ProcAddress)(a2, a1);
  if ( ((Library = hModule) != 0 || (Library = LoadLibraryExA(LibFileName, 0, 0x800u), (hModule = Library) != 0))
    && (ProcAddress = GetProcAddress(Library, ProcName), (qword_180051550 = (__int64)ProcAddress) != 0) )
  {
    return ((__int64 (__fastcall *)(unsigned int *, struct IDirect3DDeviceManager9 **))ProcAddress)(a2, a1);
  }
  else
  {
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180035c90  mov     [rsp+arg_10], rbx
0x180035c95  push    rdi
0x180035c96  sub     rsp, 60h
0x180035c9a  mov     rax, cs:__security_cookie
0x180035ca1  xor     rax, rsp
0x180035ca4  mov     [rsp+68h+var_10], rax
0x180035ca9  movsd   xmm0, qword ptr cs:aDxva2Dll; "DXVA2.DLL"
0x180035cb1  mov     rbx, rdx
0x180035cb4  movzx   eax, word ptr cs:aDxva2Dll+8; "L"
0x180035cbb  mov     rdi, rcx
0x180035cbe  movsd   qword ptr [rsp+68h+LibFileName], xmm0
0x180035cc4  mov     [rsp+68h+var_40], ax
0x180035cc9  movzx   eax, word ptr cs:aDxva2createdir+20h; "9"
0x180035cd0  mov     word ptr [rsp+68h+var_18], ax
0x180035cd5  movups  xmm0, xmmword ptr cs:aDxva2createdir; "DXVA2CreateDirect3DDeviceManager9"
0x180035cdc  movups  xmm1, xmmword ptr cs:aDxva2createdir+10h; "t3DDeviceManager9"
0x180035ce3  movups  xmmword ptr [rsp+68h+ProcName], xmm0
0x180035ce8  movups  [rsp+68h+var_28], xmm1
0x180035ced  test    rcx, rcx
0x180035cf0  jz      short loc_180035D68
0x180035cf2  test    rdx, rdx
0x180035cf5  jz      short loc_180035D68
0x180035cf7  mov     rax, cs:qword_180051550
0x180035cfe  test    rax, rax
0x180035d01  jnz     short loc_180035D5B
0x180035d03  mov     rax, cs:hModule
0x180035d0a  test    rax, rax
0x180035d0d  jnz     short loc_180035D3B
0x180035d0f  xor     edx, edx; hFile
0x180035d11  lea     rcx, [rsp+68h+LibFileName]; lpLibFileName
0x180035d16  mov     r8d, 800h; dwFlags
0x180035d1c  call    cs:__imp_LoadLibraryExA
0x180035d23  nop     dword ptr [rax+rax+00h]
0x180035d28  mov     cs:hModule, rax
0x180035d2f  test    rax, rax
0x180035d32  jnz     short loc_180035D3B
0x180035d34  mov     eax, 80004005h
0x180035d39  jmp     short loc_180035D6D
0x180035d3b  lea     rdx, [rsp+68h+ProcName]; lpProcName
0x180035d40  mov     rcx, rax; hModule
0x180035d43  call    cs:__imp_GetProcAddress
0x180035d4a  nop     dword ptr [rax+rax+00h]
0x180035d4f  mov     cs:qword_180051550, rax
0x180035d56  test    rax, rax
0x180035d59  jz      short loc_180035D34
0x180035d5b  mov     rdx, rdi
0x180035d5e  mov     rcx, rbx
0x180035d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d66  jmp     short loc_180035D6D
0x180035d68  mov     eax, 80070057h
0x180035d6d  mov     rcx, [rsp+68h+var_10]
0x180035d72  xor     rcx, rsp; StackCookie
0x180035d75  call    __security_check_cookie
0x180035d7a  mov     rbx, [rsp+68h+arg_10]
0x180035d82  add     rsp, 60h
0x180035d86  pop     rdi
0x180035d87  retn
```
