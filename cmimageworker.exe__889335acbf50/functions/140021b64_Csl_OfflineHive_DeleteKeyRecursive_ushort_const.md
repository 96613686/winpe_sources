# Csl::OfflineHive::DeleteKeyRecursive(ushort const *)

- ea: `0x140021b64`
- end: `0x140021c2b`
- name: `?DeleteKeyRecursive@OfflineHive@Csl@@QEAAJPEBG@Z`
- size: `199`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001bb2c`

## callees

- `0x140006fe4`
- `0x140008f90`
- `0x140021aac`
- `0x140021b64`
- `0x140021d08`

## string_xrefs

- `0x140021ba8`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140021bed`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::DeleteKeyRecursive(Csl::OfflineHive *this, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  const unsigned __int16 **i; // rbx
  int v8; // eax
  __int64 v9; // rdx
  int v11[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(__m128i *)v11 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v12 = -1;
  v4 = Csl::OfflineHive::EnumerateSubkeys(this, a2, v11);
  v5 = -2147024894;
  v6 = v4;
  if ( v4 != -2147024894 )
  {
    if ( v4 >= 0 )
    {
      for ( i = *(const unsigned __int16 ***)v11; i != *(const unsigned __int16 ***)&v11[2]; i += 4 )
      {
        v8 = Csl::OfflineHive::DeleteKey(this, *i);
        v5 = v8;
        if ( v8 < 0 )
        {
          v9 = 413;
LABEL_9:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v9,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)(unsigned int)v8,
            v11[0]);
          goto LABEL_13;
        }
      }
      v8 = Csl::OfflineHive::DeleteKey(this, a2);
      v5 = v8;
      if ( v8 < 0 )
      {
        v9 = 418;
        goto LABEL_9;
      }
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)(unsigned int)v4,
        v11[0]);
      v5 = v6;
    }
  }
LABEL_13:
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)v11);
  return v5;
}

```

## disassembly

```asm
0x140021b64  push    rbx
0x140021b66  push    rbp
0x140021b67  push    rsi
0x140021b68  push    rdi
0x140021b69  sub     rsp, 48h
0x140021b6d  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140021b75  lea     r8, [rsp+68h+var_48]
0x140021b7a  movdqu  xmmword ptr [rsp+68h+var_48], xmm0; int
0x140021b80  mov     rbp, rdx
0x140021b83  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x140021b8c  mov     rsi, rcx
0x140021b8f  call    ?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z; Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)
0x140021b94  mov     edi, 80070002h
0x140021b99  mov     ebx, eax
0x140021b9b  cmp     eax, edi
0x140021b9d  jz      short loc_140021C15
0x140021b9f  test    eax, eax
0x140021ba1  jns     short loc_140021BC0
0x140021ba3  mov     rcx, [rsp+68h]; this
0x140021ba8  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021baf  mov     r9d, eax; char *
0x140021bb2  mov     edx, 197h; void *
0x140021bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021bbc  mov     edi, ebx
0x140021bbe  jmp     short loc_140021C15
0x140021bc0  mov     rbx, qword ptr [rsp+68h+var_48]
0x140021bc5  mov     rcx, rsi; this
0x140021bc8  cmp     rbx, qword ptr [rsp+68h+var_48+8]
0x140021bcd  jz      short loc_140021BFE
0x140021bcf  mov     rdx, [rbx]; unsigned __int16 *
0x140021bd2  call    ?DeleteKey@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKey(ushort const *)
0x140021bd7  mov     edi, eax
0x140021bd9  test    eax, eax
0x140021bdb  js      short loc_140021BE3
0x140021bdd  add     rbx, 20h ; ' '
0x140021be1  jmp     short loc_140021BC5
0x140021be3  mov     edx, 19Dh; void *
0x140021be8  mov     rcx, [rsp+68h]; this
0x140021bed  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021bf4  mov     r9d, eax; char *
0x140021bf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021bfc  jmp     short loc_140021C15
0x140021bfe  mov     rdx, rbp; unsigned __int16 *
0x140021c01  call    ?DeleteKey@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKey(ushort const *)
0x140021c06  mov     edi, eax
0x140021c08  test    eax, eax
0x140021c0a  jns     short loc_140021C13
0x140021c0c  mov     edx, 1A2h
0x140021c11  jmp     short loc_140021BE8
0x140021c13  xor     edi, edi
0x140021c15  lea     rcx, [rsp+68h+var_48]
0x140021c1a  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x140021c1f  mov     eax, edi
0x140021c21  add     rsp, 48h
0x140021c25  pop     rdi
0x140021c26  pop     rsi
0x140021c27  pop     rbp
0x140021c28  pop     rbx
0x140021c29  retn
```
