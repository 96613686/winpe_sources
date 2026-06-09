# XMLScrSite::SetRuntimeDescription(ushort *)

- ea: `0x1400119a0`
- end: `0x140011a54`
- name: `?SetRuntimeDescription@XMLScrSite@@UEAAJPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400119a0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::SetRuntimeDescription(XMLScrSite *this, unsigned __int16 *a2)
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
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 48LL))(v7, a2);
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
0x1400119a0  mov     r11, rsp
0x1400119a3  mov     [r11+10h], rbx
0x1400119a7  push    rdi
0x1400119a8  sub     rsp, 20h
0x1400119ac  mov     rax, [rcx+10h]
0x1400119b0  mov     rdi, rdx
0x1400119b3  mov     qword ptr [r11+8], 0
0x1400119bb  lea     rdx, [r11+8]
0x1400119bf  mov     qword ptr [r11+18h], 0
0x1400119c7  mov     rcx, [rax+270h]
0x1400119ce  mov     rax, [rcx]
0x1400119d1  mov     rax, [rax+80h]
0x1400119d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400119dd  mov     ebx, eax
0x1400119df  test    eax, eax
0x1400119e1  js      short loc_140011A1B
0x1400119e3  mov     rcx, [rsp+28h+arg_0]
0x1400119e8  lea     r8, [rsp+28h+arg_10]
0x1400119ed  lea     rdx, ?IID_IWshRuntime@@3U_GUID@@B; _GUID const IID_IWshRuntime
0x1400119f4  mov     rax, [rcx]
0x1400119f7  mov     rax, [rax]
0x1400119fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400119ff  mov     ebx, eax
0x140011a01  test    eax, eax
0x140011a03  js      short loc_140011A1B
0x140011a05  mov     rcx, [rsp+28h+arg_10]
0x140011a0a  mov     rdx, rdi
0x140011a0d  mov     rax, [rcx]
0x140011a10  mov     rax, [rax+30h]
0x140011a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a19  mov     ebx, eax
0x140011a1b  mov     rcx, [rsp+28h+arg_0]
0x140011a20  test    rcx, rcx
0x140011a23  jz      short loc_140011A31
0x140011a25  mov     rax, [rcx]
0x140011a28  mov     rax, [rax+10h]
0x140011a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a31  mov     rcx, [rsp+28h+arg_10]
0x140011a36  test    rcx, rcx
0x140011a39  jz      short loc_140011A47
0x140011a3b  mov     rax, [rcx]
0x140011a3e  mov     rax, [rax+10h]
0x140011a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a47  mov     eax, ebx
0x140011a49  mov     rbx, [rsp+28h+arg_8]
0x140011a4e  add     rsp, 20h
0x140011a52  pop     rdi
0x140011a53  retn
```
