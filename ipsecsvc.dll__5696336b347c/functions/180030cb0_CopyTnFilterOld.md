# CopyTnFilterOld

- ea: `0x180030cb0`
- end: `0x180030f47`
- name: `CopyTnFilterOld`
- size: `663`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180031c30`

## callees

- `0x18000e510`
- `0x180016398`
- `0x1800171d0`
- `0x1800173d0`
- `0x1800175dc`
- `0x180030cb0`

## pseudocode

```c
__int64 __fastcall CopyTnFilterOld(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  _QWORD *v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 44) == 10
    || *(_DWORD *)(a1 + 84) == 10
    || *(_DWORD *)(a1 + 124) == 10
    || (v4 = a1 + 164, *(_DWORD *)(a1 + 164) == 10)
    || *(_DWORD *)(a1 + 212) == 2
    || *(_DWORD *)(a1 + 220) == 2 )
  {
    v7 = 50;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, 50);
    v5 = (_QWORD *)(a2 + 24);
    goto LABEL_33;
  }
  v5 = (_QWORD *)(a2 + 24);
  *(_DWORD *)a2 = *(_DWORD *)a1;
  *(_OWORD *)(a2 + 4) = *(_OWORD *)(a1 + 4);
  v6 = CopyName(*(STRSAFE_LPCWSTR *)(a1 + 24), (_QWORD *)(a2 + 24));
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = 69;
LABEL_11:
      WPP_SF_d(v8[2], v9, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v6);
    }
  }
  else
  {
    *(_DWORD *)(a2 + 32) = *(_DWORD *)(a1 + 32);
    *(_DWORD *)(a2 + 36) = *(_DWORD *)(a1 + 36);
    *(_DWORD *)(a2 + 40) = *(_DWORD *)(a1 + 40);
    v6 = CopyIntToOldExtAddresses(a1 + 44, a2 + 48);
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v9 = 70;
        goto LABEL_11;
      }
    }
    else
    {
      v6 = CopyIntToOldExtAddresses(a1 + 84, a2 + 80);
      v7 = v6;
      if ( v6 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v9 = 71;
          goto LABEL_11;
        }
      }
      else
      {
        v6 = CopyIntToOldExtAddresses(a1 + 124, a2 + 136);
        v7 = v6;
        if ( v6 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v9 = 72;
            goto LABEL_11;
          }
        }
        else
        {
          v6 = CopyIntToOldExtAddresses(v4, a2 + 168);
          v7 = v6;
          if ( !v6 )
          {
            *(_QWORD *)(a2 + 112) = *(_QWORD *)(a1 + 204);
            CopyPortsToOld(a1 + 212, a2 + 120);
            CopyPortsToOld(a1 + 220, a2 + 128);
            *(_DWORD *)(a2 + 200) = *(_DWORD *)(a1 + 228);
            *(_DWORD *)(a2 + 204) = *(_DWORD *)(a1 + 232);
            result = 0;
            *(_QWORD *)(a2 + 208) = 0;
            *(_OWORD *)(a2 + 216) = *(_OWORD *)(a1 + 248);
            return result;
          }
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v9 = 73;
            goto LABEL_11;
          }
        }
      }
    }
  }
LABEL_33:
  if ( *v5 )
  {
    SPDApiBufferFree(*v5);
    *v5 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180030cb0  push    rbx
0x180030cb2  push    rbp
0x180030cb3  push    rsi
0x180030cb4  push    rdi
0x180030cb5  push    r12
0x180030cb7  push    r13
0x180030cb9  push    r14
0x180030cbb  push    r15
0x180030cbd  sub     rsp, 28h
0x180030cc1  cmp     dword ptr [rcx+2Ch], 0Ah
0x180030cc5  mov     r14, rdx
0x180030cc8  mov     rsi, rcx
0x180030ccb  jz      loc_180030EE8
0x180030cd1  cmp     dword ptr [rcx+54h], 0Ah
0x180030cd5  jz      loc_180030EE8
0x180030cdb  cmp     dword ptr [rcx+7Ch], 0Ah
0x180030cdf  jz      loc_180030EE8
0x180030ce5  lea     r12, [rcx+0A4h]
0x180030cec  cmp     dword ptr [r12], 0Ah
0x180030cf1  jz      loc_180030EE8
0x180030cf7  cmp     dword ptr [rcx+0D4h], 2
0x180030cfe  jz      loc_180030EE8
0x180030d04  cmp     dword ptr [rcx+0DCh], 2
0x180030d0b  jz      loc_180030EE8
0x180030d11  mov     eax, [rcx]
0x180030d13  lea     rbx, [rdx+18h]
0x180030d17  mov     [rdx], eax
0x180030d19  movups  xmm0, xmmword ptr [rcx+4]
0x180030d1d  movdqu  xmmword ptr [rdx+4], xmm0
0x180030d22  mov     rcx, [rcx+18h]; pszSrc
0x180030d26  mov     rdx, rbx
0x180030d29  call    CopyName
0x180030d2e  mov     edi, eax
0x180030d30  test    eax, eax
0x180030d32  jz      short loc_180030D72
0x180030d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d3b  lea     rdx, WPP_GLOBAL_Control
0x180030d42  cmp     rcx, rdx
0x180030d45  jz      loc_180030F20
0x180030d4b  test    byte ptr [rcx+1Ch], 10h
0x180030d4f  jz      loc_180030F20
0x180030d55  mov     edx, 45h ; 'E'
0x180030d5a  mov     rcx, [rcx+10h]
0x180030d5e  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180030d65  mov     r9d, eax
0x180030d68  call    WPP_SF_d
0x180030d6d  jmp     loc_180030F20
0x180030d72  mov     eax, [rsi+20h]
0x180030d75  lea     rdx, [r14+30h]
0x180030d79  mov     [r14+20h], eax
0x180030d7d  lea     rcx, [rsi+2Ch]
0x180030d81  mov     eax, [rsi+24h]
0x180030d84  mov     [r14+24h], eax
0x180030d88  mov     eax, [rsi+28h]
0x180030d8b  mov     [r14+28h], eax
0x180030d8f  call    CopyIntToOldExtAddresses
0x180030d94  mov     edi, eax
0x180030d96  test    eax, eax
0x180030d98  jz      short loc_180030DC2
0x180030d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030da1  lea     rdx, WPP_GLOBAL_Control
0x180030da8  cmp     rcx, rdx
0x180030dab  jz      loc_180030F20
0x180030db1  test    byte ptr [rcx+1Ch], 10h
0x180030db5  jz      loc_180030F20
0x180030dbb  mov     edx, 46h ; 'F'
0x180030dc0  jmp     short loc_180030D5A
0x180030dc2  lea     rdx, [r14+50h]
0x180030dc6  lea     rcx, [rsi+54h]
0x180030dca  call    CopyIntToOldExtAddresses
0x180030dcf  mov     edi, eax
0x180030dd1  test    eax, eax
0x180030dd3  jz      short loc_180030E00
0x180030dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ddc  lea     rdx, WPP_GLOBAL_Control
0x180030de3  cmp     rcx, rdx
0x180030de6  jz      loc_180030F20
0x180030dec  test    byte ptr [rcx+1Ch], 10h
0x180030df0  jz      loc_180030F20
0x180030df6  mov     edx, 47h ; 'G'
0x180030dfb  jmp     loc_180030D5A
0x180030e00  lea     rdx, [r14+88h]
0x180030e07  lea     rcx, [rsi+7Ch]
0x180030e0b  call    CopyIntToOldExtAddresses
0x180030e10  mov     edi, eax
0x180030e12  test    eax, eax
0x180030e14  jz      short loc_180030E41
0x180030e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e1d  lea     rdx, WPP_GLOBAL_Control
0x180030e24  cmp     rcx, rdx
0x180030e27  jz      loc_180030F20
0x180030e2d  test    byte ptr [rcx+1Ch], 10h
0x180030e31  jz      loc_180030F20
0x180030e37  mov     edx, 48h ; 'H'
0x180030e3c  jmp     loc_180030D5A
0x180030e41  lea     rdx, [r14+0A8h]
0x180030e48  mov     rcx, r12
0x180030e4b  call    CopyIntToOldExtAddresses
0x180030e50  mov     edi, eax
0x180030e52  test    eax, eax
0x180030e54  jz      short loc_180030E81
0x180030e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e5d  lea     rdx, WPP_GLOBAL_Control
0x180030e64  cmp     rcx, rdx
0x180030e67  jz      loc_180030F20
0x180030e6d  test    byte ptr [rcx+1Ch], 10h
0x180030e71  jz      loc_180030F20
0x180030e77  mov     edx, 49h ; 'I'
0x180030e7c  jmp     loc_180030D5A
0x180030e81  mov     rax, [rsi+0CCh]
0x180030e88  lea     rdx, [r14+78h]
0x180030e8c  lea     rcx, [rsi+0D4h]
0x180030e93  mov     [r14+70h], rax
0x180030e97  call    CopyPortsToOld
0x180030e9c  lea     rdx, [r14+80h]
0x180030ea3  lea     rcx, [rsi+0DCh]
0x180030eaa  call    CopyPortsToOld
0x180030eaf  mov     ecx, [rsi+0E4h]
0x180030eb5  mov     [r14+0C8h], ecx
0x180030ebc  mov     eax, [rsi+0E8h]
0x180030ec2  mov     [r14+0CCh], eax
0x180030ec9  xor     eax, eax
0x180030ecb  mov     qword ptr [r14+0D0h], 0
0x180030ed6  movups  xmm0, xmmword ptr [rsi+0F8h]
0x180030edd  movdqu  xmmword ptr [r14+0D8h], xmm0
0x180030ee6  jmp     short loc_180030F36
0x180030ee8  mov     edi, 32h ; '2'
0x180030eed  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ef4  lea     rdx, WPP_GLOBAL_Control
0x180030efb  cmp     rcx, rdx
0x180030efe  jz      short loc_180030F1C
0x180030f00  test    byte ptr [rcx+1Ch], 10h
0x180030f04  jz      short loc_180030F1C
0x180030f06  mov     rcx, [rcx+10h]
0x180030f0a  lea     edx, [rdi+12h]
0x180030f0d  mov     r9d, edi
0x180030f10  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180030f17  call    WPP_SF_d
0x180030f1c  lea     rbx, [r14+18h]
0x180030f20  mov     rcx, [rbx]
0x180030f23  test    rcx, rcx
0x180030f26  jz      short loc_180030F34
0x180030f28  call    SPDApiBufferFree
0x180030f2d  mov     qword ptr [rbx], 0
0x180030f34  mov     eax, edi
0x180030f36  add     rsp, 28h
0x180030f3a  pop     r15
0x180030f3c  pop     r14
0x180030f3e  pop     r13
0x180030f40  pop     r12
0x180030f42  pop     rdi
0x180030f43  pop     rsi
0x180030f44  pop     rbp
0x180030f45  pop     rbx
0x180030f46  retn
```
