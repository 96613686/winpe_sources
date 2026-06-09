# InitializeFaxQueue(_REG_FAX_SERVICE *)

- ea: `0x14004fdac`
- end: `0x1400500d5`
- name: `?InitializeFaxQueue@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400480f0`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x14004fdac`
- `0x140065d14`
- `0x140065dbc`
- `0x140066868`
- `0x14006e160`
- `0x14006e54c`
- `0x140074a48`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004fe51`
- `KERNEL32!GetLastError` at `0x14004fef2`
- `KERNEL32!GetLastError` at `0x14004fe51`
- `KERNEL32!GetLastError` at `0x14004fef2`
- `KERNEL32!SetLastError` at `0x1400500a9`
- `KERNEL32!SetLastError` at `0x1400500a9`

## pseudocode

```c
_BOOL8 __fastcall InitializeFaxQueue(struct _REG_FAX_SERVICE *a1)
{
  unsigned __int16 *v1; // rcx
  wchar_t *v2; // rax
  wchar_t *v3; // rbx
  DWORD LastError; // eax
  CFaxConfiguration *v6; // rcx
  DWORD v7; // eax
  DWORD v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  int v12; // eax
  DWORD valid; // eax
  unsigned __int16 v14[264]; // [rsp+30h] [rbp-248h] BYREF

  memset_0(v14, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids);
  }
  v1 = (unsigned __int16 *)*((_QWORD *)g_pFaxConfig + 12);
  if ( v1 )
  {
    v2 = (wchar_t *)ExpandEnvironmentString(v1);
    v3 = v2;
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, LastError);
      }
      return 0;
    }
    if ( !PathRepresentsFullPath(v2) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, v3);
      }
      pMemFree(v3);
      return 0;
    }
    pMemFree(*((LPVOID *)g_pFaxConfig + 12));
    v6 = g_pFaxConfig;
    *((_QWORD *)g_pFaxConfig + 12) = v3;
LABEL_48:
    valid = IsValidFaxFolder(*((unsigned __int16 **)v6 + 12));
    v8 = valid;
    if ( valid )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids,
          *((_QWORD *)g_pFaxConfig + 12),
          valid);
      }
      goto LABEL_53;
    }
    return v8 == 0;
  }
  if ( (unsigned int)GetSpecialPath(35, v14, 0x104u) )
  {
    v9 = -1;
    do
      ++v9;
    while ( v14[v9] );
    v10 = (unsigned int)(v9 + 34);
    if ( (unsigned int)v10 >= 0x104 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids);
      }
      v8 = 111;
      goto LABEL_53;
    }
    v11 = (unsigned __int16 *)pMemAlloc(2 * v10);
    *((_QWORD *)g_pFaxConfig + 12) = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids,
          (unsigned int)v10);
      }
      v8 = 8;
      goto LABEL_53;
    }
    v12 = StringCchPrintfW(v11, (unsigned int)v10, L"%s\\%s", v14, L"Microsoft\\Windows NT\\MSFax\\Queue");
    v8 = v12;
    if ( v12 >= 0 )
    {
      v6 = g_pFaxConfig;
      goto LABEL_48;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids,
        (unsigned int)v12);
    }
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v8;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, v7);
    }
  }
  if ( v8 )
  {
LABEL_53:
    pMemFree(*((LPVOID *)g_pFaxConfig + 12));
    *((_QWORD *)g_pFaxConfig + 12) = 0;
    SetLastError(v8);
  }
  return v8 == 0;
}

```

## disassembly

```asm
0x14004fdac  push    rbx
0x14004fdae  push    rsi
0x14004fdaf  push    rdi
0x14004fdb0  push    r14
0x14004fdb2  push    r15
0x14004fdb4  sub     rsp, 250h
0x14004fdbb  mov     rax, cs:__security_cookie
0x14004fdc2  xor     rax, rsp
0x14004fdc5  mov     [rsp+278h+var_38], rax
0x14004fdcd  xor     edx, edx; Val
0x14004fdcf  lea     rcx, [rsp+278h+var_248]; void *
0x14004fdd4  mov     r8d, 208h; Size
0x14004fdda  call    memset_0
0x14004fddf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fde6  lea     r14, WPP_GLOBAL_Control
0x14004fded  lea     r15, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids
0x14004fdf4  cmp     rcx, r14
0x14004fdf7  jz      short loc_14004FE16
0x14004fdf9  test    byte ptr [rcx+1Ch], 4
0x14004fdfd  jz      short loc_14004FE16
0x14004fdff  cmp     byte ptr [rcx+19h], 5
0x14004fe03  jb      short loc_14004FE16
0x14004fe05  mov     rcx, [rcx+10h]
0x14004fe09  mov     edx, 0Dh
0x14004fe0e  mov     r8, r15
0x14004fe11  call    WPP_SF_
0x14004fe16  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14004fe1d  xor     esi, esi
0x14004fe1f  mov     rcx, [rax+60h]; unsigned __int16 *
0x14004fe23  test    rcx, rcx
0x14004fe26  jz      loc_14004FED7
0x14004fe2c  call    ExpandEnvironmentString
0x14004fe31  mov     rbx, rax
0x14004fe34  test    rax, rax
0x14004fe37  jnz     short loc_14004FE77
0x14004fe39  mov     rax, cs:WPP_GLOBAL_Control
0x14004fe40  cmp     rax, r14
0x14004fe43  jz      short loc_14004FE70
0x14004fe45  test    byte ptr [rax+1Ch], 4
0x14004fe49  jz      short loc_14004FE70
0x14004fe4b  cmp     byte ptr [rax+19h], 2
0x14004fe4f  jb      short loc_14004FE70
0x14004fe51  call    cs:__imp_GetLastError
0x14004fe57  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe5e  lea     edx, [rsi+0Eh]
0x14004fe61  mov     r9d, eax
0x14004fe64  mov     r8, r15
0x14004fe67  mov     rcx, [rcx+10h]
0x14004fe6b  call    WPP_SF_d
0x14004fe70  xor     eax, eax
0x14004fe72  jmp     loc_1400500B6
0x14004fe77  mov     rcx, rbx; String1
0x14004fe7a  call    PathRepresentsFullPath
0x14004fe7f  test    eax, eax
0x14004fe81  jnz     short loc_14004FEB7
0x14004fe83  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe8a  cmp     rcx, r14
0x14004fe8d  jz      short loc_14004FEAD
0x14004fe8f  test    byte ptr [rcx+1Ch], 4
0x14004fe93  jz      short loc_14004FEAD
0x14004fe95  cmp     byte ptr [rcx+19h], 2
0x14004fe99  jb      short loc_14004FEAD
0x14004fe9b  mov     rcx, [rcx+10h]
0x14004fe9f  lea     edx, [rax+0Fh]
0x14004fea2  mov     r9, rbx
0x14004fea5  mov     r8, r15
0x14004fea8  call    WPP_SF_S
0x14004fead  mov     rcx, rbx; lpMem
0x14004feb0  call    pMemFree
0x14004feb5  jmp     short loc_14004FE70
0x14004feb7  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14004febe  mov     rcx, [rcx+60h]; lpMem
0x14004fec2  call    pMemFree
0x14004fec7  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14004fece  mov     [rcx+60h], rbx
0x14004fed2  jmp     loc_140050045
0x14004fed7  mov     edi, 104h
0x14004fedc  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x14004fee1  mov     r8d, edi; unsigned __int64
0x14004fee4  mov     ecx, 23h ; '#'; csidl
0x14004fee9  call    GetSpecialPath
0x14004feee  test    eax, eax
0x14004fef0  jnz     short loc_14004FF37
0x14004fef2  call    cs:__imp_GetLastError
0x14004fef8  mov     ebx, eax
0x14004fefa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff01  cmp     rcx, r14
0x14004ff04  jz      loc_140050038
0x14004ff0a  test    byte ptr [rcx+1Ch], 4
0x14004ff0e  jz      loc_140050038
0x14004ff14  cmp     byte ptr [rcx+19h], 2
0x14004ff18  jb      loc_140050038
0x14004ff1e  mov     rcx, [rcx+10h]
0x14004ff22  mov     edx, 10h
0x14004ff27  mov     r9d, eax
0x14004ff2a  mov     r8, r15
0x14004ff2d  call    WPP_SF_d
0x14004ff32  jmp     loc_140050038
0x14004ff37  lea     rcx, [rsp+278h+var_248]
0x14004ff3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004ff40  inc     rax
0x14004ff43  cmp     [rcx+rax*2], si
0x14004ff47  jnz     short loc_14004FF40
0x14004ff49  lea     ebx, [rax+22h]
0x14004ff4c  cmp     ebx, edi
0x14004ff4e  jb      short loc_14004FF83
0x14004ff50  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff57  cmp     rcx, r14
0x14004ff5a  jz      short loc_14004FF79
0x14004ff5c  test    byte ptr [rcx+1Ch], 4
0x14004ff60  jz      short loc_14004FF79
0x14004ff62  cmp     byte ptr [rcx+19h], 2
0x14004ff66  jb      short loc_14004FF79
0x14004ff68  mov     rcx, [rcx+10h]
0x14004ff6c  mov     edx, 11h
0x14004ff71  mov     r8, r15
0x14004ff74  call    WPP_SF_
0x14004ff79  mov     ebx, 6Fh ; 'o'
0x14004ff7e  jmp     loc_14005008C
0x14004ff83  lea     rcx, [rbx+rbx]; dwBytes
0x14004ff87  mov     edi, ebx
0x14004ff89  call    pMemAlloc
0x14004ff8e  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14004ff95  mov     [rcx+60h], rax
0x14004ff99  test    rax, rax
0x14004ff9c  jnz     short loc_14004FFD2
0x14004ff9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ffa5  cmp     rcx, r14
0x14004ffa8  jz      short loc_14004FFC8
0x14004ffaa  test    byte ptr [rcx+1Ch], 4
0x14004ffae  jz      short loc_14004FFC8
0x14004ffb0  cmp     byte ptr [rcx+19h], 2
0x14004ffb4  jb      short loc_14004FFC8
0x14004ffb6  mov     rcx, [rcx+10h]
0x14004ffba  lea     edx, [rax+12h]
0x14004ffbd  mov     r9d, ebx
0x14004ffc0  mov     r8, r15
0x14004ffc3  call    WPP_SF_d
0x14004ffc8  mov     ebx, 8
0x14004ffcd  jmp     loc_14005008C
0x14004ffd2  lea     rcx, aMicrosoftWindo_0; "Microsoft\\Windows NT\\MSFax\\Queue"
0x14004ffd9  mov     rdx, rdi; unsigned __int64
0x14004ffdc  mov     [rsp+278h+var_258], rcx
0x14004ffe1  lea     r9, [rsp+278h+var_248]
0x14004ffe6  mov     rcx, rax; unsigned __int16 *
0x14004ffe9  lea     r8, aSS_0; "%s\\%s"
0x14004fff0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004fff5  mov     ebx, eax
0x14004fff7  test    eax, eax
0x14004fff9  jns     short loc_14005003E
0x14004fffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140050002  cmp     rcx, r14
0x140050005  jz      short loc_140050027
0x140050007  test    byte ptr [rcx+1Ch], 4
0x14005000b  jz      short loc_140050027
0x14005000d  cmp     byte ptr [rcx+19h], 2
0x140050011  jb      short loc_140050027
0x140050013  mov     rcx, [rcx+10h]
0x140050017  mov     edx, 13h
0x14005001c  mov     r9d, eax
0x14005001f  mov     r8, r15
0x140050022  call    WPP_SF_d
0x140050027  mov     eax, ebx
0x140050029  and     eax, 1FFF0000h
0x14005002e  cmp     eax, 70000h
0x140050033  jnz     short loc_140050038
0x140050035  movzx   ebx, bx
0x140050038  test    ebx, ebx
0x14005003a  jz      short loc_1400500AF
0x14005003c  jmp     short loc_14005008C
0x14005003e  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140050045  mov     rcx, [rcx+60h]; unsigned __int16 *
0x140050049  call    IsValidFaxFolder
0x14005004e  mov     ebx, eax
0x140050050  test    eax, eax
0x140050052  jz      short loc_1400500AF
0x140050054  mov     rcx, cs:WPP_GLOBAL_Control
0x14005005b  cmp     rcx, r14
0x14005005e  jz      short loc_14005008C
0x140050060  test    byte ptr [rcx+1Ch], 4
0x140050064  jz      short loc_14005008C
0x140050066  cmp     byte ptr [rcx+19h], 2
0x14005006a  jb      short loc_14005008C
0x14005006c  mov     r9, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140050073  mov     edx, 14h
0x140050078  mov     rcx, [rcx+10h]
0x14005007c  mov     r8, r15
0x14005007f  mov     dword ptr [rsp+278h+var_258], eax
0x140050083  mov     r9, [r9+60h]
0x140050087  call    WPP_SF_Sd
0x14005008c  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140050093  mov     rcx, [rcx+60h]; lpMem
0x140050097  call    pMemFree
0x14005009c  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400500a3  mov     ecx, ebx; dwErrCode
0x1400500a5  mov     [rax+60h], rsi
0x1400500a9  call    cs:__imp_SetLastError
0x1400500af  test    ebx, ebx
0x1400500b1  mov     eax, esi
0x1400500b3  setz    al
0x1400500b6  mov     rcx, [rsp+278h+var_38]
0x1400500be  xor     rcx, rsp; StackCookie
0x1400500c1  call    __security_check_cookie
0x1400500c6  add     rsp, 250h
0x1400500cd  pop     r15
0x1400500cf  pop     r14
0x1400500d1  pop     rdi
0x1400500d2  pop     rsi
0x1400500d3  pop     rbx
0x1400500d4  retn
```
