# dhDumpHeaders(void)

- ea: `0x1801977a4`
- end: `0x180198052`
- name: `?dhDumpHeaders@@YAXXZ`
- size: `2222`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180198058`

## callees

- `0x180027430`
- `0x1801977a4`
- `0x18019a934`
- `0x18019b9f0`
- `0x1801d6350`
- `0x180205010`

## string_xrefs

- `0x180197814`: `\nFile Type: DLL\n`
- `0x180197a3a`: `Can't read load config section\n`
- `0x180197c72`: `\nOPTIONAL HEADER VALUES\n%8hX magic #\n%8s linker version\n%8lX size of code\n%8lX size of initialized data\n%8lX size of uninitialized data\n%8lX address of entry point\n%8lX base of code\n`
- `0x180197eb3`: `%p size of stack reserve\n%p size of stack commit\n%p size of heap reserve\n%p size of heap commit\n`
- `0x180197ec6`: `%8lX  DLL characteristics\n`
- `0x180197f3b`: `NX compatible`
- `0x180197ff9`: `%8lX [%8lX] address [size] of %s Directory\n`

## pseudocode

```c
void dhDumpHeaders(void)
{
  PWINDBG_OUTPUT_ROUTINE lpOutputRoutine; // rax
  const char *v1; // rcx
  const char *v2; // rbx
  unsigned int v3; // edx
  unsigned int v4; // esi
  unsigned int v5; // eax
  unsigned int v6; // edi
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  char *v10; // rax
  __int64 v11; // rax
  char v12; // di
  unsigned int v13; // ebx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  const char *v20; // rdx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  char **v27; // rbx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  __int64 v33; // rdx
  char v34; // di
  unsigned int v35; // ebx
  int v36; // edx
  int v37; // edx
  int v38; // edx
  int v39; // edx
  int v40; // edx
  const char *v41; // rdx
  unsigned int v42; // ebx
  __int64 v43; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+20h] [rbp-E0h]
  __int64 v46; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+28h] [rbp-D8h]
  __int64 v48; // [rsp+30h] [rbp-D0h]
  __int64 v49; // [rsp+38h] [rbp-C8h]
  _DWORD v50[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v51[50]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+148h] [rbp+48h]
  char Buffer[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v54[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v55[32]; // [rsp+210h] [rbp+110h] BYREF

  if ( gdft == 1 )
  {
    lpOutputRoutine = ExtensionApis.lpOutputRoutine;
    v1 = "\nFile Type: COFF OBJECT\n";
  }
  else if ( gdft == 2 )
  {
    lpOutputRoutine = ExtensionApis.lpOutputRoutine;
    if ( (*(_WORD *)(gImageFileHdr + 18) & 0x2000) != 0 )
      v1 = "\nFile Type: DLL\n";
    else
      v1 = "\nFile Type: EXECUTABLE IMAGE\n";
  }
  else
  {
    lpOutputRoutine = ExtensionApis.lpOutputRoutine;
    if ( gdft == 3 )
      v1 = "\nFile Type: ROM IMAGE\n";
    else
      v1 = "\nFile Type: UNKNOWN\n";
  }
  lpOutputRoutine(v1, 0x2000);
  v2 = "Unknown";
  v3 = *(unsigned __int16 *)gImageFileHdr;
  if ( v3 > 0x1F2 )
  {
    switch ( v3 )
    {
      case 0x200u:
        v2 = "Intel IA64";
        break;
      case 0x284u:
        v2 = "Alpha AXP64";
        break;
      case 0x8664u:
        v2 = "X64";
        break;
      case 0xAA64u:
        v2 = "ARMv8 (64-bit)";
        break;
    }
  }
  else
  {
    switch ( v3 )
    {
      case 0x1F2u:
        v2 = "PowerPC Big-Endian 32-bit";
        break;
      case 0x14Cu:
        v2 = "i386";
        break;
      case 0x184u:
        v2 = "Alpha AXP";
        break;
      case 0x1C0u:
        v2 = "ARM 32-bit";
        break;
      case 0x1C2u:
        v2 = "ARM 32-bit (Thumb)";
        break;
      case 0x1C4u:
        v2 = "ARM NT (Thumb-2)";
        break;
    }
  }
  if ( (_WORD)v3 == 332 )
  {
    v4 = *(_DWORD *)(gImageOptionalHdr + 192);
    if ( !v4 )
      goto LABEL_52;
    v5 = *(_DWORD *)(gImageOptionalHdr + 196);
    if ( v5 < 0x80 )
      goto LABEL_52;
    v6 = 196;
    if ( v5 < 0xC4 )
      v6 = *(_DWORD *)(gImageOptionalHdr + 196);
    memset_0(v51, 0, 0xC4u);
    v50[0] = 0;
    if ( ((unsigned int (__fastcall *)(__int64, _DWORD *, _QWORD, _DWORD *))ExtensionApis.lpReadProcessMemoryRoutine)(
           gBase + v4,
           v51,
           v6,
           v50)
      && v50[0] == v6 )
    {
      if ( v51[0] >= 0x80u && v51[31] )
        v2 = "i386 (CHPE)";
      goto LABEL_52;
    }
LABEL_51:
    ExtensionApis.lpOutputRoutine("Can't read load config section\n");
    goto LABEL_52;
  }
  if ( (_WORD)v3 != 0x8664 )
    goto LABEL_52;
  v7 = *(_DWORD *)(gImageOptionalHdr + 192);
  if ( !v7 )
    goto LABEL_52;
  v8 = *(_DWORD *)(gImageOptionalHdr + 196);
  if ( v8 < 0xD0 )
    goto LABEL_52;
  v9 = 328;
  if ( v8 < 0x148 )
    v9 = *(_DWORD *)(gImageOptionalHdr + 196);
  memset_0(v51, 0, 0x148u);
  v50[0] = 0;
  if ( !((unsigned int (__fastcall *)(__int64, _DWORD *, _QWORD, _DWORD *))ExtensionApis.lpReadProcessMemoryRoutine)(
          gBase + v7,
          v51,
          v9,
          v50)
    || v50[0] != v9 )
  {
    goto LABEL_51;
  }
  if ( v51[0] >= 0xD0u && v52 )
    v2 = "X64 (CHPEv2)";
LABEL_52:
  ExtensionApis.lpOutputRoutine(
    "FILE HEADER VALUES\n%8hX machine (%s)\n%8hX number of sections\n%8lX time date stamp",
    *(unsigned __int16 *)gImageFileHdr,
    v2,
    *(unsigned __int16 *)(gImageFileHdr + 2),
    *(_DWORD *)(gImageFileHdr + 4));
  v10 = ctime((const time_t *const)(gImageFileHdr + 4));
  if ( v10 )
    ExtensionApis.lpOutputRoutine(" %s", v10);
  ExtensionApis.lpOutputRoutine("\n");
  LODWORD(v43) = *(unsigned __int16 *)(gImageFileHdr + 18);
  ExtensionApis.lpOutputRoutine(
    "%8lX file pointer to symbol table\n%8lX number of symbols\n%8hX size of optional header\n%8hX characteristics\n",
    *(unsigned int *)(gImageFileHdr + 8),
    *(unsigned int *)(gImageFileHdr + 12),
    *(unsigned __int16 *)(gImageFileHdr + 16),
    v43);
  v11 = gImageFileHdr;
  v12 = 0;
  v13 = *(unsigned __int16 *)(gImageFileHdr + 18);
  if ( *(_WORD *)(gImageFileHdr + 18) )
  {
    while ( 1 )
    {
      if ( (v13 & 1) != 0 )
      {
        v14 = 1 << v12;
        if ( 1 << v12 <= 256 )
        {
          if ( v14 == 256 )
          {
            v20 = "32 bit word machine";
          }
          else
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                v17 = v16 - 2;
                if ( v17 )
                {
                  v18 = v17 - 4;
                  if ( v18 )
                  {
                    v19 = v18 - 24;
                    if ( v19 )
                    {
                      if ( v19 == 96 )
                        v20 = "Bytes reversed";
                      else
LABEL_77:
                        v20 = "RESERVED - UNKNOWN";
                    }
                    else
                    {
                      v20 = "App can handle >2gb addresses";
                    }
                  }
                  else
                  {
                    v20 = "Symbols stripped";
                  }
                }
                else
                {
                  v20 = "Line numbers stripped";
                }
              }
              else
              {
                v20 = "Executable";
              }
            }
            else
            {
              v20 = "Relocations stripped";
            }
          }
LABEL_83:
          ExtensionApis.lpOutputRoutine("            %s\n", v20);
          goto LABEL_84;
        }
        switch ( v14 )
        {
          case 0x200:
            v20 = "Debug information stripped";
            goto LABEL_83;
          case 0x400:
            v20 = "Run from swap file if image is on removable media";
            goto LABEL_83;
          case 0x800:
            v20 = "Run from swap file if image is on net";
            goto LABEL_83;
          case 0x1000:
            v20 = "System";
            goto LABEL_83;
          case 0x2000:
            v20 = "DLL";
            goto LABEL_83;
        }
        if ( v14 != 0x8000 )
          goto LABEL_77;
      }
LABEL_84:
      ++v12;
      v13 >>= 1;
      if ( !v13 )
      {
        v11 = gImageFileHdr;
        break;
      }
    }
  }
  if ( *(_WORD *)(v11 + 16) )
  {
    sprintf_s(
      Buffer,
      0x1Eu,
      "%u.%02u",
      *(unsigned __int8 *)(gImageOptionalHdr + 2),
      *(unsigned __int8 *)(gImageOptionalHdr + 3));
    LODWORD(v45) = *(_DWORD *)(gImageOptionalHdr + 8);
    ExtensionApis.lpOutputRoutine(
      "\n"
      "OPTIONAL HEADER VALUES\n"
      "%8hX magic #\n"
      "%8s linker version\n"
      "%8lX size of code\n"
      "%8lX size of initialized data\n"
      "%8lX size of uninitialized data\n"
      "%8lX address of entry point\n"
      "%8lX base of code\n",
      *(unsigned __int16 *)gImageOptionalHdr,
      Buffer,
      *(unsigned int *)(gImageOptionalHdr + 4),
      v45,
      *(_DWORD *)(gImageOptionalHdr + 12),
      *(_DWORD *)(gImageOptionalHdr + 16),
      *(_DWORD *)(gImageOptionalHdr + 20));
  }
  if ( gdft == 3 )
  {
    LODWORD(v49) = *(_DWORD *)(gImageOptionalHdr + 52);
    LODWORD(v48) = *(_DWORD *)(gImageOptionalHdr + 48);
    LODWORD(v47) = *(_DWORD *)(gImageOptionalHdr + 44);
    LODWORD(v44) = *(_DWORD *)(gImageOptionalHdr + 40);
    ExtensionApis.lpOutputRoutine(
      "         ----- rom -----\n"
      "%8lX base of bss\n"
      "%8lX gpr mask\n"
      "         cpr mask\n"
      "         %08lX %08lX %08lX %08lX\n"
      "%8hX gp value\n",
      *(unsigned int *)(gImageOptionalHdr + 28),
      *(unsigned int *)(gImageOptionalHdr + 32),
      *(unsigned int *)(gImageOptionalHdr + 36),
      v44,
      v47,
      v48,
      v49);
  }
  if ( ((*(_WORD *)gImageOptionalHdr - 267) & 0xFEFF) != 0 )
    return;
  v21 = *(unsigned __int16 *)(gImageOptionalHdr + 68);
  if ( v21 > 9 )
  {
    v28 = v21 - 10;
    if ( !v28 )
    {
      v27 = off_180220720;
      goto LABEL_120;
    }
    v29 = v28 - 1;
    if ( !v29 )
    {
      v27 = off_180220728;
      goto LABEL_120;
    }
    v30 = v29 - 1;
    if ( !v30 )
    {
      v27 = off_180220730;
      goto LABEL_120;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      v27 = off_180220738;
      goto LABEL_120;
    }
    v32 = v31 - 1;
    if ( !v32 )
    {
      v27 = off_180220740;
      goto LABEL_120;
    }
    if ( v32 == 2 )
    {
      v27 = &off_180220748;
      goto LABEL_120;
    }
    goto LABEL_106;
  }
  if ( v21 == 9 )
  {
    v27 = off_180220718;
    goto LABEL_120;
  }
  if ( !*(_WORD *)(gImageOptionalHdr + 68) )
    goto LABEL_106;
  v22 = v21 - 1;
  if ( !v22 )
  {
    v27 = off_1802206E8;
    goto LABEL_120;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    v27 = off_1802206F0;
    goto LABEL_120;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    v27 = off_1802206F8;
    goto LABEL_120;
  }
  v25 = v24 - 2;
  if ( !v25 )
  {
    v27 = off_180220700;
    goto LABEL_120;
  }
  v26 = v25 - 2;
  if ( !v26 )
  {
    v27 = off_180220708;
    goto LABEL_120;
  }
  if ( v26 != 1 )
  {
LABEL_106:
    v27 = off_1802206E0;
    goto LABEL_120;
  }
  v27 = off_180220710;
LABEL_120:
  sprintf_s(
    v55,
    0x1Eu,
    "%hu.%02hu",
    *(unsigned __int16 *)(gImageOptionalHdr + 40),
    *(unsigned __int16 *)(gImageOptionalHdr + 42));
  sprintf_s(
    v54,
    0x1Eu,
    "%hu.%02hu",
    *(unsigned __int16 *)(gImageOptionalHdr + 44),
    *(unsigned __int16 *)(gImageOptionalHdr + 46));
  sprintf_s(
    Buffer,
    0x1Eu,
    "%hu.%02hu",
    *(unsigned __int16 *)(gImageOptionalHdr + 48),
    *(unsigned __int16 *)(gImageOptionalHdr + 50));
  LODWORD(v46) = *(unsigned __int16 *)(gImageOptionalHdr + 68);
  ExtensionApis.lpOutputRoutine(
    "         ----- new -----\n"
    "%p image base\n"
    "%8lX section alignment\n"
    "%8lX file alignment\n"
    "%8hX subsystem (%s)\n"
    "%8s operating system version\n"
    "%8s image version\n"
    "%8s subsystem version\n"
    "%8lX size of image\n"
    "%8lX size of headers\n"
    "%8lX checksum\n",
    *(_QWORD *)(gImageOptionalHdr + 24),
    *(unsigned int *)(gImageOptionalHdr + 32),
    *(unsigned int *)(gImageOptionalHdr + 36),
    v46,
    *v27,
    v55,
    v54,
    Buffer,
    *(_DWORD *)(gImageOptionalHdr + 56),
    *(_DWORD *)(gImageOptionalHdr + 60),
    *(_DWORD *)(gImageOptionalHdr + 64));
  ExtensionApis.lpOutputRoutine(
    "%p size of stack reserve\n%p size of stack commit\n%p size of heap reserve\n%p size of heap commit\n",
    *(_QWORD *)(gImageOptionalHdr + 72),
    *(_QWORD *)(gImageOptionalHdr + 80),
    *(_QWORD *)(gImageOptionalHdr + 88),
    *(_QWORD *)(gImageOptionalHdr + 96));
  ExtensionApis.lpOutputRoutine("%8lX  DLL characteristics\n", *(unsigned __int16 *)(gImageOptionalHdr + 70));
  v33 = gImageOptionalHdr;
  v34 = 0;
  v35 = *(unsigned __int16 *)(gImageOptionalHdr + 70);
  if ( *(_WORD *)(gImageOptionalHdr + 70) )
  {
    while ( 1 )
    {
      if ( (v35 & 1) != 0 )
      {
        v36 = 1 << v34;
        if ( 1 << v34 > 1024 )
        {
          switch ( v36 )
          {
            case 0x800:
              v41 = "Do not bind";
              goto LABEL_145;
            case 0x1000:
              v41 = "AppContainer executable";
              goto LABEL_145;
            case 0x2000:
              v41 = "WDM driver";
              goto LABEL_145;
            case 0x4000:
              v41 = "Guard";
              goto LABEL_145;
            case 0x8000:
              v41 = "Terminal server aware";
              goto LABEL_145;
          }
        }
        else
        {
          if ( v36 == 1024 )
          {
            v41 = "No structured exception handler";
            goto LABEL_145;
          }
          v37 = v36 - 32;
          if ( !v37 )
          {
            v41 = "High entropy VA supported";
            goto LABEL_145;
          }
          v38 = v37 - 32;
          if ( !v38 )
          {
            v41 = "Dynamic base";
            goto LABEL_145;
          }
          v39 = v38 - 64;
          if ( !v39 )
          {
            v41 = "Check integrity";
            goto LABEL_145;
          }
          v40 = v39 - 128;
          if ( !v40 )
          {
            v41 = "NX compatible";
            goto LABEL_145;
          }
          if ( v40 == 256 )
          {
            v41 = "Isolation disabled";
LABEL_145:
            ExtensionApis.lpOutputRoutine("            %s\n", v41);
          }
        }
      }
      ++v34;
      v35 >>= 1;
      if ( !v35 )
      {
        v33 = gImageOptionalHdr;
        break;
      }
    }
  }
  v42 = 0;
  while ( off_1802207E0[v42] )
  {
    ExtensionApis.lpOutputRoutine(
      "%8lX [%8lX] address [size] of %s Directory\n",
      *(unsigned int *)(v33 + 8LL * v42 + 112),
      *(unsigned int *)(v33 + 8LL * v42 + 116));
    if ( (int)++v42 >= 16 )
      break;
    v33 = gImageOptionalHdr;
  }
  ExtensionApis.lpOutputRoutine("\n");
}

```

## disassembly

```asm
0x1801977a4  push    rbp
0x1801977a6  push    rbx
0x1801977a7  push    rsi
0x1801977a8  push    rdi
0x1801977a9  push    r12
0x1801977ab  push    r14
0x1801977ad  lea     rbp, [rsp-148h]
0x1801977b5  sub     rsp, 248h
0x1801977bc  mov     rax, cs:__security_cookie
0x1801977c3  xor     rax, rsp
0x1801977c6  mov     [rbp+170h+var_40], rax
0x1801977cd  mov     ecx, cs:gdft
0x1801977d3  mov     edx, 2000h
0x1801977d8  sub     ecx, 1
0x1801977db  jz      short loc_180197826
0x1801977dd  sub     ecx, 1
0x1801977e0  jz      short loc_180197800
0x1801977e2  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801977e9  cmp     ecx, 1
0x1801977ec  jz      short loc_1801977F7
0x1801977ee  lea     rcx, aFileTypeUnknow; "\nFile Type: UNKNOWN\n"
0x1801977f5  jmp     short loc_180197834
0x1801977f7  lea     rcx, aFileTypeRomIma; "\nFile Type: ROM IMAGE\n"
0x1801977fe  jmp     short loc_180197834
0x180197800  mov     rax, cs:gImageFileHdr
0x180197807  test    [rax+12h], dx
0x18019780b  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197812  jz      short loc_18019781D
0x180197814  lea     rcx, aFileTypeDll; "\nFile Type: DLL\n"
0x18019781b  jmp     short loc_180197834
0x18019781d  lea     rcx, aFileTypeExecut; "\nFile Type: EXECUTABLE IMAGE\n"
0x180197824  jmp     short loc_180197834
0x180197826  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019782d  lea     rcx, aFileTypeCoffOb; "\nFile Type: COFF OBJECT\n"
0x180197834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197839  mov     rax, cs:gImageFileHdr
0x180197840  lea     rbx, aUnknown_0; "Unknown"
0x180197847  mov     r8d, 8664h
0x18019784d  mov     r9d, 14Ch
0x180197853  movzx   edx, word ptr [rax]
0x180197856  mov     eax, 1F2h
0x18019785b  cmp     edx, eax
0x18019785d  ja      short loc_1801978B2
0x18019785f  jz      short loc_1801978A9
0x180197861  mov     ecx, edx
0x180197863  sub     ecx, r9d
0x180197866  jz      short loc_1801978A0
0x180197868  sub     ecx, 38h ; '8'
0x18019786b  jz      short loc_180197897
0x18019786d  sub     ecx, 3Ch ; '<'
0x180197870  jz      short loc_18019788E
0x180197872  sub     ecx, 2
0x180197875  jz      short loc_180197885
0x180197877  cmp     ecx, 2
0x18019787a  jnz     short loc_1801978F1
0x18019787c  lea     rbx, aArmNtThumb2; "ARM NT (Thumb-2)"
0x180197883  jmp     short loc_1801978F1
0x180197885  lea     rbx, aArm32BitThumb; "ARM 32-bit (Thumb)"
0x18019788c  jmp     short loc_1801978F1
0x18019788e  lea     rbx, aArm32Bit; "ARM 32-bit"
0x180197895  jmp     short loc_1801978F1
0x180197897  lea     rbx, aAlphaAxp; "Alpha AXP"
0x18019789e  jmp     short loc_1801978F1
0x1801978a0  lea     rbx, aI386_0; "i386"
0x1801978a7  jmp     short loc_1801978F1
0x1801978a9  lea     rbx, aPowerpcBigEndi; "PowerPC Big-Endian 32-bit"
0x1801978b0  jmp     short loc_1801978F1
0x1801978b2  cmp     edx, 200h
0x1801978b8  jz      short loc_1801978EA
0x1801978ba  cmp     edx, 284h
0x1801978c0  jz      short loc_1801978E1
0x1801978c2  cmp     edx, r8d
0x1801978c5  jz      short loc_1801978D8
0x1801978c7  cmp     edx, 0AA64h
0x1801978cd  jnz     short loc_1801978F1
0x1801978cf  lea     rbx, aArmv864Bit; "ARMv8 (64-bit)"
0x1801978d6  jmp     short loc_1801978F1
0x1801978d8  lea     rbx, aX64; "X64"
0x1801978df  jmp     short loc_1801978F1
0x1801978e1  lea     rbx, aAlphaAxp64; "Alpha AXP64"
0x1801978e8  jmp     short loc_1801978F1
0x1801978ea  lea     rbx, aIntelIa64; "Intel IA64"
0x1801978f1  xor     r14d, r14d
0x1801978f4  mov     r12d, 80h
0x1801978fa  cmp     dx, r9w
0x1801978fe  jnz     loc_1801979A1
0x180197904  mov     rax, cs:gImageOptionalHdr
0x18019790b  mov     esi, [rax+0C0h]
0x180197911  test    esi, esi
0x180197913  jz      loc_180197A46
0x180197919  mov     eax, [rax+0C4h]
0x18019791f  test    eax, eax
0x180197921  jz      loc_180197A46
0x180197927  cmp     eax, r12d
0x18019792a  jb      loc_180197A46
0x180197930  lea     r8d, [r12+44h]; Size
0x180197935  cmp     eax, r8d
0x180197938  lea     rcx, [rbp+170h+var_1F0]; void *
0x18019793c  mov     edi, r8d
0x18019793f  cmovb   edi, eax
0x180197942  xor     edx, edx; Val
0x180197944  call    memset_0
0x180197949  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180197950  lea     r9, [rsp+270h+var_200]
0x180197955  mov     ecx, esi
0x180197957  mov     [rsp+270h+var_200], r14d
0x18019795c  add     rcx, cs:gBase
0x180197963  lea     rdx, [rbp+170h+var_1F0]
0x180197967  mov     r8d, edi
0x18019796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019796f  test    eax, eax
0x180197971  jz      loc_180197A33
0x180197977  cmp     [rsp+270h+var_200], edi
0x18019797b  jnz     loc_180197A33
0x180197981  cmp     [rbp+170h+var_1F0], r12d
0x180197985  jb      loc_180197A46
0x18019798b  cmp     [rbp+170h+var_174], r14d
0x18019798f  jz      loc_180197A46
0x180197995  lea     rbx, aI386Chpe; "i386 (CHPE)"
0x18019799c  jmp     loc_180197A46
0x1801979a1  cmp     dx, r8w
0x1801979a5  jnz     loc_180197A46
0x1801979ab  mov     rax, cs:gImageOptionalHdr
0x1801979b2  mov     esi, [rax+0C0h]
0x1801979b8  test    esi, esi
0x1801979ba  jz      loc_180197A46
0x1801979c0  mov     eax, [rax+0C4h]
0x1801979c6  test    eax, eax
0x1801979c8  jz      short loc_180197A46
0x1801979ca  mov     r12d, 0D0h
0x1801979d0  cmp     eax, r12d
0x1801979d3  jb      short loc_180197A46
0x1801979d5  lea     r8d, [r12+78h]; Size
0x1801979da  cmp     eax, r8d
0x1801979dd  lea     rcx, [rbp+170h+var_1F0]; void *
0x1801979e1  mov     edi, r8d
0x1801979e4  cmovb   edi, eax
0x1801979e7  xor     edx, edx; Val
0x1801979e9  call    memset_0
0x1801979ee  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x1801979f5  lea     r9, [rsp+270h+var_200]
0x1801979fa  mov     ecx, esi
0x1801979fc  mov     [rsp+270h+var_200], r14d
0x180197a01  add     rcx, cs:gBase
0x180197a08  lea     rdx, [rbp+170h+var_1F0]
0x180197a0c  mov     r8d, edi
0x180197a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197a14  test    eax, eax
0x180197a16  jz      short loc_180197A33
0x180197a18  cmp     [rsp+270h+var_200], edi
0x180197a1c  jnz     short loc_180197A33
0x180197a1e  cmp     [rbp+170h+var_1F0], r12d
0x180197a22  jb      short loc_180197A46
0x180197a24  cmp     [rbp+170h+var_128], r14
0x180197a28  jz      short loc_180197A46
0x180197a2a  lea     rbx, aX64Chpev2; "X64 (CHPEv2)"
0x180197a31  jmp     short loc_180197A46
0x180197a33  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197a3a  lea     rcx, aCanTReadLoadCo; "Can't read load config section\n"
0x180197a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197a46  mov     rcx, cs:gImageFileHdr
0x180197a4d  mov     r8, rbx
0x180197a50  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197a57  movzx   r9d, word ptr [rcx+2]
0x180197a5c  movzx   edx, word ptr [rcx]
0x180197a5f  mov     ecx, [rcx+4]
0x180197a62  mov     dword ptr [rsp+270h+var_250], ecx
0x180197a66  lea     rcx, aFileHeaderValu; "FILE HEADER VALUES\n%8hX machine (%s)\n"...
0x180197a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197a72  mov     rcx, cs:gImageFileHdr
0x180197a79  add     rcx, 4; Time
0x180197a7d  call    ctime
0x180197a82  test    rax, rax
0x180197a85  jz      short loc_180197A9D
0x180197a87  mov     rdx, rax
0x180197a8a  lea     rcx, aS_8; " %s"
0x180197a91  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197a9d  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197aa4  lea     rcx, asc_18022B9A8; "\n"
0x180197aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197ab0  mov     rdx, cs:gImageFileHdr
0x180197ab7  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197abe  movzx   ecx, word ptr [rdx+12h]
0x180197ac2  movzx   r9d, word ptr [rdx+10h]
0x180197ac7  mov     r8d, [rdx+0Ch]
0x180197acb  mov     edx, [rdx+8]
0x180197ace  mov     dword ptr [rsp+270h+var_250], ecx
0x180197ad2  lea     rcx, a8lxFilePointer; "%8lX file pointer to symbol table\n%8lX"...
0x180197ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197ade  mov     rax, cs:gImageFileHdr
0x180197ae5  mov     edi, r14d
0x180197ae8  mov     esi, 1
0x180197aed  movzx   ebx, word ptr [rax+12h]
0x180197af1  test    ebx, ebx
0x180197af3  jz      loc_180197BFE
0x180197af9  test    sil, bl
0x180197afc  jz      loc_180197BED
0x180197b02  mov     ecx, edi
0x180197b04  mov     edx, esi
0x180197b06  shl     edx, cl
0x180197b08  cmp     edx, 100h
0x180197b0e  jg      short loc_180197B76
0x180197b10  jz      short loc_180197B6D
0x180197b12  sub     edx, esi
0x180197b14  jz      short loc_180197B64
0x180197b16  sub     edx, esi
0x180197b18  jz      short loc_180197B5B
0x180197b1a  sub     edx, 2
0x180197b1d  jz      short loc_180197B52
0x180197b1f  sub     edx, 4
0x180197b22  jz      short loc_180197B46
0x180197b24  sub     edx, 18h
0x180197b27  jz      short loc_180197B3A
0x180197b29  cmp     edx, 60h ; '`'
0x180197b2c  jnz     short loc_180197BA6
0x180197b2e  lea     rdx, aBytesReversed; "Bytes reversed"
0x180197b35  jmp     loc_180197BDA
0x180197b3a  lea     rdx, aAppCanHandle2g; "App can handle >2gb addresses"
0x180197b41  jmp     loc_180197BDA
0x180197b46  lea     rdx, aSymbolsStrippe; "Symbols stripped"
0x180197b4d  jmp     loc_180197BDA
0x180197b52  lea     rdx, aLineNumbersStr; "Line numbers stripped"
0x180197b59  jmp     short loc_180197BDA
0x180197b5b  lea     rdx, aExecutable; "Executable"
0x180197b62  jmp     short loc_180197BDA
0x180197b64  lea     rdx, aRelocationsStr; "Relocations stripped"
0x180197b6b  jmp     short loc_180197BDA
0x180197b6d  lea     rdx, a32BitWordMachi; "32 bit word machine"
0x180197b74  jmp     short loc_180197BDA
0x180197b76  cmp     edx, 200h
0x180197b7c  jz      short loc_180197BD3
0x180197b7e  cmp     edx, 400h
0x180197b84  jz      short loc_180197BCA
0x180197b86  cmp     edx, 800h
0x180197b8c  jz      short loc_180197BC1
0x180197b8e  cmp     edx, 1000h
0x180197b94  jz      short loc_180197BB8
0x180197b96  cmp     edx, 2000h
0x180197b9c  jz      short loc_180197BAF
0x180197b9e  cmp     edx, 8000h
0x180197ba4  jz      short loc_180197BED
0x180197ba6  lea     rdx, aReservedUnknow; "RESERVED - UNKNOWN"
0x180197bad  jmp     short loc_180197BDA
0x180197baf  lea     rdx, aDll; "DLL"
0x180197bb6  jmp     short loc_180197BDA
0x180197bb8  lea     rdx, aSystem; "System"
0x180197bbf  jmp     short loc_180197BDA
0x180197bc1  lea     rdx, aRunFromSwapFil; "Run from swap file if image is on net"
0x180197bc8  jmp     short loc_180197BDA
0x180197bca  lea     rdx, aRunFromSwapFil_0; "Run from swap file if image is on remov"...
0x180197bd1  jmp     short loc_180197BDA
0x180197bd3  lea     rdx, aDebugInformati; "Debug information stripped"
0x180197bda  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197be1  lea     rcx, aS_17; "            %s\n"
0x180197be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197bed  add     edi, esi
0x180197bef  shr     ebx, 1
0x180197bf1  jnz     loc_180197AF9
0x180197bf7  mov     rax, cs:gImageFileHdr
0x180197bfe  mov     r12d, 1Eh
0x180197c04  cmp     [rax+10h], r14w
0x180197c09  jz      short loc_180197C7E
0x180197c0b  mov     rax, cs:gImageOptionalHdr
0x180197c12  lea     r8, aU02u; "%u.%02u"
0x180197c19  mov     edx, r12d; BufferCount
0x180197c1c  movzx   ecx, byte ptr [rax+3]
0x180197c20  movzx   r9d, byte ptr [rax+2]
0x180197c25  mov     dword ptr [rsp+270h+var_250], ecx
0x180197c29  lea     rcx, [rbp+170h+Buffer]; Buffer
0x180197c30  call    sprintf_s
0x180197c35  mov     r9, cs:gImageOptionalHdr
0x180197c3c  lea     r8, [rbp+170h+Buffer]
0x180197c43  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197c4a  mov     ecx, [r9+14h]
0x180197c4e  movzx   edx, word ptr [r9]
0x180197c52  mov     dword ptr [rsp+270h+var_238], ecx
0x180197c56  mov     ecx, [r9+10h]
0x180197c5a  mov     dword ptr [rsp+270h+var_240], ecx
0x180197c5e  mov     ecx, [r9+0Ch]
0x180197c62  mov     dword ptr [rsp+270h+var_248], ecx
0x180197c66  mov     ecx, [r9+8]
0x180197c6a  mov     r9d, [r9+4]
0x180197c6e  mov     dword ptr [rsp+270h+var_250], ecx
0x180197c72  lea     rcx, aOptionalHeader; "\nOPTIONAL HEADER VALUES\n%8hX magic #"...
0x180197c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197c7e  cmp     cs:gdft, 3
0x180197c85  jnz     short loc_180197CC8
0x180197c87  mov     rdx, cs:gImageOptionalHdr
0x180197c8e  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197c95  mov     ecx, [rdx+34h]
0x180197c98  mov     r9d, [rdx+24h]
0x180197c9c  mov     r8d, [rdx+20h]
0x180197ca0  mov     dword ptr [rsp+270h+var_238], ecx
0x180197ca4  mov     ecx, [rdx+30h]
0x180197ca7  mov     dword ptr [rsp+270h+var_240], ecx
0x180197cab  mov     ecx, [rdx+2Ch]
0x180197cae  mov     dword ptr [rsp+270h+var_248], ecx
0x180197cb2  mov     ecx, [rdx+28h]
0x180197cb5  mov     edx, [rdx+1Ch]
  ... truncated ...
```
