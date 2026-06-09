# CreateRegWatcher(_EJOB *,_UNICODE_STRING,TlsRegWatcher * *)

- ea: `0x18005ec50`
- end: `0x18005ed47`
- name: `?CreateRegWatcher@@YAJPEAU_EJOB@@U_UNICODE_STRING@@PEAPEAUTlsRegWatcher@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _EJOB *, struct _UNICODE_STRING *__struct_ptr, struct TlsRegWatcher **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005f0e8`

## callees

- `0x18005ec50`
- `0x18005ed50`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005ed13`
- `ntoskrnl!ZwCreateKey` at `0x18005ed13`
- `ntoskrnl!ExAllocatePool2` at `0x18005ecab`
- `ntoskrnl!ExAllocatePool2` at `0x18005ecab`

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
0x18005ec50  mov     [rsp+arg_0], rbx
0x18005ec55  mov     [rsp+arg_8], rsi
0x18005ec5a  push    rdi
0x18005ec5b  sub     rsp, 70h
0x18005ec5f  mov     rsi, r8
0x18005ec62  mov     rdi, rcx
0x18005ec65  test    r8, r8
0x18005ec68  jnz     short loc_18005EC74
0x18005ec6a  mov     eax, 0C000000Dh
0x18005ec6f  jmp     loc_18005ED34
0x18005ec74  mov     [rsp+78h+ObjectAttributes.ObjectName], rdx
0x18005ec79  xorps   xmm0, xmm0
0x18005ec7c  mov     edx, 48h ; 'H'
0x18005ec81  mov     qword ptr [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x18005ec8a  mov     r8d, 53676E43h
0x18005ec90  mov     qword ptr [rsp+78h+ObjectAttributes.Attributes], 240h
0x18005ec99  mov     [rsp+78h+ObjectAttributes.RootDirectory], 0
0x18005eca2  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005eca8  lea     ecx, [rdx-8]
0x18005ecab  call    cs:__imp_ExAllocatePool2
0x18005ecb2  nop     dword ptr [rax+rax+00h]
0x18005ecb7  mov     rbx, rax
0x18005ecba  test    rax, rax
0x18005ecbd  jnz     short loc_18005ECC6
0x18005ecbf  mov     edi, 0C0000017h
0x18005ecc4  jmp     short loc_18005ED2F
0x18005ecc6  mov     [rax+40h], rdi
0x18005ecca  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x18005eccf  mov     qword ptr [rax+8], 0
0x18005ecd7  xor     r9d, r9d; TitleIndex
0x18005ecda  lea     rax, ?TlsRegNotifyCallback@@YAXPEAX@Z; TlsRegNotifyCallback(void *)
0x18005ece1  mov     [rsp+78h+Disposition], 0; Disposition
0x18005ecea  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x18005ecf2  mov     edx, 20019h; DesiredAccess
0x18005ecf7  mov     rcx, rbx; KeyHandle
0x18005ecfa  mov     [rbx+20h], rax
0x18005ecfe  mov     [rbx+28h], rbx
0x18005ed02  mov     qword ptr [rbx+10h], 0
0x18005ed0a  mov     [rsp+78h+Class], 0; Class
0x18005ed13  call    cs:__imp_ZwCreateKey
0x18005ed1a  nop     dword ptr [rax+rax+00h]
0x18005ed1f  mov     edi, eax
0x18005ed21  test    eax, eax
0x18005ed23  jns     short loc_18005ED2F
0x18005ed25  mov     rcx, rbx; P
0x18005ed28  call    ?DeleteRegWatcher@@YAXPEAUTlsRegWatcher@@@Z; DeleteRegWatcher(TlsRegWatcher *)
0x18005ed2d  xor     ebx, ebx
0x18005ed2f  mov     [rsi], rbx
0x18005ed32  mov     eax, edi
0x18005ed34  lea     r11, [rsp+78h+var_8]
0x18005ed39  mov     rbx, [r11+10h]
0x18005ed3d  mov     rsi, [r11+18h]
0x18005ed41  mov     rsp, r11
0x18005ed44  pop     rdi
0x18005ed45  retn
```
