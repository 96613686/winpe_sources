# CleanupMemoryForGetEventClasses(ushort * *,ushort * *,ushort * *,ushort * *,ulong *,ulong)

- ea: `0x1800213b0`
- end: `0x18002147d`
- name: `?CleanupMemoryForGetEventClasses@@YAXPEAPEAG000PEAKK@Z`
- size: `205`
- prototype: `void __fastcall(unsigned __int16 **pv, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022040`

## callees

- `0x1800213b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002144c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002145b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002144c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002145b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021476`

## pseudocode

```c
void __fastcall CleanupMemoryForGetEventClasses(
        unsigned __int16 **pv,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        unsigned int a6)
{
  __int64 i; // rdi
  __int64 j; // rdi
  __int64 k; // rdi
  __int64 m; // rdi

  if ( pv )
  {
    for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
      CoTaskMemFree(pv[i]);
    CoTaskMemFree(pv);
  }
  if ( a2 )
  {
    for ( j = 0; (unsigned int)j < a6; j = (unsigned int)(j + 1) )
      CoTaskMemFree(a2[j]);
    CoTaskMemFree(a2);
  }
  if ( a3 )
  {
    for ( k = 0; (unsigned int)k < a6; k = (unsigned int)(k + 1) )
      CoTaskMemFree(a3[k]);
    CoTaskMemFree(a3);
  }
  if ( a4 )
  {
    for ( m = 0; (unsigned int)m < a6; m = (unsigned int)(m + 1) )
      CoTaskMemFree(a4[m]);
    CoTaskMemFree(a4);
  }
  CoTaskMemFree(a5);
}

```

## disassembly

```asm
0x1800213b0  push    rbx
0x1800213b2  push    rsi
0x1800213b3  push    rdi
0x1800213b4  push    r12
0x1800213b6  push    r14
0x1800213b8  push    r15
0x1800213ba  sub     rsp, 28h
0x1800213be  mov     ebx, [rsp+58h+arg_28]
0x1800213c5  mov     rsi, r9
0x1800213c8  mov     r12, r8
0x1800213cb  mov     r14, rdx
0x1800213ce  mov     r15, rcx
0x1800213d1  test    rcx, rcx
0x1800213d4  jz      short loc_1800213F5
0x1800213d6  xor     edi, edi
0x1800213d8  test    ebx, ebx
0x1800213da  jz      short loc_1800213EC
0x1800213dc  mov     rcx, [r15+rdi*8]; pv
0x1800213e0  call    cs:__imp_CoTaskMemFree
0x1800213e6  inc     edi
0x1800213e8  cmp     edi, ebx
0x1800213ea  jb      short loc_1800213DC
0x1800213ec  mov     rcx, r15; pv
0x1800213ef  call    cs:__imp_CoTaskMemFree
0x1800213f5  test    r14, r14
0x1800213f8  jz      short loc_180021419
0x1800213fa  xor     edi, edi
0x1800213fc  test    ebx, ebx
0x1800213fe  jz      short loc_180021410
0x180021400  mov     rcx, [r14+rdi*8]; pv
0x180021404  call    cs:__imp_CoTaskMemFree
0x18002140a  inc     edi
0x18002140c  cmp     edi, ebx
0x18002140e  jb      short loc_180021400
0x180021410  mov     rcx, r14; pv
0x180021413  call    cs:__imp_CoTaskMemFree
0x180021419  test    r12, r12
0x18002141c  jz      short loc_18002143D
0x18002141e  xor     edi, edi
0x180021420  test    ebx, ebx
0x180021422  jz      short loc_180021434
0x180021424  mov     rcx, [r12+rdi*8]; pv
0x180021428  call    cs:__imp_CoTaskMemFree
0x18002142e  inc     edi
0x180021430  cmp     edi, ebx
0x180021432  jb      short loc_180021424
0x180021434  mov     rcx, r12; pv
0x180021437  call    cs:__imp_CoTaskMemFree
0x18002143d  test    rsi, rsi
0x180021440  jz      short loc_180021461
0x180021442  xor     edi, edi
0x180021444  test    ebx, ebx
0x180021446  jz      short loc_180021458
0x180021448  mov     rcx, [rsi+rdi*8]; pv
0x18002144c  call    cs:__imp_CoTaskMemFree
0x180021452  inc     edi
0x180021454  cmp     edi, ebx
0x180021456  jb      short loc_180021448
0x180021458  mov     rcx, rsi; pv
0x18002145b  call    cs:__imp_CoTaskMemFree
0x180021461  mov     rcx, [rsp+58h+arg_20]
0x180021469  add     rsp, 28h
0x18002146d  pop     r15
0x18002146f  pop     r14
0x180021471  pop     r12
0x180021473  pop     rdi
0x180021474  pop     rsi
0x180021475  pop     rbx
0x180021476  jmp     cs:__imp_CoTaskMemFree
```
