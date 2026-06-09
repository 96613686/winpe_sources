# OleStdGetMetafilePictFromOleObject(IOleObject *,ulong,tagSIZE *,tagDVTARGETDEVICE *)

- ea: `0x18008ed4c`
- end: `0x18008f017`
- name: `?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@KPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@@Z`
- size: `715`
- prototype: `void *__fastcall(struct IOleObject *, unsigned int, struct tagSIZE *, struct tagDVTARGETDEVICE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005bc58`
- `0x18007fbac`

## callees

- `0x18008ed4c`
- `0x18009270c`
- `0x180092ed0`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18008efc8`
- `KERNEL32!GlobalAlloc` at `0x18008efc8`
- `KERNEL32!GlobalLock` at `0x18008efdf`
- `KERNEL32!GlobalLock` at `0x18008efdf`
- `KERNEL32!GlobalUnlock` at `0x18008f009`
- `KERNEL32!GlobalUnlock` at `0x18008f009`
- `GDI32!DeleteMetaFile` at `0x18008ef8b`
- `GDI32!DeleteMetaFile` at `0x18008ef8b`
- `GDI32!SetWindowExtEx` at `0x18008ef0c`
- `GDI32!SetWindowExtEx` at `0x18008ef0c`
- `GDI32!SetWindowOrgEx` at `0x18008eef4`
- `GDI32!SetWindowOrgEx` at `0x18008eef4`
- `GDI32!CreateMetaFileA` at `0x18008eec9`
- `GDI32!CreateMetaFileA` at `0x18008eec9`
- `GDI32!CloseMetaFile` at `0x18008ef72`
- `GDI32!CloseMetaFile` at `0x18008ef72`

## pseudocode

```c
void *__fastcall OleStdGetMetafilePictFromOleObject(
        struct IOleObject *a1,
        unsigned int a2,
        struct tagSIZE *a3,
        struct tagDVTARGETDEVICE *a4)
{
  struct IOleObjectVtbl *lpVtbl; // rax
  void *v8; // rbx
  HRESULT (__stdcall *QueryInterface)(IOleObject *, const IID *const, void **); // rax
  unsigned __int16 v10; // dx
  unsigned int v11; // r8d
  HDC MetaFileA; // rax
  int v14; // edi
  int v15; // ebx
  HDC v16; // rsi
  int v17; // ebx
  HMETAFILE v18; // rdi
  HGLOBAL v19; // rax
  _QWORD *v20; // rax
  int x[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v22; // [rsp+68h] [rbp-41h] BYREF
  __int64 v23; // [rsp+70h] [rbp-39h] BYREF
  __int64 v24; // [rsp+78h] [rbp-31h] BYREF
  struct tagPOINT pt; // [rsp+80h] [rbp-29h] BYREF
  tagSIZE sz; // [rsp+88h] [rbp-21h] BYREF
  __int128 v27; // [rsp+90h] [rbp-19h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-9h]
  struct tagSTGMEDIUM v29; // [rsp+B0h] [rbp+7h] BYREF
  __int128 v30; // [rsp+C8h] [rbp+1Fh] BYREF

  v28 = 0;
  v27 = 0;
  LODWORD(v28) = a2;
  LOWORD(v27) = 3;
  v22 = 0;
  lpVtbl = a1->lpVtbl;
  v30 = 0;
  *(_QWORD *)x = 0;
  v8 = 0;
  sz = 0;
  QueryInterface = lpVtbl->QueryInterface;
  pt = 0;
  v24 = 0;
  v23 = 0;
  *(_QWORD *)((char *)&v28 + 4) = 0x20FFFFFFFFLL;
  memset(&v29, 0, sizeof(v29));
  if ( !((unsigned int (__fastcall *)(struct IOleObject *, GUID *, __int64 *, struct tagDVTARGETDEVICE *))QueryInterface)(
          a1,
          &IID_IOleCache,
          &v24,
          a4)
    && !(**(unsigned int (__fastcall ***)(__int64, GUID *, __int64 *))v24)(v24, &IID_IDataObject, &v23)
    && !(*(unsigned int (__fastcall **)(__int64, __int128 *, struct tagSTGMEDIUM *))(*(_QWORD *)v23 + 24LL))(
          v23,
          &v27,
          &v29) )
  {
    v8 = CW32System::OleDuplicateData(v29.hBitmap, v10, v11);
    CW32System::ReleaseStgMedium(&v29);
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v8 )
    return v8;
  if ( ((__int64 (__fastcall *)(struct IOleObject *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IViewObject2,
         &v22) )
  {
    return 0;
  }
  if ( a3 )
  {
    *(struct tagSIZE *)x = *a3;
  }
  else if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v22 + 72LL))(
              v22,
              a2,
              0xFFFFFFFFLL,
              0,
              x) )
  {
    *(_QWORD *)x = 0;
  }
  MetaFileA = CreateMetaFileA(0);
  v14 = x[0];
  v15 = x[1];
  *(_QWORD *)&v30 = 0;
  *((_QWORD *)&v30 + 1) = *(_QWORD *)x;
  v16 = MetaFileA;
  SetWindowOrgEx(MetaFileA, 0, 0, &pt);
  SetWindowExtEx(v16, v14, v15, &sz);
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, HDC, __int128 *, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v22 + 24LL))(
          v22,
          a2,
          0xFFFFFFFFLL,
          0,
          0,
          0,
          v16,
          &v30,
          &v30,
          0,
          0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v18 = CloseMetaFile(v16);
  if ( v17 )
  {
    v8 = 0;
  }
  else
  {
    v19 = GlobalAlloc(0x2042u, 0x18u);
    v8 = v19;
    if ( v19 )
    {
      v20 = GlobalLock(v19);
      if ( v20 )
      {
        v20[2] = v18;
        *((_DWORD *)v20 + 1) = x[0];
        *((_DWORD *)v20 + 2) = x[1];
        *(_DWORD *)v20 = 8;
        GlobalUnlock(v8);
      }
      return v8;
    }
  }
  DeleteMetaFile(v18);
  return v8;
}

```

## disassembly

```asm
0x18008ed4c  mov     [rsp-8+arg_18], rbx
0x18008ed51  push    rbp
0x18008ed52  push    rsi
0x18008ed53  push    rdi
0x18008ed54  push    r14
0x18008ed56  push    r15
0x18008ed58  lea     rbp, [rsp-37h]
0x18008ed5d  sub     rsp, 0E0h
0x18008ed64  mov     rax, cs:__security_cookie
0x18008ed6b  xor     rax, rsp
0x18008ed6e  mov     [rbp+57h+var_28], rax
0x18008ed72  xor     r15d, r15d
0x18008ed75  xorps   xmm0, xmm0
0x18008ed78  movups  [rbp+57h+var_60], xmm0
0x18008ed7c  mov     rsi, r8
0x18008ed7f  mov     r14d, edx
0x18008ed82  movups  [rbp+57h+var_70], xmm0
0x18008ed86  lea     eax, [r15+3]
0x18008ed8a  mov     dword ptr [rbp+57h+var_60], edx
0x18008ed8d  mov     word ptr [rbp+57h+var_70], ax
0x18008ed91  lea     r8, [rbp+57h+var_88]
0x18008ed95  xor     eax, eax
0x18008ed97  mov     [rbp+57h+var_98], r15
0x18008ed9b  mov     [rbp+57h+var_50.pUnkForRelease], rax
0x18008ed9f  lea     rdx, IID_IOleCache
0x18008eda6  mov     rax, [rcx]
0x18008eda9  mov     rdi, rcx
0x18008edac  movups  [rbp+57h+var_38], xmm0
0x18008edb0  mov     qword ptr [rbp+57h+x], r15
0x18008edb4  mov     ebx, r15d
0x18008edb7  mov     qword ptr [rbp+57h+sz.cx], r15
0x18008edbb  mov     rax, [rax]
0x18008edbe  mov     qword ptr [rbp+57h+pt.x], r15
0x18008edc2  mov     [rbp+57h+var_88], r15
0x18008edc6  mov     [rbp+57h+var_90], r15
0x18008edca  mov     dword ptr [rbp+57h+var_60+4], 0FFFFFFFFh
0x18008edd1  mov     dword ptr [rbp+57h+var_60+8], 20h ; ' '
0x18008edd8  movups  xmmword ptr [rbp+57h+var_50.tymed], xmm0
0x18008eddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ede1  test    eax, eax
0x18008ede3  jnz     short loc_18008EE34
0x18008ede5  mov     rcx, [rbp+57h+var_88]
0x18008ede9  lea     r8, [rbp+57h+var_90]
0x18008eded  lea     rdx, IID_IDataObject
0x18008edf4  mov     rax, [rcx]
0x18008edf7  mov     rax, [rax]
0x18008edfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008edff  test    eax, eax
0x18008ee01  jnz     short loc_18008EE34
0x18008ee03  mov     rcx, [rbp+57h+var_90]
0x18008ee07  lea     r8, [rbp+57h+var_50]
0x18008ee0b  lea     rdx, [rbp+57h+var_70]
0x18008ee0f  mov     rax, [rcx]
0x18008ee12  mov     rax, [rax+18h]
0x18008ee16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee1b  test    eax, eax
0x18008ee1d  jnz     short loc_18008EE34
0x18008ee1f  mov     rcx, qword ptr [rbp+57h+var_50.8]; void *
0x18008ee23  call    ?OleDuplicateData@CW32System@@SAPEAXPEAXGI@Z; CW32System::OleDuplicateData(void *,ushort,uint)
0x18008ee28  lea     rcx, [rbp+57h+var_50]; struct tagSTGMEDIUM *
0x18008ee2c  mov     rbx, rax
0x18008ee2f  call    ?ReleaseStgMedium@CW32System@@SAJPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x18008ee34  mov     rdx, [rbp+57h+var_90]
0x18008ee38  test    rdx, rdx
0x18008ee3b  jz      short loc_18008EE4C
0x18008ee3d  mov     rcx, [rdx]
0x18008ee40  mov     rax, [rcx+10h]
0x18008ee44  mov     rcx, rdx
0x18008ee47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee4c  mov     rcx, [rbp+57h+var_88]
0x18008ee50  test    rcx, rcx
0x18008ee53  jz      short loc_18008EE61
0x18008ee55  mov     rax, [rcx]
0x18008ee58  mov     rax, [rax+10h]
0x18008ee5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee61  test    rbx, rbx
0x18008ee64  jnz     loc_18008EF97
0x18008ee6a  mov     rax, [rdi]
0x18008ee6d  lea     r8, [rbp+57h+var_98]
0x18008ee71  lea     rdx, IID_IViewObject2
0x18008ee78  mov     rcx, rdi
0x18008ee7b  mov     rax, [rax]
0x18008ee7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee83  test    eax, eax
0x18008ee85  jz      short loc_18008EE8E
0x18008ee87  xor     eax, eax
0x18008ee89  jmp     loc_18008EF9A
0x18008ee8e  test    rsi, rsi
0x18008ee91  jz      short loc_18008EE9C
0x18008ee93  mov     rax, [rsi]
0x18008ee96  mov     qword ptr [rbp+57h+x], rax
0x18008ee9a  jmp     short loc_18008EEC7
0x18008ee9c  mov     rcx, [rbp+57h+var_98]
0x18008eea0  lea     rdx, [rbp+57h+x]
0x18008eea4  mov     [rsp+100h+var_E0], rdx
0x18008eea9  xor     r9d, r9d
0x18008eeac  or      r8d, 0FFFFFFFFh
0x18008eeb0  mov     edx, r14d
0x18008eeb3  mov     rax, [rcx]
0x18008eeb6  mov     rax, [rax+48h]
0x18008eeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eebf  test    eax, eax
0x18008eec1  jz      short loc_18008EEC7
0x18008eec3  mov     qword ptr [rbp+57h+x], r15
0x18008eec7  xor     ecx, ecx; pszFile
0x18008eec9  call    cs:__imp_CreateMetaFileA
0x18008eed0  nop     dword ptr [rax+rax+00h]
0x18008eed5  mov     edi, [rbp+57h+x]
0x18008eed8  lea     r9, [rbp+57h+pt]; lppt
0x18008eedc  mov     ebx, [rbp+57h+x+4]
0x18008eedf  mov     rcx, rax; hdc
0x18008eee2  xor     r8d, r8d; y
0x18008eee5  mov     qword ptr [rbp+57h+var_38], r15
0x18008eee9  xor     edx, edx; x
0x18008eeeb  mov     dword ptr [rbp+57h+var_38+8], edi
0x18008eeee  mov     rsi, rax
0x18008eef1  mov     dword ptr [rbp+57h+var_38+0Ch], ebx
0x18008eef4  call    cs:__imp_SetWindowOrgEx
0x18008eefb  nop     dword ptr [rax+rax+00h]
0x18008ef00  lea     r9, [rbp+57h+sz]; lpsz
0x18008ef04  mov     r8d, ebx; y
0x18008ef07  mov     edx, edi; x
0x18008ef09  mov     rcx, rsi; hdc
0x18008ef0c  call    cs:__imp_SetWindowExtEx
0x18008ef13  nop     dword ptr [rax+rax+00h]
0x18008ef18  mov     rcx, [rbp+57h+var_98]
0x18008ef1c  lea     rdx, [rbp+57h+var_38]
0x18008ef20  mov     [rsp+100h+var_B0], r15
0x18008ef25  xor     r9d, r9d
0x18008ef28  mov     [rsp+100h+var_B8], r15
0x18008ef2d  or      r8d, 0FFFFFFFFh
0x18008ef31  mov     [rsp+100h+var_C0], rdx
0x18008ef36  lea     rdx, [rbp+57h+var_38]
0x18008ef3a  mov     rax, [rcx]
0x18008ef3d  mov     [rsp+100h+var_C8], rdx
0x18008ef42  mov     edx, r14d
0x18008ef45  mov     [rsp+100h+var_D0], rsi
0x18008ef4a  mov     [rsp+100h+var_D8], r15
0x18008ef4f  mov     rax, [rax+18h]
0x18008ef53  mov     [rsp+100h+var_E0], r15
0x18008ef58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef5d  mov     rcx, [rbp+57h+var_98]
0x18008ef61  mov     ebx, eax
0x18008ef63  mov     rdx, [rcx]
0x18008ef66  mov     rax, [rdx+10h]
0x18008ef6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef6f  mov     rcx, rsi; hdc
0x18008ef72  call    cs:__imp_CloseMetaFile
0x18008ef79  nop     dword ptr [rax+rax+00h]
0x18008ef7e  mov     rdi, rax
0x18008ef81  test    ebx, ebx
0x18008ef83  jz      short loc_18008EFBE
0x18008ef85  mov     rbx, r15
0x18008ef88  mov     rcx, rdi; hmf
0x18008ef8b  call    cs:__imp_DeleteMetaFile
0x18008ef92  nop     dword ptr [rax+rax+00h]
0x18008ef97  mov     rax, rbx
0x18008ef9a  mov     rcx, [rbp+57h+var_28]
0x18008ef9e  xor     rcx, rsp; StackCookie
0x18008efa1  call    __security_check_cookie
0x18008efa6  mov     rbx, [rsp+100h+arg_18]
0x18008efae  add     rsp, 0E0h
0x18008efb5  pop     r15
0x18008efb7  pop     r14
0x18008efb9  pop     rdi
0x18008efba  pop     rsi
0x18008efbb  pop     rbp
0x18008efbc  retn
0x18008efbe  mov     edx, 18h; dwBytes
0x18008efc3  mov     ecx, 2042h; uFlags
0x18008efc8  call    cs:__imp_GlobalAlloc
0x18008efcf  nop     dword ptr [rax+rax+00h]
0x18008efd4  mov     rbx, rax
0x18008efd7  test    rax, rax
0x18008efda  jz      short loc_18008EF88
0x18008efdc  mov     rcx, rax; hMem
0x18008efdf  call    cs:__imp_GlobalLock
0x18008efe6  nop     dword ptr [rax+rax+00h]
0x18008efeb  test    rax, rax
0x18008efee  jz      short loc_18008EF97
0x18008eff0  mov     [rax+10h], rdi
0x18008eff4  mov     ecx, [rbp+57h+x]
0x18008eff7  mov     [rax+4], ecx
0x18008effa  mov     ecx, [rbp+57h+x+4]
0x18008effd  mov     [rax+8], ecx
0x18008f000  mov     rcx, rbx; hMem
0x18008f003  mov     dword ptr [rax], 8
0x18008f009  call    cs:__imp_GlobalUnlock
0x18008f010  nop     dword ptr [rax+rax+00h]
0x18008f015  jmp     short loc_18008EF97
```
