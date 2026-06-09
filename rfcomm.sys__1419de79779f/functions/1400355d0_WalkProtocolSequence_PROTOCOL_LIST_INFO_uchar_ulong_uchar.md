# WalkProtocolSequence(_PROTOCOL_LIST_INFO *,uchar,ulong,uchar *)

- ea: `0x1400355d0`
- end: `0x140035734`
- name: `?WalkProtocolSequence@@YAJPEAU_PROTOCOL_LIST_INFO@@EKPEAE@Z`
- size: `356`
- prototype: `__int64 __fastcall(struct _PROTOCOL_LIST_INFO *, unsigned __int8, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140020260`
- `0x1400355d0`
- `0x140036568`

## pseudocode

```c
__int64 __fastcall WalkProtocolSequence(struct _PROTOCOL_LIST_INFO *a1, __int64 a2, int a3, unsigned __int8 *a4)
{
  unsigned __int8 *v5; // rbp
  __int64 v6; // rsi
  int v7; // r10d
  int v8; // edi
  unsigned __int8 v9; // si
  char v10; // di
  unsigned __int8 v11; // si
  _OWORD Buf1[4]; // [rsp+20h] [rbp-48h] BYREF

  Buf1[0] = 0;
  if ( !a3 || (*a4 & 0xF8) != 0x18 )
    return 3221225485LL;
  v5 = a4 + 1;
  v6 = (unsigned int)g_IndexToDataSize[*a4 & 7];
  SdpRetrieveUuidFromStream(a4 + 1, v6, Buf1);
  v8 = v7 - v6 - 1;
  if ( (*(_DWORD *)a1 & 2) != 0 )
  {
    if ( *((_BYTE *)a1 + 4) )
    {
      if ( memcmp(Buf1, &L2CAP_PROTOCOL_UUID, 0x10u) )
        return 3221225485LL;
      if ( !v8 )
        *((_BYTE *)a1 + 5) = 1;
      *((_BYTE *)a1 + 4) = 0;
    }
    else if ( *((_BYTE *)a1 + 5) && !*((_BYTE *)a1 + 6) )
    {
      if ( memcmp(Buf1, &SDP_PROTOCOL_UUID, 0x10u) && memcmp(Buf1, &RFCOMM_PROTOCOL_UUID, 0x10u) )
        return 3221225485LL;
      *((_BYTE *)a1 + 6) = 1;
    }
  }
  if ( !v8 )
    return 0;
  v9 = v5[v6];
  v10 = v9 >> 3;
  v11 = v9 & 7;
  if ( !memcmp(Buf1, &L2CAP_PROTOCOL_UUID, 0x10u) )
  {
    if ( v10 == 1 && g_IndexToDataSize[v11] == 2 )
    {
      *((_BYTE *)a1 + 6) = 1;
      return 0;
    }
  }
  else
  {
    if ( memcmp(Buf1, &RFCOMM_PROTOCOL_UUID, 0x10u) )
      return 0;
    if ( v10 == 1 )
      return g_IndexToDataSize[v11] != 1 ? 0xC000000D : 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400355d0  push    rbx
0x1400355d2  push    rbp
0x1400355d3  push    rsi
0x1400355d4  push    rdi
0x1400355d5  push    r12
0x1400355d7  push    r15
0x1400355d9  sub     rsp, 38h
0x1400355dd  xorps   xmm0, xmm0
0x1400355e0  mov     r10d, r8d
0x1400355e3  mov     rbx, rcx
0x1400355e6  movups  [rsp+68h+Buf1], xmm0
0x1400355eb  test    r8d, r8d
0x1400355ee  jz      loc_140035721
0x1400355f4  movzx   ecx, byte ptr [r9]
0x1400355f8  mov     al, cl
0x1400355fa  and     al, 0F8h
0x1400355fc  cmp     al, 18h
0x1400355fe  jnz     loc_140035721
0x140035604  mov     eax, ecx
0x140035606  lea     r15, g_IndexToDataSize
0x14003560d  and     eax, 7
0x140035610  lea     rbp, [r9+1]
0x140035614  lea     r8, [rsp+68h+Buf1]
0x140035619  mov     rcx, rbp
0x14003561c  mov     esi, [r15+rax*4]
0x140035620  mov     edx, esi
0x140035622  call    SdpRetrieveUuidFromStream
0x140035627  mov     eax, [rbx]
0x140035629  sub     r10d, esi
0x14003562c  mov     r12d, 10h
0x140035632  lea     edi, [r10-1]
0x140035636  test    al, 2
0x140035638  jz      short loc_1400356AA
0x14003563a  cmp     byte ptr [rbx+4], 0
0x14003563e  jz      short loc_14003566A
0x140035640  mov     r8d, r12d; Size
0x140035643  lea     rdx, L2CAP_PROTOCOL_UUID; Buf2
0x14003564a  lea     rcx, [rsp+68h+Buf1]; Buf1
0x14003564f  call    memcmp
0x140035654  test    eax, eax
0x140035656  jnz     loc_140035721
0x14003565c  test    edi, edi
0x14003565e  jnz     short loc_140035664
0x140035660  mov     byte ptr [rbx+5], 1
0x140035664  mov     byte ptr [rbx+4], 0
0x140035668  jmp     short loc_1400356AA
0x14003566a  cmp     byte ptr [rbx+5], 0
0x14003566e  jz      short loc_1400356AA
0x140035670  cmp     byte ptr [rbx+6], 0
0x140035674  jnz     short loc_1400356AA
0x140035676  mov     r8, r12; Size
0x140035679  lea     rdx, SDP_PROTOCOL_UUID; Buf2
0x140035680  lea     rcx, [rsp+68h+Buf1]; Buf1
0x140035685  call    memcmp
0x14003568a  test    eax, eax
0x14003568c  jz      short loc_1400356A6
0x14003568e  mov     r8, r12; Size
0x140035691  lea     rdx, RFCOMM_PROTOCOL_UUID; Buf2
0x140035698  lea     rcx, [rsp+68h+Buf1]; Buf1
0x14003569d  call    memcmp
0x1400356a2  test    eax, eax
0x1400356a4  jnz     short loc_140035721
0x1400356a6  mov     byte ptr [rbx+6], 1
0x1400356aa  test    edi, edi
0x1400356ac  jz      short loc_1400356EA
0x1400356ae  mov     sil, [rsi+rbp]
0x1400356b2  lea     rdx, L2CAP_PROTOCOL_UUID; Buf2
0x1400356b9  mov     dil, sil
0x1400356bc  lea     rcx, [rsp+68h+Buf1]; Buf1
0x1400356c1  mov     r8, r12; Size
0x1400356c4  shr     dil, 3
0x1400356c8  and     sil, 7
0x1400356cc  call    memcmp
0x1400356d1  test    eax, eax
0x1400356d3  jnz     short loc_1400356EE
0x1400356d5  cmp     dil, 1
0x1400356d9  jnz     short loc_140035721
0x1400356db  movzx   eax, sil
0x1400356df  cmp     dword ptr [r15+rax*4], 2
0x1400356e4  jnz     short loc_140035721
0x1400356e6  mov     [rbx+6], dil
0x1400356ea  xor     eax, eax
0x1400356ec  jmp     short loc_140035726
0x1400356ee  mov     r8, r12; Size
0x1400356f1  lea     rdx, RFCOMM_PROTOCOL_UUID; Buf2
0x1400356f8  lea     rcx, [rsp+68h+Buf1]; Buf1
0x1400356fd  call    memcmp
0x140035702  test    eax, eax
0x140035704  jnz     short loc_1400356EA
0x140035706  cmp     dil, 1
0x14003570a  jnz     short loc_140035721
0x14003570c  movzx   eax, sil
0x140035710  mov     ecx, [r15+rax*4]
0x140035714  dec     ecx
0x140035716  neg     ecx
0x140035718  sbb     eax, eax
0x14003571a  and     eax, 0C000000Dh
0x14003571f  jmp     short loc_140035726
0x140035721  mov     eax, 0C000000Dh
0x140035726  add     rsp, 38h
0x14003572a  pop     r15
0x14003572c  pop     r12
0x14003572e  pop     rdi
0x14003572f  pop     rsi
0x140035730  pop     rbp
0x140035731  pop     rbx
0x140035732  retn
```
