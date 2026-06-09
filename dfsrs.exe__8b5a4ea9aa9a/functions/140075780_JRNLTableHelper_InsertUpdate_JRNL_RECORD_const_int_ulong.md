# JRNLTableHelper::InsertUpdate(_JRNL_RECORD const &,int,ulong)

- ea: `0x140075780`
- end: `0x14007594b`
- name: `?InsertUpdate@JRNLTableHelper@@QEAAPEAVFrsStatus@@AEBU_JRNL_RECORD@@HK@Z`
- size: `459`
- prototype: `struct FrsStatus *(JRNLTableHelper *__hidden this, const struct _JRNL_RECORD *, int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140075118`
- `0x140085be0`

## callees

- `0x140075780`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140075884`
- `KERNEL32!GetCurrentThreadId` at `0x1400758f0`
- `KERNEL32!GetCurrentThreadId` at `0x140075884`
- `KERNEL32!GetCurrentThreadId` at `0x1400758f0`
- `ESENT!JetUpdate` at `0x14007586e`
- `ESENT!JetUpdate` at `0x14007586e`
- `ESENT!JetSetColumns` at `0x140075849`
- `ESENT!JetSetColumns` at `0x140075849`
- `ESENT!JetPrepareUpdate` at `0x140075816`
- `ESENT!JetPrepareUpdate` at `0x1400758df`
- `ESENT!JetPrepareUpdate` at `0x140075816`
- `ESENT!JetPrepareUpdate` at `0x1400758df`

## string_xrefs

- `0x140075895`: `JRNLTableHelper::InsertUpdate`

## pseudocode

```c
struct FrsStatus *__fastcall JRNLTableHelper::InsertUpdate(
        JRNLTableHelper *this,
        const struct _JRNL_RECORD *a2,
        int a3,
        unsigned int a4)
{
  __int64 v4; // rdi
  int v7; // r14d
  char v8; // al
  char v9; // cl
  char v10; // al
  char v11; // cl
  JET_ERR v12; // esi
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  unsigned int *v15; // rsi
  DWORD v16; // eax
  __int64 v17; // rcx

  v4 = 0;
  *((_QWORD *)this + 4) = *(_QWORD *)a2;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 1);
  v7 = 0;
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 7) = *((_QWORD *)a2 + 3);
  *((_QWORD *)this + 8) = *((_QWORD *)a2 + 4);
  *((_BYTE *)this + 72) = 0;
  if ( a3 )
  {
    v8 = *((_BYTE *)a2 + 40) & 1;
    *((_BYTE *)this + 72) = v8;
    v9 = v8 | *((_BYTE *)a2 + 40) & 2;
    *((_BYTE *)this + 72) = v9;
    v10 = v9 | (2 * (*((_BYTE *)a2 + 40) & 4));
    *((_BYTE *)this + 72) = v10;
    v11 = v10 | (2 * (*((_BYTE *)a2 + 40) & 8));
    *((_BYTE *)this + 72) = v11;
    *((_BYTE *)this + 72) = v11 | (2 * (*((_BYTE *)a2 + 40) & 0x10));
  }
  v12 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 2), a4);
  if ( v12 >= 0 )
  {
    v7 = 1;
    v12 = JetSetColumns(
            *((_QWORD *)this + 1),
            *((_QWORD *)this + 2),
            (JET_SETCOLUMN *)((char *)this + 368),
            (a3 != 0) + 5);
    if ( v12 >= 0 )
      v12 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 2), 0, 0, 0);
  }
  if ( v12 >= 0 )
    return 0;
  CurrentThreadId = GetCurrentThreadId();
  v15 = (unsigned int *)FrsStatusList::PushNewError(
                          v14,
                          (unsigned int)v12,
                          0,
                          2,
                          "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                          "JRNLTableHelper::InsertUpdate",
                          3264,
                          CurrentThreadId,
                          0);
  if ( v7 )
    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 2), 3u);
  if ( v15 )
  {
    v16 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v17,
                                 v15[1],
                                 v15[2],
                                 *v15,
                                 "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                 "JRNLTableHelper::InsertUpdate",
                                 3274,
                                 v16,
                                 v15);
  }
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x140075780  mov     [rsp+arg_0], rbx
0x140075785  mov     [rsp+arg_8], rbp
0x14007578a  mov     [rsp+arg_10], rsi
0x14007578f  push    rdi
0x140075790  push    r14
0x140075792  push    r15
0x140075794  sub     rsp, 50h
0x140075798  mov     rax, [rdx]
0x14007579b  xor     edi, edi
0x14007579d  mov     [rcx+20h], rax
0x1400757a1  mov     ebp, r8d
0x1400757a4  mov     rax, [rdx+8]
0x1400757a8  mov     rbx, rcx
0x1400757ab  mov     [rcx+28h], rax
0x1400757af  mov     r14d, edi
0x1400757b2  mov     rax, [rdx+10h]
0x1400757b6  mov     [rcx+30h], rax
0x1400757ba  mov     rax, [rdx+18h]
0x1400757be  mov     [rcx+38h], rax
0x1400757c2  mov     rax, [rdx+20h]
0x1400757c6  mov     [rcx+40h], rax
0x1400757ca  mov     [rcx+48h], dil
0x1400757ce  test    r8d, r8d
0x1400757d1  jz      short loc_14007580B
0x1400757d3  mov     al, [rdx+28h]
0x1400757d6  and     al, 1
0x1400757d8  mov     [rcx+48h], al
0x1400757db  mov     cl, [rdx+28h]
0x1400757de  and     cl, 2
0x1400757e1  or      cl, al
0x1400757e3  mov     [rbx+48h], cl
0x1400757e6  mov     al, [rdx+28h]
0x1400757e9  and     al, 4
0x1400757eb  add     al, al
0x1400757ed  or      al, cl
0x1400757ef  mov     [rbx+48h], al
0x1400757f2  mov     cl, [rdx+28h]
0x1400757f5  and     cl, 8
0x1400757f8  add     cl, cl
0x1400757fa  or      cl, al
0x1400757fc  mov     [rbx+48h], cl
0x1400757ff  mov     al, [rdx+28h]
0x140075802  and     al, 10h
0x140075804  add     al, al
0x140075806  or      al, cl
0x140075808  mov     [rbx+48h], al
0x14007580b  mov     rdx, [rbx+10h]; tableid
0x14007580f  mov     r8d, r9d; prep
0x140075812  mov     rcx, [rbx+8]; sesid
0x140075816  call    cs:__imp_JetPrepareUpdate
0x14007581d  nop     dword ptr [rax+rax+00h]
0x140075822  mov     esi, eax
0x140075824  test    eax, eax
0x140075826  js      short loc_14007587C
0x140075828  mov     rdx, [rbx+10h]; tableid
0x14007582c  lea     r8, [rbx+170h]; psetcolumn
0x140075833  mov     rcx, [rbx+8]; sesid
0x140075837  neg     ebp
0x140075839  mov     r14d, 1
0x14007583f  sbb     r9d, r9d
0x140075842  neg     r9d
0x140075845  add     r9d, 5; csetcolumn
0x140075849  call    cs:__imp_JetSetColumns
0x140075850  nop     dword ptr [rax+rax+00h]
0x140075855  mov     esi, eax
0x140075857  test    eax, eax
0x140075859  js      short loc_14007587C
0x14007585b  mov     rdx, [rbx+10h]; tableid
0x14007585f  xor     r9d, r9d; cbBookmark
0x140075862  mov     rcx, [rbx+8]; sesid
0x140075866  xor     r8d, r8d; pvBookmark
0x140075869  mov     [rsp+68h+pcbActual], rdi; pcbActual
0x14007586e  call    cs:__imp_JetUpdate
0x140075875  nop     dword ptr [rax+rax+00h]
0x14007587a  mov     esi, eax
0x14007587c  test    esi, esi
0x14007587e  jns     loc_14007592E
0x140075884  call    cs:__imp_GetCurrentThreadId
0x14007588b  nop     dword ptr [rax+rax+00h]
0x140075890  mov     [rsp+68h+var_28], rdi
0x140075895  lea     rbp, aJrnltablehelpe; "JRNLTableHelper::InsertUpdate"
0x14007589c  mov     [rsp+68h+var_30], eax
0x1400758a0  lea     r15, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x1400758a7  mov     [rsp+68h+var_38], 0CC0h
0x1400758af  mov     r9d, 2
0x1400758b5  mov     [rsp+68h+var_40], rbp
0x1400758ba  xor     r8d, r8d
0x1400758bd  mov     edx, esi
0x1400758bf  mov     [rsp+68h+pcbActual], r15
0x1400758c4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400758c9  mov     rsi, rax
0x1400758cc  test    r14d, r14d
0x1400758cf  jz      short loc_1400758EB
0x1400758d1  mov     rdx, [rbx+10h]; tableid
0x1400758d5  mov     r8d, 3; prep
0x1400758db  mov     rcx, [rbx+8]; sesid
0x1400758df  call    cs:__imp_JetPrepareUpdate
0x1400758e6  nop     dword ptr [rax+rax+00h]
0x1400758eb  test    rsi, rsi
0x1400758ee  jz      short loc_140075929
0x1400758f0  call    cs:__imp_GetCurrentThreadId
0x1400758f7  nop     dword ptr [rax+rax+00h]
0x1400758fc  mov     r9d, [rsi]
0x1400758ff  mov     r8d, [rsi+8]
0x140075903  mov     edx, [rsi+4]
0x140075906  mov     [rsp+68h+var_28], rsi
0x14007590b  mov     [rsp+68h+var_30], eax
0x14007590f  mov     [rsp+68h+var_38], 0CCAh
0x140075917  mov     [rsp+68h+var_40], rbp
0x14007591c  mov     [rsp+68h+pcbActual], r15
0x140075921  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140075926  mov     rdi, rax
0x140075929  mov     rax, rdi
0x14007592c  jmp     short loc_140075930
0x14007592e  xor     eax, eax
0x140075930  lea     r11, [rsp+68h+var_18]
0x140075935  mov     rbx, [r11+20h]
0x140075939  mov     rbp, [r11+28h]
0x14007593d  mov     rsi, [r11+30h]
0x140075941  mov     rsp, r11
0x140075944  pop     r15
0x140075946  pop     r14
0x140075948  pop     rdi
0x140075949  retn
```
