# PathCchIsRoot

- ea: `0x1400105d8`
- end: `0x140010703`
- name: `PathCchIsRoot`
- size: `299`
- prototype: `BOOL __stdcall(PCWSTR pszPath)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140008f78`
- `0x140009900`
- `0x14001070c`

## callees

- `0x14000f9b4`
- `0x14000fa50`
- `0x1400100b8`
- `0x1400105d8`
- `0x140010992`

## import_xrefs

- `msvcrt!iswalpha` at `0x140010606`
- `msvcrt!iswalpha` at `0x1400106a6`
- `msvcrt!iswalpha` at `0x140010606`
- `msvcrt!iswalpha` at `0x1400106a6`

## pseudocode

```c
BOOL __stdcall PathCchIsRoot(PCWSTR pszPath)
{
  WCHAR v2; // cx
  _WORD *v3; // rax
  __int16 v4; // cx
  int v5; // edx

  if ( pszPath )
  {
    v2 = *pszPath;
    if ( v2 )
    {
      if ( iswalpha(v2) && StrIsEqualCaseInsensitive(pszPath + 1, L":\\", 3) || *pszPath == 92 && !pszPath[1] )
        return 1;
      if ( (unsigned int)PathIsUnc2((unsigned __int16 *)pszPath) )
      {
        v3 = 0;
        v4 = MEMORY[0];
        if ( MEMORY[0] )
        {
          v5 = 0;
          while ( v4 != 92 || ++v5 <= 1 && v3[1] )
          {
            v4 = *++v3;
            if ( !*v3 )
              return 1;
          }
          return 0;
        }
        return 1;
      }
      if ( !wcsncmp_0(pszPath, L"\\\\?\\", 4u)
        && iswalpha(pszPath[4])
        && StrIsEqualCaseInsensitive(pszPath + 5, L":\\", 3)
        || PathIsVolumeGUIDWorker(pszPath) && pszPath[48] == 92 && !pszPath[49] )
      {
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400105d8  mov     [rsp+arg_8], rbx
0x1400105dd  mov     [rsp+arg_10], rsi
0x1400105e2  push    rdi
0x1400105e3  sub     rsp, 20h
0x1400105e7  xor     esi, esi
0x1400105e9  mov     rbx, rcx
0x1400105ec  mov     [rsp+28h+arg_0], rsi
0x1400105f1  test    rcx, rcx
0x1400105f4  jz      loc_1400106F0
0x1400105fa  movzx   ecx, word ptr [rcx]; C
0x1400105fd  test    cx, cx
0x140010600  jz      loc_1400106F0
0x140010606  call    cs:__imp_iswalpha
0x14001060d  nop     dword ptr [rax+rax+00h]
0x140010612  lea     rdi, [rbx+2]
0x140010616  test    eax, eax
0x140010618  jz      short loc_140010635
0x14001061a  lea     r8d, [rsi+3]; int
0x14001061e  mov     rcx, rdi; unsigned __int16 *
0x140010621  lea     rdx, asc_140013984; ":\\"
0x140010628  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x14001062d  test    al, al
0x14001062f  jnz     loc_1400106E9
0x140010635  cmp     word ptr [rbx], 5Ch ; '\'
0x140010639  jnz     short loc_140010644
0x14001063b  cmp     [rdi], si
0x14001063e  jz      loc_1400106E9
0x140010644  lea     rdx, [rsp+28h+arg_0]
0x140010649  mov     rcx, rbx; unsigned __int16 *
0x14001064c  call    PathIsUnc2
0x140010651  test    eax, eax
0x140010653  jz      short loc_140010689
0x140010655  mov     rax, [rsp+28h+arg_0]
0x14001065a  movzx   ecx, word ptr [rax]
0x14001065d  test    cx, cx
0x140010660  jz      loc_1400106E9
0x140010666  mov     edx, esi
0x140010668  cmp     cx, 5Ch ; '\'
0x14001066c  jnz     short loc_14001067B
0x14001066e  inc     edx
0x140010670  cmp     edx, 1
0x140010673  jg      short loc_1400106F0
0x140010675  cmp     [rax+2], si
0x140010679  jz      short loc_1400106F0
0x14001067b  add     rax, 2
0x14001067f  movzx   ecx, word ptr [rax]
0x140010682  test    cx, cx
0x140010685  jnz     short loc_140010668
0x140010687  jmp     short loc_1400106E9
0x140010689  mov     r8d, 4; MaxCount
0x14001068f  lea     rdx, asc_140013A28; "\\\\?\\"
0x140010696  mov     rcx, rbx; String1
0x140010699  call    wcsncmp_0
0x14001069e  test    eax, eax
0x1400106a0  jnz     short loc_1400106D0
0x1400106a2  movzx   ecx, word ptr [rbx+8]; C
0x1400106a6  call    cs:__imp_iswalpha
0x1400106ad  nop     dword ptr [rax+rax+00h]
0x1400106b2  test    eax, eax
0x1400106b4  jz      short loc_1400106D0
0x1400106b6  lea     rcx, [rbx+0Ah]; unsigned __int16 *
0x1400106ba  mov     r8d, 3; int
0x1400106c0  lea     rdx, asc_140013984; ":\\"
0x1400106c7  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x1400106cc  test    al, al
0x1400106ce  jnz     short loc_1400106E9
0x1400106d0  mov     rcx, rbx; unsigned __int16 *
0x1400106d3  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x1400106d8  test    al, al
0x1400106da  jz      short loc_1400106F0
0x1400106dc  cmp     word ptr [rbx+60h], 5Ch ; '\'
0x1400106e1  jnz     short loc_1400106F0
0x1400106e3  cmp     [rbx+62h], si
0x1400106e7  jnz     short loc_1400106F0
0x1400106e9  mov     eax, 1
0x1400106ee  jmp     short loc_1400106F2
0x1400106f0  xor     eax, eax
0x1400106f2  mov     rbx, [rsp+28h+arg_8]
0x1400106f7  mov     rsi, [rsp+28h+arg_10]
0x1400106fc  add     rsp, 20h
0x140010700  pop     rdi
0x140010701  retn
```
