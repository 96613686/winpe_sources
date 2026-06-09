# CFileCache::InnerInitialize(ushort const *)

- ea: `0x18003dbf8`
- end: `0x18003dd9d`
- name: `?InnerInitialize@CFileCache@@AEAAJPEBG@Z`
- size: `421`
- prototype: `__int64 __fastcall(CFileCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003db10`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x18001aaf0`
- `0x18001b638`
- `0x18002d980`
- `0x18002f9ac`
- `0x180030d60`
- `0x18003dad8`
- `0x18003dbf8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003dc64`
- `wbemcomn!GetMemLogObject` at `0x18003dcc2`
- `wbemcomn!GetMemLogObject` at `0x18003dd48`
- `wbemcomn!GetMemLogObject` at `0x18003dc64`
- `wbemcomn!GetMemLogObject` at `0x18003dcc2`
- `wbemcomn!GetMemLogObject` at `0x18003dd48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003dc6f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003dccd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003dd53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003dc6f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003dccd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003dd53`

## pseudocode

```c
__int64 __fastcall CFileCache::InnerInitialize(CFileCache *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rbx
  unsigned int v5; // r10d
  __int64 v6; // rax
  unsigned int v7; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax

  v2 = (unsigned __int16 *)((char *)this + 1156);
  StringCchCopyW((unsigned __int16 *)this + 578, 0x411u, a2);
  StringCchCatW(v2, v5, L"\\");
  v6 = -1;
  do
    ++v6;
  while ( v2[v6] );
  *((_DWORD *)this + 288) = v6;
  v7 = CPageSource::Init((CFileCache *)((char *)this + 8), 0, 0);
  if ( v7 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v7);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 10;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids, v7);
    }
  }
  else
  {
    v7 = CPageSource::BeginTrans((CFileCache *)((char *)this + 8));
    if ( v7 )
    {
      CFileCache::Clear(this, 0);
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, v7);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 11;
        goto LABEL_20;
      }
    }
    else
    {
      v7 = CObjectHeap::Initialize(
             (CFileCache *)((char *)this + 1024),
             (CFileCache *)((char *)this + 8),
             a2,
             *((_DWORD *)this + 288));
      if ( v7 || (v7 = CPageSource::CommitTrans((CFileCache *)((char *)this + 8))) != 0 )
      {
        CPageSource::RollbackTrans((CFileCache *)((char *)this + 8));
        CFileCache::Clear(this, 0);
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, v7);
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 12;
        goto LABEL_20;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18003dbf8  push    rbx
0x18003dbfa  push    rbp
0x18003dbfb  push    rsi
0x18003dbfc  push    rdi
0x18003dbfd  push    r14
0x18003dbff  sub     rsp, 20h
0x18003dc03  lea     rbx, [rcx+484h]
0x18003dc0a  mov     rbp, rdx
0x18003dc0d  mov     rdi, rcx
0x18003dc10  mov     r8, rdx; unsigned __int16 *
0x18003dc13  mov     r10d, 411h
0x18003dc19  mov     rcx, rbx; unsigned __int16 *
0x18003dc1c  mov     edx, r10d; unsigned __int64
0x18003dc1f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003dc24  lea     r8, asc_18004B0E0; "\\"
0x18003dc2b  mov     edx, r10d; unsigned __int64
0x18003dc2e  mov     rcx, rbx; unsigned __int16 *
0x18003dc31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003dc36  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003dc3a  xor     r14d, r14d
0x18003dc3d  inc     rax
0x18003dc40  cmp     [rbx+rax*2], r14w
0x18003dc45  jnz     short loc_18003DC3D
0x18003dc47  lea     rsi, [rdi+8]
0x18003dc4b  mov     [rdi+480h], eax
0x18003dc51  mov     rcx, rsi; this
0x18003dc54  xor     r8d, r8d; unsigned __int16 *
0x18003dc57  xor     edx, edx; bool
0x18003dc59  call    ?Init@CPageSource@@QEAAK_NPEBG@Z; CPageSource::Init(bool,ushort const *)
0x18003dc5e  mov     ebx, eax
0x18003dc60  test    eax, eax
0x18003dc62  jz      short loc_18003DCAA
0x18003dc64  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003dc6a  mov     rcx, rax
0x18003dc6d  mov     edx, ebx
0x18003dc6f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003dc75  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc7c  lea     rdx, WPP_GLOBAL_Control
0x18003dc83  cmp     rcx, rdx
0x18003dc86  jz      loc_18003DD90
0x18003dc8c  test    byte ptr [rcx+1Ch], 1
0x18003dc90  jz      loc_18003DD90
0x18003dc96  cmp     byte ptr [rcx+19h], 2
0x18003dc9a  jb      loc_18003DD90
0x18003dca0  mov     edx, 0Ah
0x18003dca5  jmp     loc_18003DD7D
0x18003dcaa  mov     rcx, rsi; this
0x18003dcad  call    ?BeginTrans@CPageSource@@QEAAKXZ; CPageSource::BeginTrans(void)
0x18003dcb2  mov     ebx, eax
0x18003dcb4  test    eax, eax
0x18003dcb6  jz      short loc_18003DD05
0x18003dcb8  xor     edx, edx; unsigned int
0x18003dcba  mov     rcx, rdi; this
0x18003dcbd  call    ?Clear@CFileCache@@AEAAXK@Z; CFileCache::Clear(ulong)
0x18003dcc2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003dcc8  mov     rcx, rax
0x18003dccb  mov     edx, ebx
0x18003dccd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003dcd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dcda  lea     rdx, WPP_GLOBAL_Control
0x18003dce1  cmp     rcx, rdx
0x18003dce4  jz      loc_18003DD90
0x18003dcea  test    byte ptr [rcx+1Ch], 1
0x18003dcee  jz      loc_18003DD90
0x18003dcf4  cmp     byte ptr [rcx+19h], 2
0x18003dcf8  jb      loc_18003DD90
0x18003dcfe  mov     edx, 0Bh
0x18003dd03  jmp     short loc_18003DD7D
0x18003dd05  mov     r9d, [rdi+480h]; unsigned int
0x18003dd0c  lea     rcx, [rdi+400h]; this
0x18003dd13  mov     r8, rbp; unsigned __int16 *
0x18003dd16  mov     rdx, rsi; struct CPageSource *
0x18003dd19  call    ?Initialize@CObjectHeap@@QEAAJPEAVCPageSource@@PEAGK@Z; CObjectHeap::Initialize(CPageSource *,ushort *,ulong)
0x18003dd1e  mov     ebx, eax
0x18003dd20  test    eax, eax
0x18003dd22  jnz     short loc_18003DD32
0x18003dd24  mov     rcx, rsi; this
0x18003dd27  call    ?CommitTrans@CPageSource@@QEAAKXZ; CPageSource::CommitTrans(void)
0x18003dd2c  mov     ebx, eax
0x18003dd2e  test    eax, eax
0x18003dd30  jz      short loc_18003DD59
0x18003dd32  mov     rcx, rsi; this
0x18003dd35  mov     ebp, r14d
0x18003dd38  call    ?RollbackTrans@CPageSource@@QEAAKXZ; CPageSource::RollbackTrans(void)
0x18003dd3d  mov     edx, r14d; unsigned int
0x18003dd40  mov     rcx, rdi; this
0x18003dd43  call    ?Clear@CFileCache@@AEAAXK@Z; CFileCache::Clear(ulong)
0x18003dd48  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003dd4e  mov     rcx, rax
0x18003dd51  mov     edx, ebx
0x18003dd53  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003dd59  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd60  lea     rdx, WPP_GLOBAL_Control
0x18003dd67  cmp     rcx, rdx
0x18003dd6a  jz      short loc_18003DD90
0x18003dd6c  test    byte ptr [rcx+1Ch], 1
0x18003dd70  jz      short loc_18003DD90
0x18003dd72  cmp     byte ptr [rcx+19h], 2
0x18003dd76  jb      short loc_18003DD90
0x18003dd78  mov     edx, 0Ch
0x18003dd7d  mov     rcx, [rcx+10h]
0x18003dd81  lea     r8, WPP_73ae52d8f45f36054e2acb1c737c3765_Traceguids
0x18003dd88  mov     r9d, ebx
0x18003dd8b  call    WPP_SF_d
0x18003dd90  mov     eax, ebx
0x18003dd92  add     rsp, 20h
0x18003dd96  pop     r14
0x18003dd98  pop     rdi
0x18003dd99  pop     rsi
0x18003dd9a  pop     rbp
0x18003dd9b  pop     rbx
0x18003dd9c  retn
```
