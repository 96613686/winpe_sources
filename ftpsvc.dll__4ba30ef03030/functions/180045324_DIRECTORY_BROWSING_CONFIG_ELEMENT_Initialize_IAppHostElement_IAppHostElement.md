# DIRECTORY_BROWSING_CONFIG_ELEMENT::Initialize(IAppHostElement *,IAppHostElement *)

- ea: `0x180045324`
- end: `0x18004549e`
- name: `?Initialize@DIRECTORY_BROWSING_CONFIG_ELEMENT@@QEAAJPEAUIAppHostElement@@0@Z`
- size: `378`
- prototype: `__int64 __fastcall(DIRECTORY_BROWSING_CONFIG_ELEMENT *__hidden this, struct IAppHostElement *, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180045dac`

## callees

- `0x180001210`
- `0x180018150`
- `0x18002b0c4`
- `0x18002b65c`
- `0x180045324`
- `0x180049010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800453c8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800453c8`
- `iisutil!PuDbgPrintError` at `0x180045420`
- `iisutil!PuDbgPrintError` at `0x18004548f`
- `iisutil!PuDbgPrintError` at `0x180045420`
- `iisutil!PuDbgPrintError` at `0x18004548f`

## string_xrefs

- `0x1800453f5`: `Failed to read element %S\n`
- `0x180045412`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x180045481`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x180045344`: `directoryBrowse`
- `0x180045381`: `virtualDirectoryTimeout`
- `0x180045405`: `DIRECTORY_BROWSING_CONFIG_ELEMENT::Initialize`
- `0x180045474`: `DIRECTORY_BROWSING_CONFIG_ELEMENT::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DIRECTORY_BROWSING_CONFIG_ELEMENT::Initialize(
        DIRECTORY_BROWSING_CONFIG_ELEMENT *this,
        struct IAppHostElement *a2,
        struct IAppHostElement *a3)
{
  int SubElement; // ebx
  char *v6; // rax
  char *v7; // rbx
  struct IAppHostElement *v9; // [rsp+98h] [rbp+20h] BYREF

  v9 = 0;
  SubElement = Config_GetSubElement(a3, L"directoryBrowse", &v9);
  if ( SubElement >= 0 )
  {
    SubElement = Config_GetDWORDProperty(v9, L"showFlags", (unsigned int *)this);
    if ( SubElement >= 0 )
    {
      SubElement = Config_GetDWORDProperty(v9, L"virtualDirectoryTimeout", (unsigned int *)this + 1);
      if ( SubElement >= 0 )
      {
        if ( (*(_BYTE *)this & 0x20) != 0 && a2 )
        {
          v6 = (char *)operator new(0x48u);
          v7 = v6;
          if ( v6 )
          {
            STRU::STRU(v6 + 16);
            *((_QWORD *)v7 + 1) = v7;
            *(_QWORD *)v7 = v7;
          }
          else
          {
            v7 = 0;
          }
          *((_QWORD *)this + 1) = v7;
          if ( !v7 )
          {
            SubElement = -2147024888;
            goto LABEL_11;
          }
          SubElement = FTP_VDIR_PARENT_TABLE::Initialize((FTP_VDIR_PARENT_TABLE **)v7, a2);
          if ( SubElement < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_13;
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
              1794,
              "DIRECTORY_BROWSING_CONFIG_ELEMENT::Initialize",
              SubElement,
              "Failed to build VDir Parent table for site\n");
            goto LABEL_11;
          }
        }
        SubElement = 0;
        goto LABEL_13;
      }
    }
  }
LABEL_11:
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
      1810,
      "DIRECTORY_BROWSING_CONFIG_ELEMENT::Initialize",
      SubElement,
      "Failed to read element %S\n",
      L"directoryBrowse");
LABEL_13:
  if ( v9 )
    ((void (__fastcall *)(struct IAppHostElement *))v9->lpVtbl->Release)(v9);
  return (unsigned int)SubElement;
}

```

## disassembly

```asm
0x180045324  mov     r11, rsp
0x180045327  push    rbx
0x180045328  push    rbp
0x180045329  push    rsi
0x18004532a  push    rdi
0x18004532b  sub     rsp, 58h
0x18004532f  mov     rax, r8
0x180045332  mov     rsi, rdx
0x180045335  mov     rdi, rcx
0x180045338  mov     qword ptr [r11+20h], 0
0x180045340  lea     r8, [r11+20h]; struct IAppHostElement **
0x180045344  lea     rbp, aDirectorybrows; "directoryBrowse"
0x18004534b  mov     rdx, rbp; unsigned __int16 *
0x18004534e  mov     rcx, rax; struct IAppHostElement *
0x180045351  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x180045356  mov     ebx, eax
0x180045358  test    eax, eax
0x18004535a  js      loc_1800453E7
0x180045360  mov     r8, rdi; unsigned int *
0x180045363  lea     rdx, aShowflags; "showFlags"
0x18004536a  mov     rcx, [rsp+78h+arg_18]; struct IAppHostElement *
0x180045372  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180045377  mov     ebx, eax
0x180045379  test    eax, eax
0x18004537b  js      short loc_1800453E7
0x18004537d  lea     r8, [rdi+4]; unsigned int *
0x180045381  lea     rdx, aVirtualdirecto; "virtualDirectoryTimeout"
0x180045388  mov     rcx, [rsp+78h+arg_18]; struct IAppHostElement *
0x180045390  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180045395  mov     ebx, eax
0x180045397  test    eax, eax
0x180045399  js      short loc_1800453E7
0x18004539b  test    byte ptr [rdi], 20h
0x18004539e  jz      loc_18004549A
0x1800453a4  test    rsi, rsi
0x1800453a7  jz      loc_18004549A
0x1800453ad  mov     ecx, 48h ; 'H'; Size
0x1800453b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800453b7  mov     rbx, rax
0x1800453ba  mov     [rsp+78h+var_38], rax
0x1800453bf  test    rax, rax
0x1800453c2  jz      short loc_1800453D7
0x1800453c4  lea     rcx, [rax+10h]
0x1800453c8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800453ce  mov     [rbx+8], rbx
0x1800453d2  mov     [rbx], rbx
0x1800453d5  jmp     short loc_1800453D9
0x1800453d7  xor     ebx, ebx
0x1800453d9  mov     [rdi+8], rbx
0x1800453dd  test    rbx, rbx
0x1800453e0  jnz     short loc_18004544A
0x1800453e2  mov     ebx, 80070008h
0x1800453e7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800453ee  jz      short loc_180045426
0x1800453f0  mov     [rsp+78h+var_48], rbp
0x1800453f5  lea     rax, aFailedToReadEl; "Failed to read element %S\n"
0x1800453fc  mov     [rsp+78h+var_50], rax
0x180045401  mov     [rsp+78h+var_58], ebx
0x180045405  lea     r9, aDirectoryBrows; "DIRECTORY_BROWSING_CONFIG_ELEMENT::Init"...
0x18004540c  mov     r8d, 712h
0x180045412  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180045419  mov     rcx, cs:g_pDebug
0x180045420  call    cs:__imp_PuDbgPrintError
0x180045426  mov     rcx, [rsp+78h+arg_18]
0x18004542e  test    rcx, rcx
0x180045431  jz      short loc_18004543F
0x180045433  mov     rax, [rcx]
0x180045436  mov     rax, [rax+10h]
0x18004543a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004543f  mov     eax, ebx
0x180045441  add     rsp, 58h
0x180045445  pop     rdi
0x180045446  pop     rsi
0x180045447  pop     rbp
0x180045448  pop     rbx
0x180045449  retn
0x18004544a  mov     rdx, rsi; struct IAppHostElement *
0x18004544d  mov     rcx, rbx; this
0x180045450  call    ?Initialize@FTP_VDIR_PARENT_TABLE@@QEAAJPEAUIAppHostElement@@@Z; FTP_VDIR_PARENT_TABLE::Initialize(IAppHostElement *)
0x180045455  mov     ebx, eax
0x180045457  test    eax, eax
0x180045459  jns     short loc_18004549A
0x18004545b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180045462  jz      short loc_180045426
0x180045464  lea     rax, aFailedToBuildV_1; "Failed to build VDir Parent table for s"...
0x18004546b  mov     [rsp+78h+var_50], rax
0x180045470  mov     [rsp+78h+var_58], ebx
0x180045474  lea     r9, aDirectoryBrows; "DIRECTORY_BROWSING_CONFIG_ELEMENT::Init"...
0x18004547b  mov     r8d, 702h
0x180045481  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180045488  mov     rcx, cs:g_pDebug
0x18004548f  call    cs:__imp_PuDbgPrintError
0x180045495  jmp     loc_1800453E7
0x18004549a  xor     ebx, ebx
0x18004549c  jmp     short loc_180045426
```
