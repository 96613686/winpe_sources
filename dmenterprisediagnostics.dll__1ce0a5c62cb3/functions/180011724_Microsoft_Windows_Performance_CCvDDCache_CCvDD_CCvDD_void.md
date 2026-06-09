# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x180011724`
- end: `0x18001177f`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(void **this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011550`
- `0x180011674`
- `0x180011788`
- `0x180011bfc`
- `0x180011e80`
- `0x180025169`
- `0x1800251b1`

## callees

- `0x180001804`
- `0x180003b10`
- `0x180017ea4`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void **this)
{
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx

  std::vector<unsigned char>::_Tidy(this + 12);
  operator delete(this[11], v2);
  this[11] = 0;
  operator delete(this[10], v3);
  this[10] = 0;
  operator delete(this[9], v4);
  this[9] = 0;
  std::wstring::~wstring((__int64)(this + 4));
  std::wstring::~wstring((__int64)this);
}

```

## disassembly

```asm
0x180011724  push    rbx
0x180011726  sub     rsp, 20h
0x18001172a  mov     rbx, rcx
0x18001172d  add     rcx, 60h ; '`'
0x180011731  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180011736  mov     rcx, [rbx+58h]; void *
0x18001173a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001173f  mov     qword ptr [rbx+58h], 0
0x180011747  mov     rcx, [rbx+50h]; void *
0x18001174b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011750  mov     qword ptr [rbx+50h], 0
0x180011758  mov     rcx, [rbx+48h]; void *
0x18001175c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011761  lea     rcx, [rbx+20h]
0x180011765  mov     qword ptr [rbx+48h], 0
0x18001176d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011772  mov     rcx, rbx
0x180011775  add     rsp, 20h
0x180011779  pop     rbx
0x18001177a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
