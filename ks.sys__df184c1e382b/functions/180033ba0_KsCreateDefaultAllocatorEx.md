# KsCreateDefaultAllocatorEx

- ea: `0x180033ba0`
- end: `0x180033f0c`
- name: `KsCreateDefaultAllocatorEx`
- size: `876`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PVOID InitializeContext, PFNKSDEFAULTALLOCATE DefaultAllocate, PFNKSDEFAULTFREE DefaultFree, PFNKSINITIALIZEALLOCATOR InitializeAllocator, PFNKSDELETEALLOCATOR DeleteAllocator)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180033b70`
- `0x18003f2f0`

## callees

- `0x1800088b0`
- `0x180019cb0`
- `0x18001a000`
- `0x180033ba0`
- `0x180033f20`
- `0x180051360`
- `0x180051630`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x180033dc2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180033db4`
- `ntoskrnl!KeInitializeSpinLock` at `0x180033cd9`
- `ntoskrnl!KeInitializeSpinLock` at `0x180033ce9`
- `ntoskrnl!KeInitializeSpinLock` at `0x180033cd9`
- `ntoskrnl!KeInitializeSpinLock` at `0x180033ce9`
- `ntoskrnl!KeInitializeEvent` at `0x180033e79`
- `ntoskrnl!KeInitializeEvent` at `0x180033e79`
- `ntoskrnl!ExFreePoolWithTag` at `0x180033c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180033d39`
- `ntoskrnl!ExFreePoolWithTag` at `0x180033c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180033d39`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180033c2c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180033c2c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180033e0d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180033e01`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180033e01`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180033d9a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x180033d9a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180033da6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x180033e29`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180033e1b`

## pseudocode

```c
NTSTATUS __stdcall KsCreateDefaultAllocatorEx(
        PIRP Irp,
        PVOID InitializeContext,
        PFNKSDEFAULTALLOCATE DefaultAllocate,
        PFNKSDEFAULTFREE DefaultFree,
        PFNKSINITIALIZEALLOCATOR InitializeAllocator,
        PFNKSDELETEALLOCATOR DeleteAllocator)
{
  NTSTATUS result; // eax
  PKSALLOCATOR_FRAMING v11; // rsi
  ULONG FileAlignment; // ecx
  __int32 v13; // ebx
  SIZE_T v14; // rbp
  char *PoolWithTag; // rax
  char *v16; // rdi
  int ObjectHeader; // ebp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  _QWORD *v19; // r14
  int v20; // ebx
  PKSALLOCATOR_FRAMING AllocatorFraming; // [rsp+40h] [rbp-68h] BYREF
  GUID InBuffer; // [rsp+48h] [rbp-60h] BYREF
  __int64 v24; // [rsp+58h] [rbp-50h]

  v24 = 0;
  AllocatorFraming = 0;
  InBuffer = 0;
  result = KsValidateAllocatorCreateRequest(Irp, &AllocatorFraming);
  if ( result >= 0 )
  {
    v11 = AllocatorFraming;
    FileAlignment = AllocatorFraming->FileAlignment;
    if ( FileAlignment <= 0xFFF )
    {
      if ( DefaultAllocate )
      {
        v13 = 2;
        v14 = 224;
        goto LABEL_7;
      }
      if ( ((FileAlignment + 1) & FileAlignment) == 0 )
      {
        v14 = 352;
        v13 = AllocatorFraming->PoolType & 1;
LABEL_7:
        PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v14, 0x6961534Bu);
        v16 = PoolWithTag;
        if ( ExPoolZeroingNativelySupported )
        {
          if ( PoolWithTag )
          {
LABEL_10:
            ObjectHeader = KsAllocateObjectHeader((KSOBJECT_HEADER *)v16, 0, 0, Irp, &Table);
            if ( ObjectHeader < 0 )
            {
              ExFreePoolWithTag(v16, 0);
              return ObjectHeader;
            }
            *(_OWORD *)(v16 + 56) = *(_OWORD *)&v11->OptionsFlags;
            *((_QWORD *)v16 + 9) = *(_QWORD *)&v11->FileAlignment;
            CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
            CurrentStackLocation->FileObject->FsContext = v16;
            *((_QWORD *)v16 + 4) = v16 + 24;
            *((_QWORD *)v16 + 3) = v16 + 24;
            *((_QWORD *)v16 + 6) = v16 + 40;
            *((_QWORD *)v16 + 5) = v16 + 40;
            KeInitializeSpinLock((PKSPIN_LOCK)v16 + 2);
            KeInitializeSpinLock((PKSPIN_LOCK)v16 + 14);
            *((_DWORD *)v16 + 2) = 0;
            v19 = v16 + 176;
            if ( v13 )
            {
              if ( v13 == 1 )
              {
                *v19 = v16 + 224;
                ExInitializePagedLookasideList(
                  (PPAGED_LOOKASIDE_LIST)(v16 + 224),
                  (PALLOCATE_FUNCTION)DefAllocatorAlloc,
                  (PFREE_FUNCTION)DefAllocatorFree,
                  0,
                  v11->FrameSize,
                  v11->FileAlignment,
                  v11->Frames);
                *((_QWORD *)v16 + 19) = ExAllocateFromPagedLookasideList;
                *((_QWORD *)v16 + 20) = ExFreeToPagedLookasideList;
                DeleteAllocator = (PFNKSDELETEALLOCATOR)ExDeletePagedLookasideList;
              }
              else
              {
                v20 = ((__int64 (__fastcall *)(PVOID, PKSALLOCATOR_FRAMING, char *))InitializeAllocator)(
                        InitializeContext,
                        v11,
                        v16 + 176);
                if ( v20 < 0 )
                  goto LABEL_17;
                *((_QWORD *)v16 + 19) = DefaultAllocate;
                *((_QWORD *)v16 + 20) = DefaultFree;
              }
            }
            else
            {
              *v19 = v16 + 224;
              ExInitializeNPagedLookasideList(
                (PNPAGED_LOOKASIDE_LIST)(v16 + 224),
                (PALLOCATE_FUNCTION)DefAllocatorAlloc,
                (PFREE_FUNCTION)DefAllocatorFree,
                0x200u,
                v11->FrameSize,
                v11->FileAlignment,
                v11->Frames);
              *((_QWORD *)v16 + 19) = ExAllocateFromNPagedLookasideList;
              *((_QWORD *)v16 + 20) = ExFreeToNPagedLookasideList;
              DeleteAllocator = (PFNKSDELETEALLOCATOR)ExDeleteNPagedLookasideList;
            }
            *((_QWORD *)v16 + 21) = DeleteAllocator;
            *((_QWORD *)v16 + 16) = 0;
            *((_QWORD *)v16 + 18) = v16;
            *((_QWORD *)v16 + 17) = FreeWorker;
            *((_QWORD *)v16 + 15) = 0;
            *((_DWORD *)v16 + 20) = 32;
            *((_QWORD *)v16 + 13) = 0;
            *((_QWORD *)v16 + 11) = v16 + 120;
            *((_DWORD *)v16 + 24) = 0;
            KeInitializeEvent((PRKEVENT)(v16 + 184), NotificationEvent, 0);
            *((_QWORD *)v16 + 26) = 0;
            v24 = 0x100000000LL;
            InBuffer = KSEVENTSETID_StreamAllocator;
            v20 = KsSynchronousIoControlDevice(
                    CurrentStackLocation->FileObject,
                    0,
                    0x2F0007u,
                    &InBuffer,
                    0x18u,
                    v16 + 80,
                    0x20u,
                    (PULONG)&AllocatorFraming);
            if ( v20 >= 0 )
              return v20;
            (*((void (__fastcall **)(_QWORD))v16 + 21))(*v19);
LABEL_17:
            KsFreeObjectHeader(*(KSOBJECT_HEADER *)v16);
            ExFreePoolWithTag(v16, 0);
            return v20;
          }
        }
        else if ( PoolWithTag )
        {
          memset(PoolWithTag, 0, v14);
          goto LABEL_10;
        }
        return -1073741670;
      }
    }
    return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x180033ba0  push    rbx
0x180033ba2  push    rbp
0x180033ba3  push    rsi
0x180033ba4  push    rdi
0x180033ba5  push    r12
0x180033ba7  push    r13
0x180033ba9  push    r14
0x180033bab  push    r15
0x180033bad  sub     rsp, 68h
0x180033bb1  xor     eax, eax
0x180033bb3  mov     r13, rdx
0x180033bb6  xorps   xmm0, xmm0
0x180033bb9  mov     [rsp+0A8h+var_50], rax
0x180033bbe  lea     rdx, [rsp+0A8h+AllocatorFraming]; AllocatorFraming
0x180033bc3  mov     [rsp+0A8h+AllocatorFraming], rax
0x180033bc8  movups  [rsp+0A8h+InBuffer], xmm0
0x180033bcd  mov     r12, r9
0x180033bd0  mov     r15, r8
0x180033bd3  mov     r14, rcx
0x180033bd6  call    KsValidateAllocatorCreateRequest
0x180033bdb  test    eax, eax
0x180033bdd  js      loc_180033EFA
0x180033be3  mov     rsi, [rsp+0A8h+AllocatorFraming]
0x180033be8  mov     ecx, [rsi+10h]
0x180033beb  cmp     ecx, 0FFFh
0x180033bf1  ja      loc_180033EF5
0x180033bf7  test    r15, r15
0x180033bfa  jz      short loc_180033C08
0x180033bfc  mov     ebx, 2
0x180033c01  mov     ebp, 0E0h
0x180033c06  jmp     short loc_180033C1E
0x180033c08  lea     eax, [rcx+1]
0x180033c0b  test    ecx, eax
0x180033c0d  jnz     loc_180033EF5
0x180033c13  mov     ebx, [rsi+4]
0x180033c16  mov     ebp, 160h
0x180033c1b  and     ebx, 1
0x180033c1e  mov     r8d, 6961534Bh; Tag
0x180033c24  mov     rdx, rbp; NumberOfBytes
0x180033c27  mov     ecx, 600h; PoolType
0x180033c2c  call    cs:__imp_ExAllocatePoolWithTag
0x180033c33  nop     dword ptr [rax+rax+00h]
0x180033c38  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180033c3f  mov     rdi, rax
0x180033c42  jnz     short loc_180033C90
0x180033c44  test    rax, rax
0x180033c47  jz      short loc_180033C95
0x180033c49  mov     r8, rbp; Size
0x180033c4c  xor     edx, edx; Val
0x180033c4e  mov     rcx, rax; void *
0x180033c51  call    memset
0x180033c56  lea     rax, Table
0x180033c5d  mov     r9, r14; Irp
0x180033c60  xor     r8d, r8d; ItemsList
0x180033c63  mov     [rsp+0A8h+Table], rax; Table
0x180033c68  xor     edx, edx; ItemsCount
0x180033c6a  mov     rcx, rdi; Header
0x180033c6d  call    KsAllocateObjectHeader
0x180033c72  mov     ebp, eax
0x180033c74  test    eax, eax
0x180033c76  jns     short loc_180033C9F
0x180033c78  xor     edx, edx; Tag
0x180033c7a  mov     rcx, rdi; P
0x180033c7d  call    cs:__imp_ExFreePoolWithTag
0x180033c84  nop     dword ptr [rax+rax+00h]
0x180033c89  mov     eax, ebp
0x180033c8b  jmp     loc_180033EFA
0x180033c90  test    rdi, rdi
0x180033c93  jnz     short loc_180033C56
0x180033c95  mov     eax, 0C000009Ah
0x180033c9a  jmp     loc_180033EFA
0x180033c9f  movups  xmm0, xmmword ptr [rsi]
0x180033ca2  lea     rcx, [rdi+10h]; SpinLock
0x180033ca6  movups  xmmword ptr [rdi+38h], xmm0
0x180033caa  movsd   xmm1, qword ptr [rsi+10h]
0x180033caf  movsd   qword ptr [rdi+48h], xmm1
0x180033cb4  mov     rbp, [r14+0B8h]
0x180033cbb  mov     rax, [rbp+30h]
0x180033cbf  mov     [rax+18h], rdi
0x180033cc3  lea     rax, [rdi+18h]
0x180033cc7  mov     [rax+8], rax
0x180033ccb  mov     [rax], rax
0x180033cce  lea     rax, [rdi+28h]
0x180033cd2  mov     [rax+8], rax
0x180033cd6  mov     [rax], rax
0x180033cd9  call    cs:__imp_KeInitializeSpinLock
0x180033ce0  nop     dword ptr [rax+rax+00h]
0x180033ce5  lea     rcx, [rdi+70h]; SpinLock
0x180033ce9  call    cs:__imp_KeInitializeSpinLock
0x180033cf0  nop     dword ptr [rax+rax+00h]
0x180033cf5  mov     dword ptr [rdi+8], 0
0x180033cfc  lea     r14, [rdi+0B0h]
0x180033d03  test    ebx, ebx
0x180033d05  jz      loc_180033DCB
0x180033d0b  cmp     ebx, 1
0x180033d0e  jz      short loc_180033D67
0x180033d10  mov     rax, [rsp+0A8h+InitializeAllocator]
0x180033d18  mov     r8, r14
0x180033d1b  mov     rdx, rsi
0x180033d1e  mov     rcx, r13
0x180033d21  call    _guard_dispatch_icall
0x180033d26  mov     ebx, eax
0x180033d28  test    eax, eax
0x180033d2a  jns     short loc_180033D4C
0x180033d2c  mov     rcx, [rdi]; Header
0x180033d2f  call    KsFreeObjectHeader
0x180033d34  xor     edx, edx; Tag
0x180033d36  mov     rcx, rdi; P
0x180033d39  call    cs:__imp_ExFreePoolWithTag
0x180033d40  nop     dword ptr [rax+rax+00h]
0x180033d45  mov     eax, ebx
0x180033d47  jmp     loc_180033EFA
0x180033d4c  mov     rax, [rsp+0A8h+DeleteAllocator]
0x180033d54  mov     [rdi+98h], r15
0x180033d5b  mov     [rdi+0A0h], r12
0x180033d62  jmp     loc_180033E30
0x180033d67  lea     rcx, [rdi+0E0h]; Lookaside
0x180033d6e  xor     r9d, r9d; Flags
0x180033d71  mov     [r14], rcx
0x180033d74  lea     r8, DefAllocatorFree; Free
0x180033d7b  movzx   eax, word ptr [rsi+8]
0x180033d7f  mov     edx, [rsi+0Ch]
0x180033d82  mov     [rsp+0A8h+Depth], ax; Depth
0x180033d87  mov     eax, [rsi+10h]
0x180033d8a  mov     [rsp+0A8h+Tag], eax; Tag
0x180033d8e  mov     [rsp+0A8h+Table], rdx; Size
0x180033d93  lea     rdx, DefAllocatorAlloc; Allocate
0x180033d9a  call    cs:__imp_ExInitializePagedLookasideList
0x180033da1  nop     dword ptr [rax+rax+00h]
0x180033da6  mov     rax, cs:__imp_ExAllocateFromPagedLookasideList
0x180033dad  mov     [rdi+98h], rax
0x180033db4  mov     rax, cs:__imp_ExFreeToPagedLookasideList
0x180033dbb  mov     [rdi+0A0h], rax
0x180033dc2  mov     rax, cs:__imp_ExDeletePagedLookasideList
0x180033dc9  jmp     short loc_180033E30
0x180033dcb  lea     rcx, [rdi+0E0h]; Lookaside
0x180033dd2  mov     r9d, 200h; Flags
0x180033dd8  mov     [r14], rcx
0x180033ddb  lea     r8, DefAllocatorFree; Free
0x180033de2  movzx   eax, word ptr [rsi+8]
0x180033de6  mov     edx, [rsi+0Ch]
0x180033de9  mov     [rsp+0A8h+Depth], ax; Depth
0x180033dee  mov     eax, [rsi+10h]
0x180033df1  mov     [rsp+0A8h+Tag], eax; Tag
0x180033df5  mov     [rsp+0A8h+Table], rdx; Size
0x180033dfa  lea     rdx, DefAllocatorAlloc; Allocate
0x180033e01  call    cs:__imp_ExInitializeNPagedLookasideList
0x180033e08  nop     dword ptr [rax+rax+00h]
0x180033e0d  mov     rax, cs:__imp_ExAllocateFromNPagedLookasideList
0x180033e14  mov     [rdi+98h], rax
0x180033e1b  mov     rax, cs:__imp_ExFreeToNPagedLookasideList
0x180033e22  mov     [rdi+0A0h], rax
0x180033e29  mov     rax, cs:__imp_ExDeleteNPagedLookasideList
0x180033e30  xor     r15d, r15d
0x180033e33  mov     [rdi+0A8h], rax
0x180033e3a  lea     rax, [rdi+78h]
0x180033e3e  mov     [rdi+80h], r15
0x180033e45  lea     rcx, FreeWorker
0x180033e4c  mov     [rax+18h], rdi
0x180033e50  mov     [rax+10h], rcx
0x180033e54  lea     rbx, [rdi+50h]
0x180033e58  lea     esi, [r15+20h]
0x180033e5c  mov     [rax], r15
0x180033e5f  lea     rcx, [rdi+0B8h]; Event
0x180033e66  mov     [rbx], esi
0x180033e68  xor     r8d, r8d; State
0x180033e6b  mov     [rdi+68h], r15
0x180033e6f  xor     edx, edx; Type
0x180033e71  mov     [rdi+58h], rax
0x180033e75  mov     [rdi+60h], r15d
0x180033e79  call    cs:__imp_KeInitializeEvent
0x180033e80  nop     dword ptr [rax+rax+00h]
0x180033e85  mov     [rdi+0D0h], r15
0x180033e8c  lea     rax, [rsp+0A8h+AllocatorFraming]
0x180033e91  movups  xmm0, xmmword ptr cs:KSEVENTSETID_StreamAllocator.Data1
0x180033e98  mov     [rsp+0A8h+BytesReturned], rax; BytesReturned
0x180033e9d  lea     r9, [rsp+0A8h+InBuffer]; InBuffer
0x180033ea2  mov     dword ptr [rsp+0A8h+var_50], r15d
0x180033ea7  xor     edx, edx; RequestorMode
0x180033ea9  movdqu  [rsp+0A8h+InBuffer], xmm0
0x180033eaf  mov     dword ptr [rsp+0A8h+var_50+4], 1
0x180033eb7  mov     r8d, 2F0007h; IoControl
0x180033ebd  mov     rcx, [rbp+30h]; FileObject
0x180033ec1  mov     dword ptr [rsp+0A8h+Depth], esi; OutSize
0x180033ec5  mov     qword ptr [rsp+0A8h+Tag], rbx; OutBuffer
0x180033eca  mov     dword ptr [rsp+0A8h+Table], 18h; InSize
0x180033ed2  call    KsSynchronousIoControlDevice
0x180033ed7  mov     ebx, eax
0x180033ed9  test    eax, eax
0x180033edb  jns     loc_180033D45
0x180033ee1  mov     rax, [rdi+0A8h]
0x180033ee8  mov     rcx, [r14]
0x180033eeb  call    _guard_dispatch_icall
0x180033ef0  jmp     loc_180033D2C
0x180033ef5  mov     eax, 0C000000Dh
0x180033efa  add     rsp, 68h
0x180033efe  pop     r15
0x180033f00  pop     r14
0x180033f02  pop     r13
0x180033f04  pop     r12
0x180033f06  pop     rdi
0x180033f07  pop     rsi
0x180033f08  pop     rbp
0x180033f09  pop     rbx
0x180033f0a  retn
```
