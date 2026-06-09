# CQueue::OpenQueue(ulong,void * *,_bstr_t const &)

- ea: `0x140006478`
- end: `0x140006556`
- name: `?OpenQueue@CQueue@@AEAAJKPEAPEAXAEBV_bstr_t@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CQueue *this, DWORD, void **, __int64 **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400062c8`

## callees

- `0x140006478`
- `0x1400073d0`
- `0x14000fe40`
- `0x140017cb0`
- `0x140017cf4`

## pseudocode

```c
__int64 __fastcall CQueue::OpenQueue(CQueue *this, DWORD a2, void **a3, __int64 **a4)
{
  __int64 **v4; // rdi
  __int64 v6; // rax
  signed int v7; // ebx
  __int64 *v9; // rax
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF

  v4 = (__int64 **)((char *)this + 96);
  v6 = *((_QWORD *)this + 12);
  v14 = v6;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 16));
  v7 = OpenQueue((_bstr_t *)&v14, a2, (__int64)a3, a3, (CQueue *)((char *)this + 104));
  if ( v7 >= 0 )
    return 0;
  if ( !(unsigned __int8)CSafeSet<_bstr_t>::insert(qword_14002ADF8, v4) )
    return (unsigned int)v7;
  v9 = *a4;
  if ( v7 != -1072824317 )
  {
    if ( v9 )
      v12 = *v9;
    else
      v12 = 0;
    if ( *v4 )
      v13 = **v4;
    else
      v13 = 0;
    EvReportWithError(0xC000089D, v7, 2u, v13, v12);
    return (unsigned int)v7;
  }
  if ( v9 )
    v10 = *v9;
  else
    v10 = 0;
  if ( *v4 )
    v11 = **v4;
  else
    v11 = 0;
  EvReport(0xC00008A4, 2u, v11, v10);
  return 3222142979LL;
}

```

## disassembly

```asm
0x140006478  mov     [rsp+arg_8], rbx
0x14000647d  mov     [rsp+arg_10], rsi
0x140006482  push    rdi
0x140006483  sub     rsp, 30h
0x140006487  lea     rdi, [rcx+60h]
0x14000648b  mov     rsi, r9
0x14000648e  mov     rax, [rdi]
0x140006491  mov     [rsp+38h+arg_0], rax
0x140006496  test    rax, rax
0x140006499  jz      short loc_14000649F
0x14000649b  lock inc dword ptr [rax+10h]
0x14000649f  lea     rax, [rcx+68h]
0x1400064a3  mov     r9, r8
0x1400064a6  lea     rcx, [rsp+38h+arg_0]
0x1400064ab  mov     [rsp+38h+var_18], rax
0x1400064b0  call    ?OpenQueue@@YAJV_bstr_t@@K_NPEAPEAXPEAV1@@Z; OpenQueue(_bstr_t,ulong,bool,void * *,_bstr_t *)
0x1400064b5  mov     ebx, eax
0x1400064b7  test    eax, eax
0x1400064b9  js      short loc_1400064C2
0x1400064bb  xor     eax, eax
0x1400064bd  jmp     loc_140006546
0x1400064c2  mov     rdx, rdi
0x1400064c5  lea     rcx, qword_14002ADF8
0x1400064cc  call    ?insert@?$CSafeSet@V_bstr_t@@@@QEAA_NAEBV_bstr_t@@@Z; CSafeSet<_bstr_t>::insert(_bstr_t const &)
0x1400064d1  test    al, al
0x1400064d3  jz      short loc_140006544
0x1400064d5  mov     rax, [rsi]
0x1400064d8  mov     esi, 0C00E0003h
0x1400064dd  cmp     ebx, esi
0x1400064df  jnz     short loc_140006511
0x1400064e1  test    rax, rax
0x1400064e4  jz      short loc_1400064EB
0x1400064e6  mov     r9, [rax]
0x1400064e9  jmp     short loc_1400064EE
0x1400064eb  xor     r9d, r9d
0x1400064ee  mov     rax, [rdi]
0x1400064f1  test    rax, rax
0x1400064f4  jz      short loc_1400064FB
0x1400064f6  mov     r8, [rax]
0x1400064f9  jmp     short loc_1400064FE
0x1400064fb  xor     r8d, r8d
0x1400064fe  mov     edx, 2; unsigned __int16
0x140006503  mov     ecx, 0C00008A4h; unsigned int
0x140006508  call    ?EvReport@@YAXKGZZ; EvReport(ulong,ushort,...)
0x14000650d  mov     eax, esi
0x14000650f  jmp     short loc_140006546
0x140006511  test    rax, rax
0x140006514  jz      short loc_14000651B
0x140006516  mov     rcx, [rax]
0x140006519  jmp     short loc_14000651D
0x14000651b  xor     ecx, ecx
0x14000651d  mov     rax, [rdi]
0x140006520  test    rax, rax
0x140006523  jz      short loc_14000652A
0x140006525  mov     r9, [rax]
0x140006528  jmp     short loc_14000652D
0x14000652a  xor     r9d, r9d
0x14000652d  mov     [rsp+38h+var_18], rcx
0x140006532  mov     r8d, 2; unsigned __int16
0x140006538  mov     ecx, 0C000089Dh; unsigned int
0x14000653d  mov     edx, ebx; dwMessageId
0x14000653f  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x140006544  mov     eax, ebx
0x140006546  mov     rbx, [rsp+38h+arg_8]
0x14000654b  mov     rsi, [rsp+38h+arg_10]
0x140006550  add     rsp, 30h
0x140006554  pop     rdi
0x140006555  retn
```
