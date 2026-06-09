# GetTimeStamp(ushort *,ushort *,_FILETIME *)

- ea: `0x18001e718`
- end: `0x18001e9a2`
- name: `?GetTimeStamp@@YAJPEAG0PEAU_FILETIME@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(LPCWSTR lpString, unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180020e0c`

## callees

- `0x18001e718`
- `0x18001ea74`
- `0x180031010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18001e7df`
- `KERNEL32!lstrlenW` at `0x18001e80b`
- `KERNEL32!lstrlenW` at `0x18001e7df`
- `KERNEL32!lstrlenW` at `0x18001e80b`
- `IisRTL!PuDbgPrintW` at `0x18001e7ba`
- `IisRTL!PuDbgPrintW` at `0x18001e8a5`
- `IisRTL!PuDbgPrintW` at `0x18001e947`
- `IisRTL!PuDbgPrintW` at `0x18001e7ba`
- `IisRTL!PuDbgPrintW` at `0x18001e8a5`
- `IisRTL!PuDbgPrintW` at `0x18001e947`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18001e776`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18001e776`

## string_xrefs

- `0x18001e7a8`: `[GetTimeStamp] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18001e8f5`: `[GetTimeStamp] Unable to read %s. GetGlobalValue failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall GetTimeStamp(LPCWSTR lpString, unsigned __int16 *a2, struct _FILETIME *a3)
{
  int SimpleObjectByIDEx; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  int Value; // eax
  void **v12; // [rsp+28h] [rbp-51h]
  __int64 v13; // [rsp+30h] [rbp-49h]
  __int64 v14; // [rsp+38h] [rbp-41h]
  int v15; // [rsp+50h] [rbp-29h] BYREF
  struct ISimpleTableRead2 *v16; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h] BYREF
  void *v18; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR v19; // [rsp+70h] [rbp-9h] BYREF
  int v20; // [rsp+78h] [rbp-1h]
  int v21; // [rsp+7Ch] [rbp+3h]
  int v22; // [rsp+80h] [rbp+7h]
  int v23; // [rsp+84h] [rbp+Bh]
  const WCHAR *v24; // [rsp+88h] [rbp+Fh]
  int v25; // [rsp+90h] [rbp+17h]
  int v26; // [rsp+94h] [rbp+1Bh]
  int v27; // [rsp+98h] [rbp+1Fh]
  int v28; // [rsp+9Ch] [rbp+23h]
  unsigned int v29; // [rsp+F8h] [rbp+7Fh] BYREF

  v17 = 0;
  v16 = 0;
  v15 = 2;
  v29 = 0;
  v18 = 0;
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v17, L"IIS");
  v7 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx >= 0 )
  {
    v19 = lpString;
    v22 = 130;
    v20 = 2;
    v21 = -268435455;
    v8 = lstrlenW(lpString);
    v25 = 2;
    v24 = L".";
    v26 = 4;
    v27 = 130;
    v23 = 2 * v8 + 2;
    v28 = 2 * lstrlenW(L".") + 2;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, LPCWSTR *, int *, int, _DWORD, struct ISimpleTableRead2 **))(*(_QWORD *)v17 + 24LL))(
           v17,
           L"METABASE",
           L"MBProperty",
           &v19,
           &v15,
           3,
           0,
           &v16);
    v7 = v9;
    if ( v9 >= 0 )
    {
      Value = GetValue(v16, L".", 0x34u, a2, &v29, &v18);
      v7 = Value;
      if ( Value >= 0 )
      {
        if ( v29 == 8 )
        {
          *a3 = *(struct _FILETIME *)v18;
        }
        else
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(v14) = 8;
            LODWORD(v12) = v29;
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
              13459,
              "GetTimeStamp",
              L"[GetTimeStamp] GetGlobalValue returns incorrect count of bytes %d for %s. Expected %d.\n",
              v12,
              a2,
              v14);
          }
          v7 = -2147024883;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v13) = Value;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          13448,
          "GetTimeStamp",
          L"[GetTimeStamp] Unable to read %s. GetGlobalValue failed with hr = 0x%x.\n",
          a2,
          v13);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v13) = v9;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        13428,
        "GetTimeStamp",
        L"[GetTimeStamp] GetTable on %s failed with hr = 0x%x.\n",
        L"MBProperty",
        v13);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      13394,
      "GetTimeStamp",
      L"[GetTimeStamp] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
      SimpleObjectByIDEx);
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead2 *))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return v7;
}

```

## disassembly

```asm
0x18001e718  push    rbp
0x18001e71a  push    rbx
0x18001e71b  push    rsi
0x18001e71c  push    rdi
0x18001e71d  push    r12
0x18001e71f  push    r14
0x18001e721  lea     rbp, [rsp-2Fh]
0x18001e726  sub     rsp, 0A8h
0x18001e72d  mov     r12d, 2
0x18001e733  mov     [rbp+57h+var_70], 0
0x18001e73b  mov     rsi, r8
0x18001e73e  mov     [rbp+57h+var_78], 0
0x18001e746  mov     rdi, rdx
0x18001e749  mov     [rbp+57h+var_80], r12d
0x18001e74d  mov     r14, rcx
0x18001e750  mov     [rbp+57h+arg_18], 0
0x18001e757  lea     ecx, [r12-1]
0x18001e75c  mov     [rbp+57h+var_68], 0
0x18001e764  lea     r9, aIis; "IIS"
0x18001e76b  lea     r8, [rbp+57h+var_70]
0x18001e76f  lea     rdx, IID_ISimpleTableDispenser2
0x18001e776  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18001e77c  mov     ebx, eax
0x18001e77e  test    eax, eax
0x18001e780  jns     short loc_18001E7C5
0x18001e782  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e789  jz      loc_18001E95E
0x18001e78f  mov     rcx, cs:g_pDebug
0x18001e796  lea     r9, aGettimestamp; "GetTimeStamp"
0x18001e79d  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18001e7a1  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e7a8  lea     rax, aGettimestampDl; "[GetTimeStamp] DllGetSimpleObjectByIDEx"...
0x18001e7af  mov     r8d, 3452h
0x18001e7b5  mov     [rsp+0D0h+var_B0], rax
0x18001e7ba  call    cs:__imp_PuDbgPrintW
0x18001e7c0  jmp     loc_18001E95E
0x18001e7c5  mov     ebx, 82h
0x18001e7ca  mov     [rbp+57h+var_60], r14
0x18001e7ce  mov     rcx, r14; lpString
0x18001e7d1  mov     [rbp+57h+var_50], ebx
0x18001e7d4  mov     [rbp+57h+var_58], r12d
0x18001e7d8  mov     [rbp+57h+var_54], 0F0000001h
0x18001e7df  call    cs:__imp_lstrlenW
0x18001e7e5  lea     r14, String; "."
0x18001e7ec  mov     [rbp+57h+var_40], r12d
0x18001e7f0  mov     rcx, r14; lpString
0x18001e7f3  mov     [rbp+57h+var_48], r14
0x18001e7f7  mov     [rbp+57h+var_3C], 4
0x18001e7fe  lea     eax, ds:2[rax*2]
0x18001e805  mov     [rbp+57h+var_38], ebx
0x18001e808  mov     [rbp+57h+var_4C], eax
0x18001e80b  call    cs:__imp_lstrlenW
0x18001e811  mov     rcx, [rbp+57h+var_70]
0x18001e815  lea     rdx, [rbp+57h+var_78]
0x18001e819  mov     [rsp+0D0h+var_98], rdx
0x18001e81e  lea     r12, aMbproperty_0; "MBProperty"
0x18001e825  mov     dword ptr [rsp+0D0h+var_A0], 0
0x18001e82d  lea     rdx, [rbp+57h+var_80]
0x18001e831  lea     eax, ds:2[rax*2]
0x18001e838  mov     dword ptr [rsp+0D0h+var_A8], 3
0x18001e840  mov     [rbp+57h+var_34], eax
0x18001e843  lea     r9, [rbp+57h+var_60]
0x18001e847  mov     rax, [rcx]
0x18001e84a  mov     r8, r12
0x18001e84d  mov     [rsp+0D0h+var_B0], rdx
0x18001e852  lea     rdx, aMetabase; "METABASE"
0x18001e859  mov     rax, [rax+18h]
0x18001e85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e862  mov     ebx, eax
0x18001e864  test    eax, eax
0x18001e866  jns     short loc_18001E8B0
0x18001e868  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e86f  jz      loc_18001E95E
0x18001e875  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18001e879  mov     r8d, 3474h
0x18001e87f  mov     [rsp+0D0h+var_A8], r12
0x18001e884  lea     rax, aGettimestampGe_0; "[GetTimeStamp] GetTable on %s failed wi"...
0x18001e88b  mov     rcx, cs:g_pDebug
0x18001e892  lea     r9, aGettimestamp; "GetTimeStamp"
0x18001e899  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e8a0  mov     [rsp+0D0h+var_B0], rax
0x18001e8a5  call    cs:__imp_PuDbgPrintW
0x18001e8ab  jmp     loc_18001E95E
0x18001e8b0  mov     rcx, [rbp+57h+var_78]; struct ISimpleTableRead2 *
0x18001e8b4  lea     rax, [rbp+57h+var_68]
0x18001e8b8  mov     [rsp+0D0h+var_A8], rax; void **
0x18001e8bd  mov     r9, rdi; unsigned __int16 *
0x18001e8c0  lea     rax, [rbp+57h+arg_18]
0x18001e8c4  mov     r8d, 34h ; '4'; unsigned int
0x18001e8ca  mov     rdx, r14; unsigned __int16 *
0x18001e8cd  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x18001e8d2  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001e8d7  mov     ebx, eax
0x18001e8d9  test    eax, eax
0x18001e8db  jns     short loc_18001E8FE
0x18001e8dd  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e8e4  jz      short loc_18001E95E
0x18001e8e6  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18001e8ea  mov     r8d, 3488h
0x18001e8f0  mov     [rsp+0D0h+var_A8], rdi
0x18001e8f5  lea     rax, aGettimestampUn; "[GetTimeStamp] Unable to read %s. GetGl"...
0x18001e8fc  jmp     short loc_18001E88B
0x18001e8fe  mov     eax, [rbp+57h+arg_18]
0x18001e901  cmp     eax, 8
0x18001e904  jz      short loc_18001E954
0x18001e906  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e90d  jz      short loc_18001E94D
0x18001e90f  mov     rcx, cs:g_pDebug
0x18001e916  lea     r9, aGettimestamp; "GetTimeStamp"
0x18001e91d  mov     dword ptr [rsp+0D0h+var_98], 8
0x18001e925  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e92c  mov     [rsp+0D0h+var_A0], rdi
0x18001e931  mov     r8d, 3493h
0x18001e937  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18001e93b  lea     rax, aGettimestampGe; "[GetTimeStamp] GetGlobalValue returns i"...
0x18001e942  mov     [rsp+0D0h+var_B0], rax
0x18001e947  call    cs:__imp_PuDbgPrintW
0x18001e94d  mov     ebx, 8007000Dh
0x18001e952  jmp     short loc_18001E95E
0x18001e954  mov     rax, [rbp+57h+var_68]
0x18001e958  mov     rcx, [rax]
0x18001e95b  mov     [rsi], rcx
0x18001e95e  mov     rcx, [rbp+57h+var_78]
0x18001e962  test    rcx, rcx
0x18001e965  jz      short loc_18001E97B
0x18001e967  mov     rax, [rcx]
0x18001e96a  mov     rax, [rax+10h]
0x18001e96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e973  mov     [rbp+57h+var_78], 0
0x18001e97b  mov     rcx, [rbp+57h+var_70]
0x18001e97f  test    rcx, rcx
0x18001e982  jz      short loc_18001E990
0x18001e984  mov     rax, [rcx]
0x18001e987  mov     rax, [rax+10h]
0x18001e98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e990  mov     eax, ebx
0x18001e992  add     rsp, 0A8h
0x18001e999  pop     r14
0x18001e99b  pop     r12
0x18001e99d  pop     rdi
0x18001e99e  pop     rsi
0x18001e99f  pop     rbx
0x18001e9a0  pop     rbp
0x18001e9a1  retn
```
