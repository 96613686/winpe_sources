# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUnknown>::GetIids(ulong *,_GUID * *)

- ea: `0x180070550`
- end: `0x1800705bd`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180070550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180070572`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IUnknown>::GetIids(
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
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v5[1] = GUID_00000000_0000_0000_c000_000000000046;
  v5[2] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180070550  mov     [rsp+arg_0], rbx
0x180070555  push    rdi
0x180070556  sub     rsp, 20h
0x18007055a  mov     qword ptr [r8], 0
0x180070561  mov     ecx, 30h ; '0'; cb
0x180070566  mov     dword ptr [rdx], 0
0x18007056c  mov     rbx, r8
0x18007056f  mov     rdi, rdx
0x180070572  call    cs:__imp_CoTaskMemAlloc
0x180070578  test    rax, rax
0x18007057b  jnz     short loc_180070584
0x18007057d  mov     eax, 8007000Eh
0x180070582  jmp     short loc_1800705B2
0x180070584  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18007058b  movdqu  xmmword ptr [rax], xmm0
0x18007058f  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x180070596  movdqu  xmmword ptr [rax+10h], xmm1
0x18007059b  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800705a2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800705a7  mov     dword ptr [rdi], 3
0x1800705ad  mov     [rbx], rax
0x1800705b0  xor     eax, eax
0x1800705b2  mov     rbx, [rsp+28h+arg_0]
0x1800705b7  add     rsp, 20h
0x1800705bb  pop     rdi
0x1800705bc  retn
```
