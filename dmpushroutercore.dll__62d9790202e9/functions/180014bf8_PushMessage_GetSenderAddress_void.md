# PushMessage::GetSenderAddress(void)

- ea: `0x180014bf8`
- end: `0x180014c80`
- name: `?GetSenderAddress@PushMessage@@QEAAPEBGXZ`
- size: `136`
- prototype: `unsigned __int16 *__fastcall(PushMessage *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016110`
- `0x18001b0f8`

## callees

- `0x180014bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c1a`
- `DMCmnUtils!CopyString` at `0x180014c57`
- `DMCmnUtils!CopyString` at `0x180014c57`

## pseudocode

```c
unsigned __int16 *__fastcall PushMessage::GetSenderAddress(PushMessage *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx
  __int64 v4; // rcx
  unsigned __int16 *v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_DWORD *)this + 4) > 4u && (v4 = *(_QWORD *)(*((_QWORD *)this + 1) + 32LL)) != 0 )
  {
    if ( *(_DWORD *)v4 == 1 )
      v3 = CopyString(*(const unsigned __int16 **)(v4 + 16), 0xFFFFFFFF, &v6);
    else
      v3 = -2147024883;
  }
  else
  {
    v3 = -2147023728;
  }
  LeaveCriticalSection(v2);
  if ( v3 >= 0 )
    return v6;
  else
    return 0;
}

```

## disassembly

```asm
0x180014bf8  mov     [rsp+arg_8], rbx
0x180014bfd  push    rdi
0x180014bfe  sub     rsp, 30h
0x180014c02  mov     rbx, rcx
0x180014c05  mov     [rsp+38h+arg_0], 0
0x180014c0e  lea     rdi, [rcx+20h]
0x180014c12  mov     [rsp+38h+var_18], rdi
0x180014c17  mov     rcx, rdi; lpCriticalSection
0x180014c1a  call    cs:__imp_EnterCriticalSection
0x180014c20  mov     [rsp+38h+var_10], 1
0x180014c25  cmp     dword ptr [rbx+10h], 4
0x180014c29  ja      short loc_180014C32
0x180014c2b  mov     ebx, 80070490h
0x180014c30  jmp     short loc_180014C5F
0x180014c32  mov     rax, [rbx+8]
0x180014c36  mov     rcx, [rax+20h]
0x180014c3a  test    rcx, rcx
0x180014c3d  jz      short loc_180014C2B
0x180014c3f  cmp     dword ptr [rcx], 1
0x180014c42  jz      short loc_180014C4B
0x180014c44  mov     ebx, 8007000Dh
0x180014c49  jmp     short loc_180014C5F
0x180014c4b  lea     r8, [rsp+38h+arg_0]
0x180014c50  or      edx, 0FFFFFFFFh
0x180014c53  mov     rcx, [rcx+10h]
0x180014c57  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180014c5d  mov     ebx, eax
0x180014c5f  mov     rcx, rdi; lpCriticalSection
0x180014c62  call    cs:__imp_LeaveCriticalSection
0x180014c68  test    ebx, ebx
0x180014c6a  jns     short loc_180014C70
0x180014c6c  xor     eax, eax
0x180014c6e  jmp     short loc_180014C75
0x180014c70  mov     rax, [rsp+38h+arg_0]
0x180014c75  mov     rbx, [rsp+38h+arg_8]
0x180014c7a  add     rsp, 30h
0x180014c7e  pop     rdi
0x180014c7f  retn
```
