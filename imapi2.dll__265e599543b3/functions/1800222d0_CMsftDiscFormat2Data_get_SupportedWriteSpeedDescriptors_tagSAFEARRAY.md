# CMsftDiscFormat2Data::get_SupportedWriteSpeedDescriptors(tagSAFEARRAY * *)

- ea: `0x1800222d0`
- end: `0x180022358`
- name: `?get_SupportedWriteSpeedDescriptors@CMsftDiscFormat2Data@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `136`
- prototype: `int(CMsftDiscFormat2Data *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000a804`
- `0x1800222d0`
- `0x180044698`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::get_SupportedWriteSpeedDescriptors(
        void (__fastcall ****this)(Imapi2Utility *, GUID *, __int64 *),
        struct tagSAFEARRAY **a2)
{
  signed int v4; // ebx
  const struct _GUID *v5; // r8
  struct tagSAFEARRAY **v6; // r9
  struct IDiscRecorder2 *v8; // [rsp+40h] [rbp+18h] BYREF

  LODWORD(v8) = 0;
  v4 = CMsftDiscFormat2Data::ValidateRecorderSet((CMsftDiscFormat2Data *)this);
  if ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(void (__fastcall ****)(Imapi2Utility *, GUID *, __int64 *), struct IDiscRecorder2 **))(*this)[29])(
           this,
           &v8);
    if ( v4 >= 0 )
      v4 = Imapi2Utility::GetSupportedWriteSpeedDescriptors(this[26], (struct IDiscRecorder2 *)(unsigned int)v8, a2, v6);
  }
  if ( (v4 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v4, (__int64)&CLSID_MsftDiscFormat2Data, v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800222d0  mov     [rsp+arg_0], rbx
0x1800222d5  mov     [rsp+arg_8], rsi
0x1800222da  push    rdi
0x1800222db  sub     rsp, 20h
0x1800222df  mov     rsi, rdx
0x1800222e2  mov     dword ptr [rsp+28h+arg_10], 0
0x1800222ea  mov     rdi, rcx
0x1800222ed  call    ?ValidateRecorderSet@CMsftDiscFormat2Data@@AEAAJXZ; CMsftDiscFormat2Data::ValidateRecorderSet(void)
0x1800222f2  mov     ebx, eax
0x1800222f4  test    eax, eax
0x1800222f6  js      short loc_18002232A
0x1800222f8  mov     rax, [rdi]
0x1800222fb  lea     rdx, [rsp+28h+arg_10]
0x180022300  mov     rcx, rdi
0x180022303  mov     rax, [rax+0E8h]
0x18002230a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002230f  mov     ebx, eax
0x180022311  test    eax, eax
0x180022313  js      short loc_18002232A
0x180022315  mov     edx, dword ptr [rsp+28h+arg_10]; struct IDiscRecorder2 *
0x180022319  mov     r8, rsi; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x18002231c  mov     rcx, [rdi+0D0h]; this
0x180022323  call    ?GetSupportedWriteSpeedDescriptors@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::GetSupportedWriteSpeedDescriptors(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,tagSAFEARRAY * *)
0x180022328  mov     ebx, eax
0x18002232a  mov     eax, ebx
0x18002232c  and     eax, 80FF0000h
0x180022331  cmp     eax, 80AA0000h
0x180022336  jnz     short loc_180022346
0x180022338  lea     rdx, CLSID_MsftDiscFormat2Data; int
0x18002233f  mov     ecx, ebx; dwMessageId
0x180022341  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180022346  mov     rsi, [rsp+28h+arg_8]
0x18002234b  mov     eax, ebx
0x18002234d  mov     rbx, [rsp+28h+arg_0]
0x180022352  add     rsp, 20h
0x180022356  pop     rdi
0x180022357  retn
```
