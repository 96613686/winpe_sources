# MRxSmbPseudoOpenTailFromCoreCreateDirectory

- ea: `0x14003b3a4`
- end: `0x14003b4c1`
- name: `MRxSmbPseudoOpenTailFromCoreCreateDirectory`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003a5f0`

## callees

- `0x14000dfa8`
- `0x14003b3a4`
- `0x1400499e0`
- `0x14004a2f0`
- `0x14004fff0`

## pseudocode

```c
__int64 __fastcall MRxSmbPseudoOpenTailFromCoreCreateDirectory(__int64 a1, unsigned __int16 a2)
{
  struct _RX_CONTEXT *v2; // rbp
  PMRX_SRV_OPEN pRelevantSrvOpen; // rsi
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 result; // rax

  v2 = *(struct _RX_CONTEXT **)(a1 + 24);
  pRelevantSrvOpen = v2->pRelevantSrvOpen;
  if ( pRelevantSrvOpen )
    v6 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  else
    v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids);
  MRxSmbPopulateFileInfoInOE(a1, a2, 0, 0);
  *(_DWORD *)(v6 + 72) = *(_DWORD *)(a1 + 504);
  *(_QWORD *)(v6 + 40) = *(_QWORD *)(a1 + 472);
  *(_QWORD *)(v6 + 48) = *(_QWORD *)(a1 + 480);
  *(_QWORD *)(v6 + 56) = *(_QWORD *)(a1 + 488);
  *(_QWORD *)(v6 + 64) = *(_QWORD *)(a1 + 496);
  *(_DWORD *)(v6 + 96) = *(_DWORD *)(a1 + 528);
  *(_QWORD *)(v6 + 80) = *(_QWORD *)(a1 + 512);
  *(_QWORD *)(v6 + 88) = *(_QWORD *)(a1 + 520);
  *(_BYTE *)(v6 + 101) = 1;
  LODWORD(pRelevantSrvOpen->Key) |= 0x100000u;
  result = MRxSmbCreateFileSuccessTail(v2, v7, 1, 0xBADDu, *(_DWORD *)(a1 + 52), 0, 2u, v6 + 40);
  if ( !(_DWORD)result && !*(_QWORD *)(v6 + 16) )
    return MRxSmbConstructDeferredOpenContext((__int64)v2);
  return result;
}

```

## disassembly

```asm
0x14003b3a4  push    rbx
0x14003b3a6  push    rbp
0x14003b3a7  push    rsi
0x14003b3a8  push    rdi
0x14003b3a9  push    r14
0x14003b3ab  push    r15
0x14003b3ad  sub     rsp, 48h
0x14003b3b1  mov     rbp, [rcx+18h]
0x14003b3b5  movzx   r15d, dx
0x14003b3b9  mov     rdi, rcx
0x14003b3bc  mov     rsi, [rbp+48h]
0x14003b3c0  test    rsi, rsi
0x14003b3c3  jnz     short loc_14003B3C9
0x14003b3c5  xor     ebx, ebx
0x14003b3c7  jmp     short loc_14003B3CD
0x14003b3c9  mov     rbx, [rsi+30h]
0x14003b3cd  lea     r14, [rbx+28h]
0x14003b3d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003b3d8  lea     rax, WPP_GLOBAL_Control
0x14003b3df  cmp     rcx, rax
0x14003b3e2  jz      short loc_14003B402
0x14003b3e4  test    dword ptr [rcx+2Ch], 400h
0x14003b3eb  jz      short loc_14003B402
0x14003b3ed  mov     rcx, [rcx+18h]
0x14003b3f1  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003b3f8  mov     edx, 2Dh ; '-'
0x14003b3fd  call    WPP_SF_
0x14003b402  xor     r9d, r9d
0x14003b405  xor     r8d, r8d
0x14003b408  movzx   edx, r15w
0x14003b40c  mov     rcx, rdi
0x14003b40f  call    MRxSmbPopulateFileInfoInOE
0x14003b414  mov     eax, [rdi+1F8h]
0x14003b41a  mov     r9d, 0BADDh
0x14003b420  mov     [r14+20h], eax
0x14003b424  mov     r8d, 1
0x14003b42a  mov     rax, [rdi+1D8h]
0x14003b431  mov     rcx, rbp; RxContext
0x14003b434  mov     [r14], rax
0x14003b437  mov     rax, [rdi+1E0h]
0x14003b43e  mov     [r14+8], rax
0x14003b442  mov     rax, [rdi+1E8h]
0x14003b449  mov     [r14+10h], rax
0x14003b44d  mov     rax, [rdi+1F0h]
0x14003b454  mov     [r14+18h], rax
0x14003b458  mov     eax, [rdi+210h]
0x14003b45e  mov     [r14+38h], eax
0x14003b462  mov     rax, [rdi+200h]
0x14003b469  mov     [r14+28h], rax
0x14003b46d  mov     rax, [rdi+208h]
0x14003b474  mov     [r14+30h], rax
0x14003b478  mov     byte ptr [r14+3Dh], 1
0x14003b47d  bts     dword ptr [rsi+48h], 14h
0x14003b482  mov     eax, [rdi+34h]
0x14003b485  mov     [rsp+78h+var_40], r14; __int64
0x14003b48a  mov     [rsp+78h+var_48], 2; int
0x14003b492  mov     [rsp+78h+var_50], 0; char
0x14003b497  mov     [rsp+78h+var_58], eax; int
0x14003b49b  call    MRxSmbCreateFileSuccessTail
0x14003b4a0  test    eax, eax
0x14003b4a2  jnz     short loc_14003B4B3
0x14003b4a4  cmp     qword ptr [rbx+10h], 0
0x14003b4a9  jnz     short loc_14003B4B3
0x14003b4ab  mov     rcx, rbp
0x14003b4ae  call    MRxSmbConstructDeferredOpenContext
0x14003b4b3  add     rsp, 48h
0x14003b4b7  pop     r15
0x14003b4b9  pop     r14
0x14003b4bb  pop     rdi
0x14003b4bc  pop     rsi
0x14003b4bd  pop     rbp
0x14003b4be  pop     rbx
0x14003b4bf  retn
```
