# AVrfpDllLoadNotificationInternal

- ea: `0x1800db344`
- end: `0x1800db401`
- name: `AVrfpDllLoadNotificationInternal`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800db268`
- `0x18010f4e0`

## callees

- `0x180007060`
- `0x1800db344`
- `0x1800db408`
- `0x1800db520`
- `0x180127d10`

## string_xrefs

- `0x1800db3b3`: `AVRF: pid 0x%X: found dll descriptor for `%ws' with verified exports \n`

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
0x1800db344  push    rbx
0x1800db346  push    rbp
0x1800db347  push    rsi
0x1800db348  push    rdi
0x1800db349  push    r12
0x1800db34b  push    r14
0x1800db34d  sub     rsp, 28h
0x1800db351  cmp     cs:AVrfpEnabled, 0
0x1800db358  mov     rbp, rcx
0x1800db35b  jz      loc_1800DB3FD
0x1800db361  mov     rbx, cs:AVrfpVerifierProvidersList
0x1800db368  lea     r12, AVrfpVerifierProvidersList
0x1800db36f  cmp     rbx, r12
0x1800db372  jz      short loc_1800DB3E7
0x1800db374  mov     r14, [rbx+28h]
0x1800db378  xor     esi, esi
0x1800db37a  mov     rbx, [rbx]
0x1800db37d  cmp     [r14], rsi
0x1800db380  jz      short loc_1800DB36F
0x1800db382  mov     edi, esi
0x1800db384  shl     rdi, 5
0x1800db388  add     rdi, r14
0x1800db38b  test    byte ptr [rdi+8], 1
0x1800db38f  jnz     short loc_1800DB3D6
0x1800db391  mov     rdx, [rdi]; String2
0x1800db394  mov     rcx, [rbp+60h]; String1
0x1800db398  call    _wcsicmp
0x1800db39d  test    eax, eax
0x1800db39f  jnz     short loc_1800DB3D6
0x1800db3a1  test    byte ptr cs:AVrfpDebug, 4
0x1800db3a8  jz      short loc_1800DB3C3
0x1800db3aa  mov     rdx, gs:40h
0x1800db3b3  lea     rcx, aAvrfPid0xXFoun; "AVRF: pid 0x%X: found dll descriptor fo"...
0x1800db3ba  mov     r8, [rbp+60h]
0x1800db3be  call    DbgPrint
0x1800db3c3  mov     rdx, rbp
0x1800db3c6  mov     rcx, rdi
0x1800db3c9  call    AVrfpDetectVerifiedExports
0x1800db3ce  test    al, al
0x1800db3d0  jz      short loc_1800DB3D6
0x1800db3d2  or      dword ptr [rdi+8], 1
0x1800db3d6  inc     esi
0x1800db3d8  mov     eax, esi
0x1800db3da  shl     rax, 5
0x1800db3de  cmp     qword ptr [rax+r14], 0
0x1800db3e3  jnz     short loc_1800DB382
0x1800db3e5  jmp     short loc_1800DB36F
0x1800db3e7  mov     rcx, rbp
0x1800db3ea  call    AVrfpSnapDllImports
0x1800db3ef  add     rsp, 28h
0x1800db3f3  pop     r14
0x1800db3f5  pop     r12
0x1800db3f7  pop     rdi
0x1800db3f8  pop     rsi
0x1800db3f9  pop     rbp
0x1800db3fa  pop     rbx
0x1800db3fb  retn
0x1800db3fd  xor     eax, eax
0x1800db3ff  jmp     short loc_1800DB3EF
```
