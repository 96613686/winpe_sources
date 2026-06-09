# EapHandlePeapTLV

- ea: `0x180017b60`
- end: `0x180017f5f`
- name: `EapHandlePeapTLV`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e100`

## callees

- `0x180007f60`
- `0x180010ae0`
- `0x180014190`
- `0x180017b60`
- `0x1800266f8`
- `0x180027494`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x180017dae`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180017dae`
- `MobileNetworking!AllocateMemory` at `0x180017ce1`
- `MobileNetworking!AllocateMemory` at `0x180017ce1`
- `MobileNetworking!FreeMemory` at `0x180017f26`
- `MobileNetworking!FreeMemory` at `0x180017f47`
- `MobileNetworking!FreeMemory` at `0x180017f26`
- `MobileNetworking!FreeMemory` at `0x180017f47`

## pseudocode

```c
__int64 __fastcall EapHandlePeapTLV(__int64 a1, __int64 a2)
{
  _BYTE *v2; // r10
  __int64 v4; // r8
  unsigned int v5; // r14d
  unsigned int v6; // ebp
  unsigned int v7; // esi
  int v8; // r15d
  unsigned int i; // ebx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 result; // rax
  int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int j; // ebp
  __int64 v17; // rax
  _BYTE *v18; // r12
  __int64 v19; // r13
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned int k; // ebx
  unsigned int m; // ebx
  __int128 v25; // [rsp+30h] [rbp-58h] BYREF
  int v27; // [rsp+98h] [rbp+10h]
  unsigned __int16 v28; // [rsp+A0h] [rbp+18h]
  __int64 v29; // [rsp+A8h] [rbp+20h] BYREF

  v2 = WPP_GLOBAL_Control;
  v27 = 0;
  v4 = a1;
  v5 = 0;
  v6 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  v7 = 0;
  v29 = 0;
  v8 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)a2 )
    {
      if ( v7 && (v14 = AllocateMemory(16 * v7, &v29, "EapHandlePeapTLV", 1538), (v5 = v14) != 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 157, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v14);
      }
      else
      {
        v15 = 0;
        for ( j = 0; v15 < v7 && j < *(_DWORD *)a2; ++j )
        {
          v17 = *(_QWORD *)(a2 + 8);
          if ( *(_DWORD *)(v17 + 16LL * j) == 8102 )
          {
            v18 = *(_BYTE **)(v17 + 16LL * j + 8);
            if ( v18[1] == 3 )
            {
              v19 = 16LL * v15;
              v28 = ((unsigned __int8)v18[2] << 8) + (unsigned __int8)v18[3];
              v5 = AllocateAndCopyPointerData(v19 + v29 + 8, v18 + 4, v28);
              if ( v5 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                {
                  v21 = 158;
LABEL_53:
                  WPP_SF_d(v20[7], v21, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v5);
                }
                goto LABEL_54;
              }
              ++v15;
              *(_WORD *)(v29 + v19 + 2) = v28;
              *(_BYTE *)(v29 + v19) = *v18;
              *(_BYTE *)(v29 + v19 + 1) = v18[1];
            }
          }
        }
        v22 = 0;
        for ( k = 0; k < v7; ++k )
        {
          if ( *(_BYTE *)(v29 + 16LL * k + 1) == 3 )
          {
            v25 = *(_OWORD *)(v29 + 16LL * k);
            v5 = EapHandleStatusTLV(a1, &v25, v4);
            if ( v5 )
            {
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                v21 = 159;
                goto LABEL_53;
              }
              goto LABEL_54;
            }
            v22 = 1;
          }
        }
        if ( !(_DWORD)v22 && (v8 || v27) )
        {
          v5 = EapHandleUnknownAttribute(a1, v22, v4);
          if ( v5 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              v21 = 160;
              goto LABEL_53;
            }
          }
        }
LABEL_54:
        if ( !v7 )
          return v5;
      }
      if ( v29 )
      {
        for ( m = 0; m < v7; ++m )
          FreeMemory(v29 + 8 + 16LL * m, "EapHandlePeapTLV", 1600);
        FreeMemory(&v29, "EapHandlePeapTLV", 1602);
      }
      return v5;
    }
    v10 = *(_QWORD *)(a2 + 8);
    v11 = *(unsigned int *)(v10 + 16LL * i);
    if ( (_DWORD)v11 == 8103 )
      break;
    if ( (_DWORD)v11 != 8102 )
    {
      if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || (v2[68] & 1) == 0 )
        goto LABEL_16;
      WPP_SF_dd(*((_QWORD *)v2 + 7), 155, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v11, 8102);
      goto LABEL_15;
    }
    v13 = *(unsigned __int8 *)(*(_QWORD *)(v10 + 16LL * i + 8) + 1LL);
    if ( (_BYTE)v13 == 3 )
    {
      ++v7;
      continue;
    }
    if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && (v2[68] & 4) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)v2 + 7), 156, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6, v13);
LABEL_15:
      v2 = WPP_GLOBAL_Control;
      v4 = a1;
    }
LABEL_16:
    v8 = 1;
LABEL_17:
    ;
  }
  result = EapRequestCredentialsChangedInformationalUI(v4, **(_DWORD **)(v10 + 16LL * i + 8) == 0);
  v5 = result;
  if ( !(_DWORD)result )
  {
    v2 = WPP_GLOBAL_Control;
    v4 = a1;
    v27 = 1;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 154, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6, result);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180017b60  mov     [rsp+arg_0], rcx
0x180017b65  push    rbx
0x180017b66  push    rbp
0x180017b67  push    rsi
0x180017b68  push    rdi
0x180017b69  push    r12
0x180017b6b  push    r14
0x180017b6d  push    r15
0x180017b6f  sub     rsp, 50h
0x180017b73  mov     rax, [rcx]
0x180017b76  lea     r12, WPP_GLOBAL_Control
0x180017b7d  mov     r10, cs:WPP_GLOBAL_Control
0x180017b84  xor     r11d, r11d
0x180017b87  mov     rdi, rdx
0x180017b8a  mov     [rsp+88h+arg_8], r11d
0x180017b92  mov     r8, rcx
0x180017b95  mov     r14d, r11d
0x180017b98  mov     ebp, [rax+14h]
0x180017b9b  mov     esi, r11d
0x180017b9e  mov     [rsp+88h+arg_18], r11
0x180017ba6  mov     r15d, r11d
0x180017ba9  mov     ebx, r11d
0x180017bac  cmp     ebx, [rdi]
0x180017bae  jnb     loc_180017CC3
0x180017bb4  mov     rax, [rdi+8]
0x180017bb8  mov     ecx, ebx
0x180017bba  add     rcx, rcx
0x180017bbd  mov     r9d, [rax+rcx*8]
0x180017bc1  cmp     r9d, 1FA7h
0x180017bc8  jnz     short loc_180017C0A
0x180017bca  mov     rax, [rax+rcx*8+8]
0x180017bcf  mov     edx, r11d
0x180017bd2  mov     rcx, r8
0x180017bd5  cmp     dword ptr [rax], 0
0x180017bd8  setz    dl
0x180017bdb  call    EapRequestCredentialsChangedInformationalUI
0x180017be0  mov     r14d, eax
0x180017be3  test    eax, eax
0x180017be5  jnz     loc_180017C87
0x180017beb  mov     r10, cs:WPP_GLOBAL_Control
0x180017bf2  xor     r11d, r11d
0x180017bf5  mov     r8, [rsp+88h+arg_0]
0x180017bfd  mov     [rsp+88h+arg_8], 1
0x180017c08  jmp     short loc_180017C80
0x180017c0a  cmp     r9d, 1FA6h
0x180017c11  jz      short loc_180017C2E
0x180017c13  cmp     r10, r12
0x180017c16  jz      short loc_180017C7A
0x180017c18  test    byte ptr [r10+44h], 1
0x180017c1d  jz      short loc_180017C7A
0x180017c1f  mov     edx, 9Bh
0x180017c24  mov     [rsp+88h+var_68], 1FA6h
0x180017c2c  jmp     short loc_180017C58
0x180017c2e  mov     rax, [rax+rcx*8+8]
0x180017c33  movzx   ecx, byte ptr [rax+1]
0x180017c37  cmp     cl, 3
0x180017c3a  jnz     short loc_180017C40
0x180017c3c  inc     esi
0x180017c3e  jmp     short loc_180017C80
0x180017c40  cmp     r10, r12
0x180017c43  jz      short loc_180017C7A
0x180017c45  test    byte ptr [r10+44h], 4
0x180017c4a  jz      short loc_180017C7A
0x180017c4c  mov     edx, 9Ch
0x180017c51  mov     [rsp+88h+var_68], ecx
0x180017c55  mov     r9d, ebp
0x180017c58  mov     rcx, [r10+38h]
0x180017c5c  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180017c63  call    WPP_SF_dd
0x180017c68  mov     r10, cs:WPP_GLOBAL_Control
0x180017c6f  xor     r11d, r11d
0x180017c72  mov     r8, [rsp+88h+arg_0]
0x180017c7a  mov     r15d, 1
0x180017c80  inc     ebx
0x180017c82  jmp     loc_180017BAC
0x180017c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c8e  cmp     rcx, r12
0x180017c91  jz      loc_180017F50
0x180017c97  test    byte ptr [rcx+44h], 1
0x180017c9b  jz      loc_180017F50
0x180017ca1  mov     rcx, [rcx+38h]
0x180017ca5  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180017cac  mov     edx, 9Ah
0x180017cb1  mov     [rsp+88h+var_68], r14d
0x180017cb6  mov     r9d, ebp
0x180017cb9  call    WPP_SF_dd
0x180017cbe  jmp     loc_180017F4D
0x180017cc3  test    esi, esi
0x180017cc5  jz      short loc_180017D28
0x180017cc7  mov     ecx, esi
0x180017cc9  lea     r8, aEaphandlepeapt; "EapHandlePeapTLV"
0x180017cd0  shl     ecx, 4
0x180017cd3  lea     rdx, [rsp+88h+arg_18]
0x180017cdb  mov     r9d, 602h
0x180017ce1  call    cs:__imp_AllocateMemory
0x180017ce7  mov     r14d, eax
0x180017cea  test    eax, eax
0x180017cec  jz      short loc_180017D25
0x180017cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cf5  cmp     rcx, r12
0x180017cf8  jz      loc_180017EF3
0x180017cfe  test    byte ptr [rcx+44h], 1
0x180017d02  jz      loc_180017EF3
0x180017d08  mov     rcx, [rcx+38h]
0x180017d0c  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180017d13  mov     edx, 9Dh
0x180017d18  mov     r9d, eax
0x180017d1b  call    WPP_SF_d
0x180017d20  jmp     loc_180017EF3
0x180017d25  xor     r11d, r11d
0x180017d28  mov     ebx, r11d
0x180017d2b  mov     [rsp+88h+var_40], r13
0x180017d30  mov     ebp, r11d
0x180017d33  mov     edx, 100h
0x180017d38  cmp     ebx, esi
0x180017d3a  jnb     loc_180017E2D
0x180017d40  cmp     ebp, [rdi]
0x180017d42  jnb     loc_180017E2D
0x180017d48  mov     rax, [rdi+8]
0x180017d4c  mov     ecx, ebp
0x180017d4e  add     rcx, rcx
0x180017d51  cmp     dword ptr [rax+rcx*8], 1FA6h
0x180017d58  jnz     loc_180017DFB
0x180017d5e  mov     r12, [rax+rcx*8+8]
0x180017d63  cmp     byte ptr [r12+1], 3
0x180017d69  jnz     loc_180017DFB
0x180017d6f  movzx   r8d, byte ptr [r12+3]
0x180017d75  movzx   eax, byte ptr [r12+2]
0x180017d7b  movzx   ecx, dx
0x180017d7e  lea     rdx, [r12+4]
0x180017d83  imul    eax, ecx
0x180017d86  mov     rcx, [rsp+88h+arg_18]
0x180017d8e  add     rcx, 8
0x180017d92  mov     r13d, ebx
0x180017d95  shl     r13, 4
0x180017d99  add     rcx, r13
0x180017d9c  add     r8w, ax
0x180017da0  movzx   eax, r8w
0x180017da4  mov     r8d, eax
0x180017da7  mov     [rsp+88h+arg_10], eax
0x180017dae  call    cs:__imp_AllocateAndCopyPointerData
0x180017db4  mov     r14d, eax
0x180017db7  test    eax, eax
0x180017db9  jnz     short loc_180017E02
0x180017dbb  mov     rax, [rsp+88h+arg_18]
0x180017dc3  inc     ebx
0x180017dc5  mov     ecx, [rsp+88h+arg_10]
0x180017dcc  mov     edx, 100h
0x180017dd1  mov     [rax+r13+2], cx
0x180017dd7  mov     rax, [rsp+88h+arg_18]
0x180017ddf  movzx   ecx, byte ptr [r12]
0x180017de4  mov     [rax+r13], cl
0x180017de8  mov     rax, [rsp+88h+arg_18]
0x180017df0  movzx   ecx, byte ptr [r12+1]
0x180017df6  mov     [rax+r13+1], cl
0x180017dfb  inc     ebp
0x180017dfd  jmp     loc_180017D38
0x180017e02  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e09  lea     rax, WPP_GLOBAL_Control
0x180017e10  cmp     rcx, rax
0x180017e13  jz      loc_180017EEA
0x180017e19  test    byte ptr [rcx+44h], 1
0x180017e1d  jz      loc_180017EEA
0x180017e23  mov     edx, 9Eh
0x180017e28  jmp     loc_180017ED7
0x180017e2d  mov     rdi, [rsp+88h+arg_0]
0x180017e35  xor     edx, edx
0x180017e37  xor     ebx, ebx
0x180017e39  cmp     ebx, esi
0x180017e3b  jnb     short loc_180017E97
0x180017e3d  mov     rax, [rsp+88h+arg_18]
0x180017e45  mov     ecx, ebx
0x180017e47  add     rcx, rcx
0x180017e4a  cmp     byte ptr [rax+rcx*8+1], 3
0x180017e4f  jnz     short loc_180017E73
0x180017e51  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180017e55  lea     rdx, [rsp+88h+var_58]
0x180017e5a  mov     rcx, rdi
0x180017e5d  movaps  [rsp+88h+var_58], xmm0
0x180017e62  call    EapHandleStatusTLV
0x180017e67  mov     r14d, eax
0x180017e6a  test    eax, eax
0x180017e6c  jnz     short loc_180017E77
0x180017e6e  mov     edx, 1
0x180017e73  inc     ebx
0x180017e75  jmp     short loc_180017E39
0x180017e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e7e  lea     rax, WPP_GLOBAL_Control
0x180017e85  cmp     rcx, rax
0x180017e88  jz      short loc_180017EEA
0x180017e8a  test    byte ptr [rcx+44h], 1
0x180017e8e  jz      short loc_180017EEA
0x180017e90  mov     edx, 9Fh
0x180017e95  jmp     short loc_180017ED7
0x180017e97  test    edx, edx
0x180017e99  jnz     short loc_180017EEA
0x180017e9b  test    r15d, r15d
0x180017e9e  jnz     short loc_180017EAA
0x180017ea0  cmp     [rsp+88h+arg_8], r15d
0x180017ea8  jz      short loc_180017EEA
0x180017eaa  mov     rcx, rdi
0x180017ead  call    EapHandleUnknownAttribute
0x180017eb2  mov     r14d, eax
0x180017eb5  test    eax, eax
0x180017eb7  jz      short loc_180017EEA
0x180017eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ec0  lea     rax, WPP_GLOBAL_Control
0x180017ec7  cmp     rcx, rax
0x180017eca  jz      short loc_180017EEA
0x180017ecc  test    byte ptr [rcx+44h], 1
0x180017ed0  jz      short loc_180017EEA
0x180017ed2  mov     edx, 0A0h
0x180017ed7  mov     rcx, [rcx+38h]
0x180017edb  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180017ee2  mov     r9d, r14d
0x180017ee5  call    WPP_SF_d
0x180017eea  mov     r13, [rsp+88h+var_40]
0x180017eef  test    esi, esi
0x180017ef1  jz      short loc_180017F4D
0x180017ef3  cmp     [rsp+88h+arg_18], 0
0x180017efc  jz      short loc_180017F4D
0x180017efe  xor     ebx, ebx
0x180017f00  test    esi, esi
0x180017f02  jz      short loc_180017F32
0x180017f04  mov     rax, [rsp+88h+arg_18]
0x180017f0c  lea     rdx, aEaphandlepeapt; "EapHandlePeapTLV"
0x180017f13  add     rax, 8
0x180017f17  mov     ecx, ebx
0x180017f19  shl     rcx, 4
0x180017f1d  mov     r8d, 640h
0x180017f23  add     rcx, rax
0x180017f26  call    cs:__imp_FreeMemory
0x180017f2c  inc     ebx
0x180017f2e  cmp     ebx, esi
0x180017f30  jb      short loc_180017F04
0x180017f32  mov     r8d, 642h
0x180017f38  lea     rdx, aEaphandlepeapt; "EapHandlePeapTLV"
0x180017f3f  lea     rcx, [rsp+88h+arg_18]
0x180017f47  call    cs:__imp_FreeMemory
0x180017f4d  mov     eax, r14d
0x180017f50  add     rsp, 50h
0x180017f54  pop     r15
0x180017f56  pop     r14
0x180017f58  pop     r12
0x180017f5a  pop     rdi
0x180017f5b  pop     rsi
0x180017f5c  pop     rbp
0x180017f5d  pop     rbx
0x180017f5e  retn
```
