# lmiGetModuleDumpInfo(_PROCESS_ENTRY *,_MODULE_ENTRY *,MODULE_INFO *)

- ea: `0x180199ba0`
- end: `0x18019a1a2`
- name: `?lmiGetModuleDumpInfo@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@PEAUMODULE_INFO@@@Z`
- size: `1538`
- prototype: `int(struct _PROCESS_ENTRY *, struct _MODULE_ENTRY *, struct MODULE_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18019ad50`

## callees

- `0x180023bdc`
- `0x180027430`
- `0x18018f500`
- `0x180199ba0`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180199f16`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180199f16`

## string_xrefs

- `0x18019a162`: `Cannot read Image header @ %p\n`
- `0x180199e94`: `Cannot read Image NT header @ %p\n`
- `0x18019a14d`: `Cannot read Image Debug header @ %p\n`
- `0x180199f2b`: `Cannot allocate memory for reading sections\n`
- `0x180199f8b`: `Can't read section headers\n`

## pseudocode

```c
__int64 __fastcall lmiGetModuleDumpInfo(struct _PROCESS_ENTRY *a1, struct _MODULE_ENTRY *a2, struct MODULE_INFO *a3)
{
  __int64 v5; // rcx
  const CHAR *v6; // rcx
  int v7; // eax
  __int16 v9; // dx
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rcx
  bool v12; // zf
  char *v13; // r8
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  const CHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  void *v19; // rax
  __int64 v20; // rax
  char *v21; // rcx
  __int64 v22; // rdx
  _OWORD *v23; // rax
  __int128 v24; // xmm1
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h]
  __int128 v28; // [rsp+58h] [rbp-A8h]
  _WORD v29[30]; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+ACh] [rbp-54h]
  int v31; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v32[2]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v33; // [rsp+B8h] [rbp-48h]
  __int16 v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+CCh] [rbp-34h]
  int v36; // [rsp+100h] [rbp+0h]
  int v37; // [rsp+108h] [rbp+8h]
  unsigned int v38; // [rsp+158h] [rbp+58h]
  unsigned int v39; // [rsp+15Ch] [rbp+5Ch]
  _BYTE v40[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v41; // [rsp+1B4h] [rbp+B4h] BYREF
  int v42; // [rsp+200h] [rbp+100h]
  int v43; // [rsp+208h] [rbp+108h]
  unsigned int v44; // [rsp+268h] [rbp+168h]
  unsigned int v45; // [rsp+26Ch] [rbp+16Ch]

  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v29, 0, 0x40u);
  memset_0(&v31, 0, 0xF8u);
  memset_0(v40, 0, 0x108u);
  memset_0(a3, 0, 0x25B8u);
  wcs2ansi((LPCWCH)a2 + 23, (char *)a3, 0x1002u);
  *((_QWORD *)a3 + 513) = *((_QWORD *)a2 + 3);
  wcs2ansi(*((LPCWCH *)a2 + 38), (char *)a3 + 4112, 0x1002u);
  v5 = *((_QWORD *)a3 + 513);
  if ( v5 )
  {
    *((_DWORD *)a3 + 2059) = *((_DWORD *)a2 + 599);
    *((_DWORD *)a3 + 2065) = *((_DWORD *)a2 + 4867);
    v7 = *((_DWORD *)a2 + 599);
    if ( v7 == 8 )
      return 1;
    if ( v7 == 5 )
      *((_DWORD *)a3 + 2065) = 0x80000000;
    if ( ((unsigned int (__fastcall *)(__int64, _WORD *, __int64, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
           v5,
           v29,
           64,
           &v25)
      && v25 == 64 )
    {
      v9 = v29[0];
      *((_WORD *)a3 + 4108) = v29[0];
      *((_DWORD *)a3 + 2066) = *((_DWORD *)a2 + 636) != 0;
      *((_DWORD *)a3 + 2133) = *((_DWORD *)a2 + 84);
      v10 = (const WCHAR *)*((_QWORD *)a2 + 40);
      if ( v10 )
      {
        wcs2ansi(v10, (char *)a3 + 8268, 0x105u);
        v9 = v29[0];
      }
      *((_DWORD *)a3 + 2201) = *((_DWORD *)a2 + 83);
      v11 = (const WCHAR *)*((_QWORD *)a2 + 39);
      if ( v11 )
      {
        wcs2ansi(v11, (char *)a3 + 8536, 0x105u);
        v9 = v29[0];
      }
      *((_DWORD *)a3 + 2200) = *((_DWORD *)a2 + 82);
      if ( v9 == 23117 )
      {
        if ( ((unsigned int (__fastcall *)(_QWORD, int *, __int64, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
               *((_QWORD *)a3 + 513) + v30,
               &v31,
               248,
               &v25)
          && v25 == 248 )
        {
          v12 = v31 == 17744;
          *((_DWORD *)a3 + 2053) = v32[0];
          *((_QWORD *)a3 + 1030) = v33;
          if ( !v12 )
          {
            if ( v34 != 263 )
            {
              v6 = "Unknown NT Image signature\n";
              goto LABEL_3;
            }
            *((_DWORD *)a3 + 2062) = 0;
            gImageFileHdr = (__int64)v32;
            v13 = (char *)v32;
            *((_DWORD *)a3 + 2063) = v35;
            goto LABEL_28;
          }
          if ( v34 != 523 )
          {
            v13 = (char *)v32;
            v14 = v39;
            *((_DWORD *)a3 + 2063) = v36;
            *((_DWORD *)a3 + 2062) = v37;
            v15 = v38;
            goto LABEL_27;
          }
          if ( ((unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
                 *((_QWORD *)a3 + 513) + v30,
                 v40,
                 264,
                 &v25)
            && v25 == 264 )
          {
            v13 = &v41;
            v14 = v45;
            *((_DWORD *)a3 + 2062) = v43;
            *((_DWORD *)a3 + 2063) = v42;
            v15 = v44;
LABEL_27:
            *((_QWORD *)a3 + 1028) = *((_QWORD *)a3 + 513) + v15;
            gImageFileHdr = (__int64)v13;
            *((_DWORD *)a3 + 2058) = v14 / 0x1C;
LABEL_28:
            *((_DWORD *)a3 + 2064) = *((unsigned __int16 *)v13 + 9);
            v18 = *((unsigned __int16 *)v13 + 1);
            gNumSections = *((unsigned __int16 *)v13 + 1);
            v19 = malloc(40 * v18);
            gSectionHdrs = v19;
            if ( !v19 )
            {
              v6 = "Cannot allocate memory for reading sections\n";
              goto LABEL_3;
            }
            gSectionHdrsAddr = *((_QWORD *)a3 + 513)
                             + 24LL
                             + v30
                             + (unsigned __int64)*(unsigned __int16 *)(gImageFileHdr + 16);
            if ( ((unsigned int (__fastcall *)(__int64, void *, _QWORD, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
                   gSectionHdrsAddr,
                   v19,
                   (unsigned int)(40 * gNumSections),
                   &v25) )
            {
              if ( v25 != 40LL * (unsigned int)gNumSections )
              {
                ExtensionApis.lpOutputRoutine("\n***\n*** Some section headers may be missing ***\n***\n\n");
                gNumSections = (unsigned __int16)(v25 / 0x28);
              }
            }
            else
            {
              ExtensionApis.lpOutputRoutine("Can't read section headers\n");
            }
            goto LABEL_39;
          }
        }
        v16 = "Cannot read Image NT header @ %p\n";
        v17 = *((_QWORD *)a3 + 513) + v30;
LABEL_47:
        ExtensionApis.lpOutputRoutine(v16, v17);
        return 0;
      }
      if ( v9 != 18756 )
      {
        v6 = "Unknown image\n";
        goto LABEL_3;
      }
      if ( ((unsigned int (__fastcall *)(_QWORD, __int128 *, __int64, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
             *((_QWORD *)a3 + 513),
             &v26,
             48,
             &v25)
        && v25 == 48 )
      {
        *((_DWORD *)a3 + 2053) = WORD2(v26);
        *((_QWORD *)a3 + 1030) = DWORD2(v26);
        *((_DWORD *)a3 + 2062) = HIDWORD(v26);
        *((_DWORD *)a3 + 2063) = DWORD1(v27);
        *((_DWORD *)a3 + 2064) = WORD3(v26);
        if ( (_DWORD)v28 )
        {
          v20 = DWORD2(v27);
          *((_DWORD *)a3 + 2058) = (unsigned int)v28 / 0x1C;
          *((_QWORD *)a3 + 1028) = HIDWORD(v27) + 8 * (5 * v20 + 6);
        }
LABEL_39:
        v21 = (char *)a3 + 8812;
        v22 = 6;
        *((_DWORD *)a3 + 2202) = *((_DWORD *)a2 + 596);
        v23 = (_OWORD *)((char *)a2 + 19888);
        do
        {
          *(_OWORD *)v21 = *v23;
          *((_OWORD *)v21 + 1) = v23[1];
          *((_OWORD *)v21 + 2) = v23[2];
          *((_OWORD *)v21 + 3) = v23[3];
          *((_OWORD *)v21 + 4) = v23[4];
          *((_OWORD *)v21 + 5) = v23[5];
          *((_OWORD *)v21 + 6) = v23[6];
          v24 = v23[7];
          v23 += 8;
          *((_OWORD *)v21 + 7) = v24;
          v21 += 128;
          --v22;
        }
        while ( v22 );
        *(_OWORD *)v21 = *v23;
        *((_OWORD *)v21 + 1) = v23[1];
        *((_DWORD *)v21 + 8) = *((_DWORD *)v23 + 8);
        if ( *((_QWORD *)a2 + 2434) )
          diaGetCompilerInfo((struct _PROCESS_ENTRY *)v21, a2, (struct MODULE_INFO *)((char *)a3 + 9616));
        return 1;
      }
      v16 = "Cannot read Image Debug header @ %p\n";
    }
    else
    {
      v16 = "Cannot read Image header @ %p\n";
    }
    v17 = *((_QWORD *)a3 + 513);
    goto LABEL_47;
  }
  v6 = "Module does not have base address\n";
LABEL_3:
  ExtensionApis.lpOutputRoutine(v6);
  return 0;
}

```

## disassembly

```asm
0x180199ba0  mov     [rsp-8+arg_0], rbx
0x180199ba5  mov     [rsp-8+arg_18], rdi
0x180199baa  push    rbp
0x180199bab  lea     rbp, [rsp-1D0h]
0x180199bb3  sub     rsp, 2D0h
0x180199bba  mov     rax, cs:__security_cookie
0x180199bc1  xor     rax, rsp
0x180199bc4  mov     [rbp+1D0h+var_10], rax
0x180199bcb  xorps   xmm0, xmm0
0x180199bce  mov     [rsp+2D0h+var_2A0], 0
0x180199bd6  mov     rdi, rdx
0x180199bd9  lea     rcx, [rsp+2D0h+var_260]; void *
0x180199bde  xor     edx, edx; Val
0x180199be0  mov     rbx, r8
0x180199be3  movups  [rsp+2D0h+var_298], xmm0
0x180199be8  movups  [rsp+2D0h+var_288], xmm0
0x180199bed  lea     r8d, [rdx+40h]; Size
0x180199bf1  movups  [rsp+2D0h+var_278], xmm0
0x180199bf6  call    memset_0
0x180199bfb  xor     edx, edx; Val
0x180199bfd  lea     rcx, [rbp+1D0h+var_220]; void *
0x180199c01  mov     r8d, 0F8h; Size
0x180199c07  call    memset_0
0x180199c0c  xor     edx, edx; Val
0x180199c0e  lea     rcx, [rbp+1D0h+var_120]; void *
0x180199c15  mov     r8d, 108h; Size
0x180199c1b  call    memset_0
0x180199c20  xor     edx, edx; Val
0x180199c22  mov     r8d, 25B8h; Size
0x180199c28  mov     rcx, rbx; void *
0x180199c2b  call    memset_0
0x180199c30  lea     rcx, [rdi+2Eh]; lpWideCharStr
0x180199c34  mov     r8d, 1002h; unsigned int
0x180199c3a  mov     rdx, rbx; char *
0x180199c3d  call    ?wcs2ansi@@YAHPEBGPEADK@Z; wcs2ansi(ushort const *,char *,ulong)
0x180199c42  mov     rax, [rdi+18h]
0x180199c46  lea     rdx, [rbx+1010h]; char *
0x180199c4d  mov     [rbx+1008h], rax
0x180199c54  mov     r8d, 1002h; unsigned int
0x180199c5a  mov     rcx, [rdi+130h]; lpWideCharStr
0x180199c61  call    ?wcs2ansi@@YAHPEBGPEADK@Z; wcs2ansi(ushort const *,char *,ulong)
0x180199c66  mov     rcx, [rbx+1008h]
0x180199c6d  test    rcx, rcx
0x180199c70  jnz     short loc_180199C8A
0x180199c72  lea     rcx, aModuleDoesNotH; "Module does not have base address\n"
0x180199c79  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180199c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199c85  jmp     loc_18019A17C
0x180199c8a  mov     eax, [rdi+95Ch]
0x180199c90  mov     [rbx+202Ch], eax
0x180199c96  mov     eax, [rdi+4C0Ch]
0x180199c9c  mov     [rbx+2044h], eax
0x180199ca2  mov     eax, [rdi+95Ch]
0x180199ca8  cmp     eax, 8
0x180199cab  jnz     short loc_180199CB7
0x180199cad  mov     eax, 1
0x180199cb2  jmp     loc_18019A17E
0x180199cb7  cmp     eax, 5
0x180199cba  jnz     short loc_180199CC6
0x180199cbc  mov     dword ptr [rbx+2044h], 80000000h
0x180199cc6  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180199ccd  lea     r9, [rsp+2D0h+var_2A0]
0x180199cd2  mov     r8d, 40h ; '@'
0x180199cd8  lea     rdx, [rsp+2D0h+var_260]
0x180199cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199ce2  test    eax, eax
0x180199ce4  jz      loc_18019A162
0x180199cea  cmp     [rsp+2D0h+var_2A0], 40h ; '@'
0x180199cef  jnz     loc_18019A162
0x180199cf5  movzx   edx, [rsp+2D0h+var_260]
0x180199cfa  xor     eax, eax
0x180199cfc  mov     [rbx+2018h], dx
0x180199d03  cmp     [rdi+9F0h], eax
0x180199d09  setnz   al
0x180199d0c  mov     [rbx+2048h], eax
0x180199d12  mov     eax, [rdi+150h]
0x180199d18  mov     [rbx+2154h], eax
0x180199d1e  mov     rcx, [rdi+140h]; lpWideCharStr
0x180199d25  test    rcx, rcx
0x180199d28  jz      short loc_180199D41
0x180199d2a  lea     rdx, [rbx+204Ch]; char *
0x180199d31  mov     r8d, 105h; unsigned int
0x180199d37  call    ?wcs2ansi@@YAHPEBGPEADK@Z; wcs2ansi(ushort const *,char *,ulong)
0x180199d3c  movzx   edx, [rsp+2D0h+var_260]
0x180199d41  mov     eax, [rdi+14Ch]
0x180199d47  mov     [rbx+2264h], eax
0x180199d4d  mov     rcx, [rdi+138h]; lpWideCharStr
0x180199d54  test    rcx, rcx
0x180199d57  jz      short loc_180199D70
0x180199d59  lea     rdx, [rbx+2158h]; char *
0x180199d60  mov     r8d, 105h; unsigned int
0x180199d66  call    ?wcs2ansi@@YAHPEBGPEADK@Z; wcs2ansi(ushort const *,char *,ulong)
0x180199d6b  movzx   edx, [rsp+2D0h+var_260]
0x180199d70  mov     eax, [rdi+148h]
0x180199d76  mov     [rbx+2260h], eax
0x180199d7c  mov     eax, 5A4Dh
0x180199d81  cmp     dx, ax
0x180199d84  jnz     loc_180199FED
0x180199d8a  movsxd  rcx, [rbp+1D0h+var_224]
0x180199d8e  lea     r9, [rsp+2D0h+var_2A0]
0x180199d93  add     rcx, [rbx+1008h]
0x180199d9a  lea     rdx, [rbp+1D0h+var_220]
0x180199d9e  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180199da5  mov     r8d, 0F8h
0x180199dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199db0  test    eax, eax
0x180199db2  jz      loc_180199E90
0x180199db8  cmp     [rsp+2D0h+var_2A0], 0F8h
0x180199dc0  jnz     loc_180199E90
0x180199dc6  cmp     [rbp+1D0h+var_220], 4550h
0x180199dcd  movzx   eax, [rbp+1D0h+var_21C]
0x180199dd1  mov     [rbx+2014h], eax
0x180199dd7  mov     eax, [rbp+1D0h+var_218]
0x180199dda  mov     [rbx+2030h], rax
0x180199de1  jz      short loc_180199E21
0x180199de3  mov     eax, 107h
0x180199de8  cmp     [rbp+1D0h+var_208], ax
0x180199dec  jnz     short loc_180199E15
0x180199dee  lea     rax, [rbp+1D0h+var_21C]
0x180199df2  mov     dword ptr [rbx+2038h], 0
0x180199dfc  mov     cs:gImageFileHdr, rax
0x180199e03  lea     r8, [rbp+1D0h+var_21C]
0x180199e07  mov     eax, [rbp+1D0h+var_204]
0x180199e0a  mov     [rbx+203Ch], eax
0x180199e10  jmp     loc_180199EF8
0x180199e15  lea     rcx, aUnknownNtImage; "Unknown NT Image signature\n"
0x180199e1c  jmp     loc_180199C79
0x180199e21  mov     eax, 20Bh
0x180199e26  cmp     [rbp+1D0h+var_208], ax
0x180199e2a  jnz     short loc_180199EA7
0x180199e2c  movsxd  rcx, [rbp+1D0h+var_224]
0x180199e30  lea     r9, [rsp+2D0h+var_2A0]
0x180199e35  add     rcx, [rbx+1008h]
0x180199e3c  lea     rdx, [rbp+1D0h+var_120]
0x180199e43  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180199e4a  mov     r8d, 108h
0x180199e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199e55  test    eax, eax
0x180199e57  jz      short loc_180199E90
0x180199e59  cmp     [rsp+2D0h+var_2A0], 108h
0x180199e61  jnz     short loc_180199E90
0x180199e63  mov     eax, [rbp+1D0h+var_C8]
0x180199e69  lea     r8, [rbp+1D0h+var_11C]
0x180199e70  mov     ecx, [rbp+1D0h+var_64]
0x180199e76  mov     [rbx+2038h], eax
0x180199e7c  mov     eax, [rbp+1D0h+var_D0]
0x180199e82  mov     [rbx+203Ch], eax
0x180199e88  mov     eax, [rbp+1D0h+var_68]
0x180199e8e  jmp     short loc_180199EC3
0x180199e90  movsxd  rdx, [rbp+1D0h+var_224]
0x180199e94  lea     rcx, aCannotReadImag_0; "Cannot read Image NT header @ %p\n"
0x180199e9b  add     rdx, [rbx+1008h]
0x180199ea2  jmp     loc_18019A170
0x180199ea7  mov     eax, [rbp+1D0h+var_1D0]
0x180199eaa  lea     r8, [rbp+1D0h+var_21C]
0x180199eae  mov     ecx, [rbp+1D0h+var_174]
0x180199eb1  mov     [rbx+203Ch], eax
0x180199eb7  mov     eax, [rbp+1D0h+var_1C8]
0x180199eba  mov     [rbx+2038h], eax
0x180199ec0  mov     eax, [rbp+1D0h+var_178]
0x180199ec3  add     rax, [rbx+1008h]
0x180199eca  mov     [rbx+2020h], rax
0x180199ed1  mov     rax, 2492492492492493h
0x180199edb  mul     rcx
0x180199ede  mov     cs:gImageFileHdr, r8
0x180199ee5  sub     rcx, rdx
0x180199ee8  shr     rcx, 1
0x180199eeb  add     rcx, rdx
0x180199eee  shr     rcx, 4
0x180199ef2  mov     [rbx+2028h], ecx
0x180199ef8  movzx   eax, word ptr [r8+12h]
0x180199efd  mov     [rbx+2040h], eax
0x180199f03  movzx   eax, word ptr [r8+2]
0x180199f08  mov     cs:gNumSections, eax
0x180199f0e  lea     rcx, [rax+rax*4]
0x180199f12  shl     rcx, 3; Size
0x180199f16  call    cs:__imp_malloc
0x180199f1c  mov     cs:gSectionHdrs, rax
0x180199f23  mov     r10, rax
0x180199f26  test    rax, rax
0x180199f29  jnz     short loc_180199F37
0x180199f2b  lea     rcx, aCannotAllocate_0; "Cannot allocate memory for reading sect"...
0x180199f32  jmp     loc_180199C79
0x180199f37  mov     rax, cs:gImageFileHdr
0x180199f3e  lea     r9, [rsp+2D0h+var_2A0]
0x180199f43  mov     edx, cs:gNumSections
0x180199f49  movzx   ecx, word ptr [rax+10h]
0x180199f4d  movsxd  rax, [rbp+1D0h+var_224]
0x180199f51  lea     r8d, [rdx+rdx*4]
0x180199f55  add     rcx, rax
0x180199f58  shl     r8d, 3
0x180199f5c  mov     rax, [rbx+1008h]
0x180199f63  mov     rdx, r10
0x180199f66  add     rax, 18h
0x180199f6a  add     rcx, rax
0x180199f6d  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180199f74  mov     cs:gSectionHdrsAddr, rcx
0x180199f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199f80  test    eax, eax
0x180199f82  jnz     short loc_180199F9C
0x180199f84  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180199f8b  lea     rcx, aCanTReadSectio; "Can't read section headers\n"
0x180199f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199f97  jmp     loc_18019A0AB
0x180199f9c  mov     eax, cs:gNumSections
0x180199fa2  lea     rcx, [rax+rax*4]
0x180199fa6  mov     eax, [rsp+2D0h+var_2A0]
0x180199faa  shl     rcx, 3
0x180199fae  cmp     rax, rcx
0x180199fb1  jz      loc_18019A0AB
0x180199fb7  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180199fbe  lea     rcx, aSomeSectionHea; "\n***\n*** Some section headers may be "...
0x180199fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199fca  mov     ecx, [rsp+2D0h+var_2A0]
0x180199fce  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180199fd8  mul     rcx
0x180199fdb  shr     rdx, 5
0x180199fdf  movzx   eax, dx
0x180199fe2  mov     cs:gNumSections, eax
0x180199fe8  jmp     loc_18019A0AB
0x180199fed  mov     eax, 4944h
0x180199ff2  cmp     dx, ax
0x180199ff5  jnz     loc_18019A156
0x180199ffb  mov     rcx, [rbx+1008h]
0x18019a002  lea     r9, [rsp+2D0h+var_2A0]
0x18019a007  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x18019a00e  lea     rdx, [rsp+2D0h+var_298]
0x18019a013  mov     r8d, 30h ; '0'
0x18019a019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a01e  test    eax, eax
0x18019a020  jz      loc_18019A14D
0x18019a026  cmp     [rsp+2D0h+var_2A0], 30h ; '0'
0x18019a02b  jnz     loc_18019A14D
0x18019a031  movzx   eax, word ptr [rsp+2D0h+var_298+4]
0x18019a036  mov     [rbx+2014h], eax
0x18019a03c  mov     eax, dword ptr [rsp+2D0h+var_298+8]
0x18019a040  mov     [rbx+2030h], rax
0x18019a047  mov     eax, dword ptr [rsp+2D0h+var_298+0Ch]
0x18019a04b  mov     [rbx+2038h], eax
0x18019a051  mov     eax, dword ptr [rsp+2D0h+var_288+4]
0x18019a055  mov     [rbx+203Ch], eax
0x18019a05b  movzx   eax, word ptr [rsp+2D0h+var_298+6]
0x18019a060  mov     [rbx+2040h], eax
0x18019a066  mov     eax, dword ptr [rsp+2D0h+var_278]
0x18019a06a  test    eax, eax
0x18019a06c  jz      short loc_18019A0AB
0x18019a06e  mov     ecx, eax
0x18019a070  mov     rax, 2492492492492493h
0x18019a07a  mul     rcx
0x18019a07d  mov     eax, dword ptr [rsp+2D0h+var_288+8]
0x18019a081  sub     rcx, rdx
0x18019a084  shr     rcx, 1
0x18019a087  add     rcx, rdx
0x18019a08a  shr     rcx, 4
0x18019a08e  mov     [rbx+2028h], ecx
0x18019a094  lea     rcx, [rax+rax*4]
0x18019a098  mov     eax, dword ptr [rsp+2D0h+var_288+0Ch]
0x18019a09c  lea     rcx, [rcx+6]
0x18019a0a0  lea     rcx, [rax+rcx*8]
0x18019a0a4  mov     [rbx+2020h], rcx
0x18019a0ab  mov     eax, [rdi+950h]
0x18019a0b1  lea     rcx, [rbx+226Ch]
0x18019a0b8  mov     edx, 6
0x18019a0bd  mov     [rbx+2268h], eax
0x18019a0c3  lea     rax, [rdi+4DB0h]
0x18019a0ca  lea     r8d, [rdx+7Ah]
0x18019a0ce  movups  xmm0, xmmword ptr [rax]
0x18019a0d1  movups  xmmword ptr [rcx], xmm0
0x18019a0d4  movups  xmm1, xmmword ptr [rax+10h]
0x18019a0d8  movups  xmmword ptr [rcx+10h], xmm1
0x18019a0dc  movups  xmm0, xmmword ptr [rax+20h]
0x18019a0e0  movups  xmmword ptr [rcx+20h], xmm0
0x18019a0e4  movups  xmm1, xmmword ptr [rax+30h]
0x18019a0e8  movups  xmmword ptr [rcx+30h], xmm1
0x18019a0ec  movups  xmm0, xmmword ptr [rax+40h]
0x18019a0f0  movups  xmmword ptr [rcx+40h], xmm0
0x18019a0f4  movups  xmm1, xmmword ptr [rax+50h]
0x18019a0f8  movups  xmmword ptr [rcx+50h], xmm1
0x18019a0fc  movups  xmm0, xmmword ptr [rax+60h]
0x18019a100  movups  xmmword ptr [rcx+60h], xmm0
0x18019a104  movups  xmm1, xmmword ptr [rax+70h]
0x18019a108  add     rax, r8
0x18019a10b  movups  xmmword ptr [rcx+70h], xmm1
0x18019a10f  add     rcx, r8; struct _PROCESS_ENTRY *
0x18019a112  sub     rdx, 1
0x18019a116  jnz     short loc_18019A0CE
0x18019a118  movups  xmm0, xmmword ptr [rax]
0x18019a11b  movups  xmmword ptr [rcx], xmm0
0x18019a11e  movups  xmm1, xmmword ptr [rax+10h]
0x18019a122  movups  xmmword ptr [rcx+10h], xmm1
0x18019a126  mov     eax, [rax+20h]
0x18019a129  mov     [rcx+20h], eax
0x18019a12c  cmp     [rdi+4C10h], rdx
0x18019a133  jz      loc_180199CAD
0x18019a139  lea     r8, [rbx+2590h]; struct _COMPILERINFO *
0x18019a140  mov     rdx, rdi; struct _MODULE_ENTRY *
0x18019a143  call    ?diaGetCompilerInfo@@YAHPEAU_PROCESS_ENTRY@@PEAU_MODULE_ENTRY@@PEAU_COMPILERINFO@@@Z; diaGetCompilerInfo(_PROCESS_ENTRY *,_MODULE_ENTRY *,_COMPILERINFO *)
0x18019a148  jmp     loc_180199CAD
0x18019a14d  lea     rcx, aCannotReadImag_1; "Cannot read Image Debug header @ %p\n"
0x18019a154  jmp     short loc_18019A169
  ... truncated ...
```
