# FindExistingCallInCtl

- ea: `0x140011838`
- end: `0x140011917`
- name: `FindExistingCallInCtl`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000f588`
- `0x14000fbac`

## callees

- `0x140001a70`
- `0x140007710`
- `0x140011838`
- `0x1400157f4`
- `0x14001587c`

## pseudocode

```c
__int64 __fastcall FindExistingCallInCtl(__int64 a1, int a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  int v6; // esi
  volatile signed __int32 *v7; // rax
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+30h] [rbp-28h]
  int v10; // [rsp+34h] [rbp-24h]

  result = 0;
  if ( *(_DWORD *)(a1 + 48) == 5 )
  {
    v5 = 0;
    v10 = 0;
    v6 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    v8 = 0u;
    v9 = 1297436229;
    while ( 1 )
    {
      v7 = EnumListEntry((volatile signed __int32 *)(a1 + 56), (__int64)&v8, *(_QWORD *)(a1 + 40) + 8LL, 0);
      if ( !v7 )
        break;
      v5 = (__int64)(v7 - 4);
      if ( v7 != (volatile signed __int32 *)16 && *(_DWORD *)(v5 + 48) == 1129337936 )
      {
        if ( *(_QWORD *)(v5 + 80) == a1 && *(unsigned __int16 *)(v5 + 316) == a2 )
        {
          v6 = 1;
          break;
        }
        DereferenceRefCount(v5);
      }
    }
    EnumComplete(&v8, *(_QWORD *)(a1 + 40) + 8LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a1 + 24))(a1);
    return v5 & -(__int64)(v6 != 0);
  }
  return result;
}

```

## disassembly

```asm
0x140011838  mov     r11, rsp
0x14001183b  mov     [r11+10h], rbx
0x14001183f  mov     [r11+18h], rbp
0x140011843  push    rsi
0x140011844  push    rdi
0x140011845  push    r14
0x140011847  sub     rsp, 40h
0x14001184b  xor     eax, eax
0x14001184d  mov     ebp, edx
0x14001184f  cmp     dword ptr [rcx+30h], 5
0x140011853  mov     rbx, rcx
0x140011856  jnz     loc_140011903
0x14001185c  xorps   xmm0, xmm0
0x14001185f  xor     edi, edi
0x140011861  movups  [rsp+58h+var_38], xmm0
0x140011866  mov     [r11-28h], rax
0x14001186a  xor     esi, esi
0x14001186c  lock inc dword ptr [rcx+10h]
0x140011870  mov     [r11-30h], rax
0x140011874  mov     [r11-38h], rax
0x140011878  mov     [rsp+58h+var_28], 4D554E45h
0x140011880  mov     r8, [rbx+28h]
0x140011884  lea     rdx, [rsp+58h+var_38]
0x140011889  add     r8, 8
0x14001188d  lea     rcx, [rbx+38h]
0x140011891  xor     r9d, r9d
0x140011894  call    EnumListEntry
0x140011899  test    rax, rax
0x14001189c  jz      short loc_1400118D0
0x14001189e  lea     rdi, [rax-10h]
0x1400118a2  test    rdi, rdi
0x1400118a5  jz      short loc_140011880
0x1400118a7  cmp     dword ptr [rdi+30h], 43505450h
0x1400118ae  jnz     short loc_140011880
0x1400118b0  cmp     [rdi+50h], rbx
0x1400118b4  jnz     short loc_1400118C1
0x1400118b6  movzx   eax, word ptr [rdi+13Ch]
0x1400118bd  cmp     eax, ebp
0x1400118bf  jz      short loc_1400118CB
0x1400118c1  mov     rcx, rdi
0x1400118c4  call    DereferenceRefCount
0x1400118c9  jmp     short loc_140011880
0x1400118cb  mov     esi, 1
0x1400118d0  mov     rdx, [rbx+28h]
0x1400118d4  lea     rcx, [rsp+58h+var_38]
0x1400118d9  add     rdx, 8
0x1400118dd  call    EnumComplete
0x1400118e2  or      eax, 0FFFFFFFFh
0x1400118e5  lock xadd [rbx+10h], eax
0x1400118ea  cmp     eax, 1
0x1400118ed  jnz     short loc_1400118FB
0x1400118ef  mov     rax, [rbx+18h]
0x1400118f3  mov     rcx, rbx
0x1400118f6  call    _guard_dispatch_icall
0x1400118fb  neg     esi
0x1400118fd  sbb     rax, rax
0x140011900  and     rax, rdi
0x140011903  mov     rbx, [rsp+58h+arg_8]
0x140011908  mov     rbp, [rsp+58h+arg_10]
0x14001190d  add     rsp, 40h
0x140011911  pop     r14
0x140011913  pop     rdi
0x140011914  pop     rsi
0x140011915  retn
```
