# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x180015260`
- end: `0x1800152a0`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `64`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001980`
- `0x180004dcc`
- `0x180015260`

## pseudocode

```c
void *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  *((_DWORD *)a1 + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)a1 + 4);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180015260  mov     [rsp+arg_0], rbx
0x180015265  push    rdi
0x180015266  sub     rsp, 20h
0x18001526a  mov     rdi, rcx
0x18001526d  mov     dword ptr [rcx+2Ch], 0C0000001h
0x180015274  add     rcx, 20h ; ' '
0x180015278  mov     ebx, edx
0x18001527a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001527f  test    bl, 1
0x180015282  jz      short loc_180015291
0x180015284  mov     edx, 30h ; '0'; unsigned __int64
0x180015289  mov     rcx, rdi; void *
0x18001528c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015291  mov     rbx, [rsp+28h+arg_0]
0x180015296  mov     rax, rdi
0x180015299  add     rsp, 20h
0x18001529d  pop     rdi
0x18001529e  retn
```
