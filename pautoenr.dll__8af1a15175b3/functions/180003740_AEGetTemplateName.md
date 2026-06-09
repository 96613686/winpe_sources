# AEGetTemplateName

- ea: `0x180003740`
- end: `0x1800038fc`
- name: `AEGetTemplateName`
- size: `444`
- prototype: `_WORD *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002f50`
- `0x180003a30`

## callees

- `0x180003740`
- `0x180007ce6`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800037f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000389f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800037f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000389f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038eb`
- `CRYPT32!CertFindExtension` at `0x180003775`
- `CRYPT32!CertFindExtension` at `0x180003840`
- `CRYPT32!CertFindExtension` at `0x180003775`
- `CRYPT32!CertFindExtension` at `0x180003840`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800037b9`
- `CRYPT32!CryptDecodeObjectEx` at `0x180003882`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800037b9`
- `CRYPT32!CryptDecodeObjectEx` at `0x180003882`

## pseudocode

```c
_WORD *__fastcall AEGetTemplateName(__int64 a1)
{
  __int64 v1; // rdx
  _WORD *v3; // rdi
  PCERT_EXTENSION Extension; // rax
  unsigned __int64 v5; // rbx
  unsigned __int64 i; // rax
  PCERT_EXTENSION v7; // rax
  __int64 v8; // rcx
  _WORD *v9; // rax
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+10h] BYREF
  HLOCAL pvStructInfo; // [rsp+70h] [rbp+18h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  hMem = 0;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  v3 = 0;
  Extension = CertFindExtension("1.3.6.1.4.1.311.21.7", *(_DWORD *)(v1 + 192), *(CERT_EXTENSION **)(v1 + 200));
  if ( Extension )
  {
    if ( CryptDecodeObjectEx(
           1u,
           "1.3.6.1.4.1.311.21.7",
           Extension->Value.pbData,
           Extension->Value.cbData,
           0x8001u,
           0,
           &pvStructInfo,
           &pcbStructInfo) )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_BYTE *)(*(_QWORD *)pvStructInfo + v5) );
      if ( v5 < 0x7FFFFFFF )
      {
        v3 = LocalAlloc(0, 2 * v5 + 2);
        if ( v3 )
        {
          for ( i = 0; i <= v5; ++i )
            v3[i] = *(char *)(*(_QWORD *)pvStructInfo + i);
        }
      }
    }
  }
  else
  {
    v7 = CertFindExtension(
           "1.3.6.1.4.1.311.20.2",
           *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
           *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
    if ( v7 )
    {
      if ( CryptDecodeObjectEx(1u, (LPCSTR)0x18, v7->Value.pbData, v7->Value.cbData, 0x8001u, 0, &hMem, &pcbStructInfo) )
      {
        v8 = *((unsigned int *)hMem + 2);
        if ( (unsigned int)v8 <= 0xFFFFFFFD )
        {
          v9 = LocalAlloc(0, v8 + 2);
          v3 = v9;
          if ( v9 )
          {
            memcpy_0(v9, *((const void **)hMem + 2), *((unsigned int *)hMem + 2));
            v3[(unsigned __int64)*((unsigned int *)hMem + 2) >> 1] = 0;
          }
        }
      }
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( pvStructInfo )
    LocalFree(pvStructInfo);
  return v3;
}

```

## disassembly

```asm
0x180003740  push    rbx
0x180003742  push    rsi
0x180003743  push    rdi
0x180003744  sub     rsp, 40h
0x180003748  mov     rdx, [rcx+18h]
0x18000374c  xor     esi, esi
0x18000374e  mov     [rsp+58h+hMem], rsi
0x180003753  mov     rbx, rcx
0x180003756  mov     [rsp+58h+arg_10], rsi
0x18000375b  lea     rcx, szStructType; "1.3.6.1.4.1.311.21.7"
0x180003762  mov     [rsp+58h+arg_0], esi
0x180003766  mov     edi, esi
0x180003768  mov     r8, [rdx+0C8h]; rgExtensions
0x18000376f  mov     edx, [rdx+0C0h]; cExtensions
0x180003775  call    cs:__imp_CertFindExtension
0x18000377b  test    rax, rax
0x18000377e  jz      loc_180003828
0x180003784  mov     r9d, [rax+10h]; cbEncoded
0x180003788  lea     rcx, [rsp+58h+arg_0]
0x18000378d  mov     r8, [rax+18h]; pbEncoded
0x180003791  lea     rdx, szStructType; "1.3.6.1.4.1.311.21.7"
0x180003798  mov     [rsp+58h+pcbStructInfo], rcx; pcbStructInfo
0x18000379d  lea     rcx, [rsp+58h+arg_10]
0x1800037a2  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x1800037a7  mov     ecx, 1; dwCertEncodingType
0x1800037ac  mov     [rsp+58h+pDecodePara], rsi; pDecodePara
0x1800037b1  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x1800037b9  call    cs:__imp_CryptDecodeObjectEx
0x1800037bf  test    eax, eax
0x1800037c1  jz      loc_1800038D1
0x1800037c7  mov     rax, [rsp+58h+arg_10]
0x1800037cc  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800037d3  mov     rcx, [rax]
0x1800037d6  inc     rbx
0x1800037d9  cmp     [rcx+rbx], sil
0x1800037dd  jnz     short loc_1800037D6
0x1800037df  cmp     rbx, 7FFFFFFFh
0x1800037e6  jnb     loc_1800038D1
0x1800037ec  lea     rdx, ds:2[rbx*2]; uBytes
0x1800037f4  xor     ecx, ecx; uFlags
0x1800037f6  call    cs:__imp_LocalAlloc
0x1800037fc  mov     rdi, rax
0x1800037ff  test    rax, rax
0x180003802  jz      loc_1800038D1
0x180003808  mov     rax, rsi
0x18000380b  mov     rcx, [rsp+58h+arg_10]
0x180003810  mov     rdx, [rcx]
0x180003813  movsx   ecx, byte ptr [rdx+rax]
0x180003817  mov     [rdi+rax*2], cx
0x18000381b  inc     rax
0x18000381e  cmp     rax, rbx
0x180003821  jbe     short loc_18000380B
0x180003823  jmp     loc_1800038D1
0x180003828  mov     rdx, [rbx+18h]
0x18000382c  lea     rcx, pszObjId; "1.3.6.1.4.1.311.20.2"
0x180003833  mov     r8, [rdx+0C8h]; rgExtensions
0x18000383a  mov     edx, [rdx+0C0h]; cExtensions
0x180003840  call    cs:__imp_CertFindExtension
0x180003846  test    rax, rax
0x180003849  jz      loc_1800038D1
0x18000384f  mov     r9d, [rax+10h]; cbEncoded
0x180003853  lea     rcx, [rsp+58h+arg_0]
0x180003858  mov     r8, [rax+18h]; pbEncoded
0x18000385c  mov     edx, 18h; lpszStructType
0x180003861  mov     [rsp+58h+pcbStructInfo], rcx; pcbStructInfo
0x180003866  lea     rcx, [rsp+58h+hMem]
0x18000386b  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x180003870  mov     ecx, 1; dwCertEncodingType
0x180003875  mov     [rsp+58h+pDecodePara], rsi; pDecodePara
0x18000387a  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x180003882  call    cs:__imp_CryptDecodeObjectEx
0x180003888  test    eax, eax
0x18000388a  jz      short loc_1800038D1
0x18000388c  mov     rax, [rsp+58h+hMem]
0x180003891  mov     ecx, [rax+8]
0x180003894  cmp     ecx, 0FFFFFFFDh
0x180003897  ja      short loc_1800038D1
0x180003899  lea     rdx, [rcx+2]; uBytes
0x18000389d  xor     ecx, ecx; uFlags
0x18000389f  call    cs:__imp_LocalAlloc
0x1800038a5  mov     rdi, rax
0x1800038a8  test    rax, rax
0x1800038ab  jz      short loc_1800038D1
0x1800038ad  mov     rdx, [rsp+58h+hMem]
0x1800038b2  mov     rcx, rax; void *
0x1800038b5  mov     r8d, [rdx+8]; Size
0x1800038b9  mov     rdx, [rdx+10h]; Src
0x1800038bd  call    memcpy_0
0x1800038c2  mov     rax, [rsp+58h+hMem]
0x1800038c7  mov     ecx, [rax+8]
0x1800038ca  shr     rcx, 1
0x1800038cd  mov     [rdi+rcx*2], si
0x1800038d1  mov     rcx, [rsp+58h+hMem]; hMem
0x1800038d6  test    rcx, rcx
0x1800038d9  jz      short loc_1800038E1
0x1800038db  call    cs:__imp_LocalFree
0x1800038e1  mov     rcx, [rsp+58h+arg_10]; hMem
0x1800038e6  test    rcx, rcx
0x1800038e9  jz      short loc_1800038F1
0x1800038eb  call    cs:__imp_LocalFree
0x1800038f1  mov     rax, rdi
0x1800038f4  add     rsp, 40h
0x1800038f8  pop     rdi
0x1800038f9  pop     rsi
0x1800038fa  pop     rbx
0x1800038fb  retn
```
