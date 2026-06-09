# CPspStatusMonitorGen::UpdatePageConnectionStatus(tagSTATMON_ENGINEDATA const *,tagSTATMON_ENGINEDATA const *)

- ea: `0x180007780`
- end: `0x180007ac8`
- name: `?UpdatePageConnectionStatus@CPspStatusMonitorGen@@IEAAXPEBUtagSTATMON_ENGINEDATA@@0@Z`
- size: `840`
- prototype: `void __fastcall(CPspStatusMonitorGen *__hidden this, const struct tagSTATMON_ENGINEDATA *, const struct tagSTATMON_ENGINEDATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18005ae60`

## callees

- `0x180007780`
- `0x18000a730`
- `0x18001e1e0`
- `0x18001eb7c`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x1800078f1`
- `USER32!SetDlgItemTextW` at `0x180007a60`
- `USER32!SetDlgItemTextW` at `0x1800078f1`
- `USER32!SetDlgItemTextW` at `0x180007a60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800078a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800078a9`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180007898`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180007898`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800078b7`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800078b7`
- `wlanapi!WlanHostedNetworkQueryProperty` at `0x180007997`
- `wlanapi!WlanHostedNetworkQueryProperty` at `0x180007997`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x1800079e9`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180007a30`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x1800079e9`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180007a30`
- `wlanapi!WlanFreeMemory` at `0x180007a0b`
- `wlanapi!WlanFreeMemory` at `0x180007a0b`

## pseudocode

```c
void __fastcall CPspStatusMonitorGen::UpdatePageConnectionStatus(
        CPspStatusMonitorGen *this,
        const struct tagSTATMON_ENGINEDATA *a2,
        const struct tagSTATMON_ENGINEDATA *a3)
{
  int v3; // edi
  unsigned int v4; // ebp
  __int64 v6; // r8
  int v7; // edx
  unsigned int v8; // eax
  int v9; // ecx
  HMODULE v10; // r14
  const WCHAR *v11; // rsi
  HRSRC Resource; // rax
  HGLOBAL v13; // rax
  int v14; // ebp
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  __int64 v17; // rdi
  void *v18; // rcx
  signed int v19; // eax
  signed int v20; // edi
  PVOID v21; // rsi
  int v22; // eax
  int v23; // eax
  const WCHAR *v24; // r8
  DWORD pdwDataSize; // [rsp+30h] [rbp-268h] BYREF
  int v26; // [rsp+34h] [rbp-264h] BYREF
  PVOID ppvData; // [rsp+38h] [rbp-260h] BYREF
  enum _WLAN_OPCODE_VALUE_TYPE pWlanOpcodeValueType[4]; // [rsp+40h] [rbp-258h] BYREF
  _BYTE v29[512]; // [rsp+50h] [rbp-248h] BYREF

  v3 = *((_DWORD *)a3 + 26);
  v4 = 0;
  v6 = *((_QWORD *)this + 11);
  v7 = *(_DWORD *)(v6 + 152);
  switch ( v3 )
  {
    case 0:
      v4 = 1048;
      if ( v7 != 3 )
        v4 = 1040;
      break;
    case 1:
      v4 = 1051;
      if ( v7 != 3 )
        v4 = 1041;
      break;
    case 2:
      v4 = 1050;
      if ( v7 != 3 )
        v4 = 1042;
      break;
    case 3:
      v4 = 1043;
      break;
    case 4:
      v4 = 1044;
      break;
    case 5:
      v4 = 1045;
      break;
    case 6:
      v4 = 1046;
      break;
    case 7:
      if ( v7 == 3 && (v8 = *(_DWORD *)(v6 + 156), v8 <= 9) && (v9 = 644, _bittest(&v9, v8)) )
        v4 = 1056;
      else
        v4 = 1047;
      break;
    case 8:
      v4 = 1035;
      break;
    case 10:
      v4 = 1036;
      break;
    case 12:
      v4 = 1038;
      break;
    case 13:
    case 14:
      v4 = 1181;
      break;
    case 15:
      v4 = 1040;
      break;
    default:
      break;
  }
  v10 = hInst;
  v11 = L" ";
  Resource = FindResourceExW(hInst, (LPCWSTR)6, (LPCWSTR)((v4 >> 4) + 1), 0);
  if ( Resource )
  {
    v13 = LoadResource(v10, Resource);
    if ( v13 )
    {
      v11 = (const WCHAR *)LockResource(v13);
      if ( !v11 )
        goto LABEL_31;
      v14 = v4 & 0xF;
      v15 = 0;
      do
      {
        v16 = &v11[v15];
        v15 = *v16;
        v11 = v16 + 1;
        LODWORD(v16) = v14--;
      }
      while ( (_DWORD)v16 );
      if ( !(_DWORD)v15 )
LABEL_31:
        v11 = L" ";
    }
  }
  SetDlgItemTextW(*((HWND *)this + 1), 1007, v11);
  if ( !v3 || (v17 = *((_QWORD *)this + 11), *(_DWORD *)(v17 + 156) != 2) )
  {
    v24 = &Caption;
    goto LABEL_52;
  }
  v26 = 256;
  memset_0(v29, 0, sizeof(v29));
  if ( *(_QWORD *)(v17 + 288) || (int)CWlanStatEngine::GetWlanConnectionAttributes((CWlanStatEngine *)v17) >= 0 )
  {
    v23 = WlanUtf8SsidToDisplayName(*(_QWORD *)(v17 + 288) + 520LL, 1, v29, &v26);
    v20 = v23;
    if ( v23 > 0 )
      v20 = (unsigned __int16)v23 | 0x80070000;
LABEL_49:
    if ( v20 < 0 )
      return;
    goto LABEL_50;
  }
  if ( (*(_DWORD *)(v17 + 160) & 0x10000) == 0 )
    return;
  v18 = *(void **)(v17 + 280);
  pWlanOpcodeValueType[0] = wlan_opcode_value_type_query_only;
  pdwDataSize = 0;
  ppvData = 0;
  v19 = WlanHostedNetworkQueryProperty(
          v18,
          wlan_hosted_network_opcode_connection_settings,
          &pdwDataSize,
          &ppvData,
          pWlanOpcodeValueType,
          0);
  v20 = v19;
  if ( v19 > 0 )
    v20 = (unsigned __int16)v19 | 0x80070000;
  v21 = ppvData;
  if ( v20 < 0 )
  {
LABEL_45:
    if ( v21 )
      WlanFreeMemory(v21);
    goto LABEL_49;
  }
  if ( ppvData )
  {
    if ( pdwDataSize )
    {
      memset_0(v29, 0, sizeof(v29));
      v22 = WlanUtf8SsidToDisplayName(v21, 1, v29, &v26);
      v20 = v22;
      if ( v22 > 0 )
        v20 = (unsigned __int16)v22 | 0x80070000;
      v21 = ppvData;
    }
    goto LABEL_45;
  }
LABEL_50:
  v24 = (const WCHAR *)v29;
LABEL_52:
  SetDlgItemTextW(*((HWND *)this + 1), 24018, v24);
}

```

## disassembly

```asm
0x180007780  push    rbx
0x180007782  push    rbp
0x180007783  push    rsi
0x180007784  push    rdi
0x180007785  push    r14
0x180007787  push    r15
0x180007789  sub     rsp, 268h
0x180007790  mov     rax, cs:__security_cookie
0x180007797  xor     rax, rsp
0x18000779a  mov     [rsp+298h+var_48], rax
0x1800077a2  movsxd  rdi, dword ptr [r8+68h]
0x1800077a6  xor     ebp, ebp
0x1800077a8  mov     rbx, rcx
0x1800077ab  cmp     edi, 0Fh; switch 16 cases
0x1800077ae  ja      def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x1800077b4  mov     r8, [rcx+58h]
0x1800077b8  lea     r9, __ImageBase
0x1800077bf  mov     ecx, ds:(jpt_1800077D1 - 180000000h)[r9+rdi*4]
0x1800077c7  add     rcx, r9
0x1800077ca  mov     edx, [r8+98h]
0x1800077d1  jmp     rcx; switch jump
0x1800077d3  cmp     edx, 3; jumptable 00000001800077D1 case 0
0x1800077d6  mov     ebp, 418h
0x1800077db  mov     eax, 410h
0x1800077e0  cmovnz  ebp, eax
0x1800077e3  jmp     def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x1800077e8  cmp     edx, 3; jumptable 00000001800077D1 case 1
0x1800077eb  mov     ebp, 41Bh
0x1800077f0  mov     eax, 411h
0x1800077f5  cmovnz  ebp, eax
0x1800077f8  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x1800077fa  cmp     edx, 3; jumptable 00000001800077D1 case 2
0x1800077fd  mov     ebp, 41Ah
0x180007802  mov     eax, 412h
0x180007807  cmovnz  ebp, eax
0x18000780a  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x18000780c  mov     ebp, 413h; jumptable 00000001800077D1 case 3
0x180007811  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x180007813  mov     ebp, 414h; jumptable 00000001800077D1 case 4
0x180007818  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x18000781a  mov     ebp, 415h; jumptable 00000001800077D1 case 5
0x18000781f  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x180007821  mov     ebp, 416h; jumptable 00000001800077D1 case 6
0x180007826  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x180007828  cmp     edx, 3; jumptable 00000001800077D1 case 7
0x18000782b  jnz     short loc_18000784A
0x18000782d  mov     eax, [r8+9Ch]
0x180007834  cmp     eax, 9
0x180007837  ja      short loc_18000784A
0x180007839  mov     ecx, 284h
0x18000783e  bt      ecx, eax
0x180007841  jnb     short loc_18000784A
0x180007843  mov     ebp, 420h
0x180007848  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x18000784a  mov     ebp, 417h
0x18000784f  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x180007851  mov     ebp, 40Bh; jumptable 00000001800077D1 case 8
0x180007856  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x180007858  mov     ebp, 40Ch; jumptable 00000001800077D1 case 10
0x18000785d  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x18000785f  mov     ebp, 40Eh; jumptable 00000001800077D1 case 12
0x180007864  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x180007866  mov     ebp, 49Dh; jumptable 00000001800077D1 cases 13,14
0x18000786b  jmp     short def_1800077D1; jumptable 00000001800077D1 default case, cases 9,11
0x18000786d  mov     ebp, 410h; jumptable 00000001800077D1 case 15
0x180007872  mov     r14, cs:hInst; jumptable 00000001800077D1 default case, cases 9,11
0x180007879  lea     r15, ?c_szSpace@@3QBGB; " "
0x180007880  mov     r8d, ebp
0x180007883  xor     r9d, r9d; wLanguage
0x180007886  shr     r8d, 4
0x18000788a  mov     edx, 6; lpType
0x18000788f  inc     r8d; lpName
0x180007892  mov     rcx, r14; hModule
0x180007895  mov     rsi, r15
0x180007898  call    cs:__imp_FindResourceExW
0x18000789e  test    rax, rax
0x1800078a1  jz      short loc_1800078E5
0x1800078a3  mov     rdx, rax; hResInfo
0x1800078a6  mov     rcx, r14; hModule
0x1800078a9  call    cs:__imp_LoadResource
0x1800078af  test    rax, rax
0x1800078b2  jz      short loc_1800078E5
0x1800078b4  mov     rcx, rax; hResData
0x1800078b7  call    cs:__imp_LockResource
0x1800078bd  mov     rsi, rax
0x1800078c0  test    rax, rax
0x1800078c3  jz      short loc_1800078E2
0x1800078c5  and     ebp, 0Fh
0x1800078c8  xor     ecx, ecx
0x1800078ca  lea     rax, [rsi+rcx*2]
0x1800078ce  movzx   ecx, word ptr [rsi+rcx*2]
0x1800078d2  lea     rsi, [rax+2]
0x1800078d6  mov     eax, ebp
0x1800078d8  dec     ebp
0x1800078da  test    eax, eax
0x1800078dc  jnz     short loc_1800078CA
0x1800078de  test    ecx, ecx
0x1800078e0  jnz     short loc_1800078E5
0x1800078e2  mov     rsi, r15
0x1800078e5  mov     rcx, [rbx+8]; hDlg
0x1800078e9  mov     r8, rsi; lpString
0x1800078ec  mov     edx, 3EFh; nIDDlgItem
0x1800078f1  call    cs:__imp_SetDlgItemTextW
0x1800078f7  test    edi, edi
0x1800078f9  jz      loc_180007A50
0x1800078ff  mov     rdi, [rbx+58h]
0x180007903  cmp     dword ptr [rdi+9Ch], 2
0x18000790a  jnz     loc_180007A50
0x180007910  xor     edx, edx; Val
0x180007912  mov     [rsp+298h+var_264], 100h
0x18000791a  mov     r8d, 200h; Size
0x180007920  lea     rcx, [rsp+298h+var_248]; void *
0x180007925  call    memset_0
0x18000792a  cmp     qword ptr [rdi+120h], 0
0x180007932  jnz     loc_180007A13
0x180007938  mov     rcx, rdi; this
0x18000793b  call    ?GetWlanConnectionAttributes@CWlanStatEngine@@IEAAJXZ; CWlanStatEngine::GetWlanConnectionAttributes(void)
0x180007940  test    eax, eax
0x180007942  jns     loc_180007A13
0x180007948  test    dword ptr [rdi+0A0h], 10000h
0x180007952  jz      loc_180007A66
0x180007958  mov     rcx, [rdi+118h]; hClientHandle
0x18000795f  lea     rax, [rsp+298h+var_258]
0x180007964  mov     [rsp+298h+pvReserved], 0; pvReserved
0x18000796d  lea     r9, [rsp+298h+ppvData]; ppvData
0x180007972  lea     r8, [rsp+298h+pdwDataSize]; pdwDataSize
0x180007977  mov     [rsp+298h+pWlanOpcodeValueType], rax; pWlanOpcodeValueType
0x18000797c  xor     edx, edx; OpCode
0x18000797e  mov     [rsp+298h+var_258], 0
0x180007986  mov     [rsp+298h+pdwDataSize], 0
0x18000798e  mov     [rsp+298h+ppvData], 0
0x180007997  call    cs:__imp_WlanHostedNetworkQueryProperty
0x18000799d  mov     edi, eax
0x18000799f  test    eax, eax
0x1800079a1  jle     short loc_1800079AC
0x1800079a3  movzx   edi, ax
0x1800079a6  or      edi, 80070000h
0x1800079ac  mov     rsi, [rsp+298h+ppvData]
0x1800079b1  test    edi, edi
0x1800079b3  js      short loc_180007A03
0x1800079b5  test    rsi, rsi
0x1800079b8  jz      loc_180007A49
0x1800079be  cmp     [rsp+298h+pdwDataSize], 0
0x1800079c3  jz      short loc_180007A03
0x1800079c5  xor     edx, edx; Val
0x1800079c7  lea     rcx, [rsp+298h+var_248]; void *
0x1800079cc  mov     r8d, 200h; Size
0x1800079d2  call    memset_0
0x1800079d7  lea     r9, [rsp+298h+var_264]
0x1800079dc  mov     edx, 1
0x1800079e1  lea     r8, [rsp+298h+var_248]
0x1800079e6  mov     rcx, rsi
0x1800079e9  call    cs:__imp_WlanUtf8SsidToDisplayName
0x1800079ef  mov     edi, eax
0x1800079f1  test    eax, eax
0x1800079f3  jle     short loc_1800079FE
0x1800079f5  movzx   edi, ax
0x1800079f8  or      edi, 80070000h
0x1800079fe  mov     rsi, [rsp+298h+ppvData]
0x180007a03  test    rsi, rsi
0x180007a06  jz      short loc_180007A45
0x180007a08  mov     rcx, rsi; pMemory
0x180007a0b  call    cs:__imp_WlanFreeMemory
0x180007a11  jmp     short loc_180007A45
0x180007a13  mov     rcx, [rdi+120h]
0x180007a1a  lea     r9, [rsp+298h+var_264]
0x180007a1f  add     rcx, 208h
0x180007a26  lea     r8, [rsp+298h+var_248]
0x180007a2b  mov     edx, 1
0x180007a30  call    cs:__imp_WlanUtf8SsidToDisplayName
0x180007a36  mov     edi, eax
0x180007a38  test    eax, eax
0x180007a3a  jle     short loc_180007A45
0x180007a3c  movzx   edi, ax
0x180007a3f  or      edi, 80070000h
0x180007a45  test    edi, edi
0x180007a47  js      short loc_180007A66
0x180007a49  lea     r8, [rsp+298h+var_248]
0x180007a4e  jmp     short loc_180007A57
0x180007a50  lea     r8, Caption; lpString
0x180007a57  mov     rcx, [rbx+8]; hDlg
0x180007a5b  mov     edx, 5DD2h; nIDDlgItem
0x180007a60  call    cs:__imp_SetDlgItemTextW
0x180007a66  mov     rcx, [rsp+298h+var_48]
0x180007a6e  xor     rcx, rsp; StackCookie
0x180007a71  call    __security_check_cookie
0x180007a76  add     rsp, 268h
0x180007a7d  pop     r15
0x180007a7f  pop     r14
0x180007a81  pop     rdi
0x180007a82  pop     rsi
0x180007a83  pop     rbp
0x180007a84  pop     rbx
0x180007a85  retn
```
