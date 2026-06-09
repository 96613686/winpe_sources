# s_SSCatDBDeleteCatalog

- ea: `0x18001c9e0`
- end: `0x18001ca97`
- name: `s_SSCatDBDeleteCatalog`
- size: `183`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007fb0`
- `0x18000938c`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000a710`
- `0x180019314`
- `0x180019a08`
- `0x18001ad58`
- `0x18001c9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca59`

## pseudocode

```c
__int64 __fastcall s_SSCatDBDeleteCatalog(RPC_BINDING_HANDLE BindingHandle, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int i; // edi
  unsigned int v7; // eax
  unsigned int Error; // ebx
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  unsigned int v11; // r8d
  int v13; // [rsp+28h] [rbp-30h]

  I_CatDBEventSubsystemAndCatalogTemplate(a2, a3, CAPI2_CATDB_REMOVE_CATALOG_START_EVENT);
  if ( BindingHandle && (unsigned int)_CatDBDVerifyGUIDString(a2) )
  {
    for ( i = 0; ; i = 1 )
    {
      v7 = _CatDBDeleteCatalog(BindingHandle, a2, a3);
      Error = v7;
      if ( !v7 || i || !(unsigned int)_CatDBErrorIsCorruption(v7) )
        break;
      if ( !(unsigned int)_CatDBRecoverFromCorruption() )
      {
        v11 = 3415;
        goto LABEL_11;
      }
    }
  }
  else
  {
    SetLastError(0xA0u);
    v11 = 3401;
LABEL_11:
    ErrLog_LogError(v10, v9, v11, 0, 0, v13);
    Error = _CatDBGetNonzeroLastError();
  }
  I_CatDBEventStatusTemplate(Error, CAPI2_CATDB_REMOVE_CATALOG_STOP_EVENT);
  return Error;
}

```

## disassembly

```asm
0x18001c9e0  push    rbx
0x18001c9e2  push    rbp
0x18001c9e3  push    rsi
0x18001c9e4  push    rdi
0x18001c9e5  push    r14
0x18001c9e7  sub     rsp, 30h
0x18001c9eb  mov     rbp, r8
0x18001c9ee  mov     rsi, rdx
0x18001c9f1  mov     r14, rcx
0x18001c9f4  lea     r8, CAPI2_CATDB_REMOVE_CATALOG_START_EVENT
0x18001c9fb  mov     rdx, rbp
0x18001c9fe  mov     rcx, rsi
0x18001ca01  call    I_CatDBEventSubsystemAndCatalogTemplate
0x18001ca06  test    r14, r14
0x18001ca09  jz      short loc_18001CA54
0x18001ca0b  mov     rcx, rsi; unsigned __int16 *
0x18001ca0e  call    ?_CatDBDVerifyGUIDString@@YAHPEBG@Z; _CatDBDVerifyGUIDString(ushort const *)
0x18001ca13  test    eax, eax
0x18001ca15  jz      short loc_18001CA54
0x18001ca17  xor     edi, edi
0x18001ca19  mov     r8, rbp; unsigned __int16 *
0x18001ca1c  mov     rdx, rsi; unsigned __int16 *
0x18001ca1f  mov     rcx, r14; BindingHandle
0x18001ca22  call    ?_CatDBDeleteCatalog@@YAKPEAXPEBG1@Z; _CatDBDeleteCatalog(void *,ushort const *,ushort const *)
0x18001ca27  mov     ebx, eax
0x18001ca29  test    eax, eax
0x18001ca2b  jz      short loc_18001CA7C
0x18001ca2d  test    edi, edi
0x18001ca2f  jnz     short loc_18001CA7C
0x18001ca31  mov     ecx, eax; unsigned int
0x18001ca33  call    ?_CatDBErrorIsCorruption@@YAHK@Z; _CatDBErrorIsCorruption(ulong)
0x18001ca38  test    eax, eax
0x18001ca3a  jz      short loc_18001CA7C
0x18001ca3c  call    ?_CatDBRecoverFromCorruption@@YAHXZ; _CatDBRecoverFromCorruption(void)
0x18001ca41  test    eax, eax
0x18001ca43  jz      short loc_18001CA4C
0x18001ca45  mov     edi, 1
0x18001ca4a  jmp     short loc_18001CA19
0x18001ca4c  mov     r8d, 0D57h
0x18001ca52  jmp     short loc_18001CA65
0x18001ca54  mov     ecx, 0A0h; dwErrCode
0x18001ca59  call    cs:__imp_SetLastError
0x18001ca5f  mov     r8d, 0D49h; unsigned int
0x18001ca65  xor     r9d, r9d; unsigned int
0x18001ca68  mov     [rsp+58h+var_38], 0; int
0x18001ca70  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001ca75  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001ca7a  mov     ebx, eax
0x18001ca7c  lea     rdx, CAPI2_CATDB_REMOVE_CATALOG_STOP_EVENT
0x18001ca83  mov     ecx, ebx
0x18001ca85  call    I_CatDBEventStatusTemplate
0x18001ca8a  mov     eax, ebx
0x18001ca8c  add     rsp, 30h
0x18001ca90  pop     r14
0x18001ca92  pop     rdi
0x18001ca93  pop     rsi
0x18001ca94  pop     rbp
0x18001ca95  pop     rbx
0x18001ca96  retn
```
