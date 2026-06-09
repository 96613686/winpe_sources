# PrSetPacketFilterForAdapter

- ea: `0x14000f1ac`
- end: `0x14000f34a`
- name: `PrSetPacketFilterForAdapter`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004100`
- `0x140014e68`

## callees

- `0x14000110c`
- `0x140004bb0`
- `0x140007040`
- `0x14000f1ac`

## import_xrefs

- `NDIS!NdisResetEvent` at `0x14000f28d`
- `NDIS!NdisResetEvent` at `0x14000f28d`
- `NDIS!NdisWaitEvent` at `0x14000f27e`
- `NDIS!NdisWaitEvent` at `0x14000f27e`
- `NDIS!NdisOidRequest` at `0x14000f251`
- `NDIS!NdisOidRequest` at `0x14000f251`

## pseudocode

```c
bool __fastcall PrSetPacketFilterForAdapter(__int64 a1, char a2)
{
  char v3; // bl
  NDIS_STATUS v5; // eax

  v3 = *(_BYTE *)(a1 + 24) & 0x40;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x30u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  if ( v3 )
  {
    if ( !a2 )
    {
LABEL_7:
      *(_DWORD *)(a1 + 336) = a2 != 0 ? 9 : 0;
      memset((void *)(a1 + 56), 0, 0xF0u);
      *(_DWORD *)(a1 + 60) = 1;
      *(_DWORD *)(a1 + 88) = 65806;
      *(_QWORD *)(a1 + 96) = a1 + 336;
      *(_DWORD *)(a1 + 104) = 4;
      v5 = NdisOidRequest(*(NDIS_HANDLE *)(a1 + 344), (PNDIS_OID_REQUEST)(a1 + 56));
      if ( v5 != 259 )
        PrRequestComplete(a1, a1 + 56, v5);
      NdisWaitEvent((PNDIS_EVENT)(a1 + 296), 0);
      NdisResetEvent((PNDIS_EVENT)(a1 + 296));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x33u,
          (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
      }
      return *(_DWORD *)(a1 + 48) == 0;
    }
  }
  else if ( a2 )
  {
    goto LABEL_7;
  }
  *(_DWORD *)(a1 + 48) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x31u,
        (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x32u,
        (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000f1ac  push    rbx
0x14000f1ae  push    rbp
0x14000f1af  push    rsi
0x14000f1b0  push    rdi
0x14000f1b1  push    r13
0x14000f1b3  sub     rsp, 20h
0x14000f1b7  mov     bl, [rcx+18h]
0x14000f1ba  mov     sil, dl
0x14000f1bd  and     bl, 40h
0x14000f1c0  mov     rdi, rcx
0x14000f1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1ca  lea     r13, WPP_GLOBAL_Control
0x14000f1d1  cmp     rcx, r13
0x14000f1d4  jz      short loc_14000F1F8
0x14000f1d6  mov     eax, [rcx+2Ch]
0x14000f1d9  test    al, 4
0x14000f1db  jz      short loc_14000F1F8
0x14000f1dd  cmp     byte ptr [rcx+29h], 3
0x14000f1e1  jb      short loc_14000F1F8
0x14000f1e3  mov     rcx, [rcx+18h]
0x14000f1e7  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f1ee  mov     edx, 30h ; '0'
0x14000f1f3  call    WPP_SF_
0x14000f1f8  test    bl, bl
0x14000f1fa  jz      loc_14000F2DA
0x14000f200  test    sil, sil
0x14000f203  jnz     loc_14000F2E3
0x14000f209  neg     sil
0x14000f20c  lea     rbp, [rdi+38h]
0x14000f210  lea     rbx, [rdi+150h]
0x14000f217  mov     r8d, 0F0h; Size
0x14000f21d  sbb     eax, eax
0x14000f21f  mov     rcx, rbp; void *
0x14000f222  and     eax, 9
0x14000f225  xor     edx, edx; Val
0x14000f227  mov     [rbx], eax
0x14000f229  call    memset
0x14000f22e  mov     dword ptr [rbp+4], 1
0x14000f235  mov     rdx, rbp; OidRequest
0x14000f238  mov     dword ptr [rbp+20h], 1010Eh
0x14000f23f  mov     [rbp+28h], rbx
0x14000f243  mov     dword ptr [rbp+30h], 4
0x14000f24a  mov     rcx, [rdi+158h]; NdisBindingHandle
0x14000f251  call    cs:__imp_NdisOidRequest
0x14000f258  nop     dword ptr [rax+rax+00h]
0x14000f25d  cmp     eax, 103h
0x14000f262  jz      short loc_14000F272
0x14000f264  mov     r8d, eax
0x14000f267  mov     rdx, rbp
0x14000f26a  mov     rcx, rdi
0x14000f26d  call    PrRequestComplete
0x14000f272  lea     rbx, [rdi+128h]
0x14000f279  xor     edx, edx; MsToWait
0x14000f27b  mov     rcx, rbx; Event
0x14000f27e  call    cs:__imp_NdisWaitEvent
0x14000f285  nop     dword ptr [rax+rax+00h]
0x14000f28a  mov     rcx, rbx; Event
0x14000f28d  call    cs:__imp_NdisResetEvent
0x14000f294  nop     dword ptr [rax+rax+00h]
0x14000f299  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2a0  cmp     rcx, r13
0x14000f2a3  jz      short loc_14000F2C7
0x14000f2a5  mov     eax, [rcx+2Ch]
0x14000f2a8  test    al, 4
0x14000f2aa  jz      short loc_14000F2C7
0x14000f2ac  cmp     byte ptr [rcx+29h], 3
0x14000f2b0  jb      short loc_14000F2C7
0x14000f2b2  mov     rcx, [rcx+18h]
0x14000f2b6  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f2bd  mov     edx, 33h ; '3'
0x14000f2c2  call    WPP_SF_
0x14000f2c7  cmp     dword ptr [rdi+30h], 0
0x14000f2cb  setz    al
0x14000f2ce  add     rsp, 20h
0x14000f2d2  pop     r13
0x14000f2d4  pop     rdi
0x14000f2d5  pop     rsi
0x14000f2d6  pop     rbp
0x14000f2d7  pop     rbx
0x14000f2d8  retn
0x14000f2da  test    sil, sil
0x14000f2dd  jnz     loc_14000F209
0x14000f2e3  mov     dword ptr [rdi+30h], 0
0x14000f2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2f1  cmp     rcx, r13
0x14000f2f4  jz      short loc_14000F346
0x14000f2f6  mov     eax, [rcx+2Ch]
0x14000f2f9  test    al, 4
0x14000f2fb  jz      short loc_14000F318
0x14000f2fd  cmp     byte ptr [rcx+29h], 3
0x14000f301  jb      short loc_14000F318
0x14000f303  mov     rcx, [rcx+18h]
0x14000f307  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f30e  mov     edx, 31h ; '1'
0x14000f313  call    WPP_SF_
0x14000f318  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f31f  cmp     rcx, r13
0x14000f322  jz      short loc_14000F346
0x14000f324  mov     eax, [rcx+2Ch]
0x14000f327  test    al, 4
0x14000f329  jz      short loc_14000F346
0x14000f32b  cmp     byte ptr [rcx+29h], 3
0x14000f32f  jb      short loc_14000F346
0x14000f331  mov     rcx, [rcx+18h]
0x14000f335  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f33c  mov     edx, 32h ; '2'
0x14000f341  call    WPP_SF_
0x14000f346  mov     al, 1
0x14000f348  jmp     short loc_14000F2CE
```
