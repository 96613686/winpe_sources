# DecompressGetPalette

- ea: `0x1800037c4`
- end: `0x1800038cb`
- name: `DecompressGetPalette`
- size: `263`
- prototype: `__int64 __fastcall(_DWORD *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x1800037c4`
- `0x1800038d4`

## import_xrefs

- `GDI32!GetSystemPaletteEntries` at `0x18000380b`
- `GDI32!GetSystemPaletteEntries` at `0x18000380b`
- `USER32!ReleaseDC` at `0x180003816`
- `USER32!ReleaseDC` at `0x180003816`
- `USER32!GetDC` at `0x1800037f1`
- `USER32!GetDC` at `0x1800037f1`

## pseudocode

```c
__int64 __fastcall DecompressGetPalette(_DWORD *a1, int *a2)
{
  __int64 result; // rax
  HDC DC; // rbx
  __int64 *v5; // rax
  __int64 v6; // rdx
  _OWORD *v7; // rcx
  __int128 v8; // xmm1
  int v9; // r8d
  char *v10; // rdx
  char v11; // cl

  result = DecompressQuery(a1, (__int64)a2);
  if ( !(_DWORD)result )
  {
    if ( *((_WORD *)a2 + 7) <= 8u )
    {
      DC = GetDC(0);
      GetSystemPaletteEntries(DC, 0, 0x100u, (LPPALETTEENTRY)((char *)a2 + *a2));
      ReleaseDC(0, DC);
      v5 = PalTable;
      v6 = 7;
      v7 = (_OWORD *)((char *)a2 + *a2 + 40);
      do
      {
        *v7 = *(_OWORD *)v5;
        v7[1] = *((_OWORD *)v5 + 1);
        v7[2] = *((_OWORD *)v5 + 2);
        v7[3] = *((_OWORD *)v5 + 3);
        v7[4] = *((_OWORD *)v5 + 4);
        v7[5] = *((_OWORD *)v5 + 5);
        v7[6] = *((_OWORD *)v5 + 6);
        v8 = *((_OWORD *)v5 + 7);
        v5 += 16;
        v7[7] = v8;
        v7 += 8;
        --v6;
      }
      while ( v6 );
      v9 = 256;
      *v7 = *(_OWORD *)v5;
      v7[1] = *((_OWORD *)v5 + 1);
      v7[2] = *((_OWORD *)v5 + 2);
      v10 = (char *)a2 + *a2;
      do
      {
        v11 = *v10;
        *v10 = v10[2];
        v10[2] = v11;
        v10 += 4;
        --v9;
      }
      while ( v9 );
      *((_QWORD *)a2 + 4) = 256;
      return 0;
    }
    else
    {
      return 4294967196LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800037c4  mov     [rsp+arg_0], rbx
0x1800037c9  push    rdi
0x1800037ca  sub     rsp, 20h
0x1800037ce  mov     rdi, rdx
0x1800037d1  call    DecompressQuery
0x1800037d6  test    eax, eax
0x1800037d8  jnz     loc_1800038C0
0x1800037de  cmp     word ptr [rdi+0Eh], 8
0x1800037e3  jbe     short loc_1800037EF
0x1800037e5  mov     eax, 0FFFFFF9Ch
0x1800037ea  jmp     loc_1800038C0
0x1800037ef  xor     ecx, ecx; hWnd
0x1800037f1  call    cs:__imp_GetDC
0x1800037f7  movsxd  r9, dword ptr [rdi]
0x1800037fa  xor     edx, edx; iStart
0x1800037fc  add     r9, rdi; pPalEntries
0x1800037ff  mov     r8d, 100h; cEntries
0x180003805  mov     rcx, rax; hdc
0x180003808  mov     rbx, rax
0x18000380b  call    cs:__imp_GetSystemPaletteEntries
0x180003811  mov     rdx, rbx; hDC
0x180003814  xor     ecx, ecx; hWnd
0x180003816  call    cs:__imp_ReleaseDC
0x18000381c  movsxd  rcx, dword ptr [rdi]
0x18000381f  lea     rax, PalTable
0x180003826  mov     edx, 7
0x18000382b  add     rcx, 28h ; '('
0x18000382f  add     rcx, rdi
0x180003832  lea     r8d, [rdx+79h]
0x180003836  movups  xmm0, xmmword ptr [rax]
0x180003839  movups  xmmword ptr [rcx], xmm0
0x18000383c  movups  xmm1, xmmword ptr [rax+10h]
0x180003840  movups  xmmword ptr [rcx+10h], xmm1
0x180003844  movups  xmm0, xmmword ptr [rax+20h]
0x180003848  movups  xmmword ptr [rcx+20h], xmm0
0x18000384c  movups  xmm1, xmmword ptr [rax+30h]
0x180003850  movups  xmmword ptr [rcx+30h], xmm1
0x180003854  movups  xmm0, xmmword ptr [rax+40h]
0x180003858  movups  xmmword ptr [rcx+40h], xmm0
0x18000385c  movups  xmm1, xmmword ptr [rax+50h]
0x180003860  movups  xmmword ptr [rcx+50h], xmm1
0x180003864  movups  xmm0, xmmword ptr [rax+60h]
0x180003868  movups  xmmword ptr [rcx+60h], xmm0
0x18000386c  movups  xmm1, xmmword ptr [rax+70h]
0x180003870  add     rax, r8
0x180003873  movups  xmmword ptr [rcx+70h], xmm1
0x180003877  add     rcx, r8
0x18000387a  sub     rdx, 1
0x18000387e  jnz     short loc_180003836
0x180003880  movups  xmm0, xmmword ptr [rax]
0x180003883  mov     r8d, 100h
0x180003889  movups  xmmword ptr [rcx], xmm0
0x18000388c  movups  xmm1, xmmword ptr [rax+10h]
0x180003890  movups  xmmword ptr [rcx+10h], xmm1
0x180003894  movups  xmm0, xmmword ptr [rax+20h]
0x180003898  movups  xmmword ptr [rcx+20h], xmm0
0x18000389c  movsxd  rdx, dword ptr [rdi]
0x18000389f  add     rdx, rdi
0x1800038a2  mov     cl, [rdx]
0x1800038a4  mov     al, [rdx+2]
0x1800038a7  mov     [rdx], al
0x1800038a9  mov     [rdx+2], cl
0x1800038ac  lea     rdx, [rdx+4]
0x1800038b0  sub     r8d, 1
0x1800038b4  jnz     short loc_1800038A2
0x1800038b6  mov     qword ptr [rdi+20h], 100h
0x1800038be  xor     eax, eax
0x1800038c0  mov     rbx, [rsp+28h+arg_0]
0x1800038c5  add     rsp, 20h
0x1800038c9  pop     rdi
0x1800038ca  retn
```
