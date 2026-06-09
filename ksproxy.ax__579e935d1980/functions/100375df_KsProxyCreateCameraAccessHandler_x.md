# KsProxyCreateCameraAccessHandler(x)

- ea: `0x100375df`
- end: `0x1003767a`
- name: `_KsProxyCreateCameraAccessHandler@4`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1000cf60`

## callees

- `0x100075ad`
- `0x1000f598`
- `0x1000f5b7`
- `0x100375df`
- `0x1003789d`
- `0x10037920`
- `0x10037980`
- `0x1003abb4`

## string_xrefs

- `0x10037651`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c
int __thiscall KsProxyCreateCameraAccessHandler(_DWORD *this)
{
  int v2; // esi
  KsProxyCameraAccessHandler *v3; // eax
  KsProxyCameraAccessHandler *v4; // ebx
  int v5; // eax
  unsigned int v7; // [esp+0h] [ebp-10h]
  const char *v8; // [esp+4h] [ebp-Ch]
  int v9; // [esp+8h] [ebp-8h]
  int v10; // [esp+Ch] [ebp-4h] BYREF

  v10 = 0;
  if ( this )
  {
    *this = 0;
    wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(&v10);
    v10 = 0;
    v3 = (KsProxyCameraAccessHandler *)operator new(0x28u, &std::nothrow);
    if ( v3 )
    {
      v4 = KsProxyCameraAccessHandler::KsProxyCameraAccessHandler(v3);
      v2 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IKsProxyCameraAccessHandler>::QueryInterface(
             v4,
             &_GUID_8eedd8d2_9612_4310_9cd7_f8f50bd425a9,
             &v10);
      if ( v4 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IKsProxyCameraAccessHandler>::Release(v4);
      if ( v2 >= 0 )
      {
        v5 = v10;
        v2 = 0;
        v10 = 0;
        *this = v5;
        goto LABEL_10;
      }
    }
    else
    {
      v2 = -2147024882;
    }
  }
  else
  {
    v2 = -2147467261;
  }
  wil::details::in1diag3::Return_Hr(
    (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
    (void *)v2,
    v7,
    v8,
    v9);
LABEL_10:
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(&v10);
  return v2;
}

```

## disassembly

```asm
0x100375df  mov     edi, edi
0x100375e1  push    ebp
0x100375e2  mov     ebp, esp
0x100375e4  push    ecx
0x100375e5  push    ebx; int
0x100375e6  push    esi; char *
0x100375e7  push    edi; unsigned int
0x100375e8  mov     edi, ecx
0x100375ea  xor     ebx, ebx
0x100375ec  mov     [ebp+var_4], ebx
0x100375ef  test    edi, edi
0x100375f1  jnz     short loc_100375FC
0x100375f3  mov     esi, 80004003h
0x100375f8  push    10h
0x100375fa  jmp     short loc_1003764C
0x100375fc  lea     ecx, [ebp+var_4]
0x100375ff  mov     [edi], ebx
0x10037601  call    ?reset@?$com_ptr_t@UIKsProxyCameraAccessHandler@@Uerr_returncode_policy@wil@@@wil@@QAEXXZ; wil::com_ptr_t<IKsProxyCameraAccessHandler,wil::err_returncode_policy>::reset(void)
0x10037606  push    offset ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1003760b  push    28h ; '('; Size
0x1003760d  mov     [ebp+var_4], ebx
0x10037610  call    ??2@YAPAXIABUnothrow_t@std@@@Z; operator new(uint,std::nothrow_t const &)
0x10037615  pop     ecx
0x10037616  pop     ecx
0x10037617  test    eax, eax
0x10037619  jnz     short loc_10037622
0x1003761b  mov     esi, 8007000Eh
0x10037620  jmp     short loc_1003764A
0x10037622  mov     ecx, eax; this
0x10037624  call    ??0KsProxyCameraAccessHandler@@QAE@XZ; KsProxyCameraAccessHandler::KsProxyCameraAccessHandler(void)
0x10037629  mov     ebx, eax
0x1003762b  lea     eax, [ebp+var_4]
0x1003762e  push    eax
0x1003762f  push    offset __GUID_8eedd8d2_9612_4310_9cd7_f8f50bd425a9
0x10037634  push    ebx
0x10037635  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIKsProxyCameraAccessHandler@@@Details@WRL@Microsoft@@UAGJABU_GUID@@PAPAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IKsProxyCameraAccessHandler>::QueryInterface(_GUID const &,void * *)
0x1003763a  mov     esi, eax
0x1003763c  test    ebx, ebx
0x1003763e  jz      short loc_10037646
0x10037640  push    ebx
0x10037641  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIKsProxyCameraAccessHandler@@@Details@WRL@Microsoft@@UAGKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IKsProxyCameraAccessHandler>::Release(void)
0x10037646  test    esi, esi
0x10037648  jns     short loc_1003765D
0x1003764a  push    13h
0x1003764c  mov     ecx, [ebp+4]
0x1003764f  pop     edx
0x10037650  push    esi; void *
0x10037651  push    offset aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10037656  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1003765b  jmp     short loc_1003766B
0x1003765d  mov     eax, [ebp+var_4]
0x10037660  xor     esi, esi
0x10037662  mov     [ebp+var_4], 0
0x10037669  mov     [edi], eax
0x1003766b  lea     ecx, [ebp+var_4]
0x1003766e  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10037673  pop     edi
0x10037674  mov     eax, esi
0x10037676  pop     esi
0x10037677  pop     ebx
0x10037678  leave
0x10037679  retn
```
