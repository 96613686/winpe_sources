# CFileStream::~CFileStream(void)

- ea: `0x18001c0a0`
- end: `0x18001c24c`
- name: `??1CFileStream@@QEAA@XZ`
- size: `428`
- prototype: `void __fastcall(CFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001c050`

## callees

- `0x18001b1c0`
- `0x18001c0a0`
- `0x180025154`
- `0x180025768`
- `0x18002e8c0`
- `0x180034df4`
- `0x18003f858`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c217`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c1e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c1e0`

## pseudocode

```c
void __fastcall CFileStream::~CFileStream(CFileStream *this)
{
  __int64 v1; // rbx
  void *v3; // rcx
  __int64 *i; // r8
  __int64 v5; // rdx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 6);
  *(_QWORD *)this = &CFileStream::`vftable'{for `ILockBytes'};
  *((_DWORD *)this + 20) = 1951624262;
  *((_QWORD *)this + 1) = &CFileStream::`vftable'{for `IFileLockBytes'};
  *((_QWORD *)this + 2) = &CFileStream::`vftable'{for `IFillLockBytes'};
  *((_QWORD *)this + 3) = &CFileStream::`vftable'{for `IFillInfo'};
  if ( v1 )
    *(_QWORD *)(v1 + 616) = 0;
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 != (void *)-1LL )
    CloseHandle(v3);
  if ( *((_QWORD *)this + 8) == -1 )
  {
    if ( !v1 )
      return;
  }
  else
  {
    if ( v1 )
      CFileStream::TurnOffMapping(this, 0);
    UnProtectHandle(*((HANDLE *)this + 8));
    CloseHandle(*((HANDLE *)this + 8));
    if ( !v1 )
      return;
    if ( *(_DWORD *)(v1 + 596) == 2 )
    {
      pv = 0;
      if ( (int)CFileStream::GetName(this, (unsigned __int16 **)&pv) >= 0 )
      {
        CFileStream::DeleteTheFile(this, v7);
        CoTaskMemFree(pv);
      }
    }
  }
  for ( i = (__int64 *)v1; ; i = (__int64 *)(v5 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + 8LL) )
  {
    v5 = *i;
    if ( !*i || !(v5 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) )
      break;
    if ( (CFileStream *)(v5 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) == (CFileStream *)((char *)this + 32) )
    {
      *i = *((_QWORD *)this + 5);
      break;
    }
  }
  if ( *(_WORD *)(v1 + 72) )
  {
    if ( !CContextList::CountContexts((CContextList *)v1) && (*(_BYTE *)(v1 + 36) & 0x10) != 0 )
    {
      v8 = *((_QWORD *)this + 6);
      if ( (*(_BYTE *)(v8 + 36) & 0xC0) == 0 )
        DeleteFileW((LPCWSTR)(v8 + 72));
    }
  }
  if ( (*(_DWORD *)(v1 + 8))-- == 1 )
    CMallocBased::operator delete((void *)v1);
}

```

## disassembly

```asm
0x18001c0a0  mov     [rsp+arg_8], rbx
0x18001c0a5  mov     [rsp+arg_10], rsi
0x18001c0aa  push    rdi
0x18001c0ab  sub     rsp, 20h
0x18001c0af  mov     rbx, [rcx+30h]
0x18001c0b3  lea     rax, ??_7CFileStream@@6BILockBytes@@@; const CFileStream::`vftable'{for `ILockBytes'}
0x18001c0ba  mov     [rcx], rax
0x18001c0bd  xor     esi, esi
0x18001c0bf  mov     dword ptr [rcx+50h], 74536C46h
0x18001c0c6  lea     rax, ??_7CFileStream@@6BIFileLockBytes@@@; const CFileStream::`vftable'{for `IFileLockBytes'}
0x18001c0cd  mov     [rcx+8], rax
0x18001c0d1  lea     rax, ??_7CFileStream@@6BIFillLockBytes@@@; const CFileStream::`vftable'{for `IFillLockBytes'}
0x18001c0d8  mov     [rcx+10h], rax
0x18001c0dc  lea     rax, ??_7CFileStream@@6BIFillInfo@@@; const CFileStream::`vftable'{for `IFillInfo'}
0x18001c0e3  mov     [rcx+18h], rax
0x18001c0e7  mov     rdi, rcx
0x18001c0ea  test    rbx, rbx
0x18001c0ed  jz      short loc_18001C0F6
0x18001c0ef  mov     [rbx+268h], rsi
0x18001c0f6  mov     rcx, [rcx+48h]; hObject
0x18001c0fa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c0fe  jnz     loc_18001C241
0x18001c104  cmp     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x18001c109  jnz     short loc_18001C185
0x18001c10b  test    rbx, rbx
0x18001c10e  jz      short loc_18001C175
0x18001c110  lea     r9, [rdi+20h]
0x18001c114  mov     r8, rbx
0x18001c117  mov     rdx, [r8]
0x18001c11a  test    rdx, rdx
0x18001c11d  jz      short loc_18001C15D
0x18001c11f  mov     rax, gs:30h
0x18001c128  mov     rcx, [rax+1758h]
0x18001c12f  mov     rax, [rcx]
0x18001c132  add     rax, rdx
0x18001c135  jz      short loc_18001C15D
0x18001c137  mov     rax, gs:30h
0x18001c140  mov     rcx, [rax+1758h]
0x18001c147  mov     rax, [rcx]
0x18001c14a  add     rax, rdx
0x18001c14d  cmp     rax, r9
0x18001c150  jnz     loc_18001C222
0x18001c156  mov     rax, [rdi+28h]
0x18001c15a  mov     [r8], rax
0x18001c15d  cmp     [rbx+48h], si
0x18001c161  jnz     loc_18001C1EB
0x18001c167  sub     dword ptr [rbx+8], 1
0x18001c16b  jnz     short loc_18001C175
0x18001c16d  mov     rcx, rbx; void *
0x18001c170  call    ??3CMallocBased@@SAXPEAX@Z; CMallocBased::operator delete(void *)
0x18001c175  mov     rbx, [rsp+28h+arg_8]
0x18001c17a  mov     rsi, [rsp+28h+arg_10]
0x18001c17f  add     rsp, 20h
0x18001c183  pop     rdi
0x18001c184  retn
0x18001c185  test    rbx, rbx
0x18001c188  jz      short loc_18001C194
0x18001c18a  xor     edx, edx; int
0x18001c18c  mov     rcx, rdi; this
0x18001c18f  call    ?TurnOffMapping@CFileStream@@AEAAJH@Z; CFileStream::TurnOffMapping(int)
0x18001c194  mov     rcx, [rdi+40h]; ObjectHandle
0x18001c198  call    ?UnProtectHandle@@YAJPEAX@Z; UnProtectHandle(void *)
0x18001c19d  mov     rcx, [rdi+40h]; hObject
0x18001c1a1  call    cs:__imp_CloseHandle
0x18001c1a7  test    rbx, rbx
0x18001c1aa  jz      short loc_18001C175
0x18001c1ac  cmp     dword ptr [rbx+254h], 2
0x18001c1b3  jnz     loc_18001C110
0x18001c1b9  lea     rdx, [rsp+28h+pv]; unsigned __int16 **
0x18001c1be  mov     [rsp+28h+pv], rsi
0x18001c1c3  mov     rcx, rdi; this
0x18001c1c6  call    ?GetName@CFileStream@@QEAAJPEAPEAG@Z; CFileStream::GetName(ushort * *)
0x18001c1cb  test    eax, eax
0x18001c1cd  js      loc_18001C110
0x18001c1d3  mov     rcx, rdi; this
0x18001c1d6  call    ?DeleteTheFile@CFileStream@@AEAAHPEBG@Z; CFileStream::DeleteTheFile(ushort const *)
0x18001c1db  mov     rcx, [rsp+28h+pv]; pv
0x18001c1e0  call    cs:__imp_CoTaskMemFree
0x18001c1e6  jmp     loc_18001C110
0x18001c1eb  mov     rcx, rbx; this
0x18001c1ee  call    ?CountContexts@CContextList@@QEAAKXZ; CContextList::CountContexts(void)
0x18001c1f3  test    eax, eax
0x18001c1f5  jnz     loc_18001C167
0x18001c1fb  test    byte ptr [rbx+24h], 10h
0x18001c1ff  jz      loc_18001C167
0x18001c205  mov     rcx, [rdi+30h]
0x18001c209  test    byte ptr [rcx+24h], 0C0h
0x18001c20d  jnz     loc_18001C167
0x18001c213  add     rcx, 48h ; 'H'; lpFileName
0x18001c217  call    cs:__imp_DeleteFileW
0x18001c21d  jmp     loc_18001C167
0x18001c222  mov     rax, gs:30h
0x18001c22b  mov     rcx, [rax+1758h]
0x18001c232  mov     r8, [rcx]
0x18001c235  add     r8, 8
0x18001c239  add     r8, rdx
0x18001c23c  jmp     loc_18001C117
0x18001c241  call    cs:__imp_CloseHandle
0x18001c247  jmp     loc_18001C104
```
