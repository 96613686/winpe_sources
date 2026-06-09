# PcwpIoctlSetSecurity(PCW_IOCTL_INPUT *,void *,ulong *)

- ea: `0x14000a9b0`
- end: `0x14000aa6c`
- name: `?PcwpIoctlSetSecurity@@YAJPEATPCW_IOCTL_INPUT@@PEAXPEAK@Z`
- size: `188`
- prototype: `__int64 __fastcall(union PCW_IOCTL_INPUT *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400099e0`
- `0x140009a08`
- `0x14000a9b0`
- `0x14000ddf4`
- `0x14000e8c0`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000aa19`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000aa19`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x14000aa48`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x14000aa48`

## pseudocode

```c
__int64 __fastcall PcwpIoctlSetSecurity(union PCW_IOCTL_INPUT *a1, void *a2, unsigned int *a3)
{
  unsigned __int16 v3; // r8
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // r9
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-18h] BYREF
  void *v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_WORD *)a1;
  v5 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
  v14 = 0;
  v13 = 0;
  v7 = AllocatedUnicodeString::Capture((AllocatedUnicodeString *)&v13, v5, v3, UserMode);
  if ( v7 >= 0 )
  {
    if ( *((_BYTE *)a1 + 2) )
    {
      v9 = PcwpClearCounterSetSecurityDescriptor(&v13);
    }
    else
    {
      LOBYTE(v6) = 1;
      LOBYTE(v8) = 1;
      v9 = SeCaptureSecurityDescriptor(*((_QWORD *)a1 + 1), v6, 1, v8, &v14);
      if ( v9 >= 0 )
      {
        v10 = PcwpSetCounterSetSecurityDescriptor(&v13, *((_DWORD *)a1 + 1), v14);
        LOBYTE(v11) = 1;
        v7 = v10;
        SeReleaseSecurityDescriptor(v14, v11);
        goto LABEL_7;
      }
    }
    v7 = v9;
  }
LABEL_7:
  AllocatedUnicodeString::~AllocatedUnicodeString((AllocatedUnicodeString *)&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a9b0  mov     rax, rsp
0x14000a9b3  mov     [rax+10h], rbx
0x14000a9b7  push    rdi
0x14000a9b8  sub     rsp, 40h
0x14000a9bc  movzx   r8d, word ptr [rcx]; unsigned __int16
0x14000a9c0  mov     rdi, rcx
0x14000a9c3  mov     rdx, [rcx+10h]; unsigned __int16 *
0x14000a9c7  xorps   xmm0, xmm0
0x14000a9ca  lea     rcx, [rax-18h]; this
0x14000a9ce  mov     qword ptr [rax+8], 0
0x14000a9d6  mov     r9d, 1; enum _MODE
0x14000a9dc  movups  xmmword ptr [rax-18h], xmm0
0x14000a9e0  call    ?Capture@AllocatedUnicodeString@@QEAAJPEBGGW4_MODE@@@Z; AllocatedUnicodeString::Capture(ushort const *,ushort,_MODE)
0x14000a9e5  mov     ebx, eax
0x14000a9e7  test    eax, eax
0x14000a9e9  js      short loc_14000AA54
0x14000a9eb  cmp     byte ptr [rdi+2], 0
0x14000a9ef  jz      short loc_14000A9FF
0x14000a9f1  lea     rcx, [rsp+48h+var_18]; struct _UNICODE_STRING *
0x14000a9f6  call    ?PcwpClearCounterSetSecurityDescriptor@@YAJPEBU_UNICODE_STRING@@@Z; PcwpClearCounterSetSecurityDescriptor(_UNICODE_STRING const *)
0x14000a9fb  mov     ebx, eax
0x14000a9fd  jmp     short loc_14000AA54
0x14000a9ff  mov     rcx, [rdi+8]
0x14000aa03  lea     rax, [rsp+48h+arg_0]
0x14000aa08  mov     r8d, 1
0x14000aa0e  mov     [rsp+48h+var_28], rax
0x14000aa13  mov     dl, r8b
0x14000aa16  mov     r9b, 1
0x14000aa19  call    cs:__imp_SeCaptureSecurityDescriptor
0x14000aa20  nop     dword ptr [rax+rax+00h]
0x14000aa25  test    eax, eax
0x14000aa27  js      short loc_14000A9FB
0x14000aa29  mov     r8, [rsp+48h+arg_0]; void *
0x14000aa2e  lea     rcx, [rsp+48h+var_18]; struct _UNICODE_STRING *
0x14000aa33  mov     edx, [rdi+4]; unsigned int
0x14000aa36  call    ?PcwpSetCounterSetSecurityDescriptor@@YAJPEBU_UNICODE_STRING@@KPEAX@Z; PcwpSetCounterSetSecurityDescriptor(_UNICODE_STRING const *,ulong,void *)
0x14000aa3b  mov     rcx, [rsp+48h+arg_0]
0x14000aa40  mov     r8b, 1
0x14000aa43  mov     dl, r8b
0x14000aa46  mov     ebx, eax
0x14000aa48  call    cs:__imp_SeReleaseSecurityDescriptor
0x14000aa4f  nop     dword ptr [rax+rax+00h]
0x14000aa54  lea     rcx, [rsp+48h+var_18]; this
0x14000aa59  call    ??1AllocatedUnicodeString@@QEAA@XZ; AllocatedUnicodeString::~AllocatedUnicodeString(void)
0x14000aa5e  mov     eax, ebx
0x14000aa60  mov     rbx, [rsp+48h+arg_8]
0x14000aa65  add     rsp, 40h
0x14000aa69  pop     rdi
0x14000aa6a  retn
```
