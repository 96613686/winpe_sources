# CKsOutputPin2::DestroyMediaTypeArrays(void)

- ea: `0x18002f2b8`
- end: `0x18002f3fc`
- name: `?DestroyMediaTypeArrays@CKsOutputPin2@@QEAAXXZ`
- size: `324`
- prototype: `void __fastcall(CKsOutputPin2 *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18002cd54`
- `0x18002dd70`

## callees

- `0x18001f1c4`
- `0x18002f2b8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002f34b`
- `ole32!CoTaskMemFree` at `0x18002f376`
- `ole32!CoTaskMemFree` at `0x18002f3a7`
- `ole32!CoTaskMemFree` at `0x18002f3ca`
- `ole32!CoTaskMemFree` at `0x18002f34b`
- `ole32!CoTaskMemFree` at `0x18002f376`
- `ole32!CoTaskMemFree` at `0x18002f3a7`
- `ole32!CoTaskMemFree` at `0x18002f3ca`

## pseudocode

```c
void __fastcall CKsOutputPin2::DestroyMediaTypeArrays(CKsOutputPin2 *this, unsigned __int64 a2)
{
  __int64 i; // rdi
  void *v4; // rcx
  bool v5; // zf
  __int64 j; // rdi
  __int64 v7; // rax
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  if ( *((_QWORD *)this + 146) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 294); i = (unsigned int)(i + 1) )
      operator delete(*(void **)(*((_QWORD *)this + 146) + 8 * i), a2);
    v4 = (void *)*((_QWORD *)this + 146);
    if ( v4 )
    {
      operator delete(v4, a2);
      *((_QWORD *)this + 146) = 0;
    }
  }
  v5 = *((_QWORD *)this + 148) == 0;
  *((_DWORD *)this + 294) = 0;
  if ( !v5 )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 300); j = (unsigned int)(j + 1) )
    {
      v7 = *((_QWORD *)this + 149);
      if ( v7 )
      {
        v8 = *(void **)(v7 + 8 * j);
        if ( v8 )
        {
          CoTaskMemFree(v8);
          *(_QWORD *)(*((_QWORD *)this + 149) + 8 * j) = 0;
        }
      }
      v9 = *(void **)(*((_QWORD *)this + 148) + 8 * j);
      if ( v9 )
      {
        CoTaskMemFree(v9);
        *(_QWORD *)(*((_QWORD *)this + 148) + 8 * j) = 0;
      }
    }
    v10 = (void *)*((_QWORD *)this + 149);
    if ( v10 )
    {
      CoTaskMemFree(v10);
      *((_QWORD *)this + 149) = 0;
    }
    v11 = (void *)*((_QWORD *)this + 148);
    if ( v11 )
    {
      CoTaskMemFree(v11);
      *((_QWORD *)this + 148) = 0;
    }
  }
  *((_DWORD *)this + 300) = 0;
}

```

## disassembly

```asm
0x18002f2b8  mov     [rsp+arg_0], rbx
0x18002f2bd  mov     [rsp+arg_8], rsi
0x18002f2c2  push    rdi
0x18002f2c3  sub     rsp, 20h
0x18002f2c7  cmp     qword ptr [rcx+490h], 0
0x18002f2cf  mov     rbx, rcx
0x18002f2d2  jz      short loc_18002F314
0x18002f2d4  xor     edi, edi
0x18002f2d6  cmp     [rcx+498h], edi
0x18002f2dc  jbe     short loc_18002F2F8
0x18002f2de  mov     rcx, [rbx+490h]
0x18002f2e5  mov     rcx, [rcx+rdi*8]; void *
0x18002f2e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002f2ee  inc     edi
0x18002f2f0  cmp     edi, [rbx+498h]
0x18002f2f6  jb      short loc_18002F2DE
0x18002f2f8  mov     rcx, [rbx+490h]; void *
0x18002f2ff  test    rcx, rcx
0x18002f302  jz      short loc_18002F314
0x18002f304  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002f309  mov     qword ptr [rbx+490h], 0
0x18002f314  cmp     qword ptr [rbx+4A0h], 0
0x18002f31c  mov     dword ptr [rbx+498h], 0
0x18002f326  jz      loc_18002F3E1
0x18002f32c  xor     edi, edi
0x18002f32e  cmp     [rbx+4B0h], edi
0x18002f334  jbe     short loc_18002F39B
0x18002f336  mov     rax, [rbx+4A8h]
0x18002f33d  test    rax, rax
0x18002f340  jz      short loc_18002F366
0x18002f342  mov     rcx, [rax+rdi*8]; pv
0x18002f346  test    rcx, rcx
0x18002f349  jz      short loc_18002F366
0x18002f34b  call    cs:__imp_CoTaskMemFree
0x18002f352  nop     dword ptr [rax+rax+00h]
0x18002f357  mov     rax, [rbx+4A8h]
0x18002f35e  mov     qword ptr [rax+rdi*8], 0
0x18002f366  mov     rax, [rbx+4A0h]
0x18002f36d  mov     rcx, [rax+rdi*8]; pv
0x18002f371  test    rcx, rcx
0x18002f374  jz      short loc_18002F391
0x18002f376  call    cs:__imp_CoTaskMemFree
0x18002f37d  nop     dword ptr [rax+rax+00h]
0x18002f382  mov     rax, [rbx+4A0h]
0x18002f389  mov     qword ptr [rax+rdi*8], 0
0x18002f391  inc     edi
0x18002f393  cmp     edi, [rbx+4B0h]
0x18002f399  jb      short loc_18002F336
0x18002f39b  mov     rcx, [rbx+4A8h]; pv
0x18002f3a2  test    rcx, rcx
0x18002f3a5  jz      short loc_18002F3BE
0x18002f3a7  call    cs:__imp_CoTaskMemFree
0x18002f3ae  nop     dword ptr [rax+rax+00h]
0x18002f3b3  mov     qword ptr [rbx+4A8h], 0
0x18002f3be  mov     rcx, [rbx+4A0h]; pv
0x18002f3c5  test    rcx, rcx
0x18002f3c8  jz      short loc_18002F3E1
0x18002f3ca  call    cs:__imp_CoTaskMemFree
0x18002f3d1  nop     dword ptr [rax+rax+00h]
0x18002f3d6  mov     qword ptr [rbx+4A0h], 0
0x18002f3e1  mov     rsi, [rsp+28h+arg_8]
0x18002f3e6  mov     dword ptr [rbx+4B0h], 0
0x18002f3f0  mov     rbx, [rsp+28h+arg_0]
0x18002f3f5  add     rsp, 20h
0x18002f3f9  pop     rdi
0x18002f3fa  retn
```
