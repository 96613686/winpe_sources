# BuildCompatibleID

- ea: `0x18003e210`
- end: `0x18003e586`
- name: `BuildCompatibleID`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003da1c`

## callees

- `0x180009778`
- `0x180012e50`
- `0x180014f70`
- `0x180027d00`
- `0x18003e210`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18003e2e0`
- `ntoskrnl!ExAllocatePool2` at `0x18003e2e0`

## pseudocode

```c
wchar_t *__fastcall BuildCompatibleID(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int v4; // ebx
  unsigned int v5; // r12d
  const wchar_t *v6; // rdi
  unsigned int v7; // r15d
  __int64 v8; // rax
  int v9; // edx
  int v10; // r13d
  int v11; // eax
  unsigned __int16 v12; // r8
  unsigned int v13; // r14d
  wchar_t *Pool2; // rax
  wchar_t *v15; // rbp
  wchar_t *v16; // rsi
  unsigned __int16 v17; // r12
  unsigned int v18; // r11d
  _OWORD *v19; // rsi
  __int16 v21; // r10
  size_t v22; // rbx
  size_t v23; // rbx
  __int64 v24; // [rsp+20h] [rbp-78h]
  __int64 v25; // [rsp+28h] [rbp-70h]
  __int64 v26; // [rsp+30h] [rbp-68h]
  unsigned __int16 v27; // [rsp+40h] [rbp-58h]
  bool v29; // [rsp+A8h] [rbp+10h]
  unsigned __int16 v30; // [rsp+B0h] [rbp+18h]
  unsigned __int16 v31; // [rsp+B8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 96);
  v3 = a1;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v31 = *(_WORD *)(v2 + 140);
  v27 = *(_WORD *)(v2 + 142);
  if ( v31 )
  {
    v7 = WStrLen(L"HID\\VID_%04X&UP:%04X_U:%04X", a2, v2, a1) + 1;
    if ( *(_BYTE *)(v2 + 2009) && v21 )
    {
      if ( *(_DWORD *)(v2 + 200) <= 1u )
        v5 = WStrLen(L"HID\\VID_%04X&PID_%04X&UP:%04X_U:%04X") + 1;
      else
        v4 = WStrLen(L"HID\\VID_%04X&PID_%04X&Col%02X&UP:%04X_U:%04X") - 1;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = *(_QWORD *)(v2 + 192);
  v9 = *(unsigned __int16 *)(v8 + 40LL * *(unsigned int *)(v3 + 44) + 2);
  v10 = *(unsigned __int16 *)(v8 + 40LL * *(unsigned int *)(v3 + 44));
  v30 = *(_WORD *)(v8 + 40LL * *(unsigned int *)(v3 + 44) + 2);
  if ( v10 == 1 )
  {
    switch ( v9 )
    {
      case 1:
      case 2:
        v6 = L"HID_DEVICE_SYSTEM_MOUSE";
        break;
      case 4:
      case 5:
        v6 = L"HID_DEVICE_SYSTEM_GAME";
        break;
      case 6:
      case 7:
        v6 = L"HID_DEVICE_SYSTEM_KEYBOARD";
        break;
      case 128:
        v6 = L"HID_DEVICE_SYSTEM_CONTROL";
        break;
    }
  }
  else if ( *(_WORD *)(v8 + 40LL * *(unsigned int *)(v3 + 44)) == 12 )
  {
    v6 = L"HID_DEVICE_SYSTEM_CONSUMER";
  }
  if ( (unsigned __int16)v10 >= 0xFF00u )
  {
    v6 = L"HID_DEVICE_UPR:FF00-FFFF";
    goto LABEL_8;
  }
  if ( v6 )
  {
LABEL_8:
    v11 = WStrLen(v6);
    v29 = (unsigned __int16)v10 >= v12;
    v13 = v11 + 1;
    goto LABEL_9;
  }
  v13 = 0;
  v29 = 0;
LABEL_9:
  Pool2 = (wchar_t *)ExAllocatePool2(64, 2LL * (v4 + v5 + v7 + v13 + 38), 1130654024);
  v15 = Pool2;
  if ( Pool2 )
  {
    v16 = Pool2;
    if ( v4 )
    {
      v22 = v4;
      RtlStringCbPrintfW(
        Pool2,
        v22 * 2,
        L"HID\\VID_%04X&PID_%04X&Col%02X&UP:%04X_U:%04X",
        v31,
        v27,
        *(unsigned __int16 *)(a1 + 40),
        v10,
        v30);
      v16 = &v15[v22];
    }
    if ( v5 )
    {
      v23 = v5;
      v17 = v30;
      v23 *= 2LL;
      LODWORD(v26) = v30;
      LODWORD(v25) = v10;
      LODWORD(v24) = v27;
      RtlStringCbPrintfW(v16, v23, L"HID\\VID_%04X&PID_%04X&UP:%04X_U:%04X", v31, v24, v25, v26);
      v16 = (wchar_t *)((char *)v16 + v23);
    }
    else
    {
      v17 = v30;
    }
    if ( v7 )
    {
      LODWORD(v25) = v17;
      LODWORD(v24) = v10;
      RtlStringCbPrintfW(v16, 2LL * v7, L"HID\\VID_%04X&UP:%04X_U:%04X", v31, v24, v25);
      v16 += v7;
    }
    if ( v6 && !v29 )
    {
      memmove(v16, v6, 2LL * v13);
      v16 += v13;
      v6 = 0;
    }
    *(_OWORD *)v16 = *(_OWORD *)L"HID_DEVICE_UP:%04x_U:%04x";
    *((_OWORD *)v16 + 1) = *(_OWORD *)L"CE_UP:%04x_U:%04x";
    *((_OWORD *)v16 + 2) = *(_OWORD *)L"4x_U:%04x";
    *((_DWORD *)v16 + 12) = *(_DWORD *)L"x";
    HexToString(v16 + 14, (unsigned __int16)v10, 4);
    HexToString(v16 + 21, v17, v18);
    v19 = v16 + 26;
    if ( v6 )
    {
      memmove(v19, v6, 2LL * v13);
      v19 = (_OWORD *)((char *)v19 + 2 * v13);
    }
    *v19 = *(_OWORD *)L"HID_DEVICE";
    *(_QWORD *)((char *)v19 + 14) = *(_QWORD *)L"ICE";
  }
  return v15;
}

```

## disassembly

```asm
0x18003e210  mov     [rsp+arg_0], rcx
0x18003e215  push    rbx
0x18003e216  push    rbp
0x18003e217  push    rsi
0x18003e218  push    rdi
0x18003e219  push    r12
0x18003e21b  push    r13
0x18003e21d  push    r14
0x18003e21f  push    r15
0x18003e221  sub     rsp, 58h
0x18003e225  mov     r8, [rcx+60h]
0x18003e229  xor     esi, esi
0x18003e22b  mov     r9, rcx
0x18003e22e  mov     ebx, esi
0x18003e230  mov     r12d, esi
0x18003e233  mov     edi, esi
0x18003e235  movzx   eax, word ptr [r8+8Ch]
0x18003e23d  movzx   r10d, word ptr [r8+8Eh]
0x18003e245  mov     [rsp+98h+arg_18], ax
0x18003e24d  mov     [rsp+98h+var_58], r10w
0x18003e253  test    ax, ax
0x18003e256  jnz     loc_18003E420
0x18003e25c  mov     r15d, esi
0x18003e25f  mov     eax, [r9+2Ch]
0x18003e263  lea     rcx, [rax+rax*4]
0x18003e267  mov     rax, [r8+0C0h]
0x18003e26e  movzx   edx, word ptr [rax+rcx*8+2]
0x18003e273  movzx   r13d, word ptr [rax+rcx*8]
0x18003e278  mov     ecx, r13d
0x18003e27b  mov     [rsp+98h+arg_10], dx
0x18003e283  sub     ecx, 1
0x18003e286  jz      loc_18003E465
0x18003e28c  cmp     ecx, 0Bh
0x18003e28f  jz      loc_18003E4BB
0x18003e295  mov     r8d, 0FF00h
0x18003e29b  cmp     r13w, r8w
0x18003e29f  jnb     loc_18003E4DF
0x18003e2a5  test    rdi, rdi
0x18003e2a8  jz      loc_18003E410
0x18003e2ae  mov     rcx, rdi
0x18003e2b1  call    WStrLen
0x18003e2b6  cmp     r13w, r8w
0x18003e2ba  setnb   [rsp+98h+arg_8]
0x18003e2c2  lea     r14d, [rax+1]
0x18003e2c6  lea     edx, [r14+26h]
0x18003e2ca  mov     ecx, 40h ; '@'
0x18003e2cf  add     edx, r15d
0x18003e2d2  mov     r8d, 43646948h
0x18003e2d8  add     edx, r12d
0x18003e2db  add     edx, ebx
0x18003e2dd  add     rdx, rdx
0x18003e2e0  call    cs:__imp_ExAllocatePool2
0x18003e2e7  nop     dword ptr [rax+rax+00h]
0x18003e2ec  mov     rbp, rax
0x18003e2ef  test    rax, rax
0x18003e2f2  jz      loc_18003E3FB
0x18003e2f8  mov     rsi, rax
0x18003e2fb  test    ebx, ebx
0x18003e2fd  jnz     loc_18003E4EB
0x18003e303  test    r12d, r12d
0x18003e306  jnz     loc_18003E541
0x18003e30c  movzx   r12d, [rsp+98h+arg_10]
0x18003e315  test    r15d, r15d
0x18003e318  jz      short loc_18003E34B
0x18003e31a  movzx   r9d, [rsp+98h+arg_18]
0x18003e323  lea     r8, aHidVid04xUp04x; "HID\\VID_%04X&UP:%04X_U:%04X"
0x18003e32a  movzx   eax, r12w
0x18003e32e  mov     rcx, rsi; pszDest
0x18003e331  mov     dword ptr [rsp+98h+var_70], eax
0x18003e335  mov     ebx, r15d
0x18003e338  add     rbx, rbx
0x18003e33b  mov     dword ptr [rsp+98h+var_78], r13d
0x18003e340  mov     rdx, rbx; cbDest
0x18003e343  call    RtlStringCbPrintfW
0x18003e348  add     rsi, rbx
0x18003e34b  test    rdi, rdi
0x18003e34e  jz      short loc_18003E374
0x18003e350  cmp     [rsp+98h+arg_8], 0
0x18003e358  jnz     short loc_18003E374
0x18003e35a  mov     eax, r14d
0x18003e35d  mov     rdx, rdi; Src
0x18003e360  mov     rcx, rsi; void *
0x18003e363  lea     rbx, [rax+rax]
0x18003e367  mov     r8, rbx; Size
0x18003e36a  call    memmove
0x18003e36f  add     rsi, rbx
0x18003e372  xor     edi, edi
0x18003e374  movups  xmm0, xmmword ptr cs:aHidDeviceUp04x; "HID_DEVICE_UP:%04x_U:%04x"
0x18003e37b  mov     r11d, 4
0x18003e381  lea     rcx, [rsi+1Ch]
0x18003e385  mov     r8d, r11d
0x18003e388  movzx   edx, r13w
0x18003e38c  movups  xmmword ptr [rsi], xmm0
0x18003e38f  movups  xmm1, xmmword ptr cs:aHidDeviceUp04x+10h; "CE_UP:%04x_U:%04x"
0x18003e396  movups  xmmword ptr [rsi+10h], xmm1
0x18003e39a  movups  xmm0, xmmword ptr cs:aHidDeviceUp04x+20h; "4x_U:%04x"
0x18003e3a1  movups  xmmword ptr [rsi+20h], xmm0
0x18003e3a5  mov     eax, dword ptr cs:aHidDeviceUp04x+30h; "x"
0x18003e3ab  mov     [rsi+30h], eax
0x18003e3ae  call    HexToString
0x18003e3b3  mov     r8d, r11d
0x18003e3b6  lea     rcx, [rsi+2Ah]
0x18003e3ba  movzx   edx, r12w
0x18003e3be  call    HexToString
0x18003e3c3  add     rsi, 34h ; '4'
0x18003e3c7  test    rdi, rdi
0x18003e3ca  jz      short loc_18003E3E4
0x18003e3cc  mov     eax, r14d
0x18003e3cf  mov     rdx, rdi; Src
0x18003e3d2  mov     rcx, rsi; void *
0x18003e3d5  lea     rbx, [rax+rax]
0x18003e3d9  mov     r8, rbx; Size
0x18003e3dc  call    memmove
0x18003e3e1  add     rsi, rbx
0x18003e3e4  movups  xmm0, xmmword ptr cs:aHidDevice; "HID_DEVICE"
0x18003e3eb  movups  xmmword ptr [rsi], xmm0
0x18003e3ee  movsd   xmm1, qword ptr cs:aHidDevice+0Eh; "ICE"
0x18003e3f6  movsd   qword ptr [rsi+0Eh], xmm1
0x18003e3fb  mov     rax, rbp
0x18003e3fe  add     rsp, 58h
0x18003e402  pop     r15
0x18003e404  pop     r14
0x18003e406  pop     r13
0x18003e408  pop     r12
0x18003e40a  pop     rdi
0x18003e40b  pop     rsi
0x18003e40c  pop     rbp
0x18003e40d  pop     rbx
0x18003e40e  retn
0x18003e410  mov     r14d, esi
0x18003e413  mov     [rsp+98h+arg_8], sil
0x18003e41b  jmp     loc_18003E2C6
0x18003e420  lea     rcx, aHidVid04xUp04x; "HID\\VID_%04X&UP:%04X_U:%04X"
0x18003e427  call    WStrLen
0x18003e42c  lea     r15d, [rax+1]
0x18003e430  cmp     [r8+7D9h], sil
0x18003e437  jz      loc_18003E25F
0x18003e43d  test    r10w, r10w
0x18003e441  jz      loc_18003E25F
0x18003e447  cmp     dword ptr [r8+0C8h], 1
0x18003e44f  jbe     short loc_18003E4A6
0x18003e451  lea     rcx, aHidVid04xPid04; "HID\\VID_%04X&PID_%04X&Col%02X&UP:%04X_"...
0x18003e458  call    WStrLen
0x18003e45d  lea     ebx, [rax-1]
0x18003e460  jmp     loc_18003E25F
0x18003e465  mov     ecx, edx
0x18003e467  sub     ecx, 1
0x18003e46a  jz      short loc_18003E4D3
0x18003e46c  sub     ecx, 1
0x18003e46f  jz      short loc_18003E4D3
0x18003e471  sub     ecx, 2
0x18003e474  jz      short loc_18003E4C7
0x18003e476  sub     ecx, 1
0x18003e479  jz      short loc_18003E4C7
0x18003e47b  sub     ecx, 1
0x18003e47e  jz      short loc_18003E49A
0x18003e480  sub     ecx, 1
0x18003e483  jz      short loc_18003E49A
0x18003e485  cmp     ecx, 79h ; 'y'
0x18003e488  jnz     loc_18003E295
0x18003e48e  lea     rdi, aHidDeviceSyste_1; "HID_DEVICE_SYSTEM_CONTROL"
0x18003e495  jmp     loc_18003E295
0x18003e49a  lea     rdi, aHidDeviceSyste_2; "HID_DEVICE_SYSTEM_KEYBOARD"
0x18003e4a1  jmp     loc_18003E295
0x18003e4a6  lea     rcx, aHidVid04xPid04_0; "HID\\VID_%04X&PID_%04X&UP:%04X_U:%04X"
0x18003e4ad  call    WStrLen
0x18003e4b2  lea     r12d, [rax+1]
0x18003e4b6  jmp     loc_18003E25F
0x18003e4bb  lea     rdi, aHidDeviceSyste_3; "HID_DEVICE_SYSTEM_CONSUMER"
0x18003e4c2  jmp     loc_18003E295
0x18003e4c7  lea     rdi, aHidDeviceSyste_0; "HID_DEVICE_SYSTEM_GAME"
0x18003e4ce  jmp     loc_18003E295
0x18003e4d3  lea     rdi, aHidDeviceSyste; "HID_DEVICE_SYSTEM_MOUSE"
0x18003e4da  jmp     loc_18003E295
0x18003e4df  lea     rdi, aHidDeviceUprFf; "HID_DEVICE_UPR:FF00-FFFF"
0x18003e4e6  jmp     loc_18003E2AE
0x18003e4eb  mov     rax, [rsp+98h+arg_0]
0x18003e4f3  movzx   r8d, [rsp+98h+var_58]
0x18003e4f9  movzx   r9d, [rsp+98h+arg_18]
0x18003e502  mov     ecx, ebx
0x18003e504  movzx   edx, word ptr [rax+28h]
0x18003e508  lea     rbx, [rcx+rcx]
0x18003e50c  movzx   ecx, [rsp+98h+arg_10]
0x18003e514  mov     [rsp+98h+var_60], ecx
0x18003e518  mov     rcx, rbp; pszDest
0x18003e51b  mov     dword ptr [rsp+98h+var_68], r13d
0x18003e520  mov     dword ptr [rsp+98h+var_70], edx
0x18003e524  mov     rdx, rbx; cbDest
0x18003e527  mov     dword ptr [rsp+98h+var_78], r8d
0x18003e52c  lea     r8, aHidVid04xPid04; "HID\\VID_%04X&PID_%04X&Col%02X&UP:%04X_"...
0x18003e533  call    RtlStringCbPrintfW
0x18003e538  lea     rsi, [rbx+rbp]
0x18003e53c  jmp     loc_18003E303
0x18003e541  movzx   edx, [rsp+98h+var_58]
0x18003e546  lea     r8, aHidVid04xPid04_0; "HID\\VID_%04X&PID_%04X&UP:%04X_U:%04X"
0x18003e54d  movzx   r9d, [rsp+98h+arg_18]
0x18003e556  mov     rcx, rsi; pszDest
0x18003e559  mov     ebx, r12d
0x18003e55c  movzx   r12d, [rsp+98h+arg_10]
0x18003e565  add     rbx, rbx
0x18003e568  mov     dword ptr [rsp+98h+var_68], r12d
0x18003e56d  mov     dword ptr [rsp+98h+var_70], r13d
0x18003e572  mov     dword ptr [rsp+98h+var_78], edx
0x18003e576  mov     rdx, rbx; cbDest
0x18003e579  call    RtlStringCbPrintfW
0x18003e57e  add     rsi, rbx
0x18003e581  jmp     loc_18003E315
```
