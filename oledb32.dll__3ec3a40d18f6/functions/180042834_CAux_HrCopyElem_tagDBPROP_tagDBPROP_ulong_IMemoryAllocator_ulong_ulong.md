# CAux::HrCopyElem(tagDBPROP *,tagDBPROP *,ulong,IMemoryAllocator *,ulong *,ulong)

- ea: `0x180042834`
- end: `0x180042af1`
- name: `?HrCopyElem@CAux@@SAJPEAUtagDBPROP@@0KPEAVIMemoryAllocator@@PEAKK@Z`
- size: `701`
- prototype: `__int64 __usercall@<rax>(struct tagDBPROP *@<rcx>, struct tagDBPROP *@<rdx>, unsigned int@<r8d>, struct IMemoryAllocator *@<r9>, unsigned int *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800437a4`
- `0x180047a20`
- `0x180047e40`

## callees

- `0x180013870`
- `0x18002ec26`
- `0x1800421a0`
- `0x18004240c`
- `0x180042834`
- `0x180042cb8`
- `0x180042eb4`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180042aa4`
- `OLEAUT32!__imp_VariantClear` at `0x180042aa4`

## string_xrefs

- `0x1800428f2`: `<CAux::HrCopyElem|OLEDB|ERR> `
- `0x180042927`: `<CAux::HrCopyElem|OLEDB|ERR> `
- `0x1800429e1`: `<CAux::HrCopyElem|OLEDB|ERR> `
- `0x180042a15`: `<CAux::HrCopyElem|OLEDB|ERR> `
- `0x180042a52`: `<CAux::HrCopyElem|OLEDB|ERR> `
- `0x180042a7e`: `<CAux::HrCopyElem|OLEDB|ERR> `

## pseudocode

```c
__int64 __fastcall CAux::HrCopyElem(
        struct tagDBPROP *a1,
        struct tagDBPROP *a2,
        unsigned int a3,
        struct IMemoryAllocator *a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int v6; // r15d
  struct IMemoryAllocator *v7; // r13
  struct tagDBPROP *v8; // rsi
  struct tagDBPROP *v9; // r12
  int v10; // ebx
  __int64 v11; // rdi
  struct tagDBPROP *i; // rbp
  int v13; // eax
  int fixed; // eax
  int v15; // r9d
  int v16; // ebp
  unsigned int v17; // eax
  struct tagDBPROP *v18; // r15
  int v19; // r9d
  unsigned int j; // esi
  unsigned int v22; // [rsp+20h] [rbp-38h]

  v6 = a3;
  v7 = a4;
  v8 = a2;
  v9 = a1;
  memcpy_0(a1, a2, 72LL * a3);
  v10 = 0;
  v11 = 0;
  if ( !a5 )
  {
    for ( i = v9; ; ++i )
    {
      if ( (unsigned int)v11 >= a3 )
        return (unsigned int)v10;
      v13 = CAux::HrCopyDBIDs(&i->colid, &v8->colid, a4, a6);
      v10 = v13;
      if ( v13 < 0 )
        break;
      fixed = CAux::HrFixCopyVariant(&i->vValue, &v8->vValue, 0);
      v10 = fixed;
      if ( fixed < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(fixed, L"<CAux::HrCopyElem|OLEDB|ERR> ", 0x1D1u);
        CAux::FreeDBIDs(&i->colid, a4);
LABEL_12:
        v7 = a4;
        goto LABEL_38;
      }
      if ( a6 )
        CAux::PatchStatusFlag(v8, i, a6, v15);
      LODWORD(v11) = v11 + 1;
      ++v8;
    }
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v13, L"<CAux::HrCopyElem|OLEDB|ERR> ", 0x1D9u);
    goto LABEL_12;
  }
  v16 = 0;
  v17 = 0;
  while ( 1 )
  {
    v22 = v17;
    if ( v17 >= v6 )
      break;
    v18 = &v9[v11];
    v10 = CAux::HrCopyDBIDs(&v18->colid, &v8->colid, v7, a6);
    if ( v10 < 0 )
    {
      if ( v10 == -2147024882 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147024882, L"<CAux::HrCopyElem|OLEDB|ERR> ", 0x218u);
        goto LABEL_38;
      }
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v10, L"<CAux::HrCopyElem|OLEDB|ERR> ", 0x21Eu);
      goto LABEL_31;
    }
    v10 = CAux::HrFixCopyVariant(&v18->vValue, &v8->vValue, v16);
    if ( v10 < 0 )
    {
      if ( v10 == -2147024882 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147024882, L"<CAux::HrCopyElem|OLEDB|ERR> ", 0x208u);
        CAux::FreeDBIDs(&v18->colid, v7);
LABEL_38:
        for ( j = 0; j < (unsigned int)v11; ++v9 )
        {
          CAux::FreeDBIDs(&v9->colid, v7);
          VariantClear(&v9->vValue);
          ++j;
        }
        return (unsigned int)v10;
      }
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v10, L"<CAux::HrCopyElem|OLEDB|ERR> ", 0x20Fu);
      CAux::FreeDBIDs(&v18->colid, v7);
LABEL_31:
      v16 = 1;
      v8->dwStatus = 2;
      goto LABEL_32;
    }
    if ( v16 == 1 )
    {
      v18->dwOptions = v8->dwOptions;
      v18->dwPropertyID = v8->dwPropertyID;
      v18->dwStatus = v8->dwStatus;
    }
    if ( a6 )
      CAux::PatchStatusFlag(v8, &v9[v11], a6, v19);
    v11 = (unsigned int)(v11 + 1);
LABEL_32:
    v6 = a3;
    v17 = v22 + 1;
    ++v8;
  }
  if ( (_DWORD)v11 != v6 )
    v10 = (_DWORD)v11 != 0 ? 265946 : -2147217887;
  *a5 = v11;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180042834  mov     rax, rsp
0x180042837  mov     [rax+8], rbx
0x18004283b  mov     [rax+10h], rbp
0x18004283f  mov     [rax+20h], r9
0x180042843  mov     [rax+18h], r8d
0x180042847  push    rsi
0x180042848  push    rdi
0x180042849  push    r12
0x18004284b  push    r13
0x18004284d  push    r15
0x18004284f  sub     rsp, 30h
0x180042853  mov     r15d, r8d
0x180042856  mov     r13, r9
0x180042859  mov     rsi, rdx
0x18004285c  mov     r12, rcx
0x18004285f  lea     r8, [r15+r15*8]
0x180042863  shl     r8, 3; Size
0x180042867  call    memcpy_0
0x18004286c  xor     ebx, ebx
0x18004286e  xor     edi, edi
0x180042870  cmp     [rsp+58h+arg_20], rbx
0x180042878  jnz     loc_180042937
0x18004287e  mov     r15d, [rsp+58h+arg_28]
0x180042886  mov     rbp, r12
0x180042889  cmp     edi, [rsp+58h+arg_10]
0x18004288d  jnb     loc_180042AD8
0x180042893  mov     r8, [rsp+58h+arg_18]; struct IMemoryAllocator *
0x180042898  lea     rdx, [rsi+10h]; struct tagDBID *
0x18004289c  mov     r9d, r15d; unsigned int
0x18004289f  lea     rcx, [rbp+10h]; struct tagDBID *
0x1800428a3  call    ?HrCopyDBIDs@CAux@@CAJPEAUtagDBID@@PEBU2@PEAVIMemoryAllocator@@K@Z; CAux::HrCopyDBIDs(tagDBID *,tagDBID const *,IMemoryAllocator *,ulong)
0x1800428a8  mov     ebx, eax
0x1800428aa  test    eax, eax
0x1800428ac  js      short loc_180042918
0x1800428ae  lea     rdx, [rsi+30h]; pvargSrc
0x1800428b2  xor     r8d, r8d; int
0x1800428b5  lea     rcx, [rbp+30h]; pvargDest
0x1800428b9  call    ?HrFixCopyVariant@CAux@@CAJPEAUtagVARIANT@@PEBU2@H@Z; CAux::HrFixCopyVariant(tagVARIANT *,tagVARIANT const *,int)
0x1800428be  mov     ebx, eax
0x1800428c0  test    eax, eax
0x1800428c2  js      short loc_1800428E3
0x1800428c4  test    r15d, r15d
0x1800428c7  jz      short loc_1800428D7
0x1800428c9  mov     r8d, r15d; unsigned int
0x1800428cc  mov     rdx, rbp; struct tagDBPROP *
0x1800428cf  mov     rcx, rsi; struct tagDBPROP *
0x1800428d2  call    ?PatchStatusFlag@CAux@@SAXPEAUtagDBPROP@@0KH@Z; CAux::PatchStatusFlag(tagDBPROP *,tagDBPROP *,ulong,int)
0x1800428d7  inc     edi
0x1800428d9  add     rsi, 48h ; 'H'
0x1800428dd  add     rbp, 48h ; 'H'
0x1800428e1  jmp     short loc_180042889
0x1800428e3  test    byte ptr cs:_bidGblFlags, 2
0x1800428ea  jz      short loc_180042900
0x1800428ec  mov     r8d, 1D1h; unsigned int
0x1800428f2  lea     rdx, aCauxHrcopyelem; "<CAux::HrCopyElem|OLEDB|ERR> "
0x1800428f9  mov     ecx, eax; int
0x1800428fb  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180042900  mov     rdx, [rsp+58h+arg_18]; struct IMemoryAllocator *
0x180042905  lea     rcx, [rbp+10h]; struct tagDBID *
0x180042909  call    ?FreeDBIDs@CAux@@CAXPEAUtagDBID@@PEAVIMemoryAllocator@@@Z; CAux::FreeDBIDs(tagDBID *,IMemoryAllocator *)
0x18004290e  mov     r13, [rsp+58h+arg_18]
0x180042913  jmp     loc_180042A8C
0x180042918  test    byte ptr cs:_bidGblFlags, 2
0x18004291f  jz      short loc_18004290E
0x180042921  mov     r8d, 1D9h; unsigned int
0x180042927  lea     rdx, aCauxHrcopyelem; "<CAux::HrCopyElem|OLEDB|ERR> "
0x18004292e  mov     ecx, eax; int
0x180042930  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180042935  jmp     short loc_18004290E
0x180042937  xor     ebp, ebp
0x180042939  xor     eax, eax
0x18004293b  mov     [rsp+58h+var_38], eax
0x18004293f  cmp     eax, r15d
0x180042942  jnb     loc_180042AB7
0x180042948  mov     r9d, [rsp+58h+arg_28]; unsigned int
0x180042950  lea     rcx, [rdi+rdi*8]
0x180042954  lea     r15, [r12+rcx*8]
0x180042958  mov     r8, r13; struct IMemoryAllocator *
0x18004295b  lea     rax, [r15+10h]
0x18004295f  mov     rcx, rax; struct tagDBID *
0x180042962  mov     [rsp+58h+var_30], rax
0x180042967  lea     rdx, [rsi+10h]; struct tagDBID *
0x18004296b  call    ?HrCopyDBIDs@CAux@@CAJPEAUtagDBID@@PEBU2@PEAVIMemoryAllocator@@K@Z; CAux::HrCopyDBIDs(tagDBID *,tagDBID const *,IMemoryAllocator *,ulong)
0x180042970  mov     ebx, eax
0x180042972  test    eax, eax
0x180042974  js      loc_1800429FD
0x18004297a  lea     rdx, [rsi+30h]; pvargSrc
0x18004297e  mov     r8d, ebp; int
0x180042981  lea     rcx, [r15+30h]; pvargDest
0x180042985  call    ?HrFixCopyVariant@CAux@@CAJPEAUtagVARIANT@@PEBU2@H@Z; CAux::HrFixCopyVariant(tagVARIANT *,tagVARIANT const *,int)
0x18004298a  mov     ebx, eax
0x18004298c  test    eax, eax
0x18004298e  js      short loc_1800429C9
0x180042990  cmp     ebp, 1
0x180042993  jnz     short loc_1800429A8
0x180042995  mov     eax, [rsi+4]
0x180042998  mov     [r15+4], eax
0x18004299c  mov     eax, [rsi]
0x18004299e  mov     [r15], eax
0x1800429a1  mov     eax, [rsi+8]
0x1800429a4  mov     [r15+8], eax
0x1800429a8  cmp     [rsp+58h+arg_28], 0
0x1800429b0  jz      short loc_1800429C5
0x1800429b2  mov     r8d, [rsp+58h+arg_28]; unsigned int
0x1800429ba  mov     rdx, r15; struct tagDBPROP *
0x1800429bd  mov     rcx, rsi; struct tagDBPROP *
0x1800429c0  call    ?PatchStatusFlag@CAux@@SAXPEAUtagDBPROP@@0KH@Z; CAux::PatchStatusFlag(tagDBPROP *,tagDBPROP *,ulong,int)
0x1800429c5  inc     edi
0x1800429c7  jmp     short loc_180042A2F
0x1800429c9  mov     eax, 8007000Eh
0x1800429ce  cmp     ebx, eax
0x1800429d0  jz      short loc_180042A43
0x1800429d2  test    byte ptr cs:_bidGblFlags, 2
0x1800429d9  jz      short loc_1800429EF
0x1800429db  mov     r8d, 20Fh; unsigned int
0x1800429e1  lea     rdx, aCauxHrcopyelem; "<CAux::HrCopyElem|OLEDB|ERR> "
0x1800429e8  mov     ecx, ebx; int
0x1800429ea  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800429ef  mov     rdx, r13; struct IMemoryAllocator *
0x1800429f2  lea     rcx, [r15+10h]; struct tagDBID *
0x1800429f6  call    ?FreeDBIDs@CAux@@CAXPEAUtagDBID@@PEAVIMemoryAllocator@@@Z; CAux::FreeDBIDs(tagDBID *,IMemoryAllocator *)
0x1800429fb  jmp     short loc_180042A23
0x1800429fd  mov     eax, 8007000Eh
0x180042a02  cmp     ebx, eax
0x180042a04  jz      short loc_180042A6F
0x180042a06  test    byte ptr cs:_bidGblFlags, 2
0x180042a0d  jz      short loc_180042A23
0x180042a0f  mov     r8d, 21Eh; unsigned int
0x180042a15  lea     rdx, aCauxHrcopyelem; "<CAux::HrCopyElem|OLEDB|ERR> "
0x180042a1c  mov     ecx, ebx; int
0x180042a1e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180042a23  mov     ebp, 1
0x180042a28  mov     dword ptr [rsi+8], 2
0x180042a2f  mov     eax, [rsp+58h+var_38]
0x180042a33  mov     r15d, [rsp+58h+arg_10]
0x180042a38  inc     eax
0x180042a3a  add     rsi, 48h ; 'H'
0x180042a3e  jmp     loc_18004293B
0x180042a43  test    byte ptr cs:_bidGblFlags, 2
0x180042a4a  jz      short loc_180042A60
0x180042a4c  mov     r8d, 208h; unsigned int
0x180042a52  lea     rdx, aCauxHrcopyelem; "<CAux::HrCopyElem|OLEDB|ERR> "
0x180042a59  mov     ecx, eax; int
0x180042a5b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180042a60  mov     rcx, [rsp+58h+var_30]; struct tagDBID *
0x180042a65  mov     rdx, r13; struct IMemoryAllocator *
0x180042a68  call    ?FreeDBIDs@CAux@@CAXPEAUtagDBID@@PEAVIMemoryAllocator@@@Z; CAux::FreeDBIDs(tagDBID *,IMemoryAllocator *)
0x180042a6d  jmp     short loc_180042A8C
0x180042a6f  test    byte ptr cs:_bidGblFlags, 2
0x180042a76  jz      short loc_180042A8C
0x180042a78  mov     r8d, 218h; unsigned int
0x180042a7e  lea     rdx, aCauxHrcopyelem; "<CAux::HrCopyElem|OLEDB|ERR> "
0x180042a85  mov     ecx, eax; int
0x180042a87  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180042a8c  xor     esi, esi
0x180042a8e  test    edi, edi
0x180042a90  jz      short loc_180042AD8
0x180042a92  lea     rcx, [r12+10h]; struct tagDBID *
0x180042a97  mov     rdx, r13; struct IMemoryAllocator *
0x180042a9a  call    ?FreeDBIDs@CAux@@CAXPEAUtagDBID@@PEAVIMemoryAllocator@@@Z; CAux::FreeDBIDs(tagDBID *,IMemoryAllocator *)
0x180042a9f  lea     rcx, [r12+30h]; pvarg
0x180042aa4  call    cs:__imp_VariantClear
0x180042aaa  inc     esi
0x180042aac  lea     r12, [r12+48h]
0x180042ab1  cmp     esi, edi
0x180042ab3  jb      short loc_180042A92
0x180042ab5  jmp     short loc_180042AD8
0x180042ab7  cmp     edi, r15d
0x180042aba  jz      short loc_180042ACE
0x180042abc  mov     eax, edi
0x180042abe  neg     eax
0x180042ac0  sbb     ebx, ebx
0x180042ac2  and     ebx, 800000B9h
0x180042ac8  add     ebx, 80040E21h
0x180042ace  mov     rax, [rsp+58h+arg_20]
0x180042ad6  mov     [rax], edi
0x180042ad8  mov     rbp, [rsp+58h+arg_8]
0x180042add  mov     eax, ebx
0x180042adf  mov     rbx, [rsp+58h+arg_0]
0x180042ae4  add     rsp, 30h
0x180042ae8  pop     r15
0x180042aea  pop     r13
0x180042aec  pop     r12
0x180042aee  pop     rdi
0x180042aef  pop     rsi
0x180042af0  retn
```
