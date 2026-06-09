# dhDumpDebugDirectory(_IMAGE_DEBUG_DIRECTORY *)

- ea: `0x180196ee0`
- end: `0x18019735f`
- name: `?dhDumpDebugDirectory@@YAXPEAU_IMAGE_DEBUG_DIRECTORY@@@Z`
- size: `1151`
- prototype: `void __fastcall(struct _IMAGE_DEBUG_DIRECTORY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180196d74`

## callees

- `0x180027430`
- `0x180196ee0`
- `0x18019a4f4`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18019712c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180202300`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18019712c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180202300`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18019707e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18019707e`

## string_xrefs

- `0x180196f83`: `	dllchar`
- `0x180197115`: `Can't read debug data\n`
- `0x180197207`: `	Can't read debug data cb=%lx\n`
- `0x180197310`: `	Can't read debug data cb=%lx\n`
- `0x1801972a3`: `\n\n%08X extended DLL characteristics\n`

## pseudocode

```c
void __fastcall dhDumpDebugDirectory(struct _IMAGE_DEBUG_DIRECTORY *a1)
{
  PWINDBG_OUTPUT_ROUTINE lpOutputRoutine; // rax
  const char *v3; // rcx
  __int64 PointerToRawData; // rcx
  __int64 v5; // rcx
  DWORD AddressOfRawData; // edx
  DWORD v7; // eax
  const CHAR *v8; // rcx
  DWORD SizeOfData; // edi
  unsigned int *v10; // rax
  unsigned int *v11; // rsi
  unsigned int *v12; // rdx
  _DWORD *v13; // rdx
  DWORD v14; // edi
  __int64 v15; // rdx
  PWINDBG_OUTPUT_ROUTINE v16; // rax
  const char *v17; // rcx
  __int64 v18; // rcx
  DWORD v19; // edx
  DWORD v20; // eax
  DWORD v21; // ebx
  __int64 v22; // rbx
  unsigned int v23; // eax
  DWORD v24; // [rsp+30h] [rbp-378h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-374h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-370h] BYREF
  unsigned int *v27; // [rsp+40h] [rbp-368h]
  unsigned int *v28; // [rsp+48h] [rbp-360h]
  _DWORD v29[4]; // [rsp+50h] [rbp-358h] BYREF
  _BYTE v30[4]; // [rsp+60h] [rbp-348h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-344h]
  _BYTE v32[792]; // [rsp+68h] [rbp-340h] BYREF

  v25 = 0;
  memset_0(v29, 0, 0x324u);
  v26 = 0;
  v24 = 0;
  switch ( a1->Type )
  {
    case 1u:
      v3 = "\tcoff   ";
      goto LABEL_20;
    case 2u:
      v3 = "\tcv     ";
      goto LABEL_20;
    case 3u:
      v3 = "\tfpo    ";
      goto LABEL_20;
    case 4u:
      v3 = "\tmisc   ";
      goto LABEL_20;
    case 5u:
      v3 = "\tpdata  ";
      goto LABEL_20;
    case 6u:
      v3 = "\tfixup  ";
      goto LABEL_20;
    case 7u:
      v3 = "\t-> src ";
      goto LABEL_20;
    case 8u:
      v3 = "\tsrc -> ";
LABEL_20:
      lpOutputRoutine = ExtensionApis.lpOutputRoutine;
      goto LABEL_21;
  }
  lpOutputRoutine = ExtensionApis.lpOutputRoutine;
  if ( a1->Type == 20 )
  {
    v3 = "\tdllchar";
LABEL_21:
    lpOutputRoutine(v3);
    goto LABEL_22;
  }
  ExtensionApis.lpOutputRoutine("\t(%5lu)");
LABEL_22:
  ExtensionApis.lpOutputRoutine("%8x    %8x %8x", a1->SizeOfData, a1->AddressOfRawData, a1->PointerToRawData);
  PointerToRawData = a1->PointerToRawData;
  if ( (_DWORD)PointerToRawData && a1->Type == 4 )
  {
    if ( (unsigned int)TranslateFilePointerToVirtualAddress(PointerToRawData, &v24) )
    {
      SizeOfData = a1->SizeOfData;
      v10 = (unsigned int *)malloc(SizeOfData);
      v11 = v10;
      v28 = v10;
      if ( v10 )
      {
        if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
               gBase + v24,
               v10,
               SizeOfData,
               &v25)
          && v25 == SizeOfData )
        {
          v12 = v11;
          v27 = v11;
          while ( *v12 != 1 )
          {
            if ( SizeOfData >= v12[1] )
            {
              SizeOfData -= v12[1];
              v12 = (unsigned int *)((char *)v12 + v11[1]);
              v27 = v12;
              if ( SizeOfData )
                continue;
            }
            goto LABEL_47;
          }
          if ( *(_BYTE *)(gImageOptionalHdr + 2) == 2 && *(_BYTE *)(gImageOptionalHdr + 3) < 0x25u )
            v13 = (unsigned int *)((char *)v12 + 9);
          else
            v13 = v12 + 3;
          ExtensionApis.lpOutputRoutine("\tImage Name: %s", v13);
        }
        else
        {
          ExtensionApis.lpOutputRoutine("Can't read debug data\n");
        }
LABEL_47:
        free(v11);
      }
    }
    else
    {
      ExtensionApis.lpOutputRoutine(" [Debug data not mapped]\n");
    }
  }
  v5 = a1->PointerToRawData;
  if ( (_DWORD)v5 && a1->Type == 2 )
  {
    AddressOfRawData = a1->AddressOfRawData;
    v7 = v24;
    if ( AddressOfRawData )
      v7 = a1->AddressOfRawData;
    v24 = v7;
    if ( !AddressOfRawData && !(unsigned int)TranslateFilePointerToVirtualAddress(v5, &v24) )
    {
      v8 = " [Debug data not mapped]\n";
LABEL_59:
      ExtensionApis.lpOutputRoutine(v8);
      goto LABEL_64;
    }
    v14 = a1->SizeOfData;
    if ( v14 > 0x324 )
      v14 = 804;
    if ( !((unsigned int (__fastcall *)(__int64, _DWORD *, _QWORD, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
            gBase + v24,
            v29,
            v14,
            &v25)
      || v25 != v14 )
    {
      v15 = v25;
      v17 = "\tCan't read debug data cb=%lx\n";
      v16 = ExtensionApis.lpOutputRoutine;
      goto LABEL_63;
    }
    v15 = v29[0];
    switch ( v29[0] )
    {
      case 0x3031424E:
        ExtensionApis.lpOutputRoutine("\tFormat: NB10, %x, %x, %s", v29[2], v29[3], v30);
        goto LABEL_64;
      case 0x3131424E:
        v8 = "\tFormat: NB11";
        goto LABEL_59;
      case 0x3930424E:
        v8 = "\tFormat: NB09";
        goto LABEL_59;
    }
    v16 = ExtensionApis.lpOutputRoutine;
    if ( v29[0] != 1396986706 )
    {
      v17 = "\tFormat: UNKNOWN - sig = 0x%x";
LABEL_63:
      v16(v17, v15);
      goto LABEL_64;
    }
    ExtensionApis.lpOutputRoutine("\tFormat: RSDS, guid, %x, %s", v31, v32);
  }
LABEL_64:
  v18 = a1->PointerToRawData;
  if ( (_DWORD)v18 && a1->Type == 20 )
  {
    v19 = a1->AddressOfRawData;
    v20 = v24;
    if ( v19 )
      v20 = a1->AddressOfRawData;
    v24 = v20;
    if ( v19 || (unsigned int)TranslateFilePointerToVirtualAddress(v18, &v24) )
    {
      v21 = a1->SizeOfData;
      if ( v21 > 4 )
        v21 = 4;
      if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))ExtensionApis.lpReadProcessMemoryRoutine)(
             gBase + v24,
             &v26,
             v21,
             &v25)
        && v25 == v21 )
      {
        ExtensionApis.lpOutputRoutine("\n\n%08X extended DLL characteristics\n", v26);
        v22 = 0;
        v23 = v26;
        while ( v23 )
        {
          if ( (v23 & 1) != 0 )
          {
            if ( (unsigned int)v22 < 6 )
              ExtensionApis.lpOutputRoutine("          %s\n", (&DllCharExString)[v22]);
            else
              ExtensionApis.lpOutputRoutine("          (Unknown)\n");
            v23 = v26;
          }
          v23 >>= 1;
          v26 = v23;
          v22 = (unsigned int)(v22 + 1);
        }
      }
      else
      {
        ExtensionApis.lpOutputRoutine("\tCan't read debug data cb=%lx\n", v25);
      }
    }
    else
    {
      ExtensionApis.lpOutputRoutine(" [Debug data not mapped]\n");
    }
  }
  ExtensionApis.lpOutputRoutine("\n");
}

```

## disassembly

```asm
0x180196ee0  mov     [rsp+arg_8], rbx
0x180196ee5  mov     [rsp+arg_10], rsi
0x180196eea  push    rdi
0x180196eeb  push    r12
0x180196eed  push    r14
0x180196eef  sub     rsp, 390h
0x180196ef6  mov     rax, cs:__security_cookie
0x180196efd  xor     rax, rsp
0x180196f00  mov     [rsp+3A8h+var_28], rax
0x180196f08  mov     rbx, rcx
0x180196f0b  mov     [rsp+3A8h+var_374], 0
0x180196f13  mov     r12d, 324h
0x180196f19  mov     r8d, r12d; Size
0x180196f1c  xor     edx, edx; Val
0x180196f1e  lea     rcx, [rsp+3A8h+var_358]; void *
0x180196f23  call    memset_0
0x180196f28  mov     [rsp+3A8h+var_370], 0
0x180196f30  mov     [rsp+3A8h+var_378], 0
0x180196f38  mov     edx, [rbx+0Ch]
0x180196f3b  mov     eax, edx
0x180196f3d  sub     eax, 1
0x180196f40  jz      loc_180196FCB
0x180196f46  sub     eax, 1
0x180196f49  jz      short loc_180196FC2
0x180196f4b  sub     eax, 1
0x180196f4e  jz      short loc_180196FB9
0x180196f50  sub     eax, 1
0x180196f53  jz      short loc_180196FB0
0x180196f55  sub     eax, 1
0x180196f58  jz      short loc_180196FA7
0x180196f5a  sub     eax, 1
0x180196f5d  jz      short loc_180196F9E
0x180196f5f  sub     eax, 1
0x180196f62  jz      short loc_180196F95
0x180196f64  sub     eax, 1
0x180196f67  jz      short loc_180196F8C
0x180196f69  cmp     eax, 0Ch
0x180196f6c  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180196f73  jz      short loc_180196F83
0x180196f75  lea     rcx, a5lu; "\t(%5lu)"
0x180196f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196f81  jmp     short loc_180196FDE
0x180196f83  lea     rcx, aDllchar; "\tdllchar"
0x180196f8a  jmp     short loc_180196FD9
0x180196f8c  lea     rcx, aSrc; "\tsrc -> "
0x180196f93  jmp     short loc_180196FD2
0x180196f95  lea     rcx, aSrc_2; "\t-> src "
0x180196f9c  jmp     short loc_180196FD2
0x180196f9e  lea     rcx, aFixup; "\tfixup  "
0x180196fa5  jmp     short loc_180196FD2
0x180196fa7  lea     rcx, aPdata_0; "\tpdata  "
0x180196fae  jmp     short loc_180196FD2
0x180196fb0  lea     rcx, aMisc; "\tmisc   "
0x180196fb7  jmp     short loc_180196FD2
0x180196fb9  lea     rcx, aFpo_1; "\tfpo    "
0x180196fc0  jmp     short loc_180196FD2
0x180196fc2  lea     rcx, aCv; "\tcv     "
0x180196fc9  jmp     short loc_180196FD2
0x180196fcb  lea     rcx, aCoff; "\tcoff   "
0x180196fd2  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180196fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196fde  mov     r9d, [rbx+18h]
0x180196fe2  mov     r8d, [rbx+14h]
0x180196fe6  mov     edx, [rbx+10h]
0x180196fe9  lea     rcx, a8x8x8x; "%8x    %8x %8x"
0x180196ff0  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180196ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196ffc  mov     ecx, [rbx+18h]
0x180196fff  mov     r14d, 4
0x180197005  test    ecx, ecx
0x180197007  jz      short loc_180197030
0x180197009  cmp     [rbx+0Ch], r14d
0x18019700d  jnz     short loc_180197030
0x18019700f  lea     rdx, [rsp+3A8h+var_378]
0x180197014  call    TranslateFilePointerToVirtualAddress
0x180197019  test    eax, eax
0x18019701b  jnz     short loc_180197079
0x18019701d  lea     rcx, aDebugDataNotMa_1; " [Debug data not mapped]\n"
0x180197024  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019702b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197030  mov     ecx, [rbx+18h]
0x180197033  test    ecx, ecx
0x180197035  jz      loc_18019721A
0x18019703b  cmp     dword ptr [rbx+0Ch], 2
0x18019703f  jnz     loc_18019721A
0x180197045  mov     edx, [rbx+14h]
0x180197048  mov     eax, [rsp+3A8h+var_378]
0x18019704c  test    edx, edx
0x18019704e  cmovnz  eax, edx
0x180197051  mov     [rsp+3A8h+var_378], eax
0x180197055  jnz     loc_180197137
0x18019705b  lea     rdx, [rsp+3A8h+var_378]
0x180197060  call    TranslateFilePointerToVirtualAddress
0x180197065  test    eax, eax
0x180197067  jnz     loc_180197137
0x18019706d  lea     rcx, aDebugDataNotMa_1; " [Debug data not mapped]\n"
0x180197074  jmp     loc_1801971C9
0x180197079  mov     edi, [rbx+10h]
0x18019707c  mov     ecx, edi; Size
0x18019707e  call    cs:__imp_malloc
0x180197084  mov     rsi, rax
0x180197087  mov     [rsp+3A8h+var_360], rax
0x18019708c  test    rax, rax
0x18019708f  jz      short loc_180197030
0x180197091  mov     ecx, [rsp+3A8h+var_378]
0x180197095  add     rcx, cs:gBase
0x18019709c  lea     r9, [rsp+3A8h+var_374]
0x1801970a1  mov     r8d, edi
0x1801970a4  mov     rdx, rax
0x1801970a7  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x1801970ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801970b3  test    eax, eax
0x1801970b5  jz      short loc_180197115
0x1801970b7  cmp     [rsp+3A8h+var_374], edi
0x1801970bb  jnz     short loc_180197115
0x1801970bd  mov     rdx, rsi
0x1801970c0  mov     [rsp+3A8h+var_368], rdx
0x1801970c5  cmp     dword ptr [rdx], 1
0x1801970c8  jz      short loc_1801970E3
0x1801970ca  cmp     edi, [rdx+4]
0x1801970cd  jb      short loc_180197129
0x1801970cf  sub     edi, [rdx+4]
0x1801970d2  mov     eax, [rsi+4]
0x1801970d5  add     rdx, rax
0x1801970d8  mov     [rsp+3A8h+var_368], rdx
0x1801970dd  test    edi, edi
0x1801970df  jnz     short loc_1801970C5
0x1801970e1  jmp     short loc_180197129
0x1801970e3  mov     rax, cs:gImageOptionalHdr
0x1801970ea  cmp     byte ptr [rax+2], 2
0x1801970ee  jnz     short loc_1801970FC
0x1801970f0  cmp     byte ptr [rax+3], 25h ; '%'
0x1801970f4  jnb     short loc_1801970FC
0x1801970f6  add     rdx, 9
0x1801970fa  jmp     short loc_180197100
0x1801970fc  add     rdx, 0Ch
0x180197100  lea     rcx, aImageNameS; "\tImage Name: %s"
0x180197107  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019710e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197113  jmp     short loc_180197129
0x180197115  lea     rcx, aCanTReadDebugD_1; "Can't read debug data\n"
0x18019711c  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197128  nop
0x180197129  mov     rcx, rsi; Block
0x18019712c  call    cs:__imp_free
0x180197132  jmp     loc_180197030
0x180197137  mov     edi, [rbx+10h]
0x18019713a  cmp     edi, r12d
0x18019713d  cmova   edi, r12d
0x180197141  mov     ecx, [rsp+3A8h+var_378]
0x180197145  add     rcx, cs:gBase
0x18019714c  lea     r9, [rsp+3A8h+var_374]
0x180197151  mov     r8d, edi
0x180197154  lea     rdx, [rsp+3A8h+var_358]
0x180197159  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180197160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197165  test    eax, eax
0x180197167  jz      loc_180197203
0x18019716d  cmp     [rsp+3A8h+var_374], edi
0x180197171  jnz     loc_180197203
0x180197177  mov     edx, [rsp+3A8h+var_358]
0x18019717b  cmp     edx, 3031424Eh
0x180197181  jz      short loc_1801971E0
0x180197183  cmp     edx, 3131424Eh
0x180197189  jz      short loc_1801971D7
0x18019718b  cmp     edx, 3930424Eh
0x180197191  jz      short loc_1801971C2
0x180197193  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019719a  cmp     edx, 53445352h
0x1801971a0  jz      short loc_1801971AB
0x1801971a2  lea     rcx, aFormatUnknownS; "\tFormat: UNKNOWN - sig = 0x%x"
0x1801971a9  jmp     short loc_180197215
0x1801971ab  lea     r8, [rsp+3A8h+var_340]
0x1801971b0  mov     edx, [rsp+3A8h+var_344]
0x1801971b4  lea     rcx, aFormatRsdsGuid; "\tFormat: RSDS, guid, %x, %s"
0x1801971bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801971c0  jmp     short loc_18019721A
0x1801971c2  lea     rcx, aFormatNb09; "\tFormat: NB09"
0x1801971c9  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801971d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801971d5  jmp     short loc_18019721A
0x1801971d7  lea     rcx, aFormatNb11; "\tFormat: NB11"
0x1801971de  jmp     short loc_1801971C9
0x1801971e0  lea     r9, [rsp+3A8h+var_348]
0x1801971e5  mov     r8d, [rsp+3A8h+var_34C]
0x1801971ea  mov     edx, [rsp+3A8h+var_350]
0x1801971ee  lea     rcx, aFormatNb10XXS; "\tFormat: NB10, %x, %x, %s"
0x1801971f5  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801971fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197201  jmp     short loc_18019721A
0x180197203  mov     edx, [rsp+3A8h+var_374]
0x180197207  lea     rcx, aCanTReadDebugD; "\tCan't read debug data cb=%lx\n"
0x18019720e  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019721a  mov     ecx, [rbx+18h]
0x18019721d  test    ecx, ecx
0x18019721f  jz      loc_180197323
0x180197225  cmp     dword ptr [rbx+0Ch], 14h
0x180197229  jnz     loc_180197323
0x18019722f  mov     edx, [rbx+14h]
0x180197232  mov     eax, [rsp+3A8h+var_378]
0x180197236  test    edx, edx
0x180197238  cmovnz  eax, edx
0x18019723b  mov     [rsp+3A8h+var_378], eax
0x18019723f  jnz     short loc_180197267
0x180197241  lea     rdx, [rsp+3A8h+var_378]
0x180197246  call    TranslateFilePointerToVirtualAddress
0x18019724b  test    eax, eax
0x18019724d  jnz     short loc_180197267
0x18019724f  lea     rcx, aDebugDataNotMa_1; " [Debug data not mapped]\n"
0x180197256  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019725d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197262  jmp     loc_180197323
0x180197267  mov     ebx, [rbx+10h]
0x18019726a  cmp     ebx, r14d
0x18019726d  cmova   ebx, r14d
0x180197271  mov     ecx, [rsp+3A8h+var_378]
0x180197275  add     rcx, cs:gBase
0x18019727c  lea     r9, [rsp+3A8h+var_374]
0x180197281  mov     r8d, ebx
0x180197284  lea     rdx, [rsp+3A8h+var_370]
0x180197289  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180197290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197295  test    eax, eax
0x180197297  jz      short loc_18019730C
0x180197299  cmp     [rsp+3A8h+var_374], ebx
0x18019729d  jnz     short loc_18019730C
0x18019729f  mov     edx, [rsp+3A8h+var_370]
0x1801972a3  lea     rcx, a08xExtendedDll; "\n\n%08X extended DLL characteristics\n"
0x1801972aa  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801972b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801972b6  xor     ebx, ebx
0x1801972b8  mov     eax, [rsp+3A8h+var_370]
0x1801972bc  jmp     short loc_180197306
0x1801972be  test    al, 1
0x1801972c0  jz      short loc_1801972FE
0x1801972c2  cmp     ebx, 6
0x1801972c5  jb      short loc_1801972DC
0x1801972c7  lea     rcx, aUnknown_1; "          (Unknown)\n"
0x1801972ce  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801972d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801972da  jmp     short loc_1801972FA
0x1801972dc  lea     rax, ?DllCharExString@@3PAPEADA; char * near * DllCharExString
0x1801972e3  mov     rdx, [rax+rbx*8]
0x1801972e7  lea     rcx, aS_3; "          %s\n"
0x1801972ee  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801972f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801972fa  mov     eax, [rsp+3A8h+var_370]
0x1801972fe  shr     eax, 1
0x180197300  mov     [rsp+3A8h+var_370], eax
0x180197304  inc     ebx
0x180197306  test    eax, eax
0x180197308  jnz     short loc_1801972BE
0x18019730a  jmp     short loc_180197323
0x18019730c  mov     edx, [rsp+3A8h+var_374]
0x180197310  lea     rcx, aCanTReadDebugD; "\tCan't read debug data cb=%lx\n"
0x180197317  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019731e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197323  lea     rcx, asc_18022B9A8; "\n"
0x18019732a  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180197331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197336  mov     rcx, [rsp+3A8h+var_28]
0x18019733e  xor     rcx, rsp; StackCookie
0x180197341  call    __security_check_cookie
0x180197346  lea     r11, [rsp+3A8h+var_18]
0x18019734e  mov     rbx, [r11+28h]
0x180197352  mov     rsi, [r11+30h]
0x180197356  mov     rsp, r11
0x180197359  pop     r14
0x18019735b  pop     r12
0x18019735d  pop     rdi
0x18019735e  retn
0x1802022f3  push    rbp
0x1802022f5  sub     rsp, 30h
0x1802022f9  mov     rbp, rdx
0x1802022fc  mov     rcx, [rbp+48h]; Block
0x180202300  call    cs:__imp_free
0x180202306  nop
0x180202307  add     rsp, 30h
0x18020230b  pop     rbp
0x18020230c  retn
```
