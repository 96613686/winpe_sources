# SmbCeCompleteVNetRootContextInitialization

- ea: `0x140042d00`
- end: `0x140042e5d`
- name: `SmbCeCompleteVNetRootContextInitialization`
- size: `349`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000fee0`
- `0x14004eb70`
- `0x14004f920`

## callees

- `0x140002470`
- `0x140003e20`
- `0x140009e40`
- `0x14000ca70`
- `0x14000e52c`
- `0x140042d00`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140042dff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140042dff`
- `ntoskrnl!ExReleaseResourceLite` at `0x140042df3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140042df3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042d72`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042d72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140042d57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140042d57`

## string_xrefs

- `0x140042e1c`: `SmbCeCompleteVNetRootContextInitialization`
- `0x140042e38`: `SmbCeCompleteVNetRootContextInitialization`

## pseudocode

```c
__int64 __fastcall SmbCeCompleteVNetRootContextInitialization(char *P)
{
  __int32 v2; // edi
  __int128 *v3; // rcx
  unsigned int v4; // esi
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_24d58658a6f53a50f897506d3fab0df4_Traceguids,
      P,
      *((_QWORD *)P + 4));
  KeEnterCriticalRegion();
  v2 = 1;
  ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
  v3 = (__int128 *)(P + 48);
  *((_QWORD *)P + 5) = 0;
  if ( *(__int128 **)v3 == v3 )
  {
    *((_QWORD *)&v6 + 1) = &v6;
    *(_QWORD *)&v6 = &v6;
  }
  else
  {
    v6 = *v3;
    *(_QWORD *)(v6 + 8) = &v6;
    **((_QWORD **)&v6 + 1) = &v6;
    *((_QWORD *)P + 7) = P + 48;
    *(_QWORD *)v3 = v3;
  }
  if ( *((_DWORD *)P + 3) )
  {
    v4 = -1073741504;
    _InterlockedExchange((volatile __int32 *)P + 3, 1);
  }
  else
  {
    v4 = 0;
    v2 = 0;
  }
  _InterlockedExchange((volatile __int32 *)(*((_QWORD *)P + 13) + 12LL), v2);
  ExReleaseResourceLite(&s_SmbCeDbResource);
  KeLeaveCriticalRegion();
  SmbCeResumeOutstandingRequests(&v6, v4);
  MRxSmbTrackDerefCount(P, "SmbCeCompleteVNetRootContextInitialization", 426);
  SmbReferenceRecord(P + 136, "SmbCeCompleteVNetRootContextInitialization", 426);
  return SmbCepDereferenceVNetRootContext(P);
}

```

## disassembly

```asm
0x140042d00  mov     [rsp+arg_0], rbx
0x140042d05  mov     [rsp+arg_8], rsi
0x140042d0a  push    rdi
0x140042d0b  sub     rsp, 40h
0x140042d0f  xorps   xmm0, xmm0
0x140042d12  mov     rbx, rcx
0x140042d15  movups  [rsp+48h+var_18], xmm0
0x140042d1a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140042d21  lea     rax, WPP_GLOBAL_Control
0x140042d28  cmp     rcx, rax
0x140042d2b  jz      short loc_140042D57
0x140042d2d  test    dword ptr [rcx+2Ch], 400h
0x140042d34  jz      short loc_140042D57
0x140042d36  mov     rax, [rbx+20h]
0x140042d3a  lea     r8, WPP_24d58658a6f53a50f897506d3fab0df4_Traceguids
0x140042d41  mov     rcx, [rcx+18h]
0x140042d45  mov     edx, 0Eh
0x140042d4a  mov     r9, rbx
0x140042d4d  mov     [rsp+48h+var_28], rax
0x140042d52  call    WPP_SF_qq
0x140042d57  call    cs:__imp_KeEnterCriticalRegion
0x140042d5e  nop     dword ptr [rax+rax+00h]
0x140042d63  mov     edi, 1
0x140042d68  lea     rcx, s_SmbCeDbResource; Resource
0x140042d6f  mov     dl, dil; Wait
0x140042d72  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140042d79  nop     dword ptr [rax+rax+00h]
0x140042d7e  lea     rcx, [rbx+30h]
0x140042d82  mov     qword ptr [rbx+28h], 0
0x140042d8a  cmp     [rcx], rcx
0x140042d8d  jnz     short loc_140042DA5
0x140042d8f  lea     rax, [rsp+48h+var_18]
0x140042d94  mov     qword ptr [rsp+48h+var_18+8], rax
0x140042d99  lea     rax, [rsp+48h+var_18]
0x140042d9e  mov     qword ptr [rsp+48h+var_18], rax
0x140042da3  jmp     short loc_140042DCF
0x140042da5  movups  xmm0, xmmword ptr [rcx]
0x140042da8  lea     rdx, [rsp+48h+var_18]
0x140042dad  movups  [rsp+48h+var_18], xmm0
0x140042db2  movq    rax, xmm0
0x140042db7  mov     [rax+8], rdx
0x140042dbb  lea     rdx, [rsp+48h+var_18]
0x140042dc0  mov     rax, qword ptr [rsp+48h+var_18+8]
0x140042dc5  mov     [rax], rdx
0x140042dc8  mov     [rcx+8], rcx
0x140042dcc  mov     [rcx], rcx
0x140042dcf  cmp     dword ptr [rbx+0Ch], 0
0x140042dd3  jnz     short loc_140042DDB
0x140042dd5  xor     esi, esi
0x140042dd7  xor     edi, edi
0x140042dd9  jmp     short loc_140042DE5
0x140042ddb  mov     eax, edi
0x140042ddd  mov     esi, 0C0000140h
0x140042de2  xchg    eax, [rbx+0Ch]
0x140042de5  mov     rax, [rbx+68h]
0x140042de9  lea     rcx, s_SmbCeDbResource; Resource
0x140042df0  xchg    edi, [rax+0Ch]
0x140042df3  call    cs:__imp_ExReleaseResourceLite
0x140042dfa  nop     dword ptr [rax+rax+00h]
0x140042dff  call    cs:__imp_KeLeaveCriticalRegion
0x140042e06  nop     dword ptr [rax+rax+00h]
0x140042e0b  mov     edx, esi
0x140042e0d  lea     rcx, [rsp+48h+var_18]
0x140042e12  call    SmbCeResumeOutstandingRequests
0x140042e17  mov     edi, 1AAh
0x140042e1c  lea     rdx, aSmbcecompletev; "SmbCeCompleteVNetRootContextInitializat"...
0x140042e23  mov     r8d, edi
0x140042e26  mov     rcx, rbx
0x140042e29  call    MRxSmbTrackDerefCount
0x140042e2e  lea     rcx, [rbx+88h]
0x140042e35  mov     r8d, edi
0x140042e38  lea     rdx, aSmbcecompletev; "SmbCeCompleteVNetRootContextInitializat"...
0x140042e3f  call    SmbReferenceRecord
0x140042e44  mov     rcx, rbx; P
0x140042e47  call    SmbCepDereferenceVNetRootContext
0x140042e4c  mov     rbx, [rsp+48h+arg_0]
0x140042e51  mov     rsi, [rsp+48h+arg_8]
0x140042e56  add     rsp, 40h
0x140042e5a  pop     rdi
0x140042e5b  retn
```
