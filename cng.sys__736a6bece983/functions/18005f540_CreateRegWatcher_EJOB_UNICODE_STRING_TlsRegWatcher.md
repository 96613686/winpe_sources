# CreateRegWatcher(_EJOB *,_UNICODE_STRING,TlsRegWatcher * *)

- ea: `0x18005f540`
- end: `0x18005f637`
- name: `?CreateRegWatcher@@YAJPEAU_EJOB@@U_UNICODE_STRING@@PEAPEAUTlsRegWatcher@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _EJOB *, struct _UNICODE_STRING *__struct_ptr, struct TlsRegWatcher **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005f9d8`

## callees

- `0x18005f540`
- `0x18005f640`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005f603`
- `ntoskrnl!ZwCreateKey` at `0x18005f603`
- `ntoskrnl!ExAllocatePool2` at `0x18005f59b`
- `ntoskrnl!ExAllocatePool2` at `0x18005f59b`

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
0x18005f540  mov     [rsp+arg_0], rbx
0x18005f545  mov     [rsp+arg_8], rsi
0x18005f54a  push    rdi
0x18005f54b  sub     rsp, 70h
0x18005f54f  mov     rsi, r8
0x18005f552  mov     rdi, rcx
0x18005f555  test    r8, r8
0x18005f558  jnz     short loc_18005F564
0x18005f55a  mov     eax, 0C000000Dh
0x18005f55f  jmp     loc_18005F624
0x18005f564  mov     [rsp+78h+ObjectAttributes.ObjectName], rdx
0x18005f569  xorps   xmm0, xmm0
0x18005f56c  mov     edx, 48h ; 'H'
0x18005f571  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x18005f57a  mov     r8d, 53676E43h
0x18005f580  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 240h
0x18005f589  mov     [rsp+78h+ObjectAttributes.RootDirectory], 0
0x18005f592  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f598  lea     ecx, [rdx-8]
0x18005f59b  call    cs:__imp_ExAllocatePool2
0x18005f5a2  nop     dword ptr [rax+rax+00h]
0x18005f5a7  mov     rbx, rax
0x18005f5aa  test    rax, rax
0x18005f5ad  jnz     short loc_18005F5B6
0x18005f5af  mov     edi, 0C0000017h
0x18005f5b4  jmp     short loc_18005F61F
0x18005f5b6  mov     [rax+40h], rdi
0x18005f5ba  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x18005f5bf  mov     qword ptr [rax+8], 0
0x18005f5c7  xor     r9d, r9d; TitleIndex
0x18005f5ca  lea     rax, ?TlsRegNotifyCallback@@YAXPEAX@Z; TlsRegNotifyCallback(void *)
0x18005f5d1  mov     [rsp+78h+Disposition], 0; Disposition
0x18005f5da  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x18005f5e2  mov     edx, 20019h; DesiredAccess
0x18005f5e7  mov     rcx, rbx; KeyHandle
0x18005f5ea  mov     [rbx+20h], rax
0x18005f5ee  mov     [rbx+28h], rbx
0x18005f5f2  mov     qword ptr [rbx+10h], 0
0x18005f5fa  mov     [rsp+78h+Class], 0; Class
0x18005f603  call    cs:__imp_ZwCreateKey
0x18005f60a  nop     dword ptr [rax+rax+00h]
0x18005f60f  mov     edi, eax
0x18005f611  test    eax, eax
0x18005f613  jns     short loc_18005F61F
0x18005f615  mov     rcx, rbx; P
0x18005f618  call    ?DeleteRegWatcher@@YAXPEAUTlsRegWatcher@@@Z; DeleteRegWatcher(TlsRegWatcher *)
0x18005f61d  xor     ebx, ebx
0x18005f61f  mov     [rsi], rbx
0x18005f622  mov     eax, edi
0x18005f624  lea     r11, [rsp+78h+var_8]
0x18005f629  mov     rbx, [r11+10h]
0x18005f62d  mov     rsi, [r11+18h]
0x18005f631  mov     rsp, r11
0x18005f634  pop     rdi
0x18005f635  retn
```
