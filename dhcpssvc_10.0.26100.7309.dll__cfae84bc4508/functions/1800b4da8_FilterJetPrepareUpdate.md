# FilterJetPrepareUpdate

- ea: `0x1800b4da8`
- end: `0x1800b4f35`
- name: `FilterJetPrepareUpdate`
- size: `397`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800b3b14`

## callees

- `0x1800b4da8`
- `0x1800b4f88`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b4df7`
- `ESENT!JetSetCurrentIndexA` at `0x1800b4df7`
- `ESENT!JetMakeKey` at `0x1800b4e3f`
- `ESENT!JetMakeKey` at `0x1800b4e7d`
- `ESENT!JetMakeKey` at `0x1800b4e3f`
- `ESENT!JetMakeKey` at `0x1800b4e7d`
- `ESENT!JetSeek` at `0x1800b4eaf`
- `ESENT!JetSeek` at `0x1800b4eaf`
- `ESENT!JetPrepareUpdate` at `0x1800b4ef7`
- `ESENT!JetPrepareUpdate` at `0x1800b4ef7`

## string_xrefs

- `0x1800b4e05`: `FilterJetPrepareUpdate`
- `0x1800b4e4d`: `FilterJetPrepareUpdate:MakeKey`
- `0x1800b4f05`: `FilterJetPrepareUpdate:PrepareUpdate`
- `0x1800b4e8b`: `FilterJetPrepareUpdate:MakeKey2`
- `0x1800b4ebd`: `FilterJetPrepareUpdate:Seek`

## pseudocode

```c
__int64 __fastcall FilterJetPrepareUpdate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const void *a4,
        __int64 a5,
        void *pvData,
        unsigned int cbData,
        int a8)
{
  JET_TABLEID v9; // rdi
  JET_SESID v10; // rsi
  unsigned int Key; // ebp
  unsigned int v12; // ebx
  unsigned int v13; // eax

  v9 = FilterGlobalTableHandle;
  v10 = DhcpGlobalJetServerSession;
  if ( a8 )
    goto LABEL_11;
  Key = JetSetCurrentIndexA(DhcpGlobalJetServerSession, FilterGlobalTableHandle, "TypePattern");
  v12 = FilterMapJetError(Key, "FilterJetPrepareUpdate");
  if ( !v12 )
  {
    Key = JetMakeKey(v10, v9, a4, 1u, 1u);
    v12 = FilterMapJetError(Key, "FilterJetPrepareUpdate:MakeKey");
    if ( !v12 )
    {
      if ( !pvData
        || (Key = JetMakeKey(v10, v9, pvData, cbData, 0),
            (v12 = FilterMapJetError(Key, "FilterJetPrepareUpdate:MakeKey2")) == 0) )
      {
        Key = JetSeek(v10, v9, 1u);
        v12 = FilterMapJetError(Key, "FilterJetPrepareUpdate:Seek");
        if ( v12 )
        {
          if ( Key == -1601 )
            v12 = 5;
          goto LABEL_3;
        }
LABEL_11:
        v13 = JetPrepareUpdate(v10, v9, a8 == 0 ? 2 : 0);
        return (unsigned int)FilterMapJetError(v13, "FilterJetPrepareUpdate:PrepareUpdate");
      }
    }
  }
LABEL_3:
  FilterMapJetError(Key, "TypePattern");
  return v12;
}

```

## disassembly

```asm
0x1800b4da8  mov     rax, rsp
0x1800b4dab  mov     [rax+8], rbx
0x1800b4daf  mov     [rax+10h], rbp
0x1800b4db3  mov     [rax+18h], rsi
0x1800b4db7  mov     [rax+20h], rdi
0x1800b4dbb  push    r12
0x1800b4dbd  push    r14
0x1800b4dbf  push    r15
0x1800b4dc1  sub     rsp, 30h
0x1800b4dc5  mov     r14d, [rsp+48h+arg_38]
0x1800b4dcd  mov     r15, r9
0x1800b4dd0  mov     rdi, cs:FilterGlobalTableHandle
0x1800b4dd7  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800b4dde  test    r14d, r14d
0x1800b4de1  jnz     loc_1800B4EE4
0x1800b4de7  lea     r12, aTypepattern; "TypePattern"
0x1800b4dee  mov     rdx, rdi; tableid
0x1800b4df1  mov     r8, r12; szIndexName
0x1800b4df4  mov     rcx, rsi; sesid
0x1800b4df7  call    cs:__imp_JetSetCurrentIndexA
0x1800b4dfe  nop     dword ptr [rax+rax+00h]
0x1800b4e03  mov     ecx, eax
0x1800b4e05  lea     rdx, aFilterjetprepa_4; "FilterJetPrepareUpdate"
0x1800b4e0c  mov     ebp, eax
0x1800b4e0e  call    FilterMapJetError
0x1800b4e13  mov     ebx, eax
0x1800b4e15  test    eax, eax
0x1800b4e17  jz      short loc_1800B4E28
0x1800b4e19  mov     rdx, r12
0x1800b4e1c  mov     ecx, ebp
0x1800b4e1e  call    FilterMapJetError
0x1800b4e23  jmp     loc_1800B4F13
0x1800b4e28  mov     r9d, 1; cbData
0x1800b4e2e  mov     [rsp+48h+grbit], 1; grbit
0x1800b4e36  mov     r8, r15; pvData
0x1800b4e39  mov     rdx, rdi; tableid
0x1800b4e3c  mov     rcx, rsi; sesid
0x1800b4e3f  call    cs:__imp_JetMakeKey
0x1800b4e46  nop     dword ptr [rax+rax+00h]
0x1800b4e4b  mov     ecx, eax
0x1800b4e4d  lea     rdx, aFilterjetprepa_2; "FilterJetPrepareUpdate:MakeKey"
0x1800b4e54  mov     ebp, eax
0x1800b4e56  call    FilterMapJetError
0x1800b4e5b  mov     ebx, eax
0x1800b4e5d  test    eax, eax
0x1800b4e5f  jnz     short loc_1800B4E19
0x1800b4e61  mov     r8, [rsp+48h+pvData]; pvData
0x1800b4e66  test    r8, r8
0x1800b4e69  jz      short loc_1800B4EA3
0x1800b4e6b  mov     r9d, [rsp+48h+cbData]; cbData
0x1800b4e73  mov     rdx, rdi; tableid
0x1800b4e76  and     [rsp+48h+grbit], eax
0x1800b4e7a  mov     rcx, rsi; sesid
0x1800b4e7d  call    cs:__imp_JetMakeKey
0x1800b4e84  nop     dword ptr [rax+rax+00h]
0x1800b4e89  mov     ecx, eax
0x1800b4e8b  lea     rdx, aFilterjetprepa_6; "FilterJetPrepareUpdate:MakeKey2"
0x1800b4e92  mov     ebp, eax
0x1800b4e94  call    FilterMapJetError
0x1800b4e99  mov     ebx, eax
0x1800b4e9b  test    eax, eax
0x1800b4e9d  jnz     loc_1800B4E19
0x1800b4ea3  mov     r8d, 1; grbit
0x1800b4ea9  mov     rdx, rdi; tableid
0x1800b4eac  mov     rcx, rsi; sesid
0x1800b4eaf  call    cs:__imp_JetSeek
0x1800b4eb6  nop     dword ptr [rax+rax+00h]
0x1800b4ebb  mov     ecx, eax
0x1800b4ebd  lea     rdx, aFilterjetprepa_1; "FilterJetPrepareUpdate:Seek"
0x1800b4ec4  mov     ebp, eax
0x1800b4ec6  call    FilterMapJetError
0x1800b4ecb  mov     ebx, eax
0x1800b4ecd  test    eax, eax
0x1800b4ecf  jz      short loc_1800B4EE4
0x1800b4ed1  cmp     ebp, 0FFFFF9BFh
0x1800b4ed7  mov     eax, 5
0x1800b4edc  cmovz   ebx, eax
0x1800b4edf  jmp     loc_1800B4E19
0x1800b4ee4  neg     r14d
0x1800b4ee7  mov     rdx, rdi; tableid
0x1800b4eea  mov     rcx, rsi; sesid
0x1800b4eed  sbb     r8d, r8d
0x1800b4ef0  not     r8d
0x1800b4ef3  and     r8d, 2; prep
0x1800b4ef7  call    cs:__imp_JetPrepareUpdate
0x1800b4efe  nop     dword ptr [rax+rax+00h]
0x1800b4f03  mov     ecx, eax
0x1800b4f05  lea     rdx, aFilterjetprepa_5; "FilterJetPrepareUpdate:PrepareUpdate"
0x1800b4f0c  call    FilterMapJetError
0x1800b4f11  mov     ebx, eax
0x1800b4f13  mov     rbp, [rsp+48h+arg_8]
0x1800b4f18  mov     eax, ebx
0x1800b4f1a  mov     rbx, [rsp+48h+arg_0]
0x1800b4f1f  mov     rsi, [rsp+48h+arg_10]
0x1800b4f24  mov     rdi, [rsp+48h+arg_18]
0x1800b4f29  add     rsp, 30h
0x1800b4f2d  pop     r15
0x1800b4f2f  pop     r14
0x1800b4f31  pop     r12
0x1800b4f33  retn
```
