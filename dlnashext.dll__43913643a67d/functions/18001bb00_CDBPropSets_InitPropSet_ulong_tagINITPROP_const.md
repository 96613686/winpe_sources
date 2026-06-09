# CDBPropSets::InitPropSet(ulong,tagINITPROP const *)

- ea: `0x18001bb00`
- end: `0x18001bb5e`
- name: `?InitPropSet@CDBPropSets@@QEAAJKPEBUtagINITPROP@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CDBPropSets *__hidden this, unsigned int, const struct tagINITPROP *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a4d0`
- `0x18001b460`
- `0x18001c12c`

## callees

- `0x180001710`
- `0x18001ad5c`
- `0x18001bb00`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001bb20`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001bb20`

## pseudocode

```c
HRESULT __fastcall CDBPropSets::InitPropSet(void **this, unsigned int a2, const struct _GUID *a3)
{
  HRESULT result; // eax
  __int64 i; // rbx
  unsigned int v8; // [rsp+20h] [rbp-38h]

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(this);
  result = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this);
  if ( result >= 0 )
  {
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      if ( result < 0 )
        break;
      result = CDBPropSets::AddProperty(
                 (CDBPropSets *)this,
                 &a3[3 * i],
                 a3[3 * i + 1].Data1,
                 (const struct tagVARIANT *)a3[3 * i + 1].Data4,
                 v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001bb00  push    rbx
0x18001bb02  push    rbp
0x18001bb03  push    rsi
0x18001bb04  push    rdi
0x18001bb05  sub     rsp, 38h
0x18001bb09  mov     rbp, r8
0x18001bb0c  mov     edi, edx
0x18001bb0e  mov     rsi, rcx
0x18001bb11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001bb16  mov     rdx, rsi; ppv
0x18001bb19  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001bb20  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001bb26  test    eax, eax
0x18001bb28  js      short loc_18001BB55
0x18001bb2a  xor     ebx, ebx
0x18001bb2c  test    edi, edi
0x18001bb2e  jz      short loc_18001BB55
0x18001bb30  test    eax, eax
0x18001bb32  js      short loc_18001BB55
0x18001bb34  lea     rdx, [rbx+rbx*2]
0x18001bb38  mov     rcx, rsi; this
0x18001bb3b  shl     rdx, 4
0x18001bb3f  add     rdx, rbp; struct _GUID *
0x18001bb42  mov     r8d, [rdx+10h]; unsigned int
0x18001bb46  lea     r9, [rdx+18h]; struct tagVARIANT *
0x18001bb4a  call    ?AddProperty@CDBPropSets@@QEAAJAEBU_GUID@@KAEBUtagVARIANT@@K@Z; CDBPropSets::AddProperty(_GUID const &,ulong,tagVARIANT const &,ulong)
0x18001bb4f  inc     ebx
0x18001bb51  cmp     ebx, edi
0x18001bb53  jb      short loc_18001BB30
0x18001bb55  add     rsp, 38h
0x18001bb59  pop     rdi
0x18001bb5a  pop     rsi
0x18001bb5b  pop     rbp
0x18001bb5c  pop     rbx
0x18001bb5d  retn
```
