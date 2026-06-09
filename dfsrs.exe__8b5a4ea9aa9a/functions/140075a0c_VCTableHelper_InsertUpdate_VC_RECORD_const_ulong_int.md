# VCTableHelper::InsertUpdate(_VC_RECORD const &,ulong,int)

- ea: `0x140075a0c`
- end: `0x140075b95`
- name: `?InsertUpdate@VCTableHelper@@QEAAPEAVFrsStatus@@AEBU_VC_RECORD@@KH@Z`
- size: `393`
- prototype: `struct FrsStatus *__fastcall(VCTableHelper *__hidden this, const struct _VC_RECORD *, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14006f244`
- `0x140070e30`
- `0x140075954`

## callees

- `0x140075a0c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140075b34`
- `KERNEL32!GetCurrentThreadId` at `0x140075b34`
- `ESENT!JetUpdate` at `0x140075add`
- `ESENT!JetUpdate` at `0x140075add`
- `ESENT!JetSetColumns` at `0x140075ab8`
- `ESENT!JetSetColumns` at `0x140075ab8`
- `ESENT!JetPrepareUpdate` at `0x140075a8d`
- `ESENT!JetPrepareUpdate` at `0x140075b28`
- `ESENT!JetPrepareUpdate` at `0x140075a8d`
- `ESENT!JetPrepareUpdate` at `0x140075b28`
- `ESENT!JetMove` at `0x140075b06`
- `ESENT!JetMove` at `0x140075b06`

## string_xrefs

- `0x140075b52`: `VCTableHelper::InsertUpdate`

## pseudocode

```c
struct FrsStatus *__fastcall VCTableHelper::InsertUpdate(
        VCTableHelper *this,
        const struct _VC_RECORD *a2,
        unsigned int a3,
        int a4)
{
  char *v6; // rax
  JET_TABLEID v7; // rdx
  JET_SESID v8; // rcx
  __int64 v9; // rdi
  JET_ERR v10; // esi
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx

  *((_QWORD *)this + 35) = a2;
  *((_DWORD *)this + 72) = 16;
  *((_DWORD *)this + 82) = 16;
  *((_QWORD *)this + 40) = (char *)a2 + 16;
  *((_DWORD *)this + 92) = 8;
  *((_QWORD *)this + 45) = (char *)a2 + 32;
  *((_QWORD *)this + 50) = (char *)a2 + 40;
  v6 = (char *)a2 + 48;
  v7 = *((_QWORD *)this + 2);
  *((_DWORD *)this + 102) = 8;
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 55) = v6;
  *((_DWORD *)this + 112) = 1;
  v9 = 0;
  v10 = JetPrepareUpdate(v8, v7, a3);
  if ( v10 < 0 )
    goto LABEL_8;
  v10 = JetSetColumns(*((_QWORD *)this + 1), *((_QWORD *)this + 2), (JET_SETCOLUMN *)((char *)this + 272), 5u);
  if ( v10 < 0 || (v10 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 2), 0, 0, 0), v10 < 0) )
  {
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 2), 3u);
LABEL_8:
    CurrentThreadId = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v12,
                                 (unsigned int)v10,
                                 0,
                                 2,
                                 "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                 "VCTableHelper::InsertUpdate",
                                 2725,
                                 CurrentThreadId,
                                 0);
  }
  if ( a4 )
  {
    v10 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 2), 1, 0);
    if ( v10 < 0 )
      goto LABEL_8;
  }
  return (struct FrsStatus *)v9;
}

```

## disassembly

```asm
0x140075a0c  mov     [rsp+arg_0], rbx
0x140075a11  mov     [rsp+arg_8], rbp
0x140075a16  mov     [rsp+arg_10], rsi
0x140075a1b  push    rdi
0x140075a1c  sub     rsp, 50h
0x140075a20  mov     rbx, rcx
0x140075a23  mov     [rcx+118h], rdx
0x140075a2a  mov     eax, 10h
0x140075a2f  mov     ebp, r9d
0x140075a32  mov     [rcx+120h], eax
0x140075a38  mov     [rcx+148h], eax
0x140075a3e  lea     rax, [rdx+10h]
0x140075a42  mov     [rcx+140h], rax
0x140075a49  mov     ecx, 8
0x140075a4e  lea     rax, [rdx+20h]
0x140075a52  mov     [rbx+170h], ecx
0x140075a58  mov     [rbx+168h], rax
0x140075a5f  lea     rax, [rdx+28h]
0x140075a63  mov     [rbx+190h], rax
0x140075a6a  lea     rax, [rdx+30h]
0x140075a6e  mov     rdx, [rbx+10h]; tableid
0x140075a72  mov     [rbx+198h], ecx
0x140075a78  mov     rcx, [rbx+8]; sesid
0x140075a7c  mov     [rbx+1B8h], rax
0x140075a83  mov     dword ptr [rbx+1C0h], 1
0x140075a8d  call    cs:__imp_JetPrepareUpdate
0x140075a94  nop     dword ptr [rax+rax+00h]
0x140075a99  xor     edi, edi
0x140075a9b  mov     esi, eax
0x140075a9d  test    eax, eax
0x140075a9f  js      loc_140075B34
0x140075aa5  mov     rdx, [rbx+10h]; tableid
0x140075aa9  lea     r8, [rbx+110h]; psetcolumn
0x140075ab0  mov     rcx, [rbx+8]; sesid
0x140075ab4  lea     r9d, [rdi+5]; csetcolumn
0x140075ab8  call    cs:__imp_JetSetColumns
0x140075abf  nop     dword ptr [rax+rax+00h]
0x140075ac4  mov     esi, eax
0x140075ac6  test    eax, eax
0x140075ac8  js      short loc_140075B1A
0x140075aca  mov     rdx, [rbx+10h]; tableid
0x140075ace  xor     r9d, r9d; cbBookmark
0x140075ad1  mov     rcx, [rbx+8]; sesid
0x140075ad5  xor     r8d, r8d; pvBookmark
0x140075ad8  mov     [rsp+58h+pcbActual], rdi; pcbActual
0x140075add  call    cs:__imp_JetUpdate
0x140075ae4  nop     dword ptr [rax+rax+00h]
0x140075ae9  mov     esi, eax
0x140075aeb  test    eax, eax
0x140075aed  js      short loc_140075B1A
0x140075aef  test    ebp, ebp
0x140075af1  jz      loc_140075B7C
0x140075af7  mov     rdx, [rbx+10h]; tableid
0x140075afb  lea     r8d, [rdi+1]; cRow
0x140075aff  mov     rcx, [rbx+8]; sesid
0x140075b03  xor     r9d, r9d; grbit
0x140075b06  call    cs:__imp_JetMove
0x140075b0d  nop     dword ptr [rax+rax+00h]
0x140075b12  mov     esi, eax
0x140075b14  test    eax, eax
0x140075b16  js      short loc_140075B34
0x140075b18  jmp     short loc_140075B7C
0x140075b1a  mov     rdx, [rbx+10h]; tableid
0x140075b1e  mov     r8d, 3; prep
0x140075b24  mov     rcx, [rbx+8]; sesid
0x140075b28  call    cs:__imp_JetPrepareUpdate
0x140075b2f  nop     dword ptr [rax+rax+00h]
0x140075b34  call    cs:__imp_GetCurrentThreadId
0x140075b3b  nop     dword ptr [rax+rax+00h]
0x140075b40  mov     [rsp+58h+var_18], rdi
0x140075b45  mov     r9d, 2
0x140075b4b  mov     [rsp+58h+var_20], eax
0x140075b4f  xor     r8d, r8d
0x140075b52  lea     rax, aVctablehelperI; "VCTableHelper::InsertUpdate"
0x140075b59  mov     [rsp+58h+var_28], 0AA5h
0x140075b61  mov     [rsp+58h+var_30], rax
0x140075b66  mov     edx, esi
0x140075b68  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140075b6f  mov     [rsp+58h+pcbActual], rax
0x140075b74  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140075b79  mov     rdi, rax
0x140075b7c  mov     rbx, [rsp+58h+arg_0]
0x140075b81  mov     rax, rdi
0x140075b84  mov     rbp, [rsp+58h+arg_8]
0x140075b89  mov     rsi, [rsp+58h+arg_10]
0x140075b8e  add     rsp, 50h
0x140075b92  pop     rdi
0x140075b93  retn
```
