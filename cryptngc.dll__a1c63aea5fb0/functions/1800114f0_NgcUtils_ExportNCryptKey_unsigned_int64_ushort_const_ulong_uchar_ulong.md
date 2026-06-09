# NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)

- ea: `0x1800114f0`
- end: `0x180011658`
- name: `?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z`
- size: `360`
- prototype: `__int64 __usercall@<rax>(NCRYPT_KEY_HANDLE hKey@<rcx>, LPCWSTR pszBlobType@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002adc4`
- `0x180039c18`

## callees

- `0x180006538`
- `0x1800114f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001164b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001164b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011551`
- `ncrypt!NCryptExportKey` at `0x180011534`
- `ncrypt!NCryptExportKey` at `0x180011593`
- `ncrypt!NCryptExportKey` at `0x180011534`
- `ncrypt!NCryptExportKey` at `0x180011593`

## string_xrefs

- `0x1800115d4`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180011617`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180011634`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::ExportNCryptKey(
        NCRYPT_KEY_HANDLE hKey,
        LPCWSTR pszBlobType,
        const unsigned __int16 *a3,
        BYTE **a4,
        unsigned __int8 **a5)
{
  SECURITY_STATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  BYTE *v11; // rax
  BYTE *v12; // rbx
  BYTE *i; // rcx
  SECURITY_STATUS v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  unsigned __int8 **v17; // rcx
  int pbOutput; // [rsp+20h] [rbp-38h]
  int pbOutputa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SIZE_T uBytes; // [rsp+70h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  v8 = NCryptExportKey(hKey, 0, pszBlobType, 0, 0, 0, (DWORD *)&uBytes, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x222,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v8,
      pbOutput);
    return v9;
  }
  else
  {
    v10 = (unsigned int)uBytes;
    v11 = (BYTE *)LocalAlloc(0, (unsigned int)uBytes);
    v12 = v11;
    if ( v11 )
    {
      for ( i = &v11[v10]; v11 != i; ++v11 )
        *v11 = 0;
      v14 = NCryptExportKey(hKey, 0, pszBlobType, 0, v12, uBytes, (DWORD *)&uBytes, 0);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
          (const char *)(unsigned int)v14,
          pbOutputa);
        LocalFree(v12);
        return v15;
      }
      else
      {
        v16 = uBytes;
        v17 = a5;
        *a4 = v12;
        *(_DWORD *)v17 = v16;
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x225,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)0x8007000ELL,
        pbOutput);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x1800114f0  mov     r11, rsp
0x1800114f3  mov     [r11+10h], rbx
0x1800114f7  mov     [r11+20h], rbp
0x1800114fb  mov     [r11+18h], r8d
0x1800114ff  push    rsi
0x180011500  push    r14
0x180011502  push    r15
0x180011504  sub     rsp, 40h
0x180011508  xor     r15d, r15d
0x18001150b  lea     rax, [r11+18h]
0x18001150f  mov     [r11-20h], r15d
0x180011513  mov     rsi, r9
0x180011516  mov     [r11-28h], rax
0x18001151a  mov     rbp, rdx
0x18001151d  mov     r8, rdx; pszBlobType
0x180011520  mov     [r11-30h], r15d
0x180011524  xor     r9d, r9d; pParameterList
0x180011527  mov     [r11-38h], r15
0x18001152b  xor     edx, edx; hExportKey
0x18001152d  mov     [r11+18h], r15d
0x180011531  mov     r14, rcx
0x180011534  call    cs:__imp_NCryptExportKey
0x18001153a  mov     ebx, eax
0x18001153c  test    eax, eax
0x18001153e  js      loc_180011612
0x180011544  mov     [rsp+58h+arg_0], rdi
0x180011549  xor     ecx, ecx; uFlags
0x18001154b  mov     edi, dword ptr [rsp+58h+uBytes]
0x18001154f  mov     edx, edi; uBytes
0x180011551  call    cs:__imp_LocalAlloc
0x180011557  mov     rbx, rax
0x18001155a  test    rax, rax
0x18001155d  jz      short loc_1800115CF
0x18001155f  lea     rcx, [rdi+rax]
0x180011563  cmp     rax, rcx
0x180011566  jnz     loc_180011600
0x18001156c  mov     eax, dword ptr [rsp+58h+uBytes]
0x180011570  lea     rcx, [rsp+58h+uBytes]
0x180011575  mov     [rsp+58h+dwFlags], r15d; dwFlags
0x18001157a  xor     r9d, r9d; pParameterList
0x18001157d  mov     [rsp+58h+pcbResult], rcx; pcbResult
0x180011582  mov     r8, rbp; pszBlobType
0x180011585  mov     [rsp+58h+cbOutput], eax; cbOutput
0x180011589  mov     rcx, r14; hKey
0x18001158c  xor     edx, edx; hExportKey
0x18001158e  mov     [rsp+58h+pbOutput], rbx; int
0x180011593  call    cs:__imp_NCryptExportKey
0x180011599  mov     edi, eax
0x18001159b  test    eax, eax
0x18001159d  js      loc_18001162F
0x1800115a3  mov     eax, dword ptr [rsp+58h+uBytes]
0x1800115a7  mov     rcx, [rsp+58h+arg_20]
0x1800115af  mov     [rsi], rbx
0x1800115b2  mov     [rcx], eax
0x1800115b4  xor     eax, eax
0x1800115b6  mov     rdi, [rsp+58h+arg_0]
0x1800115bb  mov     rbx, [rsp+58h+arg_8]
0x1800115c0  mov     rbp, [rsp+58h+arg_18]
0x1800115c5  add     rsp, 40h
0x1800115c9  pop     r15
0x1800115cb  pop     r14
0x1800115cd  pop     rsi
0x1800115ce  retn
0x1800115cf  mov     rcx, [rsp+58h]; this
0x1800115d4  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800115db  mov     r9d, 8007000Eh; char *
0x1800115e1  mov     edx, 225h; void *
0x1800115e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115eb  mov     eax, 8007000Eh
0x1800115f0  jmp     short loc_1800115B6
0x180011600  xor     edx, edx
0x180011602  mov     [rax], dl
0x180011604  inc     rax
0x180011607  cmp     rax, rcx
0x18001160a  jz      loc_18001156C
0x180011610  jmp     short loc_180011600
0x180011612  mov     rcx, [rsp+58h]; this
0x180011617  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001161e  mov     r9d, ebx; char *
0x180011621  mov     edx, 222h; void *
0x180011626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001162b  mov     eax, ebx
0x18001162d  jmp     short loc_1800115BB
0x18001162f  mov     rcx, [rsp+58h]; this
0x180011634  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001163b  mov     r9d, edi; char *
0x18001163e  mov     edx, 22Fh; void *
0x180011643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011648  mov     rcx, rbx; hMem
0x18001164b  call    cs:__imp_LocalFree
0x180011651  mov     eax, edi
0x180011653  jmp     loc_1800115B6
```
