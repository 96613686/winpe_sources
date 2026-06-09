# CPageMap::LoadSignature(void *,bool)

- ea: `0x18002e5b8`
- end: `0x18002e829`
- name: `?LoadSignature@CPageMap@@QEAAKPEAX_N@Z`
- size: `625`
- prototype: `unsigned int __fastcall(CPageMap *__hidden this, HANDLE hFile, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e128`
- `0x18002e900`

## callees

- `0x1800012b8`
- `0x18002e5b8`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002e6c2`
- `wbemcomn!GetMemLogObject` at `0x18002e71e`
- `wbemcomn!GetMemLogObject` at `0x18002e77a`
- `wbemcomn!GetMemLogObject` at `0x18002e7c7`
- `wbemcomn!GetMemLogObject` at `0x18002e6c2`
- `wbemcomn!GetMemLogObject` at `0x18002e71e`
- `wbemcomn!GetMemLogObject` at `0x18002e77a`
- `wbemcomn!GetMemLogObject` at `0x18002e7c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e6d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e72e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e78a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e7d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e6d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e72e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e78a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e7d7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e601`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e63c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e66b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e69a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e601`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e63c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e66b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002e69a`

## pseudocode

```c
__int64 __fastcall CPageMap::LoadSignature(CPageMap *this, HANDLE hFile, char a3)
{
  CMemoryLog *v7; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *MemLogObject; // rax
  _DWORD Buffer[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+38h] BYREF

  Buffer[0] = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile(hFile, Buffer, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 || Buffer[0] != 43981 )
  {
    if ( !a3 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 1358);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v9 = 12;
    goto LABEL_35;
  }
  if ( !ReadFile(hFile, this, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
  {
    if ( !a3 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, 1358);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v9 = 13;
    goto LABEL_35;
  }
  if ( !ReadFile(hFile, (char *)this + 4, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
  {
    if ( !a3 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, 1358);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v9 = 14;
    goto LABEL_35;
  }
  if ( ReadFile(hFile, (char *)this + 8, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 )
    return 0;
  if ( !a3 )
    CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
  v7 = GetMemLogObject();
  CMemoryLog::Write(v7, 1358);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 15;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 1358);
  }
  return 1358;
}

```

## disassembly

```asm
0x18002e5b8  mov     [rsp-18h+arg_0], rbx
0x18002e5bd  mov     [rsp-18h+arg_8], rsi
0x18002e5c2  push    rbp
0x18002e5c3  push    rdi
0x18002e5c4  push    r14
0x18002e5c6  mov     rbp, rsp
0x18002e5c9  sub     rsp, 40h
0x18002e5cd  mov     rdi, rdx
0x18002e5d0  mov     [rbp+Buffer], 0
0x18002e5d7  mov     bl, r8b
0x18002e5da  mov     [rbp+NumberOfBytesRead], 0
0x18002e5e1  mov     rsi, rcx
0x18002e5e4  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18002e5ed  mov     r14d, 4
0x18002e5f3  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e5f7  mov     r8d, r14d; nNumberOfBytesToRead
0x18002e5fa  lea     rdx, [rbp+Buffer]; lpBuffer
0x18002e5fe  mov     rcx, rdi; hFile
0x18002e601  call    cs:__imp_ReadFile
0x18002e607  test    eax, eax
0x18002e609  jz      loc_18002E7B6
0x18002e60f  cmp     [rbp+NumberOfBytesRead], r14d
0x18002e613  jnz     loc_18002E7B6
0x18002e619  cmp     [rbp+Buffer], 0ABCDh
0x18002e620  jnz     loc_18002E7B6
0x18002e626  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e62a  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18002e633  mov     r8d, r14d; nNumberOfBytesToRead
0x18002e636  mov     rdx, rsi; lpBuffer
0x18002e639  mov     rcx, rdi; hFile
0x18002e63c  call    cs:__imp_ReadFile
0x18002e642  test    eax, eax
0x18002e644  jz      loc_18002E769
0x18002e64a  cmp     [rbp+NumberOfBytesRead], r14d
0x18002e64e  jnz     loc_18002E769
0x18002e654  lea     rdx, [rsi+4]; lpBuffer
0x18002e658  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18002e661  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e665  mov     r8d, r14d; nNumberOfBytesToRead
0x18002e668  mov     rcx, rdi; hFile
0x18002e66b  call    cs:__imp_ReadFile
0x18002e671  test    eax, eax
0x18002e673  jz      loc_18002E70D
0x18002e679  cmp     [rbp+NumberOfBytesRead], r14d
0x18002e67d  jnz     loc_18002E70D
0x18002e683  lea     rdx, [rsi+8]; lpBuffer
0x18002e687  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18002e690  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002e694  mov     r8d, r14d; nNumberOfBytesToRead
0x18002e697  mov     rcx, rdi; hFile
0x18002e69a  call    cs:__imp_ReadFile
0x18002e6a0  test    eax, eax
0x18002e6a2  jz      short loc_18002E6B1
0x18002e6a4  cmp     [rbp+NumberOfBytesRead], r14d
0x18002e6a8  jnz     short loc_18002E6B1
0x18002e6aa  xor     eax, eax
0x18002e6ac  jmp     loc_18002E816
0x18002e6b1  test    bl, bl
0x18002e6b3  jnz     short loc_18002E6C2
0x18002e6b5  xor     r8d, r8d; unsigned int
0x18002e6b8  xor     edx, edx; bool
0x18002e6ba  mov     ecx, r14d; int
0x18002e6bd  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e6c2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e6c8  mov     ebx, 54Eh
0x18002e6cd  mov     rcx, rax
0x18002e6d0  mov     edx, ebx
0x18002e6d2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e6df  lea     rax, WPP_GLOBAL_Control
0x18002e6e6  cmp     rcx, rax
0x18002e6e9  jz      loc_18002E814
0x18002e6ef  test    byte ptr [rcx+1Ch], 1
0x18002e6f3  jz      loc_18002E814
0x18002e6f9  cmp     byte ptr [rcx+19h], 2
0x18002e6fd  jb      loc_18002E814
0x18002e703  mov     edx, 0Fh
0x18002e708  jmp     loc_18002E801
0x18002e70d  test    bl, bl
0x18002e70f  jnz     short loc_18002E71E
0x18002e711  xor     r8d, r8d; unsigned int
0x18002e714  xor     edx, edx; bool
0x18002e716  mov     ecx, r14d; int
0x18002e719  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e71e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e724  mov     ebx, 54Eh
0x18002e729  mov     rcx, rax
0x18002e72c  mov     edx, ebx
0x18002e72e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e734  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e73b  lea     rax, WPP_GLOBAL_Control
0x18002e742  cmp     rcx, rax
0x18002e745  jz      loc_18002E814
0x18002e74b  test    byte ptr [rcx+1Ch], 1
0x18002e74f  jz      loc_18002E814
0x18002e755  cmp     byte ptr [rcx+19h], 2
0x18002e759  jb      loc_18002E814
0x18002e75f  mov     edx, 0Eh
0x18002e764  jmp     loc_18002E801
0x18002e769  test    bl, bl
0x18002e76b  jnz     short loc_18002E77A
0x18002e76d  xor     r8d, r8d; unsigned int
0x18002e770  xor     edx, edx; bool
0x18002e772  mov     ecx, r14d; int
0x18002e775  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e77a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e780  mov     ebx, 54Eh
0x18002e785  mov     rcx, rax
0x18002e788  mov     edx, ebx
0x18002e78a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e790  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e797  lea     rax, WPP_GLOBAL_Control
0x18002e79e  cmp     rcx, rax
0x18002e7a1  jz      short loc_18002E814
0x18002e7a3  test    byte ptr [rcx+1Ch], 1
0x18002e7a7  jz      short loc_18002E814
0x18002e7a9  cmp     byte ptr [rcx+19h], 2
0x18002e7ad  jb      short loc_18002E814
0x18002e7af  mov     edx, 0Dh
0x18002e7b4  jmp     short loc_18002E801
0x18002e7b6  test    bl, bl
0x18002e7b8  jnz     short loc_18002E7C7
0x18002e7ba  xor     r8d, r8d; unsigned int
0x18002e7bd  xor     edx, edx; bool
0x18002e7bf  mov     ecx, r14d; int
0x18002e7c2  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18002e7c7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e7cd  mov     ebx, 54Eh
0x18002e7d2  mov     rcx, rax
0x18002e7d5  mov     edx, ebx
0x18002e7d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7e4  lea     rax, WPP_GLOBAL_Control
0x18002e7eb  cmp     rcx, rax
0x18002e7ee  jz      short loc_18002E814
0x18002e7f0  test    byte ptr [rcx+1Ch], 1
0x18002e7f4  jz      short loc_18002E814
0x18002e7f6  cmp     byte ptr [rcx+19h], 2
0x18002e7fa  jb      short loc_18002E814
0x18002e7fc  mov     edx, 0Ch
0x18002e801  mov     rcx, [rcx+10h]
0x18002e805  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002e80c  mov     r9d, ebx
0x18002e80f  call    WPP_SF_d
0x18002e814  mov     eax, ebx
0x18002e816  mov     rbx, [rsp+40h+arg_0]
0x18002e81b  mov     rsi, [rsp+40h+arg_8]
0x18002e820  add     rsp, 40h
0x18002e824  pop     r14
0x18002e826  pop     rdi
0x18002e827  pop     rbp
0x18002e828  retn
```
