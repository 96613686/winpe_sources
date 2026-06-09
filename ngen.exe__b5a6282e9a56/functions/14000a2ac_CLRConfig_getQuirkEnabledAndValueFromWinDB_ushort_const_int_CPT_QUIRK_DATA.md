# CLRConfig::getQuirkEnabledAndValueFromWinDB(ushort const *,int *,_CPT_QUIRK_DATA *)

- ea: `0x14000a2ac`
- end: `0x14000a3b9`
- name: `?getQuirkEnabledAndValueFromWinDB@CLRConfig@@SAJPEBGPEAHPEAU_CPT_QUIRK_DATA@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(wchar_t *Source, int *, struct _CPT_QUIRK_DATA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000a3bc`
- `0x14000a610`

## callees

- `0x14000a2ac`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `ucrtbase_clr0400!wcsncpy_s` at `0x14000a32c`
- `ucrtbase_clr0400!wcsncpy_s` at `0x14000a32c`
- `ucrtbase_clr0400!wcscat_s` at `0x14000a341`
- `ucrtbase_clr0400!wcscat_s` at `0x14000a341`

## pseudocode

```c
__int64 __fastcall CLRConfig::getQuirkEnabledAndValueFromWinDB(wchar_t *Source, int *a2, struct _CPT_QUIRK_DATA *a3)
{
  unsigned __int64 v6; // rax
  unsigned __int8 v7; // al
  int v8; // ebx
  int (*v9)(const unsigned __int16 *, struct _CPT_QUIRK_DATA *); // rax
  wchar_t Sourcea[8]; // [rsp+20h] [rbp-C8h] BYREF
  wchar_t Destination[72]; // [rsp+30h] [rbp-B8h] BYREF

  if ( !Source )
    return 2147500037LL;
  v6 = -1;
  wcscpy(Sourcea, L"NETFX.");
  do
    ++v6;
  while ( Source[v6] );
  if ( v6 > 0x3C )
    return 2147500037LL;
  if ( wcsncpy_s(Destination, 0x43u, Sourcea, 6u) )
    return 2147500037LL;
  if ( wcscat_s(Destination, 0x43u, Source) )
    return 2147500037LL;
  v7 = ((__int64 (__fastcall *)(wchar_t *, __int64))CLRConfig::s_IsQuirkEnabledCallback)(Destination, 0xFFFFFFFFLL);
  v8 = v7;
  if ( v7 )
  {
    if ( a3 )
    {
      v9 = CLRConfig::s_GetQuirkValueCallback;
      *(_DWORD *)a3 = 520;
      if ( ((int (__fastcall *)(wchar_t *, struct _CPT_QUIRK_DATA *))v9)(Destination, a3) < 0 )
        return 2147500037LL;
    }
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x14000a2ac  mov     [rsp+arg_18], rbx
0x14000a2b1  push    rbp
0x14000a2b2  push    rsi
0x14000a2b3  push    rdi
0x14000a2b4  sub     rsp, 0D0h
0x14000a2bb  mov     rax, cs:__security_cookie
0x14000a2c2  xor     rax, rsp
0x14000a2c5  mov     [rsp+0E8h+var_28], rax
0x14000a2cd  xor     ebp, ebp
0x14000a2cf  mov     rdi, r8
0x14000a2d2  mov     rsi, rdx
0x14000a2d5  mov     rbx, rcx
0x14000a2d8  test    rcx, rcx
0x14000a2db  jz      loc_14000A391
0x14000a2e1  mov     eax, dword ptr cs:aNetfx+8; "X."
0x14000a2e7  movsd   xmm0, qword ptr cs:aNetfx; "NETFX."
0x14000a2ef  mov     [rsp+0E8h+var_C0], eax
0x14000a2f3  movzx   eax, word ptr cs:aNetfx+0Ch; ""
0x14000a2fa  mov     [rsp+0E8h+var_BC], ax
0x14000a2ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a303  movsd   qword ptr [rsp+0E8h+Source], xmm0
0x14000a309  inc     rax
0x14000a30c  cmp     [rcx+rax*2], bp
0x14000a310  jnz     short loc_14000A309
0x14000a312  cmp     rax, 3Ch ; '<'
0x14000a316  ja      short loc_14000A391
0x14000a318  mov     r9d, 6; MaxCount
0x14000a31e  lea     r8, [rsp+0E8h+Source]; Source
0x14000a323  lea     rcx, [rsp+0E8h+Destination]; Destination
0x14000a328  lea     edx, [r9+3Dh]; SizeInWords
0x14000a32c  call    cs:__imp_wcsncpy_s
0x14000a332  test    eax, eax
0x14000a334  jnz     short loc_14000A391
0x14000a336  mov     r8, rbx; Source
0x14000a339  lea     edx, [rax+43h]; SizeInWords
0x14000a33c  lea     rcx, [rsp+0E8h+Destination]; Destination
0x14000a341  call    cs:__imp_wcscat_s
0x14000a347  test    eax, eax
0x14000a349  jnz     short loc_14000A391
0x14000a34b  mov     rax, cs:?s_IsQuirkEnabledCallback@CLRConfig@@0P6A_NPEBGK@ZEA; bool (*CLRConfig::s_IsQuirkEnabledCallback)(ushort const *,ulong)
0x14000a352  lea     rcx, [rsp+0E8h+Destination]
0x14000a357  or      edx, 0FFFFFFFFh
0x14000a35a  call    cs:__guard_dispatch_icall_fptr
0x14000a360  movzx   ebx, al
0x14000a363  test    al, al
0x14000a365  jz      short loc_14000A38B
0x14000a367  test    rdi, rdi
0x14000a36a  jz      short loc_14000A38B
0x14000a36c  mov     rax, cs:?s_GetQuirkValueCallback@CLRConfig@@0P6AJPEBGPEAU_CPT_QUIRK_DATA@@@ZEA; long (*CLRConfig::s_GetQuirkValueCallback)(ushort const *,_CPT_QUIRK_DATA *)
0x14000a373  lea     rcx, [rsp+0E8h+Destination]
0x14000a378  mov     rdx, rdi
0x14000a37b  mov     dword ptr [rdi], 208h
0x14000a381  call    cs:__guard_dispatch_icall_fptr
0x14000a387  test    eax, eax
0x14000a389  js      short loc_14000A391
0x14000a38b  mov     [rsi], ebx
0x14000a38d  xor     eax, eax
0x14000a38f  jmp     short loc_14000A396
0x14000a391  mov     eax, 80004005h
0x14000a396  mov     rcx, [rsp+0E8h+var_28]
0x14000a39e  xor     rcx, rsp; StackCookie
0x14000a3a1  call    __security_check_cookie
0x14000a3a6  mov     rbx, [rsp+0E8h+arg_18]
0x14000a3ae  add     rsp, 0D0h
0x14000a3b5  pop     rdi
0x14000a3b6  pop     rsi
0x14000a3b7  pop     rbp
0x14000a3b8  retn
```
