# CRTFWrite::GetRtfObject(_reobject &,_rtfobject &)

- ea: `0x18007fbac`
- end: `0x18007fd32`
- name: `?GetRtfObject@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z`
- size: `390`
- prototype: `int(CRTFWrite *__hidden this, struct _reobject *, struct _rtfobject *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080698`

## callees

- `0x180039990`
- `0x1800427ac`
- `0x18004bac8`
- `0x18007fbac`
- `0x18007fd38`
- `0x18008ed4c`
- `0x1800931b0`
- `0x180093bca`
- `0x180095010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18007fc83`
- `KERNEL32!GlobalLock` at `0x18007fc83`
- `KERNEL32!GlobalUnlock` at `0x18007fcac`
- `KERNEL32!GlobalUnlock` at `0x18007fcac`
- `GDI32!DeleteMetaFile` at `0x18007fc9d`
- `GDI32!DeleteMetaFile` at `0x18007fc9d`

## string_xrefs

- `0x18007fc1a`: `ProgIDFromCLSID`

## pseudocode

```c
__int64 __fastcall CRTFWrite::GetRtfObject(CRTFWrite *this, struct _reobject *a2, struct _rtfobject *a3)
{
  DWORD dwFlags; // ebp
  int v6; // ebp
  struct tagDVTARGETDEVICE *v7; // r9
  unsigned int RtfObjectMetafilePict; // r15d
  int v9; // esi
  struct COLE32_PROC *Ole32Procs; // rax
  unsigned int (__fastcall **v11)(CLSID *, __int64 *); // r14
  void *MetafilePictFromOleObject; // rax
  CRTFWrite *v13; // rcx
  void *v14; // rbx
  LPVOID v15; // rax
  HMETAFILE v16; // rcx
  LONG cx; // ecx
  struct tagSIZE sizel; // [rsp+50h] [rbp+8h] BYREF
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  sizel = (struct tagSIZE)this;
  dwFlags = a2->dwFlags;
  sizel = a2->sizel;
  v20 = 0;
  v6 = dwFlags & 0x40000000;
  memset_0(a3, 0, 0x60u);
  if ( !a2->pstg )
    return 0;
  RtfObjectMetafilePict = 0;
  v9 = 0;
  if ( !v6 )
  {
    Ole32Procs = CThreadData::GetOle32Procs();
    v11 = (unsigned int (__fastcall **)(CLSID *, __int64 *))((char *)Ole32Procs + 40);
    if ( !*((_QWORD *)Ole32Procs + 5) )
      SetProcAddr((char *)Ole32Procs + 40, 1, "ProgIDFromCLSID");
    if ( !*v11 || (*v11)(&a2->clsid, &v20) )
      v9 = 1;
    else
      *((_QWORD *)a3 + 7) = v20;
  }
  MetafilePictFromOleObject = OleStdGetMetafilePictFromOleObject(a2->poleobj, a2->dvaspect, &sizel, v7);
  v14 = MetafilePictFromOleObject;
  if ( MetafilePictFromOleObject )
  {
    RtfObjectMetafilePict = CRTFWrite::GetRtfObjectMetafilePict(v13, MetafilePictFromOleObject, a3, &sizel);
    v15 = GlobalLock(v14);
    if ( v15 )
    {
      v16 = (HMETAFILE)*((_QWORD *)v15 + 2);
      if ( v16 )
        DeleteMetaFile(v16);
      GlobalUnlock(v14);
    }
    CW32System::GlobalFree(v14);
    if ( !RtfObjectMetafilePict )
    {
      if ( v9 )
        return 0;
    }
  }
  if ( !v6 )
  {
    cx = sizel.cx;
    *(_WORD *)a3 = 2 * (v9 ^ 1) + 1;
    *((_DWORD *)a3 + 4) = (__int16)CW32System::MulDiv(cx, 72, 127);
    RtfObjectMetafilePict = 1;
    *((_DWORD *)a3 + 5) = (__int16)CW32System::MulDiv(sizel.cy, 72, 127);
  }
  *((_DWORD *)a3 + 3) = 0;
  return RtfObjectMetafilePict;
}

```

## disassembly

```asm
0x18007fbac  mov     r11, rsp
0x18007fbaf  mov     [r11+18h], rbx
0x18007fbb3  mov     [r11+20h], rbp
0x18007fbb7  mov     [r11+8], rcx
0x18007fbbb  push    rsi
0x18007fbbc  push    rdi
0x18007fbbd  push    r13
0x18007fbbf  push    r14
0x18007fbc1  push    r15
0x18007fbc3  sub     rsp, 20h
0x18007fbc7  mov     ebp, [rdx+3Ch]
0x18007fbca  mov     rdi, r8
0x18007fbcd  mov     rax, [rdx+30h]
0x18007fbd1  mov     rbx, rdx
0x18007fbd4  xor     edx, edx; Val
0x18007fbd6  mov     [r11+8], rax
0x18007fbda  mov     rcx, rdi; void *
0x18007fbdd  mov     qword ptr [r11+10h], 0
0x18007fbe5  and     ebp, 40000000h
0x18007fbeb  lea     r8d, [rdx+60h]; Size
0x18007fbef  call    memset_0
0x18007fbf4  cmp     qword ptr [rbx+20h], 0
0x18007fbf9  jz      loc_18007FD18
0x18007fbff  xor     r15d, r15d
0x18007fc02  xor     esi, esi
0x18007fc04  lea     r13d, [r15+1]
0x18007fc08  test    ebp, ebp
0x18007fc0a  jnz     short loc_18007FC54
0x18007fc0c  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007fc11  lea     r14, [rax+28h]
0x18007fc15  cmp     [r14], rsi
0x18007fc18  jnz     short loc_18007FC2C
0x18007fc1a  lea     r8, aProgidfromclsi; "ProgIDFromCLSID"
0x18007fc21  mov     edx, r13d
0x18007fc24  mov     rcx, r14
0x18007fc27  call    SetProcAddr
0x18007fc2c  mov     rax, [r14]
0x18007fc2f  test    rax, rax
0x18007fc32  jz      short loc_18007FC51
0x18007fc34  lea     rcx, [rbx+8]
0x18007fc38  lea     rdx, [rsp+48h+arg_8]
0x18007fc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc42  test    eax, eax
0x18007fc44  jnz     short loc_18007FC51
0x18007fc46  mov     rax, [rsp+48h+arg_8]
0x18007fc4b  mov     [rdi+38h], rax
0x18007fc4f  jmp     short loc_18007FC54
0x18007fc51  mov     esi, r13d
0x18007fc54  mov     edx, [rbx+38h]; unsigned int
0x18007fc57  lea     r8, [rsp+48h+arg_0]; struct tagSIZE *
0x18007fc5c  mov     rcx, [rbx+18h]; struct IOleObject *
0x18007fc60  call    ?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@KPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@@Z; OleStdGetMetafilePictFromOleObject(IOleObject *,ulong,tagSIZE *,tagDVTARGETDEVICE *)
0x18007fc65  mov     rbx, rax
0x18007fc68  test    rax, rax
0x18007fc6b  jz      short loc_18007FCC9
0x18007fc6d  lea     r9, [rsp+48h+arg_0]; struct tagSIZE *
0x18007fc72  mov     r8, rdi; struct _rtfobject *
0x18007fc75  mov     rdx, rax; void *
0x18007fc78  call    ?GetRtfObjectMetafilePict@CRTFWrite@@AEAAHPEAXAEAU_rtfobject@@AEAUtagSIZE@@@Z; CRTFWrite::GetRtfObjectMetafilePict(void *,_rtfobject &,tagSIZE &)
0x18007fc7d  mov     rcx, rbx; hMem
0x18007fc80  mov     r15d, eax
0x18007fc83  call    cs:__imp_GlobalLock
0x18007fc8a  nop     dword ptr [rax+rax+00h]
0x18007fc8f  test    rax, rax
0x18007fc92  jz      short loc_18007FCB8
0x18007fc94  mov     rcx, [rax+10h]; hmf
0x18007fc98  test    rcx, rcx
0x18007fc9b  jz      short loc_18007FCA9
0x18007fc9d  call    cs:__imp_DeleteMetaFile
0x18007fca4  nop     dword ptr [rax+rax+00h]
0x18007fca9  mov     rcx, rbx; hMem
0x18007fcac  call    cs:__imp_GlobalUnlock
0x18007fcb3  nop     dword ptr [rax+rax+00h]
0x18007fcb8  mov     rcx, rbx; void *
0x18007fcbb  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007fcc0  test    r15d, r15d
0x18007fcc3  jnz     short loc_18007FCC9
0x18007fcc5  test    esi, esi
0x18007fcc7  jnz     short loc_18007FD18
0x18007fcc9  test    ebp, ebp
0x18007fccb  jnz     short loc_18007FD0C
0x18007fccd  mov     ecx, [rsp+48h+arg_0.cx]; int
0x18007fcd1  lea     ebx, [rbp+48h]
0x18007fcd4  xor     si, r13w
0x18007fcd8  mov     edx, ebx; int
0x18007fcda  add     si, si
0x18007fcdd  add     si, r13w
0x18007fce1  mov     [rdi], si
0x18007fce4  lea     esi, [rbp+7Fh]
0x18007fce7  mov     r8d, esi; int
0x18007fcea  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007fcef  movsx   ecx, ax
0x18007fcf2  mov     r8d, esi; int
0x18007fcf5  mov     [rdi+10h], ecx
0x18007fcf8  mov     edx, ebx; int
0x18007fcfa  mov     ecx, [rsp+48h+arg_0.cy]; int
0x18007fcfe  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007fd03  movsx   ecx, ax
0x18007fd06  mov     r15d, r13d
0x18007fd09  mov     [rdi+14h], ecx
0x18007fd0c  mov     dword ptr [rdi+0Ch], 0
0x18007fd13  mov     eax, r15d
0x18007fd16  jmp     short loc_18007FD1A
0x18007fd18  xor     eax, eax
0x18007fd1a  mov     rbx, [rsp+48h+arg_10]
0x18007fd1f  mov     rbp, [rsp+48h+arg_18]
0x18007fd24  add     rsp, 20h
0x18007fd28  pop     r15
0x18007fd2a  pop     r14
0x18007fd2c  pop     r13
0x18007fd2e  pop     rdi
0x18007fd2f  pop     rsi
0x18007fd30  retn
```
