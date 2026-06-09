# dhDumpImage(unsigned __int64,ulong)

- ea: `0x180198058`
- end: `0x18019830e`
- name: `?dhDumpImage@@YAX_KK@Z`
- size: `694`
- prototype: `void __fastcall(unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180196670`
- `0x1801990f0`

## callees

- `0x180027430`
- `0x180197368`
- `0x1801977a4`
- `0x180198058`
- `0x180198314`
- `0x180198d44`
- `0x180198fa0`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801982b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180202329`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801982b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180202329`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801981e4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801981e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801980c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801980c6`

## string_xrefs

- `0x180198242`: `Can't read section headers\n`
- `0x1801980ce`: `Can't read file header: error == %d\n`

## pseudocode

```c
void __fastcall dhDumpImage(__int64 a1, char a2)
{
  unsigned __int64 v4; // rcx
  void (*lpOutputRoutine)(const char *, ...); // rbx
  DWORD LastError; // eax
  __int64 v7; // rbx
  const CHAR *v8; // rcx
  IMAGE_FILE_HEADER *p_FileHeader; // rcx
  __int64 NumberOfSections; // rax
  void *v11; // rdx
  _DWORD v12[4]; // [rsp+30h] [rbp-68h] BYREF
  _WORD v13[30]; // [rsp+40h] [rbp-58h] BYREF
  int v14; // [rsp+7Ch] [rbp-1Ch]

  memset_0(v13, 0, 0x40u);
  v12[0] = 0;
  gBase = a1;
  if ( !((unsigned int (__fastcall *)(__int64, _WORD *, __int64, _DWORD *))ExtensionApis.lpReadProcessMemoryRoutine)(
          a1,
          v13,
          64,
          v12) )
  {
    lpOutputRoutine = ExtensionApis.lpOutputRoutine;
    LastError = GetLastError();
    lpOutputRoutine("Can't read file header: error == %d\n", LastError);
    return;
  }
  if ( v12[0] != 64 || v13[0] != 23117 )
  {
    v8 = "No file header\n";
    goto LABEL_32;
  }
  v7 = gBase + v14;
  gImageNtHeadersAddr = v7;
  if ( !dhReadNtHeader(v4, &gImageNtHeaders) )
  {
    v8 = "Bad file header\n";
LABEL_32:
    ExtensionApis.lpOutputRoutine(v8);
    return;
  }
  p_FileHeader = &gImageNtHeaders.FileHeader;
  gImageFileHdr = (__int64)&gImageNtHeaders.FileHeader;
  gImageOptionalHdr = (__int64)&gImageNtHeaders.OptionalHeader;
  if ( gImageNtHeaders.FileHeader.SizeOfOptionalHeader == 56 )
  {
    gdft = 3;
  }
  else if ( (gImageNtHeaders.FileHeader.Characteristics & 0x2000) != 0
         || (gImageNtHeaders.FileHeader.Characteristics & 2) != 0 )
  {
    gdft = 2;
  }
  else
  {
    gdft = gImageNtHeaders.FileHeader.SizeOfOptionalHeader == 0;
  }
  gImage64 = gImageNtHeaders.OptionalHeader.Magic == 523;
  gImagePtrSize = 4;
  if ( gImageNtHeaders.OptionalHeader.Magic == 523 )
    gImagePtrSize = 8;
  if ( (a2 & 1) != 0 )
  {
    dhDumpHeaders();
    p_FileHeader = (IMAGE_FILE_HEADER *)gImageFileHdr;
  }
  if ( (a2 & 2) != 0 )
  {
    NumberOfSections = p_FileHeader->NumberOfSections;
    gNumSections = p_FileHeader->NumberOfSections;
    v11 = malloc(40 * NumberOfSections);
    gSectionHdrs = v11;
    if ( !v11 )
    {
      v8 = "Cannot allocate memory for dumping sections\n";
      goto LABEL_32;
    }
    gSectionHdrsAddr = v7 + *(unsigned __int16 *)(gImageFileHdr + 16) + 24LL;
    if ( ((unsigned int (__fastcall *)(__int64, void *, _QWORD, _DWORD *))ExtensionApis.lpReadProcessMemoryRoutine)(
           gSectionHdrsAddr,
           v11,
           (unsigned int)(40 * gNumSections),
           v12) )
    {
      if ( v12[0] != 40LL * (unsigned int)gNumSections )
      {
        ExtensionApis.lpOutputRoutine("\n***\n*** Some section headers may be missing ***\n***\n\n");
        gNumSections = (unsigned __int16)(v12[0] / 0x28u);
      }
      dhDumpSections();
    }
    else
    {
      ExtensionApis.lpOutputRoutine("Can't read section headers\n");
    }
    if ( gSectionHdrs )
    {
      free(gSectionHdrs);
      gSectionHdrs = 0;
    }
  }
  if ( (a2 & 4) != 0 )
    dhDumpExports();
  if ( (a2 & 8) != 0 )
    dhDumpImports();
}

```

## disassembly

```asm
0x180198058  mov     [rsp+arg_8], rbx
0x18019805d  mov     [rsp+arg_10], rsi
0x180198062  push    rdi
0x180198063  sub     rsp, 90h
0x18019806a  mov     rax, cs:__security_cookie
0x180198071  xor     rax, rsp
0x180198074  mov     [rsp+98h+var_18], rax
0x18019807c  mov     edi, edx
0x18019807e  mov     rbx, rcx
0x180198081  xor     edx, edx; Val
0x180198083  lea     r8d, [rdx+40h]; Size
0x180198087  lea     rcx, [rsp+98h+var_58]; void *
0x18019808c  call    memset_0
0x180198091  xor     esi, esi
0x180198093  mov     [rsp+98h+var_68], esi
0x180198097  mov     cs:gBase, rbx
0x18019809e  lea     r9, [rsp+98h+var_68]
0x1801980a3  lea     r8d, [rsi+40h]
0x1801980a7  lea     rdx, [rsp+98h+var_58]
0x1801980ac  mov     rcx, rbx
0x1801980af  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x1801980b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801980bb  test    eax, eax
0x1801980bd  jnz     short loc_1801980E2
0x1801980bf  mov     rbx, cs:ExtensionApis.lpOutputRoutine
0x1801980c6  call    cs:__imp_GetLastError
0x1801980cc  mov     edx, eax
0x1801980ce  lea     rcx, aCanTReadFileHe; "Can't read file header: error == %d\n"
0x1801980d5  mov     rax, rbx
0x1801980d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801980dd  jmp     loc_1801982E9
0x1801980e2  cmp     [rsp+98h+var_68], 40h ; '@'
0x1801980e7  jnz     loc_1801982D6
0x1801980ed  mov     eax, 5A4Dh
0x1801980f2  cmp     [rsp+98h+var_58], ax
0x1801980f7  jnz     loc_1801982D6
0x1801980fd  movsxd  rbx, [rsp+98h+var_1C]
0x180198102  add     rbx, cs:gBase
0x180198109  mov     cs:gImageNtHeadersAddr, rbx
0x180198110  lea     rdx, gImageNtHeaders; struct _IMAGE_NT_HEADERS64 *
0x180198117  call    ?dhReadNtHeader@@YAH_KPEAU_IMAGE_NT_HEADERS64@@@Z; dhReadNtHeader(unsigned __int64,_IMAGE_NT_HEADERS64 *)
0x18019811c  test    eax, eax
0x18019811e  jnz     short loc_18019812C
0x180198120  lea     rcx, aBadFileHeader; "Bad file header\n"
0x180198127  jmp     loc_1801982DD
0x18019812c  lea     rcx, gImageNtHeaders.FileHeader
0x180198133  mov     cs:gImageFileHdr, rcx
0x18019813a  lea     rax, gImageNtHeaders.OptionalHeader
0x180198141  mov     cs:gImageOptionalHdr, rax
0x180198148  movzx   edx, cs:gImageNtHeaders.FileHeader.SizeOfOptionalHeader
0x18019814f  cmp     dx, 38h ; '8'
0x180198153  jnz     short loc_180198161
0x180198155  mov     cs:gdft, 3
0x18019815f  jmp     short loc_18019818D
0x180198161  movzx   eax, cs:gImageNtHeaders.FileHeader.Characteristics
0x180198168  bt      ax, 0Dh
0x18019816d  jb      short loc_180198183
0x18019816f  test    al, 2
0x180198171  jnz     short loc_180198183
0x180198173  mov     eax, esi
0x180198175  test    dx, dx
0x180198178  setz    al
0x18019817b  mov     cs:gdft, eax
0x180198181  jmp     short loc_18019818D
0x180198183  mov     cs:gdft, 2
0x18019818d  mov     edx, 20Bh
0x180198192  cmp     cs:gImageNtHeaders.OptionalHeader.Magic, dx
0x180198199  setz    cs:gImage64
0x1801981a0  mov     cs:gImagePtrSize, 4
0x1801981aa  jnz     short loc_1801981B6
0x1801981ac  mov     cs:gImagePtrSize, 8
0x1801981b6  test    dil, 1
0x1801981ba  jz      short loc_1801981C8
0x1801981bc  call    ?dhDumpHeaders@@YAXXZ; dhDumpHeaders(void)
0x1801981c1  mov     rcx, cs:gImageFileHdr
0x1801981c8  test    dil, 2
0x1801981cc  jz      loc_1801982BE
0x1801981d2  movzx   eax, word ptr [rcx+2]
0x1801981d6  mov     cs:gNumSections, eax
0x1801981dc  lea     rcx, [rax+rax*4]
0x1801981e0  shl     rcx, 3; Size
0x1801981e4  call    cs:__imp_malloc
0x1801981ea  mov     rdx, rax
0x1801981ed  mov     cs:gSectionHdrs, rax
0x1801981f4  test    rax, rax
0x1801981f7  jnz     short loc_180198205
0x1801981f9  lea     rcx, aCannotAllocate; "Cannot allocate memory for dumping sect"...
0x180198200  jmp     loc_1801982DD
0x180198205  mov     rax, cs:gImageFileHdr
0x18019820c  movzx   ecx, word ptr [rax+10h]
0x180198210  add     rcx, 18h
0x180198214  add     rcx, rbx
0x180198217  mov     cs:gSectionHdrsAddr, rcx
0x18019821e  mov     r8d, cs:gNumSections
0x180198225  lea     r8d, [r8+r8*4]
0x180198229  shl     r8d, 3
0x18019822d  lea     r9, [rsp+98h+var_68]
0x180198232  mov     rax, cs:ExtensionApis.lpReadProcessMemoryRoutine
0x180198239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019823e  test    eax, eax
0x180198240  jnz     short loc_180198257
0x180198242  lea     rcx, aCanTReadSectio; "Can't read section headers\n"
0x180198249  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180198250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198255  jmp     short loc_1801982A5
0x180198257  mov     eax, cs:gNumSections
0x18019825d  lea     rcx, [rax+rax*4]
0x180198261  shl     rcx, 3
0x180198265  mov     eax, [rsp+98h+var_68]
0x180198269  cmp     rax, rcx
0x18019826c  jz      short loc_18019829F
0x18019826e  lea     rcx, aSomeSectionHea; "\n***\n*** Some section headers may be "...
0x180198275  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019827c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198281  mov     ecx, [rsp+98h+var_68]
0x180198285  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18019828f  mul     rcx
0x180198292  shr     rdx, 5
0x180198296  movzx   eax, dx
0x180198299  mov     cs:gNumSections, eax
0x18019829f  call    ?dhDumpSections@@YAXXZ; dhDumpSections(void)
0x1801982a4  nop
0x1801982a5  mov     rcx, cs:gSectionHdrs; Block
0x1801982ac  test    rcx, rcx
0x1801982af  jz      short loc_1801982BE
0x1801982b1  call    cs:__imp_free
0x1801982b7  mov     cs:gSectionHdrs, rsi
0x1801982be  test    dil, 4
0x1801982c2  jz      short loc_1801982C9
0x1801982c4  call    ?dhDumpExports@@YAXXZ; dhDumpExports(void)
0x1801982c9  test    dil, 8
0x1801982cd  jz      short loc_1801982E9
0x1801982cf  call    ?dhDumpImports@@YAXXZ; dhDumpImports(void)
0x1801982d4  jmp     short loc_1801982E9
0x1801982d6  lea     rcx, aNoFileHeader; "No file header\n"
0x1801982dd  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x1801982e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801982e9  mov     rcx, [rsp+98h+var_18]
0x1801982f1  xor     rcx, rsp; StackCookie
0x1801982f4  call    __security_check_cookie
0x1801982f9  lea     r11, [rsp+98h+var_8]
0x180198301  mov     rbx, [r11+18h]
0x180198305  mov     rsi, [r11+20h]
0x180198309  mov     rsp, r11
0x18019830c  pop     rdi
0x18019830d  retn
0x180202314  push    rbp
0x180202316  sub     rsp, 30h
0x18020231a  mov     rbp, rdx
0x18020231d  mov     rcx, cs:gSectionHdrs; Block
0x180202324  test    rcx, rcx
0x180202327  jz      short loc_18020233A
0x180202329  call    cs:__imp_free
0x18020232f  mov     cs:gSectionHdrs, 0
0x18020233a  add     rsp, 30h
0x18020233e  pop     rbp
0x18020233f  retn
```
