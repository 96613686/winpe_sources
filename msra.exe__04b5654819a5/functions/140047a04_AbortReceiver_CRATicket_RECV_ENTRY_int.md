# AbortReceiver(CRATicket *,RECV_ENTRY *,int)

- ea: `0x140047a04`
- end: `0x140047a93`
- name: `?AbortReceiver@@YAJPEAVCRATicket@@PEAURECV_ENTRY@@H@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct CRATicket *, struct RECV_ENTRY *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14002e450`
- `0x140046ee0`
- `0x140048e34`

## callees

- `0x140047a04`
- `0x14004a190`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140047a66`
- `KERNEL32!DeleteFileW` at `0x140047a66`
- `KERNEL32!CloseHandle` at `0x140047a49`
- `KERNEL32!CloseHandle` at `0x140047a49`
- `msvcrt!free` at `0x140047a76`
- `msvcrt!free` at `0x140047a76`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AbortReceiver(struct CRATicket *a1, struct RECV_ENTRY *a2, int a3)
{
  struct IRDPSRAPIVirtualChannel *v4; // rcx
  void *v5; // rcx
  const WCHAR *v6; // rcx

  if ( a2 && a1 )
  {
    *((_DWORD *)a2 + 8) = 8;
    if ( a3 == 1 )
    {
      v4 = (struct IRDPSRAPIVirtualChannel *)*((_QWORD *)a2 + 1);
      if ( v4 )
        SendStringOverVC(v4, L"FILEXFERREJECT", *(_DWORD *)a2, 2u);
    }
    v5 = (void *)*((_QWORD *)a2 + 3);
    if ( v5 )
    {
      CloseHandle(v5);
      *((_QWORD *)a2 + 3) = 0;
    }
    v6 = (const WCHAR *)*((_QWORD *)a2 + 2);
    if ( v6 )
    {
      DeleteFileW(v6);
      free(*((void **)a2 + 2));
      *((_QWORD *)a2 + 2) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140047a04  push    rbx
0x140047a06  sub     rsp, 20h
0x140047a0a  mov     rbx, rdx
0x140047a0d  test    rdx, rdx
0x140047a10  jz      short loc_140047A8A
0x140047a12  test    rcx, rcx
0x140047a15  jz      short loc_140047A8A
0x140047a17  mov     dword ptr [rdx+20h], 8
0x140047a1e  cmp     r8d, 1
0x140047a22  jnz     short loc_140047A40
0x140047a24  mov     rcx, [rdx+8]; struct IRDPSRAPIVirtualChannel *
0x140047a28  test    rcx, rcx
0x140047a2b  jz      short loc_140047A40
0x140047a2d  lea     r9d, [r8+1]; unsigned int
0x140047a31  mov     r8d, [rdx]; int
0x140047a34  lea     rdx, aFilexferreject; "FILEXFERREJECT"
0x140047a3b  call    ?SendStringOverVC@@YAJPEAUIRDPSRAPIVirtualChannel@@PEBGJK@Z; SendStringOverVC(IRDPSRAPIVirtualChannel *,ushort const *,long,ulong)
0x140047a40  mov     rcx, [rbx+18h]; hObject
0x140047a44  test    rcx, rcx
0x140047a47  jz      short loc_140047A5D
0x140047a49  call    cs:__imp_CloseHandle
0x140047a50  nop     dword ptr [rax+rax+00h]
0x140047a55  mov     qword ptr [rbx+18h], 0
0x140047a5d  mov     rcx, [rbx+10h]; lpFileName
0x140047a61  test    rcx, rcx
0x140047a64  jz      short loc_140047A8A
0x140047a66  call    cs:__imp_DeleteFileW
0x140047a6d  nop     dword ptr [rax+rax+00h]
0x140047a72  mov     rcx, [rbx+10h]; Block
0x140047a76  call    cs:__imp_free
0x140047a7d  nop     dword ptr [rax+rax+00h]
0x140047a82  mov     qword ptr [rbx+10h], 0
0x140047a8a  xor     eax, eax
0x140047a8c  add     rsp, 20h
0x140047a90  pop     rbx
0x140047a91  retn
```
