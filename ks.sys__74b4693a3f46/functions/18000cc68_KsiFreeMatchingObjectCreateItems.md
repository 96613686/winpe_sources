# KsiFreeMatchingObjectCreateItems

- ea: `0x18000cc68`
- end: `0x18000ce16`
- name: `KsiFreeMatchingObjectCreateItems`
- size: `430`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180037c80`
- `0x180037cb0`
- `0x18005b644`

## callees

- `0x18000cc68`
- `0x180048ae8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18000cca1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18000cca1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000cc8b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000cc8b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18000cd73`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18000cd73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000cd7f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000cd7f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000cdf6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000cdf6`

## pseudocode

```c
__int64 __fastcall KsiFreeMatchingObjectCreateItems(__int64 **a1, __int64 a2)
{
  struct _FAST_MUTEX *v4; // rdi
  __int64 *v5; // rbx
  __int64 *v6; // rbp
  const UNICODE_STRING **v7; // rdi
  wchar_t *v8; // rcx
  int v9; // edx
  __int64 *v10; // rax
  __int64 **v11; // rcx
  __int64 v12; // rax
  _QWORD v14[7]; // [rsp+20h] [rbp-38h] BYREF

  v14[1] = v14;
  v14[0] = v14;
  KeEnterCriticalRegion();
  v4 = (struct _FAST_MUTEX *)(a1 + 26);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 26));
  v5 = *a1;
  if ( *a1 != (__int64 *)a1 )
  {
    do
    {
      v6 = (__int64 *)*v5;
      if ( (*((_DWORD *)v5 + 9) & 2) == 0 )
      {
        v7 = (const UNICODE_STRING **)(v5 + 2);
        if ( !*(_QWORD *)a2 || *(_QWORD *)a2 == *(_QWORD *)&(*v7)->Length )
        {
          v8 = *(wchar_t **)(a2 + 8);
          if ( (!v8 || v8 == (*v7)->Buffer)
            && (!*(_QWORD *)(a2 + 24) || !RtlCompareUnicodeString(*v7 + 1, (PCUNICODE_STRING)(a2 + 16), 0))
            && (!*(_QWORD *)(a2 + 32) || *(_QWORD *)(a2 + 8) == *(_QWORD *)&(*v7)[2].Length) )
          {
            v9 = *(_DWORD *)(a2 + 40);
            if ( !v9 || (v9 & *(_DWORD *)(v5[2] + 40)) != 0 )
            {
              *((_DWORD *)v5 + 9) |= 2u;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 8, 0xFFFFFFFF) == 1 )
              {
                v10 = (__int64 *)*v5;
                if ( *(__int64 **)(*v5 + 8) != v5
                  || (v11 = (__int64 **)v5[1], *v11 != v5)
                  || (*v11 = v10, v10[1] = (__int64)v11, v12 = v14[0], *(_QWORD **)(v14[0] + 8LL) != v14) )
                {
                  __fastfail(3u);
                }
                *v5 = v14[0];
                v5[1] = (__int64)v14;
                *(_QWORD *)(v12 + 8) = v5;
                v14[0] = v5;
              }
            }
          }
        }
      }
      v5 = v6;
    }
    while ( v6 != (__int64 *)a1 );
    v4 = (struct _FAST_MUTEX *)(a1 + 26);
  }
  ExReleaseFastMutexUnsafe(v4);
  KeLeaveCriticalRegion();
  if ( (_QWORD *)v14[0] == v14 )
    return 3221225524LL;
  FreeCreateEntries(v14);
  return 0;
}

```

## disassembly

```asm
0x18000cc68  mov     r11, rsp
0x18000cc6b  push    rbx
0x18000cc6c  push    rbp
0x18000cc6d  push    rsi
0x18000cc6e  push    rdi
0x18000cc6f  push    r14
0x18000cc71  sub     rsp, 30h
0x18000cc75  lea     rax, [r11-38h]
0x18000cc79  mov     rsi, rdx
0x18000cc7c  mov     [r11-30h], rax
0x18000cc80  mov     r14, rcx
0x18000cc83  lea     rax, [r11-38h]
0x18000cc87  mov     [r11-38h], rax
0x18000cc8b  call    cs:__imp_KeEnterCriticalRegion
0x18000cc92  nop     dword ptr [rax+rax+00h]
0x18000cc97  lea     rdi, [r14+0D0h]
0x18000cc9e  mov     rcx, rdi; FastMutex
0x18000cca1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x18000cca8  nop     dword ptr [rax+rax+00h]
0x18000ccad  mov     rbx, [r14]
0x18000ccb0  cmp     rbx, r14
0x18000ccb3  jz      loc_18000CD70
0x18000ccb9  mov     eax, [rbx+24h]
0x18000ccbc  mov     rbp, [rbx]
0x18000ccbf  test    al, 2
0x18000ccc1  jnz     loc_18000CD5D
0x18000ccc7  mov     rcx, [rsi]
0x18000ccca  lea     rdi, [rbx+10h]
0x18000ccce  test    rcx, rcx
0x18000ccd1  jnz     loc_18000CDC9
0x18000ccd7  mov     rcx, [rsi+8]
0x18000ccdb  test    rcx, rcx
0x18000ccde  jnz     loc_18000CDD6
0x18000cce4  cmp     qword ptr [rsi+18h], 0
0x18000cce9  jnz     loc_18000CDE8
0x18000ccef  cmp     qword ptr [rsi+20h], 0
0x18000ccf4  jnz     loc_18000CDB6
0x18000ccfa  mov     edx, [rsi+28h]
0x18000ccfd  test    edx, edx
0x18000ccff  jz      short loc_18000CD0A
0x18000cd01  mov     rax, [rbx+10h]
0x18000cd05  test    [rax+28h], edx
0x18000cd08  jz      short loc_18000CD5D
0x18000cd0a  or      dword ptr [rbx+24h], 2
0x18000cd0e  or      eax, 0FFFFFFFFh
0x18000cd11  lock xadd [rbx+20h], eax
0x18000cd16  cmp     eax, 1
0x18000cd19  jnz     short loc_18000CD5D
0x18000cd1b  mov     rax, [rbx]
0x18000cd1e  cmp     [rax+8], rbx
0x18000cd22  jnz     loc_18000CDAF
0x18000cd28  mov     rcx, [rbx+8]
0x18000cd2c  cmp     [rcx], rbx
0x18000cd2f  jnz     short loc_18000CDAF
0x18000cd31  mov     [rcx], rax
0x18000cd34  mov     [rax+8], rcx
0x18000cd38  lea     rcx, [rsp+58h+var_38]
0x18000cd3d  mov     rax, [rsp+58h+var_38]
0x18000cd42  cmp     [rax+8], rcx
0x18000cd46  jnz     short loc_18000CDAF
0x18000cd48  mov     [rbx], rax
0x18000cd4b  lea     rcx, [rsp+58h+var_38]
0x18000cd50  mov     [rbx+8], rcx
0x18000cd54  mov     [rax+8], rbx
0x18000cd58  mov     [rsp+58h+var_38], rbx
0x18000cd5d  mov     rbx, rbp
0x18000cd60  cmp     rbp, r14
0x18000cd63  jnz     loc_18000CCB9
0x18000cd69  lea     rdi, [r14+0D0h]
0x18000cd70  mov     rcx, rdi; FastMutex
0x18000cd73  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18000cd7a  nop     dword ptr [rax+rax+00h]
0x18000cd7f  call    cs:__imp_KeLeaveCriticalRegion
0x18000cd86  nop     dword ptr [rax+rax+00h]
0x18000cd8b  lea     rax, [rsp+58h+var_38]
0x18000cd90  cmp     [rsp+58h+var_38], rax
0x18000cd95  jz      short loc_18000CE0F
0x18000cd97  lea     rcx, [rsp+58h+var_38]
0x18000cd9c  call    FreeCreateEntries
0x18000cda1  xor     eax, eax
0x18000cda3  add     rsp, 30h
0x18000cda7  pop     r14
0x18000cda9  pop     rdi
0x18000cdaa  pop     rsi
0x18000cdab  pop     rbp
0x18000cdac  pop     rbx
0x18000cdad  retn
0x18000cdaf  mov     ecx, 3
0x18000cdb4  int     29h; Win8: RtlFailFast(ecx)
0x18000cdb6  mov     rax, [rdi]
0x18000cdb9  mov     rcx, [rax+20h]
0x18000cdbd  cmp     [rsi+8], rcx
0x18000cdc1  jz      loc_18000CCFA
0x18000cdc7  jmp     short loc_18000CD5D
0x18000cdc9  mov     rax, [rdi]
0x18000cdcc  cmp     rcx, [rax]
0x18000cdcf  jnz     short loc_18000CD5D
0x18000cdd1  jmp     loc_18000CCD7
0x18000cdd6  mov     rax, [rdi]
0x18000cdd9  cmp     rcx, [rax+8]
0x18000cddd  jnz     loc_18000CD5D
0x18000cde3  jmp     loc_18000CCE4
0x18000cde8  mov     rcx, [rdi]
0x18000cdeb  lea     rdx, [rsi+10h]; String2
0x18000cdef  add     rcx, 10h; String1
0x18000cdf3  xor     r8d, r8d; CaseInSensitive
0x18000cdf6  call    cs:__imp_RtlCompareUnicodeString
0x18000cdfd  nop     dword ptr [rax+rax+00h]
0x18000ce02  test    eax, eax
0x18000ce04  jnz     loc_18000CD5D
0x18000ce0a  jmp     loc_18000CCEF
0x18000ce0f  mov     eax, 0C0000034h
0x18000ce14  jmp     short loc_18000CDA3
```
