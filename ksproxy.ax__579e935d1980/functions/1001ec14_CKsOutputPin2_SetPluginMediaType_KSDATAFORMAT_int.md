# CKsOutputPin2::SetPluginMediaType(KSDATAFORMAT *,int)

- ea: `0x1001ec14`
- end: `0x1001ed6a`
- name: `?SetPluginMediaType@CKsOutputPin2@@QAEJPATKSDATAFORMAT@@H@Z`
- size: `342`
- prototype: `int __thiscall(CKsOutputPin2 *__hidden this, union KSDATAFORMAT *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1001b660`
- `0x1001c490`

## callees

- `0x1001b604`
- `0x1001e8ef`
- `0x1001ec14`
- `0x1002d510`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001ec34`
- `ole32!CoTaskMemAlloc` at `0x1001ec34`
- `ole32!CoTaskMemFree` at `0x1001ed01`
- `ole32!CoTaskMemFree` at `0x1001ed1c`
- `ole32!CoTaskMemFree` at `0x1001ed47`
- `ole32!CoTaskMemFree` at `0x1001ed5b`
- `ole32!CoTaskMemFree` at `0x1001ed01`
- `ole32!CoTaskMemFree` at `0x1001ed1c`
- `ole32!CoTaskMemFree` at `0x1001ed47`
- `ole32!CoTaskMemFree` at `0x1001ed5b`

## pseudocode

```c
int __thiscall CKsOutputPin2::SetPluginMediaType(CKsOutputPin2 *this, union KSDATAFORMAT *Src, int a3)
{
  void *v4; // eax
  void *v5; // edi
  int v6; // esi
  int (__thiscall *v7)(_DWORD, _DWORD, void *); // ecx
  int (__thiscall *v8)(_DWORD, _DWORD, LPVOID *); // ecx
  LPVOID v9; // edi
  union KSDATAFORMAT *v11; // [esp+0h] [ebp-1Ch]
  union KSDATAFORMAT **v12; // [esp+4h] [ebp-18h]
  LPVOID v13; // [esp+Ch] [ebp-10h]
  void *v14; // [esp+10h] [ebp-Ch]
  unsigned int v15; // [esp+14h] [ebp-8h] BYREF
  LPVOID pv; // [esp+18h] [ebp-4h] BYREF

  pv = 0;
  v15 = 0;
  v4 = CoTaskMemAlloc(Src->FormatSize);
  v5 = v4;
  v14 = v4;
  if ( !v4 )
  {
    v6 = -2147467259;
    goto LABEL_16;
  }
  memcpy(v4, Src, Src->FormatSize);
  v7 = *(int (__thiscall **)(_DWORD, _DWORD, void *))(**((_DWORD **)this + 190) + 28);
  v6 = v7(v7, *((_DWORD *)this + 190), v5);
  if ( v6 >= 0 )
  {
    v8 = *(int (__thiscall **)(_DWORD, _DWORD, LPVOID *))(**((_DWORD **)this + 190) + 36);
    v6 = v8(v8, *((_DWORD *)this + 190), &pv);
    if ( v6 >= 0 )
    {
      v9 = pv;
      v13 = pv;
      if ( !pv )
      {
        v6 = -2147467259;
LABEL_19:
        CoTaskMemFree(v14);
        return v6;
      }
      if ( a3 )
      {
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12))(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 10) + 108) + 12),
          *((_DWORD *)this + 10) + 108);
        v6 = IntersectKsFormat(v13, (unsigned int)&v15, v11, v12);
        if ( v6 < 0 )
          goto LABEL_16;
        v9 = (LPVOID)v15;
      }
      else
      {
        pv = 0;
      }
      if ( *((_DWORD *)this + 204) )
      {
        CoTaskMemFree(*((LPVOID *)this + 204));
        *((_DWORD *)this + 204) = 0;
      }
      if ( *((_DWORD *)this + 203) )
        CoTaskMemFree(*((LPVOID *)this + 203));
      *((_DWORD *)this + 204) = v9;
      *((_DWORD *)this + 203) = v14;
      GetExtendedStreamHeaderSize(v11, (unsigned int *)v12);
    }
  }
LABEL_16:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v6 < 0 )
    goto LABEL_19;
  return v6;
}

```

## disassembly

```asm
0x1001ec14  mov     edi, edi
0x1001ec16  push    ebp
0x1001ec17  mov     ebp, esp
0x1001ec19  sub     esp, 10h
0x1001ec1c  push    ebx
0x1001ec1d  push    esi; unsigned int *
0x1001ec1e  mov     esi, [ebp+Src]
0x1001ec21  mov     ebx, ecx
0x1001ec23  push    edi; union KSDATAFORMAT *
0x1001ec24  mov     [ebp+pv], 0
0x1001ec2b  mov     [ebp+var_8], 0
0x1001ec32  push    dword ptr [esi]; cb
0x1001ec34  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001ec3a  mov     edi, eax
0x1001ec3c  mov     [ebp+var_C], edi
0x1001ec3f  test    edi, edi
0x1001ec41  jnz     short loc_1001EC4D
0x1001ec43  mov     esi, 80004005h
0x1001ec48  jmp     loc_1001ED3E
0x1001ec4d  push    dword ptr [esi]; Size
0x1001ec4f  push    esi; Src
0x1001ec50  push    edi; void *
0x1001ec51  call    _memcpy
0x1001ec56  mov     ecx, [ebx+2F8h]
0x1001ec5c  add     esp, 0Ch
0x1001ec5f  mov     eax, [ecx]
0x1001ec61  push    edi
0x1001ec62  push    ecx
0x1001ec63  mov     esi, [eax+1Ch]
0x1001ec66  mov     ecx, esi; this
0x1001ec68  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001ec6e  call    esi
0x1001ec70  mov     esi, eax
0x1001ec72  test    esi, esi
0x1001ec74  js      loc_1001ED3E
0x1001ec7a  mov     ecx, [ebx+2F8h]
0x1001ec80  mov     eax, [ecx]
0x1001ec82  mov     esi, [eax+24h]
0x1001ec85  lea     eax, [ebp+pv]
0x1001ec88  push    eax
0x1001ec89  push    ecx
0x1001ec8a  mov     ecx, esi; this
0x1001ec8c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001ec92  call    esi
0x1001ec94  mov     esi, eax
0x1001ec96  test    esi, esi
0x1001ec98  js      loc_1001ED3E
0x1001ec9e  mov     edi, [ebp+pv]
0x1001eca1  mov     [ebp+var_10], edi
0x1001eca4  test    edi, edi
0x1001eca6  jnz     short loc_1001ECB2
0x1001eca8  mov     esi, 80004005h
0x1001ecad  jmp     loc_1001ED58
0x1001ecb2  cmp     [ebp+arg_4], 0
0x1001ecb6  jz      short loc_1001ECEF
0x1001ecb8  mov     eax, [ebx+28h]
0x1001ecbb  mov     edi, [ebx+184h]
0x1001ecc1  add     eax, 6Ch ; 'l'
0x1001ecc4  push    eax
0x1001ecc5  mov     ecx, [eax]
0x1001ecc7  mov     esi, [ecx+0Ch]
0x1001ecca  mov     ecx, esi; this
0x1001eccc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001ecd2  call    esi
0x1001ecd4  lea     ecx, [ebp+var_8]
0x1001ecd7  mov     edx, edi
0x1001ecd9  push    ecx; unsigned int
0x1001ecda  push    [ebp+var_10]; void *
0x1001ecdd  mov     ecx, eax
0x1001ecdf  call    ?IntersectKsFormat@@YGJPAXKPATKSDATAFORMAT@@PAPAT1@@Z; IntersectKsFormat(void *,ulong,KSDATAFORMAT *,KSDATAFORMAT * *)
0x1001ece4  mov     esi, eax
0x1001ece6  test    esi, esi
0x1001ece8  js      short loc_1001ED3E
0x1001ecea  mov     edi, [ebp+var_8]
0x1001eced  jmp     short loc_1001ECF6
0x1001ecef  mov     [ebp+pv], 0
0x1001ecf6  mov     eax, [ebx+330h]
0x1001ecfc  test    eax, eax
0x1001ecfe  jz      short loc_1001ED11
0x1001ed00  push    eax; pv
0x1001ed01  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ed07  mov     dword ptr [ebx+330h], 0
0x1001ed11  mov     eax, [ebx+32Ch]
0x1001ed17  test    eax, eax
0x1001ed19  jz      short loc_1001ED22
0x1001ed1b  push    eax; pv
0x1001ed1c  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ed22  mov     eax, [ebp+var_C]
0x1001ed25  lea     edx, [ebx+30Ch]
0x1001ed2b  mov     ecx, edi
0x1001ed2d  mov     [ebx+330h], edi
0x1001ed33  mov     [ebx+32Ch], eax
0x1001ed39  call    ?GetExtendedStreamHeaderSize@@YGJPATKSDATAFORMAT@@PAK@Z; GetExtendedStreamHeaderSize(KSDATAFORMAT *,ulong *)
0x1001ed3e  cmp     [ebp+pv], 0
0x1001ed42  jz      short loc_1001ED54
0x1001ed44  push    [ebp+pv]; pv
0x1001ed47  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ed4d  mov     [ebp+pv], 0
0x1001ed54  test    esi, esi
0x1001ed56  jns     short loc_1001ED61
0x1001ed58  push    [ebp+var_C]; pv
0x1001ed5b  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ed61  pop     edi
0x1001ed62  mov     eax, esi
0x1001ed64  pop     esi
0x1001ed65  pop     ebx
0x1001ed66  leave
0x1001ed67  retn    8
```
