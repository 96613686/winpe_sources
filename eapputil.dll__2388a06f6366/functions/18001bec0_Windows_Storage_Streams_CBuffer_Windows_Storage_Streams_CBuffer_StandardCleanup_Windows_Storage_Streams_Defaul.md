# Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::GetIids(ulong *,_GUID * *)

- ea: `0x18001bec0`
- end: `0x18001bf21`
- name: `?GetIids@?$CBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@UDefaultMarshaler@234@@Streams@Storage@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001bec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bee2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x20u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_905a0fe0_bc53_11df_8c49_001e4fc686da;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001bec0  mov     [rsp+arg_0], rbx
0x18001bec5  push    rdi
0x18001bec6  sub     rsp, 20h
0x18001beca  mov     qword ptr [r8], 0
0x18001bed1  mov     ecx, 20h ; ' '; cb
0x18001bed6  mov     dword ptr [rdx], 0
0x18001bedc  mov     rbx, r8
0x18001bedf  mov     rdi, rdx
0x18001bee2  call    cs:__imp_CoTaskMemAlloc
0x18001bee8  test    rax, rax
0x18001beeb  jnz     short loc_18001BEF4
0x18001beed  mov     eax, 8007000Eh
0x18001bef2  jmp     short loc_18001BF16
0x18001bef4  movups  xmm0, xmmword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data1
0x18001befb  movdqu  xmmword ptr [rax], xmm0
0x18001beff  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001bf06  movdqu  xmmword ptr [rax+10h], xmm1
0x18001bf0b  mov     dword ptr [rdi], 2
0x18001bf11  mov     [rbx], rax
0x18001bf14  xor     eax, eax
0x18001bf16  mov     rbx, [rsp+28h+arg_0]
0x18001bf1b  add     rsp, 20h
0x18001bf1f  pop     rdi
0x18001bf20  retn
```
