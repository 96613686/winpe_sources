# AVrfpFindClosestThunkDuplicate

- ea: `0x1801378a8`
- end: `0x1801379bc`
- name: `AVrfpFindClosestThunkDuplicate`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18012330c`

## callees

- `0x180007060`
- `0x1801280f0`
- `0x180128800`
- `0x1801378a8`

## string_xrefs

- `0x180137915`: `AVRF: chain: dll: %ws\n`

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
0x1801378a8  push    rbx
0x1801378aa  push    rbp
0x1801378ab  push    rsi
0x1801378ac  push    rdi
0x1801378ad  push    r12
0x1801378af  push    r13
0x1801378b1  push    r14
0x1801378b3  push    r15
0x1801378b5  sub     rsp, 28h
0x1801378b9  mov     rbx, [rcx+8]
0x1801378bd  mov     r12, r8
0x1801378c0  mov     r13, rdx
0x1801378c3  lea     rax, AVrfpVerifierProvidersList
0x1801378ca  cmp     rbx, rax
0x1801378cd  jz      loc_1801379A8
0x1801378d3  test    byte ptr cs:AVrfpDebug, 20h
0x1801378da  mov     rax, [rbx+8]
0x1801378de  mov     [rsp+68h+arg_0], rax
0x1801378e3  jz      short loc_1801378F5
0x1801378e5  mov     rdx, [rbx+18h]
0x1801378e9  lea     rcx, aAvrfChainSearc; "AVRF: chain: searching in %ws\n"
0x1801378f0  call    DbgPrint
0x1801378f5  mov     rdi, [rbx+28h]
0x1801378f9  xor     r14d, r14d
0x1801378fc  mov     ebx, r14d
0x1801378ff  shl     rbx, 5
0x180137903  mov     rdx, [rbx+rdi]
0x180137907  test    rdx, rdx
0x18013790a  jz      short loc_180137978
0x18013790c  test    byte ptr cs:AVrfpDebug, 20h
0x180137913  jz      short loc_180137921
0x180137915  lea     rcx, aAvrfChainDllWs; "AVRF: chain: dll: %ws\n"
0x18013791c  call    DbgPrint
0x180137921  mov     rcx, [rbx+rdi]; String1
0x180137925  mov     rdx, r13; String2
0x180137928  call    _wcsicmp
0x18013792d  test    eax, eax
0x18013792f  jnz     short loc_180137973
0x180137931  mov     rsi, [rbx+rdi+18h]
0x180137936  xor     r15d, r15d
0x180137939  lea     rbp, [r15+r15*2]
0x18013793d  mov     rdx, [rsi+rbp*8]
0x180137941  test    rdx, rdx
0x180137944  jz      short loc_180137973
0x180137946  test    byte ptr cs:AVrfpDebug, 20h
0x18013794d  jz      short loc_18013795E
0x18013794f  mov     r8, r12
0x180137952  lea     rcx, aAvrfChainThunk; "AVRF: chain: thunk: %s == %s ?\n"
0x180137959  call    DbgPrint
0x18013795e  mov     rcx, [rsi+rbp*8]; String1
0x180137962  mov     rdx, r12; String2
0x180137965  call    _stricmp
0x18013796a  test    eax, eax
0x18013796c  jz      short loc_180137982
0x18013796e  inc     r15d
0x180137971  jmp     short loc_180137939
0x180137973  inc     r14d
0x180137976  jmp     short loc_1801378FC
0x180137978  mov     rbx, [rsp+68h+arg_0]
0x18013797d  jmp     loc_1801378C3
0x180137982  test    byte ptr cs:AVrfpDebug, 20h
0x180137989  jz      short loc_1801379A1
0x18013798b  mov     r9, [rbx+rdi]
0x18013798f  lea     rcx, aAvrfFoundDupli; "AVRF: Found duplicate for (%ws: %s) in "...
0x180137996  mov     r8, r12
0x180137999  mov     rdx, r13
0x18013799c  call    DbgPrint
0x1801379a1  mov     rax, [rsi+rbp*8+10h]
0x1801379a6  jmp     short loc_1801379AA
0x1801379a8  xor     eax, eax
0x1801379aa  add     rsp, 28h
0x1801379ae  pop     r15
0x1801379b0  pop     r14
0x1801379b2  pop     r13
0x1801379b4  pop     r12
0x1801379b6  pop     rdi
0x1801379b7  pop     rsi
0x1801379b8  pop     rbp
0x1801379b9  pop     rbx
0x1801379ba  retn
```
