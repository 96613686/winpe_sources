# GetPersistentRegPathFromSourceId(ushort const *,ushort const *,ulong *,ushort *)

- ea: `0x18002539c`
- end: `0x1800254a6`
- name: `?GetPersistentRegPathFromSourceId@@YAKPEBG0PEAKPEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040b48`

## callees

- `0x18002539c`
- `0x180047240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002545d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002545d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180025493`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180025493`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800253e0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800253e0`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPathFromSourceId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  unsigned int PersistedRegistryLocationW; // eax
  unsigned __int64 v8; // rbp
  unsigned int v9; // r15d
  __int64 v10; // rsi
  unsigned __int64 v11; // rbx
  unsigned __int64 i; // rdi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  unsigned int v16; // [rsp+30h] [rbp-58h] BYREF

  v16 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(a1, a2, a4, 2 * *a3, &v16);
  v8 = (unsigned __int64)v16 >> 1;
  v9 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW && a2 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    for ( i = 0; i < v11; ++i )
    {
      if ( !(unsigned int)_o__wcsnicmp(&a4[i], a2, v11 - i) )
        break;
    }
    v13 = v11 - i;
    if ( v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      if ( v13 < v14 )
      {
        do
          ++v10;
        while ( a2[v13 + v10] );
        v8 += v10;
        if ( *a3 < v8 )
          v9 = 234;
        else
          v9 = _o_wcscat_s(a4, v8);
      }
    }
  }
  *a3 = v8;
  return v9;
}

```

## disassembly

```asm
0x18002539c  push    rbx
0x18002539e  push    rbp
0x18002539f  push    rsi
0x1800253a0  push    rdi
0x1800253a1  push    r12
0x1800253a3  push    r13
0x1800253a5  push    r14
0x1800253a7  push    r15
0x1800253a9  sub     rsp, 48h
0x1800253ad  mov     rax, cs:__security_cookie
0x1800253b4  xor     rax, rsp
0x1800253b7  mov     [rsp+88h+var_50], rax
0x1800253bc  mov     r12, r9
0x1800253bf  mov     [rsp+88h+var_58], 0
0x1800253c7  mov     r9d, [r8]
0x1800253ca  lea     rax, [rsp+88h+var_58]
0x1800253cf  mov     r13, r8
0x1800253d2  mov     [rsp+88h+var_68], rax
0x1800253d7  add     r9d, r9d
0x1800253da  mov     r8, r12
0x1800253dd  mov     r14, rdx
0x1800253e0  call    cs:__imp_GetPersistedRegistryLocationW
0x1800253e6  mov     ebp, [rsp+88h+var_58]
0x1800253ea  xor     ecx, ecx
0x1800253ec  shr     rbp, 1
0x1800253ef  mov     r15d, eax
0x1800253f2  test    eax, eax
0x1800253f4  jnz     short loc_18002542B
0x1800253f6  test    r14, r14
0x1800253f9  jz      short loc_18002542B
0x1800253fb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800253ff  mov     rbx, rsi
0x180025402  inc     rbx
0x180025405  cmp     [r12+rbx*2], cx
0x18002540a  jnz     short loc_180025402
0x18002540c  mov     rdi, rcx
0x18002540f  test    rbx, rbx
0x180025412  jnz     short loc_180025450
0x180025414  sub     rbx, rdi
0x180025417  jz      short loc_18002542B
0x180025419  mov     rax, rsi
0x18002541c  inc     rax
0x18002541f  cmp     [r14+rax*2], cx
0x180025424  jnz     short loc_18002541C
0x180025426  cmp     rbx, rax
0x180025429  jb      short loc_180025473
0x18002542b  mov     [r13+0], ebp
0x18002542f  mov     eax, r15d
0x180025432  mov     rcx, [rsp+88h+var_50]
0x180025437  xor     rcx, rsp; StackCookie
0x18002543a  call    __security_check_cookie
0x18002543f  add     rsp, 48h
0x180025443  pop     r15
0x180025445  pop     r14
0x180025447  pop     r13
0x180025449  pop     r12
0x18002544b  pop     rdi
0x18002544c  pop     rsi
0x18002544d  pop     rbp
0x18002544e  pop     rbx
0x18002544f  retn
0x180025450  mov     r8, rbx
0x180025453  lea     rcx, [r12+rdi*2]
0x180025457  sub     r8, rdi
0x18002545a  mov     rdx, r14
0x18002545d  call    cs:__imp__o__wcsnicmp
0x180025463  xor     ecx, ecx
0x180025465  test    eax, eax
0x180025467  jz      short loc_180025414
0x180025469  inc     rdi
0x18002546c  cmp     rdi, rbx
0x18002546f  jb      short loc_180025450
0x180025471  jmp     short loc_180025414
0x180025473  lea     r8, [r14+rbx*2]
0x180025477  inc     rsi
0x18002547a  cmp     [r8+rsi*2], cx
0x18002547f  jnz     short loc_180025477
0x180025481  mov     eax, [r13+0]
0x180025485  add     rbp, rsi
0x180025488  cmp     rax, rbp
0x18002548b  jb      short loc_18002549E
0x18002548d  mov     rdx, rbp
0x180025490  mov     rcx, r12
0x180025493  call    cs:__imp__o_wcscat_s
0x180025499  mov     r15d, eax
0x18002549c  jmp     short loc_18002542B
0x18002549e  mov     r15d, 0EAh
0x1800254a4  jmp     short loc_18002542B
```
