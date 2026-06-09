# IkeMMDhInternalToDoi

- ea: `0x180037e90`
- end: `0x1800380e4`
- name: `IkeMMDhInternalToDoi`
- size: `596`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008e40`
- `0x18001fc40`
- `0x1800d04e4`
- `0x1800d66b4`
- `0x1800d680c`
- `0x1800fb478`
- `0x1800fbf50`
- `0x1800fc09c`
- `0x18010cdb0`

## callees

- `0x180037e90`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037f0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037f54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037f0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037f54`
- `ntdll!EtwEventWriteTransfer` at `0x180038056`
- `ntdll!EtwEventWriteTransfer` at `0x180038056`

## pseudocode

```c
__int64 __fastcall IkeMMDhInternalToDoi(unsigned __int16 a1)
{
  int v1; // ebx
  LPCRITICAL_SECTION v2; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v5; // rcx
  DWORD v6; // ecx
  char *v7; // rax
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  int v11; // eax
  __int64 result; // rax
  __int64 v13; // [rsp+38h] [rbp-80h] BYREF
  _DWORD v14[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v15; // [rsp+48h] [rbp-70h]
  char *v16; // [rsp+50h] [rbp-68h] BYREF
  int v17; // [rsp+58h] [rbp-60h]
  int v18; // [rsp+5Ch] [rbp-5Ch]
  int *v19; // [rsp+60h] [rbp-58h]
  int v20; // [rsp+68h] [rbp-50h]
  int v21; // [rsp+6Ch] [rbp-4Ch]
  __int64 *v22; // [rsp+70h] [rbp-48h]
  __int64 v23; // [rsp+78h] [rbp-40h]
  const WCHAR *v24; // [rsp+80h] [rbp-38h]
  int v25; // [rsp+88h] [rbp-30h]
  int v26; // [rsp+8Ch] [rbp-2Ch]
  const char *v27; // [rsp+90h] [rbp-28h]
  __int64 v28; // [rsp+98h] [rbp-20h]

  v1 = a1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v2 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v2 = gIkeExtGlobals;
LABEL_9:
    v5 = 0;
    goto LABEL_10;
  }
  v5 = *Value;
  v2 = gIkeExtGlobals;
LABEL_10:
  v13 = v5;
  v22 = &v13;
  v23 = 8;
  if ( !v2 )
    goto LABEL_18;
  v6 = (DWORD)v2[86].LockSemaphore;
  if ( v6 == -1 )
    goto LABEL_18;
  v7 = (char *)TlsGetValue(v6);
  v8 = (const WCHAR *)(v7 + 8);
  if ( !v7 )
    v8 = 0;
  if ( v8 )
  {
    v9 = -1;
    while ( v8[++v9] != 0 )
      ;
    v11 = 2 * v9 + 2;
  }
  else
  {
LABEL_18:
    v8 = &LocaleName;
    v11 = 2;
  }
  v25 = v11;
  v24 = v8;
  v27 = "IkeMMDhInternalToDoi";
  v14[1] = 5;
  v16 = off_180173280;
  v26 = 0;
  v28 = 21;
  v14[0] = 184549376;
  v15 = 1;
  v17 = *(unsigned __int16 *)off_180173280;
  v19 = &dword_180166EA4;
  v18 = 2;
  v20 = 45;
  v21 = 1;
  EtwEventWriteTransfer(qword_180173298, v14, 0, 0, 5, &v16);
LABEL_20:
  switch ( v1 )
  {
    case 0:
      result = 0;
      break;
    case 1:
      result = 1;
      break;
    case 2:
      result = 2;
      break;
    case 3:
      result = 14;
      break;
    case 4:
      result = 19;
      break;
    case 5:
      result = 20;
      break;
    case 6:
      result = 24;
      break;
    default:
      __fastfail(5u);
  }
  return result;
}

```

## disassembly

```asm
0x180037e90  mov     [rsp+arg_0], rbx
0x180037e95  mov     [rsp+arg_8], rbp
0x180037e9a  push    rsi
0x180037e9b  sub     rsp, 0B0h
0x180037ea2  mov     rax, cs:__security_cookie
0x180037ea9  xor     rax, rsp
0x180037eac  mov     [rsp+0B8h+var_18], rax
0x180037eb4  mov     eax, cs:dword_180173278
0x180037eba  mov     esi, 2
0x180037ebf  movzx   ebx, cx
0x180037ec2  mov     ebp, 1
0x180037ec7  cmp     eax, 5
0x180037eca  jbe     loc_18003805C
0x180037ed0  mov     rdx, cs:qword_180173290
0x180037ed7  mov     rax, cs:qword_180173288
0x180037ede  test    bpl, al
0x180037ee1  jz      loc_18003805C
0x180037ee7  mov     rax, rdx
0x180037eea  and     eax, ebp
0x180037eec  cmp     rax, rdx
0x180037eef  jnz     loc_18003805C
0x180037ef5  mov     rax, cs:gIkeExtGlobals
0x180037efc  test    rax, rax
0x180037eff  jz      short loc_180037F2A
0x180037f01  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037f07  cmp     ecx, 0FFFFFFFFh
0x180037f0a  jz      short loc_180037F2A
0x180037f0c  call    cs:__imp_TlsGetValue
0x180037f12  test    rax, rax
0x180037f15  jz      short loc_180037F23
0x180037f17  mov     rcx, [rax]
0x180037f1a  mov     rax, cs:gIkeExtGlobals
0x180037f21  jmp     short loc_180037F2C
0x180037f23  mov     rax, cs:gIkeExtGlobals
0x180037f2a  xor     ecx, ecx
0x180037f2c  mov     [rsp+0B8h+var_80], rcx
0x180037f31  lea     rcx, [rsp+0B8h+var_80]
0x180037f36  mov     [rsp+0B8h+var_48], rcx
0x180037f3b  mov     [rsp+0B8h+var_40], 8
0x180037f44  test    rax, rax
0x180037f47  jz      short loc_180037F95
0x180037f49  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037f4f  cmp     ecx, 0FFFFFFFFh
0x180037f52  jz      short loc_180037F95
0x180037f54  call    cs:__imp_TlsGetValue
0x180037f5a  mov     rcx, rax
0x180037f5d  lea     rdx, [rax+8]
0x180037f61  xor     eax, eax
0x180037f63  test    rcx, rcx
0x180037f66  cmovz   rdx, rax
0x180037f6a  test    rdx, rdx
0x180037f6d  jz      short loc_180037F95
0x180037f6f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180037f76  nop     word ptr [rax+rax+00000000h]
0x180037f80  cmp     word ptr [rdx+rax*2+2], 0
0x180037f86  lea     rax, [rax+1]
0x180037f8a  jnz     short loc_180037F80
0x180037f8c  lea     eax, ds:2[rax*2]
0x180037f93  jmp     short loc_180037F9E
0x180037f95  lea     rdx, LocaleName
0x180037f9c  mov     eax, esi
0x180037f9e  mov     [rsp+0B8h+var_30], eax
0x180037fa5  lea     rcx, _TraceLoggingMetadata
0x180037fac  mov     [rsp+0B8h+var_38], rdx
0x180037fb4  lea     rax, aIkemmdhinterna; "IkeMMDhInternalToDoi"
0x180037fbb  mov     [rsp+0B8h+var_28], rax
0x180037fc3  lea     rdx, [rsp+0B8h+var_78]
0x180037fc8  movzx   eax, cs:word_180166E9A
0x180037fcf  xor     r9d, r9d
0x180037fd2  mov     [rsp+0B8h+var_74], eax
0x180037fd6  xor     r8d, r8d
0x180037fd9  mov     rax, cs:off_180173280
0x180037fe0  mov     [rsp+0B8h+var_68], rax
0x180037fe5  mov     [rsp+0B8h+var_2C], 0
0x180037ff0  mov     [rsp+0B8h+var_20], 15h
0x180037ffc  mov     [rsp+0B8h+var_78], 0B000000h
0x180038004  mov     [rsp+0B8h+var_70], rbp
0x180038009  movzx   eax, word ptr [rax]
0x18003800c  mov     [rsp+0B8h+var_60], eax
0x180038010  lea     rax, dword_180166EA4
0x180038017  mov     [rsp+0B8h+var_58], rax
0x18003801c  lea     rax, _TraceLoggingMetadataEnd
0x180038023  sub     eax, ecx
0x180038025  mov     [rsp+0B8h+var_5C], esi
0x180038029  mov     [rsp+0B8h+var_50], 2Dh ; '-'
0x180038031  mov     [rsp+0B8h+var_4C], ebp
0x180038035  mov     [rsp+0B8h+var_88], eax
0x180038039  mov     eax, [rsp+0B8h+var_88]
0x18003803d  mov     rcx, cs:qword_180173298
0x180038044  lea     rax, [rsp+0B8h+var_68]
0x180038049  mov     [rsp+0B8h+var_90], rax
0x18003804e  mov     [rsp+0B8h+var_98], 5
0x180038056  call    cs:__imp_EtwEventWriteTransfer
0x18003805c  cmp     ebx, 6; switch 7 cases
0x18003805f  ja      short def_180038072; jumptable 0000000180038072 default case
0x180038061  lea     rdx, __ImageBase
0x180038068  mov     ecx, ds:(jpt_180038072 - 180000000h)[rdx+rbx*4]
0x18003806f  add     rcx, rdx
0x180038072  jmp     rcx; switch jump
0x180038074  xor     eax, eax; jumptable 0000000180038072 case 0
0x180038076  mov     rcx, [rsp+0B8h+var_18]
0x18003807e  xor     rcx, rsp; StackCookie
0x180038081  call    __security_check_cookie
0x180038086  lea     r11, [rsp+0B8h+var_8]
0x18003808e  mov     rbx, [r11+10h]
0x180038092  mov     rbp, [r11+18h]
0x180038096  mov     rsp, r11
0x180038099  pop     rsi
0x18003809a  retn
0x18003809b  movzx   eax, bp; jumptable 0000000180038072 case 1
0x18003809e  jmp     short loc_180038076
0x1800380a0  movzx   eax, si; jumptable 0000000180038072 case 2
0x1800380a3  jmp     short loc_180038076
0x1800380a5  mov     eax, 0Eh; jumptable 0000000180038072 case 3
0x1800380aa  jmp     short loc_180038076
0x1800380ac  mov     eax, 18h; jumptable 0000000180038072 case 6
0x1800380b1  jmp     short loc_180038076
0x1800380b3  mov     eax, 13h; jumptable 0000000180038072 case 4
0x1800380b8  jmp     short loc_180038076
0x1800380ba  mov     eax, 14h; jumptable 0000000180038072 case 5
0x1800380bf  jmp     short loc_180038076
0x1800380c1  mov     ecx, 5; jumptable 0000000180038072 default case
0x1800380c6  int     29h; Win8: RtlFailFast(ecx)
```
