# SdppGetDescriptorFromDescriptorList(_SDP_NODE *,_GUID const &,_SDP_NODE * *)

- ea: `0x1400344f4`
- end: `0x1400345aa`
- name: `?SdppGetDescriptorFromDescriptorList@@YAJPEAU_SDP_NODE@@AEBU_GUID@@PEAPEAU1@@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct _SDP_NODE *, const struct _GUID *, struct _SDP_NODE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14003468c`

## callees

- `0x140020260`
- `0x1400344f4`
- `0x1400349fc`

## pseudocode

```c
__int64 __fastcall SdppGetDescriptorFromDescriptorList(
        struct _SDP_NODE *a1,
        const struct _GUID *a2,
        struct _SDP_NODE **a3)
{
  USHORT Type; // dx
  SDP_NODE_DATA *p_u; // r14
  struct _SDP_NODE *LowPart; // rdi
  unsigned int v6; // ebx
  struct _SDP_NODE *v8; // rcx
  _OWORD Buf1[3]; // [rsp+20h] [rbp-38h] BYREF

  Type = a1->hdr.Type;
  p_u = &a1->u;
  LowPart = (struct _SDP_NODE *)a1->u.int128.LowPart;
  *a3 = 0;
  v6 = -1073741434;
  if ( Type == 6 )
  {
    while ( LowPart != (struct _SDP_NODE *)p_u )
    {
      if ( LowPart->hdr.Type != 6 )
        return v6;
      v8 = (struct _SDP_NODE *)LowPart->u.int128.LowPart;
      if ( v8 == (struct _SDP_NODE *)&LowPart->u || v8->hdr.Type != 3 )
        return v6;
      Buf1[0] = 0;
      SdpNormalizeUuid(v8, Buf1);
      if ( !memcmp(Buf1, &RFCOMM_PROTOCOL_UUID, 0x10u) )
      {
        if ( LowPart )
        {
          *a3 = LowPart;
          return 0;
        }
        return (unsigned int)-1073741275;
      }
      LowPart = (struct _SDP_NODE *)LowPart->hdr.Link.Flink;
    }
    return (unsigned int)-1073741275;
  }
  else
  {
    return Type != 6 ? 0xC0000186 : 0;
  }
}

```

## disassembly

```asm
0x1400344f4  push    rbx
0x1400344f6  push    rbp
0x1400344f7  push    rsi
0x1400344f8  push    rdi
0x1400344f9  push    r14
0x1400344fb  sub     rsp, 30h
0x1400344ff  movzx   edx, word ptr [rcx+10h]
0x140034503  lea     r14, [rcx+20h]
0x140034507  mov     rdi, [r14]
0x14003450a  mov     ebp, 6
0x14003450f  movzx   eax, bp
0x140034512  mov     qword ptr [r8], 0
0x140034519  sub     ax, dx
0x14003451c  mov     ebx, 0C0000186h
0x140034521  neg     ax
0x140034524  mov     rsi, r8
0x140034527  sbb     r9d, r9d
0x14003452a  and     r9d, ebx
0x14003452d  cmp     bp, dx
0x140034530  jnz     short loc_140034599
0x140034532  cmp     rdi, r14
0x140034535  jz      short loc_140034592
0x140034537  cmp     bp, [rdi+10h]
0x14003453b  jnz     short loc_14003459C
0x14003453d  lea     rax, [rdi+20h]
0x140034541  mov     rcx, [rax]
0x140034544  cmp     rcx, rax
0x140034547  jz      short loc_14003459C
0x140034549  mov     eax, 3
0x14003454e  cmp     ax, [rcx+10h]
0x140034552  jnz     short loc_14003459C
0x140034554  xorps   xmm0, xmm0
0x140034557  lea     rdx, [rsp+58h+Buf1]
0x14003455c  movups  [rsp+58h+Buf1], xmm0
0x140034561  call    SdpNormalizeUuid
0x140034566  mov     r8d, 10h; Size
0x14003456c  lea     rdx, RFCOMM_PROTOCOL_UUID; Buf2
0x140034573  lea     rcx, [rsp+58h+Buf1]; Buf1
0x140034578  call    memcmp
0x14003457d  test    eax, eax
0x14003457f  jz      short loc_140034586
0x140034581  mov     rdi, [rdi]
0x140034584  jmp     short loc_140034532
0x140034586  test    rdi, rdi
0x140034589  jz      short loc_140034592
0x14003458b  mov     [rsi], rdi
0x14003458e  xor     ebx, ebx
0x140034590  jmp     short loc_14003459C
0x140034592  mov     ebx, 0C0000225h
0x140034597  jmp     short loc_14003459C
0x140034599  mov     ebx, r9d
0x14003459c  mov     eax, ebx
0x14003459e  add     rsp, 30h
0x1400345a2  pop     r14
0x1400345a4  pop     rdi
0x1400345a5  pop     rsi
0x1400345a6  pop     rbp
0x1400345a7  pop     rbx
0x1400345a8  retn
```
