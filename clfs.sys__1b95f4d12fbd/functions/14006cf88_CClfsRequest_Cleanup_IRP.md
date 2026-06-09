# CClfsRequest::Cleanup(_IRP *)

- ea: `0x14006cf88`
- end: `0x14006d041`
- name: `?Cleanup@CClfsRequest@@SAJPEAU_IRP@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14006c520`

## callees

- `0x14000c2f0`
- `0x140044aa8`
- `0x140059e80`
- `0x14006cf88`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14006cff2`
- `ntoskrnl!KeBugCheckEx` at `0x14006cff2`
- `ntoskrnl!IofCompleteRequest` at `0x14006d027`
- `ntoskrnl!IofCompleteRequest` at `0x14007b848`
- `ntoskrnl!IofCompleteRequest` at `0x14006d027`
- `ntoskrnl!IofCompleteRequest` at `0x14007b848`

## pseudocode

```c
__int64 __fastcall CClfsRequest::Cleanup(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  CClfsLogCcb *FsContext2; // rdi
  ULONG_PTR v4; // rcx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MajorFunction != 18 )
    KeBugCheckEx(0xC1F5u, 0x47u, CurrentStackLocation->MajorFunction, 0, 0);
  FsContext2 = (CClfsLogCcb *)CurrentStackLocation->FileObject->FsContext2;
  if ( FsContext2 )
  {
    CClfsLogCcb::AddRef(FsContext2);
    CClfsLogCcb::Cleanup(v4);
    CClfsLogCcb::Release(FsContext2);
  }
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14006cf88  mov     rax, rsp
0x14006cf8b  mov     [rax+10h], rbx
0x14006cf8f  mov     [rax+8], rcx
0x14006cf93  push    rdi
0x14006cf94  sub     rsp, 40h
0x14006cf98  mov     rbx, rcx
0x14006cf9b  mov     qword ptr [rax-10h], 0
0x14006cfa3  mov     dword ptr [rax-18h], 0
0x14006cfaa  mov     rax, [rcx+0B8h]
0x14006cfb1  movzx   ecx, byte ptr [rax]
0x14006cfb4  cmp     cl, 12h
0x14006cfb7  jnz     short loc_14006CFDA
0x14006cfb9  mov     rax, [rax+30h]
0x14006cfbd  mov     rdi, [rax+20h]
0x14006cfc1  mov     [rsp+48h+var_10], rdi
0x14006cfc6  test    rdi, rdi
0x14006cfc9  jz      short loc_14006CFFE
0x14006cfcb  mov     rcx, rdi; this
0x14006cfce  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14006cfd3  call    ?Cleanup@CClfsLogCcb@@QEAAXXZ; CClfsLogCcb::Cleanup(void)
0x14006cfd8  jmp     short loc_14006CFFE
0x14006cfda  mov     r8, rcx; BugCheckParameter2
0x14006cfdd  mov     [rsp+48h+BugCheckParameter4], 0; BugCheckParameter4
0x14006cfe6  xor     r9d, r9d; BugCheckParameter3
0x14006cfe9  lea     edx, [r9+47h]; BugCheckParameter1
0x14006cfed  mov     ecx, 0C1F5h; BugCheckCode
0x14006cff2  call    cs:__imp_KeBugCheckEx
0x14006cffe  mov     [rsp+48h+var_18], 0
0x14006d006  test    rdi, rdi
0x14006d009  jz      short loc_14006D013
0x14006d00b  mov     rcx, rdi; Entry
0x14006d00e  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14006d013  mov     dword ptr [rbx+30h], 0
0x14006d01a  mov     qword ptr [rbx+38h], 0
0x14006d022  xor     edx, edx; PriorityBoost
0x14006d024  mov     rcx, rbx; Irp
0x14006d027  call    cs:__imp_IofCompleteRequest
0x14006d02e  nop     dword ptr [rax+rax+00h]
0x14006d033  xor     eax, eax
0x14006d035  mov     rbx, [rsp+48h+arg_8]
0x14006d03a  add     rsp, 40h
0x14006d03e  pop     rdi
0x14006d03f  retn
0x14007b81c  push    rbp
0x14007b81e  sub     rsp, 30h
0x14007b822  mov     rbp, rdx
0x14007b825  mov     rcx, [rbp+38h]; Entry
0x14007b829  test    rcx, rcx
0x14007b82c  jz      short loc_14007B834
0x14007b82e  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007b833  nop
0x14007b834  mov     rcx, [rbp+50h]; Irp
0x14007b838  mov     eax, [rbp+30h]
0x14007b83b  mov     [rcx+30h], eax
0x14007b83e  mov     qword ptr [rcx+38h], 0
0x14007b846  xor     edx, edx; PriorityBoost
0x14007b848  call    cs:__imp_IofCompleteRequest
0x14007b84f  nop     dword ptr [rax+rax+00h]
0x14007b854  nop
0x14007b855  add     rsp, 30h
0x14007b859  pop     rbp
0x14007b85a  retn
```
