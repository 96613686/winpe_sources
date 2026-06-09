# FTCache::MatchNetbiosName(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)

- ea: `0x1800295ac`
- end: `0x180029704`
- name: `?MatchNetbiosName@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z`
- size: `344`
- prototype: `int(FTCache *__hidden this, struct _UNICODE_STRING *, unsigned __int8 *, struct _UNICODE_STRING *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002901c`
- `0x180029928`
- `0x180029c4c`

## callees

- `0x18000fd18`
- `0x180021aa8`
- `0x180021ad4`
- `0x180022210`
- `0x180022278`
- `0x1800295ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002964a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002964a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800295c5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800295c5`

## pseudocode

```c
__int64 __fastcall FTCache::MatchNetbiosName(
        FTCache *this,
        struct _UNICODE_STRING *a2,
        unsigned __int8 *a3,
        struct _UNICODE_STRING *a4,
        void **a5)
{
  _QWORD *v7; // rax
  char *v8; // r14
  char *i; // rbx
  __int64 v10; // rax
  FTCache::TLN_ENTRY *v11; // rcx
  unsigned int v12; // ebx
  __int64 v14; // rdx
  void *v15; // rbx

  v7 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 424), a2);
  if ( v7 )
  {
    v8 = (char *)(v7 + 3);
    for ( i = (char *)v7[3]; i != v8; i = *(char **)i )
    {
      v10 = *((_QWORD *)i + 6);
      if ( v10 && (i[80] & 0xF) == 0 && !*(_BYTE *)(v10 + 40) )
      {
        v11 = *(FTCache::TLN_ENTRY **)(v10 + 56);
        if ( v11 )
        {
          if ( !FTCache::TLN_ENTRY::Enabled(v11) )
            continue;
        }
        else if ( *(_WORD *)(v10 + 72) )
        {
          continue;
        }
        if ( !FTCache::TDO_ENTRY::Excludes(*((FTCache::TDO_ENTRY **)i + 5), *((const struct _UNICODE_STRING **)i + 8)) )
        {
          v14 = *((_QWORD *)i + 5);
          v15 = *(void **)(v14 + 16);
          *a3 = *(_BYTE *)(v14 + 92);
          if ( !v14 || !v15 )
            break;
          if ( a4 && !FtcCopyUnicodeString(a4, (PCUNICODE_STRING)v14, 0) )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
            v12 = -1073741670;
            goto LABEL_15;
          }
          if ( !a5 || FtcCopySid(a5, v15) )
            return 0;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
          v12 = -1073741670;
          goto LABEL_14;
        }
      }
    }
  }
  v12 = -1073741198;
LABEL_14:
  if ( a4 )
  {
LABEL_15:
    LocalFree(a4->Buffer);
    *a4 = 0;
  }
  if ( a5 )
  {
    LocalFree(*a5);
    *a5 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x1800295ac  push    rbx
0x1800295ae  push    rsi
0x1800295af  push    rdi
0x1800295b0  push    r14
0x1800295b2  push    r15
0x1800295b4  sub     rsp, 20h
0x1800295b8  add     rcx, 1A8h; Table
0x1800295bf  mov     rsi, r9
0x1800295c2  mov     r15, r8
0x1800295c5  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800295cb  mov     rdi, [rsp+48h+arg_20]
0x1800295d0  test    rax, rax
0x1800295d3  jz      short loc_180029628
0x1800295d5  lea     r14, [rax+18h]
0x1800295d9  mov     rbx, [r14]
0x1800295dc  jmp     short loc_180029623
0x1800295de  mov     rax, [rbx+30h]
0x1800295e2  test    rax, rax
0x1800295e5  jz      short loc_180029620
0x1800295e7  test    byte ptr [rbx+50h], 0Fh
0x1800295eb  jnz     short loc_180029620
0x1800295ed  cmp     byte ptr [rax+28h], 0
0x1800295f1  jnz     short loc_180029620
0x1800295f3  mov     rcx, [rax+38h]; this
0x1800295f7  test    rcx, rcx
0x1800295fa  jz      short loc_180029607
0x1800295fc  call    ?Enabled@TLN_ENTRY@FTCache@@QEAAEXZ; FTCache::TLN_ENTRY::Enabled(void)
0x180029601  test    al, al
0x180029603  jz      short loc_180029620
0x180029605  jmp     short loc_18002960F
0x180029607  movzx   eax, word ptr [rax+48h]
0x18002960b  test    eax, eax
0x18002960d  jnz     short loc_180029620
0x18002960f  mov     rdx, [rbx+40h]; struct _UNICODE_STRING *
0x180029613  mov     rcx, [rbx+28h]; this
0x180029617  call    ?Excludes@TDO_ENTRY@FTCache@@QEAAEPEBU_UNICODE_STRING@@@Z; FTCache::TDO_ENTRY::Excludes(_UNICODE_STRING const *)
0x18002961c  test    al, al
0x18002961e  jz      short loc_180029665
0x180029620  mov     rbx, [rbx]
0x180029623  cmp     rbx, r14
0x180029626  jnz     short loc_1800295DE
0x180029628  mov     ebx, 0C0000272h
0x18002962d  test    rsi, rsi
0x180029630  jz      short loc_180029642
0x180029632  mov     rcx, [rsi+8]; hMem
0x180029636  call    cs:__imp_LocalFree
0x18002963c  xorps   xmm0, xmm0
0x18002963f  movups  xmmword ptr [rsi], xmm0
0x180029642  test    rdi, rdi
0x180029645  jz      short loc_180029657
0x180029647  mov     rcx, [rdi]; hMem
0x18002964a  call    cs:__imp_LocalFree
0x180029650  mov     qword ptr [rdi], 0
0x180029657  mov     eax, ebx
0x180029659  add     rsp, 20h
0x18002965d  pop     r15
0x18002965f  pop     r14
0x180029661  pop     rdi
0x180029662  pop     rsi
0x180029663  pop     rbx
0x180029664  retn
0x180029665  mov     rdx, [rbx+28h]; SourceString
0x180029669  mov     al, [rdx+5Ch]
0x18002966c  mov     rbx, [rdx+10h]
0x180029670  mov     [r15], al
0x180029673  test    rdx, rdx
0x180029676  jz      short loc_180029628
0x180029678  test    rbx, rbx
0x18002967b  jz      short loc_180029628
0x18002967d  test    rsi, rsi
0x180029680  jz      short loc_1800296BD
0x180029682  xor     r8d, r8d; unsigned __int16 *
0x180029685  mov     rcx, rsi; DestinationString
0x180029688  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x18002968d  test    al, al
0x18002968f  jnz     short loc_1800296BD
0x180029691  mov     rcx, cs:WPP_GLOBAL_Control
0x180029698  test    byte ptr [rcx+1Ch], 8
0x18002969c  jz      short loc_1800296B3
0x18002969e  mov     rcx, [rcx+10h]
0x1800296a2  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800296a9  mov     edx, 0E1h
0x1800296ae  call    WPP_SF_
0x1800296b3  mov     ebx, 0C000009Ah
0x1800296b8  jmp     loc_180029632
0x1800296bd  test    rdi, rdi
0x1800296c0  jz      short loc_1800296FD
0x1800296c2  mov     rdx, rbx; void *
0x1800296c5  mov     rcx, rdi; void **
0x1800296c8  call    ?FtcCopySid@@YAEPEAPEAXPEAX@Z; FtcCopySid(void * *,void *)
0x1800296cd  test    al, al
0x1800296cf  jnz     short loc_1800296FD
0x1800296d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296d8  test    byte ptr [rcx+1Ch], 8
0x1800296dc  jz      short loc_1800296F3
0x1800296de  mov     rcx, [rcx+10h]
0x1800296e2  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800296e9  mov     edx, 0E2h
0x1800296ee  call    WPP_SF_
0x1800296f3  mov     ebx, 0C000009Ah
0x1800296f8  jmp     loc_18002962D
0x1800296fd  xor     ebx, ebx
0x1800296ff  jmp     loc_180029657
```
