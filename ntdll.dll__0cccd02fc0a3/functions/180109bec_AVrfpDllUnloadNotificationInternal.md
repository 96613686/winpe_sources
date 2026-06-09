# AVrfpDllUnloadNotificationInternal

- ea: `0x180109bec`
- end: `0x180109ca0`
- name: `AVrfpDllUnloadNotificationInternal`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1801123c4`

## callees

- `0x180007060`
- `0x180109bec`
- `0x18011e6c4`
- `0x180127d10`

## string_xrefs

- `0x180109c66`: `AVRF: pid 0x%X: found dll descriptor for `%ws' with verified exports \n`

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
0x180109bec  push    rbx
0x180109bee  push    rbp
0x180109bef  push    rsi
0x180109bf0  push    rdi
0x180109bf1  push    r12
0x180109bf3  push    r14
0x180109bf5  sub     rsp, 28h
0x180109bf9  cmp     cs:AVrfpEnabled, 0
0x180109c00  mov     r14, rcx
0x180109c03  jz      short loc_180109C18
0x180109c05  mov     rsi, cs:AVrfpVerifierProvidersList
0x180109c0c  lea     r12, AVrfpVerifierProvidersList
0x180109c13  cmp     rsi, r12
0x180109c16  jnz     short loc_180109C28
0x180109c18  xor     eax, eax
0x180109c1a  add     rsp, 28h
0x180109c1e  pop     r14
0x180109c20  pop     r12
0x180109c22  pop     rdi
0x180109c23  pop     rsi
0x180109c24  pop     rbp
0x180109c25  pop     rbx
0x180109c26  retn
0x180109c28  mov     rbx, [rsi+28h]
0x180109c2c  xor     ebp, ebp
0x180109c2e  mov     rsi, [rsi]
0x180109c31  cmp     [rbx], rbp
0x180109c34  jz      short loc_180109C13
0x180109c36  mov     edi, ebp
0x180109c38  shl     rdi, 5
0x180109c3c  test    byte ptr [rdi+rbx+8], 1
0x180109c41  jz      short loc_180109C8C
0x180109c43  mov     rdx, [rdi+rbx]; String2
0x180109c47  mov     rcx, [r14+60h]; String1
0x180109c4b  call    _wcsicmp
0x180109c50  test    eax, eax
0x180109c52  jnz     short loc_180109C8C
0x180109c54  test    byte ptr cs:AVrfpDebug, 4
0x180109c5b  jz      short loc_180109C76
0x180109c5d  mov     rdx, gs:40h
0x180109c66  lea     rcx, aAvrfPid0xXFoun; "AVRF: pid 0x%X: found dll descriptor fo"...
0x180109c6d  mov     r8, [r14+60h]
0x180109c71  call    DbgPrint
0x180109c76  mov     rcx, [rdi+rbx+18h]
0x180109c7b  mov     rdx, r14
0x180109c7e  call    AVrfpClearVerifiedExports
0x180109c83  test    al, al
0x180109c85  jz      short loc_180109C8C
0x180109c87  and     dword ptr [rdi+rbx+8], 0FFFFFFFEh
0x180109c8c  inc     ebp
0x180109c8e  mov     eax, ebp
0x180109c90  shl     rax, 5
0x180109c94  cmp     qword ptr [rax+rbx], 0
0x180109c99  jnz     short loc_180109C36
0x180109c9b  jmp     loc_180109C13
```
