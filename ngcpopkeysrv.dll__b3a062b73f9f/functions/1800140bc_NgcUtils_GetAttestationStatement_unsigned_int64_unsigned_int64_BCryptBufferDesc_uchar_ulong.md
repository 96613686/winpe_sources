# NgcUtils::GetAttestationStatement(unsigned __int64,unsigned __int64,_BCryptBufferDesc *,uchar * *,ulong *)

- ea: `0x1800140bc`
- end: `0x1800141de`
- name: `?GetAttestationStatement@NgcUtils@@YAJ_K0PEAU_BCryptBufferDesc@@PEAPEAEPEAK@Z`
- size: `290`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int64, unsigned __int64, struct _BCryptBufferDesc *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001608c`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x1800140bc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141b5`
- `ncrypt!NCryptCreateClaim` at `0x180014103`
- `ncrypt!NCryptCreateClaim` at `0x180014188`
- `ncrypt!NCryptCreateClaim` at `0x180014103`
- `ncrypt!NCryptCreateClaim` at `0x180014188`

## string_xrefs

- `0x180014119`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180014199`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

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
  __int64 v9; // rdx
  HLOCAL v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  int v14; // [rsp+20h] [rbp-58h]
  HLOCAL hMem[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  Claim = NCryptCreateClaim(this, a2, 2);
  if ( Claim < 0 )
  {
    v9 = 507;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)Claim,
      0);
    return (unsigned int)Claim;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(hMem, 0);
  v11 = hMem[0];
  if ( !hMem[0] )
  {
    Claim = -2147024882;
    v9 = 510;
    goto LABEL_3;
  }
  v14 = (int)hMem[0];
  v12 = NCryptCreateClaim(this, a2, 2);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *(_QWORD *)&a4->ulVersion = v11;
    *(_DWORD *)a5 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v12,
      v14);
    if ( v11 )
      LocalFree(v11);
    return v13;
  }
}

```

## disassembly

```asm
0x1800140bc  mov     rax, rsp
0x1800140bf  mov     [rax+18h], r8
0x1800140c3  push    rbx
0x1800140c4  push    rbp
0x1800140c5  push    rsi
0x1800140c6  push    rdi
0x1800140c7  sub     rsp, 58h
0x1800140cb  mov     dword ptr [rax-40h], 0
0x1800140d2  mov     rsi, r9
0x1800140d5  mov     dword ptr [rax+18h], 0
0x1800140dc  lea     rax, [rax+18h]
0x1800140e0  mov     [rsp+78h+var_48], rax
0x1800140e5  xor     r9d, r9d
0x1800140e8  mov     [rsp+78h+var_50], 0
0x1800140f0  mov     rdi, rdx
0x1800140f3  mov     rbp, rcx
0x1800140f6  mov     qword ptr [rsp+78h+var_58], 0; int
0x1800140ff  lea     r8d, [r9+2]
0x180014103  call    cs:__imp_NCryptCreateClaim
0x180014109  mov     ebx, eax
0x18001410b  test    eax, eax
0x18001410d  jns     short loc_18001412F
0x18001410f  mov     edx, 1FBh; void *
0x180014114  mov     rcx, [rsp+78h]; this
0x180014119  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014120  mov     r9d, ebx; char *
0x180014123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014128  mov     eax, ebx
0x18001412a  jmp     loc_1800141D5
0x18001412f  mov     edx, [rsp+78h+arg_10]
0x180014136  lea     rcx, [rsp+78h+hMem]
0x18001413b  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180014140  mov     rbx, [rsp+78h+hMem]
0x180014145  test    rbx, rbx
0x180014148  jnz     short loc_180014156
0x18001414a  mov     ebx, 8007000Eh
0x18001414f  mov     edx, 1FEh
0x180014154  jmp     short loc_180014114
0x180014156  mov     eax, [rsp+78h+arg_10]
0x18001415d  lea     rcx, [rsp+78h+arg_10]
0x180014165  mov     [rsp+78h+var_40], 0
0x18001416d  xor     r9d, r9d
0x180014170  mov     [rsp+78h+var_48], rcx
0x180014175  mov     rdx, rdi
0x180014178  mov     [rsp+78h+var_50], eax
0x18001417c  mov     rcx, rbp
0x18001417f  mov     qword ptr [rsp+78h+var_58], rbx; int
0x180014184  lea     r8d, [r9+2]
0x180014188  call    cs:__imp_NCryptCreateClaim
0x18001418e  mov     edi, eax
0x180014190  test    eax, eax
0x180014192  jns     short loc_1800141BF
0x180014194  mov     rcx, [rsp+78h]; this
0x180014199  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800141a0  mov     r9d, eax; char *
0x1800141a3  mov     edx, 208h; void *
0x1800141a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141ad  test    rbx, rbx
0x1800141b0  jz      short loc_1800141BB
0x1800141b2  mov     rcx, rbx; hMem
0x1800141b5  call    cs:__imp_LocalFree
0x1800141bb  mov     eax, edi
0x1800141bd  jmp     short loc_1800141D5
0x1800141bf  mov     eax, [rsp+78h+arg_10]
0x1800141c6  mov     rcx, [rsp+78h+arg_20]
0x1800141ce  mov     [rsi], rbx
0x1800141d1  mov     [rcx], eax
0x1800141d3  xor     eax, eax
0x1800141d5  add     rsp, 58h
0x1800141d9  pop     rdi
0x1800141da  pop     rsi
0x1800141db  pop     rbp
0x1800141dc  pop     rbx
0x1800141dd  retn
```
