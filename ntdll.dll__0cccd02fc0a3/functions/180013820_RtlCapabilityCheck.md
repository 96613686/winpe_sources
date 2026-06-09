# RtlCapabilityCheck

- ea: `0x180013820`
- end: `0x180013be4`
- name: `RtlCapabilityCheck`
- size: `964`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18010c840`

## callees

- `0x180012c8c`
- `0x180012eb0`
- `0x180013330`
- `0x180013370`
- `0x180013540`
- `0x180013820`
- `0x180013d70`
- `0x180013ed0`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180162000`

## string_xrefs

- `0x1800138f3`: `\Registry\Machine\Software\Microsoft\SecurityManager\AdminCapabilities`

## pseudocode

```c
__int64 __fastcall RtlCapabilityCheck(__int64 a1, __int64 a2, char *a3)
{
  unsigned __int8 v4; // si
  char v5; // di
  unsigned __int8 v6; // r15
  int v9; // ebx
  size_t v10; // rax
  int v11; // eax
  int v12; // eax
  bool v13; // zf
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // [rsp+38h] [rbp-D0h] BYREF
  char v19; // [rsp+3Ch] [rbp-CCh] BYREF
  char v20; // [rsp+3Dh] [rbp-CBh]
  __int64 v21; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v26[48]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-68h] BYREF
  int v28; // [rsp+B0h] [rbp-58h] BYREF
  int v29; // [rsp+B4h] [rbp-54h]
  int v30; // [rsp+B8h] [rbp-50h]
  int v31; // [rsp+BCh] [rbp-4Ch]
  _BYTE v32[48]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v33[48]; // [rsp+F0h] [rbp-18h] BYREF

  v20 = 0;
  LODWORD(v21) = 0;
  v4 = 0;
  Handle = 0;
  v5 = 0;
  v24 = 0;
  v6 = 0;
  v23 = 0;
  v19 = 0;
  v18 = 0;
  v25 = 0;
  memset(v26, 0, 44);
  v27 = 0;
  RtlQueryPerformanceCounter(&v24);
  if ( !a2 || !a3 )
  {
    v9 = -1073741811;
    goto LABEL_20;
  }
  *a3 = 0;
  v9 = RtlDeriveCapabilitySidsFromName(a2, v32, v33);
  if ( v9 < 0 )
    goto LABEL_20;
  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    goto LABEL_25;
  *(_QWORD *)&v25 = 0;
  *((_QWORD *)&v25 + 1) = L"\\Registry\\Machine\\Software\\Microsoft\\SecurityManager\\AdminCapabilities";
  v10 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Microsoft\\SecurityManager\\AdminCapabilities");
  *(_DWORD *)v26 = 48;
  *(_QWORD *)&v26[8] = 0;
  *(_DWORD *)&v26[24] = 64;
  if ( v10 >= 0xFFFE )
    LOWORD(v10) = -4;
  LOWORD(v25) = v10;
  WORD1(v25) = v10 + 2;
  *(_QWORD *)&v26[16] = &v25;
  *(_OWORD *)&v26[32] = 0;
  if ( (int)NtOpenKey(&Handle, 0x80000000LL, v26) >= 0 && (int)NtQueryValueKey(Handle, a2, 2, &v27, 16, &v21) >= 0 )
  {
    v20 = 1;
    v28 = 257;
    v29 = 83886080;
    v30 = 18;
    v11 = RtlCheckTokenMembershipEx(a1, &v28, 0, (char *)&v18 + 1);
    v5 = BYTE1(v18);
    v9 = v11;
    if ( v11 < 0 )
      goto LABEL_20;
    if ( BYTE1(v18) )
      goto LABEL_14;
    v28 = 513;
    v29 = 83886080;
    v30 = 32;
    v31 = 544;
    v12 = RtlCheckTokenMembershipEx(a1, &v28, 0, &v18);
    v4 = v18;
    v9 = v12;
    if ( v12 < 0 )
      goto LABEL_20;
    v13 = (_BYTE)v18 == 0;
  }
  else
  {
LABEL_25:
    v9 = RtlCheckTokenMembershipEx(a1, v32, 2, (char *)&v18 + 3);
    if ( v9 < 0 )
      goto LABEL_20;
    if ( HIBYTE(v18) )
      goto LABEL_14;
    v28 = 257;
    v29 = 83886080;
    v30 = 18;
    v15 = RtlCheckTokenMembershipEx(a1, &v28, 0, (char *)&v18 + 1);
    v5 = BYTE1(v18);
    v9 = v15;
    if ( v15 < 0 )
      goto LABEL_20;
    if ( BYTE1(v18) )
      goto LABEL_14;
    v28 = 513;
    v29 = 83886080;
    v30 = 32;
    v31 = 544;
    v16 = RtlCheckTokenMembershipEx(a1, &v28, 0, &v18);
    v4 = v18;
    v9 = v16;
    if ( v16 < 0 )
      goto LABEL_20;
    if ( (_BYTE)v18 )
      goto LABEL_14;
    v28 = 257;
    v29 = 83886080;
    v30 = 4;
    v17 = RtlCheckTokenMembershipEx(a1, &v28, 2, (char *)&v18 + 2);
    v6 = BYTE2(v18);
    v9 = v17;
    if ( v17 < 0 )
      goto LABEL_20;
    v13 = BYTE2(v18) == 0;
  }
  if ( !v13 )
  {
LABEL_14:
    v9 = RtlCheckTokenCapability(a1, v33, &v19);
    if ( v9 < 0 )
      goto LABEL_20;
    *a3 = v19;
  }
  if ( *a3 && !v4 && !v5 )
    v9 = RtlpCapabilityCheckSystemCapability(a1, a2, a3);
LABEL_20:
  if ( Handle )
    NtClose(Handle);
  RtlQueryPerformanceCounter(&v23);
  if ( !v5 )
    RtlpLogCapabilityCheckLatency((unsigned int)&v24, (unsigned int)&v23, v4, v6, v20, *a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013820  mov     r11, rsp
0x180013823  push    rbp
0x180013824  push    rbx
0x180013825  push    rsi
0x180013826  push    r14
0x180013828  push    r15
0x18001382a  lea     rbp, [r11-58h]
0x18001382e  sub     rsp, 130h
0x180013835  mov     rax, cs:__security_cookie
0x18001383c  xor     rax, rsp
0x18001383f  mov     [rbp+50h+var_38], rax
0x180013843  xorps   xmm0, xmm0
0x180013846  mov     [r11+20h], rdi
0x18001384a  xor     eax, eax
0x18001384c  mov     [r11-30h], r12
0x180013850  mov     r12, rcx
0x180013853  mov     [r11-38h], r13
0x180013857  xor     ecx, ecx
0x180013859  mov     [rsp+150h+var_11B], al
0x18001385d  mov     dword ptr [rsp+150h+var_118], ecx
0x180013861  xor     sil, sil
0x180013864  mov     [rsp+150h+Handle], rcx
0x180013869  xor     dil, dil
0x18001386c  mov     qword ptr [rsp+150h+var_100], rcx
0x180013871  xor     r15b, r15b
0x180013874  mov     [rsp+150h+var_108], rcx
0x180013879  mov     r14, r8
0x18001387c  movups  [rsp+150h+var_E0+8], xmm0
0x180013881  lea     rcx, [rsp+150h+var_100]
0x180013886  mov     [rsp+150h+var_11C], al
0x18001388a  mov     r13, rdx
0x18001388d  mov     byte ptr [rsp+150h+var_120], sil
0x180013892  movups  [rsp+150h+var_100+8], xmm0
0x180013897  mov     byte ptr [rsp+150h+var_120+1], dil
0x18001389c  movups  [rsp+150h+var_F0+8], xmm0
0x1800138a1  mov     byte ptr [rsp+150h+var_120+2], r15b
0x1800138a6  movups  [rbp+50h+var_CC], xmm0
0x1800138aa  mov     byte ptr [rsp+150h+var_120+3], al
0x1800138ae  movups  [rbp+50h+var_B8], xmm0
0x1800138b2  call    RtlQueryPerformanceCounter
0x1800138b7  test    r13, r13
0x1800138ba  jz      loc_180013BDA
0x1800138c0  test    r14, r14
0x1800138c3  jz      loc_180013BDA
0x1800138c9  lea     r8, [rbp+50h+var_68]
0x1800138cd  mov     [r14], sil
0x1800138d0  lea     rdx, [rbp+50h+var_98]
0x1800138d4  mov     rcx, r13
0x1800138d7  call    RtlDeriveCapabilitySidsFromName
0x1800138dc  mov     ebx, eax
0x1800138de  test    eax, eax
0x1800138e0  js      loc_180013A65
0x1800138e6  call    RtlIsMultiSessionSku
0x1800138eb  test    al, al
0x1800138ed  jz      loc_180013AE1
0x1800138f3  lea     rcx, aRegistryMachin_19; "\\Registry\\Machine\\Software\\Microsof"...
0x1800138fa  mov     qword ptr [rsp+150h+var_100+8], 0
0x180013903  mov     qword ptr [rsp+150h+var_F0], rcx
0x180013908  call    wcslen
0x18001390d  add     rax, rax
0x180013910  mov     dword ptr [rsp+150h+var_F0+8], 30h ; '0'
0x180013918  cmp     rax, 0FFFEh
0x18001391e  mov     qword ptr [rsp+150h+var_E0], 0
0x180013927  mov     ecx, 0FFFCh
0x18001392c  mov     [rbp+50h+var_D0], 40h ; '@'
0x180013933  cmovnb  rax, rcx
0x180013937  lea     r8, [rsp+150h+var_F0+8]
0x18001393c  mov     word ptr [rsp+150h+var_100+8], ax
0x180013941  lea     rcx, [rsp+150h+Handle]
0x180013946  add     ax, 2
0x18001394a  xorps   xmm0, xmm0
0x18001394d  mov     word ptr [rsp+150h+var_100+0Ah], ax
0x180013952  mov     edx, 80000000h
0x180013957  lea     rax, [rsp+150h+var_100+8]
0x18001395c  mov     qword ptr [rsp+150h+var_E0+8], rax
0x180013961  movdqu  [rbp+50h+var_CC+4], xmm0
0x180013966  call    NtOpenKey
0x18001396b  test    eax, eax
0x18001396d  js      loc_180013AE1
0x180013973  mov     rcx, [rsp+150h+Handle]
0x180013978  lea     rax, [rsp+150h+var_118]
0x18001397d  mov     qword ptr [rsp+150h+var_128], rax
0x180013982  lea     r9, [rbp+50h+var_B8]
0x180013986  mov     r8d, 2
0x18001398c  mov     dword ptr [rsp+150h+var_130], 10h
0x180013994  mov     rdx, r13
0x180013997  call    NtQueryValueKey
0x18001399c  test    eax, eax
0x18001399e  js      loc_180013AE1
0x1800139a4  lea     r9, [rsp+150h+var_120+1]
0x1800139a9  mov     [rsp+150h+var_11B], 1
0x1800139ae  xor     r8d, r8d
0x1800139b1  mov     [rbp+50h+var_A8], 101h
0x1800139b8  lea     rdx, [rbp+50h+var_A8]
0x1800139bc  mov     [rbp+50h+var_A4], 5000000h
0x1800139c3  mov     rcx, r12
0x1800139c6  mov     [rbp+50h+var_A0], 12h
0x1800139cd  call    RtlCheckTokenMembershipEx
0x1800139d2  movzx   edi, byte ptr [rsp+150h+var_120+1]
0x1800139d7  mov     ebx, eax
0x1800139d9  test    eax, eax
0x1800139db  js      loc_180013A65
0x1800139e1  test    dil, dil
0x1800139e4  jnz     short loc_180013A26
0x1800139e6  lea     r9, [rsp+150h+var_120]
0x1800139eb  mov     [rbp+50h+var_A8], 201h
0x1800139f2  xor     r8d, r8d
0x1800139f5  mov     [rbp+50h+var_A4], 5000000h
0x1800139fc  lea     rdx, [rbp+50h+var_A8]
0x180013a00  mov     [rbp+50h+var_A0], 20h ; ' '
0x180013a07  mov     rcx, r12
0x180013a0a  mov     [rbp+50h+var_9C], 220h
0x180013a11  call    RtlCheckTokenMembershipEx
0x180013a16  movzx   esi, byte ptr [rsp+150h+var_120]
0x180013a1b  mov     ebx, eax
0x180013a1d  test    eax, eax
0x180013a1f  js      short loc_180013A65
0x180013a21  test    sil, sil
0x180013a24  jz      short loc_180013A45
0x180013a26  lea     r8, [rsp+150h+var_11C]
0x180013a2b  mov     rcx, r12
0x180013a2e  lea     rdx, [rbp+50h+var_68]
0x180013a32  call    RtlCheckTokenCapability
0x180013a37  mov     ebx, eax
0x180013a39  test    eax, eax
0x180013a3b  js      short loc_180013A65
0x180013a3d  movzx   eax, [rsp+150h+var_11C]
0x180013a42  mov     [r14], al
0x180013a45  cmp     byte ptr [r14], 0
0x180013a49  jz      short loc_180013A65
0x180013a4b  test    sil, sil
0x180013a4e  jnz     short loc_180013A65
0x180013a50  test    dil, dil
0x180013a53  jnz     short loc_180013A65
0x180013a55  mov     r8, r14
0x180013a58  mov     rdx, r13
0x180013a5b  mov     rcx, r12
0x180013a5e  call    RtlpCapabilityCheckSystemCapability
0x180013a63  mov     ebx, eax
0x180013a65  mov     rcx, [rsp+150h+Handle]; Handle
0x180013a6a  mov     r13, [rsp+150h+var_30]
0x180013a72  mov     r12, [rsp+128h]
0x180013a7a  test    rcx, rcx
0x180013a7d  jz      short loc_180013A84
0x180013a7f  call    NtClose
0x180013a84  lea     rcx, [rsp+150h+var_108]
0x180013a89  call    RtlQueryPerformanceCounter
0x180013a8e  test    dil, dil
0x180013a91  mov     rdi, [rsp+150h+arg_18]
0x180013a99  jnz     short loc_180013AC3
0x180013a9b  movzx   eax, byte ptr [r14]
0x180013a9f  lea     rdx, [rsp+150h+var_108]
0x180013aa4  mov     [rsp+150h+var_128], al
0x180013aa8  lea     rcx, [rsp+150h+var_100]
0x180013aad  movzx   eax, [rsp+150h+var_11B]
0x180013ab2  movzx   r9d, r15b
0x180013ab6  movzx   r8d, sil
0x180013aba  mov     byte ptr [rsp+150h+var_130], al
0x180013abe  call    RtlpLogCapabilityCheckLatency
0x180013ac3  mov     eax, ebx
0x180013ac5  mov     rcx, [rbp+50h+var_38]
0x180013ac9  xor     rcx, rsp; StackCookie
0x180013acc  call    __security_check_cookie
0x180013ad1  add     rsp, 130h
0x180013ad8  pop     r15
0x180013ada  pop     r14
0x180013adc  pop     rsi
0x180013add  pop     rbx
0x180013ade  pop     rbp
0x180013adf  retn
0x180013ae1  lea     r9, [rsp+150h+var_120+3]
0x180013ae6  mov     r8d, 2
0x180013aec  lea     rdx, [rbp+50h+var_98]
0x180013af0  mov     rcx, r12
0x180013af3  call    RtlCheckTokenMembershipEx
0x180013af8  mov     ebx, eax
0x180013afa  test    eax, eax
0x180013afc  js      loc_180013A65
0x180013b02  cmp     byte ptr [rsp+150h+var_120+3], sil
0x180013b07  jnz     loc_180013A26
0x180013b0d  lea     r9, [rsp+150h+var_120+1]
0x180013b12  mov     [rbp+50h+var_A8], 101h
0x180013b19  xor     r8d, r8d
0x180013b1c  mov     [rbp+50h+var_A4], 5000000h
0x180013b23  lea     rdx, [rbp+50h+var_A8]
0x180013b27  mov     [rbp+50h+var_A0], 12h
0x180013b2e  mov     rcx, r12
0x180013b31  call    RtlCheckTokenMembershipEx
0x180013b36  movzx   edi, byte ptr [rsp+150h+var_120+1]
0x180013b3b  mov     ebx, eax
0x180013b3d  test    eax, eax
0x180013b3f  js      loc_180013A65
0x180013b45  test    dil, dil
0x180013b48  jnz     loc_180013A26
0x180013b4e  lea     r9, [rsp+150h+var_120]
0x180013b53  mov     [rbp+50h+var_A8], 201h
0x180013b5a  xor     r8d, r8d
0x180013b5d  mov     [rbp+50h+var_A4], 5000000h
0x180013b64  lea     rdx, [rbp+50h+var_A8]
0x180013b68  mov     [rbp+50h+var_A0], 20h ; ' '
0x180013b6f  mov     rcx, r12
0x180013b72  mov     [rbp+50h+var_9C], 220h
0x180013b79  call    RtlCheckTokenMembershipEx
0x180013b7e  movzx   esi, byte ptr [rsp+150h+var_120]
0x180013b83  mov     ebx, eax
0x180013b85  test    eax, eax
0x180013b87  js      loc_180013A65
0x180013b8d  test    sil, sil
0x180013b90  jnz     loc_180013A26
0x180013b96  lea     r9, [rsp+150h+var_120+2]
0x180013b9b  mov     [rbp+50h+var_A8], 101h
0x180013ba2  mov     r8d, 2
0x180013ba8  mov     [rbp+50h+var_A4], 5000000h
0x180013baf  lea     rdx, [rbp+50h+var_A8]
0x180013bb3  mov     [rbp+50h+var_A0], 4
0x180013bba  mov     rcx, r12
0x180013bbd  call    RtlCheckTokenMembershipEx
0x180013bc2  movzx   r15d, byte ptr [rsp+150h+var_120+2]
0x180013bc8  mov     ebx, eax
0x180013bca  test    eax, eax
0x180013bcc  js      loc_180013A65
0x180013bd2  test    r15b, r15b
0x180013bd5  jmp     loc_180013A24
0x180013bda  mov     ebx, 0C000000Dh
0x180013bdf  jmp     loc_180013A65
```
