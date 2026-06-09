# CKsOutputPin2::CheckMediaType(CMediaType const *)

- ea: `0x18002da70`
- end: `0x18002db44`
- name: `?CheckMediaType@CKsOutputPin2@@UEAAJPEBVCMediaType@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CKsOutputPin2 *this, const struct _AMMediaType *rclsid)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180020f2c`
- `0x18002da70`
- `0x18002db4c`
- `0x18002dd70`
- `0x180038758`
- `0x18003e1cc`
- `0x18003e22c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002db28`
- `ole32!CoTaskMemFree` at `0x18002db28`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::CheckMediaType(CKsOutputPin2 *this, const struct _AMMediaType *rclsid)
{
  void *v2; // rsi
  int MediaTypeArrays; // ebx
  const struct _AMMediaType *MediaType; // rax
  struct _AMMediaType *v7; // rbp
  int v8; // eax
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v10 = 0;
  pv = 0;
  if ( *((_DWORD *)this + 300) || (MediaTypeArrays = CKsOutputPin2::CreateMediaTypeArrays(this), MediaTypeArrays >= 0) )
  {
    if ( *((_DWORD *)this + 286) )
    {
      MediaType = CreateMediaType(rclsid);
      v7 = MediaType;
      if ( !MediaType )
        return (unsigned int)-2147024882;
      v8 = InitializeKsDataFormat(MediaType, &pv, &v10);
      v2 = pv;
      MediaTypeArrays = v8;
      if ( v8 >= 0 )
        MediaTypeArrays = CKsOutputPin2::CheckPluginMediaType(this, (union KSDATAFORMAT *)pv);
      DeleteMediaType(v7);
    }
    else
    {
      MediaTypeArrays = CKsProxy::CheckMediaType(
                          *((CKsProxy **)this + 10),
                          (LPUNKNOWN)(((unsigned __int64)this + 24)
                                    & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                          *((_DWORD *)this + 146),
                          rclsid);
    }
    if ( v2 )
      CoTaskMemFree(v2);
  }
  return (unsigned int)MediaTypeArrays;
}

```

## disassembly

```asm
0x18002da70  mov     [rsp+arg_8], rbx
0x18002da75  push    rbp
0x18002da76  push    rsi
0x18002da77  push    rdi
0x18002da78  sub     rsp, 20h
0x18002da7c  xor     esi, esi
0x18002da7e  mov     [rsp+38h+arg_0], 0
0x18002da86  mov     rbp, rdx
0x18002da89  mov     rdi, rcx
0x18002da8c  mov     [rsp+38h+pv], rsi
0x18002da91  cmp     [rcx+4B0h], esi
0x18002da97  jnz     short loc_18002DAA8
0x18002da99  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QEAAJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x18002da9e  mov     ebx, eax
0x18002daa0  test    eax, eax
0x18002daa2  js      loc_18002DB34
0x18002daa8  cmp     [rdi+478h], esi
0x18002daae  jz      short loc_18002DAFB
0x18002dab0  mov     rcx, rbp; const struct _AMMediaType *
0x18002dab3  call    ?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z; CreateMediaType(_AMMediaType const *)
0x18002dab8  mov     rbp, rax
0x18002dabb  test    rax, rax
0x18002dabe  jnz     short loc_18002DAC7
0x18002dac0  mov     ebx, 8007000Eh
0x18002dac5  jmp     short loc_18002DB34
0x18002dac7  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18002dacc  mov     rcx, rbp; const struct _AMMediaType *
0x18002dacf  lea     rdx, [rsp+38h+pv]; void **
0x18002dad4  call    ?InitializeKsDataFormat@@YAJPEBU_AMMediaType@@PEAPEAXPEAK@Z; InitializeKsDataFormat(_AMMediaType const *,void * *,ulong *)
0x18002dad9  mov     rsi, [rsp+38h+pv]
0x18002dade  mov     ebx, eax
0x18002dae0  test    eax, eax
0x18002dae2  js      short loc_18002DAF1
0x18002dae4  mov     rdx, rsi; union KSDATAFORMAT *
0x18002dae7  mov     rcx, rdi; this
0x18002daea  call    ?CheckPluginMediaType@CKsOutputPin2@@QEAAJPEATKSDATAFORMAT@@@Z; CKsOutputPin2::CheckPluginMediaType(KSDATAFORMAT *)
0x18002daef  mov     ebx, eax
0x18002daf1  mov     rcx, rbp; pv
0x18002daf4  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x18002daf9  jmp     short loc_18002DB20
0x18002dafb  mov     rcx, [rdi+50h]; this
0x18002daff  lea     r8, [rdi+18h]
0x18002db03  mov     rax, rdi
0x18002db06  mov     r9, rbp; rclsid
0x18002db09  neg     rax
0x18002db0c  sbb     rdx, rdx
0x18002db0f  and     rdx, r8; pUnkOuter
0x18002db12  mov     r8d, [rdi+248h]; unsigned int
0x18002db19  call    ?CheckMediaType@CKsProxy@@QEAAJPEAUIUnknown@@KPEBVCMediaType@@@Z; CKsProxy::CheckMediaType(IUnknown *,ulong,CMediaType const *)
0x18002db1e  mov     ebx, eax
0x18002db20  test    rsi, rsi
0x18002db23  jz      short loc_18002DB34
0x18002db25  mov     rcx, rsi; pv
0x18002db28  call    cs:__imp_CoTaskMemFree
0x18002db2f  nop     dword ptr [rax+rax+00h]
0x18002db34  mov     eax, ebx
0x18002db36  mov     rbx, [rsp+38h+arg_8]
0x18002db3b  add     rsp, 20h
0x18002db3f  pop     rdi
0x18002db40  pop     rsi
0x18002db41  pop     rbp
0x18002db42  retn
```
