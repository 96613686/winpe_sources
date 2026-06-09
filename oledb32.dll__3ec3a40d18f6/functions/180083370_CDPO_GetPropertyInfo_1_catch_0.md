# _CDPO::GetPropertyInfo_::_1_::catch$0

- ea: `0x180083370`
- end: `0x180083460`
- name: `_CDPO::GetPropertyInfo_::_1_::catch$0`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18003c2e8`
- `0x180083370`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180083412`
- `OLEAUT32!__imp_VariantClear` at `0x180083412`
- `ole32!CoTaskMemFree` at `0x180083424`
- `ole32!CoTaskMemFree` at `0x180083434`
- `ole32!CoTaskMemFree` at `0x180083424`
- `ole32!CoTaskMemFree` at `0x180083434`

## pseudocode

```c
__int64 __fastcall CDPO::GetPropertyInfo_::_1_::catch_0(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  LPVOID *v4; // rdi
  unsigned int v5; // esi
  unsigned int *v6; // r15
  __int64 v7; // rbx
  __int64 i; // r14

  if ( (bidGblFlags & 2) != 0 && off_1800C8A18[0] )
  {
    v3 = *(_DWORD *)(a2 + 148);
    bidTraceA(off_1800C8450[0], 453632, off_1800C8A18[0], v3);
  }
  else
  {
    v3 = *(_DWORD *)(a2 + 148);
  }
  *(_DWORD *)(a2 + 240) = v3;
  v4 = *(LPVOID **)(a2 + 272);
  if ( v4 && *v4 )
  {
    v5 = 0;
    v6 = *(unsigned int **)(a2 + 264);
    if ( *v6 )
    {
      do
      {
        v7 = (__int64)*v4 + 32 * v5;
        if ( *(_QWORD *)v7 )
        {
          for ( i = 0; (unsigned int)i < *(_DWORD *)(v7 + 8); i = (unsigned int)(i + 1) )
            VariantClear((VARIANTARG *)(48 * i + 24 + *(_QWORD *)v7));
          CoTaskMemFree(*(LPVOID *)v7);
        }
        ++v5;
      }
      while ( v5 < *v6 );
    }
    CoTaskMemFree(*v4);
    *v4 = 0;
    *v6 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180083370  mov     [rsp+arg_8], rdx
0x180083375  push    rbx
0x180083376  push    rbp
0x180083377  push    rsi
0x180083378  push    rdi
0x180083379  push    r14
0x18008337b  push    r15
0x18008337d  sub     rsp, 58h
0x180083381  mov     rbp, rdx
0x180083384  test    byte ptr cs:_bidGblFlags, 2
0x18008338b  jz      short loc_1800833BC
0x18008338d  mov     rax, cs:off_1800C8A18; "<CDPO::GetPropertyInfo|CATCH|HR> 0x%08X"...
0x180083394  test    rax, rax
0x180083397  jz      short loc_1800833BC
0x180083399  mov     ebx, [rbp+94h]
0x18008339f  mov     r9d, ebx
0x1800833a2  mov     r8, cs:off_1800C8A18; "<CDPO::GetPropertyInfo|CATCH|HR> 0x%08X"...
0x1800833a9  mov     edx, 6EC00h
0x1800833ae  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800833b5  call    _bidTraceA
0x1800833ba  jmp     short loc_1800833C2
0x1800833bc  mov     ebx, [rbp+94h]
0x1800833c2  mov     [rbp+0F0h], ebx
0x1800833c8  mov     rdi, [rbp+110h]
0x1800833cf  test    rdi, rdi
0x1800833d2  jz      short loc_180083448
0x1800833d4  cmp     qword ptr [rdi], 0
0x1800833d8  jz      short loc_180083448
0x1800833da  xor     esi, esi
0x1800833dc  mov     r15, [rbp+108h]
0x1800833e3  cmp     [r15], esi
0x1800833e6  jbe     short loc_180083431
0x1800833e8  mov     ebx, esi
0x1800833ea  shl     rbx, 5
0x1800833ee  add     rbx, [rdi]
0x1800833f1  cmp     qword ptr [rbx], 0
0x1800833f5  jz      short loc_18008342A
0x1800833f7  xor     r14d, r14d
0x1800833fa  cmp     [rbx+8], r14d
0x1800833fe  jbe     short loc_180083421
0x180083400  lea     rdx, [r14+r14*2]
0x180083404  shl     rdx, 4
0x180083408  mov     rcx, [rbx]
0x18008340b  add     rdx, 18h
0x18008340f  add     rcx, rdx; pvarg
0x180083412  call    cs:__imp_VariantClear
0x180083418  inc     r14d
0x18008341b  cmp     r14d, [rbx+8]
0x18008341f  jb      short loc_180083400
0x180083421  mov     rcx, [rbx]; pv
0x180083424  call    cs:__imp_CoTaskMemFree
0x18008342a  inc     esi
0x18008342c  cmp     esi, [r15]
0x18008342f  jb      short loc_1800833E8
0x180083431  mov     rcx, [rdi]; pv
0x180083434  call    cs:__imp_CoTaskMemFree
0x18008343a  mov     qword ptr [rdi], 0
0x180083441  mov     dword ptr [r15], 0
0x180083448  mov     rax, 0
0x180083452  add     rsp, 58h
0x180083456  pop     r15
0x180083458  pop     r14
0x18008345a  pop     rdi
0x18008345b  pop     rsi
0x18008345c  pop     rbp
0x18008345d  pop     rbx
0x18008345e  retn
```
