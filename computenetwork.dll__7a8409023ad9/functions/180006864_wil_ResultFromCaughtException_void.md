# wil::ResultFromCaughtException(void)

- ea: `0x180006864`
- end: `0x1800068a9`
- name: `?ResultFromCaughtException@wil@@YAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(wil *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d0c8`
- `0x18000d13d`
- `0x18000d1b5`
- `0x18000e15a`
- `0x18000e28b`

## callees

- `0x180006864`
- `0x1800078d8`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall wil::ResultFromCaughtException(wil *this, void *a2, unsigned int a3)
{
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-28h]
  _BYTE v5[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (result = *(unsigned int *)g_pfnResultFromCaughtExceptionInternal(v5, 0, 0, &v7), (int)result >= 0) )
  {
    wil::details::in1diag3::_FailFast_Hr(retaddr, a2, a3, (const char *)0x8007023ELL, v4);
  }
  return result;
}

```

## disassembly

```asm
0x180006864  sub     rsp, 48h
0x180006868  mov     [rsp+48h+arg_0], 0
0x18000686d  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180006874  test    rax, rax
0x180006877  jz      short loc_180006898
0x180006879  lea     r9, [rsp+48h+arg_0]
0x18000687e  xor     r8d, r8d
0x180006881  xor     edx, edx
0x180006883  lea     rcx, [rsp+48h+var_18]
0x180006888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000688d  mov     eax, [rax]
0x18000688f  test    eax, eax
0x180006891  jns     short loc_180006898
0x180006893  add     rsp, 48h
0x180006897  retn
0x180006898  mov     rcx, [rsp+48h]; this
0x18000689d  mov     r9d, 8007023Eh; char *
0x1800068a3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
