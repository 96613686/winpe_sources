# PcwpInitDefaultSecurityDescriptor(void)

- ea: `0x14000e4e8`
- end: `0x14000e5a4`
- name: `?PcwpInitDefaultSecurityDescriptor@@YAJXZ`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ddf4`
- `0x14000ed84`

## callees

- `0x14000e088`
- `0x14000e4e8`
- `0x14000e6f8`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e544`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e58a`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e544`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000e58a`

## pseudocode

```c
__int64 PcwpInitDefaultSecurityDescriptor(void)
{
  int v0; // eax
  NTSTATUS DefaultSecurityDescriptor; // ebx
  signed __int64 v3; // rcx
  struct _UNICODE_STRING v4; // [rsp+20h] [rbp-10h] BYREF
  signed __int64 v5; // [rsp+40h] [rbp+10h] BYREF

  *(_QWORD *)&v4.Length = 0x20000;
  v4.Buffer = (wchar_t *)&qword_140003570;
  v5 = 0;
  if ( PcwDefaultSecurityDescriptor )
    goto LABEL_10;
  v0 = PcwpReadSecurityDescriptor((__int64)&v5, &v4);
  DefaultSecurityDescriptor = v0;
  if ( v0 < 0 )
  {
    if ( v0 != -1073741772
      || (DefaultSecurityDescriptor = PcwpCreateDefaultSecurityDescriptor((__int64)&v5), DefaultSecurityDescriptor < 0) )
    {
      if ( v5 )
        ObDereferenceSecurityDescriptor(v5, 1);
      return (unsigned int)DefaultSecurityDescriptor;
    }
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&PcwDefaultSecurityDescriptor, v5, 0) )
  {
LABEL_10:
    v3 = v5;
  }
  else
  {
    v3 = 0;
    v5 = 0;
  }
  if ( v3 )
    ObDereferenceSecurityDescriptor(v3, 1);
  return 0;
}

```

## disassembly

```asm
0x14000e4e8  mov     [rsp-8+arg_8], rbx
0x14000e4ed  push    rbp
0x14000e4ee  mov     rbp, rsp
0x14000e4f1  sub     rsp, 30h
0x14000e4f5  lea     rax, qword_140003570
0x14000e4fc  mov     [rbp+var_10], 20000h
0x14000e504  mov     [rbp+var_8], rax
0x14000e508  mov     rax, cs:?PcwDefaultSecurityDescriptor@@3PEAXEA; void * PcwDefaultSecurityDescriptor
0x14000e50f  mov     [rbp+arg_0], 0
0x14000e517  test    rax, rax
0x14000e51a  jnz     short loc_14000E57C
0x14000e51c  lea     rdx, [rbp+var_10]
0x14000e520  lea     rcx, [rbp+arg_0]
0x14000e524  call    ?PcwpReadSecurityDescriptor@@YAJPEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@utl@@PEBU_UNICODE_STRING@@@Z; PcwpReadSecurityDescriptor(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> *,_UNICODE_STRING const *)
0x14000e529  mov     ebx, eax
0x14000e52b  test    eax, eax
0x14000e52d  jns     short loc_14000E563
0x14000e52f  cmp     eax, 0C0000034h
0x14000e534  jz      short loc_14000E554
0x14000e536  mov     rcx, [rbp+arg_0]
0x14000e53a  test    rcx, rcx
0x14000e53d  jz      short loc_14000E550
0x14000e53f  mov     edx, 1
0x14000e544  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000e54b  nop     dword ptr [rax+rax+00h]
0x14000e550  mov     eax, ebx
0x14000e552  jmp     short loc_14000E598
0x14000e554  lea     rcx, [rbp+arg_0]
0x14000e558  call    ?PcwpCreateDefaultSecurityDescriptor@@YAJPEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@utl@@@Z; PcwpCreateDefaultSecurityDescriptor(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> *)
0x14000e55d  mov     ebx, eax
0x14000e55f  test    eax, eax
0x14000e561  js      short loc_14000E536
0x14000e563  mov     rcx, [rbp+arg_0]
0x14000e567  xor     eax, eax
0x14000e569  lock cmpxchg cs:?PcwDefaultSecurityDescriptor@@3PEAXEA, rcx; void * PcwDefaultSecurityDescriptor
0x14000e572  jnz     short loc_14000E57C
0x14000e574  xor     ecx, ecx
0x14000e576  mov     [rbp+arg_0], rcx
0x14000e57a  jmp     short loc_14000E580
0x14000e57c  mov     rcx, [rbp+arg_0]
0x14000e580  test    rcx, rcx
0x14000e583  jz      short loc_14000E596
0x14000e585  mov     edx, 1
0x14000e58a  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000e591  nop     dword ptr [rax+rax+00h]
0x14000e596  xor     eax, eax
0x14000e598  mov     rbx, [rsp+30h+arg_8]
0x14000e59d  add     rsp, 30h
0x14000e5a1  pop     rbp
0x14000e5a2  retn
```
