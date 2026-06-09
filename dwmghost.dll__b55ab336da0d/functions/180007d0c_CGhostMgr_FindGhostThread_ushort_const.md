# CGhostMgr::FindGhostThread(ushort const *)

- ea: `0x180007d0c`
- end: `0x180007e2b`
- name: `?FindGhostThread@CGhostMgr@@AEAAPEAVCGhostThread@@PEBG@Z`
- size: `287`
- prototype: `struct CGhostThread *(CGhostMgr *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180007e64`

## callees

- `0x180003850`
- `0x180004dc4`
- `0x180005bf4`
- `0x180005d04`
- `0x180005d34`
- `0x180007d0c`
- `0x1800082bc`
- `0x180008828`
- `0x180008834`
- `0x180008944`
- `0x180009f60`
- `0x180009f70`
- `0x18000a5d0`
- `0x18000a8a0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007d7d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007d7d`

## pseudocode

```c
struct CGhostThread *__fastcall CGhostMgr::FindGhostThread(CGhostMgr *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  CCountedObject *v5; // rbx
  CDynamicArray *v6; // rsi
  unsigned int Count; // r14d
  unsigned int v8; // ebp
  CGhostThread *v9; // rdi
  const WCHAR *ThreadDesktopName; // rax
  CGhostThread *v11; // rax
  __int64 v12; // rcx
  CGhostThread *v13; // rax
  void *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v5 = 0;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  if ( CGhostMgr::s_bInShutdown )
    goto LABEL_12;
  v6 = (CGhostMgr *)((char *)this + 56);
  Count = CDynamicArray::GetCount(v6);
  v8 = Count;
  if ( !Count )
  {
LABEL_6:
    if ( Count < 0x40 )
    {
      v11 = (CGhostThread *)DefaultHeap::AllocClear(0x90u);
      if ( !v11 )
        ModuleFailFastForHRESULT(v12, retaddr);
      v13 = CGhostThread::CGhostThread(v11);
      v5 = v13;
      if ( v13
        && (!(unsigned int)CGhostThread::Initialize(v13, a2) || !(unsigned int)CDynamicCountedObjectArray::Add(v6, v5)) )
      {
        CCountedObject::Release(v5);
        v5 = 0;
      }
    }
    goto LABEL_12;
  }
  while ( 1 )
  {
    v9 = CDynamicCountedObjectArray::Get(v6, --v8);
    if ( !(unsigned int)CGhostThread::IsValid(v9) )
    {
      (*(void (__fastcall **)(CDynamicArray *, _QWORD))(*(_QWORD *)v6 + 16LL))(v6, v8);
      goto LABEL_14;
    }
    ThreadDesktopName = CGhostThread::GetThreadDesktopName(v9);
    if ( !lstrcmpiW(ThreadDesktopName, a2) )
      break;
LABEL_14:
    if ( !v8 )
      goto LABEL_6;
  }
  v5 = v9;
  CCountedObject::AddRef(v9);
  if ( !v9 )
    goto LABEL_6;
LABEL_12:
  CLock::Release(v2);
  return v5;
}

```

## disassembly

```asm
0x180007d0c  push    rbx
0x180007d0e  push    rbp
0x180007d0f  push    rsi
0x180007d10  push    rdi
0x180007d11  push    r12
0x180007d13  push    r14
0x180007d15  push    r15
0x180007d17  sub     rsp, 20h
0x180007d1b  lea     r15, [rcx+10h]
0x180007d1f  mov     rsi, rcx
0x180007d22  mov     rcx, r15; lpCriticalSection
0x180007d25  mov     r12, rdx
0x180007d28  xor     ebx, ebx
0x180007d2a  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180007d2f  cmp     cs:?s_bInShutdown@CGhostMgr@@0HA, ebx; int CGhostMgr::s_bInShutdown
0x180007d35  jnz     loc_180007DE8
0x180007d3b  add     rsi, 38h ; '8'
0x180007d3f  mov     rcx, rsi; this
0x180007d42  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x180007d47  mov     r14d, eax
0x180007d4a  mov     ebp, eax
0x180007d4c  test    eax, eax
0x180007d4e  jz      short loc_180007D9B
0x180007d50  dec     ebp
0x180007d52  mov     rcx, rsi; this
0x180007d55  mov     edx, ebp; unsigned int
0x180007d57  call    ?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z; CDynamicCountedObjectArray::Get(ulong)
0x180007d5c  mov     rcx, rax; this
0x180007d5f  mov     rdi, rax
0x180007d62  call    ?IsValid@CGhostThread@@QEAAHXZ; CGhostThread::IsValid(void)
0x180007d67  test    eax, eax
0x180007d69  jz      loc_180007E02
0x180007d6f  mov     rcx, rdi; this
0x180007d72  call    ?GetThreadDesktopName@CGhostThread@@QEAAPEBGXZ; CGhostThread::GetThreadDesktopName(void)
0x180007d77  mov     rcx, rax; lpString1
0x180007d7a  mov     rdx, r12; lpString2
0x180007d7d  call    cs:__imp_lstrcmpiW
0x180007d83  test    eax, eax
0x180007d85  jnz     loc_180007E13
0x180007d8b  mov     rcx, rdi; this
0x180007d8e  mov     rbx, rdi
0x180007d91  call    ?AddRef@CCountedObject@@QEAAXXZ; CCountedObject::AddRef(void)
0x180007d96  test    rdi, rdi
0x180007d99  jnz     short loc_180007DE8
0x180007d9b  cmp     r14d, 40h ; '@'
0x180007d9f  jnb     short loc_180007DE8
0x180007da1  mov     ecx, 90h; unsigned __int64
0x180007da6  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x180007dab  test    rax, rax
0x180007dae  jz      short loc_180007E20
0x180007db0  mov     rcx, rax; this
0x180007db3  call    ??0CGhostThread@@QEAA@XZ; CGhostThread::CGhostThread(void)
0x180007db8  mov     rbx, rax
0x180007dbb  test    rax, rax
0x180007dbe  jz      short loc_180007DE8
0x180007dc0  mov     rdx, r12; unsigned __int16 *
0x180007dc3  mov     rcx, rax; this
0x180007dc6  call    ?Initialize@CGhostThread@@QEAAHPEBG@Z; CGhostThread::Initialize(ushort const *)
0x180007dcb  test    eax, eax
0x180007dcd  jz      short loc_180007DDE
0x180007dcf  mov     rdx, rbx; struct CCountedObject *
0x180007dd2  mov     rcx, rsi; this
0x180007dd5  call    ?Add@CDynamicCountedObjectArray@@QEAAHPEAVCCountedObject@@@Z; CDynamicCountedObjectArray::Add(CCountedObject *)
0x180007dda  test    eax, eax
0x180007ddc  jnz     short loc_180007DE8
0x180007dde  mov     rcx, rbx; this
0x180007de1  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180007de6  xor     ebx, ebx
0x180007de8  mov     rcx, r15; lpCriticalSection
0x180007deb  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180007df0  mov     rax, rbx
0x180007df3  add     rsp, 20h
0x180007df7  pop     r15
0x180007df9  pop     r14
0x180007dfb  pop     r12
0x180007dfd  pop     rdi
0x180007dfe  pop     rsi
0x180007dff  pop     rbp
0x180007e00  pop     rbx
0x180007e01  retn
0x180007e02  mov     rax, [rsi]
0x180007e05  mov     edx, ebp
0x180007e07  mov     rcx, rsi
0x180007e0a  mov     rax, [rax+10h]
0x180007e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e13  test    ebp, ebp
0x180007e15  jnz     loc_180007D50
0x180007e1b  jmp     loc_180007D9B
0x180007e20  mov     rdx, [rsp+58h]
0x180007e25  call    ModuleFailFastForHRESULT
```
