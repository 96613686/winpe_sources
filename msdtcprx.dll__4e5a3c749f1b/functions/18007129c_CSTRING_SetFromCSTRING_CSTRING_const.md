# CSTRING::SetFromCSTRING(CSTRING const &)

- ea: `0x18007129c`
- end: `0x18007137f`
- name: `?SetFromCSTRING@CSTRING@@AEAAXAEBV1@@Z`
- size: `227`
- prototype: `void __fastcall(CSTRING *__hidden this, const struct CSTRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f550`

## callees

- `0x180006054`
- `0x18000c0c0`
- `0x18007129c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800712d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800712d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071305`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800712f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007132e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800712f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007132e`

## pseudocode

```c
void __fastcall CSTRING::SetFromCSTRING(CSTRING *this, const struct CSTRING *a2)
{
  int v4; // r15d
  __int64 v5; // r14
  __int64 v6; // rcx
  void *v7; // rdi
  unsigned __int64 v8; // r12
  unsigned __int16 *v9; // rbp
  const char *v10; // r8

  if ( a2->Buffer )
  {
    v4 = *(_DWORD *)&a2[1].Length;
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(*(_QWORD *)&a2->Length + v6) );
    v7 = CoTaskMemAlloc(v6 + 1);
    if ( !v7 )
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    v8 = v4 + 1;
    v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
    if ( !v9 )
    {
      CoTaskMemFree(v7);
      v7 = 0;
      RaiseException(0xC0000017, 0xC0000025, 0, 0);
    }
    v10 = *(const char **)&a2->Length;
    do
      ++v5;
    while ( v10[v5] );
    StringCchCopyA((char *)v7, v5 + 1, v10);
    StringCchCopyW(v9, v8, (const unsigned __int16 *)a2->Buffer);
  }
  else
  {
    v9 = 0;
    v4 = 0;
    v7 = 0;
  }
  *(_DWORD *)&this[1].Length = v4;
  this->Buffer = (const CHAR *)v9;
  *(_QWORD *)&this->Length = v7;
}

```

## disassembly

```asm
0x18007129c  push    rbx
0x18007129e  push    rbp
0x18007129f  push    rsi
0x1800712a0  push    rdi
0x1800712a1  push    r12
0x1800712a3  push    r14
0x1800712a5  push    r15
0x1800712a7  sub     rsp, 20h
0x1800712ab  cmp     qword ptr [rdx+8], 0
0x1800712b0  mov     rbx, rdx
0x1800712b3  mov     rsi, rcx
0x1800712b6  jz      loc_18007135E
0x1800712bc  mov     r15d, [rdx+10h]
0x1800712c0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800712c4  mov     rax, [rdx]
0x1800712c7  mov     rcx, r14
0x1800712ca  inc     rcx
0x1800712cd  cmp     byte ptr [rax+rcx], 0
0x1800712d1  jnz     short loc_1800712CA
0x1800712d3  inc     rcx; cb
0x1800712d6  call    cs:__imp_CoTaskMemAlloc
0x1800712dc  mov     rdi, rax
0x1800712df  test    rax, rax
0x1800712e2  jnz     short loc_1800712FA
0x1800712e4  xor     r9d, r9d; lpArguments
0x1800712e7  xor     r8d, r8d; nNumberOfArguments
0x1800712ea  mov     edx, 0C0000025h; dwExceptionFlags
0x1800712ef  mov     ecx, 0C0000017h; dwExceptionCode
0x1800712f4  call    cs:__imp_RaiseException
0x1800712fa  lea     r8d, [r15+1]
0x1800712fe  movsxd  r12, r8d
0x180071301  lea     rcx, [r12+r12]; cb
0x180071305  call    cs:__imp_CoTaskMemAlloc
0x18007130b  mov     rbp, rax
0x18007130e  test    rax, rax
0x180071311  jnz     short loc_180071334
0x180071313  mov     rcx, rdi; pv
0x180071316  call    cs:__imp_CoTaskMemFree
0x18007131c  xor     r9d, r9d; lpArguments
0x18007131f  xor     r8d, r8d; nNumberOfArguments
0x180071322  mov     edx, 0C0000025h; dwExceptionFlags
0x180071327  mov     ecx, 0C0000017h; dwExceptionCode
0x18007132c  xor     edi, edi
0x18007132e  call    cs:__imp_RaiseException
0x180071334  mov     r8, [rbx]; char *
0x180071337  inc     r14
0x18007133a  cmp     byte ptr [r8+r14], 0
0x18007133f  jnz     short loc_180071337
0x180071341  lea     rdx, [r14+1]; unsigned __int64
0x180071345  mov     rcx, rdi; char *
0x180071348  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18007134d  mov     r8, [rbx+8]; unsigned __int16 *
0x180071351  mov     rdx, r12; unsigned __int64
0x180071354  mov     rcx, rbp; unsigned __int16 *
0x180071357  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007135c  jmp     short loc_180071365
0x18007135e  xor     ebp, ebp
0x180071360  xor     r15d, r15d
0x180071363  xor     edi, edi
0x180071365  mov     [rsi+10h], r15d
0x180071369  mov     [rsi+8], rbp
0x18007136d  mov     [rsi], rdi
0x180071370  add     rsp, 20h
0x180071374  pop     r15
0x180071376  pop     r14
0x180071378  pop     r12
0x18007137a  pop     rdi
0x18007137b  pop     rsi
0x18007137c  pop     rbp
0x18007137d  pop     rbx
0x18007137e  retn
```
