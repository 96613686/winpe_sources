# _RtlpRemovePendingDeleteLanguages

- ea: `0x18014e26c`
- end: `0x18014e3de`
- name: `_RtlpRemovePendingDeleteLanguages`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18014db50`

## callees

- `0x18000c7b0`
- `0x1800c0420`
- `0x1800d97d0`
- `0x18014e26c`
- `0x18015e4b0`
- `0x18015e910`
- `0x180162000`

## string_xrefs

- `0x18014e2ce`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\UILanguages\PendingDelete`

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
0x18014e26c  push    rbp
0x18014e26e  push    rbx
0x18014e26f  push    rsi
0x18014e270  push    rdi
0x18014e271  push    r14
0x18014e273  push    r15
0x18014e275  lea     rbp, [rsp-168h]
0x18014e27d  sub     rsp, 268h
0x18014e284  mov     rax, cs:__security_cookie
0x18014e28b  xor     rax, rsp
0x18014e28e  mov     [rbp+190h+var_40], rax
0x18014e295  or      r15d, 0FFFFFFFFh
0x18014e299  mov     [rsp+290h+Handle], 0
0x18014e2a2  mov     [rsp+290h+var_25C], 0
0x18014e2aa  xorps   xmm0, xmm0
0x18014e2ad  mov     word ptr [rsp+290h+var_260], r15w
0x18014e2b3  movzx   r14d, dx
0x18014e2b7  mov     rdi, rcx
0x18014e2ba  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x18014e2bf  test    rcx, rcx
0x18014e2c2  jnz     short loc_18014E2CE
0x18014e2c4  mov     eax, 0C000000Dh
0x18014e2c9  jmp     loc_18014E3BE
0x18014e2ce  lea     rdx, aRegistryMachin_17; "\\Registry\\Machine\\System\\CurrentCon"...
0x18014e2d5  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x18014e2da  call    RtlInitUnicodeString
0x18014e2df  lea     r9, [rsp+290h+Handle]
0x18014e2e4  xor     edx, edx
0x18014e2e6  mov     r8d, 20019h
0x18014e2ec  lea     rcx, [rsp+290h+DestinationString]
0x18014e2f1  call    LdrpOpenKey
0x18014e2f6  test    eax, eax
0x18014e2f8  js      loc_18014E3BC
0x18014e2fe  xor     ebx, ebx
0x18014e300  mov     rcx, [rsp+290h+Handle]
0x18014e305  lea     rax, [rsp+290h+var_25C]
0x18014e30a  mov     [rsp+290h+var_268], rax
0x18014e30f  lea     r9, [rsp+290h+var_240]
0x18014e314  xor     r8d, r8d
0x18014e317  mov     [rsp+290h+var_270], 200h
0x18014e31f  mov     edx, ebx
0x18014e321  call    NtEnumerateKey
0x18014e326  mov     esi, eax
0x18014e328  test    eax, eax
0x18014e32a  js      short loc_18014E39F
0x18014e32c  mov     edx, [rsp+290h+var_234]
0x18014e330  lea     rcx, [rdx+18h]
0x18014e334  cmp     rcx, 1FEh
0x18014e33b  jnb     short loc_18014E39F
0x18014e33d  shr     rdx, 1
0x18014e340  lea     r9, [rsp+290h+var_260]
0x18014e345  xor     ecx, ecx
0x18014e347  xor     r8d, r8d
0x18014e34a  mov     [rsp+rdx*2+290h+var_230], cx
0x18014e34f  lea     rdx, [rsp+290h+var_230]
0x18014e354  mov     rcx, rdi
0x18014e357  call    RtlpMuiRegGetInstalledLanguageIndexByName
0x18014e35c  test    eax, eax
0x18014e35e  js      short loc_18014E39F
0x18014e360  movsx   rax, word ptr [rsp+290h+var_260]
0x18014e366  cmp     r15w, ax
0x18014e36a  jz      short loc_18014E39F
0x18014e36c  cmp     ax, r14w
0x18014e370  jz      short loc_18014E39F
0x18014e372  imul    rdx, rax, 1Ch
0x18014e376  mov     rax, [rdi+18h]
0x18014e37a  mov     rcx, [rax+10h]
0x18014e37e  mov     eax, 0FFDFh
0x18014e383  and     [rcx+rdx], ax
0x18014e387  mov     rax, [rdi+18h]
0x18014e38b  mov     rcx, [rax+10h]
0x18014e38f  mov     eax, 8000h
0x18014e394  or      [rcx+rdx], ax
0x18014e398  inc     ebx
0x18014e39a  jmp     loc_18014E300
0x18014e39f  inc     ebx
0x18014e3a1  cmp     esi, 8000001Ah
0x18014e3a7  jnz     loc_18014E300
0x18014e3ad  mov     rcx, [rsp+290h+Handle]; Handle
0x18014e3b2  test    rcx, rcx
0x18014e3b5  jz      short loc_18014E3BC
0x18014e3b7  call    NtClose
0x18014e3bc  xor     eax, eax
0x18014e3be  mov     rcx, [rbp+190h+var_40]
0x18014e3c5  xor     rcx, rsp; StackCookie
0x18014e3c8  call    __security_check_cookie
0x18014e3cd  add     rsp, 268h
0x18014e3d4  pop     r15
0x18014e3d6  pop     r14
0x18014e3d8  pop     rdi
0x18014e3d9  pop     rsi
0x18014e3da  pop     rbx
0x18014e3db  pop     rbp
0x18014e3dc  retn
```
