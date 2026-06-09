# CWorkerTerminal::GetUserInformation(uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18007dd10`
- end: `0x18007de18`
- name: `?GetUserInformation@CWorkerTerminal@@UEAAJPEAPEAEPEAK01@Z`
- size: `264`
- prototype: `__int64 __fastcall(CWorkerTerminal *__hidden this, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800129d0`
- `0x18001d170`
- `0x18004f354`
- `0x18007dd10`
- `0x18009959c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ddf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ddf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dd40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dd55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dd40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007dd55`

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
0x18007dd10  push    rbx
0x18007dd12  push    rbp
0x18007dd13  push    rsi
0x18007dd14  push    rdi
0x18007dd15  push    r14
0x18007dd17  push    r15
0x18007dd19  sub     rsp, 38h
0x18007dd1d  mov     r14, r9
0x18007dd20  mov     r15, r8
0x18007dd23  mov     rbp, rdx
0x18007dd26  mov     rdi, rcx
0x18007dd29  lea     rdx, [rcx+668h]; struct CResource *
0x18007dd30  lea     rcx, [rsp+68h+var_48]; this
0x18007dd35  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x18007dd3a  mov     ecx, [rdi+650h]; cb
0x18007dd40  call    cs:__imp_CoTaskMemAlloc
0x18007dd47  nop     dword ptr [rax+rax+00h]
0x18007dd4c  mov     rsi, rax
0x18007dd4f  mov     ecx, [rdi+660h]; cb
0x18007dd55  call    cs:__imp_CoTaskMemAlloc
0x18007dd5c  nop     dword ptr [rax+rax+00h]
0x18007dd61  mov     rbx, rax
0x18007dd64  test    rsi, rsi
0x18007dd67  jz      short loc_18007DDE8
0x18007dd69  mov     rcx, rsi; void *
0x18007dd6c  test    rax, rax
0x18007dd6f  jz      short loc_18007DDF0
0x18007dd71  mov     r8d, [rdi+650h]; Size
0x18007dd78  xor     edx, edx; Val
0x18007dd7a  call    memset_0
0x18007dd7f  mov     r8d, [rdi+660h]; Size
0x18007dd86  xor     edx, edx; Val
0x18007dd88  mov     rcx, rbx; void *
0x18007dd8b  call    memset_0
0x18007dd90  mov     r8d, [rdi+650h]; Size
0x18007dd97  mov     rdx, [rdi+648h]; Src
0x18007dd9e  mov     rcx, rsi; void *
0x18007dda1  call    memcpy_0
0x18007dda6  mov     r8d, [rdi+660h]; Size
0x18007ddad  mov     rdx, [rdi+658h]; Src
0x18007ddb4  mov     rcx, rbx; void *
0x18007ddb7  call    memcpy_0
0x18007ddbc  mov     [rbp+0], rsi
0x18007ddc0  mov     eax, [rdi+650h]
0x18007ddc6  mov     [r15], eax
0x18007ddc9  mov     [r14], rbx
0x18007ddcc  mov     ecx, [rdi+660h]
0x18007ddd2  mov     rax, [rsp+68h+arg_20]
0x18007ddda  mov     [rax], ecx
0x18007dddc  mov     dword ptr [rdi+6D0h], 2
0x18007dde6  jmp     short loc_18007DDFD
0x18007dde8  test    rbx, rbx
0x18007ddeb  jz      short loc_18007DDFD
0x18007dded  mov     rcx, rbx; pv
0x18007ddf0  call    cs:__imp_CoTaskMemFree
0x18007ddf7  nop     dword ptr [rax+rax+00h]
0x18007ddfc  nop
0x18007ddfd  lea     rcx, [rsp+68h+var_48]; this
0x18007de02  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18007de07  nop
0x18007de08  xor     eax, eax
0x18007de0a  add     rsp, 38h
0x18007de0e  pop     r15
0x18007de10  pop     r14
0x18007de12  pop     rdi
0x18007de13  pop     rsi
0x18007de14  pop     rbp
0x18007de15  pop     rbx
0x18007de16  retn
```
