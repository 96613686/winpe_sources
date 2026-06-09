# GetRealStrongNameDll(HINSTANCE__ * *)

- ea: `0x18002a2e4`
- end: `0x18002a3b0`
- name: `?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `26`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026e10`
- `0x180026f60`
- `0x1800271b0`
- `0x180027300`
- `0x180027590`
- `0x1800276c0`
- `0x1800277f0`
- `0x180027a70`
- `0x180027ea0`
- `0x180027ff0`
- `0x180028140`
- `0x180028290`
- `0x1800283e0`
- `0x18002bf5c`
- `0x18002d910`
- `0x18002d9ac`
- `0x18002da48`
- `0x18002daf8`
- `0x18002db94`
- `0x18002dc30`
- `0x18002eaf4`
- `0x18002eb90`
- `0x18002ec28`
- `0x18002ecdc`
- `0x18002eda8`
- `0x18002ee44`

## callees

- `0x18002a120`
- `0x18002a2e4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002a33c`
- `KERNEL32!GetProcAddress` at `0x18002a33c`
- `KERNEL32!FreeLibrary` at `0x18002a34a`
- `KERNEL32!FreeLibrary` at `0x18002a34a`
- `KERNEL32!LoadLibraryExW` at `0x18002a324`
- `KERNEL32!LoadLibraryExW` at `0x18002a379`
- `KERNEL32!LoadLibraryExW` at `0x18002a324`
- `KERNEL32!LoadLibraryExW` at `0x18002a379`

## pseudocode

```c
__int64 __fastcall GetRealStrongNameDll(HINSTANCE *a1)
{
  __int64 result; // rax
  int QualifiedStrongName; // ebx
  HMODULE Library; // rax
  HMODULE v5; // rax

  if ( g_hStrongNameMod )
  {
    *a1 = g_hStrongNameMod;
    return 0;
  }
  QualifiedStrongName = GetQualifiedStrongName(0);
  if ( QualifiedStrongName < 0 )
    return (unsigned int)QualifiedStrongName;
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  *a1 = Library;
  if ( Library )
  {
    if ( !GetProcAddress(Library, "StrongNameErrorInfo") )
    {
      FreeLibrary(*a1);
      *a1 = 0;
    }
  }
  if ( *a1 )
  {
    g_hStrongNameMod = *a1;
LABEL_12:
    _InterlockedIncrement((volatile signed __int32 *)&g_numStrongNameLoaded);
    return (unsigned int)QualifiedStrongName;
  }
  result = GetQualifiedStrongName(1);
  QualifiedStrongName = result;
  if ( (int)result < 0 )
    return result;
  v5 = LoadLibraryExW(qword_180061D70, 0, 0);
  *a1 = v5;
  g_hStrongNameMod = v5;
  if ( v5 )
    goto LABEL_12;
  return (unsigned int)-2146232573;
}

```

## disassembly

```asm
0x18002a2e4  mov     [rsp+arg_0], rbx
0x18002a2e9  push    rdi
0x18002a2ea  sub     rsp, 20h
0x18002a2ee  mov     rax, cs:?g_hStrongNameMod@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hStrongNameMod
0x18002a2f5  mov     rdi, rcx
0x18002a2f8  test    rax, rax
0x18002a2fb  jz      short loc_18002A307
0x18002a2fd  mov     [rcx], rax
0x18002a300  xor     eax, eax
0x18002a302  jmp     loc_18002A3A5
0x18002a307  xor     ecx, ecx; int
0x18002a309  call    ?GetQualifiedStrongName@@YAJH@Z; GetQualifiedStrongName(int)
0x18002a30e  mov     ebx, eax
0x18002a310  test    eax, eax
0x18002a312  js      loc_18002A3A3
0x18002a318  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18002a31f  xor     r8d, r8d; dwFlags
0x18002a322  xor     edx, edx; hFile
0x18002a324  call    cs:__imp_LoadLibraryExW
0x18002a32a  mov     [rdi], rax
0x18002a32d  test    rax, rax
0x18002a330  jz      short loc_18002A357
0x18002a332  lea     rdx, aStrongnameerro_1; "StrongNameErrorInfo"
0x18002a339  mov     rcx, rax; hModule
0x18002a33c  call    cs:__imp_GetProcAddress
0x18002a342  test    rax, rax
0x18002a345  jnz     short loc_18002A357
0x18002a347  mov     rcx, [rdi]; hLibModule
0x18002a34a  call    cs:__imp_FreeLibrary
0x18002a350  mov     qword ptr [rdi], 0
0x18002a357  mov     rax, [rdi]
0x18002a35a  test    rax, rax
0x18002a35d  jnz     short loc_18002A395
0x18002a35f  lea     ecx, [rax+1]; int
0x18002a362  call    ?GetQualifiedStrongName@@YAJH@Z; GetQualifiedStrongName(int)
0x18002a367  mov     ebx, eax
0x18002a369  test    eax, eax
0x18002a36b  js      short loc_18002A3A5
0x18002a36d  mov     rcx, cs:qword_180061D70; lpLibFileName
0x18002a374  xor     r8d, r8d; dwFlags
0x18002a377  xor     edx, edx; hFile
0x18002a379  call    cs:__imp_LoadLibraryExW
0x18002a37f  mov     [rdi], rax
0x18002a382  mov     cs:?g_hStrongNameMod@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hStrongNameMod
0x18002a389  test    rax, rax
0x18002a38c  jnz     short loc_18002A39C
0x18002a38e  mov     ebx, 80131703h
0x18002a393  jmp     short loc_18002A3A3
0x18002a395  mov     cs:?g_hStrongNameMod@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hStrongNameMod
0x18002a39c  lock inc cs:?g_numStrongNameLoaded@@3KA; ulong g_numStrongNameLoaded
0x18002a3a3  mov     eax, ebx
0x18002a3a5  mov     rbx, [rsp+28h+arg_0]
0x18002a3aa  add     rsp, 20h
0x18002a3ae  pop     rdi
0x18002a3af  retn
```
