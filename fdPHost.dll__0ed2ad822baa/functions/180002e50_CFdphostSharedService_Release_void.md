# CFdphostSharedService::Release(void)

- ea: `0x180002e50`
- end: `0x180002eb8`
- name: `?Release@CFdphostSharedService@@UEAAKXZ`
- size: `104`
- prototype: `__int64 __fastcall(CFdphostSharedService *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x180001008`
- `0x180002ae8`
- `0x180002e50`
- `0x180002f84`

## pseudocode

```c
__int64 __fastcall CFdphostSharedService::Release(CFdphostSharedService *this)
{
  unsigned __int32 v2; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 16);
  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CFdphostSharedService::~CFdphostSharedService(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180002e50  mov     [rsp+arg_0], rbx
0x180002e55  push    rdi
0x180002e56  sub     rsp, 30h
0x180002e5a  mov     rbx, rcx
0x180002e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e64  lea     rax, WPP_GLOBAL_Control
0x180002e6b  cmp     rcx, rax
0x180002e6e  jz      short loc_180002E89
0x180002e70  cmp     byte ptr [rcx+19h], 4
0x180002e74  jb      short loc_180002E89
0x180002e76  mov     rcx, [rcx+10h]
0x180002e7a  mov     edx, 10h
0x180002e7f  mov     [rsp+38h+var_18], rbx
0x180002e84  call    WPP_SF_sq
0x180002e89  or      edi, 0FFFFFFFFh
0x180002e8c  lock xadd [rbx+8], edi
0x180002e91  sub     edi, 1
0x180002e94  jnz     short loc_180002EAB
0x180002e96  test    rbx, rbx
0x180002e99  jz      short loc_180002EAB
0x180002e9b  mov     rcx, rbx; this
0x180002e9e  call    ??1CFdphostSharedService@@QEAA@XZ; CFdphostSharedService::~CFdphostSharedService(void)
0x180002ea3  mov     rcx, rbx; Block
0x180002ea6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002eab  mov     rbx, [rsp+38h+arg_0]
0x180002eb0  mov     eax, edi
0x180002eb2  add     rsp, 30h
0x180002eb6  pop     rdi
0x180002eb7  retn
```
