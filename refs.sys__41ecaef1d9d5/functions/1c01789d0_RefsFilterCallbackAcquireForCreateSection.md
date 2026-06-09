# RefsFilterCallbackAcquireForCreateSection

- ea: `0x1c01789d0`
- end: `0x1c0178c69`
- name: `RefsFilterCallbackAcquireForCreateSection`
- size: `665`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1c00032fc`
- `0x1c000440c`
- `0x1c000f770`
- `0x1c0061878`
- `0x1c0068168`
- `0x1c01789d0`
- `0x1c01cdfdc`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c0178b28`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0178b28`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0178ac0`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0178ac0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0178ae2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0178ae2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0178b34`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0178b34`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c0178b6a`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c0178b6a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0178b48`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0178b7d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0178b48`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0178b7d`
- `ntoskrnl!FsRtlCheckOplockForFsFilterCallback` at `0x1c0178bae`
- `ntoskrnl!FsRtlCheckOplockForFsFilterCallback` at `0x1c0178bae`

## pseudocode

```c
__int64 __fastcall RefsFilterCallbackAcquireForCreateSection(__int64 a1)
{
  __int64 v1; // rbp
  NTSTATUS v3; // edi
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  char v12; // di
  struct _ERESOURCE *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  BOOL v16; // eax
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+30h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = 294;
  v4 = *(_QWORD *)(v1 + 32);
  v5 = *(_QWORD *)(v1 + 24);
  if ( v4 && (*(_DWORD *)(v4 + 4) & 0x2000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3ed46e530f373c033bff7a073690258d_Traceguids, 3221225895LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741401);
    return 3221225895LL;
  }
  if ( *(_QWORD *)(v5 + 16) )
  {
    if ( !(unsigned __int8)MsIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)(v5 + 120) + 104LL)) )
    {
      v7 = *(_QWORD *)(v5 + 128);
      if ( (*(_DWORD *)(v7 + 472) & 1) != 0 )
        RefsCleanCheckpoint();
    }
    LOBYTE(v8) = 1;
    RefsAcquirePagingResourceExclusive(v7, v5, v8);
    if ( *(_DWORD *)(a1 + 24) == 1 )
    {
      LOBYTE(v10) = 1;
      RefsAcquireResourceExclusive(v9, v5, v10);
      ExAcquireFastMutex(*(PFAST_MUTEX *)(v5 + 48));
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 156));
      *(_BYTE *)(v5 + 4) |= 0x20u;
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 156));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(v5 + 48));
      v11 = *(_DWORD *)(v5 + 304);
      if ( (v11 & 8) != 0 )
      {
        v12 = 0;
        *(_DWORD *)(v5 + 304) = v11 & 0xFFFFFFF7;
        IoStatus = 0;
        if ( *(_WORD *)v5 == 2050 )
          v13 = (struct _ERESOURCE *)(*(_QWORD *)(v5 + 96) + 64LL);
        else
          v13 = *(struct _ERESOURCE **)(v5 + 8);
        ExReleaseResourceLite(v13);
        if ( !IoGetTopLevelIrp() )
        {
          IoSetTopLevelIrp((PIRP)1);
          v12 = 1;
        }
        CcCoherencyFlushAndPurgeCache(*(PSECTION_OBJECT_POINTERS *)(v1 + 40), 0, 0, &IoStatus, 0);
        if ( v12 )
          IoSetTopLevelIrp(0);
        LOBYTE(v15) = 1;
        RefsAcquireResourceExclusive(v14, v5, v15);
      }
      *(_QWORD *)(v5 + 312) = KeGetCurrentThread();
      v3 = FsRtlCheckOplockForFsFilterCallback(v5 + 88, a1, 0);
      if ( v3 >= 0 )
      {
        v3 = (*(_DWORD *)(v5 + 180) != 0) + 298;
        if ( (*(_DWORD *)(a1 + 28) & 0x44) != 0 )
          _InterlockedOr((volatile signed __int32 *)(v5 + 136), 0x40000u);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    if ( v3 < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
LABEL_34:
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_3ed46e530f373c033bff7a073690258d_Traceguids,
          (unsigned int)v3);
        goto LABEL_35;
      }
      v16 = 0;
    }
    else
    {
      v16 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    }
    if ( v16 )
      goto LABEL_34;
  }
LABEL_35:
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1c01789d0  mov     [rsp+arg_0], rbx
0x1c01789d5  mov     [rsp+arg_8], rbp
0x1c01789da  mov     [rsp+arg_10], rsi
0x1c01789df  push    rdi
0x1c01789e0  sub     rsp, 40h
0x1c01789e4  mov     rbp, [rcx+10h]
0x1c01789e8  mov     rsi, rcx
0x1c01789eb  mov     edi, 126h
0x1c01789f0  mov     rax, [rbp+20h]
0x1c01789f4  mov     rbx, [rbp+18h]
0x1c01789f8  test    rax, rax
0x1c01789fb  jz      short loc_1C0178A6A
0x1c01789fd  mov     eax, [rax+4]
0x1c0178a00  bt      eax, 0Dh
0x1c0178a04  jnb     short loc_1C0178A6A
0x1c0178a06  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0178a0d  lea     rax, WPP_GLOBAL_Control
0x1c0178a14  mov     ebx, 0C00001A7h
0x1c0178a19  cmp     rcx, rax
0x1c0178a1c  jz      short loc_1C0178A45
0x1c0178a1e  test    dword ptr [rcx+2Ch], 100h
0x1c0178a25  jz      short loc_1C0178A45
0x1c0178a27  cmp     byte ptr [rcx+29h], 4
0x1c0178a2b  jb      short loc_1C0178A45
0x1c0178a2d  mov     rcx, [rcx+18h]
0x1c0178a31  lea     r8, WPP_3ed46e530f373c033bff7a073690258d_Traceguids
0x1c0178a38  mov     edx, 12h
0x1c0178a3d  mov     r9d, ebx
0x1c0178a40  call    WPP_SF_D
0x1c0178a45  mov     al, cs:RefsStatusDebugEnabled
0x1c0178a4b  test    al, al
0x1c0178a4d  jz      short loc_1C0178A63
0x1c0178a4f  mov     r8d, 0B32h
0x1c0178a55  lea     rdx, aResrcsupC; "ResrcSup.c"
0x1c0178a5c  mov     ecx, ebx; Status
0x1c0178a5e  call    RefsStatusDebug
0x1c0178a63  mov     eax, ebx
0x1c0178a65  jmp     loc_1C0178C53
0x1c0178a6a  cmp     qword ptr [rbx+10h], 0
0x1c0178a6f  jz      loc_1C0178BE4
0x1c0178a75  mov     rcx, [rbx+78h]
0x1c0178a79  mov     rcx, [rcx+68h]
0x1c0178a7d  call    MsIsFastResourceHeldExclusive
0x1c0178a82  test    al, al
0x1c0178a84  jnz     short loc_1C0178A9C
0x1c0178a86  mov     rcx, [rbx+80h]
0x1c0178a8d  mov     eax, [rcx+1D8h]
0x1c0178a93  test    al, 1
0x1c0178a95  jz      short loc_1C0178A9C
0x1c0178a97  call    RefsCleanCheckpoint
0x1c0178a9c  mov     r8b, 1
0x1c0178a9f  mov     rdx, rbx
0x1c0178aa2  call    RefsAcquirePagingResourceExclusive
0x1c0178aa7  cmp     dword ptr [rsi+18h], 1
0x1c0178aab  jnz     loc_1C0178BE4
0x1c0178ab1  mov     r8b, 1
0x1c0178ab4  mov     rdx, rbx
0x1c0178ab7  call    RefsAcquireResourceExclusive
0x1c0178abc  mov     rcx, [rbx+30h]; FastMutex
0x1c0178ac0  call    cs:__imp_ExAcquireFastMutex
0x1c0178ac7  nop     dword ptr [rax+rax+00h]
0x1c0178acc  lock inc dword ptr [rbx+9Ch]
0x1c0178ad3  or      byte ptr [rbx+4], 20h
0x1c0178ad7  lock inc dword ptr [rbx+9Ch]
0x1c0178ade  mov     rcx, [rbx+30h]; FastMutex
0x1c0178ae2  call    cs:__imp_ExReleaseFastMutex
0x1c0178ae9  nop     dword ptr [rax+rax+00h]
0x1c0178aee  mov     eax, [rbx+130h]
0x1c0178af4  test    al, 8
0x1c0178af6  jz      loc_1C0178B94
0x1c0178afc  and     eax, 0FFFFFFF7h
0x1c0178aff  xor     dil, dil
0x1c0178b02  mov     [rbx+130h], eax
0x1c0178b08  xorps   xmm0, xmm0
0x1c0178b0b  mov     eax, 802h
0x1c0178b10  movups  xmmword ptr [rsp+48h+IoStatus], xmm0
0x1c0178b15  cmp     ax, [rbx]
0x1c0178b18  jnz     short loc_1C0178B24
0x1c0178b1a  mov     rcx, [rbx+60h]
0x1c0178b1e  add     rcx, 40h ; '@'
0x1c0178b22  jmp     short loc_1C0178B28
0x1c0178b24  mov     rcx, [rbx+8]; Resource
0x1c0178b28  call    cs:__imp_ExReleaseResourceLite
0x1c0178b2f  nop     dword ptr [rax+rax+00h]
0x1c0178b34  call    cs:__imp_IoGetTopLevelIrp
0x1c0178b3b  nop     dword ptr [rax+rax+00h]
0x1c0178b40  test    rax, rax
0x1c0178b43  jnz     short loc_1C0178B57
0x1c0178b45  lea     ecx, [rax+1]; Irp
0x1c0178b48  call    cs:__imp_IoSetTopLevelIrp
0x1c0178b4f  nop     dword ptr [rax+rax+00h]
0x1c0178b54  mov     dil, 1
0x1c0178b57  mov     rcx, [rbp+28h]; SectionObjectPointer
0x1c0178b5b  lea     r9, [rsp+48h+IoStatus]; IoStatus
0x1c0178b60  and     [rsp+48h+var_28], 0
0x1c0178b65  xor     r8d, r8d; Length
0x1c0178b68  xor     edx, edx; FileOffset
0x1c0178b6a  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x1c0178b71  nop     dword ptr [rax+rax+00h]
0x1c0178b76  test    dil, dil
0x1c0178b79  jz      short loc_1C0178B89
0x1c0178b7b  xor     ecx, ecx; Irp
0x1c0178b7d  call    cs:__imp_IoSetTopLevelIrp
0x1c0178b84  nop     dword ptr [rax+rax+00h]
0x1c0178b89  mov     r8b, 1
0x1c0178b8c  mov     rdx, rbx
0x1c0178b8f  call    RefsAcquireResourceExclusive
0x1c0178b94  mov     rax, gs:188h
0x1c0178b9d  lea     rcx, [rbx+58h]
0x1c0178ba1  xor     r8d, r8d
0x1c0178ba4  mov     [rbx+138h], rax
0x1c0178bab  mov     rdx, rsi
0x1c0178bae  call    cs:__imp_FsRtlCheckOplockForFsFilterCallback
0x1c0178bb5  nop     dword ptr [rax+rax+00h]
0x1c0178bba  mov     edi, eax
0x1c0178bbc  test    eax, eax
0x1c0178bbe  js      short loc_1C0178BE4
0x1c0178bc0  mov     eax, [rbx+0B4h]
0x1c0178bc6  neg     eax
0x1c0178bc8  mov     eax, [rsi+1Ch]
0x1c0178bcb  sbb     edi, edi
0x1c0178bcd  neg     edi
0x1c0178bcf  add     edi, 12Ah
0x1c0178bd5  test    al, 44h
0x1c0178bd7  jz      short loc_1C0178BE4
0x1c0178bd9  lock or dword ptr [rbx+88h], 40000h
0x1c0178be4  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0178beb  lea     rax, WPP_GLOBAL_Control
0x1c0178bf2  cmp     rcx, rax
0x1c0178bf5  jz      short loc_1C0178C33
0x1c0178bf7  test    dword ptr [rcx+2Ch], 100h
0x1c0178bfe  jz      short loc_1C0178C33
0x1c0178c00  test    edi, edi
0x1c0178c02  js      short loc_1C0178C0F
0x1c0178c04  xor     eax, eax
0x1c0178c06  cmp     byte ptr [rcx+29h], 5
0x1c0178c0a  setnb   al
0x1c0178c0d  jmp     short loc_1C0178C17
0x1c0178c0f  cmp     byte ptr [rcx+29h], 4
0x1c0178c13  jnb     short loc_1C0178C1B
0x1c0178c15  xor     eax, eax
0x1c0178c17  test    eax, eax
0x1c0178c19  jz      short loc_1C0178C33
0x1c0178c1b  mov     rcx, [rcx+18h]
0x1c0178c1f  lea     r8, WPP_3ed46e530f373c033bff7a073690258d_Traceguids
0x1c0178c26  mov     edx, 13h
0x1c0178c2b  mov     r9d, edi
0x1c0178c2e  call    WPP_SF_D
0x1c0178c33  mov     al, cs:RefsStatusDebugEnabled
0x1c0178c39  test    al, al
0x1c0178c3b  jz      short loc_1C0178C51
0x1c0178c3d  mov     r8d, 0BD9h
0x1c0178c43  lea     rdx, aResrcsupC; "ResrcSup.c"
0x1c0178c4a  mov     ecx, edi; Status
0x1c0178c4c  call    RefsStatusDebug
0x1c0178c51  mov     eax, edi
0x1c0178c53  mov     rbx, [rsp+48h+arg_0]
0x1c0178c58  mov     rbp, [rsp+48h+arg_8]
0x1c0178c5d  mov     rsi, [rsp+48h+arg_10]
0x1c0178c62  add     rsp, 40h
0x1c0178c66  pop     rdi
0x1c0178c67  retn
```
