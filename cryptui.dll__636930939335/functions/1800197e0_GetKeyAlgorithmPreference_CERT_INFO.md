# GetKeyAlgorithmPreference(_CERT_INFO *)

- ea: `0x1800197e0`
- end: `0x18001988f`
- name: `?GetKeyAlgorithmPreference@@YAKPEAU_CERT_INFO@@@Z`
- size: `175`
- prototype: `unsigned int __fastcall(struct _CERT_INFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d72c`
- `0x180018d9c`

## callees

- `0x180001f66`
- `0x1800178c0`
- `0x1800197e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001987c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001987c`
- `CRYPT32!CertFindExtension` at `0x180019807`
- `CRYPT32!CertFindExtension` at `0x180019807`

## pseudocode

```c
__int64 __fastcall GetKeyAlgorithmPreference(struct _CERT_INFO *a1)
{
  CERT_EXTENSION *rgExtension; // r8
  _DWORD *v2; // rbx
  DWORD cExtension; // edx
  unsigned int v4; // edi
  PCERT_EXTENSION Extension; // rax
  int v6; // eax
  const void *v7; // rdx
  size_t v8; // r8
  void *v10; // [rsp+40h] [rbp+8h] BYREF

  rgExtension = a1->rgExtension;
  v2 = 0;
  cExtension = a1->cExtension;
  v4 = 0;
  v10 = 0;
  Extension = CertFindExtension("2.5.29.15", cExtension, rgExtension);
  if ( Extension )
  {
    v6 = CertUIDecodeObject((LPCSTR)0xE, Extension->Value.pbData, Extension->Value.cbData, 0, &v10);
    v2 = v10;
    if ( v6 )
    {
      if ( *(_DWORD *)v10 )
      {
        v7 = (const void *)*((_QWORD *)v10 + 1);
        if ( v7 )
        {
          v8 = 4;
          LODWORD(v10) = 0;
          if ( *v2 <= 4u )
            v8 = (unsigned int)*v2;
          memcpy_0(&v10, v7, v8);
          if ( (char)v10 < 0 )
            v4 = 0x80000000;
          if ( ((unsigned __int16)v10 & 0x8039) != 0 )
            v4 = 0x40000000;
        }
      }
    }
  }
  LocalFree(v2);
  return v4;
}

```

## disassembly

```asm
0x1800197e0  mov     [rsp+arg_8], rbx
0x1800197e5  push    rdi
0x1800197e6  sub     rsp, 30h
0x1800197ea  mov     r8, [rcx+0C8h]; rgExtensions
0x1800197f1  xor     ebx, ebx
0x1800197f3  mov     edx, [rcx+0C0h]; cExtensions
0x1800197f9  xor     edi, edi
0x1800197fb  lea     rcx, a252915; "2.5.29.15"
0x180019802  mov     [rsp+38h+arg_0], rbx
0x180019807  call    cs:__imp_CertFindExtension
0x18001980d  test    rax, rax
0x180019810  jz      short loc_180019879
0x180019812  mov     r8d, [rax+10h]; cbEncoded
0x180019816  lea     rcx, [rsp+38h+arg_0]
0x18001981b  mov     rdx, [rax+18h]; pbEncoded
0x18001981f  xor     r9d, r9d; dwFlags
0x180019822  mov     [rsp+38h+var_18], rcx; void **
0x180019827  lea     ecx, [rdi+0Eh]; lpszStructType
0x18001982a  call    ?CertUIDecodeObject@@YAHPEBDPEAEKKPEAPEAX@Z; CertUIDecodeObject(char const *,uchar *,ulong,ulong,void * *)
0x18001982f  mov     rbx, [rsp+38h+arg_0]
0x180019834  test    eax, eax
0x180019836  jz      short loc_180019879
0x180019838  cmp     [rbx], edi
0x18001983a  jz      short loc_180019879
0x18001983c  mov     rdx, [rbx+8]; Src
0x180019840  test    rdx, rdx
0x180019843  jz      short loc_180019879
0x180019845  lea     r8d, [rdi+4]
0x180019849  mov     dword ptr [rsp+38h+arg_0], edi
0x18001984d  cmp     [rbx], r8d
0x180019850  ja      short loc_180019855
0x180019852  mov     r8d, [rbx]; Size
0x180019855  lea     rcx, [rsp+38h+arg_0]; void *
0x18001985a  call    memcpy_0
0x18001985f  mov     eax, dword ptr [rsp+38h+arg_0]
0x180019863  test    al, al
0x180019865  jns     short loc_18001986C
0x180019867  mov     edi, 80000000h
0x18001986c  test    eax, 8039h
0x180019871  mov     eax, 40000000h
0x180019876  cmovnz  edi, eax
0x180019879  mov     rcx, rbx; hMem
0x18001987c  call    cs:__imp_LocalFree
0x180019882  mov     rbx, [rsp+38h+arg_8]
0x180019887  mov     eax, edi
0x180019889  add     rsp, 30h
0x18001988d  pop     rdi
0x18001988e  retn
```
