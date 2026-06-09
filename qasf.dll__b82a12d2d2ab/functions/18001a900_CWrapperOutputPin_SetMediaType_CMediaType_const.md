# CWrapperOutputPin::SetMediaType(CMediaType const *)

- ea: `0x18001a900`
- end: `0x18001aa08`
- name: `?SetMediaType@CWrapperOutputPin@@UEAAJPEBVCMediaType@@@Z`
- size: `264`
- prototype: `int(CWrapperOutputPin *__hidden this, const struct CMediaType *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001a88c`

## callees

- `0x18000724c`
- `0x180016314`
- `0x180018ebc`
- `0x18001a900`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001a91b`
- `KERNEL32!EnterCriticalSection` at `0x18001a91b`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9f5`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9f5`
- `ole32!CoTaskMemFree` at `0x18001a98b`
- `ole32!CoTaskMemFree` at `0x18001a98b`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::SetMediaType(CWrapperOutputPin *this, const struct CMediaType *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  __int64 v5; // rbp
  __int64 v6; // rdx
  struct _AMMediaType *v7; // rax
  struct _AMMediaType *v8; // rbx
  int v9; // ebx
  int v10; // ebp
  __int64 v11; // rax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 264);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  v5 = *((_QWORD *)this + 10);
  v6 = *((unsigned int *)this + 64);
  if ( *(_OWORD *)((char *)a2 + 44) == *(_OWORD *)&FORMAT_VideoInfo2 && !(_DWORD)v6 && *(_DWORD *)(v5 + 444) )
  {
    v7 = ConstructVIH1Type((const struct _AMMediaType *)a2);
    v8 = v7;
    if ( !v7 )
    {
      v9 = -2147467259;
      goto LABEL_13;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *, _QWORD))(**(_QWORD **)(v5 + 160) + 72LL))(
            *(_QWORD *)(v5 + 160),
            0,
            v7,
            0);
    CoTaskMemFree(v8);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, const struct CMediaType *, _QWORD))(**(_QWORD **)(v5 + 160) + 72LL))(
            *(_QWORD *)(v5 + 160),
            v6,
            a2,
            0);
  }
  v9 = TranslateDMOError(v10);
  if ( v9 >= 0 )
  {
    v9 = CMediaType::Set((struct _AMMediaType *)((char *)this + 104), (const struct _AMMediaType *)a2);
    if ( v9 >= 0 )
    {
      v11 = *(_QWORD *)a2 - *(_QWORD *)&MEDIATYPE_Video.Data1;
      if ( *(_QWORD *)a2 == *(_QWORD *)&MEDIATYPE_Video.Data1 )
        v11 = *((_QWORD *)a2 + 1) - *(_QWORD *)MEDIATYPE_Video.Data4;
      v9 = 0;
      *((_BYTE *)this + 422) = v11 == 0;
    }
  }
LABEL_13:
  LeaveCriticalSection(v2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a900  push    rbx
0x18001a902  push    rbp
0x18001a903  push    rsi
0x18001a904  push    rdi
0x18001a905  push    r14
0x18001a907  sub     rsp, 30h
0x18001a90b  lea     r14, [rcx+108h]
0x18001a912  mov     rsi, rcx
0x18001a915  mov     rcx, r14; lpCriticalSection
0x18001a918  mov     rdi, rdx
0x18001a91b  call    cs:__imp_EnterCriticalSection
0x18001a921  mov     rax, [rdi+2Ch]
0x18001a925  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18001a92c  mov     rbp, [rsi+50h]
0x18001a930  mov     edx, [rsi+100h]
0x18001a936  jnz     short loc_18001A993
0x18001a938  mov     rax, [rdi+34h]
0x18001a93c  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18001a943  jnz     short loc_18001A993
0x18001a945  test    edx, edx
0x18001a947  jnz     short loc_18001A993
0x18001a949  cmp     [rbp+1BCh], edx
0x18001a94f  jz      short loc_18001A993
0x18001a951  mov     rcx, rdi; struct _AMMediaType *
0x18001a954  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x18001a959  mov     rbx, rax
0x18001a95c  test    rax, rax
0x18001a95f  jnz     short loc_18001A96B
0x18001a961  mov     ebx, 80004005h
0x18001a966  jmp     loc_18001A9F2
0x18001a96b  mov     rcx, [rbp+0A0h]
0x18001a972  xor     r9d, r9d
0x18001a975  mov     r8, rbx
0x18001a978  xor     edx, edx
0x18001a97a  mov     rax, [rcx]
0x18001a97d  mov     rax, [rax+48h]
0x18001a981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a986  mov     rcx, rbx; pv
0x18001a989  mov     ebp, eax
0x18001a98b  call    cs:__imp_CoTaskMemFree
0x18001a991  jmp     short loc_18001A9AE
0x18001a993  mov     rcx, [rbp+0A0h]
0x18001a99a  xor     r9d, r9d
0x18001a99d  mov     r8, rdi
0x18001a9a0  mov     rax, [rcx]
0x18001a9a3  mov     rax, [rax+48h]
0x18001a9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ac  mov     ebp, eax
0x18001a9ae  mov     ecx, ebp; int
0x18001a9b0  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x18001a9b5  mov     ebx, eax
0x18001a9b7  test    eax, eax
0x18001a9b9  js      short loc_18001A9F2
0x18001a9bb  lea     rcx, [rsi+68h]; this
0x18001a9bf  mov     rdx, rdi; struct _AMMediaType *
0x18001a9c2  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18001a9c7  mov     ebx, eax
0x18001a9c9  test    eax, eax
0x18001a9cb  js      short loc_18001A9F2
0x18001a9cd  mov     rax, [rdi]
0x18001a9d0  sub     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x18001a9d7  jnz     short loc_18001A9E4
0x18001a9d9  mov     rax, [rdi+8]
0x18001a9dd  sub     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x18001a9e4  test    rax, rax
0x18001a9e7  setz    al
0x18001a9ea  xor     ebx, ebx
0x18001a9ec  mov     [rsi+1A6h], al
0x18001a9f2  mov     rcx, r14; lpCriticalSection
0x18001a9f5  call    cs:__imp_LeaveCriticalSection
0x18001a9fb  mov     eax, ebx
0x18001a9fd  add     rsp, 30h
0x18001aa01  pop     r14
0x18001aa03  pop     rdi
0x18001aa04  pop     rsi
0x18001aa05  pop     rbp
0x18001aa06  pop     rbx
0x18001aa07  retn
```
