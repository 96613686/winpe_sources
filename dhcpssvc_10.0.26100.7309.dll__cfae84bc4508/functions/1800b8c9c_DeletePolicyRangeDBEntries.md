# DeletePolicyRangeDBEntries

- ea: `0x1800b8c9c`
- end: `0x1800b8da5`
- name: `DeletePolicyRangeDBEntries`
- size: `265`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800882b8`
- `0x1800bc1fc`

## callees

- `0x1800b8c9c`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b8cc8`
- `ESENT!JetSetCurrentIndexA` at `0x1800b8cc8`
- `ESENT!JetMakeKey` at `0x1800b8d10`
- `ESENT!JetMakeKey` at `0x1800b8d10`
- `ESENT!JetSeek` at `0x1800b8d3c`
- `ESENT!JetSeek` at `0x1800b8d3c`
- `ESENT!JetDelete` at `0x1800b8d64`
- `ESENT!JetDelete` at `0x1800b8d64`

## string_xrefs

- `0x1800b8cd6`: `DeletePolicyRangeDBEntries:JetSetCurrentIndex`
- `0x1800b8d1e`: `DeletePolicyRangeDBEntries:JetMakeKey`
- `0x1800b8d4a`: `DeletePolicyRangeDBEntries:JetSeek`
- `0x1800b8d72`: `DeletePolicyRangeDBEntries:JetDelete`

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
0x1800b8c9c  mov     [rsp+arg_0], rbx
0x1800b8ca1  mov     [rsp+arg_8], rsi
0x1800b8ca6  mov     [rsp+arg_10], rdi
0x1800b8cab  push    r14
0x1800b8cad  sub     rsp, 30h
0x1800b8cb1  mov     edi, r8d
0x1800b8cb4  mov     r14, rdx
0x1800b8cb7  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8cbe  lea     r8, aPolicyrangetab_3; "PolicyRangeTable_Index1"
0x1800b8cc5  mov     rsi, rcx
0x1800b8cc8  call    cs:__imp_JetSetCurrentIndexA
0x1800b8ccf  nop     dword ptr [rax+rax+00h]
0x1800b8cd4  mov     ecx, eax
0x1800b8cd6  lea     rdx, aDeletepolicyra_2; "DeletePolicyRangeDBEntries:JetSetCurren"...
0x1800b8cdd  call    PolicyMapJetError
0x1800b8ce2  test    eax, eax
0x1800b8ce4  jnz     loc_1800B8D8E
0x1800b8cea  xor     ebx, ebx
0x1800b8cec  test    edi, edi
0x1800b8cee  jz      loc_1800B8D8C
0x1800b8cf4  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8cfb  lea     r8, [r14+rbx*4]; pvData
0x1800b8cff  mov     r9d, 4; cbData
0x1800b8d05  mov     [rsp+38h+grbit], 1; grbit
0x1800b8d0d  mov     rcx, rsi; sesid
0x1800b8d10  call    cs:__imp_JetMakeKey
0x1800b8d17  nop     dword ptr [rax+rax+00h]
0x1800b8d1c  mov     ecx, eax
0x1800b8d1e  lea     rdx, aDeletepolicyra; "DeletePolicyRangeDBEntries:JetMakeKey"
0x1800b8d25  call    PolicyMapJetError
0x1800b8d2a  test    eax, eax
0x1800b8d2c  jnz     short loc_1800B8D8E
0x1800b8d2e  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8d35  lea     r8d, [rax+1]; grbit
0x1800b8d39  mov     rcx, rsi; sesid
0x1800b8d3c  call    cs:__imp_JetSeek
0x1800b8d43  nop     dword ptr [rax+rax+00h]
0x1800b8d48  mov     ecx, eax
0x1800b8d4a  lea     rdx, aDeletepolicyra_0; "DeletePolicyRangeDBEntries:JetSeek"
0x1800b8d51  call    PolicyMapJetError
0x1800b8d56  test    eax, eax
0x1800b8d58  jnz     short loc_1800B8D8E
0x1800b8d5a  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8d61  mov     rcx, rsi; sesid
0x1800b8d64  call    cs:__imp_JetDelete
0x1800b8d6b  nop     dword ptr [rax+rax+00h]
0x1800b8d70  mov     ecx, eax
0x1800b8d72  lea     rdx, aDeletepolicyra_1; "DeletePolicyRangeDBEntries:JetDelete"
0x1800b8d79  call    PolicyMapJetError
0x1800b8d7e  test    eax, eax
0x1800b8d80  jnz     short loc_1800B8D8E
0x1800b8d82  inc     ebx
0x1800b8d84  cmp     ebx, edi
0x1800b8d86  jb      loc_1800B8CF4
0x1800b8d8c  xor     eax, eax
0x1800b8d8e  mov     rbx, [rsp+38h+arg_0]
0x1800b8d93  mov     rsi, [rsp+38h+arg_8]
0x1800b8d98  mov     rdi, [rsp+38h+arg_10]
0x1800b8d9d  add     rsp, 30h
0x1800b8da1  pop     r14
0x1800b8da3  retn
```
