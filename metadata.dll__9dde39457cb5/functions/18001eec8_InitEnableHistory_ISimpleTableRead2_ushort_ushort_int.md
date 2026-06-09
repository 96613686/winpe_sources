# InitEnableHistory(ISimpleTableRead2 *,ushort *,ushort *,int)

- ea: `0x18001eec8`
- end: `0x18001f108`
- name: `?InitEnableHistory@@YAJPEAUISimpleTableRead2@@PEAG1H@Z`
- size: `576`
- prototype: `__int64 __fastcall(struct ISimpleTableRead2 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020014`

## callees

- `0x18001d084`
- `0x18001ea74`
- `0x18001eec8`
- `0x180027930`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18001ef7c`
- `IisRTL!PuDbgPrintW` at `0x18001efbc`
- `IisRTL!PuDbgPrintW` at `0x18001f012`
- `IisRTL!PuDbgPrintW` at `0x18001f096`
- `IisRTL!PuDbgPrintW` at `0x18001ef7c`
- `IisRTL!PuDbgPrintW` at `0x18001efbc`
- `IisRTL!PuDbgPrintW` at `0x18001f012`
- `IisRTL!PuDbgPrintW` at `0x18001f096`

## string_xrefs

- `0x18001ef70`: `[InitEnableHistory] Could not fetch enable history. Defaulting to %d. GetComputerValue failed with hr = 0x%x.\n`
- `0x18001f08a`: `[InitEnableHistory] Could not fetch max history files. Defaulting to %d. GetComputerValue failed with hr = 0x%x.\n`
- `0x18001f0ad`: `[InitEnableHistory] Could not fetch max history files. GetComputerValue with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall InitEnableHistory(struct ISimpleTableRead2 *a1, unsigned __int16 *a2, unsigned __int16 *a3, int a4)
{
  int Value; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r8
  void **v12; // [rsp+28h] [rbp-70h]
  __int64 v13; // [rsp+30h] [rbp-68h]
  int v14; // [rsp+40h] [rbp-58h] BYREF
  int v15; // [rsp+44h] [rbp-54h] BYREF
  unsigned int *v16; // [rsp+48h] [rbp-50h] BYREF
  void *v17; // [rsp+50h] [rbp-48h] BYREF

  v14 = 0;
  v16 = (unsigned int *)&v14;
  v15 = 0;
  v17 = &v15;
  Value = GetValue(a1, L"/LM", 2u, L"EnableHistory", 0, (void **)&v16);
  if ( Value == -2145318890 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v12) = g_dwEnableHistory;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        9982,
        "InitEnableHistory",
        L"[InitEnableHistory] Could not fetch enable history. Defaulting to %d. GetComputerValue failed with hr = 0x%x.\n",
        v12,
        -2145318890);
    }
  }
  else
  {
    if ( Value < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        return (unsigned int)Value;
      v9 = L"[InitEnableHistory] Could not fetch enable history. GetGlobalValue failed with hr = 0x%x.\n";
      v10 = 9990;
LABEL_7:
      LODWORD(v12) = Value;
      PuDbgPrintW(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", v10, "InitEnableHistory", v9, v12);
      return (unsigned int)Value;
    }
    g_dwEnableHistory = *v16;
  }
  if ( g_dwEnableEditWhileRunning && !g_dwEnableHistory )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        10002,
        "InitEnableHistory",
        L"[InitEnableHistory] Warning! Edit while running is enabled, while Enable history is disabled. Forcibly enabling history.\n");
    g_dwEnableHistory = 1;
  }
  Value = GetValue(a1, L"/LM", 2u, L"MaxHistoryFiles", 0, &v17);
  if ( Value == -2145318890 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v13) = -2145318890;
      LODWORD(v12) = g_dwMaxHistoryFiles;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        10016,
        "InitEnableHistory",
        L"[InitEnableHistory] Could not fetch max history files. Defaulting to %d. GetComputerValue failed with hr = 0x%x.\n",
        v12,
        v13);
    }
    Value = 0;
    goto LABEL_22;
  }
  if ( Value < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      return (unsigned int)Value;
    v9 = L"[InitEnableHistory] Could not fetch max history files. GetComputerValue with hr = 0x%x.\n";
    v10 = 10024;
    goto LABEL_7;
  }
  g_dwMaxHistoryFiles = *(_DWORD *)v17;
LABEL_22:
  ValidateMaxHistoryFiles();
  if ( g_dwEnableHistory && !a4 )
    return (unsigned int)CreateHistoryFiles(a2, a3, g_ulHistoryMajorVersionNumber, g_dwMaxHistoryFiles);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18001eec8  mov     r11, rsp
0x18001eecb  push    rbx
0x18001eecc  push    rbp
0x18001eecd  push    rsi
0x18001eece  push    rdi
0x18001eecf  push    r13
0x18001eed1  push    r14
0x18001eed3  sub     rsp, 68h
0x18001eed7  lea     rax, [r11-58h]
0x18001eedb  mov     [rsp+98h+var_58], 0
0x18001eee3  mov     [r11-50h], rax
0x18001eee7  mov     edi, r9d
0x18001eeea  lea     rax, [r11-54h]
0x18001eeee  mov     [rsp+98h+var_54], 0
0x18001eef6  mov     [r11-48h], rax
0x18001eefa  lea     r9, aEnablehistory; "EnableHistory"
0x18001ef01  lea     rax, [r11-50h]
0x18001ef05  mov     rbp, r8
0x18001ef08  mov     r14, rdx
0x18001ef0b  mov     [r11-70h], rax
0x18001ef0f  mov     r8d, 2; unsigned int
0x18001ef15  mov     qword ptr [r11-78h], 0
0x18001ef1d  lea     rdx, aLm_0; "/LM"
0x18001ef24  mov     rsi, rcx
0x18001ef27  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001ef2c  mov     ebx, eax
0x18001ef2e  lea     r13, aInitenablehist; "InitEnableHistory"
0x18001ef35  mov     eax, 80210816h
0x18001ef3a  cmp     ebx, eax
0x18001ef3c  jnz     short loc_18001EF84
0x18001ef3e  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ef45  jz      loc_18001EFD4
0x18001ef4b  mov     rcx, cs:g_pDebug
0x18001ef52  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001ef59  mov     [rsp+98h+var_68], eax
0x18001ef5d  mov     r9, r13
0x18001ef60  mov     eax, cs:?g_dwEnableHistory@@3KA; ulong g_dwEnableHistory
0x18001ef66  mov     r8d, 26FEh
0x18001ef6c  mov     dword ptr [rsp+98h+var_70], eax
0x18001ef70  lea     rax, aInitenablehist_0; "[InitEnableHistory] Could not fetch ena"...
0x18001ef77  mov     [rsp+98h+var_78], rax
0x18001ef7c  call    cs:__imp_PuDbgPrintW
0x18001ef82  jmp     short loc_18001EFD4
0x18001ef84  test    ebx, ebx
0x18001ef86  jns     short loc_18001EFC7
0x18001ef88  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ef8f  jz      loc_18001F0F9
0x18001ef95  lea     rax, aInitenablehist_1; "[InitEnableHistory] Could not fetch ena"...
0x18001ef9c  mov     r8d, 2706h
0x18001efa2  mov     rcx, cs:g_pDebug
0x18001efa9  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001efb0  mov     dword ptr [rsp+98h+var_70], ebx
0x18001efb4  mov     r9, r13
0x18001efb7  mov     [rsp+98h+var_78], rax
0x18001efbc  call    cs:__imp_PuDbgPrintW
0x18001efc2  jmp     loc_18001F0F9
0x18001efc7  mov     rax, [rsp+98h+var_50]
0x18001efcc  mov     ecx, [rax]
0x18001efce  mov     cs:?g_dwEnableHistory@@3KA, ecx; ulong g_dwEnableHistory
0x18001efd4  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, 0; ulong g_dwEnableEditWhileRunning
0x18001efdb  jz      short loc_18001F022
0x18001efdd  cmp     cs:?g_dwEnableHistory@@3KA, 0; ulong g_dwEnableHistory
0x18001efe4  jnz     short loc_18001F022
0x18001efe6  test    byte ptr cs:g_dwDebugFlags, 3
0x18001efed  jz      short loc_18001F018
0x18001efef  mov     rcx, cs:g_pDebug
0x18001eff6  lea     rax, aInitenablehist_2; "[InitEnableHistory] Warning! Edit while"...
0x18001effd  mov     r9, r13
0x18001f000  mov     [rsp+98h+var_78], rax
0x18001f005  mov     r8d, 2712h
0x18001f00b  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f012  call    cs:__imp_PuDbgPrintW
0x18001f018  mov     cs:?g_dwEnableHistory@@3KA, 1; ulong g_dwEnableHistory
0x18001f022  lea     rax, [rsp+98h+var_48]
0x18001f027  mov     r8d, 2; unsigned int
0x18001f02d  mov     [rsp+98h+var_70], rax; void **
0x18001f032  lea     r9, aMaxhistoryfile; "MaxHistoryFiles"
0x18001f039  lea     rdx, aLm_0; "/LM"
0x18001f040  mov     [rsp+98h+var_78], 0; unsigned int *
0x18001f049  mov     rcx, rsi; struct ISimpleTableRead2 *
0x18001f04c  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001f051  mov     ebx, eax
0x18001f053  mov     eax, 80210816h
0x18001f058  cmp     ebx, eax
0x18001f05a  jnz     short loc_18001F0A0
0x18001f05c  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f063  jz      short loc_18001F09C
0x18001f065  mov     rcx, cs:g_pDebug
0x18001f06c  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f073  mov     [rsp+98h+var_68], eax
0x18001f077  mov     r9, r13
0x18001f07a  mov     eax, cs:?g_dwMaxHistoryFiles@@3KA; ulong g_dwMaxHistoryFiles
0x18001f080  mov     r8d, 2720h
0x18001f086  mov     dword ptr [rsp+98h+var_70], eax
0x18001f08a  lea     rax, aInitenablehist_4; "[InitEnableHistory] Could not fetch max"...
0x18001f091  mov     [rsp+98h+var_78], rax
0x18001f096  call    cs:__imp_PuDbgPrintW
0x18001f09c  xor     ebx, ebx
0x18001f09e  jmp     short loc_18001F0CC
0x18001f0a0  test    ebx, ebx
0x18001f0a2  jns     short loc_18001F0BF
0x18001f0a4  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f0ab  jz      short loc_18001F0F9
0x18001f0ad  lea     rax, aInitenablehist_3; "[InitEnableHistory] Could not fetch max"...
0x18001f0b4  mov     r8d, 2728h
0x18001f0ba  jmp     loc_18001EFA2
0x18001f0bf  mov     rax, [rsp+98h+var_48]
0x18001f0c4  mov     ecx, [rax]
0x18001f0c6  mov     cs:?g_dwMaxHistoryFiles@@3KA, ecx; ulong g_dwMaxHistoryFiles
0x18001f0cc  call    ?ValidateMaxHistoryFiles@@YAXXZ; ValidateMaxHistoryFiles(void)
0x18001f0d1  cmp     cs:?g_dwEnableHistory@@3KA, 0; ulong g_dwEnableHistory
0x18001f0d8  jz      short loc_18001F0F9
0x18001f0da  test    edi, edi
0x18001f0dc  jnz     short loc_18001F0F9
0x18001f0de  mov     r9d, cs:?g_dwMaxHistoryFiles@@3KA; unsigned int
0x18001f0e5  mov     rdx, rbp; unsigned __int16 *
0x18001f0e8  mov     r8d, cs:?g_ulHistoryMajorVersionNumber@@3KA; unsigned int
0x18001f0ef  mov     rcx, r14; unsigned __int16 *
0x18001f0f2  call    ?CreateHistoryFiles@@YAJPEAG0KK@Z; CreateHistoryFiles(ushort *,ushort *,ulong,ulong)
0x18001f0f7  mov     ebx, eax
0x18001f0f9  mov     eax, ebx
0x18001f0fb  add     rsp, 68h
0x18001f0ff  pop     r14
0x18001f101  pop     r13
0x18001f103  pop     rdi
0x18001f104  pop     rsi
0x18001f105  pop     rbp
0x18001f106  pop     rbx
0x18001f107  retn
```
