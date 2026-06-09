# pSpUtilsQueryOverrideValue

- ea: `0x18000762c`
- end: `0x1800076cd`
- name: `pSpUtilsQueryOverrideValue`
- size: `161`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, HANDLE, PCWSTR SourceString, int, __int64, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800061d8`
- `0x1800077d0`

## callees

- `0x180003988`
- `0x18000762c`

## pseudocode

```c
__int64 __fastcall pSpUtilsQueryOverrideValue(
        HANDLE KeyHandle,
        HANDLE a2,
        PCWSTR SourceString,
        int a4,
        __int64 a5,
        int *a6)
{
  __int64 result; // rax
  int v10; // r14d

  if ( !KeyHandle )
    return 87;
  v10 = *a6;
  if ( !a2 || (result = pSetupQueryValue(a2, SourceString, (__int64)a6), (_DWORD)result) || a4 )
  {
    *a6 = v10;
    result = pSetupQueryValue(KeyHandle, SourceString, (__int64)a6);
    if ( !(_DWORD)result )
    {
      if ( a4 )
        return 1629;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000762c  mov     [rsp+arg_8], rbx
0x180007631  mov     [rsp+arg_10], rbp
0x180007636  push    rsi
0x180007637  push    rdi
0x180007638  push    r14
0x18000763a  sub     rsp, 30h
0x18000763e  mov     [rsp+48h+arg_0], 0
0x180007646  mov     edi, r9d
0x180007649  mov     rbp, r8
0x18000764c  mov     rax, rdx
0x18000764f  mov     rsi, rcx
0x180007652  test    rcx, rcx
0x180007655  jnz     short loc_18000765C
0x180007657  lea     eax, [rcx+57h]
0x18000765a  jmp     short loc_1800076BA
0x18000765c  mov     rbx, [rsp+48h+arg_28]
0x180007661  mov     r14d, [rbx]
0x180007664  test    rax, rax
0x180007667  jz      short loc_18000768D
0x180007669  mov     r9, [rsp+48h+arg_20]
0x18000766e  lea     r8, [rsp+48h+arg_0]
0x180007673  mov     rdx, rbp; SourceString
0x180007676  mov     [rsp+48h+var_28], rbx; __int64
0x18000767b  mov     rcx, rax; KeyHandle
0x18000767e  call    pSetupQueryValue
0x180007683  test    eax, eax
0x180007685  jnz     short loc_18000768D
0x180007687  cmp     [rsp+48h+arg_0], edi
0x18000768b  jz      short loc_1800076BA
0x18000768d  mov     r9, [rsp+48h+arg_20]
0x180007692  lea     r8, [rsp+48h+arg_0]
0x180007697  mov     rdx, rbp; SourceString
0x18000769a  mov     [rbx], r14d
0x18000769d  mov     rcx, rsi; KeyHandle
0x1800076a0  mov     [rsp+48h+var_28], rbx; __int64
0x1800076a5  call    pSetupQueryValue
0x1800076aa  test    eax, eax
0x1800076ac  jnz     short loc_1800076BA
0x1800076ae  cmp     [rsp+48h+arg_0], edi
0x1800076b2  mov     ecx, 65Dh
0x1800076b7  cmovnz  eax, ecx
0x1800076ba  mov     rbx, [rsp+48h+arg_8]
0x1800076bf  mov     rbp, [rsp+48h+arg_10]
0x1800076c4  add     rsp, 30h
0x1800076c8  pop     r14
0x1800076ca  pop     rdi
0x1800076cb  pop     rsi
0x1800076cc  retn
```
