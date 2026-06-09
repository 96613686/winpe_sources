# Create_CExtensionsEnumStringRegKeyBase(IEnumString * *,HKEY__ *,ushort const *,_tagEXT_REG_ENUM_TYPE)

- ea: `0x180068c38`
- end: `0x180068cd4`
- name: `?Create_CExtensionsEnumStringRegKeyBase@@YAJPEAPEAUIEnumString@@PEAUHKEY__@@PEBGW4_tagEXT_REG_ENUM_TYPE@@@Z`
- size: `156`
- prototype: `int __high(struct IEnumString **, HKEY, const unsigned __int16 *, enum _tagEXT_REG_ENUM_TYPE)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180064000`

## callees

- `0x1800689b8`
- `0x180068c38`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068c5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068c5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068c4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068c4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068ca2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068ca2`

## pseudocode

```c
__int64 __fastcall Create_CExtensionsEnumStringRegKeyBase(__int64 *a1, __int64 a2, const WCHAR *a3)
{
  unsigned int v5; // edi
  HANDLE ProcessHeap; // rax
  LPVOID v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rdi

  v5 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( v7 )
  {
    v8 = CExtensionsEnumRegKeyBase<IEnumString,&_GUID const IID_IEnumString,unsigned short *>::CExtensionsEnumRegKeyBase<IEnumString,&_GUID const IID_IEnumString,unsigned short *>(v7);
    v9 = v8;
    if ( v8 )
    {
      v10 = (_QWORD *)(v8 + 16);
      if ( *(_QWORD *)(v8 + 16)
        || (*(_DWORD *)(v8 + 24) = 1, RegOpenKeyExW(HKEY_CURRENT_USER, a3, 0, 0x20019u, (PHKEY)(v8 + 16)), *v10) )
      {
        v5 = 0;
        *a1 = v9;
      }
      else
      {
        v5 = -2147467259;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180068c38  push    rbx
0x180068c3a  push    rbp
0x180068c3b  push    rsi
0x180068c3c  push    rdi
0x180068c3d  sub     rsp, 38h
0x180068c41  mov     rbp, r8
0x180068c44  mov     rsi, rcx
0x180068c47  mov     edi, 8007000Eh
0x180068c4c  call    cs:__imp_GetProcessHeap
0x180068c52  mov     edx, 8; dwFlags
0x180068c57  mov     rcx, rax; hHeap
0x180068c5a  lea     r8d, [rdx+18h]; dwBytes
0x180068c5e  call    cs:__imp_HeapAlloc
0x180068c64  test    rax, rax
0x180068c67  jz      short loc_180068CC9
0x180068c69  mov     rcx, rax
0x180068c6c  call    ??0?$CExtensionsEnumRegKeyBase@UIEnumString@@$1?IID_IEnumString@@3U_GUID@@BPEAG@@QEAA@XZ; CExtensionsEnumRegKeyBase<IEnumString,&_GUID const IID_IEnumString,ushort *>::CExtensionsEnumRegKeyBase<IEnumString,&_GUID const IID_IEnumString,ushort *>(void)
0x180068c71  mov     rbx, rax
0x180068c74  test    rax, rax
0x180068c77  jz      short loc_180068CC9
0x180068c79  lea     rdi, [rax+10h]
0x180068c7d  cmp     qword ptr [rdi], 0
0x180068c81  jnz     short loc_180068CAE
0x180068c83  mov     r9d, 20019h; samDesired
0x180068c89  mov     dword ptr [rax+18h], 1
0x180068c90  xor     r8d, r8d; ulOptions
0x180068c93  mov     [rsp+58h+phkResult], rdi; phkResult
0x180068c98  mov     rdx, rbp; lpSubKey
0x180068c9b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180068ca2  call    cs:__imp_RegOpenKeyExW
0x180068ca8  cmp     qword ptr [rdi], 0
0x180068cac  jz      short loc_180068CB5
0x180068cae  xor     edi, edi
0x180068cb0  mov     [rsi], rbx
0x180068cb3  jmp     short loc_180068CC9
0x180068cb5  mov     rcx, [rbx]
0x180068cb8  mov     edi, 80004005h
0x180068cbd  mov     rax, [rcx+10h]
0x180068cc1  mov     rcx, rbx
0x180068cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068cc9  mov     eax, edi
0x180068ccb  add     rsp, 38h
0x180068ccf  pop     rdi
0x180068cd0  pop     rsi
0x180068cd1  pop     rbp
0x180068cd2  pop     rbx
0x180068cd3  retn
```
