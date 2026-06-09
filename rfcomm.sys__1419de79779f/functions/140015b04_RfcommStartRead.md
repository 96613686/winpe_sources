# RfcommStartRead

- ea: `0x140015b04`
- end: `0x140015bd3`
- name: `RfcommStartRead`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400147a0`
- `0x1400174a8`

## callees

- `0x14000d970`
- `0x140015b04`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140015b35`
- `ntoskrnl!ExAllocatePool2` at `0x140015b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015bad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015bad`

## string_xrefs

- `0x140015b94`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommStartRead(_QWORD *a1, _QWORD *a2, __int64 a3, int a4)
{
  unsigned __int16 *v4; // rsi
  _QWORD *Pool2; // rbx
  int v7; // esi

  v4 = (unsigned __int16 *)a1 + 194;
  Pool2 = a2;
  if ( a2 || (Pool2 = (_QWORD *)ExAllocatePool2(64, *v4 + 39LL, 1095001682)) != 0 )
  {
    Pool2[1] = Pool2;
    *Pool2 = Pool2;
    *((_DWORD *)Pool2 + 4) = *v4 + 39;
    v7 = BrbRead(a1[9], a1[33], a1[35], a4, (__int64)(Pool2 + 4), *v4, (__int64)a1);
    if ( v7 < 0 )
      ExFreePoolWithTag(Pool2, 0);
    else
      RefObj_AddRefEx(a1 + 3, 1145128274, 5865, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140015b04  mov     [rsp+arg_0], rbx
0x140015b09  mov     [rsp+arg_8], rsi
0x140015b0e  push    rdi
0x140015b0f  sub     rsp, 40h
0x140015b13  lea     rsi, [rcx+184h]
0x140015b1a  mov     rbx, rdx
0x140015b1d  mov     rdi, rcx
0x140015b20  test    rdx, rdx
0x140015b23  jnz     short loc_140015B49
0x140015b25  movzx   edx, word ptr [rsi]
0x140015b28  lea     ecx, [rbx+40h]
0x140015b2b  add     rdx, 27h ; '''
0x140015b2f  mov     r8d, 41446652h
0x140015b35  call    cs:__imp_ExAllocatePool2
0x140015b3c  nop     dword ptr [rax+rax+00h]
0x140015b41  mov     rbx, rax
0x140015b44  test    rax, rax
0x140015b47  jz      short loc_140015BBB
0x140015b49  mov     [rbx+8], rbx
0x140015b4d  lea     rcx, [rbx+20h]
0x140015b51  mov     [rbx], rbx
0x140015b54  movzx   eax, word ptr [rsi]
0x140015b57  add     eax, 27h ; '''
0x140015b5a  mov     [rsp+48h+var_18], rdi
0x140015b5f  mov     [rbx+10h], eax
0x140015b62  movzx   eax, word ptr [rsi]
0x140015b65  mov     r8, [rdi+118h]
0x140015b6c  mov     rdx, [rdi+108h]
0x140015b73  mov     [rsp+48h+var_20], eax
0x140015b77  mov     [rsp+48h+var_28], rcx
0x140015b7c  mov     rcx, [rdi+48h]
0x140015b80  call    BrbRead
0x140015b85  mov     esi, eax
0x140015b87  test    eax, eax
0x140015b89  js      short loc_140015BA8
0x140015b8b  lea     rcx, [rdi+18h]
0x140015b8f  mov     edx, 44414552h
0x140015b94  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140015b9b  mov     r8d, 16E9h
0x140015ba1  call    RefObj_AddRefEx
0x140015ba6  jmp     short loc_140015BC0
0x140015ba8  xor     edx, edx; Tag
0x140015baa  mov     rcx, rbx; P
0x140015bad  call    cs:__imp_ExFreePoolWithTag
0x140015bb4  nop     dword ptr [rax+rax+00h]
0x140015bb9  jmp     short loc_140015BC0
0x140015bbb  mov     esi, 0C000009Ah
0x140015bc0  mov     rbx, [rsp+48h+arg_0]
0x140015bc5  mov     eax, esi
0x140015bc7  mov     rsi, [rsp+48h+arg_8]
0x140015bcc  add     rsp, 40h
0x140015bd0  pop     rdi
0x140015bd1  retn
```
