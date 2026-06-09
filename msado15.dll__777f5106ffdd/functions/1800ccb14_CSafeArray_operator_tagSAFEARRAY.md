# CSafeArray::operator=(tagSAFEARRAY *)

- ea: `0x1800ccb14`
- end: `0x1800ccb8c`
- name: `??4CSafeArray@@QEAAAEBV0@PEAUtagSAFEARRAY@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(CSafeArray *this, SAFEARRAY *psa)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002990`
- `0x18005cb64`

## callees

- `0x180059e18`
- `0x1800ccb14`
- `0x1800cd260`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800ccb41`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800ccb41`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800ccb53`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800ccb53`

## pseudocode

```c
CSafeArray *__fastcall CSafeArray::operator=(CSafeArray *this, SAFEARRAY *psa)
{
  SAFEARRAY **v2; // rdi

  v2 = (SAFEARRAY **)((char *)this + 16);
  if ( (*((_BYTE *)this + 8) & 1) != 0 )
  {
    if ( *v2 )
    {
      CSafeArray::UnlockAll(this);
      SafeArrayDestroy(*v2);
    }
    if ( SafeArrayCopy(psa, v2) < 0 )
      *((_DWORD *)this + 2) &= ~4u;
  }
  else
  {
    *v2 = psa;
  }
  *((_WORD *)this + 14) = CSafeArray::GuessAtType(this);
  return this;
}

```

## disassembly

```asm
0x1800ccb14  mov     [rsp+arg_0], rbx
0x1800ccb19  mov     [rsp+arg_8], rsi
0x1800ccb1e  push    rdi
0x1800ccb1f  sub     rsp, 20h
0x1800ccb23  test    byte ptr [rcx+8], 1
0x1800ccb27  lea     rdi, [rcx+10h]
0x1800ccb2b  mov     rsi, rdx
0x1800ccb2e  mov     rbx, rcx
0x1800ccb31  jz      short loc_1800CCB69
0x1800ccb33  cmp     qword ptr [rdi], 0
0x1800ccb37  jz      short loc_1800CCB4D
0x1800ccb39  call    ?UnlockAll@CSafeArray@@QEAAXXZ; CSafeArray::UnlockAll(void)
0x1800ccb3e  mov     rcx, [rdi]; psa
0x1800ccb41  call    cs:__imp_SafeArrayDestroy
0x1800ccb48  nop     dword ptr [rax+rax+00h]
0x1800ccb4d  mov     rdx, rdi; ppsaOut
0x1800ccb50  mov     rcx, rsi; psa
0x1800ccb53  call    cs:__imp_SafeArrayCopy
0x1800ccb5a  nop     dword ptr [rax+rax+00h]
0x1800ccb5f  test    eax, eax
0x1800ccb61  jns     short loc_1800CCB6C
0x1800ccb63  and     dword ptr [rbx+8], 0FFFFFFFBh
0x1800ccb67  jmp     short loc_1800CCB6C
0x1800ccb69  mov     [rdi], rsi
0x1800ccb6c  mov     rcx, rbx; this
0x1800ccb6f  call    ?GuessAtType@CSafeArray@@QEAAGXZ; CSafeArray::GuessAtType(void)
0x1800ccb74  mov     rsi, [rsp+28h+arg_8]
0x1800ccb79  mov     [rbx+1Ch], ax
0x1800ccb7d  mov     rax, rbx
0x1800ccb80  mov     rbx, [rsp+28h+arg_0]
0x1800ccb85  add     rsp, 20h
0x1800ccb89  pop     rdi
0x1800ccb8a  retn
```
