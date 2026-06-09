# COMAPSymsByAddrTrav::next(void)

- ea: `0x18015c7b0`
- end: `0x18015cb67`
- name: `?next@COMAPSymsByAddrTrav@@UEAA?AW4safe_hresult@@XZ`
- size: `951`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180027440`
- `0x1800ba8c0`
- `0x1800bbd80`
- `0x1800c16a0`
- `0x1800c9c10`
- `0x180153f10`
- `0x1801594e0`
- `0x18015c7b0`
- `0x1801be61c`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18015c882`
- `api-ms-win-crt-private-l1-1-0!_o_bsearch` at `0x18015c882`

## string_xrefs

- `0x18015cb44`: `ArrayBufStorage access out of range`

## pseudocode

```c
__int64 __fastcall COMAPSymsByAddrTrav::next(__int64 a1)
{
  __int64 v2; // rax
  __int64 result; // rax
  int v4; // esi
  unsigned int v5; // r14d
  __int64 v6; // rdi
  __int64 v7; // rbp
  unsigned __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // r12
  unsigned int v11; // r15d
  int v12; // edi
  __int64 v13; // rdi
  _DWORD *v14; // rsi
  __int64 v15; // rsi
  unsigned int v16; // ecx
  __int64 v17; // r15
  unsigned int v18; // ebp
  unsigned int v19; // r13d
  const struct DiaAddressMapEntry *v20; // rbp
  unsigned __int64 v21; // rsi
  const struct DiaAddressMapEntry *v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // edx
  int v26; // esi
  unsigned int v27; // edi
  unsigned int PreLegoSection; // eax
  unsigned int v29; // [rsp+30h] [rbp-78h]
  int v30; // [rsp+34h] [rbp-74h]
  _DWORD v31[2]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v33; // [rsp+B0h] [rbp+8h]
  unsigned int v34; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v35; // [rsp+C0h] [rbp+18h] BYREF
  unsigned int v36; // [rsp+C8h] [rbp+20h]

  if ( *(_BYTE *)(a1 + 44) )
  {
    v2 = *(_QWORD *)(a1 + 48);
    *(_BYTE *)(a1 + 44) = 0;
    return (*(__int64 (__fastcall **)(__int64))(v2 + 40))(a1 + 48);
  }
  else
  {
    v4 = *(_DWORD *)(a1 + 40);
    v5 = 0;
    v33 = 0;
    v30 = v4;
    while ( 1 )
    {
      v6 = *(_QWORD *)(a1 + 32);
      v7 = (***(__int64 (__fastcall ****)(_QWORD))(v6 + 16))(*(_QWORD *)(v6 + 16));
      v8 = (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 16) + 8LL))(*(_QWORD *)(v6 + 16)) >> 3;
      v31[0] = v4;
      v31[1] = 0;
      if ( v8 > 1 && (v9 = _o_bsearch(v31, v7, v8 - 1, 8, AddressMap::compareMapEntries)) != 0 )
      {
        v10 = (v9 - v7) >> 3;
      }
      else if ( *(_DWORD *)(v7 + 8 * v8 - 8) == v4 )
      {
        v10 = (__int64)(8 * v8 - 8) >> 3;
      }
      else
      {
        LODWORD(v10) = -1;
      }
      v11 = v10 + 1;
      v29 = v10 + 1;
      if ( (_DWORD)v10 == ((*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 32) + 16LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL)) >> 3)
                        - 1 )
      {
        v12 = 0x7FFFFFFF;
      }
      else
      {
        v13 = *(_QWORD *)(a1 + 32);
        v14 = (_DWORD *)ArrayBufStorage<DiaAddressMapEntry>::operator[](v13, (unsigned int)v10);
        v29 = v10 + 1;
        v12 = *(_DWORD *)ArrayBufStorage<DiaAddressMapEntry>::operator[](v13, v11) - *v14;
      }
      v15 = *(_QWORD *)(a1 + 32);
      v36 = v12;
      if ( (unsigned int)v10 >= (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 16) + 8LL))(*(_QWORD *)(v15 + 16)) >> 3 )
      {
        std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, "ArrayBufStorage access out of range");
        throw (std::out_of_range *)pExceptionObject;
      }
      v16 = *(_DWORD *)((***(__int64 (__fastcall ****)(_QWORD))(v15 + 16))(*(_QWORD *)(v15 + 16))
                      + 8LL * (unsigned int)v10
                      + 4);
      if ( v16 )
      {
        if ( v16 < v33 || v16 + v12 > v5 )
          break;
      }
LABEL_29:
      if ( (_DWORD)v10 == ((*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 32) + 16LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL)) >> 3)
                        - 1 )
        return 1;
      v4 = *(_DWORD *)ArrayBufStorage<DiaAddressMapEntry>::operator[](*(_QWORD *)(a1 + 32), v11);
      *(_DWORD *)(a1 + 40) = v4;
    }
    v17 = *(_QWORD *)(a1 + 16);
    v18 = v16;
    v19 = *(_DWORD *)(a1 + 40);
    v33 = v16;
    if ( *(_BYTE *)(v17 + 1) )
    {
      v20 = (const struct DiaAddressMapEntry *)(***(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)(v17 + 48) + 16LL))(*(_QWORD *)(*(_QWORD *)(v17 + 48) + 16LL));
      v21 = (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v17 + 48) + 16LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(v17 + 48) + 16LL)) >> 3;
      v22 = (const struct DiaAddressMapEntry *)(***(__int64 (__fastcall ****)(_QWORD))(*(_QWORD *)(v17 + 56) + 16LL))(*(_QWORD *)(*(_QWORD *)(v17 + 56) + 16LL));
      v23 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v17 + 56) + 16LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(v17 + 56) + 16LL));
      v24 = AddressMap::TranslateRvaThroughOMAP(v19, 0, (unsigned __int64)v23 >> 3, v22, v21, v20);
      v18 = v33;
      v19 = v24;
    }
    v25 = *(_DWORD *)(a1 + 40);
    if ( v25 != v30 )
    {
      AddressMap::isectOffForRva(*(AddressMap **)(a1 + 16), v25, &v35, &v34);
      CAllSymsByAddrTrav::init((CAllSymsByAddrTrav *)(a1 + 48), v35, v34);
    }
    while ( 1 )
    {
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 40LL))(a1 + 48);
      if ( v26 )
        break;
      result = CAllSymsByAddrTrav::get(a1 + 48, &v35, &v34);
      v26 = result;
      if ( (int)result < 0 )
        return result;
      v27 = v34;
      PreLegoSection = AddressMap::FindPreLegoSection(*(AddressMap **)(a1 + 16), v35 - 1);
      v5 = 0;
      if ( PreLegoSection != -1 )
        v5 = PreLegoSection + v27;
      if ( v5 >= v19 )
      {
        if ( v5 - v18 < v36 )
        {
          *(_DWORD *)(a1 + 40) += v5 - v19;
          return 0;
        }
        break;
      }
    }
    if ( v26 >= 0 )
    {
      v11 = v29;
      goto LABEL_29;
    }
    return (unsigned int)v26;
  }
}

```

## disassembly

```asm
0x18015c7b0  push    rbx
0x18015c7b2  sub     rsp, 0A0h
0x18015c7b9  cmp     byte ptr [rcx+2Ch], 0
0x18015c7bd  mov     rbx, rcx
0x18015c7c0  jz      short loc_18015C7E1
0x18015c7c2  mov     rax, [rcx+30h]
0x18015c7c6  mov     byte ptr [rcx+2Ch], 0
0x18015c7ca  add     rcx, 30h ; '0'
0x18015c7ce  mov     rax, [rax+28h]
0x18015c7d2  add     rsp, 0A0h
0x18015c7d9  pop     rbx
0x18015c7da  jmp     cs:__guard_dispatch_icall_fptr
0x18015c7e1  mov     eax, [rcx+28h]
0x18015c7e4  mov     [rsp+0A8h+var_10], rbp
0x18015c7ec  mov     [rsp+0A8h+var_18], rsi
0x18015c7f4  mov     esi, eax
0x18015c7f6  mov     [rsp+0A8h+var_20], rdi
0x18015c7fe  mov     [rsp+0A8h+var_28], r12
0x18015c806  mov     [rsp+0A8h+var_30], r13
0x18015c80b  mov     [rsp+0A8h+var_38], r14
0x18015c810  xor     r14d, r14d
0x18015c813  mov     [rsp+0A8h+arg_0], r14d
0x18015c81b  mov     [rsp+0A8h+var_40], r15
0x18015c820  mov     [rsp+0A8h+var_74], eax
0x18015c824  mov     rdi, [rbx+20h]
0x18015c828  lea     r15, ?compareMapEntries@AddressMap@@KAHPEBX0@Z; AddressMap::compareMapEntries(void const *,void const *)
0x18015c82f  mov     rcx, [rdi+10h]
0x18015c833  mov     rax, [rcx]
0x18015c836  mov     rax, [rax]
0x18015c839  call    cs:__guard_dispatch_icall_fptr
0x18015c83f  mov     rcx, [rdi+10h]
0x18015c843  mov     rbp, rax
0x18015c846  mov     rdx, [rcx]
0x18015c849  mov     rax, [rdx+8]
0x18015c84d  call    cs:__guard_dispatch_icall_fptr
0x18015c853  mov     edi, eax
0x18015c855  shr     rdi, 3
0x18015c859  mov     [rsp+0A8h+var_70], esi
0x18015c85d  mov     [rsp+0A8h+var_6C], 0
0x18015c865  cmp     rdi, 1
0x18015c869  jbe     short loc_18015C899
0x18015c86b  lea     r8, [rdi-1]
0x18015c86f  mov     [rsp+0A8h+var_88], r15
0x18015c874  mov     r9d, 8
0x18015c87a  lea     rcx, [rsp+0A8h+var_70]
0x18015c87f  mov     rdx, rbp
0x18015c882  call    cs:__imp__o_bsearch
0x18015c888  mov     r12, rax
0x18015c88b  test    rax, rax
0x18015c88e  jz      short loc_18015C899
0x18015c890  sub     r12, rbp
0x18015c893  sar     r12, 3
0x18015c897  jmp     short loc_18015C8B3
0x18015c899  cmp     [rbp+rdi*8-8], esi
0x18015c89d  jnz     short loc_18015C8AD
0x18015c89f  lea     r12, ds:0FFFFFFFFFFFFFFF8h[rdi*8]
0x18015c8a7  sar     r12, 3
0x18015c8ab  jmp     short loc_18015C8B3
0x18015c8ad  mov     r12d, 0FFFFFFFFh
0x18015c8b3  mov     rax, [rbx+20h]
0x18015c8b7  lea     r15d, [r12+1]
0x18015c8bc  mov     ebp, r12d
0x18015c8bf  mov     [rsp+0A8h+var_78], r15d
0x18015c8c4  mov     rcx, [rax+10h]
0x18015c8c8  mov     rax, [rcx]
0x18015c8cb  mov     rax, [rax+8]
0x18015c8cf  call    cs:__guard_dispatch_icall_fptr
0x18015c8d5  shr     eax, 3
0x18015c8d8  dec     eax
0x18015c8da  cmp     r12d, eax
0x18015c8dd  jnz     short loc_18015C8E6
0x18015c8df  mov     edi, 7FFFFFFFh
0x18015c8e4  jmp     short loc_18015C90C
0x18015c8e6  mov     rdi, [rbx+20h]
0x18015c8ea  mov     rdx, rbp
0x18015c8ed  mov     rcx, rdi
0x18015c8f0  call    ??A?$ArrayBufStorage@UDiaAddressMapEntry@@@@QEAAAEAUDiaAddressMapEntry@@_K@Z; ArrayBufStorage<DiaAddressMapEntry>::operator[](unsigned __int64)
0x18015c8f5  mov     edx, r15d
0x18015c8f8  mov     rcx, rdi
0x18015c8fb  mov     rsi, rax
0x18015c8fe  call    ??A?$ArrayBufStorage@UDiaAddressMapEntry@@@@QEAAAEAUDiaAddressMapEntry@@_K@Z; ArrayBufStorage<DiaAddressMapEntry>::operator[](unsigned __int64)
0x18015c903  mov     [rsp+0A8h+var_78], r15d
0x18015c908  mov     edi, [rax]
0x18015c90a  sub     edi, [rsi]
0x18015c90c  mov     rsi, [rbx+20h]
0x18015c910  mov     [rsp+0A8h+arg_18], edi
0x18015c917  mov     rcx, [rsi+10h]
0x18015c91b  mov     rax, [rcx]
0x18015c91e  mov     rax, [rax+8]
0x18015c922  call    cs:__guard_dispatch_icall_fptr
0x18015c928  mov     eax, eax
0x18015c92a  shr     rax, 3
0x18015c92e  cmp     rbp, rax
0x18015c931  jnb     loc_18015CB44
0x18015c937  mov     rcx, [rsi+10h]
0x18015c93b  mov     rax, [rcx]
0x18015c93e  mov     rax, [rax]
0x18015c941  call    cs:__guard_dispatch_icall_fptr
0x18015c947  mov     ecx, [rax+rbp*8+4]
0x18015c94b  test    ecx, ecx
0x18015c94d  jz      loc_18015CAC7
0x18015c953  cmp     ecx, [rsp+0A8h+arg_0]
0x18015c95a  jb      short loc_18015C968
0x18015c95c  lea     eax, [rcx+rdi]
0x18015c95f  cmp     eax, r14d
0x18015c962  jbe     loc_18015CAC7
0x18015c968  mov     r15, [rbx+10h]
0x18015c96c  mov     ebp, ecx
0x18015c96e  mov     r13d, [rbx+28h]
0x18015c972  mov     [rsp+0A8h+arg_0], ecx
0x18015c979  cmp     byte ptr [r15+1], 0
0x18015c97e  jz      loc_18015CA0A
0x18015c984  mov     rax, [r15+30h]
0x18015c988  mov     rcx, [rax+10h]
0x18015c98c  mov     rax, [rcx]
0x18015c98f  mov     rax, [rax]
0x18015c992  call    cs:__guard_dispatch_icall_fptr
0x18015c998  mov     rcx, [r15+30h]
0x18015c99c  mov     rbp, rax
0x18015c99f  mov     rcx, [rcx+10h]
0x18015c9a3  mov     rdx, [rcx]
0x18015c9a6  mov     rax, [rdx+8]
0x18015c9aa  call    cs:__guard_dispatch_icall_fptr
0x18015c9b0  mov     rcx, [r15+38h]
0x18015c9b4  mov     esi, eax
0x18015c9b6  shr     rsi, 3
0x18015c9ba  mov     rcx, [rcx+10h]
0x18015c9be  mov     rax, [rcx]
0x18015c9c1  mov     rax, [rax]
0x18015c9c4  call    cs:__guard_dispatch_icall_fptr
0x18015c9ca  mov     rcx, [r15+38h]
0x18015c9ce  mov     rdi, rax
0x18015c9d1  mov     rcx, [rcx+10h]
0x18015c9d5  mov     rdx, [rcx]
0x18015c9d8  mov     rax, [rdx+8]
0x18015c9dc  call    cs:__guard_dispatch_icall_fptr
0x18015c9e2  mov     [rsp+0A8h+var_80], rbp; struct DiaAddressMapEntry *
0x18015c9e7  mov     r9, rdi; struct DiaAddressMapEntry *
0x18015c9ea  mov     r8d, eax
0x18015c9ed  xor     edx, edx; bool
0x18015c9ef  shr     r8, 3; unsigned __int64
0x18015c9f3  mov     ecx, r13d; unsigned int
0x18015c9f6  mov     [rsp+0A8h+var_88], rsi; unsigned __int64
0x18015c9fb  call    ?TranslateRvaThroughOMAP@AddressMap@@KAKK_N_KPEBUDiaAddressMapEntry@@12@Z; AddressMap::TranslateRvaThroughOMAP(ulong,bool,unsigned __int64,DiaAddressMapEntry const *,unsigned __int64,DiaAddressMapEntry const *)
0x18015ca00  mov     ebp, [rsp+0A8h+arg_0]
0x18015ca07  mov     r13d, eax
0x18015ca0a  mov     edx, [rbx+28h]; unsigned int
0x18015ca0d  cmp     edx, [rsp+0A8h+var_74]
0x18015ca11  jz      short loc_18015CA44
0x18015ca13  mov     rcx, [rbx+10h]; this
0x18015ca17  lea     r9, [rsp+0A8h+arg_8]; unsigned int *
0x18015ca1f  lea     r8, [rsp+0A8h+arg_10]; unsigned int *
0x18015ca27  call    ?isectOffForRva@AddressMap@@QEAAXKAEAK0@Z; AddressMap::isectOffForRva(ulong,ulong &,ulong &)
0x18015ca2c  mov     r8d, [rsp+0A8h+arg_8]; unsigned int
0x18015ca34  lea     rcx, [rbx+30h]; this
0x18015ca38  mov     edx, [rsp+0A8h+arg_10]; unsigned int
0x18015ca3f  call    ?init@CAllSymsByAddrTrav@@QEAA_NKK@Z; CAllSymsByAddrTrav::init(ulong,ulong)
0x18015ca44  mov     rax, [rbx+30h]
0x18015ca48  lea     rcx, [rbx+30h]
0x18015ca4c  mov     rax, [rax+28h]
0x18015ca50  call    cs:__guard_dispatch_icall_fptr
0x18015ca56  mov     esi, eax
0x18015ca58  test    eax, eax
0x18015ca5a  jnz     short loc_18015CABE
0x18015ca5c  lea     r8, [rsp+0A8h+arg_8]
0x18015ca64  lea     rdx, [rsp+0A8h+arg_10]
0x18015ca6c  lea     rcx, [rbx+30h]
0x18015ca70  call    ?get@CAllSymsByAddrTrav@@QEAA?AW4safe_hresult@@PEAK0@Z; CAllSymsByAddrTrav::get(ulong *,ulong *)
0x18015ca75  mov     esi, eax
0x18015ca77  test    eax, eax
0x18015ca79  js      loc_18015CB01
0x18015ca7f  mov     edx, [rsp+0A8h+arg_10]
0x18015ca86  mov     rcx, [rbx+10h]; this
0x18015ca8a  dec     edx; unsigned int
0x18015ca8c  mov     edi, [rsp+0A8h+arg_8]
0x18015ca93  call    ?FindPreLegoSection@AddressMap@@QEAAKK@Z; AddressMap::FindPreLegoSection(ulong)
0x18015ca98  xor     r14d, r14d
0x18015ca9b  cmp     eax, 0FFFFFFFFh
0x18015ca9e  lea     ecx, [rax+rdi]
0x18015caa1  cmovnz  r14d, ecx
0x18015caa5  mov     ecx, r14d
0x18015caa8  sub     ecx, r13d
0x18015caab  cmp     r14d, r13d
0x18015caae  jb      short loc_18015CA44
0x18015cab0  mov     eax, r14d
0x18015cab3  sub     eax, ebp
0x18015cab5  cmp     eax, [rsp+0A8h+arg_18]
0x18015cabc  jb      short loc_18015CAFC
0x18015cabe  test    esi, esi
0x18015cac0  js      short loc_18015CB39
0x18015cac2  mov     r15d, [rsp+0A8h+var_78]
0x18015cac7  mov     rax, [rbx+20h]
0x18015cacb  mov     rcx, [rax+10h]
0x18015cacf  mov     rax, [rcx]
0x18015cad2  mov     rax, [rax+8]
0x18015cad6  call    cs:__guard_dispatch_icall_fptr
0x18015cadc  shr     eax, 3
0x18015cadf  dec     eax
0x18015cae1  cmp     r12d, eax
0x18015cae4  jz      short loc_18015CB3D
0x18015cae6  mov     rcx, [rbx+20h]
0x18015caea  mov     edx, r15d
0x18015caed  call    ??A?$ArrayBufStorage@UDiaAddressMapEntry@@@@QEAAAEAUDiaAddressMapEntry@@_K@Z; ArrayBufStorage<DiaAddressMapEntry>::operator[](unsigned __int64)
0x18015caf2  mov     esi, [rax]
0x18015caf4  mov     [rbx+28h], esi
0x18015caf7  jmp     loc_18015C824
0x18015cafc  add     [rbx+28h], ecx
0x18015caff  xor     eax, eax
0x18015cb01  mov     r14, [rsp+0A8h+var_38]
0x18015cb06  mov     r13, [rsp+0A8h+var_30]
0x18015cb0b  mov     r12, [rsp+0A8h+var_28]
0x18015cb13  mov     rdi, [rsp+0A8h+var_20]
0x18015cb1b  mov     rsi, [rsp+0A8h+var_18]
0x18015cb23  mov     rbp, [rsp+0A8h+var_10]
0x18015cb2b  mov     r15, [rsp+0A8h+var_40]
0x18015cb30  add     rsp, 0A0h
0x18015cb37  pop     rbx
0x18015cb38  retn
0x18015cb39  mov     eax, esi
0x18015cb3b  jmp     short loc_18015CB01
0x18015cb3d  mov     eax, 1
0x18015cb42  jmp     short loc_18015CB01
0x18015cb44  lea     rdx, aArraybufstorag; "ArrayBufStorage access out of range"
0x18015cb4b  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18015cb50  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x18015cb55  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18015cb5c  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18015cb61  call    _CxxThrowException_0
```
