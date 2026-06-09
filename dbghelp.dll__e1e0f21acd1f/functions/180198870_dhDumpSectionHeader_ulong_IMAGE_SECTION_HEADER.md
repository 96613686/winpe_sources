# dhDumpSectionHeader(ulong,_IMAGE_SECTION_HEADER *)

- ea: `0x180198870`
- end: `0x180198d3d`
- name: `?dhDumpSectionHeader@@YAXKPEAU_IMAGE_SECTION_HEADER@@@Z`
- size: `1229`
- prototype: `void __fastcall(unsigned int, struct _IMAGE_SECTION_HEADER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180198d44`

## callees

- `0x180198870`
- `0x180205010`

## string_xrefs

- `0x180198b40`: `Remove`
- `0x180198b34`: `Communal`
- `0x180198b84`: `Not Cached`
- `0x180198d0b`: `Read Only`
- `0x180198d02`: `Execute Read`
- `0x180198cf9`: `Write Only`
- `0x180198cf0`: `Execute Write`
- `0x180198ce7`: `Read Write`
- `0x180198cde`: `Execute Read Write`

## pseudocode

```c
void __fastcall dhDumpSectionHeader(unsigned int a1, struct _IMAGE_SECTION_HEADER *a2)
{
  const char *v3; // r8
  DWORD Characteristics; // edi
  __int16 v5; // bx
  char v6; // si
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  const char *v12; // rdx
  unsigned int v13; // edi
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  const char *v19; // rdx
  DWORD v20; // eax
  const char *v21; // rdx
  const char *v22; // rdx
  __int64 v23; // [rsp+20h] [rbp-58h]

  ExtensionApis.lpOutputRoutine("\nSECTION HEADER #%hX\n%8.8s name", a1, a2);
  ExtensionApis.lpOutputRoutine("\n");
  v3 = "physical address";
  if ( gdft != 1 )
    v3 = "virtual size";
  ExtensionApis.lpOutputRoutine(
    "%8lX %s\n"
    "%8lX virtual address\n"
    "%8lX size of raw data\n"
    "%8lX file pointer to raw data\n"
    "%8lX file pointer to relocation table\n",
    a2->Misc.PhysicalAddress,
    v3,
    a2->VirtualAddress,
    a2->SizeOfRawData,
    a2->PointerToRawData,
    a2->PointerToRelocations);
  LODWORD(v23) = a2->Characteristics;
  ExtensionApis.lpOutputRoutine(
    "%8lX file pointer to line numbers\n%8hX number of relocations\n%8hX number of line numbers\n%8lX flags\n",
    a2->PointerToLinenumbers,
    a2->NumberOfRelocations,
    a2->NumberOfLinenumbers,
    v23);
  Characteristics = a2->Characteristics;
  v5 = 0;
  v6 = 0;
  if ( gdft != 3 )
  {
    v13 = Characteristics & 0xFF8FFFFF;
    if ( !v13 )
    {
LABEL_89:
      v20 = a2->Characteristics & 0x700000;
      switch ( v20 )
      {
        case 0x100000u:
          v21 = "1 byte align";
          break;
        case 0x200000u:
          v21 = "2 byte align";
          break;
        case 0x300000u:
          v21 = "4 byte align";
          break;
        case 0x400000u:
          v21 = "8 byte align";
          break;
        case 0x500000u:
          v21 = "16 byte align";
          break;
        case 0x600000u:
          v21 = "32 byte align";
          break;
        default:
          v21 = "(no align specified)";
          if ( v20 == 7340032 )
            v21 = "64 byte align";
          break;
      }
      ExtensionApis.lpOutputRoutine("         %s\n", v21);
LABEL_105:
      if ( v5 )
      {
        switch ( v5 )
        {
          case 1:
            v22 = "Execute Only";
            break;
          case 2:
            v22 = "Read Only";
            break;
          case 3:
            v22 = "Execute Read";
            break;
          case 4:
            v22 = "Write Only";
            break;
          case 5:
            v22 = "Execute Write";
            break;
          case 6:
            v22 = "Read Write";
            break;
          case 7:
            v22 = "Execute Read Write";
            break;
          default:
            v22 = "Unknown Memory Flags";
            break;
        }
        ExtensionApis.lpOutputRoutine("         %s\n", v22);
      }
      return;
    }
    while ( 1 )
    {
      if ( (v13 & 1) != 0 )
      {
        v14 = (v13 & 1) << v6;
        if ( v14 <= 0x10000 )
        {
          if ( v14 == 0x10000 )
          {
            v19 = "Sys Heap";
          }
          else if ( v14 > 0x200 )
          {
            switch ( v14 )
            {
              case 0x800u:
                v19 = "Remove";
                break;
              case 0x1000u:
                v19 = "Communal";
                break;
              case 0x4000u:
                v19 = "Protected";
                break;
              case 0x8000u:
                v19 = "Far Data";
                break;
              default:
                goto LABEL_82;
            }
          }
          else if ( v14 == 512 )
          {
            v19 = "Info";
          }
          else
          {
            v15 = v14 - 8;
            if ( v15 )
            {
              v16 = v15 - 24;
              if ( v16 )
              {
                v17 = v16 - 32;
                if ( v17 )
                {
                  v18 = v17 - 64;
                  if ( v18 )
                  {
                    if ( v18 != 128 )
                      goto LABEL_82;
                    v19 = "Other";
                  }
                  else
                  {
                    v19 = "Uninitialized Data";
                  }
                }
                else
                {
                  v19 = "Initialized Data";
                }
              }
              else
              {
                v19 = "Code";
              }
            }
            else
            {
              v19 = "No Pad";
            }
          }
LABEL_87:
          ExtensionApis.lpOutputRoutine("         %s\n", v19);
          goto LABEL_88;
        }
        if ( v14 <= 0x8000000 )
        {
          switch ( v14 )
          {
            case 0x8000000u:
              v19 = "Not Paged";
              goto LABEL_87;
            case 0x20000u:
              v19 = "Purgeable or 16-Bit";
              goto LABEL_87;
            case 0x40000u:
              v19 = "Locked";
              goto LABEL_87;
            case 0x80000u:
              v19 = "Preload";
              goto LABEL_87;
            case 0x2000000u:
              v19 = "Discardable";
              goto LABEL_87;
            case 0x4000000u:
              v19 = "Not Cached";
              goto LABEL_87;
          }
LABEL_82:
          v19 = "RESERVED - UNKNOWN";
          goto LABEL_87;
        }
        switch ( v14 )
        {
          case 0x10000000u:
            v19 = "Shared";
            goto LABEL_87;
          case 0x20000000u:
            v5 |= 1u;
            break;
          case 0x40000000u:
            v5 |= 2u;
            break;
          case 0x80000000:
            v5 |= 4u;
            break;
          default:
            goto LABEL_82;
        }
      }
LABEL_88:
      ++v6;
      v13 >>= 1;
      if ( !v13 )
        goto LABEL_89;
    }
  }
  if ( Characteristics )
  {
    while ( (Characteristics & 1) == 0 )
    {
LABEL_37:
      ++v6;
      Characteristics >>= 1;
      if ( !Characteristics )
        goto LABEL_105;
    }
    v7 = (Characteristics & 1) << v6;
    if ( v7 > 0x400 )
    {
      switch ( v7 )
      {
        case 0x800u:
          v12 = "UCode";
          goto LABEL_36;
        case 0x8000000u:
          v12 = "Literal 8";
          goto LABEL_36;
        case 0x10000000u:
          v12 = "Literal 4";
          goto LABEL_36;
        case 0x20000000u:
          v12 = "Non-Relocatable overlay";
          break;
        case 0x40000000u:
          v12 = "Library";
          goto LABEL_36;
        case 0x80000000:
          v12 = "Init Code";
          break;
        default:
          goto LABEL_29;
      }
    }
    else
    {
      if ( v7 == 1024 )
      {
        v12 = "Uninit Data";
        goto LABEL_18;
      }
      if ( !v7 )
      {
        v12 = "Regular";
        goto LABEL_36;
      }
      v8 = v7 - 32;
      if ( v8 )
      {
        v9 = v8 - 32;
        if ( !v9 )
        {
          v12 = "Data";
          goto LABEL_18;
        }
        v10 = v9 - 64;
        if ( !v10 )
        {
          v12 = "GP Uninit Data";
          goto LABEL_18;
        }
        v11 = v10 - 128;
        if ( !v11 )
        {
          v12 = "Data";
          v5 = 2;
LABEL_36:
          ExtensionApis.lpOutputRoutine("         %s\n", v12);
          goto LABEL_37;
        }
        if ( v11 == 256 )
        {
          v12 = "GP Init Data";
LABEL_18:
          v5 = 6;
          goto LABEL_36;
        }
LABEL_29:
        v12 = "RESERVED - UNKNOWN";
        goto LABEL_36;
      }
      v12 = "Text";
    }
    v5 = 1;
    goto LABEL_36;
  }
}

```

## disassembly

```asm
0x180198870  push    rbx
0x180198872  push    rbp
0x180198873  push    rsi
0x180198874  push    rdi
0x180198875  push    r12
0x180198877  push    r13
0x180198879  push    r15
0x18019887b  sub     rsp, 40h
0x18019887f  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198886  mov     rbp, rdx
0x180198889  mov     r8, rdx
0x18019888c  mov     edx, ecx
0x18019888e  lea     rcx, aSectionHeaderH; "\nSECTION HEADER #%hX\n%8.8s name"
0x180198895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019889a  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801988a1  lea     rcx, asc_18022B9A8; "\n"
0x1801988a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801988ad  mov     ecx, [rbp+18h]
0x1801988b0  lea     rax, aVirtualSize; "virtual size"
0x1801988b7  mov     edx, [rbp+14h]
0x1801988ba  lea     r8, aPhysicalAddres; "physical address"
0x1801988c1  mov     r10d, [rbp+10h]
0x1801988c5  mov     r13d, 1
0x1801988cb  cmp     cs:gdft, r13d
0x1801988d2  mov     r9d, [rbp+0Ch]
0x1801988d6  mov     [rsp+78h+var_48], ecx
0x1801988da  cmovnz  r8, rax
0x1801988de  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801988e5  lea     rcx, a8lxS8lxVirtual; "%8lX %s\n%8lX virtual address\n%8lX siz"...
0x1801988ec  mov     [rsp+78h+var_50], edx
0x1801988f0  mov     edx, [rbp+8]
0x1801988f3  mov     dword ptr [rsp+78h+var_58], r10d
0x1801988f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801988fd  mov     ecx, [rbp+24h]
0x180198900  movzx   r9d, word ptr [rbp+22h]
0x180198905  movzx   r8d, word ptr [rbp+20h]
0x18019890a  mov     edx, [rbp+1Ch]
0x18019890d  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198914  mov     dword ptr [rsp+78h+var_58], ecx
0x180198918  lea     rcx, a8lxFilePointer_0; "%8lX file pointer to line numbers\n%8hX"...
0x18019891f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198924  mov     edi, [rbp+24h]
0x180198927  xor     r12d, r12d
0x18019892a  cmp     cs:gdft, 3
0x180198931  mov     ebx, r12d
0x180198934  mov     esi, r12d
0x180198937  jnz     loc_180198A60
0x18019893d  test    edi, edi
0x18019893f  jz      loc_180198D2E
0x180198945  lea     ebp, [r13+5]
0x180198949  lea     r15d, [r13+1]
0x18019894d  mov     eax, edi
0x18019894f  and     eax, r13d
0x180198952  jz      loc_180198A50
0x180198958  mov     ecx, esi
0x18019895a  shl     eax, cl
0x18019895c  cmp     eax, 400h
0x180198961  ja      short loc_1801989D6
0x180198963  jz      short loc_1801989CD
0x180198965  test    eax, eax
0x180198967  jz      short loc_1801989C4
0x180198969  sub     eax, 20h ; ' '
0x18019896c  jz      short loc_1801989B7
0x18019896e  sub     eax, 20h ; ' '
0x180198971  jz      short loc_1801989A8
0x180198973  sub     eax, 40h ; '@'
0x180198976  jz      short loc_18019899F
0x180198978  sub     eax, 80h
0x18019897d  jz      short loc_18019898F
0x18019897f  cmp     eax, 100h
0x180198984  jnz     short loc_180198A00
0x180198986  lea     rdx, aGpInitData; "GP Init Data"
0x18019898d  jmp     short loc_1801989AF
0x18019898f  lea     rdx, aData; "Data"
0x180198996  movzx   ebx, r15w
0x18019899a  jmp     loc_180198A3D
0x18019899f  lea     rdx, aGpUninitData; "GP Uninit Data"
0x1801989a6  jmp     short loc_1801989AF
0x1801989a8  lea     rdx, aData; "Data"
0x1801989af  movzx   ebx, bp
0x1801989b2  jmp     loc_180198A3D
0x1801989b7  lea     rdx, aText; "Text"
0x1801989be  movzx   ebx, r13w
0x1801989c2  jmp     short loc_180198A3D
0x1801989c4  lea     rdx, aRegular; "Regular"
0x1801989cb  jmp     short loc_180198A3D
0x1801989cd  lea     rdx, aUninitData; "Uninit Data"
0x1801989d4  jmp     short loc_1801989AF
0x1801989d6  cmp     eax, 800h
0x1801989db  jz      short loc_180198A36
0x1801989dd  cmp     eax, 8000000h
0x1801989e2  jz      short loc_180198A2D
0x1801989e4  cmp     eax, 10000000h
0x1801989e9  jz      short loc_180198A24
0x1801989eb  cmp     eax, 20000000h
0x1801989f0  jz      short loc_180198A1B
0x1801989f2  cmp     eax, 40000000h
0x1801989f7  jz      short loc_180198A12
0x1801989f9  cmp     eax, 80000000h
0x1801989fe  jz      short loc_180198A09
0x180198a00  lea     rdx, aReservedUnknow; "RESERVED - UNKNOWN"
0x180198a07  jmp     short loc_180198A3D
0x180198a09  lea     rdx, aInitCode; "Init Code"
0x180198a10  jmp     short loc_1801989BE
0x180198a12  lea     rdx, aLibrary; "Library"
0x180198a19  jmp     short loc_180198A3D
0x180198a1b  lea     rdx, aNonRelocatable; "Non-Relocatable overlay"
0x180198a22  jmp     short loc_1801989BE
0x180198a24  lea     rdx, aLiteral4; "Literal 4"
0x180198a2b  jmp     short loc_180198A3D
0x180198a2d  lea     rdx, aLiteral8; "Literal 8"
0x180198a34  jmp     short loc_180198A3D
0x180198a36  lea     rdx, aUcode; "UCode"
0x180198a3d  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198a44  lea     rcx, aS_18; "         %s\n"
0x180198a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198a50  add     esi, r13d
0x180198a53  shr     edi, 1
0x180198a55  jnz     loc_18019894D
0x180198a5b  jmp     loc_180198CAA
0x180198a60  and     edi, 0FF8FFFFFh
0x180198a66  jz      loc_180198C16
0x180198a6c  mov     eax, edi
0x180198a6e  and     eax, r13d
0x180198a71  jz      loc_180198C0B
0x180198a77  mov     ecx, esi
0x180198a79  shl     eax, cl
0x180198a7b  cmp     eax, 10000h
0x180198a80  ja      loc_180198B58
0x180198a86  jz      loc_180198B4C
0x180198a8c  cmp     eax, 200h
0x180198a91  ja      short loc_180198AFC
0x180198a93  jz      short loc_180198AF0
0x180198a95  sub     eax, 8
0x180198a98  jz      short loc_180198AE4
0x180198a9a  sub     eax, 18h
0x180198a9d  jz      short loc_180198AD8
0x180198a9f  sub     eax, 20h ; ' '
0x180198aa2  jz      short loc_180198ACC
0x180198aa4  sub     eax, 40h ; '@'
0x180198aa7  jz      short loc_180198AC0
0x180198aa9  cmp     eax, 80h
0x180198aae  jnz     loc_180198BD6
0x180198ab4  lea     rdx, aOther; "Other"
0x180198abb  jmp     loc_180198BF8
0x180198ac0  lea     rdx, aUninitializedD; "Uninitialized Data"
0x180198ac7  jmp     loc_180198BF8
0x180198acc  lea     rdx, aInitializedDat; "Initialized Data"
0x180198ad3  jmp     loc_180198BF8
0x180198ad8  lea     rdx, aCode_0; "Code"
0x180198adf  jmp     loc_180198BF8
0x180198ae4  lea     rdx, aNoPad; "No Pad"
0x180198aeb  jmp     loc_180198BF8
0x180198af0  lea     rdx, aInfo_0; "Info"
0x180198af7  jmp     loc_180198BF8
0x180198afc  cmp     eax, 800h
0x180198b01  jz      short loc_180198B40
0x180198b03  cmp     eax, 1000h
0x180198b08  jz      short loc_180198B34
0x180198b0a  cmp     eax, 4000h
0x180198b0f  jz      short loc_180198B28
0x180198b11  cmp     eax, 8000h
0x180198b16  jnz     loc_180198BD6
0x180198b1c  lea     rdx, aFarData; "Far Data"
0x180198b23  jmp     loc_180198BF8
0x180198b28  lea     rdx, aProtected; "Protected"
0x180198b2f  jmp     loc_180198BF8
0x180198b34  lea     rdx, aCommunal; "Communal"
0x180198b3b  jmp     loc_180198BF8
0x180198b40  lea     rdx, aRemove_0; "Remove"
0x180198b47  jmp     loc_180198BF8
0x180198b4c  lea     rdx, aSysHeap; "Sys Heap"
0x180198b53  jmp     loc_180198BF8
0x180198b58  cmp     eax, 8000000h
0x180198b5d  ja      short loc_180198BBA
0x180198b5f  jz      short loc_180198BB1
0x180198b61  cmp     eax, 20000h
0x180198b66  jz      short loc_180198BA8
0x180198b68  cmp     eax, 40000h
0x180198b6d  jz      short loc_180198B9F
0x180198b6f  cmp     eax, 80000h
0x180198b74  jz      short loc_180198B96
0x180198b76  cmp     eax, 2000000h
0x180198b7b  jz      short loc_180198B8D
0x180198b7d  cmp     eax, 4000000h
0x180198b82  jnz     short loc_180198BD6
0x180198b84  lea     rdx, aNotCached; "Not Cached"
0x180198b8b  jmp     short loc_180198BF8
0x180198b8d  lea     rdx, aDiscardable; "Discardable"
0x180198b94  jmp     short loc_180198BF8
0x180198b96  lea     rdx, aPreload; "Preload"
0x180198b9d  jmp     short loc_180198BF8
0x180198b9f  lea     rdx, aLocked; "Locked"
0x180198ba6  jmp     short loc_180198BF8
0x180198ba8  lea     rdx, aPurgeableOr16B; "Purgeable or 16-Bit"
0x180198baf  jmp     short loc_180198BF8
0x180198bb1  lea     rdx, aNotPaged; "Not Paged"
0x180198bb8  jmp     short loc_180198BF8
0x180198bba  cmp     eax, 10000000h
0x180198bbf  jz      short loc_180198BF1
0x180198bc1  cmp     eax, 20000000h
0x180198bc6  jz      short loc_180198BEB
0x180198bc8  cmp     eax, 40000000h
0x180198bcd  jz      short loc_180198BE5
0x180198bcf  cmp     eax, 80000000h
0x180198bd4  jz      short loc_180198BDF
0x180198bd6  lea     rdx, aReservedUnknow; "RESERVED - UNKNOWN"
0x180198bdd  jmp     short loc_180198BF8
0x180198bdf  or      bx, 4
0x180198be3  jmp     short loc_180198C0B
0x180198be5  or      bx, 2
0x180198be9  jmp     short loc_180198C0B
0x180198beb  or      bx, r13w
0x180198bef  jmp     short loc_180198C0B
0x180198bf1  lea     rdx, aShared; "Shared"
0x180198bf8  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198bff  lea     rcx, aS_18; "         %s\n"
0x180198c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198c0b  add     esi, r13d
0x180198c0e  shr     edi, 1
0x180198c10  jnz     loc_180198A6C
0x180198c16  mov     eax, [rbp+24h]
0x180198c19  mov     r8d, 700000h
0x180198c1f  and     eax, r8d
0x180198c22  cmp     eax, 100000h
0x180198c27  jz      short loc_180198C90
0x180198c29  cmp     eax, 200000h
0x180198c2e  jz      short loc_180198C87
0x180198c30  cmp     eax, 300000h
0x180198c35  jz      short loc_180198C7E
0x180198c37  cmp     eax, 400000h
0x180198c3c  jz      short loc_180198C75
0x180198c3e  cmp     eax, 500000h
0x180198c43  jz      short loc_180198C6C
0x180198c45  cmp     eax, 600000h
0x180198c4a  jz      short loc_180198C63
0x180198c4c  cmp     eax, r8d
0x180198c4f  lea     rdx, aNoAlignSpecifi; "(no align specified)"
0x180198c56  lea     rcx, a64ByteAlign; "64 byte align"
0x180198c5d  cmovz   rdx, rcx
0x180198c61  jmp     short loc_180198C97
0x180198c63  lea     rdx, a32ByteAlign; "32 byte align"
0x180198c6a  jmp     short loc_180198C97
0x180198c6c  lea     rdx, a16ByteAlign; "16 byte align"
0x180198c73  jmp     short loc_180198C97
0x180198c75  lea     rdx, a8ByteAlign; "8 byte align"
0x180198c7c  jmp     short loc_180198C97
0x180198c7e  lea     rdx, a4ByteAlign; "4 byte align"
0x180198c85  jmp     short loc_180198C97
0x180198c87  lea     rdx, a2ByteAlign; "2 byte align"
0x180198c8e  jmp     short loc_180198C97
0x180198c90  lea     rdx, a1ByteAlign; "1 byte align"
0x180198c97  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198c9e  lea     rcx, aS_18; "         %s\n"
0x180198ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198caa  test    bx, bx
0x180198cad  jz      short loc_180198D2E
0x180198caf  movzx   ecx, bx
0x180198cb2  sub     ecx, r13d
0x180198cb5  jz      short loc_180198D14
0x180198cb7  sub     ecx, r13d
0x180198cba  jz      short loc_180198D0B
0x180198cbc  sub     ecx, r13d
0x180198cbf  jz      short loc_180198D02
0x180198cc1  sub     ecx, r13d
0x180198cc4  jz      short loc_180198CF9
0x180198cc6  sub     ecx, r13d
0x180198cc9  jz      short loc_180198CF0
0x180198ccb  sub     ecx, r13d
0x180198cce  jz      short loc_180198CE7
0x180198cd0  cmp     ecx, r13d
0x180198cd3  jz      short loc_180198CDE
0x180198cd5  lea     rdx, aUnknownMemoryF; "Unknown Memory Flags"
0x180198cdc  jmp     short loc_180198D1B
0x180198cde  lea     rdx, aExecuteReadWri; "Execute Read Write"
0x180198ce5  jmp     short loc_180198D1B
0x180198ce7  lea     rdx, aReadWrite; "Read Write"
0x180198cee  jmp     short loc_180198D1B
0x180198cf0  lea     rdx, aExecuteWrite; "Execute Write"
0x180198cf7  jmp     short loc_180198D1B
0x180198cf9  lea     rdx, aWriteOnly; "Write Only"
0x180198d00  jmp     short loc_180198D1B
0x180198d02  lea     rdx, aExecuteRead; "Execute Read"
0x180198d09  jmp     short loc_180198D1B
0x180198d0b  lea     rdx, aReadOnly; "Read Only"
0x180198d12  jmp     short loc_180198D1B
0x180198d14  lea     rdx, aExecuteOnly; "Execute Only"
0x180198d1b  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198d22  lea     rcx, aS_18; "         %s\n"
0x180198d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198d2e  add     rsp, 40h
0x180198d32  pop     r15
0x180198d34  pop     r13
0x180198d36  pop     r12
0x180198d38  pop     rdi
0x180198d39  pop     rsi
0x180198d3a  pop     rbp
0x180198d3b  pop     rbx
0x180198d3c  retn
```
