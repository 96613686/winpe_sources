# _attributes_array_t::FreeElements(void)

- ea: `0x180006628`
- end: `0x1800066b4`
- name: `?FreeElements@_attributes_array_t@@QEAAXXZ`
- size: `140`
- prototype: `void __fastcall(_attributes_array_t *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e60`
- `0x180005f00`
- `0x180006970`
- `0x18000a38c`
- `0x18000a8f0`
- `0x18000aac0`
- `0x18000b028`

## callees

- `0x180006628`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000665f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000667c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000665f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000667c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006697`

## pseudocode

```c
void __fastcall _attributes_array_t::FreeElements(_attributes_array_t *this)
{
  __int64 i; // rbp
  __int64 v3; // rdi
  __int64 v4; // rbx

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
}

```

## disassembly

```asm
0x180006628  push    rbx
0x18000662a  push    rbp
0x18000662b  push    rsi
0x18000662c  push    rdi
0x18000662d  sub     rsp, 28h
0x180006631  cmp     qword ptr [rcx+8], 0
0x180006636  mov     rsi, rcx
0x180006639  jz      short loc_1800066AB
0x18000663b  xor     ebp, ebp
0x18000663d  cmp     [rcx], ebp
0x18000663f  jbe     short loc_1800066AB
0x180006641  mov     rdi, [rsi+8]
0x180006645  lea     rbx, ds:0[rbp*8]
0x18000664d  add     rbx, rbp
0x180006650  add     rbx, rbx
0x180006653  cmp     dword ptr [rdi+rbx*8+8], 0Ah
0x180006658  jnz     short loc_180006670
0x18000665a  mov     rcx, [rdi+rbx*8+10h]; pv
0x18000665f  call    cs:__imp_CoTaskMemFree
0x180006665  mov     qword ptr [rdi+rbx*8+10h], 0
0x18000666e  jmp     short loc_180006693
0x180006670  cmp     dword ptr [rdi+rbx*8+8], 0Eh
0x180006675  jnz     short loc_180006693
0x180006677  mov     rcx, [rdi+rbx*8+18h]; pv
0x18000667c  call    cs:__imp_CoTaskMemFree
0x180006682  mov     qword ptr [rdi+rbx*8+18h], 0
0x18000668b  mov     dword ptr [rdi+rbx*8+10h], 0
0x180006693  mov     rcx, [rdi+rbx*8]; pv
0x180006697  call    cs:__imp_CoTaskMemFree
0x18000669d  inc     ebp
0x18000669f  mov     qword ptr [rdi+rbx*8], 0
0x1800066a7  cmp     ebp, [rsi]
0x1800066a9  jb      short loc_180006641
0x1800066ab  add     rsp, 28h
0x1800066af  pop     rdi
0x1800066b0  pop     rsi
0x1800066b1  pop     rbp
0x1800066b2  pop     rbx
0x1800066b3  retn
```
