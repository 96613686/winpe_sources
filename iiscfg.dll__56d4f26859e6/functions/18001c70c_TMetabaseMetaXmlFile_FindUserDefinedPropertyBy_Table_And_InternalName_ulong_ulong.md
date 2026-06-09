# TMetabaseMetaXmlFile::FindUserDefinedPropertyBy_Table_And_InternalName(ulong,ulong)

- ea: `0x18001c70c`
- end: `0x18001c80b`
- name: `?FindUserDefinedPropertyBy_Table_And_InternalName@TMetabaseMetaXmlFile@@AEAAKKK@Z`
- size: `255`
- prototype: `unsigned int __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019554`

## callees

- `0x18001c70c`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001c787`
- `msvcrt!_wcsicmp` at `0x18001c7d4`
- `msvcrt!_wcsicmp` at `0x18001c787`
- `msvcrt!_wcsicmp` at `0x18001c7d4`

## pseudocode

```c
__int64 __fastcall TMetabaseMetaXmlFile::FindUserDefinedPropertyBy_Table_And_InternalName(
        TMetabaseMetaXmlFile *this,
        unsigned int a2,
        unsigned int a3)
{
  unsigned int v3; // esi
  __int64 v7; // rax
  __int64 v8; // rbx
  const wchar_t *v9; // rdi
  unsigned int *v10; // rax
  const wchar_t *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  const wchar_t *v14; // rdi
  __int64 v15; // rax
  const wchar_t *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // ecx

  v3 = *((_DWORD *)this + 640);
  while ( ++v3 < (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)this + 264LL))(this) )
  {
    v7 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(this, a2);
    v8 = *(_QWORD *)this;
    v9 = (const wchar_t *)v7;
    v10 = (unsigned int *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 176LL))(
                            this,
                            v3);
    v11 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v8 + 144))(this, *v10);
    if ( !_wcsicmp(v11, v9) )
    {
      v12 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 144LL))(this, a3);
      v13 = *(_QWORD *)this;
      v14 = (const wchar_t *)v12;
      v15 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 176LL))(this, v3);
      v16 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v13 + 144))(
                               this,
                               *(unsigned int *)(v15 + 8));
      if ( !_wcsicmp(v16, v14) )
        break;
    }
  }
  v17 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)this + 264LL))(this);
  v18 = -1;
  if ( v3 < v17 )
    return v3;
  return v18;
}

```

## disassembly

```asm
0x18001c70c  push    rbx
0x18001c70e  push    rbp
0x18001c70f  push    rsi
0x18001c710  push    rdi
0x18001c711  push    r14
0x18001c713  push    r15
0x18001c715  sub     rsp, 28h
0x18001c719  mov     esi, [rcx+0A00h]
0x18001c71f  mov     ebp, r8d
0x18001c722  mov     r15d, edx
0x18001c725  mov     r14, rcx
0x18001c728  mov     rax, [r14]
0x18001c72b  mov     rcx, r14
0x18001c72e  inc     esi
0x18001c730  mov     rax, [rax+108h]
0x18001c737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c73c  cmp     esi, eax
0x18001c73e  jnb     loc_18001C7E2
0x18001c744  mov     rax, [r14]
0x18001c747  mov     edx, r15d
0x18001c74a  mov     rcx, r14
0x18001c74d  mov     rax, [rax+90h]
0x18001c754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c759  mov     rbx, [r14]
0x18001c75c  mov     rdi, rax
0x18001c75f  mov     edx, esi
0x18001c761  mov     rcx, r14
0x18001c764  mov     rax, [rbx+0B0h]
0x18001c76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c770  mov     rcx, r14
0x18001c773  mov     edx, [rax]
0x18001c775  mov     rax, [rbx+90h]
0x18001c77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c781  mov     rdx, rdi; String2
0x18001c784  mov     rcx, rax; String1
0x18001c787  call    cs:__imp__wcsicmp
0x18001c78d  test    eax, eax
0x18001c78f  jnz     short loc_18001C728
0x18001c791  mov     rax, [r14]
0x18001c794  mov     edx, ebp
0x18001c796  mov     rcx, r14
0x18001c799  mov     rax, [rax+90h]
0x18001c7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7a5  mov     rbx, [r14]
0x18001c7a8  mov     rdi, rax
0x18001c7ab  mov     edx, esi
0x18001c7ad  mov     rcx, r14
0x18001c7b0  mov     rax, [rbx+0B0h]
0x18001c7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7bc  mov     rcx, r14
0x18001c7bf  mov     edx, [rax+8]
0x18001c7c2  mov     rax, [rbx+90h]
0x18001c7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7ce  mov     rdx, rdi; String2
0x18001c7d1  mov     rcx, rax; String1
0x18001c7d4  call    cs:__imp__wcsicmp
0x18001c7da  test    eax, eax
0x18001c7dc  jnz     loc_18001C728
0x18001c7e2  mov     rax, [r14]
0x18001c7e5  mov     rcx, r14
0x18001c7e8  mov     rax, [rax+108h]
0x18001c7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f4  or      ecx, 0FFFFFFFFh
0x18001c7f7  cmp     esi, eax
0x18001c7f9  cmovb   ecx, esi
0x18001c7fc  mov     eax, ecx
0x18001c7fe  add     rsp, 28h
0x18001c802  pop     r15
0x18001c804  pop     r14
0x18001c806  pop     rdi
0x18001c807  pop     rsi
0x18001c808  pop     rbp
0x18001c809  pop     rbx
0x18001c80a  retn
```
