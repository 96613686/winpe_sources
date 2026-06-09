# StrTabEnumDriverStoreInfForRemovalCallback

- ea: `0x180007680`
- end: `0x180007bfa`
- name: `StrTabEnumDriverStoreInfForRemovalCallback`
- size: `1402`
- prototype: `_BOOL8 __fastcall(__int64, __int64, const WCHAR *, int *, int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callees

- `0x180006c9c`
- `0x180007370`
- `0x180007680`
- `0x180008438`
- `0x180008990`
- `0x180008dfe`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007b49`
- `KERNEL32!GetLastError` at `0x180007b49`
- `SETUPAPI!SetupUninstallOEMInfW` at `0x180007b3f`
- `SETUPAPI!SetupUninstallOEMInfW` at `0x180007b3f`
- `SETUPAPI!pSetupStringTableGetExtraData` at `0x1800079a9`
- `SETUPAPI!pSetupStringTableGetExtraData` at `0x1800079a9`
- `SETUPAPI!pSetupGetFileTitle` at `0x180007938`
- `SETUPAPI!pSetupGetFileTitle` at `0x180007af4`
- `SETUPAPI!pSetupGetFileTitle` at `0x180007938`
- `SETUPAPI!pSetupGetFileTitle` at `0x180007af4`
- `SETUPAPI!pSetupStringTableStringFromId` at `0x1800079be`
- `SETUPAPI!pSetupStringTableStringFromId` at `0x1800079be`
- `drvstore!DriverStoreFindW` at `0x1800078d8`
- `drvstore!DriverStoreFindW` at `0x1800078d8`

## string_xrefs

- `0x180007b07`: `INF %ws (%ws) %ws be removed.`
- `0x180007b64`: `Failed to remove INF %ws, Err = 0x%lx`
- `0x180007b7b`: `INF %ws was removed.`

## pseudocode

```c
_BOOL8 __fastcall StrTabEnumDriverStoreInfForRemovalCallback(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        int *a4,
        int a5,
        __int64 a6)
{
  int v8; // r12d
  int v9; // edi
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  GUID *v12; // r8
  unsigned int v13; // ecx
  int v14; // ebx
  __int64 v15; // rbx
  __int64 v16; // rcx
  _WORD *v17; // rdx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  _WORD *FileTitle; // rdx
  char *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  wchar_t *v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rdx
  int DirectorySize; // eax
  unsigned __int64 v28; // rdx
  const wchar_t *v29; // rbx
  __int64 v30; // rdi
  void (*v31)(__int64, __int64, _QWORD, const char *, ...); // rsi
  __int64 v32; // rax
  __int64 v33; // rdx
  DWORD LastError; // ebx
  __int64 v35; // rcx
  void (*v36)(__int64, __int64, _QWORD, const char *, ...); // rax
  __int64 v37; // rdx
  int v38; // edx
  unsigned int v39; // eax
  __int64 v41; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v44[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v45[704]; // [rsp+100h] [rbp+0h] BYREF
  _WORD v46[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v47[528]; // [rsp+5D0h] [rbp+4D0h] BYREF

  v43 = 0;
  memset_0(v45, 0, 0x2B8u);
  memset_0(v44, 0, sizeof(v44));
  v42 = 0;
  if ( !a3 || !*a3 || a5 != 160 || !a4 || !a6 )
  {
    v8 = 87;
    return v8 == 0;
  }
  if ( (unsigned int)PnpCleanDriversNotifyCallback(a6) )
  {
    v9 = *(_DWORD *)(a6 + 60);
    v10 = *(_DWORD *)(a6 + 64);
    v8 = 0;
    if ( !(unsigned int)pUtilGetSystemTimeOfDayInfo(&v43, 0)
      && v43 >= *((_QWORD *)a4 + 14)
      && v43 - *((_QWORD *)a4 + 14) < 864000000000LL * (unsigned __int64)v10 )
    {
      goto LABEL_84;
    }
    if ( !a4[30] )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = (&off_18000B2A0)[2 * v11];
        if ( *(_QWORD *)&v12->Data1 == *((_QWORD *)a4 + 18) && *(_QWORD *)v12->Data4 == *((_QWORD *)a4 + 19) )
          break;
        if ( ++v11 )
          goto LABEL_19;
      }
      if ( (byte_18000B2A8[16 * v11] & 1) != 0 )
        v9 = 1;
    }
LABEL_19:
    v13 = *a4;
    if ( *a4 == 1 || a4[1] || (v14 = 1, ((a4[3] - 1) & 0xFFFFFFFD) == 0) )
      v14 = 0;
    if ( v9 )
    {
      if ( !a4[4] )
        goto LABEL_34;
      (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a6 + 40))(
        *(_QWORD *)(a6 + 48),
        4,
        0,
        "Applying extra filtering to %ws because it is an MBS driver",
        a3);
    }
    v13 = *a4;
    if ( *a4 == 2 )
    {
      v13 = 2;
    }
    else
    {
      if ( v13 != 5 )
      {
        if ( a4[5] || a4[2] )
          goto LABEL_33;
LABEL_34:
        if ( a4[31] && (!v9 || a4[4] || a4[32]) )
          v14 = 0;
        if ( v13 > 6 )
          goto LABEL_84;
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a6 + 40))(
          *(_QWORD *)(a6 + 48),
          6,
          0,
          "Checking driver %ws, source = %ws...",
          a3,
          off_18000B260[v13]);
        if ( !v14 )
          goto LABEL_84;
        v15 = 260;
        if ( !(unsigned int)DriverStoreFindW(*(_QWORD *)(a6 + 88), a3, 0xFFFF, 0, 1, v47, 260, v45) )
          goto LABEL_84;
        v16 = 2147483646;
        v17 = v47;
        v18 = v46;
        do
        {
          if ( !v16 )
            break;
          if ( !*v17 )
            break;
          *v18++ = *v17++;
          --v16;
          --v15;
        }
        while ( v15 );
        v19 = v18 - 1;
        if ( v15 )
          v19 = v18;
        *v19 = 0;
        if ( !v15 )
          goto LABEL_84;
        FileTitle = (_WORD *)pSetupGetFileTitle(v46, v17);
        if ( FileTitle == v46 )
          goto LABEL_84;
        v21 = (char *)(FileTitle - 1);
        if ( *(FileTitle - 1) != 92 && *(_WORD *)v21 != 47 )
          goto LABEL_84;
        if ( v21 - (char *)v46 == 4 && v46[0] && v46[1] == 58 )
          *FileTitle = 0;
        else
          *(_WORD *)v21 = 0;
        if ( (unsigned int)pSetupStringTableGetExtraData(*(_QWORD *)(a6 + 112), (unsigned int)a4[35], v44, 160) )
          v22 = pSetupStringTableStringFromId(*(_QWORD *)(a6 + 112), (unsigned int)a4[35]);
        else
          v22 = 0;
        if ( a4[6] )
        {
          v26 = *a4;
          a4[34] = 8;
          (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a6 + 40))(
            *(_QWORD *)(a6 + 48),
            4,
            0,
            "INF %ws (source = %ws) is primitive, reason = %ws",
            a3,
            off_18000B260[v26],
            L"NOT INSTALLED");
        }
        else
        {
          if ( a4[33] && !a4[34] )
            a4[34] = 7;
          v23 = a4[34];
          if ( (unsigned int)v23 > 8 )
            goto LABEL_84;
          v24 = off_18000B210[v23];
          v25 = L"NONE";
          if ( v22 )
            v25 = (const wchar_t *)v22;
          (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a6 + 40))(
            *(_QWORD *)(a6 + 48),
            4,
            0,
            "INF %ws (source = %ws) is superseded by INF %ws, reason = %ws",
            a3,
            off_18000B260[*a4],
            v25,
            v24);
        }
        DirectorySize = pUtilGetDirectorySize((__int64)v46, *(_DWORD *)(a6 + 96), &v42);
        v28 = v42;
        v29 = L"will";
        v30 = *(_QWORD *)(a6 + 48);
        if ( DirectorySize )
          v28 = 0;
        v31 = *(void (**)(__int64, __int64, _QWORD, const char *, ...))(a6 + 40);
        if ( !*(_DWORD *)(a6 + 56) )
          v29 = L"may";
        v42 = v28;
        v32 = pSetupGetFileTitle(v46, v28);
        v31(v30, 3, 0, "INF %ws (%ws) %ws be removed.", a3, v32, v29);
        if ( *(_DWORD *)(a6 + 56) )
        {
          LogInfInfo(a6, v33, a4);
          LastError = 0;
          if ( !SetupUninstallOEMInfW(a3, 0, 0) )
            LastError = GetLastError();
          v35 = *(_QWORD *)(a6 + 48);
          v36 = *(void (**)(__int64, __int64, _QWORD, const char *, ...))(a6 + 40);
          if ( LastError )
          {
            LODWORD(v41) = LastError;
            v36(v35, 1, 0, "Failed to remove INF %ws, Err = 0x%lx", a3, v41);
            goto LABEL_84;
          }
          v36(v35, 3, 0, "INF %ws was removed.", a3);
        }
        v37 = -1;
        if ( *(_QWORD *)(a6 + 80) + v42 >= *(_QWORD *)(a6 + 80) )
          v37 = *(_QWORD *)(a6 + 80) + v42;
        *(_QWORD *)(a6 + 80) = v37;
        v38 = -1;
        v39 = *(_DWORD *)(a6 + 72);
        if ( v39 + 1 >= v39 )
          v38 = v39 + 1;
        *(_DWORD *)(a6 + 72) = v38;
        goto LABEL_84;
      }
      v13 = 5;
    }
LABEL_33:
    v14 = 0;
    goto LABEL_34;
  }
  v8 = 1223;
LABEL_84:
  *(_DWORD *)a6 = v8;
  return v8 == 0;
}

```

## disassembly

```asm
0x180007680  mov     [rsp-8+arg_0], rbx
0x180007685  push    rbp
0x180007686  push    rsi
0x180007687  push    rdi
0x180007688  push    r12
0x18000768a  push    r13
0x18000768c  push    r14
0x18000768e  push    r15
0x180007690  lea     rbp, [rsp-6F0h]
0x180007698  sub     rsp, 7F0h
0x18000769f  mov     rax, cs:__security_cookie
0x1800076a6  xor     rax, rsp
0x1800076a9  mov     [rbp+720h+var_40], rax
0x1800076b0  mov     r15, [rbp+720h+arg_28]
0x1800076b7  lea     rcx, [rbp+720h+var_720]; void *
0x1800076bb  mov     r13, r8
0x1800076be  xor     esi, esi
0x1800076c0  mov     r8d, 2B8h; Size
0x1800076c6  mov     [rsp+820h+var_7C8], rsi
0x1800076cb  xor     edx, edx; Val
0x1800076cd  mov     r14, r9
0x1800076d0  call    memset_0
0x1800076d5  mov     ebx, 0A0h
0x1800076da  lea     rcx, [rsp+820h+var_7C0]; void *
0x1800076df  mov     r8d, ebx; Size
0x1800076e2  xor     edx, edx; Val
0x1800076e4  call    memset_0
0x1800076e9  mov     [rsp+820h+var_7D0], rsi
0x1800076ee  test    r13, r13
0x1800076f1  jz      loc_180007BC2
0x1800076f7  cmp     [r13+0], si
0x1800076fc  jz      loc_180007BC2
0x180007702  cmp     [rbp+720h+arg_20], ebx
0x180007708  jnz     loc_180007BC2
0x18000770e  test    r14, r14
0x180007711  jz      loc_180007BC2
0x180007717  test    r15, r15
0x18000771a  jz      loc_180007BC2
0x180007720  mov     rcx, r15
0x180007723  call    PnpCleanDriversNotifyCallback
0x180007728  test    eax, eax
0x18000772a  jnz     short loc_180007737
0x18000772c  mov     r12d, 4C7h
0x180007732  jmp     loc_180007BBD
0x180007737  mov     edi, [r15+3Ch]
0x18000773b  lea     rcx, [rsp+820h+var_7C8]
0x180007740  mov     ebx, [r15+40h]
0x180007744  xor     edx, edx
0x180007746  mov     r12d, esi
0x180007749  call    pUtilGetSystemTimeOfDayInfo
0x18000774e  test    eax, eax
0x180007750  jnz     short loc_18000777A
0x180007752  mov     rax, [rsp+820h+var_7C8]
0x180007757  cmp     rax, [r14+70h]
0x18000775b  jb      short loc_18000777A
0x18000775d  sub     rax, [r14+70h]
0x180007761  mov     ecx, ebx
0x180007763  mov     rdx, 0C92A69C000h
0x18000776d  imul    rcx, rdx
0x180007771  cmp     rax, rcx
0x180007774  jb      loc_180007BBD
0x18000777a  lea     r10, cs:180000000h
0x180007781  mov     r9d, 1
0x180007787  cmp     [r14+78h], esi
0x18000778b  jnz     short loc_1800077CB
0x18000778d  mov     ecx, esi
0x18000778f  mov     edx, ecx
0x180007791  add     rdx, rdx
0x180007794  mov     r8, ds:rva off_18000B2A0[r10+rdx*8]
0x18000779c  mov     rax, [r8]
0x18000779f  cmp     rax, [r14+90h]
0x1800077a6  jnz     short loc_1800077B5
0x1800077a8  mov     rax, [r8+8]
0x1800077ac  cmp     rax, [r14+98h]
0x1800077b3  jz      short loc_1800077BF
0x1800077b5  add     ecx, r9d
0x1800077b8  cmp     ecx, r9d
0x1800077bb  jb      short loc_18000778F
0x1800077bd  jmp     short loc_1800077CB
0x1800077bf  test    ds:rva byte_18000B2A8[r10+rdx*8], r9b
0x1800077c7  cmovnz  edi, r9d
0x1800077cb  mov     ecx, [r14]
0x1800077ce  cmp     ecx, r9d
0x1800077d1  jz      short loc_1800077EA
0x1800077d3  cmp     [r14+4], esi
0x1800077d7  jnz     short loc_1800077EA
0x1800077d9  mov     eax, [r14+0Ch]
0x1800077dd  mov     ebx, r9d
0x1800077e0  sub     eax, r9d
0x1800077e3  test    eax, 0FFFFFFFDh
0x1800077e8  jnz     short loc_1800077EC
0x1800077ea  mov     ebx, esi
0x1800077ec  test    edi, edi
0x1800077ee  jz      short loc_18000781D
0x1800077f0  cmp     [r14+10h], esi
0x1800077f4  jz      short loc_180007846
0x1800077f6  mov     rcx, [r15+30h]
0x1800077fa  lea     r9, aApplyingExtraF; "Applying extra filtering to %ws because"...
0x180007801  mov     rax, [r15+28h]
0x180007805  xor     r8d, r8d
0x180007808  mov     [rsp+820h+var_800], r13
0x18000780d  lea     edx, [r8+4]
0x180007811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007816  lea     r10, cs:180000000h
0x18000781d  mov     ecx, [r14]
0x180007820  cmp     ecx, 2
0x180007823  jz      short loc_18000783F
0x180007825  cmp     ecx, 5
0x180007828  jz      short loc_180007838
0x18000782a  cmp     [r14+14h], esi
0x18000782e  jnz     short loc_180007844
0x180007830  cmp     [r14+8], esi
0x180007834  jz      short loc_180007846
0x180007836  jmp     short loc_180007844
0x180007838  mov     ecx, 5
0x18000783d  jmp     short loc_180007844
0x18000783f  mov     ecx, 2
0x180007844  mov     ebx, esi
0x180007846  cmp     [r14+7Ch], esi
0x18000784a  jz      short loc_180007861
0x18000784c  test    edi, edi
0x18000784e  jz      short loc_18000785F
0x180007850  cmp     [r14+10h], esi
0x180007854  jnz     short loc_18000785F
0x180007856  cmp     [r14+80h], esi
0x18000785d  jz      short loc_180007861
0x18000785f  mov     ebx, esi
0x180007861  mov     edx, 6
0x180007866  cmp     ecx, edx
0x180007868  ja      loc_180007BBD
0x18000786e  mov     rax, [r15+28h]
0x180007872  lea     r9, aCheckingDriver; "Checking driver %ws, source = %ws..."
0x180007879  movsxd  rcx, ecx
0x18000787c  xor     r8d, r8d
0x18000787f  mov     rcx, ds:rva off_18000B260[r10+rcx*8]; "UNKNOWN" ...
0x180007887  mov     [rsp+820h+var_7F8], rcx
0x18000788c  mov     rcx, [r15+30h]
0x180007890  mov     [rsp+820h+var_800], r13
0x180007895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789a  test    ebx, ebx
0x18000789c  jz      loc_180007BBD
0x1800078a2  mov     rcx, [r15+58h]
0x1800078a6  lea     rax, [rbp+720h+var_720]
0x1800078aa  mov     [rsp+820h+var_7E8], rax
0x1800078af  mov     ebx, 104h
0x1800078b4  lea     rax, [rbp+720h+var_250]
0x1800078bb  mov     dword ptr [rsp+820h+var_7F0], ebx
0x1800078bf  mov     [rsp+820h+var_7F8], rax
0x1800078c4  mov     r8d, 0FFFFh
0x1800078ca  xor     r9d, r9d
0x1800078cd  mov     dword ptr [rsp+820h+var_800], 1
0x1800078d5  mov     rdx, r13
0x1800078d8  call    cs:__imp_DriverStoreFindW
0x1800078de  test    eax, eax
0x1800078e0  jz      loc_180007BBD
0x1800078e6  mov     ecx, 7FFFFFFEh
0x1800078eb  lea     rdx, [rbp+720h+var_250]
0x1800078f2  lea     rax, [rbp+720h+var_460]
0x1800078f9  test    rcx, rcx
0x1800078fc  jz      short loc_18000791D
0x1800078fe  movzx   r8d, word ptr [rdx]
0x180007902  test    r8w, r8w
0x180007906  jz      short loc_18000791D
0x180007908  mov     [rax], r8w
0x18000790c  add     rdx, 2
0x180007910  add     rax, 2
0x180007914  dec     rcx
0x180007917  sub     rbx, 1
0x18000791b  jnz     short loc_1800078F9
0x18000791d  test    rbx, rbx
0x180007920  lea     rcx, [rax-2]
0x180007924  cmovnz  rcx, rax
0x180007928  mov     [rcx], si
0x18000792b  jz      loc_180007BBD
0x180007931  lea     rcx, [rbp+720h+var_460]
0x180007938  call    cs:__imp_pSetupGetFileTitle
0x18000793e  mov     rdx, rax
0x180007941  lea     rax, [rbp+720h+var_460]
0x180007948  cmp     rdx, rax
0x18000794b  jz      loc_180007BBD
0x180007951  lea     rcx, [rdx-2]
0x180007955  cmp     word ptr [rcx], 5Ch ; '\'
0x180007959  jz      short loc_180007965
0x18000795b  cmp     word ptr [rcx], 2Fh ; '/'
0x18000795f  jnz     loc_180007BBD
0x180007965  lea     r8, [rbp+720h+var_460]
0x18000796c  mov     rax, rcx
0x18000796f  sub     rax, r8
0x180007972  cmp     rax, 4
0x180007976  jnz     short loc_180007990
0x180007978  cmp     [rbp+720h+var_460], si
0x18000797f  jz      short loc_180007990
0x180007981  cmp     [rbp+720h+var_45E], 3Ah ; ':'
0x180007989  jnz     short loc_180007990
0x18000798b  mov     [rdx], si
0x18000798e  jmp     short loc_180007993
0x180007990  mov     [rcx], si
0x180007993  mov     edx, [r14+8Ch]
0x18000799a  lea     r8, [rsp+820h+var_7C0]
0x18000799f  mov     rcx, [r15+70h]
0x1800079a3  mov     r9d, 0A0h
0x1800079a9  call    cs:__imp_pSetupStringTableGetExtraData
0x1800079af  test    eax, eax
0x1800079b1  jz      short loc_1800079C9
0x1800079b3  mov     edx, [r14+8Ch]
0x1800079ba  mov     rcx, [r15+70h]
0x1800079be  call    cs:__imp_pSetupStringTableStringFromId
0x1800079c4  mov     rdx, rax
0x1800079c7  jmp     short loc_1800079CC
0x1800079c9  mov     rdx, rsi
0x1800079cc  cmp     [r14+18h], esi
0x1800079d0  jnz     loc_180007A5C
0x1800079d6  cmp     [r14+84h], esi
0x1800079dd  jz      short loc_1800079F3
0x1800079df  cmp     [r14+88h], esi
0x1800079e6  jnz     short loc_1800079F3
0x1800079e8  mov     dword ptr [r14+88h], 7
0x1800079f3  movsxd  rcx, dword ptr [r14+88h]
0x1800079fa  cmp     ecx, 8
0x1800079fd  ja      loc_180007BBD
0x180007a03  test    rdx, rdx
0x180007a06  lea     r8, cs:180000000h
0x180007a0d  mov     rcx, ds:rva off_18000B210[r8+rcx*8]; "NONE" ...
0x180007a15  lea     rax, aNone; "NONE"
0x180007a1c  cmovnz  rax, rdx
0x180007a20  mov     [rsp+820h+var_7E8], rcx
0x180007a25  movsxd  rdx, dword ptr [r14]
0x180007a28  lea     r9, aInfWsSourceWsI_0; "INF %ws (source = %ws) is superseded by"...
0x180007a2f  mov     [rsp+820h+var_7F0], rax
0x180007a34  mov     rax, [r15+28h]
0x180007a38  mov     rcx, ds:rva off_18000B260[r8+rdx*8]; "UNKNOWN" ...
0x180007a40  xor     r8d, r8d
0x180007a43  mov     [rsp+820h+var_7F8], rcx
0x180007a48  mov     rcx, [r15+30h]
0x180007a4c  mov     [rsp+820h+var_800], r13
0x180007a51  lea     edx, [r8+4]
0x180007a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a5a  jmp     short loc_180007AAA
0x180007a5c  movsxd  rdx, dword ptr [r14]
0x180007a5f  lea     r8, cs:180000000h
0x180007a66  mov     rcx, cs:off_18000B250; "NOT INSTALLED"
0x180007a6d  lea     r9, aInfWsSourceWsI; "INF %ws (source = %ws) is primitive, re"...
0x180007a74  mov     [rsp+820h+var_7F0], rcx
0x180007a79  mov     dword ptr [r14+88h], 8
0x180007a84  mov     rcx, ds:rva off_18000B260[r8+rdx*8]; "UNKNOWN" ...
0x180007a8c  xor     r8d, r8d
0x180007a8f  mov     rax, [r15+28h]
0x180007a93  mov     [rsp+820h+var_7F8], rcx
0x180007a98  mov     rcx, [r15+30h]
0x180007a9c  lea     edx, [r8+4]
0x180007aa0  mov     [rsp+820h+var_800], r13
0x180007aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aaa  mov     edx, [r15+60h]
0x180007aae  lea     r8, [rsp+820h+var_7D0]
0x180007ab3  lea     rcx, [rbp+720h+var_460]
0x180007aba  call    pUtilGetDirectorySize
0x180007abf  mov     rdx, [rsp+820h+var_7D0]
0x180007ac4  lea     rbx, aWill; "will"
0x180007acb  mov     rdi, [r15+30h]
0x180007acf  lea     rcx, [rbp+720h+var_460]
0x180007ad6  test    eax, eax
0x180007ad8  lea     rax, aMay; "may"
0x180007adf  cmovnz  rdx, rsi
0x180007ae3  cmp     [r15+38h], esi
0x180007ae7  mov     rsi, [r15+28h]
0x180007aeb  cmovz   rbx, rax
0x180007aef  mov     [rsp+820h+var_7D0], rdx
0x180007af4  call    cs:__imp_pSetupGetFileTitle
0x180007afa  xor     r8d, r8d
0x180007afd  mov     [rsp+820h+var_7F0], rbx
0x180007b02  mov     [rsp+820h+var_7F8], rax
0x180007b07  lea     r9, aInfWsWsWsBeRem; "INF %ws (%ws) %ws be removed."
0x180007b0e  mov     rcx, rdi
0x180007b11  mov     [rsp+820h+var_800], r13
0x180007b16  mov     rax, rsi
0x180007b19  lea     edx, [r8+3]
0x180007b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b22  xor     esi, esi
0x180007b24  cmp     [r15+38h], esi
0x180007b28  jz      short loc_180007B91
0x180007b2a  mov     r8, r14
0x180007b2d  mov     rcx, r15
0x180007b30  call    LogInfInfo
0x180007b35  xor     r8d, r8d; Reserved
0x180007b38  xor     edx, edx; Flags
0x180007b3a  mov     rcx, r13; InfFileName
0x180007b3d  mov     ebx, esi
0x180007b3f  call    cs:__imp_SetupUninstallOEMInfW
0x180007b45  test    eax, eax
0x180007b47  jnz     short loc_180007B51
0x180007b49  call    cs:__imp_GetLastError
0x180007b4f  mov     ebx, eax
0x180007b51  mov     rcx, [r15+30h]
0x180007b55  xor     r8d, r8d
0x180007b58  mov     rax, [r15+28h]
0x180007b5c  test    ebx, ebx
0x180007b5e  jz      short loc_180007B7B
0x180007b60  mov     dword ptr [rsp+820h+var_7F8], ebx
0x180007b64  lea     r9, aFailedToRemove; "Failed to remove INF %ws, Err = 0x%lx"
0x180007b6b  lea     edx, [r8+1]
  ... truncated ...
```
