# CModule::SDKLoadLibraryW(ushort const *)

- ea: `0x1800b01a0`
- end: `0x1800b03eb`
- name: `?SDKLoadLibraryW@CModule@@QEAAPEAUHINSTANCE__@@PEBG@Z`
- size: `587`
- prototype: `HINSTANCE(CModule *__hidden this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180048670`
- `0x1800491ec`
- `0x18004a74c`
- `0x1800522d0`
- `0x180059bcc`
- `0x18006bda8`
- `0x18008c850`
- `0x1800d4a14`

## callees

- `0x18004e694`
- `0x18009d94c`
- `0x1800adde8`
- `0x1800ae13c`
- `0x1800b01a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800b01ba`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800b01ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0257`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b02e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0373`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0257`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b02e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0373`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
HINSTANCE __fastcall CModule::SDKLoadLibraryW(CModule *this, const unsigned __int16 *a2)
{
  HMODULE Library; // rbx
  size_t v5; // rsi
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // ebx
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  unsigned int v12; // ecx
  unsigned int v13; // ebx
  __int128 v14; // [rsp+20h] [rbp-48h] BYREF
  __int64 v15; // [rsp+30h] [rbp-38h]
  HMODULE v16; // [rsp+70h] [rbp+8h] BYREF

  Library = 0;
  v16 = 0;
  v5 = wcslen(a2) + 1;
  v14 = 0;
  v15 = 0;
  v6 = *((_DWORD *)this + 65);
  if ( v6 <= 1 )
    goto LABEL_19;
  if ( v5 + v6 )
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v14);
  std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
    a2,
    &a2[v5],
    v14 - 2 + 2LL * *((unsigned int *)this + 65));
  v7 = *((_DWORD *)this + 62);
  if ( v7 > 1 )
  {
    v8 = *((_DWORD *)this + 65) - v7;
    std::copy<unsigned short *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(
      &v16,
      *((_QWORD *)this + 28),
      *((_QWORD *)this + 28) + 2LL * (v7 - 1),
      v14 + 2LL * v8);
    Library = LoadLibraryExW((LPCWSTR)(v14 + 2LL * v8), 0, 0);
    v16 = Library;
    if ( Library )
    {
      if ( (_QWORD)v14 )
      {
        std::_Deallocate<16>(v14, 2 * ((v15 - (__int64)v14) >> 1));
        v14 = 0;
        v15 = 0;
      }
      return Library;
    }
  }
  v10 = *((_DWORD *)this + 63);
  if ( v10 > 1 )
  {
    v11 = *((_DWORD *)this + 65) - v10;
    std::copy<unsigned short *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(
      &v16,
      *((_QWORD *)this + 29),
      *((_QWORD *)this + 29) + 2LL * (v10 - 1),
      v14 + 2LL * v11);
    Library = LoadLibraryExW((LPCWSTR)(v14 + 2LL * v11), 0, 0);
    v16 = Library;
    if ( Library )
    {
      if ( (_QWORD)v14 )
      {
        std::_Deallocate<16>(v14, 2 * ((v15 - (__int64)v14) >> 1));
        v14 = 0;
        v15 = 0;
      }
      return Library;
    }
  }
  v12 = *((_DWORD *)this + 64);
  if ( v12 > 1
    && (v13 = *((_DWORD *)this + 65) - v12,
        std::copy<unsigned short *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(
          &v16,
          *((_QWORD *)this + 30),
          *((_QWORD *)this + 30) + 2LL * (v12 - 1),
          v14 + 2LL * v13),
        Library = LoadLibraryExW((LPCWSTR)(v14 + 2LL * v13), 0, 0),
        (v16 = Library) != 0) )
  {
    if ( (_QWORD)v14 )
    {
      std::_Deallocate<16>(v14, 2 * ((v15 - (__int64)v14) >> 1));
      v14 = 0;
      v15 = 0;
    }
    return Library;
  }
  else
  {
LABEL_19:
    if ( (_QWORD)v14 )
      std::_Deallocate<16>(v14, 2 * ((v15 - (__int64)v14) >> 1));
    return Library;
  }
}

```

## disassembly

```asm
0x1800b01a0  push    rbx
0x1800b01a2  push    rsi
0x1800b01a3  push    rdi
0x1800b01a4  push    r14
0x1800b01a6  sub     rsp, 48h
0x1800b01aa  mov     r14, rdx
0x1800b01ad  mov     rdi, rcx
0x1800b01b0  xor     ebx, ebx
0x1800b01b2  mov     [rsp+68h+arg_0], rbx
0x1800b01b7  mov     rcx, rdx; String
0x1800b01ba  call    cs:__imp_wcslen
0x1800b01c0  lea     rsi, [rax+1]
0x1800b01c4  xorps   xmm0, xmm0
0x1800b01c7  movdqu  [rsp+68h+var_48], xmm0
0x1800b01cd  mov     [rsp+68h+var_38], rbx
0x1800b01d2  mov     eax, [rdi+104h]
0x1800b01d8  cmp     eax, 1
0x1800b01db  jbe     loc_1800B03C1
0x1800b01e1  mov     edx, eax
0x1800b01e3  add     rdx, rsi
0x1800b01e6  jz      short loc_1800B01F2
0x1800b01e8  lea     rcx, [rsp+68h+var_48]
0x1800b01ed  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b01f2  mov     ecx, [rdi+104h]
0x1800b01f8  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b01fd  sub     rax, 2
0x1800b0201  lea     r8, [rax+rcx*2]
0x1800b0205  lea     rdx, [r14+rsi*2]
0x1800b0209  mov     rcx, r14
0x1800b020c  call    ??$_Copy_memmove@PEBU_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3@@PEAU1@@std@@YAPEAU_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3@@PEBU1@0PEAU1@@Z; std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *)
0x1800b0211  mov     ecx, [rdi+0F8h]
0x1800b0217  cmp     ecx, 1
0x1800b021a  jbe     loc_1800B02A1
0x1800b0220  mov     ebx, [rdi+104h]
0x1800b0226  sub     ebx, ecx
0x1800b0228  mov     rdx, [rdi+0E0h]
0x1800b022f  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b0234  lea     r9, [rax+rbx*2]
0x1800b0238  lea     eax, [rcx-1]
0x1800b023b  lea     r8, [rdx+rax*2]
0x1800b023f  lea     rcx, [rsp+68h+arg_0]
0x1800b0244  call    ??$copy@PEAGV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@PEAG0V10@@Z; std::copy<ushort *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(ushort *,ushort *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>)
0x1800b0249  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b024e  lea     rcx, [rax+rbx*2]; lpLibFileName
0x1800b0252  xor     r8d, r8d; dwFlags
0x1800b0255  xor     edx, edx; hFile
0x1800b0257  call    cs:__imp_LoadLibraryExW
0x1800b025d  mov     rbx, rax
0x1800b0260  mov     [rsp+68h+arg_0], rax
0x1800b0265  test    rax, rax
0x1800b0268  jz      short loc_1800B02A1
0x1800b026a  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800b026f  test    rcx, rcx
0x1800b0272  jz      short loc_1800B0299
0x1800b0274  mov     rdx, [rsp+68h+var_38]
0x1800b0279  sub     rdx, rcx
0x1800b027c  sar     rdx, 1
0x1800b027f  add     rdx, rdx
0x1800b0282  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b0287  xorps   xmm0, xmm0
0x1800b028a  movdqu  [rsp+68h+var_48], xmm0
0x1800b0290  mov     [rsp+68h+var_38], 0
0x1800b0299  mov     rax, rbx
0x1800b029c  jmp     loc_1800B03E1
0x1800b02a1  mov     ecx, [rdi+0FCh]
0x1800b02a7  cmp     ecx, 1
0x1800b02aa  jbe     loc_1800B0331
0x1800b02b0  mov     ebx, [rdi+104h]
0x1800b02b6  sub     ebx, ecx
0x1800b02b8  mov     rdx, [rdi+0E8h]
0x1800b02bf  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b02c4  lea     r9, [rax+rbx*2]
0x1800b02c8  lea     eax, [rcx-1]
0x1800b02cb  lea     r8, [rdx+rax*2]
0x1800b02cf  lea     rcx, [rsp+68h+arg_0]
0x1800b02d4  call    ??$copy@PEAGV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@PEAG0V10@@Z; std::copy<ushort *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(ushort *,ushort *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>)
0x1800b02d9  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b02de  lea     rcx, [rax+rbx*2]; lpLibFileName
0x1800b02e2  xor     r8d, r8d; dwFlags
0x1800b02e5  xor     edx, edx; hFile
0x1800b02e7  call    cs:__imp_LoadLibraryExW
0x1800b02ed  mov     rbx, rax
0x1800b02f0  mov     [rsp+68h+arg_0], rax
0x1800b02f5  test    rax, rax
0x1800b02f8  jz      short loc_1800B0331
0x1800b02fa  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800b02ff  test    rcx, rcx
0x1800b0302  jz      short loc_1800B0329
0x1800b0304  mov     rdx, [rsp+68h+var_38]
0x1800b0309  sub     rdx, rcx
0x1800b030c  sar     rdx, 1
0x1800b030f  add     rdx, rdx
0x1800b0312  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b0317  xorps   xmm0, xmm0
0x1800b031a  movdqu  [rsp+68h+var_48], xmm0
0x1800b0320  mov     [rsp+68h+var_38], 0
0x1800b0329  mov     rax, rbx
0x1800b032c  jmp     loc_1800B03E1
0x1800b0331  mov     ecx, [rdi+100h]
0x1800b0337  cmp     ecx, 1
0x1800b033a  jbe     short loc_1800B03BA
0x1800b033c  mov     ebx, [rdi+104h]
0x1800b0342  sub     ebx, ecx
0x1800b0344  mov     rdx, [rdi+0F0h]
0x1800b034b  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b0350  lea     r9, [rax+rbx*2]
0x1800b0354  lea     eax, [rcx-1]
0x1800b0357  lea     r8, [rdx+rax*2]
0x1800b035b  lea     rcx, [rsp+68h+arg_0]
0x1800b0360  call    ??$copy@PEAGV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@PEAG0V10@@Z; std::copy<ushort *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(ushort *,ushort *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>)
0x1800b0365  mov     rax, qword ptr [rsp+68h+var_48]
0x1800b036a  lea     rcx, [rax+rbx*2]; lpLibFileName
0x1800b036e  xor     r8d, r8d; dwFlags
0x1800b0371  xor     edx, edx; hFile
0x1800b0373  call    cs:__imp_LoadLibraryExW
0x1800b0379  mov     rbx, rax
0x1800b037c  mov     [rsp+68h+arg_0], rax
0x1800b0381  test    rax, rax
0x1800b0384  jz      short loc_1800B03BA
0x1800b0386  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800b038b  test    rcx, rcx
0x1800b038e  jz      short loc_1800B03B5
0x1800b0390  mov     rdx, [rsp+68h+var_38]
0x1800b0395  sub     rdx, rcx
0x1800b0398  sar     rdx, 1
0x1800b039b  add     rdx, rdx
0x1800b039e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b03a3  xorps   xmm0, xmm0
0x1800b03a6  movdqu  [rsp+68h+var_48], xmm0
0x1800b03ac  mov     [rsp+68h+var_38], 0
0x1800b03b5  mov     rax, rbx
0x1800b03b8  jmp     short loc_1800B03E1
0x1800b03ba  jmp     short loc_1800B03C1
0x1800b03bc  mov     rbx, [rsp+68h+arg_0]
0x1800b03c1  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800b03c6  test    rcx, rcx
0x1800b03c9  jz      short loc_1800B03DE
0x1800b03cb  mov     rdx, [rsp+68h+var_38]
0x1800b03d0  sub     rdx, rcx
0x1800b03d3  sar     rdx, 1
0x1800b03d6  add     rdx, rdx
0x1800b03d9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b03de  mov     rax, rbx
0x1800b03e1  add     rsp, 48h
0x1800b03e5  pop     r14
0x1800b03e7  pop     rdi
0x1800b03e8  pop     rsi
0x1800b03e9  pop     rbx
0x1800b03ea  retn
```
