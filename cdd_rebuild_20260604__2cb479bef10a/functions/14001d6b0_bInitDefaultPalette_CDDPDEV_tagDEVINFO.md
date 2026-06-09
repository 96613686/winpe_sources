# bInitDefaultPalette(CDDPDEV *,tagDEVINFO *)

- ea: `0x14001d6b0`
- end: `0x14001d8ff`
- name: `?bInitDefaultPalette@@YAHPEAUCDDPDEV@@PEAUtagDEVINFO@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(struct CDDPDEV *, struct tagDEVINFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d980`

## callees

- `0x14001d6b0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001d70f`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001d83e`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001d70f`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001d83e`
- `watchdog!WdLogSingleEntry1` at `0x14001d6f8`
- `watchdog!WdLogSingleEntry1` at `0x14001d827`
- `watchdog!WdLogSingleEntry1` at `0x14001d8d8`
- `watchdog!WdLogSingleEntry1` at `0x14001d6f8`
- `watchdog!WdLogSingleEntry1` at `0x14001d827`
- `watchdog!WdLogSingleEntry1` at `0x14001d8d8`
- `WIN32K!EngCreatePalette` at `0x14001d801`
- `WIN32K!EngCreatePalette` at `0x14001d8b6`
- `WIN32K!EngCreatePalette` at `0x14001d801`
- `WIN32K!EngCreatePalette` at `0x14001d8b6`
- `WIN32K!EngAllocMem` at `0x14001d6da`
- `WIN32K!EngAllocMem` at `0x14001d6da`
- `WIN32K!EngFreeMem` at `0x14001d877`
- `WIN32K!EngFreeMem` at `0x14001d877`

## pseudocode

```c
__int64 __fastcall bInitDefaultPalette(struct CDDPDEV *a1, struct tagDEVINFO *a2)
{
  PVOID v4; // rax
  int v5; // ebx
  _QWORD *v6; // rax
  char v8; // r9
  char v9; // dl
  char v10; // r10
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r10
  __int64 v14; // r8
  __int64 v15; // rax
  HPALETTE Palette; // rax
  _QWORD *v17; // rax
  HPALETTE v18; // rax

  if ( *((_DWORD *)a1 + 279) == 8 )
  {
    v4 = EngAllocMem(0, 0x400u, 0x64646344u);
    *((_QWORD *)a1 + 310) = v4;
    if ( !v4 )
    {
      WdLogSingleEntry1(6, a1);
      v5 = 109;
LABEL_4:
      WdLogGlobalForLineNumber = v5;
      v6 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      v6[3] = gCddImageInfo;
      v6[4] = (unsigned int)dword_14003E570;
      v6[5] = 215857758;
      WdLogGlobalForLineNumber = v5;
      return 0;
    }
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = 0;
    do
    {
      *(_BYTE *)(v12 + *((_QWORD *)a1 + 310)) = v10;
      *(_BYTE *)(v12 + *((_QWORD *)a1 + 310) + 1) = v9;
      *(_BYTE *)(*((_QWORD *)a1 + 310) + v12 + 2) = v8;
      *(_BYTE *)(*((_QWORD *)a1 + 310) + v12 + 3) = 0;
      v10 += 32;
      if ( !v10 )
      {
        v9 += 32;
        if ( !v9 )
          v8 += 64;
      }
      ++v11;
      v12 += 4;
    }
    while ( v11 != 256 );
    v13 = 0;
    do
    {
      v14 = (unsigned int)(v13 + 246);
      *(_DWORD *)(*((_QWORD *)a1 + 310) + 4 * v13) = *((_DWORD *)qword_14003A810 + v13);
      v15 = (unsigned int)(v13 + 10);
      v13 = (unsigned int)(v13 + 1);
      *(_DWORD *)(*((_QWORD *)a1 + 310) + 4 * v14) = *((_DWORD *)qword_14003A810 + v15);
    }
    while ( (unsigned int)v13 < 0xA );
    Palette = EngCreatePalette(1u, 0x100u, *((ULONG **)a1 + 310), 0, 0, 0);
    *((_QWORD *)a2 + 37) = Palette;
    *((_QWORD *)a1 + 3) = Palette;
    if ( !Palette )
    {
      WdLogSingleEntry1(6, a1);
      WdLogGlobalForLineNumber = 164;
      v17 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      v17[3] = gCddImageInfo;
      v17[4] = (unsigned int)dword_14003E570;
      v17[5] = 215857758;
      WdLogGlobalForLineNumber = 164;
      EngFreeMem(*((PVOID *)a1 + 310));
      *((_QWORD *)a1 + 310) = 0;
      return 0;
    }
  }
  else
  {
    v18 = EngCreatePalette(2u, 0, 0, *((_DWORD *)a1 + 275), *((_DWORD *)a1 + 276), *((_DWORD *)a1 + 277));
    *((_QWORD *)a2 + 37) = v18;
    *((_QWORD *)a1 + 3) = v18;
    if ( !v18 )
    {
      WdLogSingleEntry1(6, a1);
      v5 = 188;
      goto LABEL_4;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14001d6b0  mov     [rsp+arg_8], rbx
0x14001d6b5  push    rdi
0x14001d6b6  sub     rsp, 30h
0x14001d6ba  cmp     dword ptr [rcx+45Ch], 8
0x14001d6c1  mov     rdi, rdx
0x14001d6c4  mov     rbx, rcx
0x14001d6c7  jnz     loc_14001D893
0x14001d6cd  mov     edx, 400h; cjMemSize
0x14001d6d2  xor     ecx, ecx; fl
0x14001d6d4  mov     r8d, 64646344h; ulTag
0x14001d6da  call    cs:__imp_EngAllocMem
0x14001d6e1  nop     dword ptr [rax+rax+00h]
0x14001d6e6  mov     [rbx+9B0h], rax
0x14001d6ed  test    rax, rax
0x14001d6f0  jnz     short loc_14001D748
0x14001d6f2  mov     rdx, rbx
0x14001d6f5  lea     ecx, [rax+6]
0x14001d6f8  call    cs:__imp_WdLogSingleEntry1
0x14001d6ff  nop     dword ptr [rax+rax+00h]
0x14001d704  mov     ebx, 6Dh ; 'm'
0x14001d709  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001d70f  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14001d716  nop     dword ptr [rax+rax+00h]
0x14001d71b  mov     rcx, rax
0x14001d71e  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001d725  mov     [rcx+18h], rax
0x14001d729  mov     eax, cs:dword_14003E570
0x14001d72f  mov     [rcx+20h], rax
0x14001d733  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x14001d73b  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001d741  xor     eax, eax
0x14001d743  jmp     loc_14001D8F3
0x14001d748  xor     r9b, r9b
0x14001d74b  xor     dl, dl
0x14001d74d  xor     r10b, r10b
0x14001d750  xor     r8d, r8d
0x14001d753  xor     ecx, ecx
0x14001d755  mov     rax, [rbx+9B0h]
0x14001d75c  mov     [rcx+rax], r10b
0x14001d760  mov     rax, [rbx+9B0h]
0x14001d767  mov     [rcx+rax+1], dl
0x14001d76b  mov     rax, [rbx+9B0h]
0x14001d772  mov     [rax+rcx+2], r9b
0x14001d777  mov     rax, [rbx+9B0h]
0x14001d77e  mov     byte ptr [rax+rcx+3], 0
0x14001d783  add     r10b, 20h ; ' '
0x14001d787  jnz     short loc_14001D792
0x14001d789  add     dl, 20h ; ' '
0x14001d78c  jnz     short loc_14001D792
0x14001d78e  add     r9b, 40h ; '@'
0x14001d792  inc     r8
0x14001d795  add     rcx, 4
0x14001d799  cmp     r8, 100h
0x14001d7a0  jnz     short loc_14001D755
0x14001d7a2  xor     r10d, r10d
0x14001d7a5  lea     r11, qword_14003A810
0x14001d7ac  mov     eax, [r11+r10*4]
0x14001d7b0  lea     r8d, [r10+0F6h]
0x14001d7b7  mov     rcx, [rbx+9B0h]
0x14001d7be  mov     [rcx+r10*4], eax
0x14001d7c2  lea     eax, [r10+0Ah]
0x14001d7c6  mov     rcx, [rbx+9B0h]
0x14001d7cd  inc     r10d
0x14001d7d0  mov     eax, [r11+rax*4]
0x14001d7d4  mov     [rcx+r8*4], eax
0x14001d7d8  cmp     r10d, 0Ah
0x14001d7dc  jb      short loc_14001D7AC
0x14001d7de  mov     r8, [rbx+9B0h]; pulColors
0x14001d7e5  xor     r9d, r9d; flRed
0x14001d7e8  mov     [rsp+38h+flBlue], 0; flBlue
0x14001d7f0  mov     edx, 100h; cColors
0x14001d7f5  mov     [rsp+38h+flGreen], 0; flGreen
0x14001d7fd  lea     ecx, [r9+1]; iMode
0x14001d801  call    cs:__imp_EngCreatePalette
0x14001d808  nop     dword ptr [rax+rax+00h]
0x14001d80d  mov     [rdi+128h], rax
0x14001d814  mov     [rbx+18h], rax
0x14001d818  test    rax, rax
0x14001d81b  jnz     loc_14001D8EE
0x14001d821  mov     rdx, rbx
0x14001d824  lea     ecx, [rax+6]
0x14001d827  call    cs:__imp_WdLogSingleEntry1
0x14001d82e  nop     dword ptr [rax+rax+00h]
0x14001d833  mov     edi, 0A4h
0x14001d838  mov     cs:WdLogGlobalForLineNumber, edi
0x14001d83e  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14001d845  nop     dword ptr [rax+rax+00h]
0x14001d84a  mov     rcx, rax
0x14001d84d  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001d854  mov     [rcx+18h], rax
0x14001d858  mov     eax, cs:dword_14003E570
0x14001d85e  mov     [rcx+20h], rax
0x14001d862  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x14001d86a  mov     cs:WdLogGlobalForLineNumber, edi
0x14001d870  mov     rcx, [rbx+9B0h]; pv
0x14001d877  call    cs:__imp_EngFreeMem
0x14001d87e  nop     dword ptr [rax+rax+00h]
0x14001d883  mov     qword ptr [rbx+9B0h], 0
0x14001d88e  jmp     loc_14001D741
0x14001d893  mov     eax, [rcx+454h]
0x14001d899  xor     edx, edx; cColors
0x14001d89b  mov     r9d, [rcx+44Ch]; flRed
0x14001d8a2  xor     r8d, r8d; pulColors
0x14001d8a5  mov     [rsp+38h+flBlue], eax; flBlue
0x14001d8a9  mov     eax, [rcx+450h]
0x14001d8af  lea     ecx, [rdx+2]; iMode
0x14001d8b2  mov     [rsp+38h+flGreen], eax; flGreen
0x14001d8b6  call    cs:__imp_EngCreatePalette
0x14001d8bd  nop     dword ptr [rax+rax+00h]
0x14001d8c2  mov     [rdi+128h], rax
0x14001d8c9  mov     [rbx+18h], rax
0x14001d8cd  test    rax, rax
0x14001d8d0  jnz     short loc_14001D8EE
0x14001d8d2  mov     rdx, rbx
0x14001d8d5  lea     ecx, [rax+6]
0x14001d8d8  call    cs:__imp_WdLogSingleEntry1
0x14001d8df  nop     dword ptr [rax+rax+00h]
0x14001d8e4  mov     ebx, 0BCh
0x14001d8e9  jmp     loc_14001D709
0x14001d8ee  mov     eax, 1
0x14001d8f3  mov     rbx, [rsp+38h+arg_8]
0x14001d8f8  add     rsp, 30h
0x14001d8fc  pop     rdi
0x14001d8fd  retn
```
