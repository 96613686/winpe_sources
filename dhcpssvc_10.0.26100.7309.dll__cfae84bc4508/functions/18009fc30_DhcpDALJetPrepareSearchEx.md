# DhcpDALJetPrepareSearchEx

- ea: `0x18009fc30`
- end: `0x18009fd23`
- name: `DhcpDALJetPrepareSearchEx`
- size: `243`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, __int64, int, JET_GRBIT)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180050708`
- `0x18008411c`
- `0x18009fd2c`
- `0x1800a0d48`
- `0x1800be94c`
- `0x1800bf258`
- `0x1800c44ac`

## callees

- `0x18009fc30`
- `0x18009fee0`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x18009fc4e`
- `ESENT!JetSetCurrentIndex` at `0x18009fc4e`
- `ESENT!JetMakeKey` at `0x18009fcbd`
- `ESENT!JetMakeKey` at `0x18009fcbd`
- `ESENT!JetSeek` at `0x18009fcf2`
- `ESENT!JetSeek` at `0x18009fcf2`
- `ESENT!JetMove` at `0x18009fc83`
- `ESENT!JetMove` at `0x18009fc83`

## string_xrefs

- `0x18009fcfe`: `DhcpDALJetPrepareSearchEx:Move/Seek`

## pseudocode

```c
__int64 __fastcall DhcpDALJetPrepareSearchEx(
        JET_SESID sesid,
        JET_TABLEID tableid,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        JET_GRBIT a7)
{
  unsigned int v10; // eax
  __int64 result; // rax
  unsigned int v12; // eax
  const char *v13; // rdx
  unsigned int v14; // ebx
  unsigned int *v15; // rdi
  unsigned int Key; // eax

  v10 = JetSetCurrentIndex(sesid, tableid, a3);
  result = DhcpDALMapJetError(v10, "DhcpDALJetPrepareSearchEx");
  if ( !(_DWORD)result )
  {
    if ( a4 )
    {
      v12 = JetMove(sesid, tableid, 0x80000000, 0);
      v13 = "DhcpDALJetPrepareSearchEx:MakeKey";
      return DhcpDALMapJetError(v12, v13);
    }
    v14 = 0;
    if ( !a6 )
    {
LABEL_8:
      v12 = JetSeek(sesid, tableid, a7);
      v13 = "DhcpDALJetPrepareSearchEx:Move/Seek";
      return DhcpDALMapJetError(v12, v13);
    }
    v15 = (unsigned int *)(a5 + 8);
    while ( 1 )
    {
      Key = JetMakeKey(sesid, tableid, *((const void **)v15 - 1), *v15, v15[1]);
      result = DhcpDALMapJetError(Key, "DhcpDALJetPrepareSearchEx:MakeKey");
      if ( (_DWORD)result )
        break;
      ++v14;
      v15 += 4;
      if ( v14 >= a6 )
        goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009fc30  mov     [rsp+arg_0], rbx
0x18009fc35  mov     [rsp+arg_8], rbp
0x18009fc3a  mov     [rsp+arg_10], rdi
0x18009fc3f  push    r14
0x18009fc41  sub     rsp, 30h
0x18009fc45  mov     ebx, r9d
0x18009fc48  mov     rbp, rdx
0x18009fc4b  mov     r14, rcx
0x18009fc4e  call    cs:__imp_JetSetCurrentIndex
0x18009fc55  nop     dword ptr [rax+rax+00h]
0x18009fc5a  mov     ecx, eax
0x18009fc5c  lea     rdx, aDhcpdaljetprep_0; "DhcpDALJetPrepareSearchEx"
0x18009fc63  call    DhcpDALMapJetError
0x18009fc68  test    eax, eax
0x18009fc6a  jnz     loc_18009FD0C
0x18009fc70  test    ebx, ebx
0x18009fc72  jz      short loc_18009FC98
0x18009fc74  xor     r9d, r9d; grbit
0x18009fc77  mov     r8d, 80000000h; cRow
0x18009fc7d  mov     rdx, rbp; tableid
0x18009fc80  mov     rcx, r14; sesid
0x18009fc83  call    cs:__imp_JetMove
0x18009fc8a  nop     dword ptr [rax+rax+00h]
0x18009fc8f  lea     rdx, aDhcpdaljetprep_1; "DhcpDALJetPrepareSearchEx:MakeKey"
0x18009fc96  jmp     short loc_18009FD05
0x18009fc98  xor     ebx, ebx
0x18009fc9a  cmp     [rsp+38h+arg_28], ebx
0x18009fc9e  jbe     short loc_18009FCE7
0x18009fca0  mov     rdi, [rsp+38h+arg_20]
0x18009fca5  add     rdi, 8
0x18009fca9  mov     eax, [rdi+4]
0x18009fcac  mov     rdx, rbp; tableid
0x18009fcaf  mov     r9d, [rdi]; cbData
0x18009fcb2  mov     rcx, r14; sesid
0x18009fcb5  mov     r8, [rdi-8]; pvData
0x18009fcb9  mov     [rsp+38h+grbit], eax; grbit
0x18009fcbd  call    cs:__imp_JetMakeKey
0x18009fcc4  nop     dword ptr [rax+rax+00h]
0x18009fcc9  mov     ecx, eax
0x18009fccb  lea     rdx, aDhcpdaljetprep_1; "DhcpDALJetPrepareSearchEx:MakeKey"
0x18009fcd2  call    DhcpDALMapJetError
0x18009fcd7  test    eax, eax
0x18009fcd9  jnz     short loc_18009FD0C
0x18009fcdb  inc     ebx
0x18009fcdd  add     rdi, 10h
0x18009fce1  cmp     ebx, [rsp+38h+arg_28]
0x18009fce5  jb      short loc_18009FCA9
0x18009fce7  mov     r8d, [rsp+38h+arg_30]; grbit
0x18009fcec  mov     rdx, rbp; tableid
0x18009fcef  mov     rcx, r14; sesid
0x18009fcf2  call    cs:__imp_JetSeek
0x18009fcf9  nop     dword ptr [rax+rax+00h]
0x18009fcfe  lea     rdx, aDhcpdaljetprep; "DhcpDALJetPrepareSearchEx:Move/Seek"
0x18009fd05  mov     ecx, eax
0x18009fd07  call    DhcpDALMapJetError
0x18009fd0c  mov     rbx, [rsp+38h+arg_0]
0x18009fd11  mov     rbp, [rsp+38h+arg_8]
0x18009fd16  mov     rdi, [rsp+38h+arg_10]
0x18009fd1b  add     rsp, 30h
0x18009fd1f  pop     r14
0x18009fd21  retn
```
