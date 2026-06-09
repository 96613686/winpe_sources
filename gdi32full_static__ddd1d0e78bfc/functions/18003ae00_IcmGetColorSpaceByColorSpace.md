# IcmGetColorSpaceByColorSpace

- ea: `0x18003ae00`
- end: `0x18003b019`
- name: `IcmGetColorSpaceByColorSpace`
- size: `537`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f820`
- `0x180038f0c`
- `0x180039df0`
- `0x180070288`
- `0x18008e580`

## callees

- `0x18003ae00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003aeef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003af1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003af40`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003aeef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003af1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003af40`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003afb4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003aff9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003afb4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003aff9`
- `ntdll!RtlEnterCriticalSection` at `0x18003ae55`
- `ntdll!RtlEnterCriticalSection` at `0x18003ae55`
- `ntdll!RtlLeaveCriticalSection` at `0x18003ae88`
- `ntdll!RtlLeaveCriticalSection` at `0x18003ae88`

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
0x18003ae00  mov     [rsp+arg_0], rcx
0x18003ae05  push    rbx
0x18003ae06  push    rbp
0x18003ae07  push    rsi
0x18003ae08  push    rdi
0x18003ae09  push    r12
0x18003ae0b  push    r13
0x18003ae0d  push    r14
0x18003ae0f  push    r15
0x18003ae11  sub     rsp, 28h
0x18003ae15  xor     eax, eax
0x18003ae17  mov     r12, r9
0x18003ae1a  mov     rbp, r8
0x18003ae1d  mov     rsi, rdx
0x18003ae20  test    r8, r8
0x18003ae23  jz      short loc_18003AE3B
0x18003ae25  cmp     dword ptr [r8], 2
0x18003ae29  jnz     short loc_18003AE3B
0x18003ae2b  cmp     dword ptr [r8+10h], 100000h
0x18003ae33  jbe     short loc_18003AE3B
0x18003ae35  cmp     [rdx+44h], ax
0x18003ae39  jz      short loc_18003AE97
0x18003ae3b  mov     r15d, [rsp+68h+arg_28]
0x18003ae43  lea     rcx, semColorSpaceCache; CriticalSection
0x18003ae4a  and     r15d, 0FFFh
0x18003ae51  lea     rbx, [rdx+44h]
0x18003ae55  call    cs:__imp_RtlEnterCriticalSection
0x18003ae5c  nop     dword ptr [rax+rax+00h]
0x18003ae61  mov     rdi, cs:ListCachedColorSpace
0x18003ae68  xor     ecx, ecx
0x18003ae6a  mov     r13, [rsp+68h+arg_20]
0x18003ae72  lea     rax, ListCachedColorSpace
0x18003ae79  mov     r14, rcx
0x18003ae7c  cmp     rdi, rax
0x18003ae7f  jnz     short loc_18003AEA9
0x18003ae81  lea     rcx, semColorSpaceCache; CriticalSection
0x18003ae88  call    cs:__imp_RtlLeaveCriticalSection
0x18003ae8f  nop     dword ptr [rax+rax+00h]
0x18003ae94  mov     rax, r14
0x18003ae97  add     rsp, 28h
0x18003ae9b  pop     r15
0x18003ae9d  pop     r14
0x18003ae9f  pop     r13
0x18003aea1  pop     r12
0x18003aea3  pop     rdi
0x18003aea4  pop     rsi
0x18003aea5  pop     rbp
0x18003aea6  pop     rbx
0x18003aea7  retn
0x18003aea9  mov     rax, [rsp+68h+arg_0]
0x18003aeae  cmp     [rdi+10h], rax
0x18003aeb2  jz      short loc_18003AEC5
0x18003aeb4  cmp     r15d, 2
0x18003aeb8  jnz     short loc_18003AEBF
0x18003aeba  mov     rdi, [rdi]
0x18003aebd  jmp     short loc_18003AE72
0x18003aebf  cmp     [rdi+10h], rcx
0x18003aec3  jnz     short loc_18003AEBA
0x18003aec5  mov     eax, [rsi+10h]
0x18003aec8  cmp     [rdi+68h], eax
0x18003aecb  jnz     short loc_18003AEBA
0x18003aecd  mov     rax, [rdi+48h]
0x18003aed1  test    r12, r12
0x18003aed4  jnz     short loc_18003AF35
0x18003aed6  test    rax, rax
0x18003aed9  jnz     short loc_18003AEBA
0x18003aedb  mov     rax, [rdi+50h]
0x18003aedf  test    r13, r13
0x18003aee2  jz      short loc_18003AF57
0x18003aee4  test    rax, rax
0x18003aee7  jz      short loc_18003AEBA
0x18003aee9  mov     rdx, rax
0x18003aeec  mov     rcx, r13
0x18003aeef  call    cs:__imp__o__wcsicmp
0x18003aef6  nop     dword ptr [rax+rax+00h]
0x18003aefb  xor     ecx, ecx
0x18003aefd  test    eax, eax
0x18003aeff  jnz     short loc_18003AEBA
0x18003af01  lea     rax, [rdi+9Ch]
0x18003af08  mov     r14, rdi
0x18003af0b  cmp     [rbx], cx
0x18003af0e  jz      short loc_18003AF61
0x18003af10  cmp     [rax], cx
0x18003af13  jz      short loc_18003AEBA
0x18003af15  mov     rdx, rax
0x18003af18  mov     rcx, rbx
0x18003af1b  call    cs:__imp__o__wcsicmp
0x18003af22  nop     dword ptr [rax+rax+00h]
0x18003af27  xor     ecx, ecx
0x18003af29  test    eax, eax
0x18003af2b  jnz     short loc_18003AEBA
0x18003af2d  inc     dword ptr [rdi+1Ch]
0x18003af30  jmp     loc_18003AE81
0x18003af35  test    rax, rax
0x18003af38  jz      short loc_18003AEBA
0x18003af3a  mov     rdx, rax
0x18003af3d  mov     rcx, r12
0x18003af40  call    cs:__imp__o__wcsicmp
0x18003af47  nop     dword ptr [rax+rax+00h]
0x18003af4c  xor     ecx, ecx
0x18003af4e  test    eax, eax
0x18003af50  jz      short loc_18003AEDB
0x18003af52  jmp     loc_18003AEBA
0x18003af57  test    rax, rax
0x18003af5a  jz      short loc_18003AF01
0x18003af5c  jmp     loc_18003AEBA
0x18003af61  cmp     [rax], cx
0x18003af64  jnz     loc_18003AEBA
0x18003af6a  test    rbp, rbp
0x18003af6d  jnz     short loc_18003AFCC
0x18003af6f  mov     eax, [rsi+0Ch]
0x18003af72  cmp     [rdi+64h], eax
0x18003af75  jnz     loc_18003AEBA
0x18003af7b  mov     eax, [rsi+38h]
0x18003af7e  cmp     [rdi+90h], eax
0x18003af84  jnz     loc_18003AEBA
0x18003af8a  mov     eax, [rsi+3Ch]
0x18003af8d  cmp     [rdi+94h], eax
0x18003af93  jnz     loc_18003AEBA
0x18003af99  mov     eax, [rsi+40h]
0x18003af9c  cmp     [rdi+98h], eax
0x18003afa2  jnz     loc_18003AEBA
0x18003afa8  lea     rdx, [rsi+14h]; Source2
0x18003afac  lea     rcx, [rdi+6Ch]; Source1
0x18003afb0  lea     r8d, [rbp+24h]; Length
0x18003afb4  call    cs:__imp_RtlCompareMemory
0x18003afbb  nop     dword ptr [rax+rax+00h]
0x18003afc0  cmp     rax, 24h ; '$'
0x18003afc4  jz      loc_18003AF2D
0x18003afca  jmp     short loc_18003B012
0x18003afcc  cmp     dword ptr [rbp+0], 2
0x18003afd0  jnz     loc_18003AEBA
0x18003afd6  cmp     dword ptr [rdi+30h], 2
0x18003afda  jnz     loc_18003AEBA
0x18003afe0  mov     eax, [rbp+10h]
0x18003afe3  cmp     [rdi+40h], eax
0x18003afe6  jnz     loc_18003AEBA
0x18003afec  mov     rdx, [rbp+8]; Source2
0x18003aff0  mov     r8d, eax; Length
0x18003aff3  mov     rcx, [rdi+38h]; Source1
0x18003aff7  mov     ebx, eax
0x18003aff9  call    cs:__imp_RtlCompareMemory
0x18003b000  nop     dword ptr [rax+rax+00h]
0x18003b005  cmp     rax, rbx
0x18003b008  jz      loc_18003AF2D
0x18003b00e  lea     rbx, [rsi+44h]
0x18003b012  xor     ecx, ecx
0x18003b014  jmp     loc_18003AEBA
```
