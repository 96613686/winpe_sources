# NgcGetCryptoRegistryLocation

- ea: `0x180010b60`
- end: `0x180010c07`
- name: `NgcGetCryptoRegistryLocation`
- size: `167`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180010b60`
- `0x180015ca4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010be1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010be1`

## string_xrefs

- `0x180010b7f`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010bc6`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
__int64 __fastcall NgcGetCryptoRegistryLocation(unsigned __int16 *a1, HLOCAL *a2)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    hMem = 0;
    NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                          (NgcUtils *)L"NgcCrypto",
                                          L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Ngc",
                                          a1,
                                          &hMem);
    v5 = NgcStateSeparatedRegistryLocation;
    if ( NgcStateSeparatedRegistryLocation >= 0 )
    {
      *a2 = hMem;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x191,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
        v6);
      if ( hMem )
        LocalFree(hMem);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v6);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180010b60  mov     [rsp+arg_0], rbx
0x180010b65  push    rdi; int
0x180010b66  sub     rsp, 20h
0x180010b6a  mov     rbx, rdx
0x180010b6d  test    rdx, rdx
0x180010b70  jnz     short loc_180010B94
0x180010b72  mov     rcx, [rsp+28h]; this
0x180010b77  mov     ebx, 80004003h
0x180010b7c  mov     r9d, ebx; char *
0x180010b7f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010b86  mov     edx, 18Eh; void *
0x180010b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b90  mov     eax, ebx
0x180010b92  jmp     short loc_180010BFB
0x180010b94  mov     [rsp+28h+hMem], 0
0x180010b9d  lea     r9, [rsp+28h+hMem]; unsigned __int16 *
0x180010ba2  mov     r8, rcx; unsigned __int16 *
0x180010ba5  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x180010bac  lea     rcx, aNgccrypto; "NgcCrypto"
0x180010bb3  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180010bb8  mov     edi, eax
0x180010bba  test    eax, eax
0x180010bbc  jns     short loc_180010BEB
0x180010bbe  mov     rcx, [rsp+28h]; this
0x180010bc3  mov     r9d, eax; char *
0x180010bc6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010bcd  mov     edx, 191h; void *
0x180010bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bd7  mov     rcx, [rsp+28h+hMem]; hMem
0x180010bdc  test    rcx, rcx
0x180010bdf  jz      short loc_180010BE7
0x180010be1  call    cs:__imp_LocalFree
0x180010be7  mov     eax, edi
0x180010be9  jmp     short loc_180010BFB
0x180010beb  mov     rax, [rsp+28h+hMem]
0x180010bf0  mov     [rbx], rax
0x180010bf3  xor     eax, eax
0x180010bf5  jmp     short loc_180010BFB
0x180010bf7  mov     eax, dword ptr [rsp+28h+hMem]
0x180010bfb  mov     rbx, [rsp+28h+arg_0]
0x180010c00  add     rsp, 20h
0x180010c04  pop     rdi
0x180010c05  retn
```
