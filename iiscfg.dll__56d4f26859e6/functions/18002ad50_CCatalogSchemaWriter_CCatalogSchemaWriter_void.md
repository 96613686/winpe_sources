# CCatalogSchemaWriter::~CCatalogSchemaWriter(void)

- ea: `0x18002ad50`
- end: `0x18002adc4`
- name: `??1CCatalogSchemaWriter@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CCatalogSchemaWriter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180023dc0`
- `0x180023e00`

## callees

- `0x18002ad50`
- `0x18002af50`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ad85`
- `ole32!CoTaskMemFree` at `0x18002ad9f`
- `ole32!CoTaskMemFree` at `0x18002ad85`
- `ole32!CoTaskMemFree` at `0x18002ad9f`

## pseudocode

```c
void __fastcall CCatalogSchemaWriter::~CCatalogSchemaWriter(LPVOID *this)
{
  _DWORD *v1; // rdi
  __int64 i; // rsi
  void *v4; // rbp

  v1 = (_DWORD *)this + 3;
  if ( *this )
  {
    for ( i = 0; (unsigned int)i < *v1; i = (unsigned int)(i + 1) )
    {
      v4 = (void *)*((_QWORD *)*this + i);
      if ( v4 )
      {
        CCatalogCollectionWriter::~CCatalogCollectionWriter(*((CCatalogCollectionWriter **)*this + i));
        CoTaskMemFree(v4);
        *((_QWORD *)*this + i) = 0;
      }
    }
    CoTaskMemFree(*this);
    *this = 0;
  }
  *((_DWORD *)this + 2) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x18002ad50  push    rbx
0x18002ad52  push    rbp
0x18002ad53  push    rsi
0x18002ad54  push    rdi
0x18002ad55  push    r14
0x18002ad57  sub     rsp, 20h
0x18002ad5b  cmp     qword ptr [rcx], 0
0x18002ad5f  lea     rdi, [rcx+0Ch]
0x18002ad63  mov     rbx, rcx
0x18002ad66  jz      short loc_18002ADAC
0x18002ad68  xor     esi, esi
0x18002ad6a  cmp     [rdi], esi
0x18002ad6c  jbe     short loc_18002AD9C
0x18002ad6e  mov     rax, [rbx]
0x18002ad71  mov     rbp, [rax+rsi*8]
0x18002ad75  test    rbp, rbp
0x18002ad78  jz      short loc_18002AD96
0x18002ad7a  mov     rcx, rbp; this
0x18002ad7d  call    ??1CCatalogCollectionWriter@@QEAA@XZ; CCatalogCollectionWriter::~CCatalogCollectionWriter(void)
0x18002ad82  mov     rcx, rbp; pv
0x18002ad85  call    cs:__imp_CoTaskMemFree
0x18002ad8b  mov     rax, [rbx]
0x18002ad8e  mov     qword ptr [rax+rsi*8], 0
0x18002ad96  inc     esi
0x18002ad98  cmp     esi, [rdi]
0x18002ad9a  jb      short loc_18002AD6E
0x18002ad9c  mov     rcx, [rbx]; pv
0x18002ad9f  call    cs:__imp_CoTaskMemFree
0x18002ada5  mov     qword ptr [rbx], 0
0x18002adac  mov     dword ptr [rbx+8], 0
0x18002adb3  mov     dword ptr [rdi], 0
0x18002adb9  add     rsp, 20h
0x18002adbd  pop     r14
0x18002adbf  pop     rdi
0x18002adc0  pop     rsi
0x18002adc1  pop     rbp
0x18002adc2  pop     rbx
0x18002adc3  retn
```
