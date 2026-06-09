# GetFilterListSize

- ea: `0x1800b5f7c`
- end: `0x1800b62a5`
- name: `GetFilterListSize`
- size: `809`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18007800c`
- `0x1800b546c`

## callees

- `0x1800057e0`
- `0x1800b57c0`
- `0x1800b5e24`
- `0x1800b5f7c`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b5fed`
- `ESENT!JetSetCurrentIndexA` at `0x1800b5fed`
- `ESENT!JetSetIndexRange` at `0x1800b612a`
- `ESENT!JetSetIndexRange` at `0x1800b612a`
- `ESENT!JetIndexRecordCount` at `0x1800b6159`
- `ESENT!JetIndexRecordCount` at `0x1800b6159`
- `ESENT!JetMakeKey` at `0x1800b60ca`
- `ESENT!JetMakeKey` at `0x1800b60fe`
- `ESENT!JetMakeKey` at `0x1800b61cd`
- `ESENT!JetMakeKey` at `0x1800b61fd`
- `ESENT!JetMakeKey` at `0x1800b60ca`
- `ESENT!JetMakeKey` at `0x1800b60fe`
- `ESENT!JetMakeKey` at `0x1800b61cd`
- `ESENT!JetMakeKey` at `0x1800b61fd`
- `ESENT!JetSeek` at `0x1800b6225`
- `ESENT!JetSeek` at `0x1800b6225`
- `ESENT!JetMove` at `0x1800b602f`
- `ESENT!JetMove` at `0x1800b619f`
- `ESENT!JetMove` at `0x1800b602f`
- `ESENT!JetMove` at `0x1800b619f`
- `KERNEL32!EnterCriticalSection` at `0x1800b5fd4`
- `KERNEL32!EnterCriticalSection` at `0x1800b5fd4`
- `KERNEL32!LeaveCriticalSection` at `0x1800b624e`
- `KERNEL32!LeaveCriticalSection` at `0x1800b624e`

## string_xrefs

- `0x1800b61ab`: `GetFilterListSize:MoveNext`
- `0x1800b603d`: `GetFilterListSize:MoveFirst`

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
  cbData = 1;
  v21[0] = 1;
  *a4 = 0;
  LOBYTE(pvData) = 0;
  v23 = 0;
  pcrec = 0;
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
0x1800b5f7c  mov     [rsp-38h+pvData], rdx
0x1800b5f81  push    rbp
0x1800b5f82  push    rbx
0x1800b5f83  push    rsi
0x1800b5f84  push    rdi
0x1800b5f85  push    r13
0x1800b5f87  push    r14
0x1800b5f89  push    r15
0x1800b5f8b  mov     rbp, rsp
0x1800b5f8e  sub     rsp, 40h
0x1800b5f92  mov     rdi, cs:FilterGlobalTableHandle
0x1800b5f99  mov     rbx, rcx
0x1800b5f9c  mov     r13d, 1
0x1800b5fa2  mov     dword ptr [r8], 0
0x1800b5fa9  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b5fb0  mov     [rbp+cbData], r13d
0x1800b5fb4  mov     [rbp+var_C], r13d
0x1800b5fb8  mov     r14, r9
0x1800b5fbb  mov     dword ptr [r9], 0
0x1800b5fc2  mov     r15, r8
0x1800b5fc5  mov     byte ptr [rbp+pvData], 0
0x1800b5fc9  mov     [rbp+arg_10], 0
0x1800b5fcd  mov     [rbp+pcrec], 0
0x1800b5fd4  call    cs:__imp_EnterCriticalSection
0x1800b5fdb  nop     dword ptr [rax+rax+00h]
0x1800b5fe0  lea     r8, aActiontypepatt; "ActionTypePattern"
0x1800b5fe7  mov     rdx, rdi; tableid
0x1800b5fea  mov     rcx, rbx; sesid
0x1800b5fed  call    cs:__imp_JetSetCurrentIndexA
0x1800b5ff4  nop     dword ptr [rax+rax+00h]
0x1800b5ff9  mov     ecx, eax
0x1800b5ffb  lea     rdx, aGetfilterlists; "GetFilterListSize:SetCurrentIndex"
0x1800b6002  mov     esi, eax
0x1800b6004  call    FilterMapJetError
0x1800b6009  test    eax, eax
0x1800b600b  jz      short loc_1800B6020
0x1800b600d  lea     rdx, aActiontypepatt; "ActionTypePattern"
0x1800b6014  mov     ecx, esi
0x1800b6016  call    FilterMapJetError
0x1800b601b  jmp     loc_1800B6247
0x1800b6020  xor     r9d, r9d; grbit
0x1800b6023  mov     r8d, 80000000h; cRow
0x1800b6029  mov     rdx, rdi; tableid
0x1800b602c  mov     rcx, rbx; sesid
0x1800b602f  call    cs:__imp_JetMove
0x1800b6036  nop     dword ptr [rax+rax+00h]
0x1800b603b  mov     ecx, eax
0x1800b603d  lea     rdx, aGetfilterlists_6; "GetFilterListSize:MoveFirst"
0x1800b6044  call    FilterMapJetError
0x1800b6049  test    eax, eax
0x1800b604b  jnz     loc_1800B6247
0x1800b6051  mov     esi, 200h
0x1800b6056  mov     r8, cs:FilterGlobalTable
0x1800b605d  lea     rax, [rbp+var_C]
0x1800b6061  lea     r9, [rbp+arg_10]
0x1800b6065  mov     qword ptr [rsp+40h+grbit], rax; unsigned int *
0x1800b606a  mov     rdx, rdi; tableid
0x1800b606d  mov     rcx, rbx; sesid
0x1800b6070  mov     r8d, [r8+18h]; columnid
0x1800b6074  call    FilterJetGetValue
0x1800b6079  test    eax, eax
0x1800b607b  jz      loc_1800B6189
0x1800b6081  cmp     eax, 0E8h
0x1800b6086  jnz     loc_1800B6247
0x1800b608c  mov     r8, cs:FilterGlobalTable
0x1800b6093  lea     rax, [rbp+cbData]
0x1800b6097  lea     r9, [rbp+pvData]
0x1800b609b  mov     qword ptr [rsp+40h+grbit], rax; unsigned int *
0x1800b60a0  mov     rdx, rdi; tableid
0x1800b60a3  mov     rcx, rbx; sesid
0x1800b60a6  mov     r8d, [r8+48h]; columnid
0x1800b60aa  call    FilterJetGetValue
0x1800b60af  test    eax, eax
0x1800b60b1  jnz     loc_1800B6247
0x1800b60b7  mov     r9d, [rbp+cbData]; cbData
0x1800b60bb  lea     r8, [rbp+pvData]; pvData
0x1800b60bf  mov     rdx, rdi; tableid
0x1800b60c2  mov     [rsp+40h+grbit], r13d; grbit
0x1800b60c7  mov     rcx, rbx; sesid
0x1800b60ca  call    cs:__imp_JetMakeKey
0x1800b60d1  nop     dword ptr [rax+rax+00h]
0x1800b60d6  mov     ecx, eax
0x1800b60d8  lea     rdx, aGetfilterlists_5; "GetFilterListSize:MakeKey"
0x1800b60df  call    FilterMapJetError
0x1800b60e4  test    eax, eax
0x1800b60e6  jnz     loc_1800B6247
0x1800b60ec  mov     r9d, [rbp+var_C]; cbData
0x1800b60f0  lea     r8, [rbp+arg_10]; pvData
0x1800b60f4  mov     rdx, rdi; tableid
0x1800b60f7  mov     [rsp+40h+grbit], esi; grbit
0x1800b60fb  mov     rcx, rbx; sesid
0x1800b60fe  call    cs:__imp_JetMakeKey
0x1800b6105  nop     dword ptr [rax+rax+00h]
0x1800b610a  mov     ecx, eax
0x1800b610c  lea     rdx, aGetfilterlists_1; "GetFilterListSize:MakeKey2"
0x1800b6113  call    FilterMapJetError
0x1800b6118  test    eax, eax
0x1800b611a  jnz     loc_1800B6247
0x1800b6120  lea     r8d, [rax+3]; grbit
0x1800b6124  mov     rdx, rdi; tableidSrc
0x1800b6127  mov     rcx, rbx; sesid
0x1800b612a  call    cs:__imp_JetSetIndexRange
0x1800b6131  nop     dword ptr [rax+rax+00h]
0x1800b6136  mov     ecx, eax
0x1800b6138  lea     rdx, aGetfilterlists_0; "GetFilterListSize:SetIndexRange"
0x1800b613f  call    FilterMapJetError
0x1800b6144  test    eax, eax
0x1800b6146  jnz     loc_1800B6247
0x1800b614c  xor     r9d, r9d; crecMax
0x1800b614f  lea     r8, [rbp+pcrec]; pcrec
0x1800b6153  mov     rdx, rdi; tableid
0x1800b6156  mov     rcx, rbx; sesid
0x1800b6159  call    cs:__imp_JetIndexRecordCount
0x1800b6160  nop     dword ptr [rax+rax+00h]
0x1800b6165  mov     ecx, eax
0x1800b6167  lea     rdx, aGetfilterlists_2; "GetFilterListSize:IndexRecordCount"
0x1800b616e  call    FilterMapJetError
0x1800b6173  test    eax, eax
0x1800b6175  jnz     loc_1800B6247
0x1800b617b  mov     eax, [rbp+pcrec]
0x1800b617e  test    byte ptr [rbp+pvData], r13b
0x1800b6182  jz      short loc_1800B61B7
0x1800b6184  add     [r15], eax
0x1800b6187  jmp     short loc_1800B61BA
0x1800b6189  cmp     [rbp+arg_10], r13b
0x1800b618d  jz      loc_1800B608C
0x1800b6193  xor     r9d, r9d; grbit
0x1800b6196  mov     r8d, r13d; cRow
0x1800b6199  mov     rdx, rdi; tableid
0x1800b619c  mov     rcx, rbx; sesid
0x1800b619f  call    cs:__imp_JetMove
0x1800b61a6  nop     dword ptr [rax+rax+00h]
0x1800b61ab  lea     rdx, aGetfilterlists_3; "GetFilterListSize:MoveNext"
0x1800b61b2  jmp     loc_1800B6238
0x1800b61b7  add     [r14], eax
0x1800b61ba  mov     r9d, [rbp+cbData]; cbData
0x1800b61be  lea     r8, [rbp+pvData]; pvData
0x1800b61c2  mov     rdx, rdi; tableid
0x1800b61c5  mov     [rsp+40h+grbit], r13d; grbit
0x1800b61ca  mov     rcx, rbx; sesid
0x1800b61cd  call    cs:__imp_JetMakeKey
0x1800b61d4  nop     dword ptr [rax+rax+00h]
0x1800b61d9  mov     ecx, eax
0x1800b61db  lea     rdx, aGetfilterlists_5; "GetFilterListSize:MakeKey"
0x1800b61e2  call    FilterMapJetError
0x1800b61e7  test    eax, eax
0x1800b61e9  jnz     short loc_1800B6247
0x1800b61eb  mov     r9d, [rbp+var_C]; cbData
0x1800b61ef  lea     r8, [rbp+arg_10]; pvData
0x1800b61f3  mov     rdx, rdi; tableid
0x1800b61f6  mov     [rsp+40h+grbit], esi; grbit
0x1800b61fa  mov     rcx, rbx; sesid
0x1800b61fd  call    cs:__imp_JetMakeKey
0x1800b6204  nop     dword ptr [rax+rax+00h]
0x1800b6209  mov     ecx, eax
0x1800b620b  lea     rdx, aGetfilterlists_1; "GetFilterListSize:MakeKey2"
0x1800b6212  call    FilterMapJetError
0x1800b6217  test    eax, eax
0x1800b6219  jnz     short loc_1800B6247
0x1800b621b  lea     r8d, [rax+10h]; grbit
0x1800b621f  mov     rdx, rdi; tableid
0x1800b6222  mov     rcx, rbx; sesid
0x1800b6225  call    cs:__imp_JetSeek
0x1800b622c  nop     dword ptr [rax+rax+00h]
0x1800b6231  lea     rdx, aGetfilterlists_4; "GetFilterListSize:Seek"
0x1800b6238  mov     ecx, eax
0x1800b623a  call    FilterMapJetError
0x1800b623f  test    eax, eax
0x1800b6241  jz      loc_1800B6056
0x1800b6247  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b624e  call    cs:__imp_LeaveCriticalSection
0x1800b6255  nop     dword ptr [rax+rax+00h]
0x1800b625a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6261  lea     rax, WPP_GLOBAL_Control
0x1800b6268  cmp     rcx, rax
0x1800b626b  jz      short loc_1800B6295
0x1800b626d  test    dword ptr [rcx+1Ch], 8000h
0x1800b6274  jz      short loc_1800B6295
0x1800b6276  mov     eax, [r14]
0x1800b6279  lea     r8, WPP_03049d434df230c93e283a47ac7b66e1_Traceguids
0x1800b6280  mov     r9d, [r15]
0x1800b6283  mov     edx, 18h
0x1800b6288  mov     rcx, [rcx+10h]
0x1800b628c  mov     [rsp+40h+grbit], eax
0x1800b6290  call    WPP_SF_dD
0x1800b6295  add     rsp, 40h
0x1800b6299  pop     r15
0x1800b629b  pop     r14
0x1800b629d  pop     r13
0x1800b629f  pop     rdi
0x1800b62a0  pop     rsi
0x1800b62a1  pop     rbx
0x1800b62a2  pop     rbp
0x1800b62a3  retn
```
