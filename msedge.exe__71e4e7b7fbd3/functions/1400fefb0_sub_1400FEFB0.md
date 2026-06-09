# sub_1400FEFB0

- ea: `0x1400fefb0`
- end: `0x1400ff006`
- name: `sub_1400FEFB0`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401eb2e0`

## callees

- `0x1400609e0`
- `0x1400dc4d0`
- `0x1400fefb0`
- `0x140112210`
- `0x14011fa70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14017d067`
- `KERNEL32!GetCurrentThreadId` at `0x14017d19c`
- `KERNEL32!GetCurrentThreadId` at `0x14017d1a9`
- `KERNEL32!GetCurrentThreadId` at `0x14017d1b6`
- `KERNEL32!GetCurrentThreadId` at `0x14017d067`
- `KERNEL32!GetCurrentThreadId` at `0x14017d19c`
- `KERNEL32!GetCurrentThreadId` at `0x14017d1a9`
- `KERNEL32!GetCurrentThreadId` at `0x14017d1b6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14017d0f3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14017d0f3`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x14017d091`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x14017d091`

## pseudocode

```c
unsigned __int64 __fastcall sub_1400FEFB0(unsigned __int64 a1)
{
  unsigned __int64 result; // rax
  unsigned __int64 v2; // rsi
  __int64 v3; // rax
  int v4; // edi
  int v5; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // ebp
  __int64 v10; // r14
  int v11; // ebp
  __int64 v12; // r15
  int v13; // ebp
  __int64 v14; // r13
  __int64 v15; // r12
  unsigned int v16; // edi
  _QWORD v17[5]; // [rsp+0h] [rbp-B8h] BYREF
  char v18; // [rsp+28h] [rbp-90h]
  int v19; // [rsp+30h] [rbp-88h]
  const char **v20; // [rsp+38h] [rbp-80h]
  int *v21; // [rsp+40h] [rbp-78h]
  __int64 v22; // [rsp+50h] [rbp-68h] BYREF
  __int64 v23; // [rsp+58h] [rbp-60h] BYREF
  const char *v24; // [rsp+60h] [rbp-58h] BYREF
  int v25; // [rsp+6Ch] [rbp-4Ch] BYREF
  __int64 v26; // [rsp+70h] [rbp-48h]

  if ( byte_14042F272 )
    goto LABEL_4;
  while ( 1 )
  {
    result = (unsigned __int64)v17 ^ v26;
    if ( _security_cookie == ((unsigned __int64)v17 ^ v26) )
      break;
    a1 = (unsigned __int64)v17 ^ v26;
LABEL_4:
    v2 = a1;
    v3 = *(_QWORD *)(a1 + 24);
    v4 = *(_DWORD *)(v3 + 4);
    v5 = *(_DWORD *)(v3 + 8);
    CurrentThreadId = GetCurrentThreadId();
    if ( v5 != 0 && CurrentThreadId == v4 )
    {
      __debugbreak();
      BUG();
    }
    if ( CurrentThreadId == v4 )
    {
      if ( !TryAcquireSRWLockExclusive((PSRWLOCK)(v2 + 40)) )
        sub_1400609E0((PSRWLOCK)(v2 + 40));
      v7 = *(_QWORD *)(v2 + 24);
      v8 = *(_QWORD *)(v2 + 88);
      v9 = *(_DWORD *)(v7 + 8);
      if ( v9 )
      {
        if ( v9 != GetCurrentThreadId() )
        {
          __debugbreak();
          BUG();
        }
        v7 = *(_QWORD *)(v2 + 24);
      }
      v10 = *(_QWORD *)(*(_QWORD *)(v2 + 176) + 40LL);
      v11 = *(_DWORD *)(v7 + 8);
      if ( v11 )
      {
        if ( v11 != GetCurrentThreadId() )
        {
          __debugbreak();
          BUG();
        }
        v7 = *(_QWORD *)(v2 + 24);
      }
      v12 = *(_QWORD *)(*(_QWORD *)(v2 + 168) + 40LL);
      v13 = *(_DWORD *)(v7 + 8);
      if ( v13 && v13 != GetCurrentThreadId() )
      {
        __debugbreak();
        BUG();
      }
      v14 = *(_QWORD *)(v2 + 192);
      v15 = *(_QWORD *)(v2 + 200);
      ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 40));
      v22 = 306;
      if ( byte_14042F272 )
      {
        v16 = (unsigned __int8)byte_14042F272;
        v23 = sub_1400DC4D0(*(unsigned int *)(v2 + 8));
        v25 = v8 + v10 + v12 + 1022611261 * ((unsigned __int64)(v15 - v14) >> 3);
        v24 = "value";
        v21 = &v25;
        v20 = &v24;
        v17[4] = qword_1403AD6A8;
        v19 = 0;
        v18 = 67;
        sub_140112210(v16, (char)&v22, (char)&v23, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400fefb0  push    r15
0x1400fefb2  push    r14
0x1400fefb4  push    r13
0x1400fefb6  push    r12
0x1400fefb8  push    rsi
0x1400fefb9  push    rdi
0x1400fefba  push    rbp
0x1400fefbb  push    rbx
0x1400fefbc  sub     rsp, 78h
0x1400fefc0  mov     rax, cs:__security_cookie
0x1400fefc7  xor     rax, rsp
0x1400fefca  mov     [rsp+0B8h+var_48], rax
0x1400fefcf  mov     al, cs:byte_14042F272
0x1400fefd5  test    al, al
0x1400fefd7  jnz     loc_14017D05A
0x1400fefdd  mov     rax, [rsp+0B8h+var_48]
0x1400fefe2  xor     rax, rsp
0x1400fefe5  mov     rcx, cs:__security_cookie
0x1400fefec  cmp     rcx, rax
0x1400fefef  jnz     loc_14017D04D
0x1400feff5  add     rsp, 78h
0x1400feff9  pop     rbx
0x1400feffa  pop     rbp
0x1400feffb  pop     rdi
0x1400feffc  pop     rsi
0x1400feffd  pop     r12
0x1400fefff  pop     r13
0x1400ff001  pop     r14
0x1400ff003  pop     r15
0x1400ff005  retn
0x14017d04d  mov     rcx, [rsp+0B8h+var_48]
0x14017d052  xor     rcx, rsp; StackCookie
0x14017d055  call    __security_check_cookie
0x14017d05a  mov     rsi, rcx
0x14017d05d  mov     rax, [rcx+18h]
0x14017d061  mov     edi, [rax+4]
0x14017d064  mov     ebx, [rax+8]
0x14017d067  call    cs:__imp_GetCurrentThreadId
0x14017d06d  test    ebx, ebx
0x14017d06f  setnz   cl
0x14017d072  cmp     eax, edi
0x14017d074  setz    dl
0x14017d077  and     dl, cl
0x14017d079  cmp     dl, 1
0x14017d07c  jz      loc_14017D187
0x14017d082  cmp     eax, edi
0x14017d084  jnz     loc_1400FEFDD
0x14017d08a  lea     rdi, [rsi+28h]
0x14017d08e  mov     rcx, rdi; SRWLock
0x14017d091  call    cs:TryAcquireSRWLockExclusive
0x14017d097  test    al, al
0x14017d099  jnz     short loc_14017D0A3
0x14017d09b  mov     rcx, rdi; SRWLock
0x14017d09e  call    sub_1400609E0
0x14017d0a3  mov     rax, [rsi+18h]
0x14017d0a7  mov     rbx, [rsi+58h]
0x14017d0ab  mov     ebp, [rax+8]
0x14017d0ae  test    ebp, ebp
0x14017d0b0  jnz     loc_14017D19C
0x14017d0b6  mov     rcx, [rsi+0B0h]
0x14017d0bd  mov     r14, [rcx+28h]
0x14017d0c1  mov     ebp, [rax+8]
0x14017d0c4  test    ebp, ebp
0x14017d0c6  jnz     loc_14017D1A9
0x14017d0cc  mov     rcx, [rsi+0A8h]
0x14017d0d3  mov     r15, [rcx+28h]
0x14017d0d7  mov     ebp, [rax+8]
0x14017d0da  test    ebp, ebp
0x14017d0dc  jnz     loc_14017D1B6
0x14017d0e2  mov     r13, [rsi+0C0h]
0x14017d0e9  mov     r12, [rsi+0C8h]
0x14017d0f0  mov     rcx, rdi; SRWLock
0x14017d0f3  call    cs:__imp_ReleaseSRWLockExclusive
0x14017d0f9  mov     [rsp+0B8h+var_68], 132h
0x14017d102  mov     al, cs:byte_14042F272
0x14017d108  test    al, al
0x14017d10a  jz      loc_1400FEFDD
0x14017d110  movzx   edi, al
0x14017d113  add     r14d, ebx
0x14017d116  sub     r12, r13
0x14017d119  shr     r12, 3
0x14017d11d  imul    ebx, r12d, 3CF3CF3Dh
0x14017d124  add     ebx, r15d
0x14017d127  add     ebx, r14d
0x14017d12a  mov     ecx, [rsi+8]
0x14017d12d  call    sub_1400DC4D0
0x14017d132  lea     r8, [rsp+0B8h+var_60]
0x14017d137  mov     [r8], rax
0x14017d13a  lea     rax, [rsp+0B8h+var_4C]
0x14017d13f  mov     [rax], ebx
0x14017d141  lea     rcx, aValue; "value"
0x14017d148  lea     rdx, [rsp+0B8h+var_58]
0x14017d14d  mov     [rdx], rcx
0x14017d150  mov     [rsp+0B8h+var_78], rax
0x14017d155  mov     [rsp+0B8h+var_80], rdx
0x14017d15a  lea     rax, qword_1403AD6A8
0x14017d161  mov     [rsp+0B8h+var_98], rax
0x14017d166  mov     [rsp+0B8h+var_88], 0
0x14017d16e  mov     [rsp+0B8h+var_90], 43h ; 'C'
0x14017d173  lea     rdx, [rsp+0B8h+var_68]
0x14017d178  mov     ecx, edi
0x14017d17a  xor     r9d, r9d
0x14017d17d  call    sub_140112210
0x14017d182  jmp     loc_1400FEFDD
0x14017d187  int     3; Trap to Debugger
0x14017d188  ud2
0x14017d18a  mov     rax, [rsi+18h]
0x14017d18e  jmp     loc_14017D0B6
0x14017d193  mov     rax, [rsi+18h]
0x14017d197  jmp     loc_14017D0CC
0x14017d19c  call    cs:__imp_GetCurrentThreadId
0x14017d1a2  cmp     ebp, eax
0x14017d1a4  jz      short loc_14017D18A
0x14017d1a6  int     3; Trap to Debugger
0x14017d1a7  ud2
0x14017d1a9  call    cs:__imp_GetCurrentThreadId
0x14017d1af  cmp     ebp, eax
0x14017d1b1  jz      short loc_14017D193
0x14017d1b3  int     3; Trap to Debugger
0x14017d1b4  ud2
0x14017d1b6  call    cs:__imp_GetCurrentThreadId
0x14017d1bc  cmp     ebp, eax
0x14017d1be  jz      loc_14017D0E2
0x14017d1c4  int     3; Trap to Debugger
0x14017d1c5  ud2
```
