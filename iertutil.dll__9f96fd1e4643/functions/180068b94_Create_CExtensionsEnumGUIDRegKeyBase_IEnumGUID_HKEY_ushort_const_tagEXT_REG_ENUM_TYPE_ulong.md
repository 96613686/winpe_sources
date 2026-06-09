# Create_CExtensionsEnumGUIDRegKeyBase(IEnumGUID * *,HKEY__ *,ushort const *,_tagEXT_REG_ENUM_TYPE,ulong)

- ea: `0x180068b94`
- end: `0x180068c30`
- name: `?Create_CExtensionsEnumGUIDRegKeyBase@@YAJPEAPEAUIEnumGUID@@PEAUHKEY__@@PEBGW4_tagEXT_REG_ENUM_TYPE@@K@Z`
- size: `156`
- prototype: `int __high(struct IEnumGUID **, HKEY, const unsigned __int16 *, enum _tagEXT_REG_ENUM_TYPE, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180063c60`
- `0x180063d30`

## callees

- `0x18006898c`
- `0x180068b94`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068bba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068bba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068ba8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068ba8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068bfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068bfe`

## pseudocode

```c
__int64 __fastcall Create_CExtensionsEnumGUIDRegKeyBase(__int64 *a1, HKEY a2)
{
  unsigned int v4; // edi
  HANDLE ProcessHeap; // rax
  LPVOID v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  _QWORD *v9; // rdi

  v4 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( v6 )
  {
    v7 = CExtensionsEnumRegKeyBase<IEnumGUID,&_GUID const IID_IEnumGUID,_GUID>::CExtensionsEnumRegKeyBase<IEnumGUID,&_GUID const IID_IEnumGUID,_GUID>(v6);
    v8 = v7;
    if ( v7 )
    {
      v9 = (_QWORD *)(v7 + 16);
      if ( *(_QWORD *)(v7 + 16)
        || (*(_DWORD *)(v7 + 24) = 1, RegOpenKeyExW(a2, &word_1801758E4, 0, 0x20019u, (PHKEY)(v7 + 16)), *v9) )
      {
        v4 = 0;
        *a1 = v8;
      }
      else
      {
        v4 = -2147467259;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180068b94  push    rbx
0x180068b96  push    rbp
0x180068b97  push    rsi
0x180068b98  push    rdi
0x180068b99  sub     rsp, 38h
0x180068b9d  mov     rbp, rdx
0x180068ba0  mov     rsi, rcx
0x180068ba3  mov     edi, 8007000Eh
0x180068ba8  call    cs:__imp_GetProcessHeap
0x180068bae  mov     edx, 8; dwFlags
0x180068bb3  mov     rcx, rax; hHeap
0x180068bb6  lea     r8d, [rdx+18h]; dwBytes
0x180068bba  call    cs:__imp_HeapAlloc
0x180068bc0  test    rax, rax
0x180068bc3  jz      short loc_180068C25
0x180068bc5  mov     rcx, rax
0x180068bc8  call    ??0?$CExtensionsEnumRegKeyBase@UIEnumGUID@@$1?IID_IEnumGUID@@3U_GUID@@BU3@@@QEAA@XZ; CExtensionsEnumRegKeyBase<IEnumGUID,&_GUID const IID_IEnumGUID,_GUID>::CExtensionsEnumRegKeyBase<IEnumGUID,&_GUID const IID_IEnumGUID,_GUID>(void)
0x180068bcd  mov     rbx, rax
0x180068bd0  test    rax, rax
0x180068bd3  jz      short loc_180068C25
0x180068bd5  lea     rdi, [rax+10h]
0x180068bd9  cmp     qword ptr [rdi], 0
0x180068bdd  jnz     short loc_180068C0A
0x180068bdf  mov     r9d, 20019h; samDesired
0x180068be5  mov     dword ptr [rax+18h], 1
0x180068bec  xor     r8d, r8d; ulOptions
0x180068bef  mov     [rsp+58h+phkResult], rdi; phkResult
0x180068bf4  lea     rdx, word_1801758E4; lpSubKey
0x180068bfb  mov     rcx, rbp; hKey
0x180068bfe  call    cs:__imp_RegOpenKeyExW
0x180068c04  cmp     qword ptr [rdi], 0
0x180068c08  jz      short loc_180068C11
0x180068c0a  xor     edi, edi
0x180068c0c  mov     [rsi], rbx
0x180068c0f  jmp     short loc_180068C25
0x180068c11  mov     rcx, [rbx]
0x180068c14  mov     edi, 80004005h
0x180068c19  mov     rax, [rcx+10h]
0x180068c1d  mov     rcx, rbx
0x180068c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c25  mov     eax, edi
0x180068c27  add     rsp, 38h
0x180068c2b  pop     rdi
0x180068c2c  pop     rsi
0x180068c2d  pop     rbp
0x180068c2e  pop     rbx
0x180068c2f  retn
```
