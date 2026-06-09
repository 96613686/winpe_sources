# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::IHotKeyClientOwner>::GetIids(ulong *,_GUID * *)

- ea: `0x14000c850`
- end: `0x14000c8b1`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIHotKeyClientOwner@Text@Internal@UI@Windows@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c850`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000c872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000c872`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::IHotKeyClientOwner>::GetIids(
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
  *v5 = GUID_0ba2f71b_20b8_5ab8_98b9_48331301ecdf;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 2;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x14000c850  mov     [rsp+arg_0], rbx
0x14000c855  push    rdi
0x14000c856  sub     rsp, 20h
0x14000c85a  mov     qword ptr [r8], 0
0x14000c861  mov     ecx, 20h ; ' '; cb
0x14000c866  mov     dword ptr [rdx], 0
0x14000c86c  mov     rbx, r8
0x14000c86f  mov     rdi, rdx
0x14000c872  call    cs:__imp_CoTaskMemAlloc
0x14000c878  test    rax, rax
0x14000c87b  jnz     short loc_14000C884
0x14000c87d  mov     eax, 8007000Eh
0x14000c882  jmp     short loc_14000C8A6
0x14000c884  movups  xmm0, xmmword ptr cs:_GUID_0ba2f71b_20b8_5ab8_98b9_48331301ecdf.Data1
0x14000c88b  movdqu  xmmword ptr [rax], xmm0
0x14000c88f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x14000c896  movdqu  xmmword ptr [rax+10h], xmm1
0x14000c89b  mov     dword ptr [rdi], 2
0x14000c8a1  mov     [rbx], rax
0x14000c8a4  xor     eax, eax
0x14000c8a6  mov     rbx, [rsp+28h+arg_0]
0x14000c8ab  add     rsp, 20h
0x14000c8af  pop     rdi
0x14000c8b0  retn
```
