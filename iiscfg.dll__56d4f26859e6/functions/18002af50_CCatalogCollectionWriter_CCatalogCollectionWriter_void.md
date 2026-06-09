# CCatalogCollectionWriter::~CCatalogCollectionWriter(void)

- ea: `0x18002af50`
- end: `0x18002afde`
- name: `??1CCatalogCollectionWriter@@QEAA@XZ`
- size: `142`
- prototype: `void __fastcall(CCatalogCollectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002ad50`

## callees

- `0x18002af50`
- `0x18002b4ec`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002af90`
- `ole32!CoTaskMemFree` at `0x18002afb2`
- `ole32!CoTaskMemFree` at `0x18002af90`
- `ole32!CoTaskMemFree` at `0x18002afb2`

## pseudocode

```c
void __fastcall CCatalogCollectionWriter::~CCatalogCollectionWriter(CCatalogCollectionWriter *this)
{
  _DWORD *v1; // rdi
  __int64 i; // rsi
  __int64 v4; // rax
  void *v5; // rbp

  v1 = (_DWORD *)((char *)this + 156);
  if ( *((_QWORD *)this + 18) )
  {
    for ( i = 0; (unsigned int)i < *v1; i = (unsigned int)(i + 1) )
    {
      v4 = *((_QWORD *)this + 18);
      v5 = *(void **)(v4 + 8 * i);
      if ( v5 )
      {
        CCatalogPropertyWriter::~CCatalogPropertyWriter(*(CCatalogPropertyWriter **)(v4 + 8 * i));
        CoTaskMemFree(v5);
        *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)this + 18));
    *((_QWORD *)this + 18) = 0;
  }
  *((_DWORD *)this + 38) = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x18002af50  push    rbx
0x18002af52  push    rbp
0x18002af53  push    rsi
0x18002af54  push    rdi
0x18002af55  push    r14
0x18002af57  sub     rsp, 20h
0x18002af5b  cmp     qword ptr [rcx+90h], 0
0x18002af63  lea     rdi, [rcx+9Ch]
0x18002af6a  mov     rbx, rcx
0x18002af6d  jz      short loc_18002AFC3
0x18002af6f  xor     esi, esi
0x18002af71  cmp     [rdi], esi
0x18002af73  jbe     short loc_18002AFAB
0x18002af75  mov     rax, [rbx+90h]
0x18002af7c  mov     rbp, [rax+rsi*8]
0x18002af80  test    rbp, rbp
0x18002af83  jz      short loc_18002AFA5
0x18002af85  mov     rcx, rbp; this
0x18002af88  call    ??1CCatalogPropertyWriter@@QEAA@XZ; CCatalogPropertyWriter::~CCatalogPropertyWriter(void)
0x18002af8d  mov     rcx, rbp; pv
0x18002af90  call    cs:__imp_CoTaskMemFree
0x18002af96  mov     rax, [rbx+90h]
0x18002af9d  mov     qword ptr [rax+rsi*8], 0
0x18002afa5  inc     esi
0x18002afa7  cmp     esi, [rdi]
0x18002afa9  jb      short loc_18002AF75
0x18002afab  mov     rcx, [rbx+90h]; pv
0x18002afb2  call    cs:__imp_CoTaskMemFree
0x18002afb8  mov     qword ptr [rbx+90h], 0
0x18002afc3  mov     dword ptr [rbx+98h], 0
0x18002afcd  mov     dword ptr [rdi], 0
0x18002afd3  add     rsp, 20h
0x18002afd7  pop     r14
0x18002afd9  pop     rdi
0x18002afda  pop     rsi
0x18002afdb  pop     rbp
0x18002afdc  pop     rbx
0x18002afdd  retn
```
