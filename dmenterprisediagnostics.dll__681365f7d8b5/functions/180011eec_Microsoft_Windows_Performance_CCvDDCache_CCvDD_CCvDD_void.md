# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x180011eec`
- end: `0x180011f47`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011d0c`
- `0x180011e34`
- `0x180011f50`
- `0x1800123fc`
- `0x18001266c`
- `0x18002603e`
- `0x180026086`

## callees

- `0x180001824`
- `0x180003b14`
- `0x1800188e8`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void **this)
{
  std::vector<unsigned char>::_Tidy(this + 12);
  operator delete(this[11]);
  this[11] = 0;
  operator delete(this[10]);
  this[10] = 0;
  operator delete(this[9]);
  this[9] = 0;
  std::wstring::~wstring(this + 4);
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x180011eec  push    rbx
0x180011eee  sub     rsp, 20h
0x180011ef2  mov     rbx, rcx
0x180011ef5  add     rcx, 60h ; '`'
0x180011ef9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180011efe  mov     rcx, [rbx+58h]; void *
0x180011f02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011f07  mov     qword ptr [rbx+58h], 0
0x180011f0f  mov     rcx, [rbx+50h]; void *
0x180011f13  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011f18  mov     qword ptr [rbx+50h], 0
0x180011f20  mov     rcx, [rbx+48h]; void *
0x180011f24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011f29  lea     rcx, [rbx+20h]
0x180011f2d  mov     qword ptr [rbx+48h], 0
0x180011f35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f3a  mov     rcx, rbx
0x180011f3d  add     rsp, 20h
0x180011f41  pop     rbx
0x180011f42  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
