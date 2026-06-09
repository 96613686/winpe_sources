# Configuration::GetInstanceHash(ulong *)

- ea: `0x140035d18`
- end: `0x1400361ef`
- name: `?GetInstanceHash@Configuration@@QEAAJPEAK@Z`
- size: `1239`
- prototype: `__int64 __fastcall(Configuration *this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000859c`

## callees

- `0x140006fe0`
- `0x140020420`
- `0x140021f70`
- `0x140035d18`
- `0x140049bc0`
- `0x14004a13c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140035d46`
- `KERNEL32!HeapAlloc` at `0x140035d46`
- `KERNEL32!HeapFree` at `0x1400361d3`
- `KERNEL32!HeapFree` at `0x1400361d3`
- `KERNEL32!GetProcessHeap` at `0x140035d2f`
- `KERNEL32!GetProcessHeap` at `0x1400361bf`
- `KERNEL32!GetProcessHeap` at `0x140035d2f`
- `KERNEL32!GetProcessHeap` at `0x1400361bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1400361b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400361b3`

## string_xrefs

- `0x140035d5f`: `Configuration::GetInstanceHash`
- `0x140035dfa`: `Configuration::GetInstanceHash`
- `0x14003618f`: `Configuration::GetInstanceHash`
- `0x140035ead`: ` -path "`

## pseudocode

```c
__int64 __fastcall Configuration::GetInstanceHash(Configuration *this, unsigned int *a2)
{
  Configuration *v2; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rbp
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // eax
  int v14; // r9d
  const unsigned __int16 *Path; // rax
  const unsigned __int16 *v16; // rax
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  int v22; // r9d
  HANDLE v23; // rax

  v2 = Config;
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( v5 )
  {
    v7 = 0;
    *v5 = 0;
    v8 = *((_DWORD *)v2 + 66);
    if ( v8 > 7 )
    {
      v17 = v8 - 8;
      if ( v17 && (v18 = v17 - 1) != 0 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 != 1 )
              goto LABEL_33;
            v13 = StringCchCatW(v5, 0x400u, L"badid");
            v6 = v13;
            if ( v13 < 0 )
            {
              v14 = 2108;
              goto LABEL_12;
            }
          }
          else
          {
            v13 = StringCchCatW(v5, 0x400u, L" -up \"");
            v6 = v13;
            if ( v13 < 0 )
            {
              v14 = 2086;
              goto LABEL_12;
            }
            v13 = StringCchCatW(v5, 0x400u, g_HistoryDirectory);
            v6 = v13;
            if ( v13 < 0 )
            {
              v14 = 2089;
              goto LABEL_12;
            }
            v13 = StringCchCatW(v5, 0x400u, L"\"");
            v6 = v13;
            if ( v13 < 0 )
            {
              v14 = 2092;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v13 = StringCchCatW(v5, 0x400u, L" -dt \"");
          v6 = v13;
          if ( v13 < 0 )
          {
            v14 = 2097;
            goto LABEL_12;
          }
          v13 = StringCchCatW(v5, 0x400u, g_HistoryDirectory);
          v6 = v13;
          if ( v13 < 0 )
          {
            v14 = 2100;
            goto LABEL_12;
          }
          v13 = StringCchCatW(v5, 0x400u, L"\"");
          v6 = v13;
          if ( v13 < 0 )
          {
            v14 = 2103;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v13 = StringCchCatW(v5, 0x400u, L" -id ");
        v6 = v13;
        if ( v13 < 0 )
        {
          v14 = 2032;
          goto LABEL_12;
        }
        v7 = Packages_ID();
        v21 = StringCchCatW(v5, 0x400u, v7);
        v6 = v21;
        if ( v21 < 0 )
        {
          v22 = 2036;
          goto LABEL_68;
        }
      }
    }
    else
    {
      if ( v8 != 7 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( !v10 || (v11 = v10 - 1) == 0 )
          {
            if ( *((_QWORD *)v2 + 12) )
            {
              v13 = StringCchCatW(v5, 0x400u, L" -sp ");
              v6 = v13;
              if ( v13 < 0 )
              {
                v14 = 2074;
                goto LABEL_12;
              }
              v13 = StringCchCatW(v5, 0x400u, *((const unsigned __int16 **)v2 + 12));
              v6 = v13;
              if ( v13 < 0 )
              {
                v14 = 2077;
                goto LABEL_12;
              }
            }
            goto LABEL_52;
          }
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( (unsigned int)(v12 - 1) <= 1 )
            {
              v13 = StringCchCatW(v5, 0x400u, L" -cab \"");
              v6 = v13;
              if ( v13 < 0 )
              {
                v14 = 2042;
LABEL_12:
                SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::GetInstanceHash", v14, v13);
LABEL_71:
                v23 = GetProcessHeap();
                HeapFree(v23, 0, v5);
                return v6;
              }
              Path = Packages_GetPath();
              v13 = StringCchCatW(v5, 0x400u, Path);
              v6 = v13;
              if ( v13 < 0 )
              {
                v14 = 2045;
                goto LABEL_12;
              }
              v13 = StringCchCatW(v5, 0x400u, L"\"");
              v6 = v13;
              if ( v13 < 0 )
              {
                v14 = 2048;
                goto LABEL_12;
              }
              goto LABEL_52;
            }
LABEL_33:
            v6 = -2147418113;
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::GetInstanceHash", 2113, -2147418113);
            goto LABEL_71;
          }
        }
      }
      v13 = StringCchCatW(v5, 0x400u, L" -path \"");
      v6 = v13;
      if ( v13 < 0 )
      {
        v14 = 2055;
        goto LABEL_12;
      }
      v16 = Packages_GetPath();
      v13 = StringCchCatW(v5, 0x400u, v16);
      v6 = v13;
      if ( v13 < 0 )
      {
        v14 = 2058;
        goto LABEL_12;
      }
      v13 = StringCchCatW(v5, 0x400u, L"\"");
      v6 = v13;
      if ( v13 < 0 )
      {
        v14 = 2061;
        goto LABEL_12;
      }
    }
LABEL_52:
    if ( *((_QWORD *)v2 + 29) )
    {
      v21 = StringCchCatW(v5, 0x400u, L" -param \"");
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2121;
        goto LABEL_68;
      }
      v21 = StringCchCatW(v5, 0x400u, *((const unsigned __int16 **)v2 + 29));
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2124;
        goto LABEL_68;
      }
      v21 = StringCchCatW(v5, 0x400u, L"\"");
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2127;
        goto LABEL_68;
      }
    }
    if ( *((_QWORD *)v2 + 30) )
    {
      v21 = StringCchCatW(v5, 0x400u, L" -af \"");
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2135;
        goto LABEL_68;
      }
      v21 = StringCchCatW(v5, 0x400u, *((const unsigned __int16 **)v2 + 30));
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2138;
        goto LABEL_68;
      }
      v21 = StringCchCatW(v5, 0x400u, L"\"");
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 2141;
        goto LABEL_68;
      }
    }
    v21 = HashString(v5, a2);
    v6 = v21;
    if ( v21 >= 0 )
      goto LABEL_69;
    v22 = 2148;
LABEL_68:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::GetInstanceHash", v22, v21);
LABEL_69:
    if ( v7 )
      SysFreeString(v7);
    goto LABEL_71;
  }
  v6 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::GetInstanceHash", 2025, -2147024882);
  return v6;
}

```

## disassembly

```asm
0x140035d18  push    rbx
0x140035d1a  push    rbp
0x140035d1b  push    rsi
0x140035d1c  push    rdi
0x140035d1d  push    r12
0x140035d1f  push    r14
0x140035d21  sub     rsp, 38h
0x140035d25  mov     rsi, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140035d2c  mov     r14, rdx
0x140035d2f  call    cs:__imp_GetProcessHeap
0x140035d36  nop     dword ptr [rax+rax+00h]
0x140035d3b  xor     edx, edx; dwFlags
0x140035d3d  mov     r8d, 800h; dwBytes
0x140035d43  mov     rcx, rax; hHeap
0x140035d46  call    cs:__imp_HeapAlloc
0x140035d4d  nop     dword ptr [rax+rax+00h]
0x140035d52  mov     rdi, rax
0x140035d55  test    rax, rax
0x140035d58  jnz     short loc_140035D84
0x140035d5a  mov     ebx, 8007000Eh
0x140035d5f  lea     r8, aConfigurationG; "Configuration::GetInstanceHash"
0x140035d66  mov     r9d, 7E9h
0x140035d6c  mov     [rsp+68h+var_48], ebx
0x140035d70  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140035d77  lea     ecx, [rax+1]; Level
0x140035d7a  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140035d7f  jmp     loc_1400361DF
0x140035d84  xor     eax, eax
0x140035d86  xor     ebp, ebp
0x140035d88  mov     [rdi], ax
0x140035d8b  mov     r12d, 400h
0x140035d91  mov     ecx, [rsi+108h]
0x140035d97  cmp     ecx, 7
0x140035d9a  jg      loc_140035F1B
0x140035da0  jz      loc_140035EAD
0x140035da6  sub     ecx, 1
0x140035da9  jz      loc_140035EAD
0x140035daf  sub     ecx, 1
0x140035db2  jz      loc_140035E5C
0x140035db8  sub     ecx, 1
0x140035dbb  jz      loc_140035E5C
0x140035dc1  sub     ecx, 1
0x140035dc4  jz      loc_140035EAD
0x140035dca  sub     ecx, 1
0x140035dcd  jz      short loc_140035DD8
0x140035dcf  cmp     ecx, 1
0x140035dd2  jnz     loc_140035F40
0x140035dd8  lea     r8, aCab; " -cab \""
0x140035ddf  mov     rdx, r12; unsigned __int64
0x140035de2  mov     rcx, rdi; unsigned __int16 *
0x140035de5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035dea  mov     ebx, eax
0x140035dec  test    eax, eax
0x140035dee  jns     short loc_140035E17
0x140035df0  mov     r9d, 7FAh
0x140035df6  mov     [rsp+68h+var_48], eax
0x140035dfa  lea     r8, aConfigurationG; "Configuration::GetInstanceHash"
0x140035e01  mov     ecx, 1; Level
0x140035e06  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140035e0d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140035e12  jmp     loc_1400361BF
0x140035e17  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140035e1c  mov     r8, rax; unsigned __int16 *
0x140035e1f  mov     rdx, r12; unsigned __int64
0x140035e22  mov     rcx, rdi; unsigned __int16 *
0x140035e25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035e2a  mov     ebx, eax
0x140035e2c  test    eax, eax
0x140035e2e  jns     short loc_140035E38
0x140035e30  mov     r9d, 7FDh
0x140035e36  jmp     short loc_140035DF6
0x140035e38  lea     r8, asc_1400701E0; "\""
0x140035e3f  mov     rdx, r12; unsigned __int64
0x140035e42  mov     rcx, rdi; unsigned __int16 *
0x140035e45  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035e4a  mov     ebx, eax
0x140035e4c  test    eax, eax
0x140035e4e  jns     loc_14003609B
0x140035e54  mov     r9d, 800h
0x140035e5a  jmp     short loc_140035DF6
0x140035e5c  cmp     [rsi+60h], rax
0x140035e60  jz      loc_14003609B
0x140035e66  lea     r8, aSp_0; " -sp "
0x140035e6d  mov     rdx, r12; unsigned __int64
0x140035e70  mov     rcx, rdi; unsigned __int16 *
0x140035e73  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035e78  mov     ebx, eax
0x140035e7a  test    eax, eax
0x140035e7c  jns     short loc_140035E89
0x140035e7e  mov     r9d, 81Ah
0x140035e84  jmp     loc_140035DF6
0x140035e89  mov     r8, [rsi+60h]; unsigned __int16 *
0x140035e8d  mov     rdx, r12; unsigned __int64
0x140035e90  mov     rcx, rdi; unsigned __int16 *
0x140035e93  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035e98  mov     ebx, eax
0x140035e9a  test    eax, eax
0x140035e9c  jns     loc_14003609B
0x140035ea2  mov     r9d, 81Dh
0x140035ea8  jmp     loc_140035DF6
0x140035ead  lea     r8, aPath_0; " -path \""
0x140035eb4  mov     rdx, r12; unsigned __int64
0x140035eb7  mov     rcx, rdi; unsigned __int16 *
0x140035eba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035ebf  mov     ebx, eax
0x140035ec1  test    eax, eax
0x140035ec3  jns     short loc_140035ED0
0x140035ec5  mov     r9d, 807h
0x140035ecb  jmp     loc_140035DF6
0x140035ed0  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140035ed5  mov     r8, rax; unsigned __int16 *
0x140035ed8  mov     rdx, r12; unsigned __int64
0x140035edb  mov     rcx, rdi; unsigned __int16 *
0x140035ede  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035ee3  mov     ebx, eax
0x140035ee5  test    eax, eax
0x140035ee7  jns     short loc_140035EF4
0x140035ee9  mov     r9d, 80Ah
0x140035eef  jmp     loc_140035DF6
0x140035ef4  lea     r8, asc_1400701E0; "\""
0x140035efb  mov     rdx, r12; unsigned __int64
0x140035efe  mov     rcx, rdi; unsigned __int16 *
0x140035f01  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035f06  mov     ebx, eax
0x140035f08  test    eax, eax
0x140035f0a  jns     loc_14003609B
0x140035f10  mov     r9d, 80Dh
0x140035f16  jmp     loc_140035DF6
0x140035f1b  sub     ecx, 8
0x140035f1e  jz      loc_140036051
0x140035f24  sub     ecx, 1
0x140035f27  jz      loc_140036051
0x140035f2d  sub     ecx, 1
0x140035f30  jz      loc_140035FE8
0x140035f36  sub     ecx, 1
0x140035f39  jz      short loc_140035F7B
0x140035f3b  cmp     ecx, 1
0x140035f3e  jz      short loc_140035F54
0x140035f40  mov     ebx, 8000FFFFh
0x140035f45  mov     r9d, 841h
0x140035f4b  mov     [rsp+68h+var_48], ebx
0x140035f4f  jmp     loc_140035DFA
0x140035f54  lea     r8, aBadid; "badid"
0x140035f5b  mov     rdx, r12; unsigned __int64
0x140035f5e  mov     rcx, rdi; unsigned __int16 *
0x140035f61  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035f66  mov     ebx, eax
0x140035f68  test    eax, eax
0x140035f6a  jns     loc_14003609B
0x140035f70  mov     r9d, 83Ch
0x140035f76  jmp     loc_140035DF6
0x140035f7b  lea     r8, aUp; " -up \""
0x140035f82  mov     rdx, r12; unsigned __int64
0x140035f85  mov     rcx, rdi; unsigned __int16 *
0x140035f88  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035f8d  mov     ebx, eax
0x140035f8f  test    eax, eax
0x140035f91  jns     short loc_140035F9E
0x140035f93  mov     r9d, 826h
0x140035f99  jmp     loc_140035DF6
0x140035f9e  mov     r8, cs:?g_HistoryDirectory@@3PEAGEA; unsigned __int16 *
0x140035fa5  mov     rdx, r12; unsigned __int64
0x140035fa8  mov     rcx, rdi; unsigned __int16 *
0x140035fab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035fb0  mov     ebx, eax
0x140035fb2  test    eax, eax
0x140035fb4  jns     short loc_140035FC1
0x140035fb6  mov     r9d, 829h
0x140035fbc  jmp     loc_140035DF6
0x140035fc1  lea     r8, asc_1400701E0; "\""
0x140035fc8  mov     rdx, r12; unsigned __int64
0x140035fcb  mov     rcx, rdi; unsigned __int16 *
0x140035fce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035fd3  mov     ebx, eax
0x140035fd5  test    eax, eax
0x140035fd7  jns     loc_14003609B
0x140035fdd  mov     r9d, 82Ch
0x140035fe3  jmp     loc_140035DF6
0x140035fe8  lea     r8, aDt; " -dt \""
0x140035fef  mov     rdx, r12; unsigned __int64
0x140035ff2  mov     rcx, rdi; unsigned __int16 *
0x140035ff5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035ffa  mov     ebx, eax
0x140035ffc  test    eax, eax
0x140035ffe  jns     short loc_14003600B
0x140036000  mov     r9d, 831h
0x140036006  jmp     loc_140035DF6
0x14003600b  mov     r8, cs:?g_HistoryDirectory@@3PEAGEA; unsigned __int16 *
0x140036012  mov     rdx, r12; unsigned __int64
0x140036015  mov     rcx, rdi; unsigned __int16 *
0x140036018  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003601d  mov     ebx, eax
0x14003601f  test    eax, eax
0x140036021  jns     short loc_14003602E
0x140036023  mov     r9d, 834h
0x140036029  jmp     loc_140035DF6
0x14003602e  lea     r8, asc_1400701E0; "\""
0x140036035  mov     rdx, r12; unsigned __int64
0x140036038  mov     rcx, rdi; unsigned __int16 *
0x14003603b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140036040  mov     ebx, eax
0x140036042  test    eax, eax
0x140036044  jns     short loc_14003609B
0x140036046  mov     r9d, 837h
0x14003604c  jmp     loc_140035DF6
0x140036051  lea     r8, aId; " -id "
0x140036058  mov     rdx, r12; unsigned __int64
0x14003605b  mov     rcx, rdi; unsigned __int16 *
0x14003605e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140036063  mov     ebx, eax
0x140036065  test    eax, eax
0x140036067  jns     short loc_140036074
0x140036069  mov     r9d, 7F0h
0x14003606f  jmp     loc_140035DF6
0x140036074  call    ?Packages_ID@@YAPEAGXZ; Packages_ID(void)
0x140036079  mov     r8, rax; unsigned __int16 *
0x14003607c  mov     rdx, r12; unsigned __int64
0x14003607f  mov     rcx, rdi; unsigned __int16 *
0x140036082  mov     rbp, rax
0x140036085  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003608a  mov     ebx, eax
0x14003608c  test    eax, eax
0x14003608e  jns     short loc_14003609B
0x140036090  mov     r9d, 7F4h
0x140036096  jmp     loc_14003618F
0x14003609b  cmp     qword ptr [rsi+0E8h], 0
0x1400360a3  jz      short loc_14003610E
0x1400360a5  lea     r8, aParam_0; " -param \""
0x1400360ac  mov     rdx, r12; unsigned __int64
0x1400360af  mov     rcx, rdi; unsigned __int16 *
0x1400360b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400360b7  mov     ebx, eax
0x1400360b9  test    eax, eax
0x1400360bb  jns     short loc_1400360C8
0x1400360bd  mov     r9d, 849h
0x1400360c3  jmp     loc_14003618F
0x1400360c8  mov     r8, [rsi+0E8h]; unsigned __int16 *
0x1400360cf  mov     rdx, r12; unsigned __int64
0x1400360d2  mov     rcx, rdi; unsigned __int16 *
0x1400360d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400360da  mov     ebx, eax
0x1400360dc  test    eax, eax
0x1400360de  jns     short loc_1400360EB
0x1400360e0  mov     r9d, 84Ch
0x1400360e6  jmp     loc_14003618F
0x1400360eb  lea     r8, asc_1400701E0; "\""
0x1400360f2  mov     rdx, r12; unsigned __int64
0x1400360f5  mov     rcx, rdi; unsigned __int16 *
0x1400360f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400360fd  mov     ebx, eax
0x1400360ff  test    eax, eax
0x140036101  jns     short loc_14003610E
0x140036103  mov     r9d, 84Fh
0x140036109  jmp     loc_14003618F
0x14003610e  cmp     qword ptr [rsi+0F0h], 0
0x140036116  jz      short loc_140036178
0x140036118  lea     r8, aAf_0; " -af \""
0x14003611f  mov     rdx, r12; unsigned __int64
0x140036122  mov     rcx, rdi; unsigned __int16 *
0x140036125  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003612a  mov     ebx, eax
0x14003612c  test    eax, eax
0x14003612e  jns     short loc_140036138
0x140036130  mov     r9d, 857h
0x140036136  jmp     short loc_14003618F
0x140036138  mov     r8, [rsi+0F0h]; unsigned __int16 *
0x14003613f  mov     rdx, r12; unsigned __int64
0x140036142  mov     rcx, rdi; unsigned __int16 *
0x140036145  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003614a  mov     ebx, eax
0x14003614c  test    eax, eax
0x14003614e  jns     short loc_140036158
0x140036150  mov     r9d, 85Ah
0x140036156  jmp     short loc_14003618F
0x140036158  lea     r8, asc_1400701E0; "\""
0x14003615f  mov     rdx, r12; unsigned __int64
0x140036162  mov     rcx, rdi; unsigned __int16 *
0x140036165  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003616a  mov     ebx, eax
0x14003616c  test    eax, eax
0x14003616e  jns     short loc_140036178
0x140036170  mov     r9d, 85Dh
0x140036176  jmp     short loc_14003618F
0x140036178  mov     rdx, r14; unsigned int *
0x14003617b  mov     rcx, rdi; unsigned __int16 *
0x14003617e  call    ?HashString@@YAJPEBGPEAK@Z; HashString(ushort const *,ulong *)
0x140036183  mov     ebx, eax
0x140036185  test    eax, eax
0x140036187  jns     short loc_1400361AB
0x140036189  mov     r9d, 864h
0x14003618f  lea     r8, aConfigurationG; "Configuration::GetInstanceHash"
0x140036196  mov     [rsp+68h+var_48], eax
0x14003619a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400361a1  mov     ecx, 1; Level
0x1400361a6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400361ab  test    rbp, rbp
0x1400361ae  jz      short loc_1400361BF
0x1400361b0  mov     rcx, rbp; bstrString
0x1400361b3  call    cs:__imp_SysFreeString
0x1400361ba  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
