# SendPcwWerReport

- ea: `0x180009c00`
- end: `0x180009cd4`
- name: `SendPcwWerReport`
- size: `212`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009c00`
- `0x18000e240`
- `0x180018cc4`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180009c53`
- `KERNEL32!GetModuleHandleW` at `0x180009c53`
- `USER32!LoadStringW` at `0x180009c6c`
- `USER32!LoadStringW` at `0x180009c6c`

## string_xrefs

- `0x180009c33`: `ExePath: %ws`

## pseudocode

```c
_BOOL8 __fastcall SendPcwWerReport(const WCHAR *a1, int a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  HMODULE ModuleHandleW; // rax
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r9
  unsigned __int16 *v9; // rax
  unsigned int v11; // [rsp+20h] [rbp-268h]
  unsigned int v12; // [rsp+28h] [rbp-260h]
  const unsigned __int16 *v13; // [rsp+30h] [rbp-258h]
  unsigned __int16 *v14[2]; // [rsp+50h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-228h] BYREF

  v14[0] = a3;
  v14[1] = a4;
  v11 = (unsigned int)a1;
  AslLogCallPrintf(3, "SendPcwWerReport", 316, "ExePath: %ws");
  ModuleHandleW = GetModuleHandleW(0);
  if ( !LoadStringW(ModuleHandleW, 0x65u, Buffer, 260) )
    return 0;
  v9 = L"1";
  if ( !a2 )
    v9 = L"0";
  return (int)SendWerReport(a1, Buffer, v7, v8, v11, v12, v13, v9, (const unsigned __int16 **)v14) >= 0;
}

```

## disassembly

```asm
0x180009c00  mov     [rsp+arg_8], rbx
0x180009c05  push    rdi
0x180009c06  sub     rsp, 280h
0x180009c0d  mov     rax, cs:__security_cookie
0x180009c14  xor     rax, rsp
0x180009c17  mov     [rsp+288h+var_18], rax
0x180009c1f  mov     edi, edx
0x180009c21  mov     [rsp+288h+var_238], r8
0x180009c26  mov     rbx, rcx
0x180009c29  mov     [rsp+288h+var_230], r9
0x180009c2e  mov     qword ptr [rsp+288h+var_268], rcx; unsigned int
0x180009c33  lea     r9, aExepathWs; "ExePath: %ws"
0x180009c3a  mov     r8d, 13Ch
0x180009c40  lea     rdx, aSendpcwwerrepo_0; "SendPcwWerReport"
0x180009c47  mov     ecx, 3
0x180009c4c  call    AslLogCallPrintf
0x180009c51  xor     ecx, ecx; lpModuleName
0x180009c53  call    cs:__imp_GetModuleHandleW
0x180009c59  mov     r9d, 104h; cchBufferMax
0x180009c5f  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x180009c64  mov     rcx, rax; hInstance
0x180009c67  mov     edx, 65h ; 'e'; uID
0x180009c6c  call    cs:__imp_LoadStringW
0x180009c72  test    eax, eax
0x180009c74  jz      short loc_180009CB1
0x180009c76  lea     rcx, a0; "0"
0x180009c7d  test    edi, edi
0x180009c7f  lea     rax, a1; "1"
0x180009c86  cmovz   rax, rcx
0x180009c8a  lea     rdx, [rsp+288h+Buffer]; unsigned __int16 *
0x180009c8f  lea     rcx, [rsp+288h+var_238]
0x180009c94  mov     [rsp+288h+var_248], rcx; unsigned __int16 **
0x180009c99  mov     rcx, rbx; pszPath
0x180009c9c  mov     [rsp+288h+var_250], rax; unsigned __int16 *
0x180009ca1  call    ?SendWerReport@@YAJPEBG000KK00PEAPEBGK@Z; SendWerReport(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *,ushort const *,ushort const * *,ulong)
0x180009ca6  xor     ecx, ecx
0x180009ca8  test    eax, eax
0x180009caa  setns   cl
0x180009cad  mov     eax, ecx
0x180009caf  jmp     short loc_180009CB3
0x180009cb1  xor     eax, eax
0x180009cb3  mov     rcx, [rsp+288h+var_18]
0x180009cbb  xor     rcx, rsp; StackCookie
0x180009cbe  call    __security_check_cookie
0x180009cc3  mov     rbx, [rsp+288h+arg_8]
0x180009ccb  add     rsp, 280h
0x180009cd2  pop     rdi
0x180009cd3  retn
```
