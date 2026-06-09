# IdToken::GetJwtPayload(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x14000e8cc`
- end: `0x14000ea05`
- name: `?GetJwtPayload@IdToken@@AEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z`
- size: `313`
- prototype: `__int64 __fastcall(__int64, const wchar_t **, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000e328`

## callees

- `0x140007bf8`
- `0x140008ce8`
- `0x14000e684`
- `0x14000e8cc`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000e8f7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000e92f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000e96b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000e8f7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000e92f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000e96b`

## pseudocode

```c
__int64 __fastcall IdToken::GetJwtPayload(__int64 a1, const wchar_t **a2, _QWORD *a3)
{
  wchar_t *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // ebp
  wchar_t *v8; // rax
  __int64 v9; // rdi
  int v10; // eax
  wchar_t *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rdx
  __int64 result; // rax
  _OWORD pExceptionObject[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+70h] [rbp+8h] BYREF

  v16 = a1;
  if ( *((int *)*a2 - 4) >= 0 && (v5 = wcsstr(*a2, L".")) != 0 )
  {
    v6 = v5 - *a2;
    v7 = v6 + 1;
    if ( (int)v6 + 1 < 0 )
      goto LABEL_11;
  }
  else
  {
    LODWORD(v6) = -1;
    v7 = 0;
  }
  if ( (signed int)v7 <= *((_DWORD *)*a2 - 4) )
  {
    v8 = wcsstr(&(*a2)[v7], L".");
    if ( v8 )
      v9 = v8 - *a2;
    else
      LODWORD(v9) = -1;
    v10 = v9 + 1;
    if ( (int)v9 + 1 < 0 )
      goto LABEL_15;
    goto LABEL_12;
  }
LABEL_11:
  LODWORD(v9) = -1;
  v10 = 0;
LABEL_12:
  if ( v10 <= *((_DWORD *)*a2 - 4) )
  {
    v11 = wcsstr(&(*a2)[v10], L".");
    if ( v11 )
    {
      if ( (unsigned int)(v11 - *a2) != -1 )
      {
LABEL_20:
        pExceptionObject[0] = 0;
        IdToken::IdTokenParseException::IdTokenParseException((IdToken::IdTokenParseException *)pExceptionObject);
        throw (IdToken::IdTokenParseException *)pExceptionObject;
      }
    }
  }
LABEL_15:
  if ( (int)v6 <= 0 || (int)v9 <= 0 )
    goto LABEL_20;
  v12 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                    a2,
                    &v16,
                    v7,
                    (unsigned int)(v9 - v6 - 1));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a3, v12);
  v13 = (_QWORD *)(v16 - 24);
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16));
  if ( (int)result <= 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
  return result;
}

```

## disassembly

```asm
0x14000e8cc  mov     [rsp+arg_0], rcx
0x14000e8d1  push    rbx
0x14000e8d2  push    rbp
0x14000e8d3  push    rsi
0x14000e8d4  push    rdi
0x14000e8d5  push    r14
0x14000e8d7  push    r15
0x14000e8d9  sub     rsp, 38h
0x14000e8dd  mov     r14, r8
0x14000e8e0  mov     rsi, rdx
0x14000e8e3  mov     rcx, [rdx]; Str
0x14000e8e6  or      r15d, 0FFFFFFFFh
0x14000e8ea  cmp     dword ptr [rcx-10h], 0
0x14000e8ee  jl      short loc_14000E905
0x14000e8f0  lea     rdx, SubStr; "."
0x14000e8f7  call    cs:__imp_wcsstr
0x14000e8fd  mov     rbx, rax
0x14000e900  test    rax, rax
0x14000e903  jnz     short loc_14000E90C
0x14000e905  mov     ebx, r15d
0x14000e908  xor     ebp, ebp
0x14000e90a  jmp     short loc_14000E919
0x14000e90c  sub     rbx, [rsi]
0x14000e90f  sar     rbx, 1
0x14000e912  lea     ebp, [rbx+1]
0x14000e915  test    ebp, ebp
0x14000e917  js      short loc_14000E951
0x14000e919  mov     rcx, [rsi]
0x14000e91c  cmp     ebp, [rcx-10h]
0x14000e91f  jg      short loc_14000E951
0x14000e921  movsxd  rax, ebp
0x14000e924  lea     rcx, [rcx+rax*2]; Str
0x14000e928  lea     rdx, SubStr; "."
0x14000e92f  call    cs:__imp_wcsstr
0x14000e935  mov     rdi, rax
0x14000e938  test    rax, rax
0x14000e93b  jnz     short loc_14000E942
0x14000e93d  mov     edi, r15d
0x14000e940  jmp     short loc_14000E948
0x14000e942  sub     rdi, [rsi]
0x14000e945  sar     rdi, 1
0x14000e948  lea     eax, [rdi+1]
0x14000e94b  test    eax, eax
0x14000e94d  js      short loc_14000E982
0x14000e94f  jmp     short loc_14000E956
0x14000e951  mov     edi, r15d
0x14000e954  xor     eax, eax
0x14000e956  mov     rcx, [rsi]
0x14000e959  cmp     eax, [rcx-10h]
0x14000e95c  jg      short loc_14000E982
0x14000e95e  cdqe
0x14000e960  lea     rcx, [rcx+rax*2]; Str
0x14000e964  lea     rdx, SubStr; "."
0x14000e96b  call    cs:__imp_wcsstr
0x14000e971  nop
0x14000e972  test    rax, rax
0x14000e975  jz      short loc_14000E982
0x14000e977  sub     rax, [rsi]
0x14000e97a  sar     rax, 1
0x14000e97d  cmp     eax, r15d
0x14000e980  jnz     short loc_14000E9E1
0x14000e982  test    ebx, ebx
0x14000e984  jle     short loc_14000E9E1
0x14000e986  test    edi, edi
0x14000e988  jle     short loc_14000E9E1
0x14000e98a  sub     edi, ebx
0x14000e98c  lea     r9d, [rdi-1]
0x14000e990  mov     r8d, ebp
0x14000e993  lea     rdx, [rsp+68h+arg_0]
0x14000e998  mov     rcx, rsi
0x14000e99b  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x14000e9a0  nop
0x14000e9a1  mov     rdx, rax
0x14000e9a4  mov     rcx, r14
0x14000e9a7  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000e9ac  nop
0x14000e9ad  mov     rdx, [rsp+68h+arg_0]
0x14000e9b2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e9b6  mov     eax, r15d
0x14000e9b9  lock xadd [rdx+10h], eax
0x14000e9be  add     eax, r15d
0x14000e9c1  test    eax, eax
0x14000e9c3  jg      short loc_14000E9D4
0x14000e9c5  mov     rcx, [rdx]
0x14000e9c8  mov     rax, [rcx]
0x14000e9cb  mov     rax, [rax+8]
0x14000e9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9d4  add     rsp, 38h
0x14000e9d8  pop     r15
0x14000e9da  pop     r14
0x14000e9dc  pop     rdi
0x14000e9dd  pop     rsi
0x14000e9de  pop     rbp
0x14000e9df  pop     rbx
0x14000e9e0  retn
0x14000e9e1  xorps   xmm0, xmm0
0x14000e9e4  movups  [rsp+68h+pExceptionObject], xmm0
0x14000e9e9  lea     rcx, [rsp+68h+pExceptionObject]; this
0x14000e9ee  call    ??0IdTokenParseException@IdToken@@QEAA@XZ; IdToken::IdTokenParseException::IdTokenParseException(void)
0x14000e9f3  lea     rdx, _TI2?AVIdTokenParseException@IdToken@@; pThrowInfo
0x14000e9fa  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14000e9ff  call    _CxxThrowException_0
```
