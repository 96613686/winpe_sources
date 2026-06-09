# DfsRootFolder::~DfsRootFolder(void)

- ea: `0x14000a074`
- end: `0x14000a1ad`
- name: `??1DfsRootFolder@@UEAA@XZ`
- size: `313`
- prototype: `void __fastcall(DfsRootFolder *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140009f2c`
- `0x14000a2e0`
- `0x140020ae8`
- `0x140044724`

## callees

- `0x140009f90`
- `0x14000a074`
- `0x14000a600`
- `0x14000abc4`
- `0x140058db8`
- `0x14005b03c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000a0b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000a0b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a0ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a0ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a11a`

## pseudocode

```c
void __fastcall DfsRootFolder::~DfsRootFolder(DfsRootFolder *this)
{
  _WORD *v1; // rdi
  __int64 v3; // rcx
  void *v4; // rcx
  DfsGeneric *v5; // rcx

  v1 = (_WORD *)*((_QWORD *)this + 57);
  *(_QWORD *)this = &DfsRootFolder::`vftable';
  if ( v1 )
  {
    if ( *v1 == 0x8102 && _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 1, 0xFFFFFFFF) == 1 )
    {
      DeleteCriticalSection(*((LPCRITICAL_SECTION *)v1 + 2));
      HeapFree(PrefixTableHeapHandle, 0, v1);
    }
    *((_QWORD *)this + 57) = 0;
  }
  v3 = *((_QWORD *)this + 32);
  if ( v3 )
  {
    if ( *(_WORD *)v3 == 0x8101 && _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 4), 0xFFFFFFFF) == 1 )
      DfsDeletePrefixTable((LPCRITICAL_SECTION *)v3);
    *((_QWORD *)this + 32) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 50);
  if ( v4 )
    CloseHandle(v4);
  v5 = (DfsGeneric *)*((_QWORD *)this + 60);
  if ( v5 )
  {
    DfsGeneric::ReleaseReference(v5);
    *((_QWORD *)this + 60) = 0;
  }
  DfsRootFolder::DeletePerfCtrSetInstance(this);
  DfsFreeUnicodeString((char *)this + 152);
  DfsFreeUnicodeString((char *)this + 200);
  DfsFreeUnicodeString((char *)this + 296);
  DfsFreeUnicodeString((char *)this + 136);
  DfsFreeUnicodeString((char *)this + 280);
  DfsFreeUnicodeString((char *)this + 168);
  DfsFreeUnicodeString((char *)this + 184);
  DfsFolder::~DfsFolder(this);
}

```

## disassembly

```asm
0x14000a074  mov     [rsp+arg_8], rbx
0x14000a079  push    rdi
0x14000a07a  sub     rsp, 20h
0x14000a07e  mov     rdi, [rcx+1C8h]
0x14000a085  lea     rax, ??_7DfsRootFolder@@6B@; const DfsRootFolder::`vftable'
0x14000a08c  mov     [rcx], rax
0x14000a08f  mov     rbx, rcx
0x14000a092  test    rdi, rdi
0x14000a095  jz      short loc_14000A0DE
0x14000a097  mov     eax, 8102h
0x14000a09c  cmp     [rdi], ax
0x14000a09f  jnz     short loc_14000A0D6
0x14000a0a1  or      eax, 0FFFFFFFFh
0x14000a0a4  lock xadd [rdi+4], eax
0x14000a0a9  cmp     eax, 1
0x14000a0ac  jnz     short loc_14000A0D6
0x14000a0ae  mov     rcx, [rdi+10h]; lpCriticalSection
0x14000a0b2  call    cs:__imp_DeleteCriticalSection
0x14000a0b9  nop     dword ptr [rax+rax+00h]
0x14000a0be  mov     rcx, cs:PrefixTableHeapHandle; hHeap
0x14000a0c5  mov     r8, rdi; lpMem
0x14000a0c8  xor     edx, edx; dwFlags
0x14000a0ca  call    cs:__imp_HeapFree
0x14000a0d1  nop     dword ptr [rax+rax+00h]
0x14000a0d6  and     qword ptr [rbx+1C8h], 0
0x14000a0de  mov     rcx, [rbx+100h]; lpMem
0x14000a0e5  test    rcx, rcx
0x14000a0e8  jz      short loc_14000A10E
0x14000a0ea  mov     eax, 8101h
0x14000a0ef  cmp     [rcx], ax
0x14000a0f2  jnz     short loc_14000A106
0x14000a0f4  or      eax, 0FFFFFFFFh
0x14000a0f7  lock xadd [rcx+4], eax
0x14000a0fc  cmp     eax, 1
0x14000a0ff  jnz     short loc_14000A106
0x14000a101  call    DfsDeletePrefixTable
0x14000a106  and     qword ptr [rbx+100h], 0
0x14000a10e  mov     rcx, [rbx+190h]; hObject
0x14000a115  test    rcx, rcx
0x14000a118  jz      short loc_14000A126
0x14000a11a  call    cs:__imp_CloseHandle
0x14000a121  nop     dword ptr [rax+rax+00h]
0x14000a126  mov     rcx, [rbx+1E0h]; this
0x14000a12d  test    rcx, rcx
0x14000a130  jz      short loc_14000A13F
0x14000a132  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14000a137  and     qword ptr [rbx+1E0h], 0
0x14000a13f  mov     rcx, rbx; this
0x14000a142  call    ?DeletePerfCtrSetInstance@DfsRootFolder@@QEAAXXZ; DfsRootFolder::DeletePerfCtrSetInstance(void)
0x14000a147  lea     rcx, [rbx+98h]
0x14000a14e  call    DfsFreeUnicodeString
0x14000a153  lea     rcx, [rbx+0C8h]
0x14000a15a  call    DfsFreeUnicodeString
0x14000a15f  lea     rcx, [rbx+128h]
0x14000a166  call    DfsFreeUnicodeString
0x14000a16b  lea     rcx, [rbx+88h]
0x14000a172  call    DfsFreeUnicodeString
0x14000a177  lea     rcx, [rbx+118h]
0x14000a17e  call    DfsFreeUnicodeString
0x14000a183  lea     rcx, [rbx+0A8h]
0x14000a18a  call    DfsFreeUnicodeString
0x14000a18f  lea     rcx, [rbx+0B8h]
0x14000a196  call    DfsFreeUnicodeString
0x14000a19b  mov     rcx, rbx; this
0x14000a19e  mov     rbx, [rsp+28h+arg_8]
0x14000a1a3  add     rsp, 20h
0x14000a1a7  pop     rdi
0x14000a1a8  jmp     ??1DfsFolder@@UEAA@XZ; DfsFolder::~DfsFolder(void)
```
