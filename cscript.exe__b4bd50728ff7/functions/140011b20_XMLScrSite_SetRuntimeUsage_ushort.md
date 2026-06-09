# XMLScrSite::SetRuntimeUsage(ushort *)

- ea: `0x140011b20`
- end: `0x140011bd4`
- name: `?SetRuntimeUsage@XMLScrSite@@UEAAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140011b20`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::SetRuntimeUsage(XMLScrSite *this, unsigned __int16 *a2)
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
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 40LL))(v7, a2);
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
0x140011b20  mov     r11, rsp
0x140011b23  mov     [r11+10h], rbx
0x140011b27  push    rdi
0x140011b28  sub     rsp, 20h
0x140011b2c  mov     rax, [rcx+10h]
0x140011b30  mov     rdi, rdx
0x140011b33  mov     qword ptr [r11+8], 0
0x140011b3b  lea     rdx, [r11+8]
0x140011b3f  mov     qword ptr [r11+18h], 0
0x140011b47  mov     rcx, [rax+270h]
0x140011b4e  mov     rax, [rcx]
0x140011b51  mov     rax, [rax+80h]
0x140011b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b5d  mov     ebx, eax
0x140011b5f  test    eax, eax
0x140011b61  js      short loc_140011B9B
0x140011b63  mov     rcx, [rsp+28h+arg_0]
0x140011b68  lea     r8, [rsp+28h+arg_10]
0x140011b6d  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x140011b74  mov     rax, [rcx]
0x140011b77  mov     rax, [rax]
0x140011b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b7f  mov     ebx, eax
0x140011b81  test    eax, eax
0x140011b83  js      short loc_140011B9B
0x140011b85  mov     rcx, [rsp+28h+arg_10]
0x140011b8a  mov     rdx, rdi
0x140011b8d  mov     rax, [rcx]
0x140011b90  mov     rax, [rax+28h]
0x140011b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b99  mov     ebx, eax
0x140011b9b  mov     rcx, [rsp+28h+arg_0]
0x140011ba0  test    rcx, rcx
0x140011ba3  jz      short loc_140011BB1
0x140011ba5  mov     rax, [rcx]
0x140011ba8  mov     rax, [rax+10h]
0x140011bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bb1  mov     rcx, [rsp+28h+arg_10]
0x140011bb6  test    rcx, rcx
0x140011bb9  jz      short loc_140011BC7
0x140011bbb  mov     rax, [rcx]
0x140011bbe  mov     rax, [rax+10h]
0x140011bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bc7  mov     eax, ebx
0x140011bc9  mov     rbx, [rsp+28h+arg_8]
0x140011bce  add     rsp, 20h
0x140011bd2  pop     rdi
0x140011bd3  retn
```
