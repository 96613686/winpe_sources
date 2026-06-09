# FreeObjectInfo(_objectinfo *)

- ea: `0x180003a14`
- end: `0x180003ab2`
- name: `?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z`
- size: `158`
- prototype: `void __fastcall(struct _objectinfo *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a58`
- `0x18000683c`
- `0x18000745c`
- `0x18000828c`
- `0x180008fc0`
- `0x180009df0`
- `0x18000a94c`

## callees

- `0x180003a14`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsMem` at `0x180003a9c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180003a9c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a37`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a46`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a72`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a86`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a37`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a46`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a72`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180003a86`

## pseudocode

```c
void __fastcall FreeObjectInfo(WCHAR **a1)
{
  WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  unsigned int v4; // edi
  WCHAR *v5; // rcx
  WCHAR *v6; // rcx
  WCHAR *v7; // rcx

  if ( a1 )
  {
    v2 = *a1;
    if ( v2 )
      FreeADsStr(v2);
    v3 = a1[1];
    if ( v3 )
      FreeADsStr(v3);
    if ( a1[4] && *((_DWORD *)a1 + 5) )
    {
      v4 = 0;
      do
      {
        v5 = *(WCHAR **)&a1[4][8 * v4];
        if ( v5 )
          FreeADsStr(v5);
        v6 = *(WCHAR **)&a1[4][8 * v4 + 4];
        if ( v6 )
          FreeADsStr(v6);
        ++v4;
      }
      while ( v4 < *((_DWORD *)a1 + 5) );
    }
    v7 = a1[4];
    if ( v7 )
      FreeADsMem(v7);
  }
}

```

## disassembly

```asm
0x180003a14  test    rcx, rcx
0x180003a17  jz      locret_180003AB1
0x180003a1d  mov     [rsp+arg_0], rbx
0x180003a22  mov     [rsp+arg_8], rsi
0x180003a27  push    rdi
0x180003a28  sub     rsp, 20h
0x180003a2c  mov     rbx, rcx
0x180003a2f  mov     rcx, [rcx]; pStr
0x180003a32  test    rcx, rcx
0x180003a35  jz      short loc_180003A3D
0x180003a37  call    cs:__imp_FreeADsStr
0x180003a3d  mov     rcx, [rbx+8]; pStr
0x180003a41  test    rcx, rcx
0x180003a44  jz      short loc_180003A4C
0x180003a46  call    cs:__imp_FreeADsStr
0x180003a4c  cmp     qword ptr [rbx+20h], 0
0x180003a51  jz      short loc_180003A93
0x180003a53  mov     eax, [rbx+14h]
0x180003a56  test    eax, eax
0x180003a58  jz      short loc_180003A93
0x180003a5a  xor     edi, edi
0x180003a5c  test    eax, eax
0x180003a5e  jz      short loc_180003A93
0x180003a60  mov     rax, [rbx+20h]
0x180003a64  mov     esi, edi
0x180003a66  add     rsi, rsi
0x180003a69  mov     rcx, [rax+rsi*8]; pStr
0x180003a6d  test    rcx, rcx
0x180003a70  jz      short loc_180003A78
0x180003a72  call    cs:__imp_FreeADsStr
0x180003a78  mov     rax, [rbx+20h]
0x180003a7c  mov     rcx, [rax+rsi*8+8]; pStr
0x180003a81  test    rcx, rcx
0x180003a84  jz      short loc_180003A8C
0x180003a86  call    cs:__imp_FreeADsStr
0x180003a8c  inc     edi
0x180003a8e  cmp     edi, [rbx+14h]
0x180003a91  jb      short loc_180003A60
0x180003a93  mov     rcx, [rbx+20h]; pMem
0x180003a97  test    rcx, rcx
0x180003a9a  jz      short loc_180003AA2
0x180003a9c  call    cs:__imp_FreeADsMem
0x180003aa2  mov     rbx, [rsp+28h+arg_0]
0x180003aa7  mov     rsi, [rsp+28h+arg_8]
0x180003aac  add     rsp, 20h
0x180003ab0  pop     rdi
0x180003ab1  retn
```
