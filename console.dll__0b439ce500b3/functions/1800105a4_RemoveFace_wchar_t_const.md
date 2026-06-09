# RemoveFace(wchar_t const *)

- ea: `0x1800105a4`
- end: `0x18001067a`
- name: `?RemoveFace@@YAXPEB_W@Z`
- size: `214`
- prototype: `void __fastcall(LPCWSTR lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fbdc`

## callees

- `0x1800105a4`
- `0x180018d18`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800105de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800105de`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800105f9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800105f9`

## pseudocode

```c
void __fastcall RemoveFace(LPCWSTR lpString2)
{
  unsigned int v1; // edi
  int v2; // esi
  __int64 v3; // rbp
  LPCWSTR *v5; // r14
  unsigned int v6; // edi

  v1 = NumberOfFonts;
  v2 = 0;
  v3 = 0;
  if ( NumberOfFonts )
  {
    v5 = (LPCWSTR *)FontInfo;
    do
    {
      if ( lstrcmpW(v5[5 * v3 + 3], lpString2) )
      {
        v5 = (LPCWSTR *)FontInfo;
        if ( v2 > 0 )
        {
          v6 = NumberOfFonts;
          memmove_0(
            (char *)FontInfo + 40 * (unsigned int)(v3 - v2),
            (char *)FontInfo + 40 * v3,
            40LL * (NumberOfFonts - (unsigned int)v3));
          v1 = v6 - v2;
          LODWORD(v3) = v3 - v2;
          NumberOfFonts = v1;
          v2 = 0;
          goto LABEL_6;
        }
      }
      else
      {
        DeleteObject(*((HGDIOBJ *)FontInfo + 5 * v3));
        v5 = (LPCWSTR *)FontInfo;
        ++v2;
        *((_QWORD *)FontInfo + 5 * v3) = 0;
      }
      v1 = NumberOfFonts;
LABEL_6:
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < v1 );
  }
  NumberOfFonts = v1 - v2;
}

```

## disassembly

```asm
0x1800105a4  push    rbx
0x1800105a6  push    rbp
0x1800105a7  push    rsi
0x1800105a8  push    rdi
0x1800105a9  push    r12
0x1800105ab  push    r14
0x1800105ad  push    r15
0x1800105af  sub     rsp, 20h
0x1800105b3  mov     edi, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x1800105b9  xor     esi, esi
0x1800105bb  xor     ebp, ebp
0x1800105bd  mov     r12, rcx
0x1800105c0  test    edi, edi
0x1800105c2  jz      short loc_180010622
0x1800105c4  mov     r14, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x1800105cb  lea     r15, ds:0[rbp*4]
0x1800105d3  mov     rdx, r12; lpString2
0x1800105d6  add     r15, rbp
0x1800105d9  mov     rcx, [r14+r15*8+18h]; lpString1
0x1800105de  call    cs:__imp_lstrcmpW
0x1800105e5  nop     dword ptr [rax+rax+00h]
0x1800105ea  test    eax, eax
0x1800105ec  jnz     short loc_18001063A
0x1800105ee  mov     rcx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x1800105f5  mov     rcx, [rcx+r15*8]; ho
0x1800105f9  call    cs:__imp_DeleteObject
0x180010600  nop     dword ptr [rax+rax+00h]
0x180010605  mov     r14, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18001060c  inc     esi
0x18001060e  mov     qword ptr [r14+r15*8], 0
0x180010616  mov     edi, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18001061c  inc     ebp
0x18001061e  cmp     ebp, edi
0x180010620  jb      short loc_1800105CB
0x180010622  sub     edi, esi
0x180010624  mov     cs:?NumberOfFonts@@3KA, edi; ulong NumberOfFonts
0x18001062a  add     rsp, 20h
0x18001062e  pop     r15
0x180010630  pop     r14
0x180010632  pop     r12
0x180010634  pop     rdi
0x180010635  pop     rsi
0x180010636  pop     rbp
0x180010637  pop     rbx
0x180010638  retn
0x18001063a  mov     r14, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180010641  test    esi, esi
0x180010643  jle     short loc_180010616
0x180010645  mov     edi, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18001064b  lea     rdx, [r14+r15*8]; Src
0x18001064f  mov     eax, edi
0x180010651  mov     ebx, ebp
0x180010653  sub     eax, ebp
0x180010655  sub     ebx, esi
0x180010657  lea     r8, [rax+rax*4]
0x18001065b  lea     rax, [rbx+rbx*4]
0x18001065f  shl     r8, 3; Size
0x180010663  lea     rcx, [r14+rax*8]; void *
0x180010667  call    memmove_0
0x18001066c  sub     edi, esi
0x18001066e  mov     ebp, ebx
0x180010670  mov     cs:?NumberOfFonts@@3KA, edi; ulong NumberOfFonts
0x180010676  xor     esi, esi
0x180010678  jmp     short loc_18001061C
```
