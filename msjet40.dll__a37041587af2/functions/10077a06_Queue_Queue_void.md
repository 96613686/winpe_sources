# Queue::~Queue(void)

- ea: `0x10077a06`
- end: `0x10077a8e`
- name: `??1Queue@@QAE@XZ`
- size: `136`
- prototype: `void __usercall(LPCRITICAL_SECTION lpCriticalSection@<ecx>)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10060dbd`

## callees

- `0x10057a33`
- `0x10061993`
- `0x10077a06`
- `0x10123110`
- `0x10123c92`
- `0x10124048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10077a78`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10077a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10077a6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10077a6a`

## pseudocode

```c
void __thiscall Queue::~Queue(LPCRITICAL_SECTION lpCriticalSection)
{
  PresOrderList *p_LockCount; // ebx
  void *v3; // esi

  if ( lpCriticalSection[1].OwningThread )
  {
    do
    {
      p_LockCount = (PresOrderList *)&lpCriticalSection[1].LockCount;
      v3 = *(void **)lpCriticalSection[1].LockCount;
      operator delete(v3, 0x18u);
      Collection::RemoveObject((Collection *)&lpCriticalSection[1].LockCount, v3);
    }
    while ( lpCriticalSection[1].OwningThread );
  }
  else
  {
    p_LockCount = (PresOrderList *)&lpCriticalSection[1].LockCount;
  }
  PresOrderList::~PresOrderList(p_LockCount);
  CloseHandle(lpCriticalSection[1].DebugInfo);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x10077a06  mov     edi, edi
0x10077a08  push    ebp
0x10077a09  mov     ebp, esp
0x10077a0b  push    0FFFFFFFFh
0x10077a0d  push    offset ??1Queue@@QAE@XZ_SEH
0x10077a12  mov     eax, large fs:0
0x10077a18  push    eax
0x10077a19  push    ebx
0x10077a1a  push    esi
0x10077a1b  push    edi
0x10077a1c  mov     eax, ___security_cookie
0x10077a21  xor     eax, ebp
0x10077a23  push    eax
0x10077a24  lea     eax, [ebp+var_C]
0x10077a27  mov     large fs:0, eax
0x10077a2d  mov     edi, ecx
0x10077a2f  cmp     dword ptr [edi+24h], 0
0x10077a33  jbe     short loc_10077A56
0x10077a35  lea     ebx, [edi+1Ch]
0x10077a38  mov     eax, [ebx]
0x10077a3a  push    18h; unsigned int
0x10077a3c  mov     esi, [eax]
0x10077a3e  push    esi; Block
0x10077a3f  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10077a44  pop     ecx
0x10077a45  pop     ecx
0x10077a46  push    esi; void *
0x10077a47  mov     ecx, ebx; this
0x10077a49  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x10077a4e  cmp     dword ptr [edi+24h], 0
0x10077a52  ja      short loc_10077A35
0x10077a54  jmp     short loc_10077A59
0x10077a56  lea     ebx, [edi+1Ch]
0x10077a59  mov     ecx, ebx; this
0x10077a5b  call    ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x10077a60  mov     [ebp+var_4], 0
0x10077a67  push    dword ptr [edi+18h]; hObject
0x10077a6a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10077a70  push    edi; lpCriticalSection
0x10077a71  mov     [ebp+var_4], 1
0x10077a78  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10077a7e  mov     ecx, [ebp+var_C]
0x10077a81  mov     large fs:0, ecx
0x10077a88  pop     ecx
0x10077a89  pop     edi
0x10077a8a  pop     esi
0x10077a8b  pop     ebx
0x10077a8c  leave
0x10077a8d  retn
0x10124060  jmp     ds:__imp____std_terminate
0x10126f9b  nop
0x10126f9c  nop
0x10126f9d  mov     edx, [esp-4+arg_4]
0x10126fa1  lea     eax, [edx+0Ch]
0x10126fa4  mov     ecx, [edx-10h]
0x10126fa7  xor     ecx, eax; StackCookie
0x10126fa9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10126fae  mov     eax, offset stru_1012943C
0x10126fb3  jmp     ___CxxFrameHandler3
```
