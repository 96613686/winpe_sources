# AllocateAndGetComputerName(tagComputerNameAllocators,_COMPUTER_NAME_FORMAT,unsigned __int64,ulong,ulong *)

- ea: `0x1800b43a0`
- end: `0x1800b4450`
- name: `?AllocateAndGetComputerName@@YAPEAGW4tagComputerNameAllocators@@W4_COMPUTER_NAME_FORMAT@@_KKPEAK@Z`
- size: `176`
- prototype: `unsigned __int16 *__high(enum tagComputerNameAllocators, enum _COMPUTER_NAME_FORMAT, unsigned __int64, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b4340`
- `0x1800b4ce8`
- `0x1800c5a04`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800b43a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b43d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b43d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b43cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b440f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b43cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b440f`

## pseudocode

```c
void *__fastcall AllocateAndGetComputerName(
        __int64 a1,
        COMPUTER_NAME_FORMAT a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5)
{
  __int64 v6; // r14
  void *v8; // rbx
  char *v10; // rax
  char *v11; // rdi
  __int64 v12; // rcx
  DWORD nSize[18]; // [rsp+20h] [rbp-48h] BYREF

  v6 = a4;
  nSize[0] = 0;
  v8 = 0;
  GetComputerNameExW(a2, 0, nSize);
  if ( GetLastError() != 234 )
    return v8;
  if ( nSize[0] > 0x1388 )
    return 0;
  v10 = (char *)AllocWrapper(a3 + 2LL * nSize[0]);
  v8 = v10;
  if ( v10 )
  {
    v11 = &v10[v6];
    if ( GetComputerNameExW(a2, (LPWSTR)&v10[v6], nSize) )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&v11[2 * v12] );
      *a5 = v12 + 1;
      return v8;
    }
    FreeWrapper(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b43a0  push    rbx
0x1800b43a2  push    rbp
0x1800b43a3  push    rsi
0x1800b43a4  push    rdi
0x1800b43a5  push    r14
0x1800b43a7  push    r15
0x1800b43a9  sub     rsp, 38h
0x1800b43ad  mov     ebp, edx
0x1800b43af  mov     r14d, r9d
0x1800b43b2  mov     rsi, r8
0x1800b43b5  mov     edi, ecx
0x1800b43b7  xor     r15d, r15d
0x1800b43ba  lea     r8, [rsp+68h+nSize]; nSize
0x1800b43bf  mov     ecx, ebp; NameType
0x1800b43c1  mov     [rsp+68h+nSize], r15d
0x1800b43c6  xor     edx, edx; lpBuffer
0x1800b43c8  mov     ebx, r15d
0x1800b43cb  call    cs:__imp_GetComputerNameExW
0x1800b43d1  call    cs:__imp_GetLastError
0x1800b43d7  cmp     eax, 0EAh
0x1800b43dc  jnz     short loc_1800B4424
0x1800b43de  mov     eax, [rsp+68h+nSize]
0x1800b43e2  cmp     eax, 1388h
0x1800b43e7  jbe     short loc_1800B43ED
0x1800b43e9  xor     eax, eax
0x1800b43eb  jmp     short loc_1800B4427
0x1800b43ed  mov     rcx, rax
0x1800b43f0  lea     rcx, [rsi+rax*2]; dwBytes
0x1800b43f4  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b43f9  mov     rbx, rax
0x1800b43fc  test    rax, rax
0x1800b43ff  jz      short loc_1800B4421
0x1800b4401  lea     rdi, [rax+r14]
0x1800b4405  mov     ecx, ebp; NameType
0x1800b4407  mov     rdx, rdi; lpBuffer
0x1800b440a  lea     r8, [rsp+68h+nSize]; nSize
0x1800b440f  call    cs:__imp_GetComputerNameExW
0x1800b4415  test    eax, eax
0x1800b4417  jnz     short loc_1800B4434
0x1800b4419  mov     rcx, rbx; lpMem
0x1800b441c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b4421  mov     rbx, r15
0x1800b4424  mov     rax, rbx
0x1800b4427  add     rsp, 38h
0x1800b442b  pop     r15
0x1800b442d  pop     r14
0x1800b442f  pop     rdi
0x1800b4430  pop     rsi
0x1800b4431  pop     rbp
0x1800b4432  pop     rbx
0x1800b4433  retn
0x1800b4434  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b4438  inc     rcx
0x1800b443b  cmp     [rdi+rcx*2], r15w
0x1800b4440  jnz     short loc_1800B4438
0x1800b4442  mov     rax, [rsp+68h+arg_20]
0x1800b444a  inc     ecx
0x1800b444c  mov     [rax], ecx
0x1800b444e  jmp     short loc_1800B4424
```
