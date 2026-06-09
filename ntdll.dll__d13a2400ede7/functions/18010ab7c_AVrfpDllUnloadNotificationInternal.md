# AVrfpDllUnloadNotificationInternal

- ea: `0x18010ab7c`
- end: `0x18010ac30`
- name: `AVrfpDllUnloadNotificationInternal`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1801137b4`

## callees

- `0x180007060`
- `0x18010ab7c`
- `0x18011f1b4`
- `0x180128800`

## string_xrefs

- `0x18010abf6`: `AVRF: pid 0x%X: found dll descriptor for `%ws' with verified exports \n`

## pseudocode

```c
__int64 __fastcall AVrfpDllUnloadNotificationInternal(__int64 a1)
{
  __int64 *v2; // rsi
  _QWORD *v4; // rbx
  unsigned int v5; // ebp
  __int64 v6; // rdi

  if ( AVrfpEnabled )
  {
    v2 = (__int64 *)AVrfpVerifierProvidersList;
    while ( v2 != &AVrfpVerifierProvidersList )
    {
      v4 = (_QWORD *)v2[5];
      v5 = 0;
      v2 = (__int64 *)*v2;
      if ( *v4 )
      {
        do
        {
          v6 = 4LL * v5;
          if ( (v4[v6 + 1] & 1) != 0 && !wcsicmp(*(const wchar_t **)(a1 + 96), (const wchar_t *)v4[v6]) )
          {
            if ( (AVrfpDebug & 4) != 0 )
              DbgPrint(
                "AVRF: pid 0x%X: found dll descriptor for `%ws' with verified exports \n",
                NtCurrentTeb()->ClientId.UniqueProcess,
                *(_QWORD *)(a1 + 96));
            if ( (unsigned __int8)AVrfpClearVerifiedExports(v4[v6 + 3], a1) )
              LODWORD(v4[v6 + 1]) &= ~1u;
          }
          ++v5;
        }
        while ( v4[4 * v5] );
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18010ab7c  push    rbx
0x18010ab7e  push    rbp
0x18010ab7f  push    rsi
0x18010ab80  push    rdi
0x18010ab81  push    r12
0x18010ab83  push    r14
0x18010ab85  sub     rsp, 28h
0x18010ab89  cmp     cs:AVrfpEnabled, 0
0x18010ab90  mov     r14, rcx
0x18010ab93  jz      short loc_18010ABA8
0x18010ab95  mov     rsi, cs:AVrfpVerifierProvidersList
0x18010ab9c  lea     r12, AVrfpVerifierProvidersList
0x18010aba3  cmp     rsi, r12
0x18010aba6  jnz     short loc_18010ABB8
0x18010aba8  xor     eax, eax
0x18010abaa  add     rsp, 28h
0x18010abae  pop     r14
0x18010abb0  pop     r12
0x18010abb2  pop     rdi
0x18010abb3  pop     rsi
0x18010abb4  pop     rbp
0x18010abb5  pop     rbx
0x18010abb6  retn
0x18010abb8  mov     rbx, [rsi+28h]
0x18010abbc  xor     ebp, ebp
0x18010abbe  mov     rsi, [rsi]
0x18010abc1  cmp     [rbx], rbp
0x18010abc4  jz      short loc_18010ABA3
0x18010abc6  mov     edi, ebp
0x18010abc8  shl     rdi, 5
0x18010abcc  test    byte ptr [rdi+rbx+8], 1
0x18010abd1  jz      short loc_18010AC1C
0x18010abd3  mov     rdx, [rdi+rbx]; String2
0x18010abd7  mov     rcx, [r14+60h]; String1
0x18010abdb  call    _wcsicmp
0x18010abe0  test    eax, eax
0x18010abe2  jnz     short loc_18010AC1C
0x18010abe4  test    byte ptr cs:AVrfpDebug, 4
0x18010abeb  jz      short loc_18010AC06
0x18010abed  mov     rdx, gs:40h
0x18010abf6  lea     rcx, aAvrfPid0xXFoun; "AVRF: pid 0x%X: found dll descriptor fo"...
0x18010abfd  mov     r8, [r14+60h]
0x18010ac01  call    DbgPrint
0x18010ac06  mov     rcx, [rdi+rbx+18h]
0x18010ac0b  mov     rdx, r14
0x18010ac0e  call    AVrfpClearVerifiedExports
0x18010ac13  test    al, al
0x18010ac15  jz      short loc_18010AC1C
0x18010ac17  and     dword ptr [rdi+rbx+8], 0FFFFFFFEh
0x18010ac1c  inc     ebp
0x18010ac1e  mov     eax, ebp
0x18010ac20  shl     rax, 5
0x18010ac24  cmp     qword ptr [rax+rbx], 0
0x18010ac29  jnz     short loc_18010ABC6
0x18010ac2b  jmp     loc_18010ABA3
```
