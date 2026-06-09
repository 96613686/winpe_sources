# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18003f750`
- end: `0x18003f7b6`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003f728`
- `0x18003f750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f772`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18003f750  mov     [rsp+arg_0], rbx
0x18003f755  push    rdi
0x18003f756  sub     rsp, 20h
0x18003f75a  mov     qword ptr [r8], 0
0x18003f761  mov     ecx, 20h ; ' '; cb
0x18003f766  mov     dword ptr [rdx], 0
0x18003f76c  mov     rbx, r8
0x18003f76f  mov     rdi, rdx
0x18003f772  call    cs:__imp_CoTaskMemAlloc
0x18003f779  nop     dword ptr [rax+rax+00h]
0x18003f77e  mov     r8, rax
0x18003f781  test    rax, rax
0x18003f784  jnz     short loc_18003F78D
0x18003f786  mov     eax, 8007000Eh
0x18003f78b  jmp     short loc_18003F7AA
0x18003f78d  lea     rdx, [rsp+28h+arg_8]
0x18003f792  mov     [rsp+28h+arg_8], 0
0x18003f79a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$0A@UIBuffer@Streams@Storage@Windows@@UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003f79f  mov     dword ptr [rdi], 2
0x18003f7a5  xor     eax, eax
0x18003f7a7  mov     [rbx], r8
0x18003f7aa  mov     rbx, [rsp+28h+arg_0]
0x18003f7af  add     rsp, 20h
0x18003f7b3  pop     rdi
0x18003f7b4  retn
```
