# PsmpFindApplicationUsageInfoEntry

- ea: `0x18000cf28`
- end: `0x18000cffb`
- name: `PsmpFindApplicationUsageInfoEntry`
- size: `211`
- prototype: `signed __int32 *__fastcall(__int64 *, WCHAR *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009b40`

## callees

- `0x18000cf28`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000cfde`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000cfde`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000cf58`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000cf58`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000cfba`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000cfba`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000cf88`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000cf88`

## pseudocode

```c
signed __int32 *__fastcall PsmpFindApplicationUsageInfoEntry(__int64 *a1, WCHAR *a2, unsigned __int64 a3)
{
  __int64 *v5; // rsi
  int v6; // esi
  WCHAR *v7; // rdi
  WCHAR v8; // bx
  int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *i; // r14
  signed __int32 *v14; // rbx
  signed __int32 v15; // eax
  int v17; // [rsp+20h] [rbp-48h]

  v5 = a1;
  if ( !a1 )
  {
    v6 = 0;
    v7 = a2;
    do
    {
      v8 = *v7++;
      v9 = 37 * v6 + RtlUpcaseUnicodeChar(v8);
      v6 = v9;
    }
    while ( v8 );
    a3 = (char *)v7 - (char *)a2;
    v5 = &qword_18003FEE8[3 * (v9 & 0x7F)];
  }
  RtlAcquireSRWLockShared(v5 + 2);
  for ( i = (__int64 *)*v5; i != v5; i = (__int64 *)*i )
  {
    v14 = (signed __int32 *)(i - 3);
    if ( a3 == *(i - 1) )
    {
      LOBYTE(v17) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v14 + 1), a3 >> 1, a2, a3 >> 1, v17) )
      {
        _m_prefetchw(v14);
        v15 = *v14;
        while ( v15 > 0 )
        {
          v10 = (unsigned int)v15;
          v15 = _InterlockedCompareExchange(v14, v15 + 1, v15);
          if ( v15 == (_DWORD)v10 )
            goto LABEL_13;
        }
      }
    }
  }
  v14 = 0;
LABEL_13:
  RtlReleaseSRWLockShared(v5 + 2, v10, v11, v12);
  return v14;
}

```

## disassembly

```asm
0x18000cf28  push    rbx
0x18000cf2a  push    rbp
0x18000cf2b  push    rsi
0x18000cf2c  push    rdi
0x18000cf2d  push    r12
0x18000cf2f  push    r14
0x18000cf31  push    r15
0x18000cf33  sub     rsp, 30h
0x18000cf37  xor     r12d, r12d
0x18000cf3a  mov     rdi, r8
0x18000cf3d  mov     rbp, rdx
0x18000cf40  mov     rsi, rcx
0x18000cf43  test    rcx, rcx
0x18000cf46  jnz     short loc_18000CF84
0x18000cf48  mov     esi, r12d
0x18000cf4b  mov     rdi, rdx
0x18000cf4e  movzx   ebx, word ptr [rdi]
0x18000cf51  add     rdi, 2
0x18000cf55  movzx   ecx, bx; Source
0x18000cf58  call    cs:__imp_RtlUpcaseUnicodeChar
0x18000cf5e  movzx   ecx, ax
0x18000cf61  imul    eax, esi, 25h ; '%'
0x18000cf64  add     ecx, eax
0x18000cf66  mov     esi, ecx
0x18000cf68  test    bx, bx
0x18000cf6b  jnz     short loc_18000CF4E
0x18000cf6d  mov     eax, ecx
0x18000cf6f  sub     rdi, rbp
0x18000cf72  and     eax, 7Fh
0x18000cf75  lea     rcx, qword_18003FEE8
0x18000cf7c  lea     rax, [rax+rax*2]
0x18000cf80  lea     rsi, [rcx+rax*8]
0x18000cf84  lea     rcx, [rsi+10h]
0x18000cf88  call    cs:__imp_RtlAcquireSRWLockShared
0x18000cf8e  mov     r14, [rsi]
0x18000cf91  cmp     r14, rsi
0x18000cf94  jz      short loc_18000CFF6
0x18000cf96  lea     rbx, [r14-18h]
0x18000cf9a  cmp     rdi, [rbx+10h]
0x18000cf9e  jz      short loc_18000CFA5
0x18000cfa0  mov     r14, [r14]
0x18000cfa3  jmp     short loc_18000CF91
0x18000cfa5  mov     rcx, [rbx+8]
0x18000cfa9  mov     rdx, rdi
0x18000cfac  shr     rdx, 1
0x18000cfaf  mov     r8, rbp
0x18000cfb2  mov     r9, rdx
0x18000cfb5  mov     byte ptr [rsp+68h+var_48], 1
0x18000cfba  call    cs:__imp_RtlCompareUnicodeStrings
0x18000cfc0  test    eax, eax
0x18000cfc2  jnz     short loc_18000CFA0
0x18000cfc4  prefetchw byte ptr [rbx]
0x18000cfc7  mov     eax, [rbx]
0x18000cfc9  test    eax, eax
0x18000cfcb  jle     short loc_18000CFA0
0x18000cfcd  mov     edx, eax
0x18000cfcf  lea     ecx, [rax+1]
0x18000cfd2  lock cmpxchg [rbx], ecx
0x18000cfd6  cmp     eax, edx
0x18000cfd8  jnz     short loc_18000CFC9
0x18000cfda  lea     rcx, [rsi+10h]
0x18000cfde  call    cs:__imp_RtlReleaseSRWLockShared
0x18000cfe4  mov     rax, rbx
0x18000cfe7  add     rsp, 30h
0x18000cfeb  pop     r15
0x18000cfed  pop     r14
0x18000cfef  pop     r12
0x18000cff1  pop     rdi
0x18000cff2  pop     rsi
0x18000cff3  pop     rbp
0x18000cff4  pop     rbx
0x18000cff5  retn
0x18000cff6  mov     rbx, r12
0x18000cff9  jmp     short loc_18000CFDA
```
