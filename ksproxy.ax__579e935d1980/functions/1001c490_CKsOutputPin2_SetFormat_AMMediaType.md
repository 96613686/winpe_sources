# CKsOutputPin2::SetFormat(_AMMediaType *)

- ea: `0x1001c490`
- end: `0x1001c6aa`
- name: `?SetFormat@CKsOutputPin2@@UAGJPAU_AMMediaType@@@Z`
- size: `538`
- prototype: `int(CKsOutputPin2 *__hidden this, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10016a04`
- `0x1001a1c4`
- `0x1001c3e4`
- `0x1001c490`
- `0x1001e1f8`
- `0x1001ec14`
- `0x1001f64d`
- `0x1002d510`
- `0x100302a7`
- `0x1003aba0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1001c669`
- `ole32!CoTaskMemFree` at `0x1001c672`
- `ole32!CoTaskMemFree` at `0x1001c669`
- `ole32!CoTaskMemFree` at `0x1001c672`

## pseudocode

```c
int __thiscall CKsOutputPin2::SetFormat(void *ecx0, CKsOutputPin2 *this, struct _AMMediaType *a3)
{
  int v3; // ebx
  struct _AMMediaType *v4; // esi
  int MediaTypeArrays; // esi
  int (__thiscall *v6)(_DWORD, _DWORD, LPVOID, LPVOID *); // ecx
  bool v7; // zf
  char *v8; // edi
  int v9; // ecx
  void **v11; // [esp+0h] [ebp-34h]
  union KSDATAFORMAT *v12; // [esp+0h] [ebp-34h]
  unsigned int *v13; // [esp+4h] [ebp-30h]
  struct _AMMediaType **v14; // [esp+4h] [ebp-30h]
  int v15; // [esp+Ch] [ebp-28h] BYREF
  struct _AMMediaType *v16; // [esp+10h] [ebp-24h]
  LPVOID v17; // [esp+14h] [ebp-20h]
  LPVOID pv; // [esp+18h] [ebp-1Ch] BYREF
  int v19; // [esp+1Ch] [ebp-18h] BYREF
  _BYTE v20[16]; // [esp+20h] [ebp-14h] BYREF

  v3 = 0;
  v4 = a3;
  v16 = a3;
  v19 = 0;
  v15 = 0;
  v17 = 0;
  pv = 0;
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      SetFormat_Enter,
      ecx0,
      1,
      v20);
  if ( *(_DWORD *)(*((_DWORD *)this - 65) + 20) )
  {
    MediaTypeArrays = -2147220953;
    goto LABEL_30;
  }
  if ( !*((_DWORD *)this + 127) )
  {
    MediaTypeArrays = CKsOutputPin2::CreateMediaTypeArrays((CKsOutputPin2 *)((char *)this - 300));
    if ( MediaTypeArrays < 0 )
      goto LABEL_30;
    v4 = v16;
  }
  if ( v4 )
  {
    if ( *((_DWORD *)this + 117) )
    {
      MediaTypeArrays = InitializeKsDataFormat((const struct _AMMediaType *)&v15, v11, v13);
      if ( MediaTypeArrays < 0 )
        goto LABEL_30;
      v6 = *(int (__thiscall **)(_DWORD, _DWORD, LPVOID, LPVOID *))(**((_DWORD **)this + 115) + 24);
      MediaTypeArrays = v6(v6, *((_DWORD *)this + 115), v17, &pv);
      if ( MediaTypeArrays < 0 )
        goto LABEL_30;
      MediaTypeArrays = CKsOutputPin2::SetPluginMediaType(
                          (CKsOutputPin2 *)((char *)this - 300),
                          (union KSDATAFORMAT *)pv,
                          1);
      if ( MediaTypeArrays < 0 )
        goto LABEL_30;
      MediaTypeArrays = GetAmTypeFromKsFormat(v12, v14);
      if ( MediaTypeArrays < 0 )
        goto LABEL_30;
      v3 = v19;
    }
    else
    {
      MediaTypeArrays = CKsOutputPin::CompletePartialMediaType(
                          (CKsOutputPin *)&v19,
                          (struct CMediaType *)v11,
                          (struct _AMMediaType **)v13);
      if ( MediaTypeArrays < 0 )
        goto LABEL_30;
      v3 = v19;
      MediaTypeArrays = (*(int (__thiscall **)(char *, int))(*((_DWORD *)this - 75) + 32))((char *)this - 300, v19);
      if ( MediaTypeArrays < 0 )
      {
        DeleteMediaType((struct _AMMediaType *)v11);
        goto LABEL_30;
      }
    }
    if ( *((_DWORD *)this + 14)
      && (*(int (__thiscall **)(_DWORD, _DWORD, int))(**((_DWORD **)this - 69) + 44))(
           *(_DWORD *)(**((_DWORD **)this - 69) + 44),
           *((_DWORD *)this - 69),
           v3) )
    {
      DeleteMediaType((struct _AMMediaType *)v11);
      MediaTypeArrays = -2147220992;
      goto LABEL_30;
    }
  }
  if ( *((_DWORD *)this + 68) )
  {
    DeleteMediaType((struct _AMMediaType *)v11);
    *((_DWORD *)this + 68) = 0;
  }
  if ( v3 )
  {
    v7 = *((_DWORD *)this + 14) == 0;
    *((_DWORD *)this + 68) = v3;
    if ( !v7 )
    {
      if ( this == (CKsOutputPin2 *)300 )
        v8 = 0;
      else
        v8 = (char *)this - 288;
      (*(void (__thiscall **)(_DWORD, _DWORD, char *))(**(_DWORD **)(*((_DWORD *)this - 65) + 64) + 32))(
        *(_DWORD *)(**(_DWORD **)(*((_DWORD *)this - 65) + 64) + 32),
        *(_DWORD *)(*((_DWORD *)this - 65) + 64),
        v8);
    }
  }
  MediaTypeArrays = 0;
LABEL_30:
  CoTaskMemFree(pv);
  CoTaskMemFree(v17);
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_DirectShow_KernelSupport_Context, SetFormat_Exit, v9, 1, v20);
  return MediaTypeArrays;
}

```

## disassembly

```asm
0x1001c490  mov     edi, edi
0x1001c492  push    ebp
0x1001c493  mov     ebp, esp
0x1001c495  sub     esp, 28h
0x1001c498  mov     eax, ___security_cookie
0x1001c49d  xor     eax, ebp
0x1001c49f  mov     [ebp+var_4], eax
0x1001c4a2  push    ebx
0x1001c4a3  xor     ebx, ebx
0x1001c4a5  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x1001c4ac  push    esi; struct _AMMediaType **
0x1001c4ad  mov     esi, [ebp+arg_4]
0x1001c4b0  push    edi; struct _AMMediaType *
0x1001c4b1  mov     edi, [ebp+this]
0x1001c4b4  mov     [ebp+var_24], esi
0x1001c4b7  mov     [ebp+var_18], ebx
0x1001c4ba  mov     [ebp+var_28], ebx
0x1001c4bd  mov     [ebp+var_20], ebx
0x1001c4c0  mov     [ebp+pv], ebx
0x1001c4c3  jz      short loc_1001C4DB
0x1001c4c5  lea     eax, [ebp+var_14]
0x1001c4c8  mov     edx, offset _SetFormat_Enter
0x1001c4cd  push    eax
0x1001c4ce  push    1
0x1001c4d0  push    ecx
0x1001c4d1  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001c4d6  call    _McGenEventWrite_EventWriteTransfer@20; McGenEventWrite_EventWriteTransfer(x,x,x,x,x)
0x1001c4db  mov     eax, [edi-104h]
0x1001c4e1  cmp     [eax+14h], ebx
0x1001c4e4  jz      short loc_1001C4F0
0x1001c4e6  mov     esi, 80040227h
0x1001c4eb  jmp     loc_1001C666
0x1001c4f0  cmp     [edi+1FCh], ebx
0x1001c4f6  jnz     short loc_1001C510
0x1001c4f8  lea     ecx, [edi-12Ch]; this
0x1001c4fe  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QAEJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x1001c503  mov     esi, eax
0x1001c505  test    esi, esi
0x1001c507  js      loc_1001C666
0x1001c50d  mov     esi, [ebp+var_24]
0x1001c510  test    esi, esi
0x1001c512  jz      loc_1001C60D
0x1001c518  cmp     [edi+1D4h], ebx
0x1001c51e  jz      loc_1001C5C8
0x1001c524  lea     eax, [ebp+var_28]
0x1001c527  mov     ecx, esi
0x1001c529  push    eax; const struct _AMMediaType *
0x1001c52a  lea     edx, [ebp+var_20]
0x1001c52d  call    ?InitializeKsDataFormat@@YGJPBU_AMMediaType@@PAPAXPAK@Z; InitializeKsDataFormat(_AMMediaType const *,void * *,ulong *)
0x1001c532  mov     esi, eax
0x1001c534  test    esi, esi
0x1001c536  js      loc_1001C666
0x1001c53c  mov     ecx, [edi+1CCh]
0x1001c542  mov     eax, [ecx]
0x1001c544  mov     esi, [eax+18h]
0x1001c547  lea     eax, [ebp+pv]
0x1001c54a  push    eax
0x1001c54b  push    [ebp+var_20]
0x1001c54e  push    ecx
0x1001c54f  mov     ecx, esi; this
0x1001c551  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001c557  call    esi
0x1001c559  mov     esi, eax
0x1001c55b  test    esi, esi
0x1001c55d  js      loc_1001C666
0x1001c563  push    1; int
0x1001c565  push    [ebp+pv]; union KSDATAFORMAT *
0x1001c568  lea     ecx, [edi-12Ch]; this
0x1001c56e  call    ?SetPluginMediaType@CKsOutputPin2@@QAEJPATKSDATAFORMAT@@H@Z; CKsOutputPin2::SetPluginMediaType(KSDATAFORMAT *,int)
0x1001c573  mov     esi, eax
0x1001c575  test    esi, esi
0x1001c577  js      loc_1001C666
0x1001c57d  mov     ecx, [ebp+pv]
0x1001c580  lea     edx, [ebp+var_18]
0x1001c583  call    ?GetAmTypeFromKsFormat@@YGJPATKSDATAFORMAT@@PAPAU_AMMediaType@@@Z; GetAmTypeFromKsFormat(KSDATAFORMAT *,_AMMediaType * *)
0x1001c588  mov     esi, eax
0x1001c58a  test    esi, esi
0x1001c58c  js      loc_1001C666
0x1001c592  mov     ebx, [ebp+var_18]
0x1001c595  cmp     dword ptr [edi+38h], 0
0x1001c599  jz      short loc_1001C60D
0x1001c59b  mov     edx, [edi-114h]
0x1001c5a1  push    ebx
0x1001c5a2  push    edx
0x1001c5a3  mov     eax, [edx]
0x1001c5a5  mov     esi, [eax+2Ch]
0x1001c5a8  mov     ecx, esi; this
0x1001c5aa  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001c5b0  call    esi
0x1001c5b2  test    eax, eax
0x1001c5b4  jz      short loc_1001C60D
0x1001c5b6  mov     ecx, [ebp+var_24]
0x1001c5b9  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001c5be  mov     esi, 80040200h
0x1001c5c3  jmp     loc_1001C666
0x1001c5c8  lea     eax, [ebp+var_18]
0x1001c5cb  mov     edx, esi
0x1001c5cd  lea     ebx, [edi-12Ch]
0x1001c5d3  push    eax; this
0x1001c5d4  mov     ecx, ebx
0x1001c5d6  call    ?CompletePartialMediaType@CKsOutputPin@@QAGJPAVCMediaType@@PAPAU_AMMediaType@@@Z; CKsOutputPin::CompletePartialMediaType(CMediaType *,_AMMediaType * *)
0x1001c5db  mov     esi, eax
0x1001c5dd  test    esi, esi
0x1001c5df  js      loc_1001C666
0x1001c5e5  mov     eax, [ebx]
0x1001c5e7  mov     ebx, [ebp+var_18]
0x1001c5ea  push    ebx
0x1001c5eb  mov     esi, [eax+20h]
0x1001c5ee  mov     ecx, esi; this
0x1001c5f0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001c5f6  lea     ecx, [edi-12Ch]
0x1001c5fc  call    esi
0x1001c5fe  mov     esi, eax
0x1001c600  test    esi, esi
0x1001c602  jns     short loc_1001C595
0x1001c604  mov     ecx, ebx
0x1001c606  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001c60b  jmp     short loc_1001C666
0x1001c60d  mov     ecx, [edi+110h]
0x1001c613  test    ecx, ecx
0x1001c615  jz      short loc_1001C626
0x1001c617  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001c61c  mov     dword ptr [edi+110h], 0
0x1001c626  test    ebx, ebx
0x1001c628  jz      short loc_1001C664
0x1001c62a  cmp     dword ptr [edi+38h], 0
0x1001c62e  mov     [edi+110h], ebx
0x1001c634  jz      short loc_1001C664
0x1001c636  mov     eax, [edi-104h]
0x1001c63c  mov     ecx, [eax+40h]
0x1001c63f  mov     eax, [ecx]
0x1001c641  mov     esi, [eax+20h]
0x1001c644  lea     eax, [edi-12Ch]
0x1001c64a  test    eax, eax
0x1001c64c  jz      short loc_1001C656
0x1001c64e  add     edi, 0FFFFFEE0h
0x1001c654  jmp     short loc_1001C658
0x1001c656  xor     edi, edi
0x1001c658  push    edi
0x1001c659  push    ecx
0x1001c65a  mov     ecx, esi; this
0x1001c65c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001c662  call    esi
0x1001c664  xor     esi, esi
0x1001c666  push    [ebp+pv]; pv
0x1001c669  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001c66f  push    [ebp+var_20]; pv
0x1001c672  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001c678  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x1001c67f  jz      short loc_1001C697
0x1001c681  lea     eax, [ebp+var_14]
0x1001c684  mov     edx, offset _SetFormat_Exit
0x1001c689  push    eax
0x1001c68a  push    1
0x1001c68c  push    ecx
0x1001c68d  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001c692  call    _McGenEventWrite_EventWriteTransfer@20; McGenEventWrite_EventWriteTransfer(x,x,x,x,x)
0x1001c697  mov     ecx, [ebp+var_4]
0x1001c69a  mov     eax, esi
0x1001c69c  pop     edi
0x1001c69d  pop     esi
0x1001c69e  xor     ecx, ebp; StackCookie
0x1001c6a0  pop     ebx
0x1001c6a1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c6a6  leave
0x1001c6a7  retn    8
```
