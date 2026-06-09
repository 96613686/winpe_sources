# InitializeGlobalsFromXML(ISimpleTableRead2 *,ushort *,ushort *,IIS_CRYPTO_STORAGE * *,char *,int,_FILETIME *,CEtwTracer *,int)

- ea: `0x180020014`
- end: `0x180020195`
- name: `?InitializeGlobalsFromXML@@YAJPEAUISimpleTableRead2@@PEAG1PEAPEAVIIS_CRYPTO_STORAGE@@PEADHPEAU_FILETIME@@PEAVCEtwTracer@@H@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct ISimpleTableRead2 *, unsigned __int16 *, unsigned __int16 *, struct IIS_CRYPTO_STORAGE **, char *, int, struct _FILETIME *, struct CEtwTracer *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180021c40`

## callees

- `0x180015808`
- `0x18001ebec`
- `0x18001ec90`
- `0x18001eec8`
- `0x18001f2c8`
- `0x180020014`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020080`
- `KERNEL32!GetLastError` at `0x180020080`
- `KERNEL32!GetFileAttributesExW` at `0x180020076`
- `KERNEL32!GetFileAttributesExW` at `0x180020076`
- `IisRTL!PuDbgPrintW` at `0x1800200cd`
- `IisRTL!PuDbgPrintW` at `0x1800200cd`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180020148`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180020148`

## string_xrefs

- `0x1800200bb`: `[InitializeGlobalsFromXML] GetFileAttributesExW failed with hr = 0x%x.\n`
- `0x1800200a9`: `InitializeGlobalsFromXML`

## pseudocode

```c
__int64 __fastcall InitializeGlobalsFromXML(
        struct ISimpleTableRead2 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IIS_CRYPTO_STORAGE **a4,
        char *a5,
        int a6,
        struct _FILETIME *a7,
        struct CEtwTracer *a8,
        int a9)
{
  signed int LastError; // eax
  signed int v15; // [rsp+28h] [rbp-59h]
  int inited; // [rsp+40h] [rbp-41h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-39h] BYREF
  struct _FILETIME v18[2]; // [rsp+58h] [rbp-29h] BYREF
  int v19; // [rsp+68h] [rbp-19h]

  inited = 0;
  v19 = 0;
  FileInformation = 0;
  *(_OWORD *)&v18[0].dwLowDateTime = 0;
  if ( GetFileAttributesExW(a2, GetFileExInfoStandard, &FileInformation) )
  {
    if ( a7 )
      *a7 = *(struct _FILETIME *)&v18[0].dwHighDateTime;
    CMDBaseObject::SetLastChangeTime(g_pboMasterRoot, (struct _FILETIME *)&v18[0].dwHighDateTime);
    inited = InitSessionKey(a1, a4, a5, a9);
    if ( inited >= 0 )
    {
      InitEditWhileRunning(a1);
      InitChangeNumber(a1);
      InitEnableHistory(a1, a2, a3, a6);
    }
    else if ( *((_DWORD *)a8 + 2) && (*((_BYTE *)a8 + 40) & 1) != 0 && *((_DWORD *)a8 + 11) )
    {
      CEtwTracer::EtwTraceEvent(a8, (const struct _GUID *)IISAdminStatupGuid, 0x17u, &inited, 4, 0, 0);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    inited = LastError;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v15 = LastError;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        11196,
        "InitializeGlobalsFromXML",
        L"[InitializeGlobalsFromXML] GetFileAttributesExW failed with hr = 0x%x.\n",
        v15);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180020014  push    rbp
0x180020016  push    rbx
0x180020017  push    rsi
0x180020018  push    rdi
0x180020019  push    r12
0x18002001b  push    r13
0x18002001d  push    r14
0x18002001f  push    r15
0x180020021  lea     rbp, [rsp-7]
0x180020026  sub     rsp, 88h
0x18002002d  mov     rax, cs:__security_cookie
0x180020034  xor     rax, rsp
0x180020037  mov     [rbp+3Fh+var_50], rax
0x18002003b  mov     r13, [rbp+3Fh+arg_20]
0x18002003f  mov     r14, rdx
0x180020042  mov     rsi, [rbp+3Fh+arg_30]
0x180020046  xorps   xmm0, xmm0
0x180020049  mov     rbx, [rbp+3Fh+arg_38]
0x180020050  mov     r15, r8
0x180020053  mov     rdi, rcx
0x180020056  mov     [rbp+3Fh+var_80], 0
0x18002005d  xor     eax, eax
0x18002005f  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x180020063  mov     rcx, r14; lpFileName
0x180020066  mov     [rbp+3Fh+var_58], eax
0x180020069  xor     edx, edx; fInfoLevelId
0x18002006b  mov     r12, r9
0x18002006e  movups  [rbp+3Fh+FileInformation], xmm0
0x180020072  movups  xmmword ptr [rbp+3Fh+var_68.dwLowDateTime], xmm0
0x180020076  call    cs:__imp_GetFileAttributesExW
0x18002007c  test    eax, eax
0x18002007e  jnz     short loc_1800200D8
0x180020080  call    cs:__imp_GetLastError
0x180020086  test    eax, eax
0x180020088  jle     short loc_180020092
0x18002008a  movzx   eax, ax
0x18002008d  or      eax, 80070000h
0x180020092  test    byte ptr cs:g_dwDebugFlags, 3
0x180020099  mov     [rbp+3Fh+var_80], eax
0x18002009c  jz      loc_180020172
0x1800200a2  mov     rcx, cs:g_pDebug
0x1800200a9  lea     r9, aInitializeglob_2; "InitializeGlobalsFromXML"
0x1800200b0  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800200b4  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800200bb  lea     rax, aInitializeglob_1; "[InitializeGlobalsFromXML] GetFileAttri"...
0x1800200c2  mov     r8d, 2BBCh
0x1800200c8  mov     [rsp+0C0h+var_A0], rax
0x1800200cd  call    cs:__imp_PuDbgPrintW
0x1800200d3  jmp     loc_180020172
0x1800200d8  test    rsi, rsi
0x1800200db  jz      short loc_1800200E4
0x1800200dd  mov     rax, qword ptr [rbp+3Fh+var_68.dwHighDateTime]
0x1800200e1  mov     [rsi], rax
0x1800200e4  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x1800200eb  lea     rdx, [rbp+3Fh+var_68.dwHighDateTime]; struct _FILETIME *
0x1800200ef  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x1800200f4  mov     r9d, [rbp+3Fh+arg_40]; int
0x1800200fb  mov     r8, r13; char *
0x1800200fe  mov     rdx, r12; struct IIS_CRYPTO_STORAGE **
0x180020101  mov     rcx, rdi; struct ISimpleTableRead2 *
0x180020104  call    ?InitSessionKey@@YAJPEAUISimpleTableRead2@@PEAPEAVIIS_CRYPTO_STORAGE@@PEADH@Z; InitSessionKey(ISimpleTableRead2 *,IIS_CRYPTO_STORAGE * *,char *,int)
0x180020109  xor     ecx, ecx
0x18002010b  mov     [rbp+3Fh+var_80], eax
0x18002010e  test    eax, eax
0x180020110  jns     short loc_180020150
0x180020112  cmp     [rbx+8], ecx
0x180020115  jz      short loc_180020172
0x180020117  test    byte ptr [rbx+28h], 1
0x18002011b  jz      short loc_180020172
0x18002011d  cmp     dword ptr [rbx+2Ch], 1
0x180020121  jb      short loc_180020172
0x180020123  mov     [rsp+0C0h+var_90], rcx
0x180020128  lea     r8d, [rcx+17h]
0x18002012c  mov     [rsp+0C0h+var_98], rcx
0x180020131  lea     r9, [rbp+3Fh+var_80]
0x180020135  mov     rcx, rbx
0x180020138  mov     [rsp+0C0h+var_A0], 4
0x180020141  lea     rdx, IISAdminStatupGuid
0x180020148  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18002014e  jmp     short loc_180020172
0x180020150  mov     rcx, rdi; struct ISimpleTableRead2 *
0x180020153  call    ?InitEditWhileRunning@@YAJPEAUISimpleTableRead2@@@Z; InitEditWhileRunning(ISimpleTableRead2 *)
0x180020158  mov     rcx, rdi; struct ISimpleTableRead2 *
0x18002015b  call    ?InitChangeNumber@@YAJPEAUISimpleTableRead2@@@Z; InitChangeNumber(ISimpleTableRead2 *)
0x180020160  mov     r9d, [rbp+3Fh+arg_28]; int
0x180020164  mov     r8, r15; unsigned __int16 *
0x180020167  mov     rdx, r14; unsigned __int16 *
0x18002016a  mov     rcx, rdi; struct ISimpleTableRead2 *
0x18002016d  call    ?InitEnableHistory@@YAJPEAUISimpleTableRead2@@PEAG1H@Z; InitEnableHistory(ISimpleTableRead2 *,ushort *,ushort *,int)
0x180020172  mov     eax, [rbp+3Fh+var_80]
0x180020175  mov     rcx, [rbp+3Fh+var_50]
0x180020179  xor     rcx, rsp; StackCookie
0x18002017c  call    __security_check_cookie
0x180020181  add     rsp, 88h
0x180020188  pop     r15
0x18002018a  pop     r14
0x18002018c  pop     r13
0x18002018e  pop     r12
0x180020190  pop     rdi
0x180020191  pop     rsi
0x180020192  pop     rbx
0x180020193  pop     rbp
0x180020194  retn
```
