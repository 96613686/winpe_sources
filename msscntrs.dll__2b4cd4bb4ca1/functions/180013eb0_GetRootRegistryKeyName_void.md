# GetRootRegistryKeyName(void)

- ea: `0x180013eb0`
- end: `0x180013ef5`
- name: `?GetRootRegistryKeyName@@YA?AV?$TLMString@$0CA@$0CA@$0EAA@@@XZ`
- size: `69`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800111b0`
- `0x180011500`

## callees

- `0x1800120e4`

## pseudocode

```c
__int64 __fastcall GetRootRegistryKeyName(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = 33;
  *(_QWORD *)a1 = &CLMString::`vftable';
  *(_QWORD *)(a1 + 8) = a1 + 24;
  CLMString::AssignInConstructor((CLMString *)a1, L"Software\\Microsoft\\Windows Search", 0xFFFFFFFF);
  *(_QWORD *)a1 = &TLMString<32,32,1024>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180013eb0  push    rbx
0x180013eb2  sub     rsp, 30h
0x180013eb6  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180013ebd  mov     dword ptr [rcx+10h], 21h ; '!'
0x180013ec4  mov     [rcx], rax
0x180013ec7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows Search"
0x180013ece  lea     rax, [rcx+18h]
0x180013ed2  or      r8d, 0FFFFFFFFh; unsigned int
0x180013ed6  mov     [rcx+8], rax
0x180013eda  mov     rbx, rcx
0x180013edd  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180013ee2  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x180013ee9  mov     [rbx], rax
0x180013eec  mov     rax, rbx
0x180013eef  add     rsp, 30h
0x180013ef3  pop     rbx
0x180013ef4  retn
```
