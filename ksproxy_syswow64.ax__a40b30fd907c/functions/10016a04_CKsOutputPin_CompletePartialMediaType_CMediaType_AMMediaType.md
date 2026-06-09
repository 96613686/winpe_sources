# CKsOutputPin::CompletePartialMediaType(CMediaType *,_AMMediaType * *)

- ea: `0x10016a04`
- end: `0x10016b0b`
- name: `?CompletePartialMediaType@CKsOutputPin@@QAGJPAVCMediaType@@PAPAU_AMMediaType@@@Z`
- size: `263`
- prototype: `int __userpurge@<eax>(CKsOutputPin_vtbl *@<ecx>, const struct _AMMediaType *@<ebx>, CKsOutputPin *this, struct CMediaType *, struct _AMMediaType **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100179f0`
- `0x1001c490`

## callees

- `0x10016a04`
- `0x10021aad`
- `0x1002d510`
- `0x100302a7`
- `0x100302c4`

## pseudocode

```c
int __userpurge CKsOutputPin::CompletePartialMediaType@<eax>(
        CKsOutputPin_vtbl *a1@<ecx>,
        const struct _AMMediaType *a2@<ebx>,
        CKsOutputPin *this,
        struct CMediaType *a4,
        struct _AMMediaType **a5)
{
  CKsOutputPin_vtbl *v5; // esi
  CKsOutputPin_vtbl *MediaType; // eax
  HRESULT (__thiscall *DeliverNewSegment)(struct CKsOutputPin *, __int64, __int64, long double); // edi
  int (__thiscall *v8)(_DWORD, int, int, HRESULT (__thiscall *)(struct CKsOutputPin *, __int64, __int64, long double), CKsOutputPin_vtbl *); // ebx
  int v9; // eax
  int v10; // edi
  LPVOID v11; // ecx
  struct _AMMediaType *v13; // [esp-4h] [ebp-1Ch]
  struct IKsDataTypeHandler **v14; // [esp+0h] [ebp-18h]
  struct IUnknown **v15; // [esp+4h] [ebp-14h]
  char v16; // [esp+8h] [ebp-10h] BYREF
  CKsOutputPin_vtbl *v17; // [esp+Ch] [ebp-Ch]
  LPVOID ppv; // [esp+10h] [ebp-8h] BYREF
  int v19; // [esp+14h] [ebp-4h] BYREF

  v5 = a1;
  v17 = a1;
  OpenDataHandler((const struct CMediaType *)&v16, &ppv, v14, v15);
  if ( ppv )
  {
    if ( (**(int (__thiscall ***)(_DWORD, LPVOID, GUID *, int *))ppv)(
           **(_DWORD **)ppv,
           ppv,
           &_GUID_827d1a0e_0f73_11d2_b27a_00a0c9223196,
           &v19) >= 0 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v19 + 8))(*(_DWORD *)(*(_DWORD *)v19 + 8), v19);
    v5 = v17;
  }
  else
  {
    v19 = 0;
  }
  MediaType = (CKsOutputPin_vtbl *)CreateMediaType(a2);
  v17 = MediaType;
  this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = MediaType;
  if ( MediaType )
  {
    if ( v19 )
    {
      DeliverNewSegment = v5[3].DeliverNewSegment;
      v8 = *(int (__thiscall **)(_DWORD, int, int, HRESULT (__thiscall *)(struct CKsOutputPin *, __int64, __int64, long double), CKsOutputPin_vtbl *))(*(_DWORD *)v19 + 12);
      v9 = (*(int (__thiscall **)(_DWORD, int))(*((_DWORD *)v5->CheckConnect + 27) + 12))(
             *(_DWORD *)(*((_DWORD *)v5->CheckConnect + 27) + 12),
             (int)v5->CheckConnect + 108);
      v10 = v8(v8, v19, v9, DeliverNewSegment, v17);
      if ( v10 < 0 )
      {
        DeleteMediaType(v13);
        this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = 0;
      }
    }
    else
    {
      v10 = 0;
    }
  }
  else
  {
    v10 = -2147024882;
  }
  v11 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)v11 + 8))(*(_DWORD *)(*(_DWORD *)v11 + 8), v11);
  }
  return v10;
}

```

## disassembly

```asm
0x10016a04  mov     edi, edi
0x10016a06  push    ebp
0x10016a07  mov     ebp, esp
0x10016a09  sub     esp, 10h
0x10016a0c  push    esi; struct IUnknown **
0x10016a0d  mov     esi, ecx
0x10016a0f  lea     eax, [ebp+ppv]
0x10016a12  push    edi; struct IKsDataTypeHandler **
0x10016a13  mov     edi, edx
0x10016a15  mov     [ebp+var_C], esi
0x10016a18  push    eax; ppv
0x10016a19  mov     edx, esi
0x10016a1b  lea     eax, [ebp+var_10]
0x10016a1e  neg     edx
0x10016a20  mov     ecx, edi
0x10016a22  push    eax; struct CMediaType *
0x10016a23  lea     eax, [esi+0Ch]
0x10016a26  sbb     edx, edx
0x10016a28  and     edx, eax
0x10016a2a  call    ?OpenDataHandler@@YGXPBVCMediaType@@PAUIUnknown@@PAPAUIKsDataTypeHandler@@PAPAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x10016a2f  mov     ecx, [ebp+ppv]
0x10016a32  test    ecx, ecx
0x10016a34  jz      loc_10016AD2
0x10016a3a  mov     eax, [ecx]
0x10016a3c  mov     esi, [eax]
0x10016a3e  lea     eax, [ebp+var_4]
0x10016a41  push    eax
0x10016a42  push    offset __GUID_827d1a0e_0f73_11d2_b27a_00a0c9223196
0x10016a47  push    ecx
0x10016a48  mov     ecx, esi; this
0x10016a4a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10016a50  call    esi
0x10016a52  test    eax, eax
0x10016a54  js      short loc_10016A69
0x10016a56  mov     eax, [ebp+var_4]
0x10016a59  push    eax
0x10016a5a  mov     ecx, [eax]
0x10016a5c  mov     esi, [ecx+8]
0x10016a5f  mov     ecx, esi; this
0x10016a61  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10016a67  call    esi
0x10016a69  mov     esi, [ebp+var_C]
0x10016a6c  push    ebx; struct _AMMediaType *
0x10016a6d  mov     ecx, edi
0x10016a6f  call    ?CreateMediaType@@YGPAU_AMMediaType@@PBU1@@Z; CreateMediaType(_AMMediaType const *)
0x10016a74  mov     ecx, [ebp+this]
0x10016a77  mov     [ebp+var_C], eax
0x10016a7a  mov     [ecx], eax
0x10016a7c  test    eax, eax
0x10016a7e  jz      short loc_10016ADF
0x10016a80  mov     eax, [ebp+var_4]
0x10016a83  test    eax, eax
0x10016a85  jz      short loc_10016ADB
0x10016a87  mov     eax, [eax]
0x10016a89  mov     edi, [esi+184h]
0x10016a8f  mov     ebx, [eax+0Ch]
0x10016a92  mov     eax, [esi+28h]
0x10016a95  add     eax, 6Ch ; 'l'
0x10016a98  push    eax
0x10016a99  mov     ecx, [eax]
0x10016a9b  mov     esi, [ecx+0Ch]
0x10016a9e  mov     ecx, esi; this
0x10016aa0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10016aa6  call    esi
0x10016aa8  push    [ebp+var_C]
0x10016aab  mov     ecx, ebx; this
0x10016aad  push    edi
0x10016aae  push    eax
0x10016aaf  push    [ebp+var_4]
0x10016ab2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10016ab8  call    ebx
0x10016aba  mov     edi, eax
0x10016abc  test    edi, edi
0x10016abe  jns     short loc_10016AE4
0x10016ac0  mov     ebx, [ebp+this]
0x10016ac3  mov     ecx, [ebx]
0x10016ac5  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x10016aca  mov     dword ptr [ebx], 0
0x10016ad0  jmp     short loc_10016AE4
0x10016ad2  mov     [ebp+var_4], 0
0x10016ad9  jmp     short loc_10016A6C
0x10016adb  xor     edi, edi
0x10016add  jmp     short loc_10016AE4
0x10016adf  mov     edi, 8007000Eh
0x10016ae4  mov     ecx, [ebp+ppv]
0x10016ae7  pop     ebx
0x10016ae8  test    ecx, ecx
0x10016aea  jz      short loc_10016B03
0x10016aec  mov     [ebp+ppv], 0
0x10016af3  mov     eax, [ecx]
0x10016af5  push    ecx
0x10016af6  mov     esi, [eax+8]
0x10016af9  mov     ecx, esi; this
0x10016afb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10016b01  call    esi
0x10016b03  mov     eax, edi
0x10016b05  pop     edi
0x10016b06  pop     esi
0x10016b07  leave
0x10016b08  retn    4
```
