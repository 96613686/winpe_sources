# PowerHelperResolveRequesterReason

- ea: `0x180028dec`
- end: `0x180028ea6`
- name: `PowerHelperResolveRequesterReason`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180028554`

## callees

- `0x180028dec`
- `0x18003655c`

## import_xrefs

- `ntdll!RtlLoadString` at `0x180028e59`
- `ntdll!RtlLoadString` at `0x180028e59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028e20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028e20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028e90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028e90`

## pseudocode

```c
unsigned __int16 *__fastcall PowerHelperResolveRequesterReason(
        unsigned __int16 a1,
        const WCHAR *a2,
        unsigned int a3,
        struct _UNICODE_STRING *a4,
        int *a5)
{
  unsigned __int16 *v8; // rbx
  HMODULE Library; // rdi
  unsigned __int16 v11; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 *v12; // [rsp+48h] [rbp-40h] BYREF

  v12 = 0;
  v11 = 0;
  v8 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  if ( Library )
  {
    if ( (int)RtlLoadString(Library, a1, 0, 0, &v12, &v11, 0, 0) >= 0 && v11 )
      v8 = PowerHelperResolveRequestReason(v12, v11, a3, a4, a5);
    FreeLibrary(Library);
  }
  return v8;
}

```

## disassembly

```asm
0x180028dec  push    rbx
0x180028dee  push    rbp
0x180028def  push    rsi
0x180028df0  push    rdi
0x180028df1  push    r14
0x180028df3  push    r15
0x180028df5  sub     rsp, 58h
0x180028df9  xor     r15d, r15d
0x180028dfc  mov     r10, rdx
0x180028dff  mov     ebp, r8d
0x180028e02  mov     [rsp+88h+var_40], r15
0x180028e07  movzx   r14d, cx
0x180028e0b  mov     [rsp+88h+var_48], r15w
0x180028e11  xor     edx, edx; hFile
0x180028e13  mov     rcx, r10; lpLibFileName
0x180028e16  lea     r8d, [r15+2]; dwFlags
0x180028e1a  mov     rsi, r9
0x180028e1d  mov     ebx, r15d
0x180028e20  call    cs:__imp_LoadLibraryExW
0x180028e26  mov     rdi, rax
0x180028e29  test    rax, rax
0x180028e2c  jz      short loc_180028E96
0x180028e2e  mov     [rsp+88h+var_50], r15
0x180028e33  lea     rax, [rsp+88h+var_48]
0x180028e38  mov     [rsp+88h+var_58], r15
0x180028e3d  xor     r9d, r9d
0x180028e40  mov     [rsp+88h+var_60], rax
0x180028e45  xor     r8d, r8d
0x180028e48  lea     rax, [rsp+88h+var_40]
0x180028e4d  movzx   edx, r14w
0x180028e51  mov     rcx, rdi
0x180028e54  mov     [rsp+88h+var_68], rax
0x180028e59  call    cs:__imp_RtlLoadString
0x180028e5f  test    eax, eax
0x180028e61  js      short loc_180028E8D
0x180028e63  movzx   edx, [rsp+88h+var_48]; unsigned __int16
0x180028e68  test    dx, dx
0x180028e6b  jz      short loc_180028E8D
0x180028e6d  mov     rax, [rsp+88h+arg_20]
0x180028e75  mov     r9, rsi; struct _UNICODE_STRING *
0x180028e78  mov     rcx, [rsp+88h+var_40]; unsigned __int16 *
0x180028e7d  mov     r8d, ebp; unsigned int
0x180028e80  mov     [rsp+88h+var_68], rax; int *
0x180028e85  call    ?PowerHelperResolveRequestReason@@YAPEAGPEBGGKPEAU_UNICODE_STRING@@PEAH@Z; PowerHelperResolveRequestReason(ushort const *,ushort,ulong,_UNICODE_STRING *,int *)
0x180028e8a  mov     rbx, rax
0x180028e8d  mov     rcx, rdi; hLibModule
0x180028e90  call    cs:__imp_FreeLibrary
0x180028e96  mov     rax, rbx
0x180028e99  add     rsp, 58h
0x180028e9d  pop     r15
0x180028e9f  pop     r14
0x180028ea1  pop     rdi
0x180028ea2  pop     rsi
0x180028ea3  pop     rbp
0x180028ea4  pop     rbx
0x180028ea5  retn
```
