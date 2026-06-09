# AslpFileGetVersionBlock

- ea: `0x14000e380`
- end: `0x14000eaae`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000e18c`

## callees

- `0x140001e94`
- `0x140001ff2`
- `0x14000233f`
- `0x140007074`
- `0x14000bde8`
- `0x14000c460`
- `0x14000e380`
- `0x140010344`
- `0x1400115f0`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x14000ea66`
- `ntdll!ZwUnmapViewOfSection` at `0x14000ea66`
- `ntdll!LdrResSearchResource` at `0x14000e4f3`
- `ntdll!LdrResSearchResource` at `0x14000e666`
- `ntdll!LdrResSearchResource` at `0x14000e4f3`
- `ntdll!LdrResSearchResource` at `0x14000e666`
- `ntdll!RtlVerifyVersionInfo` at `0x14000e594`
- `ntdll!RtlVerifyVersionInfo` at `0x14000e594`
- `ntdll!ZwClose` at `0x14000ea45`
- `ntdll!ZwClose` at `0x14000ea83`
- `ntdll!ZwClose` at `0x14000ea45`
- `ntdll!ZwClose` at `0x14000ea83`
- `ntdll!RtlFreeHeap` at `0x14000ea28`
- `ntdll!RtlFreeHeap` at `0x14000ea28`
- `ntdll!RtlAllocateHeap` at `0x14000e7ea`
- `ntdll!RtlAllocateHeap` at `0x14000e7ea`
- `ntdll!VerSetConditionMask` at `0x14000e572`
- `ntdll!VerSetConditionMask` at `0x14000e581`
- `ntdll!VerSetConditionMask` at `0x14000e572`
- `ntdll!VerSetConditionMask` at `0x14000e581`

## string_xrefs

- `0x14000e9b1`: `Version block has bad size (falls outside file)`
- `0x14000e983`: `Version block invalid (fixed info falls outside root)`

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
  __int64 v16; // rdx
  void *v17; // rax
  int v18; // eax
  const wchar_t *v19; // rax
  char *v20; // rcx
  char *v21; // rdx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v23; // rbx
  const char *v24; // r9
  __int64 v25; // r8
  unsigned __int16 v26; // ax
  unsigned __int64 v27; // r9
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rcx
  unsigned __int16 *v30; // r8
  __int64 v32; // [rsp+20h] [rbp-228h]
  __int64 v33; // [rsp+20h] [rbp-228h]
  SIZE_T Size; // [rsp+48h] [rbp-200h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-1F8h] BYREF
  unsigned __int16 *v36; // [rsp+60h] [rbp-1E8h]
  unsigned __int16 *v37; // [rsp+68h] [rbp-1E0h]
  SIZE_T v38; // [rsp+70h] [rbp-1D8h]
  unsigned __int16 **v39; // [rsp+78h] [rbp-1D0h]
  HANDLE Handle[2]; // [rsp+80h] [rbp-1C8h] BYREF
  PVOID BaseAddress[2]; // [rsp+90h] [rbp-1B8h]
  __int128 v42; // [rsp+A0h] [rbp-1A8h]
  unsigned __int16 **v43; // [rsp+B0h] [rbp-198h]
  __int64 v44; // [rsp+B8h] [rbp-190h]
  void *v45; // [rsp+C0h] [rbp-188h]
  SIZE_T v46; // [rsp+C8h] [rbp-180h]
  struct _OSVERSIONINFOEXW VersionInfo; // [rsp+D0h] [rbp-178h] BYREF
  _QWORD v48[3]; // [rsp+1F0h] [rbp-58h] BYREF

  v39 = a2;
  v43 = a1;
  v44 = a3;
  Src[0] = 0;
  v5 = 0;
  v36 = 0;
  Size = 0;
  *(_OWORD *)Handle = 0;
  *(_OWORD *)BaseAddress = 0;
  v42 = 0;
  v6 = *(_QWORD *)(a3 + 64);
  if ( !v6 )
  {
    v9 = AslFileMappingEnsure(a3);
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
    v48[0] = 16;
    v48[1] = 1;
    v48[2] = 0;
    v10 = *(char **)(a3 + 32);
    if ( v10 )
    {
      v37 = *(unsigned __int16 **)(a3 + 32);
      v11 = *(_QWORD *)(a3 + 40);
      v38 = v11;
      v12 = v10;
    }
    else
    {
      v37 = 0;
      v11 = 0;
      v38 = 0;
      v12 = 0;
    }
    v13 = LdrResSearchResource(v10, v48, 3, *(_BYTE *)(a3 + 51) == 0 ? 0x200 : 0, Src, &Size, 0, 0);
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
      v17 = *(void **)(a3 + 8);
      BYTE8(v42) = 0;
      Handle[0] = v17;
      LOBYTE(v16) = 1;
      v18 = RtlFileMapMapView(Handle, v16);
      v8 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v32) = v18;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1618, "RtlFileMapMapView failed [%x]", v32);
        goto LABEL_68;
      }
      AslLogCallPrintf(
        3,
        "AslpFileGetVersionBlock",
        1627,
        "Re-mapped file as image to get version block: %ls",
        *(const wchar_t **)a3);
      v8 = LdrResSearchResource(BaseAddress[1], v48, 3, 0, Src, &Size, 0, 0);
      v19 = L"Found";
      if ( v8 < 0 )
        v19 = L"Did not find";
      AslLogCallPrintf(2, "AslpFileGetVersionBlock", 1640, "%ls version block after re-mapping as image [%x]", v19, v8);
      if ( v8 < 0 )
      {
        LODWORD(v33) = v8;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1643, "LdrResFindResource failed [%x]", v33);
        goto LABEL_68;
      }
      v12 = (char *)BaseAddress[1];
      v37 = (unsigned __int16 *)BaseAddress[1];
      v11 = v42;
      v38 = v42;
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
    v45 = Src[0];
    v46 = Size;
    if ( Src[0] < v12
      || (v20 = (char *)Src[0] + Size, Src[0] > (char *)Src[0] + Size)
      || (v21 = &v12[v11], Src[0] > &v12[v11])
      || v20 < v12
      || v20 > v21
      || v12 > v21
      || Size > v11 )
    {
      v8 = -1073741687;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1686, "Version block has bad size (falls outside file)");
      goto LABEL_68;
    }
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    v23 = Heap;
    v5 = Heap;
    v36 = Heap;
    if ( Heap )
    {
      memmove_0(Heap, Src[0], Size);
      if ( (unsigned int)Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( Size < 0x5C || wcsicmp_0((const wchar_t *)Src[0] + 3, L"VS_VERSION_INFO") )
        {
          v8 = -1073741595;
          v24 = "Version block invalid";
          v25 = 1722;
          goto LABEL_42;
        }
      }
      else if ( Size < 0x26 || wcsicmp_0((const wchar_t *)Src[0] + 3, L"VS_VERSION_INFO") )
      {
        v8 = -1073741595;
        v24 = "Version block invalid";
        v25 = 1729;
        goto LABEL_42;
      }
      if ( *v23 >= 0x5Cu )
      {
        if ( Size >= *v23 )
        {
          v26 = *v23;
        }
        else
        {
          AslLogCallPrintf(
            3,
            "AslpFileGetVersionBlock",
            1752,
            "LdrResSearchResource returned a VersionBlockSize smaller than reflected in the actual block data.");
          *v23 = Size;
          v26 = Size;
        }
        v37 = v23;
        v27 = v26;
        v38 = v26;
        v28 = v23 + 20;
        v45 = v23 + 20;
        v46 = 52;
        if ( v23 + 20 < v23
          || (v29 = v23 + 46, v23 + 20 >= v23 + 46)
          || (v30 = (unsigned __int16 *)((char *)v23 + v27), v28 > (unsigned __int16 *)((char *)v23 + v27))
          || v29 < v23
          || v29 > v30
          || v23 > v30
          || v27 < 0x34 )
        {
          *v39 = 0;
          if ( v23[1] )
          {
            v8 = -1073741595;
            v24 = "Version block invalid (fixed info falls outside root)";
            v25 = 1776;
            goto LABEL_42;
          }
        }
        else
        {
          *v39 = v28;
        }
        *(_QWORD *)(a3 + 64) = v23;
        v36 = 0;
        *v43 = v23;
        v8 = 0;
        goto LABEL_68;
      }
      v8 = -1073741595;
      v24 = "Version block invalid (too small to contain data)";
      v25 = 1743;
    }
    else
    {
      v8 = -1073741801;
      v24 = "Out of memory";
      v25 = 1698;
    }
LABEL_42:
    AslLogCallPrintf(1, "AslpFileGetVersionBlock", v25, v24);
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
  if ( BYTE8(v42) && Handle[0] )
    ZwClose(Handle[0]);
  if ( BYTE10(v42) && BaseAddress[1] )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress[1]);
  if ( BYTE9(v42) && Handle[1] )
    ZwClose(Handle[1]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e380  push    rbx
0x14000e382  push    rsi
0x14000e383  push    rdi
0x14000e384  push    r12
0x14000e386  push    r13
0x14000e388  push    r14
0x14000e38a  push    r15
0x14000e38c  sub     rsp, 210h
0x14000e393  mov     rax, cs:__security_cookie
0x14000e39a  xor     rax, rsp
0x14000e39d  mov     [rsp+248h+var_40], rax
0x14000e3a5  mov     r15, r8
0x14000e3a8  mov     r9, rdx
0x14000e3ab  mov     [rsp+248h+var_1D0], rdx
0x14000e3b0  mov     r10, rcx
0x14000e3b3  mov     [rsp+248h+var_198], rcx
0x14000e3bb  mov     [rsp+248h+var_190], r8
0x14000e3c3  xor     edi, edi
0x14000e3c5  mov     [rsp+248h+Src], rdi
0x14000e3ca  mov     r12d, edi
0x14000e3cd  mov     [rsp+248h+var_1E8], rdi
0x14000e3d2  mov     [rsp+248h+Size], rdi
0x14000e3d7  xorps   xmm0, xmm0
0x14000e3da  movups  xmmword ptr [rsp+248h+Handle], xmm0
0x14000e3e2  movups  xmmword ptr [rsp+248h+BaseAddress], xmm0
0x14000e3ea  movups  [rsp+248h+var_1A8], xmm0
0x14000e3f2  mov     r8, [r8+40h]
0x14000e3f6  test    r8, r8
0x14000e3f9  jz      short loc_14000E41E
0x14000e3fb  lea     rax, [r8+28h]
0x14000e3ff  mov     ecx, edi
0x14000e401  lea     edx, [rdi+34h]
0x14000e404  cmp     [r8+2], dx
0x14000e409  cmovnb  rcx, rax
0x14000e40d  mov     [r9], rcx
0x14000e410  mov     rax, [r15+40h]
0x14000e414  mov     [r10], rax
0x14000e417  mov     ebx, edi
0x14000e419  jmp     loc_14000EA11
0x14000e41e  mov     rcx, r15
0x14000e421  call    AslFileMappingEnsure
0x14000e426  mov     ebx, eax
0x14000e428  test    eax, eax
0x14000e42a  jns     short loc_14000E453
0x14000e42c  mov     dword ptr [rsp+248h+var_228], eax
0x14000e430  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000e437  mov     r8d, 5F7h
0x14000e43d  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14000e444  mov     ecx, 1
0x14000e449  call    AslLogCallPrintf
0x14000e44e  jmp     loc_14000EA11
0x14000e453  cmp     dword ptr [r15+38h], 6
0x14000e458  jz      short loc_14000E464
0x14000e45a  mov     ebx, 0C0000089h
0x14000e45f  jmp     loc_14000EA11
0x14000e464  mov     [rsp+248h+var_58], 10h
0x14000e470  mov     r14d, 1
0x14000e476  mov     [rsp+248h+var_50], r14
0x14000e47e  mov     [rsp+248h+var_48], rdi
0x14000e486  mov     rcx, [r15+20h]
0x14000e48a  test    rcx, rcx
0x14000e48d  jz      short loc_14000E4A2
0x14000e48f  mov     [rsp+248h+var_1E0], rcx
0x14000e494  mov     r12, [r15+28h]
0x14000e498  mov     [rsp+248h+var_1D8], r12
0x14000e49d  mov     r13, rcx
0x14000e4a0  jmp     short loc_14000E4B2
0x14000e4a2  mov     [rsp+248h+var_1E0], rdi
0x14000e4a7  mov     r12, rdi
0x14000e4aa  mov     [rsp+248h+var_1D8], rdi
0x14000e4af  mov     r13, rdi
0x14000e4b2  mov     al, [r15+33h]
0x14000e4b6  neg     al
0x14000e4b8  sbb     r9d, r9d
0x14000e4bb  not     r9d
0x14000e4be  and     r9d, 200h
0x14000e4c5  mov     [rsp+248h+var_210], rdi
0x14000e4ca  mov     [rsp+248h+var_218], rdi
0x14000e4cf  lea     rax, [rsp+248h+Size]
0x14000e4d4  mov     [rsp+248h+var_220], rax
0x14000e4d9  lea     rax, [rsp+248h+Src]
0x14000e4de  mov     [rsp+248h+var_228], rax
0x14000e4e3  mov     esi, 3
0x14000e4e8  mov     r8d, esi
0x14000e4eb  lea     rdx, [rsp+248h+var_58]
0x14000e4f3  call    cs:__imp_LdrResSearchResource
0x14000e4f9  mov     ebx, eax
0x14000e4fb  mov     [rsp+248h+var_208], eax
0x14000e4ff  test    eax, eax
0x14000e501  jns     loc_14000E70D
0x14000e507  add     eax, 3FFFFF77h
0x14000e50c  lea     r12d, [rsi-1]
0x14000e510  cmp     eax, r12d
0x14000e513  jbe     loc_14000E9CD
0x14000e519  cmp     ebx, 0C000007Bh
0x14000e51f  jnz     loc_14000E6E0
0x14000e525  cmp     [r15+33h], dil
0x14000e529  jnz     loc_14000E6E0
0x14000e52f  cmp     [r15+4Ch], edi
0x14000e533  jnz     loc_14000E6E0
0x14000e539  mov     ebx, 11Ch
0x14000e53e  mov     r8d, ebx; Size
0x14000e541  xor     edx, edx; Val
0x14000e543  lea     rcx, [rsp+248h+VersionInfo]; void *
0x14000e54b  call    memset_0
0x14000e550  mov     [rsp+248h+VersionInfo.dwOSVersionInfoSize], ebx
0x14000e557  mov     [rsp+248h+VersionInfo.dwMajorVersion], 6
0x14000e562  mov     [rsp+248h+VersionInfo.dwMinorVersion], r12d
0x14000e56a  mov     r8b, sil; Condition
0x14000e56d  mov     edx, r12d; TypeMask
0x14000e570  xor     ecx, ecx; ConditionMask
0x14000e572  call    cs:__imp_VerSetConditionMask
0x14000e578  mov     r8b, sil; Condition
0x14000e57b  mov     edx, r14d; TypeMask
0x14000e57e  mov     rcx, rax; ConditionMask
0x14000e581  call    cs:__imp_VerSetConditionMask
0x14000e587  mov     r8, rax; ConditionMask
0x14000e58a  mov     edx, esi; TypeMask
0x14000e58c  lea     rcx, [rsp+248h+VersionInfo]; VersionInfo
0x14000e594  call    cs:__imp_RtlVerifyVersionInfo
0x14000e59a  mov     [rsp+248h+var_208], eax
0x14000e59e  test    eax, eax
0x14000e5a0  jns     short loc_14000E5B0
0x14000e5a2  mov     ebx, 0C0000089h
0x14000e5a7  mov     [rsp+248h+var_208], ebx
0x14000e5ab  jmp     loc_14000E9CD
0x14000e5b0  mov     rax, [r15+8]
0x14000e5b4  mov     byte ptr [rsp+248h+var_1A8+8], dil
0x14000e5bc  mov     [rsp+248h+Handle], rax
0x14000e5c4  mov     [rsp+248h+var_208], edi
0x14000e5c8  mov     dl, r14b
0x14000e5cb  lea     rcx, [rsp+248h+Handle]
0x14000e5d3  call    RtlFileMapMapView
0x14000e5d8  mov     ebx, eax
0x14000e5da  mov     [rsp+248h+var_208], eax
0x14000e5de  test    eax, eax
0x14000e5e0  jns     short loc_14000E607
0x14000e5e2  mov     dword ptr [rsp+248h+var_228], eax
0x14000e5e6  lea     r9, aRtlfilemapmapv; "RtlFileMapMapView failed [%x]"
0x14000e5ed  mov     r8d, 652h
0x14000e5f3  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14000e5fa  mov     ecx, r14d
0x14000e5fd  call    AslLogCallPrintf
0x14000e602  jmp     loc_14000E9CD
0x14000e607  mov     rax, [r15]
0x14000e60a  mov     [rsp+248h+var_228], rax
0x14000e60f  lea     r9, aReMappedFileAs; "Re-mapped file as image to get version "...
0x14000e616  mov     r8d, 65Bh
0x14000e61c  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14000e623  mov     rdx, rsi
0x14000e626  mov     ebx, 3
0x14000e62b  mov     ecx, ebx
0x14000e62d  call    AslLogCallPrintf
0x14000e632  mov     [rsp+248h+var_210], rdi
0x14000e637  mov     [rsp+248h+var_218], rdi
0x14000e63c  lea     rax, [rsp+248h+Size]
0x14000e641  mov     [rsp+248h+var_220], rax
0x14000e646  lea     rax, [rsp+248h+Src]
0x14000e64b  mov     [rsp+248h+var_228], rax
0x14000e650  xor     r9d, r9d
0x14000e653  mov     r8d, ebx
0x14000e656  lea     rdx, [rsp+248h+var_58]
0x14000e65e  mov     rcx, [rsp+248h+BaseAddress+8]
0x14000e666  call    cs:__imp_LdrResSearchResource
0x14000e66c  mov     ebx, eax
0x14000e66e  mov     [rsp+248h+var_208], eax
0x14000e672  lea     rax, aFound; "Found"
0x14000e679  lea     rdx, aDidNotFind; "Did not find"
0x14000e680  test    ebx, ebx
0x14000e682  cmovs   rax, rdx
0x14000e686  mov     dword ptr [rsp+248h+var_220], ebx
0x14000e68a  mov     [rsp+248h+var_228], rax
0x14000e68f  lea     r9, aLsVersionBlock; "%ls version block after re-mapping as i"...
0x14000e696  mov     r8d, 668h
0x14000e69c  mov     rdx, rsi
0x14000e69f  mov     ecx, r12d
0x14000e6a2  call    AslLogCallPrintf
0x14000e6a7  test    ebx, ebx
0x14000e6a9  jns     short loc_14000E6C4
0x14000e6ab  mov     dword ptr [rsp+248h+var_228], ebx
0x14000e6af  lea     r9, aLdrresfindreso_0; "LdrResFindResource failed [%x]"
0x14000e6b6  mov     r8d, 66Bh
0x14000e6bc  mov     rdx, rsi
0x14000e6bf  jmp     loc_14000E5FA
0x14000e6c4  mov     r13, [rsp+248h+BaseAddress+8]
0x14000e6cc  mov     [rsp+248h+var_1E0], r13
0x14000e6d1  mov     r12, qword ptr [rsp+248h+var_1A8]
0x14000e6d9  mov     [rsp+248h+var_1D8], r12
0x14000e6de  jmp     short loc_14000E714
0x14000e6e0  mov     dword ptr [rsp+248h+var_220], ebx
0x14000e6e4  mov     rax, [r15]
0x14000e6e7  mov     [rsp+248h+var_228], rax
0x14000e6ec  lea     r9, aLdrresfindreso; "LdrResFindResource failed %ls [%x]"
0x14000e6f3  mov     r8d, 673h
0x14000e6f9  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14000e700  mov     ecx, r14d
0x14000e703  call    AslLogCallPrintf
0x14000e708  jmp     loc_14000E9CD
0x14000e70d  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14000e714  mov     rax, [rsp+248h+Src]
0x14000e719  test    rax, rax
0x14000e71c  jnz     short loc_14000E73F
0x14000e71e  mov     dword ptr [rsp+248h+var_228], ebx
0x14000e722  lea     r9, aLdrresfindreso_1; "LdrResFindResource returned null versio"...
0x14000e729  mov     r8d, 67Ah
0x14000e72f  mov     rdx, rsi
0x14000e732  mov     ecx, r14d
0x14000e735  call    AslLogCallPrintf
0x14000e73a  jmp     loc_14000E5A2
0x14000e73f  mov     r8, [rsp+248h+Size]; Size
0x14000e744  cmp     r8, 26h ; '&'
0x14000e748  jnb     short loc_14000E761
0x14000e74a  mov     ebx, 0C00000E5h
0x14000e74f  lea     r9, aVersionBlockIs_0; "Version block is too small to be valid"
0x14000e756  mov     r8d, 681h
0x14000e75c  jmp     loc_14000E9BE
0x14000e761  cmp     r8, 8000h
0x14000e768  jbe     short loc_14000E781
0x14000e76a  mov     ebx, 0C00000E5h
0x14000e76f  lea     r9, aVersionBlockIs; "Version block is too large to be valid"
0x14000e776  mov     r8d, 68Bh
0x14000e77c  jmp     loc_14000E9BE
0x14000e781  mov     [rsp+248h+var_188], rax
0x14000e789  mov     [rsp+248h+var_180], r8
0x14000e791  cmp     rax, r13
0x14000e794  jb      loc_14000E9AC
0x14000e79a  lea     rcx, [r8+rax]
0x14000e79e  cmp     rax, rcx
0x14000e7a1  ja      loc_14000E9AC
0x14000e7a7  lea     rdx, [r12+r13]
0x14000e7ab  cmp     rax, rdx
0x14000e7ae  ja      loc_14000E9AC
0x14000e7b4  cmp     rcx, r13
0x14000e7b7  jb      loc_14000E9AC
0x14000e7bd  cmp     rcx, rdx
0x14000e7c0  ja      loc_14000E9AC
0x14000e7c6  cmp     r13, rdx
0x14000e7c9  ja      loc_14000E9AC
0x14000e7cf  cmp     r8, r12
0x14000e7d2  ja      loc_14000E9AC
0x14000e7d8  mov     rcx, gs:60h
0x14000e7e1  mov     edx, 8; Flags
0x14000e7e6  mov     rcx, [rcx+30h]; HeapHandle
0x14000e7ea  call    cs:__imp_RtlAllocateHeap
0x14000e7f0  mov     rbx, rax
0x14000e7f3  mov     r12, rax
0x14000e7f6  mov     [rsp+248h+var_1E8], rax
0x14000e7fb  test    rax, rax
0x14000e7fe  jnz     short loc_14000E826
0x14000e800  mov     ebx, 0C0000017h
0x14000e805  lea     r9, aOutOfMemory; "Out of memory"
0x14000e80c  mov     r8d, 6A2h
0x14000e812  mov     [rsp+248h+var_208], ebx
0x14000e816  mov     rdx, rsi
0x14000e819  mov     ecx, r14d
0x14000e81c  call    AslLogCallPrintf
0x14000e821  jmp     loc_14000E9D0
0x14000e826  mov     r8, [rsp+248h+Size]; Size
0x14000e82b  mov     rdx, [rsp+248h+Src]; Src
0x14000e830  mov     rcx, rbx; void *
0x14000e833  call    memmove_0
0x14000e838  call    Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline
0x14000e83d  test    eax, eax
0x14000e83f  jz      short loc_14000E87B
0x14000e841  mov     r13d, 5Ch ; '\'
0x14000e847  cmp     [rsp+248h+Size], r13
0x14000e84c  jb      short loc_14000E867
0x14000e84e  mov     rcx, [rsp+248h+Src]
0x14000e853  add     rcx, 6; String1
0x14000e857  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x14000e85e  call    _wcsicmp_0
0x14000e863  test    eax, eax
0x14000e865  jz      short loc_14000E8A8
0x14000e867  mov     ebx, 0C00000E5h
0x14000e86c  lea     r9, aVersionBlockIn_0; "Version block invalid"
0x14000e873  mov     r8d, 6BAh
0x14000e879  jmp     short loc_14000E812
0x14000e87b  cmp     [rsp+248h+Size], 26h ; '&'
0x14000e881  jb      loc_14000E995
0x14000e887  mov     rcx, [rsp+248h+Src]
0x14000e88c  add     rcx, 6; String1
0x14000e890  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x14000e897  call    _wcsicmp_0
0x14000e89c  test    eax, eax
0x14000e89e  jnz     loc_14000E995
0x14000e8a4  lea     r13d, [rax+5Ch]
0x14000e8a8  cmp     r13w, [rbx]
0x14000e8ac  jbe     short loc_14000E8C5
0x14000e8ae  mov     ebx, 0C00000E5h
0x14000e8b3  lea     r9, aVersionBlockIn_1; "Version block invalid (too small to con"...
0x14000e8ba  mov     r8d, 6CFh
0x14000e8c0  jmp     loc_14000E812
0x14000e8c5  movzx   eax, word ptr [rbx]
0x14000e8c8  cmp     [rsp+248h+Size], rax
0x14000e8cd  jnb     short loc_14000E8F8
0x14000e8cf  lea     r9, aLdrressearchre; "LdrResSearchResource returned a Version"...
0x14000e8d6  mov     r8d, 6D8h
0x14000e8dc  mov     rdx, rsi
0x14000e8df  mov     ecx, 3
0x14000e8e4  call    AslLogCallPrintf
  ... truncated ...
```
