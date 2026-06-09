# CPRegDeleteKey

- ea: `0x1800137e4`
- end: `0x1800138dd`
- name: `CPRegDeleteKey`
- size: `249`
- prototype: `LSTATUS __fastcall(HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800137e4`
- `0x180013fa8`

## callees

- `0x180002940`
- `0x1800137e4`

## import_xrefs

- `msvcrt!calloc` at `0x180013839`
- `msvcrt!calloc` at `0x180013839`
- `ADVAPI32!RegCloseKey` at `0x18001384c`
- `ADVAPI32!RegCloseKey` at `0x1800138bb`
- `ADVAPI32!RegCloseKey` at `0x18001384c`
- `ADVAPI32!RegCloseKey` at `0x1800138bb`
- `ADVAPI32!RegEnumKeyExW` at `0x180013893`
- `ADVAPI32!RegEnumKeyExW` at `0x180013893`
- `ADVAPI32!RegOpenKeyExW` at `0x180013823`
- `ADVAPI32!RegOpenKeyExW` at `0x180013823`
- `ADVAPI32!RegDeleteKeyW` at `0x1800138c7`
- `ADVAPI32!RegDeleteKeyW` at `0x1800138c7`

## pseudocode

```c
LSTATUS __fastcall CPRegDeleteKey(HKEY a1, const WCHAR *a2)
{
  LSTATUS result; // eax
  WCHAR *v5; // rbx
  struct _FILETIME ftLastWriteTime; // [rsp+40h] [rbp-18h] BYREF
  DWORD cchName; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    v5 = (WCHAR *)calloc(0x21Cu, 1u);
    if ( v5 )
    {
      do
        cchName = 270;
      while ( !RegEnumKeyExW(hKey, 0, v5, &cchName, 0, 0, 0, &ftLastWriteTime)
           && !(unsigned int)CPRegDeleteKey(hKey, v5) );
      OFree(v5);
      RegCloseKey(hKey);
      return RegDeleteKeyW(a1, a2);
    }
    else
    {
      RegCloseKey(hKey);
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800137e4  mov     rax, rsp
0x1800137e7  mov     [rax+8], rbx
0x1800137eb  mov     [rax+10h], rsi
0x1800137ef  push    rdi
0x1800137f0  sub     rsp, 50h
0x1800137f4  mov     qword ptr [rax+20h], 0
0x1800137fc  mov     r9d, 2001Fh; samDesired
0x180013802  mov     dword ptr [rax+18h], 0
0x180013809  xor     r8d, r8d; ulOptions
0x18001380c  mov     qword ptr [rax-18h], 0
0x180013814  lea     rax, [rax+20h]
0x180013818  mov     [rsp+58h+phkResult], rax; phkResult
0x18001381d  mov     rdi, rdx
0x180013820  mov     rsi, rcx
0x180013823  call    cs:__imp_RegOpenKeyExW
0x180013829  test    eax, eax
0x18001382b  jnz     loc_1800138CD
0x180013831  lea     edx, [rax+1]; Size
0x180013834  mov     ecx, 21Ch; Count
0x180013839  call    cs:__imp_calloc
0x18001383f  mov     rbx, rax
0x180013842  test    rax, rax
0x180013845  jnz     short loc_180013857
0x180013847  mov     rcx, [rsp+58h+hKey]; hKey
0x18001384c  call    cs:__imp_RegCloseKey
0x180013852  lea     eax, [rbx+8]
0x180013855  jmp     short loc_1800138CD
0x180013857  mov     rcx, [rsp+58h+hKey]; hKey
0x18001385c  lea     rax, [rsp+58h+ftLastWriteTime]
0x180013861  mov     [rsp+58h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180013866  lea     r9, [rsp+58h+cchName]; lpcchName
0x18001386b  mov     [rsp+58h+lpcchClass], 0; lpcchClass
0x180013874  mov     r8, rbx; lpName
0x180013877  mov     [rsp+58h+lpClass], 0; lpClass
0x180013880  xor     edx, edx; dwIndex
0x180013882  mov     [rsp+58h+phkResult], 0; lpReserved
0x18001388b  mov     [rsp+58h+cchName], 10Eh
0x180013893  call    cs:__imp_RegEnumKeyExW
0x180013899  test    eax, eax
0x18001389b  jnz     short loc_1800138AE
0x18001389d  mov     rcx, [rsp+58h+hKey]
0x1800138a2  mov     rdx, rbx
0x1800138a5  call    CPRegDeleteKey
0x1800138aa  test    eax, eax
0x1800138ac  jz      short loc_180013857
0x1800138ae  mov     rcx, rbx
0x1800138b1  call    OFree
0x1800138b6  mov     rcx, [rsp+58h+hKey]; hKey
0x1800138bb  call    cs:__imp_RegCloseKey
0x1800138c1  mov     rdx, rdi; lpSubKey
0x1800138c4  mov     rcx, rsi; hKey
0x1800138c7  call    cs:__imp_RegDeleteKeyW
0x1800138cd  mov     rbx, [rsp+58h+arg_0]
0x1800138d2  mov     rsi, [rsp+58h+arg_8]
0x1800138d7  add     rsp, 50h
0x1800138db  pop     rdi
0x1800138dc  retn
```
