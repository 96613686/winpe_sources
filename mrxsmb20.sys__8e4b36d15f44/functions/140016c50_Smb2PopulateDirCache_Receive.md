# Smb2PopulateDirCache_Receive

- ea: `0x140016c50`
- end: `0x140016ddc`
- name: `Smb2PopulateDirCache_Receive`
- size: `396`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140016c50`
- `0x1400372c0`

## import_xrefs

- `mrxsmb!RDR_PERF_ENTER` at `0x140016c7b`
- `mrxsmb!RDR_PERF_ENTER` at `0x140016c7b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140016d2e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140016d2e`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140016caa`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140016caa`

## pseudocode

```c
__int64 __fastcall Smb2PopulateDirCache_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6,
        __int64 a7)
{
  int v7; // edi
  __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned int v12; // esi
  __int64 v13; // rdx
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // ecx

  v7 = *(_DWORD *)(a3 + 16);
  v9 = a2 + 880;
  v10 = a2;
  LOBYTE(a2) = 35;
  v12 = 0;
  RDR_PERF_ENTER(v9, a2);
  if ( v7 >= 0 )
  {
    if ( a4 >= 0x48 )
    {
      v15 = *(unsigned __int16 *)(a7 + 66);
      if ( v15 < 0x48 )
      {
        LODWORD(v13) = a5;
        v7 = -1073741629;
        goto LABEL_3;
      }
      if ( v15 <= a5
        && (v16 = *(unsigned int *)(a7 + 68), (unsigned int)v16 <= a5)
        && (unsigned int)v16 + v15 <= a5
        && (_DWORD)v16
        && (unsigned int)v16 <= *(_DWORD *)(v10 + 744) )
      {
        v7 = 0;
        if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v16) + 64) & 1) != 0 )
          _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                          * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                         % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                                 + 424LL)
                                                                                     + 1488LL))
                                                          + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                      + 1480LL)
                                                          + 84));
        *(_DWORD *)(v10 + 748) = *(_DWORD *)(a7 + 68);
        v17 = *(_DWORD *)(a7 + 68);
        v13 = *(unsigned __int16 *)(a7 + 66);
        if ( (unsigned int)v13 + v17 > a4 )
        {
          v12 = -1073741802;
          goto LABEL_3;
        }
        memmove(*(void **)(v10 + 712), (const void *)(a7 + v13), v17);
      }
      else
      {
        v7 = -1073741629;
      }
      LODWORD(v13) = a5;
      goto LABEL_3;
    }
    v7 = -1073741629;
  }
  LODWORD(v13) = a5;
LABEL_3:
  *a6 = v13;
  SmbCseUpdateBufferContextStatus(v10, (unsigned int)v7);
  return v12;
}

```

## disassembly

```asm
0x140016c50  mov     [rsp+arg_10], rbx
0x140016c55  mov     [rsp+arg_18], rsi
0x140016c5a  push    rdi
0x140016c5b  push    r13
0x140016c5d  push    r14
0x140016c5f  sub     rsp, 20h
0x140016c63  mov     edi, [r8+10h]
0x140016c67  mov     r13, rcx
0x140016c6a  lea     rcx, [rdx+370h]
0x140016c71  mov     rbx, rdx
0x140016c74  mov     dl, 23h ; '#'
0x140016c76  mov     r14d, r9d
0x140016c79  xor     esi, esi
0x140016c7b  call    cs:__imp_RDR_PERF_ENTER
0x140016c82  nop     dword ptr [rax+rax+00h]
0x140016c87  test    edi, edi
0x140016c89  jns     short loc_140016CCD
0x140016c8b  mov     edx, [rsp+38h+arg_20]
0x140016c8f  mov     rcx, [rsp+38h+arg_28]
0x140016c94  mov     dword ptr [rsp+38h+arg_30], edi
0x140016c98  mov     dword ptr [rsp+38h+arg_30+4], 0
0x140016ca0  mov     [rcx], edx
0x140016ca2  mov     rcx, rbx
0x140016ca5  mov     rdx, [rsp+38h+arg_30]
0x140016caa  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140016cb1  nop     dword ptr [rax+rax+00h]
0x140016cb6  mov     rbx, [rsp+38h+arg_10]
0x140016cbb  mov     eax, esi
0x140016cbd  mov     rsi, [rsp+38h+arg_18]
0x140016cc2  add     rsp, 20h
0x140016cc6  pop     r14
0x140016cc8  pop     r13
0x140016cca  pop     rdi
0x140016ccb  retn
0x140016ccd  cmp     r14d, 48h ; 'H'
0x140016cd1  jb      loc_140016DC7
0x140016cd7  mov     [rsp+38h+arg_0], rbp
0x140016cdc  mov     rbp, [rsp+38h+arg_30]
0x140016ce1  movzx   eax, word ptr [rbp+42h]
0x140016ce5  cmp     eax, 48h ; 'H'
0x140016ce8  jb      loc_140016DD1
0x140016cee  mov     [rsp+38h+arg_8], r15
0x140016cf3  mov     r15d, [rsp+38h+arg_20]
0x140016cf8  cmp     eax, r15d
0x140016cfb  ja      loc_140016DC0
0x140016d01  mov     ecx, [rbp+44h]
0x140016d04  cmp     ecx, r15d
0x140016d07  ja      loc_140016DC0
0x140016d0d  add     eax, ecx
0x140016d0f  cmp     eax, r15d
0x140016d12  ja      loc_140016DC0
0x140016d18  test    ecx, ecx
0x140016d1a  jz      loc_140016DC0
0x140016d20  cmp     ecx, [rbx+2E8h]
0x140016d26  ja      loc_140016DC0
0x140016d2c  xor     edi, edi
0x140016d2e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140016d35  nop     dword ptr [rax+rax+00h]
0x140016d3a  test    byte ptr [rax+40h], 1
0x140016d3e  jz      short loc_140016D70
0x140016d40  mov     rax, [r13+58h]
0x140016d44  xor     edx, edx
0x140016d46  mov     r8, [rax+1A8h]
0x140016d4d  mov     eax, gs:1A4h
0x140016d55  div     dword ptr [r8+5D0h]
0x140016d5c  mov     rax, [r8+5C8h]
0x140016d63  lea     rdx, [rdx+rdx*2]
0x140016d67  shl     rdx, 6
0x140016d6b  lock inc dword ptr [rdx+rax+54h]
0x140016d70  mov     eax, [rbp+44h]
0x140016d73  mov     [rbx+2ECh], eax
0x140016d79  mov     ecx, [rbp+44h]
0x140016d7c  movzx   edx, word ptr [rbp+42h]
0x140016d80  lea     eax, [rdx+rcx]
0x140016d83  cmp     eax, r14d
0x140016d86  ja      short loc_140016DAC
0x140016d88  mov     r8d, ecx; Size
0x140016d8b  add     rdx, rbp; Src
0x140016d8e  mov     rcx, [rbx+2C8h]; void *
0x140016d95  call    memmove
0x140016d9a  mov     edx, r15d
0x140016d9d  mov     r15, [rsp+38h+arg_8]
0x140016da2  mov     rbp, [rsp+38h+arg_0]
0x140016da7  jmp     loc_140016C8F
0x140016dac  mov     r15, [rsp+38h+arg_8]
0x140016db1  mov     esi, 0C0000016h
0x140016db6  mov     rbp, [rsp+38h+arg_0]
0x140016dbb  jmp     loc_140016C8F
0x140016dc0  mov     edi, 0C00000C3h
0x140016dc5  jmp     short loc_140016D9A
0x140016dc7  mov     edi, 0C00000C3h
0x140016dcc  jmp     loc_140016C8B
0x140016dd1  mov     edx, [rsp+38h+arg_20]
0x140016dd5  mov     edi, 0C00000C3h
0x140016dda  jmp     short loc_140016DA2
```
