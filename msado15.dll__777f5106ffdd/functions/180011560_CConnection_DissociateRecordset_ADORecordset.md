# CConnection::DissociateRecordset(_ADORecordset *)

- ea: `0x180011560`
- end: `0x180011680`
- name: `?DissociateRecordset@CConnection@@UEAAJPEAU_ADORecordset@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct _ADORecordset *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180011560`
- `0x1800119e0`
- `0x1800cdade`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011595`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011595`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011657`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180011657`

## pseudocode

```c
__int64 __fastcall CConnection::DissociateRecordset(CConnection *this, struct _ADORecordset *a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  unsigned int v6; // r8d
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 i; // r8
  __int64 v10; // rdx
  CCollectionMapEntry *v11; // rcx
  unsigned int v12; // ebx

  (*(void (__fastcall **)(CConnection *))(*(_QWORD *)this + 8LL))(this);
  v4 = ((unsigned __int64)a2 + 32) & -(__int64)(a2 != 0);
  CReaderWriterLock3AR::WriteLock((CConnection *)((char *)this + 752));
  (*(void (__fastcall **)(unsigned __int64, _QWORD))(*(_QWORD *)v4 + 152LL))(v4, 0);
  v5 = *((_QWORD *)this + 93);
  v6 = *(_DWORD *)(v5 + 16);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v5 + 8);
    v8 = 0;
    while ( *(_QWORD *)(v7 + 8 * v8) != v4 )
    {
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= v6 )
        goto LABEL_9;
    }
    if ( (_DWORD)v8 != v6 - 1 )
      memmove_0((void *)(v7 + 8 * v8), (const void *)(v7 + 8 * v8 + 8), 8LL * (~(_DWORD)v8 + v6));
    --*(_DWORD *)(v5 + 16);
  }
LABEL_9:
  for ( i = 0; (unsigned int)i < *(_DWORD *)(v5 + 24); i = (unsigned int)(i + 1) )
  {
    v10 = *(_QWORD *)(v5 + 32) + 8 * i;
    v11 = *(CCollectionMapEntry **)v10;
    if ( *(_QWORD *)v10 )
    {
      while ( v11 )
      {
        if ( *((_QWORD *)v11 + 3) == v4 )
        {
          *(_QWORD *)v10 = *(_QWORD *)(*(_QWORD *)v10 + 40LL);
          CCollectionMapEntry::`scalar deleting destructor'(v11, v10);
          --*(_DWORD *)(v5 + 40);
          goto LABEL_17;
        }
        v10 = (__int64)v11 + 40;
        v11 = (CCollectionMapEntry *)*((_QWORD *)v11 + 5);
      }
    }
  }
LABEL_17:
  v12 = (*(__int64 (__fastcall **)(char *, unsigned __int64))(*((_QWORD *)this + 85) + 352LL))((char *)this + 680, v4);
  CReaderWriterLock3AR::WriteUnlock((CConnection *)((char *)this + 752));
  (*(void (__fastcall **)(CConnection *))(*(_QWORD *)this + 16LL))(this);
  return v12;
}

```

## disassembly

```asm
0x180011560  push    rbx
0x180011562  push    rbp
0x180011563  push    rsi
0x180011564  push    rdi
0x180011565  push    r14
0x180011567  sub     rsp, 20h
0x18001156b  mov     rax, [rcx]
0x18001156e  mov     rbx, rdx
0x180011571  mov     rsi, rcx
0x180011574  mov     rax, [rax+8]
0x180011578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001157d  lea     rax, [rbx+20h]
0x180011581  neg     rbx
0x180011584  lea     r14, [rsi+2A8h]
0x18001158b  sbb     rdi, rdi
0x18001158e  lea     rcx, [r14+48h]
0x180011592  and     rdi, rax
0x180011595  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18001159c  nop     dword ptr [rax+rax+00h]
0x1800115a1  mov     rax, [rdi]
0x1800115a4  xor     edx, edx
0x1800115a6  mov     rcx, rdi
0x1800115a9  mov     rax, [rax+98h]
0x1800115b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b5  mov     rbx, [r14+40h]
0x1800115b9  mov     r8d, [rbx+10h]
0x1800115bd  test    r8d, r8d
0x1800115c0  jz      short loc_1800115F8
0x1800115c2  mov     rcx, [rbx+8]
0x1800115c6  xor     edx, edx
0x1800115c8  cmp     [rcx+rdx*8], rdi
0x1800115cc  jz      short loc_1800115D7
0x1800115ce  inc     edx
0x1800115d0  cmp     edx, r8d
0x1800115d3  jb      short loc_1800115C8
0x1800115d5  jmp     short loc_1800115F8
0x1800115d7  lea     eax, [r8-1]
0x1800115db  cmp     edx, eax
0x1800115dd  jz      short loc_1800115F5
0x1800115df  lea     rcx, [rcx+rdx*8]; void *
0x1800115e3  not     edx
0x1800115e5  add     r8d, edx
0x1800115e8  lea     rdx, [rcx+8]; Src
0x1800115ec  shl     r8, 3; Size
0x1800115f0  call    memmove_0
0x1800115f5  dec     dword ptr [rbx+10h]
0x1800115f8  xor     r8d, r8d
0x1800115fb  cmp     r8d, [rbx+18h]
0x1800115ff  jnb     short loc_18001163C
0x180011601  mov     rax, [rbx+20h]
0x180011605  lea     rdx, [rax+r8*8]; unsigned int
0x180011609  mov     rcx, [rdx]; this
0x18001160c  test    rcx, rcx
0x18001160f  jz      short loc_180011625
0x180011611  test    rcx, rcx
0x180011614  jz      short loc_180011625
0x180011616  cmp     [rcx+18h], rdi
0x18001161a  jz      short loc_18001162A
0x18001161c  lea     rdx, [rcx+28h]
0x180011620  mov     rcx, [rdx]
0x180011623  jmp     short loc_180011611
0x180011625  inc     r8d
0x180011628  jmp     short loc_1800115FB
0x18001162a  mov     rax, [rdx]
0x18001162d  mov     r8, [rax+28h]
0x180011631  mov     [rdx], r8
0x180011634  call    ??_GCCollectionMapEntry@@QEAAPEAXI@Z; CCollectionMapEntry::`scalar deleting destructor'(uint)
0x180011639  dec     dword ptr [rbx+28h]
0x18001163c  mov     rax, [r14]
0x18001163f  mov     rdx, rdi
0x180011642  mov     rcx, r14
0x180011645  mov     rax, [rax+160h]
0x18001164c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011651  mov     ebx, eax
0x180011653  lea     rcx, [r14+48h]
0x180011657  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18001165e  nop     dword ptr [rax+rax+00h]
0x180011663  mov     rcx, [rsi]
0x180011666  mov     rax, [rcx+10h]
0x18001166a  mov     rcx, rsi
0x18001166d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011672  mov     eax, ebx
0x180011674  add     rsp, 20h
0x180011678  pop     r14
0x18001167a  pop     rdi
0x18001167b  pop     rsi
0x18001167c  pop     rbp
0x18001167d  pop     rbx
0x18001167e  retn
```
