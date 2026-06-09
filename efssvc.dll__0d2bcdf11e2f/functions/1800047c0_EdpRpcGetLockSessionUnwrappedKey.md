# EdpRpcGetLockSessionUnwrappedKey

- ea: `0x1800047c0`
- end: `0x1800048f8`
- name: `EdpRpcGetLockSessionUnwrappedKey`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800047c0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionUnwrappedKey` at `0x18000489a`
- `EFSCORE!EdpDllGetLockSessionUnwrappedKey` at `0x18000489a`

## pseudocode

```c
__int64 __fastcall EdpRpcGetLockSessionUnwrappedKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  signed int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  signed int LockSessionUnwrappedKey; // eax
  __int64 v15; // rcx
  _BYTE v17[184]; // [rsp+40h] [rbp-B8h] BYREF

  memset_0(v17, 0, 0x70u);
  if ( a2 && a3 && a4 && a5 && a6 )
  {
    if ( a7 && a8 )
    {
      v11 = EdpBeginLocalOnlyRpcCall((__int64)v17);
      v13 = v11;
      if ( v11 >= 0 )
      {
        LockSessionUnwrappedKey = EdpDllGetLockSessionUnwrappedKey(v17, a2, a3, a4, a5, a6, a7, a8);
        v13 = LockSessionUnwrappedKey;
        if ( LockSessionUnwrappedKey < 0 )
          fnEfsLogTrace1(v15, (__int64)EFS_API_ERROR, LockSessionUnwrappedKey, 6, 140);
        EdpCleanupLocalOnlyRpcCall((__int64)v17);
      }
      else
      {
        fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 125);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v13;
}

```

## disassembly

```asm
0x1800047c0  push    rbx
0x1800047c2  push    rbp
0x1800047c3  push    rsi
0x1800047c4  push    rdi
0x1800047c5  push    r12
0x1800047c7  push    r13
0x1800047c9  push    r14
0x1800047cb  push    r15
0x1800047cd  sub     rsp, 0B8h
0x1800047d4  mov     r13, rdx
0x1800047d7  lea     rcx, [rsp+0F8h+var_B8]; void *
0x1800047dc  xor     edx, edx; Val
0x1800047de  mov     r12, r8
0x1800047e1  mov     r15d, r9d
0x1800047e4  lea     r8d, [rdx+70h]; Size
0x1800047e8  call    memset_0
0x1800047ed  test    r13, r13
0x1800047f0  jz      loc_1800048DC
0x1800047f6  test    r12, r12
0x1800047f9  jz      loc_1800048DC
0x1800047ff  test    r15d, r15d
0x180004802  jz      loc_1800048DC
0x180004808  mov     rdi, [rsp+0F8h+arg_20]
0x180004810  test    rdi, rdi
0x180004813  jz      loc_1800048DC
0x180004819  mov     esi, [rsp+0F8h+arg_28]
0x180004820  test    esi, esi
0x180004822  jz      loc_1800048DC
0x180004828  mov     rbp, [rsp+0F8h+arg_30]
0x180004830  test    rbp, rbp
0x180004833  jz      loc_1800048D5
0x180004839  mov     r14, [rsp+0F8h+arg_38]
0x180004841  test    r14, r14
0x180004844  jz      loc_1800048D5
0x18000484a  lea     rcx, [rsp+0F8h+var_B8]
0x18000484f  call    EdpBeginLocalOnlyRpcCall
0x180004854  mov     ebx, eax
0x180004856  test    eax, eax
0x180004858  jns     short loc_180004879
0x18000485a  mov     r9d, 6
0x180004860  mov     dword ptr [rsp+0F8h+var_D8], 0C7Dh
0x180004868  mov     r8d, eax
0x18000486b  lea     rdx, EFS_API_ERROR
0x180004872  call    fnEfsLogTrace1
0x180004877  jmp     short loc_1800048E1
0x180004879  mov     [rsp+0F8h+var_C0], r14
0x18000487e  lea     rcx, [rsp+0F8h+var_B8]
0x180004883  mov     [rsp+0F8h+var_C8], rbp
0x180004888  mov     r9d, r15d
0x18000488b  mov     [rsp+0F8h+var_D0], esi
0x18000488f  mov     r8, r12
0x180004892  mov     rdx, r13
0x180004895  mov     [rsp+0F8h+var_D8], rdi
0x18000489a  call    cs:__imp_EdpDllGetLockSessionUnwrappedKey
0x1800048a1  nop     dword ptr [rax+rax+00h]
0x1800048a6  mov     ebx, eax
0x1800048a8  test    eax, eax
0x1800048aa  jns     short loc_1800048C9
0x1800048ac  mov     r9d, 6
0x1800048b2  mov     dword ptr [rsp+0F8h+var_D8], 0C8Ch
0x1800048ba  mov     r8d, eax
0x1800048bd  lea     rdx, EFS_API_ERROR
0x1800048c4  call    fnEfsLogTrace1
0x1800048c9  lea     rcx, [rsp+0F8h+var_B8]
0x1800048ce  call    EdpCleanupLocalOnlyRpcCall
0x1800048d3  jmp     short loc_1800048E1
0x1800048d5  mov     ebx, 80004003h
0x1800048da  jmp     short loc_1800048E1
0x1800048dc  mov     ebx, 80070057h
0x1800048e1  mov     eax, ebx
0x1800048e3  add     rsp, 0B8h
0x1800048ea  pop     r15
0x1800048ec  pop     r14
0x1800048ee  pop     r13
0x1800048f0  pop     r12
0x1800048f2  pop     rdi
0x1800048f3  pop     rsi
0x1800048f4  pop     rbp
0x1800048f5  pop     rbx
0x1800048f6  retn
```
