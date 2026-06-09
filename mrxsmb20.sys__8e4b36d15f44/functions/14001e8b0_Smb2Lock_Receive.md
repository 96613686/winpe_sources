# Smb2Lock_Receive

- ea: `0x14001e8b0`
- end: `0x14001e96e`
- name: `Smb2Lock_Receive`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14001e8b0`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e8e7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e8e7`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001e948`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001e948`

## pseudocode

```c
__int64 __fastcall Smb2Lock_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int v7; // ebx

  v7 = *(_DWORD *)(a3 + 16);
  if ( !v7 )
  {
    if ( a4 >= 0x44 && *(_WORD *)(a7 + 64) == 4 )
    {
      if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 64) & 1) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                        * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                       % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                               + 424LL)
                                                                                   + 1488LL))
                                                        + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                        + 84));
    }
    else
    {
      v7 = -1073741629;
    }
  }
  *a6 = a5;
  SmbCseUpdateBufferContextStatus(a2, v7);
  return 0;
}

```

## disassembly

```asm
0x14001e8b0  mov     [rsp+arg_0], rbx
0x14001e8b5  mov     [rsp+arg_8], rsi
0x14001e8ba  push    rdi
0x14001e8bb  sub     rsp, 20h
0x14001e8bf  mov     ebx, [r8+10h]
0x14001e8c3  mov     rdi, rdx
0x14001e8c6  mov     rsi, rcx
0x14001e8c9  test    ebx, ebx
0x14001e8cb  jnz     short loc_14001E929
0x14001e8cd  cmp     r9d, 44h ; 'D'
0x14001e8d1  jb      loc_14001E967
0x14001e8d7  mov     rax, [rsp+28h+arg_30]
0x14001e8dc  cmp     word ptr [rax+40h], 4
0x14001e8e1  jnz     loc_14001E967
0x14001e8e7  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001e8ee  nop     dword ptr [rax+rax+00h]
0x14001e8f3  test    byte ptr [rax+40h], 1
0x14001e8f7  jz      short loc_14001E929
0x14001e8f9  mov     rax, [rsi+58h]
0x14001e8fd  xor     edx, edx
0x14001e8ff  mov     r8, [rax+1A8h]
0x14001e906  mov     eax, gs:1A4h
0x14001e90e  div     dword ptr [r8+5D0h]
0x14001e915  mov     rax, [r8+5C8h]
0x14001e91c  lea     rdx, [rdx+rdx*2]
0x14001e920  shl     rdx, 6
0x14001e924  lock inc dword ptr [rdx+rax+54h]
0x14001e929  mov     rcx, [rsp+28h+arg_28]
0x14001e92e  mov     eax, [rsp+28h+arg_20]
0x14001e932  mov     dword ptr [rsp+28h+arg_28], ebx
0x14001e936  mov     dword ptr [rsp+28h+arg_28+4], 0
0x14001e93e  mov     rdx, [rsp+28h+arg_28]
0x14001e943  mov     [rcx], eax
0x14001e945  mov     rcx, rdi
0x14001e948  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001e94f  nop     dword ptr [rax+rax+00h]
0x14001e954  mov     rbx, [rsp+28h+arg_0]
0x14001e959  xor     eax, eax
0x14001e95b  mov     rsi, [rsp+28h+arg_8]
0x14001e960  add     rsp, 20h
0x14001e964  pop     rdi
0x14001e965  retn
0x14001e967  mov     ebx, 0C00000C3h
0x14001e96c  jmp     short loc_14001E929
```
