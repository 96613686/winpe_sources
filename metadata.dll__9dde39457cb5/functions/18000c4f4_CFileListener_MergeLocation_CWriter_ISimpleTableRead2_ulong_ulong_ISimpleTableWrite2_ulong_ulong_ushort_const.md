# CFileListener::MergeLocation(CWriter *,ISimpleTableRead2 *,ulong *,ulong,ISimpleTableWrite2 *,ulong *,ulong,ushort const *)

- ea: `0x18000c4f4`
- end: `0x18000c679`
- name: `?MergeLocation@CFileListener@@AEAAJPEAVCWriter@@PEAUISimpleTableRead2@@PEAKKPEAUISimpleTableWrite2@@2KPEBG@Z`
- size: `389`
- prototype: `int(CFileListener *__hidden this, struct CWriter *, struct ISimpleTableRead2 *, unsigned int *, unsigned int, struct ISimpleTableWrite2 *, unsigned int *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009c14`

## callees

- `0x180006204`
- `0x1800074e4`
- `0x180009b58`
- `0x18000c4f4`
- `0x18000c680`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000c558`
- `IisRTL!PuDbgPrintW` at `0x18000c649`
- `IisRTL!PuDbgPrintW` at `0x18000c558`
- `IisRTL!PuDbgPrintW` at `0x18000c649`

## string_xrefs

- `0x18000c58b`: `[CFileListener::MergeLocation] %s. failed because CWriter::GetLocationWriter failed with hr = 0x%x.\n`
- `0x18000c623`: `[CFileListener::MergeLocation] %s. failed because CWriter::WriteLocation failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::MergeLocation(
        CFileListener *this,
        struct CWriter *a2,
        struct ISimpleTableRead2 *a3,
        unsigned int *a4,
        unsigned int a5,
        struct ISimpleTableWrite2 *a6,
        unsigned int *a7,
        unsigned int a8,
        unsigned __int16 *a9)
{
  const unsigned __int16 *v10; // rsi
  int LocationWriter; // eax
  unsigned int v14; // edx
  CFileListener *v15; // rcx
  int v16; // ebx
  unsigned int *v17; // r15
  CLocationWriter *v18; // rcx
  int v19; // eax
  int v21; // [rsp+30h] [rbp-38h]
  unsigned int *v22; // [rsp+30h] [rbp-38h]
  unsigned int v23; // [rsp+40h] [rbp-28h] BYREF
  CLocationWriter *v24; // [rsp+48h] [rbp-20h] BYREF
  CFileListener *v25; // [rsp+70h] [rbp+8h] BYREF

  v25 = this;
  v10 = a9;
  v24 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      3741,
      "CFileListener::MergeLocation",
      L"[CFileListener::MergeLocation] %s.\n",
      a9);
  LocationWriter = CWriter::GetLocationWriter(a2, &v24, v10);
  v16 = LocationWriter;
  if ( LocationWriter >= 0 )
  {
    v17 = a7;
    LODWORD(v25) = *a4;
    v23 = *a7;
    v16 = CFileListener::MergeProperties(v15, v24, a3, (unsigned int *)&v25, a5, a6, &v23, a8);
    if ( v16 >= 0 )
    {
      v18 = v24;
      *a4 = (unsigned int)v25;
      *v17 = v23;
      v19 = CLocationWriter::WriteLocation(v18, v14);
      v16 = v19;
      if ( v19 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v22) = v19;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          3785,
          "CFileListener::MergeLocation",
          L"[CFileListener::MergeLocation] %s. failed because CWriter::WriteLocation failed with hr = 0x%x.\n",
          v10,
          v22);
      }
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v21 = LocationWriter;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      3755,
      "CFileListener::MergeLocation",
      L"[CFileListener::MergeLocation] %s. failed because CWriter::GetLocationWriter failed with hr = 0x%x.\n",
      v10,
      v21);
  }
  if ( v24 )
    CLocationWriter::`scalar deleting destructor'(v24, v14);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000c4f4  mov     r11, rsp
0x18000c4f7  mov     [r11+10h], rbx
0x18000c4fb  mov     [r11+18h], rbp
0x18000c4ff  mov     [r11+8], rcx
0x18000c503  push    rsi
0x18000c504  push    r14
0x18000c506  push    r15
0x18000c508  sub     rsp, 50h
0x18000c50c  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c513  mov     r14, r9
0x18000c516  mov     rsi, [rsp+68h+arg_40]
0x18000c51e  mov     rbp, r8
0x18000c521  mov     rbx, rdx
0x18000c524  mov     qword ptr [r11-20h], 0
0x18000c52c  jz      short loc_18000C55E
0x18000c52e  mov     rcx, cs:g_pDebug
0x18000c535  lea     rax, aCfilelistenerM_11; "[CFileListener::MergeLocation] %s.\n"
0x18000c53c  mov     [r11-40h], rsi
0x18000c540  lea     r9, aCfilelistenerM_9; "CFileListener::MergeLocation"
0x18000c547  mov     r8d, 0E9Dh
0x18000c54d  mov     [r11-48h], rax
0x18000c551  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000c558  call    cs:__imp_PuDbgPrintW
0x18000c55e  mov     r8, rsi; unsigned __int16 *
0x18000c561  lea     rdx, [rsp+68h+var_20]; struct CLocationWriter **
0x18000c566  mov     rcx, rbx; this
0x18000c569  call    ?GetLocationWriter@CWriter@@QEAAJPEAPEAVCLocationWriter@@PEBG@Z; CWriter::GetLocationWriter(CLocationWriter * *,ushort const *)
0x18000c56e  mov     ebx, eax
0x18000c570  test    eax, eax
0x18000c572  jns     short loc_18000C597
0x18000c574  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c57b  jz      loc_18000C64F
0x18000c581  mov     dword ptr [rsp+68h+var_38], eax
0x18000c585  mov     r8d, 0EABh
0x18000c58b  lea     rax, aCfilelistenerM_7; "[CFileListener::MergeLocation] %s. fail"...
0x18000c592  jmp     loc_18000C62A
0x18000c597  mov     eax, [r14]
0x18000c59a  lea     r9, [rsp+68h+arg_0]; unsigned int *
0x18000c59f  mov     r15, [rsp+68h+arg_30]
0x18000c5a7  mov     r8, rbp; struct ISimpleTableRead2 *
0x18000c5aa  mov     rdx, [rsp+68h+var_20]; struct CLocationWriter *
0x18000c5af  mov     dword ptr [rsp+68h+arg_0], eax
0x18000c5b3  mov     eax, [r15]
0x18000c5b6  mov     [rsp+68h+var_28], eax
0x18000c5ba  mov     eax, [rsp+68h+arg_38]
0x18000c5c1  mov     [rsp+68h+var_30], eax; unsigned int
0x18000c5c5  lea     rax, [rsp+68h+var_28]
0x18000c5ca  mov     [rsp+68h+var_38], rax; unsigned int *
0x18000c5cf  mov     rax, [rsp+68h+arg_28]
0x18000c5d7  mov     [rsp+68h+var_40], rax; struct ISimpleTableWrite2 *
0x18000c5dc  mov     eax, [rsp+68h+arg_20]
0x18000c5e3  mov     [rsp+68h+var_48], eax; unsigned int
0x18000c5e7  call    ?MergeProperties@CFileListener@@AEAAJPEAVCLocationWriter@@PEAUISimpleTableRead2@@PEAKKPEAUISimpleTableWrite2@@2K@Z; CFileListener::MergeProperties(CLocationWriter *,ISimpleTableRead2 *,ulong *,ulong,ISimpleTableWrite2 *,ulong *,ulong)
0x18000c5ec  mov     ebx, eax
0x18000c5ee  test    eax, eax
0x18000c5f0  js      short loc_18000C64F
0x18000c5f2  mov     eax, dword ptr [rsp+68h+arg_0]
0x18000c5f6  mov     rcx, [rsp+68h+var_20]; this
0x18000c5fb  mov     [r14], eax
0x18000c5fe  mov     eax, [rsp+68h+var_28]
0x18000c602  mov     [r15], eax
0x18000c605  call    ?WriteLocation@CLocationWriter@@QEAAJH@Z; CLocationWriter::WriteLocation(int)
0x18000c60a  mov     ebx, eax
0x18000c60c  test    eax, eax
0x18000c60e  jns     short loc_18000C64F
0x18000c610  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c617  jz      short loc_18000C64F
0x18000c619  mov     dword ptr [rsp+68h+var_38], eax
0x18000c61d  mov     r8d, 0EC9h
0x18000c623  lea     rax, aCfilelistenerM_5; "[CFileListener::MergeLocation] %s. fail"...
0x18000c62a  mov     rcx, cs:g_pDebug
0x18000c631  lea     r9, aCfilelistenerM_9; "CFileListener::MergeLocation"
0x18000c638  mov     [rsp+68h+var_40], rsi
0x18000c63d  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000c644  mov     qword ptr [rsp+68h+var_48], rax
0x18000c649  call    cs:__imp_PuDbgPrintW
0x18000c64f  cmp     [rsp+68h+var_20], 0
0x18000c655  jz      short loc_18000C661
0x18000c657  mov     rcx, [rsp+68h+var_20]; this
0x18000c65c  call    ??_GCLocationWriter@@QEAAPEAXI@Z; CLocationWriter::`scalar deleting destructor'(uint)
0x18000c661  lea     r11, [rsp+68h+var_18]
0x18000c666  mov     eax, ebx
0x18000c668  mov     rbx, [r11+28h]
0x18000c66c  mov     rbp, [r11+30h]
0x18000c670  mov     rsp, r11
0x18000c673  pop     r15
0x18000c675  pop     r14
0x18000c677  pop     rsi
0x18000c678  retn
```
