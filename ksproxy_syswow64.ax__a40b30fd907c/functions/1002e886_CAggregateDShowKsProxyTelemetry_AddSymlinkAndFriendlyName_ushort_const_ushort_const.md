# CAggregateDShowKsProxyTelemetry::AddSymlinkAndFriendlyName(ushort const *,ushort const *)

- ea: `0x1002e886`
- end: `0x1002e921`
- name: `?AddSymlinkAndFriendlyName@CAggregateDShowKsProxyTelemetry@@QAEXPBG0@Z`
- size: `155`
- prototype: `void __thiscall(CAggregateDShowKsProxyTelemetry *__hidden this, OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x1000cf60`

## callees

- `0x10007823`
- `0x1002d510`
- `0x1002e886`
- `0x1002ec39`
- `0x1003aba0`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x1002e8ca`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1002e8dc`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1002e8ca`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1002e8dc`

## pseudocode

```c
void __thiscall CAggregateDShowKsProxyTelemetry::AddSymlinkAndFriendlyName(
        CAggregateDShowKsProxyTelemetry *this,
        OLECHAR *psz,
        const unsigned __int16 *a3)
{
  BSTR v4; // eax
  BSTR v5; // eax
  BSTR v6[7]; // [esp+18h] [ebp-20h] BYREF

  if ( *((_DWORD *)this + 1) )
  {
    memset(v6, 0, sizeof(v6));
    v4 = SysAllocString(psz);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__stdcall *)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned int,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(v4);
    v5 = SysAllocString(a3);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__stdcall *)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned int,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(v5);
    (*(void (__thiscall **)(_DWORD, int, BSTR *, int, int))(**((_DWORD **)this + 1) + 28))(
      *((_DWORD *)this + 1),
      6,
      v6,
      1,
      1);
    DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue(v6);
  }
}

```

## disassembly

```asm
0x1002e886  mov     edi, edi
0x1002e888  push    ebp
0x1002e889  mov     ebp, esp
0x1002e88b  sub     esp, 34h
0x1002e88e  mov     eax, ___security_cookie
0x1002e893  xor     eax, ebp
0x1002e895  mov     [ebp+var_4], eax
0x1002e898  mov     eax, [ebp+arg_4]
0x1002e89b  xor     edx, edx
0x1002e89d  push    ebx
0x1002e89e  mov     ebx, ecx
0x1002e8a0  mov     [ebp+var_24], eax
0x1002e8a3  mov     ecx, [ebp+psz]
0x1002e8a6  cmp     [ebx+4], edx
0x1002e8a9  jz      short loc_1002E912
0x1002e8ab  push    esi
0x1002e8ac  push    edi
0x1002e8ad  xor     eax, eax
0x1002e8af  mov     [ebp+var_C], edx
0x1002e8b2  lea     edi, [ebp+var_34]
0x1002e8b5  mov     [ebp+var_8], edx
0x1002e8b8  stosd
0x1002e8b9  lea     esi, [ebp+var_34]
0x1002e8bc  push    ecx; psz
0x1002e8bd  stosd
0x1002e8be  stosd
0x1002e8bf  stosd
0x1002e8c0  lea     edi, [ebp+var_20]
0x1002e8c3  movsd
0x1002e8c4  movsd
0x1002e8c5  movsd
0x1002e8c6  movsd
0x1002e8c7  mov     [ebp+var_10], edx
0x1002e8ca  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1002e8d0  push    eax
0x1002e8d1  lea     ecx, [ebp+var_C]
0x1002e8d4  call    ?reset@?$unique_storage@U?$resource_policy@PAGP6GXPAG@Z$1?SysFreeString@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAGPAG$0A@$$T@details@wil@@@details@wil@@QAEXPAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<uint,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1002e8d9  push    [ebp+var_24]; psz
0x1002e8dc  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1002e8e2  push    eax
0x1002e8e3  lea     ecx, [ebp+var_8]
0x1002e8e6  call    ?reset@?$unique_storage@U?$resource_policy@PAGP6GXPAG@Z$1?SysFreeString@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAGPAG$0A@$$T@details@wil@@@details@wil@@QAEXPAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<uint,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1002e8eb  mov     edi, [ebx+4]
0x1002e8ee  lea     eax, [ebp+var_20]
0x1002e8f1  push    1
0x1002e8f3  push    1
0x1002e8f5  push    eax
0x1002e8f6  mov     esi, [edi]
0x1002e8f8  push    6
0x1002e8fa  mov     ecx, [esi+1Ch]; this
0x1002e8fd  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002e903  mov     ecx, edi
0x1002e905  call    dword ptr [esi+1Ch]
0x1002e908  lea     ecx, [ebp+var_20]; this
0x1002e90b  call    ??1DShowKsProxyTelemetryValue@@QAE@XZ; DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue(void)
0x1002e910  pop     edi
0x1002e911  pop     esi
0x1002e912  mov     ecx, [ebp+var_4]
0x1002e915  xor     ecx, ebp; StackCookie
0x1002e917  pop     ebx
0x1002e918  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e91d  leave
0x1002e91e  retn    8
```
