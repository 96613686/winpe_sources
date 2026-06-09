# SupplicantUpdateUserDataWithCachedCreds

- ea: `0x18002a76c`
- end: `0x18002a9f7`
- name: `SupplicantUpdateUserDataWithCachedCreds`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000a550`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180017840`
- `0x180019cd0`
- `0x18001ce44`
- `0x18001d838`
- `0x1800214f0`
- `0x18002a76c`
- `0x18002ef1c`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x18002a9ae`
- `MobileNetworking!FreeMemory` at `0x18002a9ae`

## pseudocode

```c
__int64 __fastcall SupplicantUpdateUserDataWithCachedCreds(__int64 a1)
{
  __int64 *v1; // rbx
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  int v5; // r14d
  BYTE *v6; // r15
  void *v7; // rbp
  DWORD v8; // r8d
  void *v9; // rax
  int v10; // eax
  int v11; // eax
  unsigned int updated; // eax
  unsigned int v13; // ebx
  size_t v15; // [rsp+28h] [rbp-60h]
  unsigned int v16; // [rsp+90h] [rbp+8h] BYREF
  void *v17; // [rsp+98h] [rbp+10h] BYREF

  v1 = (__int64 *)(a1 + 112);
  v3 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  v16 = 0;
  v17 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 114, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *((_DWORD *)v1 + 24);
  v6 = (BYTE *)v1[13];
  v7 = *(void **)(*v1 + 2840);
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 4) != 0 )
  {
    WPP_SF_dq(v4[7], 115, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v3, *(_QWORD *)(*v1 + 2840));
    v4 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)(a1 + 488);
  if ( v8 && (v9 = *(void **)(a1 + 496)) != 0 )
  {
    LODWORD(v15) = *(_DWORD *)(a1 + 492);
    v10 = OneXUpdateUserDataWithCredentials(
            *(_QWORD *)(a1 + 360),
            v7,
            v5,
            v6,
            v8,
            v15,
            v9,
            (__int64)&v16,
            (__int64)&v17);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 119, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v3, v10);
      v13 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          116,
          WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids,
          v3,
          *((_DWORD *)v1 + 24),
          v16);
      v11 = EapSetWorkingSetUserData(v1, v16, v17);
      if ( v11
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 117, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v3, v11);
      }
      updated = EapUpdateMasterUserData(v1, v16, v17, 1u);
      v13 = updated;
      if ( updated
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          118,
          WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids,
          v3,
          updated);
      }
    }
  }
  else
  {
    v13 = 0;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 4) != 0 )
      WPP_SF_d(v4[7], 120, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v3);
  }
  FreeMemory(&v17, "OneXHlpFreeMemory", 414);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 121, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18002a76c  mov     r11, rsp
0x18002a76f  mov     [r11+18h], rbx
0x18002a773  push    rbp
0x18002a774  push    rsi
0x18002a775  push    rdi
0x18002a776  push    r12
0x18002a778  push    r13
0x18002a77a  push    r14
0x18002a77c  push    r15
0x18002a77e  sub     rsp, 50h
0x18002a782  mov     rax, [rcx]
0x18002a785  lea     rbx, [rcx+70h]
0x18002a789  mov     rsi, rcx
0x18002a78c  mov     edi, [rax+14h]
0x18002a78f  mov     dword ptr [r11+8], 0
0x18002a797  mov     qword ptr [r11+10h], 0
0x18002a79f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7a6  lea     r12, WPP_GLOBAL_Control
0x18002a7ad  lea     r13, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18002a7b4  cmp     rcx, r12
0x18002a7b7  jz      short loc_18002A7DA
0x18002a7b9  test    dword ptr [rcx+44h], 800h
0x18002a7c0  jz      short loc_18002A7DA
0x18002a7c2  mov     rcx, [rcx+38h]
0x18002a7c6  mov     edx, 72h ; 'r'
0x18002a7cb  mov     r8, r13
0x18002a7ce  call    WPP_SF_
0x18002a7d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7da  mov     rax, [rbx]
0x18002a7dd  mov     r14d, [rbx+60h]
0x18002a7e1  mov     r15, [rbx+68h]
0x18002a7e5  mov     rbp, [rax+0B18h]
0x18002a7ec  cmp     rcx, r12
0x18002a7ef  jz      short loc_18002A817
0x18002a7f1  test    byte ptr [rcx+44h], 4
0x18002a7f5  jz      short loc_18002A817
0x18002a7f7  mov     rcx, [rcx+38h]
0x18002a7fb  mov     edx, 73h ; 's'
0x18002a800  mov     r9d, edi
0x18002a803  mov     [rsp+88h+var_68], rbp
0x18002a808  mov     r8, r13
0x18002a80b  call    WPP_SF_dq
0x18002a810  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a817  mov     r8d, [rsi+1E8h]
0x18002a81e  test    r8d, r8d
0x18002a821  jz      loc_18002A97A
0x18002a827  mov     rax, [rsi+1F0h]
0x18002a82e  test    rax, rax
0x18002a831  jz      loc_18002A97A
0x18002a837  lea     rcx, [rsp+88h+arg_8]
0x18002a83f  mov     r9, r15
0x18002a842  mov     [rsp+88h+var_48], rcx
0x18002a847  mov     rdx, rbp
0x18002a84a  lea     rcx, [rsp+88h+arg_0]
0x18002a852  mov     [rsp+88h+var_50], rcx
0x18002a857  mov     rcx, [rsi+168h]
0x18002a85e  mov     [rsp+88h+var_58], rax
0x18002a863  mov     eax, [rsi+1ECh]
0x18002a869  mov     dword ptr [rsp+88h+var_60], eax
0x18002a86d  mov     dword ptr [rsp+88h+var_68], r8d
0x18002a872  mov     r8d, r14d
0x18002a875  call    OneXUpdateUserDataWithCredentials
0x18002a87a  test    eax, eax
0x18002a87c  jnz     loc_18002A94C
0x18002a882  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a889  cmp     rcx, r12
0x18002a88c  jz      short loc_18002A8B8
0x18002a88e  test    byte ptr [rcx+44h], 4
0x18002a892  jz      short loc_18002A8B8
0x18002a894  mov     rcx, [rcx+38h]
0x18002a898  lea     edx, [rax+74h]
0x18002a89b  mov     eax, [rsp+88h+arg_0]
0x18002a8a2  mov     r9d, edi
0x18002a8a5  mov     dword ptr [rsp+88h+var_60], eax
0x18002a8a9  mov     r8, r13
0x18002a8ac  mov     eax, [rbx+60h]
0x18002a8af  mov     dword ptr [rsp+88h+var_68], eax
0x18002a8b3  call    WPP_SF_ddd
0x18002a8b8  mov     r8, [rsp+88h+arg_8]
0x18002a8c0  mov     rcx, rbx
0x18002a8c3  mov     edx, [rsp+88h+arg_0]
0x18002a8ca  call    EapSetWorkingSetUserData
0x18002a8cf  test    eax, eax
0x18002a8d1  jz      short loc_18002A8FD
0x18002a8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8da  cmp     rcx, r12
0x18002a8dd  jz      short loc_18002A8FD
0x18002a8df  test    byte ptr [rcx+44h], 1
0x18002a8e3  jz      short loc_18002A8FD
0x18002a8e5  mov     rcx, [rcx+38h]
0x18002a8e9  mov     edx, 75h ; 'u'
0x18002a8ee  mov     r9d, edi
0x18002a8f1  mov     dword ptr [rsp+88h+var_68], eax
0x18002a8f5  mov     r8, r13
0x18002a8f8  call    WPP_SF_dd
0x18002a8fd  mov     r8, [rsp+88h+arg_8]
0x18002a905  mov     r9d, 1
0x18002a90b  mov     edx, [rsp+88h+arg_0]
0x18002a912  mov     rcx, rbx
0x18002a915  call    EapUpdateMasterUserData
0x18002a91a  mov     ebx, eax
0x18002a91c  test    eax, eax
0x18002a91e  jz      short loc_18002A999
0x18002a920  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a927  cmp     rcx, r12
0x18002a92a  jz      short loc_18002A999
0x18002a92c  test    byte ptr [rcx+44h], 1
0x18002a930  jz      short loc_18002A999
0x18002a932  mov     rcx, [rcx+38h]
0x18002a936  mov     edx, 76h ; 'v'
0x18002a93b  mov     r9d, edi
0x18002a93e  mov     dword ptr [rsp+88h+var_68], eax
0x18002a942  mov     r8, r13
0x18002a945  call    WPP_SF_dd
0x18002a94a  jmp     short loc_18002A999
0x18002a94c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a953  cmp     rcx, r12
0x18002a956  jz      short loc_18002A976
0x18002a958  test    byte ptr [rcx+44h], 1
0x18002a95c  jz      short loc_18002A976
0x18002a95e  mov     rcx, [rcx+38h]
0x18002a962  mov     edx, 77h ; 'w'
0x18002a967  mov     r9d, edi
0x18002a96a  mov     dword ptr [rsp+88h+var_68], eax
0x18002a96e  mov     r8, r13
0x18002a971  call    WPP_SF_dd
0x18002a976  xor     ebx, ebx
0x18002a978  jmp     short loc_18002A999
0x18002a97a  xor     ebx, ebx
0x18002a97c  cmp     rcx, r12
0x18002a97f  jz      short loc_18002A999
0x18002a981  test    byte ptr [rcx+44h], 4
0x18002a985  jz      short loc_18002A999
0x18002a987  mov     rcx, [rcx+38h]
0x18002a98b  lea     edx, [rbx+78h]
0x18002a98e  mov     r9d, edi
0x18002a991  mov     r8, r13
0x18002a994  call    WPP_SF_d
0x18002a999  mov     r8d, 19Eh
0x18002a99f  lea     rdx, aOnexhlpfreemem; "OneXHlpFreeMemory"
0x18002a9a6  lea     rcx, [rsp+88h+arg_8]
0x18002a9ae  call    cs:__imp_FreeMemory
0x18002a9b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9bb  cmp     rcx, r12
0x18002a9be  jz      short loc_18002A9DD
0x18002a9c0  test    dword ptr [rcx+44h], 800h
0x18002a9c7  jz      short loc_18002A9DD
0x18002a9c9  mov     rcx, [rcx+38h]
0x18002a9cd  mov     edx, 79h ; 'y'
0x18002a9d2  mov     r9d, ebx
0x18002a9d5  mov     r8, r13
0x18002a9d8  call    WPP_SF_D
0x18002a9dd  mov     eax, ebx
0x18002a9df  mov     rbx, [rsp+88h+arg_10]
0x18002a9e7  add     rsp, 50h
0x18002a9eb  pop     r15
0x18002a9ed  pop     r14
0x18002a9ef  pop     r13
0x18002a9f1  pop     r12
0x18002a9f3  pop     rdi
0x18002a9f4  pop     rsi
0x18002a9f5  pop     rbp
0x18002a9f6  retn
```
