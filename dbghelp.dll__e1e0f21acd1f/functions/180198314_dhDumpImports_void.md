# dhDumpImports(void)

- ea: `0x180198314`
- end: `0x18019886a`
- name: `?dhDumpImports@@YAXXZ`
- size: `1366`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180198058`

## callees

- `0x180196c7c`
- `0x180198314`
- `0x180198e6c`
- `0x1801d6350`
- `0x180205010`

## string_xrefs

- `0x180198656`: `Could not read IMAGE_DELAYLOAD_DESCRIPTOR at %p\n`
- `0x180198420`: `  _IMAGE_DELAYLOAD_DESCRIPTOR %p\n`
- `0x18019843c`: `This is not a v2 delay load descriptor, so it can't be dumped\n`
- `0x18019883b`: `Could not read import at %p\n`
- `0x18019870d`: `  _IMAGE_IMPORT_DESCRIPTOR %p\n`

## pseudocode

```c
void dhDumpImports(void)
{
  __int64 v0; // rax
  char v1; // r12
  __int64 v2; // r14
  __int64 v3; // rdx
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rcx
  __int64 v6; // r15
  unsigned int v7; // r13d
  PWINDBG_OUTPUT_ROUTINE lpOutputRoutine; // rbx
  const char *v9; // rax
  __int64 v10; // rbx
  const char *v11; // rdi
  PWINDBG_OUTPUT_ROUTINE v12; // rsi
  const char *v13; // rax
  __int64 v14; // rbx
  const char *v15; // rdi
  PWINDBG_OUTPUT_ROUTINE v16; // rsi
  const char *v17; // rax
  __int64 v18; // rbx
  const char *v19; // rdi
  PWINDBG_OUTPUT_ROUTINE v20; // rsi
  const char *v21; // rax
  __int64 v22; // rbx
  const char *v23; // rdi
  PWINDBG_OUTPUT_ROUTINE v24; // rsi
  const char *v25; // rax
  __int64 v26; // rbx
  const char *v27; // rdi
  PWINDBG_OUTPUT_ROUTINE v28; // rsi
  const char *v29; // rax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rdi
  __int64 v32; // r15
  const char *v33; // rdi
  __int64 v34; // rbx
  PWINDBG_OUTPUT_ROUTINE v35; // rsi
  const char *v36; // rax
  const char *v37; // rdi
  __int64 v38; // rbx
  PWINDBG_OUTPUT_ROUTINE v39; // rsi
  const char *v40; // rax
  __int64 v41; // rbx
  unsigned __int64 v42; // rbx
  unsigned __int64 v43; // rdi
  int v44; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v45; // [rsp+38h] [rbp-31h]
  __int128 v46; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-19h]
  __int128 v48; // [rsp+58h] [rbp-11h] BYREF
  __int128 v49; // [rsp+68h] [rbp-1h]

  v44 = 0;
  v47 = 0;
  v0 = gImageOptionalHdr;
  v1 = 1;
  v2 = gImage64 != 0 ? 8LL : 4LL;
  v3 = *(unsigned int *)(gImageOptionalHdr + 216);
  v48 = 0;
  v49 = 0;
  v46 = 0;
  if ( v3 && (v4 = *(unsigned int *)(gImageOptionalHdr + 220), (_DWORD)v4) )
  {
    v5 = v4 >> 3;
    v6 = v3 + gBase;
    v7 = 0;
    v45 = v5;
    while ( 1 )
    {
      if ( v7 >= v5 )
        goto LABEL_30;
      if ( ExtensionApis.lpCheckControlCRoutine() )
        return;
      if ( !((unsigned int (__fastcall *)(__int64, __int128 *, __int64, int *))ExtensionApis.lpReadProcessMemoryRoutine)(
              v6,
              &v48,
              32,
              &v44) )
      {
        ExtensionApis.lpOutputRoutine("Could not read IMAGE_DELAYLOAD_DESCRIPTOR at %p\n", v6);
LABEL_30:
        v0 = gImageOptionalHdr;
        goto LABEL_31;
      }
      if ( !DWORD1(v48) )
        goto LABEL_30;
      if ( v1 )
        v1 = 0;
      else
        ExtensionApis.lpOutputRoutine("\n");
      ExtensionApis.lpOutputRoutine("  _IMAGE_DELAYLOAD_DESCRIPTOR %p\n", v6);
      if ( (v48 & 1) != 0 )
        break;
      ExtensionApis.lpOutputRoutine("This is not a v2 delay load descriptor, so it can't be dumped\n");
LABEL_28:
      v5 = v45;
      ++v7;
    }
    ExtensionApis.lpOutputRoutine("    %ma\n", gBase + DWORD1(v48));
    lpOutputRoutine = ExtensionApis.lpOutputRoutine;
    v9 = dhAdjustFmtStr("              %08X Characteristics\n");
    lpOutputRoutine(v9, (unsigned int)v48);
    v10 = gBase + DWORD2(v48);
    v11 = (const char *)&MultiByteStr;
    v12 = ExtensionApis.lpOutputRoutine;
    if ( !gImage64 )
      v11 = "        ";
    v13 = dhAdjustFmtStr("      %s%p Address of HMODULE\n");
    v12(v13, v11, v10);
    v14 = gBase + HIDWORD(v48);
    v15 = (const char *)&MultiByteStr;
    v16 = ExtensionApis.lpOutputRoutine;
    if ( !gImage64 )
      v15 = "        ";
    v17 = dhAdjustFmtStr("      %s%p Import Address Table\n");
    v16(v17, v15, v14);
    v18 = gBase + (unsigned int)v49;
    v19 = (const char *)&MultiByteStr;
    v20 = ExtensionApis.lpOutputRoutine;
    if ( !gImage64 )
      v19 = "        ";
    v21 = dhAdjustFmtStr("      %s%p Import Name Table\n");
    v20(v21, v19, v18);
    v22 = gBase + DWORD1(v49);
    v23 = (const char *)&MultiByteStr;
    v24 = ExtensionApis.lpOutputRoutine;
    if ( !gImage64 )
      v23 = "        ";
    v25 = dhAdjustFmtStr("      %s%p Bound Import Name Table\n");
    v24(v25, v23, v22);
    v26 = gBase + DWORD2(v49);
    v27 = (const char *)&MultiByteStr;
    v28 = ExtensionApis.lpOutputRoutine;
    if ( !gImage64 )
      v27 = "        ";
    v29 = dhAdjustFmtStr("      %s%p Unload Import Name Table\n");
    v28(v29, v27, v26);
    ExtensionApis.lpOutputRoutine("              %8X time date stamp\n\n", HIDWORD(v49));
    v30 = gBase + (unsigned int)v49;
    v31 = gBase + HIDWORD(v48);
    while ( !ExtensionApis.lpCheckControlCRoutine() )
    {
      if ( !dhPrintThunk(v30, v31, 1u) )
      {
        v6 += 32;
        goto LABEL_28;
      }
      v30 += v2;
      v31 += v2;
    }
  }
  else
  {
LABEL_31:
    if ( *(_DWORD *)(v0 + 124) )
    {
      v32 = gBase + *(unsigned int *)(v0 + 120);
LABEL_34:
      if ( !ExtensionApis.lpCheckControlCRoutine() )
      {
        if ( v1 )
          v1 = 0;
        else
          ExtensionApis.lpOutputRoutine("\n");
        if ( ((unsigned int (__fastcall *)(__int64, __int128 *, __int64, int *))ExtensionApis.lpReadProcessMemoryRoutine)(
               v32,
               &v46,
               20,
               &v44) )
        {
          if ( HIDWORD(v46) && v47 )
          {
            ExtensionApis.lpOutputRoutine("  _IMAGE_IMPORT_DESCRIPTOR %p\n", v32);
            ExtensionApis.lpOutputRoutine("    %ma\n", gBase + HIDWORD(v46));
            v33 = (const char *)&MultiByteStr;
            v34 = gBase + v47;
            v35 = ExtensionApis.lpOutputRoutine;
            if ( !gImage64 )
              v33 = "        ";
            v36 = dhAdjustFmtStr("      %s%p Import Address Table\n");
            v35(v36, v33, v34);
            v37 = (const char *)&MultiByteStr;
            v38 = gBase + (unsigned int)v46;
            v39 = ExtensionApis.lpOutputRoutine;
            if ( !gImage64 )
              v37 = "        ";
            v40 = dhAdjustFmtStr("      %s%p Import Name Table\n");
            v39(v40, v37, v38);
            ExtensionApis.lpOutputRoutine("              %8X time date stamp\n", DWORD1(v46));
            ExtensionApis.lpOutputRoutine("              %8X Index of first forwarder reference\n\n", DWORD2(v46));
            v41 = v47;
            if ( (_DWORD)v46 )
              v41 = (unsigned int)v46;
            v42 = gBase + v41;
            v43 = v47 + gBase;
            while ( !ExtensionApis.lpCheckControlCRoutine() )
            {
              if ( !dhPrintThunk(v42, v43, 0) )
              {
                v32 += 20;
                goto LABEL_34;
              }
              v42 += v2;
              v43 += v2;
            }
          }
        }
        else
        {
          ExtensionApis.lpOutputRoutine("Could not read import at %p\n", v32);
        }
      }
    }
    else
    {
      ExtensionApis.lpOutputRoutine("No imports\n");
    }
  }
}

```

## disassembly

```asm
0x180198314  push    rbp
0x180198316  push    rbx
0x180198317  push    rsi
0x180198318  push    rdi
0x180198319  push    r12
0x18019831b  push    r13
0x18019831d  push    r14
0x18019831f  push    r15
0x180198321  lea     rbp, [rsp-1Fh]
0x180198326  sub     rsp, 88h
0x18019832d  mov     rax, cs:__security_cookie
0x180198334  xor     rax, rsp
0x180198337  mov     [rbp+57h+var_48], rax
0x18019833b  xor     eax, eax
0x18019833d  mov     [rbp+57h+var_90], 0
0x180198344  mov     [rbp+57h+var_70], eax
0x180198347  lea     r13, asc_1802524A8; "        "
0x18019834e  mov     al, cs:gImage64
0x180198354  xorps   xmm0, xmm0
0x180198357  neg     al
0x180198359  xorps   xmm1, xmm1
0x18019835c  mov     rax, cs:gImageOptionalHdr
0x180198363  mov     r12b, 1
0x180198366  sbb     r14, r14
0x180198369  and     r14d, 4
0x18019836d  add     r14, 4
0x180198371  mov     edx, [rax+0D8h]
0x180198377  movups  [rbp+57h+var_68], xmm0
0x18019837b  movups  [rbp+57h+var_58], xmm0
0x18019837f  movups  [rbp+57h+var_80], xmm1
0x180198383  test    rdx, rdx
0x180198386  jz      loc_180198673
0x18019838c  mov     ecx, [rax+0DCh]
0x180198392  test    ecx, ecx
0x180198394  jz      loc_180198673
0x18019839a  mov     r15, cs:gBase
0x1801983a1  shr     rcx, 3
0x1801983a5  add     r15, rdx
0x1801983a8  xor     r13d, r13d
0x1801983ab  mov     [rbp+57h+var_88], rcx
0x1801983af  mov     eax, r13d
0x1801983b2  cmp     rax, rcx
0x1801983b5  jnb     loc_180198665
0x1801983bb  mov     rax, cs:ExtensionApis.lpCheckControlCRoutine
0x1801983c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801983c7  test    eax, eax
0x1801983c9  jnz     loc_18019884A
0x1801983cf  lea     r8d, [rax+20h]
0x1801983d3  mov     rcx, r15
0x1801983d6  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x1801983dd  lea     r9, [rbp+57h+var_90]
0x1801983e1  lea     rdx, [rbp+57h+var_68]
0x1801983e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801983ea  test    eax, eax
0x1801983ec  jz      loc_18019864F
0x1801983f2  cmp     dword ptr [rbp+57h+var_68+4], 0
0x1801983f6  jz      loc_180198665
0x1801983fc  test    r12b, r12b
0x1801983ff  jz      short loc_180198406
0x180198401  xor     r12b, r12b
0x180198404  jmp     short loc_180198419
0x180198406  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019840d  lea     rcx, asc_18022B9A8; "\n"
0x180198414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198419  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198420  lea     rcx, aImageDelayload; "  _IMAGE_DELAYLOAD_DESCRIPTOR %p\n"
0x180198427  mov     rdx, r15
0x18019842a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019842f  test    byte ptr [rbp+57h+var_68], 1
0x180198433  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019843a  jnz     short loc_18019844D
0x18019843c  lea     rcx, aThisIsNotAV2De; "This is not a v2 delay load descriptor,"...
0x180198443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198448  jmp     loc_180198643
0x18019844d  mov     edx, dword ptr [rbp+57h+var_68+4]
0x180198450  lea     rcx, aMa; "    %ma\n"
0x180198457  add     rdx, cs:gBase
0x18019845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198463  mov     rbx, cs:ExtensionApis.lpOutputRoutine
0x18019846a  lea     rcx, a08xCharacteris; "              %08X Characteristics\n"
0x180198471  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x180198476  mov     edx, dword ptr [rbp+57h+var_68]
0x180198479  mov     rcx, rax
0x18019847c  mov     rax, rbx
0x18019847f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198484  mov     ebx, dword ptr [rbp+57h+var_68+8]
0x180198487  lea     rax, asc_1802524A8; "        "
0x18019848e  add     rbx, cs:gBase
0x180198495  lea     rdi, MultiByteStr
0x18019849c  cmp     cs:gImage64, 0
0x1801984a3  lea     rcx, aSPAddressOfHmo; "      %s%p Address of HMODULE\n"
0x1801984aa  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x1801984b1  cmovz   rdi, rax
0x1801984b5  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x1801984ba  mov     rcx, rax
0x1801984bd  mov     r8, rbx
0x1801984c0  mov     rax, rsi
0x1801984c3  mov     rdx, rdi
0x1801984c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801984cb  mov     ebx, dword ptr [rbp+57h+var_68+0Ch]
0x1801984ce  lea     rax, asc_1802524A8; "        "
0x1801984d5  add     rbx, cs:gBase
0x1801984dc  lea     rdi, MultiByteStr
0x1801984e3  cmp     cs:gImage64, 0
0x1801984ea  lea     rcx, aSPImportAddres; "      %s%p Import Address Table\n"
0x1801984f1  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x1801984f8  cmovz   rdi, rax
0x1801984fc  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x180198501  mov     rcx, rax
0x180198504  mov     r8, rbx
0x180198507  mov     rax, rsi
0x18019850a  mov     rdx, rdi
0x18019850d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198512  mov     ebx, dword ptr [rbp+57h+var_58]
0x180198515  lea     rax, asc_1802524A8; "        "
0x18019851c  add     rbx, cs:gBase
0x180198523  lea     rdi, MultiByteStr
0x18019852a  cmp     cs:gImage64, 0
0x180198531  lea     rcx, aSPImportNameTa; "      %s%p Import Name Table\n"
0x180198538  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x18019853f  cmovz   rdi, rax
0x180198543  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x180198548  mov     rcx, rax
0x18019854b  mov     r8, rbx
0x18019854e  mov     rax, rsi
0x180198551  mov     rdx, rdi
0x180198554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198559  mov     ebx, dword ptr [rbp+57h+var_58+4]
0x18019855c  lea     rax, asc_1802524A8; "        "
0x180198563  add     rbx, cs:gBase
0x18019856a  lea     rdi, MultiByteStr
0x180198571  cmp     cs:gImage64, 0
0x180198578  lea     rcx, aSPBoundImportN; "      %s%p Bound Import Name Table\n"
0x18019857f  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x180198586  cmovz   rdi, rax
0x18019858a  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x18019858f  mov     rcx, rax
0x180198592  mov     r8, rbx
0x180198595  mov     rax, rsi
0x180198598  mov     rdx, rdi
0x18019859b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801985a0  mov     ebx, dword ptr [rbp+57h+var_58+8]
0x1801985a3  lea     rax, asc_1802524A8; "        "
0x1801985aa  add     rbx, cs:gBase
0x1801985b1  lea     rdi, MultiByteStr
0x1801985b8  cmp     cs:gImage64, 0
0x1801985bf  lea     rcx, aSPUnloadImport; "      %s%p Unload Import Name Table\n"
0x1801985c6  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x1801985cd  cmovz   rdi, rax
0x1801985d1  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x1801985d6  mov     rcx, rax
0x1801985d9  mov     r8, rbx
0x1801985dc  mov     rax, rsi
0x1801985df  mov     rdx, rdi
0x1801985e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801985e7  mov     edx, dword ptr [rbp+57h+var_58+0Ch]
0x1801985ea  lea     rcx, a8xTimeDateStam; "              %8X time date stamp\n\n"
0x1801985f1  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801985f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801985fd  mov     ebx, dword ptr [rbp+57h+var_58]
0x180198600  add     rbx, cs:gBase
0x180198607  mov     edi, dword ptr [rbp+57h+var_68+0Ch]
0x18019860a  add     rdi, cs:gBase
0x180198611  mov     rax, cs:ExtensionApis.lpCheckControlCRoutine
0x180198618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019861d  test    eax, eax
0x18019861f  jnz     loc_18019884A
0x180198625  mov     r8b, 1; unsigned __int8
0x180198628  mov     rdx, rdi; unsigned __int64
0x18019862b  mov     rcx, rbx; unsigned __int64
0x18019862e  call    ?dhPrintThunk@@YAH_K0E@Z; dhPrintThunk(unsigned __int64,unsigned __int64,uchar)
0x180198633  test    eax, eax
0x180198635  jz      short loc_18019863F
0x180198637  add     rbx, r14
0x18019863a  add     rdi, r14
0x18019863d  jmp     short loc_180198611
0x18019863f  add     r15, 20h ; ' '
0x180198643  mov     rcx, [rbp+57h+var_88]
0x180198647  inc     r13d
0x18019864a  jmp     loc_1801983AF
0x18019864f  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198656  lea     rcx, aCouldNotReadIm; "Could not read IMAGE_DELAYLOAD_DESCRIPT"...
0x18019865d  mov     rdx, r15
0x180198660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198665  mov     rax, cs:gImageOptionalHdr
0x18019866c  lea     r13, asc_1802524A8; "        "
0x180198673  cmp     dword ptr [rax+7Ch], 0
0x180198677  jnz     short loc_180198691
0x180198679  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198680  lea     rcx, aNoImports; "No imports\n"
0x180198687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019868c  jmp     loc_18019884A
0x180198691  mov     r15d, [rax+78h]
0x180198695  add     r15, cs:gBase
0x18019869c  mov     rax, cs:ExtensionApis.lpCheckControlCRoutine
0x1801986a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986a8  test    eax, eax
0x1801986aa  jnz     loc_18019884A
0x1801986b0  test    r12b, r12b
0x1801986b3  jz      short loc_1801986BA
0x1801986b5  xor     r12b, r12b
0x1801986b8  jmp     short loc_1801986CD
0x1801986ba  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801986c1  lea     rcx, asc_18022B9A8; "\n"
0x1801986c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986cd  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x1801986d4  lea     r9, [rbp+57h+var_90]
0x1801986d8  mov     r8d, 14h
0x1801986de  lea     rdx, [rbp+57h+var_80]
0x1801986e2  mov     rcx, r15
0x1801986e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986ea  test    eax, eax
0x1801986ec  jz      loc_180198834
0x1801986f2  cmp     dword ptr [rbp+57h+var_80+0Ch], 0
0x1801986f6  jz      loc_18019884A
0x1801986fc  cmp     [rbp+57h+var_70], 0
0x180198700  jz      loc_18019884A
0x180198706  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019870d  lea     rcx, aImageImportDes; "  _IMAGE_IMPORT_DESCRIPTOR %p\n"
0x180198714  mov     rdx, r15
0x180198717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019871c  mov     edx, dword ptr [rbp+57h+var_80+0Ch]
0x18019871f  lea     rcx, aMa; "    %ma\n"
0x180198726  add     rdx, cs:gBase
0x18019872d  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198739  mov     ebx, [rbp+57h+var_70]
0x18019873c  lea     rdi, MultiByteStr
0x180198743  add     rbx, cs:gBase
0x18019874a  lea     rcx, aSPImportAddres; "      %s%p Import Address Table\n"
0x180198751  cmp     cs:gImage64, 0
0x180198758  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x18019875f  cmovz   rdi, r13
0x180198763  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x180198768  mov     rcx, rax
0x18019876b  mov     r8, rbx
0x18019876e  mov     rax, rsi
0x180198771  mov     rdx, rdi
0x180198774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198779  mov     ebx, dword ptr [rbp+57h+var_80]
0x18019877c  lea     rdi, MultiByteStr
0x180198783  add     rbx, cs:gBase
0x18019878a  lea     rcx, aSPImportNameTa; "      %s%p Import Name Table\n"
0x180198791  cmp     cs:gImage64, 0
0x180198798  mov     rsi, cs:ExtensionApis.lpOutputRoutine
0x18019879f  cmovz   rdi, r13
0x1801987a3  call    ?dhAdjustFmtStr@@YAPEBDPEBD@Z; dhAdjustFmtStr(char const *)
0x1801987a8  mov     rcx, rax
0x1801987ab  mov     r8, rbx
0x1801987ae  mov     rax, rsi
0x1801987b1  mov     rdx, rdi
0x1801987b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801987b9  mov     edx, dword ptr [rbp+57h+var_80+4]
0x1801987bc  lea     rcx, a8xTimeDateStam_0; "              %8X time date stamp\n"
0x1801987c3  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801987ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801987cf  mov     edx, dword ptr [rbp+57h+var_80+8]
0x1801987d2  lea     rcx, a8xIndexOfFirst; "              %8X Index of first forwar"...
0x1801987d9  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801987e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801987e5  mov     eax, dword ptr [rbp+57h+var_80]
0x1801987e8  mov     ecx, [rbp+57h+var_70]
0x1801987eb  mov     ebx, ecx
0x1801987ed  test    eax, eax
0x1801987ef  jz      short loc_1801987F3
0x1801987f1  mov     ebx, eax
0x1801987f3  mov     rax, cs:gBase
0x1801987fa  add     rbx, rax
0x1801987fd  lea     rdi, [rcx+rax]
0x180198801  mov     rax, cs:ExtensionApis.lpCheckControlCRoutine
0x180198808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019880d  test    eax, eax
0x18019880f  jnz     short loc_18019884A
0x180198811  xor     r8d, r8d; unsigned __int8
0x180198814  mov     rdx, rdi; unsigned __int64
0x180198817  mov     rcx, rbx; unsigned __int64
0x18019881a  call    ?dhPrintThunk@@YAH_K0E@Z; dhPrintThunk(unsigned __int64,unsigned __int64,uchar)
0x18019881f  test    eax, eax
0x180198821  jz      short loc_18019882B
0x180198823  add     rbx, r14
0x180198826  add     rdi, r14
0x180198829  jmp     short loc_180198801
0x18019882b  add     r15, 14h
0x18019882f  jmp     loc_18019869C
0x180198834  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019883b  lea     rcx, aCouldNotReadIm_0; "Could not read import at %p\n"
0x180198842  mov     rdx, r15
0x180198845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019884a  mov     rcx, [rbp+57h+var_48]
0x18019884e  xor     rcx, rsp; StackCookie
0x180198851  call    __security_check_cookie
0x180198856  add     rsp, 88h
0x18019885d  pop     r15
0x18019885f  pop     r14
0x180198861  pop     r13
0x180198863  pop     r12
0x180198865  pop     rdi
0x180198866  pop     rsi
0x180198867  pop     rbx
0x180198868  pop     rbp
  ... truncated ...
```
