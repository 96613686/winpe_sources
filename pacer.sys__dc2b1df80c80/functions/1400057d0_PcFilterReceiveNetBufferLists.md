# PcFilterReceiveNetBufferLists

- ea: `0x1400057d0`
- end: `0x140005af9`
- name: `PcFilterReceiveNetBufferLists`
- size: `809`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400039a0`
- `0x1400057d0`
- `0x140005b00`
- `0x140013110`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005a84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a84`
- `NDIS!NdisGetDataBuffer` at `0x140005941`
- `NDIS!NdisGetDataBuffer` at `0x140005941`
- `NDIS!NdisFreeMemoryWithTag` at `0x140005a4a`
- `NDIS!NdisFreeMemoryWithTag` at `0x140005a4a`
- `NDIS!NdisFreeRWLock` at `0x140005a70`
- `NDIS!NdisFreeRWLock` at `0x140005a70`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x14000586d`
- `NDIS!NdisFIndicateReceiveNetBufferLists` at `0x14000586d`
- `NDIS!NdisFReturnNetBufferLists` at `0x140005ae8`
- `NDIS!NdisFReturnNetBufferLists` at `0x140005ae8`
- `NETIO!RtlCopyBufferToMdl` at `0x140005ab5`
- `NETIO!RtlCopyBufferToMdl` at `0x140005ab5`

## pseudocode

```c
void __fastcall PcFilterReceiveNetBufferLists(
        __int64 a1,
        struct _NET_BUFFER_LIST *a2,
        NDIS_PORT_NUMBER a3,
        ULONG a4,
        ULONG ReceiveFlags)
{
  bool v5; // zf
  NDIS_PORT_NUMBER v7; // r15d
  struct _NET_BUFFER_LIST *v8; // rsi
  __int64 v9; // rbx
  struct _NET_BUFFER_LIST *v10; // rdi
  struct _NET_BUFFER_LIST *Alignment; // r12
  struct _NET_BUFFER_LIST **v12; // r15
  struct _NET_BUFFER_LIST **v13; // rbx
  struct _NET_BUFFER_LIST *v14; // r13
  unsigned __int16 *DataBuffer; // rax
  unsigned __int16 *v16; // r14
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  _QWORD *v20; // r13
  struct _NET_BUFFER_LIST *v21; // rax
  struct _NET_BUFFER_LIST *v22; // rax
  void *v23; // rcx
  __int64 v24; // rcx
  struct _NDIS_RW_LOCK_EX *v25; // rcx
  struct _NET_BUFFER_LIST *v27; // [rsp+38h] [rbp-C0h]
  struct _NET_BUFFER_LIST **p_Next; // [rsp+40h] [rbp-B8h]
  struct _NET_BUFFER *FirstNetBuffer; // [rsp+68h] [rbp-90h]
  __int64 v30; // [rsp+70h] [rbp-88h] BYREF
  __int64 v31; // [rsp+78h] [rbp-80h]
  __int128 v32; // [rsp+80h] [rbp-78h]
  __int64 Storage; // [rsp+98h] [rbp-60h] BYREF
  int v34; // [rsp+A0h] [rbp-58h]
  __int16 v35; // [rsp+A4h] [rbp-54h]

  v5 = *(_DWORD *)(a1 + 24) == 2;
  v7 = a3;
  v31 = a1;
  v8 = a2;
  v9 = a1;
  v32 = 0;
  if ( !v5 )
  {
    v10 = 0;
    a4 = 0;
    goto LABEL_3;
  }
  if ( *(_DWORD *)(a1 + 16) != 3 || *(_WORD *)(a1 + 212) != 2048 )
  {
    v8 = (struct _NET_BUFFER_LIST *)v32;
    v10 = a2;
    goto LABEL_3;
  }
  a4 = 0;
  Alignment = a2;
  v10 = 0;
  v8 = (struct _NET_BUFFER_LIST *)v32;
  if ( a2 )
  {
    v12 = 0;
    v13 = (struct _NET_BUFFER_LIST **)*((_QWORD *)&v32 + 1);
    while ( 1 )
    {
      v30 = 0;
      p_Next = &Alignment->Next;
      v14 = Alignment;
      v27 = Alignment;
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      *p_Next = 0;
      Storage = 0;
      v34 = 0;
      v35 = 0;
      FirstNetBuffer = v14->FirstNetBuffer;
      DataBuffer = (unsigned __int16 *)NdisGetDataBuffer(FirstNetBuffer, 0xEu, &Storage, 2u, 0);
      v16 = DataBuffer;
      if ( !DataBuffer )
        goto LABEL_25;
      v17 = PcpLineLookupById(*DataBuffer);
      v20 = (_QWORD *)v17;
      if ( !v17 )
        break;
      *(_DWORD *)v16 = *(_DWORD *)(v17 + 334);
      v16[2] = *(_WORD *)(v17 + 338);
      v16[3] = *(_WORD *)(v17 + 240);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 248), 0xFFFFFFFF) == 1 )
      {
        v23 = *(void **)(v17 + 320);
        if ( v23 )
          NdisFreeMemoryWithTag(v23, 0x616E6350u);
        v24 = v20[32];
        if ( v24 )
          PcpFilterDecrementDetachCount(v24, v18, v19);
        v25 = (struct _NDIS_RW_LOCK_EX *)v20[2];
        if ( v25 )
          NdisFreeRWLock(v25);
        ExFreePoolWithTag(v20, 0x656C6350u);
      }
      if ( v16 == (unsigned __int16 *)&Storage )
        RtlCopyBufferToMdl(v16, FirstNetBuffer->Link.Region, FirstNetBuffer->CurrentMdlOffset, 12, &v30);
      if ( v12 )
      {
        v21 = *v12;
        *v12 = v27;
      }
      else
      {
        v21 = v10;
        v10 = v27;
      }
      *p_Next = v21;
      if ( !v21 )
        v12 = &v27->Next;
      ++a4;
LABEL_21:
      if ( !Alignment )
      {
        v9 = v31;
        v7 = a3;
        goto LABEL_3;
      }
    }
    v14 = v27;
LABEL_25:
    if ( v13 )
    {
      v22 = *v13;
      *v13 = v14;
    }
    else
    {
      v22 = v8;
      v8 = v14;
    }
    *p_Next = v22;
    if ( !v22 )
      v13 = &v14->Next;
    goto LABEL_21;
  }
LABEL_3:
  if ( v8 && (ReceiveFlags & 2) == 0 )
    NdisFReturnNetBufferLists(*(NDIS_HANDLE *)(v9 + 40), v8, ReceiveFlags & 1);
  if ( v10 )
    NdisFIndicateReceiveNetBufferLists(*(NDIS_HANDLE *)(v9 + 40), v10, v7, a4, ReceiveFlags);
}

```

## disassembly

```asm
0x1400057d0  mov     r11, rsp
0x1400057d3  push    rbx
0x1400057d4  push    rbp
0x1400057d5  push    rdi
0x1400057d6  push    r14
0x1400057d8  push    r15
0x1400057da  sub     rsp, 0D0h
0x1400057e1  mov     rax, cs:__security_cookie
0x1400057e8  xor     rax, rsp
0x1400057eb  mov     [rsp+0F8h+var_50], rax
0x1400057f3  xor     eax, eax
0x1400057f5  mov     [r11-30h], rsi
0x1400057f9  cmp     dword ptr [rcx+18h], 2
0x1400057fd  xorps   xmm0, xmm0
0x140005800  xorps   xmm1, xmm1
0x140005803  mov     [r11-38h], r12
0x140005807  mov     ebp, r9d
0x14000580a  mov     [rsp+0F8h+var_C8], r8d
0x14000580f  mov     r15d, r8d
0x140005812  mov     [rsp+0F8h+var_80], rcx
0x140005817  mov     rsi, rdx
0x14000581a  mov     [rsp+0F8h+var_A0], rax
0x14000581f  mov     rbx, rcx
0x140005822  movups  xmmword ptr [rsp+0F8h+NetBufferLists], xmm0
0x140005827  movups  xmmword ptr [r11-78h], xmm1
0x14000582c  jz      short loc_140005899
0x14000582e  mov     rdi, [rsp+0F8h+NetBufferLists]
0x140005833  mov     ebp, eax
0x140005835  mov     r14d, [rsp+0F8h+arg_20]
0x14000583d  mov     r12, [rsp+0F8h+var_38]
0x140005845  test    rsi, rsi
0x140005848  jnz     loc_140005AD0
0x14000584e  mov     rsi, [rsp+0F8h+var_30]
0x140005856  test    rdi, rdi
0x140005859  jz      short loc_140005879
0x14000585b  mov     rcx, [rbx+28h]; NdisFilterHandle
0x14000585f  mov     r9d, ebp; NumberOfNetBufferLists
0x140005862  mov     r8d, r15d; PortNumber
0x140005865  mov     [rsp+0F8h+ReceiveFlags], r14d; ReceiveFlags
0x14000586a  mov     rdx, rdi; NetBufferLists
0x14000586d  call    cs:__imp_NdisFIndicateReceiveNetBufferLists
0x140005874  nop     dword ptr [rax+rax+00h]
0x140005879  mov     rcx, [rsp+0F8h+var_50]
0x140005881  xor     rcx, rsp; StackCookie
0x140005884  call    __security_check_cookie
0x140005889  add     rsp, 0D0h
0x140005890  pop     r15
0x140005892  pop     r14
0x140005894  pop     rdi
0x140005895  pop     rbp
0x140005896  pop     rbx
0x140005897  retn
0x140005899  cmp     dword ptr [rcx+10h], 3
0x14000589d  jnz     loc_140005A04
0x1400058a3  mov     eax, 800h
0x1400058a8  cmp     [rcx+0D4h], ax
0x1400058af  jnz     loc_140005A04
0x1400058b5  mov     ebp, dword ptr [rsp+0F8h+var_A0]
0x1400058b9  mov     r12, rdx
0x1400058bc  mov     rdi, [rsp+0F8h+NetBufferLists]
0x1400058c1  mov     rsi, [rsp+0F8h+var_78]
0x1400058c9  test    rdx, rdx
0x1400058cc  jz      loc_140005835
0x1400058d2  mov     r15, [rsp+0F8h+NetBufferLists+8]
0x1400058d7  xor     ecx, ecx
0x1400058d9  mov     rbx, [rsp+0F8h+var_70]
0x1400058e1  mov     [rsp+0F8h+var_40], r13
0x1400058e9  mov     rax, r12
0x1400058ec  mov     [rsp+0F8h+var_88], rcx
0x1400058f1  mov     [rsp+0F8h+var_B8], rax
0x1400058f6  lea     r8, [rsp+0F8h+Storage]; Storage
0x1400058fe  mov     r13, r12
0x140005901  mov     [rsp+0F8h+ReceiveFlags], ecx; AlignOffset
0x140005905  mov     [rsp+0F8h+var_C0], r12
0x14000590a  mov     r9d, 2; AlignMultiple
0x140005910  mov     r12, [r12]
0x140005914  mov     edx, 0Eh; BytesNeeded
0x140005919  mov     [rax], rcx
0x14000591c  xor     eax, eax
0x14000591e  mov     [rsp+0F8h+Storage], rax
0x140005926  mov     [rsp+0F8h+var_58], eax
0x14000592d  mov     [rsp+0F8h+var_54], ax
0x140005935  mov     rax, [r13+8]
0x140005939  mov     rcx, rax; NetBuffer
0x14000593c  mov     [rsp+0F8h+var_90], rax
0x140005941  call    cs:__imp_NdisGetDataBuffer
0x140005948  nop     dword ptr [rax+rax+00h]
0x14000594d  mov     r14, rax
0x140005950  test    rax, rax
0x140005953  jz      loc_140005A14
0x140005959  movzx   ecx, word ptr [rax]
0x14000595c  call    PcpLineLookupById
0x140005961  mov     r13, rax
0x140005964  test    rax, rax
0x140005967  jz      loc_140005AC6
0x14000596d  mov     ecx, [rax+14Eh]
0x140005973  mov     [r14], ecx
0x140005976  movzx   ecx, word ptr [rax+152h]
0x14000597d  mov     [r14+4], cx
0x140005982  movzx   ecx, word ptr [rax+0F0h]
0x140005989  mov     [r14+6], cx
0x14000598e  mov     ecx, 0FFFFFFFFh
0x140005993  lock xadd [rax+0F8h], ecx
0x14000599b  cmp     ecx, 1
0x14000599e  jz      loc_140005A39
0x1400059a4  lea     rax, [rsp+0F8h+Storage]
0x1400059ac  cmp     r14, rax
0x1400059af  jz      loc_140005A95
0x1400059b5  mov     rcx, [rsp+0F8h+var_C0]
0x1400059ba  test    r15, r15
0x1400059bd  jnz     short loc_1400059FC
0x1400059bf  mov     rax, rdi
0x1400059c2  mov     rdi, rcx
0x1400059c5  mov     rdx, [rsp+0F8h+var_B8]
0x1400059ca  mov     [rdx], rax
0x1400059cd  test    rax, rax
0x1400059d0  jnz     short loc_1400059D5
0x1400059d2  mov     r15, rcx
0x1400059d5  inc     ebp
0x1400059d7  mov     ecx, 0
0x1400059dc  test    r12, r12
0x1400059df  jnz     loc_1400058E9
0x1400059e5  mov     r13, [rsp+0F8h+var_40]
0x1400059ed  mov     rbx, [rsp+0F8h+var_80]
0x1400059f2  mov     r15d, [rsp+0F8h+var_C8]
0x1400059f7  jmp     loc_140005835
0x1400059fc  mov     rax, [r15]
0x1400059ff  mov     [r15], rcx
0x140005a02  jmp     short loc_1400059C5
0x140005a04  mov     rsi, [rsp+0F8h+var_78]
0x140005a0c  mov     rdi, rdx
0x140005a0f  jmp     loc_140005835
0x140005a14  test    rbx, rbx
0x140005a17  jnz     short loc_140005A31
0x140005a19  mov     rax, rsi
0x140005a1c  mov     rsi, r13
0x140005a1f  mov     rdx, [rsp+0F8h+var_B8]
0x140005a24  mov     [rdx], rax
0x140005a27  test    rax, rax
0x140005a2a  jnz     short loc_1400059D7
0x140005a2c  mov     rbx, r13
0x140005a2f  jmp     short loc_1400059D7
0x140005a31  mov     rax, [rbx]
0x140005a34  mov     [rbx], r13
0x140005a37  jmp     short loc_140005A1F
0x140005a39  mov     rcx, [rax+140h]; VirtualAddress
0x140005a40  test    rcx, rcx
0x140005a43  jz      short loc_140005A56
0x140005a45  mov     edx, 616E6350h; Tag
0x140005a4a  call    cs:__imp_NdisFreeMemoryWithTag
0x140005a51  nop     dword ptr [rax+rax+00h]
0x140005a56  mov     rcx, [r13+100h]
0x140005a5d  test    rcx, rcx
0x140005a60  jz      short loc_140005A67
0x140005a62  call    PcpFilterDecrementDetachCount
0x140005a67  mov     rcx, [r13+10h]; Lock
0x140005a6b  test    rcx, rcx
0x140005a6e  jz      short loc_140005A7C
0x140005a70  call    cs:__imp_NdisFreeRWLock
0x140005a77  nop     dword ptr [rax+rax+00h]
0x140005a7c  mov     edx, 656C6350h; Tag
0x140005a81  mov     rcx, r13; P
0x140005a84  call    cs:__imp_ExFreePoolWithTag
0x140005a8b  nop     dword ptr [rax+rax+00h]
0x140005a90  jmp     loc_1400059A4
0x140005a95  mov     rdx, [rsp+0F8h+var_90]
0x140005a9a  lea     rax, [rsp+0F8h+var_88]
0x140005a9f  mov     r9d, 0Ch
0x140005aa5  mov     qword ptr [rsp+0F8h+ReceiveFlags], rax
0x140005aaa  mov     rcx, r14
0x140005aad  mov     r8d, [rdx+10h]
0x140005ab1  mov     rdx, [rdx+8]
0x140005ab5  call    cs:__imp_RtlCopyBufferToMdl
0x140005abc  nop     dword ptr [rax+rax+00h]
0x140005ac1  jmp     loc_1400059B5
0x140005ac6  mov     r13, [rsp+0F8h+var_C0]
0x140005acb  jmp     loc_140005A14
0x140005ad0  test    r14b, 2
0x140005ad4  jnz     loc_14000584E
0x140005ada  mov     rcx, [rbx+28h]; NdisFilterHandle
0x140005ade  mov     r8d, r14d
0x140005ae1  and     r8d, 1; ReturnFlags
0x140005ae5  mov     rdx, rsi; NetBufferLists
0x140005ae8  call    cs:__imp_NdisFReturnNetBufferLists
0x140005aef  nop     dword ptr [rax+rax+00h]
0x140005af4  jmp     loc_14000584E
```
