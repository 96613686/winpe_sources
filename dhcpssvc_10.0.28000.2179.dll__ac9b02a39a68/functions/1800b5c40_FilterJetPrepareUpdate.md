# FilterJetPrepareUpdate

- ea: `0x1800b5c40`
- end: `0x1800b5dcd`
- name: `FilterJetPrepareUpdate`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800b4984`

## callees

- `0x1800b5c40`
- `0x1800b5e24`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b5c8f`
- `ESENT!JetSetCurrentIndexA` at `0x1800b5c8f`
- `ESENT!JetMakeKey` at `0x1800b5cd7`
- `ESENT!JetMakeKey` at `0x1800b5d15`
- `ESENT!JetMakeKey` at `0x1800b5cd7`
- `ESENT!JetMakeKey` at `0x1800b5d15`
- `ESENT!JetSeek` at `0x1800b5d47`
- `ESENT!JetSeek` at `0x1800b5d47`
- `ESENT!JetPrepareUpdate` at `0x1800b5d8f`
- `ESENT!JetPrepareUpdate` at `0x1800b5d8f`

## string_xrefs

- `0x1800b5d55`: `FilterJetPrepareUpdate:Seek`
- `0x1800b5d23`: `FilterJetPrepareUpdate:MakeKey2`
- `0x1800b5ce5`: `FilterJetPrepareUpdate:MakeKey`
- `0x1800b5c9d`: `FilterJetPrepareUpdate`
- `0x1800b5d9d`: `FilterJetPrepareUpdate:PrepareUpdate`

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
0x1800b5c40  mov     rax, rsp
0x1800b5c43  mov     [rax+8], rbx
0x1800b5c47  mov     [rax+10h], rbp
0x1800b5c4b  mov     [rax+18h], rsi
0x1800b5c4f  mov     [rax+20h], rdi
0x1800b5c53  push    r12
0x1800b5c55  push    r14
0x1800b5c57  push    r15
0x1800b5c59  sub     rsp, 30h
0x1800b5c5d  mov     r14d, [rsp+48h+arg_38]
0x1800b5c65  mov     r15, r9
0x1800b5c68  mov     rdi, cs:FilterGlobalTableHandle
0x1800b5c6f  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800b5c76  test    r14d, r14d
0x1800b5c79  jnz     loc_1800B5D7C
0x1800b5c7f  lea     r12, aTypepattern; "TypePattern"
0x1800b5c86  mov     rdx, rdi; tableid
0x1800b5c89  mov     r8, r12; szIndexName
0x1800b5c8c  mov     rcx, rsi; sesid
0x1800b5c8f  call    cs:__imp_JetSetCurrentIndexA
0x1800b5c96  nop     dword ptr [rax+rax+00h]
0x1800b5c9b  mov     ecx, eax
0x1800b5c9d  lea     rdx, aFilterjetprepa_4; "FilterJetPrepareUpdate"
0x1800b5ca4  mov     ebp, eax
0x1800b5ca6  call    FilterMapJetError
0x1800b5cab  mov     ebx, eax
0x1800b5cad  test    eax, eax
0x1800b5caf  jz      short loc_1800B5CC0
0x1800b5cb1  mov     rdx, r12
0x1800b5cb4  mov     ecx, ebp
0x1800b5cb6  call    FilterMapJetError
0x1800b5cbb  jmp     loc_1800B5DAB
0x1800b5cc0  mov     r9d, 1; cbData
0x1800b5cc6  mov     [rsp+48h+grbit], 1; grbit
0x1800b5cce  mov     r8, r15; pvData
0x1800b5cd1  mov     rdx, rdi; tableid
0x1800b5cd4  mov     rcx, rsi; sesid
0x1800b5cd7  call    cs:__imp_JetMakeKey
0x1800b5cde  nop     dword ptr [rax+rax+00h]
0x1800b5ce3  mov     ecx, eax
0x1800b5ce5  lea     rdx, aFilterjetprepa_2; "FilterJetPrepareUpdate:MakeKey"
0x1800b5cec  mov     ebp, eax
0x1800b5cee  call    FilterMapJetError
0x1800b5cf3  mov     ebx, eax
0x1800b5cf5  test    eax, eax
0x1800b5cf7  jnz     short loc_1800B5CB1
0x1800b5cf9  mov     r8, [rsp+48h+pvData]; pvData
0x1800b5cfe  test    r8, r8
0x1800b5d01  jz      short loc_1800B5D3B
0x1800b5d03  mov     r9d, [rsp+48h+cbData]; cbData
0x1800b5d0b  mov     rdx, rdi; tableid
0x1800b5d0e  mov     rcx, rsi; sesid
0x1800b5d11  mov     [rsp+48h+grbit], eax; grbit
0x1800b5d15  call    cs:__imp_JetMakeKey
0x1800b5d1c  nop     dword ptr [rax+rax+00h]
0x1800b5d21  mov     ecx, eax
0x1800b5d23  lea     rdx, aFilterjetprepa_6; "FilterJetPrepareUpdate:MakeKey2"
0x1800b5d2a  mov     ebp, eax
0x1800b5d2c  call    FilterMapJetError
0x1800b5d31  mov     ebx, eax
0x1800b5d33  test    eax, eax
0x1800b5d35  jnz     loc_1800B5CB1
0x1800b5d3b  mov     r8d, 1; grbit
0x1800b5d41  mov     rdx, rdi; tableid
0x1800b5d44  mov     rcx, rsi; sesid
0x1800b5d47  call    cs:__imp_JetSeek
0x1800b5d4e  nop     dword ptr [rax+rax+00h]
0x1800b5d53  mov     ecx, eax
0x1800b5d55  lea     rdx, aFilterjetprepa_1; "FilterJetPrepareUpdate:Seek"
0x1800b5d5c  mov     ebp, eax
0x1800b5d5e  call    FilterMapJetError
0x1800b5d63  mov     ebx, eax
0x1800b5d65  test    eax, eax
0x1800b5d67  jz      short loc_1800B5D7C
0x1800b5d69  cmp     ebp, 0FFFFF9BFh
0x1800b5d6f  mov     eax, 5
0x1800b5d74  cmovz   ebx, eax
0x1800b5d77  jmp     loc_1800B5CB1
0x1800b5d7c  neg     r14d
0x1800b5d7f  mov     rdx, rdi; tableid
0x1800b5d82  mov     rcx, rsi; sesid
0x1800b5d85  sbb     r8d, r8d
0x1800b5d88  not     r8d
0x1800b5d8b  and     r8d, 2; prep
0x1800b5d8f  call    cs:__imp_JetPrepareUpdate
0x1800b5d96  nop     dword ptr [rax+rax+00h]
0x1800b5d9b  mov     ecx, eax
0x1800b5d9d  lea     rdx, aFilterjetprepa_5; "FilterJetPrepareUpdate:PrepareUpdate"
0x1800b5da4  call    FilterMapJetError
0x1800b5da9  mov     ebx, eax
0x1800b5dab  mov     rbp, [rsp+48h+arg_8]
0x1800b5db0  mov     eax, ebx
0x1800b5db2  mov     rbx, [rsp+48h+arg_0]
0x1800b5db7  mov     rsi, [rsp+48h+arg_10]
0x1800b5dbc  mov     rdi, [rsp+48h+arg_18]
0x1800b5dc1  add     rsp, 30h
0x1800b5dc5  pop     r15
0x1800b5dc7  pop     r14
0x1800b5dc9  pop     r12
0x1800b5dcb  retn
```
