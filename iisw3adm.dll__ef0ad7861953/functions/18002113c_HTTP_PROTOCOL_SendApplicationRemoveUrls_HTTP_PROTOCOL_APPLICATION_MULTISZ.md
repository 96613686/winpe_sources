# HTTP_PROTOCOL::SendApplicationRemoveUrls(HTTP_PROTOCOL_APPLICATION *,MULTISZ *)

- ea: `0x18002113c`
- end: `0x180021303`
- name: `?SendApplicationRemoveUrls@HTTP_PROTOCOL@@QEAAXPEAVHTTP_PROTOCOL_APPLICATION@@PEAVMULTISZ@@@Z`
- size: `455`
- prototype: `void __fastcall(HTTP_PROTOCOL *__hidden this, struct HTTP_PROTOCOL_APPLICATION *, struct MULTISZ *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800144e0`
- `0x180016308`
- `0x1800217e0`

## callees

- `0x1800058e4`
- `0x18002113c`
- `0x180061060`

## import_xrefs

- `msvcrt!_ultow` at `0x18002126c`
- `msvcrt!_ultow` at `0x18002126c`
- `iisutil!PuDbgPrint` at `0x1800211c1`
- `iisutil!PuDbgPrint` at `0x1800211c1`
- `iisutil!PuDbgPrintError` at `0x1800212e0`
- `iisutil!PuDbgPrintError` at `0x1800212e0`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800211ef`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800211ef`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x1800211e2`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x18002120e`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x1800211e2`
- `HTTPAPI!HttpRemoveUrlFromUrlGroup` at `0x18002120e`

## string_xrefs

- `0x180021197`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x1800212d9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x1800211b5`: `Bindings change: removing all URLs registered for config group of application of site: %lu with path: %S\n`
- `0x18002118a`: `HTTP_PROTOCOL::SendApplicationRemoveUrls`
- `0x1800212c8`: `HTTP_PROTOCOL::SendApplicationRemoveUrls`
- `0x1800212bc`: `Removing all URLs from config group failed\n`

## pseudocode

```c
void __fastcall HTTP_PROTOCOL::SendApplicationRemoveUrls(
        HTTP_PROTOCOL *this,
        struct HTTP_PROTOCOL_APPLICATION *a2,
        struct MULTISZ *a3)
{
  HTTP_URL_GROUP_ID v5; // rcx
  signed int v6; // ebx
  const WCHAR *v7; // rdi
  ULONG v8; // eax
  bool v9; // cc
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12[2]; // [rsp+40h] [rbp-48h] BYREF
  wchar_t Buffer[12]; // [rsp+50h] [rbp-38h] BYREF

  if ( *((_QWORD *)this + 44) )
  {
    if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
        2910,
        "HTTP_PROTOCOL::SendApplicationRemoveUrls",
        "Bindings change: removing all URLs registered for config group of application of site: %lu with path: %S\n",
        *(_DWORD *)(*((_QWORD *)a2 + 20) + 16LL),
        *(const wchar_t **)(*((_QWORD *)a2 + 20) + 56LL));
    v5 = *((_QWORD *)a2 + 21);
    if ( v5 )
    {
      if ( a3 )
      {
        v7 = MULTISZ::First(a3);
        if ( !v7 )
          return;
        while ( 1 )
        {
          v8 = HttpRemoveUrlFromUrlGroup(*((_QWORD *)a2 + 21), v7, 0);
          v6 = 0;
          if ( v8 != 2 )
            v6 = v8;
          v9 = v6 <= 0;
          if ( v6 )
            goto LABEL_16;
          v10 = -1;
          do
            ++v10;
          while ( v7[v10] );
          v7 += v10 + 1;
          if ( !*v7 )
          {
            v6 = 0;
            goto LABEL_15;
          }
        }
      }
      v6 = HttpRemoveUrlFromUrlGroup(v5, 0, 1u);
LABEL_15:
      v9 = v6 <= 0;
      if ( v6 )
      {
LABEL_16:
        if ( !v9 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        v11 = *((_QWORD *)a2 + 20);
        *(_OWORD *)v12 = 0;
        _ultow(*(_DWORD *)(v11 + 16), Buffer, 10);
        v12[0] = *(unsigned __int16 **)(*((_QWORD *)a2 + 20) + 56LL);
        v12[1] = Buffer;
        WEB_ADMIN_SERVICE::LogW3svcEvent(g_pWebAdminService, 0xC0000448, 2u, (const unsigned __int16 **const)v12, v6);
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol.cxx",
            2970,
            "HTTP_PROTOCOL::SendApplicationRemoveUrls",
            v6,
            "Removing all URLs from config group failed\n");
      }
    }
  }
}

```

## disassembly

```asm
0x18002113c  mov     [rsp+arg_0], rbx
0x180021141  push    rbp
0x180021142  push    rsi
0x180021143  push    rdi
0x180021144  sub     rsp, 70h
0x180021148  mov     rax, cs:__security_cookie
0x18002114f  xor     rax, rsp
0x180021152  mov     [rsp+88h+var_20], rax
0x180021157  xor     ebp, ebp
0x180021159  mov     rbx, r8
0x18002115c  mov     rsi, rdx
0x18002115f  cmp     [rcx+160h], rbp
0x180021166  jz      loc_1800212E6
0x18002116c  mov     eax, cs:g_dwDebugFlags
0x180021172  test    eax, 30000h
0x180021177  setnz   cl
0x18002117a  test    al, 3
0x18002117c  setnz   al
0x18002117f  test    al, cl
0x180021181  jz      short loc_1800211C7
0x180021183  mov     rcx, [rdx+0A0h]
0x18002118a  lea     r9, aHttpProtocolSe_6; "HTTP_PROTOCOL::SendApplicationRemoveUrl"...
0x180021191  mov     r8d, 0B5Eh
0x180021197  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002119e  mov     rax, [rcx+38h]
0x1800211a2  mov     [rsp+88h+var_58], rax
0x1800211a7  mov     eax, [rcx+10h]
0x1800211aa  mov     rcx, cs:g_pDebug
0x1800211b1  mov     dword ptr [rsp+88h+var_60], eax
0x1800211b5  lea     rax, aBindingsChange; "Bindings change: removing all URLs regi"...
0x1800211bc  mov     qword ptr [rsp+88h+var_68], rax
0x1800211c1  call    cs:__imp_PuDbgPrint
0x1800211c7  mov     rcx, [rsi+0A8h]; UrlGroupId
0x1800211ce  test    rcx, rcx
0x1800211d1  jz      loc_1800212E6
0x1800211d7  test    rbx, rbx
0x1800211da  jnz     short loc_1800211EC
0x1800211dc  xor     edx, edx; pFullyQualifiedUrl
0x1800211de  lea     r8d, [rbx+1]; Flags
0x1800211e2  call    cs:__imp_HttpRemoveUrlFromUrlGroup
0x1800211e8  mov     ebx, eax
0x1800211ea  jmp     short loc_18002123C
0x1800211ec  mov     rcx, rbx
0x1800211ef  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x1800211f5  mov     rdi, rax
0x1800211f8  test    rax, rax
0x1800211fb  jz      loc_1800212E6
0x180021201  mov     rcx, [rsi+0A8h]; UrlGroupId
0x180021208  xor     r8d, r8d; Flags
0x18002120b  mov     rdx, rdi; pFullyQualifiedUrl
0x18002120e  call    cs:__imp_HttpRemoveUrlFromUrlGroup
0x180021214  cmp     eax, 2
0x180021217  mov     ebx, ebp
0x180021219  cmovnz  ebx, eax
0x18002121c  test    ebx, ebx
0x18002121e  jnz     short loc_180021244
0x180021220  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021224  inc     rax
0x180021227  cmp     [rdi+rax*2], bp
0x18002122b  jnz     short loc_180021224
0x18002122d  lea     rdi, [rdi+rax*2]
0x180021231  add     rdi, 2
0x180021235  cmp     [rdi], bp
0x180021238  jnz     short loc_180021201
0x18002123a  mov     ebx, ebp
0x18002123c  test    ebx, ebx
0x18002123e  jz      loc_1800212E6
0x180021244  jle     short loc_18002124F
0x180021246  movzx   ebx, bx
0x180021249  or      ebx, 80070000h
0x18002124f  mov     rcx, [rsi+0A0h]
0x180021256  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18002125b  xorps   xmm0, xmm0
0x18002125e  mov     r8d, 0Ah; Radix
0x180021264  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x180021269  mov     ecx, [rcx+10h]; Value
0x18002126c  call    cs:__imp__ultow
0x180021272  mov     rax, [rsi+0A0h]
0x180021279  lea     r9, [rsp+88h+var_48]; unsigned __int16 **
0x18002127e  mov     r8d, 2; unsigned __int16
0x180021284  mov     [rsp+88h+var_68], ebx; unsigned int
0x180021288  mov     edx, 0C0000448h; unsigned int
0x18002128d  mov     rcx, [rax+38h]
0x180021291  lea     rax, [rsp+88h+Buffer]
0x180021296  mov     [rsp+88h+var_48], rcx
0x18002129b  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800212a2  mov     [rsp+88h+var_48+8], rax
0x1800212a7  call    ?LogW3svcEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogW3svcEvent(ulong,ushort,ushort const * * const,ulong)
0x1800212ac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800212b3  jz      short loc_1800212E6
0x1800212b5  mov     rcx, cs:g_pDebug
0x1800212bc  lea     rax, aRemovingAllUrl; "Removing all URLs from config group fai"...
0x1800212c3  mov     [rsp+88h+var_60], rax
0x1800212c8  lea     r9, aHttpProtocolSe_6; "HTTP_PROTOCOL::SendApplicationRemoveUrl"...
0x1800212cf  mov     r8d, 0B9Ah
0x1800212d5  mov     [rsp+88h+var_68], ebx
0x1800212d9  lea     rdx, aServercommonIn_29; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800212e0  call    cs:__imp_PuDbgPrintError
0x1800212e6  mov     rcx, [rsp+88h+var_20]
0x1800212eb  xor     rcx, rsp; StackCookie
0x1800212ee  call    __security_check_cookie
0x1800212f3  mov     rbx, [rsp+88h+arg_0]
0x1800212fb  add     rsp, 70h
0x1800212ff  pop     rdi
0x180021300  pop     rsi
0x180021301  pop     rbp
0x180021302  retn
```
