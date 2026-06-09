# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x180011e34`
- end: `0x180011e99`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025fc1`

## callees

- `0x180003618`
- `0x180011e34`
- `0x180011eec`

## pseudocode

```c
__int64 __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        void ****a1)
{
  void ***v1; // rdx
  void **v3; // rdi
  void **v4; // rbx

  v1 = *a1;
  *(*a1)[1] = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (void **)*v3;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(v3 + 2);
      std::_Deallocate<16>(v3, 160);
      v3 = v4;
    }
    while ( v4 );
  }
  return std::_Deallocate<16>(*a1, 160);
}

```

## disassembly

```asm
0x180011e34  mov     [rsp+arg_0], rbx
0x180011e39  mov     [rsp+arg_8], rsi
0x180011e3e  push    rdi
0x180011e3f  sub     rsp, 20h
0x180011e43  mov     rdx, [rcx]
0x180011e46  mov     rsi, rcx
0x180011e49  mov     rax, [rdx+8]
0x180011e4d  mov     qword ptr [rax], 0
0x180011e54  mov     rdi, [rdx]
0x180011e57  test    rdi, rdi
0x180011e5a  jz      short loc_180011E7D
0x180011e5c  mov     rbx, [rdi]
0x180011e5f  lea     rcx, [rdi+10h]; this
0x180011e63  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180011e68  mov     edx, 0A0h
0x180011e6d  mov     rcx, rdi
0x180011e70  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011e75  mov     rdi, rbx
0x180011e78  test    rbx, rbx
0x180011e7b  jnz     short loc_180011E5C
0x180011e7d  mov     rcx, [rsi]
0x180011e80  mov     edx, 0A0h
0x180011e85  mov     rbx, [rsp+28h+arg_0]
0x180011e8a  mov     rsi, [rsp+28h+arg_8]
0x180011e8f  add     rsp, 20h
0x180011e93  pop     rdi
0x180011e94  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
