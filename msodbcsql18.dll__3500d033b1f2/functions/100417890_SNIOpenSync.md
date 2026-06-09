# SNIOpenSync

- ea: `0x100417890`
- end: `0x100418053`
- name: `SNIOpenSync`
- size: `1987`
- prototype: `__int64 __usercall@<rax>(struct Sni_Consumer_Info *@<rcx>, LPCWSTR lpSrcStr@<rdx>, struct SNI_Conn *@<r8>, int, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x100417864`
- `0x10043c498`

## callees

- `0x1004134ac`
- `0x100413898`
- `0x100414210`
- `0x1004158c0`
- `0x1004160e4`
- `0x100417890`
- `0x100418c84`
- `0x10041915c`
- `0x100419dc8`
- `0x10041d12c`
- `0x100422150`
- `0x100435720`
- `0x1004381cc`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548210`
- `0x1005494b8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x100417929`
- `KERNEL32!GetTickCount` at `0x100417df4`
- `KERNEL32!GetTickCount` at `0x100417929`
- `KERNEL32!GetTickCount` at `0x100417df4`

## pseudocode

```c
__int64 __fastcall SNIOpenSync(
        struct Sni_Consumer_Info *a1,
        wchar_t *lpSrcStr,
        struct SNI_Conn *a3,
        struct SNI_Conn **a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8)
{
  unsigned int v8; // r14d
  unsigned int v10; // ebx
  __int64 v13; // rax
  unsigned int ProtElem; // edi
  unsigned int v15; // r14d
  wchar_t *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // esi
  unsigned int v20; // ecx
  unsigned int v21; // edx
  unsigned int v22; // ecx
  __int64 *v23; // rax
  struct SNI_Conn *v24; // rcx
  int v25; // esi
  int v26; // esi
  int v27; // esi
  DWORD v28; // ecx
  __int64 v29; // r8
  __int64 v30; // r9
  struct SNI_Conn *v31; // rdx
  __int64 v32; // rcx
  struct SNI_Conn **v33; // rsi
  unsigned int v35[2]; // [rsp+28h] [rbp-69h]
  int v36; // [rsp+30h] [rbp-61h]
  int v37; // [rsp+38h] [rbp-59h]
  struct SNI_Conn *v38; // [rsp+40h] [rbp-51h] BYREF
  struct ProtElem *v39; // [rsp+48h] [rbp-49h] BYREF
  struct SNI_Provider *v40; // [rsp+50h] [rbp-41h] BYREF
  DWORD TickCount; // [rsp+58h] [rbp-39h]
  struct SNI_Conn **v42; // [rsp+60h] [rbp-31h]
  __int64 v43; // [rsp+68h] [rbp-29h] BYREF
  __int128 v44; // [rsp+70h] [rbp-21h] BYREF

  v8 = a6;
  v42 = a4;
  v10 = 0;
  v43 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7770[0] )
  {
    v37 = a6;
    v36 = a5;
    *(_QWORD *)v35 = a4;
    bidScopeEnterW(&v43, off_1005E7770[0], a1);
  }
  v39 = 0;
  v38 = 0;
  v40 = 0;
  TickCount = GetTickCount();
  if ( !lpSrcStr )
  {
    if ( !a3 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E4608[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, _QWORD, int, int))off_1005D39E0)(
          bidID,
          0,
          1435648,
          off_1005E4608[0],
          0,
          *(_QWORD *)v35,
          v36,
          v37);
      ProtElem = 87;
      if ( (bidGblFlags & 2) != 0 && off_1005E4610[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 1437696, off_1005E4610[0], 9);
      }
      SNISetLastError(9, 87, 50100);
      goto LABEL_85;
    }
    goto LABEL_28;
  }
  v13 = -1;
  do
    ++v13;
  while ( lpSrcStr[v13] );
  ProtElem = StrTrimBothW_Sys(lpSrcStr, 3);
  if ( ProtElem )
  {
    v15 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_1005E4600[0] )
      goto LABEL_12;
    SniErrorIdFromStringId(0xC3B4u);
    v16 = off_1005E4600[0];
    v17 = 1424384;
LABEL_11:
    bidTraceW(0, v17, v16, 9);
LABEL_12:
    v18 = ProtElem;
LABEL_13:
    SNISetLastError(9, v18, v15);
    goto LABEL_84;
  }
  if ( !wcscmp_0(L"session:", lpSrcStr) )
  {
    v19 = 2;
    goto LABEL_29;
  }
  if ( a3 )
  {
LABEL_28:
    v39 = a3;
    v19 = *(_DWORD *)a3;
    goto LABEL_29;
  }
  ProtElem = ProtElem::MakeProtElem(lpSrcStr, &v39);
  if ( ProtElem )
    goto LABEL_85;
  v19 = *(_DWORD *)v39;
LABEL_29:
  ProtElem = SNI_Conn::InitObject(&v38);
  if ( ProtElem )
    goto LABEL_84;
  *((_BYTE *)v38 + 236) = *((_BYTE *)v38 + 236) & 0xFE | (a5 != 0);
  if ( v19 != 2 )
  {
    ProtElem = SNI_Conn::SetServerName(
                 v38,
                 (unsigned __int16 *)v39 + 4,
                 (unsigned __int16 *)v39 + 260,
                 (unsigned __int16 *)v39 + 516);
    if ( ProtElem )
      goto LABEL_84;
  }
  SNISetInfo(v38, 1, a1);
  if ( v19 == 2 )
  {
    *((_DWORD *)v38 + 52) = *((_DWORD *)a3 + 52);
    *((_DWORD *)v38 + 53) = *((_DWORD *)a3 + 53);
    *((_DWORD *)v38 + 54) = *((_DWORD *)a3 + 54);
    *((_DWORD *)v38 + 55) = *((_DWORD *)a3 + 55);
    *(_DWORD *)(*((_QWORD *)v38 + 30) + 20LL) = *(_DWORD *)(*((_QWORD *)a3 + 30) + 20LL);
    *((_DWORD *)v38 + 58) = *((_DWORD *)a3 + 58);
    v44 = *(_OWORD *)((char *)a3 + 4);
    SNISetInfo(v38, 10, &v44);
  }
  else
  {
    IncrementConnBufSize(v38, (struct SNI_PROVIDER_INFO *)((char *)&rgProvInfo + 20 * v19));
    v20 = *((_DWORD *)v38 + 52);
    v21 = v20 + *((_DWORD *)v38 + 53);
    if ( v21 < v20 || v21 > 0x183E8 )
    {
      ProtElem = -2147024362;
      goto LABEL_84;
    }
    v22 = 0;
    v23 = qword_100559528;
    while ( v21 > *(_DWORD *)v23 )
    {
      ++v22;
      v23 = (__int64 *)((char *)v23 + 4);
      if ( v22 > 7 )
      {
        v22 = 7;
        break;
      }
    }
    *((_DWORD *)v38 + 58) = v22;
  }
  SNISetInfo(v38, 2, *((_QWORD *)a1 + 1));
  v24 = v38;
  *((_DWORD *)v38 + 22) = *(_DWORD *)a1;
  *((_QWORD *)v24 + 12) = *((_QWORD *)a1 + 1);
  *((_QWORD *)v24 + 13) = *((_QWORD *)a1 + 2);
  *((_QWORD *)v24 + 14) = *((_QWORD *)a1 + 3);
  *((_QWORD *)v24 + 18) = *((_QWORD *)a1 + 7);
  *((_QWORD *)v24 + 15) = *((_QWORD *)a1 + 4);
  *((_QWORD *)v24 + 16) = *((_QWORD *)a1 + 5);
  *((_QWORD *)v24 + 17) = *((_QWORD *)a1 + 6);
  *((_BYTE *)v24 + 172) = *((_BYTE *)a1 + 84);
  *((_DWORD *)v24 + 44) = *((_DWORD *)a1 + 22);
  *((_DWORD *)v24 + 45) = *((_DWORD *)a1 + 23);
  *((_DWORD *)v24 + 46) = *((_DWORD *)a1 + 24);
  *((_DWORD *)v24 + 47) = *((_DWORD *)a1 + 25);
  *((_DWORD *)v24 + 42) = *((_DWORD *)a1 + 20);
  *((_QWORD *)v24 + 20) = *((_QWORD *)a1 + 9);
  if ( g_fSandbox && v19 == 4 )
  {
    ProtElem = 50;
    v15 = 50108;
    if ( (bidGblFlags & 2) == 0 || !off_1005E4618[0] )
      goto LABEL_12;
    SniErrorIdFromStringId(0xC3BCu);
    v16 = off_1005E4618[0];
    v17 = 1564672;
    goto LABEL_11;
  }
  v25 = v19 - 1;
  if ( v25 )
  {
    v26 = v25 - 1;
    if ( v26 )
    {
      v27 = v26 - 2;
      if ( v27 )
      {
        if ( v27 != 3 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1005E4628[0] && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, _QWORD, int, int))off_1005D39E0)(
              bidID,
              0,
              1658880,
              off_1005E4628[0],
              0,
              *(_QWORD *)v35,
              v36,
              v37);
          ProtElem = 87;
          v15 = 50100;
          if ( (bidGblFlags & 2) != 0 && off_1005E4630[0] )
          {
            SniErrorIdFromStringId(0xC3B4u);
            bidTraceW(0, 1660928, off_1005E4630[0], 9);
          }
          v18 = 87;
          goto LABEL_13;
        }
        if ( a6 != -1 )
        {
          v8 = -2;
          v28 = a6 + TickCount - GetTickCount();
          if ( v28 != -1 )
            v8 = v28;
          if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4620[0] )
            bidTraceW(0, 1598464, off_1005E4620[0], v8);
        }
        ProtElem = Tcp::Open(v38, v39, &v40, v8, a7, a8);
        if ( ProtElem )
          goto LABEL_84;
        *((_DWORD *)v38 + 55) = 7;
      }
      else
      {
        SNI_Conn::Release(v38, 0);
        v38 = 0;
        ProtElem = Sm::OpenWithFallback(a1, &v38, v39, &v40, a5);
        if ( ProtElem )
          goto LABEL_84;
        *((_DWORD *)v38 + 55) = 4;
      }
    }
    else
    {
      ProtElem = Smux::Open(v38, a3, &v40);
      if ( ProtElem )
        goto LABEL_84;
    }
  }
  else
  {
    ProtElem = Np::Open(v38, v39, &v40);
    if ( ProtElem )
      goto LABEL_84;
    *((_DWORD *)v38 + 55) = 1;
  }
  *((_QWORD *)v38 + 10) = v40;
  v31 = v38;
  if ( (*((_BYTE *)v38 + 236) & 1) != 0 )
    goto LABEL_77;
  v32 = *((_QWORD *)v40 + 2);
  if ( v32 == -1 || *((_QWORD *)v38 + 40) )
    goto LABEL_77;
  ProtElem = SNIRegisterWithIOCQ(v32, v38, v29, v30);
  if ( ProtElem )
  {
LABEL_84:
    if ( a3 )
    {
LABEL_87:
      if ( v38 )
        SNI_Conn::Release(v38, 0);
      *v42 = 0;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4640[0] )
        bidTraceW(0, 1709056, off_1005E4640[0], ProtElem);
      v10 = ProtElem;
      goto LABEL_93;
    }
LABEL_85:
    if ( v39 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
    goto LABEL_87;
  }
  v31 = v38;
LABEL_77:
  v33 = v42;
  *v42 = v31;
  if ( !a3 && v39 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4638[0] )
    bidTraceW(0, 1690624, off_1005E4638[0], *v33);
LABEL_93:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v43);
  return v10;
}

```

## disassembly

```asm
0x100417890  push    rbp
0x100417892  push    rbx
0x100417893  push    rsi
0x100417894  push    rdi
0x100417895  push    r12
0x100417897  push    r13
0x100417899  push    r14
0x10041789b  push    r15
0x10041789d  lea     rbp, [rsp-7]
0x1004178a2  sub     rsp, 98h
0x1004178a9  mov     rax, cs:__security_cookie
0x1004178b0  xor     rax, rsp
0x1004178b3  mov     [rbp+3Fh+var_50], rax
0x1004178b7  mov     eax, cs:_bidGblFlags
0x1004178bd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1004178c1  mov     r14d, [rbp+3Fh+arg_28]
0x1004178c5  mov     r12, rcx
0x1004178c8  mov     r13d, [rbp+3Fh+arg_20]
0x1004178cc  mov     ecx, 20004h
0x1004178d1  and     eax, ecx
0x1004178d3  mov     [rbp+3Fh+var_70], r9
0x1004178d7  xor     ebx, ebx
0x1004178d9  mov     [rbp+3Fh+var_68], rdi
0x1004178dd  mov     r15, r8
0x1004178e0  mov     rsi, rdx
0x1004178e3  cmp     eax, ecx
0x1004178e5  jnz     short loc_10041791D
0x1004178e7  mov     rax, cs:off_1005E7770; "<SNIOpenSync|API|SNI> pConsumerInfo: %p"...
0x1004178ee  test    rax, rax
0x1004178f1  jz      short loc_10041791D
0x1004178f3  mov     [rsp+0D0h+var_98], r14d
0x1004178f8  lea     rcx, [rbp+3Fh+var_68]
0x1004178fc  mov     [rsp+0D0h+var_A0], r13d
0x100417901  mov     qword ptr [rsp+0D0h+var_A8], r9
0x100417906  mov     r9, rdx
0x100417909  mov     rdx, cs:off_1005E7770; "<SNIOpenSync|API|SNI> pConsumerInfo: %p"...
0x100417910  mov     qword ptr [rsp+0D0h+var_B0], r8
0x100417915  mov     r8, r12
0x100417918  call    _bidScopeEnterW
0x10041791d  mov     [rbp+3Fh+var_88], rbx
0x100417921  mov     [rbp+3Fh+var_90], rbx
0x100417925  mov     [rbp+3Fh+var_80], rbx
0x100417929  call    cs:__imp_GetTickCount
0x10041792f  mov     [rbp+3Fh+var_78], eax
0x100417932  test    rsi, rsi
0x100417935  jz      loc_100417A06
0x10041793b  mov     rax, rdi
0x10041793e  inc     rax
0x100417941  cmp     [rsi+rax*2], bx
0x100417945  jnz     short loc_10041793E
0x100417947  lea     edx, [rax+1]
0x10041794a  mov     [rsp+0D0h+var_B0], 3; int
0x100417952  lea     r9, sz; " \t"
0x100417959  xor     r8d, r8d
0x10041795c  mov     rcx, rsi; S2
0x10041795f  call    StrTrimBothW_Sys
0x100417964  mov     edi, eax
0x100417966  test    eax, eax
0x100417968  jz      short loc_1004179C1
0x10041796a  test    byte ptr cs:_bidGblFlags, 2
0x100417971  mov     esi, 9
0x100417976  mov     r14d, 0C3B4h
0x10041797c  jz      short loc_1004179B0
0x10041797e  mov     rax, cs:off_1005E4600; "<SNIOpenSync|ERR|SNI> ProviderNum: %d{P"...
0x100417985  test    rax, rax
0x100417988  jz      short loc_1004179B0
0x10041798a  mov     ecx, r14d; unsigned int
0x10041798d  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100417992  mov     r8, cs:off_1005E4600; "<SNIOpenSync|ERR|SNI> ProviderNum: %d{P"...
0x100417999  mov     edx, 15BC00h
0x10041799e  mov     [rsp+0D0h+var_A8], edi
0x1004179a2  mov     r9d, esi
0x1004179a5  xor     ecx, ecx
0x1004179a7  mov     [rsp+0D0h+var_B0], eax
0x1004179ab  call    _bidTraceW
0x1004179b0  mov     edx, edi
0x1004179b2  mov     r8d, r14d
0x1004179b5  mov     ecx, esi
0x1004179b7  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004179bc  jmp     loc_100417FB6
0x1004179c1  mov     rdx, rsi; String2
0x1004179c4  lea     rcx, aSession; "session:"
0x1004179cb  call    wcscmp_0
0x1004179d0  test    eax, eax
0x1004179d2  jnz     short loc_1004179DC
0x1004179d4  lea     esi, [rax+2]
0x1004179d7  jmp     loc_100417ABE
0x1004179dc  test    r15, r15
0x1004179df  jnz     loc_100417AB7
0x1004179e5  lea     rdx, [rbp+3Fh+var_88]; struct ProtElem **
0x1004179e9  mov     rcx, rsi; lpSrcStr
0x1004179ec  call    ?MakeProtElem@ProtElem@@SAKPEAGPEAPEAV1@@Z; ProtElem::MakeProtElem(ushort *,ProtElem * *)
0x1004179f1  mov     edi, eax
0x1004179f3  test    eax, eax
0x1004179f5  jnz     loc_100417FBB
0x1004179fb  mov     rax, [rbp+3Fh+var_88]
0x1004179ff  mov     esi, [rax]
0x100417a01  jmp     loc_100417ABE
0x100417a06  test    r15, r15
0x100417a09  jnz     loc_100417AB7
0x100417a0f  test    byte ptr cs:_bidGblFlags, 2
0x100417a16  jz      short loc_100417A55
0x100417a18  mov     rax, cs:off_1005E4608; "<SNIOpenSync|ERR|SNI> pOpenInfo is NULL"...
0x100417a1f  test    rax, rax
0x100417a22  jz      short loc_100417A55
0x100417a24  cmp     cs:_bidID, rdi
0x100417a2b  jz      short loc_100417A55
0x100417a2d  mov     r9, cs:off_1005E4608; "<SNIOpenSync|ERR|SNI> pOpenInfo is NULL"...
0x100417a34  xor     edx, edx
0x100417a36  mov     rcx, cs:_bidID
0x100417a3d  mov     r8d, 15E800h
0x100417a43  mov     rax, cs:off_1005D39E0
0x100417a4a  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x100417a4f  call    cs:__guard_dispatch_icall_fptr
0x100417a55  test    byte ptr cs:_bidGblFlags, 2
0x100417a5c  mov     r12d, 57h ; 'W'
0x100417a62  mov     edi, r12d
0x100417a65  mov     r14d, 0C3B4h
0x100417a6b  lea     esi, [r12-4Eh]
0x100417a70  jz      short loc_100417AA5
0x100417a72  mov     rax, cs:off_1005E4610; "<SNIOpenSync|ERR|SNI> ProviderNum: %d{P"...
0x100417a79  test    rax, rax
0x100417a7c  jz      short loc_100417AA5
0x100417a7e  mov     ecx, r14d; unsigned int
0x100417a81  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100417a86  mov     r8, cs:off_1005E4610; "<SNIOpenSync|ERR|SNI> ProviderNum: %d{P"...
0x100417a8d  mov     r9d, esi
0x100417a90  mov     edx, 15F000h
0x100417a95  mov     [rsp+0D0h+var_A8], r12d
0x100417a9a  xor     ecx, ecx
0x100417a9c  mov     [rsp+0D0h+var_B0], eax
0x100417aa0  call    _bidTraceW
0x100417aa5  mov     r8d, r14d
0x100417aa8  mov     edx, r12d
0x100417aab  mov     ecx, esi
0x100417aad  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100417ab2  jmp     loc_100417FBB
0x100417ab7  mov     [rbp+3Fh+var_88], r15
0x100417abb  mov     esi, [r15]
0x100417abe  xor     edx, edx; int
0x100417ac0  lea     rcx, [rbp+3Fh+var_90]; struct SNI_Conn **
0x100417ac4  call    ?InitObject@SNI_Conn@@SAKPEAPEAV1@H@Z; SNI_Conn::InitObject(SNI_Conn * *,int)
0x100417ac9  mov     edi, eax
0x100417acb  test    eax, eax
0x100417acd  jnz     loc_100417FB6
0x100417ad3  mov     rdx, [rbp+3Fh+var_90]
0x100417ad7  test    r13d, r13d
0x100417ada  setnz   cl
0x100417add  mov     al, [rdx+0ECh]
0x100417ae3  and     al, 0FEh
0x100417ae5  or      cl, al
0x100417ae7  mov     [rdx+0ECh], cl
0x100417aed  cmp     esi, 2
0x100417af0  jz      short loc_100417B1B
0x100417af2  mov     rdx, [rbp+3Fh+var_88]
0x100417af6  mov     rcx, [rbp+3Fh+var_90]; this
0x100417afa  lea     r9, [rdx+408h]; unsigned __int16 *
0x100417b01  lea     r8, [rdx+208h]; unsigned __int16 *
0x100417b08  add     rdx, 8; unsigned __int16 *
0x100417b0c  call    ?SetServerName@SNI_Conn@@QEAAKPEAG00@Z; SNI_Conn::SetServerName(ushort *,ushort *,ushort *)
0x100417b11  mov     edi, eax
0x100417b13  test    eax, eax
0x100417b15  jnz     loc_100417FB6
0x100417b1b  mov     rcx, [rbp+3Fh+var_90]
0x100417b1f  mov     r8, r12
0x100417b22  mov     edx, 1
0x100417b27  call    SNISetInfo
0x100417b2c  cmp     esi, 2
0x100417b2f  jnz     loc_100417BBE
0x100417b35  mov     ecx, [r15+0D0h]
0x100417b3c  lea     r8, [rbp+3Fh+var_60]
0x100417b40  mov     rax, [rbp+3Fh+var_90]
0x100417b44  mov     [rax+0D0h], ecx
0x100417b4a  mov     ecx, [r15+0D4h]
0x100417b51  mov     rax, [rbp+3Fh+var_90]
0x100417b55  mov     [rax+0D4h], ecx
0x100417b5b  mov     ecx, [r15+0D8h]
0x100417b62  mov     rax, [rbp+3Fh+var_90]
0x100417b66  mov     [rax+0D8h], ecx
0x100417b6c  mov     rax, [rbp+3Fh+var_90]
0x100417b70  mov     ecx, [r15+0DCh]
0x100417b77  mov     [rax+0DCh], ecx
0x100417b7d  mov     rax, [rbp+3Fh+var_90]
0x100417b81  mov     rdx, [r15+0F0h]
0x100417b88  mov     rcx, [rax+0F0h]
0x100417b8f  mov     eax, [rdx+14h]
0x100417b92  lea     edx, [rsi+8]
0x100417b95  mov     [rcx+14h], eax
0x100417b98  mov     ecx, [r15+0E8h]
0x100417b9f  mov     rax, [rbp+3Fh+var_90]
0x100417ba3  mov     [rax+0E8h], ecx
0x100417ba9  movups  xmm0, xmmword ptr [r15+4]
0x100417bae  mov     rcx, [rbp+3Fh+var_90]
0x100417bb2  movdqu  [rbp+3Fh+var_60], xmm0
0x100417bb7  call    SNISetInfo
0x100417bbc  jmp     short loc_100417C26
0x100417bbe  movsxd  rax, esi
0x100417bc1  lea     rcx, [rax+rax*4]
0x100417bc5  lea     rax, ?rgProvInfo@@3PAUSNI_PROVIDER_INFO@@A; SNI_PROVIDER_INFO near * rgProvInfo
0x100417bcc  lea     rdx, [rax+rcx*4]; struct SNI_PROVIDER_INFO *
0x100417bd0  mov     rcx, [rbp+3Fh+var_90]; struct SNI_Conn *
0x100417bd4  call    ?IncrementConnBufSize@@YAXPEAVSNI_Conn@@PEAUSNI_PROVIDER_INFO@@@Z; IncrementConnBufSize(SNI_Conn *,SNI_PROVIDER_INFO *)
0x100417bd9  mov     rax, [rbp+3Fh+var_90]
0x100417bdd  mov     ecx, [rax+0D0h]
0x100417be3  mov     edx, [rax+0D4h]
0x100417be9  add     edx, ecx
0x100417beb  cmp     edx, ecx
0x100417bed  jb      loc_100417FB1
0x100417bf3  cmp     edx, 183E8h
0x100417bf9  ja      loc_100417FB1
0x100417bff  mov     ecx, ebx
0x100417c01  lea     rax, qword_100559528
0x100417c08  cmp     edx, [rax]
0x100417c0a  jbe     short loc_100417C1C
0x100417c0c  inc     ecx
0x100417c0e  add     rax, 4
0x100417c12  cmp     ecx, 7
0x100417c15  jbe     short loc_100417C08
0x100417c17  mov     ecx, 7
0x100417c1c  mov     rax, [rbp+3Fh+var_90]
0x100417c20  mov     [rax+0E8h], ecx
0x100417c26  mov     r8, [r12+8]
0x100417c2b  mov     edx, 2
0x100417c30  mov     rcx, [rbp+3Fh+var_90]
0x100417c34  call    SNISetInfo
0x100417c39  mov     eax, [r12]
0x100417c3d  mov     rcx, [rbp+3Fh+var_90]
0x100417c41  mov     [rcx+58h], eax
0x100417c44  mov     rax, [r12+8]
0x100417c49  mov     [rcx+60h], rax
0x100417c4d  mov     rax, [r12+10h]
0x100417c52  mov     [rcx+68h], rax
0x100417c56  mov     rax, [r12+18h]
0x100417c5b  mov     [rcx+70h], rax
0x100417c5f  mov     rax, [r12+38h]
0x100417c64  mov     [rcx+90h], rax
0x100417c6b  mov     rax, [r12+20h]
0x100417c70  mov     [rcx+78h], rax
0x100417c74  mov     rax, [r12+28h]
0x100417c79  mov     [rcx+80h], rax
0x100417c80  mov     rax, [r12+30h]
0x100417c85  mov     [rcx+88h], rax
0x100417c8c  mov     al, [r12+54h]
0x100417c91  mov     [rcx+0ACh], al
0x100417c97  mov     eax, [r12+58h]
0x100417c9c  mov     [rcx+0B0h], eax
0x100417ca2  mov     eax, [r12+5Ch]
0x100417ca7  mov     [rcx+0B4h], eax
0x100417cad  mov     eax, [r12+60h]
0x100417cb2  mov     [rcx+0B8h], eax
0x100417cb8  mov     eax, [r12+64h]
0x100417cbd  mov     [rcx+0BCh], eax
0x100417cc3  mov     eax, [r12+50h]
0x100417cc8  mov     [rcx+0A8h], eax
0x100417cce  mov     rax, [r12+48h]
0x100417cd3  mov     [rcx+0A0h], rax
0x100417cda  cmp     cs:?g_fSandbox@@3HA, ebx; int g_fSandbox
0x100417ce0  jz      short loc_100417D29
0x100417ce2  cmp     esi, 4
0x100417ce5  jnz     short loc_100417D29
0x100417ce7  test    byte ptr cs:_bidGblFlags, 2
0x100417cee  lea     edi, [rsi+2Eh]
0x100417cf1  lea     esi, [rdi-29h]
0x100417cf4  mov     r14d, 0C3BCh
0x100417cfa  jz      loc_1004179B0
0x100417d00  mov     rax, cs:off_1005E4618; "<SNIOpenSync|ERR|SNI> ProviderNum: %d{P"...
0x100417d07  test    rax, rax
0x100417d0a  jz      loc_1004179B0
0x100417d10  mov     ecx, r14d; unsigned int
0x100417d13  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100417d18  mov     r8, cs:off_1005E4618; "<SNIOpenSync|ERR|SNI> ProviderNum: %d{P"...
0x100417d1f  mov     edx, 17E000h
0x100417d24  jmp     loc_10041799E
0x100417d29  sub     esi, 1
0x100417d2c  jz      loc_100417EE2
0x100417d32  sub     esi, 1
0x100417d35  jz      loc_100417EC6
0x100417d3b  sub     esi, 2
0x100417d3e  jz      loc_100417E84
0x100417d44  cmp     esi, 3
0x100417d47  jz      loc_100417DEC
0x100417d4d  test    byte ptr cs:_bidGblFlags, 2
0x100417d54  jz      short loc_100417D94
0x100417d56  mov     rax, cs:off_1005E4628; "<SNIOpenSync|ERR|SNI> ProvNum is unknow"...
0x100417d5d  test    rax, rax
0x100417d60  jz      short loc_100417D94
0x100417d62  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100417d6a  jz      short loc_100417D94
0x100417d6c  mov     r9, cs:off_1005E4628; "<SNIOpenSync|ERR|SNI> ProvNum is unknow"...
0x100417d73  xor     edx, edx
0x100417d75  mov     rcx, cs:_bidID
0x100417d7c  mov     r8d, 195000h
0x100417d82  mov     rax, cs:off_1005D39E0
0x100417d89  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x100417d8e  call    cs:__guard_dispatch_icall_fptr
0x100417d94  test    byte ptr cs:_bidGblFlags, 2
0x100417d9b  mov     r12d, 57h ; 'W'
0x100417da1  mov     edi, r12d
0x100417da4  mov     r14d, 0C3B4h
0x100417daa  lea     esi, [r12-4Eh]
  ... truncated ...
```
