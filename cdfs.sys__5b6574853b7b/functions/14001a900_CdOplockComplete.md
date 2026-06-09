# CdOplockComplete

- ea: `0x14001a900`
- end: `0x14001a990`
- name: `CdOplockComplete`
- size: `144`
- prototype: `void __stdcall(PVOID Context, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001160`
- `0x140002b10`
- `0x14001943c`
- `0x14001a900`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001a953`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a953`

## pseudocode

```c
void __fastcall CdOplockComplete(__int16 ***Context, PIRP Irp)
{
  NTSTATUS Status; // r8d
  __int16 **v5; // rdx
  bool v6; // [rsp+38h] [rbp+10h] BYREF

  Status = Irp->IoStatus.Status;
  v6 = 0;
  if ( Status )
  {
    CdCompleteRequest(Context, Irp, Status);
  }
  else
  {
    if ( !*((_BYTE *)Context + 64) )
    {
      v5 = Context[6];
      if ( v5 )
      {
        CdTeardownStructures((__int64)Context, *v5, &v6);
        if ( !v6 )
          ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)*Context[6] + 25) + 32LL));
        *Context[6] = 0;
        Context[6] = 0;
      }
    }
    CdAddToWorkque(Context, Irp);
  }
}

```

## disassembly

```asm
0x14001a900  mov     [rsp+arg_0], rbx
0x14001a905  push    rdi
0x14001a906  sub     rsp, 20h
0x14001a90a  mov     r8d, [rdx+30h]
0x14001a90e  mov     rdi, rdx
0x14001a911  mov     [rsp+28h+arg_8], 0
0x14001a916  mov     rbx, rcx
0x14001a919  test    r8d, r8d
0x14001a91c  jnz     short loc_14001A97F
0x14001a91e  cmp     [rcx+40h], r8b
0x14001a922  jnz     short loc_14001A972
0x14001a924  mov     rdx, [rcx+30h]
0x14001a928  test    rdx, rdx
0x14001a92b  jz      short loc_14001A972
0x14001a92d  mov     rdx, [rdx]
0x14001a930  lea     r8, [rsp+28h+arg_8]
0x14001a935  call    CdTeardownStructures
0x14001a93a  cmp     [rsp+28h+arg_8], 0
0x14001a93f  jnz     short loc_14001A95F
0x14001a941  mov     rax, [rbx+30h]
0x14001a945  mov     rcx, [rax]
0x14001a948  mov     rcx, [rcx+0C8h]
0x14001a94f  add     rcx, 20h ; ' '; Resource
0x14001a953  call    cs:__imp_ExReleaseResourceLite
0x14001a95a  nop     dword ptr [rax+rax+00h]
0x14001a95f  mov     rax, [rbx+30h]
0x14001a963  mov     qword ptr [rax], 0
0x14001a96a  mov     qword ptr [rbx+30h], 0
0x14001a972  mov     rdx, rdi
0x14001a975  mov     rcx, rbx
0x14001a978  call    CdAddToWorkque
0x14001a97d  jmp     short loc_14001A984
0x14001a97f  call    CdCompleteRequest
0x14001a984  mov     rbx, [rsp+28h+arg_0]
0x14001a989  add     rsp, 20h
0x14001a98d  pop     rdi
0x14001a98e  retn
```
