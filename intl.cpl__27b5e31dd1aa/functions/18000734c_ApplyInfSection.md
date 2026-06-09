# ApplyInfSection

- ea: `0x18000734c`
- end: `0x180007394`
- name: `ApplyInfSection`
- size: `72`
- prototype: `__int64 __fastcall(HINF InfHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007b70`
- `0x180007cec`

## callees

- `0x18000734c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007384`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x18000737a`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x18000737a`

## pseudocode

```c
__int64 __fastcall ApplyInfSection(HINF InfHandle, HKEY a2, const WCHAR *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !SetupInstallFromInfSectionW(0, InfHandle, a3, 4u, a2, 0, 0, 0, 0, 0, 0) )
    return GetLastError();
  return v3;
}

```

## disassembly

```asm
0x18000734c  mov     rax, rsp
0x18000734f  push    rbx
0x180007350  sub     rsp, 60h
0x180007354  xor     ebx, ebx
0x180007356  mov     [rax-18h], rbx
0x18000735a  mov     [rax-20h], rbx
0x18000735e  mov     [rax-28h], rbx
0x180007362  mov     [rax-30h], rbx
0x180007366  lea     r9d, [rbx+4]; Flags
0x18000736a  mov     [rax-38h], ebx
0x18000736d  mov     [rax-40h], rbx
0x180007371  mov     [rax-48h], rdx
0x180007375  mov     rdx, rcx; InfHandle
0x180007378  xor     ecx, ecx; Owner
0x18000737a  call    cs:__imp_SetupInstallFromInfSectionW
0x180007380  test    eax, eax
0x180007382  jnz     short loc_18000738C
0x180007384  call    cs:__imp_GetLastError
0x18000738a  mov     ebx, eax
0x18000738c  mov     eax, ebx
0x18000738e  add     rsp, 60h
0x180007392  pop     rbx
0x180007393  retn
```
