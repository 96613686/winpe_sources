# NpCheckForNotifyWithFilter

- ea: `0x140010d18`
- end: `0x140010eeb`
- name: `NpCheckForNotifyWithFilter`
- size: `467`
- prototype: `void __fastcall(__int64, __int64, __int64, const void **, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14001070c`
- `0x1400107c0`
- `0x140010ef4`
- `0x14001399c`

## callees

- `0x140001f40`
- `0x140002240`
- `0x140010d18`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010d5b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010d5b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010ea2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010ea2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010e0d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010e0d`

## pseudocode

```c
void __fastcall NpCheckForNotifyWithFilter(__int64 a1, __int64 a2, __int64 a3, const void **a4, int a5)
{
  _QWORD **v5; // rsi
  int v7; // edi
  _QWORD *v9; // rbx
  _QWORD *v10; // r14
  __int64 v11; // r15
  __int64 v12; // rax
  _QWORD *v13; // rcx
  int v14; // r12d
  unsigned int v15; // ecx
  _DWORD *v16; // rdi
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // [rsp+30h] [rbp-48h]
  unsigned int v20; // [rsp+80h] [rbp+8h]
  int v21; // [rsp+90h] [rbp+18h]

  v21 = a3;
  v5 = (_QWORD **)(a1 + 176);
  v7 = a3;
  if ( *v5 != v5 )
  {
    v19 = a1 + 168;
    ExAcquirePushLockExclusiveEx(a1 + 168, 0, a3, a4);
    v9 = *v5;
    v10 = (_QWORD *)**v5;
    if ( *v5 != v5 )
    {
      while ( 1 )
      {
        v11 = v9[2];
        if ( (v7 & *(_DWORD *)(v11 + 16)) != 0 )
        {
          v12 = *v9;
          if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v13 = (_QWORD *)v9[1], (_QWORD *)*v13 != v9) )
LABEL_25:
            __fastfail(3u);
          v14 = 0;
          *v13 = v12;
          *(_QWORD *)(v12 + 8) = v13;
          if ( a4 )
          {
            v15 = *(_DWORD *)(v11 + 8);
            if ( v15 )
            {
              v20 = *(unsigned __int16 *)a4 + 16;
              if ( v15 < v20 )
              {
                v14 = -1073741789;
              }
              else
              {
                v16 = (_DWORD *)*(v9 - 18);
                if ( v16
                  || (v17 = *(v9 - 20)) != 0
                  && ((*(_BYTE *)(v17 + 10) & 5) != 0
                    ? (v16 = *(_DWORD **)(v17 + 24))
                    : (v16 = MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000010u)),
                      v16) )
                {
                  memset(v16, 0, *(unsigned int *)(v11 + 8));
                  v16[2] = *(unsigned __int16 *)a4;
                  memmove(v16 + 3, a4[1], *(unsigned __int16 *)a4);
                  v16[1] = a5;
                  *(v9 - 14) = v20;
                }
                v7 = v21;
              }
            }
          }
          if ( _InterlockedExchange64(v9 - 8, 0) )
          {
            *((_DWORD *)v9 - 30) = v14;
            v18 = *(_QWORD **)(a2 + 8);
            if ( *v18 != a2 )
              goto LABEL_25;
            *v9 = a2;
            v9[1] = v18;
            *v18 = v9;
            *(_QWORD *)(a2 + 8) = v9;
          }
          else
          {
            v9[1] = v9;
            *v9 = v9;
          }
        }
        if ( v10 == v5 )
          break;
        v9 = v10;
        v10 = (_QWORD *)*v10;
      }
    }
    ExReleasePushLockExclusiveEx(v19, 0);
  }
}

```

## disassembly

```asm
0x140010d18  mov     [rsp+arg_8], rbx
0x140010d1d  mov     [rsp+arg_10], r8d
0x140010d22  push    rbp
0x140010d23  push    rsi
0x140010d24  push    rdi
0x140010d25  push    r12
0x140010d27  push    r13
0x140010d29  push    r14
0x140010d2b  push    r15
0x140010d2d  sub     rsp, 40h
0x140010d31  lea     rsi, [rcx+0B0h]
0x140010d38  mov     r13, r9
0x140010d3b  mov     edi, r8d
0x140010d3e  mov     rbp, rdx
0x140010d41  cmp     [rsi], rsi
0x140010d44  jz      loc_140010EAE
0x140010d4a  lea     rax, [rcx+0A8h]
0x140010d51  xor     edx, edx
0x140010d53  mov     rcx, rax
0x140010d56  mov     [rsp+78h+var_48], rax
0x140010d5b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140010d62  nop     dword ptr [rax+rax+00h]
0x140010d67  mov     rbx, [rsi]
0x140010d6a  mov     r14, [rbx]
0x140010d6d  cmp     rbx, rsi
0x140010d70  jz      loc_140010E9B
0x140010d76  mov     r15, [rbx+10h]
0x140010d7a  test    [r15+10h], edi
0x140010d7e  jz      loc_140010E8B
0x140010d84  mov     rax, [rbx]
0x140010d87  cmp     [rax+8], rbx
0x140010d8b  jnz     loc_140010ED9
0x140010d91  mov     rcx, [rbx+8]
0x140010d95  cmp     [rcx], rbx
0x140010d98  jnz     loc_140010ED9
0x140010d9e  xor     r12d, r12d
0x140010da1  mov     [rcx], rax
0x140010da4  mov     [rax+8], rcx
0x140010da8  test    r13, r13
0x140010dab  jz      loc_140010E65
0x140010db1  mov     ecx, [r15+8]
0x140010db5  test    ecx, ecx
0x140010db7  jz      loc_140010E65
0x140010dbd  movzx   eax, word ptr [r13+0]
0x140010dc2  add     eax, 10h
0x140010dc5  mov     [rsp+78h+arg_0], eax
0x140010dcc  cmp     ecx, eax
0x140010dce  jb      loc_140010EE0
0x140010dd4  mov     rdi, [rbx-90h]
0x140010ddb  test    rdi, rdi
0x140010dde  jnz     short loc_140010E21
0x140010de0  mov     rcx, [rbx-0A0h]; MemoryDescriptorList
0x140010de7  test    rcx, rcx
0x140010dea  jz      short loc_140010E5E
0x140010dec  test    byte ptr [rcx+0Ah], 5
0x140010df0  jnz     loc_140010ED0
0x140010df6  mov     [rsp+78h+Priority], 40000010h; Priority
0x140010dfe  lea     r8d, [r12+1]; CacheType
0x140010e03  xor     r9d, r9d; RequestedAddress
0x140010e06  mov     [rsp+78h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140010e0b  xor     edx, edx; AccessMode
0x140010e0d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140010e14  nop     dword ptr [rax+rax+00h]
0x140010e19  mov     rdi, rax
0x140010e1c  test    rdi, rdi
0x140010e1f  jz      short loc_140010E5E
0x140010e21  mov     r8d, [r15+8]; Size
0x140010e25  xor     edx, edx; Val
0x140010e27  mov     rcx, rdi; void *
0x140010e2a  call    memset
0x140010e2f  movzx   ecx, word ptr [r13+0]
0x140010e34  mov     [rdi+8], ecx
0x140010e37  lea     rcx, [rdi+0Ch]; void *
0x140010e3b  movzx   r8d, word ptr [r13+0]; Size
0x140010e40  mov     rdx, [r13+8]; Src
0x140010e44  call    memmove
0x140010e49  mov     eax, [rsp+78h+arg_20]
0x140010e50  mov     [rdi+4], eax
0x140010e53  mov     eax, [rsp+78h+arg_0]
0x140010e5a  mov     [rbx-70h], rax
0x140010e5e  mov     edi, [rsp+78h+arg_10]
0x140010e65  xor     eax, eax
0x140010e67  xchg    rax, [rbx-40h]
0x140010e6b  test    rax, rax
0x140010e6e  jz      short loc_140010EC7
0x140010e70  mov     [rbx-78h], r12d
0x140010e74  mov     rax, [rbp+8]
0x140010e78  cmp     [rax], rbp
0x140010e7b  jnz     short loc_140010ED9
0x140010e7d  mov     [rbx], rbp
0x140010e80  mov     [rbx+8], rax
0x140010e84  mov     [rax], rbx
0x140010e87  mov     [rbp+8], rbx
0x140010e8b  cmp     r14, rsi
0x140010e8e  jz      short loc_140010E9B
0x140010e90  mov     rbx, r14
0x140010e93  mov     r14, [r14]
0x140010e96  jmp     loc_140010D76
0x140010e9b  mov     rcx, [rsp+78h+var_48]
0x140010ea0  xor     edx, edx
0x140010ea2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010ea9  nop     dword ptr [rax+rax+00h]
0x140010eae  mov     rbx, [rsp+78h+arg_8]
0x140010eb6  add     rsp, 40h
0x140010eba  pop     r15
0x140010ebc  pop     r14
0x140010ebe  pop     r13
0x140010ec0  pop     r12
0x140010ec2  pop     rdi
0x140010ec3  pop     rsi
0x140010ec4  pop     rbp
0x140010ec5  retn
0x140010ec7  mov     [rbx+8], rbx
0x140010ecb  mov     [rbx], rbx
0x140010ece  jmp     short loc_140010E8B
0x140010ed0  mov     rdi, [rcx+18h]
0x140010ed4  jmp     loc_140010E1C
0x140010ed9  mov     ecx, 3
0x140010ede  int     29h; Win8: RtlFailFast(ecx)
0x140010ee0  mov     r12d, 0C0000023h
0x140010ee6  jmp     loc_140010E65
```
