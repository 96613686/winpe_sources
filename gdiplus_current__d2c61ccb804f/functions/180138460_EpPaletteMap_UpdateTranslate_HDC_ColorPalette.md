# EpPaletteMap::UpdateTranslate(HDC__ *,ColorPalette * *)

- ea: `0x180138460`
- end: `0x1801386ce`
- name: `?UpdateTranslate@EpPaletteMap@@QEAAXPEAUHDC__@@PEAPEAUColorPalette@@@Z`
- size: `622`
- prototype: `void(EpPaletteMap *__hidden this, HDC, struct ColorPalette **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18002f6e0`
- `0x180138108`

## callees

- `0x180063cd8`
- `0x180105d40`
- `0x18010673c`
- `0x180138460`

## import_xrefs

- `GDI32!GetNearestPaletteIndex` at `0x180138627`
- `GDI32!GetNearestPaletteIndex` at `0x180138627`
- `GDI32!GetNearestColor` at `0x180138612`
- `GDI32!GetNearestColor` at `0x180138612`
- `GDI32!DeleteObject` at `0x180138697`
- `GDI32!DeleteObject` at `0x180138697`
- `GDI32!GetDeviceCaps` at `0x1801384c8`
- `GDI32!GetDeviceCaps` at `0x1801384de`
- `GDI32!GetDeviceCaps` at `0x1801384c8`
- `GDI32!GetDeviceCaps` at `0x1801384de`
- `GDI32!GetSystemPaletteEntries` at `0x180138518`
- `GDI32!GetSystemPaletteEntries` at `0x180138518`
- `GDI32!CreatePalette` at `0x180138529`
- `GDI32!CreatePalette` at `0x180138529`

## pseudocode

```c
void __fastcall EpPaletteMap::UpdateTranslate(EpPaletteMap *this, HDC a2, struct ColorPalette **a3)
{
  char DeviceCaps; // bl
  HPALETTE v7; // r13
  struct ColorPalette *v8; // rcx
  struct ColorPalette *v9; // rax
  int v10; // r8d
  __int64 v11; // rdx
  int v12; // edi
  char *v13; // rsi
  int v14; // r15d
  COLORREF v15; // ebx
  COLORREF NearestColor; // eax
  UINT NearestPaletteIndex; // eax
  LOGPALETTE plpal; // [rsp+30h] [rbp-D0h] BYREF

  *(_DWORD *)this = 1279869254;
  memset_0(&plpal.palNumEntries, 0, 0x406u);
  plpal.palVersion = 768;
  DeviceCaps = GetDeviceCaps(a2, 14);
  plpal.palNumEntries = 1 << (GetDeviceCaps(a2, 12) * DeviceCaps);
  if ( plpal.palNumEntries > 0x100u )
    plpal.palNumEntries = 256;
  GetSystemPaletteEntries(a2, 0, 0x100u, plpal.palPalEntry);
  v7 = CreatePalette(&plpal);
  if ( v7 )
  {
    if ( a3 )
    {
      v8 = *a3;
      if ( !*a3 )
      {
        v9 = (struct ColorPalette *)GpMallocEx(1036, 0);
        *a3 = v9;
        v8 = v9;
        if ( !v9 )
        {
LABEL_20:
          DeleteObject(v7);
          return;
        }
      }
      v10 = 0;
      *((_DWORD *)v8 + 1) = plpal.palNumEntries;
      if ( plpal.palNumEntries )
      {
        do
        {
          v11 = v10++;
          *((_DWORD *)*a3 + v11 + 2) = plpal.palPalEntry[v11].peBlue
                                     | ((plpal.palPalEntry[v11].peGreen
                                       | ((plpal.palPalEntry[v11].peRed | 0xFFFFFF00) << 8)) << 8);
        }
        while ( v10 < plpal.palNumEntries );
      }
    }
    memset_0((char *)this + 8, 0, 0x100u);
    v12 = 0;
    v13 = &byte_180189A74;
    v14 = 0;
    while ( v12 < 256 )
    {
      if ( (unsigned int)(v12 - 8) > 3 )
        v15 = (unsigned __int8)*v13 | ((unsigned __int8)v13[1] << 8) | (((unsigned __int8)v13[2] | 0x200) << 16);
      else
        v15 = dword_1801ADF50[v12] | 0x2000000;
      NearestColor = GetNearestColor(a2, v15);
      NearestPaletteIndex = GetNearestPaletteIndex(v7, NearestColor | 0x2000000);
      if ( NearestPaletteIndex == -1 )
        goto LABEL_20;
      *((_BYTE *)this + v12 + 8) = NearestPaletteIndex;
      if ( v12 >= 40
        && (plpal.palPalEntry[NearestPaletteIndex].peRed
          | (plpal.palPalEntry[NearestPaletteIndex].peGreen << 8)
          | ((plpal.palPalEntry[NearestPaletteIndex].peBlue | 0x200) << 16)) == v15 )
      {
        ++v14;
      }
      ++v12;
      v13 += 4;
    }
    *(_DWORD *)this = 1298223153;
    *((_DWORD *)this + 66) = v14 < 212;
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x180138460  mov     [rsp-8+arg_18], rbx
0x180138465  push    rbp
0x180138466  push    rsi
0x180138467  push    rdi
0x180138468  push    r12
0x18013846a  push    r13
0x18013846c  push    r14
0x18013846e  push    r15
0x180138470  lea     rbp, [rsp-350h]
0x180138478  sub     rsp, 450h
0x18013847f  mov     rax, cs:__security_cookie
0x180138486  xor     rax, rsp
0x180138489  mov     [rbp+380h+var_40], rax
0x180138490  mov     rdi, r8
0x180138493  mov     [rsp+480h+hdc], rdx
0x180138498  mov     rsi, rdx
0x18013849b  mov     dword ptr [rcx], 4C494146h
0x1801384a1  mov     r12, rcx
0x1801384a4  xor     edx, edx; Val
0x1801384a6  mov     r8d, 406h; Size
0x1801384ac  lea     rcx, [rsp+480h+plpal.palNumEntries]; void *
0x1801384b1  call    memset_0
0x1801384b6  mov     eax, 300h
0x1801384bb  mov     edx, 0Eh; index
0x1801384c0  mov     rcx, rsi; hdc
0x1801384c3  mov     [rsp+480h+plpal.palVersion], ax
0x1801384c8  call    cs:__imp_GetDeviceCaps
0x1801384cf  nop     dword ptr [rax+rax+00h]
0x1801384d4  mov     edx, 0Ch; index
0x1801384d9  mov     rcx, rsi; hdc
0x1801384dc  mov     ebx, eax
0x1801384de  call    cs:__imp_GetDeviceCaps
0x1801384e5  nop     dword ptr [rax+rax+00h]
0x1801384ea  imul    ebx, eax
0x1801384ed  mov     edx, 1
0x1801384f2  mov     cl, bl
0x1801384f4  mov     ebx, 100h
0x1801384f9  shl     dx, cl
0x1801384fc  mov     [rsp+480h+plpal.palNumEntries], dx
0x180138501  cmp     dx, bx
0x180138504  jbe     short loc_18013850B
0x180138506  mov     [rsp+480h+plpal.palNumEntries], bx
0x18013850b  lea     r9, [rsp+480h+plpal.palPalEntry]; pPalEntries
0x180138510  mov     r8d, ebx; cEntries
0x180138513  xor     edx, edx; iStart
0x180138515  mov     rcx, rsi; hdc
0x180138518  call    cs:__imp_GetSystemPaletteEntries
0x18013851f  nop     dword ptr [rax+rax+00h]
0x180138524  lea     rcx, [rsp+480h+plpal]; plpal
0x180138529  call    cs:__imp_CreatePalette
0x180138530  nop     dword ptr [rax+rax+00h]
0x180138535  mov     r13, rax
0x180138538  test    rax, rax
0x18013853b  jz      loc_1801386A3
0x180138541  test    rdi, rdi
0x180138544  jz      short loc_1801385B3
0x180138546  mov     rcx, [rdi]
0x180138549  test    rcx, rcx
0x18013854c  jnz     short loc_180138569
0x18013854e  xor     edx, edx
0x180138550  mov     ecx, 40Ch
0x180138555  call    GpMallocEx
0x18013855a  mov     [rdi], rax
0x18013855d  mov     rcx, rax
0x180138560  test    rax, rax
0x180138563  jz      loc_180138694
0x180138569  movzx   eax, [rsp+480h+plpal.palNumEntries]
0x18013856e  xor     r8d, r8d
0x180138571  mov     [rcx+4], eax
0x180138574  xor     eax, eax
0x180138576  cmp     ax, [rsp+480h+plpal.palNumEntries]
0x18013857b  jnb     short loc_1801385B3
0x18013857d  movsxd  rdx, r8d
0x180138580  inc     r8d
0x180138583  movzx   eax, [rsp+rdx*4+480h+plpal.palPalEntry.peGreen]
0x180138588  movzx   ecx, [rsp+rdx*4+480h+plpal.palPalEntry.peRed]
0x18013858d  or      ecx, 0FFFFFF00h
0x180138593  shl     ecx, 8
0x180138596  or      ecx, eax
0x180138598  movzx   eax, [rsp+rdx*4+480h+plpal.palPalEntry.peBlue]
0x18013859d  shl     ecx, 8
0x1801385a0  or      ecx, eax
0x1801385a2  mov     rax, [rdi]
0x1801385a5  mov     [rax+rdx*4+8], ecx
0x1801385a9  movzx   eax, [rsp+480h+plpal.palNumEntries]
0x1801385ae  cmp     r8d, eax
0x1801385b1  jl      short loc_18013857D
0x1801385b3  lea     rcx, [r12+8]; void *
0x1801385b8  mov     r8, rbx; Size
0x1801385bb  xor     edx, edx; Val
0x1801385bd  call    memset_0
0x1801385c2  xor     edi, edi
0x1801385c4  lea     rsi, byte_180189A74
0x1801385cb  xor     r15d, r15d
0x1801385ce  cmp     edi, ebx
0x1801385d0  jge     loc_180138678
0x1801385d6  lea     eax, [rdi-8]
0x1801385d9  movsxd  r14, edi
0x1801385dc  cmp     eax, 3
0x1801385df  ja      short loc_1801385F2
0x1801385e1  lea     rbx, dword_1801ADF50
0x1801385e8  mov     ebx, [rbx+r14*4]
0x1801385ec  bts     ebx, 19h
0x1801385f0  jmp     short loc_18013860B
0x1801385f2  movzx   ebx, byte ptr [rsi+2]
0x1801385f6  movzx   eax, byte ptr [rsi+1]
0x1801385fa  bts     ebx, 9
0x1801385fe  shl     eax, 8
0x180138601  shl     ebx, 10h
0x180138604  or      ebx, eax
0x180138606  movzx   eax, byte ptr [rsi]
0x180138609  or      ebx, eax
0x18013860b  mov     rcx, [rsp+480h+hdc]; hdc
0x180138610  mov     edx, ebx; color
0x180138612  call    cs:__imp_GetNearestColor
0x180138619  nop     dword ptr [rax+rax+00h]
0x18013861e  bts     eax, 19h
0x180138622  mov     rcx, r13; h
0x180138625  mov     edx, eax; color
0x180138627  call    cs:__imp_GetNearestPaletteIndex
0x18013862e  nop     dword ptr [rax+rax+00h]
0x180138633  cmp     eax, 0FFFFFFFFh
0x180138636  jz      short loc_180138694
0x180138638  mov     [r12+r14+8], al
0x18013863d  cmp     edi, 28h ; '('
0x180138640  jl      short loc_180138668
0x180138642  mov     ecx, eax
0x180138644  movzx   edx, [rsp+rcx*4+480h+plpal.palPalEntry.peBlue]
0x180138649  movzx   eax, [rsp+rcx*4+480h+plpal.palPalEntry.peGreen]
0x18013864e  bts     edx, 9
0x180138652  shl     edx, 10h
0x180138655  shl     eax, 8
0x180138658  or      edx, eax
0x18013865a  movzx   eax, [rsp+rcx*4+480h+plpal.palPalEntry.peRed]
0x18013865f  or      edx, eax
0x180138661  cmp     edx, ebx
0x180138663  jnz     short loc_180138668
0x180138665  inc     r15d
0x180138668  inc     edi
0x18013866a  mov     ebx, 100h
0x18013866f  add     rsi, 4
0x180138673  jmp     loc_1801385CE
0x180138678  xor     eax, eax
0x18013867a  mov     dword ptr [r12], 4D615031h
0x180138682  cmp     r15d, 0D4h
0x180138689  setl    al
0x18013868c  mov     [r12+108h], eax
0x180138694  mov     rcx, r13; ho
0x180138697  call    cs:__imp_DeleteObject
0x18013869e  nop     dword ptr [rax+rax+00h]
0x1801386a3  mov     rcx, [rbp+380h+var_40]
0x1801386aa  xor     rcx, rsp; StackCookie
0x1801386ad  call    __security_check_cookie
0x1801386b2  mov     rbx, [rsp+480h+arg_18]
0x1801386ba  add     rsp, 450h
0x1801386c1  pop     r15
0x1801386c3  pop     r14
0x1801386c5  pop     r13
0x1801386c7  pop     r12
0x1801386c9  pop     rdi
0x1801386ca  pop     rsi
0x1801386cb  pop     rbp
0x1801386cc  retn
```
