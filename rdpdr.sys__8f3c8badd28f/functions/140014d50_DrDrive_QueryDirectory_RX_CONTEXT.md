# DrDrive::QueryDirectory(_RX_CONTEXT *)

- ea: `0x140014d50`
- end: `0x140015297`
- name: `?QueryDirectory@DrDrive@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `1351`
- prototype: `__int64 __fastcall(DrDrive *this, struct _RX_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x140001e30`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x140003428`
- `0x1400035a0`
- `0x140003624`
- `0x140006560`
- `0x1400065c0`
- `0x1400068c0`
- `0x140014d50`
- `0x1400152a0`
- `0x1400166b4`
- `0x140016870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140015103`
- `ntoskrnl!ExAllocatePool2` at `0x140015103`

## pseudocode

```c
__int64 __fastcall DrDrive::QueryDirectory(DrDrive *this, struct _RX_CONTEXT *a2, int a3)
{
  RefCount *v3; // rax
  struct _RX_CONTEXT *v4; // rbp
  int v5; // r10d
  DrDrive *v6; // rdx
  PMRX_FOBX pFobx; // r14
  unsigned int *v8; // rbx
  __int64 v9; // r9
  const void **p_Resource; // r13
  enum _FILE_INFORMATION_CLASS Flags; // r15d
  unsigned __int16 *p_pSrvOpen; // r14
  unsigned __int64 v14; // rcx
  int v15; // r8d
  int v16; // eax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // edx
  unsigned int v21; // r12d
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  __int64 v24; // rax
  int v25; // edx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int16 v29; // r8
  unsigned int DirectoryFromCache; // esi
  char *Pool2; // rax
  char *v32; // rdi
  unsigned __int64 v33; // rax
  unsigned int v34; // edx
  unsigned __int64 v35; // rax
  unsigned int v36; // edx
  unsigned int v37; // eax
  int v38; // [rsp+20h] [rbp-78h]
  RefCount *v39; // [rsp+40h] [rbp-58h] BYREF
  const void **v40; // [rsp+48h] [rbp-50h]
  int v43; // [rsp+B0h] [rbp+18h]
  unsigned int *v44; // [rsp+B8h] [rbp+20h] BYREF

  v3 = (RefCount *)*((_QWORD *)this + 4);
  v4 = a2;
  v5 = 0;
  v39 = v3;
  v6 = this;
  pFobx = v4->pFobx;
  if ( v3 )
    RefCount::AddRef(v3);
  v8 = *(unsigned int **)&v4->pFobx->OffsetOfNextEaToReturn;
  v44 = v8;
  if ( v8 )
    RefCount::AddRef((RefCount *)v8);
  if ( *((_DWORD *)v3 + 149) != 3 || !v8 )
    goto LABEL_11;
  v9 = *((unsigned int *)v6 + 14);
  if ( (_DWORD)v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v9);
LABEL_11:
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v44);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v39);
    return 3221225629LL;
  }
  p_Resource = (const void **)&v4->pFcb[2].Header.Resource;
  Flags = v4->LowIoContext.ParamsFor.Locks.Flags;
  p_pSrvOpen = (unsigned __int16 *)&pFobx[1].pSrvOpen;
  v40 = p_Resource;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_DDZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v6,
      a3,
      *((unsigned __int8 *)&v4->9 + 119),
      Flags,
      (__int64)p_Resource,
      (__int64)p_pSrvOpen);
    v5 = 0;
  }
  v14 = (unsigned int)(Flags - 1);
  if ( Flags != FileDirectoryInformation )
  {
    v14 = (unsigned int)(Flags - 2);
    if ( Flags != FileFullDirectoryInformation )
    {
      v14 = (unsigned int)(Flags - 3);
      if ( Flags != FileBothDirectoryInformation && Flags != FileNamesInformation )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
            (unsigned int)Flags);
        goto LABEL_36;
      }
    }
  }
  v15 = v5;
  v43 = v5;
  if ( *((_BYTE *)&v4->9 + 119) != (_BYTE)v5 )
  {
    v16 = *p_pSrvOpen;
    if ( !(_WORD)v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_36;
      v18 = 20;
LABEL_35:
      WPP_SF_(v17->AttachedDevice, v18, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_36:
      SmartPtr<DrFile>::~SmartPtr<DrFile>(&v44);
      SmartPtr<DrFile>::~SmartPtr<DrFile>(&v39);
      return 3221225485LL;
    }
    v19 = *(unsigned __int16 *)p_Resource;
    v20 = v19 + v16;
    if ( v19 > v19 + v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_36;
      v18 = 21;
      goto LABEL_35;
    }
    v21 = v20 + 62;
    if ( v20 >= 0xFFFFFFC2 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_36;
      v18 = 22;
      goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, p_pSrvOpen);
      v15 = v43;
    }
    v22 = *((_QWORD *)p_pSrvOpen + 1);
    v23 = (unsigned __int64)*p_pSrvOpen >> 1;
    if ( *(_WORD *)(v22 + 2 * v23 - 2) == 60 )
    {
      v15 = 1;
      *(_WORD *)(v22 + 2 * v23 - 2) = 42;
      v43 = 1;
    }
    v24 = *p_pSrvOpen >> 1;
    v25 = v24 - 1;
    if ( (int)v24 - 1 >= 0 )
    {
      v26 = v24 - 1;
      do
      {
        if ( v25 )
        {
          v27 = *((_QWORD *)p_pSrvOpen + 1);
          if ( *(_WORD *)(v27 + 2 * v26) == 46 && *(_WORD *)(v27 + 2 * v26 - 2) == 60 )
            *(_WORD *)(v27 + 2 * v26 - 2) = 42;
        }
        v28 = *((_QWORD *)p_pSrvOpen + 1);
        if ( *(_WORD *)(v28 + 2 * v26) == 62 )
        {
          *(_WORD *)(v28 + 2 * v26) = 63;
          v28 = *((_QWORD *)p_pSrvOpen + 1);
        }
        if ( v25 )
        {
          v29 = *(_WORD *)(v28 + 2 * v26);
          if ( (v29 == 63 || v29 == 42) && *(_WORD *)(v28 + 2 * v26 - 2) == 34 )
            *(_WORD *)(v28 + 2 * v26 - 2) = 46;
        }
        --v26;
        --v25;
      }
      while ( v25 >= 0 );
      v4 = a2;
      p_Resource = v40;
      v15 = v43;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_ZD(WPP_GLOBAL_Control->AttachedDevice, v25, v15, (_DWORD)p_pSrvOpen, v15);
    if ( (unsigned int)DrFile::CheckQueryDirPrefetchAllowed((DrFile *)v8) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v8[6], Flags);
      DrFile::CleanupQueryDirCache((DrFile *)v8, Flags);
    }
    goto LABEL_68;
  }
  if ( v8[12] == v5
    || (DirectoryFromCache = DrDrive::QueryDirectoryFromCache((DrDrive *)v14, v4, Flags),
        DirectoryFromCache == -1073741802) )
  {
    v21 = 56;
LABEL_68:
    Pool2 = (char *)ExAllocatePool2(256, v21, 1917088324);
    v32 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, v21);
      if ( *((_BYTE *)&v4->9 + 119) )
      {
        memmove(v32 + 56, p_Resource[1], *(unsigned __int16 *)p_Resource);
        v33 = (unsigned __int64)*(unsigned __int16 *)p_Resource >> 1;
        if ( *(_WORD *)&v32[2 * v33 + 54] == 92 )
        {
          memmove(&v32[*(unsigned __int16 *)p_Resource + 56], *((const void **)p_pSrvOpen + 1), *p_pSrvOpen);
          v34 = *(unsigned __int16 *)p_Resource + *p_pSrvOpen;
          v21 -= 2;
        }
        else
        {
          *(_WORD *)&v32[2 * v33 + 56] = 92;
          memmove(&v32[*(unsigned __int16 *)p_Resource + 58], *((const void **)p_pSrvOpen + 1), *p_pSrvOpen);
          v34 = *p_pSrvOpen + 2 + *(unsigned __int16 *)p_Resource;
        }
        if ( v43 )
        {
          v35 = (unsigned __int64)v34 >> 1;
          v34 += 2;
          *(_WORD *)&v32[2 * v35 + 56] = 46;
        }
        else
        {
          v21 -= 2;
        }
        v36 = v34 + 2;
      }
      else
      {
        v36 = 0;
      }
      *(_DWORD *)v32 = 1230128242;
      *((_DWORD *)v32 + 1) = *((_DWORD *)this + 10);
      *((_DWORD *)v32 + 2) = v8[6];
      *((_DWORD *)v32 + 4) = 12;
      v37 = v8[12];
      *((_DWORD *)v32 + 6) = Flags;
      if ( v37 )
      {
        *((_DWORD *)v32 + 5) = 240;
        *((_DWORD *)v32 + 7) = v8[13];
        v32[32] = *((_BYTE *)&v4->9 + 119);
        *(_DWORD *)(v32 + 33) = v36;
      }
      else
      {
        *((_DWORD *)v32 + 5) = 1;
        v32[28] = *((_BYTE *)&v4->9 + 119);
        *(_DWORD *)(v32 + 29) = v36;
      }
      LOBYTE(v38) = ((__int64)v4->RdbssDbgExtension & 0x1000) == 0;
      DirectoryFromCache = (*(__int64 (__fastcall **)(DrDrive *, struct _RX_CONTEXT *, char *, _QWORD, int, union _LARGE_INTEGER *, _DWORD))(*(_QWORD *)this + 24LL))(
                             this,
                             v4,
                             v32,
                             v21,
                             v38,
                             &g_IOTimeOut,
                             0);
      operator delete(v32);
    }
    else
    {
      DirectoryFromCache = -1073741670;
    }
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v44);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v39);
  return DirectoryFromCache;
}

```

## disassembly

```asm
0x140014d50  mov     [rsp+arg_8], rdx
0x140014d55  mov     [rsp+arg_0], rcx
0x140014d5a  push    rbx
0x140014d5b  push    rbp
0x140014d5c  push    rsi
0x140014d5d  push    rdi
0x140014d5e  push    r12
0x140014d60  push    r13
0x140014d62  push    r14
0x140014d64  push    r15
0x140014d66  sub     rsp, 58h
0x140014d6a  mov     rax, [rcx+20h]
0x140014d6e  mov     rbp, rdx
0x140014d71  xor     r10d, r10d
0x140014d74  mov     [rsp+98h+var_58], rax
0x140014d79  mov     rdx, rcx
0x140014d7c  mov     r14, [rbp+40h]
0x140014d80  test    rax, rax
0x140014d83  jz      short loc_140014D8D
0x140014d85  mov     rcx, rax; this
0x140014d88  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140014d8d  mov     rbx, [rbp+40h]
0x140014d91  mov     rbx, [rbx+40h]
0x140014d95  mov     [rsp+98h+arg_18], rbx
0x140014d9d  test    rbx, rbx
0x140014da0  jz      short loc_140014DAA
0x140014da2  mov     rcx, rbx; this
0x140014da5  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140014daa  cmp     dword ptr [rax+254h], 3
0x140014db1  jnz     short loc_140014DF2
0x140014db3  test    rbx, rbx
0x140014db6  jz      short loc_140014DF2
0x140014db8  mov     r9d, [rdx+38h]
0x140014dbc  test    r9d, r9d
0x140014dbf  jz      short loc_140014E20
0x140014dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dc8  lea     rsi, WPP_GLOBAL_Control
0x140014dcf  cmp     rcx, rsi
0x140014dd2  jz      short loc_140014DF2
0x140014dd4  mov     dil, 5
0x140014dd7  cmp     [rcx+29h], dil
0x140014ddb  jb      short loc_140014DF2
0x140014ddd  mov     rcx, [rcx+18h]
0x140014de1  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014de8  mov     edx, 11h
0x140014ded  call    WPP_SF_d
0x140014df2  lea     rcx, [rsp+98h+arg_18]
0x140014dfa  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014dff  lea     rcx, [rsp+98h+var_58]
0x140014e04  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014e09  mov     eax, 0C000009Dh
0x140014e0e  add     rsp, 58h
0x140014e12  pop     r15
0x140014e14  pop     r14
0x140014e16  pop     r13
0x140014e18  pop     r12
0x140014e1a  pop     rdi
0x140014e1b  pop     rsi
0x140014e1c  pop     rbp
0x140014e1d  pop     rbx
0x140014e1e  retn
0x140014e20  mov     r13, [rbp+38h]
0x140014e24  lea     rsi, WPP_GLOBAL_Control
0x140014e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e32  add     r13, 168h
0x140014e39  mov     r15d, [rbp+1C0h]
0x140014e40  add     r14, 50h ; 'P'
0x140014e44  mov     [rsp+98h+var_50], r13
0x140014e49  mov     dil, 5
0x140014e4c  cmp     rcx, rsi
0x140014e4f  jz      short loc_140014E7A
0x140014e51  cmp     [rcx+29h], dil
0x140014e55  jb      short loc_140014E7A
0x140014e57  movzx   r9d, byte ptr [rbp+207h]
0x140014e5f  mov     rcx, [rcx+18h]
0x140014e63  mov     [rsp+98h+var_68], r14
0x140014e68  mov     [rsp+98h+var_70], r13
0x140014e6d  mov     [rsp+98h+var_78], r15d
0x140014e72  call    WPP_SF_DDZZ
0x140014e77  xor     r10d, r10d
0x140014e7a  mov     ecx, r15d
0x140014e7d  sub     ecx, 1; this
0x140014e80  jz      short loc_140014EC8
0x140014e82  sub     ecx, 1
0x140014e85  jz      short loc_140014EC8
0x140014e87  sub     ecx, 1
0x140014e8a  jz      short loc_140014EC8
0x140014e8c  cmp     ecx, 9
0x140014e8f  jz      short loc_140014EC8
0x140014e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e98  cmp     rcx, rsi
0x140014e9b  jz      loc_140014F58
0x140014ea1  cmp     [rcx+29h], dil
0x140014ea5  jb      loc_140014F58
0x140014eab  mov     rcx, [rcx+18h]
0x140014eaf  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014eb6  mov     edx, 13h
0x140014ebb  mov     r9d, r15d
0x140014ebe  call    WPP_SF_d
0x140014ec3  jmp     loc_140014F58
0x140014ec8  mov     r8d, r10d
0x140014ecb  mov     [rsp+98h+arg_10], r10d
0x140014ed3  cmp     [rbp+207h], r10b
0x140014eda  jz      loc_1400150CE
0x140014ee0  movzx   eax, word ptr [r14]
0x140014ee4  test    ax, ax
0x140014ee7  jnz     short loc_140014F02
0x140014ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ef0  cmp     rcx, rsi
0x140014ef3  jz      short loc_140014F58
0x140014ef5  cmp     [rcx+29h], dil
0x140014ef9  jb      short loc_140014F58
0x140014efb  mov     edx, 14h
0x140014f00  jmp     short loc_140014F48
0x140014f02  movzx   ecx, word ptr [r13+0]
0x140014f07  lea     edx, [rcx+rax]
0x140014f0a  cmp     ecx, edx
0x140014f0c  jbe     short loc_140014F27
0x140014f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f15  cmp     rcx, rsi
0x140014f18  jz      short loc_140014F58
0x140014f1a  cmp     [rcx+29h], dil
0x140014f1e  jb      short loc_140014F58
0x140014f20  mov     edx, 15h
0x140014f25  jmp     short loc_140014F48
0x140014f27  lea     r12d, [rdx+3Eh]
0x140014f2b  cmp     r12d, 3Eh ; '>'
0x140014f2f  jnb     short loc_140014F79
0x140014f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f38  cmp     rcx, rsi
0x140014f3b  jz      short loc_140014F58
0x140014f3d  cmp     [rcx+29h], dil
0x140014f41  jb      short loc_140014F58
0x140014f43  mov     edx, 16h
0x140014f48  mov     rcx, [rcx+18h]
0x140014f4c  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014f53  call    WPP_SF_
0x140014f58  lea     rcx, [rsp+98h+arg_18]
0x140014f60  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014f65  lea     rcx, [rsp+98h+var_58]
0x140014f6a  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014f6f  mov     eax, 0C000000Dh
0x140014f74  jmp     loc_140014E0E
0x140014f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f80  cmp     rcx, rsi
0x140014f83  jz      short loc_140014FAB
0x140014f85  cmp     [rcx+29h], dil
0x140014f89  jb      short loc_140014FAB
0x140014f8b  mov     rcx, [rcx+18h]
0x140014f8f  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014f96  mov     edx, 17h
0x140014f9b  mov     r9, r14
0x140014f9e  call    WPP_SF_Z
0x140014fa3  mov     r8d, [rsp+98h+arg_10]
0x140014fab  movzx   eax, word ptr [r14]
0x140014faf  mov     r9d, 2Ah ; '*'
0x140014fb5  mov     rcx, [r14+8]
0x140014fb9  shr     rax, 1
0x140014fbc  cmp     word ptr [rcx+rax*2-2], 3Ch ; '<'
0x140014fc2  jnz     short loc_140014FD6
0x140014fc4  lea     r8d, [r9-29h]
0x140014fc8  mov     [rcx+rax*2-2], r9w
0x140014fce  mov     [rsp+98h+arg_10], r8d
0x140014fd6  movzx   eax, word ptr [r14]
0x140014fda  shr     eax, 1
0x140014fdc  lea     edx, [rax-1]
0x140014fdf  test    edx, edx
0x140014fe1  js      short loc_140015062
0x140014fe3  mov     ebp, 2Eh ; '.'
0x140014fe8  dec     rax
0x140014feb  lea     r11d, [rbp+11h]
0x140014fef  lea     r13d, [rbp+10h]
0x140014ff3  test    edx, edx
0x140014ff5  jz      short loc_14001500F
0x140014ff7  mov     rcx, [r14+8]
0x140014ffb  cmp     [rcx+rax*2], bp
0x140014fff  jnz     short loc_14001500F
0x140015001  cmp     word ptr [rcx+rax*2-2], 3Ch ; '<'
0x140015007  jnz     short loc_14001500F
0x140015009  mov     [rcx+rax*2-2], r9w
0x14001500f  mov     rcx, [r14+8]
0x140015013  cmp     [rcx+rax*2], r13w
0x140015018  jnz     short loc_140015023
0x14001501a  mov     [rcx+rax*2], r11w
0x14001501f  mov     rcx, [r14+8]
0x140015023  test    edx, edx
0x140015025  jz      short loc_140015045
0x140015027  movzx   r8d, word ptr [rcx+rax*2]
0x14001502c  cmp     r8w, r11w
0x140015030  jz      short loc_140015038
0x140015032  cmp     r8w, r9w
0x140015036  jnz     short loc_140015045
0x140015038  cmp     word ptr [rcx+rax*2-2], 22h ; '"'
0x14001503e  jnz     short loc_140015045
0x140015040  mov     [rcx+rax*2-2], bp
0x140015045  dec     rax
0x140015048  sub     edx, 1
0x14001504b  jns     short loc_140014FF3
0x14001504d  mov     rbp, [rsp+98h+arg_8]
0x140015055  mov     r13, [rsp+98h+var_50]
0x14001505a  mov     r8d, [rsp+98h+arg_10]
0x140015062  mov     rcx, cs:WPP_GLOBAL_Control
0x140015069  cmp     rcx, rsi
0x14001506c  jz      short loc_140015085
0x14001506e  cmp     [rcx+29h], dil
0x140015072  jb      short loc_140015085
0x140015074  mov     rcx, [rcx+18h]
0x140015078  mov     r9, r14
0x14001507b  mov     [rsp+98h+var_78], r8d
0x140015080  call    WPP_SF_ZD
0x140015085  mov     rcx, rbx; this
0x140015088  call    ?CheckQueryDirPrefetchAllowed@DrFile@@QEAAHXZ; DrFile::CheckQueryDirPrefetchAllowed(void)
0x14001508d  test    eax, eax
0x14001508f  jz      short loc_1400150F2
0x140015091  mov     rcx, cs:WPP_GLOBAL_Control
0x140015098  cmp     rcx, rsi
0x14001509b  jz      short loc_1400150C1
0x14001509d  cmp     [rcx+29h], dil
0x1400150a1  jb      short loc_1400150C1
0x1400150a3  mov     r9d, [rbx+18h]
0x1400150a7  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400150ae  mov     rcx, [rcx+18h]
0x1400150b2  mov     edx, 19h
0x1400150b7  mov     [rsp+98h+var_78], r15d
0x1400150bc  call    WPP_SF_dd
0x1400150c1  mov     edx, r15d; enum _FILE_INFORMATION_CLASS
0x1400150c4  mov     rcx, rbx; this
0x1400150c7  call    ?CleanupQueryDirCache@DrFile@@QEAAXW4_FILE_INFORMATION_CLASS@@@Z; DrFile::CleanupQueryDirCache(_FILE_INFORMATION_CLASS)
0x1400150cc  jmp     short loc_1400150F2
0x1400150ce  cmp     [rbx+30h], r10d
0x1400150d2  jz      short loc_1400150EC
0x1400150d4  mov     r8d, r15d; enum _FILE_INFORMATION_CLASS
0x1400150d7  mov     rdx, rbp; struct _RX_CONTEXT *
0x1400150da  call    ?QueryDirectoryFromCache@DrDrive@@IEAAJPEAU_RX_CONTEXT@@W4_FILE_INFORMATION_CLASS@@@Z; DrDrive::QueryDirectoryFromCache(_RX_CONTEXT *,_FILE_INFORMATION_CLASS)
0x1400150df  mov     esi, eax
0x1400150e1  cmp     eax, 0C0000016h
0x1400150e6  jnz     loc_140015279
0x1400150ec  mov     r12d, 38h ; '8'
0x1400150f2  mov     r8d, 72447244h
0x1400150f8  mov     edx, r12d
0x1400150fb  mov     ecx, 100h
0x140015100  mov     esi, r12d
0x140015103  call    cs:__imp_ExAllocatePool2
0x14001510a  nop     dword ptr [rax+rax+00h]
0x14001510f  mov     rdi, rax
0x140015112  test    rax, rax
0x140015115  jz      loc_140015274
0x14001511b  mov     r8d, esi; Size
0x14001511e  xor     edx, edx; Val
0x140015120  mov     rcx, rax; void *
0x140015123  call    memset
0x140015128  xor     esi, esi
0x14001512a  cmp     [rbp+207h], sil
0x140015131  jz      loc_1400151D4
0x140015137  movzx   r8d, word ptr [r13+0]; Size
0x14001513c  lea     rcx, [rdi+38h]; void *
0x140015140  mov     rdx, [r13+8]; Src
0x140015144  call    memmove
0x140015149  movzx   ecx, word ptr [r13+0]
0x14001514e  lea     r8d, [rsi+5Ch]
0x140015152  mov     eax, ecx
0x140015154  shr     rax, 1
0x140015157  cmp     [rdi+rax*2+36h], r8w
0x14001515d  jz      short loc_14001518E
0x14001515f  mov     [rdi+rax*2+38h], r8w
0x140015165  movzx   ecx, word ptr [r13+0]
0x14001516a  movzx   r8d, word ptr [r14]; Size
0x14001516e  add     rcx, 3Ah ; ':'
0x140015172  mov     rdx, [r14+8]; Src
0x140015176  add     rcx, rdi; void *
0x140015179  call    memmove
0x14001517e  movzx   ecx, word ptr [r14]
0x140015182  movzx   edx, word ptr [r13+0]
0x140015187  add     ecx, 2
0x14001518a  add     edx, ecx
0x14001518c  jmp     short loc_1400151B1
0x14001518e  movzx   r8d, word ptr [r14]; Size
0x140015192  add     rcx, 38h ; '8'
0x140015196  mov     rdx, [r14+8]; Src
0x14001519a  add     rcx, rdi; void *
0x14001519d  call    memmove
0x1400151a2  movzx   edx, word ptr [r14]
0x1400151a6  movzx   eax, word ptr [r13+0]
0x1400151ab  add     edx, eax
0x1400151ad  add     r12d, 0FFFFFFFEh
0x1400151b1  cmp     [rsp+98h+arg_10], esi
0x1400151b8  jz      short loc_1400151CB
0x1400151ba  mov     eax, edx
0x1400151bc  shr     rax, 1
0x1400151bf  add     edx, 2
0x1400151c2  mov     word ptr [rdi+rax*2+38h], 2Eh ; '.'
0x1400151c9  jmp     short loc_1400151CF
0x1400151cb  add     r12d, 0FFFFFFFEh
0x1400151cf  add     edx, 2
0x1400151d2  jmp     short loc_1400151D6
0x1400151d4  mov     edx, esi
0x1400151d6  mov     r10, [rsp+98h+arg_0]
0x1400151de  mov     dword ptr [rdi], 49524472h
0x1400151e4  mov     eax, [r10+28h]
0x1400151e8  mov     [rdi+4], eax
  ... truncated ...
```
