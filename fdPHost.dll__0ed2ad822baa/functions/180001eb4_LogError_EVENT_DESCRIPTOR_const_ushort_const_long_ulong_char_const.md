# LogError(_EVENT_DESCRIPTOR const *,ushort const *,long,ulong,char const *)

- ea: `0x180001eb4`
- end: `0x180002018`
- name: `?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@PEBGJKPEBD@Z`
- size: `356`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001950`

## callees

- `0x180001eb4`
- `0x180003150`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180001fae`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180001fae`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180001fd2`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180001fd2`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180001f92`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180001f92`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180001f0c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180001f0c`

## pseudocode

```c
__int64 __fastcall LogError(const struct _EVENT_DESCRIPTOR *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v4; // ebx
  signed int v5; // eax
  signed int v6; // edi
  ULONGLONG v7; // rcx
  __int64 v8; // rax
  signed int v9; // eax
  ULONGLONG RegHandle; // [rsp+20h] [rbp-60h] BYREF
  int v12; // [rsp+28h] [rbp-58h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-50h] BYREF
  int *v14; // [rsp+40h] [rbp-40h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  int *v16; // [rsp+50h] [rbp-30h]
  __int64 v17; // [rsp+58h] [rbp-28h]
  const char *v18; // [rsp+60h] [rbp-20h]
  __int64 v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+B0h] [rbp+30h] BYREF

  v20 = a3;
  v12 = 232;
  if ( !a2 )
    return 2147942487LL;
  RegHandle = 0;
  v4 = 0;
  v5 = EventRegister(&FDPHost, 0, 0, &RegHandle);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    else
      v4 = v5;
    v7 = 0;
    v6 = 0;
    RegHandle = 0;
  }
  else
  {
    v7 = RegHandle;
  }
  UserData.Ptr = (ULONGLONG)a2;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v8 + 2;
  v14 = &v20;
  v16 = &v12;
  v15 = 4;
  v18 = "base\\fd\\host\\fdphost.cpp";
  v17 = 4;
  v19 = 25;
  if ( !v4 )
  {
    if ( EventEnabled(v7, &ErrorRegister) )
      v6 = EventWrite(RegHandle, &ErrorRegister, 4u, &UserData);
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      else
        v4 = v6;
    }
    v7 = RegHandle;
  }
  if ( v7 )
  {
    v9 = EventUnregister(v7);
    if ( v9 )
    {
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
      else
        return (unsigned int)v9;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180001eb4  mov     [rsp-18h+arg_0], rbx
0x180001eb9  mov     [rsp-18h+arg_8], rsi
0x180001ebe  mov     [rsp-18h+arg_10], r8d
0x180001ec3  push    rbp
0x180001ec4  push    rdi
0x180001ec5  push    r14
0x180001ec7  mov     rbp, rsp
0x180001eca  sub     rsp, 80h
0x180001ed1  mov     rax, cs:__security_cookie
0x180001ed8  xor     rax, rsp
0x180001edb  mov     [rbp+var_10], rax
0x180001edf  xor     r14d, r14d
0x180001ee2  mov     [rbp+var_58], 0E8h
0x180001ee9  mov     rsi, rdx
0x180001eec  test    rdx, rdx
0x180001eef  jz      loc_180001FEF
0x180001ef5  lea     r9, [rbp+RegHandle]; RegHandle
0x180001ef9  mov     [rbp+RegHandle], r14
0x180001efd  xor     r8d, r8d; CallbackContext
0x180001f00  lea     rcx, FDPHost; ProviderId
0x180001f07  xor     edx, edx; EnableCallback
0x180001f09  mov     ebx, r14d
0x180001f0c  call    cs:__imp_EventRegister
0x180001f12  mov     edi, eax
0x180001f14  test    eax, eax
0x180001f16  jz      short loc_180001F33
0x180001f18  jg      short loc_180001F1E
0x180001f1a  mov     ebx, eax
0x180001f1c  jmp     short loc_180001F27
0x180001f1e  movzx   ebx, ax
0x180001f21  or      ebx, 80070000h
0x180001f27  mov     rcx, r14
0x180001f2a  mov     edi, r14d
0x180001f2d  mov     [rbp+RegHandle], rcx
0x180001f31  jmp     short loc_180001F37
0x180001f33  mov     rcx, [rbp+RegHandle]; RegHandle
0x180001f37  mov     [rbp+UserData.Ptr], rsi
0x180001f3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001f3f  inc     rax
0x180001f42  cmp     [rsi+rax*2], r14w
0x180001f47  jnz     short loc_180001F3F
0x180001f49  mov     dword ptr [rbp+UserData.0Ch], r14d
0x180001f4d  lea     eax, ds:2[rax*2]
0x180001f54  mov     [rbp+UserData.Size], eax
0x180001f57  lea     rax, [rbp+arg_10]
0x180001f5b  mov     [rbp+var_40], rax
0x180001f5f  lea     rax, [rbp+var_58]
0x180001f63  mov     [rbp+var_30], rax
0x180001f67  mov     esi, 4
0x180001f6c  mov     [rbp+var_38], rsi
0x180001f70  lea     rax, aBaseFdHostFdph; "base\\fd\\host\\fdphost.cpp"
0x180001f77  mov     [rbp+var_20], rax
0x180001f7b  mov     [rbp+var_28], rsi
0x180001f7f  mov     [rbp+var_18], 19h
0x180001f87  test    ebx, ebx
0x180001f89  jnz     short loc_180001FCD
0x180001f8b  lea     rdx, ErrorRegister; EventDescriptor
0x180001f92  call    cs:__imp_EventEnabled
0x180001f98  test    al, al
0x180001f9a  jz      short loc_180001FB6
0x180001f9c  mov     rcx, [rbp+RegHandle]; RegHandle
0x180001fa0  lea     r9, [rbp+UserData]; UserData
0x180001fa4  mov     r8d, esi; UserDataCount
0x180001fa7  lea     rdx, ErrorRegister; EventDescriptor
0x180001fae  call    cs:__imp_EventWrite
0x180001fb4  mov     edi, eax
0x180001fb6  test    edi, edi
0x180001fb8  jz      short loc_180001FC9
0x180001fba  jg      short loc_180001FC0
0x180001fbc  mov     ebx, edi
0x180001fbe  jmp     short loc_180001FC9
0x180001fc0  movzx   ebx, di
0x180001fc3  or      ebx, 80070000h
0x180001fc9  mov     rcx, [rbp+RegHandle]; RegHandle
0x180001fcd  test    rcx, rcx
0x180001fd0  jz      short loc_180001FEB
0x180001fd2  call    cs:__imp_EventUnregister
0x180001fd8  test    eax, eax
0x180001fda  jz      short loc_180001FEB
0x180001fdc  jg      short loc_180001FE2
0x180001fde  mov     ebx, eax
0x180001fe0  jmp     short loc_180001FEB
0x180001fe2  movzx   ebx, ax
0x180001fe5  or      ebx, 80070000h
0x180001feb  mov     eax, ebx
0x180001fed  jmp     short loc_180001FF4
0x180001fef  mov     eax, 80070057h
0x180001ff4  mov     rcx, [rbp+var_10]
0x180001ff8  xor     rcx, rsp; StackCookie
0x180001ffb  call    __security_check_cookie
0x180002000  lea     r11, [rsp+80h+var_s0]
0x180002008  mov     rbx, [r11+20h]
0x18000200c  mov     rsi, [r11+28h]
0x180002010  mov     rsp, r11
0x180002013  pop     r14
0x180002015  pop     rdi
0x180002016  pop     rbp
0x180002017  retn
```
