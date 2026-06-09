# CImpIADOSecurity::securityCheck(ushort const *,ushort const *)

- ea: `0x18002ac38`
- end: `0x18002ada4`
- name: `?securityCheck@CImpIADOSecurity@@AEAAJPEBG0@Z`
- size: `364`
- prototype: `int(CImpIADOSecurity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a4b0`

## callees

- `0x18002a920`
- `0x18002ab14`
- `0x18002ac38`
- `0x18002f086`
- `0x18002f0e0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::securityCheck(
        CImpIADOSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 result; // rax
  CImpIADOSecurity *v6; // rcx
  unsigned int v7; // edi
  struct IInternetSecurityManager *v8; // rbx
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v11; // [rsp+3Ch] [rbp-C4h] BYREF
  struct IInternetSecurityManager *v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buf2[512]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Buf1[512]; // [rsp+250h] [rbp+150h] BYREF

  v12 = 0;
  Size = 0;
  v10 = 4;
  v11 = 3;
  result = CImpIADOSecurity::getZone(this, a3, &v10, &v12);
  if ( (int)result >= 0 )
  {
    v7 = -2147024891;
    v8 = v12;
    if ( v10 )
    {
      Size = 0x20000000200LL;
      if ( ((int (__fastcall *)(struct IInternetSecurityManager *, const unsigned __int16 *, _BYTE *, size_t *, _QWORD))v12->lpVtbl->GetSecurityId)(
             v12,
             a2,
             Buf1,
             &Size,
             0) >= 0
        && ((int (__fastcall *)(struct IInternetSecurityManager *, const unsigned __int16 *, _BYTE *, char *, _QWORD))v8->lpVtbl->GetSecurityId)(
             v8,
             a3,
             Buf2,
             (char *)&Size + 4,
             0) >= 0
        && (_DWORD)Size == HIDWORD(Size) )
      {
        v7 = memcmp_0(Buf1, Buf2, (unsigned int)Size) != 0 ? 0x80070005 : 0;
      }
    }
    else if ( (int)CImpIADOSecurity::getPolicy(v6, 0, &v11) >= 0 && !v11 )
    {
      v7 = 0;
    }
    ((void (__fastcall *)(struct IInternetSecurityManager *))v8->lpVtbl->Release)(v8);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18002ac38  mov     [rsp-8+arg_0], rbx
0x18002ac3d  mov     [rsp-8+arg_18], rsi
0x18002ac42  push    rbp
0x18002ac43  push    rdi
0x18002ac44  push    r14
0x18002ac46  lea     rbp, [rsp-360h]
0x18002ac4e  sub     rsp, 460h
0x18002ac55  mov     rax, cs:__security_cookie
0x18002ac5c  xor     rax, rsp
0x18002ac5f  mov     [rbp+370h+var_20], rax
0x18002ac66  mov     rsi, r8
0x18002ac69  mov     [rsp+470h+var_430], 0
0x18002ac72  mov     r14, rdx
0x18002ac75  mov     dword ptr [rsp+470h+Size], 0
0x18002ac7d  mov     rdx, rsi; unsigned __int16 *
0x18002ac80  mov     dword ptr [rsp+470h+Size+4], 0
0x18002ac88  lea     r9, [rsp+470h+var_430]; struct IInternetSecurityManager **
0x18002ac8d  mov     [rsp+470h+var_438], 4
0x18002ac95  lea     r8, [rsp+470h+var_438]; unsigned int *
0x18002ac9a  mov     [rsp+470h+var_434], 3
0x18002aca2  call    ?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z; CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)
0x18002aca7  test    eax, eax
0x18002aca9  js      loc_18002AD7C
0x18002acaf  cmp     [rsp+470h+var_438], 0
0x18002acb4  mov     edi, 80070005h
0x18002acb9  mov     rbx, [rsp+470h+var_430]
0x18002acbe  jnz     short loc_18002ACE6
0x18002acc0  lea     r8, [rsp+470h+var_434]; unsigned int *
0x18002acc5  xor     edx, edx; unsigned int
0x18002acc7  call    ?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z; CImpIADOSecurity::getPolicy(ulong,ulong *)
0x18002accc  test    eax, eax
0x18002acce  js      loc_18002AD6B
0x18002acd4  cmp     [rsp+470h+var_434], 0
0x18002acd9  jnz     loc_18002AD6B
0x18002acdf  xor     edi, edi
0x18002ace1  jmp     loc_18002AD6B
0x18002ace6  mov     eax, 200h
0x18002aceb  mov     [rsp+470h+var_450], 0
0x18002acf4  mov     dword ptr [rsp+470h+Size], eax
0x18002acf8  lea     r9, [rsp+470h+Size]
0x18002acfd  mov     dword ptr [rsp+470h+Size+4], eax
0x18002ad01  lea     r8, [rbp+370h+Buf1]
0x18002ad08  mov     rax, [rbx]
0x18002ad0b  mov     rdx, r14
0x18002ad0e  mov     rcx, rbx
0x18002ad11  mov     rax, [rax+30h]
0x18002ad15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad1a  test    eax, eax
0x18002ad1c  js      short loc_18002AD6B
0x18002ad1e  mov     rax, [rbx]
0x18002ad21  lea     r9, [rsp+470h+Size+4]
0x18002ad26  lea     r8, [rsp+470h+Buf2]
0x18002ad2b  mov     [rsp+470h+var_450], 0
0x18002ad34  mov     rdx, rsi
0x18002ad37  mov     rcx, rbx
0x18002ad3a  mov     rax, [rax+30h]
0x18002ad3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad43  test    eax, eax
0x18002ad45  js      short loc_18002AD6B
0x18002ad47  mov     eax, dword ptr [rsp+470h+Size]
0x18002ad4b  cmp     eax, dword ptr [rsp+470h+Size+4]
0x18002ad4f  jnz     short loc_18002AD6B
0x18002ad51  mov     r8d, eax; Size
0x18002ad54  lea     rdx, [rsp+470h+Buf2]; Buf2
0x18002ad59  lea     rcx, [rbp+370h+Buf1]; Buf1
0x18002ad60  call    memcmp_0
0x18002ad65  neg     eax
0x18002ad67  sbb     eax, eax
0x18002ad69  and     edi, eax
0x18002ad6b  mov     rdx, [rbx]
0x18002ad6e  mov     rcx, rbx
0x18002ad71  mov     rax, [rdx+10h]
0x18002ad75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad7a  mov     eax, edi
0x18002ad7c  mov     rcx, [rbp+370h+var_20]
0x18002ad83  xor     rcx, rsp; StackCookie
0x18002ad86  call    __security_check_cookie
0x18002ad8b  lea     r11, [rsp+470h+var_10]
0x18002ad93  mov     rbx, [r11+20h]
0x18002ad97  mov     rsi, [r11+38h]
0x18002ad9b  mov     rsp, r11
0x18002ad9e  pop     r14
0x18002ada0  pop     rdi
0x18002ada1  pop     rbp
0x18002ada2  retn
```
