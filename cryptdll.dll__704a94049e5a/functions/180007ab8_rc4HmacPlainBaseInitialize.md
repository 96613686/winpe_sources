# rc4HmacPlainBaseInitialize

- ea: `0x180007ab8`
- end: `0x180007bab`
- name: `rc4HmacPlainBaseInitialize`
- size: `243`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007e80`
- `0x180007ea0`

## callees

- `0x1800054be`
- `0x180006a9c`
- `0x18000750c`
- `0x180007ab8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ade`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007ade`

## pseudocode

```c
__int64 __fastcall rc4HmacPlainBaseInitialize(void *Src, size_t Size, int a3, char a4, BCRYPT_KEY_HANDLE **a5)
{
  unsigned int v5; // ebp
  BCRYPT_KEY_HANDLE *v8; // rax
  BCRYPT_KEY_HANDLE *v9; // rdi
  UCHAR *v11; // r8
  int v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = a3;
  v5 = Size;
  v8 = (BCRYPT_KEY_HANDLE *)LocalAlloc(0, 0x18u);
  v9 = v8;
  if ( !v8 )
    return 3221225626LL;
  v8[2] = 0;
  v11 = (UCHAR *)&v12;
  if ( a4 )
    v11 = (UCHAR *)"fortybits";
  md5Hmac_0(
    Src,
    v5,
    v11,
    a4 != 0 ? 10 : 4,
    (UCHAR *)((unsigned __int64)&v12 & -(__int64)(a4 != 0)),
    a4 != 0 ? 4 : 0,
    v8);
  memset_0((char *)v9 + (-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFF7uLL) + 16, 171, a4 != 0 ? 9 : 0);
  CngRsa32Compat_rc4_key(v9 + 2, 0x10u, (PUCHAR)v9);
  *a5 = v9;
  return 0;
}

```

## disassembly

```asm
0x180007ab8  mov     [rsp+arg_0], rbx
0x180007abd  mov     [rsp+arg_8], rbp
0x180007ac2  mov     [rsp+arg_10], r8d
0x180007ac7  push    rsi
0x180007ac8  push    rdi
0x180007ac9  push    r14
0x180007acb  sub     rsp, 40h
0x180007acf  mov     ebp, edx
0x180007ad1  mov     r14, rcx
0x180007ad4  mov     edx, 18h; uBytes
0x180007ad9  xor     ecx, ecx; uFlags
0x180007adb  mov     sil, r9b
0x180007ade  call    cs:__imp_LocalAlloc
0x180007ae4  mov     rdi, rax
0x180007ae7  test    rax, rax
0x180007aea  jnz     short loc_180007AF6
0x180007aec  mov     eax, 0C000009Ah
0x180007af1  jmp     loc_180007B98
0x180007af6  mov     qword ptr [rax+10h], 0
0x180007afe  lea     r8, [rsp+58h+arg_10]
0x180007b03  mov     al, sil
0x180007b06  mov     [rsp+58h+var_28], rdi; __int64
0x180007b0b  neg     al
0x180007b0d  mov     al, sil
0x180007b10  sbb     edx, edx
0x180007b12  and     edx, 4
0x180007b15  neg     al
0x180007b17  mov     [rsp+58h+var_30], edx; int
0x180007b1b  lea     rax, [rsp+58h+arg_10]
0x180007b20  mov     edx, ebp; Size
0x180007b22  sbb     rcx, rcx
0x180007b25  and     rcx, rax
0x180007b28  mov     al, sil
0x180007b2b  neg     al
0x180007b2d  mov     [rsp+58h+var_38], rcx; __int64
0x180007b32  lea     rax, aFortybits; "fortybits"
0x180007b39  mov     rcx, r14; Src
0x180007b3c  sbb     r9d, r9d
0x180007b3f  and     r9d, 6
0x180007b43  add     r9d, 4
0x180007b47  test    sil, sil
0x180007b4a  cmovnz  r8, rax
0x180007b4e  call    md5Hmac_0
0x180007b53  mov     al, sil
0x180007b56  mov     edx, 0ABh; Val
0x180007b5b  neg     al
0x180007b5d  sbb     r8, r8
0x180007b60  and     r8d, 9; Size
0x180007b64  neg     sil
0x180007b67  sbb     rcx, rcx
0x180007b6a  and     rcx, 0FFFFFFFFFFFFFFF7h
0x180007b6e  add     rcx, 10h
0x180007b72  add     rcx, rdi; void *
0x180007b75  call    memset_0
0x180007b7a  mov     r8, rdi; pbSecret
0x180007b7d  lea     rcx, [rdi+10h]; phKey
0x180007b81  mov     edx, 10h; cbSecret
0x180007b86  call    CngRsa32Compat_rc4_key
0x180007b8b  mov     rax, [rsp+58h+arg_20]
0x180007b93  mov     [rax], rdi
0x180007b96  xor     eax, eax
0x180007b98  mov     rbx, [rsp+58h+arg_0]
0x180007b9d  mov     rbp, [rsp+58h+arg_8]
0x180007ba2  add     rsp, 40h
0x180007ba6  pop     r14
0x180007ba8  pop     rdi
0x180007ba9  pop     rsi
0x180007baa  retn
```
