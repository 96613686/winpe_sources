# SecCreateConsumerEntry

- ea: `0x140039a88`
- end: `0x140039bbe`
- name: `SecCreateConsumerEntry`
- size: `310`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140039c1c`

## callees

- `0x140009b80`
- `0x140011610`
- `0x1400119c0`
- `0x1400341e8`
- `0x140039a88`
- `0x14003c80c`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x140039b44`
- `ntoskrnl!RtlCopySid` at `0x140039b44`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140039add`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140039add`

## pseudocode

```c
__int64 __fastcall SecCreateConsumerEntry(PSID SourceSid, __int64 a2, _QWORD *a3)
{
  _DWORD *PoolWithTag; // rax
  _DWORD *v7; // rdi
  NTSTATUS v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx

  if ( qword_140020008 )
    PoolWithTag = (_DWORD *)qword_140020008(256, 120, 1852007251);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x78u, 0x6E636353u);
  v7 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x78u);
    *v7 = 7924234;
    v7[1] = 1;
    *((_QWORD *)v7 + 12) = a2;
    memset(v7 + 6, 0, 0x44u);
    *((_QWORD *)v7 + 2) = v7 + 2;
    *((_QWORD *)v7 + 1) = v7 + 2;
    v8 = RtlCopySid(0x44u, v7 + 6, SourceSid);
    if ( v8 >= 0 )
    {
      *a3 = v7;
      v7 = 0;
      v8 = 0;
    }
  }
  else
  {
    v8 = -1073741670;
  }
  if ( v7 )
  {
    v9 = *((_QWORD *)v7 + 13);
    if ( v9 )
    {
      MpRegFreeMonitorData(v9);
      *((_QWORD *)v7 + 13) = 0;
    }
    v10 = *((_QWORD *)v7 + 14);
    if ( v10 )
    {
      SecFileFreeMonitorData(v10);
      *((_QWORD *)v7 + 14) = 0;
    }
    SecFreePool(v7, 0x6E636353u);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140039a88  mov     rax, rsp
0x140039a8b  mov     [rax+8], rbx
0x140039a8f  mov     [rax+10h], rsi
0x140039a93  mov     [rax+18h], rdi
0x140039a97  mov     [rax+20h], r14
0x140039a9b  push    r15
0x140039a9d  sub     rsp, 30h
0x140039aa1  mov     rsi, r8
0x140039aa4  mov     r14, rdx
0x140039aa7  mov     r15, rcx
0x140039aaa  mov     qword ptr [rax-18h], 0
0x140039ab2  mov     rax, cs:qword_140020008
0x140039ab9  mov     ebx, 78h ; 'x'
0x140039abe  mov     r8d, 6E636353h; Tag
0x140039ac4  mov     edx, ebx; NumberOfBytes
0x140039ac6  test    rax, rax
0x140039ac9  jz      short loc_140039AD8
0x140039acb  mov     ecx, 100h
0x140039ad0  call    cs:__guard_dispatch_icall_fptr
0x140039ad6  jmp     short loc_140039AE9
0x140039ad8  mov     ecx, 1; PoolType
0x140039add  call    cs:__imp_ExAllocatePoolWithTag
0x140039ae4  nop     dword ptr [rax+rax+00h]
0x140039ae9  mov     rdi, rax
0x140039aec  mov     [rsp+38h+var_18], rax
0x140039af1  test    rax, rax
0x140039af4  jnz     short loc_140039AFD
0x140039af6  mov     ebx, 0C000009Ah
0x140039afb  jmp     short loc_140039B62
0x140039afd  mov     r8, rbx; Size
0x140039b00  xor     edx, edx; Val
0x140039b02  mov     rcx, rdi; void *
0x140039b05  call    memset
0x140039b0a  mov     dword ptr [rdi], 78EA0Ah
0x140039b10  mov     dword ptr [rdi+4], 1
0x140039b17  mov     [rdi+60h], r14
0x140039b1b  mov     r14d, 44h ; 'D'
0x140039b21  mov     r8d, r14d; Size
0x140039b24  xor     edx, edx; Val
0x140039b26  lea     rcx, [rdi+18h]; void *
0x140039b2a  call    memset
0x140039b2f  lea     rax, [rdi+8]
0x140039b33  mov     [rax+8], rax
0x140039b37  mov     [rax], rax
0x140039b3a  mov     r8, r15; SourceSid
0x140039b3d  lea     rdx, [rdi+18h]; DestinationSid
0x140039b41  mov     ecx, r14d; DestinationSidLength
0x140039b44  call    cs:__imp_RtlCopySid
0x140039b4b  nop     dword ptr [rax+rax+00h]
0x140039b50  mov     ebx, eax
0x140039b52  test    eax, eax
0x140039b54  js      short loc_140039B62
0x140039b56  mov     [rsi], rdi
0x140039b59  xor     edi, edi
0x140039b5b  mov     [rsp+38h+var_18], rdi
0x140039b60  xor     ebx, ebx
0x140039b62  test    rdi, rdi
0x140039b65  jz      short loc_140039BA0
0x140039b67  mov     rcx, [rdi+68h]
0x140039b6b  test    rcx, rcx
0x140039b6e  jz      short loc_140039B7D
0x140039b70  call    MpRegFreeMonitorData
0x140039b75  mov     qword ptr [rdi+68h], 0
0x140039b7d  mov     rcx, [rdi+70h]
0x140039b81  test    rcx, rcx
0x140039b84  jz      short loc_140039B93
0x140039b86  call    SecFileFreeMonitorData
0x140039b8b  mov     qword ptr [rdi+70h], 0
0x140039b93  mov     edx, 6E636353h; Tag
0x140039b98  mov     rcx, rdi; P
0x140039b9b  call    SecFreePool
0x140039ba0  mov     eax, ebx
0x140039ba2  mov     rbx, [rsp+38h+arg_0]
0x140039ba7  mov     rsi, [rsp+38h+arg_8]
0x140039bac  mov     rdi, [rsp+38h+arg_10]
0x140039bb1  mov     r14, [rsp+38h+arg_18]
0x140039bb6  add     rsp, 30h
0x140039bba  pop     r15
0x140039bbc  retn
0x14004476d  push    rbx
0x14004476f  push    rbp
0x140044770  sub     rsp, 28h
0x140044774  mov     rbp, rdx
0x140044777  mov     rbx, [rbp+20h]
0x14004477b  test    rbx, rbx
0x14004477e  jz      short loc_1400447BE
0x140044780  cmp     qword ptr [rbx+68h], 0
0x140044785  jz      short loc_140044798
0x140044787  mov     rcx, [rbx+68h]
0x14004478b  call    MpRegFreeMonitorData
0x140044790  mov     qword ptr [rbx+68h], 0
0x140044798  cmp     qword ptr [rbx+70h], 0
0x14004479d  jz      short loc_1400447B0
0x14004479f  mov     rcx, [rbx+70h]
0x1400447a3  call    SecFileFreeMonitorData
0x1400447a8  mov     qword ptr [rbx+70h], 0
0x1400447b0  mov     edx, 6E636353h; Tag
0x1400447b5  mov     rcx, rbx; P
0x1400447b8  call    SecFreePool
0x1400447bd  nop
0x1400447be  add     rsp, 28h
0x1400447c2  pop     rbp
0x1400447c3  pop     rbx
0x1400447c4  retn
```
