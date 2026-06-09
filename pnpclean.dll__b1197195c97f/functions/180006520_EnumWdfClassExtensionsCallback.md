# EnumWdfClassExtensionsCallback

- ea: `0x180006520`
- end: `0x18000663c`
- name: `EnumWdfClassExtensionsCallback`
- size: `284`
- prototype: `_BOOL8 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006520`

## import_xrefs

- `msvcrt!wcschr` at `0x1800065d1`
- `msvcrt!wcschr` at `0x1800065d1`
- `msvcrt!_wcsnicmp` at `0x1800065f2`
- `msvcrt!_wcsnicmp` at `0x1800065f2`
- `msvcrt!_wtoi` at `0x180006600`
- `msvcrt!_wtoi` at `0x180006600`
- `msvcrt!_wcsicmp` at `0x180006563`
- `msvcrt!_wcsicmp` at `0x180006563`
- `KERNEL32!CompareStringW` at `0x1800065ac`
- `KERNEL32!CompareStringW` at `0x1800065ac`

## string_xrefs

- `0x18000655c`: `WdfExtensions`
- `0x18000659a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services`

## pseudocode

```c
_BOOL8 __fastcall EnumWdfClassExtensionsCallback(__int64 a1, __int64 a2, _DWORD *a3)
{
  const wchar_t *v5; // rcx
  const WCHAR *v6; // rdi
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  const wchar_t *i; // rbx
  __int64 v10; // rax

  if ( *(_DWORD *)(a2 + 48) == 7 )
  {
    if ( *(_QWORD *)(a2 + 56) )
    {
      if ( *(_QWORD *)(a2 + 24) )
      {
        v5 = *(const wchar_t **)(a2 + 40);
        if ( v5 )
        {
          if ( !_wcsicmp(v5, L"WdfExtensions") )
          {
            v6 = *(const WCHAR **)(a2 + 24);
            v7 = -1;
            do
              ++v7;
            while ( v6[v7] );
            if ( (unsigned int)v7 >= 0x3A
              && CompareStringW(
                   0x7Fu,
                   1u,
                   v6,
                   58,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WUDF\\Services",
                   58) == 2 )
            {
              v8 = v6 + 58;
              if ( v6[58] )
              {
                if ( *v8 != 92 )
                  return *a3 == 0;
                v8 = v6 + 59;
              }
              if ( v8 && !wcschr(v8, 0x5Cu) )
              {
                for ( i = *(const wchar_t **)(a2 + 56); *i; i += v10 + 1 )
                {
                  if ( !_wcsnicmp(i, L"IddCx", 5u) && _wtoi(i + 5) )
                  {
                    *a3 = 1;
                    return *a3 == 0;
                  }
                  v10 = -1;
                  do
                    ++v10;
                  while ( i[v10] );
                }
              }
            }
          }
        }
      }
    }
  }
  return *a3 == 0;
}

```

## disassembly

```asm
0x180006520  push    rbx
0x180006522  push    rbp
0x180006523  push    rsi
0x180006524  push    rdi
0x180006525  sub     rsp, 38h
0x180006529  xor     ebp, ebp
0x18000652b  mov     rsi, r8
0x18000652e  cmp     dword ptr [rdx+30h], 7
0x180006532  mov     rbx, rdx
0x180006535  jnz     loc_18000662C
0x18000653b  cmp     [rdx+38h], rbp
0x18000653f  jz      loc_18000662C
0x180006545  cmp     [rdx+18h], rbp
0x180006549  jz      loc_18000662C
0x18000654f  mov     rcx, [rdx+28h]; String1
0x180006553  test    rcx, rcx
0x180006556  jz      loc_18000662C
0x18000655c  lea     rdx, aWdfextensions; "WdfExtensions"
0x180006563  call    cs:__imp__wcsicmp
0x180006569  test    eax, eax
0x18000656b  jnz     loc_18000662C
0x180006571  mov     rdi, [rbx+18h]
0x180006575  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006579  inc     rax
0x18000657c  cmp     [rdi+rax*2], bp
0x180006580  jnz     short loc_180006579
0x180006582  mov     r9d, 3Ah ; ':'; cchCount1
0x180006588  cmp     eax, r9d
0x18000658b  jb      loc_18000662C
0x180006591  lea     edx, [r9-39h]; dwCmpFlags
0x180006595  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x18000659a  lea     rax, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800065a1  mov     r8, rdi; lpString1
0x1800065a4  lea     ecx, [rdx+7Eh]; Locale
0x1800065a7  mov     [rsp+58h+lpString2], rax; lpString2
0x1800065ac  call    cs:__imp_CompareStringW
0x1800065b2  cmp     eax, 2
0x1800065b5  jnz     short loc_18000662C
0x1800065b7  lea     rcx, [rdi+74h]
0x1800065bb  lea     edx, [rax+5Ah]; Ch
0x1800065be  cmp     [rcx], bp
0x1800065c1  jz      short loc_1800065CC
0x1800065c3  cmp     [rcx], dx
0x1800065c6  jnz     short loc_18000662C
0x1800065c8  add     rcx, 2; Str
0x1800065cc  test    rcx, rcx
0x1800065cf  jz      short loc_18000662C
0x1800065d1  call    cs:__imp_wcschr
0x1800065d7  test    rax, rax
0x1800065da  jnz     short loc_18000662C
0x1800065dc  mov     rbx, [rbx+38h]
0x1800065e0  jmp     short loc_18000661F
0x1800065e2  mov     r8d, 5; MaxCount
0x1800065e8  lea     rdx, aIddcx; "IddCx"
0x1800065ef  mov     rcx, rbx; String1
0x1800065f2  call    cs:__imp__wcsnicmp
0x1800065f8  test    eax, eax
0x1800065fa  jnz     short loc_18000660A
0x1800065fc  lea     rcx, [rbx+0Ah]; String
0x180006600  call    cs:__imp__wtoi
0x180006606  test    eax, eax
0x180006608  jnz     short loc_180006626
0x18000660a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000660e  inc     rax
0x180006611  cmp     [rbx+rax*2], bp
0x180006615  jnz     short loc_18000660E
0x180006617  lea     rbx, [rbx+rax*2]
0x18000661b  add     rbx, 2
0x18000661f  cmp     [rbx], bp
0x180006622  jnz     short loc_1800065E2
0x180006624  jmp     short loc_18000662C
0x180006626  mov     dword ptr [rsi], 1
0x18000662c  cmp     [rsi], ebp
0x18000662e  mov     eax, ebp
0x180006630  setz    al
0x180006633  add     rsp, 38h
0x180006637  pop     rdi
0x180006638  pop     rsi
0x180006639  pop     rbp
0x18000663a  pop     rbx
0x18000663b  retn
```
