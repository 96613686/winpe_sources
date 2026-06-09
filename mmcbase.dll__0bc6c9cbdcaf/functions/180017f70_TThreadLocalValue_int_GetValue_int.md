# TThreadLocalValue<int>::GetValue(int *)

- ea: `0x180017f70`
- end: `0x180017fa8`
- name: `?GetValue@?$TThreadLocalValue@H@@QEBAJPEAH@Z`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180017fb0`
- `0x180018080`
- `0x180018170`

## callees

- `0x180017f70`
- `0x18001b0dc`

## pseudocode

```c
__int64 __fastcall TThreadLocalValue<int>::GetValue(CThreadLocalValue *a1, _DWORD *a2)
{
  __int64 result; // rax
  void *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( !a2 )
    return 2147500035LL;
  result = CThreadLocalValue::GetValue(a1, &v4);
  *a2 = (_DWORD)v4;
  return result;
}

```

## disassembly

```asm
0x180017f70  mov     [rsp+arg_0], rcx
0x180017f75  push    rbx
0x180017f76  sub     rsp, 20h
0x180017f7a  mov     [rsp+28h+arg_0], 0
0x180017f83  mov     rbx, rdx
0x180017f86  test    rdx, rdx
0x180017f89  jz      short loc_180017F9D
0x180017f8b  lea     rdx, [rsp+28h+arg_0]; void **
0x180017f90  call    ?GetValue@CThreadLocalValue@@QEBAJPEAPEAX@Z; CThreadLocalValue::GetValue(void * *)
0x180017f95  mov     ecx, dword ptr [rsp+28h+arg_0]
0x180017f99  mov     [rbx], ecx
0x180017f9b  jmp     short loc_180017FA2
0x180017f9d  mov     eax, 80004003h
0x180017fa2  add     rsp, 20h
0x180017fa6  pop     rbx
0x180017fa7  retn
```
