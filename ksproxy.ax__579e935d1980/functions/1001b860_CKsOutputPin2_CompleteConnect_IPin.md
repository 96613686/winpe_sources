# CKsOutputPin2::CompleteConnect(IPin *)

- ea: `0x1001b860`
- end: `0x1001b8d3`
- name: `?CompleteConnect@CKsOutputPin2@@UAEJPAUIPin@@@Z`
- size: `115`
- prototype: `int __thiscall(CBaseOutputPin *this, struct IPin *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x10009f60`
- `0x1001a052`
- `0x1001b860`
- `0x1002d510`
- `0x10031fd7`

## string_xrefs

- `0x1001b8b6`: `CKsOutputPin2::CompleteConnect`

## pseudocode

```c
int __thiscall CKsOutputPin2::CompleteConnect(CBaseOutputPin *this, struct IPin *a2)
{
  int v3; // esi
  CKsProxy *v5; // [esp+0h] [ebp-8h]
  int v6; // [esp+4h] [ebp-4h]

  v3 = ((int (__thiscall *)(HRESULT (__stdcall *)(struct CBaseOutputPin *, const _GUID *, void **), CBaseOutputPin *, struct IPin *))this->CBasePin::CUnknown::INonDelegatingUnknown::__vftable[1].NonDelegatingQueryInterface)(
         this->CBasePin::CUnknown::INonDelegatingUnknown::__vftable[1].NonDelegatingQueryInterface,
         this,
         a2);
  if ( v3 >= 0 )
  {
    v3 = CBaseOutputPin::CompleteConnect(this, a2);
    if ( v3 >= 0 )
      CKsProxy::GeneratePinInstances(v5, v6);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_sd(0x1Au, *((_QWORD *)WPP_GLOBAL_Control + 2), (int)"CKsOutputPin2::CompleteConnect", v3);
  return v3;
}

```

## disassembly

```asm
0x1001b860  mov     edi, edi
0x1001b862  push    ebp
0x1001b863  mov     ebp, esp
0x1001b865  and     esp, 0FFFFFFF8h
0x1001b868  push    esi; int
0x1001b869  push    edi; this
0x1001b86a  push    [ebp+arg_0]
0x1001b86d  mov     edi, ecx
0x1001b86f  push    edi
0x1001b870  mov     eax, [edi]
0x1001b872  mov     esi, [eax+5Ch]
0x1001b875  mov     ecx, esi; this
0x1001b877  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001b87d  call    esi
0x1001b87f  mov     esi, eax
0x1001b881  test    esi, esi
0x1001b883  js      short loc_1001B8A3
0x1001b885  push    [ebp+arg_0]; struct IPin *
0x1001b888  mov     ecx, edi; this
0x1001b88a  call    ?CompleteConnect@CBaseOutputPin@@UAEJPAUIPin@@@Z; CBaseOutputPin::CompleteConnect(IPin *)
0x1001b88f  mov     esi, eax
0x1001b891  test    esi, esi
0x1001b893  js      short loc_1001B8A3
0x1001b895  mov     edx, [edi+2C0h]
0x1001b89b  mov     ecx, [edi+28h]
0x1001b89e  call    ?GeneratePinInstances@CKsProxy@@QAGJH@Z; CKsProxy::GeneratePinInstances(int)
0x1001b8a3  mov     eax, _WPP_GLOBAL_Control
0x1001b8a8  cmp     eax, offset _WPP_GLOBAL_Control
0x1001b8ad  jz      short loc_1001B8C9
0x1001b8af  cmp     byte ptr [eax+19h], 2
0x1001b8b3  jb      short loc_1001B8C9
0x1001b8b5  push    esi; char
0x1001b8b6  push    offset aCksoutputpin2C; "CKsOutputPin2::CompleteConnect"
0x1001b8bb  push    dword ptr [eax+14h]
0x1001b8be  push    dword ptr [eax+10h]; LoggerHandle
0x1001b8c1  push    1Ah
0x1001b8c3  pop     ecx; MessageNumber
0x1001b8c4  call    _WPP_SF_sd@24; WPP_SF_sd(x,x,x,x,x,x)
0x1001b8c9  pop     edi
0x1001b8ca  mov     eax, esi
0x1001b8cc  pop     esi
0x1001b8cd  mov     esp, ebp
0x1001b8cf  pop     ebp
0x1001b8d0  retn    4
```
