# CxPlatHashCreate

- ea: `0x140034788`
- end: `0x14003480d`
- name: `CxPlatHashCreate`
- size: `133`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008bb0`
- `0x140028ee0`
- `0x14002d550`
- `0x140038e38`
- `0x140038f64`
- `0x14004a1f8`

## callees

- `0x140034788`
- `0x14003e928`

## import_xrefs

- `cng!BCryptCreateHash` at `0x1400347da`
- `cng!BCryptCreateHash` at `0x1400347da`

## string_xrefs

- `0x1400347f5`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall CxPlatHashCreate(int a1, UCHAR *pbSecret, ULONG cbSecret, BCRYPT_HASH_HANDLE *a4)
{
  int v4; // ecx
  BCRYPT_ALG_HANDLE v6; // rcx
  NTSTATUS Hash; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx

  if ( a1 )
  {
    v4 = a1 - 1;
    if ( v4 )
    {
      if ( v4 != 1 )
        return 3221225659LL;
      v6 = CXPLAT_HMAC_SHA512_ALG_HANDLE;
    }
    else
    {
      v6 = CXPLAT_HMAC_SHA384_ALG_HANDLE;
    }
  }
  else
  {
    v6 = CXPLAT_HMAC_SHA256_ALG_HANDLE;
  }
  Hash = BCryptCreateHash(v6, a4, 0, 0, pbSecret, cbSecret, 0x20u);
  v10 = Hash;
  if ( Hash < 0 && (Microsoft_QuicEnableBits & 4) != 0 )
    McTemplateU0qs_EtwWriteTransfer(v9, v8, (unsigned int)Hash, "BCryptCreateHash");
  return v10;
}

```

## disassembly

```asm
0x140034788  push    rbx
0x14003478a  sub     rsp, 40h
0x14003478e  mov     r10, r9
0x140034791  test    ecx, ecx
0x140034793  jz      short loc_1400347B8
0x140034795  sub     ecx, 1
0x140034798  jz      short loc_1400347AF
0x14003479a  cmp     ecx, 1
0x14003479d  jz      short loc_1400347A6
0x14003479f  mov     eax, 0C00000BBh
0x1400347a4  jmp     short loc_140034806
0x1400347a6  mov     rcx, cs:CXPLAT_HMAC_SHA512_ALG_HANDLE
0x1400347ad  jmp     short loc_1400347BF
0x1400347af  mov     rcx, cs:CXPLAT_HMAC_SHA384_ALG_HANDLE
0x1400347b6  jmp     short loc_1400347BF
0x1400347b8  mov     rcx, cs:CXPLAT_HMAC_SHA256_ALG_HANDLE; hAlgorithm
0x1400347bf  mov     [rsp+48h+dwFlags], 20h ; ' '; dwFlags
0x1400347c7  xor     r9d, r9d; cbHashObject
0x1400347ca  mov     [rsp+48h+cbSecret], r8d; cbSecret
0x1400347cf  xor     r8d, r8d; pbHashObject
0x1400347d2  mov     [rsp+48h+pbSecret], rdx; pbSecret
0x1400347d7  mov     rdx, r10; phHash
0x1400347da  call    cs:__imp_BCryptCreateHash
0x1400347e1  nop     dword ptr [rax+rax+00h]
0x1400347e6  mov     ebx, eax
0x1400347e8  test    eax, eax
0x1400347ea  jns     short loc_140034804
0x1400347ec  test    cs:Microsoft_QuicEnableBits, 4
0x1400347f3  jz      short loc_140034804
0x1400347f5  lea     r9, aBcryptcreateha; "BCryptCreateHash"
0x1400347fc  mov     r8d, eax
0x1400347ff  call    McTemplateU0qs_EtwWriteTransfer
0x140034804  mov     eax, ebx
0x140034806  add     rsp, 40h
0x14003480a  pop     rbx
0x14003480b  retn
```
