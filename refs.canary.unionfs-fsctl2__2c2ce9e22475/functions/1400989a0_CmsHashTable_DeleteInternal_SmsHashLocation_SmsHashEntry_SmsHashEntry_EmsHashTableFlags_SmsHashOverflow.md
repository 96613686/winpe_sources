# CmsHashTable::DeleteInternal(_SmsHashLocation *,SmsHashEntry *,SmsHashEntry *,EmsHashTableFlags,_SmsHashOverflow * *)

- ea: `0x1400989a0`
- end: `0x140098b7e`
- name: `?DeleteInternal@CmsHashTable@@AEAAXPEAU_SmsHashLocation@@PEAUSmsHashEntry@@1W4EmsHashTableFlags@@PEAPEAU_SmsHashOverflow@@@Z`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140036df0`

## callees

- `0x1400989a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140098aeb`
- `ntoskrnl!KeSetEvent` at `0x140098aeb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140098a2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140098a2b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140098a6a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140098a6a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9ea4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9ea4`
- `ntoskrnl!ExReleasePushLockEx` at `0x140098b08`
- `ntoskrnl!ExReleasePushLockEx` at `0x140098b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f9ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f9ec0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140098a9f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140098a9f`

## pseudocode

```c
__int64 __fastcall CmsHashTable::DeleteInternal(__int64 a1, __int64 *a2, _QWORD *a3, __int64 a4, char a5, _QWORD *a6)
{
  __int64 v6; // r14
  _QWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v13; // rcx
  void *v14; // rdx
  __int64 result; // rax
  __int64 v16; // rax
  __int64 v18; // rax
  __int64 *v19; // r15
  __int64 **v20; // rcx
  struct _KEVENT *v21; // rcx
  __int64 v22; // rcx

  v6 = a3[1];
  a3[1] = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( *a2 != -1 )
    {
LABEL_3:
      *a2 = 0;
      goto LABEL_4;
    }
  }
  else if ( *(_QWORD *)a4 != -1 )
  {
    goto LABEL_3;
  }
  *a3 = 0;
  v16 = *(_QWORD *)(a4 + 8);
  if ( (*(_DWORD *)(v16 + 4))-- == 1 )
  {
    v10 = *(_QWORD **)(a4 + 8);
    *(_QWORD *)(a4 + 8) = 0;
    goto LABEL_3;
  }
LABEL_4:
  v11 = _InterlockedExchange64((volatile __int64 *)a4, *a2);
  *a2 = 0;
  if ( v11 == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_1402653F0, 0);
    v18 = qword_1402653F8;
    if ( (__int64 *)qword_1402653F8 != &qword_1402653F8 )
    {
      do
      {
        v19 = *(__int64 **)v18;
        if ( *(_QWORD *)(v18 + 24) == a4 )
        {
          if ( v19[1] != v18 || (v20 = *(__int64 ***)(v18 + 8), *v20 != (__int64 *)v18) )
            __fastfail(3u);
          *v20 = v19;
          v19[1] = (__int64)v20;
          v21 = *(struct _KEVENT **)(v18 + 16);
          *(_QWORD *)v18 = 0;
          KeSetEvent(v21, 0, 0);
        }
        v18 = (__int64)v19;
      }
      while ( v19 != &qword_1402653F8 );
    }
    ExReleasePushLockEx(&qword_1402653F0, 0);
  }
  if ( (a5 & 1) == 0 && v6 )
  {
    v12 = *(_QWORD *)(v6 - 16);
    if ( v12 )
    {
      if ( *(_BYTE *)(v12 + 8) )
      {
        v13 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 64);
        v14 = (void *)(v6 - 16);
        if ( *(_BYTE *)(v12 + 9) )
          ExFreeToNPagedLookasideList(v13, v14);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v13, v14);
        goto LABEL_11;
      }
      v22 = *(_QWORD *)(v12 + 88);
      if ( (int)v22 < *(_DWORD *)(v12 + 80) || SHIDWORD(v22) >= (int)v22 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v12 + 64), (PSLIST_ENTRY)(v6 - 16));
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 88));
        goto LABEL_11;
      }
    }
    ExFreePoolWithTag((PVOID)(v6 - 16), 0);
  }
LABEL_11:
  if ( v10 )
  {
    if ( a6 )
    {
      *v10 = *a6;
      *a6 = v10;
    }
    else
    {
      ExFreePoolWithTag(v10, 0);
    }
  }
  result = 16LL * *((unsigned int *)a2 + 2);
  _InterlockedDecrement((volatile signed __int32 *)(result + a1 + 12));
  return result;
}

```

## disassembly

```asm
0x1400989a0  mov     [rsp+arg_18], rbx
0x1400989a5  push    rbp
0x1400989a6  push    rsi
0x1400989a7  push    rdi
0x1400989a8  push    r12
0x1400989aa  push    r14
0x1400989ac  sub     rsp, 20h
0x1400989b0  mov     r14, [r8+8]
0x1400989b4  xor     r12d, r12d
0x1400989b7  mov     [r8+8], r12
0x1400989bb  mov     rdi, r9
0x1400989be  mov     rbx, rdx
0x1400989c1  mov     rbp, rcx
0x1400989c4  mov     esi, r12d
0x1400989c7  test    rdx, rdx
0x1400989ca  jz      loc_140098B20
0x1400989d0  cmp     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1400989d4  jz      loc_140098A78
0x1400989da  mov     [rdx], r12
0x1400989dd  mov     rax, [rdx]
0x1400989e0  xchg    rax, [r9]
0x1400989e3  mov     [rsp+48h+arg_0], r13
0x1400989e8  mov     [rsp+48h+arg_10], r15
0x1400989ed  mov     [rdx], r12
0x1400989f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400989f4  jz      loc_140098A96
0x1400989fa  test    [rsp+48h+arg_20], 1
0x1400989ff  jnz     short loc_140098A37
0x140098a01  test    r14, r14
0x140098a04  jz      short loc_140098A37
0x140098a06  mov     rdi, [r14-10h]
0x140098a0a  test    rdi, rdi
0x140098a0d  jz      loc_140098B4B
0x140098a13  cmp     [rdi+8], r12b
0x140098a17  jz      loc_140098B2F
0x140098a1d  lea     rcx, [rdi+40h]; Lookaside
0x140098a21  lea     rdx, [r14-10h]; Entry
0x140098a25  cmp     [rdi+9], r12b
0x140098a29  jz      short loc_140098A6A
0x140098a2b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140098a32  nop     dword ptr [rax+rax+00h]
0x140098a37  test    rsi, rsi
0x140098a3a  jnz     loc_140098B62
0x140098a40  mov     eax, [rbx+8]
0x140098a43  nop
0x140098a44  mov     r15, [rsp+48h+arg_10]
0x140098a49  mov     r13, [rsp+48h+arg_0]
0x140098a4e  mov     rbx, [rsp+48h+arg_18]
0x140098a53  shl     rax, 4
0x140098a57  lock dec dword ptr [rax+rbp+0Ch]
0x140098a5c  nop
0x140098a5d  add     rsp, 20h
0x140098a61  pop     r14
0x140098a63  pop     r12
0x140098a65  pop     rdi
0x140098a66  pop     rsi
0x140098a67  pop     rbp
0x140098a68  retn
0x140098a6a  call    cs:__imp_ExFreeToPagedLookasideList
0x140098a71  nop     dword ptr [rax+rax+00h]
0x140098a76  jmp     short loc_140098A37
0x140098a78  mov     [r8], r12
0x140098a7b  mov     rax, [r9+8]
0x140098a7f  add     dword ptr [rax+4], 0FFFFFFFFh
0x140098a83  jnz     loc_1400989DD
0x140098a89  mov     rsi, [r9+8]
0x140098a8d  mov     [r9+8], r12
0x140098a91  jmp     loc_1400989DA
0x140098a96  xor     edx, edx
0x140098a98  lea     rcx, qword_1402653F0
0x140098a9f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140098aa6  nop     dword ptr [rax+rax+00h]
0x140098aab  mov     rax, cs:qword_1402653F8
0x140098ab2  lea     r13, qword_1402653F8
0x140098ab9  cmp     rax, r13
0x140098abc  jz      short loc_140098AFF
0x140098abe  xchg    ax, ax
0x140098ac0  mov     r15, [rax]
0x140098ac3  cmp     [rax+18h], rdi
0x140098ac7  jnz     short loc_140098AF7
0x140098ac9  cmp     [r15+8], rax
0x140098acd  jnz     short loc_140098B19
0x140098acf  mov     rcx, [rax+8]
0x140098ad3  cmp     [rcx], rax
0x140098ad6  jnz     short loc_140098B19
0x140098ad8  mov     [rcx], r15
0x140098adb  xor     r8d, r8d; Wait
0x140098ade  mov     [r15+8], rcx
0x140098ae2  xor     edx, edx; Increment
0x140098ae4  mov     rcx, [rax+10h]; Event
0x140098ae8  mov     [rax], r12
0x140098aeb  call    cs:__imp_KeSetEvent
0x140098af2  nop     dword ptr [rax+rax+00h]
0x140098af7  mov     rax, r15
0x140098afa  cmp     r15, r13
0x140098afd  jnz     short loc_140098AC0
0x140098aff  xor     edx, edx
0x140098b01  lea     rcx, qword_1402653F0
0x140098b08  call    cs:__imp_ExReleasePushLockEx
0x140098b0f  nop     dword ptr [rax+rax+00h]
0x140098b14  jmp     loc_1400989FA
0x140098b19  mov     ecx, 3
0x140098b1e  int     29h; Win8: RtlFailFast(ecx)
0x140098b20  cmp     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x140098b24  jnz     loc_1400989DA
0x140098b2a  jmp     loc_140098A78
0x140098b2f  mov     rcx, [rdi+58h]
0x140098b33  cmp     ecx, [rdi+50h]
0x140098b36  jl      loc_1401F9E9C
0x140098b3c  mov     rax, rcx
0x140098b3f  shr     rax, 20h
0x140098b43  cmp     eax, ecx
0x140098b45  jge     loc_1401F9E9C
0x140098b4b  xor     edx, edx; Tag
0x140098b4d  lea     rcx, [r14-10h]; P
0x140098b51  call    cs:__imp_ExFreePoolWithTag
0x140098b58  nop     dword ptr [rax+rax+00h]
0x140098b5d  jmp     loc_140098A37
0x140098b62  mov     rcx, [rsp+48h+arg_28]
0x140098b67  test    rcx, rcx
0x140098b6a  jz      loc_1401F9EBB
0x140098b70  mov     rax, [rcx]
0x140098b73  mov     [rsi], rax
0x140098b76  mov     [rcx], rsi
0x140098b79  jmp     loc_140098A40
0x1401f9e9c  lea     rcx, [rdi+40h]; ListHead
0x1401f9ea0  lea     rdx, [r14-10h]; ListEntry
0x1401f9ea4  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f9eab  nop     dword ptr [rax+rax+00h]
0x1401f9eb0  nop
0x1401f9eb1  lock inc dword ptr [rdi+58h]
0x1401f9eb5  nop
0x1401f9eb6  jmp     loc_140098A37
0x1401f9ebb  xor     edx, edx; Tag
0x1401f9ebd  mov     rcx, rsi; P
0x1401f9ec0  call    cs:__imp_ExFreePoolWithTag
0x1401f9ec7  nop     dword ptr [rax+rax+00h]
0x1401f9ecc  nop
0x1401f9ecd  jmp     loc_140098A40
```
