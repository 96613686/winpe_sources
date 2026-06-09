# FindSrcFileOnServer(ulong,ushort *,unsigned __int64,ushort *,void *,DbsDynamicString<ushort> *,ulong *)

- ea: `0x180296000`
- end: `0x1802963ae`
- name: `?FindSrcFileOnServer@@YAHKPEAG_K0PEAXPEAV?$DbsDynamicString@G@@PEAK@Z`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180295754`

## callees

- `0x18007be30`
- `0x18007cf9c`
- `0x180081918`
- `0x18008d550`
- `0x18009543c`
- `0x1800b94c4`
- `0x1800f0f40`
- `0x1800f2560`
- `0x180296000`
- `0x180296754`
- `0x1802984ac`
- `0x1802e2e90`
- `0x1802e7fb8`

## import_xrefs

- `dbghelp!SymInitializeW` at `0x180296227`
- `dbghelp!SymInitializeW` at `0x180296227`
- `dbghelp!SymRegisterCallbackW64` at `0x18029624e`
- `dbghelp!SymRegisterCallbackW64` at `0x18029624e`
- `dbghelp!SymGetSourceFileFromTokenByTokenNameW` at `0x1802962b3`
- `dbghelp!SymGetSourceFileFromTokenByTokenNameW` at `0x1802962b3`
- `dbghelp!SymGetSourceFileTokenByTokenNameW` at `0x1802961ed`
- `dbghelp!SymGetSourceFileTokenByTokenNameW` at `0x1802961ed`

## string_xrefs

- `0x180296163`: `<token>`
- `0x18029631c`: `    server path '%s'\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindSrcFileOnServer(
        int a1,
        const wchar_t *a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        int *a7)
{
  int v8; // esi
  struct ImageInfo *ImageByOffset; // r14
  int v10; // r15d
  wchar_t v11; // r12
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  int v14; // r9d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  const wchar_t *v19; // rdx
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // r8
  int v25; // [rsp+48h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A8h]
  int *v29; // [rsp+68h] [rbp-A0h]
  __int64 v30; // [rsp+70h] [rbp-98h]
  __int64 v31; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v32; // [rsp+84h] [rbp-84h]
  char v33; // [rsp+90h] [rbp-78h] BYREF
  __int64 v34; // [rsp+228h] [rbp+120h] BYREF
  unsigned int v35; // [rsp+234h] [rbp+12Ch]
  char v36; // [rsp+240h] [rbp+138h] BYREF

  v30 = -2;
  v28 = a4;
  v8 = a1;
  v25 = a1;
  v26 = a5;
  v29 = a7;
  if ( (g_EngOptions & 8) == 0 )
  {
    ImageByOffset = 0;
    if ( a5 || a3 && g_Process && (ImageByOffset = ProcessInfo::FindImageByOffset(g_Process, a3, 0, 0)) != 0 )
    {
      v10 = 0;
      while ( a2 && *a2 )
      {
        v11 = 0;
        v12 = wcschr(a2, 0x3Bu);
        v13 = v12;
        if ( v12 )
        {
          v11 = *v12;
          *v12 = 0;
        }
        DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
          (unsigned int)&v31,
          (unsigned int)&v33,
          200,
          200,
          1);
        DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
          (unsigned int)&v34,
          (unsigned int)&v36,
          v14,
          v14,
          1);
        if ( (unsigned __int8)IsSourceServerShare(a2, 0, &v31, &v34) )
        {
          if ( !v10 )
          {
            SrcOut(L"Scan srcsrv %s for:\n", a2);
            if ( ImageByOffset )
              v19 = (const wchar_t *)*((_QWORD *)ImageByOffset + 28);
            else
              v19 = L"<token>";
            SrcOut(L"  '%s!%s'\n", v19, v28);
            v10 = 1;
          }
          if ( v26 )
          {
            if ( g_Process )
            {
              v20 = *((_QWORD *)g_Process + 51);
            }
            else if ( SymInitializeW((HANDLE)0xF0F0F0F0LL, 0, 0) )
            {
              v20 = 4042322160LL;
              SymRegisterCallbackW64((HANDLE)0xF0F0F0F0LL, SymbolCallbackFunction, 0);
            }
            else
            {
              v20 = 0;
            }
          }
          else
          {
            LODWORD(v27) = 0;
            v20 = *((_QWORD *)g_Process + 51);
            if ( !ImageByOffset )
              MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15, v17, v18);
            v21 = 0;
            if ( v35 >= 2 )
              v21 = v34;
            v22 = 0;
            if ( v32 >= 2 )
              v22 = v31;
            if ( !(unsigned int)SymGetSourceFileTokenByTokenNameW(
                                  v20,
                                  *((_QWORD *)ImageByOffset + 4),
                                  v28,
                                  v22,
                                  v21,
                                  &v26,
                                  &v27) )
              v26 = 0;
          }
          UpdateStatusBar(L"Retrieving source file (Press Ctrl-Break to cancel)", 0);
          if ( v20 && v26 && DbsDynamicString<unsigned short>::GetStr(a6, 2080) )
          {
            v23 = 0;
            if ( v32 >= 2 )
              v23 = v31;
            if ( (unsigned int)SymGetSourceFileFromTokenByTokenNameW(v20, v26, v23, a2, *a6, *((_DWORD *)a6 + 2) >> 1) )
            {
              DbsDynamicString<unsigned short>::SetCurStrCharsUsed(a6);
              SrcOut(L"    found file '%s'\n", v28);
              SrcOut(L"    server path '%s'\n", a2);
              SrcOut(L"    local '%s'\n", *a6);
              *v29 = v25;
              if ( v13 )
                *v13 = v11;
              ClearStatusBar();
              DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v34);
              DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v31);
              return 1;
            }
          }
          ClearStatusBar();
          v8 = v25;
        }
        if ( v13 )
          *v13++ = v11;
        a2 = v13;
        v25 = ++v8;
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v34);
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v31);
      }
      if ( v10 )
        SrcOut(L"  file not found with srcsrv\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180296000  mov     rax, rsp
0x180296003  push    rbp
0x180296004  push    rsi
0x180296005  push    rdi
0x180296006  push    r12
0x180296008  push    r13
0x18029600a  push    r14
0x18029600c  push    r15
0x18029600e  lea     rbp, [rax-318h]
0x180296015  sub     rsp, 3E0h
0x18029601c  mov     [rsp+410h+var_3A8], 0FFFFFFFFFFFFFFFEh
0x180296025  mov     [rax+8], rbx
0x180296029  mov     rax, cs:__security_cookie
0x180296030  xor     rax, rsp
0x180296033  mov     [rbp+310h+var_40], rax
0x18029603a  mov     [rsp+410h+var_3B8], r9
0x18029603f  mov     rax, r8
0x180296042  mov     rdi, rdx
0x180296045  mov     esi, ecx
0x180296047  mov     dword ptr [rsp+410h+var_3D0], ecx
0x18029604b  mov     rcx, [rbp+310h+arg_20]
0x180296052  mov     [rsp+410h+var_3C8], rcx
0x180296057  mov     r13, [rbp+310h+arg_28]
0x18029605e  mov     rdx, [rbp+310h+arg_30]
0x180296065  mov     [rsp+410h+var_3B0], rdx
0x18029606a  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x180296071  jnz     loc_180296381
0x180296077  xor     ebx, ebx
0x180296079  mov     r14d, ebx
0x18029607c  test    rcx, rcx
0x18029607f  jnz     short loc_1802960B4
0x180296081  test    rax, rax
0x180296084  jz      loc_180296381
0x18029608a  mov     rcx, cs:?g_Process@@3PEAVProcessInfo@@EA; this
0x180296091  test    rcx, rcx
0x180296094  jz      loc_180296381
0x18029609a  xor     r9d, r9d; int
0x18029609d  xor     r8d, r8d; int
0x1802960a0  mov     rdx, rax; unsigned __int64
0x1802960a3  call    ?FindImageByOffset@ProcessInfo@@QEAAPEAVImageInfo@@_KHH@Z; ProcessInfo::FindImageByOffset(unsigned __int64,int,int)
0x1802960a8  mov     r14, rax
0x1802960ab  test    rax, rax
0x1802960ae  jz      loc_180296381
0x1802960b4  mov     r15d, ebx
0x1802960b7  test    rdi, rdi
0x1802960ba  jz      loc_180296370
0x1802960c0  cmp     [rdi], bx
0x1802960c3  jz      loc_180296370
0x1802960c9  mov     r12d, ebx
0x1802960cc  mov     edx, 3Bh ; ';'; Ch
0x1802960d1  mov     rcx, rdi; Str
0x1802960d4  call    wcschr
0x1802960d9  mov     rbx, rax
0x1802960dc  test    rax, rax
0x1802960df  jz      short loc_1802960EA
0x1802960e1  movzx   r12d, word ptr [rax]
0x1802960e5  xor     ecx, ecx
0x1802960e7  mov     [rax], cx
0x1802960ea  mov     byte ptr [rsp+410h+var_3F0], 1
0x1802960ef  mov     r9d, 0C8h
0x1802960f5  mov     r8d, r9d
0x1802960f8  lea     rdx, [rbp+310h+var_388]
0x1802960fc  lea     rcx, [rsp+70h]
0x180296101  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x180296106  nop
0x180296107  mov     byte ptr [rsp+410h+var_3F0], 1
0x18029610c  mov     r8d, r9d
0x18029610f  lea     rdx, [rbp+310h+var_1D8]
0x180296116  lea     rcx, [rbp+310h+var_1F0]
0x18029611d  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x180296122  nop
0x180296123  lea     r9, [rbp+310h+var_1F0]
0x18029612a  lea     r8, [rsp+70h]
0x18029612f  xor     edx, edx
0x180296131  mov     rcx, rdi
0x180296134  call    ?IsSourceServerShare@@YA_NPEBG0PEAV?$DbsDeclDynamicString@G$0MI@$00@@1@Z; IsSourceServerShare(ushort const *,ushort const *,DbsDeclDynamicString<ushort,200,1> *,DbsDeclDynamicString<ushort,200,1> *)
0x180296139  test    al, al
0x18029613b  jz      loc_1802962CC
0x180296141  test    r15d, r15d
0x180296144  jnz     short loc_180296181
0x180296146  mov     rdx, rdi
0x180296149  lea     rcx, aScanSrcsrvSFor; "Scan srcsrv %s for:\n"
0x180296150  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180296155  test    r14, r14
0x180296158  jz      short loc_180296163
0x18029615a  mov     rdx, [r14+0E0h]
0x180296161  jmp     short loc_18029616A
0x180296163  lea     rdx, aToken; "<token>"
0x18029616a  mov     r8, [rsp+410h+var_3B8]
0x18029616f  lea     rcx, aSS_14; "  '%s!%s'\n"
0x180296176  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x18029617b  mov     r15d, 1
0x180296181  cmp     [rsp+410h+var_3C8], 0
0x180296187  jnz     short loc_180296208
0x180296189  mov     dword ptr [rsp+410h+var_3C0], 0
0x180296191  mov     rax, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x180296198  mov     rsi, [rax+198h]
0x18029619f  test    r14, r14
0x1802961a2  jnz     short loc_1802961A9
0x1802961a4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1802961a9  xor     eax, eax
0x1802961ab  cmp     [rbp+310h+var_1E4], 2
0x1802961b2  cmovnb  rax, [rbp+310h+var_1F0]
0x1802961ba  xor     r9d, r9d
0x1802961bd  cmp     [rsp+410h+var_394], 2
0x1802961c2  cmovnb  r9, [rsp+70h]
0x1802961c8  lea     rcx, [rsp+410h+var_3C0]
0x1802961cd  mov     [rsp+30h], rcx
0x1802961d2  lea     rcx, [rsp+410h+var_3C8]
0x1802961d7  mov     [rsp+410h+var_3E8], rcx
0x1802961dc  mov     [rsp+410h+var_3F0], rax
0x1802961e1  mov     r8, [rsp+410h+var_3B8]
0x1802961e6  mov     rdx, [r14+20h]
0x1802961ea  mov     rcx, rsi
0x1802961ed  call    cs:__imp_SymGetSourceFileTokenByTokenNameW
0x1802961f4  nop     dword ptr [rax+rax+00h]
0x1802961f9  test    eax, eax
0x1802961fb  jnz     short loc_18029625A
0x1802961fd  mov     [rsp+410h+var_3C8], 0
0x180296206  jmp     short loc_18029625A
0x180296208  mov     rsi, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x18029620f  test    rsi, rsi
0x180296212  jz      short loc_18029621D
0x180296214  mov     rsi, [rsi+198h]
0x18029621b  jmp     short loc_18029625A
0x18029621d  xor     r8d, r8d; fInvadeProcess
0x180296220  xor     edx, edx; UserSearchPath
0x180296222  mov     ecx, 0F0F0F0F0h; hProcess
0x180296227  call    cs:__imp_SymInitializeW
0x18029622e  nop     dword ptr [rax+rax+00h]
0x180296233  test    eax, eax
0x180296235  jnz     short loc_18029623B
0x180296237  xor     esi, esi
0x180296239  jmp     short loc_18029625A
0x18029623b  mov     eax, 0F0F0F0F0h
0x180296240  mov     esi, eax
0x180296242  xor     r8d, r8d; UserContext
0x180296245  lea     rdx, ?SymbolCallbackFunction@@YAHPEAXK_K1@Z; CallbackFunction
0x18029624c  mov     ecx, eax; hProcess
0x18029624e  call    cs:__imp_SymRegisterCallbackW64
0x180296255  nop     dword ptr [rax+rax+00h]
0x18029625a  xor     edx, edx; bool
0x18029625c  lea     rcx, aRetrievingSour; "Retrieving source file (Press Ctrl-Brea"...
0x180296263  call    ?UpdateStatusBar@@YAXPEBG_N@Z; UpdateStatusBar(ushort const *,bool)
0x180296268  test    rsi, rsi
0x18029626b  jz      short loc_1802962C3
0x18029626d  cmp     [rsp+410h+var_3C8], 0
0x180296273  jz      short loc_1802962C3
0x180296275  mov     edx, 820h
0x18029627a  mov     rcx, r13
0x18029627d  call    ?GetStr@?$DbsDynamicString@G@@QEAAPEAGK@Z; DbsDynamicString<ushort>::GetStr(ulong)
0x180296282  test    rax, rax
0x180296285  jz      short loc_1802962C3
0x180296287  mov     edx, [r13+8]
0x18029628b  shr     edx, 1
0x18029628d  mov     rax, [r13+0]
0x180296291  xor     r8d, r8d
0x180296294  cmp     [rsp+410h+var_394], 2
0x180296299  cmovnb  r8, [rsp+70h]
0x18029629f  mov     dword ptr [rsp+410h+var_3E8], edx
0x1802962a3  mov     [rsp+410h+var_3F0], rax
0x1802962a8  mov     r9, rdi
0x1802962ab  mov     rdx, [rsp+410h+var_3C8]
0x1802962b0  mov     rcx, rsi
0x1802962b3  call    cs:__imp_SymGetSourceFileFromTokenByTokenNameW
0x1802962ba  nop     dword ptr [rax+rax+00h]
0x1802962bf  test    eax, eax
0x1802962c1  jnz     short loc_180296300
0x1802962c3  call    ?ClearStatusBar@@YAXXZ; ClearStatusBar(void)
0x1802962c8  mov     esi, dword ptr [rsp+410h+var_3D0]
0x1802962cc  test    rbx, rbx
0x1802962cf  jz      short loc_1802962D9
0x1802962d1  mov     [rbx], r12w
0x1802962d5  add     rbx, 2
0x1802962d9  mov     rdi, rbx
0x1802962dc  inc     esi
0x1802962de  mov     dword ptr [rsp+410h+var_3D0], esi
0x1802962e2  lea     rcx, [rbp+310h+var_1F0]
0x1802962e9  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1802962ee  nop
0x1802962ef  lea     rcx, [rsp+70h]
0x1802962f4  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1802962f9  xor     ebx, ebx
0x1802962fb  jmp     loc_1802960B7
0x180296300  mov     rcx, r13
0x180296303  call    ?SetCurStrCharsUsed@?$DbsDynamicString@G@@QEAAXXZ; DbsDynamicString<ushort>::SetCurStrCharsUsed(void)
0x180296308  mov     rdx, [rsp+410h+var_3B8]
0x18029630d  lea     rcx, aFoundFileS; "    found file '%s'\n"
0x180296314  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180296319  mov     rdx, rdi
0x18029631c  lea     rcx, aServerPathS; "    server path '%s'\n"
0x180296323  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180296328  mov     rdx, [r13+0]
0x18029632c  lea     rcx, aLocalS; "    local '%s'\n"
0x180296333  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180296338  mov     ecx, dword ptr [rsp+410h+var_3D0]
0x18029633c  mov     rdx, [rsp+410h+var_3B0]
0x180296341  mov     [rdx], ecx
0x180296343  test    rbx, rbx
0x180296346  jz      short loc_18029634C
0x180296348  mov     [rbx], r12w
0x18029634c  call    ?ClearStatusBar@@YAXXZ; ClearStatusBar(void)
0x180296351  nop
0x180296352  lea     rcx, [rbp+310h+var_1F0]
0x180296359  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18029635e  nop
0x18029635f  lea     rcx, [rsp+70h]
0x180296364  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x180296369  mov     eax, 1
0x18029636e  jmp     short loc_180296383
0x180296370  test    r15d, r15d
0x180296373  jz      short loc_180296381
0x180296375  lea     rcx, aFileNotFoundWi; "  file not found with srcsrv\n"
0x18029637c  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180296381  xor     eax, eax
0x180296383  mov     rcx, [rbp+310h+var_40]
0x18029638a  xor     rcx, rsp; StackCookie
0x18029638d  call    __security_check_cookie
0x180296392  mov     rbx, [rsp+410h+arg_0]
0x18029639a  add     rsp, 3E0h
0x1802963a1  pop     r15
0x1802963a3  pop     r14
0x1802963a5  pop     r13
0x1802963a7  pop     r12
0x1802963a9  pop     rdi
0x1802963aa  pop     rsi
0x1802963ab  pop     rbp
0x1802963ac  retn
```
