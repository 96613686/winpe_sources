# CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)

- ea: `0x140057f64`
- end: `0x140057fbe`
- name: `?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z`
- size: `90`
- prototype: `int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `24`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140005fc8`
- `0x1400068b8`
- `0x140006ab0`
- `0x14000c2bc`
- `0x14000dd80`
- `0x14000f8a0`
- `0x140020be8`
- `0x140020cf8`
- `0x1400212e4`
- `0x140021460`
- `0x140021e40`
- `0x140022598`
- `0x140022f98`
- `0x140023070`
- `0x1400231c0`
- `0x140024768`
- `0x140024830`
- `0x1400249e0`
- `0x140036bd0`
- `0x140037bbc`
- `0x140045478`
- `0x140047170`
- `0x1400480c0`
- `0x1400572f8`

## callees

- `0x140057f64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057f90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057f90`

## pseudocode

```c
__int64 __fastcall CRegistry::OpenKey(CRegistry *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  HKEY v8; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v8 = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, a4, &v8);
  *((_DWORD *)this + 2) = v6;
  if ( !v6 )
  {
    v5 = 1;
    *(_QWORD *)this = v8;
  }
  return v5;
}

```

## disassembly

```asm
0x140057f64  mov     r11, rsp
0x140057f67  mov     [r11+10h], rbx
0x140057f6b  push    rdi
0x140057f6c  sub     rsp, 30h
0x140057f70  mov     rdi, rcx
0x140057f73  mov     rax, r8
0x140057f76  lea     rcx, [r11+8]
0x140057f7a  mov     r10, rdx
0x140057f7d  mov     [r11-18h], rcx
0x140057f81  xor     ebx, ebx
0x140057f83  mov     rcx, r10; hKey
0x140057f86  mov     [r11+8], rbx
0x140057f8a  xor     r8d, r8d; ulOptions
0x140057f8d  mov     rdx, rax; lpSubKey
0x140057f90  call    cs:__imp_RegOpenKeyExW
0x140057f97  nop     dword ptr [rax+rax+00h]
0x140057f9c  mov     [rdi+8], eax
0x140057f9f  test    eax, eax
0x140057fa1  jnz     short loc_140057FB0
0x140057fa3  mov     rax, [rsp+38h+arg_0]
0x140057fa8  mov     ebx, 1
0x140057fad  mov     [rdi], rax
0x140057fb0  mov     eax, ebx
0x140057fb2  mov     rbx, [rsp+38h+arg_8]
0x140057fb7  add     rsp, 30h
0x140057fbb  pop     rdi
0x140057fbc  retn
```
