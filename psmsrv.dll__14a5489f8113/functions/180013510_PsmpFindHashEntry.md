# PsmpFindHashEntry

- ea: `0x180013510`
- end: `0x180013605`
- name: `PsmpFindHashEntry`
- size: `245`
- prototype: `signed __int32 *__fastcall(_QWORD **, __int64, WCHAR *, unsigned __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d0f8`

## callees

- `0x180013510`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800135e8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800135e8`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18001354a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18001354a`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800135b1`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800135b1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180013577`
- `ntdll!RtlAcquireSRWLockShared` at `0x180013577`

## pseudocode

```c
signed __int32 *__fastcall PsmpFindHashEntry(_QWORD **a1, __int64 a2, WCHAR *a3, unsigned __int64 a4, _DWORD *a5)
{
  _QWORD **v8; // r14
  int v9; // esi
  WCHAR *v10; // rbx
  WCHAR v11; // di
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  _QWORD *i; // rdi
  signed __int32 *v17; // rsi
  signed __int32 v18; // eax
  signed __int32 v19; // ecx
  char v20; // al
  int v22; // [rsp+20h] [rbp-48h]

  v8 = a1;
  if ( !a1 )
  {
    v9 = 0;
    v10 = a3;
    do
    {
      v11 = *v10++;
      v12 = 37 * v9 + RtlUpcaseUnicodeChar(v11);
      v9 = v12;
    }
    while ( v11 );
    a4 = (char *)v10 - (char *)a3;
    v8 = (_QWORD **)(a2 + 8 + 24LL * (v12 & 0x7F));
  }
  RtlAcquireSRWLockShared(v8 + 2);
  for ( i = *v8; i != v8; i = (_QWORD *)*i )
  {
    v17 = (signed __int32 *)(i - 3);
    if ( a4 == *(i - 1) )
    {
      LOBYTE(v22) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v17 + 1), a4 >> 1, a3, a4 >> 1, v22) )
      {
        _m_prefetchw(v17);
        v18 = *v17;
        while ( 1 )
        {
          v13 = (unsigned int)(v18 + 1);
          if ( v18 <= 0 )
            break;
          v19 = v18;
          v18 = _InterlockedCompareExchange(v17, v13, v18);
          if ( v18 == v19 )
          {
            v20 = 1;
            goto LABEL_14;
          }
        }
        v20 = 0;
LABEL_14:
        if ( a5 )
          *a5 = v13;
        if ( v20 )
          goto LABEL_20;
      }
    }
  }
  v17 = 0;
LABEL_20:
  RtlReleaseSRWLockShared(v8 + 2, v13, v14, v15);
  return v17;
}

```

## disassembly

```asm
0x180013510  push    rbx
0x180013512  push    rbp
0x180013513  push    rsi
0x180013514  push    rdi
0x180013515  push    r12
0x180013517  push    r14
0x180013519  push    r15
0x18001351b  sub     rsp, 30h
0x18001351f  mov     rbx, r9
0x180013522  mov     r12, r8
0x180013525  mov     rbp, rdx
0x180013528  mov     r14, rcx
0x18001352b  test    rcx, rcx
0x18001352e  jnz     short loc_180013573
0x180013530  xor     esi, esi
0x180013532  mov     rbx, r8
0x180013535  nop     word ptr [rax+rax+00000000h]
0x180013540  movzx   edi, word ptr [rbx]
0x180013543  add     rbx, 2
0x180013547  movzx   ecx, di; Source
0x18001354a  call    cs:__imp_RtlUpcaseUnicodeChar
0x180013550  movzx   ecx, ax
0x180013553  imul    eax, esi, 25h ; '%'
0x180013556  add     ecx, eax
0x180013558  mov     esi, ecx
0x18001355a  test    di, di
0x18001355d  jnz     short loc_180013540
0x18001355f  mov     eax, ecx
0x180013561  lea     r14, [rbp+8]
0x180013565  sub     rbx, r12
0x180013568  and     eax, 7Fh
0x18001356b  lea     rax, [rax+rax*2]
0x18001356f  lea     r14, [r14+rax*8]
0x180013573  lea     rcx, [r14+10h]
0x180013577  call    cs:__imp_RtlAcquireSRWLockShared
0x18001357d  mov     rdi, [r14]
0x180013580  mov     r15, [rsp+68h+arg_20]
0x180013588  cmp     rdi, r14
0x18001358b  jz      short loc_1800135E2
0x18001358d  cmp     rbx, [rdi-8]
0x180013591  lea     rsi, [rdi-18h]
0x180013595  jz      short loc_18001359C
0x180013597  mov     rdi, [rdi]
0x18001359a  jmp     short loc_180013588
0x18001359c  mov     rcx, [rsi+8]
0x1800135a0  mov     rdx, rbx
0x1800135a3  shr     rdx, 1
0x1800135a6  mov     r8, r12
0x1800135a9  mov     r9, rdx
0x1800135ac  mov     byte ptr [rsp+68h+var_48], 1
0x1800135b1  call    cs:__imp_RtlCompareUnicodeStrings
0x1800135b7  test    eax, eax
0x1800135b9  jnz     short loc_180013597
0x1800135bb  prefetchw byte ptr [rsi]
0x1800135be  mov     eax, [rsi]
0x1800135c0  lea     edx, [rax+1]
0x1800135c3  test    eax, eax
0x1800135c5  jle     short loc_1800135DE
0x1800135c7  mov     ecx, eax
0x1800135c9  lock cmpxchg [rsi], edx
0x1800135cd  cmp     eax, ecx
0x1800135cf  jnz     short loc_1800135C0
0x1800135d1  mov     al, 1
0x1800135d3  test    r15, r15
0x1800135d6  jnz     short loc_180013600
0x1800135d8  test    al, al
0x1800135da  jz      short loc_180013597
0x1800135dc  jmp     short loc_1800135E4
0x1800135de  xor     al, al
0x1800135e0  jmp     short loc_1800135D3
0x1800135e2  xor     esi, esi
0x1800135e4  lea     rcx, [r14+10h]
0x1800135e8  call    cs:__imp_RtlReleaseSRWLockShared
0x1800135ee  mov     rax, rsi
0x1800135f1  add     rsp, 30h
0x1800135f5  pop     r15
0x1800135f7  pop     r14
0x1800135f9  pop     r12
0x1800135fb  pop     rdi
0x1800135fc  pop     rsi
0x1800135fd  pop     rbp
0x1800135fe  pop     rbx
0x1800135ff  retn
0x180013600  mov     [r15], edx
0x180013603  jmp     short loc_1800135D8
```
