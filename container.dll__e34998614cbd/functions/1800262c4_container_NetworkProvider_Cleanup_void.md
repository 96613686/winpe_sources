# container::NetworkProvider::Cleanup(void *)

- ea: `0x1800262c4`
- end: `0x18002633b`
- name: `?Cleanup@NetworkProvider@container@@YAXPEAX@Z`
- size: `119`
- prototype: `void __fastcall(HANDLE JobHandle, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005244`
- `0x18000d134`
- `0x18000d8f0`

## callees

- `0x1800262c4`
- `0x180026560`

## import_xrefs

- `IPHLPAPI!GetJobCompartmentId` at `0x1800262d1`
- `IPHLPAPI!GetJobCompartmentId` at `0x1800262d1`
- `IPHLPAPI!SetJobCompartmentId` at `0x1800262e9`
- `IPHLPAPI!SetJobCompartmentId` at `0x1800262e9`
- `IPHLPAPI!DeleteCompartment` at `0x18002630d`
- `IPHLPAPI!DeleteCompartment` at `0x18002630d`

## pseudocode

```c
void __fastcall container::NetworkProvider::Cleanup(HANDLE JobHandle, void *a2)
{
  NET_IF_COMPARTMENT_ID JobCompartmentId; // ebx
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned int v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  JobCompartmentId = GetJobCompartmentId(JobHandle);
  if ( JobCompartmentId != 1 )
  {
    v4 = SetJobCompartmentId(JobHandle, 0);
    if ( v4 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x33, v5, (const char *)v4, v8);
    v6 = DeleteCompartment(JobCompartmentId);
    if ( v6 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x3A, v7, (const char *)v6, v8);
  }
}

```

## disassembly

```asm
0x1800262c4  mov     [rsp+arg_0], rbx
0x1800262c9  push    rdi; unsigned int
0x1800262ca  sub     rsp, 20h
0x1800262ce  mov     rdi, rcx
0x1800262d1  call    cs:__imp_GetJobCompartmentId
0x1800262d8  nop     dword ptr [rax+rax+00h]
0x1800262dd  mov     ebx, eax
0x1800262df  cmp     eax, 1
0x1800262e2  jz      short loc_18002632F
0x1800262e4  xor     edx, edx; CompartmentId
0x1800262e6  mov     rcx, rdi; JobHandle
0x1800262e9  call    cs:__imp_SetJobCompartmentId
0x1800262f0  nop     dword ptr [rax+rax+00h]
0x1800262f5  test    eax, eax
0x1800262f7  jz      short loc_18002630B
0x1800262f9  mov     rcx, [rsp+28h]; this
0x1800262fe  mov     r9d, eax; char *
0x180026301  mov     edx, 33h ; '3'; void *
0x180026306  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002630b  mov     ecx, ebx
0x18002630d  call    cs:__imp_DeleteCompartment
0x180026314  nop     dword ptr [rax+rax+00h]
0x180026319  test    eax, eax
0x18002631b  jz      short loc_18002632F
0x18002631d  mov     rcx, [rsp+28h]; this
0x180026322  mov     r9d, eax; char *
0x180026325  mov     edx, 3Ah ; ':'; void *
0x18002632a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002632f  mov     rbx, [rsp+28h+arg_0]
0x180026334  add     rsp, 20h
0x180026338  pop     rdi
0x180026339  retn
```
