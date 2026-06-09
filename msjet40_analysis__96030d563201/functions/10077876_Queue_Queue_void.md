# Queue::~Queue(void)

- ea: `0x10077876`
- end: `0x100778fe`
- name: `??1Queue@@QAE@XZ`
- size: `136`
- prototype: `void __usercall(LPCRITICAL_SECTION lpCriticalSection@<ecx>)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10060c29`

## callees

- `0x100578a3`
- `0x10061803`
- `0x10077876`
- `0x10122f60`
- `0x10123ae2`
- `0x10123e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100778e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100778e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100778da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100778da`

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
0x10077876  mov     edi, edi
0x10077878  push    ebp
0x10077879  mov     ebp, esp
0x1007787b  push    0FFFFFFFFh
0x1007787d  push    offset ??1Queue@@QAE@XZ_SEH
0x10077882  mov     eax, large fs:0
0x10077888  push    eax
0x10077889  push    ebx
0x1007788a  push    esi
0x1007788b  push    edi
0x1007788c  mov     eax, ___security_cookie
0x10077891  xor     eax, ebp
0x10077893  push    eax
0x10077894  lea     eax, [ebp+var_C]
0x10077897  mov     large fs:0, eax
0x1007789d  mov     edi, ecx
0x1007789f  cmp     dword ptr [edi+24h], 0
0x100778a3  jbe     short loc_100778C6
0x100778a5  lea     ebx, [edi+1Ch]
0x100778a8  mov     eax, [ebx]
0x100778aa  push    18h; unsigned int
0x100778ac  mov     esi, [eax]
0x100778ae  push    esi; Block
0x100778af  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100778b4  pop     ecx
0x100778b5  pop     ecx
0x100778b6  push    esi; void *
0x100778b7  mov     ecx, ebx; this
0x100778b9  call    ?RemoveObject@Collection@@QAEXPBX@Z; Collection::RemoveObject(void const *)
0x100778be  cmp     dword ptr [edi+24h], 0
0x100778c2  ja      short loc_100778A5
0x100778c4  jmp     short loc_100778C9
0x100778c6  lea     ebx, [edi+1Ch]
0x100778c9  mov     ecx, ebx; this
0x100778cb  call    ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x100778d0  mov     [ebp+var_4], 0
0x100778d7  push    dword ptr [edi+18h]; hObject
0x100778da  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100778e0  push    edi; lpCriticalSection
0x100778e1  mov     [ebp+var_4], 1
0x100778e8  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x100778ee  mov     ecx, [ebp+var_C]
0x100778f1  mov     large fs:0, ecx
0x100778f8  pop     ecx
0x100778f9  pop     edi
0x100778fa  pop     esi
0x100778fb  pop     ebx
0x100778fc  leave
0x100778fd  retn
0x10123eb0  jmp     ds:__imp____std_terminate
0x10126deb  nop
0x10126dec  nop
0x10126ded  mov     edx, [esp-4+arg_4]
0x10126df1  lea     eax, [edx+0Ch]
0x10126df4  mov     ecx, [edx-10h]
0x10126df7  xor     ecx, eax; StackCookie
0x10126df9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10126dfe  mov     eax, offset stru_1012928C
0x10126e03  jmp     ___CxxFrameHandler3
```
