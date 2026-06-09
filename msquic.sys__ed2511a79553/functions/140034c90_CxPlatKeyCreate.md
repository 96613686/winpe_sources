# CxPlatKeyCreate

- ea: `0x140034c90`
- end: `0x140034d19`
- name: `CxPlatKeyCreate`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008bb0`
- `0x14002d33c`

## callees

- `0x140034c90`
- `0x14003e928`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x140034ce6`
- `cng!BCryptGenerateSymmetricKey` at `0x140034ce6`

## pseudocode

```c
__int64 __fastcall CxPlatKeyCreate(int a1, UCHAR *pbSecret, BCRYPT_KEY_HANDLE *a3)
{
  int v3; // ecx
  BCRYPT_ALG_HANDLE v5; // rcx
  ULONG cbSecret; // eax
  NTSTATUS SymmetricKey; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx

  if ( !a1 )
  {
    cbSecret = 16;
    goto LABEL_8;
  }
  v3 = a1 - 1;
  if ( !v3 )
  {
    cbSecret = 32;
LABEL_8:
    v5 = CXPLAT_AES_GCM_ALG_HANDLE;
    goto LABEL_9;
  }
  if ( v3 != 1 )
    return 3221225659LL;
  v5 = CXPLAT_CHACHA20_POLY1305_ALG_HANDLE;
  cbSecret = 32;
LABEL_9:
  SymmetricKey = BCryptGenerateSymmetricKey(v5, a3, 0, 0, pbSecret, cbSecret, 0);
  v10 = SymmetricKey;
  if ( SymmetricKey < 0 && (Microsoft_QuicEnableBits & 4) != 0 )
    McTemplateU0qs_EtwWriteTransfer(v9, v8, (unsigned int)SymmetricKey, "BCryptGenerateSymmetricKey");
  return v10;
}

```

## disassembly

```asm
0x140034c90  push    rbx
0x140034c92  sub     rsp, 40h
0x140034c96  mov     r10, r8
0x140034c99  test    ecx, ecx
0x140034c9b  jz      short loc_140034CC3
0x140034c9d  sub     ecx, 1
0x140034ca0  jz      short loc_140034CBC
0x140034ca2  cmp     ecx, 1
0x140034ca5  jz      short loc_140034CAE
0x140034ca7  mov     eax, 0C00000BBh
0x140034cac  jmp     short loc_140034D12
0x140034cae  mov     rcx, cs:CXPLAT_CHACHA20_POLY1305_ALG_HANDLE
0x140034cb5  mov     eax, 20h ; ' '
0x140034cba  jmp     short loc_140034CCF
0x140034cbc  mov     eax, 20h ; ' '
0x140034cc1  jmp     short loc_140034CC8
0x140034cc3  mov     eax, 10h
0x140034cc8  mov     rcx, cs:CXPLAT_AES_GCM_ALG_HANDLE; hAlgorithm
0x140034ccf  and     [rsp+48h+var_18], 0
0x140034cd4  xor     r9d, r9d; cbKeyObject
0x140034cd7  mov     [rsp+48h+cbSecret], eax; cbSecret
0x140034cdb  xor     r8d, r8d; pbKeyObject
0x140034cde  mov     [rsp+48h+pbSecret], rdx; pbSecret
0x140034ce3  mov     rdx, r10; phKey
0x140034ce6  call    cs:__imp_BCryptGenerateSymmetricKey
0x140034ced  nop     dword ptr [rax+rax+00h]
0x140034cf2  mov     ebx, eax
0x140034cf4  test    eax, eax
0x140034cf6  jns     short loc_140034D10
0x140034cf8  test    cs:Microsoft_QuicEnableBits, 4
0x140034cff  jz      short loc_140034D10
0x140034d01  lea     r9, aBcryptgenerate; "BCryptGenerateSymmetricKey"
0x140034d08  mov     r8d, eax
0x140034d0b  call    McTemplateU0qs_EtwWriteTransfer
0x140034d10  mov     eax, ebx
0x140034d12  add     rsp, 40h
0x140034d16  pop     rbx
0x140034d17  retn
```
