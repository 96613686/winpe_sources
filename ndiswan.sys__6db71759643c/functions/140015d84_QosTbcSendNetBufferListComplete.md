# QosTbcSendNetBufferListComplete

- ea: `0x140015d84`
- end: `0x140015e1d`
- name: `QosTbcSendNetBufferListComplete`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011da8`
- `0x1400123e4`

## callees

- `0x140014b70`
- `0x140015d84`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015de6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015de6`

## pseudocode

```c
__int64 __fastcall QosTbcSendNetBufferListComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned int v6; // r8d
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 result; // rax

  v6 = 0;
  if ( *(_QWORD *)(a3 + 120) == *(_QWORD *)(a2 + 32) )
  {
    v8 = *(_QWORD *)(a3 + 16);
    v9 = *(unsigned __int16 *)(v8 + 10);
    if ( !*(_DWORD *)(v9 + v8 + 56) )
    {
      *(_BYTE *)(v9 + v8 + 60) = 1;
      a3 = 0;
      v10 = *(_QWORD *)(v9 + v8 + 32);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 48), 0xFFFFFFFF) == 1 )
      {
        QosNblCadReassemble(v10, 0, 0);
        a3 = *(_QWORD *)(v10 + 24);
        ExFreeToNPagedLookasideList(QosgNblCadLookasideList, (PVOID)v10);
      }
      v6 = 1;
    }
  }
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 36));
  result = v6;
  *a5 = a3;
  return result;
}

```

## disassembly

```asm
0x140015d84  mov     [rsp+arg_0], rbx
0x140015d89  mov     [rsp+arg_8], rsi
0x140015d8e  push    rdi
0x140015d8f  sub     rsp, 20h
0x140015d93  mov     rax, [rdx+20h]
0x140015d97  mov     rbx, r8
0x140015d9a  xor     r8d, r8d
0x140015d9d  mov     rsi, rcx
0x140015da0  cmp     [rbx+78h], rax
0x140015da4  jnz     short loc_140015DF8
0x140015da6  mov     rdi, [rbx+10h]
0x140015daa  movzx   eax, word ptr [rdi+0Ah]
0x140015dae  cmp     [rax+rdi+38h], r8d
0x140015db3  jnz     short loc_140015DF8
0x140015db5  mov     byte ptr [rax+rdi+3Ch], 1
0x140015dba  xor     ebx, ebx
0x140015dbc  mov     rdi, [rax+rdi+20h]
0x140015dc1  or      eax, 0FFFFFFFFh
0x140015dc4  lock xadd [rdi+30h], eax
0x140015dc9  cmp     eax, 1
0x140015dcc  jnz     short loc_140015DF2
0x140015dce  xor     edx, edx
0x140015dd0  mov     rcx, rdi
0x140015dd3  call    QosNblCadReassemble
0x140015dd8  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x140015ddf  mov     rdx, rdi; Entry
0x140015de2  mov     rbx, [rdi+18h]
0x140015de6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015ded  nop     dword ptr [rax+rax+00h]
0x140015df2  mov     r8d, 1
0x140015df8  test    rbx, rbx
0x140015dfb  jz      short loc_140015E01
0x140015dfd  lock inc dword ptr [rsi+24h]
0x140015e01  mov     rcx, [rsp+28h+arg_20]
0x140015e06  mov     eax, r8d
0x140015e09  mov     rsi, [rsp+28h+arg_8]
0x140015e0e  mov     [rcx], rbx
0x140015e11  mov     rbx, [rsp+28h+arg_0]
0x140015e16  add     rsp, 20h
0x140015e1a  pop     rdi
0x140015e1b  retn
```
