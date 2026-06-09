# CMediaWrapperFilter::InputCheckMediaType(ulong,_AMMediaType const *)

- ea: `0x180016dd4`
- end: `0x180016e84`
- name: `?InputCheckMediaType@CMediaWrapperFilter@@QEAAJKPEBU_AMMediaType@@@Z`
- size: `176`
- prototype: `int(CMediaWrapperFilter *__hidden this, unsigned int, const struct _AMMediaType *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001588c`
- `0x18001b3e0`

## callees

- `0x180016314`
- `0x180016dd4`
- `0x180018ebc`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180016e73`
- `ole32!CoTaskMemFree` at `0x180016e73`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::InputCheckMediaType(
        CMediaWrapperFilter *this,
        __int64 a2,
        const struct _AMMediaType *a3)
{
  int v5; // ebp
  int v6; // eax
  int v7; // edi
  struct _AMMediaType *v8; // rax
  struct _AMMediaType *v9; // rbx
  int v11; // eax

  v5 = a2;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, const struct _AMMediaType *, __int64))(**((_QWORD **)this + 20) + 64LL))(
         *((_QWORD *)this + 20),
         a2,
         a3,
         1);
  v7 = TranslateDMOError(v6);
  if ( v7 < 0
    && *(_QWORD *)&a3->formattype.Data1 == *(_QWORD *)&FORMAT_VideoInfo2.Data1
    && *(_QWORD *)a3->formattype.Data4 == *(_QWORD *)FORMAT_VideoInfo2.Data4
    && *((_DWORD *)this + 110)
    && !v5 )
  {
    v8 = ConstructVIH1Type(a3);
    v9 = v8;
    if ( !v8 )
      return 2147500037LL;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *, __int64))(**((_QWORD **)this + 20) + 64LL))(
            *((_QWORD *)this + 20),
            0,
            v8,
            1);
    v7 = TranslateDMOError(v11);
    CoTaskMemFree(v9);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016dd4  push    rbx
0x180016dd6  push    rbp
0x180016dd7  push    rsi
0x180016dd8  push    rdi
0x180016dd9  sub     rsp, 38h
0x180016ddd  mov     rsi, rcx
0x180016de0  mov     r9d, 1
0x180016de6  mov     rcx, [rcx+0A0h]
0x180016ded  mov     rbx, r8
0x180016df0  mov     ebp, edx
0x180016df2  mov     rax, [rcx]
0x180016df5  mov     rax, [rax+40h]
0x180016df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dfe  mov     ecx, eax; int
0x180016e00  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180016e05  mov     edi, eax
0x180016e07  test    eax, eax
0x180016e09  jns     short loc_180016E79
0x180016e0b  mov     rax, [rbx+2Ch]
0x180016e0f  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180016e16  jnz     short loc_180016E79
0x180016e18  mov     rax, [rbx+34h]
0x180016e1c  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180016e23  jnz     short loc_180016E79
0x180016e25  cmp     dword ptr [rsi+1B8h], 0
0x180016e2c  jz      short loc_180016E79
0x180016e2e  test    ebp, ebp
0x180016e30  jnz     short loc_180016E79
0x180016e32  mov     rcx, rbx; struct _AMMediaType *
0x180016e35  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x180016e3a  mov     rbx, rax
0x180016e3d  test    rax, rax
0x180016e40  jnz     short loc_180016E49
0x180016e42  mov     eax, 80004005h
0x180016e47  jmp     short loc_180016E7B
0x180016e49  mov     rcx, [rsi+0A0h]
0x180016e50  mov     r9d, 1
0x180016e56  mov     r8, rbx
0x180016e59  xor     edx, edx
0x180016e5b  mov     rax, [rcx]
0x180016e5e  mov     rax, [rax+40h]
0x180016e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e67  mov     ecx, eax; int
0x180016e69  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180016e6e  mov     rcx, rbx; pv
0x180016e71  mov     edi, eax
0x180016e73  call    cs:__imp_CoTaskMemFree
0x180016e79  mov     eax, edi
0x180016e7b  add     rsp, 38h
0x180016e7f  pop     rdi
0x180016e80  pop     rsi
0x180016e81  pop     rbp
0x180016e82  pop     rbx
0x180016e83  retn
```
