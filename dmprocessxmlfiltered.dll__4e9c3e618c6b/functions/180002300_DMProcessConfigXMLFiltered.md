# DMProcessConfigXMLFiltered

- ea: `0x180002300`
- end: `0x1800024f0`
- name: `DMProcessConfigXMLFiltered`
- size: `496`
- prototype: `HRESULT __stdcall(PCWSTR pszXmlIn, PCWSTR *rgszAllowedCspNodes, DWORD dwNumAllowedCspNodes, BSTR *pbstrXmlOut)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800021e0`
- `0x180002300`
- `0x180003ab8`
- `0x180006bd0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002384`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002384`
- `XmlLite!CreateXmlReader` at `0x1800023bc`
- `XmlLite!CreateXmlReader` at `0x1800023bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DMProcessConfigXMLFiltered(
        PCWSTR pszXmlIn,
        PCWSTR *rgszAllowedCspNodes,
        DWORD dwNumAllowedCspNodes,
        BSTR *pbstrXmlOut)
{
  __int64 v8; // rdx
  PCWSTR v9; // rax
  unsigned int v10; // ebx
  HLOCAL v11; // rax
  int v12; // ebx
  int v13; // edi
  int v14; // ebx
  void *ppvObject; // [rsp+20h] [rbp-28h] BYREF
  void **v17; // [rsp+28h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-18h]
  __int64 v19; // [rsp+38h] [rbp-10h]
  int v20; // [rsp+90h] [rbp+48h] BYREF

  ppvObject = 0;
  v17 = &CMyXmlStream::`vftable';
  hMem = 0;
  v19 = 0;
  if ( !pszXmlIn )
    goto LABEL_24;
  v8 = 0x7FFFFFFF;
  v9 = pszXmlIn;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  if ( !v8 )
    goto LABEL_24;
  v10 = 2 * (v8 != 0 ? 0x7FFFFFFF - v8 : 0) + 2;
  v11 = LocalAlloc(0, v10);
  hMem = v11;
  if ( v11 )
  {
    memcpy_0(v11, pszXmlIn, v10);
    LODWORD(v19) = v10;
  }
  if ( hMem )
  {
    v12 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(void *, void ***))(*(_QWORD *)ppvObject + 24LL))(ppvObject, &v17);
        if ( v12 >= 0 )
        {
          v20 = 0;
          v13 = 0;
          while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v20) )
          {
            if ( v20 == 1 )
            {
              if ( v13 == 1 )
              {
                v12 = ValidateAllowedCsp((struct IXmlReader *)ppvObject, rgszAllowedCspNodes, dwNumAllowedCspNodes);
                if ( v12 < 0 )
                  goto LABEL_25;
              }
              if ( (*(int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 88LL))(ppvObject) < 0 )
              {
                v12 = -2147418113;
                goto LABEL_25;
              }
              v14 = v13++;
              if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
                v13 = v14;
            }
            else if ( v20 == 15 )
            {
              --v13;
            }
          }
          v12 = DMProcessConfigXML_Remote(pszXmlIn, pbstrXmlOut);
        }
      }
    }
  }
  else
  {
LABEL_24:
    v12 = -2147024882;
  }
LABEL_25:
  v17 = &CMyXmlStream::`vftable';
  if ( hMem )
    LocalFree(hMem);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  return v12;
}

```

## disassembly

```asm
0x180002300  push    rbp
0x180002302  push    rbx
0x180002303  push    rsi
0x180002304  push    rdi
0x180002305  push    r12
0x180002307  push    r13
0x180002309  push    r14
0x18000230b  push    r15
0x18000230d  mov     rbp, rsp
0x180002310  sub     rsp, 48h
0x180002314  mov     r15, r9
0x180002317  mov     r12d, r8d
0x18000231a  mov     r13, rdx
0x18000231d  mov     rsi, rcx
0x180002320  xor     r14d, r14d
0x180002323  mov     [rbp+ppvObject], r14
0x180002327  lea     rax, ??_7CMyXmlStream@@6B@; const CMyXmlStream::`vftable'
0x18000232e  mov     [rbp+var_20], rax
0x180002332  mov     [rbp+hMem], r14
0x180002336  mov     [rbp+var_10], r14
0x18000233a  test    rcx, rcx
0x18000233d  jz      loc_1800024A7
0x180002343  mov     r8d, 7FFFFFFFh
0x180002349  mov     edx, r8d
0x18000234c  mov     rax, rcx
0x18000234f  cmp     [rax], r14w
0x180002353  jz      short loc_18000235F
0x180002355  add     rax, 2
0x180002359  sub     rdx, 1
0x18000235d  jnz     short loc_18000234F
0x18000235f  mov     rax, rdx
0x180002362  sub     r8, rdx
0x180002365  neg     rax
0x180002368  sbb     rcx, rcx
0x18000236b  and     rcx, r8
0x18000236e  test    rdx, rdx
0x180002371  jz      loc_1800024A7
0x180002377  lea     ebx, ds:2[rcx*2]
0x18000237e  mov     edi, ebx
0x180002380  mov     edx, ebx; uBytes
0x180002382  xor     ecx, ecx; uFlags
0x180002384  call    cs:__imp_LocalAlloc
0x18000238a  mov     [rbp+hMem], rax
0x18000238e  test    rax, rax
0x180002391  jz      short loc_1800023A4
0x180002393  mov     r8d, edi; Size
0x180002396  mov     rdx, rsi; Src
0x180002399  mov     rcx, rax; void *
0x18000239c  call    memcpy_0
0x1800023a1  mov     dword ptr [rbp+var_10], ebx
0x1800023a4  cmp     [rbp+hMem], r14
0x1800023a8  jz      loc_1800024A7
0x1800023ae  xor     r8d, r8d; pMalloc
0x1800023b1  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800023b5  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800023bc  call    cs:__imp_CreateXmlReader
0x1800023c2  mov     ebx, eax
0x1800023c4  test    eax, eax
0x1800023c6  js      loc_1800024AC
0x1800023cc  mov     rcx, [rbp+ppvObject]
0x1800023d0  mov     rax, [rcx]
0x1800023d3  xor     r8d, r8d
0x1800023d6  lea     edx, [r8+4]
0x1800023da  mov     rax, [rax+28h]
0x1800023de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e3  mov     ebx, eax
0x1800023e5  test    eax, eax
0x1800023e7  js      loc_1800024AC
0x1800023ed  mov     rcx, [rbp+ppvObject]
0x1800023f1  mov     rax, [rcx]
0x1800023f4  lea     rdx, [rbp+var_20]
0x1800023f8  mov     rax, [rax+18h]
0x1800023fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002401  mov     ebx, eax
0x180002403  test    eax, eax
0x180002405  js      loc_1800024AC
0x18000240b  mov     [rbp+arg_0], r14d
0x18000240f  mov     edi, r14d
0x180002412  mov     rcx, [rbp+ppvObject]
0x180002416  mov     rax, [rcx]
0x180002419  lea     rdx, [rbp+arg_0]
0x18000241d  mov     rax, [rax+30h]
0x180002421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002426  test    eax, eax
0x180002428  jnz     short loc_180002498
0x18000242a  mov     ecx, [rbp+arg_0]
0x18000242d  sub     ecx, 1
0x180002430  jz      short loc_18000243B
0x180002432  cmp     ecx, 0Eh
0x180002435  jnz     short loc_180002412
0x180002437  dec     edi
0x180002439  jmp     short loc_180002412
0x18000243b  lea     r14d, [rdi+1]
0x18000243f  cmp     r14d, 2
0x180002443  jnz     short loc_18000245A
0x180002445  mov     r8d, r12d; unsigned int
0x180002448  mov     rdx, r13; unsigned __int16 **
0x18000244b  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x18000244f  call    ?ValidateAllowedCsp@@YAJPEAUIXmlReader@@PEAPEBGK@Z; ValidateAllowedCsp(IXmlReader *,ushort const * *,ulong)
0x180002454  mov     ebx, eax
0x180002456  test    eax, eax
0x180002458  js      short loc_1800024AC
0x18000245a  mov     rcx, [rbp+ppvObject]
0x18000245e  mov     rax, [rcx]
0x180002461  mov     rax, [rax+58h]
0x180002465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000246a  test    eax, eax
0x18000246c  js      short loc_180002491
0x18000246e  mov     ebx, edi
0x180002470  mov     edi, r14d
0x180002473  mov     rcx, [rbp+ppvObject]
0x180002477  mov     rax, [rcx]
0x18000247a  mov     rax, [rax+0A0h]
0x180002481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002486  xor     r14d, r14d
0x180002489  test    eax, eax
0x18000248b  jz      short loc_180002412
0x18000248d  mov     edi, ebx
0x18000248f  jmp     short loc_180002412
0x180002491  mov     ebx, 8000FFFFh
0x180002496  jmp     short loc_1800024AC
0x180002498  mov     rdx, r15; unsigned __int16 **
0x18000249b  mov     rcx, rsi; unsigned __int16 *
0x18000249e  call    ?DMProcessConfigXML_Remote@@YAJPEBGPEAPEAG@Z; DMProcessConfigXML_Remote(ushort const *,ushort * *)
0x1800024a3  mov     ebx, eax
0x1800024a5  jmp     short loc_1800024AC
0x1800024a7  mov     ebx, 8007000Eh
0x1800024ac  lea     rax, ??_7CMyXmlStream@@6B@; const CMyXmlStream::`vftable'
0x1800024b3  mov     [rbp+var_20], rax
0x1800024b7  mov     rcx, [rbp+hMem]; hMem
0x1800024bb  test    rcx, rcx
0x1800024be  jz      short loc_1800024C7
0x1800024c0  call    cs:__imp_LocalFree
0x1800024c6  nop
0x1800024c7  mov     rcx, [rbp+ppvObject]
0x1800024cb  test    rcx, rcx
0x1800024ce  jz      short loc_1800024DD
0x1800024d0  mov     rax, [rcx]
0x1800024d3  mov     rax, [rax+10h]
0x1800024d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024dc  nop
0x1800024dd  mov     eax, ebx
0x1800024df  add     rsp, 48h
0x1800024e3  pop     r15
0x1800024e5  pop     r14
0x1800024e7  pop     r13
0x1800024e9  pop     r12
0x1800024eb  pop     rdi
0x1800024ec  pop     rsi
0x1800024ed  pop     rbx
0x1800024ee  pop     rbp
0x1800024ef  retn
```
