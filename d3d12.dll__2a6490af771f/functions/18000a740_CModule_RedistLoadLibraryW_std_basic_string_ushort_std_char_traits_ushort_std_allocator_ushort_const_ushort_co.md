# CModule::RedistLoadLibraryW(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,bool)

- ea: `0x18000a740`
- end: `0x18000a8b5`
- name: `?RedistLoadLibraryW@CModule@@AEAAPEAUHINSTANCE__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000670c`

## callees

- `0x1800066d0`
- `0x180006e2c`
- `0x180006e70`
- `0x180006ea4`
- `0x180006ebc`
- `0x18000a740`
- `0x18000a8bc`
- `0x18000be78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a870`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a870`

## string_xrefs

- `0x18000a852`: `D3D12Core.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall CModule::RedistLoadLibraryW(__int64 a1, _QWORD *a2, __int64 a3, unsigned __int8 a4)
{
  int v4; // r12d
  _QWORD *v5; // rdi
  unsigned int v7; // r8d
  __int64 v8; // r14
  __int64 v9; // r13
  unsigned __int64 v10; // rbx
  char *v11; // r15
  unsigned __int64 v12; // rcx
  WCHAR *v13; // rax
  size_t v14; // rbx
  HMODULE Library; // rbx
  HMODULE result; // rax
  LPCWSTR lpLibFileName; // [rsp+20h] [rbp-48h] BYREF
  void *v18; // [rsp+28h] [rbp-40h]
  __int64 v19; // [rsp+30h] [rbp-38h]
  __int64 v20; // [rsp+80h] [rbp+18h] BYREF

  v20 = a3;
  v4 = a4;
  v5 = a2;
  v7 = *(_DWORD *)(a1 + 40);
  if ( v7 <= 1 )
    return 0;
  v8 = a4 != 0 ? v7 - 1 : 0;
  v9 = a2[2];
  std::vector<std::unique_ptr<D3DCoreModule>>::vector<std::unique_ptr<D3DCoreModule>>(&lpLibFileName);
  try
  {
    v10 = v8 + v9 + 13;
    v11 = (char *)v18;
    v12 = ((_BYTE *)v18 - (_BYTE *)lpLibFileName) >> 1;
    if ( v10 < v12 )
    {
      v13 = (WCHAR *)&lpLibFileName[v10];
LABEL_9:
      v18 = v13;
      goto LABEL_10;
    }
    if ( v10 > v12 )
    {
      if ( v10 <= (v19 - (__int64)lpLibFileName) >> 1 )
      {
        v14 = 2 * (v10 - v12);
        memset_0(v18, 0, v14);
        v13 = (WCHAR *)&v11[v14];
        goto LABEL_9;
      }
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpLibFileName, v8 + v9 + 13);
    }
LABEL_10:
    if ( (_BYTE)v4 )
      std::copy_n<unsigned short *,unsigned __int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(
        &v20,
        *(_QWORD *)(a1 + 16),
        v8,
        lpLibFileName);
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    std::copy<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short *>(v5);
    std::_Copy_memmove_n<unsigned short const *,unsigned short *>(L"D3D12Core.dll");
    Library = LoadLibraryExW(lpLibFileName, 0, (v4 ^ 1u) << 9);
    if ( lpLibFileName )
      std::_Deallocate<16>(lpLibFileName, 2 * ((v19 - (__int64)lpLibFileName) >> 1));
    result = Library;
  }
  catch ( std::bad_alloc )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a740  mov     r11, rsp
0x18000a743  mov     [r11+8], rbx
0x18000a747  mov     [r11+10h], rsi
0x18000a74b  mov     [r11+18h], r8
0x18000a74f  push    rdi
0x18000a750  push    r12
0x18000a752  push    r13
0x18000a754  push    r14
0x18000a756  push    r15
0x18000a758  sub     rsp, 40h
0x18000a75c  movzx   r12d, r9b
0x18000a760  mov     rdi, rdx
0x18000a763  mov     rsi, rcx
0x18000a766  mov     r8d, [rcx+28h]
0x18000a76a  cmp     r8d, 1
0x18000a76e  jbe     loc_18000A89B
0x18000a774  mov     al, r12b
0x18000a777  lea     r14d, [r8-1]
0x18000a77b  neg     al
0x18000a77d  sbb     edx, edx
0x18000a77f  and     r14d, edx
0x18000a782  mov     r13, [rdi+10h]
0x18000a786  lea     rcx, [r11-48h]
0x18000a78a  call    ??0?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<D3DCoreModule>>::vector<std::unique_ptr<D3DCoreModule>>(void)
0x18000a78f  nop
0x18000a790  lea     rbx, [r13+0Dh]
0x18000a794  add     rbx, r14
0x18000a797  mov     rdx, [rsp+68h+lpLibFileName]
0x18000a79c  mov     r15, [rsp+68h+var_40]
0x18000a7a1  mov     rcx, r15
0x18000a7a4  sub     rcx, rdx
0x18000a7a7  sar     rcx, 1
0x18000a7aa  cmp     rbx, rcx
0x18000a7ad  jnb     short loc_18000A7B5
0x18000a7af  lea     rax, [rdx+rbx*2]
0x18000a7b3  jmp     short loc_18000A7ED
0x18000a7b5  jbe     short loc_18000A7F2
0x18000a7b7  mov     rax, [rsp+68h+var_38]
0x18000a7bc  sub     rax, rdx
0x18000a7bf  sar     rax, 1
0x18000a7c2  cmp     rbx, rax
0x18000a7c5  jbe     short loc_18000A7D6
0x18000a7c7  mov     rdx, rbx
0x18000a7ca  lea     rcx, [rsp+68h+lpLibFileName]
0x18000a7cf  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000a7d4  jmp     short loc_18000A7F2
0x18000a7d6  sub     rbx, rcx
0x18000a7d9  add     rbx, rbx
0x18000a7dc  mov     r8, rbx; Size
0x18000a7df  xor     edx, edx; Val
0x18000a7e1  mov     rcx, r15; void *
0x18000a7e4  call    memset_0
0x18000a7e9  lea     rax, [rbx+r15]
0x18000a7ed  mov     [rsp+68h+var_40], rax
0x18000a7f2  test    r12b, r12b
0x18000a7f5  jz      short loc_18000A810
0x18000a7f7  mov     r9, [rsp+68h+lpLibFileName]
0x18000a7fc  mov     r8, r14
0x18000a7ff  mov     rdx, [rsi+10h]
0x18000a803  lea     rcx, [rsp+68h+arg_10]
0x18000a80b  call    ??$copy_n@PEAG_KV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@PEAG_KV10@@Z; std::copy_n<ushort *,unsigned __int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(ushort *,unsigned __int64,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>)
0x18000a810  mov     rax, [rsp+68h+lpLibFileName]
0x18000a815  lea     r8, [rax+r14*2]
0x18000a819  cmp     qword ptr [rdi+18h], 7
0x18000a81e  jbe     short loc_18000A825
0x18000a820  mov     rcx, [rdi]
0x18000a823  jmp     short loc_18000A828
0x18000a825  mov     rcx, rdi
0x18000a828  mov     rax, [rdi+10h]
0x18000a82c  lea     rdx, [rcx+rax*2]
0x18000a830  jbe     short loc_18000A835
0x18000a832  mov     rdi, [rdi]
0x18000a835  mov     rcx, rdi; Src
0x18000a838  call    ??$copy@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEAG@std@@YAPEAGV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@0PEAG@Z; std::copy<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort *>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort *)
0x18000a83d  lea     rcx, [r13-1]
0x18000a841  add     rcx, r14
0x18000a844  mov     rax, [rsp+68h+lpLibFileName]
0x18000a849  lea     r8, [rax+rcx*2]
0x18000a84d  mov     edx, 0Eh
0x18000a852  lea     rcx, aD3d12coreDll; "D3D12Core.dll"
0x18000a859  call    ??$_Copy_memmove_n@PEBGPEAG@std@@YAPEAGPEBG_KPEAG@Z; std::_Copy_memmove_n<ushort const *,ushort *>(ushort const *,unsigned __int64,ushort *)
0x18000a85e  mov     r8d, r12d
0x18000a861  xor     r8d, 1
0x18000a865  shl     r8d, 9; dwFlags
0x18000a869  xor     edx, edx; hFile
0x18000a86b  mov     rcx, [rsp+68h+lpLibFileName]; lpLibFileName
0x18000a870  call    cs:__imp_LoadLibraryExW
0x18000a876  mov     rbx, rax
0x18000a879  mov     rcx, [rsp+68h+lpLibFileName]
0x18000a87e  test    rcx, rcx
0x18000a881  jz      short loc_18000A896
0x18000a883  mov     rdx, [rsp+68h+var_38]
0x18000a888  sub     rdx, rcx
0x18000a88b  sar     rdx, 1
0x18000a88e  add     rdx, rdx
0x18000a891  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a896  mov     rax, rbx
0x18000a899  jmp     short loc_18000A89D
0x18000a89b  xor     eax, eax
0x18000a89d  mov     rbx, [rsp+68h+arg_0]
0x18000a8a2  mov     rsi, [rsp+68h+arg_8]
0x18000a8a7  add     rsp, 40h
0x18000a8ab  pop     r15
0x18000a8ad  pop     r14
0x18000a8af  pop     r13
0x18000a8b1  pop     r12
0x18000a8b3  pop     rdi
0x18000a8b4  retn
```
