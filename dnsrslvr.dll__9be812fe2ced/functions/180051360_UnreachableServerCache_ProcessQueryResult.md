# UnreachableServerCache_ProcessQueryResult

- ea: `0x180051360`
- end: `0x1800514a6`
- name: `UnreachableServerCache_ProcessQueryResult`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18003ae2c`
- `0x180051360`
- `0x18007f0e0`
- `0x180086700`
- `0x180089010`

## import_xrefs

- `DNSAPI!Query_InProcSetCompletion` at `0x1800513bc`
- `DNSAPI!Query_InProcSetCompletion` at `0x1800513bc`
- `DNSAPI!DeRefQueryBlobEx` at `0x180051495`
- `DNSAPI!DeRefQueryBlobEx` at `0x180051495`
- `DNSAPI!NetInfo_Free` at `0x1800513d9`
- `DNSAPI!NetInfo_Free` at `0x1800513d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051419`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051419`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800513cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800513cc`

## string_xrefs

- `0x180051485`: `UnreachableServerCache_ProcessQueryResult`

## pseudocode

```c
__int64 __fastcall UnreachableServerCache_ProcessQueryResult(__int64 a1)
{
  __int64 result; // rax
  int v3; // ett
  void *v4; // rcx
  __int64 v5; // rdx

  _m_prefetchw((const void *)(a1 + 784));
  LODWORD(result) = *(_DWORD *)(a1 + 784);
  do
  {
    v3 = result;
    result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 784), result | 0x40000, result);
  }
  while ( v3 != (_DWORD)result );
  if ( (result & 0x40000) != 0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      return WPP_SF_(1035, 24, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids);
  }
  else
  {
    Query_InProcSetCompletion(a1);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    NetInfo_Free(*(_QWORD *)(a1 + 1024));
    v4 = *(void **)(a1 + 1152);
    *(_QWORD *)(a1 + 1024) = 0;
    Packet_FreeMsgBuf(v4);
    v5 = *(_QWORD *)(a1 + 296);
    *(_QWORD *)(a1 + 1152) = 0;
    if ( v5 )
      *(_DWORD *)(v5 + 4) = *(_DWORD *)(a1 + 508);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SdiD(
        *(unsigned __int16 *)(a1 + 256),
        25,
        (unsigned int)WPP_63e44181f87f364a710a0a22767b5b92_Traceguids,
        *(_QWORD *)(a1 + 232),
        *(_WORD *)(a1 + 256),
        *(_QWORD *)(a1 + 264),
        *(_DWORD *)(*(_QWORD *)(a1 + 296) + 4LL));
    (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 280))(*(_QWORD *)(a1 + 288), *(_QWORD *)(a1 + 296));
    return DeRefQueryBlobEx(a1, "UnreachableServerCache_ProcessQueryResult", 789, 26);
  }
  return result;
}

```

## disassembly

```asm
0x180051360  mov     [rsp+arg_0], rbx
0x180051365  push    rdi
0x180051366  sub     rsp, 40h
0x18005136a  mov     rbx, rcx
0x18005136d  prefetchw byte ptr [rcx+310h]
0x180051374  mov     eax, [rcx+310h]
0x18005137a  mov     ecx, 40000h
0x18005137f  mov     edx, eax
0x180051381  or      edx, ecx
0x180051383  lock cmpxchg [rbx+310h], edx
0x18005138b  jnz     short loc_18005137F
0x18005138d  test    ecx, eax
0x18005138f  jz      short loc_1800513B9
0x180051391  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180051398  jz      loc_18005149B
0x18005139e  mov     edx, 18h
0x1800513a3  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x1800513aa  mov     ecx, 40Bh
0x1800513af  call    WPP_SF_
0x1800513b4  jmp     loc_18005149B
0x1800513b9  mov     rcx, rbx
0x1800513bc  call    cs:__imp_Query_InProcSetCompletion
0x1800513c2  lea     rdi, [rbx+0B8h]
0x1800513c9  mov     rcx, rdi; lpCriticalSection
0x1800513cc  call    cs:__imp_EnterCriticalSection
0x1800513d2  mov     rcx, [rbx+400h]
0x1800513d9  call    cs:__imp_NetInfo_Free
0x1800513df  mov     rcx, [rbx+480h]; void *
0x1800513e6  mov     qword ptr [rbx+400h], 0
0x1800513f1  call    Packet_FreeMsgBuf
0x1800513f6  mov     rdx, [rbx+128h]
0x1800513fd  mov     qword ptr [rbx+480h], 0
0x180051408  test    rdx, rdx
0x18005140b  jz      short loc_180051416
0x18005140d  mov     eax, [rbx+1FCh]
0x180051413  mov     [rdx+4], eax
0x180051416  mov     rcx, rdi; lpCriticalSection
0x180051419  call    cs:__imp_LeaveCriticalSection
0x18005141f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180051426  jz      short loc_180051465
0x180051428  mov     rax, [rbx+128h]
0x18005142f  lea     r8, WPP_63e44181f87f364a710a0a22767b5b92_Traceguids
0x180051436  movzx   ecx, word ptr [rbx+100h]
0x18005143d  mov     edx, 19h
0x180051442  mov     r9, [rbx+0E8h]
0x180051449  mov     eax, [rax+4]
0x18005144c  mov     [rsp+48h+var_18], eax
0x180051450  mov     rax, [rbx+108h]
0x180051457  mov     [rsp+48h+var_20], rax
0x18005145c  mov     [rsp+48h+var_28], ecx
0x180051460  call    WPP_SF_SdiD
0x180051465  mov     rdx, [rbx+128h]
0x18005146c  mov     rcx, [rbx+120h]
0x180051473  mov     rax, [rbx+118h]
0x18005147a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005147f  mov     r9d, 1Ah
0x180051485  lea     rdx, aUnreachableser; "UnreachableServerCache_ProcessQueryResu"...
0x18005148c  mov     r8d, 315h
0x180051492  mov     rcx, rbx
0x180051495  call    cs:__imp_DeRefQueryBlobEx
0x18005149b  mov     rbx, [rsp+48h+arg_0]
0x1800514a0  add     rsp, 40h
0x1800514a4  pop     rdi
0x1800514a5  retn
```
