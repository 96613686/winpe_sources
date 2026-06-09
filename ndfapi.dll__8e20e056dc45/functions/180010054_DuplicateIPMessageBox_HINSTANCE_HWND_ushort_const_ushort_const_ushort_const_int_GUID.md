# DuplicateIPMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ushort const *,int,_GUID *)

- ea: `0x180010054`
- end: `0x180010249`
- name: `?DuplicateIPMessageBox@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBG22HPEAU_GUID@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(HINSTANCE, HWND, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, int pnButton, struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009710`
- `0x180009750`

## callees

- `0x18000a160`
- `0x18000a200`
- `0x18000a9e0`
- `0x18000b810`
- `0x180010054`
- `0x18001b7e4`
- `0x18001f652`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x18001022c`
- `KERNEL32!ReleaseActCtx` at `0x18001022c`
- `KERNEL32!DeactivateActCtx` at `0x180010211`
- `KERNEL32!DeactivateActCtx` at `0x180010211`
- `KERNEL32!GetLastError` at `0x18001021b`
- `KERNEL32!GetLastError` at `0x18001021b`
- `KERNEL32!MulDiv` at `0x180010110`
- `KERNEL32!MulDiv` at `0x180010110`
- `USER32!GetDialogBaseUnits` at `0x1800100fc`
- `USER32!GetDialogBaseUnits` at `0x1800100fc`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x18001015b`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x18001015b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DuplicateIPMessageBox(
        HINSTANCE a1,
        HWND a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        int pnButton,
        struct _GUID *a7)
{
  unsigned __int16 DialogBaseUnits; // ax
  UINT v10; // eax
  HINSTANCE v11; // rdx
  HRESULT v12; // ebx
  struct _GUID *v13; // rbx
  HRESULT v14; // eax
  struct _GUID v15; // xmm0
  HANDLE v17[2]; // [rsp+28h] [rbp-E0h] BYREF
  HANDLE hActCtx; // [rsp+38h] [rbp-D0h] BYREF
  ULONG_PTR ulCookie; // [rsp+40h] [rbp-C8h]
  TASKDIALOGCONFIG v20; // [rsp+48h] [rbp-C0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+E8h] [rbp-20h] BYREF
  NDFHANDLE handle; // [rsp+1A0h] [rbp+98h] BYREF

  handle = a4;
  memset_0(&v20, 0, sizeof(v20));
  v20.cbSize = 160;
  memset(v17, 0, 12);
  v20.hInstance = a1;
  v20.hwndParent = a2;
  v20.pszWindowTitle = (PCWSTR)40081;
  v20.dwFlags = 8;
  if ( pnButton )
  {
    LODWORD(v17[0]) = 40962;
    v20.pButtons = (const TASKDIALOG_BUTTON *)v17;
    *(HANDLE *)((char *)v17 + 4) = (HANDLE)40080;
    v20.cButtons = 1;
  }
  v20.pszContent = a5;
  v20.dwCommonButtons = 32;
  v20.pszMainInstruction = (PCWSTR)40121;
  DialogBaseUnits = GetDialogBaseUnits();
  v10 = MulDiv(518, 4, DialogBaseUnits);
  pnButton = 0;
  v20.cxWidth = v10;
  hActCtx = (HANDLE)-1LL;
  ulCookie = 0;
  v12 = CActivationContextV6::Activate((CActivationContextV6 *)&hActCtx, v11);
  if ( v12 >= 0 )
  {
    v12 = TaskDialogIndirect(&v20, &pnButton, 0, 0);
    if ( v12 >= 0 && pnButton == 40962 )
    {
      v13 = a7;
      handle = 0;
      if ( a7 )
      {
        memset_0(&attributes.type + 1, 0, 0x84u);
        v15 = *v13;
        attributes.type = AT_GUID;
        attributes.pwszName = L"guid";
        attributes.Guid = v15;
        v14 = NdfCreateIncident(L"NetConnection", 1u, &attributes, &handle);
      }
      else
      {
        v14 = NdfCreateConnectivityIncident(&handle);
      }
      v12 = v14;
      if ( v14 >= 0 )
      {
        v12 = NdfExecuteDiagnosis(handle, a2);
        NdfCloseIncident(handle);
      }
    }
  }
  if ( !DeactivateActCtx(0, ulCookie) )
    GetLastError();
  if ( hActCtx != (HANDLE)-1LL )
    ReleaseActCtx(hActCtx);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180010054  mov     rax, rsp
0x180010057  mov     [rax+8], rbx
0x18001005b  mov     [rax+10h], rdi
0x18001005f  mov     [rax+20h], r9
0x180010063  push    rbp
0x180010064  lea     rbp, [rax-78h]
0x180010068  sub     rsp, 170h
0x18001006f  mov     rdi, rdx
0x180010072  mov     rbx, rcx
0x180010075  xor     edx, edx; Val
0x180010077  lea     rcx, [rsp+170h+var_130]; void *
0x18001007c  mov     r8d, 0A0h; Size
0x180010082  call    memset_0
0x180010087  xor     eax, eax
0x180010089  mov     dword ptr [rsp+170h+var_130], 0A0h
0x180010091  mov     qword ptr [rsp+170h+var_150], rax
0x180010096  mov     dword ptr [rsp+170h+var_148], eax
0x18001009a  mov     [rsp+4Ch], rbx
0x18001009f  mov     [rsp+44h], rdi
0x1800100a4  mov     qword ptr [rsp+5Ch], 9C91h
0x1800100ad  mov     dword ptr [rsp+54h], 8
0x1800100b5  cmp     [rbp+70h+pnButton], eax
0x1800100bb  jz      short loc_1800100DF
0x1800100bd  lea     rax, [rsp+170h+var_150]
0x1800100c2  mov     [rsp+170h+var_150], 0A002h
0x1800100ca  mov     [rbp-80h], rax
0x1800100ce  mov     qword ptr [rsp+24h], 9C90h
0x1800100d7  mov     dword ptr [rsp+7Ch], 1
0x1800100df  mov     rax, [rbp+70h+arg_20]
0x1800100e6  mov     [rsp+74h], rax
0x1800100eb  mov     dword ptr [rsp+58h], 20h ; ' '
0x1800100f3  mov     qword ptr [rsp+6Ch], 9CB9h
0x1800100fc  call    cs:__imp_GetDialogBaseUnits
0x180010102  movzx   r8d, ax; nDenominator
0x180010106  mov     edx, 4; nNumerator
0x18001010b  mov     ecx, 206h; nNumber
0x180010110  call    cs:__imp_MulDiv
0x180010116  lea     rcx, [rsp+170h+hActCtx]; this
0x18001011b  mov     [rbp+70h+pnButton], 0
0x180010125  mov     [rbp+70h+var_94], eax
0x180010128  mov     [rsp+170h+hActCtx], 0FFFFFFFFFFFFFFFFh
0x180010131  mov     [rsp+170h+ulCookie], 0
0x18001013a  call    ?Activate@CActivationContextV6@@QEAAJPEAUHINSTANCE__@@@Z; CActivationContextV6::Activate(HINSTANCE__ *)
0x18001013f  mov     ebx, eax
0x180010141  test    eax, eax
0x180010143  js      loc_18001020A
0x180010149  xor     r9d, r9d; pfVerificationFlagChecked
0x18001014c  lea     rdx, [rbp+70h+pnButton]; pnButton
0x180010153  xor     r8d, r8d; pnRadioButton
0x180010156  lea     rcx, [rsp+170h+var_130]; pTaskConfig
0x18001015b  call    cs:__imp_TaskDialogIndirect
0x180010161  mov     ebx, eax
0x180010163  test    eax, eax
0x180010165  js      loc_18001020A
0x18001016b  cmp     [rbp+70h+pnButton], 0A002h
0x180010175  jnz     loc_18001020A
0x18001017b  mov     rbx, [rbp+70h+arg_30]
0x180010182  mov     [rbp+70h+handle], 0
0x18001018d  test    rbx, rbx
0x180010190  jnz     short loc_1800101A0
0x180010192  lea     rcx, [rbp+70h+handle]; handle
0x180010199  call    NdfCreateConnectivityIncident
0x18001019e  jmp     short loc_1800101E7
0x1800101a0  xor     edx, edx; Val
0x1800101a2  lea     rcx, [rbp+70h+attributes+0Ch]; void *
0x1800101a6  mov     r8d, 84h; Size
0x1800101ac  call    memset_0
0x1800101b1  movups  xmm0, xmmword ptr [rbx]
0x1800101b4  lea     rax, aGuid; "guid"
0x1800101bb  mov     [rbp+70h+attributes.type], 0Bh
0x1800101c2  lea     r9, [rbp+70h+handle]; handle
0x1800101c9  mov     [rbp+70h+attributes.pwszName], rax
0x1800101cd  lea     r8, [rbp+70h+attributes]; attributes
0x1800101d1  mov     edx, 1; celt
0x1800101d6  lea     rcx, aNetconnection; "NetConnection"
0x1800101dd  movdqu  xmmword ptr [rbp+70h+attributes.10h], xmm0
0x1800101e2  call    NdfCreateIncident
0x1800101e7  mov     ebx, eax
0x1800101e9  test    eax, eax
0x1800101eb  js      short loc_18001020A
0x1800101ed  mov     rcx, [rbp+70h+handle]; handle
0x1800101f4  mov     rdx, rdi; hwnd
0x1800101f7  call    NdfExecuteDiagnosis
0x1800101fc  mov     rcx, [rbp+70h+handle]; handle
0x180010203  mov     ebx, eax
0x180010205  call    NdfCloseIncident
0x18001020a  mov     rdx, [rsp+170h+ulCookie]; ulCookie
0x18001020f  xor     ecx, ecx; dwFlags
0x180010211  call    cs:__imp_DeactivateActCtx
0x180010217  test    eax, eax
0x180010219  jnz     short loc_180010221
0x18001021b  call    cs:__imp_GetLastError
0x180010221  mov     rcx, [rsp+170h+hActCtx]; hActCtx
0x180010226  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001022a  jz      short loc_180010232
0x18001022c  call    cs:__imp_ReleaseActCtx
0x180010232  lea     r11, [rsp+170h+var_s0]
0x18001023a  mov     eax, ebx
0x18001023c  mov     rbx, [r11+10h]
0x180010240  mov     rdi, [r11+18h]
0x180010244  mov     rsp, r11
0x180010247  pop     rbp
0x180010248  retn
```
