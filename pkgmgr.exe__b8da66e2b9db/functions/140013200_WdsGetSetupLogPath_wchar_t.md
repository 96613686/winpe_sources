# WdsGetSetupLogPath(wchar_t * *)

- ea: `0x140013200`
- end: `0x140013280`
- name: `?WdsGetSetupLogPath@@YAJPEAPEA_W@Z`
- size: `128`
- prototype: `__int64 __fastcall(wchar_t **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140013288`

## callees

- `0x14000726c`
- `0x140013200`
- `0x140017eb4`

## string_xrefs

- `0x140013233`: `WorkingDirectory`

## pseudocode

```c
__int64 __fastcall WdsGetSetupLogPath(wchar_t **a1, __int64 a2, __int64 a3)
{
  int StringValue; // edi
  wchar_t *v5; // rcx
  wchar_t *v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v7[1] = (wchar_t *)-2LL;
  v7[0] = 0;
  if ( a1 )
    *a1 = 0;
  StringValue = CbsRegQueryStringValue((HKEY)a1, L"SYSTEM\\Setup", a3, L"WorkingDirectory", v7);
  if ( StringValue >= 0 )
  {
    v5 = v7[0];
    if ( *v7[0] )
    {
      v7[0] = 0;
      if ( a1 )
        *a1 = v5;
    }
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v7);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x140013200  mov     rax, rsp
0x140013203  push    rdi
0x140013204  sub     rsp, 40h
0x140013208  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x140013210  mov     [rax+10h], rbx
0x140013214  mov     [rax+18h], rsi
0x140013218  mov     rbx, rcx
0x14001321b  xor     esi, esi
0x14001321d  mov     [rax-18h], rsi
0x140013221  test    rcx, rcx
0x140013224  jz      short loc_140013229
0x140013226  mov     [rcx], rsi
0x140013229  lea     rax, [rsp+48h+var_18]
0x14001322e  mov     [rsp+48h+var_28], rax; wchar_t **
0x140013233  lea     r9, aWorkingdirecto; "WorkingDirectory"
0x14001323a  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x140013241  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x140013246  mov     edi, eax
0x140013248  test    eax, eax
0x14001324a  js      short loc_140013263
0x14001324c  mov     rcx, [rsp+48h+var_18]
0x140013251  cmp     [rcx], si
0x140013254  jz      short loc_140013263
0x140013256  mov     [rsp+48h+var_18], rsi
0x14001325b  test    rbx, rbx
0x14001325e  jz      short loc_140013263
0x140013260  mov     [rbx], rcx
0x140013263  lea     rcx, [rsp+48h+var_18]
0x140013268  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001326d  nop
0x14001326e  mov     eax, edi
0x140013270  mov     rbx, [rsp+48h+arg_8]
0x140013275  mov     rsi, [rsp+48h+arg_10]
0x14001327a  add     rsp, 40h
0x14001327e  pop     rdi
0x14001327f  retn
```
