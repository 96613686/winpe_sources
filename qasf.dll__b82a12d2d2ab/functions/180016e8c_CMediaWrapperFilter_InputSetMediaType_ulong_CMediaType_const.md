# CMediaWrapperFilter::InputSetMediaType(ulong,CMediaType const *)

- ea: `0x180016e8c`
- end: `0x180016f76`
- name: `?InputSetMediaType@CMediaWrapperFilter@@QEAAJKPEBVCMediaType@@@Z`
- size: `234`
- prototype: `int(CMediaWrapperFilter *__hidden this, unsigned int, const struct CMediaType *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001588c`
- `0x18001bda0`

## callees

- `0x18000724c`
- `0x180016314`
- `0x180016e8c`
- `0x180018ebc`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180016f33`
- `ole32!CoTaskMemFree` at `0x180016f33`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::InputSetMediaType(
        CMediaWrapperFilter *this,
        __int64 a2,
        const struct CMediaType *a3)
{
  __int64 v4; // r14
  int v6; // eax
  __int64 result; // rax
  struct _AMMediaType *v8; // rax
  struct _AMMediaType *v9; // rsi
  int v10; // eax
  int v11; // ebp
  int v12; // eax
  unsigned int v13; // ecx

  v4 = (unsigned int)a2;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, const struct CMediaType *, _QWORD))(**((_QWORD **)this + 20) + 64LL))(
         *((_QWORD *)this + 20),
         a2,
         a3,
         0);
  result = TranslateDMOError(v6);
  if ( (int)result < 0 )
  {
    if ( *(_QWORD *)((char *)a3 + 44) != *(_QWORD *)&FORMAT_VideoInfo2.Data1
      || *(_QWORD *)((char *)a3 + 52) != *(_QWORD *)FORMAT_VideoInfo2.Data4
      || !*((_DWORD *)this + 110)
      || (_DWORD)v4 )
    {
      return result;
    }
    v8 = ConstructVIH1Type((const struct _AMMediaType *)a3);
    v9 = v8;
    if ( !v8 )
      return 2147500037LL;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *, _QWORD))(**((_QWORD **)this + 20) + 64LL))(
            *((_QWORD *)this + 20),
            0,
            v8,
            0);
    v11 = TranslateDMOError(v10);
    CoTaskMemFree(v9);
    if ( v11 < 0 )
      return (unsigned int)v11;
    *((_DWORD *)this + 111) = 1;
  }
  v12 = CMediaType::Set(
          (struct _AMMediaType *)(*(_QWORD *)(*((_QWORD *)this + 17) + 8 * v4) + 104LL),
          (const struct _AMMediaType *)a3);
  v13 = 0;
  if ( v12 < 0 )
    return (unsigned int)v12;
  return v13;
}

```

## disassembly

```asm
0x180016e8c  push    rbx
0x180016e8e  push    rbp
0x180016e8f  push    rsi
0x180016e90  push    rdi
0x180016e91  push    r14
0x180016e93  sub     rsp, 30h
0x180016e97  mov     rdi, rcx
0x180016e9a  mov     r14d, edx
0x180016e9d  mov     rcx, [rcx+0A0h]
0x180016ea4  xor     r9d, r9d
0x180016ea7  mov     rbx, r8
0x180016eaa  mov     rax, [rcx]
0x180016ead  mov     rax, [rax+40h]
0x180016eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eb6  mov     ecx, eax; int
0x180016eb8  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180016ebd  test    eax, eax
0x180016ebf  jns     loc_180016F4B
0x180016ec5  mov     rcx, [rbx+2Ch]
0x180016ec9  cmp     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180016ed0  jnz     loc_180016F6B
0x180016ed6  mov     rcx, [rbx+34h]
0x180016eda  cmp     rcx, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180016ee1  jnz     loc_180016F6B
0x180016ee7  cmp     dword ptr [rdi+1B8h], 0
0x180016eee  jz      short loc_180016F6B
0x180016ef0  test    r14d, r14d
0x180016ef3  jnz     short loc_180016F6B
0x180016ef5  mov     rcx, rbx; struct _AMMediaType *
0x180016ef8  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x180016efd  mov     rsi, rax
0x180016f00  test    rax, rax
0x180016f03  jnz     short loc_180016F0C
0x180016f05  mov     eax, 80004005h
0x180016f0a  jmp     short loc_180016F6B
0x180016f0c  mov     rcx, [rdi+0A0h]
0x180016f13  xor     r9d, r9d
0x180016f16  mov     r8, rsi
0x180016f19  xor     edx, edx
0x180016f1b  mov     rax, [rcx]
0x180016f1e  mov     rax, [rax+40h]
0x180016f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f27  mov     ecx, eax; int
0x180016f29  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180016f2e  mov     rcx, rsi; pv
0x180016f31  mov     ebp, eax
0x180016f33  call    cs:__imp_CoTaskMemFree
0x180016f39  test    ebp, ebp
0x180016f3b  jns     short loc_180016F41
0x180016f3d  mov     eax, ebp
0x180016f3f  jmp     short loc_180016F6B
0x180016f41  mov     dword ptr [rdi+1BCh], 1
0x180016f4b  mov     rax, [rdi+88h]
0x180016f52  mov     rdx, rbx; struct _AMMediaType *
0x180016f55  mov     rcx, [rax+r14*8]
0x180016f59  add     rcx, 68h ; 'h'; this
0x180016f5d  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180016f62  xor     ecx, ecx
0x180016f64  test    eax, eax
0x180016f66  cmovs   ecx, eax
0x180016f69  mov     eax, ecx
0x180016f6b  add     rsp, 30h
0x180016f6f  pop     r14
0x180016f71  pop     rdi
0x180016f72  pop     rsi
0x180016f73  pop     rbp
0x180016f74  pop     rbx
0x180016f75  retn
```
