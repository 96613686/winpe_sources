# RemoveInterfaceFromInterfaceStateNameList(_WNF_STATE_NAME,_GUID)

- ea: `0x18003a028`
- end: `0x18003a188`
- name: `?RemoveInterfaceFromInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@U_GUID@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180011ee4`
- `0x180039818`

## callees

- `0x1800025f0`
- `0x180039b58`
- `0x180039cfc`
- `0x180039dfc`
- `0x18003a028`
- `0x18003a190`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003a075`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003a167`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003a075`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003a167`
- `ntdll!NtDeleteWnfStateName` at `0x18003a149`
- `ntdll!NtDeleteWnfStateName` at `0x18003a149`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoveInterfaceFromInterfaceStateNameList(struct _WNF_STATE_NAME a1, struct _GUID *a2)
{
  int InterfaceStateEntry; // esi
  struct InterfaceStateEntry *v3; // rdi
  unsigned int v4; // r14d
  int InterfaceStateNameList; // eax
  unsigned int v8; // r8d
  int v9; // eax
  int v10; // r8d
  struct InterfaceStateEntry *v11; // rcx
  int v12; // eax
  unsigned int v14; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-44h] BYREF
  void *Block; // [rsp+28h] [rbp-40h] BYREF
  struct InterfaceStateEntry *v17; // [rsp+30h] [rbp-38h] BYREF
  struct _GUID v18; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-18h] BYREF

  InterfaceStateEntry = 0;
  v3 = 0;
  v15 = 0;
  v4 = 0;
  Block = 0;
  v14 = 0;
  v17 = 0;
  v19 = 0;
  while ( 1 )
  {
    do
    {
      if ( InterfaceStateEntry == -2147024774 )
      {
        if ( v3 )
        {
          free(v3);
          v3 = 0;
          Block = 0;
        }
        v4 = 0;
        v14 = 0;
      }
      if ( !v3 )
      {
        InterfaceStateNameList = AllocAndGetInterfaceStateNameList(
                                   a1,
                                   (struct InterfaceStateEntry **)&Block,
                                   &v14,
                                   &v15);
        v3 = (struct InterfaceStateEntry *)Block;
        InterfaceStateEntry = InterfaceStateNameList;
        if ( InterfaceStateNameList < 0 )
          goto LABEL_21;
        v8 = v14;
        v4 = 32 * v14;
        goto LABEL_12;
      }
      v9 = GetInterfaceStateNameList(a1, v3, &v14, &v15);
      InterfaceStateEntry = v9;
    }
    while ( v9 == -2147024774 );
    if ( v9 < 0 )
      goto LABEL_21;
    v8 = v14;
LABEL_12:
    v18 = *a2;
    InterfaceStateEntry = FindInterfaceStateEntry(&v18, v3, v8, &v17);
    if ( InterfaceStateEntry < 0 )
      break;
    v11 = v17;
    v19 = *((_QWORD *)v17 + 2);
    if ( v17 != v3 )
    {
      *(_OWORD *)v17 = *(_OWORD *)v3;
      *((_OWORD *)v11 + 1) = *((_OWORD *)v3 + 1);
    }
    v12 = SetInterfaceStateNameList(a1, (struct InterfaceStateEntry *)((char *)v3 + 32), v10 - 1, &v15);
    InterfaceStateEntry = v12;
    if ( v12 >= 0 )
    {
      NtDeleteWnfStateName(&v19);
      goto LABEL_21;
    }
    if ( v12 != -805306367 )
      goto LABEL_21;
    v14 = v4 >> 5;
  }
  if ( InterfaceStateEntry == -2147023728 )
    InterfaceStateEntry = 1;
LABEL_21:
  if ( v3 )
    free(v3);
  return (unsigned int)InterfaceStateEntry;
}

```

## disassembly

```asm
0x18003a028  push    rbp
0x18003a02a  push    rbx
0x18003a02b  push    rsi
0x18003a02c  push    rdi
0x18003a02d  push    r14
0x18003a02f  push    r15
0x18003a031  mov     rbp, rsp
0x18003a034  sub     rsp, 68h
0x18003a038  mov     rax, cs:__security_cookie
0x18003a03f  xor     rax, rsp
0x18003a042  mov     [rbp+var_10], rax
0x18003a046  xor     esi, esi
0x18003a048  xor     edi, edi
0x18003a04a  mov     [rbp+var_44], esi
0x18003a04d  xor     r14d, r14d
0x18003a050  mov     [rbp+Block], rdi
0x18003a054  mov     r15, rdx
0x18003a057  mov     [rbp+var_48], esi
0x18003a05a  mov     rbx, rcx
0x18003a05d  mov     [rbp+var_38], rsi
0x18003a061  mov     [rbp+var_18], rsi
0x18003a065  cmp     esi, 8007007Ah
0x18003a06b  jnz     short loc_18003A088
0x18003a06d  test    rdi, rdi
0x18003a070  jz      short loc_18003A081
0x18003a072  mov     rcx, rdi; Block
0x18003a075  call    cs:__imp_free
0x18003a07b  xor     edi, edi
0x18003a07d  mov     [rbp+Block], rdi
0x18003a081  xor     r14d, r14d
0x18003a084  mov     [rbp+var_48], r14d
0x18003a088  lea     r9, [rbp+var_44]; unsigned int *
0x18003a08c  mov     rcx, rbx; struct _WNF_STATE_NAME
0x18003a08f  lea     r8, [rbp+var_48]; unsigned int *
0x18003a093  test    rdi, rdi
0x18003a096  jnz     short loc_18003A0BC
0x18003a098  lea     rdx, [rbp+Block]; struct InterfaceStateEntry **
0x18003a09c  call    ?AllocAndGetInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@PEAPEAUInterfaceStateEntry@@PEAK2@Z; AllocAndGetInterfaceStateNameList(_WNF_STATE_NAME,InterfaceStateEntry * *,ulong *,ulong *)
0x18003a0a1  mov     rdi, [rbp+Block]
0x18003a0a5  mov     esi, eax
0x18003a0a7  test    eax, eax
0x18003a0a9  js      loc_18003A15F
0x18003a0af  mov     r8d, [rbp+var_48]
0x18003a0b3  mov     r14d, r8d
0x18003a0b6  shl     r14d, 5
0x18003a0ba  jmp     short loc_18003A0D9
0x18003a0bc  mov     rdx, rdi; struct InterfaceStateEntry *
0x18003a0bf  call    ?GetInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@PEAUInterfaceStateEntry@@PEAK2@Z; GetInterfaceStateNameList(_WNF_STATE_NAME,InterfaceStateEntry *,ulong *,ulong *)
0x18003a0c4  mov     esi, eax
0x18003a0c6  cmp     eax, 8007007Ah
0x18003a0cb  jz      short loc_18003A065
0x18003a0cd  test    eax, eax
0x18003a0cf  js      loc_18003A15F
0x18003a0d5  mov     r8d, [rbp+var_48]; unsigned int
0x18003a0d9  movaps  xmm0, xmmword ptr [r15]
0x18003a0dd  lea     r9, [rbp+var_38]; struct InterfaceStateEntry **
0x18003a0e1  mov     rdx, rdi; struct InterfaceStateEntry *
0x18003a0e4  movdqa  xmmword ptr [rbp+var_28.Data1], xmm0
0x18003a0e9  lea     rcx, [rbp+var_28]; struct _GUID
0x18003a0ed  call    ?FindInterfaceStateEntry@@YAJU_GUID@@PEAUInterfaceStateEntry@@KPEAPEAU2@@Z; FindInterfaceStateEntry(_GUID,InterfaceStateEntry *,ulong,InterfaceStateEntry * *)
0x18003a0f2  mov     esi, eax
0x18003a0f4  test    eax, eax
0x18003a0f6  js      short loc_18003A151
0x18003a0f8  mov     rcx, [rbp+var_38]
0x18003a0fc  mov     rax, [rcx+10h]
0x18003a100  mov     [rbp+var_18], rax
0x18003a104  cmp     rcx, rdi
0x18003a107  jz      short loc_18003A117
0x18003a109  movups  xmm0, xmmword ptr [rdi]
0x18003a10c  movups  xmmword ptr [rcx], xmm0
0x18003a10f  movups  xmm1, xmmword ptr [rdi+10h]
0x18003a113  movups  xmmword ptr [rcx+10h], xmm1
0x18003a117  dec     r8d; unsigned int
0x18003a11a  lea     rdx, [rdi+20h]; struct InterfaceStateEntry *
0x18003a11e  lea     r9, [rbp+var_44]; unsigned int *
0x18003a122  mov     rcx, rbx; struct _WNF_STATE_NAME
0x18003a125  call    ?SetInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@PEAUInterfaceStateEntry@@KPEAK@Z; SetInterfaceStateNameList(_WNF_STATE_NAME,InterfaceStateEntry *,ulong,ulong *)
0x18003a12a  mov     esi, eax
0x18003a12c  test    eax, eax
0x18003a12e  jns     short loc_18003A145
0x18003a130  cmp     eax, 0D0000001h
0x18003a135  jnz     short loc_18003A15F
0x18003a137  mov     eax, r14d
0x18003a13a  shr     eax, 5
0x18003a13d  mov     [rbp+var_48], eax
0x18003a140  jmp     loc_18003A065
0x18003a145  lea     rcx, [rbp+var_18]
0x18003a149  call    cs:__imp_NtDeleteWnfStateName
0x18003a14f  jmp     short loc_18003A15F
0x18003a151  cmp     esi, 80070490h
0x18003a157  mov     eax, 1
0x18003a15c  cmovz   esi, eax
0x18003a15f  test    rdi, rdi
0x18003a162  jz      short loc_18003A16D
0x18003a164  mov     rcx, rdi; Block
0x18003a167  call    cs:__imp_free
0x18003a16d  mov     eax, esi
0x18003a16f  mov     rcx, [rbp+var_10]
0x18003a173  xor     rcx, rsp; StackCookie
0x18003a176  call    __security_check_cookie
0x18003a17b  add     rsp, 68h
0x18003a17f  pop     r15
0x18003a181  pop     r14
0x18003a183  pop     rdi
0x18003a184  pop     rsi
0x18003a185  pop     rbx
0x18003a186  pop     rbp
0x18003a187  retn
```
