# LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)

- ea: `0x180003404`
- end: `0x180003564`
- name: `?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z`
- size: `352`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR *, int, const unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001cc0`
- `0x1800022b4`
- `0x180002f24`
- `0x180003ae8`
- `0x180004220`
- `0x180004498`

## callees

- `0x180003404`
- `0x180005270`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18000351e`
- `ntdll!EtwEventUnregister` at `0x18000351e`
- `ntdll!EtwEventEnabled` at `0x1800034de`
- `ntdll!EtwEventEnabled` at `0x1800034de`
- `ntdll!EtwEventRegister` at `0x180003458`
- `ntdll!EtwEventRegister` at `0x180003458`
- `ntdll!EtwEventWrite` at `0x1800034fa`
- `ntdll!EtwEventWrite` at `0x1800034fa`

## pseudocode

```c
__int64 __fastcall LogError(const struct _EVENT_DESCRIPTOR *a1, int a2, const unsigned __int16 *a3, int a4)
{
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 v12; // [rsp+20h] [rbp-60h] BYREF
  const unsigned __int16 *v13; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+38h] [rbp-48h]
  int v15; // [rsp+3Ch] [rbp-44h]
  int *v16; // [rsp+40h] [rbp-40h]
  __int64 v17; // [rsp+48h] [rbp-38h]
  int *v18; // [rsp+50h] [rbp-30h]
  __int64 v19; // [rsp+58h] [rbp-28h]
  const char *v20; // [rsp+60h] [rbp-20h]
  __int64 v21; // [rsp+68h] [rbp-18h]
  int v22; // [rsp+A8h] [rbp+28h] BYREF
  int v23; // [rsp+B8h] [rbp+38h] BYREF

  v23 = a4;
  v22 = a2;
  if ( !a3 )
    return 2147942487LL;
  v12 = 0;
  v5 = 0;
  v6 = EtwEventRegister(FDResPub, 0, 0, &v12);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
    v8 = 0;
    v7 = 0;
    v12 = 0;
  }
  else
  {
    v8 = v12;
  }
  v13 = a3;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v15 = 0;
  v14 = 2 * v9 + 2;
  v16 = &v22;
  v18 = &v23;
  v17 = 4;
  v20 = "base\\fd\\publishing\\respubsvc\\respubwsd.cpp";
  v19 = 4;
  v21 = 43;
  if ( !v5 )
  {
    if ( (unsigned __int8)EtwEventEnabled(v8, ErrorFcnCall) )
      v7 = EtwEventWrite(v12, ErrorFcnCall, 4, &v13);
    if ( v7 )
    {
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      else
        v5 = v7;
    }
    v8 = v12;
  }
  if ( v8 )
  {
    v10 = EtwEventUnregister();
    if ( v10 )
    {
      if ( v10 > 0 )
        return (unsigned __int16)v10 | 0x80070000;
      else
        return (unsigned int)v10;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180003404  mov     rax, rsp
0x180003407  mov     [rax+8], rbx
0x18000340b  mov     [rax+18h], rsi
0x18000340f  mov     [rax+20h], r9d
0x180003413  mov     [rax+10h], edx
0x180003416  push    rbp
0x180003417  push    rdi
0x180003418  push    r14
0x18000341a  mov     rbp, rsp
0x18000341d  sub     rsp, 80h
0x180003424  mov     rax, cs:__security_cookie
0x18000342b  xor     rax, rsp
0x18000342e  mov     [rbp+var_10], rax
0x180003432  xor     r14d, r14d
0x180003435  mov     rsi, r8
0x180003438  test    r8, r8
0x18000343b  jz      loc_18000353B
0x180003441  lea     r9, [rbp+var_60]
0x180003445  mov     [rbp+var_60], r14
0x180003449  xor     r8d, r8d
0x18000344c  lea     rcx, FDResPub
0x180003453  xor     edx, edx
0x180003455  mov     ebx, r14d
0x180003458  call    cs:__imp_EtwEventRegister
0x18000345e  mov     edi, eax
0x180003460  test    eax, eax
0x180003462  jz      short loc_18000347F
0x180003464  jg      short loc_18000346A
0x180003466  mov     ebx, eax
0x180003468  jmp     short loc_180003473
0x18000346a  movzx   ebx, ax
0x18000346d  or      ebx, 80070000h
0x180003473  mov     rcx, r14
0x180003476  mov     edi, r14d
0x180003479  mov     [rbp+var_60], rcx
0x18000347d  jmp     short loc_180003483
0x18000347f  mov     rcx, [rbp+var_60]
0x180003483  mov     [rbp+var_50], rsi
0x180003487  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000348b  inc     rax
0x18000348e  cmp     [rsi+rax*2], r14w
0x180003493  jnz     short loc_18000348B
0x180003495  mov     [rbp+var_44], r14d
0x180003499  lea     eax, ds:2[rax*2]
0x1800034a0  mov     [rbp+var_48], eax
0x1800034a3  lea     rax, [rbp+arg_8]
0x1800034a7  mov     [rbp+var_40], rax
0x1800034ab  lea     rax, [rbp+arg_18]
0x1800034af  mov     [rbp+var_30], rax
0x1800034b3  mov     esi, 4
0x1800034b8  mov     [rbp+var_38], rsi
0x1800034bc  lea     rax, aBaseFdPublishi; "base\\fd\\publishing\\respubsvc\\respub"...
0x1800034c3  mov     [rbp+var_20], rax
0x1800034c7  mov     [rbp+var_28], rsi
0x1800034cb  mov     [rbp+var_18], 2Bh ; '+'
0x1800034d3  test    ebx, ebx
0x1800034d5  jnz     short loc_180003519
0x1800034d7  lea     rdx, ErrorFcnCall
0x1800034de  call    cs:__imp_EtwEventEnabled
0x1800034e4  test    al, al
0x1800034e6  jz      short loc_180003502
0x1800034e8  mov     rcx, [rbp+var_60]
0x1800034ec  lea     r9, [rbp+var_50]
0x1800034f0  mov     r8d, esi
0x1800034f3  lea     rdx, ErrorFcnCall
0x1800034fa  call    cs:__imp_EtwEventWrite
0x180003500  mov     edi, eax
0x180003502  test    edi, edi
0x180003504  jz      short loc_180003515
0x180003506  jg      short loc_18000350C
0x180003508  mov     ebx, edi
0x18000350a  jmp     short loc_180003515
0x18000350c  movzx   ebx, di
0x18000350f  or      ebx, 80070000h
0x180003515  mov     rcx, [rbp+var_60]
0x180003519  test    rcx, rcx
0x18000351c  jz      short loc_180003537
0x18000351e  call    cs:__imp_EtwEventUnregister
0x180003524  test    eax, eax
0x180003526  jz      short loc_180003537
0x180003528  jg      short loc_18000352E
0x18000352a  mov     ebx, eax
0x18000352c  jmp     short loc_180003537
0x18000352e  movzx   ebx, ax
0x180003531  or      ebx, 80070000h
0x180003537  mov     eax, ebx
0x180003539  jmp     short loc_180003540
0x18000353b  mov     eax, 80070057h
0x180003540  mov     rcx, [rbp+var_10]
0x180003544  xor     rcx, rsp; StackCookie
0x180003547  call    __security_check_cookie
0x18000354c  lea     r11, [rsp+80h+var_s0]
0x180003554  mov     rbx, [r11+20h]
0x180003558  mov     rsi, [r11+30h]
0x18000355c  mov     rsp, r11
0x18000355f  pop     r14
0x180003561  pop     rdi
0x180003562  pop     rbp
0x180003563  retn
```
