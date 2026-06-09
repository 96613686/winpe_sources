# DllRegisterServer

- ea: `0x18000fb80`
- end: `0x18000fc3b`
- name: `DllRegisterServer`
- size: `187`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e2b0`
- `0x18000f5c4`
- `0x18000fb80`
- `0x18000ffb4`

## import_xrefs

- `msdmo!DMORegister` at `0x18000fbf3`
- `msdmo!DMORegister` at `0x18000fbf3`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  DMO_PARTIAL_MEDIATYPE *pInTypes; // rsi
  __int64 v4; // rdx
  __int64 v5; // rcx
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rax
  DMO_PARTIAL_MEDIATYPE *v7; // rdi
  int v8; // ebx
  DMO_PARTIAL_MEDIATYPE *v9; // rcx

  result = CreateCLSIDRegKey();
  if ( result >= 0 )
  {
    pInTypes = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v2, v1, &off_18001B010);
    pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v5, v4, &off_18001B068);
    v7 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
    if ( pInTypes )
    {
      if ( pOutTypes )
      {
        v8 = DMORegister(
               L"MP3 Decoder DMO",
               &CLSID_CMP3DecMediaObject,
               &DMOCATEGORY_AUDIO_DECODER,
               0,
               1u,
               pInTypes,
               1u,
               pOutTypes);
        operator delete(pInTypes);
        operator delete(v7);
        result = 0;
        if ( v8 < 0 )
          return v8;
        return result;
      }
      v9 = pInTypes;
    }
    else
    {
      if ( !pOutTypes )
        return -2147024882;
      v9 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
    }
    operator delete(v9);
    return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x18000fb80  mov     [rsp+arg_0], rbx
0x18000fb85  mov     [rsp+arg_8], rsi
0x18000fb8a  push    rdi
0x18000fb8b  sub     rsp, 40h
0x18000fb8f  call    CreateCLSIDRegKey
0x18000fb94  test    eax, eax
0x18000fb96  js      loc_18000FC2B
0x18000fb9c  lea     r8, off_18001B010
0x18000fba3  call    GuidPairArray
0x18000fba8  lea     r8, off_18001B068
0x18000fbaf  mov     rsi, rax
0x18000fbb2  call    GuidPairArray
0x18000fbb7  mov     rdi, rax
0x18000fbba  test    rsi, rsi
0x18000fbbd  jz      short loc_18000FC19
0x18000fbbf  test    rax, rax
0x18000fbc2  jz      short loc_18000FC14
0x18000fbc4  mov     [rsp+48h+pOutTypes], rax; pOutTypes
0x18000fbc9  lea     r8, DMOCATEGORY_AUDIO_DECODER; guidCategory
0x18000fbd0  mov     eax, 1
0x18000fbd5  lea     rdx, CLSID_CMP3DecMediaObject; clsidDMO
0x18000fbdc  mov     [rsp+48h+cOutTypes], eax; cOutTypes
0x18000fbe0  lea     rcx, szName; "MP3 Decoder DMO"
0x18000fbe7  mov     [rsp+48h+pInTypes], rsi; pInTypes
0x18000fbec  xor     r9d, r9d; dwFlags
0x18000fbef  mov     [rsp+48h+cInTypes], eax; cInTypes
0x18000fbf3  call    cs:__imp_DMORegister
0x18000fbf9  mov     rcx, rsi; void *
0x18000fbfc  mov     ebx, eax
0x18000fbfe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc03  mov     rcx, rdi; void *
0x18000fc06  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc0b  xor     eax, eax
0x18000fc0d  test    ebx, ebx
0x18000fc0f  cmovs   eax, ebx
0x18000fc12  jmp     short loc_18000FC2B
0x18000fc14  mov     rcx, rsi
0x18000fc17  jmp     short loc_18000FC21
0x18000fc19  test    rdi, rdi
0x18000fc1c  jz      short loc_18000FC26
0x18000fc1e  mov     rcx, rdi; void *
0x18000fc21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc26  mov     eax, 8007000Eh
0x18000fc2b  mov     rbx, [rsp+48h+arg_0]
0x18000fc30  mov     rsi, [rsp+48h+arg_8]
0x18000fc35  add     rsp, 40h
0x18000fc39  pop     rdi
0x18000fc3a  retn
```
