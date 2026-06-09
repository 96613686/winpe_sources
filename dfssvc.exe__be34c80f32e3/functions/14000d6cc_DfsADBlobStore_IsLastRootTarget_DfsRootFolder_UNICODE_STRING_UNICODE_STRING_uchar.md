# DfsADBlobStore::IsLastRootTarget(DfsRootFolder *,_UNICODE_STRING *,_UNICODE_STRING *,uchar *)

- ea: `0x14000d6cc`
- end: `0x14000d852`
- name: `?IsLastRootTarget@DfsADBlobStore@@QEAAKPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@1PEAE@Z`
- size: `390`
- prototype: `unsigned int(DfsADBlobStore *__hidden this, struct DfsRootFolder *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c214`

## callees

- `0x14000d6cc`
- `0x14000fdb8`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14000d76a`
- `ntdll!RtlCompareUnicodeString` at `0x14000d78c`
- `ntdll!RtlCompareUnicodeString` at `0x14000d76a`
- `ntdll!RtlCompareUnicodeString` at `0x14000d78c`

## pseudocode

```c
__int64 __fastcall DfsADBlobStore::IsLastRootTarget(
        DfsADBlobStore *this,
        struct DfsRootFolder *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned __int8 *a5)
{
  __int64 v5; // rax
  unsigned __int8 *v7; // r14
  __int64 (__fastcall *v9)(struct DfsRootFolder *, __int64 *); // rax
  unsigned int v12; // ebx
  __int64 v13; // r8
  int v14; // r8d
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  v5 = *(_QWORD *)a2;
  v7 = a5;
  v17 = 0;
  v16 = 0;
  v9 = *(__int64 (__fastcall **)(struct DfsRootFolder *, __int64 *))(v5 + 56);
  *a5 = 0;
  v12 = v9(a2, &v16);
  if ( !v12 )
  {
    v12 = (*(__int64 (__fastcall **)(DfsADBlobStore *, __int64, _QWORD, __int64 *))(*(_QWORD *)this + 120LL))(
            this,
            v16,
            0,
            &v17);
    if ( !v12 )
    {
      v13 = v17;
      if ( *(_DWORD *)(v17 + 12) > 1u )
        goto LABEL_16;
      if ( *((_BYTE *)a2 + 216) == 1 )
      {
        if ( RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(v17 + 16) + 32LL), a3, 1u) )
          goto LABEL_8;
        v13 = v17;
      }
      if ( RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(v13 + 16) + 48LL), a4, 1u) )
      {
LABEL_8:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_ZZZZ(
            *((_QWORD *)pWppControl + 2),
            *(_QWORD *)(v17 + 16) + 32,
            v14,
            (_DWORD)a3,
            (__int64)a4,
            *(_QWORD *)(v17 + 16) + 32LL,
            *(_QWORD *)(v17 + 16) + 48LL);
        }
        v12 = 1169;
        goto LABEL_15;
      }
      *v7 = 1;
    }
  }
LABEL_15:
  v13 = v17;
LABEL_16:
  if ( v13 )
  {
    (*(void (__fastcall **)(DfsADBlobStore *, __int64))(*(_QWORD *)this + 128LL))(this, v16);
    v17 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(struct DfsRootFolder *))(*(_QWORD *)a2 + 64LL))(a2);
  return v12;
}

```

## disassembly

```asm
0x14000d6cc  mov     [rsp-28h+arg_0], rbx
0x14000d6d1  mov     [rsp-28h+arg_10], rsi
0x14000d6d6  push    rbp
0x14000d6d7  push    rdi
0x14000d6d8  push    r12
0x14000d6da  push    r14
0x14000d6dc  push    r15
0x14000d6de  mov     rbp, rsp
0x14000d6e1  sub     rsp, 50h
0x14000d6e5  mov     rax, [rdx]
0x14000d6e8  mov     rdi, rdx
0x14000d6eb  mov     r14, [rbp+arg_20]
0x14000d6ef  lea     rdx, [rbp+var_10]
0x14000d6f3  and     [rbp+arg_8], 0
0x14000d6f8  mov     rsi, rcx
0x14000d6fb  and     [rbp+var_10], 0
0x14000d700  mov     rcx, rdi
0x14000d703  mov     rax, [rax+38h]
0x14000d707  mov     r15, r9
0x14000d70a  mov     r12, r8
0x14000d70d  mov     byte ptr [r14], 0
0x14000d711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d716  mov     ebx, eax
0x14000d718  test    eax, eax
0x14000d71a  jnz     loc_14000D7FA
0x14000d720  mov     rax, [rsi]
0x14000d723  lea     r9, [rbp+arg_8]
0x14000d727  mov     rdx, [rbp+var_10]
0x14000d72b  xor     r8d, r8d
0x14000d72e  mov     rcx, rsi
0x14000d731  mov     rax, [rax+78h]
0x14000d735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d73a  mov     ebx, eax
0x14000d73c  test    eax, eax
0x14000d73e  jnz     loc_14000D7FA
0x14000d744  mov     r8, [rbp+arg_8]
0x14000d748  cmp     dword ptr [r8+0Ch], 1
0x14000d74d  ja      loc_14000D7FE
0x14000d753  cmp     byte ptr [rdi+0D8h], 1
0x14000d75a  jnz     short loc_14000D77E
0x14000d75c  mov     rcx, [r8+10h]
0x14000d760  mov     rdx, r12; String2
0x14000d763  add     rcx, 20h ; ' '; String1
0x14000d767  mov     r8b, 1; CaseInsensitive
0x14000d76a  call    cs:__imp_RtlCompareUnicodeString
0x14000d771  nop     dword ptr [rax+rax+00h]
0x14000d776  test    eax, eax
0x14000d778  jnz     short loc_14000D79C
0x14000d77a  mov     r8, [rbp+arg_8]
0x14000d77e  mov     rcx, [r8+10h]
0x14000d782  mov     rdx, r15; String2
0x14000d785  add     rcx, 30h ; '0'; String1
0x14000d789  mov     r8b, 1; CaseInsensitive
0x14000d78c  call    cs:__imp_RtlCompareUnicodeString
0x14000d793  nop     dword ptr [rax+rax+00h]
0x14000d798  test    eax, eax
0x14000d79a  jz      short loc_14000D7F6
0x14000d79c  lea     rax, WPP_GLOBAL_Control
0x14000d7a3  cmp     cs:WPP_GLOBAL_Control, rax
0x14000d7aa  jz      short loc_14000D7EF
0x14000d7ac  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000d7b3  test    rcx, rcx
0x14000d7b6  jz      short loc_14000D7EF
0x14000d7b8  test    byte ptr [rcx+1Ch], 20h
0x14000d7bc  jz      short loc_14000D7EF
0x14000d7be  cmp     byte ptr [rcx+19h], 1
0x14000d7c2  jb      short loc_14000D7EF
0x14000d7c4  mov     rax, [rbp+arg_8]
0x14000d7c8  mov     r9, r12
0x14000d7cb  mov     rcx, [rcx+10h]
0x14000d7cf  mov     rdx, [rax+10h]
0x14000d7d3  lea     rax, [rdx+30h]
0x14000d7d7  add     rdx, 20h ; ' '
0x14000d7db  mov     [rsp+50h+var_20], rax
0x14000d7e0  mov     [rsp+50h+var_28], rdx
0x14000d7e5  mov     [rsp+50h+var_30], r15
0x14000d7ea  call    WPP_SF_ZZZZ
0x14000d7ef  mov     ebx, 491h
0x14000d7f4  jmp     short loc_14000D7FA
0x14000d7f6  mov     byte ptr [r14], 1
0x14000d7fa  mov     r8, [rbp+arg_8]
0x14000d7fe  test    r8, r8
0x14000d801  jz      short loc_14000D81E
0x14000d803  mov     rax, [rsi]
0x14000d806  mov     rcx, rsi
0x14000d809  mov     rdx, [rbp+var_10]
0x14000d80d  mov     rax, [rax+80h]
0x14000d814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d819  and     [rbp+arg_8], 0
0x14000d81e  mov     rdx, [rbp+var_10]
0x14000d822  test    rdx, rdx
0x14000d825  jz      short loc_14000D836
0x14000d827  mov     rax, [rdi]
0x14000d82a  mov     rcx, rdi
0x14000d82d  mov     rax, [rax+40h]
0x14000d831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d836  lea     r11, [rsp+50h+var_s0]
0x14000d83b  mov     eax, ebx
0x14000d83d  mov     rbx, [r11+30h]
0x14000d841  mov     rsi, [r11+40h]
0x14000d845  mov     rsp, r11
0x14000d848  pop     r15
0x14000d84a  pop     r14
0x14000d84c  pop     r12
0x14000d84e  pop     rdi
0x14000d84f  pop     rbp
0x14000d850  retn
```
