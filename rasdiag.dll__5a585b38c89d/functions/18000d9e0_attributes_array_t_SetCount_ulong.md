# _attributes_array_t::SetCount(ulong)

- ea: `0x18000d9e0`
- end: `0x18000da92`
- name: `?SetCount@_attributes_array_t@@QEAAJK@Z`
- size: `178`
- prototype: `__int64 __fastcall(_attributes_array_t *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d100`
- `0x18000d560`

## callees

- `0x18000678c`
- `0x18000d9e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da2b`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::SetCount(_attributes_array_t *this, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v6; // rdi
  _BYTE *v7; // rax

  v2 = a2;
  if ( a2 > 0x1C71C71 )
    return 2147942934LL;
  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 1) + 144 * i));
  }
  CoTaskMemFree(*((LPVOID *)this + 1));
  *((_QWORD *)this + 1) = 0;
  v6 = 144 * v2;
  *(_DWORD *)this = 0;
  v7 = CoTaskMemAlloc(144 * v2);
  *((_QWORD *)this + 1) = v7;
  if ( !v7 )
    return 2147942414LL;
  for ( ; v6; --v6 )
    *v7++ = 0;
  *(_DWORD *)this = v2;
  return 0;
}

```

## disassembly

```asm
0x18000d9e0  mov     [rsp+arg_0], rbx
0x18000d9e5  mov     [rsp+arg_8], rsi
0x18000d9ea  push    rdi
0x18000d9eb  sub     rsp, 20h
0x18000d9ef  mov     esi, edx
0x18000d9f1  mov     rbx, rcx
0x18000d9f4  cmp     edx, 1C71C71h
0x18000d9fa  jbe     short loc_18000DA03
0x18000d9fc  mov     eax, 80070216h
0x18000da01  jmp     short loc_18000DA81
0x18000da03  cmp     qword ptr [rcx+8], 0
0x18000da08  jz      short loc_18000DA27
0x18000da0a  xor     edi, edi
0x18000da0c  cmp     [rcx], edi
0x18000da0e  jbe     short loc_18000DA27
0x18000da10  lea     rcx, [rdi+rdi*8]
0x18000da14  shl     rcx, 4
0x18000da18  add     rcx, [rbx+8]; this
0x18000da1c  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000da21  inc     edi
0x18000da23  cmp     edi, [rbx]
0x18000da25  jb      short loc_18000DA10
0x18000da27  mov     rcx, [rbx+8]; pv
0x18000da2b  call    cs:__imp_CoTaskMemFree
0x18000da32  nop     dword ptr [rax+rax+00h]
0x18000da37  lea     rdi, [rsi+rsi*8]
0x18000da3b  mov     qword ptr [rbx+8], 0
0x18000da43  shl     rdi, 4
0x18000da47  mov     rcx, rdi; cb
0x18000da4a  mov     dword ptr [rbx], 0
0x18000da50  call    cs:__imp_CoTaskMemAlloc
0x18000da57  nop     dword ptr [rax+rax+00h]
0x18000da5c  mov     [rbx+8], rax
0x18000da60  test    rax, rax
0x18000da63  jnz     short loc_18000DA6C
0x18000da65  mov     eax, 8007000Eh
0x18000da6a  jmp     short loc_18000DA81
0x18000da6c  test    rdi, rdi
0x18000da6f  jz      short loc_18000DA7D
0x18000da71  mov     byte ptr [rax], 0
0x18000da74  inc     rax
0x18000da77  sub     rdi, 1
0x18000da7b  jnz     short loc_18000DA71
0x18000da7d  mov     [rbx], esi
0x18000da7f  xor     eax, eax
0x18000da81  mov     rbx, [rsp+28h+arg_0]
0x18000da86  mov     rsi, [rsp+28h+arg_8]
0x18000da8b  add     rsp, 20h
0x18000da8f  pop     rdi
0x18000da90  retn
```
