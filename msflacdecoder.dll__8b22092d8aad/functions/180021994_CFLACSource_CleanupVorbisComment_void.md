# CFLACSource::CleanupVorbisComment(void)

- ea: `0x180021994`
- end: `0x180021a29`
- name: `?CleanupVorbisComment@CFLACSource@@AEAAXXZ`
- size: `149`
- prototype: `void __fastcall(CFLACSource *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180026d90`

## callees

- `0x1800018e4`
- `0x180021994`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219dd`

## pseudocode

```c
void __fastcall CFLACSource::CleanupVorbisComment(CFLACSource *this)
{
  int v2; // eax
  int v3; // edi
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  if ( *((_QWORD *)this + 71) )
  {
    v2 = *((_DWORD *)this + 140);
    if ( v2 )
    {
      v3 = 0;
      if ( v2 > 0 )
      {
        do
        {
          v4 = *((_QWORD *)this + 71);
          if ( !*(_DWORD *)(v4 + 16LL * v3) )
            break;
          v5 = *(void **)(v4 + 16LL * v3 + 8);
          if ( v5 )
          {
            CoTaskMemFree(v5);
            *(_QWORD *)(*((_QWORD *)this + 71) + 16LL * v3 + 8) = 0;
          }
          ++v3;
        }
        while ( v3 < *((_DWORD *)this + 140) );
      }
    }
  }
  v6 = (void *)*((_QWORD *)this + 71);
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 71) = 0;
  }
}

```

## disassembly

```asm
0x180021994  mov     [rsp+arg_0], rbx
0x180021999  mov     [rsp+arg_8], rsi
0x18002199e  push    rdi
0x18002199f  sub     rsp, 20h
0x1800219a3  cmp     qword ptr [rcx+238h], 0
0x1800219ab  mov     rbx, rcx
0x1800219ae  jz      short loc_1800219FD
0x1800219b0  mov     eax, [rcx+230h]
0x1800219b6  test    eax, eax
0x1800219b8  jz      short loc_1800219FD
0x1800219ba  xor     edi, edi
0x1800219bc  test    eax, eax
0x1800219be  jle     short loc_1800219FD
0x1800219c0  mov     rcx, [rbx+238h]
0x1800219c7  movsxd  rsi, edi
0x1800219ca  add     rsi, rsi
0x1800219cd  cmp     dword ptr [rcx+rsi*8], 0
0x1800219d1  jz      short loc_1800219FD
0x1800219d3  mov     rcx, [rcx+rsi*8+8]; pv
0x1800219d8  test    rcx, rcx
0x1800219db  jz      short loc_1800219F3
0x1800219dd  call    cs:__imp_CoTaskMemFree
0x1800219e3  mov     rax, [rbx+238h]
0x1800219ea  mov     qword ptr [rax+rsi*8+8], 0
0x1800219f3  inc     edi
0x1800219f5  cmp     edi, [rbx+230h]
0x1800219fb  jl      short loc_1800219C0
0x1800219fd  mov     rcx, [rbx+238h]; Block
0x180021a04  test    rcx, rcx
0x180021a07  jz      short loc_180021A19
0x180021a09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021a0e  mov     qword ptr [rbx+238h], 0
0x180021a19  mov     rbx, [rsp+28h+arg_0]
0x180021a1e  mov     rsi, [rsp+28h+arg_8]
0x180021a23  add     rsp, 20h
0x180021a27  pop     rdi
0x180021a28  retn
```
