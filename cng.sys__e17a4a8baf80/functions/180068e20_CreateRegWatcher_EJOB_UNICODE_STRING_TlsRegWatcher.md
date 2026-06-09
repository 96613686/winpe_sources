# CreateRegWatcher(_EJOB *,_UNICODE_STRING,TlsRegWatcher * *)

- ea: `0x180068e20`
- end: `0x180068f17`
- name: `?CreateRegWatcher@@YAJPEAU_EJOB@@U_UNICODE_STRING@@PEAPEAUTlsRegWatcher@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _EJOB *, struct _UNICODE_STRING *__struct_ptr, struct TlsRegWatcher **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800692b8`

## callees

- `0x180068e20`
- `0x180068f20`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180068ee3`
- `ntoskrnl!ZwCreateKey` at `0x180068ee3`
- `ntoskrnl!ExAllocatePool2` at `0x180068e7b`
- `ntoskrnl!ExAllocatePool2` at `0x180068e7b`

## pseudocode

```c
__int64 __fastcall CreateRegWatcher(struct _EJOB *a1, struct _UNICODE_STRING *a2, struct TlsRegWatcher **a3)
{
  __int64 Pool2; // rax
  void *v7; // rbx
  NTSTATUS v8; // edi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  if ( !a3 )
    return 3221225485LL;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Pool2 = ExAllocatePool2(64, 72, 1399287363);
  v7 = (void *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 64) = a1;
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 32) = TlsRegNotifyCallback;
    *(_QWORD *)(Pool2 + 40) = Pool2;
    *(_QWORD *)(Pool2 + 16) = 0;
    v8 = ZwCreateKey((PHANDLE)Pool2, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
    if ( v8 < 0 )
    {
      DeleteRegWatcher(v7);
      v7 = 0;
    }
  }
  else
  {
    v8 = -1073741801;
  }
  *a3 = (struct TlsRegWatcher *)v7;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180068e20  mov     [rsp+arg_0], rbx
0x180068e25  mov     [rsp+arg_8], rsi
0x180068e2a  push    rdi
0x180068e2b  sub     rsp, 70h
0x180068e2f  mov     rsi, r8
0x180068e32  mov     rdi, rcx
0x180068e35  test    r8, r8
0x180068e38  jnz     short loc_180068E44
0x180068e3a  mov     eax, 0C000000Dh
0x180068e3f  jmp     loc_180068F04
0x180068e44  mov     [rsp+78h+ObjectAttributes.ObjectName], rdx
0x180068e49  xorps   xmm0, xmm0
0x180068e4c  mov     edx, 48h ; 'H'
0x180068e51  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x180068e5a  mov     r8d, 53676E43h
0x180068e60  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 240h
0x180068e69  mov     [rsp+78h+ObjectAttributes.RootDirectory], 0
0x180068e72  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x180068e78  lea     ecx, [rdx-8]
0x180068e7b  call    cs:__imp_ExAllocatePool2
0x180068e82  nop     dword ptr [rax+rax+00h]
0x180068e87  mov     rbx, rax
0x180068e8a  test    rax, rax
0x180068e8d  jnz     short loc_180068E96
0x180068e8f  mov     edi, 0C0000017h
0x180068e94  jmp     short loc_180068EFF
0x180068e96  mov     [rax+40h], rdi
0x180068e9a  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x180068e9f  mov     qword ptr [rax+8], 0
0x180068ea7  xor     r9d, r9d; TitleIndex
0x180068eaa  lea     rax, ?TlsRegNotifyCallback@@YAXPEAX@Z; TlsRegNotifyCallback(void *)
0x180068eb1  mov     [rsp+78h+Disposition], 0; Disposition
0x180068eba  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x180068ec2  mov     edx, 20019h; DesiredAccess
0x180068ec7  mov     rcx, rbx; KeyHandle
0x180068eca  mov     [rbx+20h], rax
0x180068ece  mov     [rbx+28h], rbx
0x180068ed2  mov     qword ptr [rbx+10h], 0
0x180068eda  mov     [rsp+78h+Class], 0; Class
0x180068ee3  call    cs:__imp_ZwCreateKey
0x180068eea  nop     dword ptr [rax+rax+00h]
0x180068eef  mov     edi, eax
0x180068ef1  test    eax, eax
0x180068ef3  jns     short loc_180068EFF
0x180068ef5  mov     rcx, rbx; P
0x180068ef8  call    ?DeleteRegWatcher@@YAXPEAUTlsRegWatcher@@@Z; DeleteRegWatcher(TlsRegWatcher *)
0x180068efd  xor     ebx, ebx
0x180068eff  mov     [rsi], rbx
0x180068f02  mov     eax, edi
0x180068f04  lea     r11, [rsp+78h+var_8]
0x180068f09  mov     rbx, [r11+10h]
0x180068f0d  mov     rsi, [r11+18h]
0x180068f11  mov     rsp, r11
0x180068f14  pop     rdi
0x180068f15  retn
```
