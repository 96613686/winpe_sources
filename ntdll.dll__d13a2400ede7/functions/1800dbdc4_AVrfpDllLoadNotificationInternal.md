# AVrfpDllLoadNotificationInternal

- ea: `0x1800dbdc4`
- end: `0x1800dbe81`
- name: `AVrfpDllLoadNotificationInternal`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800dbce8`
- `0x180110840`

## callees

- `0x180007060`
- `0x1800dbdc4`
- `0x1800dbe88`
- `0x1800dbfa0`
- `0x180128800`

## string_xrefs

- `0x1800dbe33`: `AVRF: pid 0x%X: found dll descriptor for `%ws' with verified exports \n`

## pseudocode

```c
__int64 __fastcall AVrfpDllLoadNotificationInternal(__int64 a1)
{
  __int64 *v2; // rbx
  _QWORD *v3; // r14
  unsigned int v4; // esi
  _QWORD *v5; // rdi

  if ( !AVrfpEnabled )
    return 0;
  v2 = (__int64 *)AVrfpVerifierProvidersList;
  while ( v2 != &AVrfpVerifierProvidersList )
  {
    v3 = (_QWORD *)v2[5];
    v4 = 0;
    v2 = (__int64 *)*v2;
    if ( *v3 )
    {
      do
      {
        v5 = &v3[4 * v4];
        if ( (v5[1] & 1) == 0 && !wcsicmp(*(const wchar_t **)(a1 + 96), (const wchar_t *)*v5) )
        {
          if ( (AVrfpDebug & 4) != 0 )
            DbgPrint(
              "AVRF: pid 0x%X: found dll descriptor for `%ws' with verified exports \n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              *(_QWORD *)(a1 + 96));
          if ( (unsigned __int8)AVrfpDetectVerifiedExports(&v3[4 * v4], a1) )
            *((_DWORD *)v5 + 2) |= 1u;
        }
        ++v4;
      }
      while ( v3[4 * v4] );
    }
  }
  return AVrfpSnapDllImports(a1);
}

```

## disassembly

```asm
0x1800dbdc4  push    rbx
0x1800dbdc6  push    rbp
0x1800dbdc7  push    rsi
0x1800dbdc8  push    rdi
0x1800dbdc9  push    r12
0x1800dbdcb  push    r14
0x1800dbdcd  sub     rsp, 28h
0x1800dbdd1  cmp     cs:AVrfpEnabled, 0
0x1800dbdd8  mov     rbp, rcx
0x1800dbddb  jz      loc_1800DBE7D
0x1800dbde1  mov     rbx, cs:AVrfpVerifierProvidersList
0x1800dbde8  lea     r12, AVrfpVerifierProvidersList
0x1800dbdef  cmp     rbx, r12
0x1800dbdf2  jz      short loc_1800DBE67
0x1800dbdf4  mov     r14, [rbx+28h]
0x1800dbdf8  xor     esi, esi
0x1800dbdfa  mov     rbx, [rbx]
0x1800dbdfd  cmp     [r14], rsi
0x1800dbe00  jz      short loc_1800DBDEF
0x1800dbe02  mov     edi, esi
0x1800dbe04  shl     rdi, 5
0x1800dbe08  add     rdi, r14
0x1800dbe0b  test    byte ptr [rdi+8], 1
0x1800dbe0f  jnz     short loc_1800DBE56
0x1800dbe11  mov     rdx, [rdi]; String2
0x1800dbe14  mov     rcx, [rbp+60h]; String1
0x1800dbe18  call    _wcsicmp
0x1800dbe1d  test    eax, eax
0x1800dbe1f  jnz     short loc_1800DBE56
0x1800dbe21  test    byte ptr cs:AVrfpDebug, 4
0x1800dbe28  jz      short loc_1800DBE43
0x1800dbe2a  mov     rdx, gs:40h
0x1800dbe33  lea     rcx, aAvrfPid0xXFoun; "AVRF: pid 0x%X: found dll descriptor fo"...
0x1800dbe3a  mov     r8, [rbp+60h]
0x1800dbe3e  call    DbgPrint
0x1800dbe43  mov     rdx, rbp
0x1800dbe46  mov     rcx, rdi
0x1800dbe49  call    AVrfpDetectVerifiedExports
0x1800dbe4e  test    al, al
0x1800dbe50  jz      short loc_1800DBE56
0x1800dbe52  or      dword ptr [rdi+8], 1
0x1800dbe56  inc     esi
0x1800dbe58  mov     eax, esi
0x1800dbe5a  shl     rax, 5
0x1800dbe5e  cmp     qword ptr [rax+r14], 0
0x1800dbe63  jnz     short loc_1800DBE02
0x1800dbe65  jmp     short loc_1800DBDEF
0x1800dbe67  mov     rcx, rbp
0x1800dbe6a  call    AVrfpSnapDllImports
0x1800dbe6f  add     rsp, 28h
0x1800dbe73  pop     r14
0x1800dbe75  pop     r12
0x1800dbe77  pop     rdi
0x1800dbe78  pop     rsi
0x1800dbe79  pop     rbp
0x1800dbe7a  pop     rbx
0x1800dbe7b  retn
0x1800dbe7d  xor     eax, eax
0x1800dbe7f  jmp     short loc_1800DBE6F
```
