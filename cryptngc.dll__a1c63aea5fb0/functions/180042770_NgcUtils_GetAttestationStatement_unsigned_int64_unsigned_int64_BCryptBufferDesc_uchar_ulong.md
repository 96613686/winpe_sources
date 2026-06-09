# NgcUtils::GetAttestationStatement(unsigned __int64,unsigned __int64,_BCryptBufferDesc *,uchar * *,ulong *)

- ea: `0x180042770`
- end: `0x18004288e`
- name: `?GetAttestationStatement@NgcUtils@@YAJ_K0PEAU_BCryptBufferDesc@@PEAPEAEPEAK@Z`
- size: `286`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int64, unsigned __int64, struct _BCryptBufferDesc *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800295f0`

## callees

- `0x180006538`
- `0x1800065c0`
- `0x180042770`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042866`
- `ncrypt!NCryptCreateClaim` at `0x1800427bb`
- `ncrypt!NCryptCreateClaim` at `0x180042839`
- `ncrypt!NCryptCreateClaim` at `0x1800427bb`
- `ncrypt!NCryptCreateClaim` at `0x180042839`

## string_xrefs

- `0x1800427d1`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18004284a`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetAttestationStatement(
        NgcUtils *this,
        __int64 a2,
        __int64 a3,
        struct _BCryptBufferDesc *a4,
        unsigned __int8 **a5)
{
  int Claim; // ebx
  __int64 v10; // rdx
  HLOCAL v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-58h]
  HLOCAL hMem[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  Claim = NCryptCreateClaim(this, a2, 2, a3);
  if ( Claim < 0 )
  {
    v10 = 507;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)Claim,
      0);
    return (unsigned int)Claim;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(hMem, 0);
  v12 = hMem[0];
  if ( !hMem[0] )
  {
    Claim = -2147024882;
    v10 = 510;
    goto LABEL_3;
  }
  v15 = (int)hMem[0];
  v13 = NCryptCreateClaim(this, a2, 2, a3);
  v14 = v13;
  if ( v13 >= 0 )
  {
    *(_QWORD *)&a4->ulVersion = v12;
    *(_DWORD *)a5 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v13,
      v15);
    if ( v12 )
      LocalFree(v12);
    return v14;
  }
}

```

## disassembly

```asm
0x180042770  push    rbx
0x180042772  push    rbp
0x180042773  push    rsi
0x180042774  push    rdi
0x180042775  push    r14
0x180042777  sub     rsp, 50h
0x18004277b  mov     [rsp+78h+var_40], 0
0x180042783  lea     rax, [rsp+78h+var_38]
0x180042788  mov     [rsp+78h+var_48], rax
0x18004278d  mov     rsi, r9
0x180042790  mov     rdi, r8
0x180042793  mov     [rsp+78h+var_50], 0
0x18004279b  mov     r9, r8
0x18004279e  mov     qword ptr [rsp+78h+var_58], 0; int
0x1800427a7  mov     r8d, 2
0x1800427ad  mov     [rsp+78h+var_38], 0
0x1800427b5  mov     rbp, rdx
0x1800427b8  mov     r14, rcx
0x1800427bb  call    cs:__imp_NCryptCreateClaim
0x1800427c1  mov     ebx, eax
0x1800427c3  test    eax, eax
0x1800427c5  jns     short loc_1800427E7
0x1800427c7  mov     edx, 1FBh; void *
0x1800427cc  mov     rcx, [rsp+78h]; this
0x1800427d1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800427d8  mov     r9d, ebx; char *
0x1800427db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800427e0  mov     eax, ebx
0x1800427e2  jmp     loc_180042883
0x1800427e7  mov     edx, [rsp+78h+var_38]
0x1800427eb  lea     rcx, [rsp+78h+hMem]
0x1800427f0  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800427f5  mov     rbx, [rsp+78h+hMem]
0x1800427fa  test    rbx, rbx
0x1800427fd  jnz     short loc_18004280B
0x1800427ff  mov     ebx, 8007000Eh
0x180042804  mov     edx, 1FEh
0x180042809  jmp     short loc_1800427CC
0x18004280b  mov     eax, [rsp+78h+var_38]
0x18004280f  lea     rcx, [rsp+78h+var_38]
0x180042814  mov     [rsp+78h+var_40], 0
0x18004281c  mov     r9, rdi
0x18004281f  mov     [rsp+78h+var_48], rcx
0x180042824  mov     r8d, 2
0x18004282a  mov     [rsp+78h+var_50], eax
0x18004282e  mov     rcx, r14
0x180042831  mov     rdx, rbp
0x180042834  mov     qword ptr [rsp+78h+var_58], rbx; int
0x180042839  call    cs:__imp_NCryptCreateClaim
0x18004283f  mov     edi, eax
0x180042841  test    eax, eax
0x180042843  jns     short loc_180042870
0x180042845  mov     rcx, [rsp+78h]; this
0x18004284a  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180042851  mov     r9d, eax; char *
0x180042854  mov     edx, 208h; void *
0x180042859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004285e  test    rbx, rbx
0x180042861  jz      short loc_18004286C
0x180042863  mov     rcx, rbx; hMem
0x180042866  call    cs:__imp_LocalFree
0x18004286c  mov     eax, edi
0x18004286e  jmp     short loc_180042883
0x180042870  mov     eax, [rsp+78h+var_38]
0x180042874  mov     rcx, [rsp+78h+arg_20]
0x18004287c  mov     [rsi], rbx
0x18004287f  mov     [rcx], eax
0x180042881  xor     eax, eax
0x180042883  add     rsp, 50h
0x180042887  pop     r14
0x180042889  pop     rdi
0x18004288a  pop     rsi
0x18004288b  pop     rbp
0x18004288c  pop     rbx
0x18004288d  retn
```
