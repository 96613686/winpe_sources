# _RtlpRemovePendingDeleteLanguages

- ea: `0x18014ebcc`
- end: `0x18014ed3e`
- name: `_RtlpRemovePendingDeleteLanguages`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18014e4b0`

## callees

- `0x18000c7b0`
- `0x1800c4700`
- `0x1800da250`
- `0x18014ebcc`
- `0x18015ecc0`
- `0x18015f120`
- `0x180162810`

## string_xrefs

- `0x18014ec2e`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\UILanguages\PendingDelete`

## pseudocode

```c
__int64 __fastcall RtlpRemovePendingDeleteLanguages(__int64 a1, __int16 a2)
{
  unsigned int v5; // ebx
  int v6; // esi
  __int64 v7; // rdx
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[12]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13; // [rsp+5Ch] [rbp-A4h]
  _WORD v14[248]; // [rsp+60h] [rbp-A0h] BYREF

  Handle = 0;
  v9 = 0;
  LOWORD(v8) = -1;
  DestinationString = 0;
  if ( !a1 )
    return 3221225485LL;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\UILanguages\\PendingDelete");
  if ( (int)LdrpOpenKey(&DestinationString, 0, 131097, &Handle) >= 0 )
  {
    v5 = 0;
    do
    {
      while ( 1 )
      {
        v6 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD, _BYTE *, int, int *, int))NtEnumerateKey)(
               Handle,
               v5,
               0,
               v12,
               512,
               &v9,
               v8);
        if ( v6 < 0 )
          break;
        if ( (unsigned __int64)v13 + 24 >= 0x1FE )
          break;
        v14[(unsigned __int64)v13 >> 1] = 0;
        if ( (int)RtlpMuiRegGetInstalledLanguageIndexByName(a1, v14, 0, &v8) < 0
          || (_WORD)v8 == 0xFFFF
          || (_WORD)v8 == a2 )
        {
          break;
        }
        v7 = 28LL * (__int16)v8;
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + v7) &= ~0x20u;
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + v7) |= 0x8000u;
        ++v5;
      }
      ++v5;
    }
    while ( v6 != -2147483622 );
    if ( Handle )
      NtClose(Handle);
  }
  return 0;
}

```

## disassembly

```asm
0x18014ebcc  push    rbp
0x18014ebce  push    rbx
0x18014ebcf  push    rsi
0x18014ebd0  push    rdi
0x18014ebd1  push    r14
0x18014ebd3  push    r15
0x18014ebd5  lea     rbp, [rsp-168h]
0x18014ebdd  sub     rsp, 268h
0x18014ebe4  mov     rax, cs:__security_cookie
0x18014ebeb  xor     rax, rsp
0x18014ebee  mov     [rbp+190h+var_40], rax
0x18014ebf5  or      r15d, 0FFFFFFFFh
0x18014ebf9  mov     [rsp+290h+Handle], 0
0x18014ec02  mov     [rsp+290h+var_25C], 0
0x18014ec0a  xorps   xmm0, xmm0
0x18014ec0d  mov     word ptr [rsp+290h+var_260], r15w
0x18014ec13  movzx   r14d, dx
0x18014ec17  mov     rdi, rcx
0x18014ec1a  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x18014ec1f  test    rcx, rcx
0x18014ec22  jnz     short loc_18014EC2E
0x18014ec24  mov     eax, 0C000000Dh
0x18014ec29  jmp     loc_18014ED1E
0x18014ec2e  lea     rdx, aRegistryMachin_17; "\\Registry\\Machine\\System\\CurrentCon"...
0x18014ec35  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x18014ec3a  call    RtlInitUnicodeString
0x18014ec3f  lea     r9, [rsp+290h+Handle]
0x18014ec44  xor     edx, edx
0x18014ec46  mov     r8d, 20019h
0x18014ec4c  lea     rcx, [rsp+290h+DestinationString]
0x18014ec51  call    LdrpOpenKey
0x18014ec56  test    eax, eax
0x18014ec58  js      loc_18014ED1C
0x18014ec5e  xor     ebx, ebx
0x18014ec60  mov     rcx, [rsp+290h+Handle]
0x18014ec65  lea     rax, [rsp+290h+var_25C]
0x18014ec6a  mov     [rsp+290h+var_268], rax
0x18014ec6f  lea     r9, [rsp+290h+var_240]
0x18014ec74  xor     r8d, r8d
0x18014ec77  mov     [rsp+290h+var_270], 200h
0x18014ec7f  mov     edx, ebx
0x18014ec81  call    NtEnumerateKey
0x18014ec86  mov     esi, eax
0x18014ec88  test    eax, eax
0x18014ec8a  js      short loc_18014ECFF
0x18014ec8c  mov     edx, [rsp+290h+var_234]
0x18014ec90  lea     rcx, [rdx+18h]
0x18014ec94  cmp     rcx, 1FEh
0x18014ec9b  jnb     short loc_18014ECFF
0x18014ec9d  shr     rdx, 1
0x18014eca0  lea     r9, [rsp+290h+var_260]
0x18014eca5  xor     ecx, ecx
0x18014eca7  xor     r8d, r8d
0x18014ecaa  mov     [rsp+rdx*2+290h+var_230], cx
0x18014ecaf  lea     rdx, [rsp+290h+var_230]
0x18014ecb4  mov     rcx, rdi
0x18014ecb7  call    RtlpMuiRegGetInstalledLanguageIndexByName
0x18014ecbc  test    eax, eax
0x18014ecbe  js      short loc_18014ECFF
0x18014ecc0  movsx   rax, word ptr [rsp+290h+var_260]
0x18014ecc6  cmp     r15w, ax
0x18014ecca  jz      short loc_18014ECFF
0x18014eccc  cmp     ax, r14w
0x18014ecd0  jz      short loc_18014ECFF
0x18014ecd2  imul    rdx, rax, 1Ch
0x18014ecd6  mov     rax, [rdi+18h]
0x18014ecda  mov     rcx, [rax+10h]
0x18014ecde  mov     eax, 0FFDFh
0x18014ece3  and     [rcx+rdx], ax
0x18014ece7  mov     rax, [rdi+18h]
0x18014eceb  mov     rcx, [rax+10h]
0x18014ecef  mov     eax, 8000h
0x18014ecf4  or      [rcx+rdx], ax
0x18014ecf8  inc     ebx
0x18014ecfa  jmp     loc_18014EC60
0x18014ecff  inc     ebx
0x18014ed01  cmp     esi, 8000001Ah
0x18014ed07  jnz     loc_18014EC60
0x18014ed0d  mov     rcx, [rsp+290h+Handle]; Handle
0x18014ed12  test    rcx, rcx
0x18014ed15  jz      short loc_18014ED1C
0x18014ed17  call    NtClose
0x18014ed1c  xor     eax, eax
0x18014ed1e  mov     rcx, [rbp+190h+var_40]
0x18014ed25  xor     rcx, rsp; StackCookie
0x18014ed28  call    __security_check_cookie
0x18014ed2d  add     rsp, 268h
0x18014ed34  pop     r15
0x18014ed36  pop     r14
0x18014ed38  pop     rdi
0x18014ed39  pop     rsi
0x18014ed3a  pop     rbx
0x18014ed3b  pop     rbp
0x18014ed3c  retn
```
