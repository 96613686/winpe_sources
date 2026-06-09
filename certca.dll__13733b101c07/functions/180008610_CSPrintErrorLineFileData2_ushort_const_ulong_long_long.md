# CSPrintErrorLineFileData2(ushort const *,ulong,long,long)

- ea: `0x180008610`
- end: `0x1800088f2`
- name: `?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z`
- size: `738`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int, int, int)`
- caller_count: `133`
- callee_count: `9`
- tags: ``

## callers

- `0x180001bf0`
- `0x180002280`
- `0x1800025a0`
- `0x180002ef0`
- `0x180003be0`
- `0x180005010`
- `0x1800051f0`
- `0x1800055b8`
- `0x1800056f0`
- `0x18000596c`
- `0x1800062d0`
- `0x180006990`
- `0x180006e60`
- `0x1800075c0`
- `0x180007a00`
- `0x180007d90`
- `0x180007f60`
- `0x180008400`
- `0x180008570`
- `0x180008960`
- `0x180009230`
- `0x18000a3b0`
- `0x18000a414`
- `0x18000a630`
- `0x18000a920`
- `0x18000ac20`
- `0x18000adf0`
- `0x18000c160`
- `0x18000ce90`
- `0x18000d110`
- `0x18000d5d0`
- `0x18000d9f0`
- `0x18000dce0`
- `0x18000de10`
- `0x18000dfb0`
- `0x18000e130`
- `0x18000e610`
- `0x18000eac0`
- `0x18000ef48`
- `0x18000f440`
- `0x18000f8a0`
- `0x180010070`
- `0x180010168`
- `0x1800103fc`
- `0x180010978`
- `0x180010db0`
- `0x1800113e0`
- `0x180011600`
- `0x180012114`
- `0x180012680`

## callees

- `0x180007da0`
- `0x180008610`
- `0x180008900`
- `0x180008960`
- `0x180009190`
- `0x180009b20`
- `0x18000e220`
- `0x1800382c0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800086c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800086c1`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000885a`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000888c`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000885a`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000888c`

## pseudocode

```c
void __fastcall CSPrintErrorLineFileData2(const unsigned __int16 *a1, unsigned int a2, int a3, int a4)
{
  int v4; // ebx
  unsigned int v9; // r12d
  void (*v10)(const struct _SYSTEMTIME *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int); // rbx
  unsigned __int64 v11; // rax
  const wchar_t *v12; // r13
  const unsigned __int16 *v13; // rax
  const WCHAR *v14; // rdi
  const wchar_t *v15; // rbx
  UINT ACP; // eax
  unsigned __int16 *v17; // rdi
  UINT v18; // eax
  unsigned int v19; // eax
  unsigned __int16 *v20; // r9
  const wchar_t *v21; // rdx
  _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-C78h] BYREF
  char v23[16]; // [rsp+90h] [rbp-C68h] BYREF
  unsigned __int16 v24[520]; // [rsp+A0h] [rbp-C58h] BYREF
  unsigned __int16 v25[1024]; // [rsp+4B0h] [rbp-848h] BYREF

  v4 = 1;
  if ( ((unsigned int)(a3 + 1066598274) <= 1 || (unsigned int)(a3 + 2147024770) <= 1)
    && !(unsigned int)DbgIsSSActive(8u) )
  {
    v4 = 0;
  }
  if ( !a4 || a4 != a3 || (DbgInit(1, 0, 0), (g_dwPrintMask & 0x10) != 0) )
  {
    if ( v4 )
    {
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      DbgInit(1, 0, 0);
      if ( (g_dwPrintMask & 1) != 0 )
      {
        if ( !a1 )
          goto LABEL_19;
        v11 = -1;
        do
          ++v11;
        while ( a1[v11] );
        v12 = L"...";
        if ( v11 <= 0x18000 )
LABEL_19:
          v12 = &Class;
        v13 = myHResultToStringInternal(v24, 0x73u, a3, 0, 0);
        v14 = a1;
        v9 = HIWORD(a2);
        if ( !a1 )
          v14 = &Class;
        v15 = L": ";
        if ( !a1 )
          v15 = &Class;
        DbgPrintf(
          0xFFFFFFFF,
          "%u.%u.%u:<%i/%i/%i, %i:%02i:%02i>: %ws%ws%.*ws%ws\n",
          (unsigned __int16)a2,
          v9,
          0,
          SystemTime.wYear,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          v13,
          v15,
          98304,
          v14,
          v12);
      }
      else
      {
        v9 = HIWORD(a2);
      }
      StringCchPrintfA(v23, 0x10u, "File%u", (unsigned __int16)a2);
      v10 = s_pfnLog;
      if ( s_pfnLog )
      {
        ACP = GetACP();
        v17 = v25;
        if ( !DbgConvertSzToWsz(ACP, v25, 1024, "Error") )
          v17 = 0;
        v18 = GetACP();
        v19 = DbgConvertSzToWsz(v18, v24, 520, v23);
        v20 = v24;
        if ( !v19 )
          v20 = L"?File?";
        v21 = L"?Message?";
        if ( v17 )
          v21 = v17;
        ((void (__fastcall *)(_SYSTEMTIME *, const wchar_t *, const unsigned __int16 *, unsigned __int16 *, unsigned int, int))v10)(
          &SystemTime,
          v21,
          a1,
          v20,
          v9,
          a3);
      }
    }
  }
}

```

## disassembly

```asm
0x180008610  push    rbx
0x180008612  push    rbp
0x180008613  push    rdi
0x180008614  push    r14
0x180008616  push    r15
0x180008618  sub     rsp, 0CD0h
0x18000861f  mov     rax, cs:__security_cookie
0x180008626  xor     rax, rsp
0x180008629  mov     [rsp+0CF8h+var_48], rax
0x180008631  mov     ebx, 1
0x180008636  lea     eax, [r8+3F92FF82h]
0x18000863d  mov     edi, r9d
0x180008640  mov     r14d, r8d
0x180008643  mov     ebp, edx
0x180008645  mov     r15, rcx
0x180008648  cmp     eax, ebx
0x18000864a  ja      loc_180008721
0x180008650  mov     ecx, 8; unsigned int
0x180008655  call    ?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x18000865a  xor     ecx, ecx
0x18000865c  test    eax, eax
0x18000865e  cmovz   ebx, ecx
0x180008661  test    edi, edi
0x180008663  jz      short loc_180008683
0x180008665  cmp     edi, r14d
0x180008668  jnz     short loc_180008683
0x18000866a  xor     r8d, r8d; char *
0x18000866d  xor     edx, edx; int
0x18000866f  mov     ecx, 1; int
0x180008674  call    ?DbgInit@@YAXHHPEBD@Z; DbgInit(int,int,char const *)
0x180008679  mov     eax, cs:?g_dwPrintMask@@3KA; ulong g_dwPrintMask
0x18000867f  test    al, 10h
0x180008681  jz      short loc_180008687
0x180008683  test    ebx, ebx
0x180008685  jnz     short loc_1800086A6
0x180008687  mov     rcx, [rsp+0CF8h+var_48]
0x18000868f  xor     rcx, rsp; StackCookie
0x180008692  call    __security_check_cookie
0x180008697  add     rsp, 0CD0h
0x18000869e  pop     r15
0x1800086a0  pop     r14
0x1800086a2  pop     rdi
0x1800086a3  pop     rbp
0x1800086a4  pop     rbx
0x1800086a5  retn
0x1800086a6  xorps   xmm0, xmm0
0x1800086a9  mov     [rsp+0CF8h+var_30], r12
0x1800086b1  lea     rcx, [rsp+0CF8h+SystemTime]; lpSystemTime
0x1800086b9  movups  xmmword ptr [rsp+0CF8h+SystemTime.wYear], xmm0
0x1800086c1  call    cs:__imp_GetLocalTime
0x1800086c7  xor     r8d, r8d; char *
0x1800086ca  xor     edx, edx; int
0x1800086cc  mov     ecx, 1; int
0x1800086d1  call    ?DbgInit@@YAXHHPEBD@Z; DbgInit(int,int,char const *)
0x1800086d6  mov     eax, cs:?g_dwPrintMask@@3KA; ulong g_dwPrintMask
0x1800086dc  test    al, 1
0x1800086de  jnz     short loc_180008735
0x1800086e0  mov     r12d, ebp
0x1800086e3  shr     r12d, 10h
0x1800086e7  movzx   r9d, bp
0x1800086eb  lea     r8, aFileU; "File%u"
0x1800086f2  mov     edx, 10h; unsigned __int64
0x1800086f7  lea     rcx, [rsp+0CF8h+var_C68]; char *
0x1800086ff  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008704  mov     rbx, cs:?s_pfnLog@@3P6AXPEBU_SYSTEMTIME@@PEBG11KJ@ZEA; void (*s_pfnLog)(_SYSTEMTIME const *,ushort const *,ushort const *,ushort const *,ulong,long)
0x18000870b  test    rbx, rbx
0x18000870e  jnz     loc_18000885A
0x180008714  mov     r12, [rsp+0CF8h+var_30]
0x18000871c  jmp     loc_180008687
0x180008721  lea     eax, [r8+7FF8FF82h]
0x180008728  cmp     eax, ebx
0x18000872a  ja      loc_180008661
0x180008730  jmp     loc_180008650
0x180008735  mov     [rsp+0CF8h+arg_18], rsi
0x18000873d  lea     rbx, Class
0x180008744  mov     [rsp+0CF8h+var_38], r13
0x18000874c  test    r15, r15
0x18000874f  jz      short loc_180008772
0x180008751  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008758  inc     rax
0x18000875b  cmp     word ptr [r15+rax*2], 0
0x180008761  jnz     short loc_180008758
0x180008763  lea     r13, asc_18006AB48; "..."
0x18000876a  cmp     rax, 18000h
0x180008770  ja      short loc_180008775
0x180008772  mov     r13, rbx
0x180008775  xor     r9d, r9d; bool
0x180008778  mov     [rsp+0CF8h+var_CD8], 0; bool
0x18000877d  mov     r8d, r14d; int
0x180008780  lea     rcx, [rsp+0CF8h+var_C58]; unsigned __int16 *
0x180008788  mov     edx, 73h ; 's'; unsigned __int64
0x18000878d  call    ?myHResultToStringInternal@@YAPEBGPEAG_KJ_N2@Z; myHResultToStringInternal(ushort *,unsigned __int64,long,bool,bool)
0x180008792  movzx   ecx, [rsp+0CF8h+SystemTime.wMinute]
0x18000879a  mov     rsi, rax
0x18000879d  movzx   edx, [rsp+0CF8h+SystemTime.wHour]
0x1800087a5  lea     rax, Class
0x1800087ac  movzx   r9d, [rsp+0CF8h+SystemTime.wDay]
0x1800087b5  mov     r12d, ebp
0x1800087b8  movzx   r10d, [rsp+0CF8h+SystemTime.wMonth]
0x1800087c1  mov     rdi, r15
0x1800087c4  movzx   r11d, [rsp+0CF8h+SystemTime.wYear]
0x1800087cd  mov     [rsp+0CF8h+var_C80], r13
0x1800087d2  shr     r12d, 10h
0x1800087d6  test    r15, r15
0x1800087d9  movzx   ebp, bp
0x1800087dc  mov     r8d, ebp
0x1800087df  cmovz   rdi, rbx
0x1800087e3  lea     rbx, asc_180063354; ": "
0x1800087ea  mov     [rsp+0CF8h+var_C88], rdi
0x1800087ef  cmovz   rbx, rax
0x1800087f3  movzx   eax, [rsp+0CF8h+SystemTime.wSecond]
0x1800087fb  mov     [rsp+0CF8h+var_C90], 18000h
0x180008803  mov     [rsp+0CF8h+var_C98], rbx
0x180008808  mov     [rsp+0CF8h+var_CA0], rsi
0x18000880d  mov     [rsp+0CF8h+var_CA8], eax
0x180008811  mov     [rsp+0CF8h+var_CB0], ecx
0x180008815  mov     ecx, 0FFFFFFFFh; unsigned int
0x18000881a  mov     [rsp+0CF8h+var_CB8], edx
0x18000881e  lea     rdx, aUUUIIII02i02iW; "%u.%u.%u:<%i/%i/%i, %i:%02i:%02i>: %ws%"...
0x180008825  mov     [rsp+0CF8h+var_CC0], r9d
0x18000882a  mov     r9d, r12d
0x18000882d  mov     [rsp+0CF8h+var_CC8], r10d
0x180008832  mov     [rsp+0CF8h+var_CD0], r11d
0x180008837  mov     qword ptr [rsp+0CF8h+var_CD8], 0
0x180008840  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x180008845  mov     r13, [rsp+0CF8h+var_38]
0x18000884d  mov     rsi, [rsp+0CF8h+arg_18]
0x180008855  jmp     loc_1800086E7
0x18000885a  call    cs:__imp_GetACP
0x180008860  lea     r9, aError; "Error"
0x180008867  mov     r8d, 400h; int
0x18000886d  mov     ecx, eax; unsigned int
0x18000886f  lea     rdx, [rsp+0CF8h+var_848]; unsigned __int16 *
0x180008877  call    ?DbgConvertSzToWsz@@YAKIPEAGJPEBD@Z; DbgConvertSzToWsz(uint,ushort *,long,char const *)
0x18000887c  xor     ecx, ecx
0x18000887e  lea     rdi, [rsp+0CF8h+var_848]
0x180008886  test    eax, eax
0x180008888  cmovz   rdi, rcx
0x18000888c  call    cs:__imp_GetACP
0x180008892  lea     r9, [rsp+0CF8h+var_C68]; char *
0x18000889a  mov     r8d, 208h; int
0x1800088a0  mov     ecx, eax; unsigned int
0x1800088a2  lea     rdx, [rsp+0CF8h+var_C58]; unsigned __int16 *
0x1800088aa  call    ?DbgConvertSzToWsz@@YAKIPEAGJPEBD@Z; DbgConvertSzToWsz(uint,ushort *,long,char const *)
0x1800088af  lea     r9, [rsp+0CF8h+var_C58]
0x1800088b7  test    eax, eax
0x1800088b9  jnz     short loc_1800088C2
0x1800088bb  lea     r9, aFile; "?File?"
0x1800088c2  test    rdi, rdi
0x1800088c5  mov     [rsp+0CF8h+var_CD0], r14d
0x1800088ca  lea     rdx, aMessage; "?Message?"
0x1800088d1  mov     dword ptr [rsp+0CF8h+var_CD8], r12d
0x1800088d6  cmovnz  rdx, rdi
0x1800088da  lea     rcx, [rsp+0CF8h+SystemTime]
0x1800088e2  mov     r8, r15
0x1800088e5  mov     rax, rbx
0x1800088e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ed  jmp     loc_180008714
```
