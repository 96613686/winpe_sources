# SspCleanup

- ea: `0x18004c494`
- end: `0x18004c54c`
- name: `SspCleanup`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020cf0`

## callees

- `0x180006c50`
- `0x18002ee7c`
- `0x18004c494`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18004c4b6`
- `ntdll!RtlDeleteResource` at `0x18004c4b6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004c4fa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004c4fa`

## pseudocode

```c
void SspCleanup()
{
  __int64 i; // rbx
  NTSTATUS v1; // eax

  for ( i = 0; (unsigned int)i < NtLmUserContextLockCount; i = (unsigned int)(i + 1) )
    RtlDeleteResource((PRTL_RESOURCE)&(&NtLmUserContextLock)[12 * i]);
  NtLmUserContextLockCount = 0;
  if ( NtLmProcessAppContainerSid )
  {
    NtLmFree(NtLmProcessAppContainerSid);
    NtLmProcessAppContainerSid = 0;
  }
  if ( hMsRc4AlgProvider )
  {
    v1 = BCryptCloseAlgorithmProvider(hMsRc4AlgProvider, 0);
    if ( v1 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
          (unsigned int)v1);
    }
    else
    {
      hMsRc4AlgProvider = 0;
    }
  }
}

```

## disassembly

```asm
0x18004c494  push    rbx
0x18004c496  sub     rsp, 20h
0x18004c49a  xor     ebx, ebx
0x18004c49c  cmp     cs:?NtLmUserContextLockCount@@3KA, ebx; ulong NtLmUserContextLockCount
0x18004c4a2  jbe     short loc_18004C4C6
0x18004c4a4  lea     rax, ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A; _RTL_RESOURCE near * NtLmUserContextLock
0x18004c4ab  lea     rcx, [rbx+rbx*2]
0x18004c4af  shl     rcx, 5
0x18004c4b3  add     rcx, rax; Resource
0x18004c4b6  call    cs:__imp_RtlDeleteResource
0x18004c4bc  inc     ebx
0x18004c4be  cmp     ebx, cs:?NtLmUserContextLockCount@@3KA; ulong NtLmUserContextLockCount
0x18004c4c4  jb      short loc_18004C4A4
0x18004c4c6  mov     rcx, cs:?NtLmProcessAppContainerSid@@3PEAXEA; void * NtLmProcessAppContainerSid
0x18004c4cd  mov     cs:?NtLmUserContextLockCount@@3KA, 0; ulong NtLmUserContextLockCount
0x18004c4d7  test    rcx, rcx
0x18004c4da  jz      short loc_18004C4EC
0x18004c4dc  call    NtLmFree
0x18004c4e1  mov     cs:?NtLmProcessAppContainerSid@@3PEAXEA, 0; void * NtLmProcessAppContainerSid
0x18004c4ec  mov     rcx, cs:?hMsRc4AlgProvider@@3PEAXEA; hAlgorithm
0x18004c4f3  test    rcx, rcx
0x18004c4f6  jz      short loc_18004C546
0x18004c4f8  xor     edx, edx; dwFlags
0x18004c4fa  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004c500  test    eax, eax
0x18004c502  js      short loc_18004C515
0x18004c504  mov     cs:?hMsRc4AlgProvider@@3PEAXEA, 0; void * hMsRc4AlgProvider
0x18004c50f  add     rsp, 20h
0x18004c513  pop     rbx
0x18004c514  retn
0x18004c515  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c51c  lea     rdx, WPP_GLOBAL_Control
0x18004c523  cmp     rcx, rdx
0x18004c526  jz      short loc_18004C546
0x18004c528  test    byte ptr [rcx+1Ch], 1
0x18004c52c  jz      short loc_18004C546
0x18004c52e  mov     rcx, [rcx+10h]
0x18004c532  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x18004c539  mov     edx, 14h
0x18004c53e  mov     r9d, eax
0x18004c541  call    WPP_SF_d
0x18004c546  add     rsp, 20h
0x18004c54a  pop     rbx
0x18004c54b  retn
```
