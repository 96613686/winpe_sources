# DeletePolicyRangeDBEntries

- ea: `0x1800b9b9c`
- end: `0x1800b9ca5`
- name: `DeletePolicyRangeDBEntries`
- size: `265`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088260`
- `0x1800bd190`

## callees

- `0x1800b9b9c`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b9bc8`
- `ESENT!JetSetCurrentIndexA` at `0x1800b9bc8`
- `ESENT!JetMakeKey` at `0x1800b9c10`
- `ESENT!JetMakeKey` at `0x1800b9c10`
- `ESENT!JetSeek` at `0x1800b9c3c`
- `ESENT!JetSeek` at `0x1800b9c3c`
- `ESENT!JetDelete` at `0x1800b9c64`
- `ESENT!JetDelete` at `0x1800b9c64`

## string_xrefs

- `0x1800b9c72`: `DeletePolicyRangeDBEntries:JetDelete`
- `0x1800b9c4a`: `DeletePolicyRangeDBEntries:JetSeek`
- `0x1800b9c1e`: `DeletePolicyRangeDBEntries:JetMakeKey`
- `0x1800b9bd6`: `DeletePolicyRangeDBEntries:JetSetCurrentIndex`

## pseudocode

```c
__int64 __fastcall DeletePolicyRangeDBEntries(JET_SESID sesid, __int64 a2, unsigned int a3)
{
  unsigned int v6; // eax
  __int64 result; // rax
  __int64 v8; // rbx
  unsigned int Key; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax

  v6 = JetSetCurrentIndexA(sesid, PolicyRangeTableId, "PolicyRangeTable_Index1");
  result = PolicyMapJetError(v6, "DeletePolicyRangeDBEntries:JetSetCurrentIndex");
  if ( !(_DWORD)result )
  {
    v8 = 0;
    if ( a3 )
    {
      while ( 1 )
      {
        Key = JetMakeKey(sesid, PolicyRangeTableId, (const void *)(a2 + 4 * v8), 4u, 1u);
        result = PolicyMapJetError(Key, "DeletePolicyRangeDBEntries:JetMakeKey");
        if ( (_DWORD)result )
          break;
        v10 = JetSeek(sesid, PolicyRangeTableId, 1u);
        result = PolicyMapJetError(v10, "DeletePolicyRangeDBEntries:JetSeek");
        if ( (_DWORD)result )
          break;
        v11 = JetDelete(sesid, PolicyRangeTableId);
        result = PolicyMapJetError(v11, "DeletePolicyRangeDBEntries:JetDelete");
        if ( (_DWORD)result )
          break;
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= a3 )
          return 0;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b9b9c  mov     [rsp+arg_0], rbx
0x1800b9ba1  mov     [rsp+arg_8], rsi
0x1800b9ba6  mov     [rsp+arg_10], rdi
0x1800b9bab  push    r14
0x1800b9bad  sub     rsp, 30h
0x1800b9bb1  mov     edi, r8d
0x1800b9bb4  mov     r14, rdx
0x1800b9bb7  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b9bbe  lea     r8, aPolicyrangetab_3; "PolicyRangeTable_Index1"
0x1800b9bc5  mov     rsi, rcx
0x1800b9bc8  call    cs:__imp_JetSetCurrentIndexA
0x1800b9bcf  nop     dword ptr [rax+rax+00h]
0x1800b9bd4  mov     ecx, eax
0x1800b9bd6  lea     rdx, aDeletepolicyra_2; "DeletePolicyRangeDBEntries:JetSetCurren"...
0x1800b9bdd  call    PolicyMapJetError
0x1800b9be2  test    eax, eax
0x1800b9be4  jnz     loc_1800B9C8E
0x1800b9bea  xor     ebx, ebx
0x1800b9bec  test    edi, edi
0x1800b9bee  jz      loc_1800B9C8C
0x1800b9bf4  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b9bfb  lea     r8, [r14+rbx*4]; pvData
0x1800b9bff  mov     r9d, 4; cbData
0x1800b9c05  mov     [rsp+38h+grbit], 1; grbit
0x1800b9c0d  mov     rcx, rsi; sesid
0x1800b9c10  call    cs:__imp_JetMakeKey
0x1800b9c17  nop     dword ptr [rax+rax+00h]
0x1800b9c1c  mov     ecx, eax
0x1800b9c1e  lea     rdx, aDeletepolicyra; "DeletePolicyRangeDBEntries:JetMakeKey"
0x1800b9c25  call    PolicyMapJetError
0x1800b9c2a  test    eax, eax
0x1800b9c2c  jnz     short loc_1800B9C8E
0x1800b9c2e  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b9c35  lea     r8d, [rax+1]; grbit
0x1800b9c39  mov     rcx, rsi; sesid
0x1800b9c3c  call    cs:__imp_JetSeek
0x1800b9c43  nop     dword ptr [rax+rax+00h]
0x1800b9c48  mov     ecx, eax
0x1800b9c4a  lea     rdx, aDeletepolicyra_0; "DeletePolicyRangeDBEntries:JetSeek"
0x1800b9c51  call    PolicyMapJetError
0x1800b9c56  test    eax, eax
0x1800b9c58  jnz     short loc_1800B9C8E
0x1800b9c5a  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b9c61  mov     rcx, rsi; sesid
0x1800b9c64  call    cs:__imp_JetDelete
0x1800b9c6b  nop     dword ptr [rax+rax+00h]
0x1800b9c70  mov     ecx, eax
0x1800b9c72  lea     rdx, aDeletepolicyra_1; "DeletePolicyRangeDBEntries:JetDelete"
0x1800b9c79  call    PolicyMapJetError
0x1800b9c7e  test    eax, eax
0x1800b9c80  jnz     short loc_1800B9C8E
0x1800b9c82  inc     ebx
0x1800b9c84  cmp     ebx, edi
0x1800b9c86  jb      loc_1800B9BF4
0x1800b9c8c  xor     eax, eax
0x1800b9c8e  mov     rbx, [rsp+38h+arg_0]
0x1800b9c93  mov     rsi, [rsp+38h+arg_8]
0x1800b9c98  mov     rdi, [rsp+38h+arg_10]
0x1800b9c9d  add     rsp, 30h
0x1800b9ca1  pop     r14
0x1800b9ca3  retn
```
