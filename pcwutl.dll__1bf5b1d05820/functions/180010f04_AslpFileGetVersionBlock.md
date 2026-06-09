# AslpFileGetVersionBlock

- ea: `0x180010f04`
- end: `0x180011632`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180010d10`

## callees

- `0x180002664`
- `0x1800027e2`
- `0x18000dcf4`
- `0x18000e240`
- `0x180010f04`
- `0x1800137d0`
- `0x180013814`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!VerSetConditionMask` at `0x1800110f6`
- `KERNEL32!VerSetConditionMask` at `0x180011105`
- `KERNEL32!VerSetConditionMask` at `0x1800110f6`
- `KERNEL32!VerSetConditionMask` at `0x180011105`
- `ntdll!ZwClose` at `0x1800115c9`
- `ntdll!ZwClose` at `0x180011607`
- `ntdll!ZwClose` at `0x1800115c9`
- `ntdll!ZwClose` at `0x180011607`
- `ntdll!LdrResSearchResource` at `0x180011077`
- `ntdll!LdrResSearchResource` at `0x1800111ea`
- `ntdll!LdrResSearchResource` at `0x180011077`
- `ntdll!LdrResSearchResource` at `0x1800111ea`
- `ntdll!RtlVerifyVersionInfo` at `0x180011118`
- `ntdll!RtlVerifyVersionInfo` at `0x180011118`
- `ntdll!ZwUnmapViewOfSection` at `0x1800115ea`
- `ntdll!ZwUnmapViewOfSection` at `0x1800115ea`
- `ntdll!RtlFreeHeap` at `0x1800115ac`
- `ntdll!RtlFreeHeap` at `0x1800115ac`
- `ntdll!RtlAllocateHeap` at `0x18001136e`
- `ntdll!RtlAllocateHeap` at `0x18001136e`

## string_xrefs

- `0x180011535`: `Version block has bad size (falls outside file)`
- `0x180011507`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlock(unsigned __int16 **a1, unsigned __int16 **a2, __int64 a3)
{
  unsigned __int16 *v5; // r12
  __int64 v6; // r8
  unsigned __int16 *v7; // rcx
  int v8; // ebx
  int v9; // eax
  char *v10; // rcx
  SIZE_T v11; // r12
  char *v12; // r13
  int v13; // eax
  ULONGLONG v14; // rax
  ULONGLONG v15; // rax
  void *v16; // rax
  int v17; // eax
  const wchar_t *v18; // rax
  char *v19; // rcx
  char *v20; // rdx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v22; // rbx
  const char *v23; // r9
  __int64 v24; // r8
  unsigned __int16 v25; // ax
  unsigned __int64 v26; // r9
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  unsigned __int16 *v29; // r8
  __int64 v31; // [rsp+20h] [rbp-228h]
  __int64 v32; // [rsp+20h] [rbp-228h]
  SIZE_T Size; // [rsp+48h] [rbp-200h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-1F8h] BYREF
  unsigned __int16 *v35; // [rsp+60h] [rbp-1E8h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-1E0h]
  SIZE_T v37; // [rsp+70h] [rbp-1D8h]
  unsigned __int16 **v38; // [rsp+78h] [rbp-1D0h]
  HANDLE Handle[2]; // [rsp+80h] [rbp-1C8h] BYREF
  PVOID BaseAddress[2]; // [rsp+90h] [rbp-1B8h]
  __int128 v41; // [rsp+A0h] [rbp-1A8h]
  unsigned __int16 **v42; // [rsp+B0h] [rbp-198h]
  __int64 v43; // [rsp+B8h] [rbp-190h]
  void *v44; // [rsp+C0h] [rbp-188h]
  SIZE_T v45; // [rsp+C8h] [rbp-180h]
  struct _OSVERSIONINFOEXW VersionInfo; // [rsp+D0h] [rbp-178h] BYREF
  _QWORD v47[3]; // [rsp+1F0h] [rbp-58h] BYREF

  v38 = a2;
  v42 = a1;
  v43 = a3;
  Src[0] = 0;
  v5 = 0;
  v35 = 0;
  Size = 0;
  *(_OWORD *)Handle = 0;
  *(_OWORD *)BaseAddress = 0;
  v41 = 0;
  v6 = *(_QWORD *)(a3 + 64);
  if ( !v6 )
  {
    v9 = AslFileMappingEnsure(a3, a2, 0, a2);
    v8 = v9;
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1527, "AslFileMappingEnsure failed [%x]", v9);
      goto LABEL_69;
    }
    if ( *(_DWORD *)(a3 + 56) != 6 )
    {
      v8 = -1073741687;
      goto LABEL_69;
    }
    v47[0] = 16;
    v47[1] = 1;
    v47[2] = 0;
    v10 = *(char **)(a3 + 32);
    if ( v10 )
    {
      v36 = *(unsigned __int16 **)(a3 + 32);
      v11 = *(_QWORD *)(a3 + 40);
      v37 = v11;
      v12 = v10;
    }
    else
    {
      v36 = 0;
      v11 = 0;
      v37 = 0;
      v12 = 0;
    }
    v13 = LdrResSearchResource(v10, v47, 3, *(_BYTE *)(a3 + 51) == 0 ? 0x200 : 0, Src, &Size, 0, 0);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( (unsigned int)(v13 + 1073741687) <= 2 )
      {
LABEL_68:
        v5 = 0;
        goto LABEL_69;
      }
      if ( v13 != -1073741701 || *(_BYTE *)(a3 + 51) || *(_DWORD *)(a3 + 76) )
      {
        AslLogCallPrintf(
          1,
          "AslpFileGetVersionBlock",
          1651,
          "LdrResFindResource failed %ls [%x]",
          *(const wchar_t **)a3,
          v13);
        goto LABEL_68;
      }
      memset_0(&VersionInfo, 0, sizeof(VersionInfo));
      VersionInfo.dwOSVersionInfoSize = 284;
      VersionInfo.dwMajorVersion = 6;
      VersionInfo.dwMinorVersion = 2;
      v14 = VerSetConditionMask(0, 2u, 3u);
      v15 = VerSetConditionMask(v14, 1u, 3u);
      if ( RtlVerifyVersionInfo(&VersionInfo, 3u, v15) < 0 )
      {
LABEL_18:
        v8 = -1073741687;
        goto LABEL_68;
      }
      v16 = *(void **)(a3 + 8);
      BYTE8(v41) = 0;
      Handle[0] = v16;
      v17 = RtlFileMapMapView((__int64)Handle, 1);
      v8 = v17;
      if ( v17 < 0 )
      {
        LODWORD(v31) = v17;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1618, "RtlFileMapMapView failed [%x]", v31);
        goto LABEL_68;
      }
      AslLogCallPrintf(
        3,
        "AslpFileGetVersionBlock",
        1627,
        "Re-mapped file as image to get version block: %ls",
        *(const wchar_t **)a3);
      v8 = LdrResSearchResource(BaseAddress[1], v47, 3, 0, Src, &Size, 0, 0);
      v18 = L"Found";
      if ( v8 < 0 )
        v18 = L"Did not find";
      AslLogCallPrintf(2, "AslpFileGetVersionBlock", 1640, "%ls version block after re-mapping as image [%x]", v18, v8);
      if ( v8 < 0 )
      {
        LODWORD(v32) = v8;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1643, "LdrResFindResource failed [%x]", v32);
        goto LABEL_68;
      }
      v12 = (char *)BaseAddress[1];
      v36 = (unsigned __int16 *)BaseAddress[1];
      v11 = v41;
      v37 = v41;
    }
    if ( !Src[0] )
    {
      AslLogCallPrintf(
        1,
        "AslpFileGetVersionBlock",
        1658,
        "LdrResFindResource returned null version block with status: [%x]",
        v8);
      goto LABEL_18;
    }
    if ( Size < 0x26 )
    {
      v8 = -1073741595;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1665, "Version block is too small to be valid");
      goto LABEL_68;
    }
    if ( Size > 0x8000 )
    {
      v8 = -1073741595;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1675, "Version block is too large to be valid");
      goto LABEL_68;
    }
    v44 = Src[0];
    v45 = Size;
    if ( Src[0] < v12
      || (v19 = (char *)Src[0] + Size, Src[0] > (char *)Src[0] + Size)
      || (v20 = &v12[v11], Src[0] > &v12[v11])
      || v19 < v12
      || v19 > v20
      || v12 > v20
      || Size > v11 )
    {
      v8 = -1073741687;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1686, "Version block has bad size (falls outside file)");
      goto LABEL_68;
    }
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    v22 = Heap;
    v5 = Heap;
    v35 = Heap;
    if ( Heap )
    {
      memmove_0(Heap, Src[0], Size);
      if ( (unsigned int)Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( Size < 0x5C || wcsicmp_0((const wchar_t *)Src[0] + 3, L"VS_VERSION_INFO") )
        {
          v8 = -1073741595;
          v23 = "Version block invalid";
          v24 = 1722;
          goto LABEL_42;
        }
      }
      else if ( Size < 0x26 || wcsicmp_0((const wchar_t *)Src[0] + 3, L"VS_VERSION_INFO") )
      {
        v8 = -1073741595;
        v23 = "Version block invalid";
        v24 = 1729;
        goto LABEL_42;
      }
      if ( *v22 >= 0x5Cu )
      {
        if ( Size >= *v22 )
        {
          v25 = *v22;
        }
        else
        {
          AslLogCallPrintf(
            3,
            "AslpFileGetVersionBlock",
            1752,
            "LdrResSearchResource returned a VersionBlockSize smaller than reflected in the actual block data.");
          *v22 = Size;
          v25 = Size;
        }
        v36 = v22;
        v26 = v25;
        v37 = v25;
        v27 = v22 + 20;
        v44 = v22 + 20;
        v45 = 52;
        if ( v22 + 20 < v22
          || (v28 = v22 + 46, v22 + 20 >= v22 + 46)
          || (v29 = (unsigned __int16 *)((char *)v22 + v26), v27 > (unsigned __int16 *)((char *)v22 + v26))
          || v28 < v22
          || v28 > v29
          || v22 > v29
          || v26 < 0x34 )
        {
          *v38 = 0;
          if ( v22[1] )
          {
            v8 = -1073741595;
            v23 = "Version block invalid (fixed info falls outside root)";
            v24 = 1776;
            goto LABEL_42;
          }
        }
        else
        {
          *v38 = v27;
        }
        *(_QWORD *)(a3 + 64) = v22;
        v35 = 0;
        *v42 = v22;
        v8 = 0;
        goto LABEL_68;
      }
      v8 = -1073741595;
      v23 = "Version block invalid (too small to contain data)";
      v24 = 1743;
    }
    else
    {
      v8 = -1073741801;
      v23 = "Out of memory";
      v24 = 1698;
    }
LABEL_42:
    AslLogCallPrintf(1, "AslpFileGetVersionBlock", v24, v23);
    goto LABEL_69;
  }
  v7 = 0;
  if ( *(_WORD *)(v6 + 2) >= 0x34u )
    v7 = (unsigned __int16 *)(v6 + 40);
  *a2 = v7;
  *a1 = *(unsigned __int16 **)(a3 + 64);
  v8 = 0;
LABEL_69:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( BYTE8(v41) && Handle[0] )
    ZwClose(Handle[0]);
  if ( BYTE10(v41) && BaseAddress[1] )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress[1]);
  if ( BYTE9(v41) && Handle[1] )
    ZwClose(Handle[1]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010f04  push    rbx
0x180010f06  push    rsi
0x180010f07  push    rdi
0x180010f08  push    r12
0x180010f0a  push    r13
0x180010f0c  push    r14
0x180010f0e  push    r15
0x180010f10  sub     rsp, 210h
0x180010f17  mov     rax, cs:__security_cookie
0x180010f1e  xor     rax, rsp
0x180010f21  mov     [rsp+248h+var_40], rax
0x180010f29  mov     r15, r8
0x180010f2c  mov     r9, rdx
0x180010f2f  mov     [rsp+248h+var_1D0], rdx
0x180010f34  mov     r10, rcx
0x180010f37  mov     [rsp+248h+var_198], rcx
0x180010f3f  mov     [rsp+248h+var_190], r8
0x180010f47  xor     edi, edi
0x180010f49  mov     [rsp+248h+Src], rdi
0x180010f4e  mov     r12d, edi
0x180010f51  mov     [rsp+248h+var_1E8], rdi
0x180010f56  mov     [rsp+248h+Size], rdi
0x180010f5b  xorps   xmm0, xmm0
0x180010f5e  movups  xmmword ptr [rsp+248h+Handle], xmm0
0x180010f66  movups  xmmword ptr [rsp+248h+BaseAddress], xmm0
0x180010f6e  movups  [rsp+248h+var_1A8], xmm0
0x180010f76  mov     r8, [r8+40h]
0x180010f7a  test    r8, r8
0x180010f7d  jz      short loc_180010FA2
0x180010f7f  lea     rax, [r8+28h]
0x180010f83  mov     ecx, edi
0x180010f85  lea     edx, [rdi+34h]
0x180010f88  cmp     [r8+2], dx
0x180010f8d  cmovnb  rcx, rax
0x180010f91  mov     [r9], rcx
0x180010f94  mov     rax, [r15+40h]
0x180010f98  mov     [r10], rax
0x180010f9b  mov     ebx, edi
0x180010f9d  jmp     loc_180011595
0x180010fa2  mov     rcx, r15
0x180010fa5  call    AslFileMappingEnsure
0x180010faa  mov     ebx, eax
0x180010fac  test    eax, eax
0x180010fae  jns     short loc_180010FD7
0x180010fb0  mov     dword ptr [rsp+248h+var_228], eax
0x180010fb4  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x180010fbb  mov     r8d, 5F7h
0x180010fc1  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180010fc8  mov     ecx, 1
0x180010fcd  call    AslLogCallPrintf
0x180010fd2  jmp     loc_180011595
0x180010fd7  cmp     dword ptr [r15+38h], 6
0x180010fdc  jz      short loc_180010FE8
0x180010fde  mov     ebx, 0C0000089h
0x180010fe3  jmp     loc_180011595
0x180010fe8  mov     [rsp+248h+var_58], 10h
0x180010ff4  mov     r14d, 1
0x180010ffa  mov     [rsp+248h+var_50], r14
0x180011002  mov     [rsp+248h+var_48], rdi
0x18001100a  mov     rcx, [r15+20h]
0x18001100e  test    rcx, rcx
0x180011011  jz      short loc_180011026
0x180011013  mov     [rsp+248h+var_1E0], rcx
0x180011018  mov     r12, [r15+28h]
0x18001101c  mov     [rsp+248h+var_1D8], r12
0x180011021  mov     r13, rcx
0x180011024  jmp     short loc_180011036
0x180011026  mov     [rsp+248h+var_1E0], rdi
0x18001102b  mov     r12, rdi
0x18001102e  mov     [rsp+248h+var_1D8], rdi
0x180011033  mov     r13, rdi
0x180011036  mov     al, [r15+33h]
0x18001103a  neg     al
0x18001103c  sbb     r9d, r9d
0x18001103f  not     r9d
0x180011042  and     r9d, 200h
0x180011049  mov     [rsp+248h+var_210], rdi
0x18001104e  mov     [rsp+248h+var_218], rdi
0x180011053  lea     rax, [rsp+248h+Size]
0x180011058  mov     [rsp+248h+var_220], rax
0x18001105d  lea     rax, [rsp+248h+Src]
0x180011062  mov     [rsp+248h+var_228], rax
0x180011067  mov     esi, 3
0x18001106c  mov     r8d, esi
0x18001106f  lea     rdx, [rsp+248h+var_58]
0x180011077  call    cs:__imp_LdrResSearchResource
0x18001107d  mov     ebx, eax
0x18001107f  mov     [rsp+248h+var_208], eax
0x180011083  test    eax, eax
0x180011085  jns     loc_180011291
0x18001108b  add     eax, 3FFFFF77h
0x180011090  lea     r12d, [rsi-1]
0x180011094  cmp     eax, r12d
0x180011097  jbe     loc_180011551
0x18001109d  cmp     ebx, 0C000007Bh
0x1800110a3  jnz     loc_180011264
0x1800110a9  cmp     [r15+33h], dil
0x1800110ad  jnz     loc_180011264
0x1800110b3  cmp     [r15+4Ch], edi
0x1800110b7  jnz     loc_180011264
0x1800110bd  mov     ebx, 11Ch
0x1800110c2  mov     r8d, ebx; Size
0x1800110c5  xor     edx, edx; Val
0x1800110c7  lea     rcx, [rsp+248h+VersionInfo]; void *
0x1800110cf  call    memset_0
0x1800110d4  mov     [rsp+248h+VersionInfo.dwOSVersionInfoSize], ebx
0x1800110db  mov     [rsp+248h+VersionInfo.dwMajorVersion], 6
0x1800110e6  mov     [rsp+248h+VersionInfo.dwMinorVersion], r12d
0x1800110ee  mov     r8b, sil; Condition
0x1800110f1  mov     edx, r12d; TypeMask
0x1800110f4  xor     ecx, ecx; ConditionMask
0x1800110f6  call    cs:__imp_VerSetConditionMask
0x1800110fc  mov     r8b, sil; Condition
0x1800110ff  mov     edx, r14d; TypeMask
0x180011102  mov     rcx, rax; ConditionMask
0x180011105  call    cs:__imp_VerSetConditionMask
0x18001110b  mov     r8, rax; ConditionMask
0x18001110e  mov     edx, esi; TypeMask
0x180011110  lea     rcx, [rsp+248h+VersionInfo]; VersionInfo
0x180011118  call    cs:__imp_RtlVerifyVersionInfo
0x18001111e  mov     [rsp+248h+var_208], eax
0x180011122  test    eax, eax
0x180011124  jns     short loc_180011134
0x180011126  mov     ebx, 0C0000089h
0x18001112b  mov     [rsp+248h+var_208], ebx
0x18001112f  jmp     loc_180011551
0x180011134  mov     rax, [r15+8]
0x180011138  mov     byte ptr [rsp+248h+var_1A8+8], dil
0x180011140  mov     [rsp+248h+Handle], rax
0x180011148  mov     [rsp+248h+var_208], edi
0x18001114c  mov     dl, r14b
0x18001114f  lea     rcx, [rsp+248h+Handle]
0x180011157  call    RtlFileMapMapView
0x18001115c  mov     ebx, eax
0x18001115e  mov     [rsp+248h+var_208], eax
0x180011162  test    eax, eax
0x180011164  jns     short loc_18001118B
0x180011166  mov     dword ptr [rsp+248h+var_228], eax
0x18001116a  lea     r9, aRtlfilemapmapv; "RtlFileMapMapView failed [%x]"
0x180011171  mov     r8d, 652h
0x180011177  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x18001117e  mov     ecx, r14d
0x180011181  call    AslLogCallPrintf
0x180011186  jmp     loc_180011551
0x18001118b  mov     rax, [r15]
0x18001118e  mov     [rsp+248h+var_228], rax
0x180011193  lea     r9, aReMappedFileAs; "Re-mapped file as image to get version "...
0x18001119a  mov     r8d, 65Bh
0x1800111a0  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x1800111a7  mov     rdx, rsi
0x1800111aa  mov     ebx, 3
0x1800111af  mov     ecx, ebx
0x1800111b1  call    AslLogCallPrintf
0x1800111b6  mov     [rsp+248h+var_210], rdi
0x1800111bb  mov     [rsp+248h+var_218], rdi
0x1800111c0  lea     rax, [rsp+248h+Size]
0x1800111c5  mov     [rsp+248h+var_220], rax
0x1800111ca  lea     rax, [rsp+248h+Src]
0x1800111cf  mov     [rsp+248h+var_228], rax
0x1800111d4  xor     r9d, r9d
0x1800111d7  mov     r8d, ebx
0x1800111da  lea     rdx, [rsp+248h+var_58]
0x1800111e2  mov     rcx, [rsp+248h+BaseAddress+8]
0x1800111ea  call    cs:__imp_LdrResSearchResource
0x1800111f0  mov     ebx, eax
0x1800111f2  mov     [rsp+248h+var_208], eax
0x1800111f6  lea     rax, aFound; "Found"
0x1800111fd  lea     rdx, aDidNotFind; "Did not find"
0x180011204  test    ebx, ebx
0x180011206  cmovs   rax, rdx
0x18001120a  mov     dword ptr [rsp+248h+var_220], ebx
0x18001120e  mov     [rsp+248h+var_228], rax
0x180011213  lea     r9, aLsVersionBlock; "%ls version block after re-mapping as i"...
0x18001121a  mov     r8d, 668h
0x180011220  mov     rdx, rsi
0x180011223  mov     ecx, r12d
0x180011226  call    AslLogCallPrintf
0x18001122b  test    ebx, ebx
0x18001122d  jns     short loc_180011248
0x18001122f  mov     dword ptr [rsp+248h+var_228], ebx
0x180011233  lea     r9, aLdrresfindreso_0; "LdrResFindResource failed [%x]"
0x18001123a  mov     r8d, 66Bh
0x180011240  mov     rdx, rsi
0x180011243  jmp     loc_18001117E
0x180011248  mov     r13, [rsp+248h+BaseAddress+8]
0x180011250  mov     [rsp+248h+var_1E0], r13
0x180011255  mov     r12, qword ptr [rsp+248h+var_1A8]
0x18001125d  mov     [rsp+248h+var_1D8], r12
0x180011262  jmp     short loc_180011298
0x180011264  mov     dword ptr [rsp+248h+var_220], ebx
0x180011268  mov     rax, [r15]
0x18001126b  mov     [rsp+248h+var_228], rax
0x180011270  lea     r9, aLdrresfindreso; "LdrResFindResource failed %ls [%x]"
0x180011277  mov     r8d, 673h
0x18001127d  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180011284  mov     ecx, r14d
0x180011287  call    AslLogCallPrintf
0x18001128c  jmp     loc_180011551
0x180011291  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180011298  mov     rax, [rsp+248h+Src]
0x18001129d  test    rax, rax
0x1800112a0  jnz     short loc_1800112C3
0x1800112a2  mov     dword ptr [rsp+248h+var_228], ebx
0x1800112a6  lea     r9, aLdrresfindreso_1; "LdrResFindResource returned null versio"...
0x1800112ad  mov     r8d, 67Ah
0x1800112b3  mov     rdx, rsi
0x1800112b6  mov     ecx, r14d
0x1800112b9  call    AslLogCallPrintf
0x1800112be  jmp     loc_180011126
0x1800112c3  mov     r8, [rsp+248h+Size]; Size
0x1800112c8  cmp     r8, 26h ; '&'
0x1800112cc  jnb     short loc_1800112E5
0x1800112ce  mov     ebx, 0C00000E5h
0x1800112d3  lea     r9, aVersionBlockIs_0; "Version block is too small to be valid"
0x1800112da  mov     r8d, 681h
0x1800112e0  jmp     loc_180011542
0x1800112e5  cmp     r8, 8000h
0x1800112ec  jbe     short loc_180011305
0x1800112ee  mov     ebx, 0C00000E5h
0x1800112f3  lea     r9, aVersionBlockIs; "Version block is too large to be valid"
0x1800112fa  mov     r8d, 68Bh
0x180011300  jmp     loc_180011542
0x180011305  mov     [rsp+248h+var_188], rax
0x18001130d  mov     [rsp+248h+var_180], r8
0x180011315  cmp     rax, r13
0x180011318  jb      loc_180011530
0x18001131e  lea     rcx, [r8+rax]
0x180011322  cmp     rax, rcx
0x180011325  ja      loc_180011530
0x18001132b  lea     rdx, [r12+r13]
0x18001132f  cmp     rax, rdx
0x180011332  ja      loc_180011530
0x180011338  cmp     rcx, r13
0x18001133b  jb      loc_180011530
0x180011341  cmp     rcx, rdx
0x180011344  ja      loc_180011530
0x18001134a  cmp     r13, rdx
0x18001134d  ja      loc_180011530
0x180011353  cmp     r8, r12
0x180011356  ja      loc_180011530
0x18001135c  mov     rcx, gs:60h
0x180011365  mov     edx, 8; Flags
0x18001136a  mov     rcx, [rcx+30h]; HeapHandle
0x18001136e  call    cs:__imp_RtlAllocateHeap
0x180011374  mov     rbx, rax
0x180011377  mov     r12, rax
0x18001137a  mov     [rsp+248h+var_1E8], rax
0x18001137f  test    rax, rax
0x180011382  jnz     short loc_1800113AA
0x180011384  mov     ebx, 0C0000017h
0x180011389  lea     r9, aOutOfMemory; "Out of memory"
0x180011390  mov     r8d, 6A2h
0x180011396  mov     [rsp+248h+var_208], ebx
0x18001139a  mov     rdx, rsi
0x18001139d  mov     ecx, r14d
0x1800113a0  call    AslLogCallPrintf
0x1800113a5  jmp     loc_180011554
0x1800113aa  mov     r8, [rsp+248h+Size]; Size
0x1800113af  mov     rdx, [rsp+248h+Src]; Src
0x1800113b4  mov     rcx, rbx; void *
0x1800113b7  call    memmove_0
0x1800113bc  call    Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline
0x1800113c1  test    eax, eax
0x1800113c3  jz      short loc_1800113FF
0x1800113c5  mov     r13d, 5Ch ; '\'
0x1800113cb  cmp     [rsp+248h+Size], r13
0x1800113d0  jb      short loc_1800113EB
0x1800113d2  mov     rcx, [rsp+248h+Src]
0x1800113d7  add     rcx, 6; String1
0x1800113db  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x1800113e2  call    _wcsicmp_0
0x1800113e7  test    eax, eax
0x1800113e9  jz      short loc_18001142C
0x1800113eb  mov     ebx, 0C00000E5h
0x1800113f0  lea     r9, aVersionBlockIn_0; "Version block invalid"
0x1800113f7  mov     r8d, 6BAh
0x1800113fd  jmp     short loc_180011396
0x1800113ff  cmp     [rsp+248h+Size], 26h ; '&'
0x180011405  jb      loc_180011519
0x18001140b  mov     rcx, [rsp+248h+Src]
0x180011410  add     rcx, 6; String1
0x180011414  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x18001141b  call    _wcsicmp_0
0x180011420  test    eax, eax
0x180011422  jnz     loc_180011519
0x180011428  lea     r13d, [rax+5Ch]
0x18001142c  cmp     r13w, [rbx]
0x180011430  jbe     short loc_180011449
0x180011432  mov     ebx, 0C00000E5h
0x180011437  lea     r9, aVersionBlockIn_1; "Version block invalid (too small to con"...
0x18001143e  mov     r8d, 6CFh
0x180011444  jmp     loc_180011396
0x180011449  movzx   eax, word ptr [rbx]
0x18001144c  cmp     [rsp+248h+Size], rax
0x180011451  jnb     short loc_18001147C
0x180011453  lea     r9, aLdrressearchre; "LdrResSearchResource returned a Version"...
0x18001145a  mov     r8d, 6D8h
0x180011460  mov     rdx, rsi
0x180011463  mov     ecx, 3
0x180011468  call    AslLogCallPrintf
  ... truncated ...
```
