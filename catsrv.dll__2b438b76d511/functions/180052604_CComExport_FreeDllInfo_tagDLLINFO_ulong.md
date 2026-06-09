# CComExport::FreeDllInfo(_tagDLLINFO *,ulong)

- ea: `0x180052604`
- end: `0x1800526e0`
- name: `?FreeDllInfo@CComExport@@KAXPEAU_tagDLLINFO@@K@Z`
- size: `220`
- prototype: `void __fastcall(struct _tagDLLINFO *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800524f0`

## callees

- `0x180052604`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005265f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052678`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005265f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052678`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800526d9`

## pseudocode

```c
void __fastcall CComExport::FreeDllInfo(struct _tagDLLINFO *a1, unsigned int a2)
{
  unsigned int v2; // r15d
  unsigned int v3; // r13d
  __int64 v5; // r14
  __int64 v6; // r12
  char *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // r13

  v2 = 0;
  v3 = a2;
  if ( a2 )
  {
    v5 = 0;
    do
    {
      v6 = 0;
      v7 = (char *)a1 + 32 * v5;
      if ( *((_DWORD *)v7 + 2) )
      {
        do
        {
          v8 = *((_QWORD *)v7 + 2);
          if ( *(_DWORD *)(v8 + 48 * v6 + 24) )
          {
            v9 = 0;
            do
            {
              CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(v8 + 48 * v6 + 40) + 8 * v9));
              v8 = *((_QWORD *)v7 + 2);
              v9 = (unsigned int)(v9 + 1);
            }
            while ( (unsigned int)v9 < *(_DWORD *)(v8 + 48 * v6 + 24) );
          }
          CoTaskMemFree(*(LPVOID *)(v8 + 48 * v6 + 40));
          CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 2) + 48 * v6 + 16));
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < *((_DWORD *)a1 + 8 * v5 + 2) );
        v3 = a2;
      }
      CoTaskMemFree(*((LPVOID *)v7 + 2));
      CoTaskMemFree(*((LPVOID *)a1 + 4 * v5));
      ++v2;
      ++v5;
    }
    while ( v2 < v3 );
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x180052604  mov     [rsp+arg_8], edx
0x180052608  push    rbx
0x180052609  push    rbp
0x18005260a  push    rsi
0x18005260b  push    rdi
0x18005260c  push    r12
0x18005260e  push    r13
0x180052610  push    r14
0x180052612  push    r15
0x180052614  sub     rsp, 28h
0x180052618  xor     r15d, r15d
0x18005261b  mov     r13d, edx
0x18005261e  mov     rbx, rcx
0x180052621  test    edx, edx
0x180052623  jz      loc_1800526C6
0x180052629  xor     r14d, r14d
0x18005262c  mov     rbp, r14
0x18005262f  xor     r12d, r12d
0x180052632  shl     rbp, 5
0x180052636  lea     rdi, [rbx+rbp]
0x18005263a  cmp     [rbx+rbp+8], r12d
0x18005263f  jbe     short loc_18005269C
0x180052641  mov     rcx, [rdi+10h]
0x180052645  lea     rsi, [r12+r12*2]
0x180052649  add     rsi, rsi
0x18005264c  cmp     dword ptr [rcx+rsi*8+18h], 0
0x180052651  jbe     short loc_180052673
0x180052653  xor     r13d, r13d
0x180052656  mov     rcx, [rcx+rsi*8+28h]
0x18005265b  mov     rcx, [rcx+r13*8]; pv
0x18005265f  call    cs:__imp_CoTaskMemFree
0x180052665  mov     rcx, [rdi+10h]
0x180052669  inc     r13d
0x18005266c  cmp     r13d, [rcx+rsi*8+18h]
0x180052671  jb      short loc_180052656
0x180052673  mov     rcx, [rcx+rsi*8+28h]; pv
0x180052678  call    cs:__imp_CoTaskMemFree
0x18005267e  mov     rcx, [rdi+10h]
0x180052682  mov     rcx, [rcx+rsi*8+10h]; pv
0x180052687  call    cs:__imp_CoTaskMemFree
0x18005268d  inc     r12d
0x180052690  cmp     r12d, [rbx+rbp+8]
0x180052695  jb      short loc_180052641
0x180052697  mov     r13d, [rsp+68h+arg_8]
0x18005269c  mov     rcx, [rdi+10h]; pv
0x1800526a0  call    cs:__imp_CoTaskMemFree
0x1800526a6  mov     rcx, r14
0x1800526a9  shl     rcx, 5
0x1800526ad  mov     rcx, [rcx+rbx]; pv
0x1800526b1  call    cs:__imp_CoTaskMemFree
0x1800526b7  inc     r15d
0x1800526ba  inc     r14
0x1800526bd  cmp     r15d, r13d
0x1800526c0  jb      loc_18005262C
0x1800526c6  mov     rcx, rbx
0x1800526c9  add     rsp, 28h
0x1800526cd  pop     r15
0x1800526cf  pop     r14
0x1800526d1  pop     r13
0x1800526d3  pop     r12
0x1800526d5  pop     rdi
0x1800526d6  pop     rsi
0x1800526d7  pop     rbp
0x1800526d8  pop     rbx
0x1800526d9  jmp     cs:__imp_CoTaskMemFree
```
