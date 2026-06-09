# CompareAuthIdentity(void *,void *)

- ea: `0x18009c7b0`
- end: `0x18009c8b5`
- name: `?CompareAuthIdentity@@YAHPEAX0@Z`
- size: `261`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18009c7b0`
- `0x18009c8c0`
- `0x1800a5380`
- `0x1800b6760`
- `0x1800b76b0`

## import_xrefs

- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18009c7de`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18009c818`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18009c7de`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18009c818`
- `SspiCli!SspiCompareAuthIdentities` at `0x18009c858`
- `SspiCli!SspiCompareAuthIdentities` at `0x18009c858`

## pseudocode

```c
_BOOL8 __fastcall CompareAuthIdentity(void *a1, void *a2)
{
  void *v2; // rbx
  void *v3; // rbp
  void *v4; // rsi
  void *v5; // rdi
  void *v6; // rax
  SECURITY_STATUS v7; // ebx
  void *v8; // rax
  unsigned __int8 SameSuppliedUser; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int8 SameSuppliedIdentity; // [rsp+48h] [rbp+10h] BYREF

  SameSuppliedUser = 0;
  v2 = a2;
  SameSuppliedIdentity = 0;
  v3 = a1;
  if ( a1 != a2 )
  {
    v4 = 0;
    v5 = 0;
    if ( a1 && SspiIsAuthIdentityEncrypted(a1) )
    {
      v6 = DuplicateAuthIdentity(v3);
      v4 = v6;
      if ( !v6 )
        return 0;
      if ( (unsigned int)DecryptAuthIdentity(v6) )
      {
        v7 = 14;
LABEL_16:
        WipeOutAuthIdentity(v4);
        FreeAuthIdentity(v4);
LABEL_17:
        if ( v5 )
        {
          WipeOutAuthIdentity(v5);
          FreeAuthIdentity(v5);
        }
        if ( !v7 && SameSuppliedUser )
          return SameSuppliedIdentity != 0;
        return 0;
      }
      v3 = v4;
    }
    if ( v2 && SspiIsAuthIdentityEncrypted(v2) )
    {
      v8 = DuplicateAuthIdentity(v2);
      v5 = v8;
      if ( !v8 || (unsigned int)DecryptAuthIdentity(v8) )
      {
        v7 = 14;
        goto LABEL_15;
      }
      v2 = v5;
    }
    v7 = SspiCompareAuthIdentities(v3, v2, &SameSuppliedUser, &SameSuppliedIdentity);
LABEL_15:
    if ( !v4 )
      goto LABEL_17;
    goto LABEL_16;
  }
  return 1;
}

```

## disassembly

```asm
0x18009c7b0  mov     [rsp+arg_10], rbx
0x18009c7b5  push    rbp
0x18009c7b6  push    rsi
0x18009c7b7  push    rdi
0x18009c7b8  sub     rsp, 20h
0x18009c7bc  mov     [rsp+38h+SameSuppliedUser], 0
0x18009c7c1  mov     rbx, rdx
0x18009c7c4  mov     [rsp+38h+SameSuppliedIdentity], 0
0x18009c7c9  mov     rbp, rcx
0x18009c7cc  cmp     rcx, rdx
0x18009c7cf  jz      loc_18009C8A3
0x18009c7d5  xor     esi, esi
0x18009c7d7  xor     edi, edi
0x18009c7d9  test    rcx, rcx
0x18009c7dc  jz      short loc_18009C810
0x18009c7de  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x18009c7e4  test    al, al
0x18009c7e6  jz      short loc_18009C810
0x18009c7e8  mov     rcx, rbp; void *
0x18009c7eb  call    ?DuplicateAuthIdentity@@YAPEAXPEAX@Z; DuplicateAuthIdentity(void *)
0x18009c7f0  mov     rsi, rax
0x18009c7f3  test    rax, rax
0x18009c7f6  jz      loc_18009C89F
0x18009c7fc  mov     rcx, rax; void *
0x18009c7ff  call    ?DecryptAuthIdentity@@YAJPEAX@Z; DecryptAuthIdentity(void *)
0x18009c804  test    eax, eax
0x18009c806  jz      short loc_18009C80D
0x18009c808  lea     ebx, [rdi+0Eh]
0x18009c80b  jmp     short loc_18009C865
0x18009c80d  mov     rbp, rsi
0x18009c810  test    rbx, rbx
0x18009c813  jz      short loc_18009C848
0x18009c815  mov     rcx, rbx; EncryptedAuthData
0x18009c818  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x18009c81e  test    al, al
0x18009c820  jz      short loc_18009C848
0x18009c822  mov     rcx, rbx; void *
0x18009c825  call    ?DuplicateAuthIdentity@@YAPEAXPEAX@Z; DuplicateAuthIdentity(void *)
0x18009c82a  mov     rdi, rax
0x18009c82d  test    rax, rax
0x18009c830  jnz     short loc_18009C839
0x18009c832  mov     ebx, 0Eh
0x18009c837  jmp     short loc_18009C860
0x18009c839  mov     rcx, rdi; void *
0x18009c83c  call    ?DecryptAuthIdentity@@YAJPEAX@Z; DecryptAuthIdentity(void *)
0x18009c841  test    eax, eax
0x18009c843  jnz     short loc_18009C832
0x18009c845  mov     rbx, rdi
0x18009c848  lea     r9, [rsp+38h+SameSuppliedIdentity]; SameSuppliedIdentity
0x18009c84d  mov     rdx, rbx; AuthIdentity2
0x18009c850  lea     r8, [rsp+38h+SameSuppliedUser]; SameSuppliedUser
0x18009c855  mov     rcx, rbp; AuthIdentity1
0x18009c858  call    cs:__imp_SspiCompareAuthIdentities
0x18009c85e  mov     ebx, eax
0x18009c860  test    rsi, rsi
0x18009c863  jz      short loc_18009C875
0x18009c865  mov     rcx, rsi; void *
0x18009c868  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x18009c86d  mov     rcx, rsi; void *
0x18009c870  call    ?FreeAuthIdentity@@YAXPEAX@Z; FreeAuthIdentity(void *)
0x18009c875  test    rdi, rdi
0x18009c878  jz      short loc_18009C88A
0x18009c87a  mov     rcx, rdi; void *
0x18009c87d  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x18009c882  mov     rcx, rdi; void *
0x18009c885  call    ?FreeAuthIdentity@@YAXPEAX@Z; FreeAuthIdentity(void *)
0x18009c88a  test    ebx, ebx
0x18009c88c  jnz     short loc_18009C89F
0x18009c88e  cmp     [rsp+38h+SameSuppliedUser], bl
0x18009c892  jz      short loc_18009C89F
0x18009c894  xor     eax, eax
0x18009c896  cmp     [rsp+38h+SameSuppliedIdentity], al
0x18009c89a  setnz   al
0x18009c89d  jmp     short loc_18009C8A8
0x18009c89f  xor     eax, eax
0x18009c8a1  jmp     short loc_18009C8A8
0x18009c8a3  mov     eax, 1
0x18009c8a8  mov     rbx, [rsp+38h+arg_10]
0x18009c8ad  add     rsp, 20h
0x18009c8b1  pop     rdi
0x18009c8b2  pop     rsi
0x18009c8b3  pop     rbp
0x18009c8b4  retn
```
