# IsPacketFragment

- ea: `0x140028af8`
- end: `0x140028c03`
- name: `IsPacketFragment`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140029850`
- `0x140029e50`
- `0x14002a440`

## callees

- `0x1400021bc`
- `0x140028af8`
- `0x140028c0c`
- `0x140028d34`

## import_xrefs

- `NETIO!NetioAllocateMdl` at `0x140028b28`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140028b32`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140028b32`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140028bea`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140028bea`

## pseudocode

```c
__int64 __fastcall IsPacketFragment(__int64 a1, ULONG a2, _BYTE *a3)
{
  NDIS_STATUS v3; // ebx
  __int64 *v4; // rsi
  struct _NET_BUFFER *v7; // rcx
  unsigned int v8; // eax
  _DWORD *Buffer; // rax
  struct _NET_BUFFER *v10; // rcx
  ULONG v11; // edx

  v3 = 0;
  v4 = (__int64 *)(a1 + 8);
  if ( !a2 )
  {
LABEL_10:
    if ( *(_DWORD *)(*v4 + 24) >= 0x14u )
    {
      Buffer = NatShimAllocateBuffer(*v4);
      if ( Buffer )
      {
        if ( (*(_WORD *)(*((_QWORD *)Buffer + 2) + 6LL) & 0xFF3F) != 0 )
          *a3 = 1;
        NatShimFreeBuffer(Buffer);
      }
      else
      {
        v3 = -1073741823;
      }
      if ( a2 )
      {
        v10 = (struct _NET_BUFFER *)*v4;
        v11 = a2 + *(_DWORD *)(*v4 + 16);
        if ( v11 >= *(_DWORD *)(*(_QWORD *)(*v4 + 8) + 40LL) )
        {
          NdisAdvanceNetBufferDataStart(v10, a2, 0, 0);
        }
        else
        {
          v10->DataOffset += a2;
          v10->DataLength -= a2;
          v10->CurrentMdlOffset = v11;
        }
      }
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)v3;
  }
  v7 = (struct _NET_BUFFER *)*v4;
  v8 = *(_DWORD *)(*v4 + 16);
  if ( v8 >= a2 )
  {
    v7->DataOffset -= a2;
    v7->DataLength += a2;
    v7->CurrentMdlOffset = v8 - a2;
    goto LABEL_10;
  }
  v3 = NdisRetreatNetBufferDataStart(v7, a2, 0, NetioAllocateMdl);
  if ( v3
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x10u,
      (__int64)WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids,
      v3);
  }
  if ( v3 >= 0 )
    goto LABEL_10;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140028af8  push    rbx
0x140028afa  push    rsi
0x140028afb  push    rdi
0x140028afc  push    r14
0x140028afe  sub     rsp, 28h
0x140028b02  xor     ebx, ebx
0x140028b04  lea     rsi, [rcx+8]
0x140028b08  mov     r14, r8
0x140028b0b  mov     edi, edx
0x140028b0d  test    edx, edx
0x140028b0f  jz      short loc_140028B80
0x140028b11  mov     rcx, [rsi]; NetBuffer
0x140028b14  mov     eax, [rcx+10h]
0x140028b17  cmp     eax, edx
0x140028b19  jb      short loc_140028B28
0x140028b1b  sub     [rcx+28h], edx
0x140028b1e  sub     eax, edx
0x140028b20  add     [rcx+18h], edx
0x140028b23  mov     [rcx+10h], eax
0x140028b26  jmp     short loc_140028B80
0x140028b28  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140028b2f  xor     r8d, r8d; DataBackFill
0x140028b32  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140028b39  nop     dword ptr [rax+rax+00h]
0x140028b3e  mov     ebx, eax
0x140028b40  test    eax, eax
0x140028b42  jz      short loc_140028B7C
0x140028b44  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b4b  lea     rax, WPP_GLOBAL_Control
0x140028b52  cmp     rcx, rax
0x140028b55  jz      short loc_140028B7C
0x140028b57  mov     eax, [rcx+2Ch]
0x140028b5a  test    al, 2
0x140028b5c  jz      short loc_140028B7C
0x140028b5e  cmp     byte ptr [rcx+29h], 2
0x140028b62  jb      short loc_140028B7C
0x140028b64  mov     rcx, [rcx+18h]
0x140028b68  lea     r8, WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids
0x140028b6f  mov     edx, 10h
0x140028b74  mov     r9d, ebx
0x140028b77  call    WPP_SF_d
0x140028b7c  test    ebx, ebx
0x140028b7e  js      short loc_140028BF6
0x140028b80  mov     rcx, [rsi]
0x140028b83  cmp     dword ptr [rcx+18h], 14h
0x140028b87  jnb     short loc_140028B90
0x140028b89  mov     ebx, 0C0000001h
0x140028b8e  jmp     short loc_140028BF6
0x140028b90  call    NatShimAllocateBuffer
0x140028b95  mov     rdx, rax
0x140028b98  test    rax, rax
0x140028b9b  jnz     short loc_140028BA4
0x140028b9d  mov     ebx, 0C0000001h
0x140028ba2  jmp     short loc_140028BC2
0x140028ba4  mov     rax, [rax+10h]
0x140028ba8  movzx   ecx, word ptr [rax+6]
0x140028bac  mov     eax, 0FF3Fh
0x140028bb1  test    ax, cx
0x140028bb4  jz      short loc_140028BBA
0x140028bb6  mov     byte ptr [r14], 1
0x140028bba  mov     rcx, rdx
0x140028bbd  call    NatShimFreeBuffer
0x140028bc2  test    edi, edi
0x140028bc4  jz      short loc_140028BF6
0x140028bc6  mov     rcx, [rsi]; NetBuffer
0x140028bc9  mov     rax, [rcx+8]
0x140028bcd  mov     edx, [rcx+10h]
0x140028bd0  add     edx, edi
0x140028bd2  cmp     edx, [rax+28h]
0x140028bd5  jnb     short loc_140028BE2
0x140028bd7  add     [rcx+28h], edi
0x140028bda  sub     [rcx+18h], edi
0x140028bdd  mov     [rcx+10h], edx
0x140028be0  jmp     short loc_140028BF6
0x140028be2  xor     r9d, r9d; FreeMdlHandler
0x140028be5  xor     r8d, r8d; FreeMdl
0x140028be8  mov     edx, edi; DataOffsetDelta
0x140028bea  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140028bf1  nop     dword ptr [rax+rax+00h]
0x140028bf6  mov     eax, ebx
0x140028bf8  add     rsp, 28h
0x140028bfc  pop     r14
0x140028bfe  pop     rdi
0x140028bff  pop     rsi
0x140028c00  pop     rbx
0x140028c01  retn
```
