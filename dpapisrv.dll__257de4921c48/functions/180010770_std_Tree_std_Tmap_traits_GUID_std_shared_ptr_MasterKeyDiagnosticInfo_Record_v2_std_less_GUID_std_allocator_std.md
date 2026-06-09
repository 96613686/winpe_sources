# std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>,void *> * const,_GUID const &)

- ea: `0x180010770`
- end: `0x1800107b2`
- name: `??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@PEAX@1@AEBU_GUID@@@Z`
- size: `66`
- prototype: `bool __fastcall(__int64, UUID *, UUID *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fe04`
- `0x18000ffb0`
- `0x180010504`
- `0x1800105f0`

## callees

- `0x180010770`

## import_xrefs

- `RPCRT4!UuidCompare` at `0x180010796`
- `RPCRT4!UuidCompare` at `0x180010796`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>,0>>::_Lower_bound_duplicate<_GUID>(
        __int64 a1,
        UUID *a2,
        UUID *a3)
{
  bool result; // al
  __int64 Status; // [rsp+30h] [rbp+8h] BYREF

  Status = a1;
  result = 0;
  if ( !a2[1].Data4[1] )
  {
    LODWORD(Status) = 0;
    if ( UuidCompare(a3, a2 + 2, (RPC_STATUS *)&Status) >= 0 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180010770  mov     [rsp+Status], rcx
0x180010775  sub     rsp, 28h
0x180010779  cmp     byte ptr [rdx+19h], 0
0x18001077d  mov     rax, r8
0x180010780  jnz     short loc_1800107A6
0x180010782  add     rdx, 20h ; ' '; Uuid2
0x180010786  mov     dword ptr [rsp+28h+Status], 0
0x18001078e  lea     r8, [rsp+28h+Status]; Status
0x180010793  mov     rcx, rax; Uuid1
0x180010796  call    cs:__imp_UuidCompare
0x18001079d  nop     dword ptr [rax+rax+00h]
0x1800107a2  test    eax, eax
0x1800107a4  jns     short loc_1800107AE
0x1800107a6  xor     al, al
0x1800107a8  add     rsp, 28h
0x1800107ac  retn
0x1800107ae  mov     al, 1
0x1800107b0  jmp     short loc_1800107A8
```
