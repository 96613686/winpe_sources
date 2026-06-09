# DotTxtSym(_DOT_COMMAND *,DebugClient *)

- ea: `0x1801fa5d0`
- end: `0x1801fa769`
- name: `?DotTxtSym@@YAXPEAU_DOT_COMMAND@@PEAVDebugClient@@@Z`
- size: `409`
- prototype: `void __fastcall(struct _DOT_COMMAND *, struct DebugClient *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800793cc`
- `0x18009fb80`
- `0x1801fa5d0`
- `0x1801fc0f0`
- `0x180240f9c`
- `0x180280968`
- `0x1802e7c48`
- `0x18038605c`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!_wfopen` at `0x1801fa642`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen` at `0x1801fa642`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1801fa758`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1801fa758`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1804e1306`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1801fa6cb`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1801fa6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fa65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801fa65b`

## string_xrefs

- `0x1801fa66d`: `Unable to open '%s', Win32 error %d\n`

## pseudocode

```c
void __fastcall DotTxtSym(struct _DOT_COMMAND *a1, struct DebugClient *a2)
{
  wchar_t *v2; // rsi
  FILE *v3; // rdi
  DWORD LastError; // eax
  __int64 v5; // rax
  wint_t NextChar; // bx
  unsigned __int64 Expression; // rbx
  unsigned int v8; // eax
  unsigned __int16 v9; // [rsp+60h] [rbp+18h] BYREF
  FILE *v10; // [rsp+68h] [rbp+20h] BYREF

  FeatureUsageTracker::FeatureUsed(L"DeprecatedFeatures1812", L"DotTxtSym", 1u);
  v9 = 0;
  if ( !g_Process )
    ReportError(0x1018u, 0);
  v2 = BufferStringValue(&g_CurCmd, 0x8Du, (unsigned int *)&v10, &v9, 0);
  v3 = _wfopen(v2, L"r");
  v10 = v3;
  if ( v3 )
  {
    NextChar = v9;
    if ( v9 == 34 )
      NextChar = *++g_CurCmd;
    if ( iswspace(NextChar) )
    {
      ++g_CurCmd;
      NextChar = GetNextChar((const unsigned __int16 **)&g_CurCmd);
    }
    if ( NextChar != 61 )
      ReportError(0x1001u, 0);
    ++g_CurCmd;
    Expression = GetExpression(0);
    if ( GetNextChar((const unsigned __int16 **)&g_CurCmd) != 44 )
      ReportError(0x1001u, 0);
    ++g_CurCmd;
    v8 = GetExpression(0);
    LoadTxtSym(v3, v2, Expression, v8);
    fclose(v3);
  }
  else
  {
    LastError = GetLastError();
    ErrOut(L"Unable to open '%s', Win32 error %d\n", v2, LastError);
    v5 = -1;
    do
      ++v5;
    while ( g_CurCmd[v5] );
    g_CurCmd += v5;
  }
}

```

## disassembly

```asm
0x1801fa5d0  mov     [rsp+arg_0], rbx
0x1801fa5d5  push    rsi
0x1801fa5d6  push    rdi
0x1801fa5d7  push    r14
0x1801fa5d9  sub     rsp, 30h
0x1801fa5dd  mov     r8d, 1; unsigned int
0x1801fa5e3  lea     rdx, aDottxtsym; "DotTxtSym"
0x1801fa5ea  lea     rcx, aDeprecatedfeat; "DeprecatedFeatures1812"
0x1801fa5f1  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1801fa5f6  xor     r14d, r14d
0x1801fa5f9  mov     [rsp+48h+arg_10], r14w
0x1801fa5ff  cmp     cs:?g_Process@@3PEAVProcessInfo@@EA, r14; ProcessInfo * g_Process
0x1801fa606  jnz     short loc_1801FA615
0x1801fa608  xor     edx, edx; unsigned __int16 **
0x1801fa60a  mov     ecx, 1018h; unsigned int
0x1801fa60f  call    ?ReportError@@YAXKPEAPEBG@Z; ReportError(ulong,ushort const * *)
0x1801fa615  mov     [rsp+48h+var_28], r14; int *
0x1801fa61a  lea     r9, [rsp+48h+arg_10]; unsigned __int16 *
0x1801fa61f  lea     r8, [rsp+48h+arg_18]; unsigned int *
0x1801fa624  mov     edx, 8Dh; unsigned int
0x1801fa629  lea     rcx, ?g_CurCmd@@3PEAGEA; unsigned __int16 **
0x1801fa630  call    ?BufferStringValue@@YAPEAGPEAPEAGKPEAKPEAGPEAH@Z; BufferStringValue(ushort * *,ulong,ulong *,ushort *,int *)
0x1801fa635  mov     rsi, rax
0x1801fa638  lea     rdx, aR_4; "r"
0x1801fa63f  mov     rcx, rax; FileName
0x1801fa642  call    cs:__imp__wfopen
0x1801fa649  nop     dword ptr [rax+rax+00h]
0x1801fa64e  mov     rdi, rax
0x1801fa651  mov     [rsp+48h+arg_18], rax
0x1801fa656  test    rax, rax
0x1801fa659  jnz     short loc_1801FA6A8
0x1801fa65b  call    cs:__imp_GetLastError
0x1801fa662  nop     dword ptr [rax+rax+00h]
0x1801fa667  mov     r8d, eax
0x1801fa66a  mov     rdx, rsi
0x1801fa66d  lea     rcx, aUnableToOpenSW; "Unable to open '%s', Win32 error %d\n"
0x1801fa674  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801fa679  mov     rcx, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1801fa680  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801fa684  inc     rax
0x1801fa687  cmp     [rcx+rax*2], r14w
0x1801fa68c  jnz     short loc_1801FA684
0x1801fa68e  lea     rax, [rcx+rax*2]
0x1801fa692  mov     cs:?g_CurCmd@@3PEAGEA, rax; ushort * g_CurCmd
0x1801fa699  mov     rbx, [rsp+48h+arg_0]
0x1801fa69e  add     rsp, 30h
0x1801fa6a2  pop     r14
0x1801fa6a4  pop     rdi
0x1801fa6a5  pop     rsi
0x1801fa6a6  retn
0x1801fa6a8  movzx   ebx, [rsp+48h+arg_10]
0x1801fa6ad  cmp     bx, 22h ; '"'
0x1801fa6b1  jnz     short loc_1801FA6C8
0x1801fa6b3  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1801fa6ba  add     rax, 2
0x1801fa6be  mov     cs:?g_CurCmd@@3PEAGEA, rax; ushort * g_CurCmd
0x1801fa6c5  movzx   ebx, word ptr [rax]
0x1801fa6c8  movzx   ecx, bx; C
0x1801fa6cb  call    cs:__imp_iswspace
0x1801fa6d2  nop     dword ptr [rax+rax+00h]
0x1801fa6d7  test    eax, eax
0x1801fa6d9  jz      short loc_1801FA6F2
0x1801fa6db  add     cs:?g_CurCmd@@3PEAGEA, 2; ushort * g_CurCmd
0x1801fa6e3  lea     rcx, ?g_CurCmd@@3PEAGEA; unsigned __int16 **
0x1801fa6ea  call    ?GetNextChar@@YAGPEAPEBG@Z; GetNextChar(ushort const * *)
0x1801fa6ef  movzx   ebx, ax
0x1801fa6f2  cmp     bx, 3Dh ; '='
0x1801fa6f6  jz      short loc_1801FA704
0x1801fa6f8  xor     edx, edx; unsigned __int16 **
0x1801fa6fa  mov     ecx, 1001h; unsigned int
0x1801fa6ff  call    ?ReportError@@YAXKPEAPEBG@Z; ReportError(ulong,ushort const * *)
0x1801fa704  add     cs:?g_CurCmd@@3PEAGEA, 2; ushort * g_CurCmd
0x1801fa70c  xor     ecx, ecx; unsigned __int16 *
0x1801fa70e  call    ?GetExpression@@YA_KPEBG@Z; GetExpression(ushort const *)
0x1801fa713  mov     rbx, rax
0x1801fa716  lea     rcx, ?g_CurCmd@@3PEAGEA; unsigned __int16 **
0x1801fa71d  call    ?GetNextChar@@YAGPEAPEBG@Z; GetNextChar(ushort const * *)
0x1801fa722  cmp     ax, 2Ch ; ','
0x1801fa726  jz      short loc_1801FA734
0x1801fa728  xor     edx, edx; unsigned __int16 **
0x1801fa72a  mov     ecx, 1001h; unsigned int
0x1801fa72f  call    ?ReportError@@YAXKPEAPEBG@Z; ReportError(ulong,ushort const * *)
0x1801fa734  add     cs:?g_CurCmd@@3PEAGEA, 2; ushort * g_CurCmd
0x1801fa73c  xor     ecx, ecx; unsigned __int16 *
0x1801fa73e  call    ?GetExpression@@YA_KPEBG@Z; GetExpression(ushort const *)
0x1801fa743  mov     r9, rax; unsigned int
0x1801fa746  mov     r8, rbx; unsigned __int64
0x1801fa749  mov     rdx, rsi; unsigned __int16 *
0x1801fa74c  mov     rcx, rdi; Stream
0x1801fa74f  call    ?LoadTxtSym@@YAXPEAU_iobuf@@PEAG_KK@Z; LoadTxtSym(_iobuf *,ushort *,unsigned __int64,ulong)
0x1801fa754  nop
0x1801fa755  mov     rcx, rdi; Stream
0x1801fa758  call    cs:__imp_fclose
0x1801fa75f  nop     dword ptr [rax+rax+00h]
0x1801fa764  jmp     loc_1801FA699
0x1804e12f4  push    rbp
0x1804e12f6  sub     rsp, 30h
0x1804e12fa  mov     rbp, rdx
0x1804e12fd  mov     rcx, [rbp+68h]
0x1804e1301  add     rsp, 30h
0x1804e1305  pop     rbp
0x1804e1306  jmp     cs:__imp_fclose
```
