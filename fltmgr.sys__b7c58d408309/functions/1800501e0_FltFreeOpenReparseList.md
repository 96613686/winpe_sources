# FltFreeOpenReparseList

- ea: `0x1800501e0`
- end: `0x18005027c`
- name: `FltFreeOpenReparseList`
- size: `156`
- prototype: `void __fastcall(__int64, struct _ECP_LIST *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18004ffa0`
- `0x180083a00`

## callees

- `0x180009f20`
- `0x1800501e0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005025b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005025b`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180050201`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180050201`

## pseudocode

```c
void __fastcall FltFreeOpenReparseList(__int64 a1, struct _ECP_LIST *a2)
{
  NTSTATUS ExtraCreateParameter; // eax
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // rcx
  void *v6; // rdx
  PVOID EcpContext; // [rsp+40h] [rbp+18h] BYREF

  EcpContext = 0;
  ExtraCreateParameter = FsRtlFindExtraCreateParameter(a2, &ECP_TYPE_OPEN_REPARSE_GUID, &EcpContext, 0);
  if ( (int)FltpDbgStatus(ExtraCreateParameter) >= 0 )
  {
    v3 = *(_QWORD **)EcpContext;
    while ( v3 != EcpContext )
    {
      v4 = (_QWORD *)*v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
        __fastfail(3u);
      *v5 = v4;
      v6 = v3;
      v4[1] = v5;
      v3 = v4;
      ExFreeToPagedLookasideList(&stru_18003F340, v6);
    }
  }
}

```

## disassembly

```asm
0x1800501e0  push    rbx
0x1800501e2  sub     rsp, 20h
0x1800501e6  mov     rcx, rdx; EcpList
0x1800501e9  mov     [rsp+28h+EcpContext], 0
0x1800501f2  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x1800501f9  xor     r9d, r9d; EcpContextSize
0x1800501fc  lea     r8, [rsp+28h+EcpContext]; EcpContext
0x180050201  call    cs:__imp_FsRtlFindExtraCreateParameter
0x180050208  nop     dword ptr [rax+rax+00h]
0x18005020d  mov     r8d, 5D5h
0x180050213  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x18005021a  mov     ecx, eax
0x18005021c  xor     r9d, r9d
0x18005021f  call    FltpDbgStatus
0x180050224  test    eax, eax
0x180050226  js      short loc_18005026E
0x180050228  mov     rax, [rsp+28h+EcpContext]
0x18005022d  mov     rbx, [rax]
0x180050230  cmp     rbx, rax
0x180050233  jz      short loc_18005026E
0x180050235  mov     rax, [rbx]
0x180050238  cmp     [rax+8], rbx
0x18005023c  jnz     short loc_180050275
0x18005023e  mov     rcx, [rbx+8]
0x180050242  cmp     [rcx], rbx
0x180050245  jnz     short loc_180050275
0x180050247  mov     [rcx], rax
0x18005024a  mov     rdx, rbx; Entry
0x18005024d  mov     [rax+8], rcx
0x180050251  mov     rbx, rax
0x180050254  lea     rcx, stru_18003F340; Lookaside
0x18005025b  call    cs:__imp_ExFreeToPagedLookasideList
0x180050262  nop     dword ptr [rax+rax+00h]
0x180050267  cmp     rbx, [rsp+28h+EcpContext]
0x18005026c  jnz     short loc_180050235
0x18005026e  add     rsp, 20h
0x180050272  pop     rbx
0x180050273  retn
0x180050275  mov     ecx, 3
0x18005027a  int     29h; Win8: RtlFailFast(ecx)
```
