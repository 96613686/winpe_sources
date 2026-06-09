# CIOPort::HrAddPortCallback(void *,ulong,ITpPortCallback *)

- ea: `0x180115740`
- end: `0x18011594f`
- name: `?HrAddPortCallback@CIOPort@@UEAAJPEAXKPEAUITpPortCallback@@@Z`
- size: `527`
- prototype: `int(CIOPort *__hidden this, void *, unsigned int, struct ITpPortCallback *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800264b4`
- `0x18002d8d4`
- `0x18002d96c`
- `0x1800723a8`
- `0x18010711c`
- `0x18010717c`
- `0x180115740`
- `0x1801179cc`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801158d8`
- `KERNEL32!GetCurrentThreadId` at `0x1801158d8`
- `KERNEL32!CreateIoCompletionPort` at `0x180115904`
- `KERNEL32!CreateIoCompletionPort` at `0x180115904`

## pseudocode

```c
__int64 __fastcall CIOPort::HrAddPortCallback(
        CIOPort *this,
        const struct Mso::Memory::NoThrow::MarkingLeak_t *a2,
        int a3,
        struct ITpPortCallback *a4)
{
  ULONG_PTR *v4; // rsi
  char v5; // r15
  int v10; // ebx
  __int64 v11; // rax
  CSRWLock *v12; // rcx
  ULONG_PTR *v13; // rax
  bool v14; // dl
  unsigned int v15; // r8d
  ULONG_PTR v16; // rbp
  __int64 v17; // rbx
  signed __int64 v18; // rax
  signed __int64 v19; // rtt
  __int64 v20; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v22; // rcx
  CSRWLock *v24; // [rsp+58h] [rbp+10h] BYREF

  v4 = 0;
  v5 = 0;
  if ( !a2 || !a4 )
    goto LABEL_30;
  if ( !*((_QWORD *)this + 16) )
    return (unsigned int)-2147467259;
  v11 = *((_QWORD *)this + 5);
  v10 = 0;
  v24 = 0;
  if ( !v11 )
  {
    v10 = TpHrCreateSRWLock(&v24);
    if ( v10 >= 0 )
    {
      v12 = v24;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 5, (signed __int64)v24, 0) )
      {
        if ( v12 )
          CSRWLock::`scalar deleting destructor'(v12, (unsigned int)a2);
      }
    }
  }
  if ( v10 >= 0 )
  {
    v13 = (ULONG_PTR *)operator new(0x28u, a2);
    v4 = v13;
    if ( v13 )
    {
      v13[1] = (ULONG_PTR)a2;
      *((_DWORD *)v13 + 6) = a3;
      v13[2] = (ULONG_PTR)a4;
      (*(void (__fastcall **)(struct ITpPortCallback *))(*(_QWORD *)a4 + 8LL))(a4);
      v4[4] = 0;
      *v4 = 0;
    }
    else
    {
      v4 = 0;
    }
    if ( !v4 )
      return (unsigned int)-2147024882;
    CExclusiveLock::FAcquire(*((CExclusiveLock **)this + 5), v14, v15);
    v16 = *((_QWORD *)this + 6);
    v17 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 6) = v16 + 1;
    if ( v16 >= 0xCCCCCCC )
      MsoShipAssertTagProc(507553946);
    *v4 = v16;
    v4[4] = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v4;
    if ( !v17 )
    {
      _m_prefetchw((char *)this + 16);
      v18 = *((_QWORD *)this + 2);
      do
      {
        v24 = (CSRWLock *)(v18 | 0x80000000LL);
        if ( (v18 & 0x3FF80000) != 0 )
        {
          v5 = 0;
        }
        else
        {
          v5 = 1;
          LODWORD(v24) = (v18 | 0x80000000) ^ ((v18 | 0x80000000) ^ ((v18 | 0x80000000) + 0x80000)) & 0x3FF80000;
        }
        v19 = v18;
        v18 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, (signed __int64)v24, v18);
      }
      while ( v19 != v18 );
    }
    CExclusiveLock::ReleaseLock(*((CExclusiveLock **)this + 5));
    if ( v5 )
    {
      LOBYTE(v20) = 1;
      v10 = (*(__int64 (__fastcall **)(CIOPort *, __int64, _QWORD))(*(_QWORD *)this + 16LL))(this, v20, 0);
      if ( v10 < 0 )
        goto LABEL_31;
    }
    if ( (Microsoft_Office_ThreadpoolEnableBits & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      McTemplateU0qq_EventWriteTransfer(v22, TPPortAssociateFile, (unsigned int)v16, CurrentThreadId);
    }
    if ( CreateIoCompletionPort(a2, *((HANDLE *)this + 16), v16, *((_DWORD *)this + 34)) )
      return 0;
LABEL_30:
    v10 = -2147467259;
LABEL_31:
    if ( v4 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(CIOPort *, const struct Mso::Memory::NoThrow::MarkingLeak_t *, struct ITpPortCallback *))(*(_QWORD *)this + 48LL))(
        this,
        a2,
        a4);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180115740  mov     [rsp+arg_0], rbx
0x180115745  mov     [rsp+arg_10], rbp
0x18011574a  push    rsi
0x18011574b  push    rdi
0x18011574c  push    r12
0x18011574e  push    r14
0x180115750  push    r15
0x180115752  sub     rsp, 20h
0x180115756  xor     esi, esi
0x180115758  xor     r15b, r15b
0x18011575b  mov     r14, r9
0x18011575e  mov     ebp, r8d
0x180115761  mov     r12, rdx
0x180115764  mov     rdi, rcx
0x180115767  test    rdx, rdx
0x18011576a  jz      loc_180115913
0x180115770  test    r9, r9
0x180115773  jz      loc_180115913
0x180115779  cmp     [rcx+80h], rsi
0x180115780  jnz     short loc_18011578C
0x180115782  mov     ebx, 80004005h
0x180115787  jmp     loc_180115936
0x18011578c  mov     rax, [rcx+28h]
0x180115790  xor     ebx, ebx
0x180115792  mov     [rsp+48h+arg_8], rbx
0x180115797  test    rax, rax
0x18011579a  jnz     short loc_1801157C5
0x18011579c  lea     rcx, [rsp+48h+arg_8]; struct CSRWLock **
0x1801157a1  call    ?TpHrCreateSRWLock@@YAJPEAPEAVCSRWLock@@@Z; TpHrCreateSRWLock(CSRWLock * *)
0x1801157a6  mov     ebx, eax
0x1801157a8  test    eax, eax
0x1801157aa  js      short loc_1801157C5
0x1801157ac  mov     rcx, [rsp+48h+arg_8]; this
0x1801157b1  xor     eax, eax
0x1801157b3  lock cmpxchg [rdi+28h], rcx
0x1801157b9  jz      short loc_1801157C5
0x1801157bb  test    rcx, rcx
0x1801157be  jz      short loc_1801157C5
0x1801157c0  call    ??_GCSRWLock@@QEAAPEAXI@Z; CSRWLock::`scalar deleting destructor'(uint)
0x1801157c5  test    ebx, ebx
0x1801157c7  js      loc_180115936
0x1801157cd  mov     ecx, 28h ; '('; unsigned __int64
0x1801157d2  call    ??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new(unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x1801157d7  mov     rsi, rax
0x1801157da  test    rax, rax
0x1801157dd  jz      short loc_18011580B
0x1801157df  mov     [rax+8], r12
0x1801157e3  mov     [rax+18h], ebp
0x1801157e6  mov     [rax+10h], r14
0x1801157ea  mov     rcx, [r14]
0x1801157ed  mov     rax, [rcx+8]
0x1801157f1  mov     rcx, r14
0x1801157f4  call    cs:__guard_dispatch_icall_fptr
0x1801157fa  mov     qword ptr [rsi+20h], 0
0x180115802  mov     qword ptr [rsi], 0
0x180115809  jmp     short loc_18011580D
0x18011580b  xor     esi, esi
0x18011580d  test    rsi, rsi
0x180115810  jnz     short loc_18011581C
0x180115812  mov     ebx, 8007000Eh
0x180115817  jmp     loc_180115936
0x18011581c  mov     rcx, [rdi+28h]; this
0x180115820  call    ?FAcquire@CExclusiveLock@@QEAA_N_NK@Z; CExclusiveLock::FAcquire(bool,ulong)
0x180115825  mov     rbp, [rdi+30h]
0x180115829  mov     rbx, [rdi+20h]
0x18011582d  lea     rax, [rbp+1]
0x180115831  mov     [rdi+30h], rax
0x180115835  cmp     rbp, 0CCCCCCCh
0x18011583c  jb      short loc_180115848
0x18011583e  mov     ecx, 1E40A89Ah
0x180115843  call    MsoShipAssertTagProc
0x180115848  mov     [rsi], rbp
0x18011584b  mov     rax, [rdi+20h]
0x18011584f  mov     [rsi+20h], rax
0x180115853  mov     [rdi+20h], rsi
0x180115857  test    rbx, rbx
0x18011585a  jnz     short loc_1801158A6
0x18011585c  prefetchw byte ptr [rdi+10h]
0x180115860  mov     rax, [rdi+10h]
0x180115864  mov     r8d, 3FF80000h
0x18011586a  mov     [rsp+48h+arg_8], rax
0x18011586f  mov     edx, dword ptr [rsp+48h+arg_8]
0x180115873  bts     edx, 1Fh
0x180115877  mov     dword ptr [rsp+48h+arg_8], edx
0x18011587b  test    r8d, edx
0x18011587e  jnz     short loc_180115896
0x180115880  lea     ecx, [rdx+80000h]
0x180115886  mov     r15b, 1
0x180115889  xor     ecx, edx
0x18011588b  and     ecx, r8d
0x18011588e  xor     ecx, edx
0x180115890  mov     dword ptr [rsp+48h+arg_8], ecx
0x180115894  jmp     short loc_180115899
0x180115896  xor     r15b, r15b
0x180115899  mov     rcx, [rsp+48h+arg_8]
0x18011589e  lock cmpxchg [rdi+10h], rcx
0x1801158a4  jnz     short loc_18011586A
0x1801158a6  mov     rcx, [rdi+28h]; this
0x1801158aa  call    ?ReleaseLock@CExclusiveLock@@QEAAXXZ; CExclusiveLock::ReleaseLock(void)
0x1801158af  test    r15b, r15b
0x1801158b2  jz      short loc_1801158CF
0x1801158b4  mov     rax, [rdi]
0x1801158b7  xor     r8d, r8d
0x1801158ba  mov     dl, 1
0x1801158bc  mov     rcx, rdi
0x1801158bf  mov     rax, [rax+10h]
0x1801158c3  call    cs:__guard_dispatch_icall_fptr
0x1801158c9  mov     ebx, eax
0x1801158cb  test    eax, eax
0x1801158cd  js      short loc_180115918
0x1801158cf  test    cs:Microsoft_Office_ThreadpoolEnableBits, 20h
0x1801158d6  jz      short loc_1801158F0
0x1801158d8  call    cs:__imp_GetCurrentThreadId
0x1801158de  mov     r8d, ebp
0x1801158e1  lea     rdx, TPPortAssociateFile
0x1801158e8  mov     r9d, eax
0x1801158eb  call    McTemplateU0qq_EventWriteTransfer
0x1801158f0  mov     r9d, [rdi+88h]; NumberOfConcurrentThreads
0x1801158f7  mov     r8, rbp; CompletionKey
0x1801158fa  mov     rdx, [rdi+80h]; ExistingCompletionPort
0x180115901  mov     rcx, r12; FileHandle
0x180115904  call    cs:__imp_CreateIoCompletionPort
0x18011590a  test    rax, rax
0x18011590d  jz      short loc_180115913
0x18011590f  xor     ebx, ebx
0x180115911  jmp     short loc_180115936
0x180115913  mov     ebx, 80004005h
0x180115918  test    rsi, rsi
0x18011591b  jz      short loc_180115936
0x18011591d  lfence
0x180115920  mov     rax, [rdi]
0x180115923  mov     r8, r14
0x180115926  mov     rdx, r12
0x180115929  mov     rcx, rdi
0x18011592c  mov     rax, [rax+30h]
0x180115930  call    cs:__guard_dispatch_icall_fptr
0x180115936  mov     rbp, [rsp+48h+arg_10]
0x18011593b  mov     eax, ebx
0x18011593d  mov     rbx, [rsp+48h+arg_0]
0x180115942  add     rsp, 20h
0x180115946  pop     r15
0x180115948  pop     r14
0x18011594a  pop     r12
0x18011594c  pop     rdi
0x18011594d  pop     rsi
0x18011594e  retn
```
