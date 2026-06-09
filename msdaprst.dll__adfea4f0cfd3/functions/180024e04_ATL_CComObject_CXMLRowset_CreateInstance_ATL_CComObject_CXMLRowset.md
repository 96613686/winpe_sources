# ATL::CComObject<CXMLRowset>::CreateInstance(ATL::CComObject<CXMLRowset> * *)

- ea: `0x180024e04`
- end: `0x180024eaa`
- name: `?CreateInstance@?$CComObject@VCXMLRowset@@@ATL@@SAJPEAPEAV12@@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800248d8`

## callees

- `0x180001dd4`
- `0x180020e3c`
- `0x180024e04`
- `0x180028d60`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CXMLRowset>::CreateInstance(CRowset **a1, unsigned int a2)
{
  unsigned int v4; // esi
  CXMLRowset *v5; // rax
  CRowset *v6; // rbx

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = -2147024882;
  v5 = (CXMLRowset *)MMMAlloc(0x288u, a2);
  v6 = v5;
  if ( v5 )
  {
    CXMLRowset::CXMLRowset(v5);
    *(_QWORD *)v6 = &ATL::CComObject<CXMLRowset>::`vftable';
    _InterlockedIncrement(&dword_1800464E8);
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    v4 = CRowset::FinalConstruct(v6);
    if ( v4 )
    {
      (*(void (__fastcall **)(CRowset *, __int64))(*(_QWORD *)v6 + 128LL))(v6, 1);
      v6 = 0;
    }
  }
  *a1 = v6;
  return v4;
}

```

## disassembly

```asm
0x180024e04  mov     [rsp+arg_8], rbx
0x180024e09  mov     [rsp+arg_10], rsi
0x180024e0e  push    rdi
0x180024e0f  sub     rsp, 30h
0x180024e13  mov     rdi, rcx
0x180024e16  test    rcx, rcx
0x180024e19  jnz     short loc_180024E22
0x180024e1b  mov     eax, 80004003h
0x180024e20  jmp     short loc_180024E99
0x180024e22  mov     qword ptr [rcx], 0
0x180024e29  mov     esi, 8007000Eh
0x180024e2e  mov     ecx, 288h; unsigned int
0x180024e33  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180024e38  mov     rbx, rax
0x180024e3b  mov     [rsp+38h+arg_0], rax
0x180024e40  test    rax, rax
0x180024e43  jz      short loc_180024E60
0x180024e45  mov     rcx, rax; this
0x180024e48  call    ??0CXMLRowset@@QEAA@XZ; CXMLRowset::CXMLRowset(void)
0x180024e4d  lea     rax, ??_7?$CComObject@VCXMLRowset@@@ATL@@6B@; const ATL::CComObject<CXMLRowset>::`vftable'
0x180024e54  mov     [rbx], rax
0x180024e57  lock inc cs:dword_1800464E8
0x180024e5e  jmp     short loc_180024E62
0x180024e60  xor     ebx, ebx
0x180024e62  test    rbx, rbx
0x180024e65  jz      short loc_180024E8E
0x180024e67  mov     rcx, rbx; this
0x180024e6a  call    ?FinalConstruct@CRowset@@QEAAJXZ; CRowset::FinalConstruct(void)
0x180024e6f  mov     esi, eax
0x180024e71  test    eax, eax
0x180024e73  jz      short loc_180024E8E
0x180024e75  mov     r8, [rbx]
0x180024e78  mov     edx, 1
0x180024e7d  mov     rcx, rbx
0x180024e80  mov     rax, [r8+80h]
0x180024e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e8c  xor     ebx, ebx
0x180024e8e  mov     [rdi], rbx
0x180024e91  mov     eax, esi
0x180024e93  jmp     short loc_180024E99
0x180024e95  mov     eax, [rsp+38h+var_18]
0x180024e99  mov     rbx, [rsp+38h+arg_8]
0x180024e9e  mov     rsi, [rsp+38h+arg_10]
0x180024ea3  add     rsp, 30h
0x180024ea7  pop     rdi
0x180024ea8  retn
```
