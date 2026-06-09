# OpenPrinterInf(_PSETUP_LOCAL_DATA *,PLATFORM,void * *)

- ea: `0x18001a454`
- end: `0x18001a5cf`
- name: `?OpenPrinterInf@@YAJPEAU_PSETUP_LOCAL_DATA@@W4PLATFORM@@PEAPEAX@Z`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001e4f0`
- `0x180022dec`

## callees

- `0x18000b200`
- `0x18000d57c`
- `0x18000d624`
- `0x180012b28`
- `0x18001a454`
- `0x180020b60`
- `0x180034f60`

## import_xrefs

- `SETUPAPI!SetupFindFirstLineW` at `0x18001a4fb`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001a4fb`
- `SETUPAPI!SetupCloseInfFile` at `0x18001a581`
- `SETUPAPI!SetupCloseInfFile` at `0x18001a581`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18001a591`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18001a591`

## string_xrefs

- `0x18001a48e`: `Opening %ws`
- `0x18001a498`: `OpenPrinterInf`
- `0x18001a510`: `OpenPrinterInf`
- `0x18001a5b4`: `OpenPrinterInf`
- `0x18001a509`: `Cross-platform drivers must not reference a LayoutFile. The INF must be installed remotely.`
- `0x18001a53e`: `OpenPrinterInf`
- `0x18001a5aa`: `Error opening INF %ws: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall OpenPrinterInf(const unsigned __int16 **a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // r8
  unsigned __int16 *v7; // rsi
  NCoreLibrary *v8; // rcx
  void *v9; // rdi
  unsigned int LastErrorAsFailHR; // ebx
  struct _INFCONTEXT Context; // [rsp+50h] [rbp-58h] BYREF

  v3 = (int)a2;
  if ( !a1 || !(unsigned int)ValidPlatform(a2) || !v6 )
  {
    v7 = 0;
    LastErrorAsFailHR = -2147024809;
    goto LABEL_13;
  }
  v7 = (unsigned __int16 *)*a1;
  ClassInstallerTelemetry::WriteDbgTraceInfo("OpenPrinterInf", L"Opening %ws", *a1);
  v9 = (void *)OpenPrinterInfFile(v7, 0);
  if ( v9 == (void *)-1LL )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8);
    if ( (LastErrorAsFailHR & 0x80000000) == 0 )
      goto LABEL_7;
LABEL_13:
    ClassInstallerTelemetry::WriteDbgTraceError(
      "OpenPrinterInf",
      L"Error opening INF %ws: hr: 0x%x",
      v7,
      LastErrorAsFailHR);
    return LastErrorAsFailHR;
  }
  LastErrorAsFailHR = 0;
LABEL_7:
  if ( (_DWORD)v3 != MyPlatform )
  {
    memset(&Context, 0, sizeof(Context));
    if ( SetupFindFirstLineW(v9, L"Version", L"LayoutFile", &Context) )
    {
      ClassInstallerTelemetry::WriteDbgTraceError(
        "OpenPrinterInf",
        L"Cross-platform drivers must not reference a LayoutFile. The INF must be installed remotely.");
      SplLogPrinterSetupEvent(
        &SETUP_PARSEINF_FAILED,
        L"OpenPrinterInf",
        L"SetupFindFirstLine failed",
        0,
        *a1,
        a1[1],
        a1[2],
        (const unsigned __int16 *)PlatformEnv[v3],
        0x661u,
        0x80070661);
      LastErrorAsFailHR = -2147023263;
      if ( v9 != (void *)-1LL )
        SetupCloseInfFile(v9);
      goto LABEL_13;
    }
  }
  SetupOpenAppendInfFileW(0, v9, 0);
  *a3 = v9;
  return LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18001a454  push    rbx
0x18001a456  push    rbp
0x18001a457  push    rsi
0x18001a458  push    rdi
0x18001a459  push    r14
0x18001a45b  push    r15
0x18001a45d  sub     rsp, 78h
0x18001a461  movsxd  rbp, edx
0x18001a464  mov     r15, r8
0x18001a467  mov     r14, rcx
0x18001a46a  test    rcx, rcx
0x18001a46d  jz      loc_18001A5A0
0x18001a473  mov     ecx, ebp
0x18001a475  call    ValidPlatform
0x18001a47a  test    eax, eax
0x18001a47c  jz      loc_18001A5A0
0x18001a482  test    r8, r8
0x18001a485  jz      loc_18001A5A0
0x18001a48b  mov     rsi, [r14]
0x18001a48e  lea     rdx, aOpeningWs; "Opening %ws"
0x18001a495  mov     r8, rsi
0x18001a498  lea     rcx, aOpenprinterinf_3; "OpenPrinterInf"
0x18001a49f  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001a4a4  xor     edx, edx
0x18001a4a6  mov     rcx, rsi; unsigned __int16 *
0x18001a4a9  call    OpenPrinterInfFile
0x18001a4ae  mov     rdi, rax
0x18001a4b1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a4b5  jz      short loc_18001A4BB
0x18001a4b7  xor     ebx, ebx
0x18001a4b9  jmp     short loc_18001A4CA
0x18001a4bb  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001a4c0  mov     ebx, eax
0x18001a4c2  test    eax, eax
0x18001a4c4  js      loc_18001A5A7
0x18001a4ca  cmp     ebp, cs:MyPlatform
0x18001a4d0  jz      loc_18001A589
0x18001a4d6  xorps   xmm0, xmm0
0x18001a4d9  lea     r9, [rsp+0A8h+Context]; Context
0x18001a4de  xor     eax, eax
0x18001a4e0  lea     r8, Key; "LayoutFile"
0x18001a4e7  lea     rdx, cszVersion; "Version"
0x18001a4ee  mov     qword ptr [rsp+0A8h+Context.Section], rax
0x18001a4f3  mov     rcx, rdi; InfHandle
0x18001a4f6  movups  xmmword ptr [rsp+0A8h+Context.Inf], xmm0
0x18001a4fb  call    cs:__imp_SetupFindFirstLineW
0x18001a501  test    eax, eax
0x18001a503  jz      loc_18001A589
0x18001a509  lea     rdx, aCrossPlatformD; "Cross-platform drivers must not referen"...
0x18001a510  lea     rcx, aOpenprinterinf_3; "OpenPrinterInf"
0x18001a517  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001a51c  mov     [rsp+0A8h+var_60], 80070661h; unsigned int
0x18001a524  lea     rcx, PlatformEnv
0x18001a52b  mov     rax, [rcx+rbp*8]
0x18001a52f  lea     r8, aSetupfindfirst_0; "SetupFindFirstLine failed"
0x18001a536  mov     [rsp+0A8h+var_68], 661h; unsigned int
0x18001a53e  lea     rdx, aOpenprinterinf_1; "OpenPrinterInf"
0x18001a545  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x18001a54a  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001a551  mov     rax, [r14+10h]
0x18001a555  xor     r9d, r9d; unsigned __int16 *
0x18001a558  mov     [rsp+0A8h+var_78], rax; unsigned __int16 *
0x18001a55d  mov     rax, [r14+8]
0x18001a561  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x18001a566  mov     rax, [r14]
0x18001a569  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x18001a56e  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001a573  mov     ebx, 80070661h
0x18001a578  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001a57c  jz      short loc_18001A5A7
0x18001a57e  mov     rcx, rdi; InfHandle
0x18001a581  call    cs:__imp_SetupCloseInfFile
0x18001a587  jmp     short loc_18001A5A7
0x18001a589  xor     r8d, r8d; ErrorLine
0x18001a58c  mov     rdx, rdi; InfHandle
0x18001a58f  xor     ecx, ecx; FileName
0x18001a591  call    cs:__imp_SetupOpenAppendInfFileW
0x18001a597  mov     [r15], rdi
0x18001a59a  test    ebx, ebx
0x18001a59c  jns     short loc_18001A5C0
0x18001a59e  jmp     short loc_18001A5A7
0x18001a5a0  xor     esi, esi
0x18001a5a2  mov     ebx, 80070057h
0x18001a5a7  mov     r9d, ebx
0x18001a5aa  lea     rdx, aErrorOpeningIn; "Error opening INF %ws: hr: 0x%x"
0x18001a5b1  mov     r8, rsi
0x18001a5b4  lea     rcx, aOpenprinterinf_3; "OpenPrinterInf"
0x18001a5bb  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001a5c0  mov     eax, ebx
0x18001a5c2  add     rsp, 78h
0x18001a5c6  pop     r15
0x18001a5c8  pop     r14
0x18001a5ca  pop     rdi
0x18001a5cb  pop     rsi
0x18001a5cc  pop     rbp
0x18001a5cd  pop     rbx
0x18001a5ce  retn
```
