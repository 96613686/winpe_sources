# DfsAddOrRemoveMachineAceForLdapEntry(ushort const *,ushort const *,ulong,ushort const *,uchar)

- ea: `0x140032efc`
- end: `0x14003304b`
- name: `?DfsAddOrRemoveMachineAceForLdapEntry@@YAKPEBG0K0E@Z`
- size: `335`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, unsigned __int8)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000af60`
- `0x140042ddc`

## callees

- `0x140032e44`
- `0x140032eac`
- `0x140032efc`
- `0x1400333f0`
- `0x1400334fc`
- `0x140049758`
- `0x14004ac38`
- `0x14005a010`
- `0x14005a52c`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f44`
- `RPCRT4!RpcRevertToSelf` at `0x140032fae`
- `RPCRT4!RpcRevertToSelf` at `0x140032fae`
- `RPCRT4!RpcImpersonateClient` at `0x140032f34`
- `RPCRT4!RpcImpersonateClient` at `0x140032f34`

## string_xrefs

- `0x140032fea`: `Remove`

## pseudocode

```c
__int64 __fastcall DfsAddOrRemoveMachineAceForLdapEntry(
        const unsigned __int16 *a1,
        WCHAR *a2,
        unsigned int a3,
        WCHAR *a4,
        unsigned __int8 a5)
{
  DWORD LastError; // ebx
  int v10; // r8d
  struct CLocalMachine *Instance; // rax
  CLdap *v12; // rcx
  DWORD v13; // eax
  const wchar_t *v14; // rax
  LDAP *ld[132]; // [rsp+50h] [rbp-458h] BYREF

  CLdap::CLdap((CLdap *)ld);
  if ( RpcImpersonateClient(0) )
  {
    LastError = GetLastError();
  }
  else
  {
    Instance = CLocalMachine::_GetInstance(0);
    if ( (unsigned int)CLdap::Bind((CLdap *)ld, *((const unsigned __int16 **)Instance + 6), a1) )
    {
      if ( a5 )
        v13 = DfsAddMachineAce(ld[0], a1, a2, a4, a3);
      else
        v13 = DfsRemoveMachineAce(ld[0], a1, a2, a4);
      LastError = v13;
      CLdap::Deinit((CLdap *)ld);
    }
    else
    {
      LastError = CLdap::GetLastError(v12);
    }
    RpcRevertToSelf();
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    v14 = L"Add";
    if ( !a5 )
      v14 = L"Remove";
    WPP_SF_SSdSSD(
      *((_QWORD *)pWppControl + 2),
      (unsigned int)L"Remove",
      v10,
      (_DWORD)a1,
      (__int64)a2,
      a3,
      (__int64)a4,
      (__int64)v14,
      LastError);
  }
  CLdap::Deinit((CLdap *)ld);
  return LastError;
}

```

## disassembly

```asm
0x140032efc  push    rbx
0x140032efe  push    rbp
0x140032eff  push    rsi
0x140032f00  push    rdi
0x140032f01  push    r15
0x140032f03  sub     rsp, 480h
0x140032f0a  mov     rax, cs:__security_cookie
0x140032f11  xor     rax, rsp
0x140032f14  mov     [rsp+4A8h+var_38], rax
0x140032f1c  mov     rdi, rcx
0x140032f1f  mov     rbp, r9
0x140032f22  lea     rcx, [rsp+4A8h+ld]; this
0x140032f27  mov     r15d, r8d
0x140032f2a  mov     rsi, rdx
0x140032f2d  call    ??0CLdap@@QEAA@XZ; CLdap::CLdap(void)
0x140032f32  xor     ecx, ecx; BindingHandle
0x140032f34  call    cs:__imp_RpcImpersonateClient
0x140032f3b  nop     dword ptr [rax+rax+00h]
0x140032f40  test    eax, eax
0x140032f42  jz      short loc_140032F54
0x140032f44  call    cs:__imp_GetLastError
0x140032f4b  nop     dword ptr [rax+rax+00h]
0x140032f50  mov     ebx, eax
0x140032f52  jmp     short loc_140032FBA
0x140032f54  xor     ecx, ecx; unsigned int *
0x140032f56  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x140032f5b  mov     r8, rdi; unsigned __int16 *
0x140032f5e  lea     rcx, [rsp+4A8h+ld]; this
0x140032f63  mov     rdx, [rax+30h]; unsigned __int16 *
0x140032f67  call    ?Bind@CLdap@@QEAAHPEBG0@Z; CLdap::Bind(ushort const *,ushort const *)
0x140032f6c  test    eax, eax
0x140032f6e  jnz     short loc_140032F79
0x140032f70  call    ?GetLastError@CLdap@@QEAAKXZ; CLdap::GetLastError(void)
0x140032f75  mov     ebx, eax
0x140032f77  jmp     short loc_140032FAE
0x140032f79  cmp     [rsp+4A8h+arg_20], 0
0x140032f81  mov     r9, rbp
0x140032f84  mov     rcx, [rsp+4A8h+ld]; ld
0x140032f89  mov     r8, rsi
0x140032f8c  mov     rdx, rdi
0x140032f8f  jz      short loc_140032F9D
0x140032f91  mov     dword ptr [rsp+4A8h+var_488], r15d
0x140032f96  call    DfsAddMachineAce
0x140032f9b  jmp     short loc_140032FA2
0x140032f9d  call    DfsRemoveMachineAce
0x140032fa2  lea     rcx, [rsp+4A8h+ld]; this
0x140032fa7  mov     ebx, eax
0x140032fa9  call    ?Deinit@CLdap@@AEAAXXZ; CLdap::Deinit(void)
0x140032fae  call    cs:__imp_RpcRevertToSelf
0x140032fb5  nop     dword ptr [rax+rax+00h]
0x140032fba  lea     rax, WPP_GLOBAL_Control
0x140032fc1  cmp     cs:WPP_GLOBAL_Control, rax
0x140032fc8  jz      short loc_140033020
0x140032fca  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140032fd1  test    rcx, rcx
0x140032fd4  jz      short loc_140033020
0x140032fd6  test    byte ptr [rcx+1Ch], 40h
0x140032fda  jz      short loc_140033020
0x140032fdc  cmp     byte ptr [rcx+19h], 2
0x140032fe0  jb      short loc_140033020
0x140032fe2  cmp     [rsp+4A8h+arg_20], 0
0x140032fea  lea     rdx, aRemove; "Remove"
0x140032ff1  mov     rcx, [rcx+10h]
0x140032ff5  lea     rax, aAdd; "Add"
0x140032ffc  mov     [rsp+4A8h+var_468], ebx
0x140033000  cmovz   rax, rdx
0x140033004  mov     [rsp+4A8h+var_470], rax
0x140033009  mov     r9, rdi
0x14003300c  mov     [rsp+4A8h+var_478], rbp
0x140033011  mov     [rsp+4A8h+var_480], r15d
0x140033016  mov     [rsp+4A8h+var_488], rsi
0x14003301b  call    WPP_SF_SSdSSD
0x140033020  lea     rcx, [rsp+4A8h+ld]; this
0x140033025  call    ?Deinit@CLdap@@AEAAXXZ; CLdap::Deinit(void)
0x14003302a  mov     eax, ebx
0x14003302c  mov     rcx, [rsp+4A8h+var_38]
0x140033034  xor     rcx, rsp; StackCookie
0x140033037  call    __security_check_cookie
0x14003303c  add     rsp, 480h
0x140033043  pop     r15
0x140033045  pop     rdi
0x140033046  pop     rsi
0x140033047  pop     rbp
0x140033048  pop     rbx
0x140033049  retn
```
