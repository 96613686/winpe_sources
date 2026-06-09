# ComputeBitMapInfoHeaderSize(tagBITMAPINFOHEADER const *,uint *,uint *)

- ea: `0x18000f148`
- end: `0x18000f1c7`
- name: `?ComputeBitMapInfoHeaderSize@@YAHPEBUtagBITMAPINFOHEADER@@PEAI1@Z`
- size: `127`
- prototype: `__int64 __fastcall(const struct tagBITMAPINFOHEADER *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004a68`
- `0x180014e50`
- `0x180019ea4`
- `0x18001f874`
- `0x180028b6c`

## callees

- `0x18000f148`

## pseudocode

```c
__int64 __fastcall ComputeBitMapInfoHeaderSize(
        const struct tagBITMAPINFOHEADER *a1,
        unsigned int *a2,
        unsigned int *a3)
{
  __int64 result; // rax
  DWORD biSize; // r10d
  unsigned int biBitCount; // edx
  int v8; // ecx
  DWORD v9; // eax
  DWORD biClrUsed; // ecx
  unsigned int v11; // eax

  result = 0;
  *a2 = 0;
  *a3 = 0;
  if ( a1->biPlanes == 1 )
  {
    biSize = a1->biSize;
    if ( a1->biSize >= 0x28 )
    {
      biBitCount = a1->biBitCount;
      v8 = 0;
      if ( !biBitCount )
        biBitCount = 1;
      if ( a1->biCompression == 3 )
      {
        LODWORD(result) = 12;
      }
      else if ( biBitCount <= 8 )
      {
        v9 = 1 << biBitCount;
        biClrUsed = a1->biClrUsed;
        if ( biClrUsed )
        {
          if ( biClrUsed < v9 )
            v9 = a1->biClrUsed;
        }
        LODWORD(result) = 4 * v9;
        v8 = 1024 - result;
      }
      v11 = biSize + result;
      *a2 = v11;
      *a3 = v8 + v11;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f148  mov     [rsp+arg_0], rdi
0x18000f14d  xor     eax, eax
0x18000f14f  mov     dword ptr [rdx], 0
0x18000f155  mov     r11, rdx
0x18000f158  mov     dword ptr [r8], 0
0x18000f15f  mov     r9, rcx
0x18000f162  lea     edi, [rax+1]
0x18000f165  cmp     di, [rcx+0Ch]
0x18000f169  jnz     short loc_18000F1C1
0x18000f16b  mov     r10d, [rcx]
0x18000f16e  cmp     r10d, 28h ; '('
0x18000f172  jb      short loc_18000F1C1
0x18000f174  movzx   edx, word ptr [r9+0Eh]
0x18000f179  xor     ecx, ecx
0x18000f17b  cmp     edx, edi
0x18000f17d  cmovb   edx, edi
0x18000f180  cmp     [r9+10h], eax
0x18000f184  jz      short loc_18000F192
0x18000f186  cmp     dword ptr [r9+10h], 3
0x18000f18b  jnz     short loc_18000F192
0x18000f18d  lea     eax, [rdi+0Bh]
0x18000f190  jmp     short loc_18000F1B4
0x18000f192  cmp     edx, 8
0x18000f195  ja      short loc_18000F1B4
0x18000f197  mov     ecx, edx
0x18000f199  mov     eax, edi
0x18000f19b  shl     eax, cl
0x18000f19d  mov     ecx, [r9+20h]
0x18000f1a1  test    ecx, ecx
0x18000f1a3  jz      short loc_18000F1AA
0x18000f1a5  cmp     ecx, eax
0x18000f1a7  cmovb   eax, ecx
0x18000f1aa  shl     eax, 2
0x18000f1ad  mov     ecx, 400h
0x18000f1b2  sub     ecx, eax
0x18000f1b4  add     eax, r10d
0x18000f1b7  mov     [r11], eax
0x18000f1ba  add     eax, ecx
0x18000f1bc  mov     [r8], eax
0x18000f1bf  mov     eax, edi
0x18000f1c1  mov     rdi, [rsp+arg_0]
0x18000f1c6  retn
```
