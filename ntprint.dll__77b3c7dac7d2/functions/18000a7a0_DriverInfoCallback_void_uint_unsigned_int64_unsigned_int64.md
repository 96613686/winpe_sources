# DriverInfoCallback(void *,uint,unsigned __int64,unsigned __int64)

- ea: `0x18000a7a0`
- end: `0x18000a95b`
- name: `?DriverInfoCallback@@YAIPEAXI_K1@Z`
- size: `443`
- prototype: `UINT __stdcall(PVOID Context, UINT Notification, UINT_PTR Param1, UINT_PTR Param2)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180007944`
- `0x18000a7a0`
- `0x18000d624`
- `0x18001c914`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a7ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a821`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a901`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a7ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a821`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a901`
- `KERNEL32!lstrcmpiW` at `0x18000a844`
- `KERNEL32!lstrcmpiW` at `0x18000a864`
- `KERNEL32!lstrcmpiW` at `0x18000a880`
- `KERNEL32!lstrcmpiW` at `0x18000a8a1`
- `KERNEL32!lstrcmpiW` at `0x18000a844`
- `KERNEL32!lstrcmpiW` at `0x18000a864`
- `KERNEL32!lstrcmpiW` at `0x18000a880`
- `KERNEL32!lstrcmpiW` at `0x18000a8a1`

## string_xrefs

- `0x18000a8c1`: `Copying dependent file %ws into the dependent file list`
- `0x18000a921`: `Copying color file %ws into the color file list`

## pseudocode

```c
__int64 __fastcall DriverInfoCallback(_QWORD *Context, UINT Notification, wchar_t *Param1, UINT_PTR Param2)
{
  __int64 v6; // rax
  const unsigned __int16 *v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rbp
  unsigned int v10; // ebp
  wchar_t **v11; // r14
  const WCHAR *v12; // rax
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  wchar_t *v15; // rcx
  const WCHAR *v16; // rax
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rcx

  v6 = FileNamePart(Param1);
  v7 = (const unsigned __int16 *)v6;
  if ( !v6 )
    return 87;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v6 + 2 * v9) );
  do
    ++v8;
  while ( gpszSkipDir[v8] );
  if ( (unsigned int)_o__wcsnicmp(Param1, gpszSkipDir) )
  {
    v10 = v9 + 1;
    if ( (unsigned int)_o__wcsnicmp(Param1, Context + 5) )
    {
      if ( !(unsigned int)_o__wcsnicmp(Param1, Context + 70) )
      {
        v18 = (unsigned __int16 *)Context[4];
        if ( v18 )
        {
          StringCchCopyW(v18, v10, v7);
          ClassInstallerTelemetry::WriteDbgTraceInfo(
            "DriverInfoCallback",
            L"Copying color file %ws into the color file list",
            v7);
          Context[4] += 2LL * v10;
        }
        else
        {
          *((_DWORD *)Context + 3) += v10;
        }
      }
    }
    else
    {
      v11 = (wchar_t **)*Context;
      v12 = (const WCHAR *)FileNamePart(*(wchar_t **)(*Context + 288LL));
      if ( lstrcmpiW(v7, v12)
        && (v13 = (const WCHAR *)FileNamePart(v11[38]), lstrcmpiW(v7, v13))
        && (v14 = (const WCHAR *)FileNamePart(v11[37]), lstrcmpiW(v7, v14))
        && ((v15 = v11[39]) == 0 || (v16 = (const WCHAR *)FileNamePart(v15), lstrcmpiW(v7, v16))) )
      {
        v17 = (unsigned __int16 *)Context[3];
        if ( v17 )
        {
          StringCchCopyW(v17, v10, v7);
          ClassInstallerTelemetry::WriteDbgTraceInfo(
            "DriverInfoCallback",
            L"Copying dependent file %ws into the dependent file list",
            v7);
          Context[3] += 2LL * v10;
        }
        else
        {
          *((_DWORD *)Context + 2) += v10;
        }
      }
      else
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "DriverInfoCallback",
          L"%ws is not a dependent file, skipping processing",
          Param1);
      }
    }
  }
  else
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo("DriverInfoCallback", L"Skipping processing for %ws", Param1);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a7a0  push    rbx
0x18000a7a2  push    rbp
0x18000a7a3  push    rsi
0x18000a7a4  push    rdi
0x18000a7a5  push    r14
0x18000a7a7  push    r15
0x18000a7a9  sub     rsp, 28h
0x18000a7ad  mov     rdi, rcx
0x18000a7b0  mov     rbx, r8
0x18000a7b3  mov     rcx, r8; Str
0x18000a7b6  call    FileNamePart
0x18000a7bb  xor     r15d, r15d
0x18000a7be  mov     rsi, rax
0x18000a7c1  test    rax, rax
0x18000a7c4  jz      loc_18000A949
0x18000a7ca  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a7ce  mov     rbp, r8
0x18000a7d1  inc     rbp
0x18000a7d4  cmp     [rax+rbp*2], r15w
0x18000a7d9  jnz     short loc_18000A7D1
0x18000a7db  mov     rdx, cs:gpszSkipDir
0x18000a7e2  inc     r8
0x18000a7e5  cmp     [rdx+r8*2], r15w
0x18000a7ea  jnz     short loc_18000A7E2
0x18000a7ec  mov     rcx, rbx
0x18000a7ef  call    cs:__imp__o__wcsnicmp
0x18000a7f5  test    eax, eax
0x18000a7f7  jnz     short loc_18000A814
0x18000a7f9  lea     rdx, aSkippingProces; "Skipping processing for %ws"
0x18000a800  mov     r8, rbx
0x18000a803  lea     rcx, aDriverinfocall; "DriverInfoCallback"
0x18000a80a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000a80f  jmp     loc_18000A945
0x18000a814  mov     r8d, [rdi+10h]
0x18000a818  lea     rdx, [rdi+28h]
0x18000a81c  mov     rcx, rbx
0x18000a81f  inc     ebp
0x18000a821  call    cs:__imp__o__wcsnicmp
0x18000a827  test    eax, eax
0x18000a829  jnz     loc_18000A8F3
0x18000a82f  mov     r14, [rdi]
0x18000a832  mov     rcx, [r14+120h]; Str
0x18000a839  call    FileNamePart
0x18000a83e  mov     rdx, rax; lpString2
0x18000a841  mov     rcx, rsi; lpString1
0x18000a844  call    cs:__imp_lstrcmpiW
0x18000a84a  test    eax, eax
0x18000a84c  jz      loc_18000A8E7
0x18000a852  mov     rcx, [r14+130h]; Str
0x18000a859  call    FileNamePart
0x18000a85e  mov     rdx, rax; lpString2
0x18000a861  mov     rcx, rsi; lpString1
0x18000a864  call    cs:__imp_lstrcmpiW
0x18000a86a  test    eax, eax
0x18000a86c  jz      short loc_18000A8E7
0x18000a86e  mov     rcx, [r14+128h]; Str
0x18000a875  call    FileNamePart
0x18000a87a  mov     rdx, rax; lpString2
0x18000a87d  mov     rcx, rsi; lpString1
0x18000a880  call    cs:__imp_lstrcmpiW
0x18000a886  test    eax, eax
0x18000a888  jz      short loc_18000A8E7
0x18000a88a  mov     rcx, [r14+138h]; Str
0x18000a891  test    rcx, rcx
0x18000a894  jz      short loc_18000A8AB
0x18000a896  call    FileNamePart
0x18000a89b  mov     rdx, rax; lpString2
0x18000a89e  mov     rcx, rsi; lpString1
0x18000a8a1  call    cs:__imp_lstrcmpiW
0x18000a8a7  test    eax, eax
0x18000a8a9  jz      short loc_18000A8E7
0x18000a8ab  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18000a8af  test    rcx, rcx
0x18000a8b2  jz      short loc_18000A8E2
0x18000a8b4  mov     r8, rsi; unsigned __int16 *
0x18000a8b7  mov     edx, ebp; unsigned __int64
0x18000a8b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a8be  mov     r8, rsi
0x18000a8c1  lea     rdx, aCopyingDepende; "Copying dependent file %ws into the dep"...
0x18000a8c8  lea     rcx, aDriverinfocall; "DriverInfoCallback"
0x18000a8cf  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000a8d4  lea     rax, ds:0[rbp*2]
0x18000a8dc  add     [rdi+18h], rax
0x18000a8e0  jmp     short loc_18000A945
0x18000a8e2  add     [rdi+8], ebp
0x18000a8e5  jmp     short loc_18000A945
0x18000a8e7  lea     rdx, aWsIsNotADepend; "%ws is not a dependent file, skipping p"...
0x18000a8ee  jmp     loc_18000A800
0x18000a8f3  mov     r8d, [rdi+14h]
0x18000a8f7  lea     rdx, [rdi+230h]
0x18000a8fe  mov     rcx, rbx
0x18000a901  call    cs:__imp__o__wcsnicmp
0x18000a907  test    eax, eax
0x18000a909  jnz     short loc_18000A945
0x18000a90b  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18000a90f  test    rcx, rcx
0x18000a912  jz      short loc_18000A942
0x18000a914  mov     r8, rsi; unsigned __int16 *
0x18000a917  mov     edx, ebp; unsigned __int64
0x18000a919  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a91e  mov     r8, rsi
0x18000a921  lea     rdx, aCopyingColorFi; "Copying color file %ws into the color f"...
0x18000a928  lea     rcx, aDriverinfocall; "DriverInfoCallback"
0x18000a92f  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000a934  lea     rax, ds:0[rbp*2]
0x18000a93c  add     [rdi+20h], rax
0x18000a940  jmp     short loc_18000A945
0x18000a942  add     [rdi+0Ch], ebp
0x18000a945  xor     eax, eax
0x18000a947  jmp     short loc_18000A94E
0x18000a949  mov     eax, 57h ; 'W'
0x18000a94e  add     rsp, 28h
0x18000a952  pop     r15
0x18000a954  pop     r14
0x18000a956  pop     rdi
0x18000a957  pop     rsi
0x18000a958  pop     rbp
0x18000a959  pop     rbx
0x18000a95a  retn
```
