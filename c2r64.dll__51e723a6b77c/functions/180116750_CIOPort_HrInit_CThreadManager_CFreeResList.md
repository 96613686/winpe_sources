# CIOPort::HrInit(CThreadManager *,CFreeResList *)

- ea: `0x180116750`
- end: `0x18011681e`
- name: `?HrInit@CIOPort@@UEAAJPEAVCThreadManager@@PEAVCFreeResList@@@Z`
- size: `206`
- prototype: `int(CIOPort *__hidden this, struct CThreadManager *, struct CFreeResList *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800264b4`
- `0x180105b44`
- `0x180107874`
- `0x180116750`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180116791`
- `KERNEL32!GetTickCount64` at `0x180116791`
- `KERNEL32!CreateIoCompletionPort` at `0x1801167d1`
- `KERNEL32!CreateIoCompletionPort` at `0x1801167d1`

## pseudocode

```c
__int64 __fastcall CIOPort::HrInit(CIOPort *this, struct CThreadManager *a2, struct CFreeResList *a3)
{
  int v4; // edi
  unsigned int IdealConcurrencyValue; // eax
  unsigned int v6; // ecx
  unsigned int v7; // eax
  DWORD v8; // r9d

  if ( *((_QWORD *)this + 16) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    *((_QWORD *)this + 1) = a2;
    v4 = CTpQueue::HrInit((CIOPort *)((char *)this + 144), a3);
    if ( v4 >= 0 )
    {
      _mm_lfence();
      *((_QWORD *)this + 13) = GetTickCount64();
      IdealConcurrencyValue = MsoGetIdealConcurrencyValue();
      v6 = 4;
      if ( IdealConcurrencyValue )
        v6 = IdealConcurrencyValue;
      v7 = 512;
      if ( v6 < 0x200 )
        v7 = v6;
      v8 = 127;
      if ( v7 < 0x7F )
        v8 = v7;
      *((_DWORD *)this + 34) = v8;
      *((_QWORD *)this + 16) = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, v8);
      *((_DWORD *)this + 4) = *((_DWORD *)this + 34) ^ (*((_DWORD *)this + 34) ^ *((_DWORD *)this + 4)) & 0xFFFFF000;
      if ( (*(unsigned int (__fastcall **)(CIOPort *))(*(_QWORD *)this + 32LL))(this) )
        MsoShipAssertTagProc(507553949);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180116750  mov     [rsp+arg_0], rbx
0x180116755  push    rdi
0x180116756  sub     rsp, 20h
0x18011675a  mov     rbx, rcx
0x18011675d  cmp     qword ptr [rcx+80h], 0
0x180116765  jz      short loc_180116771
0x180116767  mov     edi, 80004005h
0x18011676c  jmp     loc_180116811
0x180116771  mov     [rcx+8], rdx
0x180116775  add     rcx, 90h; this
0x18011677c  mov     rdx, r8; struct CTpFreeList *
0x18011677f  call    ?HrInit@CTpQueue@@QEAAJPEAVCTpFreeList@@@Z; CTpQueue::HrInit(CTpFreeList *)
0x180116784  mov     edi, eax
0x180116786  test    eax, eax
0x180116788  js      loc_180116811
0x18011678e  lfence
0x180116791  call    cs:__imp_GetTickCount64
0x180116797  mov     [rbx+68h], rax
0x18011679b  call    ?MsoGetIdealConcurrencyValue@@YAKXZ; MsoGetIdealConcurrencyValue(void)
0x1801167a0  mov     ecx, 4
0x1801167a5  test    eax, eax
0x1801167a7  cmovnz  ecx, eax
0x1801167aa  mov     eax, 200h
0x1801167af  cmp     ecx, eax
0x1801167b1  cmovb   eax, ecx
0x1801167b4  mov     r9d, 7Fh
0x1801167ba  cmp     eax, r9d
0x1801167bd  cmovb   r9d, eax; NumberOfConcurrentThreads
0x1801167c1  mov     [rbx+88h], r9d
0x1801167c8  xor     r8d, r8d; CompletionKey
0x1801167cb  xor     edx, edx; ExistingCompletionPort
0x1801167cd  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1801167d1  call    cs:__imp_CreateIoCompletionPort
0x1801167d7  mov     [rbx+80h], rax
0x1801167de  mov     ecx, [rbx+88h]
0x1801167e4  mov     eax, [rbx+10h]
0x1801167e7  xor     eax, ecx
0x1801167e9  and     eax, 0FFFFF000h
0x1801167ee  xor     eax, ecx
0x1801167f0  mov     [rbx+10h], eax
0x1801167f3  mov     rax, [rbx]
0x1801167f6  mov     rcx, rbx
0x1801167f9  mov     rax, [rax+20h]
0x1801167fd  call    cs:__guard_dispatch_icall_fptr
0x180116803  test    eax, eax
0x180116805  jz      short loc_180116811
0x180116807  mov     ecx, 1E40A89Dh
0x18011680c  call    MsoShipAssertTagProc
0x180116811  mov     eax, edi
0x180116813  mov     rbx, [rsp+28h+arg_0]
0x180116818  add     rsp, 20h
0x18011681c  pop     rdi
0x18011681d  retn
```
