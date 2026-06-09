# DiagnosticsClient::GetHelperClassName(ushort * *)

- ea: `0x180006350`
- end: `0x1800063f2`
- name: `?GetHelperClassName@DiagnosticsClient@@UEAAJPEAPEAG@Z`
- size: `162`
- prototype: `__int64 __fastcall(DiagnosticsClient *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006350`
- `0x180006460`
- `0x18000665c`
- `0x18002c80e`

## import_xrefs

- `wdi!WdiGetParameterByIndex` at `0x180006386`
- `wdi!WdiGetParameterByIndex` at `0x180006386`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063df`

## pseudocode

```c
__int64 __fastcall DiagnosticsClient::GetHelperClassName(DiagnosticsClient *this, unsigned __int16 **a2)
{
  __int64 v2; // rcx
  int ParameterByIndex; // ebx
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF
  void *v7; // [rsp+40h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 1);
  if ( !v2 )
    return 2147942406LL;
  v7 = 0;
  String1 = 0;
  ParameterByIndex = WdiGetParameterByIndex(v2, 0, &v7);
  if ( ParameterByIndex >= 0 )
  {
    ParameterByIndex = GetNameFromWDI(v7, &String1);
    if ( ParameterByIndex >= 0 )
    {
      if ( !wcscmp_0(String1, L"HelperClassName") )
        ParameterByIndex = GetStringFromWDI(v7, a2);
      else
        ParameterByIndex = -2147024809;
    }
    if ( String1 )
      CoTaskMemFree(String1);
  }
  return (unsigned int)ParameterByIndex;
}

```

## disassembly

```asm
0x180006350  mov     [rsp+arg_8], rbx
0x180006355  push    rsi
0x180006356  sub     rsp, 20h
0x18000635a  mov     rcx, [rcx+8]
0x18000635e  mov     rsi, rdx
0x180006361  test    rcx, rcx
0x180006364  jnz     short loc_18000636D
0x180006366  mov     eax, 80070006h
0x18000636b  jmp     short loc_1800063E7
0x18000636d  lea     r8, [rsp+28h+arg_10]
0x180006372  mov     [rsp+28h+arg_10], 0
0x18000637b  xor     edx, edx
0x18000637d  mov     [rsp+28h+String1], 0
0x180006386  call    cs:__imp_WdiGetParameterByIndex
0x18000638c  mov     ebx, eax
0x18000638e  test    eax, eax
0x180006390  js      short loc_1800063E5
0x180006392  mov     rcx, [rsp+28h+arg_10]; void *
0x180006397  lea     rdx, [rsp+28h+String1]; unsigned __int16 **
0x18000639c  call    ?GetNameFromWDI@@YAJPEAXPEAPEAG@Z; GetNameFromWDI(void *,ushort * *)
0x1800063a1  mov     ebx, eax
0x1800063a3  test    eax, eax
0x1800063a5  js      short loc_1800063D2
0x1800063a7  mov     rcx, [rsp+28h+String1]; String1
0x1800063ac  lea     rdx, aHelperclassnam; "HelperClassName"
0x1800063b3  call    wcscmp_0
0x1800063b8  test    eax, eax
0x1800063ba  jz      short loc_1800063C3
0x1800063bc  mov     ebx, 80070057h
0x1800063c1  jmp     short loc_1800063D2
0x1800063c3  mov     rcx, [rsp+28h+arg_10]; void *
0x1800063c8  mov     rdx, rsi; unsigned __int16 **
0x1800063cb  call    ?GetStringFromWDI@@YAJPEAXPEAPEAG@Z; GetStringFromWDI(void *,ushort * *)
0x1800063d0  mov     ebx, eax
0x1800063d2  cmp     [rsp+28h+String1], 0
0x1800063d8  jz      short loc_1800063E5
0x1800063da  mov     rcx, [rsp+28h+String1]; pv
0x1800063df  call    cs:__imp_CoTaskMemFree
0x1800063e5  mov     eax, ebx
0x1800063e7  mov     rbx, [rsp+28h+arg_8]
0x1800063ec  add     rsp, 20h
0x1800063f0  pop     rsi
0x1800063f1  retn
```
