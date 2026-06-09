# FindIdFromGaps

- ea: `0x1800bb4b8`
- end: `0x1800bb666`
- name: `FindIdFromGaps`
- size: `430`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, JET_PCSTR szIndexName, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b7970`
- `0x1800b82d4`
- `0x1800b86ac`
- `0x1800bb66c`

## callees

- `0x1800bb4b8`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndex2A` at `0x1800bb4f0`
- `ESENT!JetSetCurrentIndex2A` at `0x1800bb4f0`
- `ESENT!JetMakeKey` at `0x1800bb537`
- `ESENT!JetMakeKey` at `0x1800bb537`
- `ESENT!JetSeek` at `0x1800bb562`
- `ESENT!JetSeek` at `0x1800bb562`
- `ESENT!JetRetrieveColumn` at `0x1800bb5f6`
- `ESENT!JetRetrieveColumn` at `0x1800bb5f6`
- `ESENT!JetMove` at `0x1800bb5a4`
- `ESENT!JetMove` at `0x1800bb5a4`

## string_xrefs

- `0x1800bb5b2`: `FindIdFromGaps:JetMove`

## pseudocode

```c
__int64 __fastcall FindIdFromGaps(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        JET_PCSTR szIndexName,
        unsigned int *a5)
{
  unsigned int *v5; // rdi
  unsigned int v9; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // eax
  int pvData[4]; // [rsp+40h] [rbp-28h] BYREF

  v5 = a5;
  *a5 = 0;
  v9 = JetSetCurrentIndex2A(sesid, tableid, szIndexName, 0);
  result = PolicyMapJetError(v9, "FindIdFromGaps:JetSetCurrentIndex");
  if ( !(_DWORD)result )
  {
    pvData[0] = 1;
    LODWORD(a5) = 1;
    Key = JetMakeKey(sesid, tableid, pvData, 4u, 1u);
    result = PolicyMapJetError(Key, "FindIdFromGaps:JetMakeKey");
    if ( !(_DWORD)result )
    {
      v12 = JetSeek(sesid, tableid, 1u);
      v13 = PolicyMapJetError(v12, "FindIdFromGaps:JetSeek");
      v14 = (unsigned int)a5;
      v15 = v13;
      if ( !v13 )
      {
        while ( v14 <= 1 )
        {
          v16 = JetMove(sesid, tableid, 1, 0);
          result = PolicyMapJetError(v16, "FindIdFromGaps:JetMove");
          if ( (_DWORD)result )
            return result;
          v12 = JetRetrieveColumn(sesid, tableid, columnid, &a5, 4u, 0, 1u, 0);
          result = PolicyMapJetError(v12, "FindIdFromGaps:JetRetrieveColumn");
          v15 = result;
          if ( (_DWORD)result )
            return result;
          v14 = (unsigned int)a5;
          if ( (unsigned int)a5 > pvData[0] + 1 )
          {
            *v5 = pvData[0] + 1;
            return 0;
          }
          ++pvData[0];
        }
      }
      if ( v12 == -1601 && v14 != -1 )
      {
        *v5 = v14;
        return 0;
      }
      return v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800bb4b8  mov     [rsp+arg_0], rbx
0x1800bb4bd  mov     [rsp+arg_8], rbp
0x1800bb4c2  mov     [rsp+arg_10], rsi
0x1800bb4c7  push    rdi
0x1800bb4c8  push    r12
0x1800bb4ca  push    r14
0x1800bb4cc  sub     rsp, 50h
0x1800bb4d0  mov     rdi, [rsp+68h+arg_20]
0x1800bb4d8  mov     rax, r9
0x1800bb4db  mov     r14d, r8d
0x1800bb4de  xor     r9d, r9d; grbit
0x1800bb4e1  mov     r8, rax; szIndexName
0x1800bb4e4  mov     rsi, rdx
0x1800bb4e7  mov     rbp, rcx
0x1800bb4ea  mov     dword ptr [rdi], 0
0x1800bb4f0  call    cs:__imp_JetSetCurrentIndex2A
0x1800bb4f7  nop     dword ptr [rax+rax+00h]
0x1800bb4fc  mov     ecx, eax
0x1800bb4fe  lea     rdx, aFindidfromgaps_2; "FindIdFromGaps:JetSetCurrentIndex"
0x1800bb505  call    PolicyMapJetError
0x1800bb50a  test    eax, eax
0x1800bb50c  jnz     loc_1800BB64B
0x1800bb512  lea     r12d, [rax+1]
0x1800bb516  mov     rdx, rsi; tableid
0x1800bb519  lea     r9d, [rax+4]; cbData
0x1800bb51d  mov     [rsp+68h+pvData], r12d
0x1800bb522  lea     r8, [rsp+68h+pvData]; pvData
0x1800bb527  mov     dword ptr [rsp+68h+arg_20], r12d
0x1800bb52f  mov     rcx, rbp; sesid
0x1800bb532  mov     [rsp+68h+grbit], r12d; grbit
0x1800bb537  call    cs:__imp_JetMakeKey
0x1800bb53e  nop     dword ptr [rax+rax+00h]
0x1800bb543  mov     ecx, eax
0x1800bb545  lea     rdx, aFindidfromgaps_0; "FindIdFromGaps:JetMakeKey"
0x1800bb54c  call    PolicyMapJetError
0x1800bb551  test    eax, eax
0x1800bb553  jnz     loc_1800BB64B
0x1800bb559  mov     r8d, r12d; grbit
0x1800bb55c  mov     rdx, rsi; tableid
0x1800bb55f  mov     rcx, rbp; sesid
0x1800bb562  call    cs:__imp_JetSeek
0x1800bb569  nop     dword ptr [rax+rax+00h]
0x1800bb56e  mov     ecx, eax
0x1800bb570  lea     rdx, aFindidfromgaps_1; "FindIdFromGaps:JetSeek"
0x1800bb577  mov     ebx, eax
0x1800bb579  call    PolicyMapJetError
0x1800bb57e  mov     ecx, dword ptr [rsp+68h+arg_20]
0x1800bb585  mov     edx, eax
0x1800bb587  test    eax, eax
0x1800bb589  jnz     loc_1800BB638
0x1800bb58f  cmp     ecx, r12d
0x1800bb592  ja      loc_1800BB638
0x1800bb598  xor     r9d, r9d; grbit
0x1800bb59b  mov     r8d, r12d; cRow
0x1800bb59e  mov     rdx, rsi; tableid
0x1800bb5a1  mov     rcx, rbp; sesid
0x1800bb5a4  call    cs:__imp_JetMove
0x1800bb5ab  nop     dword ptr [rax+rax+00h]
0x1800bb5b0  mov     ecx, eax
0x1800bb5b2  lea     rdx, aFindidfromgaps_3; "FindIdFromGaps:JetMove"
0x1800bb5b9  call    PolicyMapJetError
0x1800bb5be  test    eax, eax
0x1800bb5c0  jnz     loc_1800BB64B
0x1800bb5c6  mov     [rsp+68h+pretinfo], 0; pretinfo
0x1800bb5cf  lea     r9, [rsp+68h+arg_20]; pvData
0x1800bb5d7  mov     [rsp+68h+var_38], r12d; grbit
0x1800bb5dc  mov     r8d, r14d; columnid
0x1800bb5df  mov     [rsp+68h+pcbActual], 0; pcbActual
0x1800bb5e8  mov     rdx, rsi; tableid
0x1800bb5eb  mov     rcx, rbp; sesid
0x1800bb5ee  mov     [rsp+68h+grbit], 4; cbData
0x1800bb5f6  call    cs:__imp_JetRetrieveColumn
0x1800bb5fd  nop     dword ptr [rax+rax+00h]
0x1800bb602  mov     ecx, eax
0x1800bb604  lea     rdx, aFindidfromgaps; "FindIdFromGaps:JetRetrieveColumn"
0x1800bb60b  mov     ebx, eax
0x1800bb60d  call    PolicyMapJetError
0x1800bb612  mov     edx, eax
0x1800bb614  test    eax, eax
0x1800bb616  jnz     short loc_1800BB64B
0x1800bb618  mov     eax, [rsp+68h+pvData]
0x1800bb61c  mov     ecx, dword ptr [rsp+68h+arg_20]
0x1800bb623  inc     eax
0x1800bb625  cmp     ecx, eax
0x1800bb627  ja      short loc_1800BB632
0x1800bb629  mov     [rsp+68h+pvData], eax
0x1800bb62d  jmp     loc_1800BB58F
0x1800bb632  mov     [rdi], eax
0x1800bb634  xor     eax, eax
0x1800bb636  jmp     short loc_1800BB64B
0x1800bb638  cmp     ebx, 0FFFFF9BFh
0x1800bb63e  jnz     short loc_1800BB649
0x1800bb640  cmp     ecx, 0FFFFFFFFh
0x1800bb643  jz      short loc_1800BB649
0x1800bb645  mov     [rdi], ecx
0x1800bb647  xor     edx, edx
0x1800bb649  mov     eax, edx
0x1800bb64b  lea     r11, [rsp+68h+var_18]
0x1800bb650  mov     rbx, [r11+20h]
0x1800bb654  mov     rbp, [r11+28h]
0x1800bb658  mov     rsi, [r11+30h]
0x1800bb65c  mov     rsp, r11
0x1800bb65f  pop     r14
0x1800bb661  pop     r12
0x1800bb663  pop     rdi
0x1800bb664  retn
```
