# LdrpResValidateFilePath

- ea: `0x1800d2f88`
- end: `0x1800d31af`
- name: `LdrpResValidateFilePath`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x1800aec20`

## callees

- `0x18001861c`
- `0x18002b030`
- `0x18006f0d0`
- `0x1800ae518`
- `0x1800d2f88`
- `0x1800d31c0`
- `0x18015f280`
- `0x180162810`

## string_xrefs

- `0x1800d2fdf`: `LdrpResValidateFilePath Enter`
- `0x1800d2ff4`: `LdrpResValidateFilePath Exit`

## pseudocode

```c
__int64 __fastcall LdrpResValidateFilePath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rcx
  signed int AttributesFile; // edi
  unsigned int v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v20; // [rsp+20h] [rbp-C8h] BYREF
  const wchar_t *v21; // [rsp+28h] [rbp-C0h]
  __int64 v22; // [rsp+30h] [rbp-B8h] BYREF
  const wchar_t *v23; // [rsp+38h] [rbp-B0h]
  unsigned int v24; // [rsp+40h] [rbp-A8h]
  __int128 v25; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v26[48]; // [rsp+58h] [rbp-90h] BYREF
  _BYTE v27[32]; // [rsp+88h] [rbp-60h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-40h]

  memset(v26, 0, 44);
  v25 = 0;
  memset(v27, 0, sizeof(v27));
  v28 = 0;
  v20 = 3932218;
  v21 = L"LdrpResValidateFilePath Enter";
  v22 = 3801144;
  v23 = L"LdrpResValidateFilePath Exit";
  v8 = 2147353477;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(a1, a2, a3, a4) )
    v9 = (__int64)NtCurrentPeb()->SharedData + 555;
  else
    v9 = 2147353477;
  if ( (*(_BYTE *)v9 & 1) != 0 )
  {
    v10 = 2147353476;
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v9, v5, v6, v7) )
      v11 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v11 = 2147353476;
    LdrpTraceLoadMUIDll(&v20, *(unsigned __int8 *)v11);
  }
  else
  {
    v10 = 2147353476;
  }
  if ( !a1 || (v13 = RtlDetermineDosPathNameType_U(a1), v5 = v13, v24 = v13, ((v13 - 1) & 0xFFFFFFFA) != 0) || v13 == 5 )
  {
    AttributesFile = -1073741811;
  }
  else if ( (unsigned __int8)((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD, __int64, const wchar_t *, __int64, const wchar_t *, unsigned int))RtlDosPathNameToNtPathName_U)(
                               a1,
                               &v25,
                               0,
                               0,
                               v20,
                               v21,
                               v22,
                               v23,
                               v24) )
  {
    v14 = *((_QWORD *)&v25 + 1);
    *(_DWORD *)v26 = 48;
    *(_QWORD *)&v26[8] = 0;
    *(_DWORD *)&v26[24] = 64;
    *(_QWORD *)&v26[16] = &v25;
    *(_OWORD *)&v26[32] = 0;
    AttributesFile = ZwQueryAttributesFile(v26, v27);
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v14);
    if ( AttributesFile >= 0 )
      AttributesFile = (v28 & 0x10) != 0 ? 0xC000000D : 0;
  }
  else
  {
    AttributesFile = -1073741766;
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v9, v5, v6, v7) )
    v8 = (__int64)NtCurrentPeb()->SharedData + 555;
  if ( (*(_BYTE *)v8 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v16, v15, v17, v18) )
      v10 = (__int64)NtCurrentPeb()->SharedData + 554;
    LdrpTraceLoadMUIDll(&v22, *(unsigned __int8 *)v10);
  }
  return (unsigned int)AttributesFile;
}

```

## disassembly

```asm
0x1800d2f88  mov     r11, rsp
0x1800d2f8b  push    rbx
0x1800d2f8c  push    rsi
0x1800d2f8d  push    rdi
0x1800d2f8e  push    r14
0x1800d2f90  sub     rsp, 0C8h
0x1800d2f97  mov     rax, cs:__security_cookie
0x1800d2f9e  xor     rax, rsp
0x1800d2fa1  mov     [rsp+0E8h+var_38], rax
0x1800d2fa9  mov     rbx, rcx
0x1800d2fac  xor     eax, eax
0x1800d2fae  xorps   xmm0, xmm0
0x1800d2fb1  movups  [rsp+0E8h+var_90], xmm0
0x1800d2fb6  movups  [rsp+0E8h+var_80], xmm0
0x1800d2fbb  movups  [rsp+0E8h+var_80+0Ch], xmm0
0x1800d2fc0  movups  [rsp+0E8h+var_A0], xmm0
0x1800d2fc5  xorps   xmm1, xmm1
0x1800d2fc8  movups  xmmword ptr [r11-60h], xmm1
0x1800d2fcd  movups  xmmword ptr [r11-50h], xmm1
0x1800d2fd2  mov     [r11-40h], rax
0x1800d2fd6  mov     [rsp+0E8h+var_C8], 3C003Ah
0x1800d2fdf  lea     rax, aLdrpresvalidat; "LdrpResValidateFilePath Enter"
0x1800d2fe6  mov     [rsp+0E8h+var_C0], rax
0x1800d2feb  mov     [rsp+0E8h+var_B8], 3A0038h
0x1800d2ff4  lea     rax, aLdrpresvalidat_0; "LdrpResValidateFilePath Exit"
0x1800d2ffb  mov     [rsp+0E8h+var_B0], rax
0x1800d3000  call    RtlGetCurrentServiceSessionId
0x1800d3005  mov     r14d, 7FFE0385h
0x1800d300b  test    eax, eax
0x1800d300d  jz      short loc_1800D3028
0x1800d300f  mov     rax, gs:60h
0x1800d3018  mov     rcx, [rax+90h]
0x1800d301f  add     rcx, 22Bh
0x1800d3026  jmp     short loc_1800D302B
0x1800d3028  mov     rcx, r14
0x1800d302b  test    byte ptr [rcx], 1
0x1800d302e  jz      short loc_1800D3069
0x1800d3030  call    RtlGetCurrentServiceSessionId
0x1800d3035  mov     esi, 7FFE0384h
0x1800d303a  test    eax, eax
0x1800d303c  jz      short loc_1800D3057
0x1800d303e  mov     rax, gs:60h
0x1800d3047  mov     rcx, [rax+90h]
0x1800d304e  add     rcx, 22Ah
0x1800d3055  jmp     short loc_1800D305A
0x1800d3057  mov     rcx, rsi
0x1800d305a  movzx   edx, byte ptr [rcx]
0x1800d305d  lea     rcx, [rsp+0E8h+var_C8]
0x1800d3062  call    LdrpTraceLoadMUIDll
0x1800d3067  jmp     short loc_1800D306E
0x1800d3069  mov     esi, 7FFE0384h
0x1800d306e  test    rbx, rbx
0x1800d3071  jnz     short loc_1800D307D
0x1800d3073  mov     edi, 0C000000Dh
0x1800d3078  jmp     loc_1800D313C
0x1800d307d  mov     rcx, rbx
0x1800d3080  call    RtlDetermineDosPathNameType_U
0x1800d3085  mov     edx, eax
0x1800d3087  mov     [rsp+0E8h+var_A8], eax
0x1800d308b  dec     eax
0x1800d308d  test    eax, 0FFFFFFFAh
0x1800d3092  jnz     short loc_1800D3073
0x1800d3094  cmp     edx, 5
0x1800d3097  jz      short loc_1800D3073
0x1800d3099  xor     r9d, r9d
0x1800d309c  xor     r8d, r8d
0x1800d309f  lea     rdx, [rsp+0E8h+var_A0]
0x1800d30a4  mov     rcx, rbx
0x1800d30a7  call    RtlDosPathNameToNtPathName_U
0x1800d30ac  test    al, al
0x1800d30ae  jnz     short loc_1800D30BA
0x1800d30b0  mov     edi, 0C000003Ah
0x1800d30b5  jmp     loc_1800D313C
0x1800d30ba  mov     rbx, qword ptr [rsp+0E8h+var_A0+8]
0x1800d30bf  mov     dword ptr [rsp+0E8h+var_90], 30h ; '0'
0x1800d30c7  mov     qword ptr [rsp+0E8h+var_90+8], 0
0x1800d30d0  mov     dword ptr [rsp+0E8h+var_80+8], 40h ; '@'
0x1800d30d8  lea     rax, [rsp+0E8h+var_A0]
0x1800d30dd  mov     qword ptr [rsp+0E8h+var_80], rax
0x1800d30e2  xorps   xmm0, xmm0
0x1800d30e5  movdqu  [rsp+0E8h+var_70], xmm0
0x1800d30eb  lea     rdx, [rsp+0E8h+var_60]
0x1800d30f3  lea     rcx, [rsp+0E8h+var_90]
0x1800d30f8  call    ZwQueryAttributesFile
0x1800d30fd  mov     edi, eax
0x1800d30ff  mov     rcx, gs:60h
0x1800d3108  mov     r8, rbx
0x1800d310b  xor     edx, edx
0x1800d310d  mov     rcx, [rcx+30h]
0x1800d3111  call    RtlFreeHeap_0
0x1800d3116  test    edi, edi
0x1800d3118  js      short loc_1800D313C
0x1800d311a  mov     rax, [rsp+0E8h+var_40]
0x1800d3122  and     al, 10h
0x1800d3124  neg     al
0x1800d3126  sbb     eax, eax
0x1800d3128  mov     edi, 0C000000Dh
0x1800d312d  and     edi, eax
0x1800d312f  jmp     short loc_1800D313C
0x1800d3131  mov     edi, eax
0x1800d3133  mov     esi, 7FFE0384h
0x1800d3138  lea     r14d, [rsi+1]
0x1800d313c  call    RtlGetCurrentServiceSessionId
0x1800d3141  test    eax, eax
0x1800d3143  jz      short loc_1800D315C
0x1800d3145  mov     rax, gs:60h
0x1800d314e  mov     r14, [rax+90h]
0x1800d3155  add     r14, 22Bh
0x1800d315c  test    byte ptr [r14], 1
0x1800d3160  jz      short loc_1800D318F
0x1800d3162  call    RtlGetCurrentServiceSessionId
0x1800d3167  test    eax, eax
0x1800d3169  jz      short loc_1800D3182
0x1800d316b  mov     rax, gs:60h
0x1800d3174  mov     rsi, [rax+90h]
0x1800d317b  add     rsi, 22Ah
0x1800d3182  movzx   edx, byte ptr [rsi]
0x1800d3185  lea     rcx, [rsp+0E8h+var_B8]
0x1800d318a  call    LdrpTraceLoadMUIDll
0x1800d318f  mov     eax, edi
0x1800d3191  mov     rcx, [rsp+0E8h+var_38]
0x1800d3199  xor     rcx, rsp; StackCookie
0x1800d319c  call    __security_check_cookie
0x1800d31a1  add     rsp, 0C8h
0x1800d31a8  pop     r14
0x1800d31aa  pop     rdi
0x1800d31ab  pop     rsi
0x1800d31ac  pop     rbx
0x1800d31ad  retn
```
