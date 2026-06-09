# ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)

- ea: `0x180006b60`
- end: `0x180006c08`
- name: `?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800069b0`

## callees

- `0x1800011c4`
- `0x180006b60`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFileStream>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v3; // r14d
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  _DWORD *v7; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x20u);
    v5 = v4;
    if ( v4 )
    {
      v4[2] = 0;
      *((_QWORD *)v4 + 3) = -1;
      *(_QWORD *)v4 = &ATL::CComObject<CFileStream>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v7 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
    v3 = 0;
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180006b60  mov     [rsp+arg_18], rbx
0x180006b65  mov     [rsp+arg_0], rcx
0x180006b6a  push    rsi
0x180006b6b  push    rdi
0x180006b6c  push    r14
0x180006b6e  sub     rsp, 20h
0x180006b72  mov     rsi, rcx
0x180006b75  xor     ebx, ebx
0x180006b77  test    rcx, rcx
0x180006b7a  jnz     short loc_180006B83
0x180006b7c  mov     eax, 80004003h
0x180006b81  jmp     short loc_180006BFA
0x180006b83  mov     [rcx], rbx
0x180006b86  mov     r14d, 8007000Eh
0x180006b8c  mov     [rsp+38h+arg_8], r14d
0x180006b91  mov     [rsp+38h+arg_10], rbx
0x180006b96  mov     ecx, 20h ; ' '; Size
0x180006b9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ba0  mov     rdi, rax
0x180006ba3  test    rax, rax
0x180006ba6  jz      short loc_180006BD2
0x180006ba8  mov     [rax+8], ebx
0x180006bab  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180006bb3  lea     rax, ??_7?$CComObject@VCFileStream@@@ATL@@6B@; const ATL::CComObject<CFileStream>::`vftable'
0x180006bba  mov     [rdi], rax
0x180006bbd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006bc4  mov     rax, [rcx]
0x180006bc7  mov     rax, [rax+8]
0x180006bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd0  jmp     short loc_180006BD5
0x180006bd2  mov     rdi, rbx
0x180006bd5  mov     [rsp+38h+arg_10], rdi
0x180006bda  jmp     short loc_180006BED
0x180006bdc  xor     ebx, ebx
0x180006bde  mov     rsi, [rsp+38h+arg_0]
0x180006be3  mov     r14d, [rsp+38h+arg_8]
0x180006be8  mov     rdi, [rsp+38h+arg_10]
0x180006bed  test    rdi, rdi
0x180006bf0  cmovnz  r14d, ebx
0x180006bf4  mov     [rsi], rdi
0x180006bf7  mov     eax, r14d
0x180006bfa  mov     rbx, [rsp+38h+arg_18]
0x180006bff  add     rsp, 20h
0x180006c03  pop     r14
0x180006c05  pop     rdi
0x180006c06  pop     rsi
0x180006c07  retn
```
