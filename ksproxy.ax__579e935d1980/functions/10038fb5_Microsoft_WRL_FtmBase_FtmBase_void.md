# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x10038fb5`
- end: `0x10039031`
- name: `??0FtmBase@WRL@Microsoft@@QAE@XZ`
- size: `124`
- prototype: `_DWORD __thiscall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x100386a2`
- `0x1003872f`
- `0x10039bef`
- `0x1003a3ad`

## callees

- `0x1002d510`
- `0x10037e8d`
- `0x10038fb5`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x10038fd9`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x10038fd9`

## pseudocode

```c
Microsoft::WRL::FtmBase *__thiscall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  Microsoft::WRL::FtmBase *v1; // edi
  Microsoft::WRL::ComPtr<IMarshal> *p_marshaller; // ebx
  IMarshal *ptr; // ecx
  LPUNKNOWN v4; // esi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const _GUID *, void **); // eax
  HRESULT (__stdcall *v8)(IUnknown *, const _GUID *, void **); // [esp+Ch] [ebp-8h]
  LPUNKNOWN ppunkMarshal; // [esp+10h] [ebp-4h] BYREF

  v1 = this;
  this->__vftable = (Microsoft::WRL::FtmBase_vtbl *)&Microsoft::WRL::FtmBase::`vftable';
  p_marshaller = &this->marshaller_;
  this->marshaller_.ptr_ = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    ptr = p_marshaller->ptr_;
    v4 = ppunkMarshal;
    QueryInterface = ppunkMarshal->QueryInterface;
    v8 = QueryInterface;
    if ( p_marshaller->ptr_ )
    {
      p_marshaller->ptr_ = 0;
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMarshal *))ptr->Release)(ptr->Release, ptr);
      v1 = this;
      QueryInterface = v8;
    }
    ((void (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), LPUNKNOWN, GUID *, Microsoft::WRL::ComPtr<IMarshal> *))v8)(
      QueryInterface,
      v4,
      &_GUID_00000003_0000_0000_c000_000000000046,
      p_marshaller);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(&ppunkMarshal);
  return v1;
}

```

## disassembly

```asm
0x10038fb5  mov     edi, edi
0x10038fb7  push    ebp
0x10038fb8  mov     ebp, esp
0x10038fba  sub     esp, 0Ch
0x10038fbd  push    ebx
0x10038fbe  push    edi
0x10038fbf  mov     edi, ecx
0x10038fc1  lea     eax, [ebp+ppunkMarshal]
0x10038fc4  xor     ecx, ecx
0x10038fc6  mov     [ebp+var_C], edi
0x10038fc9  push    eax; ppunkMarshal
0x10038fca  push    ecx; punkOuter
0x10038fcb  mov     dword ptr [edi], offset ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x10038fd1  lea     ebx, [edi+0Ch]
0x10038fd4  mov     [ebx], ecx
0x10038fd6  mov     [ebp+ppunkMarshal], ecx
0x10038fd9  call    ds:__imp__CoCreateFreeThreadedMarshaler@8; CoCreateFreeThreadedMarshaler(x,x)
0x10038fdf  test    eax, eax
0x10038fe1  js      short loc_10039023
0x10038fe3  mov     ecx, [ebx]
0x10038fe5  push    esi
0x10038fe6  mov     esi, [ebp+ppunkMarshal]
0x10038fe9  mov     eax, [esi]
0x10038feb  mov     eax, [eax]
0x10038fed  mov     [ebp+var_8], eax
0x10038ff0  test    ecx, ecx
0x10038ff2  jz      short loc_10039010
0x10038ff4  mov     dword ptr [ebx], 0
0x10038ffa  mov     eax, [ecx]
0x10038ffc  push    ecx
0x10038ffd  mov     edi, [eax+8]
0x10039000  mov     ecx, edi; this
0x10039002  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10039008  call    edi
0x1003900a  mov     edi, [ebp+var_C]
0x1003900d  mov     eax, [ebp+var_8]
0x10039010  push    ebx
0x10039011  push    offset __GUID_00000003_0000_0000_c000_000000000046
0x10039016  push    esi
0x10039017  mov     ecx, eax; this
0x10039019  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003901f  call    [ebp+var_8]
0x10039022  pop     esi
0x10039023  lea     ecx, [ebp+ppunkMarshal]
0x10039026  call    ??1?$ComPtr@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::ComPtr<Windows::Internal::IComPoolTask>::~ComPtr<Windows::Internal::IComPoolTask>(void)
0x1003902b  mov     eax, edi
0x1003902d  pop     edi
0x1003902e  pop     ebx
0x1003902f  leave
0x10039030  retn
```
