# FILTER_LIST::LoadFilter(ushort const *,int,FILTER_FAILURE_POINT *)

- ea: `0x180006e10`
- end: `0x180006f3c`
- name: `?LoadFilter@FILTER_LIST@@AEAAJPEBGHPEAW4FILTER_FAILURE_POINT@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(FILTER_LIST *__hidden this, const unsigned __int16 *, int, enum FILTER_FAILURE_POINT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006aa0`

## callees

- `0x180006e10`
- `0x180006f50`
- `0x1800092fc`
- `0x18000a4d8`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006e7c`
- `iisutil!PuDbgPrint` at `0x180006efd`
- `iisutil!PuDbgPrint` at `0x180006e7c`
- `iisutil!PuDbgPrint` at `0x180006efd`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006ec2`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180006ec2`

## string_xrefs

- `0x180006e5e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x180006ef6`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x180006e65`: `Cannot load filter dll '%ws'.  hr = %x\n`
- `0x180006ed8`: `Refusing READ_RAW filter on site (%S)\n`

## pseudocode

```c
__int64 __fastcall FILTER_LIST::LoadFilter(
        FILTER_LIST *this,
        const unsigned __int16 *a2,
        int a3,
        enum FILTER_FAILURE_POINT *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  HTTP_FILTER_DLL *v10; // rbx
  int v11; // edi
  int v12; // [rsp+30h] [rbp-48h]
  struct HTTP_FILTER_DLL *v13[7]; // [rsp+40h] [rbp-38h] BYREF

  v13[0] = 0;
  v7 = HTTP_FILTER_DLL::OpenFilter(a2, a3, v13, a4);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = v13[0];
    if ( ((*((_DWORD *)v13[0] + 15) | *((_DWORD *)v13[0] + 16)) & 0x8000) != 0 )
    {
      v13[0] = (struct HTTP_FILTER_DLL *)a2;
      EVENT_LOG::LogEvent((EVENT_LOG *)g_pEventLog, 0xC00008D5, 1u, (const unsigned __int16 **const)v13, 0);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
          477,
          "FILTER_LIST::LoadFilter",
          "Refusing READ_RAW filter on site (%S)\n",
          a2);
      HTTP_FILTER_DLL::DereferenceFilterDll(v10);
      result = 2147942450LL;
      *(_DWORD *)a4 = 4;
    }
    else
    {
      v11 = FILTER_LIST::AddFilterToList(this, v13[0]);
      if ( v11 < 0 )
        HTTP_FILTER_DLL::DereferenceFilterDll(v10);
      return (unsigned int)v11;
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v12 = v7;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
        453,
        "FILTER_LIST::LoadFilter",
        "Cannot load filter dll '%ws'.  hr = %x\n",
        a2,
        v12);
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180006e10  push    rbx
0x180006e12  push    rbp
0x180006e13  push    rsi
0x180006e14  push    rdi
0x180006e15  sub     rsp, 58h
0x180006e19  mov     eax, r8d
0x180006e1c  mov     [rsp+78h+var_38], 0
0x180006e25  mov     rsi, rdx
0x180006e28  lea     r8, [rsp+78h+var_38]; struct HTTP_FILTER_DLL **
0x180006e2d  mov     rbp, rcx
0x180006e30  mov     edx, eax; int
0x180006e32  mov     rcx, rsi; unsigned __int16 *
0x180006e35  mov     rdi, r9
0x180006e38  call    ?OpenFilter@HTTP_FILTER_DLL@@SAJPEBGHPEAPEAV1@PEAW4FILTER_FAILURE_POINT@@@Z; HTTP_FILTER_DLL::OpenFilter(ushort const *,int,HTTP_FILTER_DLL * *,FILTER_FAILURE_POINT *)
0x180006e3d  mov     ebx, eax
0x180006e3f  test    eax, eax
0x180006e41  jns     short loc_180006E8D
0x180006e43  test    cs:g_dwDebugFlags, 3
0x180006e4a  jz      short loc_180006E82
0x180006e4c  mov     rcx, cs:g_pDebug
0x180006e53  lea     r9, aFilterListLoad; "FILTER_LIST::LoadFilter"
0x180006e5a  mov     [rsp+78h+var_48], eax
0x180006e5e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006e65  lea     rax, aCannotLoadFilt; "Cannot load filter dll '%ws'.  hr = %x"...
0x180006e6c  mov     [rsp+78h+var_50], rsi
0x180006e71  mov     r8d, 1C5h
0x180006e77  mov     [rsp+78h+var_58], rax
0x180006e7c  call    cs:__imp_PuDbgPrint
0x180006e82  mov     eax, ebx
0x180006e84  add     rsp, 58h
0x180006e88  pop     rdi
0x180006e89  pop     rsi
0x180006e8a  pop     rbp
0x180006e8b  pop     rbx
0x180006e8c  retn
0x180006e8d  mov     rbx, [rsp+78h+var_38]
0x180006e92  mov     eax, [rbx+40h]
0x180006e95  or      eax, [rbx+3Ch]
0x180006e98  bt      eax, 0Fh
0x180006e9c  jnb     short loc_180006F18
0x180006e9e  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_pEventLog
0x180006ea5  lea     r9, [rsp+78h+var_38]
0x180006eaa  mov     r8d, 1
0x180006eb0  mov     [rsp+78h+var_38], rsi
0x180006eb5  mov     edx, 0C00008D5h
0x180006eba  mov     dword ptr [rsp+78h+var_58], 0
0x180006ec2  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180006ec8  test    cs:g_dwDebugFlags, 3
0x180006ecf  jz      short loc_180006F03
0x180006ed1  mov     rcx, cs:g_pDebug
0x180006ed8  lea     rax, aRefusingReadRa; "Refusing READ_RAW filter on site (%S)\n"
0x180006edf  mov     [rsp+78h+var_50], rsi
0x180006ee4  lea     r9, aFilterListLoad; "FILTER_LIST::LoadFilter"
0x180006eeb  mov     r8d, 1DDh
0x180006ef1  mov     [rsp+78h+var_58], rax
0x180006ef6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006efd  call    cs:__imp_PuDbgPrint
0x180006f03  mov     rcx, rbx; this
0x180006f06  call    ?DereferenceFilterDll@HTTP_FILTER_DLL@@QEAAXXZ; HTTP_FILTER_DLL::DereferenceFilterDll(void)
0x180006f0b  mov     eax, 80070032h
0x180006f10  mov     dword ptr [rdi], 4
0x180006f16  jmp     short loc_180006F33
0x180006f18  mov     rdx, rbx; struct HTTP_FILTER_DLL *
0x180006f1b  mov     rcx, rbp; this
0x180006f1e  call    ?AddFilterToList@FILTER_LIST@@QEAAJPEAVHTTP_FILTER_DLL@@@Z; FILTER_LIST::AddFilterToList(HTTP_FILTER_DLL *)
0x180006f23  mov     edi, eax
0x180006f25  test    eax, eax
0x180006f27  jns     short loc_180006F31
0x180006f29  mov     rcx, rbx; this
0x180006f2c  call    ?DereferenceFilterDll@HTTP_FILTER_DLL@@QEAAXXZ; HTTP_FILTER_DLL::DereferenceFilterDll(void)
0x180006f31  mov     eax, edi
0x180006f33  add     rsp, 58h
0x180006f37  pop     rdi
0x180006f38  pop     rsi
0x180006f39  pop     rbp
0x180006f3a  pop     rbx
0x180006f3b  retn
```
