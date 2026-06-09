# InsideModalLoop

- ea: `0x180018080`
- end: `0x18001815f`
- name: `InsideModalLoop`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180008630`
- `0x18000bd34`
- `0x180017f70`
- `0x180018080`

## pseudocode

```c
__int64 __fastcall InsideModalLoop(CThreadLocalValue *a1)
{
  int Value; // ebx
  int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  int v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  if ( a1 )
  {
    v3 = 0;
    Value = TThreadLocalValue<int>::GetValue(a1, &v8);
    if ( Value >= 0 )
    {
      if ( v8 >= 0 )
      {
        LOBYTE(v3) = v8 > 0;
        goto LABEL_16;
      }
      Value = -2147023537;
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        goto LABEL_16;
      v5 = 18;
      v6 = (unsigned int)v8;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        goto LABEL_16;
      v5 = 17;
      v6 = (unsigned int)Value;
    }
    WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_4e4a8dc55cfe315632bff27c17d4aad1_Traceguids, v6);
LABEL_16:
    *(_DWORD *)a1 = v3;
    return (unsigned int)Value;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_4e4a8dc55cfe315632bff27c17d4aad1_Traceguids);
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x180018080  mov     [rsp+arg_8], rbx
0x180018085  mov     [rsp+arg_10], rsi
0x18001808a  push    rdi
0x18001808b  sub     rsp, 20h
0x18001808f  mov     [rsp+28h+arg_0], 0
0x180018097  mov     rsi, rcx
0x18001809a  test    rcx, rcx
0x18001809d  jnz     short loc_1800180D2
0x18001809f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180a6  lea     rax, WPP_GLOBAL_Control
0x1800180ad  cmp     rcx, rax
0x1800180b0  jz      short loc_1800180CB
0x1800180b2  cmp     byte ptr [rcx+19h], 2
0x1800180b6  jb      short loc_1800180CB
0x1800180b8  mov     rcx, [rcx+10h]
0x1800180bc  lea     edx, [rsi+10h]
0x1800180bf  lea     r8, WPP_4e4a8dc55cfe315632bff27c17d4aad1_Traceguids
0x1800180c6  call    WPP_SF_
0x1800180cb  mov     ebx, 80004003h
0x1800180d0  jmp     short loc_18001814D
0x1800180d2  lea     rdx, [rsp+28h+arg_0]
0x1800180d7  xor     edi, edi
0x1800180d9  call    ?GetValue@?$TThreadLocalValue@H@@QEBAJPEAH@Z; TThreadLocalValue<int>::GetValue(int *)
0x1800180de  mov     ebx, eax
0x1800180e0  test    eax, eax
0x1800180e2  jns     short loc_180018115
0x1800180e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180eb  lea     rax, WPP_GLOBAL_Control
0x1800180f2  cmp     rcx, rax
0x1800180f5  jz      short loc_18001814B
0x1800180f7  cmp     byte ptr [rcx+19h], 2
0x1800180fb  jb      short loc_18001814B
0x1800180fd  lea     edx, [rdi+11h]
0x180018100  mov     r9d, ebx
0x180018103  mov     rcx, [rcx+10h]
0x180018107  lea     r8, WPP_4e4a8dc55cfe315632bff27c17d4aad1_Traceguids
0x18001810e  call    WPP_SF_d
0x180018113  jmp     short loc_18001814B
0x180018115  mov     r8d, [rsp+28h+arg_0]
0x18001811a  test    r8d, r8d
0x18001811d  jns     short loc_180018147
0x18001811f  mov     ebx, 8007054Fh
0x180018124  mov     rcx, cs:WPP_GLOBAL_Control
0x18001812b  lea     rax, WPP_GLOBAL_Control
0x180018132  cmp     rcx, rax
0x180018135  jz      short loc_18001814B
0x180018137  cmp     byte ptr [rcx+19h], 2
0x18001813b  jb      short loc_18001814B
0x18001813d  mov     edx, 12h
0x180018142  mov     r9d, r8d
0x180018145  jmp     short loc_180018103
0x180018147  setnle  dil
0x18001814b  mov     [rsi], edi
0x18001814d  mov     rsi, [rsp+28h+arg_10]
0x180018152  mov     eax, ebx
0x180018154  mov     rbx, [rsp+28h+arg_8]
0x180018159  add     rsp, 20h
0x18001815d  pop     rdi
0x18001815e  retn
```
