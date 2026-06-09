# FltpFindFrameForFilter

- ea: `0x1800524c0`
- end: `0x18005263a`
- name: `FltpFindFrameForFilter`
- size: `378`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004c810`

## callees

- `0x180009f20`
- `0x18004c008`
- `0x18004dd30`
- `0x180052114`
- `0x1800524c0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800525d7`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800525d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800524e3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800524e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800525b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800525b1`
- `ntoskrnl!ExReleaseFastResource` at `0x1800525a5`
- `ntoskrnl!ExReleaseFastResource` at `0x1800525a5`
- `ntoskrnl!RtlCompareAltitudes` at `0x180052527`
- `ntoskrnl!RtlCompareAltitudes` at `0x18005253c`
- `ntoskrnl!RtlCompareAltitudes` at `0x180052527`
- `ntoskrnl!RtlCompareAltitudes` at `0x18005253c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1800524fb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1800524fb`

## pseudocode

```c
__int64 __fastcall FltpFindFrameForFilter(__int64 a1, UNICODE_STRING *a2)
{
  __int64 v2; // rdi
  __int64 v5; // r8
  __int64 *v6; // rsi
  __int64 *i; // rbp
  __int64 *v8; // r14
  LONG v9; // ebx
  LONG v10; // eax
  unsigned int v11; // eax
  LARGE_INTEGER Interval; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(v2) = 0;
  Interval.QuadPart = 0;
  while ( 2 )
  {
    KeEnterCriticalRegion();
    LOBYTE(v5) = 1;
    ExAcquireFastResourceExclusive(qword_18003E798, 0, v5);
LABEL_3:
    v6 = (__int64 *)qword_18003E808;
    for ( i = 0; ; i = v8 )
    {
      if ( v6 == &qword_18003E800 )
      {
        v11 = FltpAdjustFrameAltitudesForLegacyFilter();
        LODWORD(v2) = v11;
        if ( v11 == -1073741267 )
          goto LABEL_11;
        if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 915, 0) < 0 )
        {
          LODWORD(v2) = FltpAttachFrame(a2, a1 + 56);
          goto LABEL_11;
        }
        goto LABEL_3;
      }
      v8 = v6 - 1;
      v9 = RtlCompareAltitudes(a2, (PCUNICODE_STRING)(v6 + 3));
      v10 = RtlCompareAltitudes(a2, (PCUNICODE_STRING)(v6 + 5));
      if ( v9 < 0 )
        break;
      if ( v10 <= 0 )
      {
        *(_QWORD *)(a1 + 56) = v8;
        goto LABEL_11;
      }
      v6 = (__int64 *)v6[1];
    }
    v2 = (unsigned int)FltpCopyUnicodeString((__int64)(i + 6), (const void **)a2);
    if ( (int)FltpDbgStatus(v2, "minkernel\\fs\\filtermgr\\filter\\framesup.c", 872, 0) >= 0 )
      *(_QWORD *)(a1 + 56) = i;
LABEL_11:
    ExReleaseFastResource(qword_18003E798, 0);
    KeLeaveCriticalRegion();
    if ( (_DWORD)v2 == -1073741267 )
    {
      Interval.QuadPart = -20000;
      KeDelayExecutionThread(0, 0, &Interval);
      continue;
    }
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x1800524c0  mov     [rsp+arg_0], rbx
0x1800524c5  mov     [rsp+arg_8], rbp
0x1800524ca  push    rsi
0x1800524cb  push    rdi
0x1800524cc  push    r12
0x1800524ce  push    r14
0x1800524d0  push    r15
0x1800524d2  sub     rsp, 20h
0x1800524d6  xor     edi, edi
0x1800524d8  mov     r12, rdx
0x1800524db  mov     qword ptr [rsp+48h+Interval], rdi
0x1800524e0  mov     r15, rcx
0x1800524e3  call    cs:__imp_KeEnterCriticalRegion
0x1800524ea  nop     dword ptr [rax+rax+00h]
0x1800524ef  mov     r8b, 1
0x1800524f2  lea     rcx, qword_18003E798
0x1800524f9  xor     edx, edx
0x1800524fb  call    cs:__imp_ExAcquireFastResourceExclusive
0x180052502  nop     dword ptr [rax+rax+00h]
0x180052507  mov     rsi, cs:qword_18003E808
0x18005250e  xor     ebp, ebp
0x180052510  lea     rax, qword_18003E800
0x180052517  cmp     rsi, rax
0x18005251a  jz      short loc_180052561
0x18005251c  lea     r14, [rsi-8]
0x180052520  mov     rcx, r12; Altitude1
0x180052523  lea     rdx, [r14+20h]; Altitude2
0x180052527  call    cs:__imp_RtlCompareAltitudes
0x18005252e  nop     dword ptr [rax+rax+00h]
0x180052533  lea     rdx, [r14+30h]; Altitude2
0x180052537  mov     rcx, r12; Altitude1
0x18005253a  mov     ebx, eax
0x18005253c  call    cs:__imp_RtlCompareAltitudes
0x180052543  nop     dword ptr [rax+rax+00h]
0x180052548  test    ebx, ebx
0x18005254a  js      loc_1800525EE
0x180052550  test    eax, eax
0x180052552  jle     loc_1800525E8
0x180052558  mov     rsi, [rsi+8]
0x18005255c  mov     rbp, r14
0x18005255f  jmp     short loc_180052510
0x180052561  call    FltpAdjustFrameAltitudesForLegacyFilter
0x180052566  mov     edi, eax
0x180052568  cmp     eax, 0C000022Dh
0x18005256d  jz      short loc_18005259C
0x18005256f  mov     r8d, 393h
0x180052575  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x18005257c  xor     r9d, r9d
0x18005257f  mov     ecx, eax
0x180052581  call    FltpDbgStatus
0x180052586  test    eax, eax
0x180052588  jns     loc_180052507
0x18005258e  lea     rdx, [r15+38h]
0x180052592  mov     rcx, r12
0x180052595  call    FltpAttachFrame
0x18005259a  mov     edi, eax
0x18005259c  xor     edx, edx
0x18005259e  lea     rcx, qword_18003E798
0x1800525a5  call    cs:__imp_ExReleaseFastResource
0x1800525ac  nop     dword ptr [rax+rax+00h]
0x1800525b1  call    cs:__imp_KeLeaveCriticalRegion
0x1800525b8  nop     dword ptr [rax+rax+00h]
0x1800525bd  cmp     edi, 0C000022Dh
0x1800525c3  jnz     short loc_180052620
0x1800525c5  lea     r8, [rsp+48h+Interval]; Interval
0x1800525ca  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFFFFB1E0h
0x1800525d3  xor     edx, edx; Alertable
0x1800525d5  xor     ecx, ecx; WaitMode
0x1800525d7  call    cs:__imp_KeDelayExecutionThread
0x1800525de  nop     dword ptr [rax+rax+00h]
0x1800525e3  jmp     loc_1800524E3
0x1800525e8  mov     [r15+38h], r14
0x1800525ec  jmp     short loc_18005259C
0x1800525ee  lea     rcx, [rbp+30h]
0x1800525f2  mov     rdx, r12
0x1800525f5  call    FltpCopyUnicodeString
0x1800525fa  mov     r8d, 368h
0x180052600  lea     rdx, aMinkernelFsFil_24; "minkernel\\fs\\filtermgr\\filter\\frame"...
0x180052607  xor     r9d, r9d
0x18005260a  mov     ecx, eax
0x18005260c  mov     edi, eax
0x18005260e  call    FltpDbgStatus
0x180052613  test    eax, eax
0x180052615  js      short loc_18005259C
0x180052617  mov     [r15+38h], rbp
0x18005261b  jmp     loc_18005259C
0x180052620  mov     rbx, [rsp+48h+arg_0]
0x180052625  mov     eax, edi
0x180052627  mov     rbp, [rsp+48h+arg_8]
0x18005262c  add     rsp, 20h
0x180052630  pop     r15
0x180052632  pop     r14
0x180052634  pop     r12
0x180052636  pop     rdi
0x180052637  pop     rsi
0x180052638  retn
```
