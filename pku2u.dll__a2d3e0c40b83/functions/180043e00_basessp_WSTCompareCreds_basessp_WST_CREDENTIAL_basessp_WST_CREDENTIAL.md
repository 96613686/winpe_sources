# basessp::WSTCompareCreds(basessp::_WST_CREDENTIAL *,basessp::_WST_CREDENTIAL *)

- ea: `0x180043e00`
- end: `0x18004402f`
- name: `?WSTCompareCreds@basessp@@YAHPEAU_WST_CREDENTIAL@1@0@Z`
- size: `559`
- prototype: `int(basessp *__hidden this, struct basessp::_WST_CREDENTIAL *, struct basessp::_WST_CREDENTIAL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044040`

## callees

- `0x180021a54`
- `0x180043cc0`
- `0x180043e00`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180043ef1`
- `ntdll!RtlCompareUnicodeString` at `0x180043f76`
- `ntdll!RtlCompareUnicodeString` at `0x180043f93`
- `ntdll!RtlCompareUnicodeString` at `0x180043ef1`
- `ntdll!RtlCompareUnicodeString` at `0x180043f76`
- `ntdll!RtlCompareUnicodeString` at `0x180043f93`

## pseudocode

```c
__int64 __fastcall basessp::WSTCompareCreds(
        basessp *this,
        struct basessp::_WST_CREDENTIAL *a2,
        struct basessp::_WST_CREDENTIAL *a3)
{
  signed __int64 v5; // rdx
  __int64 v6; // r8
  USHORT v7; // ax
  LONG v8; // eax
  struct basessp::_WST_CONTEXT_SUPPLIED_CREDS *v9; // r8
  struct basessp::_WST_CONTEXT_SUPPLIED_CREDS *v10; // r8
  LONG v11; // eax
  LONG v12; // eax
  unsigned int i; // r8d
  __int64 result; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-D8h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-B8h]
  _SECPKG_SUPPLIED_CREDENTIAL v18; // [rsp+50h] [rbp-A8h] BYREF
  unsigned __int16 v19; // [rsp+78h] [rbp-80h]
  __int64 v20; // [rsp+80h] [rbp-78h]
  struct _SECPKG_SUPPLIED_CREDENTIAL v21; // [rsp+90h] [rbp-68h] BYREF
  unsigned __int16 v22; // [rsp+B8h] [rbp-40h]
  __int64 v23; // [rsp+C0h] [rbp-38h]

  if ( *(_QWORD *)this == 0x444552434F545357LL && *(_QWORD *)a2 == 0x444552434F545357LL )
  {
    v5 = *((unsigned int *)this + 16) - (unsigned __int64)*((unsigned int *)a2 + 16);
    if ( !v5 )
    {
      v5 = *((unsigned int *)this + 15) - (unsigned __int64)*((unsigned int *)a2 + 15);
      if ( !v5 )
      {
        v5 = *((unsigned int *)this + 8) - (unsigned __int64)*((unsigned int *)a2 + 8);
        if ( !v5 )
        {
          v5 = *((unsigned int *)this + 18) - (unsigned __int64)*((unsigned int *)a2 + 18);
          if ( !v5 )
          {
            v5 = *((unsigned int *)this + 17) - (unsigned __int64)*((unsigned int *)a2 + 17);
            if ( !v5 )
            {
              v6 = *((unsigned __int16 *)a2 + 44);
              v7 = *((_WORD *)this + 44);
              v5 = v7 - v6;
              if ( !v5 )
              {
                if ( !v7 )
                  goto LABEL_28;
                String1 = 0;
                String2 = 0;
                String1.Length = v7;
                String1.MaximumLength = v7;
                String1.Buffer = (PWSTR)((char *)this + *((unsigned int *)this + 21) + 16);
                String2.Length = v6;
                String2.MaximumLength = v6;
                String2.Buffer = (PWSTR)((char *)a2 + *((unsigned int *)a2 + 21) + 16);
                v8 = RtlCompareUnicodeString(&String1, &String2, 1u);
                v5 = v8;
                if ( !v8 )
                {
LABEL_28:
                  v5 = *((unsigned __int16 *)this + 53) - (unsigned __int64)*((unsigned __int16 *)a2 + 53);
                  if ( !v5 )
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
                      v5 = v11;
                      if ( !v11 )
                      {
                        v12 = RtlCompareUnicodeString(
                                (PCUNICODE_STRING)&v18.PackedCredentials.ByteArrayLength,
                                (PCUNICODE_STRING)&v21.PackedCredentials.ByteArrayLength,
                                1u);
                        v5 = v12;
                        if ( !v12 )
                        {
                          v5 = v19 - (unsigned __int64)v22;
                          if ( v19 == (unsigned __int64)v22 )
                          {
                            for ( i = 0; i < v19; ++i )
                            {
                              v5 = *(unsigned __int8 *)(i + v20) - (unsigned __int64)*(unsigned __int8 *)(i + v23);
                              if ( v5 )
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
    v5 = -1;
    v17 = -1;
  }
  if ( v5 > 0 )
    result = 1;
  if ( !v5 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180043e00  push    rbx
0x180043e02  push    rsi
0x180043e03  push    rdi
0x180043e04  push    r14
0x180043e06  push    r15
0x180043e08  sub     rsp, 0D0h
0x180043e0f  mov     r14, rdx
0x180043e12  mov     rsi, rcx
0x180043e15  mov     rax, 444552434F545357h
0x180043e1f  cmp     [rcx], rax
0x180043e22  jnz     loc_180043FF1
0x180043e28  cmp     [rdx], rax
0x180043e2b  jnz     loc_180043FF1
0x180043e31  mov     edx, [rcx+40h]
0x180043e34  mov     eax, [r14+40h]
0x180043e38  sub     rdx, rax
0x180043e3b  jnz     loc_180043FE6
0x180043e41  mov     edx, [rcx+3Ch]
0x180043e44  mov     eax, [r14+3Ch]
0x180043e48  sub     rdx, rax
0x180043e4b  jnz     loc_180043FE6
0x180043e51  mov     edx, [rcx+20h]
0x180043e54  mov     eax, [r14+20h]
0x180043e58  sub     rdx, rax
0x180043e5b  jnz     loc_180043FE6
0x180043e61  mov     edx, [rcx+48h]
0x180043e64  mov     eax, [r14+48h]
0x180043e68  sub     rdx, rax
0x180043e6b  jnz     loc_180043FE6
0x180043e71  mov     edx, [rcx+44h]
0x180043e74  mov     eax, [r14+44h]
0x180043e78  sub     rdx, rax
0x180043e7b  jnz     loc_180043FE6
0x180043e81  movzx   r8d, word ptr [r14+58h]
0x180043e86  movzx   eax, word ptr [rcx+58h]
0x180043e8a  mov     edx, eax
0x180043e8c  sub     rdx, r8
0x180043e8f  jnz     loc_180043FE6
0x180043e95  xor     ebx, ebx
0x180043e97  lea     edi, [rdx+1]
0x180043e9a  test    ax, ax
0x180043e9d  jz      short loc_180043F02
0x180043e9f  xorps   xmm0, xmm0
0x180043ea2  movups  xmmword ptr [rsp+0F8h+String1.Length], xmm0
0x180043ea7  xorps   xmm1, xmm1
0x180043eaa  movups  xmmword ptr [rsp+0F8h+String2.Length], xmm1
0x180043eaf  mov     [rsp+0F8h+String1.Length], ax
0x180043eb4  mov     [rsp+0F8h+String1.MaximumLength], ax
0x180043eb9  mov     ecx, [rcx+54h]
0x180043ebc  add     rcx, 10h
0x180043ec0  add     rcx, rsi
0x180043ec3  mov     [rsp+0F8h+String1.Buffer], rcx
0x180043ec8  mov     [rsp+0F8h+String2.Length], r8w
0x180043ece  mov     [rsp+0F8h+String2.MaximumLength], r8w
0x180043ed4  mov     ecx, [r14+54h]
0x180043ed8  add     rcx, 10h
0x180043edc  add     rcx, r14
0x180043edf  mov     [rsp+0F8h+String2.Buffer], rcx
0x180043ee4  mov     r8b, dil; CaseInsensitive
0x180043ee7  lea     rdx, [rsp+0F8h+String2]; String2
0x180043eec  lea     rcx, [rsp+0F8h+String1]; String1
0x180043ef1  call    cs:__imp_RtlCompareUnicodeString
0x180043ef7  movsxd  rdx, eax
0x180043efa  test    eax, eax
0x180043efc  jnz     loc_180043FEB
0x180043f02  lea     r15, [rsi+68h]
0x180043f06  movzx   edx, word ptr [r15+2]
0x180043f0b  movzx   eax, word ptr [r14+6Ah]
0x180043f10  sub     rdx, rax; Val
0x180043f13  jnz     loc_180043FEB
0x180043f19  cmp     [rsi+80h], bx
0x180043f20  jz      loc_180043FEB
0x180043f26  lea     esi, [rdx+40h]
0x180043f29  mov     r8d, esi; Size
0x180043f2c  lea     rcx, [rsp+0F8h+var_A8]; void *
0x180043f31  call    memset_0
0x180043f36  mov     r8d, esi; Size
0x180043f39  xor     edx, edx; Val
0x180043f3b  lea     rcx, [rsp+0F8h+var_68]; void *
0x180043f43  call    memset_0
0x180043f48  lea     rdx, [rsp+0F8h+var_A8]; struct _SECPKG_SUPPLIED_CREDENTIAL *
0x180043f4d  mov     rcx, r15; this
0x180043f50  call    ?WSTUnpackSuppliedCreds@basessp@@YAXPEAU_SECPKG_SUPPLIED_CREDENTIAL@@PEAU_WST_CONTEXT_SUPPLIED_CREDS@1@@Z; basessp::WSTUnpackSuppliedCreds(_SECPKG_SUPPLIED_CREDENTIAL *,basessp::_WST_CONTEXT_SUPPLIED_CREDS *)
0x180043f55  lea     rdx, [rsp+0F8h+var_68]; struct _SECPKG_SUPPLIED_CREDENTIAL *
0x180043f5d  lea     rcx, [r14+68h]; this
0x180043f61  call    ?WSTUnpackSuppliedCreds@basessp@@YAXPEAU_SECPKG_SUPPLIED_CREDENTIAL@@PEAU_WST_CONTEXT_SUPPLIED_CREDS@1@@Z; basessp::WSTUnpackSuppliedCreds(_SECPKG_SUPPLIED_CREDENTIAL *,basessp::_WST_CONTEXT_SUPPLIED_CREDS *)
0x180043f66  mov     r8b, dil; CaseInsensitive
0x180043f69  lea     rdx, [rsp+0F8h+var_68.UserName.ShortArrayCount]; String2
0x180043f71  lea     rcx, [rsp+0F8h+var_A8.UserName.ShortArrayCount]; String1
0x180043f76  call    cs:__imp_RtlCompareUnicodeString
0x180043f7c  movsxd  rdx, eax
0x180043f7f  test    eax, eax
0x180043f81  jnz     short loc_180043FEB
0x180043f83  mov     r8b, dil; CaseInsensitive
0x180043f86  lea     rdx, [rsp+0F8h+var_68.PackedCredentials.ByteArrayLength]; String2
0x180043f8e  lea     rcx, [rsp+0F8h+var_A8.PackedCredentials.ByteArrayLength]; String1
0x180043f93  call    cs:__imp_RtlCompareUnicodeString
0x180043f99  movsxd  rdx, eax
0x180043f9c  test    eax, eax
0x180043f9e  jnz     short loc_180043FEB
0x180043fa0  movzx   eax, [rsp+0F8h+var_40]
0x180043fa8  movzx   edx, [rsp+0F8h+var_80]
0x180043fad  sub     rdx, rax
0x180043fb0  jnz     short loc_180043FEB
0x180043fb2  mov     r8d, ebx
0x180043fb5  mov     r9, [rsp+0F8h+var_78]
0x180043fbd  mov     r10, [rsp+0F8h+var_38]
0x180043fc5  movzx   eax, [rsp+0F8h+var_80]
0x180043fca  cmp     r8d, eax
0x180043fcd  jnb     short loc_180043FEB
0x180043fcf  mov     eax, r8d
0x180043fd2  movzx   ecx, byte ptr [rax+r10]
0x180043fd7  movzx   edx, byte ptr [rax+r9]
0x180043fdc  sub     rdx, rcx
0x180043fdf  jnz     short loc_180043FEB
0x180043fe1  add     r8d, edi
0x180043fe4  jmp     short loc_180043FC5
0x180043fe6  xor     ebx, ebx
0x180043fe8  lea     edi, [rbx+1]
0x180043feb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043fef  jmp     short loc_180044016
0x180043ff1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043ff5  mov     rdx, rax
0x180043ff8  mov     [rsp+0F8h+var_B8], rax
0x180043ffd  xor     ebx, ebx
0x180043fff  lea     edi, [rax+2]
0x180044002  jmp     short loc_180044016
0x180044004  mov     edx, 1
0x180044009  mov     [rsp+0F8h+var_B8], rdx
0x18004400e  xor     ebx, ebx
0x180044010  mov     edi, edx
0x180044012  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044016  test    rdx, rdx
0x180044019  cmovg   eax, edi
0x18004401c  jnz     short loc_180044020
0x18004401e  mov     eax, ebx
0x180044020  add     rsp, 0D0h
0x180044027  pop     r15
0x180044029  pop     r14
0x18004402b  pop     rdi
0x18004402c  pop     rsi
0x18004402d  pop     rbx
0x18004402e  retn
```
