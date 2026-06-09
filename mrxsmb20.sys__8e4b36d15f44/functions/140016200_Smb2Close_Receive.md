# Smb2Close_Receive

- ea: `0x140016200`
- end: `0x140016313`
- name: `Smb2Close_Receive`
- size: `275`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x140016200`

## import_xrefs

- `mrxsmb!RDR_PERF_ENTER` at `0x14001621f`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001621f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140016286`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140016286`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400162dc`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400162dc`

## pseudocode

```c
__int64 __fastcall Smb2Close_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int v7; // esi
  __int64 v8; // rbp

  v7 = *(_DWORD *)(a3 + 16);
  v8 = a2;
  LOBYTE(a2) = 35;
  RDR_PERF_ENTER(a1 + 512, a2);
  if ( v7 )
  {
    *a6 = a5;
  }
  else if ( a4 < 0x7C )
  {
    v7 = -1073741629;
    *a6 = a5;
  }
  else
  {
    if ( (*(_BYTE *)(a7 + 66) & 1) != 0 )
    {
      *(_BYTE *)(a1 + 2409) = 1;
      *(_OWORD *)(a1 + 2416) = *(_OWORD *)(a7 + 72);
      *(_OWORD *)(a1 + 2432) = *(_OWORD *)(a7 + 88);
      *(_OWORD *)(a1 + 2448) = *(_OWORD *)(a7 + 104);
      *(_DWORD *)(a1 + 2464) = *(_DWORD *)(a7 + 120);
    }
    *a6 = a5;
    if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a6) + 64) & 1) != 0 )
      _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                      * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                     % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                             + 424LL)
                                                                                 + 1488LL))
                                                      + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                      + 84));
  }
  SmbCseUpdateBufferContextStatus(v8, v7);
  return 0;
}

```

## disassembly

```asm
0x140016200  push    rbx
0x140016202  push    rbp
0x140016203  push    rsi
0x140016204  push    rdi
0x140016205  sub     rsp, 28h
0x140016209  mov     esi, [r8+10h]
0x14001620d  mov     rbp, rdx
0x140016210  mov     rbx, rcx
0x140016213  mov     dl, 23h ; '#'
0x140016215  add     rcx, 200h
0x14001621c  mov     edi, r9d
0x14001621f  call    cs:__imp_RDR_PERF_ENTER
0x140016226  nop     dword ptr [rax+rax+00h]
0x14001622b  test    esi, esi
0x14001622d  jnz     loc_1400162F4
0x140016233  cmp     edi, 7Ch ; '|'
0x140016236  jb      loc_140016301
0x14001623c  mov     rax, [rsp+48h+arg_30]
0x140016244  test    byte ptr [rax+42h], 1
0x140016248  jz      short loc_14001627B
0x14001624a  mov     byte ptr [rbx+969h], 1
0x140016251  movups  xmm0, xmmword ptr [rax+48h]
0x140016255  movups  xmmword ptr [rbx+970h], xmm0
0x14001625c  movups  xmm1, xmmword ptr [rax+58h]
0x140016260  movups  xmmword ptr [rbx+980h], xmm1
0x140016267  movups  xmm0, xmmword ptr [rax+68h]
0x14001626b  movups  xmmword ptr [rbx+990h], xmm0
0x140016272  mov     ecx, [rax+78h]
0x140016275  mov     [rbx+9A0h], ecx
0x14001627b  mov     rcx, [rsp+48h+arg_28]
0x140016280  mov     eax, [rsp+48h+arg_20]
0x140016284  mov     [rcx], eax
0x140016286  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001628d  nop     dword ptr [rax+rax+00h]
0x140016292  test    byte ptr [rax+40h], 1
0x140016296  jz      short loc_1400162C8
0x140016298  mov     rax, [rbx+58h]
0x14001629c  xor     edx, edx
0x14001629e  mov     r8, [rax+1A8h]
0x1400162a5  mov     eax, gs:1A4h
0x1400162ad  div     dword ptr [r8+5D0h]
0x1400162b4  mov     rax, [r8+5C8h]
0x1400162bb  lea     rdx, [rdx+rdx*2]
0x1400162bf  shl     rdx, 6
0x1400162c3  lock inc dword ptr [rdx+rax+54h]
0x1400162c8  mov     dword ptr [rsp+48h+arg_0], esi
0x1400162cc  mov     rcx, rbp
0x1400162cf  mov     dword ptr [rsp+48h+arg_0+4], 0
0x1400162d7  mov     rdx, [rsp+48h+arg_0]
0x1400162dc  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x1400162e3  nop     dword ptr [rax+rax+00h]
0x1400162e8  xor     eax, eax
0x1400162ea  add     rsp, 28h
0x1400162ee  pop     rdi
0x1400162ef  pop     rsi
0x1400162f0  pop     rbp
0x1400162f1  pop     rbx
0x1400162f2  retn
0x1400162f4  mov     rcx, [rsp+48h+arg_28]
0x1400162f9  mov     eax, [rsp+48h+arg_20]
0x1400162fd  mov     [rcx], eax
0x1400162ff  jmp     short loc_1400162C8
0x140016301  mov     rcx, [rsp+48h+arg_28]
0x140016306  mov     esi, 0C00000C3h
0x14001630b  mov     eax, [rsp+48h+arg_20]
0x14001630f  mov     [rcx], eax
0x140016311  jmp     short loc_1400162C8
```
