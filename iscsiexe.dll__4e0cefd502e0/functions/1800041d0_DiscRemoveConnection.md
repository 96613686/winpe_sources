# DiscRemoveConnection

- ea: `0x1800041d0`
- end: `0x180004300`
- name: `DiscRemoveConnection`
- size: `304`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001410`
- `0x1800041d0`
- `0x180004e84`
- `0x18000b3c8`

## import_xrefs

- `ISCSIUM!DiscpExecuteMethod` at `0x1800042aa`
- `ISCSIUM!DiscpExecuteMethod` at `0x1800042aa`
- `ISCSIUM!DiscpFreeMemory` at `0x1800042bc`
- `ISCSIUM!DiscpFreeMemory` at `0x1800042d2`
- `ISCSIUM!DiscpFreeMemory` at `0x1800042bc`
- `ISCSIUM!DiscpFreeMemory` at `0x1800042d2`

## pseudocode

```c
__int64 __fastcall DiscRemoveConnection(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  volatile signed __int32 *v6; // rdi
  int v8; // [rsp+50h] [rbp-30h] BYREF
  unsigned int *v9; // [rsp+58h] [rbp-28h] BYREF
  volatile signed __int32 *v10; // [rsp+60h] [rbp-20h] BYREF
  __int128 v11; // [rsp+68h] [rbp-18h] BYREF

  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  if ( !a1 || !a2 )
    return 87;
  v4 = DiscpCheckCallerIsAdmin(a1);
  if ( !v4 )
  {
    v4 = DiscpSelectHBAByUniqueSessionId((void **)a1, &v10);
    if ( !v4 )
    {
      v5 = *(_QWORD *)(a1 + 8);
      v6 = v10;
      *(_QWORD *)&v11 = v5;
      *((_QWORD *)&v11 + 1) = *(_QWORD *)(a2 + 8);
      v8 = 260;
      v9 = 0;
      v4 = DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, *((_QWORD *)v10 + 5), 34, &v11, 16, &v9, &v8, 4);
      if ( !v4 )
      {
        v4 = *v9;
        DiscpFreeMemory(v9);
      }
      if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) == 1 )
        DiscpFreeMemory(v6);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800041d0  mov     [rsp-18h+arg_10], rbx
0x1800041d5  push    rbp
0x1800041d6  push    rsi
0x1800041d7  push    rdi
0x1800041d8  mov     rbp, rsp
0x1800041db  sub     rsp, 80h
0x1800041e2  mov     rax, cs:__security_cookie
0x1800041e9  xor     rax, rsp
0x1800041ec  mov     [rbp+var_8], rax
0x1800041f0  mov     [rbp+var_28], 0
0x1800041f8  xorps   xmm0, xmm0
0x1800041fb  mov     [rbp+var_30], 0
0x180004202  mov     rsi, rdx
0x180004205  mov     [rbp+var_20], 0
0x18000420d  mov     rdi, rcx
0x180004210  movups  [rbp+var_18], xmm0
0x180004214  test    rcx, rcx
0x180004217  jz      loc_1800042DC
0x18000421d  test    rdx, rdx
0x180004220  jz      loc_1800042DC
0x180004226  call    DiscpCheckCallerIsAdmin
0x18000422b  mov     ebx, eax
0x18000422d  test    eax, eax
0x18000422f  jnz     loc_1800042D8
0x180004235  lea     rdx, [rbp+var_20]
0x180004239  mov     rcx, rdi
0x18000423c  call    DiscpSelectHBAByUniqueSessionId
0x180004241  mov     ebx, eax
0x180004243  test    eax, eax
0x180004245  jnz     loc_1800042D8
0x18000424b  mov     rax, [rdi+8]
0x18000424f  lea     r9d, [rbx+22h]
0x180004253  mov     rdi, [rbp+var_20]
0x180004257  lea     rcx, MSiSCSI_Operations_GUID
0x18000425e  mov     qword ptr [rbp+var_18], rax
0x180004262  xor     edx, edx
0x180004264  mov     rax, [rsi+8]
0x180004268  mov     qword ptr [rbp+var_18+8], rax
0x18000426c  lea     rax, [rbp+var_30]
0x180004270  mov     [rsp+80h+var_40], 4
0x180004278  mov     [rsp+80h+var_48], rax
0x18000427d  lea     rax, [rbp+var_28]
0x180004281  mov     [rsp+80h+var_50], rax
0x180004286  lea     rax, [rbp+var_18]
0x18000428a  mov     [rbp+var_30], 104h
0x180004291  mov     [rbp+var_28], 0
0x180004299  mov     r8, [rdi+28h]
0x18000429d  mov     [rsp+80h+var_58], 10h
0x1800042a5  mov     [rsp+80h+var_60], rax
0x1800042aa  call    cs:__imp_DiscpExecuteMethod
0x1800042b0  mov     ebx, eax
0x1800042b2  test    eax, eax
0x1800042b4  jnz     short loc_1800042C2
0x1800042b6  mov     rcx, [rbp+var_28]
0x1800042ba  mov     ebx, [rcx]
0x1800042bc  call    cs:__imp_DiscpFreeMemory
0x1800042c2  or      eax, 0FFFFFFFFh
0x1800042c5  lock xadd [rdi+10h], eax
0x1800042ca  cmp     eax, 1
0x1800042cd  jnz     short loc_1800042D8
0x1800042cf  mov     rcx, rdi
0x1800042d2  call    cs:__imp_DiscpFreeMemory
0x1800042d8  mov     eax, ebx
0x1800042da  jmp     short loc_1800042E1
0x1800042dc  mov     eax, 57h ; 'W'
0x1800042e1  mov     rcx, [rbp+var_8]
0x1800042e5  xor     rcx, rsp; StackCookie
0x1800042e8  call    __security_check_cookie
0x1800042ed  mov     rbx, [rsp+80h+arg_10]
0x1800042f5  add     rsp, 80h
0x1800042fc  pop     rdi
0x1800042fd  pop     rsi
0x1800042fe  pop     rbp
0x1800042ff  retn
```
