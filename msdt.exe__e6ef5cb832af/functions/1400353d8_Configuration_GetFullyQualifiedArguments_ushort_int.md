# Configuration::GetFullyQualifiedArguments(ushort * *,int)

- ea: `0x1400353d8`
- end: `0x140035d10`
- name: `?GetFullyQualifiedArguments@Configuration@@QEAAJPEAPEAGH@Z`
- size: `2360`
- prototype: `__int64 __fastcall(Configuration *__hidden this, unsigned __int16 **, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002840c`
- `0x14003d82c`

## callees

- `0x140006fe0`
- `0x1400070b0`
- `0x140020420`
- `0x140020b00`
- `0x140029d18`
- `0x1400353d8`
- `0x140049bc0`
- `0x14004a13c`
- `0x140061c90`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140035424`
- `KERNEL32!HeapAlloc` at `0x14003585b`
- `KERNEL32!HeapAlloc` at `0x140035ad6`
- `KERNEL32!HeapAlloc` at `0x140035424`
- `KERNEL32!HeapAlloc` at `0x14003585b`
- `KERNEL32!HeapAlloc` at `0x140035ad6`
- `KERNEL32!HeapFree` at `0x140035c8f`
- `KERNEL32!HeapFree` at `0x140035cb9`
- `KERNEL32!HeapFree` at `0x140035ce3`
- `KERNEL32!HeapFree` at `0x140035c8f`
- `KERNEL32!HeapFree` at `0x140035cb9`
- `KERNEL32!HeapFree` at `0x140035ce3`
- `KERNEL32!GetProcessHeap` at `0x14003540d`
- `KERNEL32!GetProcessHeap` at `0x140035844`
- `KERNEL32!GetProcessHeap` at `0x140035abf`
- `KERNEL32!GetProcessHeap` at `0x140035c7b`
- `KERNEL32!GetProcessHeap` at `0x140035ca5`
- `KERNEL32!GetProcessHeap` at `0x140035ccf`
- `KERNEL32!GetProcessHeap` at `0x14003540d`
- `KERNEL32!GetProcessHeap` at `0x140035844`
- `KERNEL32!GetProcessHeap` at `0x140035abf`
- `KERNEL32!GetProcessHeap` at `0x140035c7b`
- `KERNEL32!GetProcessHeap` at `0x140035ca5`
- `KERNEL32!GetProcessHeap` at `0x140035ccf`
- `OLEAUT32!__imp_SysFreeString` at `0x140035c6a`
- `OLEAUT32!__imp_SysFreeString` at `0x140035c6a`
- `ole32!StringFromGUID2` at `0x1400358c2`
- `ole32!StringFromGUID2` at `0x1400358c2`
- `RPCRT4!UuidCreate` at `0x14003588b`
- `RPCRT4!UuidCreate` at `0x14003588b`

## string_xrefs

- `0x1400354bf`: ` -path "`
- `0x140035735`: ` -path "`
- `0x14003543f`: `Configuration::GetFullyQualifiedArguments`
- `0x1400354dd`: `Configuration::GetFullyQualifiedArguments`
- `0x140035712`: `Configuration::GetFullyQualifiedArguments`

## pseudocode

```c
__int64 __fastcall Configuration::GetFullyQualifiedArguments(Configuration *this, unsigned __int16 **a2, int a3)
{
  Configuration *v3; // rbp
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx
  unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // r13
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // eax
  int v17; // r9d
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rax
  unsigned __int64 v20; // rbx
  const unsigned __int16 *Path; // rax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // eax
  int v26; // r9d
  const unsigned __int16 *v27; // rax
  HANDLE v28; // rax
  RPC_STATUS v29; // eax
  HANDLE v30; // rax
  unsigned __int16 *v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  OLECHAR *lpMem; // [rsp+30h] [rbp-78h]
  unsigned __int16 *v37; // [rsp+38h] [rbp-70h]
  UUID Uuid; // [rsp+40h] [rbp-68h] BYREF

  v3 = Config;
  Uuid = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v8 = 0;
  v9 = v7;
  if ( !v7 )
  {
    v8 = -2147024882;
    SdpDebugPrint(
      1u,
      "Dwz ERROR: %s:%d - hr = 0x%08X\n",
      "Configuration::GetFullyQualifiedArguments",
      2193,
      -2147024882);
    return v8;
  }
  *v7 = 0;
  v10 = 0;
  v11 = *((_DWORD *)v3 + 66);
  lpMem = 0;
  v37 = 0;
  if ( v11 > 6 )
  {
    v22 = v11 - 7;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          if ( v24 != 3 )
            goto LABEL_44;
        }
      }
      v16 = StringCchCatW(v7, 0x400u, L" -id ");
      v8 = v16;
      if ( v16 < 0 )
      {
        v17 = 2205;
        goto LABEL_13;
      }
      v10 = Packages_ID();
      v25 = StringCchCatW(v9, 0x400u, v10);
      v8 = v25;
      if ( v25 < 0 )
      {
        v26 = 2210;
        goto LABEL_49;
      }
LABEL_56:
      if ( *((_QWORD *)v3 + 27) )
      {
        v25 = StringCchCatW(v9, 0x400u, L" -context ");
        v8 = v25;
        if ( v25 < 0 )
        {
          v26 = 2297;
          goto LABEL_49;
        }
        v25 = StringCchCatW(v9, 0x400u, *((const unsigned __int16 **)v3 + 27));
        v8 = v25;
        if ( v25 < 0 )
        {
          v26 = 2300;
          goto LABEL_49;
        }
      }
      if ( *((_DWORD *)v3 + 8) )
      {
        v25 = StringCchCatW(v9, 0x400u, L" -disconnected yes");
        v8 = v25;
        if ( v25 < 0 )
        {
          v26 = 2311;
          goto LABEL_49;
        }
      }
      if ( *((_DWORD *)v3 + 5) )
      {
        v25 = StringCchCatW(v9, 0x400u, L" -elev ");
        v8 = v25;
        if ( v25 < 0 )
        {
          v26 = 2316;
          goto LABEL_49;
        }
        v28 = GetProcessHeap();
        lpMem = (OLECHAR *)HeapAlloc(v28, 0, 0x200u);
        if ( !lpMem )
        {
          v25 = -2147024882;
          v26 = 2321;
          v8 = -2147024882;
          goto LABEL_49;
        }
        v29 = UuidCreate(&Uuid);
        if ( v29 && v29 != 1824 )
        {
          v25 = -2147467259;
          v26 = 2326;
          v8 = -2147467259;
          goto LABEL_49;
        }
        if ( !StringFromGUID2(&Uuid, lpMem, 256) )
        {
          v25 = -2147467259;
          v26 = 2331;
          v8 = -2147467259;
          goto LABEL_49;
        }
        v25 = StringCchCatW(v9, 0x400u, lpMem);
        v8 = v25;
        if ( v25 < 0 )
        {
          v26 = 2335;
          goto LABEL_49;
        }
        v25 = DwzStrCpy((unsigned __int16 **)v3 + 15, lpMem);
        v8 = v25;
        if ( v25 < 0 )
        {
          v26 = 2338;
          goto LABEL_49;
        }
      }
      if ( (unsigned int)Configuration::SkipWelcome(v3) )
      {
        if ( !*((_DWORD *)v3 + 17) )
        {
          v25 = StringCchCatW(v9, 0x400u, L" -skip yes");
          v8 = v25;
          if ( v25 < 0 )
          {
            v26 = 2353;
            goto LABEL_49;
          }
          goto LABEL_80;
        }
      }
      else if ( !*((_DWORD *)v3 + 17) )
      {
LABEL_80:
        if ( *((_DWORD *)v3 + 10) && (v25 = StringCchCatW(v9, 0x400u, L" -custom yes"), v8 = v25, v25 < 0) )
        {
          v26 = 2359;
        }
        else
        {
          if ( *((_QWORD *)v3 + 29) )
          {
            v25 = StringCchCatW(v9, 0x400u, L" -param \"");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2367;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, *((const unsigned __int16 **)v3 + 29));
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2370;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, L"\"");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2373;
              goto LABEL_49;
            }
          }
          if ( *((_QWORD *)v3 + 30) )
          {
            v25 = StringCchCatW(v9, 0x400u, L" -af \"");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2381;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, *((const unsigned __int16 **)v3 + 30));
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2384;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, L"\"");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2387;
              goto LABEL_49;
            }
          }
          if ( *((_QWORD *)v3 + 34) )
          {
            v25 = StringCchCatW(v9, 0x400u, L" -modal ");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2395;
              goto LABEL_49;
            }
            v30 = GetProcessHeap();
            v31 = (unsigned __int16 *)HeapAlloc(v30, 0, 0x200u);
            v37 = v31;
            if ( !v31 )
            {
              v25 = -2147024882;
              v26 = 2397;
              v8 = -2147024882;
              goto LABEL_49;
            }
            v25 = StringCchPrintfW(v31, 0x100u, L"%p", *((_QWORD *)v3 + 34));
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2400;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, v37);
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2403;
              goto LABEL_49;
            }
          }
          if ( *((_QWORD *)v3 + 20) )
          {
            v25 = StringCchCatW(v9, 0x400u, L" -ep ");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2408;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, *((const unsigned __int16 **)v3 + 20));
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2411;
              goto LABEL_49;
            }
          }
          if ( !*((_DWORD *)v3 + 22) )
          {
            v25 = StringCchCatW(v9, 0x400u, L" -moreoptions ");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2419;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, L"false");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2422;
              goto LABEL_49;
            }
          }
          if ( !*((_DWORD *)v3 + 23) )
          {
            v25 = StringCchCatW(v9, 0x400u, L" -givefeedback ");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2428;
              goto LABEL_49;
            }
            v25 = StringCchCatW(v9, 0x400u, L"false");
            v8 = v25;
            if ( v25 < 0 )
            {
              v26 = 2431;
              goto LABEL_49;
            }
          }
          if ( !a3 || (v25 = StringCchCatW(v9, 0x400u, L" -elevated yes"), v8 = v25, v25 >= 0) )
          {
            *a2 = v9;
            v9 = 0;
LABEL_130:
            if ( v10 )
              SysFreeString(v10);
            if ( !v9 )
              goto LABEL_134;
            goto LABEL_133;
          }
          v26 = 2439;
        }
LABEL_49:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::GetFullyQualifiedArguments", v26, v25);
        goto LABEL_130;
      }
      v25 = StringCchCatW(v9, 0x400u, L" -skip force");
      v8 = v25;
      if ( v25 < 0 )
      {
        v26 = 2347;
        goto LABEL_49;
      }
      goto LABEL_80;
    }
    goto LABEL_50;
  }
  if ( v11 == 6 )
  {
LABEL_34:
    v16 = StringCchCatW(v7, 0x400u, L" -cab \"");
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2216;
      goto LABEL_13;
    }
    Path = Packages_GetPath();
    v16 = StringCchCatW(v9, 0x400u, Path);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2219;
      goto LABEL_13;
    }
    v16 = StringCchCatW(v9, 0x400u, L"\"");
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2222;
      goto LABEL_13;
    }
    goto LABEL_56;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
LABEL_50:
    v16 = StringCchCatW(v7, 0x400u, L" -path \"");
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2228;
      goto LABEL_13;
    }
    v27 = Packages_GetPath();
    v16 = StringCchCatW(v9, 0x400u, v27);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2231;
      goto LABEL_13;
    }
    v16 = StringCchCatW(v9, 0x400u, L"\"");
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2234;
      goto LABEL_13;
    }
    goto LABEL_56;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_29:
    if ( !*((_QWORD *)v3 + 12) )
      goto LABEL_56;
    v16 = StringCchCatW(v9, 0x400u, L" -sp ");
    v8 = v16;
    if ( v16 >= 0 )
    {
      v16 = StringCchCatW(v9, 0x400u, *((const unsigned __int16 **)v3 + 12));
      v8 = v16;
      if ( v16 >= 0 )
        goto LABEL_56;
      v17 = 2283;
    }
    else
    {
      v17 = 2280;
    }
    goto LABEL_13;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v16 = StringCchCatW(v7, 0x400u, L" -dci ");
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2267;
      goto LABEL_13;
    }
    v16 = StringCchCatW(v9, 0x400u, *((const unsigned __int16 **)v3 + 14));
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 2270;
      goto LABEL_13;
    }
    goto LABEL_29;
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    if ( v15 != 1 )
    {
LABEL_44:
      v16 = -2147467259;
      v17 = 2289;
      v8 = -2147467259;
      goto LABEL_13;
    }
    goto LABEL_34;
  }
  v16 = StringCchCatW(v7, 0x400u, L" -path \"");
  v8 = v16;
  if ( v16 >= 0 )
  {
    v18 = Packages_GetPath();
    v16 = StringCchCatW(v9, 0x400u, v18);
    v8 = v16;
    if ( v16 >= 0 )
    {
      if ( !Packages_GetPath() )
        goto LABEL_23;
      v19 = Packages_GetPath();
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( v20 > 1 && Packages_GetPath()[v20 - 1] == 92 && (v16 = StringCchCatW(v9, 0x400u, L"\\"), v8 = v16, v16 < 0) )
      {
        v17 = 2257;
      }
      else
      {
LABEL_23:
        v16 = StringCchCatW(v9, 0x400u, L"\"");
        v8 = v16;
        if ( v16 >= 0 )
          goto LABEL_56;
        v17 = 2262;
      }
    }
    else
    {
      v17 = 2242;
    }
  }
  else
  {
    v17 = 2239;
  }
LABEL_13:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::GetFullyQualifiedArguments", v17, v16);
LABEL_133:
  v32 = GetProcessHeap();
  HeapFree(v32, 0, v9);
LABEL_134:
  if ( lpMem )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, lpMem);
  }
  if ( v37 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v37);
  }
  return v8;
}

```

## disassembly

```asm
0x1400353d8  push    rbx
0x1400353da  push    rbp
0x1400353db  push    rsi
0x1400353dc  push    rdi
0x1400353dd  push    r12
0x1400353df  push    r13
0x1400353e1  push    r14
0x1400353e3  push    r15
0x1400353e5  sub     rsp, 68h
0x1400353e9  mov     rax, cs:__security_cookie
0x1400353f0  xor     rax, rsp
0x1400353f3  mov     [rsp+0A8h+var_58], rax
0x1400353f8  mov     rbp, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400353ff  xorps   xmm0, xmm0
0x140035402  movups  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm0
0x140035407  mov     r15d, r8d
0x14003540a  mov     r12, rdx
0x14003540d  call    cs:__imp_GetProcessHeap
0x140035414  nop     dword ptr [rax+rax+00h]
0x140035419  xor     edx, edx; dwFlags
0x14003541b  mov     r8d, 800h; dwBytes
0x140035421  mov     rcx, rax; hHeap
0x140035424  call    cs:__imp_HeapAlloc
0x14003542b  nop     dword ptr [rax+rax+00h]
0x140035430  xor     ebx, ebx
0x140035432  mov     r14, rax
0x140035435  test    rax, rax
0x140035438  jnz     short loc_140035467
0x14003543a  mov     eax, 8007000Eh
0x14003543f  lea     r8, aConfigurationG_0; "Configuration::GetFullyQualifiedArgumen"...
0x140035446  mov     r9d, 891h
0x14003544c  mov     [rsp+0A8h+var_88], eax
0x140035450  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140035457  mov     ebx, eax
0x140035459  lea     ecx, [r14+1]; Level
0x14003545d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140035462  jmp     loc_140035CEF
0x140035467  mov     [rax], bx
0x14003546a  mov     r13, rbx
0x14003546d  mov     ecx, [rbp+108h]
0x140035473  mov     edi, 1
0x140035478  mov     [rsp+0A8h+lpMem], rbx
0x14003547d  mov     [rsp+0A8h+var_70], rbx
0x140035482  cmp     ecx, 6
0x140035485  jg      loc_14003569D
0x14003548b  jz      loc_14003562A
0x140035491  sub     ecx, edi
0x140035493  jz      loc_140035730
0x140035499  mov     esi, 400h
0x14003549e  sub     ecx, edi
0x1400354a0  jz      loc_1400355D9
0x1400354a6  sub     ecx, edi
0x1400354a8  jz      loc_140035596
0x1400354ae  sub     ecx, edi
0x1400354b0  jz      short loc_1400354BF
0x1400354b2  cmp     ecx, edi
0x1400354b4  jz      loc_14003562F
0x1400354ba  jmp     loc_1400356B3
0x1400354bf  lea     r8, aPath_0; " -path \""
0x1400354c6  mov     rdx, rsi; unsigned __int64
0x1400354c9  mov     rcx, r14; unsigned __int16 *
0x1400354cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400354d1  mov     ebx, eax
0x1400354d3  test    eax, eax
0x1400354d5  jns     short loc_1400354FB
0x1400354d7  mov     r9d, 8BFh
0x1400354dd  lea     r8, aConfigurationG_0; "Configuration::GetFullyQualifiedArgumen"...
0x1400354e4  mov     [rsp+0A8h+var_88], eax
0x1400354e8  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400354ef  mov     ecx, edi; Level
0x1400354f1  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400354f6  jmp     loc_140035C7B
0x1400354fb  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140035500  mov     r8, rax; unsigned __int16 *
0x140035503  mov     rdx, rsi; unsigned __int64
0x140035506  mov     rcx, r14; unsigned __int16 *
0x140035509  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003550e  mov     ebx, eax
0x140035510  test    eax, eax
0x140035512  jns     short loc_14003551C
0x140035514  mov     r9d, 8C2h
0x14003551a  jmp     short loc_1400354DD
0x14003551c  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140035521  test    rax, rax
0x140035524  jz      short loc_14003556F
0x140035526  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x14003552b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003552f  xor     ecx, ecx
0x140035531  inc     rbx
0x140035534  cmp     [rax+rbx*2], cx
0x140035538  jnz     short loc_140035531
0x14003553a  cmp     rbx, rdi
0x14003553d  jbe     short loc_14003556F
0x14003553f  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140035544  cmp     word ptr [rax+rbx*2-2], 5Ch ; '\'
0x14003554a  jnz     short loc_14003556F
0x14003554c  lea     r8, asc_14006B250; "\\"
0x140035553  mov     rdx, rsi; unsigned __int64
0x140035556  mov     rcx, r14; unsigned __int16 *
0x140035559  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003555e  mov     ebx, eax
0x140035560  test    eax, eax
0x140035562  jns     short loc_14003556F
0x140035564  mov     r9d, 8D1h
0x14003556a  jmp     loc_1400354DD
0x14003556f  lea     r8, asc_1400701E0; "\""
0x140035576  mov     rdx, rsi; unsigned __int64
0x140035579  mov     rcx, r14; unsigned __int16 *
0x14003557c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035581  mov     ebx, eax
0x140035583  test    eax, eax
0x140035585  jns     loc_14003579E
0x14003558b  mov     r9d, 8D6h
0x140035591  jmp     loc_1400354DD
0x140035596  lea     r8, aDci; " -dci "
0x14003559d  mov     rdx, rsi; unsigned __int64
0x1400355a0  mov     rcx, r14; unsigned __int16 *
0x1400355a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400355a8  mov     ebx, eax
0x1400355aa  test    eax, eax
0x1400355ac  jns     short loc_1400355B9
0x1400355ae  mov     r9d, 8DBh
0x1400355b4  jmp     loc_1400354DD
0x1400355b9  mov     r8, [rbp+70h]; unsigned __int16 *
0x1400355bd  mov     rdx, rsi; unsigned __int64
0x1400355c0  mov     rcx, r14; unsigned __int16 *
0x1400355c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400355c8  mov     ebx, eax
0x1400355ca  test    eax, eax
0x1400355cc  jns     short loc_1400355D9
0x1400355ce  mov     r9d, 8DEh
0x1400355d4  jmp     loc_1400354DD
0x1400355d9  cmp     [rbp+60h], r13
0x1400355dd  jz      loc_14003579E
0x1400355e3  lea     r8, aSp_0; " -sp "
0x1400355ea  mov     rdx, rsi; unsigned __int64
0x1400355ed  mov     rcx, r14; unsigned __int16 *
0x1400355f0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400355f5  mov     ebx, eax
0x1400355f7  test    eax, eax
0x1400355f9  jns     short loc_140035606
0x1400355fb  mov     r9d, 8E8h
0x140035601  jmp     loc_1400354DD
0x140035606  mov     r8, [rbp+60h]; unsigned __int16 *
0x14003560a  mov     rdx, rsi; unsigned __int64
0x14003560d  mov     rcx, r14; unsigned __int16 *
0x140035610  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035615  mov     ebx, eax
0x140035617  test    eax, eax
0x140035619  jns     loc_14003579E
0x14003561f  mov     r9d, 8EBh
0x140035625  jmp     loc_1400354DD
0x14003562a  mov     esi, 400h
0x14003562f  lea     r8, aCab; " -cab \""
0x140035636  mov     rdx, rsi; unsigned __int64
0x140035639  mov     rcx, r14; unsigned __int16 *
0x14003563c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035641  mov     ebx, eax
0x140035643  test    eax, eax
0x140035645  jns     short loc_140035652
0x140035647  mov     r9d, 8A8h
0x14003564d  jmp     loc_1400354DD
0x140035652  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x140035657  mov     r8, rax; unsigned __int16 *
0x14003565a  mov     rdx, rsi; unsigned __int64
0x14003565d  mov     rcx, r14; unsigned __int16 *
0x140035660  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035665  mov     ebx, eax
0x140035667  test    eax, eax
0x140035669  jns     short loc_140035676
0x14003566b  mov     r9d, 8ABh
0x140035671  jmp     loc_1400354DD
0x140035676  lea     r8, asc_1400701E0; "\""
0x14003567d  mov     rdx, rsi; unsigned __int64
0x140035680  mov     rcx, r14; unsigned __int16 *
0x140035683  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035688  mov     ebx, eax
0x14003568a  test    eax, eax
0x14003568c  jns     loc_14003579E
0x140035692  mov     r9d, 8AEh
0x140035698  jmp     loc_1400354DD
0x14003569d  sub     ecx, 7
0x1400356a0  jz      loc_140035730
0x1400356a6  sub     ecx, edi
0x1400356a8  jz      short loc_1400356C5
0x1400356aa  sub     ecx, edi
0x1400356ac  jz      short loc_1400356C5
0x1400356ae  cmp     ecx, 3
0x1400356b1  jz      short loc_1400356C5
0x1400356b3  mov     eax, 80004005h
0x1400356b8  mov     r9d, 8F1h
0x1400356be  mov     ebx, eax
0x1400356c0  jmp     loc_1400354DD
0x1400356c5  mov     esi, 400h
0x1400356ca  lea     r8, aId; " -id "
0x1400356d1  mov     edx, esi; unsigned __int64
0x1400356d3  mov     rcx, r14; unsigned __int16 *
0x1400356d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400356db  mov     ebx, eax
0x1400356dd  test    eax, eax
0x1400356df  jns     short loc_1400356EC
0x1400356e1  mov     r9d, 89Dh
0x1400356e7  jmp     loc_1400354DD
0x1400356ec  call    ?Packages_ID@@YAPEAGXZ; Packages_ID(void)
0x1400356f1  mov     r8, rax; unsigned __int16 *
0x1400356f4  mov     rdx, rsi; unsigned __int64
0x1400356f7  mov     rcx, r14; unsigned __int16 *
0x1400356fa  mov     r13, rax
0x1400356fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035702  mov     ebx, eax
0x140035704  test    eax, eax
0x140035706  jns     loc_14003579E
0x14003570c  mov     r9d, 8A2h
0x140035712  lea     r8, aConfigurationG_0; "Configuration::GetFullyQualifiedArgumen"...
0x140035719  mov     [rsp+0A8h+var_88], eax
0x14003571d  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140035724  mov     ecx, edi; Level
0x140035726  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003572b  jmp     loc_140035C62
0x140035730  mov     esi, 400h
0x140035735  lea     r8, aPath_0; " -path \""
0x14003573c  mov     edx, esi; unsigned __int64
0x14003573e  mov     rcx, r14; unsigned __int16 *
0x140035741  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035746  mov     ebx, eax
0x140035748  test    eax, eax
0x14003574a  jns     short loc_140035757
0x14003574c  mov     r9d, 8B4h
0x140035752  jmp     loc_1400354DD
0x140035757  call    ?Packages_GetPath@@YAPEBGXZ; Packages_GetPath(void)
0x14003575c  mov     r8, rax; unsigned __int16 *
0x14003575f  mov     rdx, rsi; unsigned __int64
0x140035762  mov     rcx, r14; unsigned __int16 *
0x140035765  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003576a  mov     ebx, eax
0x14003576c  test    eax, eax
0x14003576e  jns     short loc_14003577B
0x140035770  mov     r9d, 8B7h
0x140035776  jmp     loc_1400354DD
0x14003577b  lea     r8, asc_1400701E0; "\""
0x140035782  mov     rdx, rsi; unsigned __int64
0x140035785  mov     rcx, r14; unsigned __int16 *
0x140035788  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003578d  mov     ebx, eax
0x14003578f  test    eax, eax
0x140035791  jns     short loc_14003579E
0x140035793  mov     r9d, 8BAh
0x140035799  jmp     loc_1400354DD
0x14003579e  cmp     qword ptr [rbp+0D8h], 0
0x1400357a6  jz      short loc_1400357EE
0x1400357a8  lea     r8, aContext_1; " -context "
0x1400357af  mov     rdx, rsi; unsigned __int64
0x1400357b2  mov     rcx, r14; unsigned __int16 *
0x1400357b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400357ba  mov     ebx, eax
0x1400357bc  test    eax, eax
0x1400357be  jns     short loc_1400357CB
0x1400357c0  mov     r9d, 8F9h
0x1400357c6  jmp     loc_140035712
0x1400357cb  mov     r8, [rbp+0D8h]; unsigned __int16 *
0x1400357d2  mov     rdx, rsi; unsigned __int64
0x1400357d5  mov     rcx, r14; unsigned __int16 *
0x1400357d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400357dd  mov     ebx, eax
0x1400357df  test    eax, eax
0x1400357e1  jns     short loc_1400357EE
0x1400357e3  mov     r9d, 8FCh
0x1400357e9  jmp     loc_140035712
0x1400357ee  cmp     dword ptr [rbp+20h], 0
0x1400357f2  jz      short loc_140035817
0x1400357f4  lea     r8, aDisconnectedYe; " -disconnected yes"
0x1400357fb  mov     rdx, rsi; unsigned __int64
0x1400357fe  mov     rcx, r14; unsigned __int16 *
0x140035801  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035806  mov     ebx, eax
0x140035808  test    eax, eax
0x14003580a  jns     short loc_140035817
0x14003580c  mov     r9d, 907h
0x140035812  jmp     loc_140035712
0x140035817  cmp     dword ptr [rbp+14h], 0
0x14003581b  jz      loc_140035922
0x140035821  lea     r8, aElev; " -elev "
0x140035828  mov     rdx, rsi; unsigned __int64
0x14003582b  mov     rcx, r14; unsigned __int16 *
0x14003582e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140035833  mov     ebx, eax
0x140035835  test    eax, eax
0x140035837  jns     short loc_140035844
0x140035839  mov     r9d, 90Ch
0x14003583f  jmp     loc_140035712
0x140035844  call    cs:__imp_GetProcessHeap
0x14003584b  nop     dword ptr [rax+rax+00h]
0x140035850  xor     edx, edx; dwFlags
0x140035852  mov     r8d, 200h; dwBytes
0x140035858  mov     rcx, rax; hHeap
0x14003585b  call    cs:__imp_HeapAlloc
0x140035862  nop     dword ptr [rax+rax+00h]
0x140035867  mov     [rsp+0A8h+lpMem], rax
0x14003586c  mov     rbx, rax
0x14003586f  test    rax, rax
  ... truncated ...
```
