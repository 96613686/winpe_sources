# CStdCollection::Delete(tagVARIANT &)

- ea: `0x1800649c0`
- end: `0x180064af7`
- name: `?Delete@CStdCollection@@UEAAJAEAUtagVARIANT@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(CStdCollection *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180079720`

## callees

- `0x180009240`
- `0x180011700`
- `0x180020e20`
- `0x180027790`
- `0x1800649c0`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800649ef`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x1800649ef`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180064acf`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180064acf`

## string_xrefs

- `0x180064ab8`: `<CStdCollection::Delete|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStdCollection::Delete(CStdCollection *this, struct tagVARIANT *a2)
{
  __int64 v4; // r9
  __int64 v5; // rdx
  unsigned int v6; // ebx
  _BYTE v8[32]; // [rsp+20h] [rbp-30h] BYREF
  CStdCollection *v9; // [rsp+40h] [rbp-10h]
  unsigned int v10; // [rsp+48h] [rbp-8h]
  int v11; // [rsp+70h] [rbp+20h] BYREF
  struct CStdComObjectRoot *v12; // [rsp+80h] [rbp+30h] BYREF

  v9 = this;
  CContext::Init((CContext *)v8);
  v12 = 0;
  CReaderWriterLock3AR::WriteLock((CStdCollection *)((char *)this + 72));
  v11 = (*(__int64 (__fastcall **)(CStdCollection *, _QWORD, __int64))(*(_QWORD *)this + 128LL))(this, 0, 1);
  if ( (unsigned int)CContext::Failed((CContext *)v8, &v11) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v4 = 370;
      v5 = 378889;
LABEL_10:
      bidTraceW(off_18012A1B8[0], v5, L"<CStdCollection::Delete|ADO|ERR>  line %d\n", v4);
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(CStdCollection *, struct tagVARIANT *, struct CStdComObjectRoot **))(*(_QWORD *)this + 240LL))(
            this,
            a2,
            &v12);
    if ( (unsigned int)CContext::Failed((CContext *)v8, &v11) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v4 = 372;
        v5 = 380937;
        goto LABEL_10;
      }
    }
    else
    {
      v11 = CStdCollection::Delete(this, v12);
      if ( (unsigned int)CContext::Failed((CContext *)v8, &v11) && (bidGblFlags & 2) != 0 )
      {
        v4 = 375;
        v5 = 384009;
        goto LABEL_10;
      }
    }
  }
  CReaderWriterLock3AR::WriteUnlock((CStdCollection *)((char *)this + 72));
  v6 = v10;
  CContext::~CContext((CContext *)v8);
  return v6;
}

```

## disassembly

```asm
0x1800649c0  mov     [rsp-18h+arg_8], rbx
0x1800649c5  push    rbp
0x1800649c6  push    rsi
0x1800649c7  push    rdi
0x1800649c8  mov     rbp, rsp
0x1800649cb  sub     rsp, 50h
0x1800649cf  mov     rsi, rdx
0x1800649d2  mov     rbx, rcx
0x1800649d5  mov     [rbp+var_10], rcx
0x1800649d9  lea     rcx, [rbp+var_30]; this
0x1800649dd  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800649e2  nop
0x1800649e3  mov     [rbp+arg_10], 0
0x1800649eb  lea     rcx, [rbx+48h]
0x1800649ef  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x1800649f6  nop     dword ptr [rax+rax+00h]
0x1800649fb  mov     rax, [rbx]
0x1800649fe  xor     edx, edx
0x180064a00  lea     r8d, [rdx+1]
0x180064a04  mov     rcx, rbx
0x180064a07  mov     rax, [rax+80h]
0x180064a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a13  mov     [rbp+arg_0], eax
0x180064a16  lea     rdx, [rbp+arg_0]; int *
0x180064a1a  lea     rcx, [rbp+var_30]; this
0x180064a1e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180064a23  test    eax, eax
0x180064a25  jz      short loc_180064A41
0x180064a27  test    byte ptr cs:_bidGblFlags, 2
0x180064a2e  jz      loc_180064ACB
0x180064a34  mov     r9d, 172h
0x180064a3a  mov     edx, 5C809h
0x180064a3f  jmp     short loc_180064AB8
0x180064a41  mov     rax, [rbx]
0x180064a44  lea     r8, [rbp+arg_10]
0x180064a48  mov     rdx, rsi
0x180064a4b  mov     rcx, rbx
0x180064a4e  mov     rax, [rax+0F0h]
0x180064a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a5a  mov     [rbp+arg_0], eax
0x180064a5d  lea     rdx, [rbp+arg_0]; int *
0x180064a61  lea     rcx, [rbp+var_30]; this
0x180064a65  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180064a6a  test    eax, eax
0x180064a6c  jz      short loc_180064A84
0x180064a6e  test    byte ptr cs:_bidGblFlags, 2
0x180064a75  jz      short loc_180064ACB
0x180064a77  mov     r9d, 174h
0x180064a7d  mov     edx, 5D009h
0x180064a82  jmp     short loc_180064AB8
0x180064a84  mov     rdx, [rbp+arg_10]; struct CStdComObjectRoot *
0x180064a88  mov     rcx, rbx; this
0x180064a8b  call    ?Delete@CStdCollection@@QEAAJPEAVCStdComObjectRoot@@@Z; CStdCollection::Delete(CStdComObjectRoot *)
0x180064a90  mov     [rbp+arg_0], eax
0x180064a93  lea     rdx, [rbp+arg_0]; int *
0x180064a97  lea     rcx, [rbp+var_30]; this
0x180064a9b  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180064aa0  test    eax, eax
0x180064aa2  jz      short loc_180064ACB
0x180064aa4  test    byte ptr cs:_bidGblFlags, 2
0x180064aab  jz      short loc_180064ACB
0x180064aad  mov     r9d, 177h
0x180064ab3  mov     edx, 5DC09h
0x180064ab8  lea     r8, aCstdcollection_0; "<CStdCollection::Delete|ADO|ERR>  line "...
0x180064abf  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180064ac6  call    _bidTraceW
0x180064acb  lea     rcx, [rbx+48h]
0x180064acf  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x180064ad6  nop     dword ptr [rax+rax+00h]
0x180064adb  mov     ebx, [rbp+var_8]
0x180064ade  lea     rcx, [rbp+var_30]; this
0x180064ae2  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180064ae7  mov     eax, ebx
0x180064ae9  mov     rbx, [rsp+50h+arg_8]
0x180064aee  add     rsp, 50h
0x180064af2  pop     rdi
0x180064af3  pop     rsi
0x180064af4  pop     rbp
0x180064af5  retn
```
