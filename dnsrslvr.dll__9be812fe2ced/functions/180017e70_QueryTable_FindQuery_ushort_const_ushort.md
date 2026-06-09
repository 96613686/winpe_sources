# QueryTable::FindQuery(ushort const *,ushort)

- ea: `0x180017e70`
- end: `0x180017f43`
- name: `?FindQuery@QueryTable@@QEAAPEAVQTableNode@@PEBGG@Z`
- size: `211`
- prototype: `struct QTableNode *__fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, __int16)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017860`
- `0x180017d00`
- `0x180018c68`
- `0x180032030`

## callees

- `0x180017e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017e8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017e8f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017ef8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017ef8`

## pseudocode

```c
struct QTableNode *__fastcall QueryTable::FindQuery(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        __int16 a3)
{
  QueryTable *i; // rbx
  __int16 v7; // ax
  const WCHAR *v8; // r8

  EnterCriticalSection(this + 1);
  for ( i = (QueryTable *)this->DebugInfo; i != (QueryTable *)this; i = *(QueryTable **)i )
  {
    v7 = *((_WORD *)i - 16);
    if ( v7 == a3 || v7 == 255 || (v7 == 28 || v7 == 1) && a3 == 47 )
    {
      v8 = (const WCHAR *)*((_QWORD *)i - 5);
      if ( v8 )
      {
        if ( a2 && CompareStringW(0x409u, 1u, v8, -1, a2, -1) == 2 )
        {
LABEL_11:
          LeaveCriticalSection(this + 1);
          return (QueryTable *)((char *)i - 40);
        }
      }
      else if ( !a2 )
      {
        goto LABEL_11;
      }
    }
  }
  LeaveCriticalSection(this + 1);
  return 0;
}

```

## disassembly

```asm
0x180017e70  mov     [rsp+arg_18], rbx
0x180017e75  push    rbp
0x180017e76  push    rsi
0x180017e77  push    r12
0x180017e79  push    r14
0x180017e7b  push    r15
0x180017e7d  sub     rsp, 30h
0x180017e81  mov     rsi, rcx
0x180017e84  movzx   ebp, r8w
0x180017e88  add     rcx, 28h ; '('; lpCriticalSection
0x180017e8c  mov     r15, rdx
0x180017e8f  call    cs:__imp_EnterCriticalSection
0x180017e95  mov     rbx, [rsi]
0x180017e98  mov     r12d, 0FFh
0x180017e9e  mov     [rsp+58h+arg_10], rdi
0x180017ea3  cmp     rbx, rsi
0x180017ea6  jz      loc_180017F35
0x180017eac  movzx   eax, word ptr [rbx-20h]
0x180017eb0  cmp     ax, bp
0x180017eb3  jz      short loc_180017ECD
0x180017eb5  cmp     ax, r12w
0x180017eb9  jz      short loc_180017ECD
0x180017ebb  cmp     ax, 1Ch
0x180017ebf  jz      short loc_180017EC7
0x180017ec1  cmp     ax, 1
0x180017ec5  jnz     short loc_180017F2D
0x180017ec7  cmp     bp, 2Fh ; '/'
0x180017ecb  jnz     short loc_180017F2D
0x180017ecd  mov     r8, [rbx-28h]; lpString1
0x180017ed1  test    r8, r8
0x180017ed4  jz      short loc_180017F28
0x180017ed6  test    r15, r15
0x180017ed9  jz      short loc_180017F2D
0x180017edb  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180017ee3  mov     edx, 1; dwCmpFlags
0x180017ee8  mov     ecx, 409h; Locale
0x180017eed  mov     [rsp+58h+lpString2], r15; lpString2
0x180017ef2  mov     r9d, 0FFFFFFFFh; cchCount1
0x180017ef8  call    cs:__imp_CompareStringW
0x180017efe  cmp     eax, 2
0x180017f01  jnz     short loc_180017F2D
0x180017f03  lea     rcx, [rsi+28h]; lpCriticalSection
0x180017f07  call    cs:__imp_LeaveCriticalSection
0x180017f0d  lea     rax, [rbx-28h]
0x180017f11  mov     rdi, [rsp+58h+arg_10]
0x180017f16  mov     rbx, [rsp+58h+arg_18]
0x180017f1b  add     rsp, 30h
0x180017f1f  pop     r15
0x180017f21  pop     r14
0x180017f23  pop     r12
0x180017f25  pop     rsi
0x180017f26  pop     rbp
0x180017f27  retn
0x180017f28  test    r15, r15
0x180017f2b  jz      short loc_180017F03
0x180017f2d  mov     rbx, [rbx]
0x180017f30  jmp     loc_180017EA3
0x180017f35  lea     rcx, [rsi+28h]; lpCriticalSection
0x180017f39  call    cs:__imp_LeaveCriticalSection
0x180017f3f  xor     eax, eax
0x180017f41  jmp     short loc_180017F11
```
