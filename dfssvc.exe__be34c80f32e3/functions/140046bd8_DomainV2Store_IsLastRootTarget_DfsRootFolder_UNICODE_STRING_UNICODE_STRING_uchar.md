# DomainV2Store::IsLastRootTarget(DfsRootFolder *,_UNICODE_STRING *,_UNICODE_STRING *,uchar *)

- ea: `0x140046bd8`
- end: `0x140046cf1`
- name: `?IsLastRootTarget@DomainV2Store@@QEAAKPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@1PEAE@Z`
- size: `281`
- prototype: `unsigned int(DomainV2Store *__hidden this, struct DfsRootFolder *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140045dec`

## callees

- `0x140046bd8`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140046c64`
- `ntdll!RtlCompareUnicodeString` at `0x140046c86`
- `ntdll!RtlCompareUnicodeString` at `0x140046c64`
- `ntdll!RtlCompareUnicodeString` at `0x140046c86`

## pseudocode

```c
__int64 __fastcall DomainV2Store::IsLastRootTarget(
        DomainV2Store *this,
        struct DfsRootFolder *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned __int8 *a5)
{
  __int64 v5; // rax
  unsigned __int8 *v7; // rbx
  __int64 (__fastcall *v9)(struct DfsRootFolder *, __int64 *); // rax
  unsigned int v12; // edi
  __int64 v13; // r8
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+78h] [rbp+38h] BYREF

  v5 = *(_QWORD *)a2;
  v7 = a5;
  v16 = 0;
  v15 = 0;
  v9 = *(__int64 (__fastcall **)(struct DfsRootFolder *, __int64 *))(v5 + 56);
  *a5 = 0;
  v12 = v9(a2, &v15);
  if ( !v12 )
  {
    v12 = (*(__int64 (__fastcall **)(DomainV2Store *, __int64, _QWORD, __int64 *))(*(_QWORD *)this + 120LL))(
            this,
            v15,
            0,
            &v16);
    if ( !v12 )
    {
      v13 = v16;
      if ( *(_DWORD *)(v16 + 12) != 1 )
      {
        *v7 = 0;
        goto LABEL_9;
      }
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(v16 + 16) + 32LL), a3, 1u)
        && !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(v16 + 16) + 48LL), a4, 1u) )
      {
        *v7 = 1;
      }
    }
  }
  v13 = v16;
LABEL_9:
  if ( v13 )
  {
    (*(void (__fastcall **)(DomainV2Store *, __int64))(*(_QWORD *)this + 128LL))(this, v15);
    v16 = 0;
  }
  if ( v15 )
    (*(void (__fastcall **)(struct DfsRootFolder *))(*(_QWORD *)a2 + 64LL))(a2);
  return v12;
}

```

## disassembly

```asm
0x140046bd8  mov     [rsp-28h+arg_0], rbx
0x140046bdd  mov     [rsp-28h+arg_10], rsi
0x140046be2  push    rbp
0x140046be3  push    rdi
0x140046be4  push    r12
0x140046be6  push    r14
0x140046be8  push    r15
0x140046bea  mov     rbp, rsp
0x140046bed  sub     rsp, 40h
0x140046bf1  mov     rax, [rdx]
0x140046bf4  mov     r14, rdx
0x140046bf7  mov     rbx, [rbp+arg_20]
0x140046bfb  lea     rdx, [rbp+var_10]
0x140046bff  and     [rbp+arg_8], 0
0x140046c04  mov     rsi, rcx
0x140046c07  and     [rbp+var_10], 0
0x140046c0c  mov     rcx, r14
0x140046c0f  mov     rax, [rax+38h]
0x140046c13  mov     r12, r9
0x140046c16  mov     r15, r8
0x140046c19  mov     byte ptr [rbx], 0
0x140046c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c21  mov     edi, eax
0x140046c23  test    eax, eax
0x140046c25  jnz     short loc_140046C99
0x140046c27  mov     rax, [rsi]
0x140046c2a  lea     r9, [rbp+arg_8]
0x140046c2e  mov     rdx, [rbp+var_10]
0x140046c32  xor     r8d, r8d
0x140046c35  mov     rcx, rsi
0x140046c38  mov     rax, [rax+78h]
0x140046c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c41  mov     edi, eax
0x140046c43  test    eax, eax
0x140046c45  jnz     short loc_140046C99
0x140046c47  mov     r8, [rbp+arg_8]
0x140046c4b  cmp     dword ptr [r8+0Ch], 1
0x140046c50  jz      short loc_140046C56
0x140046c52  mov     [rbx], al
0x140046c54  jmp     short loc_140046C9D
0x140046c56  mov     rcx, [r8+10h]
0x140046c5a  mov     rdx, r15; String2
0x140046c5d  add     rcx, 20h ; ' '; String1
0x140046c61  mov     r8b, 1; CaseInsensitive
0x140046c64  call    cs:__imp_RtlCompareUnicodeString
0x140046c6b  nop     dword ptr [rax+rax+00h]
0x140046c70  test    eax, eax
0x140046c72  jnz     short loc_140046C99
0x140046c74  mov     rax, [rbp+arg_8]
0x140046c78  mov     r8b, 1; CaseInsensitive
0x140046c7b  mov     rdx, r12; String2
0x140046c7e  mov     rcx, [rax+10h]
0x140046c82  add     rcx, 30h ; '0'; String1
0x140046c86  call    cs:__imp_RtlCompareUnicodeString
0x140046c8d  nop     dword ptr [rax+rax+00h]
0x140046c92  test    eax, eax
0x140046c94  jnz     short loc_140046C99
0x140046c96  mov     byte ptr [rbx], 1
0x140046c99  mov     r8, [rbp+arg_8]
0x140046c9d  test    r8, r8
0x140046ca0  jz      short loc_140046CBD
0x140046ca2  mov     rax, [rsi]
0x140046ca5  mov     rcx, rsi
0x140046ca8  mov     rdx, [rbp+var_10]
0x140046cac  mov     rax, [rax+80h]
0x140046cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046cb8  and     [rbp+arg_8], 0
0x140046cbd  mov     rdx, [rbp+var_10]
0x140046cc1  test    rdx, rdx
0x140046cc4  jz      short loc_140046CD5
0x140046cc6  mov     rax, [r14]
0x140046cc9  mov     rcx, r14
0x140046ccc  mov     rax, [rax+40h]
0x140046cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046cd5  lea     r11, [rsp+40h+var_s0]
0x140046cda  mov     eax, edi
0x140046cdc  mov     rbx, [r11+30h]
0x140046ce0  mov     rsi, [r11+40h]
0x140046ce4  mov     rsp, r11
0x140046ce7  pop     r15
0x140046ce9  pop     r14
0x140046ceb  pop     r12
0x140046ced  pop     rdi
0x140046cee  pop     rbp
0x140046cef  retn
```
