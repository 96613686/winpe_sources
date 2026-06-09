# RxUninitializeCacheMap

- ea: `0x140071990`
- end: `0x140071aae`
- name: `RxUninitializeCacheMap`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140045410`
- `0x14006c5c0`

## callees

- `0x140016e20`
- `0x140016ec0`
- `0x140017040`
- `0x1400180a8`
- `0x140071990`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400719d6`
- `ntoskrnl!KeInitializeEvent` at `0x1400719d6`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400719f4`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400719f4`

## pseudocode

```c
__int64 __fastcall RxUninitializeCacheMap(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        LARGE_INTEGER *a3,
        struct _CACHE_UNINITIALIZE_EVENT *a4)
{
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  PVOID FsContext; // rdx
  LARGE_INTEGER v13; // rax

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    FsContext = a2->FsContext;
    if ( a3 )
      v13 = *a3;
    else
      v13.QuadPart = 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqi)(
      WPP_GLOBAL_Control->AttachedDevice,
      FsContext,
      a3,
      a2,
      FsContext,
      (LARGE_INTEGER)v13.QuadPart);
  }
  if ( a4 )
    KeInitializeEvent(&a4->Event, SynchronizationEvent, 0);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0pp_EtwWriteTransfer(v8, &CcUninitializeRequest, a1 + 412, a1, a2);
  v10 = CcUninitializeCacheMap(a2, a3, a4);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(v9, &CcUninitializeCompletion, a1 + 412, a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, &WPP_62be9881804536e6c54be111b50a5a79_Traceguids, v10);
  }
  return (unsigned __int8)v10;
}

```

## disassembly

```asm
0x140071990  push    rbx
0x140071992  push    rbp
0x140071993  push    rsi
0x140071994  push    rdi
0x140071995  push    r14
0x140071997  push    r15
0x140071999  sub     rsp, 38h
0x14007199d  mov     rbx, r9
0x1400719a0  mov     r14, r8
0x1400719a3  mov     rbp, rdx
0x1400719a6  mov     rdi, rcx
0x1400719a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400719b0  lea     r15, WPP_GLOBAL_Control
0x1400719b7  cmp     rcx, r15
0x1400719ba  jz      short loc_1400719C5
0x1400719bc  test    dword ptr [rcx+2Ch], 200h
0x1400719c3  jnz     short loc_140071A32
0x1400719c5  test    rbx, rbx
0x1400719c8  jz      short loc_1400719E2
0x1400719ca  lea     rcx, [rbx+8]; Event
0x1400719ce  xor     r8d, r8d; State
0x1400719d1  mov     edx, 1; Type
0x1400719d6  call    cs:__imp_KeInitializeEvent
0x1400719dd  nop     dword ptr [rax+rax+00h]
0x1400719e2  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x1400719e9  jnz     short loc_140071A4D
0x1400719eb  mov     r8, rbx; UninitializeEvent
0x1400719ee  mov     rdx, r14; TruncateSize
0x1400719f1  mov     rcx, rbp; FileObject
0x1400719f4  call    cs:__imp_CcUninitializeCacheMap
0x1400719fb  nop     dword ptr [rax+rax+00h]
0x140071a00  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140071a07  movzx   ebx, al
0x140071a0a  jnz     short loc_140071A6A
0x140071a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140071a13  cmp     rcx, r15
0x140071a16  jz      short loc_140071A21
0x140071a18  test    dword ptr [rcx+2Ch], 200h
0x140071a1f  jnz     short loc_140071A8B
0x140071a21  movzx   eax, bl
0x140071a24  add     rsp, 38h
0x140071a28  pop     r15
0x140071a2a  pop     r14
0x140071a2c  pop     rdi
0x140071a2d  pop     rsi
0x140071a2e  pop     rbp
0x140071a2f  pop     rbx
0x140071a30  retn
0x140071a32  cmp     byte ptr [rcx+29h], 4
0x140071a36  jb      short loc_1400719C5
0x140071a38  mov     rdx, [rdx+18h]
0x140071a3c  test    r14, r14
0x140071a3f  jz      loc_14007F72C
0x140071a45  mov     rax, [r8]
0x140071a48  jmp     loc_14007F72E
0x140071a4d  mov     r9, rdi
0x140071a50  mov     [rsp+68h+var_48], rbp
0x140071a55  lea     r8, [rdi+19Ch]
0x140071a5c  lea     rdx, CcUninitializeRequest
0x140071a63  call    McTemplateK0pp_EtwWriteTransfer
0x140071a68  jmp     short loc_1400719EB
0x140071a6a  mov     dword ptr [rsp+68h+var_40], ebx
0x140071a6e  lea     r8, [rdi+19Ch]
0x140071a75  mov     r9, rdi
0x140071a78  mov     [rsp+68h+var_48], rbp
0x140071a7d  lea     rdx, CcUninitializeCompletion
0x140071a84  call    McTemplateK0ppq_EtwWriteTransfer
0x140071a89  jmp     short loc_140071A0C
0x140071a8b  cmp     byte ptr [rcx+29h], 4
0x140071a8f  jb      short loc_140071A21
0x140071a91  mov     rcx, [rcx+18h]
0x140071a95  lea     r8, WPP_62be9881804536e6c54be111b50a5a79_Traceguids
0x140071a9c  mov     edx, 23h ; '#'
0x140071aa1  mov     r9d, ebx
0x140071aa4  call    WPP_SF_d
0x140071aa9  jmp     loc_140071A21
0x14007f72c  xor     eax, eax
0x14007f72e  mov     rcx, [rcx+18h]
0x14007f732  mov     r9, rbp
0x14007f735  mov     [rsp+68h+var_40], rax
0x14007f73a  mov     [rsp+68h+var_48], rdx
0x14007f73f  call    WPP_SF_qqi
0x14007f744  nop
0x14007f745  jmp     loc_1400719C5
```
