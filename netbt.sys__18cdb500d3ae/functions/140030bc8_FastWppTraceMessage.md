# FastWppTraceMessage

- ea: `0x140030bc8`
- end: `0x140030d59`
- name: `FastWppTraceMessage`
- size: `401`
- prototype: ``
- caller_count: `110`
- callee_count: `3`
- tags: ``

## callers

- `0x140040008`
- `0x1400400a4`
- `0x1400400dc`
- `0x140040164`
- `0x1400401c4`
- `0x140040214`
- `0x14004025c`
- `0x140040294`
- `0x1400402b4`
- `0x14004031c`
- `0x140040360`
- `0x1400403b4`
- `0x140040428`
- `0x140040470`
- `0x1400404c0`
- `0x140040520`
- `0x140040590`
- `0x1400405d4`
- `0x140040628`
- `0x1400406e8`
- `0x140040748`
- `0x1400407dc`
- `0x1400408dc`
- `0x140040a04`
- `0x140040a4c`
- `0x140040ab4`
- `0x140040b10`
- `0x140040b90`
- `0x140040c40`
- `0x140040d00`
- `0x140040d78`
- `0x140040e08`
- `0x140040e9c`
- `0x140040f48`
- `0x140040fcc`
- `0x14004102c`
- `0x140041098`
- `0x140041104`
- `0x140041160`
- `0x1400411d4`
- `0x14004127c`
- `0x1400412fc`
- `0x140041390`
- `0x140041444`
- `0x1400414dc`
- `0x140041580`
- `0x140041604`
- `0x140041654`
- `0x140041718`
- `0x1400417c8`

## callees

- `0x140030b3c`
- `0x140030bc8`
- `0x140030f40`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x140030caa`
- `ntoskrnl!ExAllocatePool3` at `0x140030caa`
- `ntoskrnl!EtwWriteEx` at `0x140030d18`
- `ntoskrnl!EtwWriteEx` at `0x140030d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030d31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030d31`

## pseudocode

```c
void FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  void *v3; // rbx
  __int64 Pool3; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v7; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v8[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  EventDescriptor = 0;
  UserData = 0;
  v7 = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor.Id = a2;
    EventDescriptor.Level = HIBYTE(a1);
    v3 = 0;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE12(v7) = 0;
    DWORD2(v7) = 256;
    EventDescriptor.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    *(_QWORD *)&v7 = v8;
    FastWppPackEvent((__int64 *)va, v8, 256, (char *)&v7 + 8);
    if ( DWORD2(v7) > 0x100 )
    {
      Pool3 = ExAllocatePool3(64, DWORD2(v7), 1180127312, 0, 0);
      v3 = (void *)Pool3;
      if ( Pool3 )
      {
        *(_QWORD *)&v7 = Pool3;
        FastWppPackEvent((__int64 *)va, Pool3, DWORD2(v7), (char *)&v7 + 8);
      }
      else
      {
        DWORD2(v7) = 256;
      }
    }
    EtwWriteEx(FastWppRegHandle, &EventDescriptor, 0, 0, 0, 0, 2u, &UserData);
    if ( v3 )
      ExFreePoolWithTag(v3, 0x46575050u);
  }
}

```

## disassembly

```asm
0x140030bc8  mov     [rsp-8+arg_10], r8
0x140030bcd  mov     [rsp-8+arg_18], r9
0x140030bd2  push    rbp
0x140030bd3  push    rbx
0x140030bd4  push    r15
0x140030bd6  lea     rbp, [rsp-90h]
0x140030bde  sub     rsp, 190h
0x140030be5  mov     rax, cs:__security_cookie
0x140030bec  xor     rax, rsp
0x140030bef  mov     [rbp+0A0h+var_20], rax
0x140030bf6  mov     eax, cs:FastWppInitState
0x140030bfc  xorps   xmm1, xmm1
0x140030bff  mov     [rsp+1A0h+var_160], 0
0x140030c08  xorps   xmm0, xmm0
0x140030c0b  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x140030c10  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x140030c15  movups  [rsp+1A0h+var_138], xmm1
0x140030c1a  cmp     eax, 2
0x140030c1d  jnz     loc_140030D3D
0x140030c23  movzx   eax, cx
0x140030c26  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x140030c2b  shr     ax, 8
0x140030c2f  lea     r15, [rbp+0A0h+arg_18]
0x140030c36  mov     [rsp+1A0h+EventDescriptor.Level], al
0x140030c3a  lea     r9, [rsp+1A0h+var_138+8]
0x140030c3f  xor     ebx, ebx
0x140030c41  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x140030c46  mov     r8d, 100h
0x140030c4c  mov     [rsp+1A0h+var_148.Size], 10h
0x140030c54  lea     rdx, [rbp+0A0h+var_120]
0x140030c58  mov     byte ptr [rsp+1A0h+var_138+0Ch], bl
0x140030c5c  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140030c64  lea     eax, [rbx+1]
0x140030c67  shl     rax, cl
0x140030c6a  mov     rcx, r15
0x140030c6d  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x140030c72  mov     rax, [rbp+0A0h+arg_10]
0x140030c79  mov     [rsp+1A0h+var_148.Ptr], rax
0x140030c7e  lea     rax, [rbp+0A0h+var_120]
0x140030c82  mov     qword ptr [rsp+1A0h+var_138], rax
0x140030c87  call    FastWppPackEvent
0x140030c8c  cmp     dword ptr [rsp+1A0h+var_138+8], 100h
0x140030c94  jbe     short loc_140030CE2
0x140030c96  mov     edx, dword ptr [rsp+1A0h+var_138+8]
0x140030c9a  lea     ecx, [rbx+40h]
0x140030c9d  xor     r9d, r9d
0x140030ca0  mov     dword ptr [rsp+1A0h+ActivityId], ebx
0x140030ca4  mov     r8d, 46575050h
0x140030caa  call    cs:__imp_ExAllocatePool3
0x140030cb1  nop     dword ptr [rax+rax+00h]
0x140030cb6  mov     rbx, rax
0x140030cb9  test    rax, rax
0x140030cbc  jz      short loc_140030CDA
0x140030cbe  mov     r8d, dword ptr [rsp+1A0h+var_138+8]
0x140030cc3  lea     r9, [rsp+1A0h+var_138+8]
0x140030cc8  mov     rdx, rax
0x140030ccb  mov     qword ptr [rsp+1A0h+var_138], rax
0x140030cd0  mov     rcx, r15
0x140030cd3  call    FastWppPackEvent
0x140030cd8  jmp     short loc_140030CE2
0x140030cda  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140030ce2  mov     rcx, cs:FastWppRegHandle; RegHandle
0x140030ce9  lea     rax, [rsp+1A0h+var_148]
0x140030cee  mov     [rsp+1A0h+UserData], rax; UserData
0x140030cf3  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x140030cf8  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x140030d00  xor     r9d, r9d; Flags
0x140030d03  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x140030d0c  xor     r8d, r8d; Filter
0x140030d0f  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x140030d18  call    cs:__imp_EtwWriteEx
0x140030d1f  nop     dword ptr [rax+rax+00h]
0x140030d24  test    rbx, rbx
0x140030d27  jz      short loc_140030D3D
0x140030d29  mov     edx, 46575050h; Tag
0x140030d2e  mov     rcx, rbx; P
0x140030d31  call    cs:__imp_ExFreePoolWithTag
0x140030d38  nop     dword ptr [rax+rax+00h]
0x140030d3d  mov     rcx, [rbp+0A0h+var_20]
0x140030d44  xor     rcx, rsp; StackCookie
0x140030d47  call    __security_check_cookie
0x140030d4c  add     rsp, 190h
0x140030d53  pop     r15
0x140030d55  pop     rbx
0x140030d56  pop     rbp
0x140030d57  retn
```
