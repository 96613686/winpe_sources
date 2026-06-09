# HrOnGetHelpTopic(_SFVM_HELPTOPIC_DATA *)

- ea: `0x180047f34`
- end: `0x180048051`
- name: `?HrOnGetHelpTopic@@YAJPEAU_SFVM_HELPTOPIC_DATA@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct _SFVM_HELPTOPIC_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180048060`

## callees

- `0x180047f34`
- `0x180065010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180047ff0`
- `ntdll!WinSqmAddToStream` at `0x180047ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047fb5`
- `ole32!CoCreateInstance` at `0x180047f94`
- `ole32!CoCreateInstance` at `0x180047f94`
- `ole32!CoUninitialize` at `0x180048039`
- `ole32!CoUninitialize` at `0x180048039`
- `ole32!CoInitializeEx` at `0x180047f57`
- `ole32!CoInitializeEx` at `0x180047f57`
- `OLEAUT32!__imp_SysAllocString` at `0x180047fa7`
- `OLEAUT32!__imp_SysAllocString` at `0x180047fa7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004800f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004800f`

## pseudocode

```c
__int64 __fastcall HrOnGetHelpTopic(struct _SFVM_HELPTOPIC_DATA *a1)
{
  HRESULT v1; // eax
  int v2; // ebx
  char v3; // di
  OLECHAR *v4; // rsi
  signed int LastError; // eax
  int v7; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v8; // [rsp+38h] [rbp-10h]
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  ppv = 0;
  v1 = CoInitializeEx(0, 2u);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v1 != -2147417850 )
      goto LABEL_10;
  }
  v2 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v2 >= 0 )
  {
    v4 = SysAllocString(L"mshelp://windows/?id=ca2d0191-299e-4dc3-afab-df5862d460be");
    if ( v4 )
    {
      v7 = 2;
      v8 = L"NETWORK_CONNECTIONS_HELP_BUTTON";
      WinSqmAddToStream(0, 911, 1, &v7);
      v2 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 24LL))(ppv, v4);
      SysFreeString(v4);
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_10:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v3 )
    CoUninitialize();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180047f34  mov     rax, rsp
0x180047f37  mov     [rax+10h], rbx
0x180047f3b  mov     [rax+18h], rsi
0x180047f3f  mov     [rax+8], rcx
0x180047f43  push    rdi
0x180047f44  sub     rsp, 40h
0x180047f48  mov     edx, 2; dwCoInit
0x180047f4d  mov     qword ptr [rax+8], 0
0x180047f55  xor     ecx, ecx; pvReserved
0x180047f57  call    cs:__imp_CoInitializeEx
0x180047f5d  mov     ebx, eax
0x180047f5f  test    eax, eax
0x180047f61  jns     short loc_180047F73
0x180047f63  xor     dil, dil
0x180047f66  cmp     eax, 80010106h
0x180047f6b  jnz     loc_180048015
0x180047f71  jmp     short loc_180047F76
0x180047f73  mov     dil, 1
0x180047f76  xor     edx, edx; pUnkOuter
0x180047f78  lea     rax, [rsp+48h+arg_0]
0x180047f7d  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180047f84  mov     [rsp+48h+ppv], rax; ppv
0x180047f89  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180047f90  lea     r8d, [rdx+1]; dwClsContext
0x180047f94  call    cs:__imp_CoCreateInstance
0x180047f9a  mov     ebx, eax
0x180047f9c  test    eax, eax
0x180047f9e  js      short loc_180048015
0x180047fa0  lea     rcx, aMshelpWindowsI; "mshelp://windows/?id=ca2d0191-299e-4dc3"...
0x180047fa7  call    cs:__imp_SysAllocString
0x180047fad  mov     rsi, rax
0x180047fb0  test    rax, rax
0x180047fb3  jnz     short loc_180047FCC
0x180047fb5  call    cs:__imp_GetLastError
0x180047fbb  mov     ebx, eax
0x180047fbd  test    eax, eax
0x180047fbf  jle     short loc_180048015
0x180047fc1  movzx   ebx, ax
0x180047fc4  or      ebx, 80070000h
0x180047fca  jmp     short loc_180048015
0x180047fcc  xor     ecx, ecx
0x180047fce  mov     [rsp+48h+var_18], 2
0x180047fd6  lea     rax, aNetworkConnect; "NETWORK_CONNECTIONS_HELP_BUTTON"
0x180047fdd  mov     edx, 38Fh
0x180047fe2  lea     r9, [rsp+48h+var_18]
0x180047fe7  mov     [rsp+48h+var_10], rax
0x180047fec  lea     r8d, [rcx+1]
0x180047ff0  call    cs:__imp_WinSqmAddToStream
0x180047ff6  mov     rcx, [rsp+48h+arg_0]
0x180047ffb  mov     rdx, rsi
0x180047ffe  mov     rax, [rcx]
0x180048001  mov     rax, [rax+18h]
0x180048005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004800a  mov     ebx, eax
0x18004800c  mov     rcx, rsi; bstrString
0x18004800f  call    cs:__imp_SysFreeString
0x180048015  mov     rcx, [rsp+48h+arg_0]
0x18004801a  test    rcx, rcx
0x18004801d  jz      short loc_180048034
0x18004801f  mov     rax, [rcx]
0x180048022  mov     rax, [rax+10h]
0x180048026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004802b  mov     [rsp+48h+arg_0], 0
0x180048034  test    dil, dil
0x180048037  jz      short loc_18004803F
0x180048039  call    cs:__imp_CoUninitialize
0x18004803f  mov     rsi, [rsp+48h+arg_10]
0x180048044  mov     eax, ebx
0x180048046  mov     rbx, [rsp+48h+arg_8]
0x18004804b  add     rsp, 40h
0x18004804f  pop     rdi
0x180048050  retn
```
