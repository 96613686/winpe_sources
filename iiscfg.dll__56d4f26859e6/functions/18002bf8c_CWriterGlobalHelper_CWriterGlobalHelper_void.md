# CWriterGlobalHelper::~CWriterGlobalHelper(void)

- ea: `0x18002bf8c`
- end: `0x18002c126`
- name: `??1CWriterGlobalHelper@@QEAA@XZ`
- size: `410`
- prototype: `void __fastcall(CWriterGlobalHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a39c`

## callees

- `0x18002bf8c`
- `0x18002d78c`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c097`
- `ole32!CoTaskMemFree` at `0x18002c0b6`
- `ole32!CoTaskMemFree` at `0x18002c0d5`
- `ole32!CoTaskMemFree` at `0x18002c0f4`
- `ole32!CoTaskMemFree` at `0x18002c10e`
- `ole32!CoTaskMemFree` at `0x18002c097`
- `ole32!CoTaskMemFree` at `0x18002c0b6`
- `ole32!CoTaskMemFree` at `0x18002c0d5`
- `ole32!CoTaskMemFree` at `0x18002c0f4`
- `ole32!CoTaskMemFree` at `0x18002c10e`

## pseudocode

```c
void __fastcall CWriterGlobalHelper::~CWriterGlobalHelper(CWriterGlobalHelper *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  struct IMetabaseSchemaCompiler *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)this = 0;
  }
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 4) = 0;
  }
  v7 = *((_QWORD *)this + 5);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 5) = 0;
  }
  v8 = *((_QWORD *)this + 6);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 6) = 0;
  }
  v9 = *((_QWORD *)this + 7);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 7) = 0;
  }
  v10 = (struct IMetabaseSchemaCompiler *)*((_QWORD *)this + 8);
  if ( v10 )
  {
    (*(void (__fastcall **)(struct IMetabaseSchemaCompiler *))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 8) = 0;
  }
  if ( *((_QWORD *)this + 31) )
    ReleaseBinFile(v10, (unsigned __int16 **)this + 31);
  v11 = (void *)*((_QWORD *)this + 33);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)this + 33) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 35);
  *((_DWORD *)this + 68) = 0;
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)this + 35) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 37);
  *((_DWORD *)this + 72) = 0;
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 37) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 39);
  *((_DWORD *)this + 76) = 0;
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)this + 39) = 0;
  }
  *((_DWORD *)this + 80) = 0;
  CoTaskMemFree(*((LPVOID *)this + 41));
  *((_QWORD *)this + 41) = 0;
}

```

## disassembly

```asm
0x18002bf8c  mov     [rsp+arg_0], rbx
0x18002bf91  push    rdi
0x18002bf92  sub     rsp, 20h
0x18002bf96  mov     rbx, rcx
0x18002bf99  xor     edi, edi
0x18002bf9b  mov     rcx, [rcx]
0x18002bf9e  test    rcx, rcx
0x18002bfa1  jz      short loc_18002BFB2
0x18002bfa3  mov     rax, [rcx]
0x18002bfa6  mov     rax, [rax+10h]
0x18002bfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfaf  mov     [rbx], rdi
0x18002bfb2  mov     rcx, [rbx+8]
0x18002bfb6  test    rcx, rcx
0x18002bfb9  jz      short loc_18002BFCB
0x18002bfbb  mov     rax, [rcx]
0x18002bfbe  mov     rax, [rax+10h]
0x18002bfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfc7  mov     [rbx+8], rdi
0x18002bfcb  mov     rcx, [rbx+10h]
0x18002bfcf  test    rcx, rcx
0x18002bfd2  jz      short loc_18002BFE4
0x18002bfd4  mov     rax, [rcx]
0x18002bfd7  mov     rax, [rax+10h]
0x18002bfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfe0  mov     [rbx+10h], rdi
0x18002bfe4  mov     rcx, [rbx+18h]
0x18002bfe8  test    rcx, rcx
0x18002bfeb  jz      short loc_18002BFFD
0x18002bfed  mov     rax, [rcx]
0x18002bff0  mov     rax, [rax+10h]
0x18002bff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bff9  mov     [rbx+18h], rdi
0x18002bffd  mov     rcx, [rbx+20h]
0x18002c001  test    rcx, rcx
0x18002c004  jz      short loc_18002C016
0x18002c006  mov     rax, [rcx]
0x18002c009  mov     rax, [rax+10h]
0x18002c00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c012  mov     [rbx+20h], rdi
0x18002c016  mov     rcx, [rbx+28h]
0x18002c01a  test    rcx, rcx
0x18002c01d  jz      short loc_18002C02F
0x18002c01f  mov     rax, [rcx]
0x18002c022  mov     rax, [rax+10h]
0x18002c026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c02b  mov     [rbx+28h], rdi
0x18002c02f  mov     rcx, [rbx+30h]
0x18002c033  test    rcx, rcx
0x18002c036  jz      short loc_18002C048
0x18002c038  mov     rax, [rcx]
0x18002c03b  mov     rax, [rax+10h]
0x18002c03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c044  mov     [rbx+30h], rdi
0x18002c048  mov     rcx, [rbx+38h]
0x18002c04c  test    rcx, rcx
0x18002c04f  jz      short loc_18002C061
0x18002c051  mov     rax, [rcx]
0x18002c054  mov     rax, [rax+10h]
0x18002c058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c05d  mov     [rbx+38h], rdi
0x18002c061  mov     rcx, [rbx+40h]
0x18002c065  test    rcx, rcx
0x18002c068  jz      short loc_18002C07A
0x18002c06a  mov     rax, [rcx]
0x18002c06d  mov     rax, [rax+10h]
0x18002c071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c076  mov     [rbx+40h], rdi
0x18002c07a  lea     rdx, [rbx+0F8h]; unsigned __int16 **
0x18002c081  cmp     [rdx], rdi
0x18002c084  jz      short loc_18002C08B
0x18002c086  call    ?ReleaseBinFile@@YAXPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z; ReleaseBinFile(IMetabaseSchemaCompiler *,ushort * *)
0x18002c08b  mov     rcx, [rbx+108h]; pv
0x18002c092  test    rcx, rcx
0x18002c095  jz      short loc_18002C0A4
0x18002c097  call    cs:__imp_CoTaskMemFree
0x18002c09d  mov     [rbx+108h], rdi
0x18002c0a4  mov     rcx, [rbx+118h]; pv
0x18002c0ab  mov     [rbx+110h], edi
0x18002c0b1  test    rcx, rcx
0x18002c0b4  jz      short loc_18002C0C3
0x18002c0b6  call    cs:__imp_CoTaskMemFree
0x18002c0bc  mov     [rbx+118h], rdi
0x18002c0c3  mov     rcx, [rbx+128h]; pv
0x18002c0ca  mov     [rbx+120h], edi
0x18002c0d0  test    rcx, rcx
0x18002c0d3  jz      short loc_18002C0E2
0x18002c0d5  call    cs:__imp_CoTaskMemFree
0x18002c0db  mov     [rbx+128h], rdi
0x18002c0e2  mov     rcx, [rbx+138h]; pv
0x18002c0e9  mov     [rbx+130h], edi
0x18002c0ef  test    rcx, rcx
0x18002c0f2  jz      short loc_18002C101
0x18002c0f4  call    cs:__imp_CoTaskMemFree
0x18002c0fa  mov     [rbx+138h], rdi
0x18002c101  mov     [rbx+140h], edi
0x18002c107  mov     rcx, [rbx+148h]; pv
0x18002c10e  call    cs:__imp_CoTaskMemFree
0x18002c114  mov     [rbx+148h], rdi
0x18002c11b  mov     rbx, [rsp+28h+arg_0]
0x18002c120  add     rsp, 20h
0x18002c124  pop     rdi
0x18002c125  retn
```
