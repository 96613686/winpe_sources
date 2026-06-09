# FindIdFromGaps

- ea: `0x1800ba598`
- end: `0x1800ba739`
- name: `FindIdFromGaps`
- size: `417`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, JET_PCSTR szIndexName, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b6adc`
- `0x1800b7404`
- `0x1800b77e0`
- `0x1800ba740`

## callees

- `0x1800ba598`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndex2A` at `0x1800ba5cd`
- `ESENT!JetSetCurrentIndex2A` at `0x1800ba5cd`
- `ESENT!JetMakeKey` at `0x1800ba614`
- `ESENT!JetMakeKey` at `0x1800ba614`
- `ESENT!JetSeek` at `0x1800ba63f`
- `ESENT!JetSeek` at `0x1800ba63f`
- `ESENT!JetRetrieveColumn` at `0x1800ba6c9`
- `ESENT!JetRetrieveColumn` at `0x1800ba6c9`
- `ESENT!JetMove` at `0x1800ba681`
- `ESENT!JetMove` at `0x1800ba681`

## string_xrefs

- `0x1800ba68f`: `FindIdFromGaps:JetMove`

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
0x1800ba598  mov     [rsp+arg_0], rbx
0x1800ba59d  mov     [rsp+arg_8], rbp
0x1800ba5a2  mov     [rsp+arg_10], rsi
0x1800ba5a7  push    rdi
0x1800ba5a8  push    r12
0x1800ba5aa  push    r14
0x1800ba5ac  sub     rsp, 50h
0x1800ba5b0  mov     rdi, [rsp+68h+arg_20]
0x1800ba5b8  mov     rax, r9
0x1800ba5bb  mov     r14d, r8d
0x1800ba5be  xor     r9d, r9d; grbit
0x1800ba5c1  mov     r8, rax; szIndexName
0x1800ba5c4  mov     rsi, rdx
0x1800ba5c7  mov     rbp, rcx
0x1800ba5ca  and     dword ptr [rdi], 0
0x1800ba5cd  call    cs:__imp_JetSetCurrentIndex2A
0x1800ba5d4  nop     dword ptr [rax+rax+00h]
0x1800ba5d9  mov     ecx, eax
0x1800ba5db  lea     rdx, aFindidfromgaps_2; "FindIdFromGaps:JetSetCurrentIndex"
0x1800ba5e2  call    PolicyMapJetError
0x1800ba5e7  test    eax, eax
0x1800ba5e9  jnz     loc_1800BA71E
0x1800ba5ef  lea     r12d, [rax+1]
0x1800ba5f3  mov     rdx, rsi; tableid
0x1800ba5f6  lea     r9d, [rax+4]; cbData
0x1800ba5fa  mov     [rsp+68h+pvData], r12d
0x1800ba5ff  lea     r8, [rsp+68h+pvData]; pvData
0x1800ba604  mov     dword ptr [rsp+68h+arg_20], r12d
0x1800ba60c  mov     rcx, rbp; sesid
0x1800ba60f  mov     [rsp+68h+grbit], r12d; grbit
0x1800ba614  call    cs:__imp_JetMakeKey
0x1800ba61b  nop     dword ptr [rax+rax+00h]
0x1800ba620  mov     ecx, eax
0x1800ba622  lea     rdx, aFindidfromgaps_0; "FindIdFromGaps:JetMakeKey"
0x1800ba629  call    PolicyMapJetError
0x1800ba62e  test    eax, eax
0x1800ba630  jnz     loc_1800BA71E
0x1800ba636  mov     r8d, r12d; grbit
0x1800ba639  mov     rdx, rsi; tableid
0x1800ba63c  mov     rcx, rbp; sesid
0x1800ba63f  call    cs:__imp_JetSeek
0x1800ba646  nop     dword ptr [rax+rax+00h]
0x1800ba64b  mov     ecx, eax
0x1800ba64d  lea     rdx, aFindidfromgaps_1; "FindIdFromGaps:JetSeek"
0x1800ba654  mov     ebx, eax
0x1800ba656  call    PolicyMapJetError
0x1800ba65b  mov     ecx, dword ptr [rsp+68h+arg_20]
0x1800ba662  mov     edx, eax
0x1800ba664  test    eax, eax
0x1800ba666  jnz     loc_1800BA70B
0x1800ba66c  cmp     ecx, r12d
0x1800ba66f  ja      loc_1800BA70B
0x1800ba675  xor     r9d, r9d; grbit
0x1800ba678  mov     r8d, r12d; cRow
0x1800ba67b  mov     rdx, rsi; tableid
0x1800ba67e  mov     rcx, rbp; sesid
0x1800ba681  call    cs:__imp_JetMove
0x1800ba688  nop     dword ptr [rax+rax+00h]
0x1800ba68d  mov     ecx, eax
0x1800ba68f  lea     rdx, aFindidfromgaps_3; "FindIdFromGaps:JetMove"
0x1800ba696  call    PolicyMapJetError
0x1800ba69b  test    eax, eax
0x1800ba69d  jnz     short loc_1800BA71E
0x1800ba69f  and     [rsp+68h+var_30], 0
0x1800ba6a5  lea     r9, [rsp+68h+arg_20]; pvData
0x1800ba6ad  mov     [rsp+68h+var_38], r12d; grbit
0x1800ba6b2  mov     r8d, r14d; columnid
0x1800ba6b5  and     [rsp+68h+var_40], 0
0x1800ba6bb  mov     rdx, rsi; tableid
0x1800ba6be  mov     rcx, rbp; sesid
0x1800ba6c1  mov     [rsp+68h+grbit], 4; cbData
0x1800ba6c9  call    cs:__imp_JetRetrieveColumn
0x1800ba6d0  nop     dword ptr [rax+rax+00h]
0x1800ba6d5  mov     ecx, eax
0x1800ba6d7  lea     rdx, aFindidfromgaps; "FindIdFromGaps:JetRetrieveColumn"
0x1800ba6de  mov     ebx, eax
0x1800ba6e0  call    PolicyMapJetError
0x1800ba6e5  mov     edx, eax
0x1800ba6e7  test    eax, eax
0x1800ba6e9  jnz     short loc_1800BA71E
0x1800ba6eb  mov     eax, [rsp+68h+pvData]
0x1800ba6ef  mov     ecx, dword ptr [rsp+68h+arg_20]
0x1800ba6f6  inc     eax
0x1800ba6f8  cmp     ecx, eax
0x1800ba6fa  ja      short loc_1800BA705
0x1800ba6fc  mov     [rsp+68h+pvData], eax
0x1800ba700  jmp     loc_1800BA66C
0x1800ba705  mov     [rdi], eax
0x1800ba707  xor     eax, eax
0x1800ba709  jmp     short loc_1800BA71E
0x1800ba70b  cmp     ebx, 0FFFFF9BFh
0x1800ba711  jnz     short loc_1800BA71C
0x1800ba713  cmp     ecx, 0FFFFFFFFh
0x1800ba716  jz      short loc_1800BA71C
0x1800ba718  mov     [rdi], ecx
0x1800ba71a  xor     edx, edx
0x1800ba71c  mov     eax, edx
0x1800ba71e  lea     r11, [rsp+68h+var_18]
0x1800ba723  mov     rbx, [r11+20h]
0x1800ba727  mov     rbp, [r11+28h]
0x1800ba72b  mov     rsi, [r11+30h]
0x1800ba72f  mov     rsp, r11
0x1800ba732  pop     r14
0x1800ba734  pop     r12
0x1800ba736  pop     rdi
0x1800ba737  retn
```
