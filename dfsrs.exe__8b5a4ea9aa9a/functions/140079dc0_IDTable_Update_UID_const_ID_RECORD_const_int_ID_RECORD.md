# IDTable::Update(UID const &,ID_RECORD const &,int,ID_RECORD &)

- ea: `0x140079dc0`
- end: `0x140079f94`
- name: `?Update@IDTable@@QEAAPEAVFrsStatus@@AEBVUID@@AEBVID_RECORD@@HAEAV4@@Z`
- size: `468`
- prototype: `struct FrsStatus *(IDTable *__hidden this, const struct UID *, const struct ID_RECORD *, int, struct ID_RECORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14002ddb0`
- `0x140032320`
- `0x140085d20`

## callees

- `0x14006f9c0`
- `0x140075b9c`
- `0x140077ac8`
- `0x140078a68`
- `0x140079dc0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140079ed4`
- `KERNEL32!GetCurrentThreadId` at `0x140079f42`
- `KERNEL32!GetCurrentThreadId` at `0x140079ed4`
- `KERNEL32!GetCurrentThreadId` at `0x140079f42`
- `ESENT!JetUpdate` at `0x140079ebb`
- `ESENT!JetUpdate` at `0x140079ebb`
- `ESENT!JetSetColumns` at `0x140079e8d`
- `ESENT!JetSetColumns` at `0x140079e8d`
- `ESENT!JetPrepareUpdate` at `0x140079e26`
- `ESENT!JetPrepareUpdate` at `0x140079f31`
- `ESENT!JetPrepareUpdate` at `0x140079e26`
- `ESENT!JetPrepareUpdate` at `0x140079f31`

## string_xrefs

- `0x140079de3`: `IDTable::Update`

## pseudocode

```c
struct FrsStatus *__fastcall IDTable::Update(
        IDTable *this,
        const struct UID *a2,
        const struct ID_RECORD *a3,
        int a4,
        struct ID_RECORD *a5)
{
  __int64 v5; // rbx
  IDTableHelper **v6; // rdi
  int v9; // r14d
  struct FrsStatus *v10; // rsi
  JET_ERR v11; // esi
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  int v16; // edx
  char *const v17; // r8

  v5 = 0;
  v6 = (IDTableHelper **)((char *)this + 16);
  v9 = 0;
  if ( !a4 )
  {
    v10 = IDTableHelper::Seek(*v6, a2, 0);
    if ( v10 )
      goto LABEL_9;
  }
  v11 = JetPrepareUpdate(***((_QWORD ***)this + 1), *((_QWORD *)*v6 + 2), 2u);
  if ( v11 < 0 )
    goto LABEL_8;
  v9 = 1;
  v10 = IDTableHelper::Retrieve(*v6, a5);
  if ( !v10 )
  {
    IDTableHelper::ConvertIn(*v6, a3, a5);
    v11 = JetSetColumns(***((_QWORD ***)this + 1), *((_QWORD *)*v6 + 2), (JET_SETCOLUMN *)*v6 + 40, 0x12u);
    if ( v11 >= 0 )
    {
      v11 = JetUpdate(***((_QWORD ***)this + 1), *((_QWORD *)*v6 + 2), 0, 0, 0);
      if ( v11 >= 0 )
        return 0;
    }
LABEL_8:
    CurrentThreadId = GetCurrentThreadId();
    v10 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v14,
                                (unsigned int)v11,
                                0,
                                2,
                                "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                "IDTable::Update",
                                2225,
                                CurrentThreadId,
                                0);
  }
LABEL_9:
  if ( v9 )
    JetPrepareUpdate(***((_QWORD ***)this + 1), *((_QWORD *)*v6 + 2), 3u);
  if ( v10 )
  {
    v15 = GetCurrentThreadId();
    return LogTranslatedError(*((_DWORD *)v10 + 1), v16, v17, "IDTable::Update", 0x8BCu, v15, 0, v10);
  }
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x140079dc0  mov     rax, rsp
0x140079dc3  mov     [rax+8], rbx
0x140079dc7  mov     [rax+10h], rbp
0x140079dcb  mov     [rax+18h], rsi
0x140079dcf  mov     [rax+20h], rdi
0x140079dd3  push    r12
0x140079dd5  push    r14
0x140079dd7  push    r15
0x140079dd9  sub     rsp, 50h
0x140079ddd  xor     ebx, ebx
0x140079ddf  lea     rdi, [rcx+10h]
0x140079de3  lea     r12, aIdtableUpdate; "IDTable::Update"
0x140079dea  mov     r15, r8
0x140079ded  mov     rbp, rcx
0x140079df0  mov     r14d, ebx
0x140079df3  test    r9d, r9d
0x140079df6  jnz     short loc_140079E0F
0x140079df8  mov     rcx, [rdi]; this
0x140079dfb  xor     r8d, r8d; int
0x140079dfe  call    ?Seek@IDTableHelper@@QEAAPEAVFrsStatus@@AEBVUID@@H@Z; IDTableHelper::Seek(UID const &,int)
0x140079e03  mov     rsi, rax
0x140079e06  test    rax, rax
0x140079e09  jnz     loc_140079F15
0x140079e0f  mov     rax, [rdi]
0x140079e12  mov     r8d, 2; prep
0x140079e18  mov     rdx, [rax+10h]; tableid
0x140079e1c  mov     rax, [rbp+8]
0x140079e20  mov     rcx, [rax]
0x140079e23  mov     rcx, [rcx]; sesid
0x140079e26  call    cs:__imp_JetPrepareUpdate
0x140079e2d  nop     dword ptr [rax+rax+00h]
0x140079e32  mov     esi, eax
0x140079e34  test    eax, eax
0x140079e36  js      loc_140079ED4
0x140079e3c  mov     rdx, [rsp+68h+arg_20]; struct ID_RECORD *
0x140079e44  mov     r14d, 1
0x140079e4a  mov     rcx, [rdi]; this
0x140079e4d  call    ?Retrieve@IDTableHelper@@QEAAPEAVFrsStatus@@AEAVID_RECORD@@@Z; IDTableHelper::Retrieve(ID_RECORD &)
0x140079e52  mov     rsi, rax
0x140079e55  test    rax, rax
0x140079e58  jnz     loc_140079F15
0x140079e5e  mov     r8, [rsp+68h+arg_20]; struct ID_RECORD *
0x140079e66  mov     rdx, r15; struct ID_RECORD *
0x140079e69  mov     rcx, [rdi]; this
0x140079e6c  call    ?ConvertIn@IDTableHelper@@QEAAXAEBVID_RECORD@@PEBV2@@Z; IDTableHelper::ConvertIn(ID_RECORD const &,ID_RECORD const *)
0x140079e71  mov     r8, [rdi]
0x140079e74  lea     r9d, [r14+11h]; csetcolumn
0x140079e78  mov     rax, [rbp+8]
0x140079e7c  mov     rdx, [r8+10h]; tableid
0x140079e80  add     r8, 640h; psetcolumn
0x140079e87  mov     rcx, [rax]
0x140079e8a  mov     rcx, [rcx]; sesid
0x140079e8d  call    cs:__imp_JetSetColumns
0x140079e94  nop     dword ptr [rax+rax+00h]
0x140079e99  mov     esi, eax
0x140079e9b  test    eax, eax
0x140079e9d  js      short loc_140079ED4
0x140079e9f  mov     rax, [rdi]
0x140079ea2  xor     r9d, r9d; cbBookmark
0x140079ea5  xor     r8d, r8d; pvBookmark
0x140079ea8  mov     [rsp+68h+pcbActual], rbx; pcbActual
0x140079ead  mov     rdx, [rax+10h]; tableid
0x140079eb1  mov     rax, [rbp+8]
0x140079eb5  mov     rcx, [rax]
0x140079eb8  mov     rcx, [rcx]; sesid
0x140079ebb  call    cs:__imp_JetUpdate
0x140079ec2  nop     dword ptr [rax+rax+00h]
0x140079ec7  mov     esi, eax
0x140079ec9  test    eax, eax
0x140079ecb  js      short loc_140079ED4
0x140079ecd  xor     eax, eax
0x140079ecf  jmp     loc_140079F74
0x140079ed4  call    cs:__imp_GetCurrentThreadId
0x140079edb  nop     dword ptr [rax+rax+00h]
0x140079ee0  mov     [rsp+68h+var_28], rbx
0x140079ee5  mov     r9d, 2
0x140079eeb  mov     dword ptr [rsp+68h+var_30], eax
0x140079eef  xor     r8d, r8d
0x140079ef2  mov     [rsp+68h+var_38], 8B1h
0x140079efa  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140079f01  mov     qword ptr [rsp+68h+var_40], r12
0x140079f06  mov     edx, esi
0x140079f08  mov     [rsp+68h+pcbActual], rax
0x140079f0d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140079f12  mov     rsi, rax
0x140079f15  test    r14d, r14d
0x140079f18  jz      short loc_140079F3D
0x140079f1a  mov     rax, [rbp+8]
0x140079f1e  mov     r8d, 3; prep
0x140079f24  mov     rdx, [rdi]
0x140079f27  mov     rcx, [rax]
0x140079f2a  mov     rdx, [rdx+10h]; tableid
0x140079f2e  mov     rcx, [rcx]; sesid
0x140079f31  call    cs:__imp_JetPrepareUpdate
0x140079f38  nop     dword ptr [rax+rax+00h]
0x140079f3d  test    rsi, rsi
0x140079f40  jz      short loc_140079F71
0x140079f42  call    cs:__imp_GetCurrentThreadId
0x140079f49  nop     dword ptr [rax+rax+00h]
0x140079f4e  mov     ecx, [rsi+4]; int
0x140079f51  mov     r9, r12; char *
0x140079f54  mov     [rsp+68h+var_30], rsi; struct FrsStatus *
0x140079f59  mov     [rsp+68h+var_38], ebx; int
0x140079f5d  mov     [rsp+68h+var_40], eax; unsigned int
0x140079f61  mov     dword ptr [rsp+68h+pcbActual], 8BCh; unsigned int
0x140079f69  call    ?LogTranslatedError@@YAPEAVFrsStatus@@JHQEAD0KKHPEAV1@@Z; LogTranslatedError(long,int,char * const,char * const,ulong,ulong,int,FrsStatus *)
0x140079f6e  mov     rbx, rax
0x140079f71  mov     rax, rbx
0x140079f74  lea     r11, [rsp+68h+var_18]
0x140079f79  mov     rbx, [r11+20h]
0x140079f7d  mov     rbp, [r11+28h]
0x140079f81  mov     rsi, [r11+30h]
0x140079f85  mov     rdi, [r11+38h]
0x140079f89  mov     rsp, r11
0x140079f8c  pop     r15
0x140079f8e  pop     r14
0x140079f90  pop     r12
0x140079f92  retn
```
