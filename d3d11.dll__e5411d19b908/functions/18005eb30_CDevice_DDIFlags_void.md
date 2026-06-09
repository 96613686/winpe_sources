# CDevice::DDIFlags(void)

- ea: `0x18005eb30`
- end: `0x18005ec6f`
- name: `?DDIFlags@CDevice@@QEBAIXZ`
- size: `319`
- prototype: `unsigned int __fastcall(CDevice *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180037440`
- `0x18005e4f0`
- `0x1800a3aa4`
- `0x180115d10`
- `0x180165b70`
- `0x180166770`
- `0x1801675f0`
- `0x1801bada0`

## callees

- `0x18005eb30`
- `0x18005ec80`
- `0x1800ac684`

## import_xrefs

- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18005ec52`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18005ec52`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncComputeDDICreationFlag` at `0x18005ec60`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncComputeDDICreationFlag` at `0x18005ec60`

## pseudocode

```c
__int64 __fastcall CDevice::DDIFlags(CDevice *this, __int64 a2)
{
  int v3; // r8d
  unsigned int v4; // r9d
  unsigned int v5; // r10d
  unsigned int v6; // ebx
  char v7; // al
  int v8; // eax

  LOBYTE(a2) = 9;
  if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(this, a2, 4) )
    v6 = v4 | v5 & 0x1000;
  else
    v6 = v4;
  v7 = *((_BYTE *)this + 1112);
  if ( (v7 & 0xFC) != 0 || v7 == 1 )
  {
    v8 = *((_DWORD *)this + 320);
    if ( v8 != 45056 )
    {
      switch ( v8 )
      {
        case 45312:
          v3 = 6;
          break;
        case 41216:
          v3 = 2;
          break;
        case 37120:
          v3 = 8;
          break;
        case 37376:
          v3 = 10;
          break;
        case 37632:
          v3 = 12;
          break;
        case 40960:
          v3 = 0;
          break;
        default:
          v3 = 14;
          if ( v8 != 49152 )
            v3 = 64;
          break;
      }
    }
    v6 |= v3 | (16 * (v5 & 1)) | (v5 >> 1) & 0x20;
    if ( (unsigned __int8)IsXboxIsAsyncComputeOnlyDevicePresent()
      && (unsigned int)XboxIsAsyncComputeOnlyDevice(*((unsigned int *)this + 315)) )
    {
      v6 |= XboxGetAsyncComputeDDICreationFlag();
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18005eb30  mov     [rsp+arg_0], rbx
0x18005eb35  mov     [rsp+arg_8], rsi
0x18005eb3a  push    rdi
0x18005eb3b  sub     rsp, 20h
0x18005eb3f  mov     r10d, [rcx+4ECh]
0x18005eb46  mov     r8d, 4
0x18005eb4c  mov     r9d, r10d
0x18005eb4f  mov     dl, 9
0x18005eb51  shr     r9d, 3
0x18005eb55  mov     rdi, rcx
0x18005eb58  and     r9d, 1
0x18005eb5c  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x18005eb61  test    al, al
0x18005eb63  jz      short loc_18005EBC7
0x18005eb65  mov     ebx, r10d
0x18005eb68  and     ebx, 1000h
0x18005eb6e  or      ebx, r9d
0x18005eb71  mov     al, [rdi+458h]
0x18005eb77  test    al, 0FCh
0x18005eb79  jz      short loc_18005EBC1
0x18005eb7b  mov     eax, [rdi+500h]
0x18005eb81  cmp     eax, 0B000h
0x18005eb86  jnz     short loc_18005EBCC
0x18005eb88  mov     eax, r10d
0x18005eb8b  and     r10d, 1
0x18005eb8f  shr     eax, 1
0x18005eb91  and     eax, 20h
0x18005eb94  shl     r10d, 4
0x18005eb98  or      eax, r10d
0x18005eb9b  or      eax, r8d
0x18005eb9e  or      ebx, eax
0x18005eba0  mov     esi, ebx
0x18005eba2  call    IsXboxIsAsyncComputeOnlyDevicePresent
0x18005eba7  test    al, al
0x18005eba9  jnz     loc_18005EC4C
0x18005ebaf  mov     rsi, [rsp+28h+arg_8]
0x18005ebb4  mov     eax, ebx
0x18005ebb6  mov     rbx, [rsp+28h+arg_0]
0x18005ebbb  add     rsp, 20h
0x18005ebbf  pop     rdi
0x18005ebc0  retn
0x18005ebc1  cmp     al, 1
0x18005ebc3  jz      short loc_18005EB7B
0x18005ebc5  jmp     short loc_18005EBAF
0x18005ebc7  mov     ebx, r9d
0x18005ebca  jmp     short loc_18005EB71
0x18005ebcc  cmp     eax, 0B100h
0x18005ebd1  jz      short loc_18005EC0D
0x18005ebd3  cmp     eax, 0A100h
0x18005ebd8  jz      short loc_18005EC18
0x18005ebda  cmp     eax, 9100h
0x18005ebdf  jz      short loc_18005EC41
0x18005ebe1  cmp     eax, 9200h
0x18005ebe6  jz      short loc_18005EC36
0x18005ebe8  cmp     eax, 9300h
0x18005ebed  jz      short loc_18005EC2B
0x18005ebef  cmp     eax, 0A000h
0x18005ebf4  jz      short loc_18005EC23
0x18005ebf6  mov     ecx, 40h ; '@'
0x18005ebfb  cmp     eax, 0C000h
0x18005ec00  lea     r8d, [rcx-32h]
0x18005ec04  cmovnz  r8d, ecx
0x18005ec08  jmp     loc_18005EB88
0x18005ec0d  mov     r8d, 6
0x18005ec13  jmp     loc_18005EB88
0x18005ec18  mov     r8d, 2
0x18005ec1e  jmp     loc_18005EB88
0x18005ec23  xor     r8d, r8d
0x18005ec26  jmp     loc_18005EB88
0x18005ec2b  mov     r8d, 0Ch
0x18005ec31  jmp     loc_18005EB88
0x18005ec36  mov     r8d, 0Ah
0x18005ec3c  jmp     loc_18005EB88
0x18005ec41  mov     r8d, 8
0x18005ec47  jmp     loc_18005EB88
0x18005ec4c  mov     ecx, [rdi+4ECh]
0x18005ec52  call    cs:__imp_XboxIsAsyncComputeOnlyDevice
0x18005ec58  test    eax, eax
0x18005ec5a  jz      loc_18005EBAF
0x18005ec60  call    cs:__imp_XboxGetAsyncComputeDDICreationFlag
0x18005ec66  mov     ebx, eax
0x18005ec68  or      ebx, esi
0x18005ec6a  jmp     loc_18005EBAF
```
