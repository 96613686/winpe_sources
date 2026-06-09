# MRxSmb2UpdateConnectionInfo

- ea: `0x140057df0`
- end: `0x140057f20`
- name: `MRxSmb2UpdateConnectionInfo`
- size: `304`
- prototype: `void __fastcall(_QWORD *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140028500`
- `0x140057df0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140057eea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057eea`
- `ntoskrnl!ExAllocatePool2` at `0x140057e6c`
- `ntoskrnl!ExAllocatePool2` at `0x140057e6c`
- `rdbss!RxCreateRxContext` at `0x140057e1c`
- `rdbss!RxCreateRxContext` at `0x140057e1c`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140057ed1`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140057ed1`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x140057e38`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x140057ec2`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x140057e38`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x140057ec2`

## pseudocode

```c
void __fastcall MRxSmb2UpdateConnectionInfo(_QWORD *Context)
{
  PRX_CONTEXT RxContext; // rsi
  __int64 Pool2; // rax
  void *v4; // rbp

  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(Context[52] + 384LL) + 24LL), 0x80000002);
  if ( RxContext )
  {
    Pool2 = ExAllocatePool2(66, 0x10000, 1665366098);
    v4 = (void *)Pool2;
    if ( !Pool2
      || (LOBYTE(RxContext->RealDevice) = 13,
          *((_DWORD *)&RxContext->9 + 35) = 1311228,
          *((_DWORD *)&RxContext->9 + 43) = 0x10000,
          RxContext->Create.TransportName.Buffer = (PWSTR)Pool2,
          (unsigned int)Smb2GenericFsControl((__int64)RxContext, 1311228, (__int64)Context) != 259) )
    {
      SmbCeDereferenceVNetRootContext(Context);
      RxDereferenceAndDeleteRxContext_Real(RxContext);
      if ( v4 )
        ExFreePoolWithTag(v4, 0x63437852u);
    }
  }
  else
  {
    SmbCeDereferenceVNetRootContext(Context);
  }
}

```

## disassembly

```asm
0x140057df0  mov     [rsp+arg_8], rbx
0x140057df5  mov     [rsp+arg_10], rsi
0x140057dfa  push    rdi
0x140057dfb  sub     rsp, 20h
0x140057dff  mov     rax, [rcx+1A0h]
0x140057e06  mov     rdi, rcx
0x140057e09  mov     r8d, 80000002h; InitialContextFlags
0x140057e0f  xor     ecx, ecx; Irp
0x140057e11  mov     rdx, [rax+180h]
0x140057e18  mov     rdx, [rdx+18h]; RxDeviceObject
0x140057e1c  call    cs:__imp_RxCreateRxContext
0x140057e23  nop     dword ptr [rax+rax+00h]
0x140057e28  mov     rsi, rax
0x140057e2b  test    rax, rax
0x140057e2e  jnz     short loc_140057E57
0x140057e30  mov     rcx, rdi
0x140057e33  mov     ebx, 0C000009Ah
0x140057e38  call    cs:__imp_SmbCeDereferenceVNetRootContext
0x140057e3f  nop     dword ptr [rax+rax+00h]
0x140057e44  mov     eax, ebx
0x140057e46  mov     rbx, [rsp+28h+arg_8]
0x140057e4b  mov     rsi, [rsp+28h+arg_10]
0x140057e50  add     rsp, 20h
0x140057e54  pop     rdi
0x140057e55  retn
0x140057e57  mov     edx, 10000h
0x140057e5c  mov     [rsp+28h+arg_0], rbp
0x140057e61  mov     ecx, 42h ; 'B'
0x140057e66  mov     r8d, 63437852h
0x140057e6c  call    cs:__imp_ExAllocatePool2
0x140057e73  nop     dword ptr [rax+rax+00h]
0x140057e78  mov     rbp, rax
0x140057e7b  test    rax, rax
0x140057e7e  jnz     short loc_140057E87
0x140057e80  mov     ebx, 0C000009Ah
0x140057e85  jmp     short loc_140057EBF
0x140057e87  mov     r8, rdi
0x140057e8a  mov     byte ptr [rsi+20h], 0Dh
0x140057e8e  mov     edx, 1401FCh
0x140057e93  mov     dword ptr [rsi+21Ch], 1401FCh
0x140057e9d  mov     rcx, rsi
0x140057ea0  mov     dword ptr [rsi+23Ch], 10000h
0x140057eaa  mov     [rsi+230h], rbp
0x140057eb1  call    Smb2GenericFsControl
0x140057eb6  mov     ebx, eax
0x140057eb8  cmp     eax, 103h
0x140057ebd  jz      short loc_140057EF8
0x140057ebf  mov     rcx, rdi
0x140057ec2  call    cs:__imp_SmbCeDereferenceVNetRootContext
0x140057ec9  nop     dword ptr [rax+rax+00h]
0x140057ece  mov     rcx, rsi; RxContext
0x140057ed1  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140057ed8  nop     dword ptr [rax+rax+00h]
0x140057edd  test    rbp, rbp
0x140057ee0  jz      short loc_140057EF6
0x140057ee2  mov     edx, 63437852h; Tag
0x140057ee7  mov     rcx, rbp; P
0x140057eea  call    cs:__imp_ExFreePoolWithTag
0x140057ef1  nop     dword ptr [rax+rax+00h]
0x140057ef6  mov     eax, ebx
0x140057ef8  mov     rbp, [rsp+28h+arg_0]
0x140057efd  mov     rbx, [rsp+28h+arg_8]
0x140057f02  mov     rsi, [rsp+28h+arg_10]
0x140057f07  add     rsp, 20h
0x140057f0b  pop     rdi
0x140057f0c  retn
```
