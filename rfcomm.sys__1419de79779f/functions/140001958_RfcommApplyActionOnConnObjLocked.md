# RfcommApplyActionOnConnObjLocked

- ea: `0x140001958`
- end: `0x140001b29`
- name: `RfcommApplyActionOnConnObjLocked`
- size: `465`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000280c`
- `0x140002ac8`

## callees

- `0x140001958`
- `0x140003bf4`
- `0x140004a68`
- `0x140004b4c`
- `0x140004d30`
- `0x14001e74c`

## string_xrefs

- `0x140001b0f`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
__int64 *__fastcall RfcommApplyActionOnConnObjLocked(__int64 a1, int *a2, int a3, int a4)
{
  __int64 *v4; // r15
  __int64 *v6; // rbx
  _UNKNOWN **v7; // rdx
  __int64 v9; // rdi
  int v10; // r14d
  int v11; // r12d
  __int64 v12; // r13
  int v14; // ebp
  int v15; // r9d
  int v16; // [rsp+20h] [rbp-78h]

  v4 = (__int64 *)(a1 + 96);
  v6 = *(__int64 **)(a1 + 96);
  v7 = &WPP_RECORDER_INITIALIZED;
  LOBYTE(v9) = 0;
  while ( v6 != v4 )
  {
    if ( a3 != 2 || *((_DWORD *)v6 + 20) == 2 )
    {
      v10 = *a2;
      v11 = *((_DWORD *)v6 + 206);
      v12 = *(__int64 *)((char *)v6 + 116);
      if ( *a2 == 1 )
      {
        v9 = v6[13];
        if ( v9 )
          LOBYTE(v9) = *(_BYTE *)(v9 + 112);
      }
      else if ( *a2 == 2 || *a2 == 4 )
      {
        LOBYTE(v9) = *((_BYTE *)v6 + 140);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_qdDid(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          a3,
          a4,
          v16,
          (char)v6,
          v10,
          v11,
          v12,
          v9);
        v7 = &WPP_RECORDER_INITIALIZED;
      }
      if ( v10 == *a2 && v11 == a2[1] && v12 == *((_QWORD *)a2 + 1) && (_BYTE)v9 == *((_BYTE *)a2 + 16) )
      {
        v14 = a3 - 1;
        if ( v14 )
        {
          if ( v14 == 1 )
          {
            *((_BYTE *)v6 + 829) = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v15 = 60;
              goto LABEL_27;
            }
LABEL_30:
            RefObj_AddRefEx(v6 + 3, 541672532, 1298, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
            return v6;
          }
        }
        else
        {
          *((_BYTE *)v6 + 829) = 1;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_30;
          v15 = 59;
LABEL_27:
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            (unsigned int)&WPP_RECORDER_INITIALIZED,
            19,
            v15,
            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
            v6);
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v7,
            19,
            61,
            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
            (char)v6,
            *((_DWORD *)v6 + 6) + 1);
        goto LABEL_30;
      }
    }
    v6 = (__int64 *)*v6;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      19,
      58,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140001958  push    rbx
0x14000195a  push    rbp
0x14000195b  push    rsi
0x14000195c  push    rdi
0x14000195d  push    r12
0x14000195f  push    r13
0x140001961  push    r14
0x140001963  push    r15
0x140001965  sub     rsp, 58h
0x140001969  lea     r15, [rcx+60h]
0x14000196d  mov     rsi, rdx
0x140001970  mov     rbx, [r15]
0x140001973  lea     rdx, WPP_RECORDER_INITIALIZED
0x14000197a  mov     ebp, r8d
0x14000197d  xor     dil, dil
0x140001980  jmp     loc_140001A1F
0x140001985  cmp     ebp, 2
0x140001988  jnz     short loc_140001993
0x14000198a  cmp     [rbx+50h], ebp
0x14000198d  jnz     loc_140001A1C
0x140001993  mov     r14d, [rsi]
0x140001996  mov     ecx, r14d
0x140001999  mov     r12d, [rbx+338h]
0x1400019a0  mov     r13, [rbx+74h]
0x1400019a4  sub     ecx, 1
0x1400019a7  jz      short loc_1400019BC
0x1400019a9  sub     ecx, 1
0x1400019ac  jz      short loc_1400019B3
0x1400019ae  cmp     ecx, 2
0x1400019b1  jnz     short loc_1400019C9
0x1400019b3  mov     dil, [rbx+8Ch]
0x1400019ba  jmp     short loc_1400019C9
0x1400019bc  mov     rdi, [rbx+68h]
0x1400019c0  test    rdi, rdi
0x1400019c3  jz      short loc_1400019C9
0x1400019c5  mov     dil, [rdi+70h]
0x1400019c9  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400019d0  jz      short loc_140001A05
0x1400019d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019d9  movzx   eax, dil
0x1400019dd  mov     [rsp+98h+var_50], eax
0x1400019e1  mov     [rsp+98h+var_58], r13
0x1400019e6  mov     rcx, [rcx+40h]
0x1400019ea  mov     [rsp+98h+var_60], r12d
0x1400019ef  mov     [rsp+98h+var_68], r14d
0x1400019f4  mov     [rsp+98h+var_70], rbx
0x1400019f9  call    WPP_RECORDER_SF_qdDid
0x1400019fe  lea     rdx, WPP_RECORDER_INITIALIZED
0x140001a05  cmp     r14d, [rsi]
0x140001a08  jnz     short loc_140001A1C
0x140001a0a  cmp     r12d, [rsi+4]
0x140001a0e  jnz     short loc_140001A1C
0x140001a10  cmp     r13, [rsi+8]
0x140001a14  jnz     short loc_140001A1C
0x140001a16  cmp     dil, [rsi+10h]
0x140001a1a  jz      short loc_140001A6B
0x140001a1c  mov     rbx, [rbx]
0x140001a1f  cmp     rbx, r15
0x140001a22  jnz     loc_140001985
0x140001a28  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140001a2f  jz      short loc_140001A57
0x140001a31  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a38  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001a3f  mov     r9d, 3Ah ; ':'
0x140001a45  mov     [rsp+98h+var_78], rsi
0x140001a4a  mov     rcx, [rcx+40h]
0x140001a4e  lea     r8d, [r9-27h]
0x140001a52  call    WPP_RECORDER_SF_
0x140001a57  xor     eax, eax
0x140001a59  add     rsp, 58h
0x140001a5d  pop     r15
0x140001a5f  pop     r14
0x140001a61  pop     r13
0x140001a63  pop     r12
0x140001a65  pop     rdi
0x140001a66  pop     rsi
0x140001a67  pop     rbp
0x140001a68  pop     rbx
0x140001a69  retn
0x140001a6b  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001a72  mov     edi, 13h
0x140001a77  sub     ebp, 1
0x140001a7a  jz      short loc_140001A97
0x140001a7c  cmp     ebp, 1
0x140001a7f  jnz     short loc_140001ACA
0x140001a81  mov     byte ptr [rbx+33Dh], 0
0x140001a88  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140001a8f  jz      short loc_140001B06
0x140001a91  lea     r9d, [rdi+29h]
0x140001a95  jmp     short loc_140001AAD
0x140001a97  mov     byte ptr [rbx+33Dh], 1
0x140001a9e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140001aa5  jz      short loc_140001B06
0x140001aa7  mov     r9d, 3Bh ; ';'
0x140001aad  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ab4  mov     r8d, edi
0x140001ab7  mov     [rsp+98h+var_70], rbx
0x140001abc  mov     [rsp+98h+var_78], rsi
0x140001ac1  mov     rcx, [rcx+40h]
0x140001ac5  call    WPP_RECORDER_SF_q
0x140001aca  lea     rax, WPP_RECORDER_INITIALIZED
0x140001ad1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001ad8  jz      short loc_140001B06
0x140001ada  mov     eax, [rbx+18h]
0x140001add  mov     r9d, 3Dh ; '='
0x140001ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001aea  inc     eax
0x140001aec  mov     [rsp+98h+var_68], eax
0x140001af0  mov     r8d, edi
0x140001af3  mov     [rsp+98h+var_70], rbx
0x140001af8  mov     [rsp+98h+var_78], rsi
0x140001afd  mov     rcx, [rcx+40h]
0x140001b01  call    WPP_RECORDER_SF_qD
0x140001b06  lea     rcx, [rbx+18h]
0x140001b0a  mov     edx, 20494454h
0x140001b0f  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140001b16  mov     r8d, 512h
0x140001b1c  call    RefObj_AddRefEx
0x140001b21  mov     rax, rbx
0x140001b24  jmp     loc_140001A59
```
