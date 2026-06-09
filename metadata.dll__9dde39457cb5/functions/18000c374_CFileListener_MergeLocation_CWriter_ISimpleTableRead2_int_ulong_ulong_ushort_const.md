# CFileListener::MergeLocation(CWriter *,ISimpleTableRead2 *,int,ulong *,ulong,ushort const *)

- ea: `0x18000c374`
- end: `0x18000c4ed`
- name: `?MergeLocation@CFileListener@@AEAAJPEAVCWriter@@PEAUISimpleTableRead2@@HPEAKKPEBG@Z`
- size: `377`
- prototype: `int(CFileListener *__hidden this, struct CWriter *, struct ISimpleTableRead2 *, int, unsigned int *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009c14`
- `0x18000cb28`

## callees

- `0x180006204`
- `0x1800074e4`
- `0x180009b58`
- `0x18000c374`
- `0x18000ccc0`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000c3ff`
- `IisRTL!PuDbgPrintW` at `0x18000c4c1`
- `IisRTL!PuDbgPrintW` at `0x18000c3ff`
- `IisRTL!PuDbgPrintW` at `0x18000c4c1`

## string_xrefs

- `0x18000c3d8`: `[CFileListener::MergeLocation] Copy %s from %s.\n`
- `0x18000c432`: `[CFileListener::MergeLocation] %s from %s. Unable to merge, GetLocationWriter failed with hr = 0x%x.\n`
- `0x18000c496`: `[CFileListener::MergeLocation] Copy %s from %s failed CLocationWriter::WriteLocation failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::MergeLocation(
        CFileListener *this,
        struct CWriter *a2,
        struct ISimpleTableRead2 *a3,
        int a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned __int16 *a7)
{
  unsigned int *v7; // r14
  const wchar_t *v8; // rbp
  const unsigned __int16 *v9; // rsi
  int LocationWriter; // eax
  unsigned int v14; // edx
  CFileListener *v15; // rcx
  int v16; // ebx
  CLocationWriter *v17; // rcx
  int v18; // eax
  CLocationWriter *v20; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+20h] BYREF

  v7 = a5;
  v8 = L"MBProperty";
  v9 = a7;
  v20 = 0;
  v21 = *a5;
  if ( !a4 )
    v8 = L"MBPropertyDiff";
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4166,
      "CFileListener::MergeLocation",
      L"[CFileListener::MergeLocation] Copy %s from %s.\n",
      a7,
      v8);
  LocationWriter = CWriter::GetLocationWriter(a2, &v20, v9);
  v16 = LocationWriter;
  if ( LocationWriter >= 0 )
  {
    v16 = CFileListener::MergeRemainingProperties(v15, v20, a3, a4, &v21, a6);
    if ( v16 >= 0 )
    {
      v17 = v20;
      *v7 = v21;
      v18 = CLocationWriter::WriteLocation(v17, v14);
      v16 = v18;
      if ( v18 < 0 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          4203,
          "CFileListener::MergeLocation",
          L"[CFileListener::MergeLocation] Copy %s from %s failed CLocationWriter::WriteLocation failed with hr = 0x%x.\n",
          v9,
          v8,
          v18);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4180,
      "CFileListener::MergeLocation",
      L"[CFileListener::MergeLocation] %s from %s. Unable to merge, GetLocationWriter failed with hr = 0x%x.\n",
      v9,
      v8,
      LocationWriter);
  }
  if ( v20 )
    CLocationWriter::`scalar deleting destructor'(v20, v14);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000c374  mov     r11, rsp
0x18000c377  mov     [r11+10h], rbx
0x18000c37b  mov     [r11+8], rcx
0x18000c37f  push    rbp
0x18000c380  push    rsi
0x18000c381  push    r12
0x18000c383  push    r14
0x18000c385  push    r15
0x18000c387  sub     rsp, 40h
0x18000c38b  mov     r14, [rsp+68h+arg_20]
0x18000c393  lea     rbp, aMbproperty_0; "MBProperty"
0x18000c39a  mov     rsi, [rsp+68h+arg_30]
0x18000c3a2  test    r9d, r9d
0x18000c3a5  mov     r15d, r9d
0x18000c3a8  mov     qword ptr [r11+8], 0
0x18000c3b0  mov     r12, r8
0x18000c3b3  mov     rbx, rdx
0x18000c3b6  mov     eax, [r14]
0x18000c3b9  mov     [r11+20h], eax
0x18000c3bd  lea     rax, aMbpropertydiff; "MBPropertyDiff"
0x18000c3c4  cmovz   rbp, rax
0x18000c3c8  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c3cf  jz      short loc_18000C405
0x18000c3d1  mov     rcx, cs:g_pDebug
0x18000c3d8  lea     rax, aCfilelistenerM_13; "[CFileListener::MergeLocation] Copy %s "...
0x18000c3df  mov     [r11-38h], rbp
0x18000c3e3  lea     r9, aCfilelistenerM_9; "CFileListener::MergeLocation"
0x18000c3ea  mov     [r11-40h], rsi
0x18000c3ee  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000c3f5  mov     r8d, 1046h
0x18000c3fb  mov     [r11-48h], rax
0x18000c3ff  call    cs:__imp_PuDbgPrintW
0x18000c405  mov     r8, rsi; unsigned __int16 *
0x18000c408  lea     rdx, [rsp+68h+arg_0]; struct CLocationWriter **
0x18000c40d  mov     rcx, rbx; this
0x18000c410  call    ?GetLocationWriter@CWriter@@QEAAJPEAPEAVCLocationWriter@@PEBG@Z; CWriter::GetLocationWriter(CLocationWriter * *,ushort const *)
0x18000c415  mov     ebx, eax
0x18000c417  test    eax, eax
0x18000c419  jns     short loc_18000C43B
0x18000c41b  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c422  jz      loc_18000C4C7
0x18000c428  mov     [rsp+68h+var_30], eax
0x18000c42c  mov     r8d, 1054h
0x18000c432  lea     rax, aCfilelistenerM_1; "[CFileListener::MergeLocation] %s from "...
0x18000c439  jmp     short loc_18000C49D
0x18000c43b  mov     eax, [rsp+68h+arg_28]
0x18000c442  mov     r9d, r15d; int
0x18000c445  mov     rdx, [rsp+68h+arg_0]; struct CLocationWriter *
0x18000c44a  mov     r8, r12; struct ISimpleTableRead2 *
0x18000c44d  mov     [rsp+68h+var_40], eax; unsigned int
0x18000c451  lea     rax, [rsp+68h+arg_18]
0x18000c459  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000c45e  call    ?MergeRemainingProperties@CFileListener@@AEAAJPEAVCLocationWriter@@PEAUISimpleTableRead2@@HPEAKK@Z; CFileListener::MergeRemainingProperties(CLocationWriter *,ISimpleTableRead2 *,int,ulong *,ulong)
0x18000c463  mov     ebx, eax
0x18000c465  test    eax, eax
0x18000c467  js      short loc_18000C4C7
0x18000c469  mov     eax, [rsp+68h+arg_18]
0x18000c470  mov     rcx, [rsp+68h+arg_0]; this
0x18000c475  mov     [r14], eax
0x18000c478  call    ?WriteLocation@CLocationWriter@@QEAAJH@Z; CLocationWriter::WriteLocation(int)
0x18000c47d  mov     ebx, eax
0x18000c47f  test    eax, eax
0x18000c481  jns     short loc_18000C4C7
0x18000c483  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c48a  jz      short loc_18000C4C7
0x18000c48c  mov     [rsp+68h+var_30], eax
0x18000c490  mov     r8d, 106Bh
0x18000c496  lea     rax, aCfilelistenerM_4; "[CFileListener::MergeLocation] Copy %s "...
0x18000c49d  mov     rcx, cs:g_pDebug
0x18000c4a4  lea     r9, aCfilelistenerM_9; "CFileListener::MergeLocation"
0x18000c4ab  mov     [rsp+68h+var_38], rbp
0x18000c4b0  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000c4b7  mov     qword ptr [rsp+68h+var_40], rsi
0x18000c4bc  mov     [rsp+68h+var_48], rax
0x18000c4c1  call    cs:__imp_PuDbgPrintW
0x18000c4c7  cmp     [rsp+68h+arg_0], 0
0x18000c4cd  jz      short loc_18000C4D9
0x18000c4cf  mov     rcx, [rsp+68h+arg_0]; this
0x18000c4d4  call    ??_GCLocationWriter@@QEAAPEAXI@Z; CLocationWriter::`scalar deleting destructor'(uint)
0x18000c4d9  mov     eax, ebx
0x18000c4db  mov     rbx, [rsp+68h+arg_8]
0x18000c4e0  add     rsp, 40h
0x18000c4e4  pop     r15
0x18000c4e6  pop     r14
0x18000c4e8  pop     r12
0x18000c4ea  pop     rsi
0x18000c4eb  pop     rbp
0x18000c4ec  retn
```
