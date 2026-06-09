# NewSessionTemporaryPath(ushort *,unsigned __int64)

- ea: `0x1400418a4`
- end: `0x140041a8a`
- name: `?NewSessionTemporaryPath@@YAJPEAG_K@Z`
- size: `486`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140040b14`

## callees

- `0x140006fe0`
- `0x140020420`
- `0x140022070`
- `0x1400407b0`
- `0x1400413ac`
- `0x1400418a4`
- `0x140061c90`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400418ed`
- `KERNEL32!HeapAlloc` at `0x1400418ed`
- `KERNEL32!HeapFree` at `0x140041a5e`
- `KERNEL32!HeapFree` at `0x140041a5e`
- `KERNEL32!GetProcessHeap` at `0x1400418d6`
- `KERNEL32!GetProcessHeap` at `0x140041a4a`
- `KERNEL32!GetProcessHeap` at `0x1400418d6`
- `KERNEL32!GetProcessHeap` at `0x140041a4a`
- `ole32!StringFromGUID2` at `0x140041969`
- `ole32!StringFromGUID2` at `0x140041969`
- `RPCRT4!UuidCreate` at `0x140041930`
- `RPCRT4!UuidCreate` at `0x140041930`

## string_xrefs

- `0x140041906`: `NewSessionTemporaryPath`
- `0x140041a2e`: `NewSessionTemporaryPath`

## pseudocode

```c
__int64 __fastcall NewSessionTemporaryPath(unsigned __int16 *lpSrc)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rdi
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  int MsdtTempPath; // eax
  int v7; // r9d
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rax
  HANDLE v10; // rax
  unsigned __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-20h] BYREF

  v12 = 0;
  Uuid = 0;
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x200u);
  if ( v3 )
  {
    v5 = UuidCreate(&Uuid);
    if ( !v5 || v5 == 1824 )
    {
      if ( StringFromGUID2(&Uuid, v3, 256) )
      {
        MsdtTempPath = StringCchLengthW(v3, 0x100u, &v12);
        v4 = MsdtTempPath;
        if ( MsdtTempPath >= 0 )
        {
          v9 = v12;
          if ( v12 > 2 )
          {
            *v3 = 95;
            v3[v9 - 1] = 95;
          }
          MsdtTempPath = GetMsdtTempPath(lpSrc, v8);
          v4 = MsdtTempPath;
          if ( MsdtTempPath >= 0 )
          {
            MsdtTempPath = StringCchCatW(lpSrc, 0x104u, v3);
            v4 = MsdtTempPath;
            if ( MsdtTempPath >= 0 )
            {
              MsdtTempPath = StringCchCatW(lpSrc, 0x104u, L"\\");
              v4 = MsdtTempPath;
              if ( MsdtTempPath >= 0 )
              {
                MsdtTempPath = CreateDirectoryW(lpSrc);
                v4 = MsdtTempPath;
                if ( MsdtTempPath >= 0 )
                {
LABEL_21:
                  v10 = GetProcessHeap();
                  HeapFree(v10, 0, v3);
                  return v4;
                }
                v7 = 576;
              }
              else
              {
                v7 = 570;
              }
            }
            else
            {
              v7 = 564;
            }
          }
          else
          {
            v7 = 558;
          }
        }
        else
        {
          v7 = 544;
        }
      }
      else
      {
        MsdtTempPath = -2147467259;
        v7 = 540;
        v4 = -2147467259;
      }
    }
    else
    {
      MsdtTempPath = -2147467259;
      v7 = 535;
      v4 = -2147467259;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "NewSessionTemporaryPath", v7, MsdtTempPath);
    goto LABEL_21;
  }
  v4 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "NewSessionTemporaryPath", 530, -2147024882);
  return v4;
}

```

## disassembly

```asm
0x1400418a4  mov     [rsp+arg_8], rbx
0x1400418a9  mov     [rsp+arg_10], rsi
0x1400418ae  push    rdi
0x1400418af  sub     rsp, 50h
0x1400418b3  mov     rax, cs:__security_cookie
0x1400418ba  xor     rax, rsp
0x1400418bd  mov     [rsp+58h+var_10], rax
0x1400418c2  xorps   xmm0, xmm0
0x1400418c5  mov     [rsp+58h+var_28], 0
0x1400418ce  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1400418d3  mov     rsi, rcx
0x1400418d6  call    cs:__imp_GetProcessHeap
0x1400418dd  nop     dword ptr [rax+rax+00h]
0x1400418e2  xor     edx, edx; dwFlags
0x1400418e4  mov     r8d, 200h; dwBytes
0x1400418ea  mov     rcx, rax; hHeap
0x1400418ed  call    cs:__imp_HeapAlloc
0x1400418f4  nop     dword ptr [rax+rax+00h]
0x1400418f9  mov     rdi, rax
0x1400418fc  test    rax, rax
0x1400418ff  jnz     short loc_14004192B
0x140041901  mov     ebx, 8007000Eh
0x140041906  lea     r8, aNewsessiontemp; "NewSessionTemporaryPath"
0x14004190d  mov     r9d, 212h
0x140041913  mov     [rsp+58h+var_38], ebx
0x140041917  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004191e  lea     ecx, [rax+1]; Level
0x140041921  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041926  jmp     loc_140041A6A
0x14004192b  lea     rcx, [rsp+58h+Uuid]; Uuid
0x140041930  call    cs:__imp_UuidCreate
0x140041937  nop     dword ptr [rax+rax+00h]
0x14004193c  test    eax, eax
0x14004193e  jz      short loc_140041959
0x140041940  cmp     eax, 720h
0x140041945  jz      short loc_140041959
0x140041947  mov     eax, 80004005h
0x14004194c  mov     r9d, 217h
0x140041952  mov     ebx, eax
0x140041954  jmp     loc_140041A2E
0x140041959  mov     ebx, 100h
0x14004195e  lea     rcx, [rsp+58h+Uuid]; rguid
0x140041963  mov     r8d, ebx; cchMax
0x140041966  mov     rdx, rdi; lpsz
0x140041969  call    cs:__imp_StringFromGUID2
0x140041970  nop     dword ptr [rax+rax+00h]
0x140041975  test    eax, eax
0x140041977  jnz     short loc_14004198B
0x140041979  mov     eax, 80004005h
0x14004197e  mov     r9d, 21Ch
0x140041984  mov     ebx, eax
0x140041986  jmp     loc_140041A2E
0x14004198b  lea     r8, [rsp+58h+var_28]; unsigned __int64 *
0x140041990  mov     rdx, rbx; unsigned __int64
0x140041993  mov     rcx, rdi; unsigned __int16 *
0x140041996  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14004199b  mov     ebx, eax
0x14004199d  test    eax, eax
0x14004199f  jns     short loc_1400419AC
0x1400419a1  mov     r9d, 220h
0x1400419a7  jmp     loc_140041A2E
0x1400419ac  mov     rax, [rsp+58h+var_28]
0x1400419b1  cmp     rax, 2
0x1400419b5  jbe     short loc_1400419C4
0x1400419b7  mov     ecx, 5Fh ; '_'
0x1400419bc  mov     [rdi], cx
0x1400419bf  mov     [rdi+rax*2-2], cx
0x1400419c4  mov     rcx, rsi; unsigned __int16 *
0x1400419c7  call    ?GetMsdtTempPath@@YAJPEAG_K@Z; GetMsdtTempPath(ushort *,unsigned __int64)
0x1400419cc  mov     ebx, eax
0x1400419ce  test    eax, eax
0x1400419d0  jns     short loc_1400419DA
0x1400419d2  mov     r9d, 22Eh
0x1400419d8  jmp     short loc_140041A2E
0x1400419da  mov     r8, rdi; unsigned __int16 *
0x1400419dd  mov     edx, 104h; unsigned __int64
0x1400419e2  mov     rcx, rsi; unsigned __int16 *
0x1400419e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400419ea  mov     ebx, eax
0x1400419ec  test    eax, eax
0x1400419ee  jns     short loc_1400419F8
0x1400419f0  mov     r9d, 234h
0x1400419f6  jmp     short loc_140041A2E
0x1400419f8  lea     r8, asc_14006B250; "\\"
0x1400419ff  mov     edx, 104h; unsigned __int64
0x140041a04  mov     rcx, rsi; unsigned __int16 *
0x140041a07  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140041a0c  mov     ebx, eax
0x140041a0e  test    eax, eax
0x140041a10  jns     short loc_140041A1A
0x140041a12  mov     r9d, 23Ah
0x140041a18  jmp     short loc_140041A2E
0x140041a1a  mov     rcx, rsi; lpSrc
0x140041a1d  call    ?CreateDirectoryW@@YAJPEBG@Z; CreateDirectoryW(ushort const *)
0x140041a22  mov     ebx, eax
0x140041a24  test    eax, eax
0x140041a26  jns     short loc_140041A4A
0x140041a28  mov     r9d, 240h
0x140041a2e  lea     r8, aNewsessiontemp; "NewSessionTemporaryPath"
0x140041a35  mov     [rsp+58h+var_38], eax
0x140041a39  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041a40  mov     ecx, 1; Level
0x140041a45  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041a4a  call    cs:__imp_GetProcessHeap
0x140041a51  nop     dword ptr [rax+rax+00h]
0x140041a56  mov     r8, rdi; lpMem
0x140041a59  xor     edx, edx; dwFlags
0x140041a5b  mov     rcx, rax; hHeap
0x140041a5e  call    cs:__imp_HeapFree
0x140041a65  nop     dword ptr [rax+rax+00h]
0x140041a6a  mov     eax, ebx
0x140041a6c  mov     rcx, [rsp+58h+var_10]
0x140041a71  xor     rcx, rsp; StackCookie
0x140041a74  call    __security_check_cookie
0x140041a79  mov     rbx, [rsp+58h+arg_8]
0x140041a7e  mov     rsi, [rsp+58h+arg_10]
0x140041a83  add     rsp, 50h
0x140041a87  pop     rdi
0x140041a88  retn
```
