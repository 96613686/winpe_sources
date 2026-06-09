# DsrSidInitAscii(uchar *,ulong,ushort * *)

- ea: `0x18002bca8`
- end: `0x18002bda9`
- name: `?DsrSidInitAscii@@YAJPEAEKPEAPEAG@Z`
- size: `257`
- prototype: `signed int __fastcall(unsigned __int8 *pSid, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c064`

## callees

- `0x180009868`
- `0x18002bca8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002bd05`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002bd05`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002bcd9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002bcd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002bcc5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002bcc5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002bcf4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002bcf4`

## pseudocode

```c
signed int __fastcall DsrSidInitAscii(unsigned __int8 *pSid, __int64 a2, unsigned __int16 **a3)
{
  DWORD LengthSid; // eax
  __int64 v6; // rbp
  unsigned __int16 *v7; // rdi
  signed int result; // eax
  PUCHAR SidSubAuthorityCount; // rax
  PUCHAR v10; // rbx
  __int64 i; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  _QWORD v14[9]; // [rsp+20h] [rbp-48h]

  LODWORD(v14[0]) = 553;
  LengthSid = GetLengthSid(pSid);
  v6 = LengthSid;
  v7 = (unsigned __int16 *)GlobalAlloc(0x40u, 8 * LengthSid + 20);
  if ( !v7 )
    return -2147024882;
  SidSubAuthorityCount = GetSidSubAuthorityCount(pSid);
  v10 = SidSubAuthorityCount;
  if ( SidSubAuthorityCount )
  {
    ++*SidSubAuthorityCount;
    for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
    {
      v12 = (unsigned int)(3 * i);
      v7[v12] = 92;
      StringCbPrintfW(&v7[(unsigned int)(v12 + 1)], 6u, L"%02x", pSid[i], v14[0]);
    }
    while ( (unsigned int)i < (unsigned __int64)(v6 + 4) )
    {
      v13 = (unsigned int)(3 * i);
      v7[v13] = 92;
      StringCbPrintfW(&v7[(unsigned int)(v13 + 1)], 6u, L"%02x", *((unsigned __int8 *)v14 + (unsigned int)(i - v6)));
      LODWORD(i) = i + 1;
    }
    --*v10;
    result = 0;
    *a3 = v7;
  }
  else
  {
    GlobalFree(v7);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002bca8  push    rbx
0x18002bcaa  push    rbp
0x18002bcab  push    rsi
0x18002bcac  push    rdi
0x18002bcad  push    r13
0x18002bcaf  push    r14
0x18002bcb1  push    r15
0x18002bcb3  sub     rsp, 30h
0x18002bcb7  mov     r15, r8
0x18002bcba  mov     [rsp+68h+var_48], 229h
0x18002bcc2  mov     r14, rcx
0x18002bcc5  call    cs:__imp_GetLengthSid
0x18002bccb  mov     ebp, eax
0x18002bccd  mov     ecx, 40h ; '@'; uFlags
0x18002bcd2  lea     edx, ds:14h[rbp*8]; dwBytes
0x18002bcd9  call    cs:__imp_GlobalAlloc
0x18002bcdf  mov     rdi, rax
0x18002bce2  test    rax, rax
0x18002bce5  jnz     short loc_18002BCF1
0x18002bce7  mov     eax, 8007000Eh
0x18002bcec  jmp     loc_18002BD9A
0x18002bcf1  mov     rcx, r14; pSid
0x18002bcf4  call    cs:__imp_GetSidSubAuthorityCount
0x18002bcfa  mov     rbx, rax
0x18002bcfd  test    rax, rax
0x18002bd00  jnz     short loc_18002BD23
0x18002bd02  mov     rcx, rdi; hMem
0x18002bd05  call    cs:__imp_GlobalFree
0x18002bd0b  call    cs:__imp_GetLastError
0x18002bd11  test    eax, eax
0x18002bd13  jle     loc_18002BD9A
0x18002bd19  movzx   eax, ax
0x18002bd1c  or      eax, 80070000h
0x18002bd21  jmp     short loc_18002BD9A
0x18002bd23  inc     byte ptr [rax]
0x18002bd25  xor     esi, esi
0x18002bd27  lea     r13d, [rsi+5Ch]
0x18002bd2b  test    ebp, ebp
0x18002bd2d  jz      short loc_18002BD5A
0x18002bd2f  lea     ecx, [rsi+rsi*2]
0x18002bd32  mov     edx, 6; cbDest
0x18002bd37  mov     [rdi+rcx*2], r13w
0x18002bd3c  lea     eax, [rcx+1]
0x18002bd3f  movzx   r9d, byte ptr [rsi+r14]
0x18002bd44  lea     rcx, [rdi+rax*2]; pszDest
0x18002bd48  lea     r8, a02x; "%02x"
0x18002bd4f  call    StringCbPrintfW
0x18002bd54  inc     esi
0x18002bd56  cmp     esi, ebp
0x18002bd58  jb      short loc_18002BD2F
0x18002bd5a  lea     r14, [rbp+4]
0x18002bd5e  jmp     short loc_18002BD8C
0x18002bd60  mov     eax, esi
0x18002bd62  lea     ecx, [rsi+rsi*2]
0x18002bd65  sub     eax, ebp
0x18002bd67  mov     [rdi+rcx*2], r13w
0x18002bd6c  lea     r8, a02x; "%02x"
0x18002bd73  mov     edx, 6; cbDest
0x18002bd78  movzx   r9d, byte ptr [rsp+rax+68h+var_48]
0x18002bd7e  lea     eax, [rcx+1]
0x18002bd81  lea     rcx, [rdi+rax*2]; pszDest
0x18002bd85  call    StringCbPrintfW
0x18002bd8a  inc     esi
0x18002bd8c  mov     eax, esi
0x18002bd8e  cmp     rax, r14
0x18002bd91  jb      short loc_18002BD60
0x18002bd93  dec     byte ptr [rbx]
0x18002bd95  xor     eax, eax
0x18002bd97  mov     [r15], rdi
0x18002bd9a  add     rsp, 30h
0x18002bd9e  pop     r15
0x18002bda0  pop     r14
0x18002bda2  pop     r13
0x18002bda4  pop     rdi
0x18002bda5  pop     rsi
0x18002bda6  pop     rbp
0x18002bda7  pop     rbx
0x18002bda8  retn
```
