# Smb2PopulateVolInfoCache_Receive

- ea: `0x14001d950`
- end: `0x14001daa4`
- name: `Smb2PopulateVolInfoCache_Receive`
- size: `340`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001d950`
- `0x1400372c0`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001d9cd`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001d9cd`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001da68`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001da68`

## pseudocode

```c
__int64 __fastcall Smb2PopulateVolInfoCache_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  int v7; // ebx
  unsigned int v8; // r14d
  unsigned int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // rcx

  v7 = *(_DWORD *)(a3 + 16);
  v8 = 0;
  if ( v7 < 0 )
    goto LABEL_14;
  if ( a4 < 0x48 )
  {
    v7 = -1073741629;
LABEL_14:
    v12 = a5;
    goto LABEL_12;
  }
  v12 = a5;
  v13 = *(unsigned __int16 *)(a7 + 66);
  if ( v13 < 0x48
    || v13 > a5
    || (v14 = *(unsigned int *)(a7 + 68), (unsigned int)v14 > a5)
    || (unsigned int)v14 + v13 > a5
    || (unsigned int)v14 > *(_DWORD *)(a2 + 744) )
  {
    v7 = -1073741629;
  }
  else
  {
    v7 = 0;
    if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v14) + 64) & 1) != 0 )
      _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                      * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                     % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                             + 424LL)
                                                                                 + 1488LL))
                                                      + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                      + 84));
    *(_DWORD *)(a2 + 748) = *(_DWORD *)(a7 + 68);
    v15 = *(_DWORD *)(a7 + 68);
    v16 = *(unsigned __int16 *)(a7 + 66);
    if ( (unsigned int)v16 + v15 > a4 )
    {
      v8 = -1073741802;
      v12 = *(unsigned __int16 *)(a7 + 66);
    }
    else
    {
      memmove(*(void **)(a2 + 712), (const void *)(a7 + v16), v15);
    }
  }
LABEL_12:
  *a6 = v12;
  SmbCseUpdateBufferContextStatus(a2, (unsigned int)v7);
  return v8;
}

```

## disassembly

```asm
0x14001d950  push    rbx
0x14001d952  push    rbp
0x14001d953  push    rsi
0x14001d954  push    rdi
0x14001d955  push    r13
0x14001d957  push    r14
0x14001d959  sub     rsp, 28h
0x14001d95d  mov     ebx, [r8+10h]
0x14001d961  xor     r14d, r14d
0x14001d964  mov     ebp, r9d
0x14001d967  mov     rsi, rdx
0x14001d96a  mov     r13, rcx
0x14001d96d  test    ebx, ebx
0x14001d96f  js      loc_14001DA8A
0x14001d975  cmp     r9d, 48h ; 'H'
0x14001d979  jb      loc_14001DA85
0x14001d97f  mov     edi, [rsp+58h+arg_20]
0x14001d986  mov     [rsp+58h+arg_0], r15
0x14001d98b  mov     r15, [rsp+58h+arg_30]
0x14001d993  movzx   eax, word ptr [r15+42h]
0x14001d998  cmp     eax, 48h ; 'H'
0x14001d99b  jb      loc_14001DA9D
0x14001d9a1  cmp     eax, edi
0x14001d9a3  ja      loc_14001DA9D
0x14001d9a9  mov     ecx, [r15+44h]
0x14001d9ad  cmp     ecx, edi
0x14001d9af  ja      loc_14001DA9D
0x14001d9b5  add     eax, ecx
0x14001d9b7  cmp     eax, edi
0x14001d9b9  ja      loc_14001DA9D
0x14001d9bf  cmp     ecx, [rdx+2E8h]
0x14001d9c5  ja      loc_14001DA9D
0x14001d9cb  xor     ebx, ebx
0x14001d9cd  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001d9d4  nop     dword ptr [rax+rax+00h]
0x14001d9d9  test    byte ptr [rax+40h], 1
0x14001d9dd  jz      short loc_14001DA0F
0x14001d9df  mov     rax, [r13+58h]
0x14001d9e3  xor     edx, edx
0x14001d9e5  mov     r8, [rax+1A8h]
0x14001d9ec  mov     eax, gs:1A4h
0x14001d9f4  div     dword ptr [r8+5D0h]
0x14001d9fb  mov     rax, [r8+5C8h]
0x14001da02  lea     rdx, [rdx+rdx*2]
0x14001da06  shl     rdx, 6
0x14001da0a  lock inc dword ptr [rdx+rax+54h]
0x14001da0f  mov     eax, [r15+44h]
0x14001da13  mov     [rsi+2ECh], eax
0x14001da19  mov     edx, [r15+44h]
0x14001da1d  movzx   ecx, word ptr [r15+42h]
0x14001da22  lea     eax, [rcx+rdx]
0x14001da25  cmp     eax, ebp
0x14001da27  ja      short loc_14001DA93
0x14001da29  mov     r8d, edx; Size
0x14001da2c  lea     rdx, [r15+rcx]; Src
0x14001da30  mov     rcx, [rsi+2C8h]; void *
0x14001da37  call    memmove
0x14001da3c  mov     r15, [rsp+58h+arg_0]
0x14001da41  mov     rcx, [rsp+58h+arg_28]
0x14001da49  mov     dword ptr [rsp+58h+arg_30], ebx
0x14001da50  mov     dword ptr [rsp+58h+arg_30+4], 0
0x14001da5b  mov     rdx, [rsp+58h+arg_30]
0x14001da63  mov     [rcx], edi
0x14001da65  mov     rcx, rsi
0x14001da68  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001da6f  nop     dword ptr [rax+rax+00h]
0x14001da74  mov     eax, r14d
0x14001da77  add     rsp, 28h
0x14001da7b  pop     r14
0x14001da7d  pop     r13
0x14001da7f  pop     rdi
0x14001da80  pop     rsi
0x14001da81  pop     rbp
0x14001da82  pop     rbx
0x14001da83  retn
0x14001da85  mov     ebx, 0C00000C3h
0x14001da8a  mov     edi, [rsp+58h+arg_20]
0x14001da91  jmp     short loc_14001DA41
0x14001da93  mov     r14d, 0C0000016h
0x14001da99  mov     edi, ecx
0x14001da9b  jmp     short loc_14001DA3C
0x14001da9d  mov     ebx, 0C00000C3h
0x14001daa2  jmp     short loc_14001DA3C
```
