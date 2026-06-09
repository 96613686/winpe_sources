# DeleteSecurityContextMarshalParams

- ea: `0x180026630`
- end: `0x1800266b9`
- name: `DeleteSecurityContextMarshalParams`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026630`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18002665f`
- `ntoskrnl!ExAllocatePool2` at `0x18002665f`

## pseudocode

```c
__int64 __fastcall DeleteSecurityContextMarshalParams(_QWORD *a1, __int64 *a2, _DWORD *a3)
{
  __int64 Pool2; // rax
  _QWORD *v7; // rdx
  __int64 result; // rax

  *a3 = 80;
  Pool2 = ExAllocatePool2(256, 80, 1131180883);
  if ( Pool2 )
  {
    *a2 = Pool2;
    v7 = (_QWORD *)a1[5];
    if ( v7 )
    {
      *(_QWORD *)(Pool2 + 56) = *v7;
      *(_QWORD *)(Pool2 + 64) = v7[1];
    }
    *(_DWORD *)(Pool2 + 72) = *a1 != 0;
    return 0;
  }
  else
  {
    result = 3221225626LL;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180026630  mov     [rsp+arg_0], rbx
0x180026635  mov     [rsp+arg_8], rsi
0x18002663a  push    rdi
0x18002663b  sub     rsp, 20h
0x18002663f  mov     rsi, r8
0x180026642  mov     dword ptr [r8], 50h ; 'P'
0x180026649  mov     rdi, rdx
0x18002664c  mov     rbx, rcx
0x18002664f  mov     edx, 50h ; 'P'
0x180026654  mov     ecx, 100h
0x180026659  mov     r8d, 436C7353h
0x18002665f  call    cs:__imp_ExAllocatePool2
0x180026666  nop     dword ptr [rax+rax+00h]
0x18002666b  test    rax, rax
0x18002666e  jz      short loc_1800266AE
0x180026670  mov     [rdi], rax
0x180026673  mov     rdx, [rbx+28h]
0x180026677  test    rdx, rdx
0x18002667a  jz      short loc_18002668B
0x18002667c  mov     rcx, [rdx]
0x18002667f  mov     [rax+38h], rcx
0x180026683  mov     rcx, [rdx+8]
0x180026687  mov     [rax+40h], rcx
0x18002668b  xor     ecx, ecx
0x18002668d  mov     edx, 1
0x180026692  cmp     [rbx], rcx
0x180026695  cmovnz  ecx, edx
0x180026698  mov     [rax+48h], ecx
0x18002669b  xor     eax, eax
0x18002669d  mov     rbx, [rsp+28h+arg_0]
0x1800266a2  mov     rsi, [rsp+28h+arg_8]
0x1800266a7  add     rsp, 20h
0x1800266ab  pop     rdi
0x1800266ac  retn
0x1800266ae  xor     ecx, ecx
0x1800266b0  mov     eax, 0C000009Ah
0x1800266b5  mov     [rsi], ecx
0x1800266b7  jmp     short loc_18002669D
```
