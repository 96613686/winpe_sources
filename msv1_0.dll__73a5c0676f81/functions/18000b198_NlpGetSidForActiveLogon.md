# NlpGetSidForActiveLogon

- ea: `0x18000b198`
- end: `0x18000b243`
- name: `NlpGetSidForActiveLogon`
- size: `171`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180040124`

## callees

- `0x18000b198`
- `0x18000c5d0`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000b1d8`
- `ntdll!RtlLengthSid` at `0x18000b1d8`
- `ntdll!RtlCopySid` at `0x18000b206`
- `ntdll!RtlCopySid` at `0x18000b206`
- `ntdll!RtlReleaseResource` at `0x18000b21e`
- `ntdll!RtlReleaseResource` at `0x18000b21e`
- `ntdll!RtlAcquireResourceShared` at `0x18000b1b7`
- `ntdll!RtlAcquireResourceShared` at `0x18000b1b7`

## pseudocode

```c
__int64 __fastcall NlpGetSidForActiveLogon(void *a1, _QWORD *a2)
{
  __int64 ActiveLogon; // rax
  __int64 v5; // rdi
  NTSTATUS v6; // edi
  __int64 v7; // rbp
  void *v8; // rax
  void *v9; // rbx

  *a2 = 0;
  RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
  ActiveLogon = NlpFindActiveLogon(a1);
  v5 = ActiveLogon;
  if ( !ActiveLogon )
  {
    v6 = -1073741729;
LABEL_7:
    v9 = 0;
    goto LABEL_8;
  }
  v7 = RtlLengthSid(*(PSID *)(ActiveLogon + 64));
  v8 = (void *)((__int64 (__fastcall *)(__int64))qword_180088238)(v7);
  v9 = v8;
  if ( !v8 )
  {
    v6 = -1073741801;
    goto LABEL_8;
  }
  v6 = RtlCopySid(v7, v8, *(PSID *)(v5 + 64));
  if ( v6 >= 0 )
  {
    *a2 = v9;
    goto LABEL_7;
  }
LABEL_8:
  RtlReleaseResource(&NlpActiveLogonLock);
  if ( v9 )
    ((void (__fastcall *)(void *))qword_180088240)(v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b198  push    rbx
0x18000b19a  push    rbp
0x18000b19b  push    rsi
0x18000b19c  push    rdi
0x18000b19d  sub     rsp, 28h
0x18000b1a1  mov     rsi, rdx
0x18000b1a4  mov     qword ptr [rdx], 0
0x18000b1ab  mov     rbx, rcx
0x18000b1ae  mov     dl, 1; Wait
0x18000b1b0  lea     rcx, NlpActiveLogonLock; Resource
0x18000b1b7  call    cs:__imp_RtlAcquireResourceShared
0x18000b1bd  mov     rcx, rbx; void *
0x18000b1c0  call    NlpFindActiveLogon
0x18000b1c5  mov     rdi, rax
0x18000b1c8  test    rax, rax
0x18000b1cb  jnz     short loc_18000B1D4
0x18000b1cd  mov     edi, 0C000005Fh
0x18000b1d2  jmp     short loc_18000B215
0x18000b1d4  mov     rcx, [rax+40h]; Sid
0x18000b1d8  call    cs:__imp_RtlLengthSid
0x18000b1de  mov     ebp, eax
0x18000b1e0  mov     ecx, eax
0x18000b1e2  mov     rax, cs:qword_180088238
0x18000b1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ee  mov     rbx, rax
0x18000b1f1  test    rax, rax
0x18000b1f4  jnz     short loc_18000B1FD
0x18000b1f6  mov     edi, 0C0000017h
0x18000b1fb  jmp     short loc_18000B217
0x18000b1fd  mov     r8, [rdi+40h]; SourceSid
0x18000b201  mov     rdx, rbx; DestinationSid
0x18000b204  mov     ecx, ebp; DestinationSidLength
0x18000b206  call    cs:__imp_RtlCopySid
0x18000b20c  mov     edi, eax
0x18000b20e  test    eax, eax
0x18000b210  js      short loc_18000B217
0x18000b212  mov     [rsi], rbx
0x18000b215  xor     ebx, ebx
0x18000b217  lea     rcx, NlpActiveLogonLock; Resource
0x18000b21e  call    cs:__imp_RtlReleaseResource
0x18000b224  test    rbx, rbx
0x18000b227  jz      short loc_18000B238
0x18000b229  mov     rax, cs:qword_180088240
0x18000b230  mov     rcx, rbx
0x18000b233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b238  mov     eax, edi
0x18000b23a  add     rsp, 28h
0x18000b23e  pop     rdi
0x18000b23f  pop     rsi
0x18000b240  pop     rbp
0x18000b241  pop     rbx
0x18000b242  retn
```
