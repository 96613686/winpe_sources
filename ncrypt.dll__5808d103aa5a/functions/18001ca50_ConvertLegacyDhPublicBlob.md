# ConvertLegacyDhPublicBlob

- ea: `0x18001ca50`
- end: `0x18001cb7d`
- name: `ConvertLegacyDhPublicBlob`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180017990`

## callees

- `0x18000e120`
- `0x1800146b0`
- `0x18001ca50`
- `0x18001ce88`
- `0x18001f175`
- `0x18001f1b0`

## string_xrefs

- `0x18001caa1`: `onecore\ds\security\cryptoapi\ncrypt\common\translate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyDhPublicBlob(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4, unsigned int *a5)
{
  unsigned int v7; // ebx
  __int64 v8; // r9
  size_t v9; // r11
  unsigned int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r10
  __int64 v15; // r9
  _OWORD v17[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v18; // [rsp+40h] [rbp-28h]

  v18 = 0;
  memset(v17, 0, sizeof(v17));
  if ( a1 )
  {
    if ( !(unsigned int)VerifyLegacyDhPublicBlob(a1, a2, v17) )
    {
      v10 = DWORD1(v17[0]) >> 3;
      v11 = v10 + 2 * (v10 + 4);
      *a5 = v11;
      if ( a3 )
      {
        if ( (unsigned int)v9 < v11 )
          return (unsigned int)-2146893784;
        memset_0(a3, 0, v9);
        *a3 = 1112557636;
        a3[1] = v10;
        ReverseMemCopy(a3 + 2, a1 + 48, v10);
        ReverseMemCopy(
          (unsigned int)a3[1] + v13,
          (unsigned int)a3[1] + ((unsigned __int64)DWORD2(v17[0]) >> 3) + v12,
          (unsigned int)a3[1]);
        ReverseMemCopy(
          v14 + (unsigned int)a3[1],
          v15 + a3[1] + ((unsigned int)(HIDWORD(v17[0]) + 7) >> 3),
          (unsigned int)a3[1]);
      }
      return 0;
    }
    v7 = -2146893821;
    v8 = 581;
  }
  else
  {
    v7 = -2146893785;
    v8 = 573;
  }
  DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\translate.c", v8);
  return v7;
}

```

## disassembly

```asm
0x18001ca50  mov     [rsp+arg_8], rbx
0x18001ca55  push    rsi
0x18001ca56  push    rdi
0x18001ca57  push    r14
0x18001ca59  sub     rsp, 50h
0x18001ca5d  mov     rax, cs:__security_cookie
0x18001ca64  xor     rax, rsp
0x18001ca67  mov     [rsp+68h+var_20], rax
0x18001ca6c  mov     r14, [rsp+68h+arg_20]
0x18001ca74  xor     eax, eax
0x18001ca76  mov     r11d, r9d
0x18001ca79  xorps   xmm0, xmm0
0x18001ca7c  mov     [rsp+68h+var_28], rax
0x18001ca81  mov     rsi, r8
0x18001ca84  mov     rdi, rcx
0x18001ca87  movups  [rsp+68h+var_48], xmm0
0x18001ca8c  movups  [rsp+68h+var_38], xmm0
0x18001ca91  test    rcx, rcx
0x18001ca94  jnz     short loc_18001CABB
0x18001ca96  mov     ebx, 80090027h
0x18001ca9b  mov     r9d, 23Dh
0x18001caa1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001caa8  mov     ecx, ebx
0x18001caaa  lea     rdx, aStatus; "Status"
0x18001cab1  call    DebugTraceError
0x18001cab6  jmp     loc_18001CB60
0x18001cabb  lea     r8, [rsp+68h+var_48]
0x18001cac0  call    VerifyLegacyDhPublicBlob
0x18001cac5  test    eax, eax
0x18001cac7  jz      short loc_18001CAD6
0x18001cac9  mov     ebx, 80090003h
0x18001cace  mov     r9d, 245h
0x18001cad4  jmp     short loc_18001CAA1
0x18001cad6  mov     ebx, dword ptr [rsp+68h+var_48+4]
0x18001cada  shr     ebx, 3
0x18001cadd  lea     eax, [rbx+4]
0x18001cae0  lea     eax, [rbx+rax*2]
0x18001cae3  mov     [r14], eax
0x18001cae6  test    rsi, rsi
0x18001cae9  jz      short loc_18001CB5E
0x18001caeb  cmp     r11d, eax
0x18001caee  jnb     short loc_18001CAF7
0x18001caf0  mov     ebx, 80090028h
0x18001caf5  jmp     short loc_18001CB60
0x18001caf7  mov     r8, r11; Size
0x18001cafa  xor     edx, edx; Val
0x18001cafc  mov     rcx, rsi; void *
0x18001caff  call    memset_0
0x18001cb04  lea     r9, [rdi+30h]
0x18001cb08  mov     dword ptr [rsi], 42504844h
0x18001cb0e  mov     rdx, r9
0x18001cb11  mov     [rsi+4], ebx
0x18001cb14  lea     rcx, [rsi+8]
0x18001cb18  mov     r8d, ebx
0x18001cb1b  call    ReverseMemCopy
0x18001cb20  mov     r8d, [rsi+4]
0x18001cb24  mov     eax, dword ptr [rsp+68h+var_48+8]
0x18001cb28  shr     rax, 3
0x18001cb2c  add     rax, r8
0x18001cb2f  add     r9, rax
0x18001cb32  lea     r10, [r8+rcx]
0x18001cb36  mov     rdx, r9
0x18001cb39  mov     rcx, r10
0x18001cb3c  call    ReverseMemCopy
0x18001cb41  mov     r8d, [rsi+4]
0x18001cb45  mov     edx, dword ptr [rsp+68h+var_48+0Ch]
0x18001cb49  add     edx, 7
0x18001cb4c  shr     edx, 3
0x18001cb4f  add     edx, r8d
0x18001cb52  lea     rcx, [r10+r8]
0x18001cb56  add     rdx, r9
0x18001cb59  call    ReverseMemCopy
0x18001cb5e  xor     ebx, ebx
0x18001cb60  mov     eax, ebx
0x18001cb62  mov     rcx, [rsp+68h+var_20]
0x18001cb67  xor     rcx, rsp; StackCookie
0x18001cb6a  call    __security_check_cookie
0x18001cb6f  mov     rbx, [rsp+68h+arg_8]
0x18001cb74  add     rsp, 50h
0x18001cb78  pop     r14
0x18001cb7a  pop     rdi
0x18001cb7b  pop     rsi
0x18001cb7c  retn
```
