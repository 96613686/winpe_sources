# APPLICATION::UpdateBindingsForW3SVCApplications(PROTOCOL_BINDING *,int)

- ea: `0x180016308`
- end: `0x180016586`
- name: `?UpdateBindingsForW3SVCApplications@APPLICATION@@QEAAXPEAVPROTOCOL_BINDING@@H@Z`
- size: `638`
- prototype: `void __fastcall(APPLICATION *__hidden this, struct PROTOCOL_BINDING *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015958`

## callees

- `0x180001234`
- `0x180001274`
- `0x180015d38`
- `0x180016308`
- `0x18002113c`
- `0x18002130c`
- `0x18003f2f4`
- `0x18003fd28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001648f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001648f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016499`
- `iisutil!PuDbgPrint` at `0x180016376`
- `iisutil!PuDbgPrint` at `0x180016376`
- `iisutil!PuDbgPrintError` at `0x180016530`
- `iisutil!PuDbgPrintError` at `0x180016530`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001640e`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001640e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001653e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001653e`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x1800163e3`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x1800163e3`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800163af`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18001642e`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180016449`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800163af`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18001642e`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180016449`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180016479`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180016479`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x180016485`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x180016485`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800164c8`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800164c8`

## string_xrefs

- `0x180016350`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\application.cxx`
- `0x18001636b`: `application asked to reset w3svc apps of site: %lu with path: %S\n`
- `0x180016345`: `APPLICATION::UpdateBindingsForW3SVCApplications`
- `0x180016529`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`
- `0x18001650c`: `UpdateBindingsForW3SVCApplications failed.`
- `0x180016518`: `HTTP_PROTOCOL_APPLICATION::UpdateBindingsForW3SVCApplications`

## pseudocode

```c
void __fastcall APPLICATION::UpdateBindingsForW3SVCApplications(APPLICATION *this, struct PROTOCOL_BINDING *a2, int a3)
{
  APPLICATION *i; // rax
  HTTP_PROTOCOL **v6; // rbp
  __int64 v7; // rcx
  HTTP_PROTOCOL *v8; // r12
  MULTISZ *v9; // rax
  struct MULTISZ *v10; // rsi
  const unsigned __int16 *v11; // rbx
  int v12; // r9d
  signed int v13; // edi
  MULTISZ *v14; // rbx
  const unsigned __int16 *v15; // rax
  signed int LastError; // eax
  struct MULTISZ *v17; // r8
  APPLICATION *v18; // [rsp+80h] [rbp+8h]

  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\application.cxx",
      742,
      "APPLICATION::UpdateBindingsForW3SVCApplications",
      "application asked to reset w3svc apps of site: %lu with path: %S\n",
      *((_DWORD *)this + 4),
      *((const wchar_t **)this + 7));
  for ( i = (APPLICATION *)*((_QWORD *)this + 20); i != (APPLICATION *)((char *)this + 160); i = v18 )
  {
    v6 = (HTTP_PROTOCOL **)((char *)i - 88);
    v18 = *(APPLICATION **)i;
    if ( !IsStringEqualOrdinalIgnoreCase(*(const unsigned __int16 **)(*((_QWORD *)i + 6) + 152LL), L"HTTP") )
      continue;
    v7 = *(_QWORD *)(*((_QWORD *)this + 15) + 736LL);
    if ( !v7 || !MULTISZ::FindStringNoCase((MULTISZ *)(v7 + 16), *((const unsigned __int16 **)v6[17] + 19)) )
    {
      PROTOCOL_APPLICATION::Terminate((PROTOCOL_APPLICATION *)v6);
      continue;
    }
    v8 = v6[17];
    v9 = (MULTISZ *)operator new(0x38u);
    if ( v9 )
    {
      v10 = MULTISZ::MULTISZ(v9);
      if ( v10 )
      {
        v11 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
        if ( IsStringEqualOrdinalIgnoreCase(v11, L"HTTP") )
        {
          v12 = 0;
        }
        else
        {
          v13 = 0;
          if ( !IsStringEqualOrdinalIgnoreCase(v11, L"HTTPS") )
            goto LABEL_14;
          v12 = 1;
        }
        v13 = HTTP_PROTOCOL_APPLICATION::AddBindingsToList((HTTP_PROTOCOL_APPLICATION *)v6, v10, a2, v12);
        if ( v13 >= 0 )
        {
LABEL_14:
          v14 = v6[18];
          v15 = MULTISZ::First(v10);
          if ( MULTISZ::FastAppend(v14, v15) )
          {
            if ( a3 )
            {
              MULTISZ::Reset(v6[18]);
              v17 = 0;
            }
            else
            {
              v17 = v10;
            }
            HTTP_PROTOCOL::SendApplicationRemoveUrls(v8, (struct HTTP_PROTOCOL_APPLICATION *)v6, v17);
            HTTP_PROTOCOL::SendApplicationUrls(v8, (struct HTTP_PROTOCOL_APPLICATION *)v6, v10);
          }
          else if ( GetLastError() )
          {
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v13 = -2147467259;
          }
          if ( v13 >= 0 )
          {
LABEL_30:
            MULTISZ::~MULTISZ(v10);
            operator delete(v10);
            continue;
          }
          goto LABEL_27;
        }
      }
    }
    else
    {
      v10 = 0;
    }
    v13 = -2147024882;
LABEL_27:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_protocol_application.cxx",
        1414,
        "HTTP_PROTOCOL_APPLICATION::UpdateBindingsForW3SVCApplications",
        v13,
        "UpdateBindingsForW3SVCApplications failed.");
    if ( v10 )
      goto LABEL_30;
  }
  APPLICATION::CreateActiveProtocolApplications(this);
}

```

## disassembly

```asm
0x180016308  mov     r11, rsp
0x18001630b  mov     [r11+10h], rbx
0x18001630f  mov     [r11+18h], r8d
0x180016313  push    rbp
0x180016314  push    rsi
0x180016315  push    rdi
0x180016316  push    r12
0x180016318  push    r13
0x18001631a  push    r14
0x18001631c  push    r15
0x18001631e  sub     rsp, 40h
0x180016322  mov     eax, cs:g_dwDebugFlags
0x180016328  mov     r13, rdx
0x18001632b  test    eax, 30000h
0x180016330  mov     r14, rcx
0x180016333  setnz   r9b
0x180016337  test    al, 3
0x180016339  setnz   al
0x18001633c  test    al, r9b
0x18001633f  jz      short loc_18001637C
0x180016341  mov     rax, [rcx+38h]
0x180016345  lea     r9, aApplicationUpd; "APPLICATION::UpdateBindingsForW3SVCAppl"...
0x18001634c  mov     [r11-48h], rax
0x180016350  lea     rdx, aServercommonIn_46; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016357  mov     eax, [rcx+10h]
0x18001635a  mov     r8d, 2E6h
0x180016360  mov     rcx, cs:g_pDebug
0x180016367  mov     dword ptr [rsp+78h+var_50], eax
0x18001636b  lea     rax, aApplicationAsk; "application asked to reset w3svc apps o"...
0x180016372  mov     [r11-58h], rax
0x180016376  call    cs:__imp_PuDbgPrint
0x18001637c  lea     r15, [r14+0A0h]
0x180016383  mov     rax, [r15]
0x180016386  jmp     loc_18001655E
0x18001638b  mov     rcx, [rax]
0x18001638e  lea     rbp, [rax-58h]
0x180016392  mov     [rsp+78h+arg_0], rcx
0x18001639a  lea     rdx, aHttp_0; "HTTP"
0x1800163a1  mov     rcx, [rbp+88h]
0x1800163a8  mov     rcx, [rcx+98h]
0x1800163af  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x1800163b5  test    al, al
0x1800163b7  jz      loc_180016556
0x1800163bd  mov     rax, [r14+78h]
0x1800163c1  mov     rcx, [rax+2E0h]
0x1800163c8  test    rcx, rcx
0x1800163cb  jz      loc_18001654E
0x1800163d1  mov     rdx, [rbp+88h]
0x1800163d8  add     rcx, 10h
0x1800163dc  mov     rdx, [rdx+98h]
0x1800163e3  call    cs:__imp_?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindStringNoCase(ushort const *)
0x1800163e9  test    eax, eax
0x1800163eb  jz      loc_18001654E
0x1800163f1  mov     r12, [rbp+88h]
0x1800163f8  mov     ecx, 38h ; '8'; Size
0x1800163fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016402  test    rax, rax
0x180016405  jz      loc_1800164F5
0x18001640b  mov     rcx, rax
0x18001640e  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180016414  mov     rsi, rax
0x180016417  test    rax, rax
0x18001641a  jz      loc_1800164F7
0x180016420  mov     rbx, [r13+28h]
0x180016424  lea     rdx, aHttp_0; "HTTP"
0x18001642b  mov     rcx, rbx
0x18001642e  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180016434  test    al, al
0x180016436  jz      short loc_18001643D
0x180016438  xor     r9d, r9d
0x18001643b  jmp     short loc_180016457
0x18001643d  lea     rdx, aHttps_0; "HTTPS"
0x180016444  mov     rcx, rbx
0x180016447  xor     edi, edi
0x180016449  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x18001644f  test    al, al
0x180016451  jz      short loc_18001646F
0x180016453  lea     r9d, [rdi+1]; int
0x180016457  mov     r8, r13; struct PROTOCOL_BINDING *
0x18001645a  mov     rdx, rsi; struct MULTISZ *
0x18001645d  mov     rcx, rbp; this
0x180016460  call    ?AddBindingsToList@HTTP_PROTOCOL_APPLICATION@@AEAAJPEAVMULTISZ@@PEAVPROTOCOL_BINDING@@H@Z; HTTP_PROTOCOL_APPLICATION::AddBindingsToList(MULTISZ *,PROTOCOL_BINDING *,int)
0x180016465  mov     edi, eax
0x180016467  test    eax, eax
0x180016469  js      loc_1800164F7
0x18001646f  mov     rbx, [rbp+90h]
0x180016476  mov     rcx, rsi
0x180016479  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x18001647f  mov     rdx, rax
0x180016482  mov     rcx, rbx
0x180016485  call    cs:__imp_?FastAppend@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FastAppend(ushort const *)
0x18001648b  test    eax, eax
0x18001648d  jnz     short loc_1800164B7
0x18001648f  call    cs:__imp_GetLastError
0x180016495  test    eax, eax
0x180016497  jz      short loc_1800164B0
0x180016499  call    cs:__imp_GetLastError
0x18001649f  mov     edi, eax
0x1800164a1  test    eax, eax
0x1800164a3  jle     short loc_1800164EF
0x1800164a5  movzx   edi, ax
0x1800164a8  or      edi, 80070000h
0x1800164ae  jmp     short loc_1800164EF
0x1800164b0  mov     edi, 80004005h
0x1800164b5  jmp     short loc_1800164EF
0x1800164b7  cmp     [rsp+78h+arg_10], 0
0x1800164bf  jz      short loc_1800164D3
0x1800164c1  mov     rcx, [rbp+90h]
0x1800164c8  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x1800164ce  xor     r8d, r8d
0x1800164d1  jmp     short loc_1800164D6
0x1800164d3  mov     r8, rsi; struct MULTISZ *
0x1800164d6  mov     rdx, rbp; struct HTTP_PROTOCOL_APPLICATION *
0x1800164d9  mov     rcx, r12; this
0x1800164dc  call    ?SendApplicationRemoveUrls@HTTP_PROTOCOL@@QEAAXPEAVHTTP_PROTOCOL_APPLICATION@@PEAVMULTISZ@@@Z; HTTP_PROTOCOL::SendApplicationRemoveUrls(HTTP_PROTOCOL_APPLICATION *,MULTISZ *)
0x1800164e1  mov     r8, rsi; struct MULTISZ *
0x1800164e4  mov     rdx, rbp; struct HTTP_PROTOCOL_APPLICATION *
0x1800164e7  mov     rcx, r12; this
0x1800164ea  call    ?SendApplicationUrls@HTTP_PROTOCOL@@QEAAXPEAVHTTP_PROTOCOL_APPLICATION@@PEAVMULTISZ@@@Z; HTTP_PROTOCOL::SendApplicationUrls(HTTP_PROTOCOL_APPLICATION *,MULTISZ *)
0x1800164ef  test    edi, edi
0x1800164f1  jns     short loc_18001653B
0x1800164f3  jmp     short loc_1800164FC
0x1800164f5  xor     esi, esi
0x1800164f7  mov     edi, 8007000Eh
0x1800164fc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180016503  jz      short loc_180016536
0x180016505  mov     rcx, cs:g_pDebug
0x18001650c  lea     rax, aUpdatebindings; "UpdateBindingsForW3SVCApplications fail"...
0x180016513  mov     [rsp+78h+var_50], rax
0x180016518  lea     r9, aHttpProtocolAp_1; "HTTP_PROTOCOL_APPLICATION::UpdateBindin"...
0x18001651f  mov     r8d, 586h
0x180016525  mov     [rsp+78h+var_58], edi
0x180016529  lea     rdx, aServercommonIn_34; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016530  call    cs:__imp_PuDbgPrintError
0x180016536  test    rsi, rsi
0x180016539  jz      short loc_180016556
0x18001653b  mov     rcx, rsi
0x18001653e  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180016544  mov     rcx, rsi; Block
0x180016547  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001654c  jmp     short loc_180016556
0x18001654e  mov     rcx, rbp; this
0x180016551  call    ?Terminate@PROTOCOL_APPLICATION@@QEAAXXZ; PROTOCOL_APPLICATION::Terminate(void)
0x180016556  mov     rax, [rsp+78h+arg_0]
0x18001655e  cmp     rax, r15
0x180016561  jnz     loc_18001638B
0x180016567  mov     rcx, r14; this
0x18001656a  mov     rbx, [rsp+78h+arg_8]
0x180016572  add     rsp, 40h
0x180016576  pop     r15
0x180016578  pop     r14
0x18001657a  pop     r13
0x18001657c  pop     r12
0x18001657e  pop     rdi
0x18001657f  pop     rsi
0x180016580  pop     rbp
0x180016581  jmp     ?CreateActiveProtocolApplications@APPLICATION@@QEAAXXZ; APPLICATION::CreateActiveProtocolApplications(void)
```
