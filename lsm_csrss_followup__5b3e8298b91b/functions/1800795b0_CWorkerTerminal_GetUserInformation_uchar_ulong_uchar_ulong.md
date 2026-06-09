# CWorkerTerminal::GetUserInformation(uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x1800795b0`
- end: `0x1800796a5`
- name: `?GetUserInformation@CWorkerTerminal@@UEAAJPEAPEAEPEAK01@Z`
- size: `245`
- prototype: `__int64 __fastcall(CWorkerTerminal *__hidden this, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ce00`
- `0x18001cec0`
- `0x18004bf44`
- `0x1800795b0`
- `0x18009404c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079684`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079684`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800795e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800795ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800795e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800795ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkerTerminal::GetUserInformation(
        const void **this,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  void *v9; // rsi
  LPVOID v10; // rax
  void *v11; // rbx
  void *v12; // rcx
  _BYTE v14[72]; // [rsp+20h] [rbp-48h] BYREF

  CAutoSharedLock::CAutoSharedLock((CAutoSharedLock *)v14, (struct CResource *)(this + 205));
  v9 = CoTaskMemAlloc(*((unsigned int *)this + 404));
  v10 = CoTaskMemAlloc(*((unsigned int *)this + 408));
  v11 = v10;
  if ( !v9 )
  {
    if ( !v10 )
      goto LABEL_7;
    v12 = v10;
LABEL_6:
    CoTaskMemFree(v12);
    goto LABEL_7;
  }
  v12 = v9;
  if ( !v10 )
    goto LABEL_6;
  memset_0(v9, 0, *((unsigned int *)this + 404));
  memset_0(v11, 0, *((unsigned int *)this + 408));
  memcpy_0(v9, this[201], *((unsigned int *)this + 404));
  memcpy_0(v11, this[203], *((unsigned int *)this + 408));
  *a2 = (unsigned __int8 *)v9;
  *a3 = *((_DWORD *)this + 404);
  *a4 = (unsigned __int8 *)v11;
  *a5 = *((_DWORD *)this + 408);
  *((_DWORD *)this + 436) = 2;
LABEL_7:
  CAutoLock::Unlock((CAutoLock *)v14);
  return 0;
}

```

## disassembly

```asm
0x1800795b0  push    rbx
0x1800795b2  push    rbp
0x1800795b3  push    rsi
0x1800795b4  push    rdi
0x1800795b5  push    r14
0x1800795b7  push    r15
0x1800795b9  sub     rsp, 38h
0x1800795bd  mov     r14, r9
0x1800795c0  mov     r15, r8
0x1800795c3  mov     rbp, rdx
0x1800795c6  mov     rdi, rcx
0x1800795c9  lea     rdx, [rcx+668h]; struct CResource *
0x1800795d0  lea     rcx, [rsp+68h+var_48]; this
0x1800795d5  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x1800795da  mov     ecx, [rdi+650h]; cb
0x1800795e0  call    cs:__imp_CoTaskMemAlloc
0x1800795e6  mov     rsi, rax
0x1800795e9  mov     ecx, [rdi+660h]; cb
0x1800795ef  call    cs:__imp_CoTaskMemAlloc
0x1800795f5  mov     rbx, rax
0x1800795f8  test    rsi, rsi
0x1800795fb  jz      short loc_18007967C
0x1800795fd  mov     rcx, rsi; void *
0x180079600  test    rax, rax
0x180079603  jz      short loc_180079684
0x180079605  mov     r8d, [rdi+650h]; Size
0x18007960c  xor     edx, edx; Val
0x18007960e  call    memset_0
0x180079613  mov     r8d, [rdi+660h]; Size
0x18007961a  xor     edx, edx; Val
0x18007961c  mov     rcx, rbx; void *
0x18007961f  call    memset_0
0x180079624  mov     r8d, [rdi+650h]; Size
0x18007962b  mov     rdx, [rdi+648h]; Src
0x180079632  mov     rcx, rsi; void *
0x180079635  call    memcpy_0
0x18007963a  mov     r8d, [rdi+660h]; Size
0x180079641  mov     rdx, [rdi+658h]; Src
0x180079648  mov     rcx, rbx; void *
0x18007964b  call    memcpy_0
0x180079650  mov     [rbp+0], rsi
0x180079654  mov     eax, [rdi+650h]
0x18007965a  mov     [r15], eax
0x18007965d  mov     [r14], rbx
0x180079660  mov     ecx, [rdi+660h]
0x180079666  mov     rax, [rsp+68h+arg_20]
0x18007966e  mov     [rax], ecx
0x180079670  mov     dword ptr [rdi+6D0h], 2
0x18007967a  jmp     short loc_18007968B
0x18007967c  test    rbx, rbx
0x18007967f  jz      short loc_18007968B
0x180079681  mov     rcx, rbx; pv
0x180079684  call    cs:__imp_CoTaskMemFree
0x18007968a  nop
0x18007968b  lea     rcx, [rsp+68h+var_48]; this
0x180079690  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180079695  nop
0x180079696  xor     eax, eax
0x180079698  add     rsp, 38h
0x18007969c  pop     r15
0x18007969e  pop     r14
0x1800796a0  pop     rdi
0x1800796a1  pop     rsi
0x1800796a2  pop     rbp
0x1800796a3  pop     rbx
0x1800796a4  retn
```
