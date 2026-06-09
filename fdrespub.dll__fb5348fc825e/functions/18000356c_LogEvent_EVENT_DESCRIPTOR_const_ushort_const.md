# LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)

- ea: `0x18000356c`
- end: `0x180003699`
- name: `?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z`
- size: `301`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800036b0`
- `0x180003898`
- `0x18000399c`
- `0x180004220`
- `0x180004640`

## callees

- `0x18000356c`
- `0x180005270`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180003657`
- `ntdll!EtwEventUnregister` at `0x180003657`
- `ntdll!EtwEventEnabled` at `0x180003617`
- `ntdll!EtwEventEnabled` at `0x180003617`
- `ntdll!EtwEventRegister` at `0x1800035c0`
- `ntdll!EtwEventRegister` at `0x1800035c0`
- `ntdll!EtwEventWrite` at `0x180003632`
- `ntdll!EtwEventWrite` at `0x180003632`

## pseudocode

```c
__int64 __fastcall LogEvent(const struct _EVENT_DESCRIPTOR *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF
  const unsigned __int16 *v12; // [rsp+28h] [rbp-30h] BYREF
  int v13; // [rsp+30h] [rbp-28h]
  int v14; // [rsp+34h] [rbp-24h]

  if ( !a1 || !a2 )
    return 2147942487LL;
  v11 = 0;
  v4 = 0;
  v5 = EtwEventRegister(FDResPub, 0, 0, &v11);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    else
      v4 = v5;
    v7 = 0;
    v6 = 0;
    v11 = 0;
  }
  else
  {
    v7 = v11;
  }
  v12 = a2;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v14 = 0;
  v13 = 2 * v8 + 2;
  if ( !v4 )
  {
    if ( (unsigned __int8)EtwEventEnabled(v7, a1) )
      v6 = EtwEventWrite(v11, a1, 1, &v12);
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      else
        v4 = v6;
    }
    v7 = v11;
  }
  if ( v7 )
  {
    v9 = EtwEventUnregister();
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
0x18000356c  mov     r11, rsp
0x18000356f  mov     [r11+10h], rbx
0x180003573  mov     [r11+18h], rbp
0x180003577  push    rsi
0x180003578  push    rdi
0x180003579  push    r14
0x18000357b  sub     rsp, 40h
0x18000357f  mov     rax, cs:__security_cookie
0x180003586  xor     rax, rsp
0x180003589  mov     [rsp+58h+var_20], rax
0x18000358e  xor     r14d, r14d
0x180003591  mov     rsi, rdx
0x180003594  mov     rbp, rcx
0x180003597  test    rcx, rcx
0x18000359a  jz      loc_180003674
0x1800035a0  test    rdx, rdx
0x1800035a3  jz      loc_180003674
0x1800035a9  lea     r9, [r11-38h]
0x1800035ad  mov     [r11-38h], r14
0x1800035b1  xor     r8d, r8d
0x1800035b4  lea     rcx, FDResPub
0x1800035bb  xor     edx, edx
0x1800035bd  mov     ebx, r14d
0x1800035c0  call    cs:__imp_EtwEventRegister
0x1800035c6  mov     edi, eax
0x1800035c8  test    eax, eax
0x1800035ca  jz      short loc_1800035E8
0x1800035cc  jg      short loc_1800035D2
0x1800035ce  mov     ebx, eax
0x1800035d0  jmp     short loc_1800035DB
0x1800035d2  movzx   ebx, ax
0x1800035d5  or      ebx, 80070000h
0x1800035db  mov     rcx, r14
0x1800035de  mov     edi, r14d
0x1800035e1  mov     [rsp+58h+var_38], rcx
0x1800035e6  jmp     short loc_1800035ED
0x1800035e8  mov     rcx, [rsp+58h+var_38]
0x1800035ed  mov     [rsp+58h+var_30], rsi
0x1800035f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800035f6  inc     rax
0x1800035f9  cmp     [rsi+rax*2], r14w
0x1800035fe  jnz     short loc_1800035F6
0x180003600  mov     [rsp+58h+var_24], r14d
0x180003605  lea     eax, ds:2[rax*2]
0x18000360c  mov     [rsp+58h+var_28], eax
0x180003610  test    ebx, ebx
0x180003612  jnz     short loc_180003652
0x180003614  mov     rdx, rbp
0x180003617  call    cs:__imp_EtwEventEnabled
0x18000361d  test    al, al
0x18000361f  jz      short loc_18000363A
0x180003621  mov     rcx, [rsp+58h+var_38]
0x180003626  lea     r9, [rsp+58h+var_30]
0x18000362b  lea     r8d, [rbx+1]
0x18000362f  mov     rdx, rbp
0x180003632  call    cs:__imp_EtwEventWrite
0x180003638  mov     edi, eax
0x18000363a  test    edi, edi
0x18000363c  jz      short loc_18000364D
0x18000363e  jg      short loc_180003644
0x180003640  mov     ebx, edi
0x180003642  jmp     short loc_18000364D
0x180003644  movzx   ebx, di
0x180003647  or      ebx, 80070000h
0x18000364d  mov     rcx, [rsp+58h+var_38]
0x180003652  test    rcx, rcx
0x180003655  jz      short loc_180003670
0x180003657  call    cs:__imp_EtwEventUnregister
0x18000365d  test    eax, eax
0x18000365f  jz      short loc_180003670
0x180003661  jg      short loc_180003667
0x180003663  mov     ebx, eax
0x180003665  jmp     short loc_180003670
0x180003667  movzx   ebx, ax
0x18000366a  or      ebx, 80070000h
0x180003670  mov     eax, ebx
0x180003672  jmp     short loc_180003679
0x180003674  mov     eax, 80070057h
0x180003679  mov     rcx, [rsp+58h+var_20]
0x18000367e  xor     rcx, rsp; StackCookie
0x180003681  call    __security_check_cookie
0x180003686  mov     rbx, [rsp+58h+arg_8]
0x18000368b  mov     rbp, [rsp+58h+arg_10]
0x180003690  add     rsp, 40h
0x180003694  pop     r14
0x180003696  pop     rdi
0x180003697  pop     rsi
0x180003698  retn
```
