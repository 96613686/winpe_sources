# DrDrive::QueryDirectoryFromCache(_RX_CONTEXT *,_FILE_INFORMATION_CLASS)

- ea: `0x1400152a0`
- end: `0x14001548f`
- name: `?QueryDirectoryFromCache@DrDrive@@IEAAJPEAU_RX_CONTEXT@@W4_FILE_INFORMATION_CLASS@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(DrDrive *this, struct _RX_CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140014d50`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x1400032c0`
- `0x140003314`
- `0x14001285c`
- `0x140012a3c`
- `0x140012bf4`
- `0x140012db0`
- `0x1400152a0`
- `0x1400168f0`

## pseudocode

```c
__int64 __fastcall DrDrive::QueryDirectoryFromCache(DrDrive *this, struct _RX_CONTEXT *a2, unsigned int a3)
{
  PMRX_FOBX pFobx; // rbx
  unsigned int *v6; // rbx
  struct tagRDPDR_QUERYDIR_CACHE_ENTRY *CurrentQueryDirCacheEntry; // rax
  struct tagRDPDR_QUERYDIR_CACHE_ENTRY *v8; // r8
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  DrDrive *v13; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v14; // [rsp+78h] [rbp+38h] BYREF
  unsigned int *v15; // [rsp+88h] [rbp+48h] BYREF

  v13 = this;
  pFobx = a2->pFobx;
  LODWORD(v13) = -1073741823;
  v14 = 0;
  v6 = *(unsigned int **)&pFobx->OffsetOfNextEaToReturn;
  v15 = v6;
  if ( v6 )
    RefCount::AddRef((RefCount *)v6);
  CurrentQueryDirCacheEntry = DrFile::GetCurrentQueryDirCacheEntry((DrFile *)v6, a3);
  v8 = CurrentQueryDirCacheEntry;
  if ( CurrentQueryDirCacheEntry )
  {
    switch ( a3 )
    {
      case 1u:
        v10 = DrDrive::OnFileDirectoryInformation(
                (DrDrive *)&v13,
                a2,
                *((_DWORD *)CurrentQueryDirCacheEntry + 1),
                (unsigned __int8 *)CurrentQueryDirCacheEntry + 8,
                *(_DWORD *)CurrentQueryDirCacheEntry - 8,
                (int *)&v13,
                &v14);
        break;
      case 2u:
        v10 = DrDrive::OnFileFullDirectoryInformation(
                (DrDrive *)&v13,
                a2,
                *((_DWORD *)CurrentQueryDirCacheEntry + 1),
                (unsigned __int8 *)CurrentQueryDirCacheEntry + 8,
                *(_DWORD *)CurrentQueryDirCacheEntry - 8,
                (int *)&v13,
                &v14);
        break;
      case 3u:
        v10 = DrDrive::OnFileBothDirectoryInformation(
                (DrDrive *)&v13,
                a2,
                *((_DWORD *)CurrentQueryDirCacheEntry + 1),
                (unsigned __int8 *)CurrentQueryDirCacheEntry + 8,
                *(_DWORD *)CurrentQueryDirCacheEntry - 8,
                (int *)&v13,
                &v14);
        break;
      case 0xCu:
        v10 = DrDrive::OnFileNamesInformation(
                (DrDrive *)&v13,
                a2,
                *((_DWORD *)CurrentQueryDirCacheEntry + 1),
                (unsigned __int8 *)CurrentQueryDirCacheEntry + 8,
                *(_DWORD *)CurrentQueryDirCacheEntry - 8,
                (int *)&v13,
                &v14);
        break;
      default:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v6[6], a3);
        v9 = 3221225485LL;
        goto LABEL_17;
    }
    v9 = v10;
LABEL_17:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_DDDDD(WPP_GLOBAL_Control->AttachedDevice, v9, v8, v6[6], a3, v9, (_DWORD)v13, v14);
    v11 = (unsigned int)v13;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v6[6], a3);
  v11 = -1073741802;
LABEL_25:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v15);
  return v11;
}

```

## disassembly

```asm
0x1400152a0  mov     [rsp-28h+arg_0], rcx
0x1400152a5  push    rbp
0x1400152a6  push    rbx
0x1400152a7  push    rsi
0x1400152a8  push    rdi
0x1400152a9  push    r14
0x1400152ab  mov     rbp, rsp
0x1400152ae  sub     rsp, 40h
0x1400152b2  mov     rbx, [rdx+40h]
0x1400152b6  mov     edi, r8d
0x1400152b9  mov     r14, rdx
0x1400152bc  mov     dword ptr [rbp+arg_0], 0C0000001h
0x1400152c3  mov     [rbp+arg_8], 0
0x1400152ca  mov     rbx, [rbx+40h]
0x1400152ce  mov     [rbp+arg_18], rbx
0x1400152d2  test    rbx, rbx
0x1400152d5  jz      short loc_1400152DF
0x1400152d7  mov     rcx, rbx; this
0x1400152da  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400152df  mov     edx, edi; enum _FILE_INFORMATION_CLASS
0x1400152e1  mov     rcx, rbx; this
0x1400152e4  call    ?GetCurrentQueryDirCacheEntry@DrFile@@QEAAPEAUtagRDPDR_QUERYDIR_CACHE_ENTRY@@W4_FILE_INFORMATION_CLASS@@@Z; DrFile::GetCurrentQueryDirCacheEntry(_FILE_INFORMATION_CLASS)
0x1400152e9  lea     rsi, WPP_GLOBAL_Control
0x1400152f0  mov     r8, rax
0x1400152f3  test    rax, rax
0x1400152f6  jz      loc_140015444
0x1400152fc  mov     edx, edi
0x1400152fe  sub     edx, 1
0x140015301  jz      loc_1400153DD
0x140015307  sub     edx, 1
0x14001530a  jz      loc_1400153B0
0x140015310  sub     edx, 1
0x140015313  jz      short loc_140015383
0x140015315  cmp     edx, 9
0x140015318  jz      short loc_140015353
0x14001531a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015321  cmp     rcx, rsi
0x140015324  jz      short loc_140015349
0x140015326  cmp     byte ptr [rcx+29h], 2
0x14001532a  jb      short loc_140015349
0x14001532c  mov     r9d, [rbx+18h]
0x140015330  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140015337  mov     rcx, [rcx+18h]
0x14001533b  mov     edx, 1Ah
0x140015340  mov     [rsp+40h+var_20], edi
0x140015344  call    WPP_SF_dd
0x140015349  mov     edx, 0C000000Dh
0x14001534e  jmp     loc_14001540A
0x140015353  mov     eax, [rax]
0x140015355  lea     rcx, [rbp+arg_8]
0x140015359  mov     [rsp+40h+var_10], rcx; unsigned int *
0x14001535e  lea     r9, [r8+8]; unsigned __int8 *
0x140015362  mov     r8d, [r8+4]; int
0x140015366  lea     rcx, [rbp+arg_0]; this
0x14001536a  sub     eax, 8
0x14001536d  mov     [rsp+40h+var_18], rcx; int *
0x140015372  mov     rdx, r14; struct _RX_CONTEXT *
0x140015375  mov     [rsp+40h+var_20], eax; unsigned int
0x140015379  call    ?OnFileNamesInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileNamesInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x14001537e  jmp     loc_140015408
0x140015383  mov     eax, [rax]
0x140015385  lea     rcx, [rbp+arg_8]
0x140015389  mov     [rsp+40h+var_10], rcx; unsigned int *
0x14001538e  lea     r9, [r8+8]; unsigned __int8 *
0x140015392  mov     r8d, [r8+4]; int
0x140015396  lea     rcx, [rbp+arg_0]; this
0x14001539a  sub     eax, 8
0x14001539d  mov     [rsp+40h+var_18], rcx; int *
0x1400153a2  mov     rdx, r14; struct _RX_CONTEXT *
0x1400153a5  mov     [rsp+40h+var_20], eax; unsigned int
0x1400153a9  call    ?OnFileBothDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileBothDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x1400153ae  jmp     short loc_140015408
0x1400153b0  mov     eax, [rax]
0x1400153b2  lea     rcx, [rbp+arg_8]
0x1400153b6  mov     [rsp+40h+var_10], rcx; unsigned int *
0x1400153bb  lea     r9, [r8+8]; unsigned __int8 *
0x1400153bf  mov     r8d, [r8+4]; int
0x1400153c3  lea     rcx, [rbp+arg_0]; this
0x1400153c7  sub     eax, 8
0x1400153ca  mov     [rsp+40h+var_18], rcx; int *
0x1400153cf  mov     rdx, r14; struct _RX_CONTEXT *
0x1400153d2  mov     [rsp+40h+var_20], eax; unsigned int
0x1400153d6  call    ?OnFileFullDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileFullDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x1400153db  jmp     short loc_140015408
0x1400153dd  mov     eax, [rax]
0x1400153df  lea     rcx, [rbp+arg_8]
0x1400153e3  mov     [rsp+40h+var_10], rcx; unsigned int *
0x1400153e8  lea     r9, [r8+8]; unsigned __int8 *
0x1400153ec  mov     r8d, [r8+4]; int
0x1400153f0  lea     rcx, [rbp+arg_0]; this
0x1400153f4  sub     eax, 8
0x1400153f7  mov     [rsp+40h+var_18], rcx; int *
0x1400153fc  mov     rdx, r14; struct _RX_CONTEXT *
0x1400153ff  mov     [rsp+40h+var_20], eax; unsigned int
0x140015403  call    ?OnFileDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x140015408  mov     edx, eax
0x14001540a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015411  cmp     rcx, rsi
0x140015414  jz      short loc_14001543F
0x140015416  cmp     byte ptr [rcx+29h], 5
0x14001541a  jb      short loc_14001543F
0x14001541c  mov     eax, [rbp+arg_8]
0x14001541f  mov     r9d, [rbx+18h]
0x140015423  mov     rcx, [rcx+18h]
0x140015427  mov     [rsp+40h+var_8], eax
0x14001542b  mov     eax, dword ptr [rbp+arg_0]
0x14001542e  mov     dword ptr [rsp+40h+var_10], eax
0x140015432  mov     dword ptr [rsp+40h+var_18], edx
0x140015436  mov     [rsp+40h+var_20], edi
0x14001543a  call    WPP_SF_DDDDD
0x14001543f  mov     ebx, dword ptr [rbp+arg_0]
0x140015442  jmp     short loc_140015478
0x140015444  mov     rcx, cs:WPP_GLOBAL_Control
0x14001544b  cmp     rcx, rsi
0x14001544e  jz      short loc_140015473
0x140015450  cmp     byte ptr [rcx+29h], 5
0x140015454  jb      short loc_140015473
0x140015456  mov     r9d, [rbx+18h]
0x14001545a  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140015461  mov     rcx, [rcx+18h]
0x140015465  mov     edx, 1Ch
0x14001546a  mov     [rsp+40h+var_20], edi
0x14001546e  call    WPP_SF_dd
0x140015473  mov     ebx, 0C0000016h
0x140015478  lea     rcx, [rbp+arg_18]
0x14001547c  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140015481  mov     eax, ebx
0x140015483  add     rsp, 40h
0x140015487  pop     r14
0x140015489  pop     rdi
0x14001548a  pop     rsi
0x14001548b  pop     rbx
0x14001548c  pop     rbp
0x14001548d  retn
```
