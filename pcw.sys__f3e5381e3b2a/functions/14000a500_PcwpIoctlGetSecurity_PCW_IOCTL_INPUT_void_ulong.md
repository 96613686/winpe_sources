# PcwpIoctlGetSecurity(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a500`
- end: `0x14000a571`
- name: `?PcwpIoctlGetSecurity@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `113`
- prototype: `int(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400099e0`
- `0x140009a08`
- `0x14000a500`
- `0x14000e3e8`

## pseudocode

```c
__int64 __fastcall PcwpIoctlGetSecurity(union PCW_IOCTL_INPUT *a1, void *a2, unsigned int *a3)
{
  __int16 v5; // r8
  unsigned __int16 *v7; // rdx
  int CounterSetSecurityDescriptor; // ebx
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-38h] BYREF

  v5 = *((_WORD *)a1 + 2);
  v7 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v10 = 0;
  CounterSetSecurityDescriptor = AllocatedUnicodeString::Capture((AllocatedUnicodeString *)&v10, v7, v5, UserMode);
  if ( CounterSetSecurityDescriptor >= 0 )
  {
    CounterSetSecurityDescriptor = PcwpGetCounterSetSecurityDescriptor(&v10, *(_DWORD *)a1, a2, a3);
    if ( CounterSetSecurityDescriptor == -1073741789 )
      CounterSetSecurityDescriptor = -2147483643;
  }
  AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v10);
  return (unsigned int)CounterSetSecurityDescriptor;
}

```

## disassembly

```asm
0x14000a500  push    rbx
0x14000a502  push    rbp
0x14000a503  push    rsi
0x14000a504  push    rdi
0x14000a505  sub     rsp, 38h
0x14000a509  mov     rsi, r8
0x14000a50c  mov     rbp, rdx
0x14000a50f  movzx   r8d, word ptr [rcx+4]; unsigned __int16
0x14000a514  mov     rdi, rcx
0x14000a517  mov     rdx, [rcx+8]; unsigned __int16 *
0x14000a51b  xorps   xmm0, xmm0
0x14000a51e  lea     rcx, [rsp+58h+var_38]; this
0x14000a523  mov     r9d, 1; enum _MODE
0x14000a529  movups  xmmword ptr [rsp+58h+var_38.Length], xmm0
0x14000a52e  call    ?Capture@AllocatedUnicodeString@@QEAAJPEBGGW4_MODE@@@Z; AllocatedUnicodeString::Capture(ushort const *,ushort,_MODE)
0x14000a533  lea     rcx, [rsp+58h+var_38]; struct _UNICODE_STRING *
0x14000a538  mov     ebx, eax
0x14000a53a  test    eax, eax
0x14000a53c  js      short loc_14000A560
0x14000a53e  mov     edx, [rdi]; unsigned int
0x14000a540  mov     r9, rsi; unsigned int *
0x14000a543  mov     r8, rbp; void *
0x14000a546  call    ?PcwpGetCounterSetSecurityDescriptor@@YAJPEBU_UNICODE_STRING@@KPEAXPEAK@Z; PcwpGetCounterSetSecurityDescriptor(_UNICODE_STRING const *,ulong,void *,ulong *)
0x14000a54b  mov     ebx, eax
0x14000a54d  lea     rcx, [rsp+58h+var_38]; this
0x14000a552  cmp     ebx, 0C0000023h
0x14000a558  mov     eax, 80000005h
0x14000a55d  cmovz   ebx, eax
0x14000a560  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000a565  mov     eax, ebx
0x14000a567  add     rsp, 38h
0x14000a56b  pop     rdi
0x14000a56c  pop     rsi
0x14000a56d  pop     rbp
0x14000a56e  pop     rbx
0x14000a56f  retn
```
