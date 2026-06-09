# ReuploadFiles(void)

- ea: `0x14003dad0`
- end: `0x14003ddc2`
- name: `?ReuploadFiles@@YAJXZ`
- size: `754`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x14003eb60`

## callees

- `0x1400039b1`
- `0x14000706c`
- `0x1400070b0`
- `0x140020420`
- `0x140029d98`
- `0x14003dad0`
- `0x14003e5f0`
- `0x14003e700`
- `0x1400433c8`
- `0x14005055c`
- `0x1400516a4`
- `0x140051f74`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003dd22`
- `KERNEL32!GetLastError` at `0x14003dd22`
- `KERNEL32!HeapAlloc` at `0x14003db51`
- `KERNEL32!HeapAlloc` at `0x14003dc26`
- `KERNEL32!HeapAlloc` at `0x14003db51`
- `KERNEL32!HeapAlloc` at `0x14003dc26`
- `KERNEL32!HeapFree` at `0x14003dd7e`
- `KERNEL32!HeapFree` at `0x14003dd9e`
- `KERNEL32!HeapFree` at `0x14003dd7e`
- `KERNEL32!HeapFree` at `0x14003dd9e`
- `KERNEL32!GetProcessHeap` at `0x14003db3a`
- `KERNEL32!GetProcessHeap` at `0x14003dc0f`
- `KERNEL32!GetProcessHeap` at `0x14003dd6a`
- `KERNEL32!GetProcessHeap` at `0x14003dd8a`
- `KERNEL32!GetProcessHeap` at `0x14003db3a`
- `KERNEL32!GetProcessHeap` at `0x14003dc0f`
- `KERNEL32!GetProcessHeap` at `0x14003dd6a`
- `KERNEL32!GetProcessHeap` at `0x14003dd8a`
- `KERNEL32!DeleteFileW` at `0x14003dd0e`
- `KERNEL32!DeleteFileW` at `0x14003dd0e`

## pseudocode

```c
__int64 ReuploadFiles(void)
{
  int updated; // eax
  signed int v1; // ebx
  int v2; // r9d
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // rsi
  int SupportProvider; // eax
  int v6; // r9d
  HANDLE v7; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  Configuration *v10; // rcx
  int v11; // r9d
  signed int LastError; // eax
  HANDLE v13; // rax
  HANDLE v14; // rax
  unsigned __int16 *v16[9]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v17[7]; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned int v18; // [rsp+C0h] [rbp+67h] BYREF

  memset_0(v16, 0, 0x58u);
  v18 = 0;
  updated = UpdateUITextByID(0x15Fu);
  v1 = updated;
  if ( updated >= 0 )
  {
    g_ErrorContext = 405;
    ProcessHeap = GetProcessHeap();
    v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
    if ( !v4 )
    {
      updated = -2147024882;
      v2 = 1077;
      v1 = -2147024882;
      goto LABEL_3;
    }
    memset_0(v16, 0, 0x58u);
    v17[1] = v17;
    v17[0] = v17;
    SupportProvider = StringCchPrintfW(v4, 0x104u, L"%s\\%s", g_HistoryDirectory, L"results.cab");
    v1 = SupportProvider;
    if ( SupportProvider >= 0 )
    {
      g_ErrorContext = 351;
      SupportProvider = QuerySupportProvider(*((unsigned __int16 **)Config + 12), v16);
      v1 = SupportProvider;
      if ( SupportProvider >= 0 )
      {
        v7 = GetProcessHeap();
        v8 = (unsigned __int16 *)HeapAlloc(v7, 0, 0x800u);
        v9 = v8;
        if ( v8 )
        {
          v1 = StringCchCopyW(v8, 0x400u, v16[5]);
          if ( v1 >= 0 )
          {
            Configuration::SupportName(v10, v9);
            g_ErrorContext = 410;
            SupportProvider = GetSupportResponse(*((unsigned __int16 **)Config + 14), v16, &v18);
            v1 = SupportProvider;
            if ( SupportProvider < 0 )
            {
              v6 = 1109;
              goto LABEL_8;
            }
            *((_QWORD *)Config + 35) = v16;
            SupportProvider = UpdateUITextByID(0x161u);
            v1 = SupportProvider;
            if ( SupportProvider < 0 )
            {
              v6 = 1114;
              goto LABEL_8;
            }
            SupportProvider = UploadFile(v4);
            v1 = SupportProvider;
            if ( SupportProvider < 0 )
            {
              v6 = 1117;
              goto LABEL_8;
            }
            if ( SupportProvider )
              goto LABEL_32;
            SupportProvider = HistoryFileRemoveSupportKey();
            v1 = SupportProvider;
            if ( SupportProvider < 0 )
            {
              v6 = 1125;
              goto LABEL_8;
            }
            if ( DeleteFileW(v4) )
            {
              v1 = 0;
              goto LABEL_32;
            }
            LastError = GetLastError();
            v1 = LastError;
            if ( LastError > 0 )
              v1 = (unsigned __int16)LastError | 0x80070000;
            if ( v1 >= 0 )
              goto LABEL_32;
            v9 = 0;
            v11 = 1128;
          }
          else
          {
            v11 = 1099;
          }
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ReuploadFiles", v11, v1);
          if ( v9 )
          {
            v13 = GetProcessHeap();
            HeapFree(v13, 0, v9);
          }
          goto LABEL_32;
        }
        SupportProvider = -2147024882;
        v6 = 1096;
        v1 = -2147024882;
      }
      else
      {
        v6 = 1094;
      }
    }
    else
    {
      v6 = 1087;
    }
LABEL_8:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ReuploadFiles", v6, SupportProvider);
LABEL_32:
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v4);
    goto LABEL_33;
  }
  v2 = 1074;
LABEL_3:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ReuploadFiles", v2, updated);
LABEL_33:
  CloseSupportResponse((struct _SUPPORT_RESPONSE *)v16);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14003dad0  push    rbp
0x14003dad2  push    rbx
0x14003dad3  push    rsi
0x14003dad4  push    rdi
0x14003dad5  lea     rbp, [rsp-3Fh]
0x14003dada  sub     rsp, 98h
0x14003dae1  xor     edx, edx; Val
0x14003dae3  lea     rcx, [rbp+57h+var_80]; void *
0x14003dae7  lea     r8d, [rdx+58h]; Size
0x14003daeb  call    memset_0
0x14003daf0  mov     edi, 15Fh
0x14003daf5  mov     [rbp+57h+arg_0], 0
0x14003dafc  mov     ecx, edi; uID
0x14003dafe  call    ?UpdateUITextByID@@YAJI@Z; UpdateUITextByID(uint)
0x14003db03  mov     ebx, eax
0x14003db05  test    eax, eax
0x14003db07  jns     short loc_14003DB30
0x14003db09  mov     r9d, 432h
0x14003db0f  lea     r8, aReuploadfiles; "ReuploadFiles"
0x14003db16  mov     dword ptr [rsp+0B0h+var_90], eax
0x14003db1a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003db21  mov     ecx, 1; Level
0x14003db26  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003db2b  jmp     loc_14003DDAA
0x14003db30  mov     cs:?g_ErrorContext@@3IC, 195h; uint volatile g_ErrorContext
0x14003db3a  call    cs:__imp_GetProcessHeap
0x14003db41  nop     dword ptr [rax+rax+00h]
0x14003db46  xor     edx, edx; dwFlags
0x14003db48  mov     r8d, 208h; dwBytes
0x14003db4e  mov     rcx, rax; hHeap
0x14003db51  call    cs:__imp_HeapAlloc
0x14003db58  nop     dword ptr [rax+rax+00h]
0x14003db5d  mov     rsi, rax
0x14003db60  test    rax, rax
0x14003db63  jnz     short loc_14003DB74
0x14003db65  mov     eax, 8007000Eh
0x14003db6a  mov     r9d, 435h
0x14003db70  mov     ebx, eax
0x14003db72  jmp     short loc_14003DB0F
0x14003db74  xor     edx, edx; Val
0x14003db76  lea     rcx, [rbp+57h+var_80]; void *
0x14003db7a  lea     r8d, [rdx+58h]; Size
0x14003db7e  call    memset_0
0x14003db83  mov     r9, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x14003db8a  lea     rax, [rbp+57h+var_38]
0x14003db8e  mov     [rbp+57h+var_30], rax
0x14003db92  lea     r8, aSS_1; "%s\\%s"
0x14003db99  lea     rax, [rbp+57h+var_38]
0x14003db9d  mov     edx, 104h; unsigned __int64
0x14003dba2  mov     [rbp+57h+var_38], rax
0x14003dba6  mov     rcx, rsi; unsigned __int16 *
0x14003dba9  lea     rax, aResultsCab; "results.cab"
0x14003dbb0  mov     [rsp+0B0h+var_90], rax
0x14003dbb5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003dbba  mov     ebx, eax
0x14003dbbc  test    eax, eax
0x14003dbbe  jns     short loc_14003DBE7
0x14003dbc0  mov     r9d, 43Fh
0x14003dbc6  lea     r8, aReuploadfiles; "ReuploadFiles"
0x14003dbcd  mov     dword ptr [rsp+0B0h+var_90], eax
0x14003dbd1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003dbd8  mov     ecx, 1; Level
0x14003dbdd  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003dbe2  jmp     loc_14003DD8A
0x14003dbe7  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003dbee  lea     rdx, [rbp+57h+var_80]; struct _SUPPORT_RESPONSE *
0x14003dbf2  mov     cs:?g_ErrorContext@@3IC, edi; uint volatile g_ErrorContext
0x14003dbf8  mov     rcx, [rcx+60h]; unsigned __int16 *
0x14003dbfc  call    ?QuerySupportProvider@@YAJPEAGPEAU_SUPPORT_RESPONSE@@@Z; QuerySupportProvider(ushort *,_SUPPORT_RESPONSE *)
0x14003dc01  mov     ebx, eax
0x14003dc03  test    eax, eax
0x14003dc05  jns     short loc_14003DC0F
0x14003dc07  mov     r9d, 446h
0x14003dc0d  jmp     short loc_14003DBC6
0x14003dc0f  call    cs:__imp_GetProcessHeap
0x14003dc16  nop     dword ptr [rax+rax+00h]
0x14003dc1b  xor     edx, edx; dwFlags
0x14003dc1d  mov     r8d, 800h; dwBytes
0x14003dc23  mov     rcx, rax; hHeap
0x14003dc26  call    cs:__imp_HeapAlloc
0x14003dc2d  nop     dword ptr [rax+rax+00h]
0x14003dc32  mov     rdi, rax
0x14003dc35  test    rax, rax
0x14003dc38  jnz     short loc_14003DC4C
0x14003dc3a  mov     eax, 8007000Eh
0x14003dc3f  mov     r9d, 448h
0x14003dc45  mov     ebx, eax
0x14003dc47  jmp     loc_14003DBC6
0x14003dc4c  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x14003dc50  mov     edx, 400h; unsigned __int64
0x14003dc55  mov     rcx, rdi; unsigned __int16 *
0x14003dc58  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003dc5d  mov     ebx, eax
0x14003dc5f  test    eax, eax
0x14003dc61  jns     short loc_14003DC6E
0x14003dc63  mov     r9d, 44Bh
0x14003dc69  jmp     loc_14003DD49
0x14003dc6e  mov     rdx, rdi; unsigned __int16 *
0x14003dc71  call    ?SupportName@Configuration@@QEAAXPEAG@Z; Configuration::SupportName(ushort *)
0x14003dc76  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003dc7d  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x14003dc81  lea     rdx, [rbp+57h+var_80]; unsigned __int16 **
0x14003dc85  mov     cs:?g_ErrorContext@@3IC, 19Ah; uint volatile g_ErrorContext
0x14003dc8f  mov     rcx, [rcx+70h]; unsigned __int16 *
0x14003dc93  call    ?GetSupportResponse@@YAJPEAGPEAU_SUPPORT_RESPONSE@@PEAK@Z; GetSupportResponse(ushort *,_SUPPORT_RESPONSE *,ulong *)
0x14003dc98  mov     ebx, eax
0x14003dc9a  test    eax, eax
0x14003dc9c  jns     short loc_14003DCA9
0x14003dc9e  mov     r9d, 455h
0x14003dca4  jmp     loc_14003DBC6
0x14003dca9  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14003dcb0  lea     rcx, [rbp+57h+var_80]
0x14003dcb4  mov     [rax+118h], rcx
0x14003dcbb  mov     ecx, 161h; uID
0x14003dcc0  call    ?UpdateUITextByID@@YAJI@Z; UpdateUITextByID(uint)
0x14003dcc5  mov     ebx, eax
0x14003dcc7  test    eax, eax
0x14003dcc9  jns     short loc_14003DCD6
0x14003dccb  mov     r9d, 45Ah
0x14003dcd1  jmp     loc_14003DBC6
0x14003dcd6  mov     rcx, rsi; unsigned __int16 *
0x14003dcd9  call    ?UploadFile@@YAJPEAG@Z; UploadFile(ushort *)
0x14003dcde  mov     ebx, eax
0x14003dce0  test    eax, eax
0x14003dce2  jns     short loc_14003DCEF
0x14003dce4  mov     r9d, 45Dh
0x14003dcea  jmp     loc_14003DBC6
0x14003dcef  jnz     loc_14003DD8A
0x14003dcf5  call    ?HistoryFileRemoveSupportKey@@YAJXZ; HistoryFileRemoveSupportKey(void)
0x14003dcfa  mov     ebx, eax
0x14003dcfc  test    eax, eax
0x14003dcfe  jns     short loc_14003DD0B
0x14003dd00  mov     r9d, 465h
0x14003dd06  jmp     loc_14003DBC6
0x14003dd0b  mov     rcx, rsi; lpFileName
0x14003dd0e  call    cs:__imp_DeleteFileW
0x14003dd15  nop     dword ptr [rax+rax+00h]
0x14003dd1a  test    eax, eax
0x14003dd1c  jz      short loc_14003DD22
0x14003dd1e  xor     ebx, ebx
0x14003dd20  jmp     short loc_14003DD8A
0x14003dd22  call    cs:__imp_GetLastError
0x14003dd29  nop     dword ptr [rax+rax+00h]
0x14003dd2e  mov     ebx, eax
0x14003dd30  test    eax, eax
0x14003dd32  jle     short loc_14003DD3D
0x14003dd34  movzx   ebx, ax
0x14003dd37  or      ebx, 80070000h
0x14003dd3d  test    ebx, ebx
0x14003dd3f  jns     short loc_14003DD8A
0x14003dd41  xor     edi, edi
0x14003dd43  mov     r9d, 468h
0x14003dd49  lea     r8, aReuploadfiles; "ReuploadFiles"
0x14003dd50  mov     ecx, 1; Level
0x14003dd55  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003dd5c  mov     dword ptr [rsp+0B0h+var_90], ebx
0x14003dd60  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003dd65  test    rdi, rdi
0x14003dd68  jz      short loc_14003DD8A
0x14003dd6a  call    cs:__imp_GetProcessHeap
0x14003dd71  nop     dword ptr [rax+rax+00h]
0x14003dd76  mov     r8, rdi; lpMem
0x14003dd79  xor     edx, edx; dwFlags
0x14003dd7b  mov     rcx, rax; hHeap
0x14003dd7e  call    cs:__imp_HeapFree
0x14003dd85  nop     dword ptr [rax+rax+00h]
0x14003dd8a  call    cs:__imp_GetProcessHeap
0x14003dd91  nop     dword ptr [rax+rax+00h]
0x14003dd96  mov     r8, rsi; lpMem
0x14003dd99  xor     edx, edx; dwFlags
0x14003dd9b  mov     rcx, rax; hHeap
0x14003dd9e  call    cs:__imp_HeapFree
0x14003dda5  nop     dword ptr [rax+rax+00h]
0x14003ddaa  lea     rcx, [rbp+57h+var_80]; struct _SUPPORT_RESPONSE *
0x14003ddae  call    ?CloseSupportResponse@@YAXPEAU_SUPPORT_RESPONSE@@@Z; CloseSupportResponse(_SUPPORT_RESPONSE *)
0x14003ddb3  mov     eax, ebx
0x14003ddb5  add     rsp, 98h
0x14003ddbc  pop     rdi
0x14003ddbd  pop     rsi
0x14003ddbe  pop     rbx
0x14003ddbf  pop     rbp
0x14003ddc0  retn
```
