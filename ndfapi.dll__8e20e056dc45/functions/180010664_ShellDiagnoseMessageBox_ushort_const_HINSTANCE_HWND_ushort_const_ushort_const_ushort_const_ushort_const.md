# ShellDiagnoseMessageBox(ushort const *,HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180010664`
- end: `0x180010845`
- name: `?ShellDiagnoseMessageBox@@YAJPEBGPEAUHINSTANCE__@@PEAUHWND__@@0000@Z`
- size: `481`
- prototype: `__int64 __usercall@<rax>(LPCWSTR UNCPath@<rcx>, HINSTANCE@<rdx>, HWND@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015590`

## callees

- `0x18000a160`
- `0x18000afb0`
- `0x18000b810`
- `0x180010410`
- `0x180010664`
- `0x18001b7e4`
- `0x18001f652`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x180010831`
- `KERNEL32!ReleaseActCtx` at `0x180010831`
- `KERNEL32!DeactivateActCtx` at `0x180010816`
- `KERNEL32!DeactivateActCtx` at `0x180010816`
- `KERNEL32!GetLastError` at `0x180010820`
- `KERNEL32!GetLastError` at `0x180010820`
- `KERNEL32!MulDiv` at `0x180010726`
- `KERNEL32!MulDiv` at `0x180010726`
- `USER32!GetDialogBaseUnits` at `0x180010712`
- `USER32!GetDialogBaseUnits` at `0x180010712`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x18001076b`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x18001076b`

## pseudocode

```c
__int64 __fastcall ShellDiagnoseMessageBox(
        LPCWSTR UNCPath,
        HINSTANCE a2,
        HWND a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        WCHAR *handle)
{
  TASKDIALOG_FLAGS v10; // eax
  unsigned __int16 DialogBaseUnits; // ax
  UINT v12; // eax
  HINSTANCE v13; // rdx
  HRESULT v14; // edi
  HRESULT SharingIncident; // eax
  unsigned int v16; // r8d
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rbx
  HRESULT v19; // eax
  unsigned int v20; // r8d
  HANDLE hActCtx; // [rsp+20h] [rbp-A1h] BYREF
  ULONG_PTR ulCookie; // [rsp+28h] [rbp-99h]
  int v24; // [rsp+30h] [rbp-91h] BYREF
  __int64 v25; // [rsp+34h] [rbp-8Dh]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-81h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]
  HINSTANCE pnButton; // [rsp+118h] [rbp+57h] BYREF

  pnButton = a2;
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  pTaskConfig.hInstance = g_hinstDll;
  v24 = 40962;
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v24;
  v10 = 73;
  if ( a3 )
    v10 = 65609;
  v25 = 40080;
  pTaskConfig.dwFlags = v10;
  pTaskConfig.pszExpandedInformation = handle;
  pTaskConfig.hwndParent = a3;
  pTaskConfig.cbSize = 160;
  pTaskConfig.pszWindowTitle = (PCWSTR)40081;
  pTaskConfig.cButtons = 1;
  pTaskConfig.dwCommonButtons = 8;
  pTaskConfig.pszMainInstruction = a4;
  pTaskConfig.pszContent = (PCWSTR)40083;
  pTaskConfig.pszExpandedControlText = (PCWSTR)40071;
  pTaskConfig.pszCollapsedControlText = (PCWSTR)40070;
  DialogBaseUnits = GetDialogBaseUnits();
  v12 = MulDiv(518, 4, DialogBaseUnits);
  LODWORD(pnButton) = 0;
  pTaskConfig.cxWidth = v12;
  hActCtx = (HANDLE)-1LL;
  ulCookie = 0;
  v14 = CActivationContextV6::Activate((CActivationContextV6 *)&hActCtx, v13);
  if ( v14 >= 0 )
  {
    v14 = TaskDialogIndirect(&pTaskConfig, (int *)&pnButton, 0, 0);
    if ( v14 >= 0 )
    {
      if ( (_DWORD)pnButton == 40962 )
      {
        handle = 0;
        SharingIncident = NdfCreateSharingIncident(UNCPath, (NDFHANDLE *)&handle);
        v14 = SharingIncident;
        if ( SharingIncident < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2B,
            v16,
            (const char *)(unsigned int)SharingIncident,
            (int)hActCtx);
          v17 = handle;
          if ( !handle )
            goto LABEL_16;
          goto LABEL_8;
        }
        v18 = handle;
        v19 = NdfExecuteDiagnosis(handle, 0);
        v14 = v19;
        if ( v19 >= 0 )
        {
          if ( v18 )
            NdfCloseIncident(v18);
          v14 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x2C, v20, (const char *)(unsigned int)v19, (int)hActCtx);
          if ( v18 )
          {
            v17 = v18;
LABEL_8:
            NdfCloseIncident(v17);
          }
        }
      }
      else
      {
        v14 = ((_DWORD)pnButton != 2) - 2147467260;
      }
    }
  }
LABEL_16:
  if ( !DeactivateActCtx(0, ulCookie) )
    GetLastError();
  if ( hActCtx != (HANDLE)-1LL )
    ReleaseActCtx(hActCtx);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180010664  mov     [rsp-8+pnButton], rdx
0x180010669  push    rbp
0x18001066a  push    rbx
0x18001066b  push    rsi
0x18001066c  push    rdi
0x18001066d  lea     rbp, [rsp-27h]
0x180010672  sub     rsp, 0E8h
0x180010679  mov     rbx, r8
0x18001067c  mov     rsi, rcx
0x18001067f  mov     r8d, 0A0h; Size
0x180010685  lea     rcx, [rsp+100h+pTaskConfig]; void *
0x18001068a  xor     edx, edx; Val
0x18001068c  mov     rdi, r9
0x18001068f  call    memset_0
0x180010694  mov     rax, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstDll
0x18001069b  mov     ecx, 10049h
0x1800106a0  mov     [rbp+3Fh+pTaskConfig.hInstance], rax
0x1800106a4  test    rbx, rbx
0x1800106a7  lea     rax, [rsp+100h+var_D0]
0x1800106ac  mov     [rsp+100h+var_D0], 0A002h
0x1800106b4  mov     [rbp+3Fh+pTaskConfig.pButtons], rax
0x1800106b8  mov     eax, 49h ; 'I'
0x1800106bd  cmovnz  eax, ecx
0x1800106c0  mov     [rsp+100h+var_CC], 9C90h
0x1800106c9  mov     [rbp+3Fh+pTaskConfig.dwFlags], eax
0x1800106cc  mov     rax, [rbp+3Fh+handle]
0x1800106d0  mov     [rbp+3Fh+pTaskConfig.pszExpandedInformation], rax
0x1800106d4  mov     [rbp+3Fh+pTaskConfig.hwndParent], rbx
0x1800106d8  mov     [rsp+100h+pTaskConfig.cbSize], 0A0h
0x1800106e0  mov     [rbp+3Fh+pTaskConfig.pszWindowTitle], 9C91h
0x1800106e8  mov     [rbp+3Fh+pTaskConfig.cButtons], 1
0x1800106ef  mov     [rbp+3Fh+pTaskConfig.dwCommonButtons], 8
0x1800106f6  mov     [rbp+3Fh+pTaskConfig.pszMainInstruction], rdi
0x1800106fa  mov     [rbp+3Fh+pTaskConfig.pszContent], 9C93h
0x180010702  mov     [rbp+3Fh+pTaskConfig.pszExpandedControlText], 9C87h
0x18001070a  mov     [rbp+3Fh+pTaskConfig.pszCollapsedControlText], 9C86h
0x180010712  call    cs:__imp_GetDialogBaseUnits
0x180010718  movzx   r8d, ax; nDenominator
0x18001071c  mov     edx, 4; nNumerator
0x180010721  mov     ecx, 206h; nNumber
0x180010726  call    cs:__imp_MulDiv
0x18001072c  lea     rcx, [rsp+100h+hActCtx]; this
0x180010731  mov     dword ptr [rbp+3Fh+pnButton], 0
0x180010738  mov     [rbp+3Fh+pTaskConfig.cxWidth], eax
0x18001073b  mov     [rsp+100h+hActCtx], 0FFFFFFFFFFFFFFFFh; int
0x180010744  mov     [rsp+100h+ulCookie], 0
0x18001074d  call    ?Activate@CActivationContextV6@@QEAAJPEAUHINSTANCE__@@@Z; CActivationContextV6::Activate(HINSTANCE__ *)
0x180010752  mov     edi, eax
0x180010754  test    eax, eax
0x180010756  js      loc_18001080F
0x18001075c  xor     r9d, r9d; pfVerificationFlagChecked
0x18001075f  lea     rdx, [rbp+3Fh+pnButton]; pnButton
0x180010763  xor     r8d, r8d; pnRadioButton
0x180010766  lea     rcx, [rsp+100h+pTaskConfig]; pTaskConfig
0x18001076b  call    cs:__imp_TaskDialogIndirect
0x180010771  mov     edi, eax
0x180010773  test    eax, eax
0x180010775  js      loc_18001080F
0x18001077b  cmp     dword ptr [rbp+3Fh+pnButton], 0A002h
0x180010782  jnz     short loc_1800107FF
0x180010784  lea     rdx, [rbp+3Fh+handle]; handle
0x180010788  mov     [rbp+3Fh+handle], 0
0x180010790  mov     rcx, rsi; UNCPath
0x180010793  call    NdfCreateSharingIncident
0x180010798  mov     edi, eax
0x18001079a  test    eax, eax
0x18001079c  jns     short loc_1800107BF
0x18001079e  mov     rcx, [rbp+47h]; this
0x1800107a2  mov     r9d, eax; char *
0x1800107a5  mov     edx, 2Bh ; '+'; void *
0x1800107aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107af  mov     rcx, [rbp+3Fh+handle]; handle
0x1800107b3  test    rcx, rcx
0x1800107b6  jz      short loc_18001080F
0x1800107b8  call    NdfCloseIncident
0x1800107bd  jmp     short loc_18001080F
0x1800107bf  mov     rbx, [rbp+3Fh+handle]
0x1800107c3  xor     edx, edx; hwnd
0x1800107c5  mov     rcx, rbx; handle
0x1800107c8  call    NdfExecuteDiagnosis
0x1800107cd  mov     edi, eax
0x1800107cf  test    eax, eax
0x1800107d1  jns     short loc_1800107EE
0x1800107d3  mov     rcx, [rbp+47h]; this
0x1800107d7  mov     r9d, eax; char *
0x1800107da  mov     edx, 2Ch ; ','; void *
0x1800107df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107e4  test    rbx, rbx
0x1800107e7  jz      short loc_18001080F
0x1800107e9  mov     rcx, rbx
0x1800107ec  jmp     short loc_1800107B8
0x1800107ee  test    rbx, rbx
0x1800107f1  jz      short loc_1800107FB
0x1800107f3  mov     rcx, rbx; handle
0x1800107f6  call    NdfCloseIncident
0x1800107fb  xor     edi, edi
0x1800107fd  jmp     short loc_18001080F
0x1800107ff  xor     edi, edi
0x180010801  cmp     dword ptr [rbp+3Fh+pnButton], 2
0x180010805  setnz   dil
0x180010809  add     edi, 80004004h
0x18001080f  mov     rdx, [rsp+100h+ulCookie]; ulCookie
0x180010814  xor     ecx, ecx; dwFlags
0x180010816  call    cs:__imp_DeactivateActCtx
0x18001081c  test    eax, eax
0x18001081e  jnz     short loc_180010826
0x180010820  call    cs:__imp_GetLastError
0x180010826  mov     rcx, [rsp+100h+hActCtx]; hActCtx
0x18001082b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001082f  jz      short loc_180010837
0x180010831  call    cs:__imp_ReleaseActCtx
0x180010837  mov     eax, edi
0x180010839  add     rsp, 0E8h
0x180010840  pop     rdi
0x180010841  pop     rsi
0x180010842  pop     rbx
0x180010843  pop     rbp
0x180010844  retn
```
