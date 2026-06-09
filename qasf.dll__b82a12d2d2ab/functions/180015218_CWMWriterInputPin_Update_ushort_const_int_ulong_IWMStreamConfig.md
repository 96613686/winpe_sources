# CWMWriterInputPin::Update(ushort const *,int,ulong,IWMStreamConfig *)

- ea: `0x180015218`
- end: `0x1800152e7`
- name: `?Update@CWMWriterInputPin@@QEAAJPEBGHKPEAUIWMStreamConfig@@@Z`
- size: `207`
- prototype: `__int64 __usercall@<rax>(CWMWriterInputPin *__hidden this@<rcx>, const unsigned __int16 *Src@<rdx>, int@<r8d>, unsigned int@<r9d>, struct IWMStreamConfig *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000e444`

## callees

- `0x180001008`
- `0x180001014`
- `0x1800138bc`
- `0x180015218`
- `0x18001e5c5`
- `0x18001f010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180015277`
- `KERNEL32!lstrlenW` at `0x180015277`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::Update(
        CWMWriterInputPin *this,
        const unsigned __int16 *Src,
        int a3,
        int a4,
        struct IWMStreamConfig *a5)
{
  unsigned __int64 v7; // rsi
  void *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi

  *((_DWORD *)this + 99) = a3;
  *((_DWORD *)this + 100) = a3 + 1;
  *((_QWORD *)this + 56) = a5;
  *((_DWORD *)this + 106) = a4;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 116) = 0;
  if ( Src )
  {
    operator delete(*((void **)this + 5));
    v7 = (unsigned int)(lstrlenW(Src) + 1);
    v8 = operator new[](saturated_mul(v7, 2u));
    *((_QWORD *)this + 5) = v8;
    if ( v8 )
      memcpy_0(v8, Src, 2 * v7);
  }
  v9 = CWMWriterInputPin::BuildInputTypeList(this);
  v10 = *((_QWORD *)this + 56);
  v11 = v9;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  return v11;
}

```

## disassembly

```asm
0x180015218  mov     [rsp+arg_0], rbx
0x18001521d  mov     [rsp+arg_8], rsi
0x180015222  push    rdi
0x180015223  sub     rsp, 20h
0x180015227  mov     [rcx+18Ch], r8d
0x18001522e  lea     eax, [r8+1]
0x180015232  mov     [rcx+190h], eax
0x180015238  mov     rdi, rdx
0x18001523b  mov     rax, [rsp+28h+arg_20]
0x180015240  mov     rbx, rcx
0x180015243  mov     [rcx+1C0h], rax
0x18001524a  mov     [rcx+1A8h], r9d
0x180015251  mov     qword ptr [rcx+1C8h], 0
0x18001525c  mov     dword ptr [rcx+1D0h], 0
0x180015266  test    rdx, rdx
0x180015269  jz      short loc_1800152B3
0x18001526b  mov     rcx, [rcx+28h]; void *
0x18001526f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015274  mov     rcx, rdi; lpString
0x180015277  call    cs:__imp_lstrlenW
0x18001527d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015284  lea     esi, [rax+1]
0x180015287  mov     eax, 2
0x18001528c  mul     rsi
0x18001528f  cmovb   rax, rcx
0x180015293  mov     rcx, rax; unsigned __int64
0x180015296  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001529b  mov     [rbx+28h], rax
0x18001529f  test    rax, rax
0x1800152a2  jz      short loc_1800152B3
0x1800152a4  lea     r8, [rsi+rsi]; Size
0x1800152a8  mov     rdx, rdi; Src
0x1800152ab  mov     rcx, rax; void *
0x1800152ae  call    memcpy_0
0x1800152b3  mov     rcx, rbx; this
0x1800152b6  call    ?BuildInputTypeList@CWMWriterInputPin@@QEAAJXZ; CWMWriterInputPin::BuildInputTypeList(void)
0x1800152bb  mov     rcx, [rbx+1C0h]
0x1800152c2  mov     edi, eax
0x1800152c4  test    rcx, rcx
0x1800152c7  jz      short loc_1800152D5
0x1800152c9  mov     rdx, [rcx]
0x1800152cc  mov     rax, [rdx+8]
0x1800152d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152d5  mov     rbx, [rsp+28h+arg_0]
0x1800152da  mov     eax, edi
0x1800152dc  mov     rsi, [rsp+28h+arg_8]
0x1800152e1  add     rsp, 20h
0x1800152e5  pop     rdi
0x1800152e6  retn
```
