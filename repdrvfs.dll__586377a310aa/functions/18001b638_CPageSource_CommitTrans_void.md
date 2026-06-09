# CPageSource::CommitTrans(void)

- ea: `0x18001b638`
- end: `0x18001b850`
- name: `?CommitTrans@CPageSource@@QEAAKXZ`
- size: `536`
- prototype: `__int64 __fastcall(CPageSource *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b578`
- `0x18001b5c0`
- `0x18003dbf8`

## callees

- `0x1800012b8`
- `0x18001b638`
- `0x18001b858`
- `0x18001bad0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001b659`
- `wbemcomn!GetMemLogObject` at `0x18001b6b9`
- `wbemcomn!GetMemLogObject` at `0x18001b700`
- `wbemcomn!GetMemLogObject` at `0x18001b757`
- `wbemcomn!GetMemLogObject` at `0x18001b7bb`
- `wbemcomn!GetMemLogObject` at `0x18001b659`
- `wbemcomn!GetMemLogObject` at `0x18001b6b9`
- `wbemcomn!GetMemLogObject` at `0x18001b700`
- `wbemcomn!GetMemLogObject` at `0x18001b757`
- `wbemcomn!GetMemLogObject` at `0x18001b7bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b664`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b6c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b70b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b762`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b7cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b664`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b6c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b70b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b762`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b7cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPageSource::CommitTrans(CPageSource *this)
{
  CPageFile *v1; // rbp
  unsigned int v3; // edi
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v5; // r10
  __int64 v6; // rdx
  __int64 v7; // rcx
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  int v12; // eax
  CMemoryLog *v13; // rax

  v1 = (CPageSource *)((char *)this + 488);
  v3 = CPageFile::ReserveCommitSpace((CPageSource *)((char *)this + 488));
  if ( v3 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v3);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v6 = 111;
    goto LABEL_6;
  }
  v3 = CPageFile::ReserveCommitSpace((CPageSource *)((char *)this + 32));
  if ( v3 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, v3);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v6 = 112;
    goto LABEL_6;
  }
  v3 = CPageFile::Trans_Commit(v1);
  if ( v3 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, v3);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v6 = 113;
LABEL_6:
    v7 = *((_QWORD *)v5 + 2);
LABEL_7:
    WPP_SF_d(v7, v6, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v3);
    return v3;
  }
  v3 = CPageFile::Trans_Commit((CPageSource *)((char *)this + 32));
  if ( v3 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, v3);
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v6 = 114;
    goto LABEL_7;
  }
  v12 = ++*((_DWORD *)this + 59);
  if ( v12 == ++*((_DWORD *)this + 173) )
  {
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 0);
    }
    return 0;
  }
  else
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, 1306);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 1306);
    }
    return 1306;
  }
}

```

## disassembly

```asm
0x18001b638  push    rbx
0x18001b63a  push    rbp
0x18001b63b  push    rsi
0x18001b63c  push    rdi
0x18001b63d  sub     rsp, 28h
0x18001b641  lea     rbp, [rcx+1E8h]
0x18001b648  mov     rbx, rcx
0x18001b64b  mov     rcx, rbp; this
0x18001b64e  call    ?ReserveCommitSpace@CPageFile@@QEAAKXZ; CPageFile::ReserveCommitSpace(void)
0x18001b653  mov     edi, eax
0x18001b655  test    eax, eax
0x18001b657  jz      short loc_18001B6AA
0x18001b659  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b65f  mov     rcx, rax
0x18001b662  mov     edx, edi
0x18001b664  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b66a  mov     r10, cs:WPP_GLOBAL_Control
0x18001b671  lea     rcx, WPP_GLOBAL_Control
0x18001b678  cmp     r10, rcx
0x18001b67b  jz      short loc_18001B6A3
0x18001b67d  test    byte ptr [r10+1Ch], 1
0x18001b682  jz      short loc_18001B6A3
0x18001b684  cmp     byte ptr [r10+19h], 2
0x18001b689  jb      short loc_18001B6A3
0x18001b68b  mov     edx, 6Fh ; 'o'
0x18001b690  mov     rcx, [r10+10h]
0x18001b694  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b69b  mov     r9d, edi
0x18001b69e  call    WPP_SF_d
0x18001b6a3  mov     eax, edi
0x18001b6a5  jmp     loc_18001B847
0x18001b6aa  lea     rcx, [rbx+20h]; this
0x18001b6ae  call    ?ReserveCommitSpace@CPageFile@@QEAAKXZ; CPageFile::ReserveCommitSpace(void)
0x18001b6b3  mov     edi, eax
0x18001b6b5  test    eax, eax
0x18001b6b7  jz      short loc_18001B6F2
0x18001b6b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b6bf  mov     rcx, rax
0x18001b6c2  mov     edx, edi
0x18001b6c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b6ca  mov     r10, cs:WPP_GLOBAL_Control
0x18001b6d1  lea     rcx, WPP_GLOBAL_Control
0x18001b6d8  cmp     r10, rcx
0x18001b6db  jz      short loc_18001B6A3
0x18001b6dd  test    byte ptr [r10+1Ch], 1
0x18001b6e2  jz      short loc_18001B6A3
0x18001b6e4  cmp     byte ptr [r10+19h], 2
0x18001b6e9  jb      short loc_18001B6A3
0x18001b6eb  mov     edx, 70h ; 'p'
0x18001b6f0  jmp     short loc_18001B690
0x18001b6f2  mov     rcx, rbp; this
0x18001b6f5  call    ?Trans_Commit@CPageFile@@QEAAKXZ; CPageFile::Trans_Commit(void)
0x18001b6fa  mov     edi, eax
0x18001b6fc  test    eax, eax
0x18001b6fe  jz      short loc_18001B748
0x18001b700  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b706  mov     rcx, rax
0x18001b709  mov     edx, edi
0x18001b70b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b711  mov     r10, cs:WPP_GLOBAL_Control
0x18001b718  lea     rcx, WPP_GLOBAL_Control
0x18001b71f  cmp     r10, rcx
0x18001b722  jz      loc_18001B6A3
0x18001b728  test    byte ptr [r10+1Ch], 1
0x18001b72d  jz      loc_18001B6A3
0x18001b733  cmp     byte ptr [r10+19h], 2
0x18001b738  jb      loc_18001B6A3
0x18001b73e  mov     edx, 71h ; 'q'
0x18001b743  jmp     loc_18001B690
0x18001b748  lea     rcx, [rbx+20h]; this
0x18001b74c  call    ?Trans_Commit@CPageFile@@QEAAKXZ; CPageFile::Trans_Commit(void)
0x18001b751  mov     edi, eax
0x18001b753  test    eax, eax
0x18001b755  jz      short loc_18001B7A1
0x18001b757  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b75d  mov     rcx, rax
0x18001b760  mov     edx, edi
0x18001b762  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b768  mov     rax, cs:WPP_GLOBAL_Control
0x18001b76f  lea     rcx, WPP_GLOBAL_Control
0x18001b776  cmp     rax, rcx
0x18001b779  jz      loc_18001B6A3
0x18001b77f  test    byte ptr [rax+1Ch], 1
0x18001b783  jz      loc_18001B6A3
0x18001b789  cmp     byte ptr [rax+19h], 2
0x18001b78d  jb      loc_18001B6A3
0x18001b793  mov     rcx, [rax+10h]
0x18001b797  mov     edx, 72h ; 'r'
0x18001b79c  jmp     loc_18001B694
0x18001b7a1  inc     dword ptr [rbx+0ECh]
0x18001b7a7  mov     eax, [rbx+0ECh]
0x18001b7ad  inc     dword ptr [rbx+2B4h]
0x18001b7b3  cmp     eax, [rbx+2B4h]
0x18001b7b9  jz      short loc_18001B80E
0x18001b7bb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b7c1  mov     ebx, 51Ah
0x18001b7c6  mov     rcx, rax
0x18001b7c9  mov     edx, ebx
0x18001b7cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b7d1  mov     r10, cs:WPP_GLOBAL_Control
0x18001b7d8  lea     rcx, WPP_GLOBAL_Control
0x18001b7df  cmp     r10, rcx
0x18001b7e2  jz      short loc_18001B80A
0x18001b7e4  test    byte ptr [r10+1Ch], 1
0x18001b7e9  jz      short loc_18001B80A
0x18001b7eb  cmp     byte ptr [r10+19h], 2
0x18001b7f0  jb      short loc_18001B80A
0x18001b7f2  mov     rcx, [r10+10h]
0x18001b7f6  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b7fd  mov     edx, 73h ; 's'
0x18001b802  mov     r9d, ebx
0x18001b805  call    WPP_SF_d
0x18001b80a  mov     eax, ebx
0x18001b80c  jmp     short loc_18001B847
0x18001b80e  mov     rax, cs:WPP_GLOBAL_Control
0x18001b815  lea     rcx, WPP_GLOBAL_Control
0x18001b81c  cmp     rax, rcx
0x18001b81f  jz      short loc_18001B845
0x18001b821  test    byte ptr [rax+1Ch], 1
0x18001b825  jz      short loc_18001B845
0x18001b827  cmp     byte ptr [rax+19h], 2
0x18001b82b  jb      short loc_18001B845
0x18001b82d  mov     rcx, [rax+10h]
0x18001b831  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b838  mov     edx, 74h ; 't'
0x18001b83d  xor     r9d, r9d
0x18001b840  call    WPP_SF_d
0x18001b845  xor     eax, eax
0x18001b847  add     rsp, 28h
0x18001b84b  pop     rdi
0x18001b84c  pop     rsi
0x18001b84d  pop     rbp
0x18001b84e  pop     rbx
0x18001b84f  retn
```
