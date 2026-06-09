# DevAuth2_HostExportKey

- ea: `0x180003d00`
- end: `0x180003e18`
- name: `DevAuth2_HostExportKey`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800013a0`

## callees

- `0x180002888`
- `0x180003d00`
- `0x1800067e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x180003d80`
- `ntoskrnl!RtlCompareMemory` at `0x180003d80`

## pseudocode

```c
_BOOL8 __fastcall DevAuth2_HostExportKey(__int64 a1, const void *a2, void *a3, int a4)
{
  int v6; // edi
  __int128 v8; // xmm1
  __int128 v9; // xmm1
  _BOOL8 result; // rax
  size_t Size; // [rsp+30h] [rbp-88h]
  _QWORD Source2[2]; // [rsp+40h] [rbp-78h] BYREF
  int v13[4]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v14; // [rsp+60h] [rbp-58h]
  __int128 v15; // [rsp+70h] [rbp-48h]
  __int128 v16; // [rsp+80h] [rbp-38h]

  strcpy((char *)Source2, "EXPORTER");
  v6 = (int)a2;
  result = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          if ( *(_BYTE *)a1 == 2 && RtlCompareMemory(a2, Source2, 8u) == 8 )
          {
            v8 = *(_OWORD *)(a1 + 32);
            *(_OWORD *)v13 = *(_OWORD *)(a1 + 16);
            v14 = v8;
            v9 = *(_OWORD *)(a1 + 64);
            v15 = *(_OWORD *)(a1 + 48);
            v16 = v9;
            if ( a1 != -1048 )
            {
              LODWORD(Size) = a4;
              if ( (unsigned int)DevAuthPesudoRandomFunction(v6, (int)a1 + 1048, 48, (int)v13, 64, a3, Size) )
                return 1;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003d00  mov     [rsp+arg_18], rbx
0x180003d05  push    rbp
0x180003d06  push    rsi
0x180003d07  push    rdi
0x180003d08  sub     rsp, 0A0h
0x180003d0f  mov     rax, cs:__security_cookie
0x180003d16  xor     rax, rsp
0x180003d19  mov     [rsp+0B8h+var_28], rax
0x180003d21  movsd   xmm0, qword ptr cs:aExporter; "EXPORTER"
0x180003d29  mov     esi, r9d
0x180003d2c  mov     al, byte ptr cs:aExporter+8; ""
0x180003d32  mov     rbp, r8
0x180003d35  movsd   [rsp+0B8h+Source2], xmm0
0x180003d3b  mov     rdi, rdx
0x180003d3e  mov     [rsp+0B8h+var_70], al
0x180003d42  mov     rbx, rcx
0x180003d45  test    rcx, rcx
0x180003d48  jz      loc_180003DF2
0x180003d4e  test    rdx, rdx
0x180003d51  jz      loc_180003DF2
0x180003d57  test    r8, r8
0x180003d5a  jz      loc_180003DF2
0x180003d60  test    r9d, r9d
0x180003d63  jz      loc_180003DF2
0x180003d69  cmp     byte ptr [rcx], 2
0x180003d6c  jnz     loc_180003DF2
0x180003d72  mov     r8d, 8; Length
0x180003d78  lea     rdx, [rsp+0B8h+Source2]; Source2
0x180003d7d  mov     rcx, rdi; Source1
0x180003d80  call    cs:__imp_RtlCompareMemory
0x180003d87  nop     dword ptr [rax+rax+00h]
0x180003d8c  cmp     rax, 8
0x180003d90  jnz     short loc_180003DF2
0x180003d92  movups  xmm0, xmmword ptr [rbx+10h]
0x180003d96  lea     rdx, [rbx+418h]; int
0x180003d9d  movups  xmm1, xmmword ptr [rbx+20h]
0x180003da1  movaps  xmmword ptr [rsp+0B8h+var_68], xmm0
0x180003da6  movaps  [rsp+0B8h+var_58], xmm1
0x180003dab  movups  xmm0, xmmword ptr [rbx+30h]
0x180003daf  movups  xmm1, xmmword ptr [rbx+40h]
0x180003db3  movaps  [rsp+0B8h+var_48], xmm0
0x180003db8  movaps  [rsp+0B8h+var_38], xmm1
0x180003dc0  test    rdx, rdx
0x180003dc3  jz      short loc_180003DF2
0x180003dc5  mov     dword ptr [rsp+0B8h+Size], esi; Size
0x180003dc9  lea     r9, [rsp+0B8h+var_68]; int
0x180003dce  mov     [rsp+0B8h+var_90], rbp; void *
0x180003dd3  lea     r8d, [rax+28h]; int
0x180003dd7  mov     rcx, rdi; int
0x180003dda  mov     [rsp+0B8h+var_98], 40h ; '@'; int
0x180003de2  call    DevAuthPesudoRandomFunction
0x180003de7  test    eax, eax
0x180003de9  jz      short loc_180003DF2
0x180003deb  mov     eax, 1
0x180003df0  jmp     short loc_180003DF4
0x180003df2  xor     eax, eax
0x180003df4  mov     rcx, [rsp+0B8h+var_28]
0x180003dfc  xor     rcx, rsp; StackCookie
0x180003dff  call    __security_check_cookie
0x180003e04  mov     rbx, [rsp+0B8h+arg_18]
0x180003e0c  add     rsp, 0A0h
0x180003e13  pop     rdi
0x180003e14  pop     rsi
0x180003e15  pop     rbp
0x180003e16  retn
```
