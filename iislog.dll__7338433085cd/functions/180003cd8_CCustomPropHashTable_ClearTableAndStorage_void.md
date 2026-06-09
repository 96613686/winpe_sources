# CCustomPropHashTable::ClearTableAndStorage(void)

- ea: `0x180003cd8`
- end: `0x180003d40`
- name: `?ClearTableAndStorage@CCustomPropHashTable@@QEAAXXZ`
- size: `104`
- prototype: `void __fastcall(CCustomPropHashTable *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003984`
- `0x180004044`
- `0x180004a5c`

## callees

- `0x180001048`
- `0x180003ab4`
- `0x180003cd8`

## import_xrefs

- `IisRTL!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003ce5`
- `IisRTL!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003ce5`

## pseudocode

```c
void __fastcall CCustomPropHashTable::ClearTableAndStorage(CCustomPropHashTable *this)
{
  __int64 v2; // rax
  void *v3; // r14
  __int64 v4; // rdi
  LOG_PROPERTY_INFO *i; // rsi

  CLKRHashTable::Clear(this);
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    v3 = (void *)(v2 - 8);
    v4 = *(_QWORD *)(v2 - 8);
    for ( i = (LOG_PROPERTY_INFO *)(v2 + 136 * v4); v4; --v4 )
    {
      i = (LOG_PROPERTY_INFO *)((char *)i - 136);
      LOG_PROPERTY_INFO::~LOG_PROPERTY_INFO(i);
    }
    operator delete(v3);
    *((_QWORD *)this + 9) = 0;
  }
  *((_DWORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x180003cd8  push    rbx
0x180003cda  push    rsi
0x180003cdb  push    rdi
0x180003cdc  push    r14
0x180003cde  sub     rsp, 28h
0x180003ce2  mov     rbx, rcx
0x180003ce5  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180003ceb  mov     rax, [rbx+48h]
0x180003cef  test    rax, rax
0x180003cf2  jz      short loc_180003D2F
0x180003cf4  lea     r14, [rax-8]
0x180003cf8  mov     rdi, [r14]
0x180003cfb  imul    rsi, rdi, 88h
0x180003d02  add     rsi, rax
0x180003d05  test    rdi, rdi
0x180003d08  jz      short loc_180003D1F
0x180003d0a  sub     rsi, 88h
0x180003d11  mov     rcx, rsi; this
0x180003d14  call    ??1LOG_PROPERTY_INFO@@QEAA@XZ; LOG_PROPERTY_INFO::~LOG_PROPERTY_INFO(void)
0x180003d19  sub     rdi, 1
0x180003d1d  jnz     short loc_180003D0A
0x180003d1f  mov     rcx, r14; Block
0x180003d22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003d27  mov     qword ptr [rbx+48h], 0
0x180003d2f  mov     dword ptr [rbx+50h], 0
0x180003d36  add     rsp, 28h
0x180003d3a  pop     r14
0x180003d3c  pop     rdi
0x180003d3d  pop     rsi
0x180003d3e  pop     rbx
0x180003d3f  retn
```
