# AcquireResidentSystemAddress_0

- ea: `0x140103b88`
- end: `0x140103eab`
- name: `AcquireResidentSystemAddress_0`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140103b70`

## callees

- `0x140004268`
- `0x1400c115c`
- `0x1400cede8`
- `0x140103b88`
- `0x140103eb4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140103e53`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140103e53`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140103ce5`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140103ce5`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140103c32`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140103c32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140103d79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140103d79`
- `watchdog!WdLogSingleEntry5` at `0x140103e95`
- `watchdog!WdLogSingleEntry5` at `0x140103e95`
- `watchdog!WdLogSingleEntry0` at `0x140103d38`
- `watchdog!WdLogSingleEntry0` at `0x140103df1`
- `watchdog!WdLogSingleEntry0` at `0x140103d38`
- `watchdog!WdLogSingleEntry0` at `0x140103df1`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140103e6d`

## string_xrefs

- `0x140103d49`: `Failed to create system space mapping for MDL`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
PVOID __fastcall AcquireResidentSystemAddress_0(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // r11
  int v7; // eax
  unsigned __int64 v8; // rdx
  PVOID result; // rax
  unsigned __int64 v10; // r8
  const struct _MDL *v11; // rcx
  __int64 v12; // r9
  int v13; // eax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdi
  _QWORD *v16; // r11
  __int64 v17; // r9
  unsigned int v18; // r8d
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // r8d
  __int64 v22; // r9
  unsigned int v23; // r8d
  struct _MDL **v24; // r9
  struct _MDL *v25; // rax
  int v26; // ecx
  int v27; // r8d
  __int64 v28; // rcx
  __int64 v29; // [rsp+88h] [rbp+10h] BYREF

  v3 = *((_QWORD *)a2 + 17);
  v7 = *(_DWORD *)(v3 + 64);
  if ( (v7 & 0x1000) != 0 )
    return *(PVOID *)(*(_QWORD *)a2 + 224LL);
  if ( (v7 & 0x2000) != 0 )
  {
    v8 = *((_QWORD *)a2 + 18);
    v29 = 0;
    if ( *(_BYTE *)(a3 + 16) )
      return VIDMM_MEMORY_SEGMENT::GetAddressForPageTableInCpuHostAperture((VIDMM_MEMORY_SEGMENT *)v3, v8, a2[4]);
    if ( (int)AcquireResidentSystemAddressInCpuHostAperture(
                (struct VIDMM_PHYSICAL_ALLOC *)a2,
                v8,
                *(VIDMM_CPU_HOST_APERTURE **)(v3 + 512),
                a3,
                (__int64)&v29) >= 0 )
      return (PVOID)v29;
    return 0;
  }
  if ( (v7 & 4) == 0 )
  {
    v28 = *(_QWORD *)a2;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 73, a1, v28, v3);
    WdLogGlobalForLineNumber = 227;
    JUMPOUT(0x140103EABLL);
  }
  v10 = *((_QWORD *)a2 + 18);
  v11 = *(const struct _MDL **)(v3 + 32);
  v12 = (__int64)v11 + v10;
  v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL) + 444LL);
  if ( *(_BYTE *)(a3 + 16) )
  {
    v14 = *((_QWORD *)a2 + 2);
    v15 = v14 >> 12;
    v16 = (_QWORD *)(*(_QWORD *)(a1 + 2504) + 48LL);
    if ( (v13 & 8) != 0 )
    {
      v22 = (v10 >> 12) + 6;
      v23 = 0;
      v24 = &v11->Next + v22;
      if ( v15 )
      {
        do
        {
          ++v23;
          *v16 = *v24++;
          v14 = *((_QWORD *)a2 + 2);
          ++v16;
        }
        while ( v23 < v14 >> 12 );
      }
    }
    else
    {
      v17 = v12 >> 12;
      v18 = 0;
      if ( v15 )
      {
        do
        {
          ++v18;
          *v16 = v17++;
          v14 = *((_QWORD *)a2 + 2);
          ++v16;
        }
        while ( v18 < v14 >> 12 );
      }
    }
    v19 = *(_QWORD *)(a1 + 2504);
    *(_DWORD *)(v19 + 40) = v14;
    *(_WORD *)(v19 + 8) = 8 * (((v14 + 4095) >> 12) + 6);
    *(_QWORD *)v19 = 0;
    *(_WORD *)(v19 + 10) = 0;
    *(_QWORD *)(v19 + 32) = 0;
    *(_DWORD *)(v19 + 44) = 0;
    *(_WORD *)(*(_QWORD *)(a1 + 2504) + 10LL) |= 0x802u;
    return MmMapLockedPagesWithReservedMapping(
             *(PVOID *)(a1 + 2496),
             0x6D4D6956u,
             *(PMDL *)(a1 + 2504),
             MmWriteCombined);
  }
  else
  {
    if ( (v13 & 8) == 0 )
      return (PVOID)MmMapIoSpaceEx(v12, *((_QWORD *)a2 + 2), 1028);
    v25 = VidMmiBuildMdlFromMdl(*((_QWORD *)a2 + 2), v11, v10 >> 12);
    *(_QWORD *)a3 = v25;
    if ( !v25 )
    {
      _InterlockedIncrement(&dword_140087774);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1377;
      DxgkLogInternalTriageEvent(
        v26,
        262145,
        v27,
        (unsigned int)L"Failed to build SoftGPU MDL system address",
        1377,
        0,
        0,
        0);
      return 0;
    }
    v25->MdlFlags |= 0x802u;
    result = MmMapLockedPagesSpecifyCache(*(PMDL *)a3, 0, MmCached, 0, 0, 0x40000010u);
    if ( !result )
    {
      _InterlockedIncrement(&dword_1400878A8);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1400;
      DxgkLogInternalTriageEvent(
        v20,
        262145,
        v21,
        (unsigned int)L"Failed to create system space mapping for MDL",
        1400,
        0,
        0,
        0);
      ExFreePoolWithTag(*(PVOID *)a3, 0);
      *(_QWORD *)a3 = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140103b88  push    rbx
0x140103b8a  push    rbp
0x140103b8b  push    rsi
0x140103b8c  push    rdi
0x140103b8d  sub     rsp, 58h
0x140103b91  mov     r11, [rdx+88h]
0x140103b98  mov     rdi, r8
0x140103b9b  mov     r10, rdx
0x140103b9e  mov     rsi, rcx
0x140103ba1  mov     eax, [r11+40h]
0x140103ba5  bt      eax, 0Ch
0x140103ba9  jb      short loc_140103BE2
0x140103bab  bt      eax, 0Dh
0x140103baf  jnb     short loc_140103BEE
0x140103bb1  mov     rdx, [rdx+90h]; unsigned __int64
0x140103bb8  xor     ebx, ebx
0x140103bba  mov     [rsp+78h+arg_8], rbx
0x140103bc2  cmp     [r8+10h], bl
0x140103bc6  jz      loc_140103CF6
0x140103bcc  mov     r8d, [r10+10h]; unsigned int
0x140103bd0  mov     rcx, r11; this
0x140103bd3  call    ?GetAddressForPageTableInCpuHostAperture@VIDMM_MEMORY_SEGMENT@@QEAAPEAX_KI@Z; VIDMM_MEMORY_SEGMENT::GetAddressForPageTableInCpuHostAperture(unsigned __int64,uint)
0x140103bd8  add     rsp, 58h
0x140103bdc  pop     rdi
0x140103bdd  pop     rsi
0x140103bde  pop     rbp
0x140103bdf  pop     rbx
0x140103be0  retn
0x140103be2  mov     rax, [rdx]
0x140103be5  mov     rax, [rax+0E0h]
0x140103bec  jmp     short loc_140103BD8
0x140103bee  test    al, 4
0x140103bf0  jz      loc_140103E6D
0x140103bf6  mov     rax, [rsi+38h]
0x140103bfa  xor     ebx, ebx
0x140103bfc  mov     r8, [rdx+90h]
0x140103c03  mov     rcx, [r11+20h]
0x140103c07  mov     rbp, [rax+18h]
0x140103c0b  lea     r9, [rcx+r8]
0x140103c0f  mov     eax, [rbp+1BCh]
0x140103c15  cmp     [rdi+10h], bl
0x140103c18  jnz     short loc_140103C40
0x140103c1a  mov     r11, [rdx+10h]
0x140103c1e  test    al, 8
0x140103c20  jnz     loc_140103DD0
0x140103c26  mov     r8d, 404h
0x140103c2c  mov     rdx, r11
0x140103c2f  mov     rcx, r9
0x140103c32  call    cs:__imp_MmMapIoSpaceEx
0x140103c39  nop     dword ptr [rax+rax+00h]
0x140103c3e  jmp     short loc_140103BD8
0x140103c40  mov     rdx, [rdx+10h]
0x140103c44  mov     r11, [rsi+9C8h]
0x140103c4b  mov     rdi, rdx
0x140103c4e  shr     rdi, 0Ch
0x140103c52  add     r11, 30h ; '0'
0x140103c56  test    al, 8
0x140103c58  jnz     loc_140103D8F
0x140103c5e  sar     r9, 0Ch
0x140103c62  mov     r8d, ebx
0x140103c65  test    rdi, rdi
0x140103c68  jz      short loc_140103C8D
0x140103c6a  mov     rax, r9
0x140103c6d  inc     r8d
0x140103c70  mov     [r11], rax
0x140103c73  inc     r9
0x140103c76  mov     rdx, [r10+10h]
0x140103c7a  lea     r11, [r11+8]
0x140103c7e  mov     rcx, rdx
0x140103c81  mov     eax, r8d
0x140103c84  shr     rcx, 0Ch
0x140103c88  cmp     rax, rcx
0x140103c8b  jb      short loc_140103C6A
0x140103c8d  mov     rcx, [rsi+9C8h]
0x140103c94  lea     rax, [rdx+0FFFh]
0x140103c9b  shr     rax, 0Ch
0x140103c9f  mov     r9d, 2; CacheType
0x140103ca5  add     ax, 6
0x140103ca9  shl     ax, 3
0x140103cad  mov     [rcx+28h], edx
0x140103cb0  mov     edx, 6D4D6956h; PoolTag
0x140103cb5  mov     [rcx+8], ax
0x140103cb9  mov     [rcx], rbx
0x140103cbc  mov     [rcx+0Ah], bx
0x140103cc0  mov     [rcx+20h], rbx
0x140103cc4  mov     [rcx+2Ch], ebx
0x140103cc7  mov     ecx, 802h
0x140103ccc  mov     rax, [rsi+9C8h]
0x140103cd3  or      [rax+0Ah], cx
0x140103cd7  mov     r8, [rsi+9C8h]; MemoryDescriptorList
0x140103cde  mov     rcx, [rsi+9C0h]; MappingAddress
0x140103ce5  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140103cec  nop     dword ptr [rax+rax+00h]
0x140103cf1  jmp     loc_140103BD8
0x140103cf6  lea     rax, [rsp+78h+arg_8]
0x140103cfe  mov     rcx, r10; struct VIDMM_PHYSICAL_ALLOC *
0x140103d01  lea     r9, [r8+8]
0x140103d05  mov     qword ptr [rsp+78h+Priority], rax; __int64
0x140103d0a  mov     r8, [r11+200h]; this
0x140103d11  mov     qword ptr [rsp+78h+BugCheckOnFailure], rdi; __int64
0x140103d16  call    AcquireResidentSystemAddressInCpuHostAperture
0x140103d1b  test    eax, eax
0x140103d1d  js      short loc_140103D88
0x140103d1f  mov     rax, [rsp+78h+arg_8]
0x140103d27  jmp     loc_140103BD8
0x140103d2c  lock inc cs:dword_1400878A8
0x140103d33  mov     ecx, 6
0x140103d38  call    cs:__imp_WdLogSingleEntry0
0x140103d3f  nop     dword ptr [rax+rax+00h]
0x140103d44  mov     [rsp+78h+var_40], rbx
0x140103d49  lea     r9, aFailedToCreate_0; "Failed to create system space mapping f"...
0x140103d50  mov     eax, 578h
0x140103d55  mov     [rsp+78h+var_48], rbx
0x140103d5a  mov     qword ptr [rsp+78h+Priority], rbx
0x140103d5f  mov     edx, 40001h
0x140103d64  mov     cs:WdLogGlobalForLineNumber, eax
0x140103d6a  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x140103d6f  call    DxgkLogInternalTriageEvent
0x140103d74  mov     rcx, [rdi]; P
0x140103d77  xor     edx, edx; Tag
0x140103d79  call    cs:__imp_ExFreePoolWithTag
0x140103d80  nop     dword ptr [rax+rax+00h]
0x140103d85  mov     [rdi], rbx
0x140103d88  xor     eax, eax
0x140103d8a  jmp     loc_140103BD8
0x140103d8f  shr     r8, 0Ch
0x140103d93  lea     r9, [r8+6]
0x140103d97  mov     r8d, ebx
0x140103d9a  lea     r9, [rcx+r9*8]
0x140103d9e  test    rdi, rdi
0x140103da1  jz      loc_140103C8D
0x140103da7  mov     rax, [r9]
0x140103daa  inc     r8d
0x140103dad  mov     [r11], rax
0x140103db0  lea     r9, [r9+8]
0x140103db4  mov     rdx, [r10+10h]
0x140103db8  lea     r11, [r11+8]
0x140103dbc  mov     rcx, rdx
0x140103dbf  mov     eax, r8d
0x140103dc2  shr     rcx, 0Ch
0x140103dc6  cmp     rax, rcx
0x140103dc9  jb      short loc_140103DA7
0x140103dcb  jmp     loc_140103C8D
0x140103dd0  mov     rdx, rcx; struct _MDL *
0x140103dd3  shr     r8, 0Ch; unsigned __int64
0x140103dd7  mov     rcx, r11; Length
0x140103dda  call    ?VidMmiBuildMdlFromMdl@@YAPEAU_MDL@@_KPEBU1@0@Z; VidMmiBuildMdlFromMdl(unsigned __int64,_MDL const *,unsigned __int64)
0x140103ddf  mov     [rdi], rax
0x140103de2  test    rax, rax
0x140103de5  jnz     short loc_140103E32
0x140103de7  lock inc cs:dword_140087774
0x140103dee  lea     ecx, [rax+6]
0x140103df1  call    cs:__imp_WdLogSingleEntry0
0x140103df8  nop     dword ptr [rax+rax+00h]
0x140103dfd  mov     [rsp+78h+var_40], rbx
0x140103e02  lea     r9, aFailedToBuildS; "Failed to build SoftGPU MDL system addr"...
0x140103e09  mov     eax, 561h
0x140103e0e  mov     [rsp+78h+var_48], rbx
0x140103e13  mov     qword ptr [rsp+78h+Priority], rbx
0x140103e18  mov     edx, 40001h
0x140103e1d  mov     cs:WdLogGlobalForLineNumber, eax
0x140103e23  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax
0x140103e28  call    DxgkLogInternalTriageEvent
0x140103e2d  jmp     loc_140103D88
0x140103e32  xor     r9d, r9d; RequestedAddress
0x140103e35  mov     [rsp+78h+Priority], 40000010h; Priority
0x140103e3d  mov     ecx, 802h
0x140103e42  mov     [rsp+78h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x140103e46  or      [rax+0Ah], cx
0x140103e4a  xor     edx, edx; AccessMode
0x140103e4c  mov     rcx, [rdi]; MemoryDescriptorList
0x140103e4f  lea     r8d, [r9+1]; CacheType
0x140103e53  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140103e5a  nop     dword ptr [rax+rax+00h]
0x140103e5f  test    rax, rax
0x140103e62  jnz     loc_140103BD8
0x140103e68  jmp     loc_140103D2C
0x140103e6d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140103e74  mov     rcx, [rdx]
0x140103e77  mov     dword ptr [rax], 1
0x140103e7d  mov     qword ptr [rsp+78h+Priority], r11
0x140103e82  mov     r9, rsi
0x140103e85  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx
0x140103e8a  mov     edx, 10Eh
0x140103e8f  xor     ecx, ecx
0x140103e91  lea     r8d, [rcx+49h]
0x140103e95  call    cs:__imp_WdLogSingleEntry5
0x140103e9c  nop     dword ptr [rax+rax+00h]
0x140103ea1  mov     cs:WdLogGlobalForLineNumber, 0E3h
```
