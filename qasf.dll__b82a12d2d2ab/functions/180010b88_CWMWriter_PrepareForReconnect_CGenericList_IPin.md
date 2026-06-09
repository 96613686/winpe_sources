# CWMWriter::PrepareForReconnect(CGenericList<IPin> &)

- ea: `0x180010b88`
- end: `0x180010c3f`
- name: `?PrepareForReconnect@CWMWriter@@AEAAJAEAV?$CGenericList@UIPin@@@@@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ea00`

## callees

- `0x180001460`
- `0x180006f48`
- `0x180010b88`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::PrepareForReconnect(__int64 a1, CBaseList *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rbx
  void *v7; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_DWORD *)(a1 + 516) )
  {
    v3 = *(_QWORD *)(a1 + 408);
    if ( v3 )
    {
      do
      {
        v4 = *(_QWORD *)(v3 + 16);
        v5 = *(_QWORD *)(v3 + 8);
        v7 = 0;
        if ( (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)(v4 + 24) + 48LL))(v4 + 24, &v7) >= 0 )
        {
          CBaseList::AddTailI(a2, v7);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(v4 + 24) + 40LL))(v4 + 24);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 40LL))(v7);
        }
        v3 = v5;
      }
      while ( v5 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010b88  mov     [rsp+arg_10], rbx
0x180010b8d  mov     [rsp+arg_18], rsi
0x180010b92  push    rdi
0x180010b93  sub     rsp, 30h
0x180010b97  mov     rax, cs:__security_cookie
0x180010b9e  xor     rax, rsp
0x180010ba1  mov     [rsp+38h+var_10], rax
0x180010ba6  cmp     dword ptr [rcx+204h], 0
0x180010bad  mov     rsi, rdx
0x180010bb0  jz      short loc_180010C20
0x180010bb2  mov     rax, [rcx+198h]
0x180010bb9  test    rax, rax
0x180010bbc  jz      short loc_180010C20
0x180010bbe  mov     rdi, [rax+10h]
0x180010bc2  lea     rdx, [rsp+38h+var_18]
0x180010bc7  mov     rbx, [rax+8]
0x180010bcb  mov     [rsp+38h+var_18], 0
0x180010bd4  mov     rax, [rdi+18h]
0x180010bd8  lea     rcx, [rdi+18h]
0x180010bdc  mov     rax, [rax+30h]
0x180010be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be5  test    eax, eax
0x180010be7  js      short loc_180010C18
0x180010be9  mov     rdx, [rsp+38h+var_18]; void *
0x180010bee  mov     rcx, rsi; this
0x180010bf1  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x180010bf6  mov     rax, [rdi+18h]
0x180010bfa  lea     rcx, [rdi+18h]
0x180010bfe  mov     rax, [rax+28h]
0x180010c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c07  mov     rcx, [rsp+38h+var_18]
0x180010c0c  mov     rax, [rcx]
0x180010c0f  mov     rax, [rax+28h]
0x180010c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c18  mov     rax, rbx
0x180010c1b  test    rbx, rbx
0x180010c1e  jnz     short loc_180010BBE
0x180010c20  xor     eax, eax
0x180010c22  mov     rcx, [rsp+38h+var_10]
0x180010c27  xor     rcx, rsp; StackCookie
0x180010c2a  call    __security_check_cookie
0x180010c2f  mov     rbx, [rsp+38h+arg_10]
0x180010c34  mov     rsi, [rsp+38h+arg_18]
0x180010c39  add     rsp, 30h
0x180010c3d  pop     rdi
0x180010c3e  retn
```
