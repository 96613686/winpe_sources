# msSet

- ea: `0x180001bfc`
- end: `0x180001ee5`
- name: `msSet`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800025fc`

## callees

- `0x18000145c`
- `0x180001bfc`
- `0x180005270`
- `0x180005ff0`

## import_xrefs

- `WINMM!midiOutGetNumDevs` at `0x180001e38`
- `WINMM!midiOutGetNumDevs` at `0x180001e4e`
- `WINMM!midiOutGetNumDevs` at `0x180001e38`
- `WINMM!midiOutGetNumDevs` at `0x180001e4e`

## pseudocode

```c
__int64 __fastcall msSet(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  unsigned int v4; // r8d
  unsigned int v7; // ebx
  int v8; // ecx
  int v9; // eax
  unsigned __int8 v10; // r10
  char *v11; // r9
  __int64 v12; // r8
  unsigned int v13; // edx
  UINT v15; // esi
  DWORD_PTR v16; // rcx
  char v17; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int16 v18; // [rsp+24h] [rbp-54h]
  char v19; // [rsp+26h] [rbp-52h]
  char v20; // [rsp+27h] [rbp-51h]
  _OWORD v21[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+60h] [rbp-18h]

  v4 = a3 & 0xFFFF9FFC;
  if ( v4 != (v4 & 0x10F1F00) )
    return 259;
  v7 = 0;
  if ( v4 > 0x10000 )
  {
    switch ( v4 )
    {
      case 0x20000u:
        v15 = a4[5];
        if ( v15 == 65533 )
        {
          midiSeqMessage(*(_QWORD *)(a1 + 256), 0xDu, 1, 0);
          *(_DWORD *)(a1 + 288) = 65533;
          return v7;
        }
        if ( !midiOutGetNumDevs() )
          return 343;
        if ( v15 != -1 && v15 >= midiOutGetNumDevs() )
          return 338;
        if ( v15 == *(_DWORD *)(a1 + 288) )
          return v7;
        v16 = *(_QWORD *)(a1 + 256);
        *(_DWORD *)(a1 + 288) = v15;
        memset(v21, 0, sizeof(v21));
        v22 = 0;
        midiSeqMessage(v16, 0xBu, (__int64)v21, 0);
        if ( !DWORD2(v21[0]) )
          return v7;
        midiSeqMessage(*(_QWORD *)(a1 + 256), 0xDu, 1, 0);
        return (unsigned int)OpenMidiPort(a1);
      case 0x40000u:
        switch ( a4[6] )
        {
          case 0x4002:
            v11 = 0;
            v12 = 1;
            break;
          case 0x4003:
          case 0x4004:
            return 274;
          case 0xFFFD:
            v11 = 0;
            v12 = 0;
            break;
          default:
            return v7;
        }
        break;
      case 0x80000u:
        if ( a4[7] == 16387 || a4[7] == 16388 )
          return 274;
        if ( a4[7] != 65533 )
          return v7;
        v11 = 0;
        v12 = 0;
        v13 = 19;
        return (unsigned int)midiSeqMessage(*(_QWORD *)(a1 + 256), v13, v12, (__int64)v11);
      case 0x1000000u:
        v9 = a4[8];
        v10 = *((_BYTE *)a4 + 32);
        v18 = __PAIR16__(BYTE1(v9), v10);
        v19 = BYTE2(v9);
        v20 = HIBYTE(v9);
        if ( (v9 & 0x80808080) != 0 || v10 > 0x17u || BYTE1(v9) > 0x3Bu || BYTE2(v9) > 0x3Bu || HIBYTE(v9) > 0x1Du )
          return 282;
        v11 = &v17;
        v12 = 4;
        break;
      default:
        return 273;
    }
    v13 = 18;
    return (unsigned int)midiSeqMessage(*(_QWORD *)(a1 + 256), v13, v12, (__int64)v11);
  }
  if ( v4 == 0x10000 )
    return (unsigned int)midiSeqMessage(*(_QWORD *)(a1 + 256), 6u, (unsigned int)a4[4], 0);
  if ( ((v4 - 256) & 0xFFFFFEFF) != 0 )
  {
    if ( v4 == 1024 )
    {
      v8 = a4[2];
      if ( v8 && v8 != 4 && v8 != 5 && v8 != 6 && v8 != 7 )
      {
        if ( v8 != 16385 )
          return 293;
        if ( *(_DWORD *)(a1 + 340) )
          return 336;
      }
      *(_DWORD *)(a1 + 344) = v8;
      return v7;
    }
    if ( ((v4 - 2048) & 0xFFFFF7FF) != 0 )
      return 273;
  }
  return 274;
}

```

## disassembly

```asm
0x180001bfc  mov     [rsp+arg_8], rbx
0x180001c01  mov     [rsp+arg_10], rsi
0x180001c06  push    rdi
0x180001c07  sub     rsp, 70h
0x180001c0b  mov     rax, cs:__security_cookie
0x180001c12  xor     rax, rsp
0x180001c15  mov     [rsp+78h+var_10], rax
0x180001c1a  and     r8d, 0FFFF9FFCh
0x180001c21  mov     rdi, rcx
0x180001c24  mov     eax, r8d
0x180001c27  and     eax, 10F1F00h
0x180001c2c  cmp     r8d, eax
0x180001c2f  jz      short loc_180001C3B
0x180001c31  mov     eax, 103h
0x180001c36  jmp     loc_180001EC6
0x180001c3b  xor     ebx, ebx
0x180001c3d  mov     eax, 10000h
0x180001c42  cmp     r8d, eax
0x180001c45  ja      loc_180001CEB
0x180001c4b  jz      short loc_180001CCC
0x180001c4d  lea     eax, [r8-100h]
0x180001c54  test    eax, 0FFFFFEFFh
0x180001c59  jz      short loc_180001C76
0x180001c5b  cmp     r8d, 400h
0x180001c62  jz      short loc_180001C80
0x180001c64  lea     eax, [r8-800h]
0x180001c6b  test    eax, 0FFFFF7FFh
0x180001c70  jnz     loc_180001D1B
0x180001c76  mov     ebx, 112h
0x180001c7b  jmp     loc_180001EC4
0x180001c80  mov     ecx, [r9+8]
0x180001c84  mov     eax, ecx
0x180001c86  test    ecx, ecx
0x180001c88  jz      short loc_180001CC1
0x180001c8a  sub     eax, 4
0x180001c8d  jz      short loc_180001CC1
0x180001c8f  sub     eax, 1
0x180001c92  jz      short loc_180001CC1
0x180001c94  sub     eax, 1
0x180001c97  jz      short loc_180001CC1
0x180001c99  sub     eax, 1
0x180001c9c  jz      short loc_180001CC1
0x180001c9e  cmp     eax, 3FFAh
0x180001ca3  jz      short loc_180001CAF
0x180001ca5  mov     ebx, 125h
0x180001caa  jmp     loc_180001EC4
0x180001caf  cmp     [rdi+154h], ebx
0x180001cb5  jz      short loc_180001CC1
0x180001cb7  mov     ebx, 150h
0x180001cbc  jmp     loc_180001EC4
0x180001cc1  mov     [rdi+158h], ecx
0x180001cc7  jmp     loc_180001EC4
0x180001ccc  mov     r8d, [r9+10h]
0x180001cd0  xor     r9d, r9d
0x180001cd3  mov     rcx, [rcx+100h]; dwUser
0x180001cda  lea     edx, [r9+6]
0x180001cde  call    midiSeqMessage
0x180001ce3  mov     rbx, rax
0x180001ce6  jmp     loc_180001EC4
0x180001ceb  cmp     r8d, 20000h
0x180001cf2  jz      loc_180001E0A
0x180001cf8  cmp     r8d, 40000h
0x180001cff  jz      loc_180001DC9
0x180001d05  cmp     r8d, 80000h
0x180001d0c  jz      loc_180001D98
0x180001d12  cmp     r8d, 1000000h
0x180001d19  jz      short loc_180001D25
0x180001d1b  mov     ebx, 111h
0x180001d20  jmp     loc_180001EC4
0x180001d25  mov     eax, [r9+20h]
0x180001d29  mov     r8d, eax
0x180001d2c  mov     r10b, [r9+20h]
0x180001d30  mov     edx, eax
0x180001d32  shr     r8d, 8
0x180001d36  mov     ecx, eax
0x180001d38  shr     edx, 10h
0x180001d3b  shr     ecx, 18h
0x180001d3e  mov     [rsp+78h+var_54], r10b
0x180001d43  mov     [rsp+78h+var_53], r8b
0x180001d48  mov     [rsp+78h+var_52], dl
0x180001d4c  mov     [rsp+78h+var_51], cl
0x180001d50  test    eax, 80808080h
0x180001d55  jnz     short loc_180001D8E
0x180001d57  cmp     r10b, 17h
0x180001d5b  ja      short loc_180001D8E
0x180001d5d  cmp     r8b, 3Bh ; ';'
0x180001d61  ja      short loc_180001D8E
0x180001d63  cmp     dl, 3Bh ; ';'
0x180001d66  ja      short loc_180001D8E
0x180001d68  cmp     cl, 1Dh
0x180001d6b  ja      short loc_180001D8E
0x180001d6d  lea     r9, [rsp+78h+var_58]
0x180001d72  mov     r8d, 4
0x180001d78  mov     edx, 12h
0x180001d7d  mov     rcx, [rdi+100h]; dwUser
0x180001d84  call    midiSeqMessage
0x180001d89  jmp     loc_180001EC2
0x180001d8e  mov     ebx, 11Ah
0x180001d93  jmp     loc_180001EC4
0x180001d98  mov     ecx, [r9+1Ch]
0x180001d9c  sub     ecx, 4003h
0x180001da2  jz      loc_180001C76
0x180001da8  sub     ecx, 1
0x180001dab  jz      loc_180001C76
0x180001db1  cmp     ecx, 0BFF9h
0x180001db7  jnz     loc_180001EC4
0x180001dbd  xor     r9d, r9d
0x180001dc0  xor     r8d, r8d
0x180001dc3  lea     edx, [r9+13h]
0x180001dc7  jmp     short loc_180001D7D
0x180001dc9  mov     ecx, [r9+18h]
0x180001dcd  sub     ecx, 4002h
0x180001dd3  jz      short loc_180001DFE
0x180001dd5  sub     ecx, 1
0x180001dd8  jz      loc_180001C76
0x180001dde  sub     ecx, 1
0x180001de1  jz      loc_180001C76
0x180001de7  cmp     ecx, 0BFF9h
0x180001ded  jnz     loc_180001EC4
0x180001df3  xor     r9d, r9d
0x180001df6  xor     r8d, r8d
0x180001df9  jmp     loc_180001D78
0x180001dfe  xor     r9d, r9d
0x180001e01  lea     r8d, [r9+1]
0x180001e05  jmp     loc_180001D78
0x180001e0a  mov     esi, [r9+14h]
0x180001e0e  cmp     esi, 0FFFDh
0x180001e14  jnz     short loc_180001E38
0x180001e16  mov     rcx, [rcx+100h]; dwUser
0x180001e1d  xor     r9d, r9d
0x180001e20  lea     edx, [r9+0Dh]
0x180001e24  lea     r8d, [r9+1]
0x180001e28  call    midiSeqMessage
0x180001e2d  mov     [rdi+120h], esi
0x180001e33  jmp     loc_180001EC4
0x180001e38  call    cs:__imp_midiOutGetNumDevs
0x180001e3e  test    eax, eax
0x180001e40  jnz     short loc_180001E49
0x180001e42  mov     ebx, 157h
0x180001e47  jmp     short loc_180001EC4
0x180001e49  cmp     esi, 0FFFFFFFFh
0x180001e4c  jz      short loc_180001E5F
0x180001e4e  call    cs:__imp_midiOutGetNumDevs
0x180001e54  cmp     esi, eax
0x180001e56  jb      short loc_180001E5F
0x180001e58  mov     ebx, 152h
0x180001e5d  jmp     short loc_180001EC4
0x180001e5f  cmp     esi, [rdi+120h]
0x180001e65  jz      short loc_180001EC4
0x180001e67  mov     rcx, [rdi+100h]; dwUser
0x180001e6e  lea     r8, [rsp+78h+var_48]
0x180001e73  xorps   xmm0, xmm0
0x180001e76  mov     [rdi+120h], esi
0x180001e7c  xor     eax, eax
0x180001e7e  xor     r9d, r9d
0x180001e81  movups  [rsp+78h+var_48], xmm0
0x180001e86  mov     [rsp+78h+var_18], rax
0x180001e8b  movups  [rsp+78h+var_38], xmm0
0x180001e90  lea     edx, [rax+0Bh]
0x180001e93  movups  [rsp+78h+var_28], xmm0
0x180001e98  call    midiSeqMessage
0x180001e9d  cmp     dword ptr [rsp+78h+var_48+8], ebx
0x180001ea1  jz      short loc_180001EC4
0x180001ea3  mov     rcx, [rdi+100h]; dwUser
0x180001eaa  xor     r9d, r9d
0x180001ead  lea     edx, [r9+0Dh]
0x180001eb1  lea     r8d, [r9+1]
0x180001eb5  call    midiSeqMessage
0x180001eba  mov     rcx, rdi
0x180001ebd  call    OpenMidiPort
0x180001ec2  mov     ebx, eax
0x180001ec4  mov     eax, ebx
0x180001ec6  mov     rcx, [rsp+78h+var_10]
0x180001ecb  xor     rcx, rsp; StackCookie
0x180001ece  call    __security_check_cookie
0x180001ed3  lea     r11, [rsp+78h+var_8]
0x180001ed8  mov     rbx, [r11+18h]
0x180001edc  mov     rsi, [r11+20h]
0x180001ee0  mov     rsp, r11
0x180001ee3  pop     rdi
0x180001ee4  retn
```
