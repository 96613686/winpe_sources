# SetComputerSid

- ea: `0x14004f4fc`
- end: `0x14004f65a`
- name: `SetComputerSid`
- size: `350`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400478d0`

## callees

- `0x14004f4fc`
- `0x140059f00`
- `0x14005a200`
- `0x14005a720`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004f5e4`
- `ntoskrnl!ExAllocatePool2` at `0x14004f5e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f642`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f642`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14004f53a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14004f53a`
- `ntoskrnl!ExReleaseFastResource` at `0x14004f629`
- `ntoskrnl!ExReleaseFastResource` at `0x14004f629`
- `ntoskrnl!RtlLengthSid` at `0x14004f57f`
- `ntoskrnl!RtlLengthSid` at `0x14004f590`
- `ntoskrnl!RtlLengthSid` at `0x14004f5b8`
- `ntoskrnl!RtlLengthSid` at `0x14004f57f`
- `ntoskrnl!RtlLengthSid` at `0x14004f590`
- `ntoskrnl!RtlLengthSid` at `0x14004f5b8`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14004f51f`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14004f51f`

## pseudocode

```c
__int64 __fastcall SetComputerSid(void *Buf2)
{
  void *v2; // rbx
  __int64 v3; // r8
  void *v4; // rdi
  __int64 v5; // rbp
  ULONG v6; // eax
  size_t v7; // rdi
  void *Pool2; // rax
  unsigned int v9; // edi
  _BYTE v11[120]; // [rsp+20h] [rbp-78h] BYREF

  memset(v11, 0, 0x48u);
  v2 = 0;
  ExInitializeFastOwnerEntry(v11);
  LOBYTE(v3) = 1;
  ExAcquireFastResourceExclusive(&GlobalResource, v11, v3);
  if ( Buf2 )
  {
    v4 = *(void **)&ComputerSidAndAttributes.Revision;
    if ( !*(_QWORD *)&ComputerSidAndAttributes.Revision
      || (v5 = RtlLengthSid(*(PSID *)&ComputerSidAndAttributes.Revision), v5 != RtlLengthSid(v4))
      || memcmp(v4, Buf2, (unsigned int)v5) )
    {
      v6 = RtlLengthSid(Buf2);
      v2 = *(void **)&ComputerSidAndAttributes.Revision;
      v7 = v6;
      ComputerSidAndAttributes.SubAuthority[0] = 0;
      Pool2 = (void *)ExAllocatePool2(256, v6, 1094929747);
      *(_QWORD *)&ComputerSidAndAttributes.Revision = Pool2;
      if ( !Pool2 )
      {
        v9 = -1073741670;
        goto LABEL_11;
      }
      memmove(Pool2, Buf2, v7);
      ComputerSidAndAttributes.SubAuthority[0] = 7;
    }
  }
  else if ( *(_QWORD *)&ComputerSidAndAttributes.Revision )
  {
    v2 = *(void **)&ComputerSidAndAttributes.Revision;
    *(_QWORD *)&ComputerSidAndAttributes.Revision = 0;
    ComputerSidAndAttributes.SubAuthority[0] = 0;
  }
  v9 = 0;
LABEL_11:
  ExReleaseFastResource(&GlobalResource, v11);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x41434D53u);
  return v9;
}

```

## disassembly

```asm
0x14004f4fc  push    rbx
0x14004f4fe  push    rbp
0x14004f4ff  push    rsi
0x14004f500  push    rdi
0x14004f501  sub     rsp, 78h
0x14004f505  xor     edx, edx; Val
0x14004f507  mov     rsi, rcx
0x14004f50a  lea     rcx, [rsp+98h+var_78]; void *
0x14004f50f  lea     r8d, [rdx+48h]; Size
0x14004f513  call    memset
0x14004f518  lea     rcx, [rsp+98h+var_78]
0x14004f51d  xor     ebx, ebx
0x14004f51f  call    cs:__imp_ExInitializeFastOwnerEntry
0x14004f526  nop     dword ptr [rax+rax+00h]
0x14004f52b  mov     r8b, 1
0x14004f52e  lea     rdx, [rsp+98h+var_78]
0x14004f533  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x14004f53a  call    cs:__imp_ExAcquireFastResourceExclusive
0x14004f541  nop     dword ptr [rax+rax+00h]
0x14004f546  test    rsi, rsi
0x14004f549  jnz     short loc_14004F570
0x14004f54b  mov     rax, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f552  test    rax, rax
0x14004f555  jz      loc_14004F61B
0x14004f55b  mov     rbx, rax
0x14004f55e  mov     qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision, rsi; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f565  mov     cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.SubAuthority, esi; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f56b  jmp     loc_14004F61B
0x14004f570  mov     rdi, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f577  test    rdi, rdi
0x14004f57a  jz      short loc_14004F5B5
0x14004f57c  mov     rcx, rdi; Sid
0x14004f57f  call    cs:__imp_RtlLengthSid
0x14004f586  nop     dword ptr [rax+rax+00h]
0x14004f58b  mov     rcx, rdi; Sid
0x14004f58e  mov     ebp, eax
0x14004f590  call    cs:__imp_RtlLengthSid
0x14004f597  nop     dword ptr [rax+rax+00h]
0x14004f59c  mov     eax, eax
0x14004f59e  cmp     rbp, rax
0x14004f5a1  jnz     short loc_14004F5B5
0x14004f5a3  mov     r8d, ebp; Size
0x14004f5a6  mov     rdx, rsi; Buf2
0x14004f5a9  mov     rcx, rdi; Buf1
0x14004f5ac  call    memcmp
0x14004f5b1  test    eax, eax
0x14004f5b3  jz      short loc_14004F61B
0x14004f5b5  mov     rcx, rsi; Sid
0x14004f5b8  call    cs:__imp_RtlLengthSid
0x14004f5bf  nop     dword ptr [rax+rax+00h]
0x14004f5c4  mov     rbx, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f5cb  mov     r8d, 41434D53h
0x14004f5d1  mov     edx, eax
0x14004f5d3  mov     ecx, 100h
0x14004f5d8  mov     edi, eax
0x14004f5da  mov     cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.SubAuthority, 0; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f5e4  call    cs:__imp_ExAllocatePool2
0x14004f5eb  nop     dword ptr [rax+rax+00h]
0x14004f5f0  mov     qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision, rax; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f5f7  test    rax, rax
0x14004f5fa  jnz     short loc_14004F603
0x14004f5fc  mov     edi, 0C000009Ah
0x14004f601  jmp     short loc_14004F61D
0x14004f603  mov     r8, rdi; Size
0x14004f606  mov     rdx, rsi; Src
0x14004f609  mov     rcx, rax; void *
0x14004f60c  call    memmove
0x14004f611  mov     cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.SubAuthority, 7; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14004f61b  xor     edi, edi
0x14004f61d  lea     rdx, [rsp+98h+var_78]
0x14004f622  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x14004f629  call    cs:__imp_ExReleaseFastResource
0x14004f630  nop     dword ptr [rax+rax+00h]
0x14004f635  test    rbx, rbx
0x14004f638  jz      short loc_14004F64E
0x14004f63a  mov     edx, 41434D53h; Tag
0x14004f63f  mov     rcx, rbx; P
0x14004f642  call    cs:__imp_ExFreePoolWithTag
0x14004f649  nop     dword ptr [rax+rax+00h]
0x14004f64e  mov     eax, edi
0x14004f650  add     rsp, 78h
0x14004f654  pop     rdi
0x14004f655  pop     rsi
0x14004f656  pop     rbp
0x14004f657  pop     rbx
0x14004f658  retn
```
