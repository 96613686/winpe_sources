# R_ReadCacheRecords

- ea: `0x180050650`
- end: `0x18005088f`
- name: `R_ReadCacheRecords`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation`

## callees

- `0x1800078e8`
- `0x18000f7ac`
- `0x1800111d4`
- `0x180012bb0`
- `0x180015a90`
- `0x18002a1b0`
- `0x18002b2f0`
- `0x180039f20`
- `0x180050650`
- `0x18007af64`
- `0x18008841c`
- `0x180088578`

## import_xrefs

- `DNSAPI!DnsRecordSetCopyEx` at `0x1800507a4`
- `DNSAPI!DnsRecordSetCopyEx` at `0x1800507a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050801`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005083c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050801`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005083c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800506bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800506bf`

## pseudocode

```c
__int64 __fastcall R_ReadCacheRecords(int a1, int a2, __int64 *a3)
{
  __int64 v3; // rdi
  unsigned int v5; // r13d
  unsigned int v6; // ebx
  _QWORD *p_pNext; // r15
  unsigned int v8; // r12d
  __int64 v9; // rsi
  _QWORD *v10; // r14
  __int64 PreferedEntry; // rax
  __int64 v12; // r14
  PDNS_RECORD v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v17; // [rsp+80h] [rbp+18h]
  __int64 v18; // [rsp+88h] [rbp+20h]

  v3 = 0;
  v5 = 0;
  v17 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qiq(a1, 13, (_DWORD)a3, a1, a2, (__int64)a3);
  if ( !a3 )
  {
    v6 = 87;
    goto LABEL_33;
  }
  *a3 = 0;
  if ( !(unsigned int)Rpc_AccessCheck(2u) )
  {
    v6 = 5;
    goto LABEL_33;
  }
  EnterCriticalSection(&g_csCache);
  v6 = Cache_InitializeIfNotInitialized();
  if ( v6 )
    goto LABEL_27;
  p_pNext = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_dd(1035, 14, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids, (unsigned int)g_EntryCount, g_RecordSetCount);
  v8 = 0;
LABEL_10:
  if ( v8 >= g_HashTableSize )
  {
    if ( g_fVelocityFixTtlGetCache )
    {
      v14 = Dns_RecordListScreenEx(v3, 16);
      v3 = v14;
      if ( v14 )
        Cache_RestoreRecordListForRpc(v14, (unsigned int)g_CurrentCacheTime);
    }
    LeaveCriticalSection(&g_csCache);
    *a3 = v3;
    v3 = 0;
    goto LABEL_33;
  }
  v9 = 16LL * v8;
  v18 = v9;
  v10 = *(_QWORD **)((char *)g_HashTable + v9);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v10 == (_QWORD *)((char *)g_HashTable + v9) )
      {
        ++v8;
        goto LABEL_10;
      }
      if ( (unsigned int)Cache_IsInvalidNetworkVersion(v10 - 1) )
      {
        v10 = (_QWORD *)*v10;
        goto LABEL_15;
      }
      v9 = v18;
      PreferedEntry = GetPreferedEntry(v10 - 1, (char *)g_HashTable + v18);
      v12 = PreferedEntry;
      if ( !g_fVelocityFixTtlGetCache || (unsigned int)Cache_IsRecordTtlValid(*(_QWORD *)(PreferedEntry + 120)) )
        break;
      v10 = *(_QWORD **)(v12 + 8);
LABEL_15:
      v5 = v17;
    }
    v13 = DnsRecordSetCopyEx(*(PDNS_RECORD *)(v12 + 120), DnsCharSetUnicode, DnsCharSetUnicode);
    if ( !v13 )
      break;
    v6 = 0;
    if ( p_pNext )
      *p_pNext = v13;
    else
      v3 = (__int64)v13;
    do
    {
      p_pNext = &v13->pNext;
      v13 = v13->pNext;
    }
    while ( v13 );
    v10 = *(_QWORD **)(v12 + 8);
    v5 = ++v17;
  }
  v5 = v17;
  v6 = 87;
LABEL_27:
  LeaveCriticalSection(&g_csCache);
LABEL_33:
  Dns_RecordListFree(v3);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Dd(v15, 15, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids, v5, v6);
  return v6;
}

```

## disassembly

```asm
0x180050650  mov     [rsp+arg_0], rbx
0x180050655  push    rbp
0x180050656  push    rsi
0x180050657  push    rdi
0x180050658  push    r12
0x18005065a  push    r13
0x18005065c  push    r14
0x18005065e  push    r15
0x180050660  sub     rsp, 30h
0x180050664  xor     edi, edi
0x180050666  mov     rbp, r8
0x180050669  xor     r13d, r13d
0x18005066c  mov     rax, rdx
0x18005066f  mov     [rsp+68h+arg_10], r13d
0x180050677  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005067e  jz      short loc_180050695
0x180050680  mov     [rsp+68h+var_40], r8
0x180050685  lea     edx, [rdi+0Dh]
0x180050688  mov     r9, rcx
0x18005068b  mov     [rsp+68h+var_48], rax
0x180050690  call    WPP_SF_qiq
0x180050695  test    rbp, rbp
0x180050698  jz      loc_18005084A
0x18005069e  mov     ecx, 2
0x1800506a3  mov     [rbp+0], rdi
0x1800506a7  call    Rpc_AccessCheck
0x1800506ac  test    eax, eax
0x1800506ae  jnz     short loc_1800506B8
0x1800506b0  lea     ebx, [rax+5]
0x1800506b3  jmp     loc_18005084F
0x1800506b8  lea     rcx, g_csCache; lpCriticalSection
0x1800506bf  call    cs:__imp_EnterCriticalSection
0x1800506c5  call    Cache_InitializeIfNotInitialized
0x1800506ca  mov     ebx, eax
0x1800506cc  test    eax, eax
0x1800506ce  jnz     loc_1800507FA
0x1800506d4  xor     r15d, r15d
0x1800506d7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800506de  jz      short loc_180050707
0x1800506e0  mov     r8d, cs:g_RecordSetCount
0x1800506e7  lea     edx, [rax+0Eh]
0x1800506ea  mov     r9d, cs:g_EntryCount
0x1800506f1  mov     ecx, 40Bh
0x1800506f6  mov     dword ptr [rsp+68h+var_48], r8d
0x1800506fb  lea     r8, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids
0x180050702  call    WPP_SF_dd
0x180050707  xor     r12d, r12d
0x18005070a  cmp     r12d, cs:g_HashTableSize
0x180050711  jnb     loc_180050809
0x180050717  mov     rax, cs:g_HashTable
0x18005071e  mov     esi, r12d
0x180050721  shl     rsi, 4
0x180050725  mov     [rsp+68h+arg_18], rsi
0x18005072d  mov     r14, [rsi+rax]
0x180050731  mov     rcx, cs:g_HashTable
0x180050738  add     rcx, rsi
0x18005073b  cmp     r14, rcx
0x18005073e  jz      loc_1800507E5
0x180050744  lea     rcx, [r14-8]
0x180050748  call    Cache_IsInvalidNetworkVersion
0x18005074d  test    eax, eax
0x18005074f  jz      short loc_18005075E
0x180050751  mov     r14, [r14]
0x180050754  mov     r13d, [rsp+68h+arg_10]
0x18005075c  jmp     short loc_180050731
0x18005075e  mov     rdx, cs:g_HashTable
0x180050765  lea     rcx, [r14-8]
0x180050769  mov     rsi, [rsp+68h+arg_18]
0x180050771  add     rdx, rsi
0x180050774  call    GetPreferedEntry
0x180050779  cmp     cs:g_fVelocityFixTtlGetCache, 0
0x180050780  mov     r14, rax
0x180050783  jz      short loc_180050798
0x180050785  mov     rcx, [rax+78h]
0x180050789  call    Cache_IsRecordTtlValid
0x18005078e  test    eax, eax
0x180050790  jnz     short loc_180050798
0x180050792  mov     r14, [r14+8]
0x180050796  jmp     short loc_180050754
0x180050798  mov     rcx, [r14+78h]; pRecordSet
0x18005079c  mov     edx, 1; CharSetIn
0x1800507a1  mov     r8d, edx; CharSetOut
0x1800507a4  call    cs:__imp_DnsRecordSetCopyEx
0x1800507aa  test    rax, rax
0x1800507ad  jz      short loc_1800507ED
0x1800507af  xor     ebx, ebx
0x1800507b1  test    r15, r15
0x1800507b4  jz      short loc_1800507BB
0x1800507b6  mov     [r15], rax
0x1800507b9  jmp     short loc_1800507BE
0x1800507bb  mov     rdi, rax
0x1800507be  mov     r15, rax
0x1800507c1  mov     rax, [rax]
0x1800507c4  test    rax, rax
0x1800507c7  jnz     short loc_1800507BE
0x1800507c9  mov     r13d, [rsp+68h+arg_10]
0x1800507d1  mov     r14, [r14+8]
0x1800507d5  inc     r13d
0x1800507d8  mov     [rsp+68h+arg_10], r13d
0x1800507e0  jmp     loc_180050731
0x1800507e5  inc     r12d
0x1800507e8  jmp     loc_18005070A
0x1800507ed  mov     r13d, [rsp+68h+arg_10]
0x1800507f5  mov     ebx, 57h ; 'W'
0x1800507fa  lea     rcx, g_csCache; lpCriticalSection
0x180050801  call    cs:__imp_LeaveCriticalSection
0x180050807  jmp     short loc_18005084F
0x180050809  cmp     cs:g_fVelocityFixTtlGetCache, 0
0x180050810  jz      short loc_180050835
0x180050812  mov     edx, 10h
0x180050817  mov     rcx, rdi
0x18005081a  call    Dns_RecordListScreenEx
0x18005081f  mov     rdi, rax
0x180050822  test    rax, rax
0x180050825  jz      short loc_180050835
0x180050827  mov     edx, cs:g_CurrentCacheTime
0x18005082d  mov     rcx, rax
0x180050830  call    Cache_RestoreRecordListForRpc
0x180050835  lea     rcx, g_csCache; lpCriticalSection
0x18005083c  call    cs:__imp_LeaveCriticalSection
0x180050842  mov     [rbp+0], rdi
0x180050846  xor     edi, edi
0x180050848  jmp     short loc_18005084F
0x18005084a  mov     ebx, 57h ; 'W'
0x18005084f  mov     rcx, rdi
0x180050852  call    Dns_RecordListFree
0x180050857  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005085e  jz      short loc_180050878
0x180050860  mov     edx, 0Fh
0x180050865  mov     dword ptr [rsp+68h+var_48], ebx
0x180050869  mov     r9d, r13d
0x18005086c  lea     r8, WPP_19079b4fdf5130d1a4d307ec0fef1a81_Traceguids
0x180050873  call    WPP_SF_Dd
0x180050878  mov     eax, ebx
0x18005087a  mov     rbx, [rsp+68h+arg_0]
0x18005087f  add     rsp, 30h
0x180050883  pop     r15
0x180050885  pop     r14
0x180050887  pop     r13
0x180050889  pop     r12
0x18005088b  pop     rdi
0x18005088c  pop     rsi
0x18005088d  pop     rbp
0x18005088e  retn
```
