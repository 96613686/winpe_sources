# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CMFTBase>::`scalar deleting destructor'(uint)

- ea: `0x180056a10`
- end: `0x180056a50`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCMFTBase@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `64`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180054534`
- `0x180056a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180056a2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180056a2a`

## pseudocode

```c
char *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CMFTBase>::`scalar deleting destructor'(
        char *Block,
        char a2)
{
  *((_DWORD *)Block + 17) = -1073741823;
  DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 24));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180056a10  mov     [rsp+arg_0], rbx
0x180056a15  push    rdi
0x180056a16  sub     rsp, 20h
0x180056a1a  mov     rdi, rcx
0x180056a1d  mov     dword ptr [rcx+44h], 0C0000001h
0x180056a24  add     rcx, 18h; lpCriticalSection
0x180056a28  mov     ebx, edx
0x180056a2a  call    cs:__imp_DeleteCriticalSection
0x180056a30  test    bl, 1
0x180056a33  jz      short loc_180056A42
0x180056a35  mov     edx, 48h ; 'H'
0x180056a3a  mov     rcx, rdi; Block
0x180056a3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056a42  mov     rbx, [rsp+28h+arg_0]
0x180056a47  mov     rax, rdi
0x180056a4a  add     rsp, 20h
0x180056a4e  pop     rdi
0x180056a4f  retn
```
