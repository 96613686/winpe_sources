# basessp::WSTCompareCreds(basessp::_WST_CREDENTIAL *,basessp::_WST_CREDENTIAL *)

- ea: `0x180006db0`
- end: `0x180006fce`
- name: `?WSTCompareCreds@basessp@@YAHPEAU_WST_CREDENTIAL@1@0@Z`
- size: `542`
- prototype: `__int64 __fastcall(basessp *__hidden this, struct basessp::_WST_CREDENTIAL *, struct basessp::_WST_CREDENTIAL *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006d60`
- `0x1800169d4`

## callees

- `0x180006db0`
- `0x180006fd4`
- `0x18001ecee`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180006ee7`
- `ntdll!RtlCompareUnicodeString` at `0x180006f08`
- `ntdll!RtlCompareUnicodeString` at `0x180006fb8`
- `ntdll!RtlCompareUnicodeString` at `0x180006ee7`
- `ntdll!RtlCompareUnicodeString` at `0x180006f08`
- `ntdll!RtlCompareUnicodeString` at `0x180006fb8`

## pseudocode

```c
__int64 __fastcall basessp::WSTCompareCreds(
        basessp *this,
        struct basessp::_WST_CREDENTIAL *a2,
        struct basessp::_WST_CREDENTIAL *a3)
{
  __int64 result; // rax
  signed __int64 v6; // rdx
  __int64 v7; // r8
  USHORT v8; // ax
  struct basessp::_WST_CONTEXT_SUPPLIED_CREDS *v9; // r8
  struct basessp::_WST_CONTEXT_SUPPLIED_CREDS *v10; // r8
  LONG v11; // eax
  LONG v12; // eax
  __int64 i; // r8
  LONG v14; // eax
  UNICODE_STRING v15; // [rsp+20h] [rbp-B8h] BYREF
  UNICODE_STRING v16; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-98h]
  _SECPKG_SUPPLIED_CREDENTIAL v18; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int16 v19; // [rsp+78h] [rbp-60h]
  __int64 v20; // [rsp+80h] [rbp-58h]
  struct _SECPKG_SUPPLIED_CREDENTIAL v21; // [rsp+90h] [rbp-48h] BYREF
  unsigned __int16 v22; // [rsp+B8h] [rbp-20h]
  __int64 v23; // [rsp+C0h] [rbp-18h]

  if ( *(_QWORD *)this == 0x444552434F545357LL && *(_QWORD *)a2 == 0x444552434F545357LL )
  {
    v6 = *((unsigned int *)this + 16) - (unsigned __int64)*((unsigned int *)a2 + 16);
    if ( !v6 )
    {
      v6 = *((unsigned int *)this + 15) - (unsigned __int64)*((unsigned int *)a2 + 15);
      if ( !v6 )
      {
        v6 = *((unsigned int *)this + 8) - (unsigned __int64)*((unsigned int *)a2 + 8);
        if ( !v6 )
        {
          v6 = *((unsigned int *)this + 18) - (unsigned __int64)*((unsigned int *)a2 + 18);
          if ( !v6 )
          {
            v6 = *((unsigned int *)this + 17) - (unsigned __int64)*((unsigned int *)a2 + 17);
            if ( !v6 )
            {
              v7 = *((unsigned __int16 *)a2 + 44);
              v8 = *((_WORD *)this + 44);
              v6 = v8 - v7;
              if ( !v6 )
              {
                if ( !v8 )
                  goto LABEL_30;
                v16 = 0;
                v15 = 0;
                v16.Length = v8;
                v16.MaximumLength = v8;
                v16.Buffer = (PWSTR)((char *)this + *((unsigned int *)this + 21) + 16);
                v15.Length = v7;
                v15.MaximumLength = v7;
                v15.Buffer = (PWSTR)((char *)a2 + *((unsigned int *)a2 + 21) + 16);
                v14 = RtlCompareUnicodeString(&v16, &v15, 1u);
                v6 = v14;
                if ( !v14 )
                {
LABEL_30:
                  v6 = *((unsigned __int16 *)this + 53) - (unsigned __int64)*((unsigned __int16 *)a2 + 53);
                  if ( !v6 )
                  {
                    if ( *((_WORD *)this + 64) )
                    {
                      memset_0(&v18, 0, 0x40u);
                      memset_0(&v21, 0, 0x40u);
                      basessp::WSTUnpackSuppliedCreds((basessp *)((char *)this + 104), &v18, v9);
                      basessp::WSTUnpackSuppliedCreds((struct basessp::_WST_CREDENTIAL *)((char *)a2 + 104), &v21, v10);
                      v11 = RtlCompareUnicodeString(
                              (PCUNICODE_STRING)&v18.UserName.ShortArrayCount,
                              (PCUNICODE_STRING)&v21.UserName.ShortArrayCount,
                              1u);
                      v6 = v11;
                      if ( !v11 )
                      {
                        v12 = RtlCompareUnicodeString(
                                (PCUNICODE_STRING)&v18.PackedCredentials.ByteArrayLength,
                                (PCUNICODE_STRING)&v21.PackedCredentials.ByteArrayLength,
                                1u);
                        v6 = v12;
                        if ( !v12 )
                        {
                          v6 = v19 - (unsigned __int64)v22;
                          if ( v19 == (unsigned __int64)v22 )
                          {
                            for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
                            {
                              v6 = *(unsigned __int8 *)(i + v20) - (unsigned __int64)*(unsigned __int8 *)(i + v23);
                              if ( v6 )
                                break;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    result = -1;
  }
  else
  {
    result = -1;
    v6 = -1;
    v17 = -1;
  }
  if ( !v6 )
    return 0;
  if ( v6 > 0 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180006db0  mov     [rsp+arg_0], rbx
0x180006db5  mov     [rsp+arg_8], rsi
0x180006dba  push    rdi
0x180006dbb  sub     rsp, 0D0h
0x180006dc2  mov     rdi, rdx
0x180006dc5  mov     rbx, rcx
0x180006dc8  mov     rax, 444552434F545357h
0x180006dd2  cmp     [rcx], rax
0x180006dd5  jnz     short loc_180006DDC
0x180006dd7  cmp     [rdx], rax
0x180006dda  jz      short loc_180006E00
0x180006ddc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006de3  mov     rdx, rax
0x180006de6  mov     [rsp+0D8h+var_98], rax
0x180006deb  jmp     short loc_180006E1D
0x180006ded  mov     edx, 1
0x180006df2  mov     [rsp+0D8h+var_98], rdx
0x180006df7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006dfe  jmp     short loc_180006E1D
0x180006e00  mov     edx, [rcx+40h]
0x180006e03  mov     eax, [rdi+40h]
0x180006e06  sub     rdx, rax
0x180006e09  jnz     short loc_180006E16
0x180006e0b  mov     edx, [rcx+3Ch]
0x180006e0e  mov     eax, [rdi+3Ch]
0x180006e11  sub     rdx, rax
0x180006e14  jz      short loc_180006E43
0x180006e16  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006e1d  test    rdx, rdx
0x180006e20  jnz     short loc_180006E39
0x180006e22  xor     eax, eax
0x180006e24  lea     r11, [rsp+0D8h+var_8]
0x180006e2c  mov     rbx, [r11+10h]
0x180006e30  mov     rsi, [r11+18h]
0x180006e34  mov     rsp, r11
0x180006e37  pop     rdi
0x180006e38  retn
0x180006e39  mov     ecx, 1
0x180006e3e  cmovg   eax, ecx
0x180006e41  jmp     short loc_180006E24
0x180006e43  mov     edx, [rcx+20h]
0x180006e46  mov     eax, [rdi+20h]
0x180006e49  sub     rdx, rax
0x180006e4c  jnz     short loc_180006E16
0x180006e4e  mov     edx, [rcx+48h]
0x180006e51  mov     eax, [rdi+48h]
0x180006e54  sub     rdx, rax
0x180006e57  jnz     short loc_180006E16
0x180006e59  mov     edx, [rcx+44h]
0x180006e5c  mov     eax, [rdi+44h]
0x180006e5f  sub     rdx, rax
0x180006e62  jnz     short loc_180006E16
0x180006e64  movzx   r8d, word ptr [rdi+58h]
0x180006e69  movzx   eax, word ptr [rcx+58h]
0x180006e6d  mov     edx, eax
0x180006e6f  sub     rdx, r8
0x180006e72  jnz     short loc_180006E16
0x180006e74  test    ax, ax
0x180006e77  jnz     loc_180006F67
0x180006e7d  movzx   edx, word ptr [rbx+6Ah]
0x180006e81  movzx   eax, word ptr [rdi+6Ah]
0x180006e85  sub     rdx, rax; Val
0x180006e88  jnz     short loc_180006E16
0x180006e8a  cmp     [rbx+80h], dx
0x180006e91  jz      short loc_180006E16
0x180006e93  mov     r8d, 40h ; '@'; Size
0x180006e99  lea     rcx, [rsp+0D8h+var_88]; void *
0x180006e9e  call    memset_0
0x180006ea3  xor     edx, edx; Val
0x180006ea5  mov     r8d, 40h ; '@'; Size
0x180006eab  lea     rcx, [rsp+0D8h+var_48]; void *
0x180006eb3  call    memset_0
0x180006eb8  lea     rdx, [rsp+0D8h+var_88]; struct _SECPKG_SUPPLIED_CREDENTIAL *
0x180006ebd  lea     rcx, [rbx+68h]; this
0x180006ec1  call    ?WSTUnpackSuppliedCreds@basessp@@YAXPEAU_SECPKG_SUPPLIED_CREDENTIAL@@PEAU_WST_CONTEXT_SUPPLIED_CREDS@1@@Z; basessp::WSTUnpackSuppliedCreds(_SECPKG_SUPPLIED_CREDENTIAL *,basessp::_WST_CONTEXT_SUPPLIED_CREDS *)
0x180006ec6  lea     rdx, [rsp+0D8h+var_48]; struct _SECPKG_SUPPLIED_CREDENTIAL *
0x180006ece  lea     rcx, [rdi+68h]; this
0x180006ed2  call    ?WSTUnpackSuppliedCreds@basessp@@YAXPEAU_SECPKG_SUPPLIED_CREDENTIAL@@PEAU_WST_CONTEXT_SUPPLIED_CREDS@1@@Z; basessp::WSTUnpackSuppliedCreds(_SECPKG_SUPPLIED_CREDENTIAL *,basessp::_WST_CONTEXT_SUPPLIED_CREDS *)
0x180006ed7  mov     r8b, 1; CaseInsensitive
0x180006eda  lea     rdx, [rsp+0D8h+var_48.UserName.ShortArrayCount]; String2
0x180006ee2  lea     rcx, [rsp+0D8h+var_88.UserName.ShortArrayCount]; String1
0x180006ee7  call    cs:__imp_RtlCompareUnicodeString
0x180006eed  movsxd  rdx, eax
0x180006ef0  test    eax, eax
0x180006ef2  jnz     loc_180006E16
0x180006ef8  mov     r8b, 1; CaseInsensitive
0x180006efb  lea     rdx, [rsp+0D8h+var_48.PackedCredentials.ByteArrayLength]; String2
0x180006f03  lea     rcx, [rsp+0D8h+var_88.PackedCredentials.ByteArrayLength]; String1
0x180006f08  call    cs:__imp_RtlCompareUnicodeString
0x180006f0e  movsxd  rdx, eax
0x180006f11  test    eax, eax
0x180006f13  jnz     loc_180006E16
0x180006f19  movzx   eax, [rsp+0D8h+var_20]
0x180006f21  movzx   r9d, [rsp+0D8h+var_60]
0x180006f27  mov     edx, r9d
0x180006f2a  sub     rdx, rax
0x180006f2d  jnz     loc_180006E16
0x180006f33  xor     r8d, r8d
0x180006f36  mov     r10, [rsp+0D8h+var_58]
0x180006f3e  mov     r11, [rsp+0D8h+var_18]
0x180006f46  cmp     r8d, r9d
0x180006f49  jnb     loc_180006E16
0x180006f4f  movzx   ecx, byte ptr [r8+r11]
0x180006f54  movzx   edx, byte ptr [r8+r10]
0x180006f59  sub     rdx, rcx
0x180006f5c  jnz     loc_180006E16
0x180006f62  inc     r8d
0x180006f65  jmp     short loc_180006F46
0x180006f67  xorps   xmm0, xmm0
0x180006f6a  movups  xmmword ptr [rsp+0D8h+var_A8.Length], xmm0
0x180006f6f  xorps   xmm1, xmm1
0x180006f72  movups  xmmword ptr [rsp+0D8h+var_B8.Length], xmm1
0x180006f77  mov     [rsp+0D8h+var_A8.Length], ax
0x180006f7c  mov     [rsp+0D8h+var_A8.MaximumLength], ax
0x180006f81  mov     ecx, [rcx+54h]
0x180006f84  add     rcx, 10h
0x180006f88  add     rcx, rbx
0x180006f8b  mov     [rsp+0D8h+var_A8.Buffer], rcx
0x180006f90  mov     [rsp+0D8h+var_B8.Length], r8w
0x180006f96  mov     [rsp+0D8h+var_B8.MaximumLength], r8w
0x180006f9c  mov     ecx, [rdi+54h]
0x180006f9f  add     rcx, 10h
0x180006fa3  add     rcx, rdi
0x180006fa6  mov     [rsp+0D8h+var_B8.Buffer], rcx
0x180006fab  mov     r8b, 1; CaseInsensitive
0x180006fae  lea     rdx, [rsp+0D8h+var_B8]; String2
0x180006fb3  lea     rcx, [rsp+0D8h+var_A8]; String1
0x180006fb8  call    cs:__imp_RtlCompareUnicodeString
0x180006fbe  movsxd  rdx, eax
0x180006fc1  test    eax, eax
0x180006fc3  jz      loc_180006E7D
0x180006fc9  jmp     loc_180006E16
```
