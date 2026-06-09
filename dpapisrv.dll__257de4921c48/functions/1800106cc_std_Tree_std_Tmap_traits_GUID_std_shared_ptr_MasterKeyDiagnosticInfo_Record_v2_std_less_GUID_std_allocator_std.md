# std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)

- ea: `0x1800106cc`
- end: `0x180010768`
- name: `??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z`
- size: `156`
- prototype: `UUID **__fastcall(__int64, UUID **, UUID *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fe04`
- `0x18000ffb0`
- `0x180010504`
- `0x1800105f0`

## callees

- `0x1800106cc`

## import_xrefs

- `RPCRT4!UuidCompare` at `0x180010727`
- `RPCRT4!UuidCompare` at `0x180010727`

## pseudocode

```c
UUID **__fastcall std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>,0>>::_Find_lower_bound<_GUID>(
        __int64 a1,
        UUID **a2,
        UUID *a3)
{
  UUID *v5; // rcx
  UUID *v6; // rbx
  int v7; // eax
  __int64 Status; // [rsp+30h] [rbp+8h] BYREF

  Status = a1;
  v5 = *(UUID **)(qword_18004C920 + 8);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = (UUID *)qword_18004C920; !v6[1].Data4[1]; v6 = *(UUID **)&v6->Data1 )
  {
    *a2 = v6;
    LODWORD(Status) = 0;
    if ( UuidCompare(v6 + 2, a3, (RPC_STATUS *)&Status) >= 0 )
    {
      a2[2] = v6;
      v7 = 1;
    }
    else
    {
      ++v6;
      v7 = 0;
    }
    *((_DWORD *)a2 + 2) = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x1800106cc  mov     [rsp+arg_8], rbx
0x1800106d1  mov     [rsp+arg_10], rsi
0x1800106d6  mov     [rsp+Status], rcx
0x1800106db  push    rdi
0x1800106dc  sub     rsp, 20h
0x1800106e0  mov     rax, cs:qword_18004C920
0x1800106e7  mov     rsi, r8
0x1800106ea  mov     rdi, rdx
0x1800106ed  mov     rcx, [rax+8]
0x1800106f1  mov     [rdx], rcx
0x1800106f4  mov     rbx, rcx
0x1800106f7  mov     qword ptr [rdx+8], 0
0x1800106ff  mov     rax, cs:qword_18004C920
0x180010706  mov     [rdx+10h], rax
0x18001070a  cmp     byte ptr [rcx+19h], 0
0x18001070e  jnz     short loc_180010749
0x180010710  lea     rcx, [rbx+20h]; Uuid1
0x180010714  mov     [rdi], rbx
0x180010717  lea     r8, [rsp+28h+Status]; Status
0x18001071c  mov     dword ptr [rsp+28h+Status], 0
0x180010724  mov     rdx, rsi; Uuid2
0x180010727  call    cs:__imp_UuidCompare
0x18001072e  nop     dword ptr [rax+rax+00h]
0x180010733  test    eax, eax
0x180010735  jns     short loc_18001075D
0x180010737  add     rbx, 10h
0x18001073b  xor     eax, eax
0x18001073d  mov     [rdi+8], eax
0x180010740  mov     rbx, [rbx]
0x180010743  cmp     byte ptr [rbx+19h], 0
0x180010747  jz      short loc_180010710
0x180010749  mov     rbx, [rsp+28h+arg_8]
0x18001074e  mov     rax, rdi
0x180010751  mov     rsi, [rsp+28h+arg_10]
0x180010756  add     rsp, 20h
0x18001075a  pop     rdi
0x18001075b  retn
0x18001075d  mov     [rdi+10h], rbx
0x180010761  mov     eax, 1
0x180010766  jmp     short loc_18001073D
```
