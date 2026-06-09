# COMAPSymsByAddrTrav::prev(void)

- ea: `0x18015e550`
- end: `0x18015e91d`
- name: `?prev@COMAPSymsByAddrTrav@@UEAA_NXZ`
- size: `973`
- prototype: `bool __fastcall(COMAPSymsByAddrTrav *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180027440`
- `0x1800bbd80`
- `0x1800c0690`
- `0x1800c9c10`
- `0x1800d31b0`
- `0x1800d4120`
- `0x1801594e0`
- `0x18015e550`
- `0x1801be61c`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18015e639`
- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18015e639`

## string_xrefs

- `0x18015e8b4`: `ArrayBufStorage access out of range`
- `0x18015e8d7`: `ArrayBufStorage access out of range`
- `0x18015e8fa`: `ArrayBufStorage access out of range`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall COMAPSymsByAddrTrav::prev(COMAPSymsByAddrTrav *this)
{
  __int64 v2; // rbx
  unsigned int *v3; // rax
  unsigned int v4; // r15d
  __int64 v5; // rbx
  __int64 v6; // r14
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rsi
  unsigned int v10; // ebx
  unsigned int PreLegoSection; // eax
  unsigned int v12; // r15d
  int v13; // ebx
  char v14; // cl
  AddressMap *v15; // rcx
  unsigned int v16; // ebx
  unsigned int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // ebx
  __int64 v20; // r15
  unsigned __int64 v21; // r14
  __int64 v23; // rbx
  unsigned int v24; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+3Ch] [rbp-CCh] BYREF
  _DWORD v26[2]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A8h]
  void **v29; // [rsp+68h] [rbp-A0h] BYREF
  int v30; // [rsp+70h] [rbp-98h]
  unsigned int v31; // [rsp+78h] [rbp-90h]
  unsigned int v32; // [rsp+1DCh] [rbp+D4h]
  __int64 v33; // [rsp+3F0h] [rbp+2E8h]

  v28 = -2;
  --*((_DWORD *)this + 10);
  v2 = *((_QWORD *)this + 4);
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v2 + 16) + 8LL))(*(_QWORD *)(v2 + 16)) & 0xFFFFFFF8) == 0 )
  {
LABEL_38:
    std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, "ArrayBufStorage access out of range");
    throw (std::out_of_range *)pExceptionObject;
  }
LABEL_2:
  v3 = (unsigned int *)(***(__int64 (__fastcall ****)(_QWORD))(v2 + 16))(*(_QWORD *)(v2 + 16));
  v4 = *((_DWORD *)this + 10);
  if ( v4 < *v3 )
    return 0;
  v5 = *((_QWORD *)this + 4);
  v6 = (***(__int64 (__fastcall ****)(_QWORD))(v5 + 16))(*(_QWORD *)(v5 + 16));
  v7 = (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 16) + 8LL))(*(_QWORD *)(v5 + 16)) >> 3;
  v26[0] = v4;
  v26[1] = 0;
  if ( v7 > 1 && (v8 = _o_bsearch(v26, v6, v7 - 1, 8, AddressMap::compareMapEntries)) != 0 )
  {
    v9 = (v8 - v6) >> 3;
  }
  else if ( *(_DWORD *)(v6 + 8 * v7 - 8) == v4 )
  {
    v9 = (__int64)(8 * v7 - 8) >> 3;
  }
  else
  {
    LODWORD(v9) = -1;
  }
  AddressMap::isectOffForRva(*((AddressMap **)this + 2), *((_DWORD *)this + 10), &v25, &v24);
  CAllSymsByAddrTrav::init((COMAPSymsByAddrTrav *)((char *)this + 48), v25, v24);
  v10 = v24;
  PreLegoSection = AddressMap::FindPreLegoSection(*((AddressMap **)this + 2), v25 - 1);
  v12 = 0;
  if ( PreLegoSection != -1 )
    v12 = PreLegoSection + v10;
  while ( 1 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 80LL))((char *)this + 48) )
    {
      v21 = (unsigned int)v9;
      goto LABEL_31;
    }
    SymRowImage::SymRowImage((SymRowImage *)&v29);
    v29 = &CSymRow::`vftable';
    v13 = (*(__int64 (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 12) + 48LL))(*((_QWORD *)this + 12), &v29);
    if ( v13 >= 0 )
    {
      v14 = v33;
      if ( (v33 & 0x10000) != 0
        || (_BYTE)v30 && (LOBYTE(v30) = 0, ((void (__fastcall *)(void ***))*v29)(&v29), v14 = v33, (v33 & 0x10000) != 0) )
      {
        v25 = v32;
      }
      else
      {
        v25 = 0;
      }
      if ( (v14 & 1) != 0
        || (_BYTE)v30 && (LOBYTE(v30) = 0, ((void (__fastcall *)(void ***))*v29)(&v29), (v33 & 1) != 0) )
      {
        v24 = v31;
      }
      else
      {
        v24 = 0;
      }
    }
    SymRowImage::~SymRowImage((SymRowImage *)&v29);
    v15 = (AddressMap *)*((_QWORD *)this + 2);
    if ( v13 < 0 )
      break;
    v16 = v24;
    v17 = AddressMap::FindPreLegoSection(v15, v25 - 1);
    v18 = 0;
    if ( v17 != -1 )
      v18 = v17 + v16;
    v19 = v12 - v18;
    if ( v12 != v18 )
    {
      v20 = *((_QWORD *)this + 4);
      if ( (unsigned int)v9 >= (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 16) + 8LL))(*(_QWORD *)(v20 + 16)) >> 3 )
      {
        std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, "ArrayBufStorage access out of range");
        throw (std::out_of_range *)pExceptionObject;
      }
      v21 = (unsigned int)v9;
      if ( v19 <= *((_DWORD *)this + 10)
                - *(_DWORD *)((***(__int64 (__fastcall ****)(_QWORD))(v20 + 16))(*(_QWORD *)(v20 + 16))
                            + 8LL * (unsigned int)v9) )
      {
        *((_DWORD *)this + 10) -= v19;
        return 1;
      }
LABEL_31:
      if ( !(_DWORD)v9 )
        return 0;
      v23 = *((_QWORD *)this + 4);
      if ( v21 >= (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v23 + 16) + 8LL))(*(_QWORD *)(v23 + 16)) >> 3 )
      {
        std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, "ArrayBufStorage access out of range");
        throw (std::out_of_range *)pExceptionObject;
      }
      *((_DWORD *)this + 10) = *(_DWORD *)((***(__int64 (__fastcall ****)(_QWORD))(v23 + 16))(*(_QWORD *)(v23 + 16))
                                         + 8 * v21)
                             - 1;
      v2 = *((_QWORD *)this + 4);
      if ( ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v2 + 16) + 8LL))(*(_QWORD *)(v2 + 16)) & 0xFFFFFFF8) == 0 )
        goto LABEL_38;
      goto LABEL_2;
    }
  }
  SymCache::ReportErrorViaCallback(v15, -2140340210, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18015e550  mov     rax, rsp
0x18015e553  push    rbp
0x18015e554  push    r12
0x18015e556  push    r13
0x18015e558  push    r14
0x18015e55a  push    r15
0x18015e55c  lea     rbp, [rax-348h]
0x18015e563  sub     rsp, 420h
0x18015e56a  mov     [rsp+440h+var_3E8], 0FFFFFFFFFFFFFFFEh
0x18015e573  mov     [rax+10h], rbx
0x18015e577  mov     [rax+18h], rsi
0x18015e57b  mov     [rax+20h], rdi
0x18015e57f  mov     rax, cs:__security_cookie
0x18015e586  xor     rax, rsp
0x18015e589  mov     [rbp+340h+var_30], rax
0x18015e590  mov     rdi, rcx
0x18015e593  dec     dword ptr [rcx+28h]
0x18015e596  mov     rbx, [rcx+20h]
0x18015e59a  mov     rcx, [rbx+10h]
0x18015e59e  mov     rax, [rcx]
0x18015e5a1  mov     rax, [rax+8]
0x18015e5a5  call    cs:__guard_dispatch_icall_fptr
0x18015e5ab  test    eax, 0FFFFFFF8h
0x18015e5b0  jbe     loc_18015E8D7
0x18015e5b6  xor     r12d, r12d
0x18015e5b9  lea     r13, ??_7CSymRow@@6B@; const CSymRow::`vftable'
0x18015e5c0  lea     rsi, ?compareMapEntries@AddressMap@@KAHPEBX0@Z; AddressMap::compareMapEntries(void const *,void const *)
0x18015e5c7  mov     rcx, [rbx+10h]
0x18015e5cb  mov     rax, [rcx]
0x18015e5ce  mov     rax, [rax]
0x18015e5d1  call    cs:__guard_dispatch_icall_fptr
0x18015e5d7  mov     r15d, [rdi+28h]
0x18015e5db  cmp     r15d, [rax]
0x18015e5de  jb      loc_18015E8AD
0x18015e5e4  mov     rbx, [rdi+20h]
0x18015e5e8  mov     rcx, [rbx+10h]
0x18015e5ec  mov     rax, [rcx]
0x18015e5ef  mov     rax, [rax]
0x18015e5f2  call    cs:__guard_dispatch_icall_fptr
0x18015e5f8  mov     r14, rax
0x18015e5fb  mov     rcx, [rbx+10h]
0x18015e5ff  mov     rdx, [rcx]
0x18015e602  mov     rax, [rdx+8]
0x18015e606  call    cs:__guard_dispatch_icall_fptr
0x18015e60c  mov     ebx, eax
0x18015e60e  shr     rbx, 3
0x18015e612  mov     dword ptr [rsp+440h+var_408], r15d
0x18015e617  mov     [rsp+440h+var_404], r12d
0x18015e61c  cmp     rbx, 1
0x18015e620  jbe     short loc_18015E650
0x18015e622  lea     r8, [rbx-1]
0x18015e626  mov     [rsp+440h+var_420], rsi
0x18015e62b  mov     r9d, 8
0x18015e631  mov     rdx, r14
0x18015e634  lea     rcx, [rsp+440h+var_408]
0x18015e639  call    cs:__imp__o_bsearch
0x18015e63f  mov     rsi, rax
0x18015e642  test    rax, rax
0x18015e645  jz      short loc_18015E650
0x18015e647  sub     rsi, r14
0x18015e64a  sar     rsi, 3
0x18015e64e  jmp     short loc_18015E66A
0x18015e650  cmp     [r14+rbx*8-8], r15d
0x18015e655  jnz     short loc_18015E665
0x18015e657  lea     rsi, ds:0FFFFFFFFFFFFFFF8h[rbx*8]
0x18015e65f  sar     rsi, 3
0x18015e663  jmp     short loc_18015E66A
0x18015e665  mov     esi, 0FFFFFFFFh
0x18015e66a  lea     r9, [rsp+440h+var_410]; unsigned int *
0x18015e66f  lea     r8, [rsp+440h+var_40C]; unsigned int *
0x18015e674  mov     edx, [rdi+28h]; unsigned int
0x18015e677  mov     rcx, [rdi+10h]; this
0x18015e67b  call    ?isectOffForRva@AddressMap@@QEAAXKAEAK0@Z; AddressMap::isectOffForRva(ulong,ulong &,ulong &)
0x18015e680  mov     r8d, [rsp+440h+var_410]; unsigned int
0x18015e685  mov     edx, [rsp+440h+var_40C]; unsigned int
0x18015e689  lea     rcx, [rdi+30h]; this
0x18015e68d  call    ?init@CAllSymsByAddrTrav@@QEAA_NKK@Z; CAllSymsByAddrTrav::init(ulong,ulong)
0x18015e692  mov     ebx, [rsp+440h+var_410]
0x18015e696  mov     edx, [rsp+440h+var_40C]
0x18015e69a  dec     edx; unsigned int
0x18015e69c  mov     rcx, [rdi+10h]; this
0x18015e6a0  call    ?FindPreLegoSection@AddressMap@@QEAAKK@Z; AddressMap::FindPreLegoSection(ulong)
0x18015e6a5  lea     ecx, [rax+rbx]
0x18015e6a8  mov     r15d, r12d
0x18015e6ab  cmp     eax, 0FFFFFFFFh
0x18015e6ae  cmovnz  r15d, ecx
0x18015e6b2  mov     rax, [rdi+30h]
0x18015e6b6  lea     rcx, [rdi+30h]
0x18015e6ba  mov     rax, [rax+50h]
0x18015e6be  call    cs:__guard_dispatch_icall_fptr
0x18015e6c4  test    al, al
0x18015e6c6  jz      loc_18015E838
0x18015e6cc  lea     rcx, [rsp+440h+var_3E0]; this
0x18015e6d1  call    ??0SymRowImage@@QEAA@XZ; SymRowImage::SymRowImage(void)
0x18015e6d6  mov     [rsp+440h+var_3E0], r13
0x18015e6db  mov     rcx, [rdi+60h]
0x18015e6df  mov     rax, [rcx]
0x18015e6e2  lea     rdx, [rsp+440h+var_3E0]
0x18015e6e7  mov     rax, [rax+30h]
0x18015e6eb  call    cs:__guard_dispatch_icall_fptr
0x18015e6f1  mov     ebx, eax
0x18015e6f3  test    eax, eax
0x18015e6f5  js      loc_18015E783
0x18015e6fb  mov     rcx, [rbp+340h+var_58]
0x18015e702  bt      rcx, 10h
0x18015e707  jb      short loc_18015E73D
0x18015e709  cmp     byte ptr [rsp+440h+var_3D8], 0
0x18015e70e  jz      short loc_18015E736
0x18015e710  mov     byte ptr [rsp+440h+var_3D8], 0
0x18015e715  mov     rcx, [rsp+440h+var_3E0]
0x18015e71a  mov     rax, [rcx]
0x18015e71d  lea     rcx, [rsp+440h+var_3E0]
0x18015e722  call    cs:__guard_dispatch_icall_fptr
0x18015e728  mov     rcx, [rbp+340h+var_58]
0x18015e72f  bt      rcx, 10h
0x18015e734  jb      short loc_18015E73D
0x18015e736  mov     [rsp+440h+var_40C], r12d
0x18015e73b  jmp     short loc_18015E747
0x18015e73d  mov     eax, [rbp+340h+var_26C]
0x18015e743  mov     [rsp+440h+var_40C], eax
0x18015e747  test    cl, 1
0x18015e74a  jnz     short loc_18015E77B
0x18015e74c  cmp     byte ptr [rsp+440h+var_3D8], 0
0x18015e751  jz      short loc_18015E774
0x18015e753  mov     byte ptr [rsp+440h+var_3D8], 0
0x18015e758  mov     rax, [rsp+440h+var_3E0]
0x18015e75d  lea     rcx, [rsp+440h+var_3E0]
0x18015e762  mov     rax, [rax]
0x18015e765  call    cs:__guard_dispatch_icall_fptr
0x18015e76b  test    byte ptr [rbp+340h+var_58], 1
0x18015e772  jnz     short loc_18015E77B
0x18015e774  mov     [rsp+440h+var_410], r12d
0x18015e779  jmp     short loc_18015E783
0x18015e77b  mov     eax, [rsp+440h+var_3D0]
0x18015e77f  mov     [rsp+440h+var_410], eax
0x18015e783  lea     rcx, [rsp+440h+var_3E0]; this
0x18015e788  call    ??1SymRowImage@@QEAA@XZ; SymRowImage::~SymRowImage(void)
0x18015e78d  mov     rcx, [rdi+10h]; this
0x18015e791  test    ebx, ebx
0x18015e793  js      loc_18015E89D
0x18015e799  mov     ebx, [rsp+440h+var_410]
0x18015e79d  mov     edx, [rsp+440h+var_40C]
0x18015e7a1  dec     edx; unsigned int
0x18015e7a3  call    ?FindPreLegoSection@AddressMap@@QEAAKK@Z; AddressMap::FindPreLegoSection(ulong)
0x18015e7a8  lea     ecx, [rax+rbx]
0x18015e7ab  mov     edx, r12d
0x18015e7ae  cmp     eax, 0FFFFFFFFh
0x18015e7b1  cmovnz  edx, ecx
0x18015e7b4  mov     ebx, r15d
0x18015e7b7  sub     ebx, edx
0x18015e7b9  jz      loc_18015E6B2
0x18015e7bf  mov     r15, [rdi+20h]
0x18015e7c3  mov     rcx, [r15+10h]
0x18015e7c7  mov     rax, [rcx]
0x18015e7ca  mov     rax, [rax+8]
0x18015e7ce  call    cs:__guard_dispatch_icall_fptr
0x18015e7d4  shr     eax, 3
0x18015e7d7  cmp     esi, eax
0x18015e7d9  jnb     loc_18015E8B4
0x18015e7df  mov     r14d, esi
0x18015e7e2  mov     rcx, [r15+10h]
0x18015e7e6  mov     rax, [rcx]
0x18015e7e9  mov     rax, [rax]
0x18015e7ec  call    cs:__guard_dispatch_icall_fptr
0x18015e7f2  lea     rcx, [rax+r14*8]
0x18015e7f6  mov     edx, [rdi+28h]
0x18015e7f9  mov     eax, edx
0x18015e7fb  sub     eax, [rcx]
0x18015e7fd  cmp     ebx, eax
0x18015e7ff  ja      short loc_18015E83B
0x18015e801  sub     edx, ebx
0x18015e803  mov     [rdi+28h], edx
0x18015e806  mov     al, 1
0x18015e808  mov     rcx, [rbp+340h+var_30]
0x18015e80f  xor     rcx, rsp; StackCookie
0x18015e812  call    __security_check_cookie
0x18015e817  lea     r11, [rsp+440h+var_20]
0x18015e81f  mov     rbx, [r11+38h]
0x18015e823  mov     rsi, [r11+40h]
0x18015e827  mov     rdi, [r11+48h]
0x18015e82b  mov     rsp, r11
0x18015e82e  pop     r15
0x18015e830  pop     r14
0x18015e832  pop     r13
0x18015e834  pop     r12
0x18015e836  pop     rbp
0x18015e837  retn
0x18015e838  mov     r14d, esi
0x18015e83b  test    esi, esi
0x18015e83d  jz      short loc_18015E8AD
0x18015e83f  mov     rbx, [rdi+20h]
0x18015e843  mov     rcx, [rbx+10h]
0x18015e847  mov     rax, [rcx]
0x18015e84a  mov     rax, [rax+8]
0x18015e84e  call    cs:__guard_dispatch_icall_fptr
0x18015e854  mov     eax, eax
0x18015e856  shr     rax, 3
0x18015e85a  cmp     r14, rax
0x18015e85d  jnb     loc_18015E8FA
0x18015e863  mov     rcx, [rbx+10h]
0x18015e867  mov     rax, [rcx]
0x18015e86a  mov     rax, [rax]
0x18015e86d  call    cs:__guard_dispatch_icall_fptr
0x18015e873  mov     ecx, [rax+r14*8]
0x18015e877  dec     ecx
0x18015e879  mov     [rdi+28h], ecx
0x18015e87c  mov     rbx, [rdi+20h]
0x18015e880  mov     rcx, [rbx+10h]
0x18015e884  mov     rax, [rcx]
0x18015e887  mov     rax, [rax+8]
0x18015e88b  call    cs:__guard_dispatch_icall_fptr
0x18015e891  test    eax, 0FFFFFFF8h
0x18015e896  jbe     short loc_18015E8D7
0x18015e898  jmp     loc_18015E5C0
0x18015e89d  xor     r9d, r9d; wchar_t *
0x18015e8a0  xor     r8d, r8d; wchar_t *
0x18015e8a3  mov     edx, 806D000Eh; int
0x18015e8a8  call    ?ReportErrorViaCallback@SymCache@@QEAAXJPEB_W0@Z; SymCache::ReportErrorViaCallback(long,wchar_t const *,wchar_t const *)
0x18015e8ad  xor     al, al
0x18015e8af  jmp     loc_18015E808
0x18015e8b4  lea     rdx, aArraybufstorag; "ArrayBufStorage access out of range"
0x18015e8bb  lea     rcx, [rsp+440h+pExceptionObject]; this
0x18015e8c0  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x18015e8c5  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18015e8cc  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x18015e8d1  call    _CxxThrowException_0
0x18015e8d7  lea     rdx, aArraybufstorag; "ArrayBufStorage access out of range"
0x18015e8de  lea     rcx, [rsp+440h+pExceptionObject]; this
0x18015e8e3  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x18015e8e8  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18015e8ef  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x18015e8f4  call    _CxxThrowException_0
0x18015e8fa  lea     rdx, aArraybufstorag; "ArrayBufStorage access out of range"
0x18015e901  lea     rcx, [rsp+440h+pExceptionObject]; this
0x18015e906  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x18015e90b  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18015e912  lea     rcx, [rsp+440h+pExceptionObject]; pExceptionObject
0x18015e917  call    _CxxThrowException_0
```
