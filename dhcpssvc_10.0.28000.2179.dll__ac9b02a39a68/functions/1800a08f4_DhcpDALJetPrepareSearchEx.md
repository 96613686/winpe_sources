# DhcpDALJetPrepareSearchEx

- ea: `0x1800a08f4`
- end: `0x1800a09e7`
- name: `DhcpDALJetPrepareSearchEx`
- size: `243`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, __int64, int, JET_GRBIT)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800503c8`
- `0x180083fb0`
- `0x1800a09f0`
- `0x1800a1a38`
- `0x1800bf964`
- `0x1800c0270`
- `0x1800c54a8`

## callees

- `0x1800a08f4`
- `0x1800a0bac`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x1800a0912`
- `ESENT!JetSetCurrentIndex` at `0x1800a0912`
- `ESENT!JetMakeKey` at `0x1800a0981`
- `ESENT!JetMakeKey` at `0x1800a0981`
- `ESENT!JetSeek` at `0x1800a09b6`
- `ESENT!JetSeek` at `0x1800a09b6`
- `ESENT!JetMove` at `0x1800a0947`
- `ESENT!JetMove` at `0x1800a0947`

## string_xrefs

- `0x1800a09c2`: `DhcpDALJetPrepareSearchEx:Move/Seek`

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
0x1800a08f4  mov     [rsp+arg_0], rbx
0x1800a08f9  mov     [rsp+arg_8], rbp
0x1800a08fe  mov     [rsp+arg_10], rdi
0x1800a0903  push    r14
0x1800a0905  sub     rsp, 30h
0x1800a0909  mov     ebx, r9d
0x1800a090c  mov     rbp, rdx
0x1800a090f  mov     r14, rcx
0x1800a0912  call    cs:__imp_JetSetCurrentIndex
0x1800a0919  nop     dword ptr [rax+rax+00h]
0x1800a091e  mov     ecx, eax
0x1800a0920  lea     rdx, aDhcpdaljetprep_0; "DhcpDALJetPrepareSearchEx"
0x1800a0927  call    DhcpDALMapJetError
0x1800a092c  test    eax, eax
0x1800a092e  jnz     loc_1800A09D0
0x1800a0934  test    ebx, ebx
0x1800a0936  jz      short loc_1800A095C
0x1800a0938  xor     r9d, r9d; grbit
0x1800a093b  mov     r8d, 80000000h; cRow
0x1800a0941  mov     rdx, rbp; tableid
0x1800a0944  mov     rcx, r14; sesid
0x1800a0947  call    cs:__imp_JetMove
0x1800a094e  nop     dword ptr [rax+rax+00h]
0x1800a0953  lea     rdx, aDhcpdaljetprep_1; "DhcpDALJetPrepareSearchEx:MakeKey"
0x1800a095a  jmp     short loc_1800A09C9
0x1800a095c  xor     ebx, ebx
0x1800a095e  cmp     [rsp+38h+arg_28], ebx
0x1800a0962  jbe     short loc_1800A09AB
0x1800a0964  mov     rdi, [rsp+38h+arg_20]
0x1800a0969  add     rdi, 8
0x1800a096d  mov     eax, [rdi+4]
0x1800a0970  mov     rdx, rbp; tableid
0x1800a0973  mov     r9d, [rdi]; cbData
0x1800a0976  mov     rcx, r14; sesid
0x1800a0979  mov     r8, [rdi-8]; pvData
0x1800a097d  mov     [rsp+38h+grbit], eax; grbit
0x1800a0981  call    cs:__imp_JetMakeKey
0x1800a0988  nop     dword ptr [rax+rax+00h]
0x1800a098d  mov     ecx, eax
0x1800a098f  lea     rdx, aDhcpdaljetprep_1; "DhcpDALJetPrepareSearchEx:MakeKey"
0x1800a0996  call    DhcpDALMapJetError
0x1800a099b  test    eax, eax
0x1800a099d  jnz     short loc_1800A09D0
0x1800a099f  inc     ebx
0x1800a09a1  add     rdi, 10h
0x1800a09a5  cmp     ebx, [rsp+38h+arg_28]
0x1800a09a9  jb      short loc_1800A096D
0x1800a09ab  mov     r8d, [rsp+38h+arg_30]; grbit
0x1800a09b0  mov     rdx, rbp; tableid
0x1800a09b3  mov     rcx, r14; sesid
0x1800a09b6  call    cs:__imp_JetSeek
0x1800a09bd  nop     dword ptr [rax+rax+00h]
0x1800a09c2  lea     rdx, aDhcpdaljetprep; "DhcpDALJetPrepareSearchEx:Move/Seek"
0x1800a09c9  mov     ecx, eax
0x1800a09cb  call    DhcpDALMapJetError
0x1800a09d0  mov     rbx, [rsp+38h+arg_0]
0x1800a09d5  mov     rbp, [rsp+38h+arg_8]
0x1800a09da  mov     rdi, [rsp+38h+arg_10]
0x1800a09df  add     rsp, 30h
0x1800a09e3  pop     r14
0x1800a09e5  retn
```
