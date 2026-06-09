# UlAddUrlToUrlGroupIoctl

- ea: `0x1c00a0c20`
- end: `0x1c00a0e2f`
- name: `UlAddUrlToUrlGroupIoctl`
- size: `527`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1c0001008`
- `0x1c0001038`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c00a0b70`
- `0x1c00a0c20`
- `0x1c00a133c`
- `0x1c00a14ac`
- `0x1c00a1960`

## import_xrefs

- `ntoskrnl!SeCreateAccessState` at `0x1c00a0d99`
- `ntoskrnl!SeCreateAccessState` at `0x1c00a0d99`
- `ntoskrnl!SeDeleteAccessState` at `0x1c00a0dd3`
- `ntoskrnl!SeDeleteAccessState` at `0x1c00a0dd3`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00a0cd4`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00a0cd4`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x1c00dd299`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x1c00dd299`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1c00a0d58`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1c00a0d58`

## pseudocode

```c
__int64 __fastcall UlAddUrlToUrlGroupIoctl(PIRP Irp, __int64 a2)
{
  unsigned int v4; // r14d
  int CommChannel; // ebx
  BOOLEAN v6; // r15
  __int64 v7; // rdx
  _DWORD *v8; // rsi
  int ThreadObjectCompartmentId; // r15d
  bool v10; // zf
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h]
  _QWORD v16[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[160]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v18[224]; // [rsp+140h] [rbp+40h] BYREF

  v15 = 0;
  v14 = 0;
  memset(v17, 0, sizeof(v17));
  memset(v18, 0, sizeof(v18));
  v13 = 0;
  v4 = 0;
  memset(v16, 0, sizeof(v16));
  v12 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qq(44, WPP_18ca8755388c316524f95a91261e2540_Traceguids, Irp, a2);
  CommChannel = UlGetCommChannel(a2, &v13);
  if ( CommChannel >= 0 )
  {
    v6 = IoIs32bitProcess(Irp);
    CommChannel = UxGetInputBuffer(Irp, a2, v6 != 0 ? 48 : 64, &v12);
    if ( CommChannel >= 0 )
    {
      if ( v6 )
      {
        v8 = v16;
        LODWORD(v16[0]) = *(_DWORD *)v12;
        v16[1] = *(_QWORD *)(v12 + 8);
        v16[2] = *(_QWORD *)(v12 + 16);
        LODWORD(v16[3]) = *(_DWORD *)(v12 + 24);
        v16[4] = *(unsigned int *)(v12 + 28);
        LODWORD(v16[5]) = *(_DWORD *)(v12 + 32);
        v16[6] = *(unsigned int *)(v12 + 36);
        LODWORD(v16[7]) = *(_DWORD *)(v12 + 40);
      }
      else
      {
        v8 = (_DWORD *)v12;
      }
      LOBYTE(v7) = Irp->RequestorMode;
      CommChannel = UxCaptureUnicodeString(v8 + 10, v7, &v14);
      if ( CommChannel >= 0 )
      {
        if ( !(_WORD)v14 )
        {
          CommChannel = -1073741811;
          goto LABEL_16;
        }
        if ( *v8 == 1 )
        {
          v4 = 1;
          ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
          if ( *(_BYTE *)(*(_QWORD *)(v13 + 56) + 79LL) )
            v10 = ThreadObjectCompartmentId == 1;
          else
            v10 = ThreadObjectCompartmentId == (unsigned int)NdisGetJobObjectCompartmentId(*(_QWORD *)(v13 + 48));
          if ( !v10 )
          {
            CommChannel = -1073741637;
            goto LABEL_16;
          }
        }
        else if ( *v8 )
        {
          CommChannel = -1073741811;
        }
        else
        {
          v4 = 2;
        }
        if ( CommChannel >= 0 )
        {
          CommChannel = SeCreateAccessState(v17, v18, v4, &g_UrlAccessGenericMapping);
          if ( CommChannel >= 0 )
          {
            CommChannel = UlAddUrlToConfigGroup(
                            v13,
                            (_DWORD)v8,
                            (unsigned int)&v14,
                            (unsigned int)v17,
                            v4,
                            Irp->RequestorMode);
            SeDeleteAccessState(v17);
          }
        }
      }
    }
  }
LABEL_16:
  UxFreeCapturedUnicodeString(&v14);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(45, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
  return UxCompleteIrpForReturn(Irp, (unsigned int)CommChannel);
}

```

## disassembly

```asm
0x1c00a0c20  mov     [rsp-8+arg_10], rbx
0x1c00a0c25  mov     [rsp-8+arg_18], rsi
0x1c00a0c2a  push    rbp
0x1c00a0c2b  push    rdi
0x1c00a0c2c  push    r12
0x1c00a0c2e  push    r14
0x1c00a0c30  push    r15
0x1c00a0c32  lea     rbp, [rsp-130h]
0x1c00a0c3a  sub     rsp, 230h
0x1c00a0c41  mov     rax, cs:__security_cookie
0x1c00a0c48  xor     rax, rsp
0x1c00a0c4b  mov     [rbp+150h+var_30], rax
0x1c00a0c52  mov     rsi, rdx
0x1c00a0c55  mov     rdi, rcx
0x1c00a0c58  xorps   xmm0, xmm0
0x1c00a0c5b  lea     rcx, [rbp+150h+var_1B0]; void *
0x1c00a0c5f  xor     eax, eax
0x1c00a0c61  xor     edx, edx; Val
0x1c00a0c63  mov     r8d, 0A0h; Size
0x1c00a0c69  mov     [rsp+250h+var_200], rax
0x1c00a0c6e  movups  [rsp+250h+var_210], xmm0
0x1c00a0c73  call    memset
0x1c00a0c78  xor     edx, edx; Val
0x1c00a0c7a  lea     rcx, [rbp+150h+var_110]; void *
0x1c00a0c7e  mov     r8d, 0E0h; Size
0x1c00a0c84  call    memset
0x1c00a0c89  xor     r12d, r12d
0x1c00a0c8c  lea     rcx, [rsp+250h+var_1F0]; void *
0x1c00a0c91  xor     edx, edx; Val
0x1c00a0c93  mov     [rsp+250h+var_218], r12
0x1c00a0c98  mov     r14d, r12d
0x1c00a0c9b  lea     r8d, [r12+40h]; Size
0x1c00a0ca0  call    memset
0x1c00a0ca5  mov     [rsp+250h+var_220], r12
0x1c00a0caa  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00a0cb4  jnz     loc_1C00DD212
0x1c00a0cba  lea     rdx, [rsp+250h+var_218]
0x1c00a0cbf  mov     rcx, rsi
0x1c00a0cc2  call    UlGetCommChannel
0x1c00a0cc7  mov     ebx, eax
0x1c00a0cc9  test    eax, eax
0x1c00a0ccb  js      loc_1C00A0DDF
0x1c00a0cd1  mov     rcx, rdi; Irp
0x1c00a0cd4  call    cs:__imp_IoIs32bitProcess
0x1c00a0cdb  nop     dword ptr [rax+rax+00h]
0x1c00a0ce0  lea     r9, [rsp+250h+var_220]
0x1c00a0ce5  mov     rdx, rsi
0x1c00a0ce8  mov     cl, al
0x1c00a0cea  mov     r15b, al
0x1c00a0ced  neg     cl
0x1c00a0cef  mov     rcx, rdi
0x1c00a0cf2  sbb     r8d, r8d
0x1c00a0cf5  and     r8d, 0FFFFFFF0h
0x1c00a0cf9  add     r8d, 40h ; '@'
0x1c00a0cfd  call    UxGetInputBuffer
0x1c00a0d02  mov     ebx, eax
0x1c00a0d04  test    eax, eax
0x1c00a0d06  js      loc_1C00A0DDF
0x1c00a0d0c  test    r15b, r15b
0x1c00a0d0f  jnz     loc_1C00DD22F
0x1c00a0d15  mov     rsi, [rsp+250h+var_220]
0x1c00a0d1a  mov     dl, [rdi+40h]
0x1c00a0d1d  lea     rcx, [rsi+28h]
0x1c00a0d21  lea     r8, [rsp+250h+var_210]
0x1c00a0d26  call    UxCaptureUnicodeString
0x1c00a0d2b  mov     ebx, eax
0x1c00a0d2d  test    eax, eax
0x1c00a0d2f  js      loc_1C00A0DDF
0x1c00a0d35  cmp     word ptr [rsp+250h+var_210], r12w
0x1c00a0d3b  jz      loc_1C00DD281
0x1c00a0d41  mov     eax, [rsi]
0x1c00a0d43  cmp     eax, 1
0x1c00a0d46  jnz     loc_1C00DD2AD
0x1c00a0d4c  mov     rcx, gs:188h
0x1c00a0d55  mov     r14d, eax
0x1c00a0d58  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1c00a0d5f  nop     dword ptr [rax+rax+00h]
0x1c00a0d64  mov     r15d, eax
0x1c00a0d67  mov     rax, [rsp+250h+var_218]
0x1c00a0d6c  mov     rcx, [rax+38h]
0x1c00a0d70  cmp     [rcx+4Fh], r12b
0x1c00a0d74  jz      loc_1C00DD295
0x1c00a0d7a  cmp     r15d, r14d
0x1c00a0d7d  jnz     loc_1C00DD28B
0x1c00a0d83  test    ebx, ebx
0x1c00a0d85  js      short loc_1C00A0DDF
0x1c00a0d87  lea     r9, g_UrlAccessGenericMapping
0x1c00a0d8e  mov     r8d, r14d
0x1c00a0d91  lea     rdx, [rbp+150h+var_110]
0x1c00a0d95  lea     rcx, [rbp+150h+var_1B0]
0x1c00a0d99  call    cs:__imp_SeCreateAccessState
0x1c00a0da0  nop     dword ptr [rax+rax+00h]
0x1c00a0da5  mov     ebx, eax
0x1c00a0da7  test    eax, eax
0x1c00a0da9  js      short loc_1C00A0DDF
0x1c00a0dab  mov     al, [rdi+40h]
0x1c00a0dae  lea     r9, [rbp+150h+var_1B0]
0x1c00a0db2  mov     rcx, [rsp+250h+var_218]
0x1c00a0db7  lea     r8, [rsp+250h+var_210]
0x1c00a0dbc  mov     [rsp+250h+var_228], al
0x1c00a0dc0  mov     rdx, rsi
0x1c00a0dc3  mov     [rsp+250h+var_230], r14d
0x1c00a0dc8  call    UlAddUrlToConfigGroup
0x1c00a0dcd  mov     ebx, eax
0x1c00a0dcf  lea     rcx, [rbp+150h+var_1B0]
0x1c00a0dd3  call    cs:__imp_SeDeleteAccessState
0x1c00a0dda  nop     dword ptr [rax+rax+00h]
0x1c00a0ddf  lea     rcx, [rsp+250h+var_210]
0x1c00a0de4  call    UxFreeCapturedUnicodeString
0x1c00a0de9  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00a0df3  jnz     loc_1C00DD2C4
0x1c00a0df9  mov     edx, ebx
0x1c00a0dfb  mov     rcx, rdi
0x1c00a0dfe  call    UxCompleteIrpForReturn
0x1c00a0e03  mov     rcx, [rbp+150h+var_30]
0x1c00a0e0a  xor     rcx, rsp; StackCookie
0x1c00a0e0d  call    __security_check_cookie
0x1c00a0e12  lea     r11, [rsp+250h+var_20]
0x1c00a0e1a  mov     rbx, [r11+40h]
0x1c00a0e1e  mov     rsi, [r11+48h]
0x1c00a0e22  mov     rsp, r11
0x1c00a0e25  pop     r15
0x1c00a0e27  pop     r14
0x1c00a0e29  pop     r12
0x1c00a0e2b  pop     rdi
0x1c00a0e2c  pop     rbp
0x1c00a0e2d  retn
0x1c00dd212  mov     ecx, 2Ch ; ','
0x1c00dd217  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00dd21e  mov     r9, rsi
0x1c00dd221  mov     r8, rdi
0x1c00dd224  call    WPP_SF_qq
0x1c00dd229  nop
0x1c00dd22a  jmp     loc_1C00A0CBA
0x1c00dd22f  mov     rcx, [rsp+250h+var_220]
0x1c00dd234  lea     rsi, [rsp+250h+var_1F0]
0x1c00dd239  mov     eax, [rcx]
0x1c00dd23b  mov     [rsp+250h+var_1F0], eax
0x1c00dd23f  mov     rax, [rcx+8]
0x1c00dd243  mov     [rsp+250h+var_1E8], rax
0x1c00dd248  mov     rax, [rcx+10h]
0x1c00dd24c  mov     [rsp+250h+var_1E0], rax
0x1c00dd251  mov     eax, [rcx+18h]
0x1c00dd254  mov     [rsp+250h+var_1D8], eax
0x1c00dd258  mov     eax, [rcx+1Ch]
0x1c00dd25b  mov     [rbp+150h+var_1D0], rax
0x1c00dd25f  movzx   eax, word ptr [rcx+20h]
0x1c00dd263  mov     [rbp+150h+var_1C8], ax
0x1c00dd267  movzx   eax, word ptr [rcx+22h]
0x1c00dd26b  mov     [rbp+150h+var_1C6], ax
0x1c00dd26f  mov     eax, [rcx+24h]
0x1c00dd272  mov     [rbp+150h+var_1C0], rax
0x1c00dd276  mov     eax, [rcx+28h]
0x1c00dd279  mov     [rbp+150h+var_1B8], eax
0x1c00dd27c  jmp     loc_1C00A0D1A
0x1c00dd281  mov     ebx, 0C000000Dh
0x1c00dd286  jmp     loc_1C00A0DDF
0x1c00dd28b  mov     ebx, 0C00000BBh
0x1c00dd290  jmp     loc_1C00A0DDF
0x1c00dd295  mov     rcx, [rax+30h]
0x1c00dd299  call    cs:__imp_NdisGetJobObjectCompartmentId
0x1c00dd2a0  nop     dword ptr [rax+rax+00h]
0x1c00dd2a5  cmp     r15d, eax
0x1c00dd2a8  jmp     loc_1C00A0D7D
0x1c00dd2ad  test    eax, eax
0x1c00dd2af  jnz     short loc_1C00DD2BA
0x1c00dd2b1  lea     r14d, [rax+2]
0x1c00dd2b5  jmp     loc_1C00A0D83
0x1c00dd2ba  mov     ebx, 0C000000Dh
0x1c00dd2bf  jmp     loc_1C00A0D83
0x1c00dd2c4  mov     ecx, 2Dh ; '-'
0x1c00dd2c9  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00dd2d0  mov     r8d, ebx
0x1c00dd2d3  call    WPP_SF_D
0x1c00dd2d8  nop
0x1c00dd2d9  jmp     loc_1C00A0DF9
```
