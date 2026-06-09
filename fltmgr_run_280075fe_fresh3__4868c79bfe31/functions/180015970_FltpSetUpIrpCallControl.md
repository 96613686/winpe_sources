# FltpSetUpIrpCallControl

- ea: `0x180015970`
- end: `0x180015c7c`
- name: `FltpSetUpIrpCallControl`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18006e150`

## callees

- `0x180015970`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180015a4c`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180015a4c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180015aa6`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180015aa6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180015a88`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180015a88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180015afc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180015afc`
- `ntoskrnl!ExReleaseFastResource` at `0x180015af0`
- `ntoskrnl!ExReleaseFastResource` at `0x180015af0`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180015a74`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x180015a74`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180015a63`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180015a63`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180015bae`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180015bf8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180015bae`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x180015bf8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180015b1e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180015b1e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180015b12`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x180015b12`

## pseudocode

```c
void __fastcall FltpSetUpIrpCallControl(__int64 a1, __int64 a2, __int64 a3, char a4, _BYTE *a5)
{
  int v7; // ecx
  _BYTE *v8; // r15
  __int64 v9; // rbp
  unsigned int v10; // ecx
  _BYTE *v11; // rbx
  __int64 v12; // r12
  __int64 v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // r13
  __int64 v18; // r8
  __int64 *v19; // rbx
  __int64 *i; // rdi
  int v21; // ecx
  __int64 v22; // rcx
  _BYTE v23[80]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE *v24; // [rsp+A0h] [rbp+8h]
  __int64 v25; // [rsp+C0h] [rbp+28h]

  v7 = *(unsigned __int16 *)(a1 + 4);
  if ( v7 )
  {
    v21 = v7 - 1;
    if ( !v21 )
    {
LABEL_22:
      *(_QWORD *)(a3 + 24) = 0;
      goto LABEL_23;
    }
    if ( v21 == 1 )
    {
      v22 = *(_QWORD *)(a1 + 64);
      if ( (!v22 || v22 == *(_QWORD *)(*(_QWORD *)a3 + 88LL))
        && *(_DWORD *)(a2 + 24) > *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL) )
      {
        goto LABEL_22;
      }
      if ( (*(_BYTE *)(a1 + 6) & 2) != 0 )
        *(_DWORD *)(a3 + 40) |= 0x10u;
    }
LABEL_23:
    v8 = a5;
    if ( !a5 )
      return;
    goto LABEL_24;
  }
  v8 = a5;
  v9 = *(_QWORD *)(a1 + 72);
  if ( v9 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(v9 + 64) + 88LL) == *(_QWORD *)(*(_QWORD *)a3 + 88LL) )
    {
      v10 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL);
      if ( *(_DWORD *)(a2 + 24) > v10 )
      {
        *(_QWORD *)(a3 + 24) = 0;
      }
      else
      {
        v11 = (_BYTE *)(a1 + 6);
        if ( *(_DWORD *)(a2 + 24) == v10 )
        {
          if ( a5 )
          {
            *(_QWORD *)(a3 + 24) = *(_QWORD *)(a1 + 16);
          }
          else
          {
            if ( (*v11 & 0x20) != 0 )
            {
              v12 = (unsigned __int8)(a4 + 22);
              v13 = *(_QWORD *)(v9 + 8 * v12 + 304);
              if ( !v13
                || (*(_DWORD *)(v9 + 80) & 6) != 0
                || !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v9 + 56), 1u) )
              {
                v13 = 0;
              }
              *(_QWORD *)(a3 + 24) = v13;
            }
            else
            {
              LOBYTE(v12) = a4 + 22;
            }
            if ( (*v11 & 0x20) == 0 || !*(_QWORD *)(a3 + 24) )
            {
              v24 = v11;
              v14 = 0;
              memset(v23, 0, 0x48u);
              ExInitializeFastOwnerEntry(v23);
              v15 = *(_QWORD *)(v9 + 64);
              v16 = qword_18003E9A0;
              KeEnterGuardedRegion();
              v25 = ExAcquireCacheAwarePushLockSharedEx(v16, 0);
              KeEnterCriticalRegion();
              v17 = v15 + 192;
              LOBYTE(v18) = 1;
              ExAcquireFastResourceShared(v15 + 192, v23, v18);
              v19 = *(__int64 **)(v9 + 16);
              for ( i = (__int64 *)(v15 + 296); v19 != i; v14 = 0 )
              {
                if ( (v19[8] & 6) == 0 )
                {
                  v14 = v19[(unsigned __int8)v12 + 36];
                  if ( v14 )
                  {
                    if ( ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)v19[5], 1u) )
                      break;
                  }
                }
                v19 = (__int64 *)*v19;
              }
              ExReleaseFastResource(v17, v23);
              KeLeaveCriticalRegion();
              ExReleaseCacheAwarePushLockSharedEx(v25, 0);
              KeLeaveGuardedRegion();
              v11 = v24;
              *(_QWORD *)(a3 + 24) = v14;
            }
          }
        }
        if ( (*v11 & 2) != 0 )
          *(_DWORD *)(a3 + 40) |= 0x10u;
      }
    }
    else if ( (*(_BYTE *)(a1 + 6) & 2) != 0 )
    {
      *(_DWORD *)(a3 + 40) |= 0x10u;
    }
  }
  if ( v8 )
  {
    *(_DWORD *)(a3 + 40) |= 2u;
LABEL_24:
    *v8 = 1;
  }
}

```

## disassembly

```asm
0x180015970  mov     r11, rsp
0x180015973  push    r14
0x180015975  push    r15
0x180015977  sub     rsp, 88h
0x18001597e  mov     r14, r8
0x180015981  mov     r8, rcx
0x180015984  movzx   ecx, word ptr [rcx+4]
0x180015988  test    ecx, ecx
0x18001598a  jnz     loc_180015B76
0x180015990  mov     r15, [rsp+98h+arg_20]
0x180015998  mov     [r11+18h], rbp
0x18001599c  mov     rbp, [r8+48h]
0x1800159a0  test    rbp, rbp
0x1800159a3  jz      loc_180015B62
0x1800159a9  mov     rax, [r14]
0x1800159ac  mov     rcx, [rbp+40h]
0x1800159b0  mov     rax, [rax+58h]
0x1800159b4  cmp     [rcx+58h], rax
0x1800159b8  jnz     loc_180015C27
0x1800159be  mov     rax, [r8+8]
0x1800159c2  mov     ecx, [rax+18h]
0x1800159c5  cmp     [rdx+18h], ecx
0x1800159c8  ja      loc_180015C1A
0x1800159ce  mov     [r11+10h], rbx
0x1800159d2  lea     rbx, [r8+6]
0x1800159d6  jnz     loc_180015B50
0x1800159dc  test    r15, r15
0x1800159df  jnz     loc_180015BC7
0x1800159e5  test    byte ptr [rbx], 20h
0x1800159e8  mov     [r11-18h], rdi
0x1800159ec  mov     [r11-20h], r12
0x1800159f0  jz      loc_180015C11
0x1800159f6  add     r9b, 16h
0x1800159fa  movzx   r12d, r9b
0x1800159fe  mov     rdi, [rbp+r12*8+130h]
0x180015a06  test    rdi, rdi
0x180015a09  jnz     loc_180015BE4
0x180015a0f  xor     edi, edi
0x180015a11  mov     [r14+18h], rdi
0x180015a15  test    byte ptr [rbx], 20h
0x180015a18  jnz     loc_180015BD4
0x180015a1e  mov     [rsp+98h+arg_18], rsi
0x180015a26  lea     rcx, [rsp+98h+var_78]; void *
0x180015a2b  xor     edx, edx; Val
0x180015a2d  mov     [rsp+98h+var_28], r13
0x180015a32  mov     r8d, 48h ; 'H'; Size
0x180015a38  mov     [rsp+98h+arg_0], rbx
0x180015a40  xor     esi, esi
0x180015a42  call    memset
0x180015a47  lea     rcx, [rsp+98h+var_78]
0x180015a4c  call    cs:__imp_ExInitializeFastOwnerEntry
0x180015a53  nop     dword ptr [rax+rax+00h]
0x180015a58  mov     rdi, [rbp+40h]
0x180015a5c  mov     rbx, cs:qword_18003E9A0
0x180015a63  call    cs:__imp_KeEnterGuardedRegion
0x180015a6a  nop     dword ptr [rax+rax+00h]
0x180015a6f  xor     edx, edx
0x180015a71  mov     rcx, rbx
0x180015a74  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x180015a7b  nop     dword ptr [rax+rax+00h]
0x180015a80  mov     [rsp+98h+arg_20], rax
0x180015a88  call    cs:__imp_KeEnterCriticalRegion
0x180015a8f  nop     dword ptr [rax+rax+00h]
0x180015a94  lea     r13, [rdi+0C0h]
0x180015a9b  mov     r8b, 1
0x180015a9e  mov     rcx, r13
0x180015aa1  lea     rdx, [rsp+98h+var_78]
0x180015aa6  call    cs:__imp_ExAcquireFastResourceShared
0x180015aad  nop     dword ptr [rax+rax+00h]
0x180015ab2  mov     rbx, [rbp+10h]
0x180015ab6  add     rdi, 128h
0x180015abd  cmp     rbx, rdi
0x180015ac0  jz      short loc_180015AE8
0x180015ac2  mov     eax, [rbx+40h]
0x180015ac5  test    al, 6
0x180015ac7  jnz     short loc_180015ADE
0x180015ac9  movzx   eax, r12b
0x180015acd  mov     rsi, [rbx+rax*8+120h]
0x180015ad5  test    rsi, rsi
0x180015ad8  jnz     loc_180015BA5
0x180015ade  mov     rbx, [rbx]
0x180015ae1  xor     esi, esi
0x180015ae3  cmp     rbx, rdi
0x180015ae6  jnz     short loc_180015AC2
0x180015ae8  lea     rdx, [rsp+98h+var_78]
0x180015aed  mov     rcx, r13
0x180015af0  call    cs:__imp_ExReleaseFastResource
0x180015af7  nop     dword ptr [rax+rax+00h]
0x180015afc  call    cs:__imp_KeLeaveCriticalRegion
0x180015b03  nop     dword ptr [rax+rax+00h]
0x180015b08  mov     rcx, [rsp+98h+arg_20]
0x180015b10  xor     edx, edx
0x180015b12  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x180015b19  nop     dword ptr [rax+rax+00h]
0x180015b1e  call    cs:__imp_KeLeaveGuardedRegion
0x180015b25  nop     dword ptr [rax+rax+00h]
0x180015b2a  mov     rbx, [rsp+98h+arg_0]
0x180015b32  mov     r13, [rsp+98h+var_28]
0x180015b37  mov     [r14+18h], rsi
0x180015b3b  mov     rsi, [rsp+98h+arg_18]
0x180015b43  mov     rdi, [rsp+98h+var_18]
0x180015b4b  mov     r12, [rsp+98h+var_20]
0x180015b50  test    byte ptr [rbx], 2
0x180015b53  jz      short loc_180015B5A
0x180015b55  or      dword ptr [r14+28h], 10h
0x180015b5a  mov     rbx, [rsp+98h+arg_8]
0x180015b62  mov     rbp, [rsp+98h+arg_10]
0x180015b6a  test    r15, r15
0x180015b6d  jz      short loc_180015B98
0x180015b6f  or      dword ptr [r14+28h], 2
0x180015b74  jmp     short loc_180015B94
0x180015b76  sub     ecx, 1
0x180015b79  jnz     loc_180015C3C
0x180015b7f  mov     qword ptr [r14+18h], 0
0x180015b87  mov     r15, [rsp+98h+arg_20]
0x180015b8f  test    r15, r15
0x180015b92  jz      short loc_180015B98
0x180015b94  mov     byte ptr [r15], 1
0x180015b98  add     rsp, 88h
0x180015b9f  pop     r15
0x180015ba1  pop     r14
0x180015ba3  retn
0x180015ba5  mov     rcx, [rbx+28h]; RunRefCacheAware
0x180015ba9  mov     edx, 1; Count
0x180015bae  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180015bb5  nop     dword ptr [rax+rax+00h]
0x180015bba  test    al, al
0x180015bbc  jz      loc_180015ADE
0x180015bc2  jmp     loc_180015AE8
0x180015bc7  mov     rax, [r8+10h]
0x180015bcb  mov     [r14+18h], rax
0x180015bcf  jmp     loc_180015B50
0x180015bd4  cmp     qword ptr [r14+18h], 0
0x180015bd9  jnz     loc_180015B43
0x180015bdf  jmp     loc_180015A1E
0x180015be4  mov     eax, [rbp+50h]
0x180015be7  test    al, 6
0x180015be9  jnz     loc_180015A0F
0x180015bef  mov     rcx, [rbp+38h]; RunRefCacheAware
0x180015bf3  mov     edx, 1; Count
0x180015bf8  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x180015bff  nop     dword ptr [rax+rax+00h]
0x180015c04  test    al, al
0x180015c06  jnz     loc_180015A11
0x180015c0c  jmp     loc_180015A0F
0x180015c11  lea     r12d, [r9+16h]
0x180015c15  jmp     loc_180015A15
0x180015c1a  mov     qword ptr [r14+18h], 0
0x180015c22  jmp     loc_180015B62
0x180015c27  test    byte ptr [r8+6], 2
0x180015c2c  jz      loc_180015B62
0x180015c32  or      dword ptr [r14+28h], 10h
0x180015c37  jmp     loc_180015B62
0x180015c3c  cmp     ecx, 1
0x180015c3f  jnz     loc_180015B87
0x180015c45  mov     rcx, [r8+40h]
0x180015c49  test    rcx, rcx
0x180015c4c  jz      short loc_180015C57
0x180015c4e  mov     rax, [r14]
0x180015c51  cmp     rcx, [rax+58h]
0x180015c55  jnz     short loc_180015C67
0x180015c57  mov     rax, [r8+8]
0x180015c5b  mov     ecx, [rax+18h]
0x180015c5e  cmp     [rdx+18h], ecx
0x180015c61  ja      loc_180015B7F
0x180015c67  test    byte ptr [r8+6], 2
0x180015c6c  jz      loc_180015B87
0x180015c72  or      dword ptr [r14+28h], 10h
0x180015c77  jmp     loc_180015B87
```
