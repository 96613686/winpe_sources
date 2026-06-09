# Smb2SetInfo_Receive

- ea: `0x14001e100`
- end: `0x14001e1d3`
- name: `Smb2SetInfo_Receive`
- size: `211`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14001e100`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e146`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001e146`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001e19a`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001e19a`

## pseudocode

```c
__int64 __fastcall Smb2SetInfo_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int v7; // ebx
  __int16 v10; // dx
  __int64 result; // rax

  v7 = *(_DWORD *)(a3 + 16);
  if ( v7 )
  {
    *a6 = a5;
    goto LABEL_6;
  }
  if ( a4 < 0x42 )
  {
    *a6 = a5;
    goto LABEL_9;
  }
  v10 = *(_WORD *)(a7 + 64);
  *a6 = a5;
  if ( v10 != 2 )
  {
LABEL_9:
    v7 = -1073741629;
    goto LABEL_6;
  }
  if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a6) + 64) & 1) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                    * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                   % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                               + 1488LL))
                                                    + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                    + 84));
LABEL_6:
  SmbCseUpdateBufferContextStatus(a2, v7);
  result = 0;
  *(_DWORD *)(a1 + 16) = v7;
  *(_DWORD *)(a1 + 20) = 0;
  return result;
}

```

## disassembly

```asm
0x14001e100  push    rbx
0x14001e102  push    rbp
0x14001e103  push    rsi
0x14001e104  push    rdi
0x14001e105  sub     rsp, 28h
0x14001e109  mov     ebx, [r8+10h]
0x14001e10d  mov     rsi, rdx
0x14001e110  mov     rdi, rcx
0x14001e113  test    ebx, ebx
0x14001e115  jnz     loc_14001E1B8
0x14001e11b  mov     rcx, [rsp+48h+arg_28]
0x14001e120  cmp     r9d, 42h ; 'B'
0x14001e124  jb      loc_14001E1C6
0x14001e12a  mov     rax, [rsp+48h+arg_30]
0x14001e132  movzx   edx, word ptr [rax+40h]
0x14001e136  mov     eax, [rsp+48h+arg_20]
0x14001e13a  mov     [rcx], eax
0x14001e13c  cmp     dx, 2
0x14001e140  jnz     loc_14001E1CC
0x14001e146  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001e14d  nop     dword ptr [rax+rax+00h]
0x14001e152  test    byte ptr [rax+40h], 1
0x14001e156  jz      short loc_14001E188
0x14001e158  mov     rax, [rdi+58h]
0x14001e15c  xor     edx, edx
0x14001e15e  mov     r8, [rax+1A8h]
0x14001e165  mov     eax, gs:1A4h
0x14001e16d  div     dword ptr [r8+5D0h]
0x14001e174  mov     rax, [r8+5C8h]
0x14001e17b  lea     rdx, [rdx+rdx*2]
0x14001e17f  shl     rdx, 6
0x14001e183  lock inc dword ptr [rdx+rax+54h]
0x14001e188  xor     ebp, ebp
0x14001e18a  mov     dword ptr [rsp+48h+arg_0], ebx
0x14001e18e  mov     dword ptr [rsp+48h+arg_0+4], ebp
0x14001e192  mov     rcx, rsi
0x14001e195  mov     rdx, [rsp+48h+arg_0]
0x14001e19a  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001e1a1  nop     dword ptr [rax+rax+00h]
0x14001e1a6  xor     eax, eax
0x14001e1a8  mov     [rdi+10h], ebx
0x14001e1ab  mov     [rdi+14h], ebp
0x14001e1ae  add     rsp, 28h
0x14001e1b2  pop     rdi
0x14001e1b3  pop     rsi
0x14001e1b4  pop     rbp
0x14001e1b5  pop     rbx
0x14001e1b6  retn
0x14001e1b8  mov     r8, [rsp+48h+arg_28]
0x14001e1bd  mov     eax, [rsp+48h+arg_20]
0x14001e1c1  mov     [r8], eax
0x14001e1c4  jmp     short loc_14001E188
0x14001e1c6  mov     eax, [rsp+48h+arg_20]
0x14001e1ca  mov     [rcx], eax
0x14001e1cc  mov     ebx, 0C00000C3h
0x14001e1d1  jmp     short loc_14001E188
```
