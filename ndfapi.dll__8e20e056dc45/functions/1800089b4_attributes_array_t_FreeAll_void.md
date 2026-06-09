# _attributes_array_t::FreeAll(void)

- ea: `0x1800089b4`
- end: `0x180008a58`
- name: `?FreeAll@_attributes_array_t@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(_attributes_array_t *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008304`
- `0x1800084b0`
- `0x18000a9e0`
- `0x18000c0a0`
- `0x18000e0c4`

## callees

- `0x1800089b4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800089eb`
- `ole32!CoTaskMemFree` at `0x180008a08`
- `ole32!CoTaskMemFree` at `0x180008a23`
- `ole32!CoTaskMemFree` at `0x180008a3b`
- `ole32!CoTaskMemFree` at `0x1800089eb`
- `ole32!CoTaskMemFree` at `0x180008a08`
- `ole32!CoTaskMemFree` at `0x180008a23`
- `ole32!CoTaskMemFree` at `0x180008a3b`

## pseudocode

```c
void __fastcall _attributes_array_t::FreeAll(_attributes_array_t *this)
{
  __int64 i; // rbp
  __int64 v3; // rsi
  __int64 v4; // rdi

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; *(_QWORD *)(v3 + 8 * v4) = 0 )
    {
      v3 = *((_QWORD *)this + 1);
      v4 = 18 * i;
      if ( *(_DWORD *)(v3 + 144 * i + 8) == 10 )
      {
        CoTaskMemFree(*(LPVOID *)(v3 + 144 * i + 16));
        *(_QWORD *)(v3 + 144 * i + 16) = 0;
      }
      else if ( *(_DWORD *)(v3 + 144 * i + 8) == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v3 + 144 * i + 24));
        *(_QWORD *)(v3 + 144 * i + 24) = 0;
        *(_DWORD *)(v3 + 144 * i + 16) = 0;
      }
      CoTaskMemFree(*(LPVOID *)(v3 + 144 * i));
      i = (unsigned int)(i + 1);
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 1));
  *((_QWORD *)this + 1) = 0;
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x1800089b4  push    rbx
0x1800089b6  push    rbp
0x1800089b7  push    rsi
0x1800089b8  push    rdi
0x1800089b9  sub     rsp, 28h
0x1800089bd  cmp     qword ptr [rcx+8], 0
0x1800089c2  mov     rbx, rcx
0x1800089c5  jz      short loc_180008A37
0x1800089c7  xor     ebp, ebp
0x1800089c9  cmp     [rcx], ebp
0x1800089cb  jbe     short loc_180008A37
0x1800089cd  mov     rsi, [rbx+8]
0x1800089d1  lea     rdi, ds:0[rbp*8]
0x1800089d9  add     rdi, rbp
0x1800089dc  add     rdi, rdi
0x1800089df  cmp     dword ptr [rsi+rdi*8+8], 0Ah
0x1800089e4  jnz     short loc_1800089FC
0x1800089e6  mov     rcx, [rsi+rdi*8+10h]; pv
0x1800089eb  call    cs:__imp_CoTaskMemFree
0x1800089f1  mov     qword ptr [rsi+rdi*8+10h], 0
0x1800089fa  jmp     short loc_180008A1F
0x1800089fc  cmp     dword ptr [rsi+rdi*8+8], 0Eh
0x180008a01  jnz     short loc_180008A1F
0x180008a03  mov     rcx, [rsi+rdi*8+18h]; pv
0x180008a08  call    cs:__imp_CoTaskMemFree
0x180008a0e  mov     qword ptr [rsi+rdi*8+18h], 0
0x180008a17  mov     dword ptr [rsi+rdi*8+10h], 0
0x180008a1f  mov     rcx, [rsi+rdi*8]; pv
0x180008a23  call    cs:__imp_CoTaskMemFree
0x180008a29  inc     ebp
0x180008a2b  mov     qword ptr [rsi+rdi*8], 0
0x180008a33  cmp     ebp, [rbx]
0x180008a35  jb      short loc_1800089CD
0x180008a37  mov     rcx, [rbx+8]; pv
0x180008a3b  call    cs:__imp_CoTaskMemFree
0x180008a41  mov     qword ptr [rbx+8], 0
0x180008a49  mov     dword ptr [rbx], 0
0x180008a4f  add     rsp, 28h
0x180008a53  pop     rdi
0x180008a54  pop     rsi
0x180008a55  pop     rbp
0x180008a56  pop     rbx
0x180008a57  retn
```
