# CWppAutoTrace::SetConfiguration(ushort const *,ushort const *,ushort const *,_GUID const *,ulong)

- ea: `0x180078e80`
- end: `0x180079808`
- name: `?SetConfiguration@CWppAutoTrace@@UEAAJPEBG00PEBU_GUID@@K@Z`
- size: `2440`
- prototype: `int(CWppAutoTrace *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800091a8`
- `0x18000e420`
- `0x18001569c`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x180034970`
- `0x180059838`
- `0x1800598d0`
- `0x180063160`
- `0x180072abc`
- `0x180073258`
- `0x180078918`
- `0x1800789fc`
- `0x180078e80`
- `0x18014c328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007961b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007961b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180079591`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180079591`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180079136`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800792cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180079136`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800792cb`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800794ae`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180079539`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800794ae`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180079539`

## string_xrefs

- `0x180079189`: `Invalid CapturePath`
- `0x180079117`: `CapturePath`
- `0x18007931e`: `Invalid CompletedPath`
- `0x180079210`: `Capture path length`
- `0x180079697`: `CWppAutoTrace::CreatePath`
- `0x18007938f`: `Completed path length`
- `0x1800796ed`: `CWppAutoTrace::DeleteOldFiles`

## pseudocode

```c
__int64 __fastcall CWppAutoTrace::SetConfiguration(
        CWppAutoTrace *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const struct _GUID *Src,
        unsigned int a6)
{
  PVOID *v10; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const wchar_t *v12; // rcx
  unsigned int v13; // eax
  int Path; // ebx
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  unsigned int v18; // eax
  int v19; // edx
  const char *v20; // rcx
  DWORD v21; // eax
  unsigned int v22; // eax
  int v23; // edx
  const char *v24; // rcx
  PVOID *v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // eax
  DWORD v28; // eax
  unsigned int v29; // eax
  __int64 v30; // r8
  ULONG v31; // eax
  char v32; // bl
  unsigned int v33; // eax
  int v34; // edx
  ULONG v35; // eax
  const WCHAR *v36; // rsi
  char LastError; // bl
  unsigned int v38; // eax
  CWppAutoTrace *v39; // rcx
  unsigned int v40; // r9d
  CWppAutoTrace *v41; // rcx
  unsigned int v42; // r9d
  unsigned int v43; // eax
  __int64 v45; // [rsp+28h] [rbp-330h]
  _EVENT_TRACE_PROPERTIES Properties; // [rsp+30h] [rbp-328h] BYREF

  memset_0(&Properties, 0, 0x2D0u);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = a2;
    if ( !a2 )
      v12 = L"NULL";
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v12);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 8) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
        v13,
        -2147418113);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    Path = -2147418113;
    goto LABEL_134;
  }
  *((_BYTE *)this + 24) = 0;
  if ( !a2 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 17;
    v17 = "SessionName";
LABEL_19:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v15,
      (__int64)v17);
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
    Path = -2147467261;
    goto LABEL_134;
  }
  if ( *a2 )
  {
    if ( !Src )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 19;
      v17 = "pProviderIds";
      goto LABEL_19;
    }
    if ( !a6 )
    {
      Path = -2147024883;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)Path;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_134;
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = a6 + 20;
      v20 = "Invalid ProviderId count";
      goto LABEL_26;
    }
    if ( !a3 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 21;
      v17 = "CapturePath";
      goto LABEL_19;
    }
    v21 = ExpandEnvironmentStringsW(a3, (LPWSTR)this + 328, 0x104u);
    if ( v21 - 1 > 0x102 )
    {
      Path = -2147024883;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)Path;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_134;
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 23;
      LODWORD(v45) = -2147024883;
      v24 = "Invalid CapturePath";
      goto LABEL_47;
    }
    if ( *((_WORD *)this + v21 + 327) != 92 )
    {
      Path = StringCchCatW((unsigned __int16 *)this + 328, 0x104u, L"\\");
      if ( Path < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_134;
        }
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        v23 = 24;
        LODWORD(v45) = Path;
        v24 = "Capture path length";
        goto LABEL_47;
      }
    }
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
        v26,
        (__int64)this + 656);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a4 )
    {
      v28 = ExpandEnvironmentStringsW(a4, (LPWSTR)this + 588, 0x104u);
      if ( v28 - 1 > 0x102 )
      {
        Path = -2147024883;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return (unsigned int)Path;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_134;
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        v23 = 27;
        LODWORD(v45) = -2147024883;
        v24 = "Invalid CompletedPath";
        goto LABEL_47;
      }
      if ( *((_WORD *)this + v28 + 587) != 92 )
      {
        Path = StringCchCatW((unsigned __int16 *)this + 588, 0x104u, L"\\");
        if ( Path < 0 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_134;
          }
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          v23 = 28;
          LODWORD(v45) = Path;
          v24 = "Completed path length";
          goto LABEL_47;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
          v29,
          (__int64)this + 1176);
      }
    }
    else
    {
      if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 7) & 0x400) != 0 && *((_BYTE *)v25 + 25) >= 5u )
      {
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v27);
      }
      *((_WORD *)this + 588) = 0;
    }
    Path = StringCchCopyW((unsigned __int16 *)this + 288, 0x28u, a2);
    if ( Path < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 30;
      LODWORD(v45) = Path;
      v24 = "Invalid SessionName";
      goto LABEL_47;
    }
    memset_0((char *)this + 28, 0, 0x200u);
    v30 = a6;
    if ( a6 >= 0x20 )
      v30 = 32;
    memcpy_0((char *)this + 28, Src, 16 * v30);
    memset_0(&Properties, 0, 0x2D0u);
    Properties.Wnode.BufferSize = 720;
    Properties.Wnode.Flags = 0x20000;
    v31 = ControlTraceW(0, (LPCWSTR)this + 288, &Properties, 0);
    v32 = v31;
    if ( v31 != 4201 )
    {
      if ( v31 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v33 = RdpWppGetCurrentThreadActivityIdPrefix();
        v34 = 31;
LABEL_92:
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v34,
          (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
          v33,
          (__int64)this + 576,
          v32);
        v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_93:
        Path = -2147467259;
        goto LABEL_134;
      }
      v35 = ControlTraceW(Properties.Wnode.HistoricalContext, 0, &Properties, 1u);
      v32 = v35;
      if ( v35 != 4201 )
      {
        if ( v35 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_93;
          }
          v33 = RdpWppGetCurrentThreadActivityIdPrefix();
          v34 = 32;
          goto LABEL_92;
        }
        v36 = (const WCHAR *)((char *)&Properties + Properties.LogFileNameOffset);
        if ( DeleteFileW(v36) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)this + 576, (__int64)v36);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          LastError = GetLastError();
          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
            v38,
            (__int64)v36,
            LastError);
        }
      }
    }
    Path = CWppAutoTrace::CreatePath((LPCWSTR)this + 328);
    if ( Path < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 35;
LABEL_114:
      LODWORD(v45) = Path;
      v24 = "CWppAutoTrace::CreatePath";
LABEL_47:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
        v22,
        (__int64)v24,
        v45);
LABEL_133:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_134;
    }
    Path = CWppAutoTrace::DeleteOldFiles(
             v39,
             (const unsigned __int16 *)this + 328,
             (const unsigned __int16 *)this + 288,
             v40);
    if ( Path >= 0 )
    {
      if ( !*((_WORD *)this + 588) )
        goto LABEL_132;
      Path = CWppAutoTrace::CreatePath((LPCWSTR)this + 588);
      if ( Path < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_134;
        }
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        v23 = 37;
        goto LABEL_114;
      }
      Path = CWppAutoTrace::DeleteOldFiles(
               v41,
               (const unsigned __int16 *)this + 588,
               (const unsigned __int16 *)this + 288,
               v42);
      if ( Path >= 0 )
      {
LABEL_132:
        *((_BYTE *)this + 8) = 1;
        goto LABEL_133;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 38;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 36;
    }
    LODWORD(v45) = Path;
    v24 = "CWppAutoTrace::DeleteOldFiles";
    goto LABEL_47;
  }
  Path = -2147024883;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)Path;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    v19 = 18;
    v20 = "Invalid SessionName";
LABEL_26:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v18,
      (__int64)v20,
      -2147024883);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_134:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x400) != 0 && *((_BYTE *)v10 + 25) >= 5u )
  {
    v43 = RdpWppGetCurrentThreadActivityIdPrefix();
    if ( !a2 )
      a2 = L"NULL";
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v43,
      (__int64)a2,
      Path);
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x180078e80  push    rbx
0x180078e82  push    rbp
0x180078e83  push    rsi
0x180078e84  push    rdi
0x180078e85  push    r12
0x180078e87  push    r13
0x180078e89  push    r14
0x180078e8b  push    r15
0x180078e8d  sub     rsp, 318h
0x180078e94  mov     rax, cs:__security_cookie
0x180078e9b  xor     rax, rsp
0x180078e9e  mov     [rsp+358h+var_58], rax
0x180078ea6  mov     r12, [rsp+358h+Src]
0x180078eae  mov     rbx, r8
0x180078eb1  mov     r13, rdx
0x180078eb4  mov     rdi, rcx
0x180078eb7  xor     edx, edx; Val
0x180078eb9  lea     rcx, [rsp+358h+Properties]; void *
0x180078ebe  mov     r8d, 2D0h; Size
0x180078ec4  mov     rbp, r9
0x180078ec7  call    memset_0
0x180078ecc  mov     rax, cs:WPP_GLOBAL_Control
0x180078ed3  lea     rcx, WPP_GLOBAL_Control
0x180078eda  xor     r14d, r14d
0x180078edd  lea     r15, aNull_0; "NULL"
0x180078ee4  lea     rsi, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x180078eeb  cmp     rax, rcx
0x180078eee  jz      short loc_180078F3B
0x180078ef0  test    dword ptr [rax+1Ch], 400h
0x180078ef7  jz      short loc_180078F3B
0x180078ef9  cmp     byte ptr [rax+19h], 5
0x180078efd  jb      short loc_180078F3B
0x180078eff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078f04  test    r13, r13
0x180078f07  lea     edx, [r14+0Fh]
0x180078f0b  mov     rcx, r13
0x180078f0e  mov     r9d, eax
0x180078f11  cmovz   rcx, r15
0x180078f15  mov     r8, rsi
0x180078f18  mov     [rsp+358h+var_338], rcx
0x180078f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f24  mov     rcx, [rcx+10h]
0x180078f28  call    WPP_SF_DS
0x180078f2d  mov     rax, cs:WPP_GLOBAL_Control
0x180078f34  lea     rcx, WPP_GLOBAL_Control
0x180078f3b  cmp     [rdi+8], r14b
0x180078f3f  jz      short loc_180078F92
0x180078f41  cmp     rax, rcx
0x180078f44  jz      short loc_180078F81
0x180078f46  test    byte ptr [rax+1Ch], 8
0x180078f4a  jz      short loc_180078F81
0x180078f4c  cmp     byte ptr [rax+19h], 2
0x180078f50  jb      short loc_180078F81
0x180078f52  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180078f5e  mov     edx, 10h
0x180078f63  mov     r9d, eax
0x180078f66  mov     dword ptr [rsp+358h+var_338], 8000FFFFh
0x180078f6e  mov     r8, rsi
0x180078f71  mov     rcx, [rcx+10h]
0x180078f75  call    WPP_SF_Dd
0x180078f7a  mov     rax, cs:WPP_GLOBAL_Control
0x180078f81  mov     ebx, 8000FFFFh
0x180078f86  lea     rdi, WPP_GLOBAL_Control
0x180078f8d  jmp     loc_18007979A
0x180078f92  mov     [rdi+18h], r14b
0x180078f96  test    r13, r13
0x180078f99  jnz     short loc_180078FEC
0x180078f9b  mov     rax, cs:WPP_GLOBAL_Control
0x180078fa2  cmp     rax, rcx
0x180078fa5  jz      short loc_180078FE5
0x180078fa7  test    byte ptr [rax+1Ch], 8
0x180078fab  jz      short loc_180078FE5
0x180078fad  cmp     byte ptr [rax+19h], 2
0x180078fb1  jb      short loc_180078FE5
0x180078fb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078fb8  lea     edx, [r13+11h]
0x180078fbc  lea     rcx, aSessionname; "SessionName"
0x180078fc3  mov     [rsp+358h+var_338], rcx
0x180078fc8  mov     r9d, eax
0x180078fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180078fd2  mov     r8, rsi
0x180078fd5  mov     rcx, [rcx+10h]
0x180078fd9  call    WPP_SF_Ds
0x180078fde  mov     rax, cs:WPP_GLOBAL_Control
0x180078fe5  mov     ebx, 80004003h
0x180078fea  jmp     short loc_180078F86
0x180078fec  cmp     [r13+0], r14w
0x180078ff1  jnz     short loc_18007905C
0x180078ff3  mov     ebx, 8007000Dh
0x180078ff8  mov     rax, cs:WPP_GLOBAL_Control
0x180078fff  cmp     rax, rcx
0x180079002  jz      loc_1800797E2
0x180079008  test    byte ptr [rax+1Ch], 8
0x18007900c  jz      loc_180078F86
0x180079012  cmp     byte ptr [rax+19h], 2
0x180079016  jb      loc_180078F86
0x18007901c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079021  mov     edx, 12h
0x180079026  lea     rcx, aInvalidSession; "Invalid SessionName"
0x18007902d  mov     dword ptr [rsp+358h+var_330], 8007000Dh
0x180079035  mov     r9d, eax
0x180079038  mov     [rsp+358h+var_338], rcx
0x18007903d  mov     r8, rsi
0x180079040  mov     rcx, cs:WPP_GLOBAL_Control
0x180079047  mov     rcx, [rcx+10h]
0x18007904b  call    WPP_SF_DsD
0x180079050  mov     rax, cs:WPP_GLOBAL_Control
0x180079057  jmp     loc_180078F86
0x18007905c  test    r12, r12
0x18007905f  jnz     short loc_18007909B
0x180079061  mov     rax, cs:WPP_GLOBAL_Control
0x180079068  cmp     rax, rcx
0x18007906b  jz      loc_180078FE5
0x180079071  test    byte ptr [rax+1Ch], 8
0x180079075  jz      loc_180078FE5
0x18007907b  cmp     byte ptr [rax+19h], 2
0x18007907f  jb      loc_180078FE5
0x180079085  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007908a  lea     edx, [r12+13h]
0x18007908f  lea     rcx, aPproviderids; "pProviderIds"
0x180079096  jmp     loc_180078FC3
0x18007909b  mov     r14d, [rsp+358h+arg_28]
0x1800790a3  test    r14d, r14d
0x1800790a6  jnz     short loc_1800790E6
0x1800790a8  mov     ebx, 8007000Dh
0x1800790ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800790b4  cmp     rax, rcx
0x1800790b7  jz      loc_1800797E2
0x1800790bd  test    byte ptr [rax+1Ch], 8
0x1800790c1  jz      loc_180078F86
0x1800790c7  cmp     byte ptr [rax+19h], 2
0x1800790cb  jb      loc_180078F86
0x1800790d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800790d6  lea     edx, [r14+14h]
0x1800790da  lea     rcx, aInvalidProvide; "Invalid ProviderId count"
0x1800790e1  jmp     loc_18007902D
0x1800790e6  test    rbx, rbx
0x1800790e9  jnz     short loc_180079123
0x1800790eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800790f2  cmp     rax, rcx
0x1800790f5  jz      loc_180078FE5
0x1800790fb  test    byte ptr [rax+1Ch], 8
0x1800790ff  jz      loc_180078FE5
0x180079105  cmp     byte ptr [rax+19h], 2
0x180079109  jb      loc_180078FE5
0x18007910f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079114  lea     edx, [rbx+15h]
0x180079117  lea     rcx, aCapturepath; "CapturePath"
0x18007911e  jmp     loc_180078FC3
0x180079123  lea     r15, [rdi+290h]
0x18007912a  mov     r8d, 104h; nSize
0x180079130  mov     rdx, r15; lpDst
0x180079133  mov     rcx, rbx; lpSrc
0x180079136  call    cs:__imp_ExpandEnvironmentStringsW
0x18007913c  lea     ecx, [rax-1]
0x18007913f  cmp     ecx, 102h
0x180079145  jbe     short loc_1800791B0
0x180079147  mov     ebx, 8007000Dh
0x18007914c  mov     rax, cs:WPP_GLOBAL_Control
0x180079153  lea     rdi, WPP_GLOBAL_Control
0x18007915a  cmp     rax, rdi
0x18007915d  jz      loc_1800797E2
0x180079163  test    byte ptr [rax+1Ch], 8
0x180079167  jz      loc_180079793
0x18007916d  cmp     byte ptr [rax+19h], 2
0x180079171  jb      loc_180079793
0x180079177  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007917c  mov     edx, 17h
0x180079181  mov     dword ptr [rsp+358h+var_330], 8007000Dh
0x180079189  lea     rcx, aInvalidCapture; "Invalid CapturePath"
0x180079190  mov     r8, rsi
0x180079193  mov     [rsp+358h+var_338], rcx
0x180079198  mov     r9d, eax
0x18007919b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791a2  mov     rcx, [rcx+10h]
0x1800791a6  call    WPP_SF_DsD
0x1800791ab  jmp     loc_18007978C
0x1800791b0  dec     eax
0x1800791b2  cmp     word ptr [rdi+rax*2+290h], 5Ch ; '\'
0x1800791bb  jz      short loc_18007921C
0x1800791bd  lea     r8, asc_180158700; "\\"
0x1800791c4  mov     edx, 104h; unsigned __int64
0x1800791c9  mov     rcx, r15; unsigned __int16 *
0x1800791cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800791d1  mov     ebx, eax
0x1800791d3  test    eax, eax
0x1800791d5  jns     short loc_18007921C
0x1800791d7  mov     rax, cs:WPP_GLOBAL_Control
0x1800791de  lea     rdi, WPP_GLOBAL_Control
0x1800791e5  cmp     rax, rdi
0x1800791e8  jz      loc_180079793
0x1800791ee  test    byte ptr [rax+1Ch], 8
0x1800791f2  jz      loc_180079793
0x1800791f8  cmp     byte ptr [rax+19h], 2
0x1800791fc  jb      loc_180079793
0x180079202  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079207  mov     edx, 18h
0x18007920c  mov     dword ptr [rsp+358h+var_330], ebx
0x180079210  lea     rcx, aCapturePathLen; "Capture path length"
0x180079217  jmp     loc_180079190
0x18007921c  mov     rax, cs:WPP_GLOBAL_Control
0x180079223  lea     rcx, WPP_GLOBAL_Control
0x18007922a  cmp     rax, rcx
0x18007922d  jz      short loc_180079271
0x18007922f  test    dword ptr [rax+1Ch], 400h
0x180079236  jz      short loc_180079271
0x180079238  cmp     byte ptr [rax+19h], 5
0x18007923c  jb      short loc_180079271
0x18007923e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079243  mov     rcx, cs:WPP_GLOBAL_Control
0x18007924a  mov     edx, 19h
0x18007924f  mov     r9d, eax
0x180079252  mov     [rsp+358h+var_338], r15
0x180079257  mov     r8, rsi
0x18007925a  mov     rcx, [rcx+10h]
0x18007925e  call    WPP_SF_DS
0x180079263  mov     rax, cs:WPP_GLOBAL_Control
0x18007926a  lea     rcx, WPP_GLOBAL_Control
0x180079271  test    rbp, rbp
0x180079274  jnz     short loc_1800792B6
0x180079276  cmp     rax, rcx
0x180079279  jz      short loc_1800792A8
0x18007927b  test    dword ptr [rax+1Ch], 400h
0x180079282  jz      short loc_1800792A8
0x180079284  cmp     byte ptr [rax+19h], 5
0x180079288  jb      short loc_1800792A8
0x18007928a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007928f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079296  lea     edx, [rbp+1Ah]
0x180079299  mov     r9d, eax
0x18007929c  mov     r8, rsi
0x18007929f  mov     rcx, [rcx+10h]
0x1800792a3  call    WPP_SF_d
0x1800792a8  xor     eax, eax
0x1800792aa  mov     [rdi+498h], ax
0x1800792b1  jmp     loc_1800793EF
0x1800792b6  lea     rsi, [rdi+498h]
0x1800792bd  mov     ebx, 104h
0x1800792c2  mov     r8d, ebx; nSize
0x1800792c5  mov     rdx, rsi; lpDst
0x1800792c8  mov     rcx, rbp; lpSrc
0x1800792cb  call    cs:__imp_ExpandEnvironmentStringsW
0x1800792d1  lea     ecx, [rax-1]
0x1800792d4  cmp     ecx, 102h
0x1800792da  jbe     short loc_180079331
0x1800792dc  mov     ebx, 8007000Dh
0x1800792e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800792e8  lea     rdi, WPP_GLOBAL_Control
0x1800792ef  cmp     rax, rdi
0x1800792f2  jz      loc_1800797E2
0x1800792f8  test    byte ptr [rax+1Ch], 8
0x1800792fc  jz      loc_180079793
0x180079302  cmp     byte ptr [rax+19h], 2
0x180079306  jb      loc_180079793
0x18007930c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079311  mov     edx, 1Bh
0x180079316  mov     dword ptr [rsp+358h+var_330], 8007000Dh
0x18007931e  lea     rcx, aInvalidComplet; "Invalid CompletedPath"
0x180079325  lea     r8, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x18007932c  jmp     loc_180079193
0x180079331  dec     eax
0x180079333  cmp     word ptr [rdi+rax*2+498h], 5Ch ; '\'
0x18007933c  jz      short loc_180079398
0x18007933e  lea     r8, asc_180158700; "\\"
0x180079345  mov     rdx, rbx; unsigned __int64
0x180079348  mov     rcx, rsi; unsigned __int16 *
0x18007934b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180079350  mov     ebx, eax
0x180079352  test    eax, eax
0x180079354  jns     short loc_180079398
0x180079356  mov     rax, cs:WPP_GLOBAL_Control
0x18007935d  lea     rdi, WPP_GLOBAL_Control
0x180079364  cmp     rax, rdi
0x180079367  jz      loc_180079793
0x18007936d  test    byte ptr [rax+1Ch], 8
0x180079371  jz      loc_180079793
0x180079377  cmp     byte ptr [rax+19h], 2
0x18007937b  jb      loc_180079793
0x180079381  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079386  mov     edx, 1Ch
0x18007938b  mov     dword ptr [rsp+358h+var_330], ebx
0x18007938f  lea     rcx, aCompletedPathL; "Completed path length"
0x180079396  jmp     short loc_180079325
0x180079398  mov     rax, cs:WPP_GLOBAL_Control
0x18007939f  lea     rcx, WPP_GLOBAL_Control
0x1800793a6  cmp     rax, rcx
0x1800793a9  jz      short loc_1800793E8
0x1800793ab  test    dword ptr [rax+1Ch], 400h
0x1800793b2  jz      short loc_1800793E8
0x1800793b4  cmp     byte ptr [rax+19h], 5
0x1800793b8  jb      short loc_1800793E8
0x1800793ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800793bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793c6  mov     edx, 1Dh
0x1800793cb  mov     [rsp+358h+var_338], rsi
0x1800793d0  mov     r9d, eax
0x1800793d3  lea     rsi, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x1800793da  mov     r8, rsi
0x1800793dd  mov     rcx, [rcx+10h]
  ... truncated ...
```
