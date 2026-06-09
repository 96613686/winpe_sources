# FILE_LISTENER::ListenForChanges(void)

- ea: `0x180004544`
- end: `0x1800045d9`
- name: `?ListenForChanges@FILE_LISTENER@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(FILE_LISTENER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000401c`
- `0x180007b00`

## callees

- `0x180001048`
- `0x180003e1c`
- `0x180004544`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800045ac`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800045ac`

## pseudocode

```c
void __fastcall FILE_LISTENER::ListenForChanges(FILE_LISTENER *this)
{
  bool v1; // zf
  DWORD v3; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 47) == 1;
  v3 = 0;
  if ( !v1 && !*((_DWORD *)this + 46) )
  {
    *((_OWORD *)this + 6) = 0;
    *((_OWORD *)this + 7) = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 1);
    if ( !ReadDirectoryChangesW(
            *((HANDLE *)this + 10),
            *((LPVOID *)this + 21),
            *((_DWORD *)this + 44),
            0,
            0x11u,
            &v3,
            (LPOVERLAPPED)this + 3,
            0)
      && _InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) == 1 )
    {
      FILE_LISTENER::~FILE_LISTENER(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180004544  mov     r11, rsp
0x180004547  push    rbx
0x180004548  sub     rsp, 40h
0x18000454c  cmp     dword ptr [rcx+0BCh], 1
0x180004553  mov     rbx, rcx
0x180004556  mov     [rsp+48h+arg_0], 0
0x18000455e  jz      short loc_1800045D3
0x180004560  cmp     dword ptr [rcx+0B8h], 0
0x180004567  jnz     short loc_1800045D3
0x180004569  lea     rax, [rcx+60h]
0x18000456d  xorps   xmm0, xmm0
0x180004570  movups  xmmword ptr [rax], xmm0
0x180004573  movups  xmmword ptr [rax+10h], xmm0
0x180004577  lock inc dword ptr [rcx+4]
0x18000457b  mov     r8d, [rcx+0B0h]; nBufferLength
0x180004582  xor     r9d, r9d; bWatchSubtree
0x180004585  mov     rdx, [rcx+0A8h]; lpBuffer
0x18000458c  mov     rcx, [rcx+50h]; hDirectory
0x180004590  mov     qword ptr [r11-10h], 0
0x180004598  mov     [r11-18h], rax
0x18000459c  lea     rax, [r11+8]
0x1800045a0  mov     [r11-20h], rax
0x1800045a4  mov     [rsp+48h+dwNotifyFilter], 11h; dwNotifyFilter
0x1800045ac  call    cs:__imp_ReadDirectoryChangesW
0x1800045b2  test    eax, eax
0x1800045b4  jnz     short loc_1800045D3
0x1800045b6  or      eax, 0FFFFFFFFh
0x1800045b9  lock xadd [rbx+4], eax
0x1800045be  cmp     eax, 1
0x1800045c1  jnz     short loc_1800045D3
0x1800045c3  mov     rcx, rbx; this
0x1800045c6  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x1800045cb  mov     rcx, rbx; Block
0x1800045ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045d3  add     rsp, 40h
0x1800045d7  pop     rbx
0x1800045d8  retn
```
