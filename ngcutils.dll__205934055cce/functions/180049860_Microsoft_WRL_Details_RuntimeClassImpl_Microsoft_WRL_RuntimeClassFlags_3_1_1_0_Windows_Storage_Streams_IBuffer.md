# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180049860`
- end: `0x1800498cd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049a90`

## callees

- `0x180049860`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049882`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_905a0fe0_bc53_11df_8c49_001e4fc686da;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_905a0fef_bc53_11df_8c49_001e4fc686da;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180049860  mov     [rsp+arg_0], rbx
0x180049865  push    rdi
0x180049866  sub     rsp, 20h
0x18004986a  mov     qword ptr [r8], 0
0x180049871  mov     ecx, 30h ; '0'; cb
0x180049876  mov     dword ptr [rdx], 0
0x18004987c  mov     rbx, r8
0x18004987f  mov     rdi, rdx
0x180049882  call    cs:__imp_CoTaskMemAlloc
0x180049888  test    rax, rax
0x18004988b  jnz     short loc_180049894
0x18004988d  mov     eax, 8007000Eh
0x180049892  jmp     short loc_1800498C2
0x180049894  movups  xmm0, xmmword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data1
0x18004989b  movdqu  xmmword ptr [rax], xmm0
0x18004989f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800498a6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800498ab  movups  xmm0, xmmword ptr cs:_GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data1
0x1800498b2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800498b7  mov     dword ptr [rdi], 3
0x1800498bd  mov     [rbx], rax
0x1800498c0  xor     eax, eax
0x1800498c2  mov     rbx, [rsp+28h+arg_0]
0x1800498c7  add     rsp, 20h
0x1800498cb  pop     rdi
0x1800498cc  retn
```
