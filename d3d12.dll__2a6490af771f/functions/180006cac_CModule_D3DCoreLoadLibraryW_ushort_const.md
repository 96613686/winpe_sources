# CModule::D3DCoreLoadLibraryW(ushort const *)

- ea: `0x180006cac`
- end: `0x180006dba`
- name: `?D3DCoreLoadLibraryW@CModule@@AEAAPEAUHINSTANCE__@@PEBG@Z`
- size: `270`
- prototype: `HINSTANCE __fastcall(CModule *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000670c`

## callees

- `0x180006cac`
- `0x180006e2c`
- `0x180006e70`
- `0x180006ea4`
- `0x180006ebc`
- `0x18000be78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180006d56`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180006d56`

## string_xrefs

- `0x180006d45`: `D3D12Core.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HINSTANCE __fastcall CModule::D3DCoreLoadLibraryW(CModule *this, const unsigned __int16 *a2)
{
  HMODULE LibraryW; // rbx
  unsigned int v4; // eax
  __int64 v5; // rdi
  unsigned __int64 v6; // rbx
  char *v7; // r14
  unsigned __int64 v8; // rcx
  WCHAR *v10; // rax
  size_t v11; // rbx
  LPCWSTR lpLibFileName; // [rsp+20h] [rbp-48h] BYREF
  void *v13; // [rsp+28h] [rbp-40h]
  __int64 v14; // [rsp+30h] [rbp-38h]
  HMODULE v15; // [rsp+78h] [rbp+10h]

  LibraryW = 0;
  v4 = *((_DWORD *)this + 11);
  if ( v4 <= 1 )
    return LibraryW;
  v5 = v4 - 1;
  std::vector<std::unique_ptr<D3DCoreModule>>::vector<std::unique_ptr<D3DCoreModule>>(&lpLibFileName);
  try
  {
    v6 = v5 + 14;
    v7 = (char *)v13;
    v8 = ((_BYTE *)v13 - (_BYTE *)lpLibFileName) >> 1;
    if ( v5 + 14 < v8 )
    {
      v10 = (WCHAR *)&lpLibFileName[v6];
    }
    else
    {
      if ( v5 + 14 <= v8 )
      {
LABEL_7:
        if ( v5 )
          std::_Copy_memmove_n<unsigned short const *,unsigned short *>(*((void **)this + 3));
        std::_Copy_memmove_n<unsigned short const *,unsigned short *>(L"D3D12Core.dll");
        LibraryW = LoadLibraryW(lpLibFileName);
        v15 = LibraryW;
        if ( lpLibFileName )
          std::_Deallocate<16>(lpLibFileName, 2 * ((v14 - (__int64)lpLibFileName) >> 1));
        return LibraryW;
      }
      if ( v6 > (v14 - (__int64)lpLibFileName) >> 1 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpLibFileName, v5 + 14);
        goto LABEL_7;
      }
      v11 = 2 * (v6 - v8);
      memset_0(v13, 0, v11);
      v10 = (WCHAR *)&v7[v11];
    }
    v13 = v10;
    goto LABEL_7;
  }
  catch ( std::bad_alloc )
  {
    return v15;
  }
  return LibraryW;
}

```

## disassembly

```asm
0x180006cac  mov     [rsp+arg_8], rdx
0x180006cb1  push    rbx
0x180006cb2  push    rsi
0x180006cb3  push    rdi
0x180006cb4  push    r14
0x180006cb6  sub     rsp, 48h
0x180006cba  mov     rsi, rcx
0x180006cbd  xor     ebx, ebx
0x180006cbf  mov     [rsp+68h+arg_8], rbx
0x180006cc4  mov     eax, [rcx+2Ch]
0x180006cc7  cmp     eax, 1
0x180006cca  jbe     loc_180006D82
0x180006cd0  lea     edi, [rax-1]
0x180006cd3  lea     rcx, [rsp+68h+lpLibFileName]
0x180006cd8  call    ??0?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<D3DCoreModule>>::vector<std::unique_ptr<D3DCoreModule>>(void)
0x180006cdd  nop
0x180006cde  lea     rbx, [rdi+0Eh]
0x180006ce2  mov     rdx, [rsp+68h+lpLibFileName]
0x180006ce7  mov     r14, [rsp+68h+var_40]
0x180006cec  mov     rcx, r14
0x180006cef  sub     rcx, rdx
0x180006cf2  sar     rcx, 1
0x180006cf5  cmp     rbx, rcx
0x180006cf8  jb      loc_180006D8F
0x180006cfe  jbe     short loc_180006D21
0x180006d00  mov     rax, [rsp+68h+var_38]
0x180006d05  sub     rax, rdx
0x180006d08  sar     rax, 1
0x180006d0b  cmp     rbx, rax
0x180006d0e  jbe     loc_180006D9A
0x180006d14  mov     rdx, rbx
0x180006d17  lea     rcx, [rsp+68h+lpLibFileName]
0x180006d1c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180006d21  test    rdi, rdi
0x180006d24  jz      short loc_180006D37
0x180006d26  mov     r8, [rsp+68h+lpLibFileName]
0x180006d2b  mov     rdx, rdi
0x180006d2e  mov     rcx, [rsi+18h]; Src
0x180006d32  call    ??$_Copy_memmove_n@PEBGPEAG@std@@YAPEAGPEBG_KPEAG@Z; std::_Copy_memmove_n<ushort const *,ushort *>(ushort const *,unsigned __int64,ushort *)
0x180006d37  mov     rax, [rsp+68h+lpLibFileName]
0x180006d3c  lea     r8, [rax+rdi*2]
0x180006d40  mov     edx, 0Eh
0x180006d45  lea     rcx, aD3d12coreDll; "D3D12Core.dll"
0x180006d4c  call    ??$_Copy_memmove_n@PEBGPEAG@std@@YAPEAGPEBG_KPEAG@Z; std::_Copy_memmove_n<ushort const *,ushort *>(ushort const *,unsigned __int64,ushort *)
0x180006d51  mov     rcx, [rsp+68h+lpLibFileName]; lpLibFileName
0x180006d56  call    cs:__imp_LoadLibraryW
0x180006d5c  mov     rbx, rax
0x180006d5f  mov     [rsp+68h+arg_8], rax
0x180006d64  mov     rcx, [rsp+68h+lpLibFileName]
0x180006d69  test    rcx, rcx
0x180006d6c  jz      short loc_180006D82
0x180006d6e  mov     rdx, [rsp+68h+var_38]
0x180006d73  sub     rdx, rcx
0x180006d76  sar     rdx, 1
0x180006d79  add     rdx, rdx
0x180006d7c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006d81  nop
0x180006d82  mov     rax, rbx
0x180006d85  add     rsp, 48h
0x180006d89  pop     r14
0x180006d8b  pop     rdi
0x180006d8c  pop     rsi
0x180006d8d  pop     rbx
0x180006d8e  retn
0x180006d8f  lea     rax, [rdx+rbx*2]
0x180006d93  mov     [rsp+68h+var_40], rax
0x180006d98  jmp     short loc_180006D21
0x180006d9a  sub     rbx, rcx
0x180006d9d  add     rbx, rbx
0x180006da0  mov     r8, rbx; Size
0x180006da3  xor     edx, edx; Val
0x180006da5  mov     rcx, r14; void *
0x180006da8  call    memset_0
0x180006dad  lea     rax, [rbx+r14]
0x180006db1  jmp     short loc_180006D93
0x180006db3  mov     rbx, [rsp+68h+arg_8]
0x180006db8  jmp     short loc_180006D82
```
