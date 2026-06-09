# XMLScrSite::SetRuntimeExample(ushort *)

- ea: `0x140011a60`
- end: `0x140011b14`
- name: `?SetRuntimeExample@XMLScrSite@@UEAAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140011a60`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::SetRuntimeExample(XMLScrSite *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 2);
  v6 = 0;
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v2 + 624) + 128LL))(*(_QWORD *)(v2 + 624), &v6);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IWshRuntime, &v7);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 56LL))(v7, a2);
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140011a60  mov     r11, rsp
0x140011a63  mov     [r11+10h], rbx
0x140011a67  push    rdi
0x140011a68  sub     rsp, 20h
0x140011a6c  mov     rax, [rcx+10h]
0x140011a70  mov     rdi, rdx
0x140011a73  mov     qword ptr [r11+8], 0
0x140011a7b  lea     rdx, [r11+8]
0x140011a7f  mov     qword ptr [r11+18h], 0
0x140011a87  mov     rcx, [rax+270h]
0x140011a8e  mov     rax, [rcx]
0x140011a91  mov     rax, [rax+80h]
0x140011a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a9d  mov     ebx, eax
0x140011a9f  test    eax, eax
0x140011aa1  js      short loc_140011ADB
0x140011aa3  mov     rcx, [rsp+28h+arg_0]
0x140011aa8  lea     r8, [rsp+28h+arg_10]
0x140011aad  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x140011ab4  mov     rax, [rcx]
0x140011ab7  mov     rax, [rax]
0x140011aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011abf  mov     ebx, eax
0x140011ac1  test    eax, eax
0x140011ac3  js      short loc_140011ADB
0x140011ac5  mov     rcx, [rsp+28h+arg_10]
0x140011aca  mov     rdx, rdi
0x140011acd  mov     rax, [rcx]
0x140011ad0  mov     rax, [rax+38h]
0x140011ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011ad9  mov     ebx, eax
0x140011adb  mov     rcx, [rsp+28h+arg_0]
0x140011ae0  test    rcx, rcx
0x140011ae3  jz      short loc_140011AF1
0x140011ae5  mov     rax, [rcx]
0x140011ae8  mov     rax, [rax+10h]
0x140011aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011af1  mov     rcx, [rsp+28h+arg_10]
0x140011af6  test    rcx, rcx
0x140011af9  jz      short loc_140011B07
0x140011afb  mov     rax, [rcx]
0x140011afe  mov     rax, [rax+10h]
0x140011b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b07  mov     eax, ebx
0x140011b09  mov     rbx, [rsp+28h+arg_8]
0x140011b0e  add     rsp, 20h
0x140011b12  pop     rdi
0x140011b13  retn
```
