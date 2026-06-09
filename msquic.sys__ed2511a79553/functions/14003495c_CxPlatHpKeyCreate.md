# CxPlatHpKeyCreate

- ea: `0x14003495c`
- end: `0x140034ad2`
- name: `CxPlatHpKeyCreate`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008bb0`

## callees

- `0x14003495c`
- `0x14003ce00`
- `0x14003e928`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140034a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034a69`
- `ntoskrnl!ExAllocatePool2` at `0x1400349d6`
- `ntoskrnl!ExAllocatePool2` at `0x1400349d6`
- `cng!BCryptGenerateSymmetricKey` at `0x140034a29`
- `cng!BCryptGenerateSymmetricKey` at `0x140034a29`

## pseudocode

```c
__int64 __fastcall CxPlatHpKeyCreate(int a1, UCHAR *a2, __int64 *a3)
{
  BCRYPT_ALG_HANDLE v7; // r14
  __int64 v8; // rsi
  ULONG cbSecret; // ebx
  __int64 Pool2; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rcx
  NTSTATUS SymmetricKey; // esi
  const char *v17; // r9

  if ( !a1 )
  {
    cbSecret = 16;
    goto LABEL_8;
  }
  if ( a1 == 1 )
  {
    cbSecret = 32;
LABEL_8:
    v7 = CXPLAT_AES_ECB_ALG_HANDLE;
    v8 = 16;
    goto LABEL_9;
  }
  if ( a1 != 2 )
    return 3221225659LL;
  v7 = CXPLAT_CHACHA20_POLY1305_ALG_HANDLE;
  v8 = 120;
  cbSecret = 32;
LABEL_9:
  Pool2 = ExAllocatePool2(66, v8, 875717457);
  v13 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 8) = a1;
    SymmetricKey = BCryptGenerateSymmetricKey(v7, (BCRYPT_KEY_HANDLE *)Pool2, 0, 0, a2, cbSecret, 0);
    if ( SymmetricKey >= 0 )
    {
      if ( a1 == 2 )
      {
        memset((void *)(v13 + 16), 0, 0x58u);
        *(_QWORD *)(v13 + 40) = 0;
        *(_DWORD *)(v13 + 48) = 0;
        *(_QWORD *)(v13 + 56) = v13 + 104;
        *(_DWORD *)(v13 + 16) = 88;
        *(_DWORD *)(v13 + 20) = 1;
        *(_DWORD *)(v13 + 64) = 16;
      }
      *a3 = v13;
    }
    else
    {
      if ( (Microsoft_QuicEnableBits & 4) != 0 )
      {
        v17 = "BCryptGenerateSymmetricKey (ChaCha)";
        if ( a1 != 2 )
          v17 = "BCryptGenerateSymmetricKey (ECB)";
        McTemplateU0qs_EtwWriteTransfer(v15, v14, (unsigned int)SymmetricKey, v17);
      }
      ExFreePoolWithTag((PVOID)v13, 0x34326351u);
    }
    return (unsigned int)SymmetricKey;
  }
  else
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v12, v11, "CXPLAT_HP_KEY", v8);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x14003495c  mov     [rsp+arg_0], rbx
0x140034961  mov     [rsp+arg_8], rbp
0x140034966  mov     [rsp+arg_10], rsi
0x14003496b  push    rdi
0x14003496c  push    r12
0x14003496e  push    r13
0x140034970  push    r14
0x140034972  push    r15
0x140034974  sub     rsp, 40h
0x140034978  mov     r15, r8
0x14003497b  mov     r12, rdx
0x14003497e  mov     ebp, ecx
0x140034980  mov     r9d, ecx
0x140034983  mov     r13d, 10h
0x140034989  test    ecx, ecx
0x14003498b  jz      short loc_1400349BB
0x14003498d  sub     r9d, 1
0x140034991  jz      short loc_1400349B4
0x140034993  cmp     r9d, 1
0x140034997  jz      short loc_1400349A3
0x140034999  mov     eax, 0C00000BBh
0x14003499e  jmp     loc_140034AB3
0x1400349a3  mov     r14, cs:CXPLAT_CHACHA20_POLY1305_ALG_HANDLE
0x1400349aa  mov     esi, 78h ; 'x'
0x1400349af  lea     ebx, [rsi-58h]
0x1400349b2  jmp     short loc_1400349C8
0x1400349b4  mov     ebx, 20h ; ' '
0x1400349b9  jmp     short loc_1400349BE
0x1400349bb  mov     ebx, r13d
0x1400349be  mov     r14, cs:CXPLAT_AES_ECB_ALG_HANDLE
0x1400349c5  mov     rsi, r13
0x1400349c8  mov     r8d, 34326351h
0x1400349ce  mov     rdx, rsi
0x1400349d1  mov     ecx, 42h ; 'B'
0x1400349d6  call    cs:__imp_ExAllocatePool2
0x1400349dd  nop     dword ptr [rax+rax+00h]
0x1400349e2  mov     rdi, rax
0x1400349e5  test    rax, rax
0x1400349e8  jnz     short loc_140034A0C
0x1400349ea  test    cs:Microsoft_QuicEnableBits, 2
0x1400349f1  jz      short loc_140034A02
0x1400349f3  mov     r9, rsi
0x1400349f6  lea     r8, aCxplatHpKey; "CXPLAT_HP_KEY"
0x1400349fd  call    McTemplateU0sx_EtwWriteTransfer
0x140034a02  mov     eax, 0C0000017h
0x140034a07  jmp     loc_140034AB3
0x140034a0c  and     [rsp+68h+var_38], 0
0x140034a11  xor     r9d, r9d; cbKeyObject
0x140034a14  mov     [rsp+68h+cbSecret], ebx; cbSecret
0x140034a18  xor     r8d, r8d; pbKeyObject
0x140034a1b  mov     rdx, rdi; phKey
0x140034a1e  mov     [rsp+68h+pbSecret], r12; pbSecret
0x140034a23  mov     rcx, r14; hAlgorithm
0x140034a26  mov     [rax+8], ebp
0x140034a29  call    cs:__imp_BCryptGenerateSymmetricKey
0x140034a30  nop     dword ptr [rax+rax+00h]
0x140034a35  mov     esi, eax
0x140034a37  test    eax, eax
0x140034a39  jns     short loc_140034A77
0x140034a3b  test    cs:Microsoft_QuicEnableBits, 4
0x140034a42  jz      short loc_140034A61
0x140034a44  cmp     ebp, 2
0x140034a47  lea     rax, aBcryptgenerate_1; "BCryptGenerateSymmetricKey (ECB)"
0x140034a4e  lea     r9, aBcryptgenerate_2; "BCryptGenerateSymmetricKey (ChaCha)"
0x140034a55  mov     r8d, esi
0x140034a58  cmovnz  r9, rax
0x140034a5c  call    McTemplateU0qs_EtwWriteTransfer
0x140034a61  mov     edx, 34326351h; Tag
0x140034a66  mov     rcx, rdi; P
0x140034a69  call    cs:__imp_ExFreePoolWithTag
0x140034a70  nop     dword ptr [rax+rax+00h]
0x140034a75  jmp     short loc_140034AB1
0x140034a77  cmp     ebp, 2
0x140034a7a  jnz     short loc_140034AAE
0x140034a7c  mov     ebp, 58h ; 'X'
0x140034a81  lea     rcx, [rdi+10h]; void *
0x140034a85  mov     r8d, ebp; Size
0x140034a88  xor     edx, edx; Val
0x140034a8a  call    memset
0x140034a8f  and     qword ptr [rdi+28h], 0
0x140034a94  lea     rax, [rdi+68h]
0x140034a98  and     dword ptr [rdi+30h], 0
0x140034a9c  mov     [rdi+38h], rax
0x140034aa0  mov     [rdi+10h], ebp
0x140034aa3  mov     dword ptr [rdi+14h], 1
0x140034aaa  mov     [rdi+40h], r13d
0x140034aae  mov     [r15], rdi
0x140034ab1  mov     eax, esi
0x140034ab3  lea     r11, [rsp+68h+var_28]
0x140034ab8  mov     rbx, [r11+30h]
0x140034abc  mov     rbp, [r11+38h]
0x140034ac0  mov     rsi, [r11+40h]
0x140034ac4  mov     rsp, r11
0x140034ac7  pop     r15
0x140034ac9  pop     r14
0x140034acb  pop     r13
0x140034acd  pop     r12
0x140034acf  pop     rdi
0x140034ad0  retn
```
