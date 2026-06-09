# PsmpSignalQuiesceComplete

- ea: `0x180016544`
- end: `0x180016755`
- name: `PsmpSignalQuiesceComplete`
- size: `529`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800164c4`
- `0x180016530`

## callees

- `0x18000ed68`
- `0x1800114d0`
- `0x180013610`
- `0x1800137a4`
- `0x180016544`
- `0x1800192fc`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800165f9`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800165f9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016601`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016601`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800165cb`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800165cb`

## pseudocode

```c
__int64 __fastcall PsmpSignalQuiesceComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // r14
  signed __int32 v7; // edi
  signed __int8 v8; // r15
  __int64 v9; // rcx
  int v10; // r14d
  unsigned int v11; // esi
  __int64 v12; // r8
  char *v13; // rdx
  __int64 v14; // r8
  signed __int8 v16; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-95h] BYREF
  signed __int32 v18; // [rsp+38h] [rbp-91h] BYREF
  int v19; // [rsp+3Ch] [rbp-8Dh] BYREF
  __int64 v20; // [rsp+40h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-79h] BYREF
  unsigned int *v22; // [rsp+70h] [rbp-59h]
  __int64 v23; // [rsp+78h] [rbp-51h]
  char v24[16]; // [rsp+80h] [rbp-49h] BYREF
  signed __int32 *v25; // [rsp+90h] [rbp-39h]
  __int64 v26; // [rsp+98h] [rbp-31h]
  signed __int8 *v27; // [rsp+A0h] [rbp-29h]
  __int64 v28; // [rsp+A8h] [rbp-21h]
  int *v29; // [rsp+B0h] [rbp-19h]
  __int64 v30; // [rsp+B8h] [rbp-11h]
  __int64 *v31; // [rsp+C0h] [rbp-9h]
  __int64 v32; // [rsp+C8h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+D0h] [rbp+7h] BYREF

  v4 = a3;
  if ( (unsigned int)dword_18003F080 > 4 && tlgKeywordOn((__int64)&dword_18003F080, 1) )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18003F080, (unsigned __int8 *)&dword_180038124, 0, 0, 2u, &v33);
  v7 = 0;
  if ( !v4 )
    RtlAcquireSRWLockShared(a2 + 328);
  v8 = _interlockedbittestandreset((volatile signed __int32 *)(a1 + 32), 1u);
  if ( v8 )
    v7 = _InterlockedDecrement((volatile signed __int32 *)(a2 + 148));
  v9 = a2 + 328;
  if ( v4 )
    RtlReleaseSRWLockExclusive(v9);
  else
    RtlReleaseSRWLockShared(v9, a2, a3, a4);
  v10 = *(_DWORD *)(a1 + 24);
  if ( v8 )
  {
    if ( !v7 )
    {
      if ( (*(_DWORD *)(a2 + 132) & 0x1000) != 0 )
        PsmpIssueHostStateNotification(a2, a2 + 6800, 2);
      PsmpChangeApplicationState(
        a2,
        0,
        (__int64 (__fastcall *)(__int64, __int64, unsigned int *, __int64 *))PsmpTryCompleteQuiescing,
        0xBu,
        1,
        0);
    }
    v11 = 0;
  }
  else
  {
    v11 = -1073741637;
  }
  if ( (unsigned int)dword_18003F080 > 4 && tlgKeywordOn((__int64)&dword_18003F080, 3) )
  {
    v13 = *(char **)(a2 + 8);
    v22 = &v17;
    v17 = v11;
    v23 = v12;
    tlgCreate1Sz_wchar_t((__int64)v24, v13);
    v26 = v14;
    v30 = v14;
    v25 = &v18;
    v32 = (unsigned int)(v14 + 4);
    v27 = &v16;
    v18 = v7;
    v29 = &v19;
    v20 = *(_QWORD *)(a2 + 96);
    v31 = &v20;
    v16 = v8;
    v28 = 1;
    v19 = v10;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18003F080, (unsigned __int8 *)&unk_180038240, 0, 0, v32, &v21);
  }
  return v11;
}

```

## disassembly

```asm
0x180016544  mov     [rsp-8+arg_10], rbx
0x180016549  push    rbp
0x18001654a  push    rsi
0x18001654b  push    rdi
0x18001654c  push    r14
0x18001654e  push    r15
0x180016550  lea     rbp, [rsp-37h]
0x180016555  sub     rsp, 100h
0x18001655c  mov     rax, cs:__security_cookie
0x180016563  xor     rax, rsp
0x180016566  mov     [rbp+57h+var_30], rax
0x18001656a  mov     eax, cs:dword_18003F080
0x180016570  mov     r14b, r8b
0x180016573  mov     rbx, rdx
0x180016576  mov     rsi, rcx
0x180016579  cmp     eax, 4
0x18001657c  jbe     short loc_1800165BD
0x18001657e  mov     edx, 1
0x180016583  lea     rcx, dword_18003F080
0x18001658a  call    _tlgKeywordOn
0x18001658f  test    al, al
0x180016591  jz      short loc_1800165BD
0x180016593  lea     rax, [rbp+57h+var_50]
0x180016597  xor     r9d, r9d
0x18001659a  mov     [rsp+120h+var_F8], rax
0x18001659f  lea     rdx, dword_180038124
0x1800165a6  xor     r8d, r8d
0x1800165a9  mov     [rsp+120h+var_100], 2
0x1800165b1  lea     rcx, dword_18003F080
0x1800165b8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800165bd  xor     edi, edi
0x1800165bf  test    r14b, r14b
0x1800165c2  jnz     short loc_1800165D1
0x1800165c4  lea     rcx, [rbx+148h]
0x1800165cb  call    cs:__imp_RtlAcquireSRWLockShared
0x1800165d1  lock btr dword ptr [rsi+20h], 1
0x1800165d7  setb    r15b
0x1800165db  test    r15b, r15b
0x1800165de  jz      short loc_1800165ED
0x1800165e0  or      edi, 0FFFFFFFFh
0x1800165e3  lock xadd [rbx+94h], edi
0x1800165eb  dec     edi
0x1800165ed  lea     rcx, [rbx+148h]
0x1800165f4  test    r14b, r14b
0x1800165f7  jnz     short loc_180016601
0x1800165f9  call    cs:__imp_RtlReleaseSRWLockShared
0x1800165ff  jmp     short loc_180016607
0x180016601  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180016607  mov     r14d, [rsi+18h]
0x18001660b  test    r15b, r15b
0x18001660e  jnz     short loc_180016617
0x180016610  mov     esi, 0C00000BBh
0x180016615  jmp     short loc_18001666C
0x180016617  test    edi, edi
0x180016619  jnz     short loc_18001666A
0x18001661b  test    dword ptr [rbx+84h], 1000h
0x180016625  jz      short loc_180016642
0x180016627  lea     rdx, [rbx+1A90h]
0x18001662e  mov     [rsp+120h+var_100], 1
0x180016636  lea     r8d, [rdi+2]
0x18001663a  mov     rcx, rbx
0x18001663d  call    PsmpIssueHostStateNotification
0x180016642  mov     [rsp+120h+var_F8], 0
0x18001664b  lea     r8, PsmpTryCompleteQuiescing
0x180016652  mov     r9d, 0Bh
0x180016658  mov     [rsp+120h+var_100], 1
0x180016660  xor     edx, edx
0x180016662  mov     rcx, rbx
0x180016665  call    PsmpChangeApplicationState
0x18001666a  xor     esi, esi
0x18001666c  mov     eax, cs:dword_18003F080
0x180016672  mov     r8d, 4
0x180016678  cmp     eax, r8d
0x18001667b  jbe     loc_180016730
0x180016681  lea     edx, [r8-1]
0x180016685  lea     rcx, dword_18003F080
0x18001668c  call    _tlgKeywordOn
0x180016691  test    al, al
0x180016693  jz      loc_180016730
0x180016699  mov     rdx, [rbx+8]
0x18001669d  lea     rax, [rsp+120h+var_EC]
0x1800166a2  lea     rcx, [rbp+57h+var_A0]
0x1800166a6  mov     [rbp+57h+var_B0], rax
0x1800166aa  mov     [rsp+120h+var_EC], esi
0x1800166ae  mov     [rbp+57h+var_A8], r8
0x1800166b2  call    _tlgCreate1Sz_wchar_t
0x1800166b7  lea     edx, [r8+4]
0x1800166bb  mov     [rbp+57h+var_88], r8
0x1800166bf  lea     rax, [rsp+120h+var_E8]
0x1800166c4  mov     [rbp+57h+var_68], r8
0x1800166c8  mov     [rbp+57h+var_90], rax
0x1800166cc  lea     rcx, dword_18003F080
0x1800166d3  lea     rax, [rsp+120h+var_F0]
0x1800166d8  mov     [rbp+57h+var_58], rdx
0x1800166dc  mov     [rbp+57h+var_80], rax
0x1800166e0  xor     r9d, r9d
0x1800166e3  lea     rax, [rsp+120h+var_E4]
0x1800166e8  mov     [rsp+120h+var_E8], edi
0x1800166ec  mov     [rbp+57h+var_70], rax
0x1800166f0  xor     r8d, r8d
0x1800166f3  mov     rax, [rbx+60h]
0x1800166f7  mov     [rsp+120h+var_E0], rax
0x1800166fc  lea     rax, [rsp+120h+var_E0]
0x180016701  mov     [rbp+57h+var_60], rax
0x180016705  lea     rax, [rbp+57h+var_D0]
0x180016709  mov     [rsp+120h+var_F8], rax
0x18001670e  mov     [rsp+120h+var_100], edx
0x180016712  lea     rdx, unk_180038240
0x180016719  mov     [rsp+120h+var_F0], r15b
0x18001671e  mov     [rbp+57h+var_78], 1
0x180016726  mov     [rsp+120h+var_E4], r14d
0x18001672b  call    _tlgWriteTransfer_EventWriteTransfer
0x180016730  mov     eax, esi
0x180016732  mov     rcx, [rbp+57h+var_30]
0x180016736  xor     rcx, rsp; StackCookie
0x180016739  call    __security_check_cookie
0x18001673e  mov     rbx, [rsp+120h+arg_10]
0x180016746  add     rsp, 100h
0x18001674d  pop     r15
0x18001674f  pop     r14
0x180016751  pop     rdi
0x180016752  pop     rsi
0x180016753  pop     rbp
0x180016754  retn
```
