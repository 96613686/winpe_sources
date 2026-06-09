# CPNRPResolver::Initialize(ulong,HINSTANCE__ *)

- ea: `0x140038c7c`
- end: `0x140038db2`
- name: `?Initialize@CPNRPResolver@@QEAAJKPEAUHINSTANCE__@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(CPNRPResolver *__hidden this, unsigned int, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026270`

## callees

- `0x140034ce4`
- `0x140038c7c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140038ccb`
- `KERNEL32!GetProcessHeap` at `0x140038d2b`
- `KERNEL32!GetProcessHeap` at `0x140038d5d`
- `KERNEL32!GetProcessHeap` at `0x140038ccb`
- `KERNEL32!GetProcessHeap` at `0x140038d2b`
- `KERNEL32!GetProcessHeap` at `0x140038d5d`
- `KERNEL32!HeapAlloc` at `0x140038ce5`
- `KERNEL32!HeapAlloc` at `0x140038d42`
- `KERNEL32!HeapAlloc` at `0x140038d74`
- `KERNEL32!HeapAlloc` at `0x140038ce5`
- `KERNEL32!HeapAlloc` at `0x140038d42`
- `KERNEL32!HeapAlloc` at `0x140038d74`

## string_xrefs

- `0x140038cae`: `base\diagnosis\ra\racommon\src\pnrpresolver.cpp`
- `0x140038d0c`: `base\diagnosis\ra\racommon\src\pnrpresolver.cpp`

## pseudocode

```c
__int64 __fastcall CPNRPResolver::Initialize(CPNRPResolver *this, __int64 a2, HINSTANCE a3)
{
  HANDLE ProcessHeap; // rax
  LPVOID v7; // rax
  CEventLogger *v8; // rcx
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  HANDLE v11; // rax
  LPVOID v12; // rax
  HANDLE v13; // rax
  LPVOID v14; // rax

  if ( !a3 )
  {
    CEventLogger::LogError(
      this,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\pnrpresolver.cpp",
      0x55u,
      L"CPNRPResolver::Initialize",
      0x80070057);
    return 2147942487LL;
  }
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x18u);
  *(_QWORD *)this = v7;
  if ( v7 )
  {
    v11 = GetProcessHeap();
    v12 = HeapAlloc(v11, 8u, 0x18u);
    *((_QWORD *)this + 2) = v12;
    if ( v12 )
    {
      v13 = GetProcessHeap();
      v14 = HeapAlloc(v13, 8u, 0x18u);
      *((_QWORD *)this + 3) = v14;
      if ( v14 )
      {
        v10 = 0;
        *((_DWORD *)this + 2) = 3;
        *((_QWORD *)this + 4) = a3;
        return v10;
      }
      v9 = 91;
    }
    else
    {
      v9 = 90;
    }
  }
  else
  {
    v9 = 89;
  }
  v10 = -2147024882;
  CEventLogger::LogError(
    v8,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\racommon\\src\\pnrpresolver.cpp",
    v9,
    L"CPNRPResolver::Initialize",
    0x8007000E);
  return v10;
}

```

## disassembly

```asm
0x140038c7c  mov     [rsp+arg_0], rbx
0x140038c81  mov     [rsp+arg_8], rsi
0x140038c86  push    rdi
0x140038c87  sub     rsp, 30h
0x140038c8b  mov     rsi, r8
0x140038c8e  mov     rdi, rcx
0x140038c91  test    r8, r8
0x140038c94  jnz     short loc_140038CCB
0x140038c96  lea     rax, aCpnrpresolverI; "CPNRPResolver::Initialize"
0x140038c9d  mov     [rsp+38h+var_10], 80070057h; unsigned int
0x140038ca5  lea     r9d, [r8+55h]; unsigned int
0x140038ca9  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140038cae  lea     r8, aBaseDiagnosisR_19; "base\\diagnosis\\ra\\racommon\\src\\pnr"...
0x140038cb5  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038cbc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038cc1  mov     eax, 80070057h
0x140038cc6  jmp     loc_140038DA1
0x140038ccb  call    cs:__imp_GetProcessHeap
0x140038cd2  nop     dword ptr [rax+rax+00h]
0x140038cd7  mov     ebx, 18h
0x140038cdc  mov     rcx, rax; hHeap
0x140038cdf  mov     r8d, ebx; dwBytes
0x140038ce2  lea     edx, [rbx-10h]; dwFlags
0x140038ce5  call    cs:__imp_HeapAlloc
0x140038cec  nop     dword ptr [rax+rax+00h]
0x140038cf1  mov     [rdi], rax
0x140038cf4  test    rax, rax
0x140038cf7  jnz     short loc_140038D2B
0x140038cf9  lea     r9d, [rbx+41h]; unsigned int
0x140038cfd  lea     rax, aCpnrpresolverI; "CPNRPResolver::Initialize"
0x140038d04  mov     [rsp+38h+var_10], 8007000Eh; unsigned int
0x140038d0c  lea     r8, aBaseDiagnosisR_19; "base\\diagnosis\\ra\\racommon\\src\\pnr"...
0x140038d13  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140038d18  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038d1f  mov     ebx, 8007000Eh
0x140038d24  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038d29  jmp     short loc_140038D9F
0x140038d2b  call    cs:__imp_GetProcessHeap
0x140038d32  nop     dword ptr [rax+rax+00h]
0x140038d37  mov     r8, rbx; dwBytes
0x140038d3a  mov     edx, 8; dwFlags
0x140038d3f  mov     rcx, rax; hHeap
0x140038d42  call    cs:__imp_HeapAlloc
0x140038d49  nop     dword ptr [rax+rax+00h]
0x140038d4e  mov     [rdi+10h], rax
0x140038d52  test    rax, rax
0x140038d55  jnz     short loc_140038D5D
0x140038d57  lea     r9d, [rax+5Ah]
0x140038d5b  jmp     short loc_140038CFD
0x140038d5d  call    cs:__imp_GetProcessHeap
0x140038d64  nop     dword ptr [rax+rax+00h]
0x140038d69  mov     r8, rbx; dwBytes
0x140038d6c  mov     edx, 8; dwFlags
0x140038d71  mov     rcx, rax; hHeap
0x140038d74  call    cs:__imp_HeapAlloc
0x140038d7b  nop     dword ptr [rax+rax+00h]
0x140038d80  mov     [rdi+18h], rax
0x140038d84  test    rax, rax
0x140038d87  jnz     short loc_140038D92
0x140038d89  lea     r9d, [rax+5Bh]
0x140038d8d  jmp     loc_140038CFD
0x140038d92  xor     ebx, ebx
0x140038d94  mov     dword ptr [rdi+8], 3
0x140038d9b  mov     [rdi+20h], rsi
0x140038d9f  mov     eax, ebx
0x140038da1  mov     rbx, [rsp+38h+arg_0]
0x140038da6  mov     rsi, [rsp+38h+arg_8]
0x140038dab  add     rsp, 30h
0x140038daf  pop     rdi
0x140038db0  retn
```
