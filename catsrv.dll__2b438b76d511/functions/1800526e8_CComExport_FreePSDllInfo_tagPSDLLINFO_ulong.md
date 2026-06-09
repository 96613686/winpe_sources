# CComExport::FreePSDllInfo(_tagPSDLLINFO *,ulong)

- ea: `0x1800526e8`
- end: `0x1800527c2`
- name: `?FreePSDllInfo@CComExport@@KAXPEAU_tagPSDLLINFO@@K@Z`
- size: `218`
- prototype: `void __fastcall(struct _tagPSDLLINFO *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800524f0`

## callees

- `0x1800526e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800527bb`

## pseudocode

```c
void __fastcall CComExport::FreePSDllInfo(struct _tagPSDLLINFO *a1, unsigned int a2)
{
  unsigned int v2; // r14d
  __int64 v5; // rbx
  __int64 v6; // r13
  __int64 v7; // r15
  char *v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // r13

  v2 = 0;
  if ( a2 )
  {
    v5 = 0;
    do
    {
      v6 = 3 * v5;
      v7 = 0;
      v8 = (char *)a1 + 24 * v5;
      if ( *((_DWORD *)v8 + 2) )
      {
        do
        {
          v9 = *((_QWORD *)v8 + 2);
          if ( *(_DWORD *)(v9 + 40 * v7 + 24) )
          {
            v10 = 0;
            do
            {
              CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(v9 + 40 * v7 + 32) + 24 * v10 + 16));
              v9 = *((_QWORD *)v8 + 2);
              v10 = (unsigned int)(v10 + 1);
            }
            while ( (unsigned int)v10 < *(_DWORD *)(v9 + 40 * v7 + 24) );
            v6 = 3 * v5;
          }
          CoTaskMemFree(*(LPVOID *)(v9 + 40 * v7 + 32));
          CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v8 + 2) + 40 * v7 + 16));
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < *((_DWORD *)a1 + 2 * v6 + 2) );
      }
      CoTaskMemFree(*((LPVOID *)v8 + 2));
      CoTaskMemFree(*((LPVOID *)a1 + 3 * v5));
      ++v2;
      ++v5;
    }
    while ( v2 < a2 );
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x1800526e8  push    rbx
0x1800526ea  push    rbp
0x1800526eb  push    rsi
0x1800526ec  push    rdi
0x1800526ed  push    r12
0x1800526ef  push    r13
0x1800526f1  push    r14
0x1800526f3  push    r15
0x1800526f5  sub     rsp, 28h
0x1800526f9  xor     r14d, r14d
0x1800526fc  mov     r12d, edx
0x1800526ff  mov     rdi, rcx
0x180052702  test    edx, edx
0x180052704  jz      loc_1800527A8
0x18005270a  xor     ebx, ebx
0x18005270c  lea     r13, [rbx+rbx*2]
0x180052710  xor     r15d, r15d
0x180052713  lea     rsi, [rdi+r13*8]
0x180052717  cmp     [rdi+r13*8+8], r15d
0x18005271c  jbe     short loc_180052781
0x18005271e  mov     rcx, [rsi+10h]
0x180052722  lea     rbp, [r15+r15*4]
0x180052726  cmp     dword ptr [rcx+rbp*8+18h], 0
0x18005272b  jbe     short loc_18005275D
0x18005272d  xor     r13d, r13d
0x180052730  mov     rcx, [rcx+rbp*8+20h]
0x180052735  lea     rdx, ds:0[r13*2]
0x18005273d  add     rdx, r13
0x180052740  mov     rcx, [rcx+rdx*8+10h]; pv
0x180052745  call    cs:__imp_CoTaskMemFree
0x18005274b  mov     rcx, [rsi+10h]
0x18005274f  inc     r13d
0x180052752  cmp     r13d, [rcx+rbp*8+18h]
0x180052757  jb      short loc_180052730
0x180052759  lea     r13, [rbx+rbx*2]
0x18005275d  mov     rcx, [rcx+rbp*8+20h]; pv
0x180052762  call    cs:__imp_CoTaskMemFree
0x180052768  mov     rcx, [rsi+10h]
0x18005276c  mov     rcx, [rcx+rbp*8+10h]; pv
0x180052771  call    cs:__imp_CoTaskMemFree
0x180052777  inc     r15d
0x18005277a  cmp     r15d, [rdi+r13*8+8]
0x18005277f  jb      short loc_18005271E
0x180052781  mov     rcx, [rsi+10h]; pv
0x180052785  call    cs:__imp_CoTaskMemFree
0x18005278b  lea     rcx, [rbx+rbx*2]
0x18005278f  mov     rcx, [rdi+rcx*8]; pv
0x180052793  call    cs:__imp_CoTaskMemFree
0x180052799  inc     r14d
0x18005279c  inc     rbx
0x18005279f  cmp     r14d, r12d
0x1800527a2  jb      loc_18005270C
0x1800527a8  mov     rcx, rdi
0x1800527ab  add     rsp, 28h
0x1800527af  pop     r15
0x1800527b1  pop     r14
0x1800527b3  pop     r13
0x1800527b5  pop     r12
0x1800527b7  pop     rdi
0x1800527b8  pop     rsi
0x1800527b9  pop     rbp
0x1800527ba  pop     rbx
0x1800527bb  jmp     cs:__imp_CoTaskMemFree
```
