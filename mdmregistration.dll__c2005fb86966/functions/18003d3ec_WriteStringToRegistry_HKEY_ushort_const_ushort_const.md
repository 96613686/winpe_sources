# WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18003d3ec`
- end: `0x18003d4a8`
- name: `?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `188`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003ec40`

## callees

- `0x18003d3ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d474`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d474`

## pseudocode

```c
__int64 __fastcall WriteStringToRegistry(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)
{
  BYTE *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned __int64 v8; // rax
  unsigned __int64 cbData; // rcx
  LSTATUS v10; // eax

  if ( !lpData )
    return 0;
  v5 = lpData;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v5 )
      break;
    v5 += 2;
    --v6;
  }
  while ( v6 );
  v7 = v6 == 0 ? 0x80070057 : 0;
  if ( v6 )
  {
    v8 = (2 * (0x7FFFFFFF - v6)) & -(__int64)(v6 != 0);
    cbData = v8 + 2;
    if ( v8 + 2 < v8 || cbData > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v7 = 0;
      v10 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, cbData);
      if ( v10 )
      {
        if ( v10 > 0 )
          return (unsigned __int16)v10 | 0x80070000;
        else
          return (unsigned int)v10;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18003d3ec  mov     [rsp+arg_0], rbx
0x18003d3f1  push    rdi
0x18003d3f2  sub     rsp, 30h
0x18003d3f6  xor     edi, edi
0x18003d3f8  mov     r10, rdx
0x18003d3fb  mov     r11, rcx
0x18003d3fe  test    r8, r8
0x18003d401  jnz     short loc_18003D40A
0x18003d403  xor     eax, eax
0x18003d405  jmp     loc_18003D49C
0x18003d40a  mov     edx, 7FFFFFFFh
0x18003d40f  mov     rax, r8
0x18003d412  mov     ecx, edx
0x18003d414  cmp     [rax], di
0x18003d417  jz      short loc_18003D423
0x18003d419  add     rax, 2
0x18003d41d  sub     rcx, 1
0x18003d421  jnz     short loc_18003D414
0x18003d423  mov     rax, rcx
0x18003d426  neg     rax
0x18003d429  sbb     ebx, ebx
0x18003d42b  not     ebx
0x18003d42d  and     ebx, 80070057h
0x18003d433  test    rcx, rcx
0x18003d436  jz      short loc_18003D49A
0x18003d438  sub     rdx, rcx
0x18003d43b  add     rdx, rdx
0x18003d43e  neg     rcx
0x18003d441  sbb     rax, rax
0x18003d444  and     rax, rdx
0x18003d447  lea     rcx, [rax+2]
0x18003d44b  cmp     rcx, rax
0x18003d44e  jb      short loc_18003D495
0x18003d450  mov     eax, 0FFFFFFFFh
0x18003d455  cmp     rcx, rax
0x18003d458  ja      short loc_18003D495
0x18003d45a  mov     [rsp+38h+cbData], ecx; cbData
0x18003d45e  mov     r9d, 1; dwType
0x18003d464  mov     [rsp+38h+lpData], r8; lpData
0x18003d469  mov     rdx, r10; lpValueName
0x18003d46c  xor     r8d, r8d; Reserved
0x18003d46f  mov     rcx, r11; hKey
0x18003d472  mov     ebx, edi
0x18003d474  call    cs:__imp_RegSetValueExW
0x18003d47b  nop     dword ptr [rax+rax+00h]
0x18003d480  test    eax, eax
0x18003d482  jz      short loc_18003D49A
0x18003d484  jg      short loc_18003D48A
0x18003d486  mov     ebx, eax
0x18003d488  jmp     short loc_18003D49A
0x18003d48a  movzx   ebx, ax
0x18003d48d  or      ebx, 80070000h
0x18003d493  jmp     short loc_18003D49A
0x18003d495  mov     ebx, 80070216h
0x18003d49a  mov     eax, ebx
0x18003d49c  mov     rbx, [rsp+38h+arg_0]
0x18003d4a1  add     rsp, 30h
0x18003d4a5  pop     rdi
0x18003d4a6  retn
```
