# BuildMsdadiagFullPath

- ea: `0x1800195fc`
- end: `0x180019659`
- name: `BuildMsdadiagFullPath`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019408`
- `0x1800198f4`

## callees

- `0x1800028e8`
- `0x1800195fc`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180019610`
- `KERNEL32!GetSystemDirectoryW` at `0x180019610`

## string_xrefs

- `0x180019634`: `\msdadiag.dll`

## pseudocode

```c
_BOOL8 __fastcall BuildMsdadiagFullPath(WCHAR *a1)
{
  __int64 SystemDirectoryW; // rdx

  SystemDirectoryW = GetSystemDirectoryW(a1, 0x10Eu);
  return (unsigned __int64)(SystemDirectoryW - 1) <= 0x10C
      && (int)StringCchCopyW(&a1[SystemDirectoryW], 270 - SystemDirectoryW, L"\\msdadiag.dll") >= 0;
}

```

## disassembly

```asm
0x1800195fc  mov     [rsp+arg_0], rbx
0x180019601  push    rdi
0x180019602  sub     rsp, 20h
0x180019606  mov     ebx, 10Eh
0x18001960b  mov     rdi, rcx
0x18001960e  mov     edx, ebx; uSize
0x180019610  call    cs:__imp_GetSystemDirectoryW
0x180019617  nop     dword ptr [rax+rax+00h]
0x18001961c  mov     edx, eax
0x18001961e  lea     rax, [rdx-1]
0x180019622  cmp     rax, 10Ch
0x180019628  ja      short loc_18001964B
0x18001962a  sub     rbx, rdx
0x18001962d  lea     rcx, [rdi+rdx*2]; unsigned __int16 *
0x180019631  mov     rdx, rbx; unsigned __int64
0x180019634  lea     r8, aMsdadiagDll_0; "\\msdadiag.dll"
0x18001963b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019640  test    eax, eax
0x180019642  js      short loc_18001964B
0x180019644  mov     eax, 1
0x180019649  jmp     short loc_18001964D
0x18001964b  xor     eax, eax
0x18001964d  mov     rbx, [rsp+28h+arg_0]
0x180019652  add     rsp, 20h
0x180019656  pop     rdi
0x180019657  retn
```
