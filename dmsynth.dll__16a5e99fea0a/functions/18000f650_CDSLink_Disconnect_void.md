# CDSLink::Disconnect(void)

- ea: `0x18000f650`
- end: `0x18000f902`
- name: `?Disconnect@CDSLink@@AEAAJXZ`
- size: `690`
- prototype: `__int64 __fastcall(CDSLink *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e4d0`
- `0x18000ef90`

## callees

- `0x180001d9a`
- `0x18000f650`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f776`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f88e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f776`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f88e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f826`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f826`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f838`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f769`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f8f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f769`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f8f2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f742`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f854`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f86d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f854`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f86d`

## pseudocode

```c
__int64 __fastcall CDSLink::Disconnect(CDSLink *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r8
  int v5; // edx
  int v6; // r9d
  __int64 v7; // rcx
  char *v8; // r8
  char *v9; // r10
  char *v10; // rax
  char *v11; // rdx
  HANDLE v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  size_t Size; // [rsp+70h] [rbp+8h] BYREF
  size_t v17; // [rsp+78h] [rbp+10h] BYREF
  void *v18; // [rsp+80h] [rbp+18h] BYREF
  void *v19; // [rsp+88h] [rbp+20h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v2 = *((_QWORD *)this + 15);
  if ( v2 )
  {
    v3 = *((unsigned int *)this + 53);
    v19 = 0;
    v18 = 0;
    LODWORD(Size) = 0;
    LODWORD(v17) = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, void **, size_t *, void **, size_t *, _DWORD))(*(_QWORD *)v2 + 88LL))(
           v2,
           0,
           v3,
           &v19,
           &Size,
           &v18,
           &v17,
           0) >= 0 )
    {
      v4 = (unsigned int)Size;
      if ( (_DWORD)Size )
      {
        memset_0(v19, 0, (unsigned int)Size);
        v4 = (unsigned int)Size;
      }
      v5 = v17;
      if ( (_DWORD)v17 )
      {
        memset_0(v18, 0, (unsigned int)v17);
        v4 = (unsigned int)Size;
        v5 = v17;
      }
      (*(void (__fastcall **)(_QWORD, void *, __int64, void *, int))(**((_QWORD **)this + 15) + 152LL))(
        *((_QWORD *)this + 15),
        v19,
        v4,
        v18,
        v5);
      Sleep(0x32u);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 144LL))(*((_QWORD *)this + 15));
  }
  *((_DWORD *)this + 10) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  EnterCriticalSection(&CriticalSection);
  if ( *((_DWORD *)this + 56) )
  {
    v6 = dword_18001E610;
    if ( dword_18001E610 )
    {
      v7 = g_DSLinkList;
      v8 = (char *)this + 16;
      if ( !this )
        v8 = 0;
      if ( v8 == (char *)g_DSLinkList )
      {
        v7 = *(_QWORD *)g_DSLinkList;
      }
      else
      {
        v9 = 0;
        v10 = (char *)g_DSLinkList;
        if ( g_DSLinkList )
        {
          while ( 1 )
          {
            v11 = *(char **)v10;
            if ( v10 == v8 )
              break;
            v9 = v10;
            v10 = *(char **)v10;
            if ( !v11 )
              goto LABEL_20;
          }
          *(_QWORD *)v9 = v11;
          *(_QWORD *)v10 = 0;
          v6 = dword_18001E610;
        }
      }
LABEL_20:
      g_DSLinkList = v7;
      dword_18001E610 = v6 - 1;
    }
    *((_DWORD *)this + 56) = 0;
    if ( !dword_18001E610 )
    {
      v12 = hHandle;
      if ( hHandle )
      {
        if ( !hEvent )
        {
LABEL_27:
          if ( v12 )
          {
            CloseHandle(v12);
            hHandle = 0;
          }
          goto LABEL_29;
        }
        dword_18001E600 = 1;
        SetEvent(hEvent);
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        v12 = hHandle;
      }
      if ( hEvent )
      {
        CloseHandle(hEvent);
        v12 = hHandle;
        hEvent = 0;
      }
      goto LABEL_27;
    }
  }
LABEL_29:
  LeaveCriticalSection(&CriticalSection);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v13 = *((_QWORD *)this + 15);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 15) = 0;
  }
  v14 = *((_QWORD *)this + 14);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 14) = 0;
  }
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 54) = 1000;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  return 0;
}

```

## disassembly

```asm
0x18000f650  push    rbx
0x18000f652  push    rsi
0x18000f653  push    rdi
0x18000f654  sub     rsp, 50h
0x18000f658  mov     rbx, rcx
0x18000f65b  add     rcx, 88h; lpCriticalSection
0x18000f662  call    cs:__imp_EnterCriticalSection
0x18000f668  mov     rcx, [rbx+78h]
0x18000f66c  xor     esi, esi
0x18000f66e  test    rcx, rcx
0x18000f671  jz      loc_18000F75B
0x18000f677  mov     r8d, [rbx+0D4h]
0x18000f67e  lea     rdx, [rsp+68h+arg_8]
0x18000f683  mov     [rsp+68h+var_30], esi
0x18000f687  lea     r9, [rsp+68h+arg_18]
0x18000f68f  mov     [rsp+68h+var_38], rdx
0x18000f694  lea     rdx, [rsp+68h+arg_10]
0x18000f69c  mov     [rsp+68h+var_40], rdx
0x18000f6a1  lea     rdx, [rsp+68h+Size]
0x18000f6a6  mov     [rsp+68h+arg_18], rsi
0x18000f6ae  mov     [rsp+68h+arg_10], rsi
0x18000f6b6  mov     dword ptr [rsp+68h+Size], esi
0x18000f6ba  mov     dword ptr [rsp+68h+arg_8], esi
0x18000f6be  mov     rax, [rcx]
0x18000f6c1  mov     [rsp+68h+var_48], rdx
0x18000f6c6  xor     edx, edx
0x18000f6c8  mov     rax, [rax+58h]
0x18000f6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d1  test    eax, eax
0x18000f6d3  js      short loc_18000F748
0x18000f6d5  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18000f6da  test    r8d, r8d
0x18000f6dd  jz      short loc_18000F6F3
0x18000f6df  mov     rcx, [rsp+68h+arg_18]; void *
0x18000f6e7  xor     edx, edx; Val
0x18000f6e9  call    memset_0
0x18000f6ee  mov     r8d, dword ptr [rsp+68h+Size]
0x18000f6f3  mov     edx, dword ptr [rsp+68h+arg_8]
0x18000f6f7  test    edx, edx
0x18000f6f9  jz      short loc_18000F716
0x18000f6fb  mov     rcx, [rsp+68h+arg_10]; void *
0x18000f703  mov     r8d, edx; Size
0x18000f706  xor     edx, edx; Val
0x18000f708  call    memset_0
0x18000f70d  mov     r8d, dword ptr [rsp+68h+Size]
0x18000f712  mov     edx, dword ptr [rsp+68h+arg_8]
0x18000f716  mov     rcx, [rbx+78h]
0x18000f71a  mov     r9, [rsp+68h+arg_10]
0x18000f722  mov     dword ptr [rsp+68h+var_48], edx
0x18000f726  mov     rdx, [rsp+68h+arg_18]
0x18000f72e  mov     rax, [rcx]
0x18000f731  mov     rax, [rax+98h]
0x18000f738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f73d  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000f742  call    cs:__imp_Sleep
0x18000f748  mov     rcx, [rbx+78h]
0x18000f74c  mov     rax, [rcx]
0x18000f74f  mov     rax, [rax+90h]
0x18000f756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f75b  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000f762  mov     dword ptr [rbx+28h], 1
0x18000f769  call    cs:__imp_LeaveCriticalSection
0x18000f76f  lea     rcx, CriticalSection; lpCriticalSection
0x18000f776  call    cs:__imp_EnterCriticalSection
0x18000f77c  cmp     [rbx+0E0h], esi
0x18000f782  jz      loc_18000F87A
0x18000f788  mov     r9d, cs:dword_18001E610
0x18000f78f  test    r9d, r9d
0x18000f792  jz      short loc_18000F7F3
0x18000f794  mov     rcx, cs:?g_DSLinkList@@3VCDSLinkList@@A; CDSLinkList g_DSLinkList
0x18000f79b  lea     r8, [rbx+10h]
0x18000f79f  test    rbx, rbx
0x18000f7a2  cmovz   r8, rsi
0x18000f7a6  cmp     r8, rcx
0x18000f7a9  jnz     short loc_18000F7B0
0x18000f7ab  mov     rcx, [rcx]
0x18000f7ae  jmp     short loc_18000F7E2
0x18000f7b0  mov     r10, rsi
0x18000f7b3  mov     rax, rcx
0x18000f7b6  test    rcx, rcx
0x18000f7b9  jz      short loc_18000F7E2
0x18000f7bb  nop     dword ptr [rax+rax+00h]
0x18000f7c0  mov     rdx, [rax]
0x18000f7c3  cmp     rax, r8
0x18000f7c6  jz      short loc_18000F7D5
0x18000f7c8  mov     r10, rax
0x18000f7cb  mov     rax, rdx
0x18000f7ce  test    rdx, rdx
0x18000f7d1  jnz     short loc_18000F7C0
0x18000f7d3  jmp     short loc_18000F7E2
0x18000f7d5  mov     [r10], rdx
0x18000f7d8  mov     [rax], rsi
0x18000f7db  mov     r9d, cs:dword_18001E610
0x18000f7e2  dec     r9d
0x18000f7e5  mov     cs:?g_DSLinkList@@3VCDSLinkList@@A, rcx; CDSLinkList g_DSLinkList
0x18000f7ec  mov     cs:dword_18001E610, r9d
0x18000f7f3  mov     [rbx+0E0h], esi
0x18000f7f9  cmp     cs:dword_18001E610, esi
0x18000f7ff  jnz     short loc_18000F87A
0x18000f801  mov     rcx, cs:hHandle
0x18000f808  test    rcx, rcx
0x18000f80b  jz      short loc_18000F845
0x18000f80d  mov     rax, cs:hEvent
0x18000f814  test    rax, rax
0x18000f817  jz      short loc_18000F868
0x18000f819  mov     rcx, rax; hEvent
0x18000f81c  mov     cs:dword_18001E600, 1
0x18000f826  call    cs:__imp_SetEvent
0x18000f82c  mov     rcx, cs:hHandle; hHandle
0x18000f833  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000f838  call    cs:__imp_WaitForSingleObject
0x18000f83e  mov     rcx, cs:hHandle
0x18000f845  mov     rax, cs:hEvent
0x18000f84c  test    rax, rax
0x18000f84f  jz      short loc_18000F868
0x18000f851  mov     rcx, rax; hObject
0x18000f854  call    cs:__imp_CloseHandle
0x18000f85a  mov     rcx, cs:hHandle; hObject
0x18000f861  mov     cs:hEvent, rsi
0x18000f868  test    rcx, rcx
0x18000f86b  jz      short loc_18000F87A
0x18000f86d  call    cs:__imp_CloseHandle
0x18000f873  mov     cs:hHandle, rsi
0x18000f87a  lea     rcx, CriticalSection; lpCriticalSection
0x18000f881  call    cs:__imp_LeaveCriticalSection
0x18000f887  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000f88e  call    cs:__imp_EnterCriticalSection
0x18000f894  mov     rcx, [rbx+78h]
0x18000f898  test    rcx, rcx
0x18000f89b  jz      short loc_18000F8AD
0x18000f89d  mov     rax, [rcx]
0x18000f8a0  mov     rax, [rax+10h]
0x18000f8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a9  mov     [rbx+78h], rsi
0x18000f8ad  mov     rcx, [rbx+70h]
0x18000f8b1  test    rcx, rcx
0x18000f8b4  jz      short loc_18000F8C6
0x18000f8b6  mov     rax, [rcx]
0x18000f8b9  mov     rax, [rax+10h]
0x18000f8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8c2  mov     [rbx+70h], rsi
0x18000f8c6  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000f8cd  mov     [rbx+0B8h], rsi
0x18000f8d4  mov     [rbx+0C0h], esi
0x18000f8da  mov     [rbx+0C8h], rsi
0x18000f8e1  mov     [rbx+0D0h], rsi
0x18000f8e8  mov     dword ptr [rbx+0D8h], 3E8h
0x18000f8f2  call    cs:__imp_LeaveCriticalSection
0x18000f8f8  xor     eax, eax
0x18000f8fa  add     rsp, 50h
0x18000f8fe  pop     rdi
0x18000f8ff  pop     rsi
0x18000f900  pop     rbx
0x18000f901  retn
```
