# CAutoImpersonate::ImpersonateUser(void *)

- ea: `0x180013aac`
- end: `0x180013aec`
- name: `?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z`
- size: `64`
- prototype: `__int64 __fastcall(CAutoImpersonate *__hidden this, void *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180007468`
- `0x180008258`
- `0x180009c68`
- `0x180011880`
- `0x180012314`
- `0x180016158`

## callees

- `0x18000927c`
- `0x180013aac`
- `0x18001d748`

## pseudocode

```c
__int64 __fastcall CAutoImpersonate::ImpersonateUser(CAutoImpersonate *this, void *a2)
{
  __int64 result; // rax

  result = 2147500037LL;
  if ( a2 )
  {
    CAutoImpersonate::ResetImpersonation(this);
    result = ImpersonateUser(a2, (void **)this);
    *((_BYTE *)this + 8) = (int)result >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013aac  mov     [rsp+arg_0], rbx
0x180013ab1  push    rdi
0x180013ab2  sub     rsp, 20h
0x180013ab6  mov     rbx, rdx
0x180013ab9  mov     rdi, rcx
0x180013abc  mov     eax, 80004005h
0x180013ac1  test    rdx, rdx
0x180013ac4  jz      short loc_180013AE1
0x180013ac6  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180013acb  mov     rdx, rdi; void **
0x180013ace  mov     rcx, rbx; hToken
0x180013ad1  call    ?ImpersonateUser@@YAJPEAXPEAPEAX@Z; ImpersonateUser(void *,void * *)
0x180013ad6  mov     edx, eax
0x180013ad8  shr     edx, 1Fh
0x180013adb  xor     dl, 1
0x180013ade  mov     [rdi+8], dl
0x180013ae1  mov     rbx, [rsp+28h+arg_0]
0x180013ae6  add     rsp, 20h
0x180013aea  pop     rdi
0x180013aeb  retn
```
