# GetFilterListSize

- ea: `0x1800b50e0`
- end: `0x1800b5400`
- name: `GetFilterListSize`
- size: `800`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18007811c`
- `0x1800b45f0`

## callees

- `0x1800057f4`
- `0x1800b4944`
- `0x1800b4f88`
- `0x1800b50e0`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b5148`
- `ESENT!JetSetCurrentIndexA` at `0x1800b5148`
- `ESENT!JetSetIndexRange` at `0x1800b5285`
- `ESENT!JetSetIndexRange` at `0x1800b5285`
- `ESENT!JetIndexRecordCount` at `0x1800b52b4`
- `ESENT!JetIndexRecordCount` at `0x1800b52b4`
- `ESENT!JetMakeKey` at `0x1800b5225`
- `ESENT!JetMakeKey` at `0x1800b5259`
- `ESENT!JetMakeKey` at `0x1800b5328`
- `ESENT!JetMakeKey` at `0x1800b5358`
- `ESENT!JetMakeKey` at `0x1800b5225`
- `ESENT!JetMakeKey` at `0x1800b5259`
- `ESENT!JetMakeKey` at `0x1800b5328`
- `ESENT!JetMakeKey` at `0x1800b5358`
- `ESENT!JetSeek` at `0x1800b5380`
- `ESENT!JetSeek` at `0x1800b5380`
- `ESENT!JetMove` at `0x1800b518a`
- `ESENT!JetMove` at `0x1800b52fa`
- `ESENT!JetMove` at `0x1800b518a`
- `ESENT!JetMove` at `0x1800b52fa`
- `KERNEL32!EnterCriticalSection` at `0x1800b512f`
- `KERNEL32!EnterCriticalSection` at `0x1800b512f`
- `KERNEL32!LeaveCriticalSection` at `0x1800b53a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800b53a9`

## string_xrefs

- `0x1800b5198`: `GetFilterListSize:MoveFirst`
- `0x1800b5306`: `GetFilterListSize:MoveNext`

## pseudocode

```c
_UNKNOWN **__fastcall GetFilterListSize(JET_SESID sesid, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  JET_TABLEID v4; // rdi
  unsigned int v8; // esi
  unsigned int v9; // eax
  int Value; // eax
  unsigned int Key; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  const char *v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // eax
  _UNKNOWN **result; // rax
  unsigned int cbData; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v21[3]; // [rsp+34h] [rbp-Ch] BYREF
  __int64 pvData; // [rsp+88h] [rbp+48h] BYREF
  char v23; // [rsp+90h] [rbp+50h] BYREF
  unsigned int pcrec; // [rsp+98h] [rbp+58h] BYREF

  pvData = a2;
  v4 = FilterGlobalTableHandle;
  *a3 = 0;
  *a4 = 0;
  pcrec = 0;
  cbData = 1;
  v21[0] = 1;
  LOBYTE(pvData) = 0;
  v23 = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v8 = JetSetCurrentIndexA(sesid, v4, "ActionTypePattern");
  if ( (unsigned int)FilterMapJetError(v8, "GetFilterListSize:SetCurrentIndex") )
  {
    FilterMapJetError(v8, "ActionTypePattern");
    goto LABEL_20;
  }
  v9 = JetMove(sesid, v4, 0x80000000, 0);
  if ( !(unsigned int)FilterMapJetError(v9, "GetFilterListSize:MoveFirst") )
  {
    do
    {
      Value = FilterJetGetValue(sesid, v4, *(_DWORD *)(FilterGlobalTable + 24), v21);
      if ( Value )
      {
        if ( Value != 232 )
          break;
      }
      else if ( v23 != 1 )
      {
        v15 = JetMove(sesid, v4, 1, 0);
        v16 = "GetFilterListSize:MoveNext";
        continue;
      }
      if ( (unsigned int)FilterJetGetValue(sesid, v4, *(_DWORD *)(FilterGlobalTable + 72), &cbData) )
        break;
      Key = JetMakeKey(sesid, v4, &pvData, cbData, 1u);
      if ( (unsigned int)FilterMapJetError(Key, "GetFilterListSize:MakeKey") )
        break;
      v12 = JetMakeKey(sesid, v4, &v23, v21[0], 0x200u);
      if ( (unsigned int)FilterMapJetError(v12, "GetFilterListSize:MakeKey2") )
        break;
      v13 = JetSetIndexRange(sesid, v4, 3u);
      if ( (unsigned int)FilterMapJetError(v13, "GetFilterListSize:SetIndexRange") )
        break;
      v14 = JetIndexRecordCount(sesid, v4, &pcrec, 0);
      if ( (unsigned int)FilterMapJetError(v14, "GetFilterListSize:IndexRecordCount") )
        break;
      if ( (pvData & 1) != 0 )
        *a3 += pcrec;
      else
        *a4 += pcrec;
      v17 = JetMakeKey(sesid, v4, &pvData, cbData, 1u);
      if ( (unsigned int)FilterMapJetError(v17, "GetFilterListSize:MakeKey") )
        break;
      v18 = JetMakeKey(sesid, v4, &v23, v21[0], 0x200u);
      if ( (unsigned int)FilterMapJetError(v18, "GetFilterListSize:MakeKey2") )
        break;
      v15 = JetSeek(sesid, v4, 0x10u);
      v16 = "GetFilterListSize:Seek";
    }
    while ( !(unsigned int)FilterMapJetError(v15, v16) );
  }
LABEL_20:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    return (_UNKNOWN **)WPP_SF_dD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          24,
                          &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids,
                          (unsigned int)*a3,
                          *a4);
  return result;
}

```

## disassembly

```asm
0x1800b50e0  mov     [rsp-38h+pvData], rdx
0x1800b50e5  push    rbp
0x1800b50e6  push    rbx
0x1800b50e7  push    rsi
0x1800b50e8  push    rdi
0x1800b50e9  push    r13
0x1800b50eb  push    r14
0x1800b50ed  push    r15
0x1800b50ef  mov     rbp, rsp
0x1800b50f2  sub     rsp, 40h
0x1800b50f6  mov     rdi, cs:FilterGlobalTableHandle
0x1800b50fd  mov     rbx, rcx
0x1800b5100  and     dword ptr [r8], 0
0x1800b5104  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b510b  and     dword ptr [r9], 0
0x1800b510f  mov     r13d, 1
0x1800b5115  and     [rbp+pcrec], 0
0x1800b5119  mov     r14, r9
0x1800b511c  mov     [rbp+cbData], r13d
0x1800b5120  mov     r15, r8
0x1800b5123  mov     [rbp+var_C], r13d
0x1800b5127  mov     byte ptr [rbp+pvData], 0
0x1800b512b  mov     [rbp+arg_10], 0
0x1800b512f  call    cs:__imp_EnterCriticalSection
0x1800b5136  nop     dword ptr [rax+rax+00h]
0x1800b513b  lea     r8, aActiontypepatt; "ActionTypePattern"
0x1800b5142  mov     rdx, rdi; tableid
0x1800b5145  mov     rcx, rbx; sesid
0x1800b5148  call    cs:__imp_JetSetCurrentIndexA
0x1800b514f  nop     dword ptr [rax+rax+00h]
0x1800b5154  mov     ecx, eax
0x1800b5156  lea     rdx, aGetfilterlists; "GetFilterListSize:SetCurrentIndex"
0x1800b515d  mov     esi, eax
0x1800b515f  call    FilterMapJetError
0x1800b5164  test    eax, eax
0x1800b5166  jz      short loc_1800B517B
0x1800b5168  lea     rdx, aActiontypepatt; "ActionTypePattern"
0x1800b516f  mov     ecx, esi
0x1800b5171  call    FilterMapJetError
0x1800b5176  jmp     loc_1800B53A2
0x1800b517b  xor     r9d, r9d; grbit
0x1800b517e  mov     r8d, 80000000h; cRow
0x1800b5184  mov     rdx, rdi; tableid
0x1800b5187  mov     rcx, rbx; sesid
0x1800b518a  call    cs:__imp_JetMove
0x1800b5191  nop     dword ptr [rax+rax+00h]
0x1800b5196  mov     ecx, eax
0x1800b5198  lea     rdx, aGetfilterlists_6; "GetFilterListSize:MoveFirst"
0x1800b519f  call    FilterMapJetError
0x1800b51a4  test    eax, eax
0x1800b51a6  jnz     loc_1800B53A2
0x1800b51ac  mov     esi, 200h
0x1800b51b1  mov     r8, cs:FilterGlobalTable
0x1800b51b8  lea     rax, [rbp+var_C]
0x1800b51bc  lea     r9, [rbp+arg_10]
0x1800b51c0  mov     qword ptr [rsp+40h+grbit], rax; unsigned int *
0x1800b51c5  mov     rdx, rdi; tableid
0x1800b51c8  mov     rcx, rbx; sesid
0x1800b51cb  mov     r8d, [r8+18h]; columnid
0x1800b51cf  call    FilterJetGetValue
0x1800b51d4  test    eax, eax
0x1800b51d6  jz      loc_1800B52E4
0x1800b51dc  cmp     eax, 0E8h
0x1800b51e1  jnz     loc_1800B53A2
0x1800b51e7  mov     r8, cs:FilterGlobalTable
0x1800b51ee  lea     rax, [rbp+cbData]
0x1800b51f2  lea     r9, [rbp+pvData]
0x1800b51f6  mov     qword ptr [rsp+40h+grbit], rax; unsigned int *
0x1800b51fb  mov     rdx, rdi; tableid
0x1800b51fe  mov     rcx, rbx; sesid
0x1800b5201  mov     r8d, [r8+48h]; columnid
0x1800b5205  call    FilterJetGetValue
0x1800b520a  test    eax, eax
0x1800b520c  jnz     loc_1800B53A2
0x1800b5212  mov     r9d, [rbp+cbData]; cbData
0x1800b5216  lea     r8, [rbp+pvData]; pvData
0x1800b521a  mov     rdx, rdi; tableid
0x1800b521d  mov     [rsp+40h+grbit], r13d; grbit
0x1800b5222  mov     rcx, rbx; sesid
0x1800b5225  call    cs:__imp_JetMakeKey
0x1800b522c  nop     dword ptr [rax+rax+00h]
0x1800b5231  mov     ecx, eax
0x1800b5233  lea     rdx, aGetfilterlists_5; "GetFilterListSize:MakeKey"
0x1800b523a  call    FilterMapJetError
0x1800b523f  test    eax, eax
0x1800b5241  jnz     loc_1800B53A2
0x1800b5247  mov     r9d, [rbp+var_C]; cbData
0x1800b524b  lea     r8, [rbp+arg_10]; pvData
0x1800b524f  mov     rdx, rdi; tableid
0x1800b5252  mov     [rsp+40h+grbit], esi; grbit
0x1800b5256  mov     rcx, rbx; sesid
0x1800b5259  call    cs:__imp_JetMakeKey
0x1800b5260  nop     dword ptr [rax+rax+00h]
0x1800b5265  mov     ecx, eax
0x1800b5267  lea     rdx, aGetfilterlists_1; "GetFilterListSize:MakeKey2"
0x1800b526e  call    FilterMapJetError
0x1800b5273  test    eax, eax
0x1800b5275  jnz     loc_1800B53A2
0x1800b527b  lea     r8d, [rax+3]; grbit
0x1800b527f  mov     rdx, rdi; tableidSrc
0x1800b5282  mov     rcx, rbx; sesid
0x1800b5285  call    cs:__imp_JetSetIndexRange
0x1800b528c  nop     dword ptr [rax+rax+00h]
0x1800b5291  mov     ecx, eax
0x1800b5293  lea     rdx, aGetfilterlists_0; "GetFilterListSize:SetIndexRange"
0x1800b529a  call    FilterMapJetError
0x1800b529f  test    eax, eax
0x1800b52a1  jnz     loc_1800B53A2
0x1800b52a7  xor     r9d, r9d; crecMax
0x1800b52aa  lea     r8, [rbp+pcrec]; pcrec
0x1800b52ae  mov     rdx, rdi; tableid
0x1800b52b1  mov     rcx, rbx; sesid
0x1800b52b4  call    cs:__imp_JetIndexRecordCount
0x1800b52bb  nop     dword ptr [rax+rax+00h]
0x1800b52c0  mov     ecx, eax
0x1800b52c2  lea     rdx, aGetfilterlists_2; "GetFilterListSize:IndexRecordCount"
0x1800b52c9  call    FilterMapJetError
0x1800b52ce  test    eax, eax
0x1800b52d0  jnz     loc_1800B53A2
0x1800b52d6  mov     eax, [rbp+pcrec]
0x1800b52d9  test    byte ptr [rbp+pvData], r13b
0x1800b52dd  jz      short loc_1800B5312
0x1800b52df  add     [r15], eax
0x1800b52e2  jmp     short loc_1800B5315
0x1800b52e4  cmp     [rbp+arg_10], r13b
0x1800b52e8  jz      loc_1800B51E7
0x1800b52ee  xor     r9d, r9d; grbit
0x1800b52f1  mov     r8d, r13d; cRow
0x1800b52f4  mov     rdx, rdi; tableid
0x1800b52f7  mov     rcx, rbx; sesid
0x1800b52fa  call    cs:__imp_JetMove
0x1800b5301  nop     dword ptr [rax+rax+00h]
0x1800b5306  lea     rdx, aGetfilterlists_3; "GetFilterListSize:MoveNext"
0x1800b530d  jmp     loc_1800B5393
0x1800b5312  add     [r14], eax
0x1800b5315  mov     r9d, [rbp+cbData]; cbData
0x1800b5319  lea     r8, [rbp+pvData]; pvData
0x1800b531d  mov     rdx, rdi; tableid
0x1800b5320  mov     [rsp+40h+grbit], r13d; grbit
0x1800b5325  mov     rcx, rbx; sesid
0x1800b5328  call    cs:__imp_JetMakeKey
0x1800b532f  nop     dword ptr [rax+rax+00h]
0x1800b5334  mov     ecx, eax
0x1800b5336  lea     rdx, aGetfilterlists_5; "GetFilterListSize:MakeKey"
0x1800b533d  call    FilterMapJetError
0x1800b5342  test    eax, eax
0x1800b5344  jnz     short loc_1800B53A2
0x1800b5346  mov     r9d, [rbp+var_C]; cbData
0x1800b534a  lea     r8, [rbp+arg_10]; pvData
0x1800b534e  mov     rdx, rdi; tableid
0x1800b5351  mov     [rsp+40h+grbit], esi; grbit
0x1800b5355  mov     rcx, rbx; sesid
0x1800b5358  call    cs:__imp_JetMakeKey
0x1800b535f  nop     dword ptr [rax+rax+00h]
0x1800b5364  mov     ecx, eax
0x1800b5366  lea     rdx, aGetfilterlists_1; "GetFilterListSize:MakeKey2"
0x1800b536d  call    FilterMapJetError
0x1800b5372  test    eax, eax
0x1800b5374  jnz     short loc_1800B53A2
0x1800b5376  lea     r8d, [rax+10h]; grbit
0x1800b537a  mov     rdx, rdi; tableid
0x1800b537d  mov     rcx, rbx; sesid
0x1800b5380  call    cs:__imp_JetSeek
0x1800b5387  nop     dword ptr [rax+rax+00h]
0x1800b538c  lea     rdx, aGetfilterlists_4; "GetFilterListSize:Seek"
0x1800b5393  mov     ecx, eax
0x1800b5395  call    FilterMapJetError
0x1800b539a  test    eax, eax
0x1800b539c  jz      loc_1800B51B1
0x1800b53a2  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b53a9  call    cs:__imp_LeaveCriticalSection
0x1800b53b0  nop     dword ptr [rax+rax+00h]
0x1800b53b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b53bc  lea     rax, WPP_GLOBAL_Control
0x1800b53c3  cmp     rcx, rax
0x1800b53c6  jz      short loc_1800B53F0
0x1800b53c8  test    dword ptr [rcx+1Ch], 8000h
0x1800b53cf  jz      short loc_1800B53F0
0x1800b53d1  mov     eax, [r14]
0x1800b53d4  lea     r8, WPP_03049d434df230c93e283a47ac7b66e1_Traceguids
0x1800b53db  mov     r9d, [r15]
0x1800b53de  mov     edx, 18h
0x1800b53e3  mov     rcx, [rcx+10h]
0x1800b53e7  mov     [rsp+40h+grbit], eax
0x1800b53eb  call    WPP_SF_dD
0x1800b53f0  add     rsp, 40h
0x1800b53f4  pop     r15
0x1800b53f6  pop     r14
0x1800b53f8  pop     r13
0x1800b53fa  pop     rdi
0x1800b53fb  pop     rsi
0x1800b53fc  pop     rbx
0x1800b53fd  pop     rbp
0x1800b53fe  retn
```
