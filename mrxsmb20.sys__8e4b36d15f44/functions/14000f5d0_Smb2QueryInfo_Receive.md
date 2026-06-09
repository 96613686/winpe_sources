# Smb2QueryInfo_Receive

- ea: `0x14000f5d0`
- end: `0x14000f7b8`
- name: `Smb2QueryInfo_Receive`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x14000f5d0`
- `0x14000fa00`
- `0x1400372c0`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000f659`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000f659`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14000f6ef`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14000f6ef`

## pseudocode

```c
__int64 __fastcall Smb2QueryInfo_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  unsigned int v7; // edi
  unsigned int v11; // esi
  unsigned int v12; // ebp
  __int64 v13; // r13
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // rcx
  int v19; // eax
  __int64 v20; // [rsp+70h] [rbp+8h] BYREF
  _DWORD *v21; // [rsp+80h] [rbp+18h] BYREF

  v7 = *(_DWORD *)(a3 + 16);
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147483643 )
  {
    v11 = a5;
    v12 = 0;
    if ( a4 < 0x48 )
    {
      v7 = -1073741629;
    }
    else
    {
      v13 = a7;
      if ( *(_WORD *)(a7 + 64) == 9
        && (v14 = *(unsigned __int16 *)(a7 + 66), v14 <= a5)
        && (v15 = *(unsigned int *)(a7 + 68), (unsigned int)v15 <= a5)
        && (unsigned int)v15 + v14 <= a5
        && (unsigned int)v15 <= *(_DWORD *)(a2 + 744) )
      {
        if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v15) + 64) & 1) != 0 )
          _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                          * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                         % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                                 + 424LL)
                                                                                     + 1488LL))
                                                          + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                      + 1480LL)
                                                          + 84));
        *(_DWORD *)(a2 + 748) = *(_DWORD *)(v13 + 68);
        v16 = *(_DWORD *)(v13 + 68);
        v17 = *(unsigned __int16 *)(v13 + 66);
        if ( (unsigned int)v17 + v16 > a4 )
        {
          v12 = -1073741802;
          v11 = *(unsigned __int16 *)(v13 + 66);
        }
        else
        {
          memmove(*(void **)(a1 + 1736), (const void *)(v17 + v13), v16);
        }
      }
      else
      {
        v7 = -1073741629;
      }
    }
  }
  else
  {
    v21 = 0;
    LODWORD(v20) = 0;
    v19 = Smb2QueryErrorDataFromResponse(a7 + 64, a4, 0, &v21, (unsigned int *)&v20);
    if ( v19 < 0 )
    {
      v11 = a5;
      v7 = v19;
      v12 = 0;
    }
    else
    {
      if ( v7 == -1073741789 )
      {
        if ( (_DWORD)v20 == 4 )
          *(_DWORD *)(a2 + 748) = *v21;
        else
          *(_DWORD *)(a2 + 748) = 0;
      }
      v11 = a5;
      v12 = 0;
    }
  }
  *a6 = v11;
  v20 = v7;
  SmbCseUpdateBufferContextStatus(a2, v7);
  return v12;
}

```

## disassembly

```asm
0x14000f5d0  push    rbx
0x14000f5d2  push    rbp
0x14000f5d3  push    rsi
0x14000f5d4  push    rdi
0x14000f5d5  push    r12
0x14000f5d7  push    r14
0x14000f5d9  push    r15
0x14000f5db  sub     rsp, 30h
0x14000f5df  mov     edi, [r8+10h]
0x14000f5e3  mov     r12, rcx
0x14000f5e6  mov     ecx, 80000000h
0x14000f5eb  mov     r14d, r9d
0x14000f5ee  mov     r15, rdx
0x14000f5f1  lea     eax, [rdi+rcx]
0x14000f5f4  test    ecx, eax
0x14000f5f6  jz      loc_14000F70D
0x14000f5fc  mov     esi, [rsp+68h+arg_20]
0x14000f603  xor     ebx, ebx
0x14000f605  mov     ebp, ebx
0x14000f607  cmp     r14d, 48h ; 'H'
0x14000f60b  jb      loc_14000F76A
0x14000f611  mov     [rsp+68h+arg_8], r13
0x14000f616  mov     r13, [rsp+68h+arg_30]
0x14000f61e  cmp     word ptr [r13+40h], 9
0x14000f624  jnz     loc_14000F780
0x14000f62a  movzx   eax, word ptr [r13+42h]
0x14000f62f  cmp     eax, esi
0x14000f631  ja      loc_14000F780
0x14000f637  mov     ecx, [r13+44h]
0x14000f63b  cmp     ecx, esi
0x14000f63d  ja      loc_14000F780
0x14000f643  add     eax, ecx
0x14000f645  cmp     eax, esi
0x14000f647  ja      loc_14000F780
0x14000f64d  cmp     ecx, [rdx+2E8h]
0x14000f653  ja      loc_14000F780
0x14000f659  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14000f660  nop     dword ptr [rax+rax+00h]
0x14000f665  test    byte ptr [rax+40h], 1
0x14000f669  jz      short loc_14000F69C
0x14000f66b  mov     rax, [r12+58h]
0x14000f670  xor     edx, edx
0x14000f672  mov     r8, [rax+1A8h]
0x14000f679  mov     eax, gs:1A4h
0x14000f681  div     dword ptr [r8+5D0h]
0x14000f688  mov     rax, [r8+5C8h]
0x14000f68f  lea     rdx, [rdx+rdx*2]
0x14000f693  shl     rdx, 6
0x14000f697  lock inc dword ptr [rdx+rax+54h]
0x14000f69c  mov     eax, [r13+44h]
0x14000f6a0  mov     [r15+2ECh], eax
0x14000f6a7  mov     edx, [r13+44h]
0x14000f6ab  movzx   ecx, word ptr [r13+42h]
0x14000f6b0  lea     eax, [rcx+rdx]
0x14000f6b3  cmp     eax, r14d
0x14000f6b6  ja      loc_14000F774
0x14000f6bc  mov     r8d, edx; Size
0x14000f6bf  lea     rdx, [rcx+r13]; Src
0x14000f6c3  mov     rcx, [r12+6C8h]; void *
0x14000f6cb  call    memmove
0x14000f6d0  mov     r13, [rsp+68h+arg_8]
0x14000f6d5  mov     rcx, [rsp+68h+arg_28]
0x14000f6dd  mov     [rcx], esi
0x14000f6df  mov     rcx, r15
0x14000f6e2  mov     dword ptr [rsp+68h+arg_0], edi
0x14000f6e6  mov     dword ptr [rsp+68h+arg_0+4], ebx
0x14000f6ea  mov     rdx, [rsp+68h+arg_0]
0x14000f6ef  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14000f6f6  nop     dword ptr [rax+rax+00h]
0x14000f6fb  mov     eax, ebp
0x14000f6fd  add     rsp, 30h
0x14000f701  pop     r15
0x14000f703  pop     r14
0x14000f705  pop     r12
0x14000f707  pop     rdi
0x14000f708  pop     rsi
0x14000f709  pop     rbp
0x14000f70a  pop     rbx
0x14000f70b  retn
0x14000f70d  cmp     edi, 80000005h
0x14000f713  jz      loc_14000F5FC
0x14000f719  mov     rcx, [rsp+68h+arg_30]
0x14000f721  lea     rax, [rsp+68h+arg_0]
0x14000f726  xor     ebx, ebx
0x14000f728  mov     [rsp+68h+var_48], rax
0x14000f72d  add     rcx, 40h ; '@'
0x14000f731  mov     [rsp+68h+arg_10], rbx
0x14000f739  lea     r9, [rsp+68h+arg_10]
0x14000f741  mov     dword ptr [rsp+68h+arg_0], ebx
0x14000f745  xor     r8d, r8d
0x14000f748  mov     edx, r14d
0x14000f74b  call    Smb2QueryErrorDataFromResponse
0x14000f750  test    eax, eax
0x14000f752  js      short loc_14000F78A
0x14000f754  cmp     edi, 0C0000023h
0x14000f75a  jz      short loc_14000F79A
0x14000f75c  mov     esi, [rsp+68h+arg_20]
0x14000f763  mov     ebp, ebx
0x14000f765  jmp     loc_14000F6D5
0x14000f76a  mov     edi, 0C00000C3h
0x14000f76f  jmp     loc_14000F6D5
0x14000f774  mov     ebp, 0C0000016h
0x14000f779  mov     esi, ecx
0x14000f77b  jmp     loc_14000F6D0
0x14000f780  mov     edi, 0C00000C3h
0x14000f785  jmp     loc_14000F6D0
0x14000f78a  mov     esi, [rsp+68h+arg_20]
0x14000f791  mov     edi, eax
0x14000f793  mov     ebp, ebx
0x14000f795  jmp     loc_14000F6D5
0x14000f79a  cmp     dword ptr [rsp+68h+arg_0], 4
0x14000f79f  jnz     loc_140039C76
0x14000f7a5  mov     rax, [rsp+68h+arg_10]
0x14000f7ad  mov     ecx, [rax]
0x14000f7af  mov     [r15+2ECh], ecx
0x14000f7b6  jmp     short loc_14000F75C
0x140039c76  mov     [r15+2ECh], ebx
0x140039c7d  jmp     loc_14000F75C
```
