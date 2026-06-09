# MRxSmbPseudoOpenTailFromGFAResponse

- ea: `0x140049870`
- end: `0x1400499d3`
- name: `MRxSmbPseudoOpenTailFromGFAResponse`
- size: `355`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003a5f0`
- `0x140047fb0`
- `0x14004a4a4`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x140049870`
- `0x1400499e0`
- `0x14004a2f0`

## pseudocode

```c
__int64 __fastcall MRxSmbPseudoOpenTailFromGFAResponse(__int64 a1, __int64 a2)
{
  struct _RX_CONTEXT *v2; // rbp
  PMRX_SRV_OPEN pRelevantSrvOpen; // rsi
  __int64 v5; // r14
  __int64 result; // rax
  unsigned int v7; // ebx

  v2 = *(struct _RX_CONTEXT **)(a1 + 24);
  pRelevantSrvOpen = v2->pRelevantSrvOpen;
  if ( pRelevantSrvOpen )
    v5 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  else
    v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids);
  *(_DWORD *)(v5 + 72) = *(_DWORD *)(a1 + 504);
  *(_QWORD *)(v5 + 40) = *(_QWORD *)(a1 + 472);
  *(_QWORD *)(v5 + 48) = *(_QWORD *)(a1 + 480);
  *(_QWORD *)(v5 + 56) = *(_QWORD *)(a1 + 488);
  *(_QWORD *)(v5 + 64) = *(_QWORD *)(a1 + 496);
  *(_DWORD *)(v5 + 96) = *(_DWORD *)(a1 + 528);
  *(_QWORD *)(v5 + 80) = *(_QWORD *)(a1 + 512);
  *(_QWORD *)(v5 + 88) = *(_QWORD *)(a1 + 520);
  *(_BYTE *)(v5 + 101) = *(_DWORD *)(a1 + 552) == 1;
  LODWORD(pRelevantSrvOpen->Key) |= 0x100200u;
  result = MRxSmbCreateFileSuccessTail(
             v2,
             a2,
             *(unsigned int *)(a1 + 552),
             0xBADDu,
             *(_DWORD *)(a1 + 52),
             0,
             1u,
             v5 + 40);
  v7 = result;
  if ( (_DWORD)result )
    goto LABEL_7;
  if ( *(_QWORD *)(v5 + 16) )
  {
    LODWORD(pRelevantSrvOpen->Key) |= 0x100000u;
    return result;
  }
  result = MRxSmbConstructDeferredOpenContext((__int64)v2);
  v7 = result;
  if ( (_DWORD)result )
  {
LABEL_7:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, v7);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140049870  push    rbx
0x140049872  push    rbp
0x140049873  push    rsi
0x140049874  push    rdi
0x140049875  push    r14
0x140049877  push    r15
0x140049879  sub     rsp, 48h
0x14004987d  mov     rbp, [rcx+18h]
0x140049881  mov     rbx, rcx
0x140049884  mov     rsi, [rbp+48h]
0x140049888  test    rsi, rsi
0x14004988b  jz      loc_140049985
0x140049891  mov     r14, [rsi+30h]
0x140049895  lea     rdi, [r14+28h]
0x140049899  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400498a0  lea     r15, WPP_GLOBAL_Control
0x1400498a7  cmp     rcx, r15
0x1400498aa  jz      short loc_1400498B9
0x1400498ac  test    dword ptr [rcx+2Ch], 400h
0x1400498b3  jnz     loc_1400499A9
0x1400498b9  mov     eax, [rbx+1F8h]
0x1400498bf  mov     r9d, 0BADDh
0x1400498c5  mov     [rdi+20h], eax
0x1400498c8  mov     rcx, rbp; RxContext
0x1400498cb  mov     rax, [rbx+1D8h]
0x1400498d2  mov     [rdi], rax
0x1400498d5  mov     rax, [rbx+1E0h]
0x1400498dc  mov     [rdi+8], rax
0x1400498e0  mov     rax, [rbx+1E8h]
0x1400498e7  mov     [rdi+10h], rax
0x1400498eb  mov     rax, [rbx+1F0h]
0x1400498f2  mov     [rdi+18h], rax
0x1400498f6  mov     eax, [rbx+210h]
0x1400498fc  mov     [rdi+38h], eax
0x1400498ff  mov     rax, [rbx+200h]
0x140049906  mov     [rdi+28h], rax
0x14004990a  mov     rax, [rbx+208h]
0x140049911  mov     [rdi+30h], rax
0x140049915  cmp     dword ptr [rbx+228h], 1
0x14004991c  mov     [rsp+78h+var_40], rdi; __int64
0x140049921  setz    al
0x140049924  mov     [rsp+78h+var_48], 1; int
0x14004992c  mov     [rdi+3Dh], al
0x14004992f  or      dword ptr [rsi+48h], 100200h
0x140049936  mov     eax, [rbx+34h]
0x140049939  mov     r8d, [rbx+228h]
0x140049940  mov     [rsp+78h+var_50], 0; char
0x140049945  mov     [rsp+78h+var_58], eax; int
0x140049949  call    MRxSmbCreateFileSuccessTail
0x14004994e  mov     ebx, eax
0x140049950  test    eax, eax
0x140049952  jz      short loc_1400499C3
0x140049954  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004995b  cmp     rcx, r15
0x14004995e  jz      short loc_140049981
0x140049960  test    dword ptr [rcx+2Ch], 400h
0x140049967  jz      short loc_140049981
0x140049969  mov     rcx, [rcx+18h]
0x14004996d  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x140049974  mov     edx, 30h ; '0'
0x140049979  mov     r9d, ebx
0x14004997c  call    WPP_SF_d
0x140049981  mov     eax, ebx
0x140049983  jmp     short loc_14004999B
0x140049985  xor     r14d, r14d
0x140049988  jmp     loc_140049895
0x14004998d  mov     rcx, rbp
0x140049990  call    MRxSmbConstructDeferredOpenContext
0x140049995  mov     ebx, eax
0x140049997  test    eax, eax
0x140049999  jnz     short loc_140049954
0x14004999b  add     rsp, 48h
0x14004999f  pop     r15
0x1400499a1  pop     r14
0x1400499a3  pop     rdi
0x1400499a4  pop     rsi
0x1400499a5  pop     rbp
0x1400499a6  pop     rbx
0x1400499a7  retn
0x1400499a9  mov     rcx, [rcx+18h]
0x1400499ad  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x1400499b4  mov     edx, 2Fh ; '/'
0x1400499b9  call    WPP_SF_
0x1400499be  jmp     loc_1400498B9
0x1400499c3  cmp     qword ptr [r14+10h], 0
0x1400499c8  jz      short loc_14004998D
0x1400499ca  or      dword ptr [rsi+48h], 100000h
0x1400499d1  jmp     short loc_14004999B
```
