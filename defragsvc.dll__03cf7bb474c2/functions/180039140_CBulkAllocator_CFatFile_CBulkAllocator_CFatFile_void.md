# CBulkAllocator<CFatFile>::~CBulkAllocator<CFatFile>(void)

- ea: `0x180039140`
- end: `0x1800391f4`
- name: `??1?$CBulkAllocator@VCFatFile@@@@AEAA@XZ`
- size: `180`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011e58`

## callees

- `0x180039140`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391d6`

## pseudocode

```c
void __fastcall CBulkAllocator<CFatFile>::~CBulkAllocator<CFatFile>(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rcx

  if ( *(_QWORD *)(a1 + 8) )
  {
    v2 = 0;
    v3 = 0;
    do
    {
      v4 = *(_QWORD *)(v3 + *(_QWORD *)(a1 + 8));
      if ( v4 )
      {
        CoTaskMemFree(*(LPVOID *)(v4 + 8));
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + v3) + 8LL) = 0;
        CoTaskMemFree(**(LPVOID **)(v3 + *(_QWORD *)(a1 + 8)));
        **(_QWORD **)(v3 + *(_QWORD *)(a1 + 8)) = 0;
        CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(a1 + 8) + v3));
        *(_QWORD *)(v3 + *(_QWORD *)(a1 + 8)) = 0;
      }
      ++v2;
      v3 += 8;
    }
    while ( v2 != 0x10000 );
    CoTaskMemFree(*(LPVOID *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180039140  mov     [rsp+arg_0], rbx
0x180039145  mov     [rsp+arg_8], rsi
0x18003914a  push    rdi
0x18003914b  sub     rsp, 20h
0x18003914f  cmp     qword ptr [rcx+8], 0
0x180039154  mov     rbx, rcx
0x180039157  jz      loc_1800391E4
0x18003915d  xor     esi, esi
0x18003915f  xor     edi, edi
0x180039161  mov     rax, [rbx+8]
0x180039165  mov     rcx, [rdi+rax]
0x180039169  test    rcx, rcx
0x18003916c  jz      short loc_1800391C2
0x18003916e  mov     rcx, [rcx+8]; pv
0x180039172  call    cs:__imp_CoTaskMemFree
0x180039178  mov     rax, [rbx+8]
0x18003917c  mov     rcx, [rax+rdi]
0x180039180  mov     qword ptr [rcx+8], 0
0x180039188  mov     rax, [rbx+8]
0x18003918c  mov     rcx, [rdi+rax]
0x180039190  mov     rcx, [rcx]; pv
0x180039193  call    cs:__imp_CoTaskMemFree
0x180039199  mov     rax, [rbx+8]
0x18003919d  mov     rcx, [rdi+rax]
0x1800391a1  mov     qword ptr [rcx], 0
0x1800391a8  mov     rcx, [rbx+8]
0x1800391ac  mov     rcx, [rcx+rdi]; pv
0x1800391b0  call    cs:__imp_CoTaskMemFree
0x1800391b6  mov     rax, [rbx+8]
0x1800391ba  mov     qword ptr [rdi+rax], 0
0x1800391c2  inc     rsi
0x1800391c5  add     rdi, 8
0x1800391c9  cmp     rsi, 10000h
0x1800391d0  jnz     short loc_180039161
0x1800391d2  mov     rcx, [rbx+8]; pv
0x1800391d6  call    cs:__imp_CoTaskMemFree
0x1800391dc  mov     qword ptr [rbx+8], 0
0x1800391e4  mov     rbx, [rsp+28h+arg_0]
0x1800391e9  mov     rsi, [rsp+28h+arg_8]
0x1800391ee  add     rsp, 20h
0x1800391f2  pop     rdi
0x1800391f3  retn
```
