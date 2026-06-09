# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x180011674`
- end: `0x1800116d9`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800250ed`

## callees

- `0x1800035c4`
- `0x180011674`
- `0x180011724`

## pseudocode

```c
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rdi
  _QWORD *v4; // rbx

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v3 + 2));
      std::_Deallocate<16>(v3, 0xA0u);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*a1, 0xA0u);
}

```

## disassembly

```asm
0x180011674  mov     [rsp+arg_0], rbx
0x180011679  mov     [rsp+arg_8], rsi
0x18001167e  push    rdi
0x18001167f  sub     rsp, 20h
0x180011683  mov     rdx, [rcx]
0x180011686  mov     rsi, rcx
0x180011689  mov     rax, [rdx+8]
0x18001168d  mov     qword ptr [rax], 0
0x180011694  mov     rdi, [rdx]
0x180011697  test    rdi, rdi
0x18001169a  jz      short loc_1800116BD
0x18001169c  mov     rbx, [rdi]
0x18001169f  lea     rcx, [rdi+10h]; this
0x1800116a3  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x1800116a8  mov     edx, 0A0h
0x1800116ad  mov     rcx, rdi
0x1800116b0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800116b5  mov     rdi, rbx
0x1800116b8  test    rbx, rbx
0x1800116bb  jnz     short loc_18001169C
0x1800116bd  mov     rcx, [rsi]
0x1800116c0  mov     edx, 0A0h
0x1800116c5  mov     rbx, [rsp+28h+arg_0]
0x1800116ca  mov     rsi, [rsp+28h+arg_8]
0x1800116cf  add     rsp, 20h
0x1800116d3  pop     rdi
0x1800116d4  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
