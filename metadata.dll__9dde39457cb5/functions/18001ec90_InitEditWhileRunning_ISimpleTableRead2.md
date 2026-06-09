# InitEditWhileRunning(ISimpleTableRead2 *)

- ea: `0x18001ec90`
- end: `0x18001eec1`
- name: `?InitEditWhileRunning@@YAJPEAUISimpleTableRead2@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(struct ISimpleTableRead2 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020014`

## callees

- `0x18000e9ec`
- `0x18001ea74`
- `0x18001ec90`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18001ed34`
- `IisRTL!PuDbgPrintW` at `0x18001eded`
- `IisRTL!PuDbgPrintW` at `0x18001ee31`
- `IisRTL!PuDbgPrintW` at `0x18001ee9b`
- `IisRTL!PuDbgPrintW` at `0x18001ed34`
- `IisRTL!PuDbgPrintW` at `0x18001eded`
- `IisRTL!PuDbgPrintW` at `0x18001ee31`
- `IisRTL!PuDbgPrintW` at `0x18001ee9b`

## string_xrefs

- `0x18001ecec`: `[InitEditWhileRunning] Could not determine if edit while running was enabled. Defaulting to %d. GetComputerValue failed with hr = 0x%x.\n`
- `0x18001ee12`: `[InitEditWhileRunning] Read history major version number as 0x%x.\n`

## pseudocode

```c
__int64 __fastcall InitEditWhileRunning(struct ISimpleTableRead2 *a1)
{
  int Value; // eax
  int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // ecx
  int v6; // eax
  unsigned int v7; // ebx
  void **v9; // [rsp+28h] [rbp-40h]
  void **v10; // [rsp+28h] [rbp-40h]
  void **v11; // [rsp+28h] [rbp-40h]
  __int64 v12; // [rsp+30h] [rbp-38h]
  void *v13; // [rsp+40h] [rbp-28h] BYREF
  int v14; // [rsp+78h] [rbp+10h] BYREF
  unsigned int *v15; // [rsp+80h] [rbp+18h] BYREF
  void *v16; // [rsp+88h] [rbp+20h] BYREF

  v14 = 0;
  v15 = (unsigned int *)&v14;
  v16 = 0;
  v13 = 0;
  Value = GetValue(a1, L"/LM", 2u, L"EnableEditWhileRunning", 0, (void **)&v15);
  if ( Value >= 0 )
  {
    g_dwEnableEditWhileRunning = *v15;
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v9) = g_dwEnableEditWhileRunning;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      9880,
      "InitEditWhileRunning",
      L"[InitEditWhileRunning] Could not determine if edit while running was enabled. Defaulting to %d. GetComputerValue f"
       "ailed with hr = 0x%x.\n",
      v9,
      Value);
  }
  if ( (unsigned int)ShouldForceEWR() )
    g_dwEnableEditWhileRunning = 1;
  v3 = GetValue(a1, L".", 0x34u, L"HistoryMajorVersionNumber", 0, &v16);
  if ( v3 == -2145318890 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_16;
    LODWORD(v12) = -2145318890;
    v4 = 9915;
LABEL_13:
    LODWORD(v10) = g_ulHistoryMajorVersionNumber;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      v4,
      "InitEditWhileRunning",
      L"[InitEditWhileRunning] Could not fetch history major version number. Defaulting to 0x%x. GetGlobalValue failed with hr = 0x%x.\n",
      v10,
      v12);
    goto LABEL_16;
  }
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_16;
    LODWORD(v12) = v3;
    v4 = 9923;
    goto LABEL_13;
  }
  v5 = *(_DWORD *)v16;
  g_ulHistoryMajorVersionNumber = *(_DWORD *)v16;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v10) = v5;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      9933,
      "InitEditWhileRunning",
      L"[InitEditWhileRunning] Read history major version number as 0x%x.\n",
      v10);
  }
LABEL_16:
  v6 = GetValue(a1, L"/LM", 2u, L"MaxErrorFiles", 0, &v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    g_dwMaxErrorFiles = *(_DWORD *)v13;
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v12) = v6;
    LODWORD(v11) = g_dwEnableEditWhileRunning;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      9949,
      "InitEditWhileRunning",
      L"[InitEditWhileRunning] Could not determine if edit while running was enabled. Defaulting to %d. GetComputerValue f"
       "ailed with hr = 0x%x.\n",
      v11,
      v12);
  }
  return v7;
}

```

## disassembly

```asm
0x18001ec90  mov     r11, rsp
0x18001ec93  mov     [r11+8], rbx
0x18001ec97  push    rbp
0x18001ec98  push    r14
0x18001ec9a  push    r15
0x18001ec9c  sub     rsp, 50h
0x18001eca0  lea     rax, [r11+10h]
0x18001eca4  mov     [rsp+68h+arg_8], 0
0x18001ecac  mov     [r11+18h], rax
0x18001ecb0  lea     r9, aEnableeditwhil; "EnableEditWhileRunning"
0x18001ecb7  lea     rax, [r11+18h]
0x18001ecbb  mov     qword ptr [r11+20h], 0
0x18001ecc3  mov     [r11-40h], rax
0x18001ecc7  lea     rdx, aLm_0; "/LM"
0x18001ecce  mov     r8d, 2; unsigned int
0x18001ecd4  mov     qword ptr [r11-48h], 0
0x18001ecdc  mov     rbx, rcx
0x18001ecdf  mov     qword ptr [r11-28h], 0
0x18001ece7  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001ecec  lea     r15, aIniteditwhiler; "[InitEditWhileRunning] Could not determ"...
0x18001ecf3  lea     rbp, aIniteditwhiler_0; "InitEditWhileRunning"
0x18001ecfa  lea     r14, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001ed01  test    eax, eax
0x18001ed03  jns     short loc_18001ED3C
0x18001ed05  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ed0c  jz      short loc_18001ED4C
0x18001ed0e  mov     rcx, cs:g_pDebug
0x18001ed15  mov     r9, rbp
0x18001ed18  mov     [rsp+68h+var_38], eax
0x18001ed1c  mov     r8d, 2698h
0x18001ed22  mov     eax, cs:?g_dwEnableEditWhileRunning@@3KA; ulong g_dwEnableEditWhileRunning
0x18001ed28  mov     rdx, r14
0x18001ed2b  mov     dword ptr [rsp+68h+var_40], eax
0x18001ed2f  mov     [rsp+68h+var_48], r15
0x18001ed34  call    cs:__imp_PuDbgPrintW
0x18001ed3a  jmp     short loc_18001ED4C
0x18001ed3c  mov     rax, [rsp+68h+arg_10]
0x18001ed44  mov     ecx, [rax]
0x18001ed46  mov     cs:?g_dwEnableEditWhileRunning@@3KA, ecx; ulong g_dwEnableEditWhileRunning
0x18001ed4c  call    ?ShouldForceEWR@@YAHXZ; ShouldForceEWR(void)
0x18001ed51  test    eax, eax
0x18001ed53  jz      short loc_18001ED5F
0x18001ed55  mov     cs:?g_dwEnableEditWhileRunning@@3KA, 1; ulong g_dwEnableEditWhileRunning
0x18001ed5f  lea     rax, [rsp+68h+arg_18]
0x18001ed67  mov     r8d, 34h ; '4'; unsigned int
0x18001ed6d  mov     [rsp+68h+var_40], rax; void **
0x18001ed72  lea     r9, aHistorymajorve; "HistoryMajorVersionNumber"
0x18001ed79  lea     rdx, String; "."
0x18001ed80  mov     [rsp+68h+var_48], 0; unsigned int *
0x18001ed89  mov     rcx, rbx; struct ISimpleTableRead2 *
0x18001ed8c  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001ed91  mov     ecx, 80210816h
0x18001ed96  cmp     eax, ecx
0x18001ed98  jnz     short loc_18001EDB3
0x18001ed9a  test    byte ptr cs:g_dwDebugFlags, 3
0x18001eda1  jz      loc_18001EE37
0x18001eda7  mov     [rsp+68h+var_38], ecx
0x18001edab  mov     r8d, 26BBh
0x18001edb1  jmp     short loc_18001EDCA
0x18001edb3  test    eax, eax
0x18001edb5  jns     short loc_18001EDF5
0x18001edb7  test    byte ptr cs:g_dwDebugFlags, 3
0x18001edbe  jz      short loc_18001EE37
0x18001edc0  mov     [rsp+68h+var_38], eax
0x18001edc4  mov     r8d, 26C3h
0x18001edca  mov     eax, cs:?g_ulHistoryMajorVersionNumber@@3KA; ulong g_ulHistoryMajorVersionNumber
0x18001edd0  mov     r9, rbp
0x18001edd3  mov     rcx, cs:g_pDebug
0x18001edda  mov     rdx, r14
0x18001eddd  mov     dword ptr [rsp+68h+var_40], eax
0x18001ede1  lea     rax, aIniteditwhiler_2; "[InitEditWhileRunning] Could not fetch "...
0x18001ede8  mov     [rsp+68h+var_48], rax
0x18001eded  call    cs:__imp_PuDbgPrintW
0x18001edf3  jmp     short loc_18001EE37
0x18001edf5  test    byte ptr cs:g_dwDebugFlags, 3
0x18001edfc  mov     rax, [rsp+68h+arg_18]
0x18001ee04  mov     ecx, [rax]
0x18001ee06  mov     cs:?g_ulHistoryMajorVersionNumber@@3KA, ecx; ulong g_ulHistoryMajorVersionNumber
0x18001ee0c  jz      short loc_18001EE37
0x18001ee0e  mov     dword ptr [rsp+68h+var_40], ecx
0x18001ee12  lea     rax, aIniteditwhiler_1; "[InitEditWhileRunning] Read history maj"...
0x18001ee19  mov     rcx, cs:g_pDebug
0x18001ee20  mov     r9, rbp
0x18001ee23  mov     r8d, 26CDh
0x18001ee29  mov     [rsp+68h+var_48], rax
0x18001ee2e  mov     rdx, r14
0x18001ee31  call    cs:__imp_PuDbgPrintW
0x18001ee37  lea     rax, [rsp+68h+var_28]
0x18001ee3c  mov     r8d, 2; unsigned int
0x18001ee42  mov     [rsp+68h+var_40], rax; void **
0x18001ee47  lea     r9, aMaxerrorfiles; "MaxErrorFiles"
0x18001ee4e  lea     rdx, aLm_0; "/LM"
0x18001ee55  mov     [rsp+68h+var_48], 0; unsigned int *
0x18001ee5e  mov     rcx, rbx; struct ISimpleTableRead2 *
0x18001ee61  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001ee66  mov     ebx, eax
0x18001ee68  test    eax, eax
0x18001ee6a  jns     short loc_18001EEA3
0x18001ee6c  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ee73  jz      short loc_18001EEB0
0x18001ee75  mov     ecx, cs:?g_dwEnableEditWhileRunning@@3KA; ulong g_dwEnableEditWhileRunning
0x18001ee7b  mov     r9, rbp
0x18001ee7e  mov     [rsp+68h+var_38], eax
0x18001ee82  mov     r8d, 26DDh
0x18001ee88  mov     dword ptr [rsp+68h+var_40], ecx
0x18001ee8c  mov     rdx, r14
0x18001ee8f  mov     rcx, cs:g_pDebug
0x18001ee96  mov     [rsp+68h+var_48], r15
0x18001ee9b  call    cs:__imp_PuDbgPrintW
0x18001eea1  jmp     short loc_18001EEB0
0x18001eea3  mov     rax, [rsp+68h+var_28]
0x18001eea8  mov     ecx, [rax]
0x18001eeaa  mov     cs:?g_dwMaxErrorFiles@@3KA, ecx; ulong g_dwMaxErrorFiles
0x18001eeb0  mov     eax, ebx
0x18001eeb2  mov     rbx, [rsp+68h+arg_0]
0x18001eeb7  add     rsp, 50h
0x18001eebb  pop     r15
0x18001eebd  pop     r14
0x18001eebf  pop     rbp
0x18001eec0  retn
```
