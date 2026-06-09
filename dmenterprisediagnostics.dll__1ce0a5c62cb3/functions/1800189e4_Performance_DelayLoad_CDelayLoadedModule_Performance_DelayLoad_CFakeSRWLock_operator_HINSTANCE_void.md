# Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(void)

- ea: `0x1800189e4`
- end: `0x180018a34`
- name: `??B?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAPEAUHINSTANCE__@@XZ`
- size: `80`
- prototype: `HMODULE __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018998`

## callees

- `0x1800189e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018a01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018a1d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018a01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018a1d`

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
0x1800189e4  push    rbx
0x1800189e6  sub     rsp, 20h
0x1800189ea  cmp     byte ptr [rcx+18h], 0
0x1800189ee  mov     rbx, rcx
0x1800189f1  jz      short loc_1800189F8
0x1800189f3  mov     rax, [rcx]
0x1800189f6  jmp     short loc_180018A2E
0x1800189f8  mov     rcx, [rcx+8]; lpLibFileName
0x1800189fc  xor     r8d, r8d; dwFlags
0x1800189ff  xor     edx, edx; hFile
0x180018a01  call    cs:__imp_LoadLibraryExW
0x180018a07  mov     [rbx], rax
0x180018a0a  test    rax, rax
0x180018a0d  jnz     short loc_180018A2A
0x180018a0f  mov     rcx, [rbx+10h]; lpLibFileName
0x180018a13  test    rcx, rcx
0x180018a16  jz      short loc_180018A28
0x180018a18  xor     r8d, r8d; dwFlags
0x180018a1b  xor     edx, edx; hFile
0x180018a1d  call    cs:__imp_LoadLibraryExW
0x180018a23  mov     [rbx], rax
0x180018a26  jmp     short loc_180018A2A
0x180018a28  xor     eax, eax
0x180018a2a  mov     byte ptr [rbx+18h], 1
0x180018a2e  add     rsp, 20h
0x180018a32  pop     rbx
0x180018a33  retn
```
