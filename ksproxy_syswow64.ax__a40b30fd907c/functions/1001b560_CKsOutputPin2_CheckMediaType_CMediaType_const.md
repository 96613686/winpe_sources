# CKsOutputPin2::CheckMediaType(CMediaType const *)

- ea: `0x1001b560`
- end: `0x1001b5fe`
- name: `?CheckMediaType@CKsOutputPin2@@UAEJPBVCMediaType@@@Z`
- size: `158`
- prototype: `int __thiscall(CKsOutputPin2 *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x1000af81`
- `0x1001b560`
- `0x1001e1f8`
- `0x1001ed70`
- `0x1001f64d`
- `0x100302a7`
- `0x100302c4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1001b5ef`
- `ole32!CoTaskMemFree` at `0x1001b5ef`

## pseudocode

```c
int __thiscall CKsOutputPin2::CheckMediaType(CKsOutputPin2 *this, struct IUnknown *a2)
{
  void *v3; // ebx
  int MediaTypeArrays; // edi
  int v5; // eax
  const struct _AMMediaType *v7; // [esp+0h] [ebp-18h]
  void **v8; // [esp+0h] [ebp-18h]
  struct _AMMediaType *v9; // [esp+0h] [ebp-18h]
  struct CMediaType *v10; // [esp+4h] [ebp-14h]
  char v11; // [esp+Ch] [ebp-Ch] BYREF
  LPVOID pv; // [esp+14h] [ebp-4h]

  v3 = 0;
  pv = 0;
  if ( *((_DWORD *)this + 202) || (MediaTypeArrays = CKsOutputPin2::CreateMediaTypeArrays(this), MediaTypeArrays >= 0) )
  {
    if ( *((_DWORD *)this + 192) )
    {
      if ( !CreateMediaType(v7) )
        return -2147024882;
      v5 = InitializeKsDataFormat((const struct _AMMediaType *)&v11, v8, &v10->majortype.Data1);
      v3 = pv;
      MediaTypeArrays = v5;
      if ( v5 >= 0 )
        MediaTypeArrays = CKsOutputPin2::CheckPluginMediaType(this, (union KSDATAFORMAT *)pv);
      DeleteMediaType(v9);
    }
    else
    {
      MediaTypeArrays = CKsProxy::CheckMediaType(
                          this != 0 ? (unsigned int)this + 12 : 0,
                          *((_DWORD *)this + 10),
                          *((CKsProxy **)this + 97),
                          a2,
                          (unsigned int)v7,
                          v10);
    }
    if ( v3 )
      CoTaskMemFree(v3);
  }
  return MediaTypeArrays;
}

```

## disassembly

```asm
0x1001b560  mov     edi, edi
0x1001b562  push    ebp
0x1001b563  mov     ebp, esp
0x1001b565  sub     esp, 0Ch
0x1001b568  push    ebx
0x1001b569  push    esi; struct CMediaType *
0x1001b56a  mov     esi, ecx
0x1001b56c  xor     ebx, ebx
0x1001b56e  push    edi; unsigned int
0x1001b56f  mov     [ebp+pv], ebx
0x1001b572  cmp     [esi+328h], ebx
0x1001b578  jnz     short loc_1001B585
0x1001b57a  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QAEJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x1001b57f  mov     edi, eax
0x1001b581  test    edi, edi
0x1001b583  js      short loc_1001B5F5
0x1001b585  cmp     [esi+300h], ebx
0x1001b58b  jz      short loc_1001B5CE
0x1001b58d  mov     ecx, [ebp+arg_0]
0x1001b590  call    ?CreateMediaType@@YGPAU_AMMediaType@@PBU1@@Z; CreateMediaType(_AMMediaType const *)
0x1001b595  mov     [ebp+var_8], eax
0x1001b598  test    eax, eax
0x1001b59a  jnz     short loc_1001B5A3
0x1001b59c  mov     edi, 8007000Eh
0x1001b5a1  jmp     short loc_1001B5F5
0x1001b5a3  lea     ecx, [ebp+var_C]
0x1001b5a6  push    ecx; const struct _AMMediaType *
0x1001b5a7  lea     edx, [ebp+pv]
0x1001b5aa  mov     ecx, eax
0x1001b5ac  call    ?InitializeKsDataFormat@@YGJPBU_AMMediaType@@PAPAXPAK@Z; InitializeKsDataFormat(_AMMediaType const *,void * *,ulong *)
0x1001b5b1  mov     ebx, [ebp+pv]
0x1001b5b4  mov     edi, eax
0x1001b5b6  test    edi, edi
0x1001b5b8  js      short loc_1001B5C4
0x1001b5ba  push    ebx; union KSDATAFORMAT *
0x1001b5bb  mov     ecx, esi; this
0x1001b5bd  call    ?CheckPluginMediaType@CKsOutputPin2@@QAEJPATKSDATAFORMAT@@@Z; CKsOutputPin2::CheckPluginMediaType(KSDATAFORMAT *)
0x1001b5c2  mov     edi, eax
0x1001b5c4  mov     ecx, [ebp+var_8]
0x1001b5c7  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001b5cc  jmp     short loc_1001B5EA
0x1001b5ce  push    [ebp+arg_0]; struct IUnknown *
0x1001b5d1  mov     ecx, [esi+28h]
0x1001b5d4  lea     edx, [esi+0Ch]
0x1001b5d7  push    dword ptr [esi+184h]; this
0x1001b5dd  neg     esi
0x1001b5df  sbb     esi, esi
0x1001b5e1  and     edx, esi
0x1001b5e3  call    ?CheckMediaType@CKsProxy@@QAGJPAUIUnknown@@KPBVCMediaType@@@Z; CKsProxy::CheckMediaType(IUnknown *,ulong,CMediaType const *)
0x1001b5e8  mov     edi, eax
0x1001b5ea  test    ebx, ebx
0x1001b5ec  jz      short loc_1001B5F5
0x1001b5ee  push    ebx; pv
0x1001b5ef  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001b5f5  mov     eax, edi
0x1001b5f7  pop     edi
0x1001b5f8  pop     esi
0x1001b5f9  pop     ebx
0x1001b5fa  leave
0x1001b5fb  retn    4
```
