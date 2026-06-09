# FltpSetCallbacksForInstance

- ea: `0x18001ce00`
- end: `0x18001d185`
- name: `FltpSetCallbacksForInstance`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180069c90`

## callees

- `0x180019250`
- `0x18001ce00`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18001ce32`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18001ce32`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18001cfc2`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18001cfc2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001cfa7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001cfa7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001cfec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001cfec`
- `ntoskrnl!ExReleaseFastResource` at `0x18001cfe0`
- `ntoskrnl!ExReleaseFastResource` at `0x18001cfe0`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x18001ce65`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x18001ce65`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001ce54`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001cf8c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001ce54`
- `ntoskrnl!KeEnterGuardedRegion` at `0x18001cf8c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001cf79`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001d00b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001d10e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001cf79`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001d00b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x18001d10e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18001cf6d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18001d102`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18001cf6d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x18001d102`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x18001cf9b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x18001cf9b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x18001cfff`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x18001cfff`

## pseudocode

```c
__int64 __fastcall FltpSetCallbacksForInstance(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // r15
  __int64 v7; // rbx
  char *v8; // rsi
  __int64 v9; // rbx
  char v10; // dl
  unsigned __int8 v11; // dl
  __int64 v12; // rdx
  int v13; // ecx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // r9
  __int64 v18; // rbx
  __int64 v19; // r8
  unsigned int v21; // eax
  _QWORD *v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 *v25; // r9
  __int64 v26; // r10
  __int64 *v27; // r11
  __int64 v28; // rcx
  _BYTE v29[136]; // [rsp+40h] [rbp-88h] BYREF

  memset(v29, 0, 0x48u);
  ExInitializeFastOwnerEntry(v29);
  v6 = *(_QWORD *)(a1 + 64);
  v7 = qword_18003E9A0;
  v8 = *(char **)(*(_QWORD *)(a1 + 72) + 432LL);
  KeEnterGuardedRegion();
  v9 = ExAcquireCacheAwarePushLockSharedEx(v7, 0);
  while ( 1 )
  {
    while ( 1 )
    {
      v10 = *v8;
      if ( *v8 == (char)0x80 || !a3 )
      {
        v14 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 384LL);
        if ( v14 && a3 )
        {
          *(_QWORD *)(a2 + 16) = a1;
          *(_DWORD *)(a2 + 40) = 0;
          *(_QWORD *)(a2 + 24) = v14;
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a1 + 312) = a2;
          LODWORD(a2) = a2 + 48;
          --a3;
        }
        v15 = *(_QWORD **)(a1 + 72);
        v16 = v15[50];
        v17 = v15 + 49;
        if ( (v16 || *v17) && a3 )
          FltpInitializeCallbackNode(a2, 0, 0, *v17, v16, v15[51], a1, 0);
        ExReleaseCacheAwarePushLockSharedEx(v9, 0);
        KeLeaveGuardedRegion();
        v18 = qword_18003E9A0;
        KeEnterGuardedRegion();
        ExAcquireCacheAwarePushLockExclusive(v18);
        KeEnterCriticalRegion();
        LOBYTE(v19) = 1;
        ExAcquireFastResourceShared(v6 + 192, v29, v19);
        if ( (*(_DWORD *)a1 & 1) != 0 )
          goto LABEL_21;
        v21 = 0;
        while ( 1 )
        {
          v22 = *(_QWORD **)(a1 + 8LL * v21 + 304);
          if ( !v22 )
            goto LABEL_25;
          v23 = a1;
          do
          {
            v24 = *(_QWORD *)(v23 + 24);
            if ( v24 == v6 + 296 )
            {
              v25 = (__int64 *)(v6 + 16 * (v21 + 20LL));
              v26 = *v25;
              if ( *(__int64 **)(*v25 + 8) == v25 )
              {
                *v22 = v26;
                v22[1] = v25;
                *(_QWORD *)(v26 + 8) = v22;
                *v25 = (__int64)v22;
                goto LABEL_31;
              }
LABEL_36:
              __fastfail(3u);
            }
            v27 = *(__int64 **)(v24 + 8LL * v21 + 288);
            v23 = v24 - 16;
          }
          while ( !v27 || !*v27 );
          v28 = *v27;
          if ( *(__int64 **)(*v27 + 8) != v27 )
            goto LABEL_36;
          *v22 = v28;
          v22[1] = v27;
          *(_QWORD *)(v28 + 8) = v22;
          *v27 = (__int64)v22;
LABEL_31:
          *(_DWORD *)(v6 + 4LL * v21 + 1120) &= *(_DWORD *)(*(_QWORD *)(a1 + 8LL * v21 + 304) + 40LL);
LABEL_25:
          if ( ++v21 >= 0x32 )
          {
LABEL_21:
            ExReleaseFastResource(v6 + 192, v29);
            KeLeaveCriticalRegion();
            ExReleaseCacheAwarePushLockExclusive(qword_18003E9A0);
            KeLeaveGuardedRegion();
            return 0;
          }
        }
      }
      if ( (unsigned __int8)(v10 + 20) > 1u && (*((_QWORD *)v8 + 1) || *((_QWORD *)v8 + 2)) )
      {
        v11 = v10 + 22;
        if ( v11 < 0x32u )
          break;
      }
      v8 += 32;
    }
    v12 = a1 + 8LL * v11;
    if ( *(_QWORD *)(v12 + 304) )
      break;
    *(_QWORD *)(a2 + 16) = a1;
    v13 = 0;
    *(_DWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 24) = *((_QWORD *)v8 + 1);
    *(_QWORD *)(a2 + 32) = *((_QWORD *)v8 + 2);
    if ( (*((_DWORD *)v8 + 1) & 1) != 0 )
    {
      *(_DWORD *)(a2 + 40) = 1;
      v13 = 1;
    }
    if ( (*((_DWORD *)v8 + 1) & 2) != 0 )
    {
      v13 |= 2u;
      *(_DWORD *)(a2 + 40) = v13;
    }
    if ( (*((_DWORD *)v8 + 1) & 4) != 0 )
    {
      v13 |= 8u;
      *(_DWORD *)(a2 + 40) = v13;
    }
    if ( (*((_DWORD *)v8 + 1) & 8) != 0 )
      *(_DWORD *)(a2 + 40) = v13 | 0x10;
    *(_QWORD *)a2 = 0;
    v8 += 32;
    *(_QWORD *)(v12 + 304) = a2;
    a2 += 48;
    --a3;
  }
  ExReleaseCacheAwarePushLockSharedEx(v9, 0);
  KeLeaveGuardedRegion();
  return 3223060493LL;
}

```

## disassembly

```asm
0x18001ce00  push    rbx
0x18001ce02  push    rbp
0x18001ce03  push    rsi
0x18001ce04  push    rdi
0x18001ce05  push    r12
0x18001ce07  push    r14
0x18001ce09  push    r15
0x18001ce0b  sub     rsp, 90h
0x18001ce12  mov     ebp, r8d
0x18001ce15  mov     r14, rdx
0x18001ce18  mov     rdi, rcx
0x18001ce1b  xor     edx, edx; Val
0x18001ce1d  mov     r8d, 48h ; 'H'; Size
0x18001ce23  lea     rcx, [rsp+0C8h+var_88]; void *
0x18001ce28  call    memset
0x18001ce2d  lea     rcx, [rsp+0C8h+var_88]
0x18001ce32  call    cs:__imp_ExInitializeFastOwnerEntry
0x18001ce39  nop     dword ptr [rax+rax+00h]
0x18001ce3e  mov     rax, [rdi+48h]
0x18001ce42  mov     r15, [rdi+40h]
0x18001ce46  mov     rbx, cs:qword_18003E9A0
0x18001ce4d  mov     rsi, [rax+1B0h]
0x18001ce54  call    cs:__imp_KeEnterGuardedRegion
0x18001ce5b  nop     dword ptr [rax+rax+00h]
0x18001ce60  xor     edx, edx
0x18001ce62  mov     rcx, rbx
0x18001ce65  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x18001ce6c  nop     dword ptr [rax+rax+00h]
0x18001ce71  mov     rbx, rax
0x18001ce74  xor     r12d, r12d
0x18001ce77  movzx   edx, byte ptr [rsi]
0x18001ce7a  cmp     dl, 80h
0x18001ce7d  jz      loc_18001CF30
0x18001ce83  test    ebp, ebp
0x18001ce85  jz      loc_18001CF30
0x18001ce8b  lea     ecx, [rdx+14h]
0x18001ce8e  cmp     cl, 1
0x18001ce91  jbe     loc_18001D02C
0x18001ce97  cmp     [rsi+8], r12
0x18001ce9b  jz      loc_18001D0E2
0x18001cea1  add     dl, 16h
0x18001cea4  cmp     dl, 32h ; '2'
0x18001cea7  jnb     loc_18001D02C
0x18001cead  movzx   eax, dl
0x18001ceb0  lea     rdx, [rdi+rax*8]
0x18001ceb4  cmp     [rdx+130h], r12
0x18001cebb  jnz     loc_18001D0FD
0x18001cec1  mov     [r14+10h], rdi
0x18001cec5  mov     ecx, r12d
0x18001cec8  mov     [r14+28h], r12d
0x18001cecc  mov     rax, [rsi+8]
0x18001ced0  mov     [r14+18h], rax
0x18001ced4  mov     rax, [rsi+10h]
0x18001ced8  mov     [r14+20h], rax
0x18001cedc  mov     eax, [rsi+4]
0x18001cedf  test    al, 1
0x18001cee1  jz      short loc_18001CEF0
0x18001cee3  mov     dword ptr [r14+28h], 1
0x18001ceeb  mov     ecx, 1
0x18001cef0  mov     eax, [rsi+4]
0x18001cef3  test    al, 2
0x18001cef5  jz      short loc_18001CEFE
0x18001cef7  or      ecx, 2
0x18001cefa  mov     [r14+28h], ecx
0x18001cefe  mov     eax, [rsi+4]
0x18001cf01  test    al, 4
0x18001cf03  jnz     loc_18001D0F1
0x18001cf09  mov     eax, [rsi+4]
0x18001cf0c  test    al, 8
0x18001cf0e  jz      short loc_18001CF17
0x18001cf10  or      ecx, 10h
0x18001cf13  mov     [r14+28h], ecx
0x18001cf17  mov     [r14], r12
0x18001cf1a  add     rsi, 20h ; ' '
0x18001cf1e  mov     [rdx+130h], r14
0x18001cf25  add     r14, 30h ; '0'
0x18001cf29  dec     ebp
0x18001cf2b  jmp     loc_18001CE77
0x18001cf30  mov     rax, [rdi+48h]
0x18001cf34  mov     rcx, [rax+180h]
0x18001cf3b  test    rcx, rcx
0x18001cf3e  jnz     loc_18001D124
0x18001cf44  mov     rax, [rdi+48h]
0x18001cf48  mov     rcx, [rax+190h]
0x18001cf4f  lea     r9, [rax+188h]
0x18001cf56  test    rcx, rcx
0x18001cf59  jnz     loc_18001D14D
0x18001cf5f  cmp     [r9], r12
0x18001cf62  jnz     loc_18001D14D
0x18001cf68  xor     edx, edx
0x18001cf6a  mov     rcx, rbx
0x18001cf6d  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x18001cf74  nop     dword ptr [rax+rax+00h]
0x18001cf79  call    cs:__imp_KeLeaveGuardedRegion
0x18001cf80  nop     dword ptr [rax+rax+00h]
0x18001cf85  mov     rbx, cs:qword_18003E9A0
0x18001cf8c  call    cs:__imp_KeEnterGuardedRegion
0x18001cf93  nop     dword ptr [rax+rax+00h]
0x18001cf98  mov     rcx, rbx
0x18001cf9b  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x18001cfa2  nop     dword ptr [rax+rax+00h]
0x18001cfa7  call    cs:__imp_KeEnterCriticalRegion
0x18001cfae  nop     dword ptr [rax+rax+00h]
0x18001cfb3  mov     r8b, 1
0x18001cfb6  lea     rdx, [rsp+0C8h+var_88]
0x18001cfbb  lea     rcx, [r15+0C0h]
0x18001cfc2  call    cs:__imp_ExAcquireFastResourceShared
0x18001cfc9  nop     dword ptr [rax+rax+00h]
0x18001cfce  mov     eax, [rdi]
0x18001cfd0  test    al, 1
0x18001cfd2  jz      short loc_18001D035
0x18001cfd4  lea     rdx, [rsp+0C8h+var_88]
0x18001cfd9  lea     rcx, [r15+0C0h]
0x18001cfe0  call    cs:__imp_ExReleaseFastResource
0x18001cfe7  nop     dword ptr [rax+rax+00h]
0x18001cfec  call    cs:__imp_KeLeaveCriticalRegion
0x18001cff3  nop     dword ptr [rax+rax+00h]
0x18001cff8  mov     rcx, cs:qword_18003E9A0
0x18001cfff  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x18001d006  nop     dword ptr [rax+rax+00h]
0x18001d00b  call    cs:__imp_KeLeaveGuardedRegion
0x18001d012  nop     dword ptr [rax+rax+00h]
0x18001d017  xor     eax, eax
0x18001d019  add     rsp, 90h
0x18001d020  pop     r15
0x18001d022  pop     r14
0x18001d024  pop     r12
0x18001d026  pop     rdi
0x18001d027  pop     rsi
0x18001d028  pop     rbp
0x18001d029  pop     rbx
0x18001d02a  retn
0x18001d02c  add     rsi, 20h ; ' '
0x18001d030  jmp     loc_18001CE77
0x18001d035  mov     eax, r12d
0x18001d038  nop     dword ptr [rax+rax+00000000h]
0x18001d040  mov     r8d, eax
0x18001d043  mov     rdx, [rdi+r8*8+130h]
0x18001d04b  test    rdx, rdx
0x18001d04e  jnz     short loc_18001D05C
0x18001d050  inc     eax
0x18001d052  cmp     eax, 32h ; '2'
0x18001d055  jb      short loc_18001D040
0x18001d057  jmp     loc_18001CFD4
0x18001d05c  mov     r9, rdi
0x18001d05f  lea     r10, [r15+128h]
0x18001d066  mov     rcx, [r9+18h]
0x18001d06a  cmp     rcx, r10
0x18001d06d  jnz     short loc_18001D0A9
0x18001d06f  lea     r9, [r8+14h]
0x18001d073  shl     r9, 4
0x18001d077  add     r9, r15
0x18001d07a  mov     r10, [r9]
0x18001d07d  mov     rcx, [r10+8]
0x18001d081  cmp     rcx, r9
0x18001d084  jnz     short loc_18001D0DB
0x18001d086  mov     [rdx], r10
0x18001d089  mov     [rdx+8], r9
0x18001d08d  mov     [r10+8], rdx
0x18001d091  mov     [r9], rdx
0x18001d094  mov     rcx, [rdi+r8*8+130h]
0x18001d09c  mov     edx, [rcx+28h]
0x18001d09f  and     [r15+r8*4+460h], edx
0x18001d0a7  jmp     short loc_18001D050
0x18001d0a9  mov     r11, [rcx+r8*8+120h]
0x18001d0b1  lea     r9, [rcx-10h]
0x18001d0b5  test    r11, r11
0x18001d0b8  jz      short loc_18001D066
0x18001d0ba  mov     rcx, [r11]
0x18001d0bd  test    rcx, rcx
0x18001d0c0  jz      short loc_18001D066
0x18001d0c2  mov     rcx, [r11]
0x18001d0c5  cmp     [rcx+8], r11
0x18001d0c9  jnz     short loc_18001D0DB
0x18001d0cb  mov     [rdx], rcx
0x18001d0ce  mov     [rdx+8], r11
0x18001d0d2  mov     [rcx+8], rdx
0x18001d0d6  mov     [r11], rdx
0x18001d0d9  jmp     short loc_18001D094
0x18001d0db  mov     ecx, 3
0x18001d0e0  int     29h; Win8: RtlFailFast(ecx)
0x18001d0e2  cmp     [rsi+10h], r12
0x18001d0e6  jz      loc_18001D02C
0x18001d0ec  jmp     loc_18001CEA1
0x18001d0f1  or      ecx, 8
0x18001d0f4  mov     [r14+28h], ecx
0x18001d0f8  jmp     loc_18001CF09
0x18001d0fd  xor     edx, edx
0x18001d0ff  mov     rcx, rbx
0x18001d102  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x18001d109  nop     dword ptr [rax+rax+00h]
0x18001d10e  call    cs:__imp_KeLeaveGuardedRegion
0x18001d115  nop     dword ptr [rax+rax+00h]
0x18001d11a  mov     eax, 0C01C000Dh
0x18001d11f  jmp     loc_18001D019
0x18001d124  test    ebp, ebp
0x18001d126  jz      loc_18001CF44
0x18001d12c  mov     [r14+10h], rdi
0x18001d130  mov     [r14+28h], r12d
0x18001d134  mov     [r14+18h], rcx
0x18001d138  mov     [r14], r12
0x18001d13b  mov     [rdi+138h], r14
0x18001d142  add     r14, 30h ; '0'
0x18001d146  dec     ebp
0x18001d148  jmp     loc_18001CF44
0x18001d14d  test    ebp, ebp
0x18001d14f  jz      loc_18001CF68
0x18001d155  mov     rax, [rax+198h]
0x18001d15c  xor     r8d, r8d
0x18001d15f  mov     r9, [r9]
0x18001d162  xor     edx, edx
0x18001d164  mov     [rsp+0C8h+var_90], r12d
0x18001d169  mov     [rsp+0C8h+var_98], rdi
0x18001d16e  mov     [rsp+0C8h+var_A0], rax
0x18001d173  mov     [rsp+0C8h+var_A8], rcx
0x18001d178  mov     rcx, r14
0x18001d17b  call    FltpInitializeCallbackNode
0x18001d180  jmp     loc_18001CF68
```
