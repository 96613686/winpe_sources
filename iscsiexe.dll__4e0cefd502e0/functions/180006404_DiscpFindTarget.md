# DiscpFindTarget

- ea: `0x180006404`
- end: `0x1800064f2`
- name: `DiscpFindTarget`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, char, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006598`
- `0x180006c30`
- `0x180007320`
- `0x1800076dc`

## callees

- `0x180006404`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006451`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800064a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006451`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800064a7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800064d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800064d8`
- `ntdll!RtlEnterCriticalSection` at `0x180006428`
- `ntdll!RtlEnterCriticalSection` at `0x180006428`

## pseudocode

```c
__int64 __fastcall DiscpFindTarget(__int64 a1, __int64 a2, char a3, _QWORD *a4)
{
  _QWORD *v8; // rbx
  unsigned int v9; // r12d
  _QWORD *v10; // rbp
  _QWORD *v11; // rdi
  _QWORD *v12; // rsi
  __int64 v13; // rcx

  RtlEnterCriticalSection(&DiscpCritSection);
  v8 = DiscpTargetsList;
  v9 = -268500951;
  while ( 1 )
  {
    if ( v8 == &DiscpTargetsList )
      goto LABEL_22;
    if ( *((int *)v8 + 9) >= 0 && !(unsigned int)_o__wcsicmp(v8[6], a1) )
      break;
    v8 = (_QWORD *)*v8;
  }
  if ( !a2 && !a3 )
  {
LABEL_21:
    _InterlockedIncrement((volatile signed __int32 *)v8 + 8);
    *a4 = v8;
    v9 = 0;
    goto LABEL_22;
  }
  v10 = v8 + 2;
  v11 = v8 + 2;
  if ( !a2 )
  {
    while ( 1 )
    {
      v8 = v11 - 2;
      if ( !v11[6] )
        goto LABEL_21;
      v11 = (_QWORD *)*v11;
      if ( v11 == v10 )
        goto LABEL_22;
    }
  }
  v12 = 0;
  do
  {
    v8 = v11 - 2;
    v13 = v11[6];
    if ( v13 )
    {
      if ( !(unsigned int)_o__wcsicmp(v13, a2) )
        goto LABEL_21;
    }
    else
    {
      v12 = v11 - 2;
    }
    v11 = (_QWORD *)*v11;
  }
  while ( v11 != v10 );
  if ( !a3 && v12 )
  {
    v8 = v12;
    goto LABEL_21;
  }
LABEL_22:
  RtlLeaveCriticalSection(&DiscpCritSection);
  return v9;
}

```

## disassembly

```asm
0x180006404  push    rbx
0x180006406  push    rbp
0x180006407  push    rsi
0x180006408  push    rdi
0x180006409  push    r12
0x18000640b  push    r13
0x18000640d  push    r14
0x18000640f  push    r15
0x180006411  sub     rsp, 28h
0x180006415  mov     rdi, rcx
0x180006418  mov     r13, r9
0x18000641b  lea     rcx, DiscpCritSection; CriticalSection
0x180006422  mov     r15b, r8b
0x180006425  mov     r14, rdx
0x180006428  call    cs:__imp_RtlEnterCriticalSection
0x18000642e  mov     rbx, cs:DiscpTargetsList
0x180006435  lea     rsi, DiscpTargetsList
0x18000643c  mov     r12d, 0EFFF0029h
0x180006442  jmp     short loc_18000645E
0x180006444  cmp     dword ptr [rbx+24h], 0
0x180006448  jl      short loc_18000645B
0x18000644a  mov     rcx, [rbx+30h]
0x18000644e  mov     rdx, rdi
0x180006451  call    cs:__imp__o__wcsicmp
0x180006457  test    eax, eax
0x180006459  jz      short loc_180006465
0x18000645b  mov     rbx, [rbx]
0x18000645e  cmp     rbx, rsi
0x180006461  jnz     short loc_180006444
0x180006463  jmp     short loc_1800064D1
0x180006465  test    r14, r14
0x180006468  jnz     short loc_18000646F
0x18000646a  test    r15b, r15b
0x18000646d  jz      short loc_1800064C6
0x18000646f  lea     rbp, [rbx+10h]
0x180006473  mov     rdi, rbp
0x180006476  test    r14, r14
0x180006479  jnz     short loc_180006490
0x18000647b  lea     rbx, [rdi-10h]
0x18000647f  cmp     qword ptr [rbx+40h], 0
0x180006484  jz      short loc_1800064C6
0x180006486  mov     rdi, [rdi]
0x180006489  cmp     rdi, rbp
0x18000648c  jnz     short loc_18000647B
0x18000648e  jmp     short loc_1800064D1
0x180006490  xor     esi, esi
0x180006492  lea     rbx, [rdi-10h]
0x180006496  mov     rcx, [rbx+40h]
0x18000649a  test    rcx, rcx
0x18000649d  jnz     short loc_1800064A4
0x18000649f  mov     rsi, rbx
0x1800064a2  jmp     short loc_1800064B1
0x1800064a4  mov     rdx, r14
0x1800064a7  call    cs:__imp__o__wcsicmp
0x1800064ad  test    eax, eax
0x1800064af  jz      short loc_1800064C6
0x1800064b1  mov     rdi, [rdi]
0x1800064b4  cmp     rdi, rbp
0x1800064b7  jnz     short loc_180006492
0x1800064b9  test    r15b, r15b
0x1800064bc  jnz     short loc_1800064D1
0x1800064be  test    rsi, rsi
0x1800064c1  jz      short loc_1800064D1
0x1800064c3  mov     rbx, rsi
0x1800064c6  lock inc dword ptr [rbx+20h]
0x1800064ca  mov     [r13+0], rbx
0x1800064ce  xor     r12d, r12d
0x1800064d1  lea     rcx, DiscpCritSection; CriticalSection
0x1800064d8  call    cs:__imp_RtlLeaveCriticalSection
0x1800064de  mov     eax, r12d
0x1800064e1  add     rsp, 28h
0x1800064e5  pop     r15
0x1800064e7  pop     r14
0x1800064e9  pop     r13
0x1800064eb  pop     r12
0x1800064ed  pop     rdi
0x1800064ee  pop     rsi
0x1800064ef  pop     rbp
0x1800064f0  pop     rbx
0x1800064f1  retn
```
