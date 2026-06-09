# Int_FwValidateString

- ea: `0x180010f20`
- end: `0x180011021`
- name: `Int_FwValidateString`
- size: `257`
- prototype: `__int64 __fastcall(wchar_t *Str, int, unsigned int, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180014b6c`
- `0x180014cb0`
- `0x1800150e0`
- `0x180016650`
- `0x1800169f0`
- `0x18002d930`
- `0x18002daf4`
- `0x18002e420`
- `0x18002e7c0`

## callees

- `0x18000ccd4`
- `0x180010f20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180010f58`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180010f58`

## pseudocode

```c
__int64 __fastcall Int_FwValidateString(wchar_t *Str, int a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  v4 = 0;
  if ( !Str )
  {
    if ( a2 )
      return v4;
    v4 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v8 = 228;
LABEL_21:
    WPP_SF_d(v7[2], v8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    return v4;
  }
  v5 = -1;
  do
    ++v5;
  while ( Str[v5] );
  if ( v5 >= a4 )
  {
    v4 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v8 = 229;
    goto LABEL_21;
  }
  if ( v5 < a3 )
  {
    v4 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v8 = 230;
    goto LABEL_21;
  }
  if ( wcschr(Str, 0x7Cu) )
  {
    v4 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 231;
      goto LABEL_21;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180010f20  push    rbx
0x180010f22  sub     rsp, 20h
0x180010f26  xor     ebx, ebx
0x180010f28  mov     r10, rcx
0x180010f2b  test    rcx, rcx
0x180010f2e  jz      short loc_180010F6B
0x180010f30  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010f37  inc     rax
0x180010f3a  cmp     [rcx+rax*2], bx
0x180010f3e  jnz     short loc_180010F37
0x180010f40  mov     ecx, r9d
0x180010f43  cmp     rax, rcx
0x180010f46  jnb     short loc_180010F94
0x180010f48  mov     ecx, r8d
0x180010f4b  cmp     rax, rcx
0x180010f4e  jb      short loc_180010FB9
0x180010f50  mov     edx, 7Ch ; '|'; Ch
0x180010f55  mov     rcx, r10; Str
0x180010f58  call    cs:__imp_wcschr
0x180010f5e  test    rax, rax
0x180010f61  jnz     short loc_180010FDE
0x180010f63  mov     eax, ebx
0x180010f65  add     rsp, 20h
0x180010f69  pop     rbx
0x180010f6a  retn
0x180010f6b  test    edx, edx
0x180010f6d  jnz     short loc_180010F63
0x180010f6f  mov     ebx, 57h ; 'W'
0x180010f74  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f7b  lea     rax, WPP_GLOBAL_Control
0x180010f82  cmp     rcx, rax
0x180010f85  jz      short loc_180010F63
0x180010f87  test    byte ptr [rcx+1Ch], 1
0x180010f8b  jz      short loc_180010F63
0x180010f8d  mov     edx, 0E4h
0x180010f92  jmp     short loc_180011009
0x180010f94  mov     ebx, 57h ; 'W'
0x180010f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fa0  lea     rax, WPP_GLOBAL_Control
0x180010fa7  cmp     rcx, rax
0x180010faa  jz      short loc_180010F63
0x180010fac  test    byte ptr [rcx+1Ch], 1
0x180010fb0  jz      short loc_180010F63
0x180010fb2  mov     edx, 0E5h
0x180010fb7  jmp     short loc_180011009
0x180010fb9  mov     ebx, 57h ; 'W'
0x180010fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fc5  lea     rax, WPP_GLOBAL_Control
0x180010fcc  cmp     rcx, rax
0x180010fcf  jz      short loc_180010F63
0x180010fd1  test    byte ptr [rcx+1Ch], 1
0x180010fd5  jz      short loc_180010F63
0x180010fd7  mov     edx, 0E6h
0x180010fdc  jmp     short loc_180011009
0x180010fde  mov     ebx, 57h ; 'W'
0x180010fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fea  lea     rax, WPP_GLOBAL_Control
0x180010ff1  cmp     rcx, rax
0x180010ff4  jz      loc_180010F63
0x180010ffa  test    byte ptr [rcx+1Ch], 1
0x180010ffe  jz      loc_180010F63
0x180011004  mov     edx, 0E7h
0x180011009  mov     rcx, [rcx+10h]
0x18001100d  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180011014  mov     r9d, ebx
0x180011017  call    WPP_SF_d
0x18001101c  jmp     loc_180010F63
```
