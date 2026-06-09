# AVrfpFindClosestThunkDuplicate

- ea: `0x180136db8`
- end: `0x180136ecc`
- name: `AVrfpFindClosestThunkDuplicate`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18012281c`

## callees

- `0x180007060`
- `0x180127600`
- `0x180127d10`
- `0x180136db8`

## string_xrefs

- `0x180136e25`: `AVRF: chain: dll: %ws\n`

## pseudocode

```c
__int64 __fastcall AVrfpFindClosestThunkDuplicate(__int64 a1, const wchar_t *a2, const char *a3)
{
  __int64 *i; // rbx
  __int64 v6; // rdi
  unsigned int j; // r14d
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 k; // r15
  const char *v11; // rdx
  __int64 *v13; // [rsp+70h] [rbp+8h]

  for ( i = *(__int64 **)(a1 + 8); i != &AVrfpVerifierProvidersList; i = v13 )
  {
    v13 = (__int64 *)i[1];
    if ( (AVrfpDebug & 0x20) != 0 )
      DbgPrint("AVRF: chain: searching in %ws\n", i[3]);
    v6 = i[5];
    for ( j = 0; ; ++j )
    {
      v8 = 32LL * j;
      if ( !*(_QWORD *)(v8 + v6) )
        break;
      if ( (AVrfpDebug & 0x20) != 0 )
        DbgPrint("AVRF: chain: dll: %ws\n");
      if ( !wcsicmp(*(const wchar_t **)(v8 + v6), a2) )
      {
        v9 = *(_QWORD *)(v8 + v6 + 24);
        for ( k = 0; ; k = (unsigned int)(k + 1) )
        {
          v11 = *(const char **)(v9 + 24 * k);
          if ( !v11 )
            break;
          if ( (AVrfpDebug & 0x20) != 0 )
            DbgPrint("AVRF: chain: thunk: %s == %s ?\n", v11, a3);
          if ( !stricmp(*(const char **)(v9 + 24 * k), a3) )
          {
            if ( (AVrfpDebug & 0x20) != 0 )
              DbgPrint("AVRF: Found duplicate for (%ws: %s) in %ws\n", a2, a3, *(_QWORD *)(v8 + v6));
            return *(_QWORD *)(v9 + 24 * k + 16);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180136db8  push    rbx
0x180136dba  push    rbp
0x180136dbb  push    rsi
0x180136dbc  push    rdi
0x180136dbd  push    r12
0x180136dbf  push    r13
0x180136dc1  push    r14
0x180136dc3  push    r15
0x180136dc5  sub     rsp, 28h
0x180136dc9  mov     rbx, [rcx+8]
0x180136dcd  mov     r12, r8
0x180136dd0  mov     r13, rdx
0x180136dd3  lea     rax, AVrfpVerifierProvidersList
0x180136dda  cmp     rbx, rax
0x180136ddd  jz      loc_180136EB8
0x180136de3  test    byte ptr cs:AVrfpDebug, 20h
0x180136dea  mov     rax, [rbx+8]
0x180136dee  mov     [rsp+68h+arg_0], rax
0x180136df3  jz      short loc_180136E05
0x180136df5  mov     rdx, [rbx+18h]
0x180136df9  lea     rcx, aAvrfChainSearc; "AVRF: chain: searching in %ws\n"
0x180136e00  call    DbgPrint
0x180136e05  mov     rdi, [rbx+28h]
0x180136e09  xor     r14d, r14d
0x180136e0c  mov     ebx, r14d
0x180136e0f  shl     rbx, 5
0x180136e13  mov     rdx, [rbx+rdi]
0x180136e17  test    rdx, rdx
0x180136e1a  jz      short loc_180136E88
0x180136e1c  test    byte ptr cs:AVrfpDebug, 20h
0x180136e23  jz      short loc_180136E31
0x180136e25  lea     rcx, aAvrfChainDllWs; "AVRF: chain: dll: %ws\n"
0x180136e2c  call    DbgPrint
0x180136e31  mov     rcx, [rbx+rdi]; String1
0x180136e35  mov     rdx, r13; String2
0x180136e38  call    _wcsicmp
0x180136e3d  test    eax, eax
0x180136e3f  jnz     short loc_180136E83
0x180136e41  mov     rsi, [rbx+rdi+18h]
0x180136e46  xor     r15d, r15d
0x180136e49  lea     rbp, [r15+r15*2]
0x180136e4d  mov     rdx, [rsi+rbp*8]
0x180136e51  test    rdx, rdx
0x180136e54  jz      short loc_180136E83
0x180136e56  test    byte ptr cs:AVrfpDebug, 20h
0x180136e5d  jz      short loc_180136E6E
0x180136e5f  mov     r8, r12
0x180136e62  lea     rcx, aAvrfChainThunk; "AVRF: chain: thunk: %s == %s ?\n"
0x180136e69  call    DbgPrint
0x180136e6e  mov     rcx, [rsi+rbp*8]; String1
0x180136e72  mov     rdx, r12; String2
0x180136e75  call    _stricmp
0x180136e7a  test    eax, eax
0x180136e7c  jz      short loc_180136E92
0x180136e7e  inc     r15d
0x180136e81  jmp     short loc_180136E49
0x180136e83  inc     r14d
0x180136e86  jmp     short loc_180136E0C
0x180136e88  mov     rbx, [rsp+68h+arg_0]
0x180136e8d  jmp     loc_180136DD3
0x180136e92  test    byte ptr cs:AVrfpDebug, 20h
0x180136e99  jz      short loc_180136EB1
0x180136e9b  mov     r9, [rbx+rdi]
0x180136e9f  lea     rcx, aAvrfFoundDupli; "AVRF: Found duplicate for (%ws: %s) in "...
0x180136ea6  mov     r8, r12
0x180136ea9  mov     rdx, r13
0x180136eac  call    DbgPrint
0x180136eb1  mov     rax, [rsi+rbp*8+10h]
0x180136eb6  jmp     short loc_180136EBA
0x180136eb8  xor     eax, eax
0x180136eba  add     rsp, 28h
0x180136ebe  pop     r15
0x180136ec0  pop     r14
0x180136ec2  pop     r13
0x180136ec4  pop     r12
0x180136ec6  pop     rdi
0x180136ec7  pop     rsi
0x180136ec8  pop     rbp
0x180136ec9  pop     rbx
0x180136eca  retn
```
