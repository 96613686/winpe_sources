# FormatEtcLoadFromStream(IStream *,tagFORMATETC *)

- ea: `0x180019bb8`
- end: `0x180019ce9`
- name: `?FormatEtcLoadFromStream@@YAJPEAUIStream@@PEAUtagFORMATETC@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IStream *pstm, struct tagFORMATETC *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a010`

## callees

- `0x180002240`
- `0x180019bb8`

## import_xrefs

- `SHLWAPI!__imp_IStream_Read` at `0x180019c10`
- `SHLWAPI!__imp_IStream_Read` at `0x180019c5c`
- `SHLWAPI!__imp_IStream_Read` at `0x180019c8b`
- `SHLWAPI!__imp_IStream_Read` at `0x180019c10`
- `SHLWAPI!__imp_IStream_Read` at `0x180019c5c`
- `SHLWAPI!__imp_IStream_Read` at `0x180019c8b`
- `USER32!RegisterClipboardFormatW` at `0x180019caf`
- `USER32!RegisterClipboardFormatW` at `0x180019caf`

## pseudocode

```c
__int64 __fastcall FormatEtcLoadFromStream(struct IStream *pstm, struct tagFORMATETC *a2)
{
  HRESULT v4; // ecx
  CLIPFORMAT v5; // ax
  ULONG cb; // [rsp+20h] [rbp-E0h] BYREF
  __int128 pv; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v9; // [rsp+38h] [rbp-C8h]
  WCHAR szFormat[264]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = -2147024809;
  if ( pstm )
  {
    v9 = 0;
    pv = 0;
    v4 = IStream_Read(pstm, &pv, 0x14u);
    if ( v4 >= 0 )
    {
      v4 = -2147024883;
      a2->cfFormat = pv;
      *(_QWORD *)&a2->dwAspect = *((_QWORD *)&pv + 1);
      a2->tymed = v9;
      a2->ptd = 0;
      if ( !DWORD1(pv) )
      {
        cb = 0;
        v4 = IStream_Read(pstm, &cb, 4u);
        if ( v4 >= 0 )
        {
          v4 = -2147024883;
          if ( cb - 1 <= 0x207 && (cb & 1) == 0 )
          {
            v4 = IStream_Read(pstm, szFormat, cb);
            if ( v4 >= 0 )
            {
              v4 = -2147024883;
              if ( !szFormat[((unsigned __int64)cb >> 1) - 1] )
              {
                v5 = RegisterClipboardFormatW(szFormat);
                a2->cfFormat = v5;
                return v5 == 0 ? 0x8007000E : 0;
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019bb8  mov     [rsp-8+arg_10], rbx
0x180019bbd  push    rbp
0x180019bbe  push    rsi
0x180019bbf  push    rdi
0x180019bc0  lea     rbp, [rsp-160h]
0x180019bc8  sub     rsp, 260h
0x180019bcf  mov     rax, cs:__security_cookie
0x180019bd6  xor     rax, rsp
0x180019bd9  mov     [rbp+170h+var_20], rax
0x180019be0  mov     rdi, rcx
0x180019be3  xor     esi, esi
0x180019be5  mov     rbx, rdx
0x180019be8  mov     ecx, 80070057h
0x180019bed  test    rdi, rdi
0x180019bf0  jz      loc_180019CC5
0x180019bf6  xorps   xmm0, xmm0
0x180019bf9  lea     r8d, [rsi+14h]; cb
0x180019bfd  xor     eax, eax
0x180019bff  lea     rdx, [rsp+270h+pv]; pv
0x180019c04  mov     rcx, rdi; pstm
0x180019c07  mov     [rsp+270h+var_238], eax
0x180019c0b  movups  [rsp+270h+pv], xmm0
0x180019c10  call    cs:__imp_IStream_Read
0x180019c16  mov     ecx, eax
0x180019c18  test    eax, eax
0x180019c1a  js      loc_180019CC5
0x180019c20  mov     ecx, 8007000Dh
0x180019c25  movzx   eax, word ptr [rsp+270h+pv]
0x180019c2a  mov     [rbx], ax
0x180019c2d  mov     eax, dword ptr [rsp+270h+pv+8]
0x180019c31  mov     [rbx+10h], eax
0x180019c34  mov     eax, dword ptr [rsp+270h+pv+0Ch]
0x180019c38  mov     [rbx+14h], eax
0x180019c3b  mov     eax, [rsp+270h+var_238]
0x180019c3f  mov     [rbx+18h], eax
0x180019c42  mov     [rbx+8], rsi
0x180019c46  cmp     dword ptr [rsp+270h+pv+4], esi
0x180019c4a  jnz     short loc_180019CC5
0x180019c4c  lea     r8d, [rsi+4]; cb
0x180019c50  mov     [rsp+270h+cb], esi
0x180019c54  lea     rdx, [rsp+270h+cb]; pv
0x180019c59  mov     rcx, rdi; pstm
0x180019c5c  call    cs:__imp_IStream_Read
0x180019c62  mov     ecx, eax
0x180019c64  test    eax, eax
0x180019c66  js      short loc_180019CC5
0x180019c68  mov     r8d, [rsp+270h+cb]; cb
0x180019c6d  mov     ecx, 8007000Dh
0x180019c72  lea     eax, [r8-1]
0x180019c76  cmp     eax, 207h
0x180019c7b  ja      short loc_180019CC5
0x180019c7d  test    r8b, 1
0x180019c81  jnz     short loc_180019CC5
0x180019c83  lea     rdx, [rsp+270h+szFormat]; pv
0x180019c88  mov     rcx, rdi; pstm
0x180019c8b  call    cs:__imp_IStream_Read
0x180019c91  mov     ecx, eax
0x180019c93  test    eax, eax
0x180019c95  js      short loc_180019CC5
0x180019c97  mov     eax, [rsp+270h+cb]
0x180019c9b  mov     ecx, 8007000Dh
0x180019ca0  shr     rax, 1
0x180019ca3  cmp     [rsp+rax*2+270h+var_232], si
0x180019ca8  jnz     short loc_180019CC5
0x180019caa  lea     rcx, [rsp+270h+szFormat]; lpszFormat
0x180019caf  call    cs:__imp_RegisterClipboardFormatW
0x180019cb5  mov     [rbx], ax
0x180019cb8  neg     ax
0x180019cbb  sbb     ecx, ecx
0x180019cbd  not     ecx
0x180019cbf  and     ecx, 8007000Eh
0x180019cc5  mov     eax, ecx
0x180019cc7  mov     rcx, [rbp+170h+var_20]
0x180019cce  xor     rcx, rsp; StackCookie
0x180019cd1  call    __security_check_cookie
0x180019cd6  mov     rbx, [rsp+270h+arg_10]
0x180019cde  add     rsp, 260h
0x180019ce5  pop     rdi
0x180019ce6  pop     rsi
0x180019ce7  pop     rbp
0x180019ce8  retn
```
