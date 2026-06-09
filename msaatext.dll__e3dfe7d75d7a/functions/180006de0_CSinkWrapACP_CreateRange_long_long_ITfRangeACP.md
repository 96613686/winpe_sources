# CSinkWrapACP::CreateRange(long,long,ITfRangeACP * *)

- ea: `0x180006de0`
- end: `0x180006ecb`
- name: `?CreateRange@CSinkWrapACP@@UEAAJJJPEAPEAUITfRangeACP@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(CSinkWrapACP *__hidden this, int, int, struct ITfRangeACP **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800026d0`
- `0x180006de0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSinkWrapACP::CreateRange(
        CSinkWrapACP *this,
        unsigned int a2,
        unsigned int a3,
        struct ITfRangeACP **a4)
{
  __int64 **v7; // rbx
  __int64 i; // rbx
  unsigned int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v7 = (__int64 **)((char *)this + 32);
  if ( !*((_QWORD *)this + 3) || !*v7 )
    InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", 0x86Du, 8u, 0, v12, 0, (wchar_t *)L"m_pMgr && m_pDocs");
  for ( i = **v7; ; i = *(_QWORD *)(i + 8) )
  {
    if ( !i )
      return 2147500037LL;
    v9 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *))(i + 24);
    if ( v9 )
      break;
LABEL_10:
    ;
  }
  v13 = 0;
  if ( (**v9)(v9, &GUID_aa80e901_2021_11d2_93e0_0060b067b86e, &v13) )
  {
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_10;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct ITfRangeACP **))(*(_QWORD *)v13 + 48LL))(
          v13,
          a2,
          a3,
          a4);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v10;
}

```

## disassembly

```asm
0x180006de0  push    rbx
0x180006de2  push    rbp
0x180006de3  push    rsi
0x180006de4  push    rdi
0x180006de5  sub     rsp, 48h
0x180006de9  mov     rdi, r9
0x180006dec  mov     esi, r8d
0x180006def  mov     ebp, edx
0x180006df1  lea     rbx, [rcx+20h]
0x180006df5  cmp     qword ptr [rcx+18h], 0
0x180006dfa  jz      short loc_180006E02
0x180006dfc  cmp     qword ptr [rbx], 0
0x180006e00  jnz     short loc_180006E2E
0x180006e02  lea     rax, aMPmgrMPdocs; "m_pMgr && m_pDocs"
0x180006e09  mov     [rsp+68h+var_38], rax; __int64
0x180006e0e  mov     [rsp+68h+var_40], 0; int
0x180006e16  xor     r9d, r9d
0x180006e19  mov     edx, 86Dh; Value
0x180006e1e  lea     r8d, [r9+8]
0x180006e22  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180006e29  call    InternalTrace
0x180006e2e  mov     rbx, [rbx]
0x180006e31  mov     rbx, [rbx]
0x180006e34  test    rbx, rbx
0x180006e37  jz      loc_180006EBD
0x180006e3d  mov     rcx, [rbx+18h]
0x180006e41  test    rcx, rcx
0x180006e44  jz      short loc_180006E81
0x180006e46  mov     [rsp+68h+arg_0], 0
0x180006e4f  mov     rax, [rcx]
0x180006e52  lea     r8, [rsp+68h+arg_0]
0x180006e57  lea     rdx, _GUID_aa80e901_2021_11d2_93e0_0060b067b86e
0x180006e5e  mov     rax, [rax]
0x180006e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e66  test    eax, eax
0x180006e68  jz      short loc_180006E87
0x180006e6a  mov     rcx, [rsp+68h+arg_0]
0x180006e6f  test    rcx, rcx
0x180006e72  jz      short loc_180006E81
0x180006e74  mov     rax, [rcx]
0x180006e77  mov     rax, [rax+10h]
0x180006e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e80  nop
0x180006e81  mov     rbx, [rbx+8]
0x180006e85  jmp     short loc_180006E34
0x180006e87  mov     rcx, [rsp+68h+arg_0]
0x180006e8c  mov     rax, [rcx]
0x180006e8f  mov     r9, rdi
0x180006e92  mov     r8d, esi
0x180006e95  mov     edx, ebp
0x180006e97  mov     rax, [rax+30h]
0x180006e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea0  mov     ebx, eax
0x180006ea2  mov     rcx, [rsp+68h+arg_0]
0x180006ea7  test    rcx, rcx
0x180006eaa  jz      short loc_180006EB9
0x180006eac  mov     rdx, [rcx]
0x180006eaf  mov     rax, [rdx+10h]
0x180006eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb8  nop
0x180006eb9  mov     eax, ebx
0x180006ebb  jmp     short loc_180006EC2
0x180006ebd  mov     eax, 80004005h
0x180006ec2  add     rsp, 48h
0x180006ec6  pop     rdi
0x180006ec7  pop     rsi
0x180006ec8  pop     rbp
0x180006ec9  pop     rbx
0x180006eca  retn
```
