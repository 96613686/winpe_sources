# RefsSendBeginDismountEvent(_IRP_CONTEXT *,_VCB *,_REFS_ACTIVITY_ID *,_REFS_DISMOUNT_REASON)

- ea: `0x14028ed0c`
- end: `0x14028f175`
- name: `?RefsSendBeginDismountEvent@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_REFS_ACTIVITY_ID@@W4_REFS_DISMOUNT_REASON@@@Z`
- size: `1129`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400aeae0`
- `0x14028ec68`
- `0x1402b1d38`
- `0x1402b75e0`
- `0x1402c70f4`
- `0x1402cc560`
- `0x140319010`

## callees

- `0x1400ac03c`
- `0x1400f662c`
- `0x1400f7ddc`
- `0x140119294`
- `0x1401f3fb0`
- `0x1401f4400`
- `0x14028ed0c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14028f13d`
- `ntoskrnl!ObfDereferenceObject` at `0x140345054`
- `ntoskrnl!ObfDereferenceObject` at `0x14028f13d`
- `ntoskrnl!ObfDereferenceObject` at `0x140345054`
- `ntoskrnl!IoGetActivityIdThread` at `0x14028edd6`
- `ntoskrnl!IoGetActivityIdThread` at `0x14028edd6`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14028ee38`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14028ee38`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14028eda4`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14028eda4`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14028ee20`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14028ee20`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14028f0ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14028f0ef`

## pseudocode

```c
LONG_PTR __fastcall RefsSendBeginDismountEvent(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  const CHAR *v7; // rbx
  LONG_PTR result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  _OWORD *ActivityIdThread; // rax
  _OWORD *v12; // rax
  _OWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  const char *const near *v17; // rdi
  int v18; // esi
  int v19; // ebx
  char DeveloperVolumeState; // al
  int v21; // r9d
  int v22; // edx
  int v23; // ecx
  PEPROCESS Process; // [rsp+E0h] [rbp-588h] BYREF
  const CHAR *ProcessImageFileName; // [rsp+E8h] [rbp-580h]
  const CHAR *v26; // [rsp+F0h] [rbp-578h]
  __int128 v27; // [rsp+F8h] [rbp-570h]
  __int128 v28; // [rsp+118h] [rbp-550h]
  __int64 DirtyPagesAccumulator; // [rsp+128h] [rbp-540h]
  _QWORD *v30; // [rsp+130h] [rbp-538h]
  _QWORD v31[76]; // [rsp+140h] [rbp-528h] BYREF
  _BYTE v32[608]; // [rsp+3A0h] [rbp-2C8h] BYREF
  _QWORD v33[3]; // [rsp+600h] [rbp-68h] BYREF

  v4 = a4;
  memset(v33, 0, sizeof(v33));
  Process = 0;
  v7 = &File;
  ProcessImageFileName = &File;
  memset(v31, 0, sizeof(v31));
  v27 = 0;
  v28 = 0;
  DirtyPagesAccumulator = 0;
  result = *(unsigned int *)(a2 + 24);
  if ( (result & 1) != 0 )
  {
    *(_QWORD *)&v27 = KeQueryUnbiasedInterruptTime();
    v30 = v33;
    if ( a1 && (ActivityIdThread = *(_OWORD **)(a1 + 80)) != 0
      || (ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v10, v9)) != 0 )
    {
      *(_OWORD *)&v33[1] = *ActivityIdThread;
      v33[0] = &v33[1];
    }
    else
    {
      v33[0] = 0;
    }
    if ( PsLookupProcessByProcessId(*(HANDLE *)(a1 + 704), &Process) >= 0 )
      ProcessImageFileName = (const CHAR *)PsGetProcessImageFileName(Process);
    if ( (int)MsGetPerfCountersStatistics(*(_QWORD *)(a2 + 112), 0, v31) < 0 )
    {
      memset(v32, 0, sizeof(v32));
      v12 = v31;
      v13 = v32;
      v14 = 4;
      do
      {
        *v12 = *v13;
        v12[1] = v13[1];
        v12[2] = v13[2];
        v12[3] = v13[3];
        v12[4] = v13[4];
        v12[5] = v13[5];
        v12[6] = v13[6];
        v12[7] = v13[7];
        v12 += 8;
        v13 += 8;
        --v14;
      }
      while ( v14 );
      *v12 = *v13;
      v12[1] = v13[1];
      v12[2] = v13[2];
      v12[3] = v13[3];
      v12[4] = v13[4];
      v12[5] = v13[5];
    }
    *(_QWORD *)&v28 = v31[61];
    DWORD2(v28) = v31[62];
    DirtyPagesAccumulator = MsGetDirtyPagesAccumulator(*(_QWORD *)(a2 + 112));
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      v17 = (&RefsDismountReasonMapping)[v4];
      v18 = *(_DWORD *)(a1 + 704);
      if ( *(_QWORD *)(a2 + 10240) )
        v7 = *(const CHAR **)(a2 + 10240);
      v26 = v7;
      v19 = *(_DWORD *)(a2 + 6288);
      DeveloperVolumeState = RefsGetDeveloperVolumeState(a2, v15, v16);
      v22 = v19 - 1;
      v23 = 0;
      if ( (unsigned int)(v19 - 1) > 0x13 )
        LOBYTE(v19) = 0;
      LOBYTE(v23) = (v21 & 0x1000) != 0;
      McTemplateK0jmzuuhtqzzzzzqjqtjsqssid_EtwWriteTransfer(
        v23,
        v22,
        v33[0],
        a2 + 6064,
        a2 + 6704,
        *(_QWORD *)(a2 + 6160),
        *(_BYTE *)(a2 + 792),
        *(_BYTE *)(a2 + 793),
        *(_WORD *)(a2 + 6728),
        v23,
        DeveloperVolumeState,
        *(_QWORD *)(a2 + 824),
        *(_QWORD *)(a2 + 6304),
        *(_QWORD *)(a2 + 6320),
        *(_QWORD *)(a2 + 6336),
        *(_QWORD *)(a2 + 6352),
        v19,
        a2 + 6376,
        *(_DWORD *)(a2 + 6372),
        (v21 & 0x20000000) != 0,
        a2 + 13080,
        (__int64)v26,
        v18,
        (__int64)ProcessImageFileName,
        (__int64)v17,
        v31[61],
        v31[62]);
    }
    result = *(_QWORD *)(a1 + 712);
    if ( result
      || (result = (LONG_PTR)ExAllocatePoolWithTag(PoolType, 0x38u, 0x66466552u), (*(_QWORD *)(a1 + 712) = result) != 0) )
    {
      *(_OWORD *)result = v27;
      *(_OWORD *)(result + 16) = 0;
      *(_OWORD *)(result + 32) = v28;
      *(_QWORD *)(result + 48) = DirtyPagesAccumulator;
    }
  }
  if ( Process )
    return ObfDereferenceObject(Process);
  return result;
}

```

## disassembly

```asm
0x14028ed0c  mov     r11, rsp
0x14028ed0f  push    rbx
0x14028ed10  push    rsi
0x14028ed11  push    rdi
0x14028ed12  push    r12
0x14028ed14  push    r13
0x14028ed16  push    r14
0x14028ed18  push    r15
0x14028ed1a  sub     rsp, 630h
0x14028ed21  movaps  xmmword ptr [r11-48h], xmm6
0x14028ed26  mov     rax, cs:__security_cookie
0x14028ed2d  xor     rax, rsp
0x14028ed30  mov     [rsp+668h+var_50], rax
0x14028ed38  movsxd  rdi, r9d
0x14028ed3b  mov     r12, rdx
0x14028ed3e  mov     r13, rcx
0x14028ed41  xorps   xmm0, xmm0
0x14028ed44  xor     eax, eax
0x14028ed46  movups  xmmword ptr [r11-68h], xmm0
0x14028ed4b  mov     [r11-58h], rax
0x14028ed4f  mov     [r11-588h], rax
0x14028ed56  lea     rbx, File
0x14028ed5d  mov     [r11-580h], rbx
0x14028ed64  mov     esi, 260h
0x14028ed69  mov     r8d, esi; Size
0x14028ed6c  xor     edx, edx; Val
0x14028ed6e  lea     rcx, [r11-528h]; void *
0x14028ed75  call    memset
0x14028ed7a  xorps   xmm6, xmm6
0x14028ed7d  xor     eax, eax
0x14028ed7f  movups  [rsp+668h+var_570], xmm6
0x14028ed87  movups  [rsp+668h+var_550], xmm6
0x14028ed8f  mov     [rsp+668h+var_540], rax
0x14028ed97  mov     eax, [r12+18h]
0x14028ed9c  test    al, 1
0x14028ed9e  jz      loc_14028F130
0x14028eda4  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14028edab  nop     dword ptr [rax+rax+00h]
0x14028edb0  mov     qword ptr [rsp+668h+var_570], rax
0x14028edb8  lea     rax, [rsp+668h+var_68]
0x14028edc0  mov     [rsp+668h+var_538], rax
0x14028edc8  test    r13, r13
0x14028edcb  jz      short loc_14028EDD6
0x14028edcd  mov     rax, [r13+50h]
0x14028edd1  test    rax, rax
0x14028edd4  jnz     short loc_14028EDE7
0x14028edd6  call    cs:__imp_IoGetActivityIdThread
0x14028eddd  nop     dword ptr [rax+rax+00h]
0x14028ede2  test    rax, rax
0x14028ede5  jz      short loc_14028EE05
0x14028ede7  movups  xmm0, xmmword ptr [rax]
0x14028edea  movdqu  [rsp+668h+var_60], xmm0
0x14028edf3  lea     rax, [rsp+668h+var_60]
0x14028edfb  mov     [rsp+668h+var_68], rax
0x14028ee03  jmp     short loc_14028EE11
0x14028ee05  mov     [rsp+668h+var_68], 0
0x14028ee11  lea     rdx, [rsp+668h+Process]; Process
0x14028ee19  mov     rcx, [r13+2C0h]; ProcessId
0x14028ee20  call    cs:__imp_PsLookupProcessByProcessId
0x14028ee27  nop     dword ptr [rax+rax+00h]
0x14028ee2c  test    eax, eax
0x14028ee2e  js      short loc_14028EE4C
0x14028ee30  mov     rcx, [rsp+668h+Process]
0x14028ee38  call    cs:__imp_PsGetProcessImageFileName
0x14028ee3f  nop     dword ptr [rax+rax+00h]
0x14028ee44  mov     [rsp+668h+var_580], rax
0x14028ee4c  lea     r8, [rsp+668h+var_528]
0x14028ee54  xor     edx, edx
0x14028ee56  mov     rcx, [r12+70h]
0x14028ee5b  call    MsGetPerfCountersStatistics
0x14028ee60  test    eax, eax
0x14028ee62  jns     loc_14028EF0B
0x14028ee68  mov     r8, rsi; Size
0x14028ee6b  xor     edx, edx; Val
0x14028ee6d  lea     rcx, [rsp+668h+var_2C8]; void *
0x14028ee75  call    memset
0x14028ee7a  lea     rax, [rsp+668h+var_528]
0x14028ee82  lea     rcx, [rsp+668h+var_2C8]
0x14028ee8a  mov     edx, 4
0x14028ee8f  lea     r8d, [rdx+7Ch]
0x14028ee93  movups  xmm0, xmmword ptr [rcx]
0x14028ee96  movups  xmmword ptr [rax], xmm0
0x14028ee99  movups  xmm1, xmmword ptr [rcx+10h]
0x14028ee9d  movups  xmmword ptr [rax+10h], xmm1
0x14028eea1  movups  xmm0, xmmword ptr [rcx+20h]
0x14028eea5  movups  xmmword ptr [rax+20h], xmm0
0x14028eea9  movups  xmm1, xmmword ptr [rcx+30h]
0x14028eead  movups  xmmword ptr [rax+30h], xmm1
0x14028eeb1  movups  xmm0, xmmword ptr [rcx+40h]
0x14028eeb5  movups  xmmword ptr [rax+40h], xmm0
0x14028eeb9  movups  xmm1, xmmword ptr [rcx+50h]
0x14028eebd  movups  xmmword ptr [rax+50h], xmm1
0x14028eec1  movups  xmm0, xmmword ptr [rcx+60h]
0x14028eec5  movups  xmmword ptr [rax+60h], xmm0
0x14028eec9  movups  xmm1, xmmword ptr [rcx+70h]
0x14028eecd  movups  xmmword ptr [rax+70h], xmm1
0x14028eed1  add     rax, r8
0x14028eed4  add     rcx, r8
0x14028eed7  sub     rdx, 1
0x14028eedb  jnz     short loc_14028EE93
0x14028eedd  movups  xmm0, xmmword ptr [rcx]
0x14028eee0  movups  xmmword ptr [rax], xmm0
0x14028eee3  movups  xmm1, xmmword ptr [rcx+10h]
0x14028eee7  movups  xmmword ptr [rax+10h], xmm1
0x14028eeeb  movups  xmm0, xmmword ptr [rcx+20h]
0x14028eeef  movups  xmmword ptr [rax+20h], xmm0
0x14028eef3  movups  xmm1, xmmword ptr [rcx+30h]
0x14028eef7  movups  xmmword ptr [rax+30h], xmm1
0x14028eefb  movups  xmm0, xmmword ptr [rcx+40h]
0x14028eeff  movups  xmmword ptr [rax+40h], xmm0
0x14028ef03  movups  xmm1, xmmword ptr [rcx+50h]
0x14028ef07  movups  xmmword ptr [rax+50h], xmm1
0x14028ef0b  mov     rax, [rsp+668h+var_340]
0x14028ef13  mov     qword ptr [rsp+668h+var_550], rax
0x14028ef1b  mov     eax, [rsp+668h+var_338]
0x14028ef22  mov     dword ptr [rsp+668h+var_550+8], eax
0x14028ef29  mov     rcx, [r12+70h]
0x14028ef2e  call    MsGetDirtyPagesAccumulator
0x14028ef33  mov     [rsp+668h+var_540], rax
0x14028ef3b  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, 4
0x14028ef42  jz      loc_14028F0D4
0x14028ef48  mov     rax, rdi
0x14028ef4b  lea     rdi, ?RefsDismountReasonMapping@@3QBQEBDB; char const * const near * const RefsDismountReasonMapping
0x14028ef52  mov     rdi, [rdi+rax*8]
0x14028ef56  mov     esi, [r13+2C0h]
0x14028ef5d  lea     r15, [r12+1A30h]
0x14028ef65  mov     rax, [r15+0DD0h]
0x14028ef6c  test    rax, rax
0x14028ef6f  cmovnz  rbx, rax
0x14028ef73  mov     [rsp+668h+var_578], rbx
0x14028ef7b  mov     r9d, [r12+1Ch]
0x14028ef80  mov     ebx, [r12+1890h]
0x14028ef88  mov     rcx, r12
0x14028ef8b  call    ?RefsGetDeveloperVolumeState@@YA?AW4REFS_DEV_VOL_STATE@@PEAU_VCB@@@Z; RefsGetDeveloperVolumeState(_VCB *)
0x14028ef90  mov     r14d, eax
0x14028ef93  lea     r8, [r12+3318h]
0x14028ef9b  xor     r10d, r10d
0x14028ef9e  bt      r9d, 1Dh
0x14028efa3  setb    r10b
0x14028efa7  lea     r11, [r12+18E8h]
0x14028efaf  lea     edx, [rbx-1]
0x14028efb2  xor     ecx, ecx
0x14028efb4  cmp     edx, 13h
0x14028efb7  cmova   ebx, ecx
0x14028efba  bt      r9d, 0Ch
0x14028efbf  setb    cl
0x14028efc2  lea     r9, [r12+17B0h]
0x14028efca  mov     eax, [rsp+668h+var_338]
0x14028efd1  mov     [rsp+668h+var_598], eax
0x14028efd8  mov     rax, [rsp+668h+var_340]
0x14028efe0  mov     [rsp+668h+var_5A0], rax
0x14028efe8  mov     [rsp+668h+var_5A8], rdi
0x14028eff0  mov     rax, [rsp+668h+var_580]
0x14028eff8  mov     [rsp+668h+var_5B0], rax
0x14028f000  mov     [rsp+668h+var_5B8], esi
0x14028f007  mov     rax, [rsp+668h+var_578]
0x14028f00f  mov     [rsp+668h+var_5C0], rax
0x14028f017  mov     [rsp+668h+var_5C8], r8
0x14028f01f  mov     [rsp+668h+var_5D0], r10d
0x14028f027  mov     eax, [r12+18E4h]
0x14028f02f  mov     [rsp+668h+var_5D8], eax
0x14028f036  mov     [rsp+668h+var_5E0], r11
0x14028f03e  mov     [rsp+668h+var_5E8], ebx
0x14028f045  mov     rax, [r12+18D0h]
0x14028f04d  mov     [rsp+668h+var_5F0], rax
0x14028f052  mov     rax, [r12+18C0h]
0x14028f05a  mov     [rsp+668h+var_5F8], rax
0x14028f05f  mov     rax, [r12+18B0h]
0x14028f067  mov     [rsp+668h+var_600], rax
0x14028f06c  mov     rax, [r12+18A0h]
0x14028f074  mov     [rsp+668h+var_608], rax
0x14028f079  mov     rax, [r12+338h]
0x14028f081  mov     [rsp+668h+var_610], rax
0x14028f086  mov     [rsp+668h+var_618], r14d
0x14028f08b  mov     [rsp+668h+var_620], ecx
0x14028f08f  movzx   eax, word ptr [r12+1A48h]
0x14028f098  mov     [rsp+668h+var_628], ax
0x14028f09d  mov     al, [r12+319h]
0x14028f0a5  mov     [rsp+668h+var_630], al
0x14028f0a9  mov     al, [r12+318h]
0x14028f0b1  mov     [rsp+668h+var_638], al
0x14028f0b5  mov     rax, [r12+1810h]
0x14028f0bd  mov     [rsp+668h+var_640], rax
0x14028f0c2  mov     [rsp+668h+var_648], r15
0x14028f0c7  mov     r8, [rsp+668h+var_68]
0x14028f0cf  call    McTemplateK0jmzuuhtqzzzzzqjqtjsqssid_EtwWriteTransfer
0x14028f0d4  mov     rax, [r13+2C8h]
0x14028f0db  test    rax, rax
0x14028f0de  jnz     short loc_14028F107
0x14028f0e0  mov     ecx, cs:PoolType; PoolType
0x14028f0e6  lea     edx, [rax+38h]; NumberOfBytes
0x14028f0e9  mov     r8d, 66466552h; Tag
0x14028f0ef  call    cs:__imp_ExAllocatePoolWithTag
0x14028f0f6  nop     dword ptr [rax+rax+00h]
0x14028f0fb  mov     [r13+2C8h], rax
0x14028f102  test    rax, rax
0x14028f105  jz      short loc_14028F130
0x14028f107  movups  xmm0, [rsp+668h+var_570]
0x14028f10f  movups  xmmword ptr [rax], xmm0
0x14028f112  movups  xmmword ptr [rax+10h], xmm6
0x14028f116  movups  xmm0, [rsp+668h+var_550]
0x14028f11e  movups  xmmword ptr [rax+20h], xmm0
0x14028f122  movsd   xmm1, [rsp+668h+var_540]
0x14028f12b  movsd   qword ptr [rax+30h], xmm1
0x14028f130  mov     rcx, [rsp+668h+Process]; Object
0x14028f138  test    rcx, rcx
0x14028f13b  jz      short loc_14028F149
0x14028f13d  call    cs:__imp_ObfDereferenceObject
0x14028f144  nop     dword ptr [rax+rax+00h]
0x14028f149  mov     rcx, [rsp+668h+var_50]
0x14028f151  xor     rcx, rsp; StackCookie
0x14028f154  call    __security_check_cookie
0x14028f159  movaps  xmm6, [rsp+668h+var_48]
0x14028f161  add     rsp, 630h
0x14028f168  pop     r15
0x14028f16a  pop     r14
0x14028f16c  pop     r13
0x14028f16e  pop     r12
0x14028f170  pop     rdi
0x14028f171  pop     rsi
0x14028f172  pop     rbx
0x14028f173  retn
0x14034503c  push    rbp
0x14034503e  sub     rsp, 0E0h
0x140345045  mov     rbp, rdx
0x140345048  mov     rcx, [rbp+0E0h]; Object
0x14034504f  test    rcx, rcx
0x140345052  jz      short loc_140345061
0x140345054  call    cs:__imp_ObfDereferenceObject
0x14034505b  nop     dword ptr [rax+rax+00h]
0x140345060  nop
0x140345061  add     rsp, 0E0h
0x140345068  pop     rbp
0x140345069  retn
```
