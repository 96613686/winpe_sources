# PcwpIoctlCreateNotifier(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a1e0`
- end: `0x14000a274`
- name: `?PcwpIoctlCreateNotifier@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `148`
- prototype: `__int64 __fastcall(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400080b4`
- `0x1400099e0`
- `0x140009a08`
- `0x14000a1e0`
- `0x14000bbb0`

## pseudocode

```c
__int64 __fastcall PcwpIoctlCreateNotifier(unsigned __int16 **a1, _QWORD *a2, unsigned int *a3)
{
  int v4; // ebx
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-18h] BYREF
  void *Handle; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  Handle = 0;
  v4 = AllocatedUnicodeString::Capture((AllocatedUnicodeString *)&v6, a1[1], *(_WORD *)a1, UserMode);
  if ( v4 < 0 || (v4 = PCW_NOTIFIER::Create(&Handle, &v6), v4 < 0) )
  {
    AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v6);
    return (unsigned int)v4;
  }
  else
  {
    RtlWriteULong64ToUser(a2, (__int64)Handle);
    AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v6);
    return 0;
  }
}

```

## disassembly

```asm
0x14000a1e0  mov     rax, rsp
0x14000a1e3  mov     [rax+10h], rbx
0x14000a1e7  push    rdi
0x14000a1e8  sub     rsp, 30h
0x14000a1ec  mov     rdi, rdx
0x14000a1ef  xorps   xmm0, xmm0
0x14000a1f2  movups  xmmword ptr [rax-18h], xmm0
0x14000a1f6  mov     qword ptr [rax+8], 0
0x14000a1fe  mov     r9d, 1; enum _MODE
0x14000a204  movzx   r8d, word ptr [rcx]; unsigned __int16
0x14000a208  mov     rdx, [rcx+8]; unsigned __int16 *
0x14000a20c  lea     rcx, [rax-18h]; this
0x14000a210  call    ?Capture@AllocatedUnicodeString@@QEAAJPEBGGW4_MODE@@@Z; AllocatedUnicodeString::Capture(ushort const *,ushort,_MODE)
0x14000a215  mov     ebx, eax
0x14000a217  test    eax, eax
0x14000a219  jns     short loc_14000A229
0x14000a21b  lea     rcx, [rsp+38h+var_18]; this
0x14000a220  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000a225  mov     eax, ebx
0x14000a227  jmp     short loc_14000A268
0x14000a229  lea     rdx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x14000a22e  lea     rcx, [rsp+38h+Handle]; Handle
0x14000a233  call    ?Create@PCW_NOTIFIER@@SAJPEAPEAXPEBU_UNICODE_STRING@@@Z; PCW_NOTIFIER::Create(void * *,_UNICODE_STRING const *)
0x14000a238  mov     ebx, eax
0x14000a23a  test    eax, eax
0x14000a23c  js      short loc_14000A21B
0x14000a23e  mov     rdx, [rsp+38h+Handle]
0x14000a243  mov     rcx, rdi
0x14000a246  call    RtlWriteULong64ToUser
0x14000a24b  nop
0x14000a24c  lea     rcx, [rsp+38h+var_18]; this
0x14000a251  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000a256  xor     eax, eax
0x14000a258  jmp     short loc_14000A268
0x14000a25a  mov     ebx, eax
0x14000a25c  lea     rcx, [rsp+38h+var_18]; this
0x14000a261  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000a266  mov     eax, ebx
0x14000a268  mov     rbx, [rsp+38h+arg_8]
0x14000a26d  add     rsp, 30h
0x14000a271  pop     rdi
0x14000a272  retn
```
