# MRxSmbFsControl

- ea: `0x14002f120`
- end: `0x14002f635`
- name: `MRxSmbFsControl`
- size: `1301`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x14002f640`
- `0x14002ff70`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x1400169c0`
- `0x14002f120`
- `0x1400381d0`
- `0x14003dd64`
- `0x14004ab38`
- `0x14004b1b0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14002f3a4`
- `ntoskrnl!ProbeForWrite` at `0x14002f3a4`
- `ntoskrnl!ProbeForRead` at `0x14002f383`
- `ntoskrnl!ProbeForRead` at `0x14002f383`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002f244`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002f244`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f590`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f590`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x14002f259`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x14002f259`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14002f294`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14002f294`
- `mrxsmb!FsRtlValidateReparsePointBufferEx` at `0x14002f609`
- `mrxsmb!FsRtlValidateReparsePointBufferEx` at `0x14002f609`

## pseudocode

```c
__int64 __fastcall MRxSmbFsControl(__int64 a1)
{
  PERESOURCE *v2; // r15
  __int64 *v3; // r12
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // r14
  __int16 v7; // ax
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 *v10; // r14
  NTSTATUS v11; // ebx
  bool v12; // r15
  NTSTATUS v13; // eax
  bool v14; // zf
  SIZE_T v15; // rcx
  volatile void *v16; // r13
  SIZE_T v17; // rdx
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // [rsp+80h] [rbp-D8h] BYREF
  volatile void *v24; // [rsp+88h] [rbp-D0h]
  __int64 v25; // [rsp+90h] [rbp-C8h]
  __int64 v26; // [rsp+98h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-B8h]
  int v28; // [rsp+A8h] [rbp-B0h]
  int v29; // [rsp+ACh] [rbp-ACh]
  _DWORD v30[42]; // [rsp+B0h] [rbp-A8h] BYREF
  PERESOURCE *v31; // [rsp+160h] [rbp+8h] BYREF
  SIZE_T Length; // [rsp+168h] [rbp+10h]
  int v33; // [rsp+170h] [rbp+18h]
  int v34; // [rsp+178h] [rbp+20h] BYREF

  v31 = *(PERESOURCE **)(a1 + 56);
  v2 = v31;
  v3 = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0xFFFF;
  memset(v30, 0, 0x68u);
  if ( *(_WORD *)v31 == 0xEC23 )
    return 3221225488LL;
  v4 = *(_DWORD *)(a1 + 540);
  if ( v4 == 1310956 && *(_BYTE *)(a1 + 33) != 4 )
    return 3221225488LL;
  v5 = *(_QWORD *)(a1 + 64);
  v25 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids, v4);
  HIBYTE(v23) = 0;
  if ( v5 )
  {
    if ( *(_WORD *)v5 == 0xEB12 )
    {
      v7 = *(_WORD *)(v6 + 114);
      goto LABEL_25;
    }
    if ( v4 != 1311139 )
    {
      v8 = *(_QWORD *)(v5 + 32);
      v9 = 0;
      if ( v8 )
        v9 = *(_QWORD *)(v8 + 48);
      if ( (*(_DWORD *)(v8 + 72) & 0x100000) == 0 )
      {
LABEL_23:
        v7 = *(_WORD *)(v9 + 8);
        goto LABEL_25;
      }
      v10 = 0;
      if ( ExIsResourceAcquiredExclusiveLite(v2[1]) )
      {
        v12 = 0;
        v11 = 0;
      }
      else
      {
        v11 = RxAcquireExclusiveFcbResourceInMRx(0);
        v12 = v11 == 0;
      }
      if ( v11 )
      {
        v2 = v31;
      }
      else
      {
        v13 = MRxSmbDeferredCreate(a1);
        v11 = v13;
        v14 = !v12;
        v2 = v31;
        if ( v14 )
          goto LABEL_22;
        RxReleaseFcbResourceInMRx(0);
      }
      v13 = v11;
LABEL_22:
      if ( v13 )
        goto LABEL_58;
      goto LABEL_23;
    }
  }
  v7 = 0;
LABEL_25:
  WORD2(v23) = v7;
  LODWORD(v23) = v4;
  BYTE6(v23) = 1;
  LOWORD(v26) = 2;
  v27 = 0;
  v11 = 0;
  LODWORD(v31) = 0;
  v10 = *(__int64 **)(a1 + 552);
  v15 = *(unsigned int *)(a1 + 568);
  v33 = *(_DWORD *)(a1 + 568);
  v16 = *(volatile void **)(a1 + 560);
  v24 = v16;
  v17 = *(unsigned int *)(a1 + 572);
  LODWORD(Length) = *(_DWORD *)(a1 + 572);
  if ( (v4 & 3) != 0 && (v4 & 3) != 1 && (v4 & 3) != 2 )
  {
    if ( (v4 & 3) != 3 )
      return 3221225485LL;
    if ( (v4 & 0xFFFF0000) != 0x90000 )
      return 3221225474LL;
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 40) + 64LL) )
    {
      if ( v10 )
      {
        ProbeForRead(v10, v15, 1u);
        v17 = (unsigned int)Length;
      }
      if ( v16 )
        ProbeForWrite(v16, v17, 1u);
      LODWORD(v15) = v33;
    }
  }
  v3 = v10;
  if ( v4 == 1310956 )
  {
    if ( v10 )
    {
      v19 = *v10;
      v25 = v19;
      if ( v19 )
      {
        v20 = *(_QWORD *)(*(_QWORD *)(v19 + 32) + 32LL);
        if ( v20 && (v21 = *(_QWORD *)(v20 + 48)) != 0 )
        {
          *v10 = *(unsigned __int16 *)(v21 + 8);
        }
        else
        {
          v11 = -1073741811;
          LODWORD(v31) = -1073741811;
        }
      }
      if ( v11 >= 0 )
      {
        v34 = v15;
        v3 = (__int64 *)Smb64ThunkRemoteLinkTrackingInfo(v10, &v34, &v31);
        v11 = (int)v31;
      }
      v16 = v24;
    }
    else
    {
      v11 = -1073741811;
    }
    goto LABEL_48;
  }
  if ( v4 != 1311139 )
  {
LABEL_48:
    if ( v11 >= 0 )
    {
      v11 = SmbCeTransact(
              a1,
              (unsigned int)&v26,
              (unsigned int)&v23,
              8,
              (__int64)&v23,
              8,
              0,
              0,
              0,
              0,
              (__int64)v3,
              v33,
              (__int64)v16,
              Length,
              (__int64)v30);
      *(_QWORD *)(a1 + 184) = v30[15];
      if ( v11 >= 0 )
      {
        MRxSmbInvalidateFileInfoCache(a1);
        LOBYTE(v22) = 1;
        MRxSmbInvalidateFullDirectoryCacheParent(a1, v22);
        *((_DWORD *)v2 + 39) &= ~0x40000u;
        if ( *(_QWORD *)(a1 + 184) > (unsigned __int64)(unsigned int)Length )
          v11 = -1073741789;
      }
      if ( v11 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids,
          (unsigned int)v11);
      }
    }
    if ( v4 == 589992 && ((int)(v11 + 0x80000000) < 0 || v11 == -2147483643) )
      v11 = FsRtlValidateReparsePointBufferEx(*(unsigned int *)(a1 + 184), v16, (unsigned int)v11);
  }
LABEL_58:
  if ( v4 == 1310956 )
  {
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    if ( v25 )
      *v10 = v25;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002f120  mov     rax, rsp
0x14002f123  push    rbx
0x14002f124  push    rsi
0x14002f125  push    rdi
0x14002f126  push    r12
0x14002f128  push    r13
0x14002f12a  push    r14
0x14002f12c  push    r15
0x14002f12e  sub     rsp, 120h
0x14002f135  mov     rdi, rcx
0x14002f138  mov     r15, [rcx+38h]
0x14002f13c  mov     [rsp+158h+arg_0], r15
0x14002f144  xor     r12d, r12d
0x14002f147  mov     [rax-0D8h], r12
0x14002f14e  mov     [rax-0C0h], r12
0x14002f155  mov     [rax-0B8h], r12
0x14002f15c  mov     [rax-0B0h], r12d
0x14002f163  mov     dword ptr [rax-0ACh], 0FFFFh
0x14002f16d  xor     edx, edx; Val
0x14002f16f  lea     r8d, [r12+68h]; Size
0x14002f174  lea     rcx, [rax-0A8h]; void *
0x14002f17b  call    memset
0x14002f180  mov     eax, 0EC23h
0x14002f185  cmp     [r15], ax
0x14002f189  jz      loc_14002F61C
0x14002f18f  mov     esi, [rdi+21Ch]
0x14002f195  cmp     esi, 1400ECh
0x14002f19b  jnz     short loc_14002F1A7
0x14002f19d  cmp     byte ptr [rdi+21h], 4
0x14002f1a1  jnz     loc_14002F61C
0x14002f1a7  mov     rbx, [rdi+40h]
0x14002f1ab  mov     [rsp+158h+var_C8], r12
0x14002f1b3  mov     rax, [rdi+48h]
0x14002f1b7  mov     rcx, [rax+28h]
0x14002f1bb  mov     r14, [rcx+28h]
0x14002f1bf  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f1c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f1cd  cmp     rcx, rax
0x14002f1d0  jz      short loc_14002F1F3
0x14002f1d2  test    dword ptr [rcx+2Ch], 400h
0x14002f1d9  jz      short loc_14002F1F3
0x14002f1db  mov     edx, 1Dh
0x14002f1e0  mov     r9d, esi
0x14002f1e3  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x14002f1ea  mov     rcx, [rcx+18h]
0x14002f1ee  call    WPP_SF_d
0x14002f1f3  mov     [rsp+158h+var_D1], r12b
0x14002f1fb  test    rbx, rbx
0x14002f1fe  jz      loc_14002F2BB
0x14002f204  mov     eax, 0EB12h
0x14002f209  cmp     [rbx], ax
0x14002f20c  jnz     short loc_14002F218
0x14002f20e  movzx   eax, word ptr [r14+72h]
0x14002f213  jmp     loc_14002F2BE
0x14002f218  cmp     esi, 1401A3h
0x14002f21e  jz      loc_14002F2BB
0x14002f224  mov     rax, [rbx+20h]
0x14002f228  test    rax, rax
0x14002f22b  mov     r13, r12
0x14002f22e  jz      short loc_14002F234
0x14002f230  mov     r13, [rax+30h]
0x14002f234  test    dword ptr [rax+48h], 100000h
0x14002f23b  jz      short loc_14002F2B4
0x14002f23d  mov     r14, r12
0x14002f240  mov     rcx, [r15+8]; Resource
0x14002f244  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14002f24b  nop     dword ptr [rax+rax+00h]
0x14002f250  test    al, al
0x14002f252  jnz     short loc_14002F26F
0x14002f254  mov     rdx, r15
0x14002f257  xor     ecx, ecx; Fcb
0x14002f259  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x14002f260  nop     dword ptr [rax+rax+00h]
0x14002f265  mov     ebx, eax
0x14002f267  test    eax, eax
0x14002f269  setz    r15b
0x14002f26d  jmp     short loc_14002F274
0x14002f26f  xor     r15b, r15b
0x14002f272  xor     ebx, ebx
0x14002f274  test    ebx, ebx
0x14002f276  jnz     short loc_14002F2A2
0x14002f278  mov     rcx, rdi
0x14002f27b  call    MRxSmbDeferredCreate
0x14002f280  mov     ebx, eax
0x14002f282  test    r15b, r15b
0x14002f285  mov     r15, [rsp+158h+arg_0]
0x14002f28d  jz      short loc_14002F2AC
0x14002f28f  mov     rdx, r15
0x14002f292  xor     ecx, ecx; Fcb
0x14002f294  call    cs:__imp_RxReleaseFcbResourceInMRx
0x14002f29b  nop     dword ptr [rax+rax+00h]
0x14002f2a0  jmp     short loc_14002F2AA
0x14002f2a2  mov     r15, [rsp+158h+arg_0]
0x14002f2aa  mov     eax, ebx
0x14002f2ac  test    eax, eax
0x14002f2ae  jnz     loc_14002F577
0x14002f2b4  movzx   eax, word ptr [r13+8]
0x14002f2b9  jmp     short loc_14002F2BE
0x14002f2bb  mov     eax, r12d
0x14002f2be  mov     [rsp+158h+var_D4], ax
0x14002f2c6  mov     [rsp+158h+var_D8], esi
0x14002f2cd  mov     [rsp+158h+var_D2], 1
0x14002f2d5  mov     eax, 2
0x14002f2da  mov     word ptr [rsp+158h+var_C0], ax
0x14002f2e2  mov     [rsp+158h+var_B8], r12
0x14002f2ea  mov     ebx, r12d
0x14002f2ed  mov     dword ptr [rsp+158h+arg_0], ebx
0x14002f2f4  mov     r14, [rdi+228h]
0x14002f2fb  mov     ecx, [rdi+238h]
0x14002f301  mov     [rsp+158h+arg_10], ecx
0x14002f308  mov     r13, [rdi+230h]
0x14002f30f  mov     [rsp+158h+var_D0], r13
0x14002f317  mov     edx, [rdi+23Ch]
0x14002f31d  mov     dword ptr [rsp+158h+Length], edx
0x14002f324  mov     eax, esi
0x14002f326  and     eax, 3
0x14002f329  jz      loc_14002F3C3
0x14002f32f  sub     eax, 1
0x14002f332  jz      loc_14002F3C3
0x14002f338  sub     eax, 1
0x14002f33b  jz      loc_14002F3C3
0x14002f341  cmp     eax, 1
0x14002f344  jz      short loc_14002F350
0x14002f346  mov     eax, 0C000000Dh
0x14002f34b  jmp     loc_14002F621
0x14002f350  mov     eax, esi
0x14002f352  and     eax, 0FFFF0000h
0x14002f357  cmp     eax, 90000h
0x14002f35c  jz      short loc_14002F368
0x14002f35e  mov     eax, 0C0000002h
0x14002f363  jmp     loc_14002F621
0x14002f368  mov     rax, [rdi+28h]
0x14002f36c  cmp     [rax+40h], r12b
0x14002f370  jz      short loc_14002F3C3
0x14002f372  test    r14, r14
0x14002f375  jz      short loc_14002F396
0x14002f377  mov     rdx, rcx; Length
0x14002f37a  mov     r8d, 1; Alignment
0x14002f380  mov     rcx, r14; Address
0x14002f383  call    cs:__imp_ProbeForRead
0x14002f38a  nop     dword ptr [rax+rax+00h]
0x14002f38f  mov     edx, dword ptr [rsp+158h+Length]; Length
0x14002f396  test    r13, r13
0x14002f399  jz      short loc_14002F3B0
0x14002f39b  mov     r8d, 1; Alignment
0x14002f3a1  mov     rcx, r13; Address
0x14002f3a4  call    cs:__imp_ProbeForWrite
0x14002f3ab  nop     dword ptr [rax+rax+00h]
0x14002f3b0  mov     ecx, [rsp+158h+arg_10]
0x14002f3b7  jmp     short loc_14002F3C3
0x14002f3b9  mov     eax, 0C000000Dh
0x14002f3be  jmp     loc_14002F621
0x14002f3c3  mov     r12, r14
0x14002f3c6  cmp     esi, 1400ECh
0x14002f3cc  jnz     loc_14002F56B
0x14002f3d2  test    r14, r14
0x14002f3d5  jz      loc_14002F561
0x14002f3db  mov     r13, [r14]
0x14002f3de  mov     [rsp+158h+var_C8], r13
0x14002f3e6  test    r13, r13
0x14002f3e9  jz      short loc_14002F416
0x14002f3eb  mov     rax, [r13+20h]
0x14002f3ef  mov     rax, [rax+20h]
0x14002f3f3  test    rax, rax
0x14002f3f6  jz      short loc_14002F40A
0x14002f3f8  mov     rax, [rax+30h]
0x14002f3fc  test    rax, rax
0x14002f3ff  jz      short loc_14002F40A
0x14002f401  movzx   eax, word ptr [rax+8]
0x14002f405  mov     [r14], rax
0x14002f408  jmp     short loc_14002F416
0x14002f40a  mov     ebx, 0C000000Dh
0x14002f40f  mov     dword ptr [rsp+158h+arg_0], ebx
0x14002f416  test    ebx, ebx
0x14002f418  js      short loc_14002F443
0x14002f41a  mov     [rsp+158h+arg_18], ecx
0x14002f421  lea     r8, [rsp+158h+arg_0]
0x14002f429  lea     rdx, [rsp+158h+arg_18]
0x14002f431  mov     rcx, r14
0x14002f434  call    Smb64ThunkRemoteLinkTrackingInfo
0x14002f439  mov     r12, rax
0x14002f43c  mov     ebx, dword ptr [rsp+158h+arg_0]
0x14002f443  mov     r13, [rsp+158h+var_D0]
0x14002f44b  test    ebx, ebx
0x14002f44d  js      loc_14002F5DA
0x14002f453  lea     rax, [rsp+158h+var_A8]
0x14002f45b  mov     [rsp+158h+var_E8], rax
0x14002f460  mov     eax, dword ptr [rsp+158h+Length]
0x14002f467  mov     [rsp+158h+var_F0], eax
0x14002f46b  mov     [rsp+158h+var_F8], r13
0x14002f470  mov     eax, [rsp+158h+arg_10]
0x14002f477  mov     [rsp+158h+var_100], eax
0x14002f47b  mov     [rsp+158h+var_108], r12
0x14002f480  mov     [rsp+158h+var_110], 0
0x14002f488  mov     [rsp+158h+var_118], 0
0x14002f491  mov     [rsp+158h+var_120], 0
0x14002f499  mov     [rsp+158h+var_128], 0
0x14002f4a2  mov     r9d, 8
0x14002f4a8  mov     [rsp+158h+var_130], r9d
0x14002f4ad  lea     rax, [rsp+158h+var_D8]
0x14002f4b5  mov     [rsp+158h+var_138], rax
0x14002f4ba  lea     r8, [rsp+158h+var_D8]
0x14002f4c2  lea     rdx, [rsp+158h+var_C0]
0x14002f4ca  mov     rcx, rdi
0x14002f4cd  call    SmbCeTransact
0x14002f4d2  mov     ebx, eax
0x14002f4d4  mov     eax, [rsp+158h+var_6C]
0x14002f4db  mov     [rdi+0B8h], rax
0x14002f4e2  test    ebx, ebx
0x14002f4e4  js      short loc_14002F516
0x14002f4e6  mov     rcx, rdi
0x14002f4e9  call    MRxSmbInvalidateFileInfoCache
0x14002f4ee  mov     dl, 1
0x14002f4f0  mov     rcx, rdi
0x14002f4f3  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14002f4f8  btr     dword ptr [r15+9Ch], 12h
0x14002f501  mov     eax, dword ptr [rsp+158h+Length]
0x14002f508  cmp     [rdi+0B8h], rax
0x14002f50f  jbe     short loc_14002F516
0x14002f511  mov     ebx, 0C0000023h
0x14002f516  mov     eax, ebx
0x14002f518  test    eax, eax
0x14002f51a  jns     loc_14002F5DA
0x14002f520  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f527  lea     r15, WPP_GLOBAL_Control
0x14002f52e  cmp     rcx, r15
0x14002f531  jz      loc_14002F5E1
0x14002f537  test    dword ptr [rcx+2Ch], 400h
0x14002f53e  jz      loc_14002F5E1
0x14002f544  mov     edx, 1Eh
0x14002f549  mov     r9d, ebx
0x14002f54c  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x14002f553  mov     rcx, [rcx+18h]
0x14002f557  call    WPP_SF_d
0x14002f55c  jmp     loc_14002F5E1
0x14002f561  mov     ebx, 0C000000Dh
0x14002f566  jmp     loc_14002F44B
0x14002f56b  cmp     esi, 1401A3h
0x14002f571  jnz     loc_14002F44B
0x14002f577  lea     r15, WPP_GLOBAL_Control
0x14002f57e  cmp     esi, 1400ECh
0x14002f584  jnz     short loc_14002F5AC
0x14002f586  test    r12, r12
0x14002f589  jz      short loc_14002F59C
0x14002f58b  xor     edx, edx; Tag
0x14002f58d  mov     rcx, r12; P
0x14002f590  call    cs:__imp_ExFreePoolWithTag
0x14002f597  nop     dword ptr [rax+rax+00h]
0x14002f59c  mov     rax, [rsp+158h+var_C8]
0x14002f5a4  test    rax, rax
0x14002f5a7  jz      short loc_14002F5AC
0x14002f5a9  mov     [r14], rax
0x14002f5ac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f5b3  cmp     rcx, r15
0x14002f5b6  jz      short loc_14002F5D6
0x14002f5b8  test    dword ptr [rcx+2Ch], 400h
0x14002f5bf  jz      short loc_14002F5D6
0x14002f5c1  mov     edx, 1Fh
0x14002f5c6  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x14002f5cd  mov     rcx, [rcx+18h]
0x14002f5d1  call    WPP_SF_
0x14002f5d6  mov     eax, ebx
0x14002f5d8  jmp     short loc_14002F621
0x14002f5da  lea     r15, WPP_GLOBAL_Control
0x14002f5e1  cmp     esi, 900A8h
0x14002f5e7  jnz     short loc_14002F57E
0x14002f5e9  mov     ecx, 80000000h
0x14002f5ee  lea     eax, [rbx+rcx]
0x14002f5f1  test    ecx, eax
0x14002f5f3  jnz     short loc_14002F5FD
0x14002f5f5  cmp     ebx, 80000005h
0x14002f5fb  jnz     short loc_14002F57E
0x14002f5fd  mov     r8d, ebx
0x14002f600  mov     rdx, r13
0x14002f603  mov     ecx, [rdi+0B8h]
0x14002f609  call    cs:__imp_FsRtlValidateReparsePointBufferEx
0x14002f610  nop     dword ptr [rax+rax+00h]
0x14002f615  mov     ebx, eax
0x14002f617  jmp     loc_14002F57E
0x14002f61c  mov     eax, 0C0000010h
0x14002f621  add     rsp, 120h
0x14002f628  pop     r15
0x14002f62a  pop     r14
0x14002f62c  pop     r13
0x14002f62e  pop     r12
0x14002f630  pop     rdi
0x14002f631  pop     rsi
0x14002f632  pop     rbx
0x14002f633  retn
```
