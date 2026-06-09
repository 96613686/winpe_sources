# GetBinaryRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)

- ea: `0x180001b90`
- end: `0x180001d75`
- name: `?GetBinaryRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z`
- size: `485`
- prototype: `int(struct IIS_SETUP_REGISTRY_ENTRY *, struct BUFFER *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000224c`

## callees

- `0x180001b90`
- `0x180002ff8`
- `0x180003024`
- `0x180003605`
- `0x180003650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001c21`
- `KERNEL32!GetLastError` at `0x180001c21`

## pseudocode

```c
__int64 __fastcall GetBinaryRegistryValueToWrite(struct IIS_SETUP_REGISTRY_ENTRY *a1, void **a2, unsigned int *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // edi
  signed int LastError; // eax
  unsigned int v10; // ebx
  __int16 *v11; // r9
  __int16 v12; // cx
  _BYTE *i; // r11
  __int16 v14; // dx
  char v15; // dl
  void *v16; // rdx
  _QWORD v18[4]; // [rsp+20h] [rbp-68h] BYREF
  void *Src; // [rsp+40h] [rbp-48h]
  int v20; // [rsp+48h] [rbp-40h]
  __int16 v21; // [rsp+4Ch] [rbp-3Ch]

  v20 = 32;
  v18[0] = 0;
  Src = v18;
  v21 = 256;
  if ( a1 && a2 && a3 )
  {
    v6 = *((_QWORD *)a1 + 5);
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
    v8 = ((int)v7 + 1) / 3u;
    if ( v8 > 0x20 && !BUFFER::ReallocStorage((BUFFER *)v18, v8) )
      goto LABEL_8;
    v11 = (__int16 *)*((_QWORD *)a1 + 5);
    v12 = *v11;
    if ( *v11 )
    {
      for ( i = Src; ; ++i )
      {
        if ( (unsigned __int16)(v12 - 97) > 5u && (unsigned __int16)(v12 - 65) > 5u && (unsigned __int16)(v12 - 48) > 9u )
          goto LABEL_34;
        v14 = v11[1];
        if ( (unsigned __int16)(v14 - 97) > 5u && (unsigned __int16)(v14 - 65) > 5u && (unsigned __int16)(v14 - 48) > 9u )
          goto LABEL_34;
        if ( (unsigned __int16)(v12 - 97) > 5u )
        {
          if ( (unsigned __int16)(v12 - 65) > 5u )
          {
            if ( (unsigned __int16)(v12 - 48) > 9u )
              LOBYTE(v12) = -1;
          }
          else
          {
            LOBYTE(v12) = v12 - 55;
          }
        }
        else
        {
          LOBYTE(v12) = v12 - 87;
        }
        if ( (unsigned __int16)(v14 - 97) > 5u )
        {
          if ( (unsigned __int16)(v14 - 65) > 5u )
            v15 = (unsigned __int16)(v14 - 48) > 9u ? -1 : v14 - 48;
          else
            v15 = v14 - 55;
        }
        else
        {
          v15 = v14 - 87;
        }
        *i = v15 + 16 * v12;
        if ( v11[2] != 44 )
          break;
        v11 += 3;
        v12 = *v11;
        if ( !*v11 )
          goto LABEL_36;
      }
      if ( v11[2] )
      {
LABEL_34:
        v10 = -2147024883;
        goto LABEL_40;
      }
    }
LABEL_36:
    if ( v8 <= *((_DWORD *)a2 + 10) || BUFFER::ReallocStorage((BUFFER *)a2, v8) )
    {
      v16 = Src;
      v10 = 0;
      *a3 = v8;
      memcpy_0(a2[4], v16, v8);
    }
    else
    {
LABEL_8:
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_40:
  if ( (_BYTE)v21 )
    BUFFER::FreeMemoryInternal((BUFFER *)v18);
  return v10;
}

```

## disassembly

```asm
0x180001b90  push    rbx
0x180001b92  push    rbp
0x180001b93  push    rsi
0x180001b94  push    rdi
0x180001b95  push    r14
0x180001b97  sub     rsp, 60h
0x180001b9b  mov     rax, cs:__security_cookie
0x180001ba2  xor     rax, rsp
0x180001ba5  mov     [rsp+88h+var_38], rax
0x180001baa  xor     ebp, ebp
0x180001bac  mov     [rsp+88h+var_40], 20h ; ' '
0x180001bb4  mov     [rsp+88h+var_68], rbp
0x180001bb9  lea     rax, [rsp+88h+var_68]
0x180001bbe  mov     [rsp+88h+Src], rax
0x180001bc3  mov     r14, r8
0x180001bc6  mov     [rsp+88h+var_3C], 100h
0x180001bcd  mov     rsi, rdx
0x180001bd0  mov     rbx, rcx
0x180001bd3  test    rcx, rcx
0x180001bd6  jz      loc_180001D45
0x180001bdc  test    rdx, rdx
0x180001bdf  jz      loc_180001D45
0x180001be5  test    r8, r8
0x180001be8  jz      loc_180001D45
0x180001bee  mov     rax, [rcx+28h]
0x180001bf2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001bf6  inc     rcx
0x180001bf9  cmp     [rax+rcx*2], bp
0x180001bfd  jnz     short loc_180001BF6
0x180001bff  inc     ecx
0x180001c01  mov     eax, 0AAAAAAABh
0x180001c06  mul     ecx
0x180001c08  mov     edi, edx
0x180001c0a  shr     edi, 1
0x180001c0c  cmp     edi, 20h ; ' '
0x180001c0f  jbe     short loc_180001C3F
0x180001c11  mov     edx, edi; unsigned int
0x180001c13  lea     rcx, [rsp+88h+var_68]; this
0x180001c18  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180001c1d  test    al, al
0x180001c1f  jnz     short loc_180001C3F
0x180001c21  call    cs:__imp_GetLastError
0x180001c27  mov     ebx, eax
0x180001c29  test    eax, eax
0x180001c2b  jle     loc_180001D4A
0x180001c31  movzx   ebx, ax
0x180001c34  or      ebx, 80070000h
0x180001c3a  jmp     loc_180001D4A
0x180001c3f  mov     r9, [rbx+28h]
0x180001c43  movzx   ecx, word ptr [r9]
0x180001c47  test    cx, cx
0x180001c4a  jz      loc_180001D16
0x180001c50  mov     r11, [rsp+88h+Src]
0x180001c55  mov     bx, 5
0x180001c59  lea     r8d, [rcx-61h]
0x180001c5d  cmp     r8w, bx
0x180001c61  jbe     short loc_180001C78
0x180001c63  lea     eax, [rcx-41h]
0x180001c66  cmp     ax, bx
0x180001c69  jbe     short loc_180001C78
0x180001c6b  lea     eax, [rcx-30h]
0x180001c6e  cmp     ax, 9
0x180001c72  ja      loc_180001D08
0x180001c78  movzx   edx, word ptr [r9+2]
0x180001c7d  lea     r10d, [rdx-61h]
0x180001c81  cmp     r10w, bx
0x180001c85  jbe     short loc_180001C98
0x180001c87  lea     eax, [rdx-41h]
0x180001c8a  cmp     ax, bx
0x180001c8d  jbe     short loc_180001C98
0x180001c8f  lea     eax, [rdx-30h]
0x180001c92  cmp     ax, 9
0x180001c96  ja      short loc_180001D08
0x180001c98  cmp     r8w, bx
0x180001c9c  ja      short loc_180001CA3
0x180001c9e  sub     cl, 57h ; 'W'
0x180001ca1  jmp     short loc_180001CBB
0x180001ca3  lea     eax, [rcx-41h]
0x180001ca6  cmp     ax, bx
0x180001ca9  ja      short loc_180001CB0
0x180001cab  sub     cl, 37h ; '7'
0x180001cae  jmp     short loc_180001CBB
0x180001cb0  lea     eax, [rcx-30h]
0x180001cb3  cmp     ax, 9
0x180001cb7  jbe     short loc_180001CBB
0x180001cb9  mov     cl, 0FFh
0x180001cbb  cmp     r10w, bx
0x180001cbf  ja      short loc_180001CC6
0x180001cc1  sub     dl, 57h ; 'W'
0x180001cc4  jmp     short loc_180001CE3
0x180001cc6  lea     eax, [rdx-41h]
0x180001cc9  cmp     ax, bx
0x180001ccc  ja      short loc_180001CD3
0x180001cce  sub     dl, 37h ; '7'
0x180001cd1  jmp     short loc_180001CE3
0x180001cd3  lea     eax, [rdx-30h]
0x180001cd6  cmp     ax, 9
0x180001cda  ja      short loc_180001CE1
0x180001cdc  sub     dl, 30h ; '0'
0x180001cdf  jmp     short loc_180001CE3
0x180001ce1  mov     dl, 0FFh
0x180001ce3  shl     cl, 4
0x180001ce6  add     cl, dl
0x180001ce8  mov     [r11], cl
0x180001ceb  cmp     word ptr [r9+4], 2Ch ; ','
0x180001cf1  jnz     short loc_180001D0F
0x180001cf3  add     r9, 6
0x180001cf7  movzx   ecx, word ptr [r9]
0x180001cfb  test    cx, cx
0x180001cfe  jz      short loc_180001D16
0x180001d00  inc     r11
0x180001d03  jmp     loc_180001C59
0x180001d08  mov     ebx, 8007000Dh
0x180001d0d  jmp     short loc_180001D4A
0x180001d0f  cmp     [r9+4], bp
0x180001d14  jnz     short loc_180001D08
0x180001d16  cmp     edi, [rsi+28h]
0x180001d19  jbe     short loc_180001D2D
0x180001d1b  mov     edx, edi; unsigned int
0x180001d1d  mov     rcx, rsi; this
0x180001d20  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180001d25  test    al, al
0x180001d27  jz      loc_180001C21
0x180001d2d  mov     rdx, [rsp+88h+Src]; Src
0x180001d32  mov     ebx, ebp
0x180001d34  mov     [r14], edi
0x180001d37  mov     rcx, [rsi+20h]; void *
0x180001d3b  mov     r8d, edi; Size
0x180001d3e  call    memcpy_0
0x180001d43  jmp     short loc_180001D4A
0x180001d45  mov     ebx, 80070057h
0x180001d4a  cmp     byte ptr [rsp+88h+var_3C], bpl
0x180001d4f  jz      short loc_180001D5B
0x180001d51  lea     rcx, [rsp+88h+var_68]; this
0x180001d56  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180001d5b  mov     eax, ebx
0x180001d5d  mov     rcx, [rsp+88h+var_38]
0x180001d62  xor     rcx, rsp; StackCookie
0x180001d65  call    __security_check_cookie
0x180001d6a  add     rsp, 60h
0x180001d6e  pop     r14
0x180001d70  pop     rdi
0x180001d71  pop     rsi
0x180001d72  pop     rbp
0x180001d73  pop     rbx
0x180001d74  retn
```
