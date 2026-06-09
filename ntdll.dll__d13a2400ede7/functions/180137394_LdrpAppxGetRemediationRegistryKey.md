# LdrpAppxGetRemediationRegistryKey

- ea: `0x180137394`
- end: `0x180137535`
- name: `LdrpAppxGetRemediationRegistryKey`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18009d420`

## callees

- `0x180016bc0`
- `0x18003906c`
- `0x1800e937c`
- `0x180137394`
- `0x180161030`
- `0x180162810`

## string_xrefs

- `0x1801373eb`: `TargetNtPath`
- `0x1801373ce`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`

## pseudocode

```c
__int64 __fastcall LdrpAppxGetRemediationRegistryKey(int a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v9; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v10[48]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[528]; // [rsp+90h] [rbp-70h] BYREF

  memset(v10, 0, 44);
  v9 = 0;
  result = RtlGetPersistedStateLocation((wchar_t *)L"AppxStateChange", v11, 522, (__int64)&v8);
  if ( (int)result >= 0 )
  {
    if ( a1 != -1073740702 )
    {
      DWORD1(v9) = 0;
      v8 = 0;
      result = RtlStringLengthWorkerW_0(v11, 0x7FFF, &v8);
      if ( (int)result < 0 )
        return result;
      v7 = 131097;
      goto LABEL_9;
    }
    result = RtlStringCbCatW(v11, 522, L"\\PackageList\\");
    if ( (int)result >= 0 )
    {
      result = RtlStringCbCatW(v11, 522, a2);
      if ( (int)result >= 0 )
      {
        DWORD1(v9) = 0;
        v8 = 0;
        result = RtlStringLengthWorkerW_0(v11, 0x7FFF, &v8);
        if ( (int)result >= 0 )
        {
          v7 = 131353;
LABEL_9:
          *(_DWORD *)v10 = 48;
          LOWORD(v9) = 2 * v8;
          *(_QWORD *)&v10[8] = 0;
          WORD1(v9) = 2 * v8 + 2;
          *(_DWORD *)&v10[24] = 64;
          *((_QWORD *)&v9 + 1) = v11;
          *(_QWORD *)&v10[16] = &v9;
          *(_OWORD *)&v10[32] = 0;
          return NtOpenKeyEx(a3, v7, v10, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180137394  mov     [rsp-8+arg_0], rbx
0x180137399  push    rbp
0x18013739a  push    rsi
0x18013739b  push    rdi
0x18013739c  lea     rbp, [rsp-1B0h]
0x1801373a4  sub     rsp, 2B0h
0x1801373ab  mov     rax, cs:__security_cookie
0x1801373b2  xor     rax, rsp
0x1801373b5  mov     [rbp+1C0h+var_20], rax
0x1801373bc  xorps   xmm0, xmm0
0x1801373bf  xor     eax, eax
0x1801373c1  lea     rax, [rsp+2C0h+var_280]
0x1801373c6  mov     rsi, r8
0x1801373c9  mov     [rsp+2C0h+var_290], rax; __int64
0x1801373ce  lea     r8, aRegistryMachin_34; "\\Registry\\Machine\\Software\\Microsof"...
0x1801373d5  lea     rax, [rbp+1C0h+var_230]
0x1801373d9  mov     [rsp+2C0h+var_298], 20Ah; int
0x1801373e1  mov     rdi, rdx
0x1801373e4  mov     [rsp+2C0h+var_2A0], rax; void *
0x1801373e9  mov     ebx, ecx
0x1801373eb  lea     rdx, aTargetntpath; "TargetNtPath"
0x1801373f2  movups  [rsp+2C0h+var_258], xmm0
0x1801373f7  xor     r9d, r9d
0x1801373fa  lea     rcx, aAppxstatechang; "AppxStateChange"
0x180137401  movups  [rsp+2C0h+var_268], xmm0
0x180137406  movups  [rsp+2C0h+var_258+0Ch], xmm0
0x18013740b  movups  [rsp+2C0h+var_278], xmm0
0x180137410  call    RtlGetPersistedStateLocation
0x180137415  test    eax, eax
0x180137417  js      loc_180137512
0x18013741d  lea     rcx, [rbp+1C0h+var_230]
0x180137421  cmp     ebx, 0C0000462h
0x180137427  jnz     short loc_18013748E
0x180137429  lea     r8, aPackagelist; "\\PackageList\\"
0x180137430  mov     edx, 20Ah
0x180137435  call    RtlStringCbCatW
0x18013743a  test    eax, eax
0x18013743c  js      loc_180137512
0x180137442  mov     r8, rdi
0x180137445  lea     rcx, [rbp+1C0h+var_230]
0x180137449  mov     edx, 20Ah
0x18013744e  call    RtlStringCbCatW
0x180137453  test    eax, eax
0x180137455  js      loc_180137512
0x18013745b  lea     r8, [rsp+2C0h+var_280]
0x180137460  mov     dword ptr [rsp+2C0h+var_278+4], 0
0x180137468  mov     edx, 7FFFh
0x18013746d  mov     [rsp+2C0h+var_280], 0
0x180137476  lea     rcx, [rbp+1C0h+var_230]
0x18013747a  call    RtlStringLengthWorkerW_0
0x18013747f  test    eax, eax
0x180137481  js      loc_180137512
0x180137487  mov     edx, 20119h
0x18013748c  jmp     short loc_1801374B7
0x18013748e  lea     r8, [rsp+2C0h+var_280]
0x180137493  mov     dword ptr [rsp+2C0h+var_278+4], 0
0x18013749b  mov     edx, 7FFFh
0x1801374a0  mov     [rsp+2C0h+var_280], 0
0x1801374a9  call    RtlStringLengthWorkerW_0
0x1801374ae  test    eax, eax
0x1801374b0  js      short loc_180137512
0x1801374b2  mov     edx, 20019h
0x1801374b7  movzx   eax, word ptr [rsp+2C0h+var_280]
0x1801374bc  lea     r8, [rsp+2C0h+var_268]
0x1801374c1  add     ax, ax
0x1801374c4  mov     dword ptr [rsp+2C0h+var_268], 30h ; '0'
0x1801374cc  mov     word ptr [rsp+2C0h+var_278], ax
0x1801374d1  xorps   xmm0, xmm0
0x1801374d4  add     ax, 2
0x1801374d8  mov     qword ptr [rsp+2C0h+var_268+8], 0
0x1801374e1  mov     word ptr [rsp+2C0h+var_278+2], ax
0x1801374e6  xor     r9d, r9d
0x1801374e9  lea     rax, [rbp+1C0h+var_230]
0x1801374ed  mov     dword ptr [rsp+2C0h+var_258+8], 40h ; '@'
0x1801374f5  mov     qword ptr [rsp+2C0h+var_278+8], rax
0x1801374fa  mov     rcx, rsi
0x1801374fd  lea     rax, [rsp+2C0h+var_278]
0x180137502  mov     qword ptr [rsp+2C0h+var_258], rax
0x180137507  movdqu  [rsp+2C0h+var_248], xmm0
0x18013750d  call    NtOpenKeyEx
0x180137512  mov     rcx, [rbp+1C0h+var_20]
0x180137519  xor     rcx, rsp; StackCookie
0x18013751c  call    __security_check_cookie
0x180137521  mov     rbx, [rsp+2C0h+arg_0]
0x180137529  add     rsp, 2B0h
0x180137530  pop     rdi
0x180137531  pop     rsi
0x180137532  pop     rbp
0x180137533  retn
```
