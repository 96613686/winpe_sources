# CCDSResultsParser::ParseCodec(ushort const *,IPropertyStore *)

- ea: `0x18002dec0`
- end: `0x18002df7a`
- name: `?ParseCodec@CCDSResultsParser@@SAJPEBGPEAUIPropertyStore@@@Z`
- size: `186`
- prototype: `static int(const unsigned __int16 *, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180011930`
- `0x18002c8fc`
- `0x18002dec0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002deec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002deec`

## pseudocode

```c
HRESULT __fastcall CCDSResultsParser::ParseCodec(const unsigned __int16 *a1, struct IPropertyStore *a2)
{
  HRESULT result; // eax
  const PROPERTYKEY *v5; // rdx
  int v6; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v7[3]; // [rsp+28h] [rbp-40h] BYREF
  CLSID pclsid; // [rsp+40h] [rbp-28h] BYREF

  pclsid = 0;
  result = CLSIDFromString(a1, &pclsid);
  if ( result >= 0 )
  {
    v6 = 0;
    result = CCDSResultsParser::GetMediaTypeForItem(a2, (enum _CDS_MEDIA_TYPE *)&v6);
    if ( result >= 0 )
    {
      v7[0] = 31;
      v7[2] = 0;
      v7[1] = a1;
      if ( v6 == 2 )
      {
        v5 = &PKEY_Audio_Format;
      }
      else
      {
        if ( v6 != 4 )
          return result;
        v5 = &PKEY_Video_Compression;
      }
      return ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, _QWORD *))a2->lpVtbl->SetValue)(
               a2,
               v5,
               v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002dec0  mov     [rsp+arg_10], rbx
0x18002dec5  push    rdi
0x18002dec6  sub     rsp, 60h
0x18002deca  mov     rax, cs:__security_cookie
0x18002ded1  xor     rax, rsp
0x18002ded4  mov     [rsp+68h+var_18], rax
0x18002ded9  mov     rbx, rdx
0x18002dedc  xorps   xmm0, xmm0
0x18002dedf  lea     rdx, [rsp+68h+pclsid]; pclsid
0x18002dee4  mov     rdi, rcx
0x18002dee7  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x18002deec  call    cs:__imp_CLSIDFromString
0x18002def2  test    eax, eax
0x18002def4  js      short loc_18002DF5F
0x18002def6  lea     rdx, [rsp+68h+var_48]; enum _CDS_MEDIA_TYPE *
0x18002defb  mov     [rsp+68h+var_48], 0
0x18002df03  mov     rcx, rbx; struct IPropertyStore *
0x18002df06  call    ?GetMediaTypeForItem@CCDSResultsParser@@SAJPEAUIPropertyStore@@PEAW4_CDS_MEDIA_TYPE@@@Z; CCDSResultsParser::GetMediaTypeForItem(IPropertyStore *,_CDS_MEDIA_TYPE *)
0x18002df0b  test    eax, eax
0x18002df0d  js      short loc_18002DF5F
0x18002df0f  xor     ecx, ecx
0x18002df11  xorps   xmm0, xmm0
0x18002df14  cmp     [rsp+68h+var_48], 2
0x18002df19  movups  [rsp+68h+var_40], xmm0
0x18002df1e  mov     [rsp+68h+var_30], rcx
0x18002df23  mov     ecx, 1Fh
0x18002df28  mov     word ptr [rsp+68h+var_40], cx
0x18002df2d  mov     qword ptr [rsp+68h+var_40+8], rdi
0x18002df32  jnz     short loc_18002DF3D
0x18002df34  lea     rdx, PKEY_Audio_Format
0x18002df3b  jmp     short loc_18002DF4B
0x18002df3d  cmp     [rsp+68h+var_48], 4
0x18002df42  jnz     short loc_18002DF5F
0x18002df44  lea     rdx, PKEY_Video_Compression
0x18002df4b  mov     rax, [rbx]
0x18002df4e  lea     r8, [rsp+68h+var_40]
0x18002df53  mov     rcx, rbx
0x18002df56  mov     rax, [rax+30h]
0x18002df5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df5f  mov     rcx, [rsp+68h+var_18]
0x18002df64  xor     rcx, rsp; StackCookie
0x18002df67  call    __security_check_cookie
0x18002df6c  mov     rbx, [rsp+68h+arg_10]
0x18002df74  add     rsp, 60h
0x18002df78  pop     rdi
0x18002df79  retn
```
