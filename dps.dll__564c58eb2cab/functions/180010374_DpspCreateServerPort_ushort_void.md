# DpspCreateServerPort(ushort *,void * *)

- ea: `0x180010374`
- end: `0x1800104ed`
- name: `?DpspCreateServerPort@@YAJPEAGPEAPEAX@Z`
- size: `377`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011274`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x180010374`
- `0x180017794`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800103d0`
- `ntdll!RtlInitUnicodeString` at `0x1800103d0`
- `ntdll!RtlNtStatusToDosError` at `0x18001047f`
- `ntdll!RtlNtStatusToDosError` at `0x18001047f`
- `ntdll!NtAlpcCreatePort` at `0x18001046f`
- `ntdll!NtAlpcCreatePort` at `0x18001046f`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180010441`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18001044b`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180010441`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18001044b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800104c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800104c8`

## string_xrefs

- `0x1800104ac`: `DpspCreateServerPort`

## pseudocode

```c
__int64 __fastcall DpspCreateServerPort(PCWSTR SourceString, void **a2)
{
  __int64 v3; // rcx
  int Args; // eax
  signed int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  NTSTATUS v13; // eax
  signed int v14; // eax
  HLOCAL hMem[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v17; // [rsp+40h] [rbp-59h]
  __int128 v18; // [rsp+48h] [rbp-51h] BYREF
  __int128 v19; // [rsp+58h] [rbp-41h]
  __int128 v20; // [rsp+68h] [rbp-31h]
  _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-21h] BYREF
  _DWORD v22[4]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+B0h] [rbp+17h]

  DestinationString = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset_0(v22, 0, 0x48u);
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_OWORD *)hMem = 0;
  v17 = 0;
  Args = WdipCreateSecurityDescriptor(v3, hMem);
  v5 = Args;
  if ( Args >= 0 )
  {
    LODWORD(v18) = 48;
    *((_QWORD *)&v18 + 1) = 0;
    *(_QWORD *)&v19 = &DestinationString;
    DWORD2(v19) = 64;
    v20 = (unsigned __int64)hMem[1];
    memset_0(v22, 0, 0x48u);
    v23 = AlpcMaxAllowedMessageLength(v7, v6, v8);
    v12 = AlpcMaxAllowedMessageLength(v10, v9, v11);
    v22[0] = 0x40000;
    v24 = v12 << 8;
    v13 = NtAlpcCreatePort(&g_hServerPort, &v18, v22);
    if ( v13 < 0 )
    {
      v14 = RtlNtStatusToDosError(v13);
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v5 = 0;
    }
    if ( v5 < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
        (int)L"DpspCreateServerPort",
        1279,
        (int)L"Error = %d",
        v5);
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspCreateServerPort",
      1260,
      (int)L"Error = %d",
      Args);
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010374  mov     [rsp-8+arg_8], rbx
0x180010379  push    rbp
0x18001037a  lea     rbp, [rsp-57h]
0x18001037f  sub     rsp, 0F0h
0x180010386  mov     rax, cs:__security_cookie
0x18001038d  xor     rax, rsp
0x180010390  mov     [rbp+57h+var_10], rax
0x180010394  xorps   xmm1, xmm1
0x180010397  xor     edx, edx; Val
0x180010399  mov     rbx, rcx
0x18001039c  xorps   xmm0, xmm0
0x18001039f  lea     rcx, [rbp+57h+var_60]; void *
0x1800103a3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800103a7  lea     r8d, [rdx+48h]; Size
0x1800103ab  movups  [rbp+57h+var_A8], xmm1
0x1800103af  movups  [rbp+57h+var_98], xmm1
0x1800103b3  movups  [rbp+57h+var_88], xmm1
0x1800103b7  call    memset_0
0x1800103bc  xorps   xmm0, xmm0
0x1800103bf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800103c3  xor     eax, eax
0x1800103c5  mov     rdx, rbx; SourceString
0x1800103c8  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x1800103cc  mov     [rbp+57h+var_B0], rax
0x1800103d0  call    cs:__imp_RtlInitUnicodeString
0x1800103d6  xorps   xmm0, xmm0
0x1800103d9  lea     rdx, [rbp+57h+hMem]
0x1800103dd  xor     eax, eax
0x1800103df  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x1800103e3  mov     [rbp+57h+var_B0], rax
0x1800103e7  call    WdipCreateSecurityDescriptor
0x1800103ec  mov     ebx, eax
0x1800103ee  test    eax, eax
0x1800103f0  jns     short loc_180010404
0x1800103f2  movzx   ecx, ax
0x1800103f5  mov     r8d, 4ECh
0x1800103fb  mov     dword ptr [rsp+0F0h+Args], ecx
0x1800103ff  jmp     loc_1800104A5
0x180010404  xor     edx, edx; Val
0x180010406  mov     dword ptr [rbp+57h+var_A8], 30h ; '0'
0x18001040d  lea     rax, [rbp+57h+DestinationString]
0x180010411  mov     qword ptr [rbp+57h+var_A8+8], 0
0x180010419  mov     qword ptr [rbp+57h+var_98], rax
0x18001041d  lea     rcx, [rbp+57h+var_60]; void *
0x180010421  mov     rax, [rbp+57h+hMem+8]
0x180010425  lea     r8d, [rdx+48h]; Size
0x180010429  mov     dword ptr [rbp+57h+var_98+8], 40h ; '@'
0x180010430  mov     qword ptr [rbp+57h+var_88], rax
0x180010434  mov     qword ptr [rbp+57h+var_88+8], 0
0x18001043c  call    memset_0
0x180010441  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180010447  mov     [rbp+57h+var_50], rax
0x18001044b  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180010451  lea     r8, [rbp+57h+var_60]
0x180010455  mov     [rbp+57h+var_60], 40000h
0x18001045c  shl     rax, 8
0x180010460  lea     rdx, [rbp+57h+var_A8]
0x180010464  lea     rcx, g_hServerPort
0x18001046b  mov     [rbp+57h+var_40], rax
0x18001046f  call    cs:__imp_NtAlpcCreatePort
0x180010475  test    eax, eax
0x180010477  js      short loc_18001047D
0x180010479  xor     ebx, ebx
0x18001047b  jmp     short loc_180010494
0x18001047d  mov     ecx, eax; Status
0x18001047f  call    cs:__imp_RtlNtStatusToDosError
0x180010485  mov     ebx, eax
0x180010487  test    eax, eax
0x180010489  jle     short loc_180010494
0x18001048b  movzx   ebx, ax
0x18001048e  or      ebx, 80070000h
0x180010494  test    ebx, ebx
0x180010496  jns     short loc_1800104BF
0x180010498  movzx   eax, bx
0x18001049b  mov     r8d, 4FFh; int
0x1800104a1  mov     dword ptr [rsp+0F0h+Args], eax; Args
0x1800104a5  lea     r9, aErrorD; "Error = %d"
0x1800104ac  lea     rdx, aDpspcreateserv; "DpspCreateServerPort"
0x1800104b3  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800104ba  call    WdipTraceError
0x1800104bf  mov     rcx, [rbp+57h+hMem+8]; hMem
0x1800104c3  test    rcx, rcx
0x1800104c6  jz      short loc_1800104CE
0x1800104c8  call    cs:__imp_LocalFree
0x1800104ce  mov     eax, ebx
0x1800104d0  mov     rcx, [rbp+57h+var_10]
0x1800104d4  xor     rcx, rsp; StackCookie
0x1800104d7  call    __security_check_cookie
0x1800104dc  mov     rbx, [rsp+0F0h+arg_8]
0x1800104e4  add     rsp, 0F0h
0x1800104eb  pop     rbp
0x1800104ec  retn
```
