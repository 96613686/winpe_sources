# PsmpDeleteClientContext

- ea: `0x1800162b0`
- end: `0x1800164bb`
- name: `PsmpDeleteClientContext`
- size: `523`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180016254`
- `0x180019bfc`

## callees

- `0x180001fdc`
- `0x1800092b4`
- `0x180009b40`
- `0x1800114d0`
- `0x1800137a4`
- `0x1800162b0`
- `0x1800192fc`
- `0x18001b7e0`
- `0x180022b2c`
- `0x180023ebc`

## import_xrefs

- `ntdll!NtClose` at `0x180016448`
- `ntdll!NtClose` at `0x180016457`
- `ntdll!NtClose` at `0x180016491`
- `ntdll!NtClose` at `0x180016448`
- `ntdll!NtClose` at `0x180016457`
- `ntdll!NtClose` at `0x180016491`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016413`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016413`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016439`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016439`

## pseudocode

```c
__int64 __fastcall PsmpDeleteClientContext(__int64 a1)
{
  _QWORD *v2; // r15
  _QWORD *v3; // r14
  __int64 v4; // rsi
  volatile __int64 *v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // rsi
  _QWORD *v12; // rdi
  _QWORD *v13; // rcx
  int v15; // [rsp+30h] [rbp-49h] BYREF
  int v16; // [rsp+34h] [rbp-45h] BYREF
  __int64 v17; // [rsp+38h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+40h] [rbp-39h] BYREF
  int *v19; // [rsp+60h] [rbp-19h]
  __int64 v20; // [rsp+68h] [rbp-11h]
  int *v21; // [rsp+70h] [rbp-9h]
  __int64 v22; // [rsp+78h] [rbp-1h]
  __int64 *v23; // [rsp+80h] [rbp+7h]
  __int64 v24; // [rsp+88h] [rbp+Fh]

  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    v2 = (_QWORD *)(a1 + 32);
    v3 = *(_QWORD **)(a1 + 32);
    while ( v3 != v2 )
    {
      v4 = (__int64)(v3 - 840);
      if ( (*(_DWORD *)(v3 - 824) & 0x400000) != 0 )
      {
        PsmpChangeApplicationState((__int64)(v3 - 840), 0, 0, 0, 1, 0);
      }
      else if ( *(_DWORD *)(v4 + 344) == 5 )
      {
        PsmpChangeApplicationState((__int64)(v3 - 840), 0, 0, 6u, 6, 0);
      }
      v3 = (_QWORD *)*v3;
      PsmpDeleteCacheEntry(v4, 1);
      PsmpDereferenceApplicationEx(v4, 0);
    }
    v5 = *(volatile __int64 **)(a1 + 56);
    _InterlockedExchange64(v5 + 8, 0);
    PsmpDereferenceManagerContext((PVOID)v5);
  }
  else if ( (*(_BYTE *)a1 & 2) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 96);
    if ( (unsigned int)dword_18003F080 > 4 && tlgKeywordOn((__int64)&dword_18003F080, 3) )
    {
      v15 = *(_DWORD *)(a1 + 24);
      v20 = 4;
      v19 = &v15;
      v16 = *(_DWORD *)(a1 + 32);
      v21 = &v16;
      v17 = *(_QWORD *)(v6 + 96);
      v23 = &v17;
      v22 = 4;
      v24 = 8;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18003F080, (unsigned __int8 *)byte_18003855D, 0, 0, 5u, &v18);
    }
    RtlAcquireSRWLockExclusive(v6 + 328);
    v7 = *(_QWORD *)(a1 + 104);
    if ( *(_QWORD *)(v7 + 8) != a1 + 104 || (v8 = *(_QWORD **)(a1 + 112), *v8 != a1 + 104) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    RtlReleaseSRWLockExclusive(v6 + 328);
    v9 = *(void **)(a1 + 80);
    if ( v9 )
      NtClose(v9);
    v10 = *(void **)(a1 + 88);
    if ( v10 )
      NtClose(v10);
    PsmpDereferenceApplicationEx(v6, 0);
  }
  else if ( (*(_BYTE *)a1 & 4) != 0 )
  {
    v11 = (_QWORD *)(a1 + 32);
    v12 = *(_QWORD **)(a1 + 32);
    while ( v12 != v11 )
    {
      v13 = v12 - 8;
      v12 = (_QWORD *)*v12;
      PsmpDestroyTcEntry(v13);
    }
  }
  NtClose(*(HANDLE *)(a1 + 16));
  return PsmpFreeHeap(a1);
}

```

## disassembly

```asm
0x1800162b0  push    rbp
0x1800162b2  push    rbx
0x1800162b3  push    rsi
0x1800162b4  push    rdi
0x1800162b5  push    r14
0x1800162b7  push    r15
0x1800162b9  lea     rbp, [rsp-2Fh]
0x1800162be  sub     rsp, 0A8h
0x1800162c5  mov     rax, cs:__security_cookie
0x1800162cc  xor     rax, rsp
0x1800162cf  mov     [rbp+57h+var_40], rax
0x1800162d3  test    byte ptr [rcx], 1
0x1800162d6  mov     rbx, rcx
0x1800162d9  jz      loc_180016366
0x1800162df  lea     r15, [rcx+20h]
0x1800162e3  xor     edi, edi
0x1800162e5  mov     r14, [r15]
0x1800162e8  jmp     short loc_18001634F
0x1800162ea  lea     rsi, [r14-1A40h]
0x1800162f1  test    dword ptr [rsi+80h], 400000h
0x1800162fb  jz      short loc_18001630F
0x1800162fd  mov     [rsp+0D0h+var_A8], rdi
0x180016302  xor     r9d, r9d
0x180016305  mov     [rsp+0D0h+var_B0], 1
0x18001630d  jmp     short loc_18001632B
0x18001630f  cmp     dword ptr [rsi+158h], 5
0x180016316  jnz     short loc_180016338
0x180016318  mov     [rsp+0D0h+var_A8], rdi
0x18001631d  mov     r9d, 6
0x180016323  mov     [rsp+0D0h+var_B0], 6
0x18001632b  xor     r8d, r8d
0x18001632e  xor     edx, edx
0x180016330  mov     rcx, rsi
0x180016333  call    PsmpChangeApplicationState
0x180016338  mov     r14, [r14]
0x18001633b  mov     dl, 1
0x18001633d  mov     rcx, rsi
0x180016340  call    PsmpDeleteCacheEntry
0x180016345  xor     edx, edx
0x180016347  mov     rcx, rsi
0x18001634a  call    PsmpDereferenceApplicationEx
0x18001634f  cmp     r14, r15
0x180016352  jnz     short loc_1800162EA
0x180016354  mov     rcx, [rbx+38h]; P
0x180016358  xchg    rdi, [rcx+40h]
0x18001635c  call    PsmpDereferenceManagerContext
0x180016361  jmp     loc_18001648D
0x180016366  test    byte ptr [rcx], 2
0x180016369  jz      loc_18001646E
0x18001636f  mov     eax, cs:dword_18003F080
0x180016375  mov     r15d, 3
0x18001637b  mov     rsi, [rcx+60h]
0x18001637f  cmp     eax, 4
0x180016382  jbe     loc_180016409
0x180016388  mov     edx, r15d
0x18001638b  lea     rcx, dword_18003F080
0x180016392  call    _tlgKeywordOn
0x180016397  test    al, al
0x180016399  jz      short loc_180016409
0x18001639b  mov     eax, [rbx+18h]
0x18001639e  lea     rdx, byte_18003855D
0x1800163a5  mov     [rbp+57h+var_A0], eax
0x1800163a8  lea     rcx, dword_18003F080
0x1800163af  lea     rax, [rbp+57h+var_A0]
0x1800163b3  mov     [rbp+57h+var_68], 4
0x1800163bb  mov     [rbp+57h+var_70], rax
0x1800163bf  xor     r9d, r9d
0x1800163c2  mov     eax, [rbx+20h]
0x1800163c5  xor     r8d, r8d
0x1800163c8  mov     [rbp+57h+var_9C], eax
0x1800163cb  lea     rax, [rbp+57h+var_9C]
0x1800163cf  mov     [rbp+57h+var_60], rax
0x1800163d3  mov     rax, [rsi+60h]
0x1800163d7  mov     [rbp+57h+var_98], rax
0x1800163db  lea     rax, [rbp+57h+var_98]
0x1800163df  mov     [rbp+57h+var_50], rax
0x1800163e3  lea     rax, [rbp+57h+var_90]
0x1800163e7  mov     [rsp+0D0h+var_A8], rax
0x1800163ec  mov     [rsp+0D0h+var_B0], 5
0x1800163f4  mov     [rbp+57h+var_58], 4
0x1800163fc  mov     [rbp+57h+var_48], 8
0x180016404  call    _tlgWriteTransfer_EventWriteTransfer
0x180016409  lea     r14, [rsi+148h]
0x180016410  mov     rcx, r14
0x180016413  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180016419  lea     rax, [rbx+68h]
0x18001641d  mov     rdx, [rax]
0x180016420  cmp     [rdx+8], rax
0x180016424  jnz     short loc_180016469
0x180016426  mov     rcx, [rax+8]
0x18001642a  cmp     [rcx], rax
0x18001642d  jnz     short loc_180016469
0x18001642f  mov     [rcx], rdx
0x180016432  mov     [rdx+8], rcx
0x180016436  mov     rcx, r14
0x180016439  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001643f  mov     rcx, [rbx+50h]; Handle
0x180016443  test    rcx, rcx
0x180016446  jz      short loc_18001644E
0x180016448  call    cs:__imp_NtClose
0x18001644e  mov     rcx, [rbx+58h]; Handle
0x180016452  test    rcx, rcx
0x180016455  jz      short loc_18001645D
0x180016457  call    cs:__imp_NtClose
0x18001645d  xor     edx, edx
0x18001645f  mov     rcx, rsi
0x180016462  call    PsmpDereferenceApplicationEx
0x180016467  jmp     short loc_18001648D
0x180016469  mov     rcx, r15
0x18001646c  int     29h; Win8: RtlFailFast(ecx)
0x18001646e  test    byte ptr [rcx], 4
0x180016471  jz      short loc_18001648D
0x180016473  lea     rsi, [rcx+20h]
0x180016477  mov     rdi, [rsi]
0x18001647a  jmp     short loc_180016488
0x18001647c  lea     rcx, [rdi-40h]
0x180016480  mov     rdi, [rdi]
0x180016483  call    PsmpDestroyTcEntry
0x180016488  cmp     rdi, rsi
0x18001648b  jnz     short loc_18001647C
0x18001648d  mov     rcx, [rbx+10h]; Handle
0x180016491  call    cs:__imp_NtClose
0x180016497  mov     rcx, rbx
0x18001649a  call    PsmpFreeHeap
0x18001649f  mov     rcx, [rbp+57h+var_40]
0x1800164a3  xor     rcx, rsp; StackCookie
0x1800164a6  call    __security_check_cookie
0x1800164ab  add     rsp, 0A8h
0x1800164b2  pop     r15
0x1800164b4  pop     r14
0x1800164b6  pop     rdi
0x1800164b7  pop     rsi
0x1800164b8  pop     rbx
0x1800164b9  pop     rbp
0x1800164ba  retn
```
