# DumpChainTemplate(bool,_CERT_INFO const *)

- ea: `0x18001a254`
- end: `0x18001a3fb`
- name: `?DumpChainTemplate@@YAX_NPEBU_CERT_INFO@@@Z`
- size: `423`
- prototype: `void __fastcall(char, const struct _CERT_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001af48`

## callees

- `0x180007da0`
- `0x180008400`
- `0x180012450`
- `0x18001a254`
- `0x18001b7ac`
- `0x18001e080`
- `0x180021e30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3ed`
- `CRYPT32!CertFindExtension` at `0x18001a28f`
- `CRYPT32!CertFindExtension` at `0x18001a325`
- `CRYPT32!CertFindExtension` at `0x18001a28f`
- `CRYPT32!CertFindExtension` at `0x18001a325`

## string_xrefs

- `0x18001a2e8`: `  Template: %ws\n`
- `0x18001a39b`: `  Template: %ws\n`
- `0x18001a301`: `  Template: %ws\n`
- `0x18001a3a7`: `  Template: %ws\n`
- `0x18001a3b8`: `  Template: %hs\n`
- `0x18001a3d0`: `  Template: %hs\n`

## pseudocode

```c
void __fastcall DumpChainTemplate(char a1, const struct _CERT_INFO *a2)
{
  PCERT_EXTENSION Extension; // rax
  int v5; // eax
  PCERT_EXTENSION v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  _WORD *OIDNameA; // rax

  Extension = CertFindExtension("1.3.6.1.4.1.311.20.2", a2->cExtension, a2->rgExtension);
  if ( Extension )
  {
    if ( (unsigned int)myDecodeObjectEx(1, 24, Extension->Value.pbData, Extension->Value.cbData, 0) )
    {
      if ( a1 )
        DbgPrintf(0xFFFFFFFF, "  Template: %ws\n", MEMORY[0x10]);
      else
        myConsolePrintf(L"  Template: %ws\n", MEMORY[0x10]);
    }
    else
    {
      v5 = myHLastError();
      CSPrintErrorLineFile(0x130601A3u, v5);
    }
  }
  v6 = CertFindExtension("1.3.6.1.4.1.311.21.7", a2->cExtension, a2->rgExtension);
  if ( v6 )
  {
    if ( (unsigned int)myDecodeObjectEx(1, 64, v6->Value.pbData, v6->Value.cbData, 0) )
    {
      OIDNameA = (_WORD *)myGetOIDNameA(v7, MEMORY[0]);
      if ( OIDNameA && *OIDNameA )
      {
        if ( a1 )
          DbgPrintf(0xFFFFFFFF, "  Template: %ws\n", OIDNameA);
        else
          myConsolePrintf(L"  Template: %ws\n", OIDNameA);
      }
      else if ( a1 )
      {
        DbgPrintf(0xFFFFFFFF, "  Template: %hs\n", MEMORY[0]);
      }
      else
      {
        myConsolePrintf(L"  Template: %hs\n", MEMORY[0]);
      }
    }
    else
    {
      v8 = myHLastError();
      CSPrintErrorLineFile(0x131E01A3u, v8);
    }
  }
  LocalFree(0);
  LocalFree(0);
}

```

## disassembly

```asm
0x18001a254  push    rbp
0x18001a256  push    rbx
0x18001a257  push    rdi
0x18001a258  mov     rbp, rsp
0x18001a25b  sub     rsp, 40h
0x18001a25f  mov     r8, [rdx+0C8h]; rgExtensions
0x18001a266  mov     rdi, rdx
0x18001a269  mov     edx, [rdx+0C0h]; cExtensions
0x18001a26f  mov     bl, cl
0x18001a271  lea     rcx, a136141311202_0; "1.3.6.1.4.1.311.20.2"
0x18001a278  mov     [rbp+arg_18], 0
0x18001a280  mov     [rbp+hMem], 0
0x18001a288  mov     [rbp+arg_8], 0
0x18001a28f  call    cs:__imp_CertFindExtension
0x18001a295  test    rax, rax
0x18001a298  jz      short loc_18001A311
0x18001a29a  mov     r9d, [rax+10h]
0x18001a29e  lea     rcx, [rbp+arg_8]
0x18001a2a2  mov     r8, [rax+18h]
0x18001a2a6  mov     edx, 18h
0x18001a2ab  mov     [rsp+40h+var_8], rcx
0x18001a2b0  lea     rcx, [rbp+arg_18]
0x18001a2b4  mov     [rsp+40h+var_10], rcx
0x18001a2b9  mov     [rsp+40h+var_20], 0
0x18001a2c1  lea     ecx, [rdx-17h]
0x18001a2c4  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x18001a2c9  test    eax, eax
0x18001a2cb  jnz     short loc_18001A2E0
0x18001a2cd  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a2d2  mov     edx, eax; int
0x18001a2d4  mov     ecx, 130601A3h; unsigned int
0x18001a2d9  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a2de  jmp     short loc_18001A311
0x18001a2e0  test    bl, bl
0x18001a2e2  jz      short loc_18001A2FD
0x18001a2e4  mov     r8, [rbp+arg_18]
0x18001a2e8  lea     rdx, aTemplateWs; "  Template: %ws\n"
0x18001a2ef  or      ecx, 0FFFFFFFFh; unsigned int
0x18001a2f2  mov     r8, [r8+10h]
0x18001a2f6  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x18001a2fb  jmp     short loc_18001A311
0x18001a2fd  mov     rdx, [rbp+arg_18]
0x18001a301  lea     rcx, aTemplateWs_0; "  Template: %ws\n"
0x18001a308  mov     rdx, [rdx+10h]
0x18001a30c  call    ?myConsolePrintf@@YAHPEBGZZ; myConsolePrintf(ushort const *,...)
0x18001a311  mov     r8, [rdi+0C8h]; rgExtensions
0x18001a318  lea     rcx, a136141311217_0; "1.3.6.1.4.1.311.21.7"
0x18001a31f  mov     edx, [rdi+0C0h]; cExtensions
0x18001a325  call    cs:__imp_CertFindExtension
0x18001a32b  test    rax, rax
0x18001a32e  jz      loc_18001A3DF
0x18001a334  mov     r9d, [rax+10h]
0x18001a338  lea     rdx, [rbp+arg_8]
0x18001a33c  mov     r8, [rax+18h]
0x18001a340  mov     [rsp+40h+var_8], rdx
0x18001a345  lea     rdx, [rbp+hMem]
0x18001a349  mov     [rsp+40h+var_10], rdx
0x18001a34e  mov     edx, 40h ; '@'
0x18001a353  mov     [rsp+40h+var_20], 0
0x18001a35b  lea     ecx, [rdx-3Fh]
0x18001a35e  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x18001a363  test    eax, eax
0x18001a365  jnz     short loc_18001A37A
0x18001a367  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001a36c  mov     edx, eax; int
0x18001a36e  mov     ecx, 131E01A3h; unsigned int
0x18001a373  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001a378  jmp     short loc_18001A3DF
0x18001a37a  mov     rdx, [rbp+hMem]
0x18001a37e  mov     rdx, [rdx]
0x18001a381  call    ?myGetOIDNameA@@YAPEBGW4KeyPreference@@PEBD@Z; myGetOIDNameA(KeyPreference,char const *)
0x18001a386  test    rax, rax
0x18001a389  jz      short loc_18001A3B0
0x18001a38b  xor     r8d, r8d
0x18001a38e  cmp     r8w, [rax]
0x18001a392  jz      short loc_18001A3B0
0x18001a394  test    bl, bl
0x18001a396  jz      short loc_18001A3A4
0x18001a398  mov     r8, rax
0x18001a39b  lea     rdx, aTemplateWs; "  Template: %ws\n"
0x18001a3a2  jmp     short loc_18001A3C2
0x18001a3a4  mov     rdx, rax
0x18001a3a7  lea     rcx, aTemplateWs_0; "  Template: %ws\n"
0x18001a3ae  jmp     short loc_18001A3DA
0x18001a3b0  test    bl, bl
0x18001a3b2  jz      short loc_18001A3CC
0x18001a3b4  mov     r8, [rbp+hMem]
0x18001a3b8  lea     rdx, aTemplateHs_0; "  Template: %hs\n"
0x18001a3bf  mov     r8, [r8]
0x18001a3c2  or      ecx, 0FFFFFFFFh; unsigned int
0x18001a3c5  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x18001a3ca  jmp     short loc_18001A3DF
0x18001a3cc  mov     rdx, [rbp+hMem]
0x18001a3d0  lea     rcx, aTemplateHs; "  Template: %hs\n"
0x18001a3d7  mov     rdx, [rdx]
0x18001a3da  call    ?myConsolePrintf@@YAHPEBGZZ; myConsolePrintf(ushort const *,...)
0x18001a3df  mov     rcx, [rbp+hMem]; hMem
0x18001a3e3  call    cs:__imp_LocalFree
0x18001a3e9  mov     rcx, [rbp+arg_18]; hMem
0x18001a3ed  call    cs:__imp_LocalFree
0x18001a3f3  add     rsp, 40h
0x18001a3f7  pop     rdi
0x18001a3f8  pop     rbx
0x18001a3f9  pop     rbp
0x18001a3fa  retn
```
