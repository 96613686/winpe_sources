# I_ValidatePageHashesBlob

- ea: `0x180094574`
- end: `0x180094666`
- name: `I_ValidatePageHashesBlob`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180059578`
- `0x18009474c`
- `0x180095c78`

## callees

- `0x180094574`
- `0x180094670`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1800945c0`
- `ntoskrnl!RtlCompareMemory` at `0x1800945e3`
- `ntoskrnl!RtlCompareMemory` at `0x180094641`
- `ntoskrnl!RtlCompareMemory` at `0x1800945c0`
- `ntoskrnl!RtlCompareMemory` at `0x1800945e3`
- `ntoskrnl!RtlCompareMemory` at `0x180094641`

## pseudocode

```c
_BOOL8 __fastcall I_ValidatePageHashesBlob(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  bool v5; // zf
  __int64 v7; // rbp
  const void *v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int *v13; // r8
  const void **v14; // r9
  _BOOL8 result; // rax
  int Source1; // [rsp+50h] [rbp+8h] BYREF

  v5 = *(_DWORD *)(a1 + 32) == 10;
  v7 = a4;
  Source1 = 0;
  result = 0;
  if ( v5 )
  {
    v10 = *(const void **)(a1 + 40);
    if ( v10 )
    {
      if ( *(_QWORD *)(a1 + 56)
        && (RtlCompareMemory(qword_180032010, v10, 0xAu) == 10
         || RtlCompareMemory(qword_180032030, *(const void **)(a1 + 40), 0xAu) == 10) )
      {
        v11 = *(_QWORD *)(a1 + 56);
        if ( v11 >= a2 )
        {
          v12 = *(unsigned int *)(a1 + 48);
          if ( (unsigned int)v12 <= a3
            && (int)MinAsn1ExtractContent(v11, v12, a5, a5 + 8) >= 0
            && !(*v13 % (unsigned __int64)(v7 + 4))
            && *v13 / (unsigned __int64)(v7 + 4)
            && *v14
            && RtlCompareMemory(&Source1, *v14, 4u) == 4 )
          {
            return 1;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180094574  push    rbx
0x180094576  push    rbp
0x180094577  push    rsi
0x180094578  push    rdi
0x180094579  sub     rsp, 28h
0x18009457d  cmp     dword ptr [rcx+20h], 0Ah
0x180094581  mov     edi, r8d
0x180094584  mov     ebp, r9d
0x180094587  mov     rsi, rdx
0x18009458a  mov     rbx, rcx
0x18009458d  mov     [rsp+48h+Source1], 0
0x180094595  jnz     loc_180094662
0x18009459b  mov     rdx, [rcx+28h]; Source2
0x18009459f  test    rdx, rdx
0x1800945a2  jz      loc_180094662
0x1800945a8  cmp     qword ptr [rcx+38h], 0
0x1800945ad  jz      loc_180094662
0x1800945b3  mov     r8d, 0Ah; Length
0x1800945b9  lea     rcx, qword_180032010; Source1
0x1800945c0  call    cs:__imp_RtlCompareMemory
0x1800945c7  nop     dword ptr [rax+rax+00h]
0x1800945cc  cmp     rax, 0Ah
0x1800945d0  jz      short loc_1800945F5
0x1800945d2  mov     rdx, [rbx+28h]; Source2
0x1800945d6  lea     rcx, qword_180032030; Source1
0x1800945dd  mov     r8d, 0Ah; Length
0x1800945e3  call    cs:__imp_RtlCompareMemory
0x1800945ea  nop     dword ptr [rax+rax+00h]
0x1800945ef  cmp     rax, 0Ah
0x1800945f3  jnz     short loc_180094662
0x1800945f5  mov     rcx, [rbx+38h]
0x1800945f9  cmp     rcx, rsi
0x1800945fc  jb      short loc_180094662
0x1800945fe  mov     edx, [rbx+30h]
0x180094601  cmp     edx, edi
0x180094603  ja      short loc_180094662
0x180094605  mov     r8, [rsp+48h+arg_20]
0x18009460a  lea     r9, [r8+8]
0x18009460e  call    MinAsn1ExtractContent
0x180094613  test    eax, eax
0x180094615  js      short loc_180094662
0x180094617  mov     eax, [r8]
0x18009461a  lea     rcx, [rbp+4]
0x18009461e  xor     edx, edx
0x180094620  div     rcx
0x180094623  test    rdx, rdx
0x180094626  jnz     short loc_180094662
0x180094628  cmp     rax, 1
0x18009462c  jb      short loc_180094662
0x18009462e  mov     rdx, [r9]; Source2
0x180094631  test    rdx, rdx
0x180094634  jz      short loc_180094662
0x180094636  mov     r8d, 4; Length
0x18009463c  lea     rcx, [rsp+48h+Source1]; Source1
0x180094641  call    cs:__imp_RtlCompareMemory
0x180094648  nop     dword ptr [rax+rax+00h]
0x18009464d  cmp     rax, 4
0x180094651  jnz     short loc_180094662
0x180094653  mov     eax, 1
0x180094658  add     rsp, 28h
0x18009465c  pop     rdi
0x18009465d  pop     rsi
0x18009465e  pop     rbp
0x18009465f  pop     rbx
0x180094660  retn
0x180094662  xor     eax, eax
0x180094664  jmp     short loc_180094658
```
