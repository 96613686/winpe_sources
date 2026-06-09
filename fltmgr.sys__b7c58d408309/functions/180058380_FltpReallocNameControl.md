# FltpReallocNameControl

- ea: `0x180058380`
- end: `0x1800584cf`
- name: `FltpReallocNameControl`
- size: `335`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, _QWORD *, _DWORD *)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18004dbd0`
- `0x180058320`
- `0x180058640`
- `0x180059470`
- `0x180059a00`
- `0x18005a460`
- `0x18005aa30`
- `0x18005b4b0`
- `0x18005b920`
- `0x18005e410`
- `0x180067b00`

## callees

- `0x180022a60`
- `0x180024900`
- `0x180058380`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180079063`
- `ntoskrnl!ExFreePoolWithTag` at `0x180079063`
- `ntoskrnl!ExAllocatePool2` at `0x180058468`
- `ntoskrnl!ExAllocatePool2` at `0x180058468`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007904c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007904c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800583c2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800583c2`

## pseudocode

```c
__int64 __fastcall FltpReallocNameControl(unsigned __int16 *a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v4; // ebx
  PVOID Pool2; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r15d
  void *v12; // rsi
  int v13; // eax
  __int64 result; // rax
  void *v15; // rcx
  unsigned int v16; // [rsp+30h] [rbp-38h]

  v4 = a2;
  if ( a3 )
  {
    *a3 = 0;
    *a4 = 0;
  }
  if ( a2 > 0x400 )
  {
    v11 = 1;
    Pool2 = (PVOID)ExAllocatePool2(256, a2, 879643974);
  }
  else
  {
    Pool2 = ExAllocateFromPagedLookasideList(&stru_18003F440);
    v4 = 1024;
    v11 = 3;
  }
  v12 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  if ( (byte_1800404C3 & 4) != 0 )
  {
    v16 = *a1 >> 1;
    McTemplateU0spddwdd_EtwWriteTransfer(
      v16,
      v9,
      v10,
      a1,
      *((_DWORD *)a1 + 5),
      v4,
      v16,
      *((_QWORD *)a1 + 1),
      *((_DWORD *)a1 + 4),
      v11);
  }
  if ( *a1 + a1[13] )
    memmove(v12, *((const void **)a1 + 1), *a1);
  v13 = *((_DWORD *)a1 + 4);
  if ( (v13 & 1) != 0 )
  {
    v15 = (void *)*((_QWORD *)a1 + 1);
    if ( a3 )
    {
      *a3 = v15;
      *a4 = *((_DWORD *)a1 + 4);
      *((_DWORD *)a1 + 4) &= 0xFFFFFFFC;
    }
    else
    {
      if ( (v13 & 2) != 0 )
      {
        ExFreeToPagedLookasideList(&stru_18003F440, *((PVOID *)a1 + 1));
        *((_DWORD *)a1 + 4) &= ~2u;
      }
      else
      {
        ExFreePoolWithTag(v15, 0x346E4D46u);
      }
      *((_DWORD *)a1 + 4) &= ~1u;
    }
    v13 = *((_DWORD *)a1 + 4);
  }
  *((_DWORD *)a1 + 5) = v4;
  *((_DWORD *)a1 + 4) = v11 | v13;
  *((_QWORD *)a1 + 1) = v12;
  if ( v4 > 0xFFFE )
    LOWORD(v4) = -2;
  result = 0;
  a1[1] = v4;
  return result;
}

```

## disassembly

```asm
0x180058380  mov     [rsp+arg_8], rbx
0x180058385  mov     [rsp+arg_10], rbp
0x18005838a  push    rsi
0x18005838b  push    rdi
0x18005838c  push    r14
0x18005838e  sub     rsp, 50h
0x180058392  mov     ebx, edx
0x180058394  mov     r14, r9
0x180058397  mov     rdi, r8
0x18005839a  mov     rbp, rcx
0x18005839d  test    r8, r8
0x1800583a0  jz      short loc_1800583AA
0x1800583a2  xor     eax, eax
0x1800583a4  mov     [r8], rax
0x1800583a7  mov     [r9], eax
0x1800583aa  mov     [rsp+68h+arg_0], r15
0x1800583af  cmp     ebx, 400h
0x1800583b5  ja      loc_180058454
0x1800583bb  lea     rcx, stru_18003F440; Lookaside
0x1800583c2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1800583c9  nop     dword ptr [rax+rax+00h]
0x1800583ce  mov     ebx, 400h
0x1800583d3  mov     r15d, 3
0x1800583d9  mov     rsi, rax
0x1800583dc  test    rax, rax
0x1800583df  jz      short loc_18005844D
0x1800583e1  test    cs:byte_1800404C3, 4
0x1800583e8  jnz     loc_180058479
0x1800583ee  movzx   ecx, word ptr [rbp+0]
0x1800583f2  movzx   eax, word ptr [rbp+1Ah]
0x1800583f6  add     eax, ecx
0x1800583f8  jz      short loc_180058409
0x1800583fa  mov     rdx, [rbp+8]; Src
0x1800583fe  mov     r8d, ecx; Size
0x180058401  mov     rcx, rsi; void *
0x180058404  call    memmove
0x180058409  mov     eax, [rbp+10h]
0x18005840c  test    al, 1
0x18005840e  jnz     loc_1800584B0
0x180058414  or      eax, r15d
0x180058417  mov     [rbp+14h], ebx
0x18005841a  mov     [rbp+10h], eax
0x18005841d  mov     eax, 0FFFEh
0x180058422  cmp     ebx, eax
0x180058424  mov     [rbp+8], rsi
0x180058428  cmova   ebx, eax
0x18005842b  xor     eax, eax
0x18005842d  mov     [rbp+2], bx
0x180058431  mov     r15, [rsp+68h+arg_0]
0x180058436  mov     rbx, [rsp+68h+arg_8]
0x18005843b  mov     rbp, [rsp+68h+arg_10]
0x180058443  add     rsp, 50h
0x180058447  pop     r14
0x180058449  pop     rdi
0x18005844a  pop     rsi
0x18005844b  retn
0x18005844d  mov     eax, 0C000009Ah
0x180058452  jmp     short loc_180058431
0x180058454  mov     rdx, rbx
0x180058457  mov     ecx, 100h
0x18005845c  mov     r8d, 346E4D46h
0x180058462  mov     r15d, 1
0x180058468  call    cs:__imp_ExAllocatePool2
0x18005846f  nop     dword ptr [rax+rax+00h]
0x180058474  jmp     loc_1800583D9
0x180058479  mov     eax, [rbp+10h]
0x18005847c  mov     r9, rbp
0x18005847f  movzx   ecx, word ptr [rbp+0]
0x180058483  mov     [rsp+68h+var_20], r15d
0x180058488  mov     [rsp+68h+var_28], eax
0x18005848c  mov     rax, [rbp+8]
0x180058490  mov     [rsp+68h+var_30], rax
0x180058495  mov     eax, [rbp+14h]
0x180058498  shr     ecx, 1
0x18005849a  mov     [rsp+68h+var_38], ecx
0x18005849e  mov     [rsp+68h+var_40], ebx
0x1800584a2  mov     [rsp+68h+var_48], eax
0x1800584a6  call    McTemplateU0spddwdd_EtwWriteTransfer
0x1800584ab  jmp     loc_1800583EE
0x1800584b0  mov     rcx, [rbp+8]; P
0x1800584b4  test    rdi, rdi
0x1800584b7  jz      loc_18007903E
0x1800584bd  mov     [rdi], rcx
0x1800584c0  mov     eax, [rbp+10h]
0x1800584c3  mov     [r14], eax
0x1800584c6  and     dword ptr [rbp+10h], 0FFFFFFFCh
0x1800584ca  jmp     loc_180079073
0x18007903e  test    al, 2
0x180079040  jz      short loc_18007905E
0x180079042  mov     rdx, rcx; Entry
0x180079045  lea     rcx, stru_18003F440; Lookaside
0x18007904c  call    cs:__imp_ExFreeToPagedLookasideList
0x180079053  nop     dword ptr [rax+rax+00h]
0x180079058  and     dword ptr [rbp+10h], 0FFFFFFFDh
0x18007905c  jmp     short loc_18007906F
0x18007905e  mov     edx, 346E4D46h; Tag
0x180079063  call    cs:__imp_ExFreePoolWithTag
0x18007906a  nop     dword ptr [rax+rax+00h]
0x18007906f  and     dword ptr [rbp+10h], 0FFFFFFFEh
0x180079073  mov     eax, [rbp+10h]
0x180079076  jmp     loc_180058414
```
