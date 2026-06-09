# FreeProvisionDataArray(co_array_t<_MVProvisionData> *)

- ea: `0x1800139a0`
- end: `0x180013aa4`
- name: `?FreeProvisionDataArray@@YAXPEAU?$co_array_t@U_MVProvisionData@@@@@Z`
- size: `260`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f36c`
- `0x1800109f0`
- `0x180010bd4`
- `0x180015740`
- `0x180018698`
- `0x18001def0`
- `0x180021b84`

## callees

- `0x1800139a0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a88`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FreeProvisionDataArray(__int64 a1)
{
  unsigned int i; // esi
  __int64 v3; // rbx
  _QWORD *v4; // r14
  unsigned int v5; // r15d
  __int64 j; // rbp
  __int64 v7; // rcx

  for ( i = 0; i < *(_DWORD *)(a1 + 8); ++i )
  {
    v3 = *(_QWORD *)a1 + 104LL * i;
    if ( v3 )
    {
      v4 = *(_QWORD **)(v3 + 24);
      if ( v4 )
      {
        v5 = *(_DWORD *)(v3 + 32);
        for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
        {
          v7 = v4[j];
          if ( v7 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            v4[j] = 0;
          }
        }
        CoTaskMemFree(v4);
      }
      CoTaskMemFree(*(LPVOID *)(v3 + 8));
      *(_QWORD *)(v3 + 8) = 0;
      CoTaskMemFree(*(LPVOID *)(v3 + 16));
      *(_QWORD *)(v3 + 16) = 0;
      CoTaskMemFree(*(LPVOID *)(v3 + 40));
      *(_QWORD *)(v3 + 40) = 0;
      CoTaskMemFree(*(LPVOID *)(v3 + 56));
      *(_QWORD *)(v3 + 56) = 0;
      CoTaskMemFree(*(LPVOID *)(v3 + 64));
      *(_QWORD *)(v3 + 64) = 0;
      CoTaskMemFree(*(LPVOID *)(v3 + 48));
      *(_QWORD *)(v3 + 48) = 0;
    }
  }
  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x1800139a0  push    rbx
0x1800139a2  push    rbp
0x1800139a3  push    rsi
0x1800139a4  push    rdi
0x1800139a5  push    r12
0x1800139a7  push    r14
0x1800139a9  push    r15
0x1800139ab  sub     rsp, 20h
0x1800139af  mov     rdi, rcx
0x1800139b2  xor     esi, esi
0x1800139b4  cmp     [rcx+8], esi
0x1800139b7  jbe     loc_180013A85
0x1800139bd  mov     eax, esi
0x1800139bf  imul    rbx, rax, 68h ; 'h'
0x1800139c3  add     rbx, [rdi]
0x1800139c6  jz      loc_180013A7A
0x1800139cc  mov     r14, [rbx+18h]
0x1800139d0  test    r14, r14
0x1800139d3  jz      short loc_180013A0E
0x1800139d5  mov     r15d, [rbx+20h]
0x1800139d9  xor     ebp, ebp
0x1800139db  test    r15d, r15d
0x1800139de  jz      short loc_180013A04
0x1800139e0  mov     rcx, [r14+rbp*8]
0x1800139e4  test    rcx, rcx
0x1800139e7  jz      short loc_1800139FD
0x1800139e9  mov     rax, [rcx]
0x1800139ec  mov     rax, [rax+10h]
0x1800139f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139f5  mov     qword ptr [r14+rbp*8], 0
0x1800139fd  inc     ebp
0x1800139ff  cmp     ebp, r15d
0x180013a02  jb      short loc_1800139E0
0x180013a04  mov     rcx, r14; pv
0x180013a07  call    cs:__imp_CoTaskMemFree
0x180013a0d  nop
0x180013a0e  mov     rcx, [rbx+8]; pv
0x180013a12  call    cs:__imp_CoTaskMemFree
0x180013a18  mov     qword ptr [rbx+8], 0
0x180013a20  mov     rcx, [rbx+10h]; pv
0x180013a24  call    cs:__imp_CoTaskMemFree
0x180013a2a  mov     qword ptr [rbx+10h], 0
0x180013a32  mov     rcx, [rbx+28h]; pv
0x180013a36  call    cs:__imp_CoTaskMemFree
0x180013a3c  mov     qword ptr [rbx+28h], 0
0x180013a44  mov     rcx, [rbx+38h]; pv
0x180013a48  call    cs:__imp_CoTaskMemFree
0x180013a4e  mov     qword ptr [rbx+38h], 0
0x180013a56  mov     rcx, [rbx+40h]; pv
0x180013a5a  call    cs:__imp_CoTaskMemFree
0x180013a60  mov     qword ptr [rbx+40h], 0
0x180013a68  mov     rcx, [rbx+30h]; pv
0x180013a6c  call    cs:__imp_CoTaskMemFree
0x180013a72  mov     qword ptr [rbx+30h], 0
0x180013a7a  inc     esi
0x180013a7c  cmp     esi, [rdi+8]
0x180013a7f  jb      loc_1800139BD
0x180013a85  mov     rcx, [rdi]; pv
0x180013a88  call    cs:__imp_CoTaskMemFree
0x180013a8e  mov     qword ptr [rdi], 0
0x180013a95  add     rsp, 20h
0x180013a99  pop     r15
0x180013a9b  pop     r14
0x180013a9d  pop     r12
0x180013a9f  pop     rdi
0x180013aa0  pop     rsi
0x180013aa1  pop     rbp
0x180013aa2  pop     rbx
0x180013aa3  retn
```
