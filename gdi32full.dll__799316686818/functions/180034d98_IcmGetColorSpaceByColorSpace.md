# IcmGetColorSpaceByColorSpace

- ea: `0x180034d98`
- end: `0x180034f86`
- name: `IcmGetColorSpaceByColorSpace`
- size: `494`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800267d0`
- `0x180033000`
- `0x180033e14`
- `0x18006b93c`
- `0x180088fa0`

## callees

- `0x180034d98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034e7a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034ea0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034ebf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034e7a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034ea0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034ebf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180034f2d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180034f6c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180034f2d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180034f6c`
- `ntdll!RtlEnterCriticalSection` at `0x180034ded`
- `ntdll!RtlEnterCriticalSection` at `0x180034ded`
- `ntdll!RtlLeaveCriticalSection` at `0x180034e1a`
- `ntdll!RtlLeaveCriticalSection` at `0x180034e1a`

## pseudocode

```c
PVOID *__fastcall IcmGetColorSpaceByColorSpace(PVOID a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int16 a6)
{
  PVOID *result; // rax
  _WORD *v10; // rbx
  PVOID *i; // rdi
  PVOID *v12; // r14
  PVOID v13; // rax
  PVOID v14; // rax
  _WORD *v15; // rax
  unsigned int v16; // eax

  result = 0;
  if ( !a3 || *(_DWORD *)a3 != 2 || *(_DWORD *)(a3 + 16) <= 0x100000u || *(_WORD *)(a2 + 68) )
  {
    v10 = (_WORD *)(a2 + 68);
    RtlEnterCriticalSection(&semColorSpaceCache);
    for ( i = (PVOID *)ListCachedColorSpace; ; i = (PVOID *)*i )
    {
      v12 = 0;
      if ( i == &ListCachedColorSpace )
      {
LABEL_7:
        RtlLeaveCriticalSection(&semColorSpaceCache);
        return v12;
      }
      if ( (i[2] == a1 || (a6 & 0xFFF) != 2 && !i[2]) && *((_DWORD *)i + 26) == *(_DWORD *)(a2 + 16) )
      {
        v13 = i[9];
        if ( a4 )
        {
          if ( !v13 || (unsigned int)_o__wcsicmp(a4, i[9]) )
            continue;
        }
        else if ( v13 )
        {
          continue;
        }
        v14 = i[10];
        if ( a5 )
        {
          if ( !v14 || (unsigned int)_o__wcsicmp(a5, i[10]) )
            continue;
        }
        else if ( v14 )
        {
          continue;
        }
        v15 = (_WORD *)i + 78;
        v12 = i;
        if ( *v10 )
        {
          if ( *v15 && !(unsigned int)_o__wcsicmp(v10, (char *)i + 156) )
            goto LABEL_22;
        }
        else if ( !*v15 )
        {
          if ( a3 )
          {
            if ( *(_DWORD *)a3 == 2 && *((_DWORD *)i + 12) == 2 )
            {
              v16 = *(_DWORD *)(a3 + 16);
              if ( *((_DWORD *)i + 16) == v16 )
              {
                if ( RtlCompareMemory(i[7], *(const void **)(a3 + 8), v16) == v16 )
                  goto LABEL_22;
                v10 = (_WORD *)(a2 + 68);
              }
            }
          }
          else if ( *((_DWORD *)i + 25) == *(_DWORD *)(a2 + 12)
                 && *((_DWORD *)i + 36) == *(_DWORD *)(a2 + 56)
                 && *((_DWORD *)i + 37) == *(_DWORD *)(a2 + 60)
                 && *((_DWORD *)i + 38) == *(_DWORD *)(a2 + 64)
                 && RtlCompareMemory((char *)i + 108, (const void *)(a2 + 20), 0x24u) == 36 )
          {
LABEL_22:
            ++*((_DWORD *)i + 7);
            goto LABEL_7;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180034d98  mov     [rsp+arg_0], rcx
0x180034d9d  push    rbx
0x180034d9e  push    rbp
0x180034d9f  push    rsi
0x180034da0  push    rdi
0x180034da1  push    r12
0x180034da3  push    r13
0x180034da5  push    r14
0x180034da7  push    r15
0x180034da9  sub     rsp, 28h
0x180034dad  xor     eax, eax
0x180034daf  mov     r12, r9
0x180034db2  mov     rbp, r8
0x180034db5  mov     rsi, rdx
0x180034db8  test    r8, r8
0x180034dbb  jz      short loc_180034DD3
0x180034dbd  cmp     dword ptr [r8], 2
0x180034dc1  jnz     short loc_180034DD3
0x180034dc3  cmp     dword ptr [r8+10h], 100000h
0x180034dcb  jbe     short loc_180034DD3
0x180034dcd  cmp     [rdx+44h], ax
0x180034dd1  jz      short loc_180034E23
0x180034dd3  mov     r15d, [rsp+68h+arg_28]
0x180034ddb  lea     rcx, semColorSpaceCache; CriticalSection
0x180034de2  and     r15d, 0FFFh
0x180034de9  lea     rbx, [rdx+44h]
0x180034ded  call    cs:__imp_RtlEnterCriticalSection
0x180034df3  mov     rdi, cs:ListCachedColorSpace
0x180034dfa  xor     ecx, ecx
0x180034dfc  mov     r13, [rsp+68h+arg_20]
0x180034e04  lea     rax, ListCachedColorSpace
0x180034e0b  mov     r14, rcx
0x180034e0e  cmp     rdi, rax
0x180034e11  jnz     short loc_180034E34
0x180034e13  lea     rcx, semColorSpaceCache; CriticalSection
0x180034e1a  call    cs:__imp_RtlLeaveCriticalSection
0x180034e20  mov     rax, r14
0x180034e23  add     rsp, 28h
0x180034e27  pop     r15
0x180034e29  pop     r14
0x180034e2b  pop     r13
0x180034e2d  pop     r12
0x180034e2f  pop     rdi
0x180034e30  pop     rsi
0x180034e31  pop     rbp
0x180034e32  pop     rbx
0x180034e33  retn
0x180034e34  mov     rax, [rsp+68h+arg_0]
0x180034e39  cmp     [rdi+10h], rax
0x180034e3d  jz      short loc_180034E50
0x180034e3f  cmp     r15d, 2
0x180034e43  jnz     short loc_180034E4A
0x180034e45  mov     rdi, [rdi]
0x180034e48  jmp     short loc_180034E04
0x180034e4a  cmp     [rdi+10h], rcx
0x180034e4e  jnz     short loc_180034E45
0x180034e50  mov     eax, [rsi+10h]
0x180034e53  cmp     [rdi+68h], eax
0x180034e56  jnz     short loc_180034E45
0x180034e58  mov     rax, [rdi+48h]
0x180034e5c  test    r12, r12
0x180034e5f  jnz     short loc_180034EB4
0x180034e61  test    rax, rax
0x180034e64  jnz     short loc_180034E45
0x180034e66  mov     rax, [rdi+50h]
0x180034e6a  test    r13, r13
0x180034e6d  jz      short loc_180034ED0
0x180034e6f  test    rax, rax
0x180034e72  jz      short loc_180034E45
0x180034e74  mov     rdx, rax
0x180034e77  mov     rcx, r13
0x180034e7a  call    cs:__imp__o__wcsicmp
0x180034e80  xor     ecx, ecx
0x180034e82  test    eax, eax
0x180034e84  jnz     short loc_180034E45
0x180034e86  lea     rax, [rdi+9Ch]
0x180034e8d  mov     r14, rdi
0x180034e90  cmp     [rbx], cx
0x180034e93  jz      short loc_180034EDA
0x180034e95  cmp     [rax], cx
0x180034e98  jz      short loc_180034E45
0x180034e9a  mov     rdx, rax
0x180034e9d  mov     rcx, rbx
0x180034ea0  call    cs:__imp__o__wcsicmp
0x180034ea6  xor     ecx, ecx
0x180034ea8  test    eax, eax
0x180034eaa  jnz     short loc_180034E45
0x180034eac  inc     dword ptr [rdi+1Ch]
0x180034eaf  jmp     loc_180034E13
0x180034eb4  test    rax, rax
0x180034eb7  jz      short loc_180034E45
0x180034eb9  mov     rdx, rax
0x180034ebc  mov     rcx, r12
0x180034ebf  call    cs:__imp__o__wcsicmp
0x180034ec5  xor     ecx, ecx
0x180034ec7  test    eax, eax
0x180034ec9  jz      short loc_180034E66
0x180034ecb  jmp     loc_180034E45
0x180034ed0  test    rax, rax
0x180034ed3  jz      short loc_180034E86
0x180034ed5  jmp     loc_180034E45
0x180034eda  cmp     [rax], cx
0x180034edd  jnz     loc_180034E45
0x180034ee3  test    rbp, rbp
0x180034ee6  jnz     short loc_180034F3F
0x180034ee8  mov     eax, [rsi+0Ch]
0x180034eeb  cmp     [rdi+64h], eax
0x180034eee  jnz     loc_180034E45
0x180034ef4  mov     eax, [rsi+38h]
0x180034ef7  cmp     [rdi+90h], eax
0x180034efd  jnz     loc_180034E45
0x180034f03  mov     eax, [rsi+3Ch]
0x180034f06  cmp     [rdi+94h], eax
0x180034f0c  jnz     loc_180034E45
0x180034f12  mov     eax, [rsi+40h]
0x180034f15  cmp     [rdi+98h], eax
0x180034f1b  jnz     loc_180034E45
0x180034f21  lea     rdx, [rsi+14h]; Source2
0x180034f25  lea     rcx, [rdi+6Ch]; Source1
0x180034f29  lea     r8d, [rbp+24h]; Length
0x180034f2d  call    cs:__imp_RtlCompareMemory
0x180034f33  cmp     rax, 24h ; '$'
0x180034f37  jz      loc_180034EAC
0x180034f3d  jmp     short loc_180034F7F
0x180034f3f  cmp     dword ptr [rbp+0], 2
0x180034f43  jnz     loc_180034E45
0x180034f49  cmp     dword ptr [rdi+30h], 2
0x180034f4d  jnz     loc_180034E45
0x180034f53  mov     eax, [rbp+10h]
0x180034f56  cmp     [rdi+40h], eax
0x180034f59  jnz     loc_180034E45
0x180034f5f  mov     rdx, [rbp+8]; Source2
0x180034f63  mov     r8d, eax; Length
0x180034f66  mov     rcx, [rdi+38h]; Source1
0x180034f6a  mov     ebx, eax
0x180034f6c  call    cs:__imp_RtlCompareMemory
0x180034f72  cmp     rax, rbx
0x180034f75  jz      loc_180034EAC
0x180034f7b  lea     rbx, [rsi+44h]
0x180034f7f  xor     ecx, ecx
0x180034f81  jmp     loc_180034E45
```
