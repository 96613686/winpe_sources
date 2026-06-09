# LdrpResValidateFilePath

- ea: `0x1800d1858`
- end: `0x1800d1a7f`
- name: `LdrpResValidateFilePath`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x1800a6250`

## callees

- `0x18001861c`
- `0x18002bd30`
- `0x1800526f0`
- `0x1800a5b48`
- `0x1800d1858`
- `0x1800d1a90`
- `0x18015ea70`
- `0x180162000`

## string_xrefs

- `0x1800d18af`: `LdrpResValidateFilePath Enter`
- `0x1800d18c4`: `LdrpResValidateFilePath Exit`

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
0x1800d1858  mov     r11, rsp
0x1800d185b  push    rbx
0x1800d185c  push    rsi
0x1800d185d  push    rdi
0x1800d185e  push    r14
0x1800d1860  sub     rsp, 0C8h
0x1800d1867  mov     rax, cs:__security_cookie
0x1800d186e  xor     rax, rsp
0x1800d1871  mov     [rsp+0E8h+var_38], rax
0x1800d1879  mov     rbx, rcx
0x1800d187c  xor     eax, eax
0x1800d187e  xorps   xmm0, xmm0
0x1800d1881  movups  [rsp+0E8h+var_90], xmm0
0x1800d1886  movups  [rsp+0E8h+var_80], xmm0
0x1800d188b  movups  [rsp+0E8h+var_80+0Ch], xmm0
0x1800d1890  movups  [rsp+0E8h+var_A0], xmm0
0x1800d1895  xorps   xmm1, xmm1
0x1800d1898  movups  xmmword ptr [r11-60h], xmm1
0x1800d189d  movups  xmmword ptr [r11-50h], xmm1
0x1800d18a2  mov     [r11-40h], rax
0x1800d18a6  mov     [rsp+0E8h+var_C8], 3C003Ah
0x1800d18af  lea     rax, aLdrpresvalidat; "LdrpResValidateFilePath Enter"
0x1800d18b6  mov     [rsp+0E8h+var_C0], rax
0x1800d18bb  mov     [rsp+0E8h+var_B8], 3A0038h
0x1800d18c4  lea     rax, aLdrpresvalidat_0; "LdrpResValidateFilePath Exit"
0x1800d18cb  mov     [rsp+0E8h+var_B0], rax
0x1800d18d0  call    RtlGetCurrentServiceSessionId
0x1800d18d5  mov     r14d, 7FFE0385h
0x1800d18db  test    eax, eax
0x1800d18dd  jz      short loc_1800D18F8
0x1800d18df  mov     rax, gs:60h
0x1800d18e8  mov     rcx, [rax+90h]
0x1800d18ef  add     rcx, 22Bh
0x1800d18f6  jmp     short loc_1800D18FB
0x1800d18f8  mov     rcx, r14
0x1800d18fb  test    byte ptr [rcx], 1
0x1800d18fe  jz      short loc_1800D1939
0x1800d1900  call    RtlGetCurrentServiceSessionId
0x1800d1905  mov     esi, 7FFE0384h
0x1800d190a  test    eax, eax
0x1800d190c  jz      short loc_1800D1927
0x1800d190e  mov     rax, gs:60h
0x1800d1917  mov     rcx, [rax+90h]
0x1800d191e  add     rcx, 22Ah
0x1800d1925  jmp     short loc_1800D192A
0x1800d1927  mov     rcx, rsi
0x1800d192a  movzx   edx, byte ptr [rcx]
0x1800d192d  lea     rcx, [rsp+0E8h+var_C8]
0x1800d1932  call    LdrpTraceLoadMUIDll
0x1800d1937  jmp     short loc_1800D193E
0x1800d1939  mov     esi, 7FFE0384h
0x1800d193e  test    rbx, rbx
0x1800d1941  jnz     short loc_1800D194D
0x1800d1943  mov     edi, 0C000000Dh
0x1800d1948  jmp     loc_1800D1A0C
0x1800d194d  mov     rcx, rbx
0x1800d1950  call    RtlDetermineDosPathNameType_U
0x1800d1955  mov     edx, eax
0x1800d1957  mov     [rsp+0E8h+var_A8], eax
0x1800d195b  dec     eax
0x1800d195d  test    eax, 0FFFFFFFAh
0x1800d1962  jnz     short loc_1800D1943
0x1800d1964  cmp     edx, 5
0x1800d1967  jz      short loc_1800D1943
0x1800d1969  xor     r9d, r9d
0x1800d196c  xor     r8d, r8d
0x1800d196f  lea     rdx, [rsp+0E8h+var_A0]
0x1800d1974  mov     rcx, rbx
0x1800d1977  call    RtlDosPathNameToNtPathName_U
0x1800d197c  test    al, al
0x1800d197e  jnz     short loc_1800D198A
0x1800d1980  mov     edi, 0C000003Ah
0x1800d1985  jmp     loc_1800D1A0C
0x1800d198a  mov     rbx, qword ptr [rsp+0E8h+var_A0+8]
0x1800d198f  mov     dword ptr [rsp+0E8h+var_90], 30h ; '0'
0x1800d1997  mov     qword ptr [rsp+0E8h+var_90+8], 0
0x1800d19a0  mov     dword ptr [rsp+0E8h+var_80+8], 40h ; '@'
0x1800d19a8  lea     rax, [rsp+0E8h+var_A0]
0x1800d19ad  mov     qword ptr [rsp+0E8h+var_80], rax
0x1800d19b2  xorps   xmm0, xmm0
0x1800d19b5  movdqu  [rsp+0E8h+var_70], xmm0
0x1800d19bb  lea     rdx, [rsp+0E8h+var_60]
0x1800d19c3  lea     rcx, [rsp+0E8h+var_90]
0x1800d19c8  call    ZwQueryAttributesFile
0x1800d19cd  mov     edi, eax
0x1800d19cf  mov     rcx, gs:60h
0x1800d19d8  mov     r8, rbx
0x1800d19db  xor     edx, edx
0x1800d19dd  mov     rcx, [rcx+30h]
0x1800d19e1  call    RtlFreeHeap_0
0x1800d19e6  test    edi, edi
0x1800d19e8  js      short loc_1800D1A0C
0x1800d19ea  mov     rax, [rsp+0E8h+var_40]
0x1800d19f2  and     al, 10h
0x1800d19f4  neg     al
0x1800d19f6  sbb     eax, eax
0x1800d19f8  mov     edi, 0C000000Dh
0x1800d19fd  and     edi, eax
0x1800d19ff  jmp     short loc_1800D1A0C
0x1800d1a01  mov     edi, eax
0x1800d1a03  mov     esi, 7FFE0384h
0x1800d1a08  lea     r14d, [rsi+1]
0x1800d1a0c  call    RtlGetCurrentServiceSessionId
0x1800d1a11  test    eax, eax
0x1800d1a13  jz      short loc_1800D1A2C
0x1800d1a15  mov     rax, gs:60h
0x1800d1a1e  mov     r14, [rax+90h]
0x1800d1a25  add     r14, 22Bh
0x1800d1a2c  test    byte ptr [r14], 1
0x1800d1a30  jz      short loc_1800D1A5F
0x1800d1a32  call    RtlGetCurrentServiceSessionId
0x1800d1a37  test    eax, eax
0x1800d1a39  jz      short loc_1800D1A52
0x1800d1a3b  mov     rax, gs:60h
0x1800d1a44  mov     rsi, [rax+90h]
0x1800d1a4b  add     rsi, 22Ah
0x1800d1a52  movzx   edx, byte ptr [rsi]
0x1800d1a55  lea     rcx, [rsp+0E8h+var_B8]
0x1800d1a5a  call    LdrpTraceLoadMUIDll
0x1800d1a5f  mov     eax, edi
0x1800d1a61  mov     rcx, [rsp+0E8h+var_38]
0x1800d1a69  xor     rcx, rsp; StackCookie
0x1800d1a6c  call    __security_check_cookie
0x1800d1a71  add     rsp, 0C8h
0x1800d1a78  pop     r14
0x1800d1a7a  pop     rdi
0x1800d1a7b  pop     rsi
0x1800d1a7c  pop     rbx
0x1800d1a7d  retn
```
