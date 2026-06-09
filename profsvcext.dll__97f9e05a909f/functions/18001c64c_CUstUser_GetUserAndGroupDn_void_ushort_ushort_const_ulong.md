# CUstUser::GetUserAndGroupDn(void *,ushort *,ushort * * * const,ulong &)

- ea: `0x18001c64c`
- end: `0x18001c6f3`
- name: `?GetUserAndGroupDn@CUstUser@@SAJPEAXPEAGQEAPEAPEAGAEAK@Z`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpString1, unsigned __int16 ***const, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001b214`

## callees

- `0x18000a8f0`
- `0x18001c64c`
- `0x18001c6fc`
- `0x18001c988`
- `0x18001cdb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6cd`

## pseudocode

```c
__int64 __fastcall CUstUser::GetUserAndGroupDn(
        HANDLE TokenHandle,
        LPCWSTR lpString1,
        unsigned __int16 ***const a3,
        unsigned int *a4)
{
  int GroupSid; // eax
  unsigned __int64 v9; // rdx
  LPCWSTR *v10; // rdi
  int UserSid; // esi
  __int64 i; // rbx
  WCHAR *v13; // rcx
  DWORD cNames; // [rsp+20h] [rbp-48h] BYREF
  LPWSTR *StringSid; // [rsp+28h] [rbp-40h] BYREF

  StringSid = 0;
  cNames = 0;
  GroupSid = CUstUser::_GetGroupSid(TokenHandle, &StringSid, &cNames);
  v10 = (LPCWSTR *)StringSid;
  UserSid = GroupSid;
  if ( GroupSid >= 0 )
  {
    UserSid = CUstUser::_GetUserSid(TokenHandle, lpString1, StringSid);
    if ( UserSid >= 0 )
      UserSid = CUstUser::_GetDistName(v10, cNames, a3, a4);
  }
  if ( v10 )
  {
    for ( i = 0; (unsigned int)i < cNames; i = (unsigned int)(i + 1) )
    {
      v13 = (WCHAR *)v10[i];
      if ( v13 )
        LocalFree(v13);
    }
    operator delete(v10, v9);
  }
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x18001c64c  mov     rax, rsp
0x18001c64f  push    rbx
0x18001c650  push    rsi
0x18001c651  push    rdi
0x18001c652  push    r12
0x18001c654  push    r14
0x18001c656  push    r15
0x18001c658  sub     rsp, 38h
0x18001c65c  mov     r12, r8
0x18001c65f  mov     qword ptr [rax-40h], 0
0x18001c667  mov     r14, rdx
0x18001c66a  mov     dword ptr [rax-48h], 0
0x18001c671  lea     r8, [rax-48h]; unsigned int *
0x18001c675  mov     r15, r9
0x18001c678  lea     rdx, [rax-40h]; unsigned __int16 ***
0x18001c67c  mov     rbx, rcx
0x18001c67f  call    ?_GetGroupSid@CUstUser@@KAJPEAXQEAPEAPEAGAEAK@Z; CUstUser::_GetGroupSid(void *,ushort * * * const,ulong &)
0x18001c684  mov     rdi, [rsp+68h+StringSid]
0x18001c689  mov     esi, eax
0x18001c68b  test    eax, eax
0x18001c68d  js      short loc_18001C6B7
0x18001c68f  mov     r8, rdi; StringSid
0x18001c692  mov     rdx, r14; lpString1
0x18001c695  mov     rcx, rbx; TokenHandle
0x18001c698  call    ?_GetUserSid@CUstUser@@KAJPEAXPEAGPEAPEAG@Z; CUstUser::_GetUserSid(void *,ushort *,ushort * *)
0x18001c69d  mov     esi, eax
0x18001c69f  test    eax, eax
0x18001c6a1  js      short loc_18001C6B7
0x18001c6a3  mov     edx, [rsp+68h+cNames]; cNames
0x18001c6a7  mov     r9, r15; unsigned int *
0x18001c6aa  mov     r8, r12; unsigned __int16 ***
0x18001c6ad  mov     rcx, rdi; rpNames
0x18001c6b0  call    ?_GetDistName@CUstUser@@KAJQEAPEAGKPEAPEAPEAGAEAK@Z; CUstUser::_GetDistName(ushort * * const,ulong,ushort * * *,ulong &)
0x18001c6b5  mov     esi, eax
0x18001c6b7  test    rdi, rdi
0x18001c6ba  jz      short loc_18001C6E3
0x18001c6bc  xor     ebx, ebx
0x18001c6be  cmp     [rsp+68h+cNames], ebx
0x18001c6c2  jbe     short loc_18001C6DB
0x18001c6c4  mov     rcx, [rdi+rbx*8]; hMem
0x18001c6c8  test    rcx, rcx
0x18001c6cb  jz      short loc_18001C6D3
0x18001c6cd  call    cs:__imp_LocalFree
0x18001c6d3  inc     ebx
0x18001c6d5  cmp     ebx, [rsp+68h+cNames]
0x18001c6d9  jb      short loc_18001C6C4
0x18001c6db  mov     rcx, rdi; void *
0x18001c6de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c6e3  mov     eax, esi
0x18001c6e5  add     rsp, 38h
0x18001c6e9  pop     r15
0x18001c6eb  pop     r14
0x18001c6ed  pop     r12
0x18001c6ef  pop     rdi
0x18001c6f0  pop     rsi
0x18001c6f1  pop     rbx
0x18001c6f2  retn
```
