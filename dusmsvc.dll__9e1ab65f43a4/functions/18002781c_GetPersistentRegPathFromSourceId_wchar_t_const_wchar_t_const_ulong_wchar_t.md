# GetPersistentRegPathFromSourceId(wchar_t const *,wchar_t const *,ulong *,wchar_t *)

- ea: `0x18002781c`
- end: `0x18002792a`
- name: `?GetPersistentRegPathFromSourceId@@YAKPEB_W0PEAKPEA_W@Z`
- size: `270`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned int *, wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800276c8`

## callees

- `0x180007c90`
- `0x18002781c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800278a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800278a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800278f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800278f4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180027860`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180027860`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPathFromSourceId(
        const wchar_t *a1,
        const wchar_t *a2,
        unsigned int *a3,
        wchar_t *a4)
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
0x18002781c  push    rbx
0x18002781e  push    rbp
0x18002781f  push    rsi
0x180027820  push    rdi
0x180027821  push    r12
0x180027823  push    r13
0x180027825  push    r14
0x180027827  push    r15
0x180027829  sub     rsp, 48h
0x18002782d  mov     rax, cs:__security_cookie
0x180027834  xor     rax, rsp
0x180027837  mov     [rsp+88h+var_50], rax
0x18002783c  mov     r12, r9
0x18002783f  mov     [rsp+88h+var_58], 0
0x180027847  mov     r9d, [r8]
0x18002784a  lea     rax, [rsp+88h+var_58]
0x18002784f  mov     r13, r8
0x180027852  mov     [rsp+88h+var_68], rax
0x180027857  add     r9d, r9d
0x18002785a  mov     r8, r12
0x18002785d  mov     r14, rdx
0x180027860  call    cs:__imp_GetPersistedRegistryLocationW
0x180027866  mov     ebp, [rsp+88h+var_58]
0x18002786a  xor     ecx, ecx
0x18002786c  shr     rbp, 1
0x18002786f  mov     r15d, eax
0x180027872  test    eax, eax
0x180027874  jnz     loc_180027905
0x18002787a  test    r14, r14
0x18002787d  jz      loc_180027905
0x180027883  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027887  mov     rbx, rsi
0x18002788a  inc     rbx
0x18002788d  cmp     [r12+rbx*2], cx
0x180027892  jnz     short loc_18002788A
0x180027894  mov     rdi, rcx
0x180027897  test    rbx, rbx
0x18002789a  jz      short loc_1800278BD
0x18002789c  mov     r8, rbx
0x18002789f  lea     rcx, [r12+rdi*2]
0x1800278a3  sub     r8, rdi
0x1800278a6  mov     rdx, r14
0x1800278a9  call    cs:__imp__o__wcsnicmp
0x1800278af  xor     ecx, ecx
0x1800278b1  test    eax, eax
0x1800278b3  jz      short loc_1800278BD
0x1800278b5  inc     rdi
0x1800278b8  cmp     rdi, rbx
0x1800278bb  jb      short loc_18002789C
0x1800278bd  sub     rbx, rdi
0x1800278c0  jz      short loc_180027905
0x1800278c2  mov     rax, rsi
0x1800278c5  inc     rax
0x1800278c8  cmp     [r14+rax*2], cx
0x1800278cd  jnz     short loc_1800278C5
0x1800278cf  cmp     rbx, rax
0x1800278d2  jnb     short loc_180027905
0x1800278d4  lea     r8, [r14+rbx*2]
0x1800278d8  inc     rsi
0x1800278db  cmp     [r8+rsi*2], cx
0x1800278e0  jnz     short loc_1800278D8
0x1800278e2  mov     eax, [r13+0]
0x1800278e6  add     rbp, rsi
0x1800278e9  cmp     rax, rbp
0x1800278ec  jb      short loc_1800278FF
0x1800278ee  mov     rdx, rbp
0x1800278f1  mov     rcx, r12
0x1800278f4  call    cs:__imp__o_wcscat_s
0x1800278fa  mov     r15d, eax
0x1800278fd  jmp     short loc_180027905
0x1800278ff  mov     r15d, 0EAh
0x180027905  mov     [r13+0], ebp
0x180027909  mov     eax, r15d
0x18002790c  mov     rcx, [rsp+88h+var_50]
0x180027911  xor     rcx, rsp; StackCookie
0x180027914  call    __security_check_cookie
0x180027919  add     rsp, 48h
0x18002791d  pop     r15
0x18002791f  pop     r14
0x180027921  pop     r13
0x180027923  pop     r12
0x180027925  pop     rdi
0x180027926  pop     rsi
0x180027927  pop     rbp
0x180027928  pop     rbx
0x180027929  retn
```
