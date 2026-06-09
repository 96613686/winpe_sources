# Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(void)

- ea: `0x1800193a0`
- end: `0x1800193fd`
- name: `??B?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAPEAUHINSTANCE__@@XZ`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001934c`

## callees

- `0x1800193a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800193bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800193df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800193bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800193df`

## pseudocode

```c
HMODULE __fastcall Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(
        __int64 a1)
{
  HMODULE result; // rax
  const WCHAR *v3; // rcx

  if ( *(_BYTE *)(a1 + 24) )
    return *(HMODULE *)a1;
  result = LoadLibraryExW(*(LPCWSTR *)(a1 + 8), 0, 0);
  *(_QWORD *)a1 = result;
  if ( !result )
  {
    v3 = *(const WCHAR **)(a1 + 16);
    if ( v3 )
    {
      result = LoadLibraryExW(v3, 0, 0);
      *(_QWORD *)a1 = result;
    }
    else
    {
      result = 0;
    }
  }
  *(_BYTE *)(a1 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x1800193a0  push    rbx
0x1800193a2  sub     rsp, 20h
0x1800193a6  cmp     byte ptr [rcx+18h], 0
0x1800193aa  mov     rbx, rcx
0x1800193ad  jz      short loc_1800193B4
0x1800193af  mov     rax, [rcx]
0x1800193b2  jmp     short loc_1800193F6
0x1800193b4  mov     rcx, [rcx+8]; lpLibFileName
0x1800193b8  xor     r8d, r8d; dwFlags
0x1800193bb  xor     edx, edx; hFile
0x1800193bd  call    cs:__imp_LoadLibraryExW
0x1800193c4  nop     dword ptr [rax+rax+00h]
0x1800193c9  mov     [rbx], rax
0x1800193cc  test    rax, rax
0x1800193cf  jnz     short loc_1800193F2
0x1800193d1  mov     rcx, [rbx+10h]; lpLibFileName
0x1800193d5  test    rcx, rcx
0x1800193d8  jz      short loc_1800193F0
0x1800193da  xor     r8d, r8d; dwFlags
0x1800193dd  xor     edx, edx; hFile
0x1800193df  call    cs:__imp_LoadLibraryExW
0x1800193e6  nop     dword ptr [rax+rax+00h]
0x1800193eb  mov     [rbx], rax
0x1800193ee  jmp     short loc_1800193F2
0x1800193f0  xor     eax, eax
0x1800193f2  mov     byte ptr [rbx+18h], 1
0x1800193f6  add     rsp, 20h
0x1800193fa  pop     rbx
0x1800193fb  retn
```
