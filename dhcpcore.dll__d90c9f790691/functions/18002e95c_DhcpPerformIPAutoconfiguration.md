# DhcpPerformIPAutoconfiguration

- ea: `0x18002e95c`
- end: `0x18002ec2d`
- name: `DhcpPerformIPAutoconfiguration`
- size: `721`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003c064`

## callees

- `0x1800207ec`
- `0x18002e95c`
- `0x18002ec34`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ea86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002eab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ead6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ea86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002eab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ead6`
- `WS2_32!__imp_inet_addr` at `0x18002ea2d`
- `WS2_32!__imp_inet_addr` at `0x18002ea3e`
- `WS2_32!__imp_inet_addr` at `0x18002ea2d`
- `WS2_32!__imp_inet_addr` at `0x18002ea3e`

## pseudocode

```c
__int64 __fastcall DhcpPerformIPAutoconfiguration(__int64 a1)
{
  unsigned int v1; // edi
  unsigned int v2; // r15d
  unsigned int v3; // r12d
  __int64 v4; // rsi
  IPAddr v5; // ebp
  int v6; // ecx
  int v7; // edx
  int v8; // eax
  int v9; // r14d
  void *v10; // r13
  unsigned int v11; // ebx
  ULONGLONG TickCount64; // rcx
  unsigned int v13; // ebx
  unsigned int v14; // esi
  int v15; // edx
  int v17; // [rsp+20h] [rbp-68h]
  int v18; // [rsp+30h] [rbp-58h]
  int v20; // [rsp+98h] [rbp+10h] BYREF
  size_t Size; // [rsp+A0h] [rbp+18h]
  int v22; // [rsp+A8h] [rbp+20h]

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v4 = a1;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids);
  v5 = *(_DWORD *)(v4 + 416);
  v6 = *(_DWORD *)(v4 + 424);
  v7 = *(_DWORD *)(v4 + 420);
  v8 = *(_DWORD *)(v4 + 96);
  v9 = *(_DWORD *)(v4 + 428);
  v10 = *(void **)(v4 + 88);
  v18 = v6;
  v22 = v7;
  LODWORD(Size) = v8;
  v20 = v9;
  if ( v5 )
    goto LABEL_6;
  v5 = GrandHashing((_DWORD)v10, v8, (unsigned int)&v20, v6, v7);
  while ( 1 )
  {
    v9 = v20;
LABEL_6:
    if ( v2 >= 0x64 )
    {
LABEL_21:
      if ( v1 )
      {
        v1 = 4100;
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_(1025, 15, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids);
      }
      goto LABEL_24;
    }
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 11, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids, v5);
    v11 = v5 & inet_addr("255.255.255.0");
    if ( v11 != inet_addr("169.254.255.0") )
      break;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 12, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids);
    ++v2;
LABEL_20:
    v15 = Size;
    v17 = v22;
    *(_DWORD *)(v4 + 428) = v9;
    v5 = GrandHashing((_DWORD)v10, v15, (unsigned int)&v20, v18, v17);
    if ( v3 >= 0xA )
      goto LABEL_21;
  }
  *(_DWORD *)(v4 + 796) = 1;
  *(_DWORD *)(v4 + 120) = v5;
  *(_DWORD *)(v4 + 440) = 0;
  *(_QWORD *)(v4 + 448) = GetTickCount64() / 0x3E8;
  *(_QWORD *)(v4 + 456) = GetTickCount64() / 0x3E8;
  TickCount64 = GetTickCount64();
  *(_QWORD *)(v4 + 472) = 0xFFFFFFFFLL;
  *(_QWORD *)(v4 + 464) = TickCount64 / 0x3E8;
  v13 = 0;
  v14 = Size;
  do
  {
    if ( v1 == 4100 )
      break;
    ++v13;
    v1 = CheckForAddressConflict(v5, v10, v14);
  }
  while ( v13 < 2 );
  v4 = a1;
  if ( !v1 )
    goto LABEL_24;
  if ( v1 == 4100 )
  {
    ++v3;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 14, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids, v5);
    goto LABEL_20;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_(1025, 13, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids);
  v1 = 0;
LABEL_24:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 16, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18002e95c  mov     [rsp+arg_0], rcx
0x18002e961  push    rbx
0x18002e962  push    rbp
0x18002e963  push    rsi
0x18002e964  push    rdi
0x18002e965  push    r12
0x18002e967  push    r13
0x18002e969  push    r14
0x18002e96b  push    r15
0x18002e96d  sub     rsp, 48h
0x18002e971  xor     edi, edi
0x18002e973  xor     r15d, r15d
0x18002e976  xor     r12d, r12d
0x18002e979  mov     rsi, rcx
0x18002e97c  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002e983  jz      short loc_18002E999
0x18002e985  lea     edx, [rdi+0Ah]
0x18002e988  mov     ecx, 404h
0x18002e98d  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002e994  call    WPP_SF_
0x18002e999  mov     ebp, [rsi+1A0h]
0x18002e99f  mov     ecx, [rsi+1A8h]
0x18002e9a5  mov     edx, [rsi+1A4h]
0x18002e9ab  mov     eax, [rsi+60h]
0x18002e9ae  mov     r14d, [rsi+1ACh]
0x18002e9b5  mov     r13, [rsi+58h]
0x18002e9b9  mov     [rsp+88h+var_58], ecx
0x18002e9bd  mov     [rsp+88h+arg_18], edx
0x18002e9c4  mov     dword ptr [rsp+88h+Size], eax
0x18002e9cb  mov     [rsp+88h+arg_8], r14d
0x18002e9d3  test    ebp, ebp
0x18002e9d5  jnz     short loc_18002E9FA
0x18002e9d7  mov     [rsp+88h+var_68], edx
0x18002e9db  lea     r8, [rsp+88h+arg_8]
0x18002e9e3  mov     r9d, ecx
0x18002e9e6  mov     edx, eax
0x18002e9e8  mov     rcx, r13
0x18002e9eb  call    GrandHashing
0x18002e9f0  mov     ebp, eax
0x18002e9f2  mov     r14d, [rsp+88h+arg_8]
0x18002e9fa  cmp     r15d, 64h ; 'd'
0x18002e9fe  jnb     loc_18002EBAD
0x18002ea04  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002ea0b  jz      short loc_18002EA26
0x18002ea0d  mov     edx, 0Bh
0x18002ea12  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002ea19  mov     ecx, 404h
0x18002ea1e  mov     r9d, ebp
0x18002ea21  call    WPP_SF_D
0x18002ea26  lea     rcx, a2552552550; "255.255.255.0"
0x18002ea2d  call    cs:__imp_inet_addr
0x18002ea33  mov     ebx, eax
0x18002ea35  lea     rcx, a1692542550; "169.254.255.0"
0x18002ea3c  and     ebx, ebp
0x18002ea3e  call    cs:__imp_inet_addr
0x18002ea44  cmp     ebx, eax
0x18002ea46  jnz     short loc_18002EA6F
0x18002ea48  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002ea4f  jz      short loc_18002EA67
0x18002ea51  mov     edx, 0Ch
0x18002ea56  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002ea5d  mov     ecx, 404h
0x18002ea62  call    WPP_SF_
0x18002ea67  inc     r15d
0x18002ea6a  jmp     loc_18002EB73
0x18002ea6f  mov     dword ptr [rsi+31Ch], 1
0x18002ea79  mov     [rsi+78h], ebp
0x18002ea7c  mov     dword ptr [rsi+1B8h], 0
0x18002ea86  call    cs:__imp_GetTickCount64
0x18002ea8c  mov     rcx, rax
0x18002ea8f  mov     rbx, 624DD2F1A9FBE77h
0x18002ea99  mov     rax, rbx
0x18002ea9c  mul     rcx
0x18002ea9f  sub     rcx, rdx
0x18002eaa2  shr     rcx, 1
0x18002eaa5  add     rcx, rdx
0x18002eaa8  shr     rcx, 9
0x18002eaac  mov     [rsi+1C0h], rcx
0x18002eab3  call    cs:__imp_GetTickCount64
0x18002eab9  mov     rcx, rax
0x18002eabc  mov     rax, rbx
0x18002eabf  mul     rcx
0x18002eac2  sub     rcx, rdx
0x18002eac5  shr     rcx, 1
0x18002eac8  add     rcx, rdx
0x18002eacb  shr     rcx, 9
0x18002eacf  mov     [rsi+1C8h], rcx
0x18002ead6  call    cs:__imp_GetTickCount64
0x18002eadc  mov     rcx, rax
0x18002eadf  mov     rax, rbx
0x18002eae2  mul     rcx
0x18002eae5  mov     eax, 0FFFFFFFFh
0x18002eaea  sub     rcx, rdx
0x18002eaed  mov     [rsi+1D8h], rax
0x18002eaf4  shr     rcx, 1
0x18002eaf7  add     rcx, rdx
0x18002eafa  shr     rcx, 9
0x18002eafe  mov     [rsi+1D0h], rcx
0x18002eb05  xor     ebx, ebx
0x18002eb07  mov     esi, dword ptr [rsp+88h+Size]
0x18002eb0e  cmp     edi, 1004h
0x18002eb14  jz      short loc_18002EB32
0x18002eb16  mov     r9d, 2
0x18002eb1c  mov     r8d, esi; Size
0x18002eb1f  mov     rdx, r13; Buf2
0x18002eb22  mov     ecx, ebp; DestIP
0x18002eb24  call    CheckForAddressConflict
0x18002eb29  inc     ebx
0x18002eb2b  mov     edi, eax
0x18002eb2d  cmp     ebx, 2
0x18002eb30  jb      short loc_18002EB0E
0x18002eb32  mov     rsi, [rsp+88h+arg_0]
0x18002eb3a  test    edi, edi
0x18002eb3c  jz      loc_18002EBD5
0x18002eb42  cmp     edi, 1004h
0x18002eb48  jnz     loc_18002EC0A
0x18002eb4e  inc     r12d
0x18002eb51  test    byte ptr cs:xmmword_1800616A0, 2
0x18002eb58  jz      short loc_18002EB73
0x18002eb5a  mov     edx, 0Eh
0x18002eb5f  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002eb66  mov     ecx, 401h
0x18002eb6b  mov     r9d, ebp
0x18002eb6e  call    WPP_SF_D
0x18002eb73  mov     eax, [rsp+88h+arg_18]
0x18002eb7a  lea     r8, [rsp+88h+arg_8]
0x18002eb82  mov     r9d, [rsp+88h+var_58]
0x18002eb87  mov     rcx, r13
0x18002eb8a  mov     edx, dword ptr [rsp+88h+Size]
0x18002eb91  mov     [rsp+88h+var_68], eax
0x18002eb95  mov     [rsi+1ACh], r14d
0x18002eb9c  call    GrandHashing
0x18002eba1  mov     ebp, eax
0x18002eba3  cmp     r12d, 0Ah
0x18002eba7  jb      loc_18002E9F2
0x18002ebad  test    edi, edi
0x18002ebaf  jz      short loc_18002EBD5
0x18002ebb1  mov     edi, 1004h
0x18002ebb6  test    byte ptr cs:xmmword_1800616A0, 2
0x18002ebbd  jz      short loc_18002EBD5
0x18002ebbf  mov     edx, 0Fh
0x18002ebc4  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002ebcb  mov     ecx, 401h
0x18002ebd0  call    WPP_SF_
0x18002ebd5  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002ebdc  jz      short loc_18002EBF7
0x18002ebde  mov     edx, 10h
0x18002ebe3  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002ebea  mov     ecx, 404h
0x18002ebef  mov     r9d, edi
0x18002ebf2  call    WPP_SF_D
0x18002ebf7  mov     eax, edi
0x18002ebf9  add     rsp, 48h
0x18002ebfd  pop     r15
0x18002ebff  pop     r14
0x18002ec01  pop     r13
0x18002ec03  pop     r12
0x18002ec05  pop     rdi
0x18002ec06  pop     rsi
0x18002ec07  pop     rbp
0x18002ec08  pop     rbx
0x18002ec09  retn
0x18002ec0a  test    byte ptr cs:xmmword_1800616A0, 2
0x18002ec11  jz      short loc_18002EC29
0x18002ec13  mov     edx, 0Dh
0x18002ec18  lea     r8, WPP_86b4c3d7cf6b376243f8af02b7793002_Traceguids
0x18002ec1f  mov     ecx, 401h
0x18002ec24  call    WPP_SF_
0x18002ec29  xor     edi, edi
0x18002ec2b  jmp     short loc_18002EBD5
```
