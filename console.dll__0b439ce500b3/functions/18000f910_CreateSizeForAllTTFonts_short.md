# CreateSizeForAllTTFonts(short)

- ea: `0x18000f910`
- end: `0x18000f96a`
- name: `?CreateSizeForAllTTFonts@@YAXF@Z`
- size: `90`
- prototype: `void __fastcall(__int16)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008d68`
- `0x18000fbdc`

## callees

- `0x18000f910`
- `0x18000fa40`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000f921`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000f921`

## pseudocode

```c
void __fastcall CreateSizeForAllTTFonts(__int16 a1)
{
  HDC CompatibleDC; // rax
  wchar_t *v2; // rbx
  HDC v3; // rdi
  __int16 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  CompatibleDC = CreateCompatibleDC(0);
  v2 = (wchar_t *)gpFaceNames;
  v3 = CompatibleDC;
  while ( v2 )
  {
    if ( (v2[4] & 0x10) != 0 )
      DoFontEnum(v3, v2 + 6, &v4, 1);
    v2 = *(wchar_t **)v2;
  }
}

```

## disassembly

```asm
0x18000f910  mov     [rsp+arg_8], rbx
0x18000f915  mov     [rsp+arg_0], cx
0x18000f91a  push    rdi
0x18000f91b  sub     rsp, 20h
0x18000f91f  xor     ecx, ecx; hdc
0x18000f921  call    cs:__imp_CreateCompatibleDC
0x18000f928  nop     dword ptr [rax+rax+00h]
0x18000f92d  mov     rbx, cs:?gpFaceNames@@3PEAUtagFACENODE@@EA; tagFACENODE * gpFaceNames
0x18000f934  mov     rdi, rax
0x18000f937  jmp     short loc_18000F959
0x18000f939  test    byte ptr [rbx+8], 10h
0x18000f93d  jz      short loc_18000F956
0x18000f93f  lea     rdx, [rbx+0Ch]; wchar_t *
0x18000f943  mov     r9d, 1; unsigned int
0x18000f949  lea     r8, [rsp+28h+arg_0]; __int16 *
0x18000f94e  mov     rcx, rdi; hdc
0x18000f951  call    ?DoFontEnum@@YAHPEAUHDC__@@PEA_WPEAFI@Z; DoFontEnum(HDC__ *,wchar_t *,short *,uint)
0x18000f956  mov     rbx, [rbx]
0x18000f959  test    rbx, rbx
0x18000f95c  jnz     short loc_18000F939
0x18000f95e  mov     rbx, [rsp+28h+arg_8]
0x18000f963  add     rsp, 20h
0x18000f967  pop     rdi
0x18000f968  retn
```
