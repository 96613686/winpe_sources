# DhcpEnumClasses

- ea: `0x18003eed0`
- end: `0x18003f134`
- name: `DhcpEnumClasses`
- size: `612`
- prototype: `DWORD __stdcall(LPWSTR ServerIpAddress, DWORD ReservedMustBeZero, DHCP_RESUME_HANDLE *ResumeHandle, DWORD PreferredMaximum, LPDHCP_CLASS_INFO_ARRAY *ClassInfoArray, DWORD *nRead, DWORD *nTotal)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180043660`

## callees

- `0x180001670`
- `0x180012c0c`
- `0x18003eed0`
- `0x1800463d4`
- `0x18004be38`
- `0x18004c33c`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d958`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003f0f3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003f0f3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003efeb`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003efeb`
- `RPCRT4!I_RpcExceptionFilter` at `0x180047fc4`
- `RPCRT4!I_RpcExceptionFilter` at `0x180047fc4`
- `WS2_32!__imp_ntohl` at `0x18003f07b`
- `WS2_32!__imp_ntohl` at `0x18003f0cd`
- `WS2_32!__imp_ntohl` at `0x18003f07b`
- `WS2_32!__imp_ntohl` at `0x18003f0cd`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
DWORD __stdcall DhcpEnumClasses(
        LPWSTR ServerIpAddress,
        DWORD ReservedMustBeZero,
        DHCP_RESUME_HANDLE *ResumeHandle,
        DWORD PreferredMaximum,
        LPDHCP_CLASS_INFO_ARRAY *ClassInfoArray,
        DWORD *nRead,
        DWORD *nTotal)
{
  __int64 v7; // r14
  __int64 v9; // rbx
  DWORD v10; // ebx
  DWORD v11; // eax
  u_long *v12; // r15
  u_long v13; // eax
  u_long v14; // ebx
  __int128 v16; // [rsp+48h] [rbp-60h] BYREF
  _QWORD v17[10]; // [rsp+58h] [rbp-50h] BYREF
  int v18; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+10h] BYREF
  DHCP_RESUME_HANDLE *v20; // [rsp+C0h] [rbp+18h]
  __int64 v21; // [rsp+C8h] [rbp+20h]

  v21 = *(_QWORD *)&PreferredMaximum;
  v20 = ResumeHandle;
  v18 = (int)ServerIpAddress;
  v7 = *(_QWORD *)&PreferredMaximum;
  v9 = *(_QWORD *)&ReservedMustBeZero;
  memset(v17, 0, 32);
  v16 = 0;
  LOBYTE(v18) = 77;
  v19 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_LSqq(
      (_DWORD)ServerIpAddress,
      ReservedMustBeZero,
      (_DWORD)ResumeHandle,
      0,
      ReservedMustBeZero,
      (char)ResumeHandle,
      PreferredMaximum);
  if ( !v9 || !ResumeHandle )
  {
    v10 = 87;
    goto LABEL_26;
  }
  if ( !v7 && *ResumeHandle )
  {
    v10 = 13;
    goto LABEL_26;
  }
  LOBYTE(v18) = 77;
  LODWORD(v17[0]) = 1;
  v17[1] = &v18;
  v10 = DhcpAdapterNameToIfId(v9, &v19);
  if ( !v10 )
  {
    v11 = RpcSrvRequestParams(0, (unsigned int)&v19, 0, 0, (__int64)v17, (__int64)&v16);
    v10 = v11;
    if ( !v11 )
    {
      if ( !(_DWORD)v16 )
        goto LABEL_26;
      if ( (unsigned int)v16 >= 0xC )
      {
        v12 = (u_long *)*((_QWORD *)&v16 + 1);
        v13 = ntohl(*(_DWORD *)(*((_QWORD *)&v16 + 1) + 8LL));
        v14 = v13;
        if ( v13 )
        {
          if ( (unsigned int)v16 >= (unsigned __int64)v13 + 12 )
          {
            *v12 = ntohl(*v12);
            v10 = ConvertFromBufferToClassInfo(v12 + 3, v14, v7, ResumeHandle);
            goto LABEL_26;
          }
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_Dd(1025, 80, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, (unsigned int)v16, v13 + 12);
        }
        else if ( (xmmword_1800616A0 & 2) != 0 )
        {
          WPP_SF_(1025, 79, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids);
        }
      }
      else if ( (xmmword_1800616A0 & 2) != 0 )
      {
        WPP_SF_Dd(1025, 78, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, (unsigned int)v16, 12);
      }
      v10 = 1359;
      goto LABEL_26;
    }
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 77, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, v11);
  }
LABEL_26:
  if ( *((_QWORD *)&v16 + 1) )
    LocalFree(*((HLOCAL *)&v16 + 1));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 81, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, v19, v10);
  return v10;
}

```

## disassembly

```asm
0x18003eed0  mov     rax, rsp
0x18003eed3  mov     [rax+20h], r9
0x18003eed7  mov     [rax+18h], r8
0x18003eedb  mov     [rax+8], ecx
0x18003eede  push    rbx
0x18003eedf  push    rsi
0x18003eee0  push    r14
0x18003eee2  push    r15
0x18003eee4  sub     rsp, 88h
0x18003eeeb  mov     r14, r9
0x18003eeee  mov     rsi, r8
0x18003eef1  mov     rbx, rdx
0x18003eef4  xorps   xmm0, xmm0
0x18003eef7  movups  xmmword ptr [rax-50h], xmm0
0x18003eefb  movups  xmmword ptr [rax-40h], xmm0
0x18003eeff  movups  xmmword ptr [rax-60h], xmm0
0x18003ef03  mov     byte ptr [rax+8], 4Dh ; 'M'
0x18003ef07  mov     qword ptr [rax+10h], 0
0x18003ef0f  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003ef16  jz      short loc_18003EF2D
0x18003ef18  mov     [rax-78h], r9
0x18003ef1c  mov     [rax-80h], r8
0x18003ef20  mov     [rsp+0A8h+var_88], rdx
0x18003ef25  xor     r9d, r9d
0x18003ef28  call    WPP_SF_LSqq
0x18003ef2d  test    rbx, rbx
0x18003ef30  jnz     short loc_18003EF3C
0x18003ef32  mov     ebx, 57h ; 'W'
0x18003ef37  jmp     loc_18003F0E9
0x18003ef3c  test    rsi, rsi
0x18003ef3f  jz      short loc_18003EF32
0x18003ef41  test    r14, r14
0x18003ef44  jnz     short loc_18003EF54
0x18003ef46  cmp     [rsi], r14d
0x18003ef49  jz      short loc_18003EF54
0x18003ef4b  lea     ebx, [r14+0Dh]
0x18003ef4f  jmp     loc_18003F0E9
0x18003ef54  mov     byte ptr [rsp+0A8h+arg_0], 4Dh ; 'M'
0x18003ef5c  mov     [rsp+0A8h+var_50], 1
0x18003ef64  lea     rax, [rsp+0A8h+arg_0]
0x18003ef6c  mov     [rsp+0A8h+var_48], rax
0x18003ef71  lea     rdx, [rsp+0A8h+arg_8]
0x18003ef79  mov     rcx, rbx
0x18003ef7c  call    DhcpAdapterNameToIfId
0x18003ef81  mov     ebx, eax
0x18003ef83  test    eax, eax
0x18003ef85  jnz     loc_18003F0E9
0x18003ef8b  lea     rax, [rsp+0A8h+var_60]
0x18003ef90  mov     [rsp+0A8h+var_80], rax
0x18003ef95  lea     rax, [rsp+0A8h+var_50]
0x18003ef9a  mov     [rsp+0A8h+var_88], rax
0x18003ef9f  xor     r9d, r9d
0x18003efa2  xor     r8d, r8d
0x18003efa5  lea     rdx, [rsp+0A8h+arg_8]
0x18003efad  xor     ecx, ecx
0x18003efaf  call    RpcSrvRequestParams
0x18003efb4  mov     ebx, eax
0x18003efb6  mov     [rsp+0A8h+var_68], eax
0x18003efba  test    eax, eax
0x18003efbc  jz      short loc_18003F028
0x18003efbe  test    byte ptr cs:xmmword_1800616A0, 2
0x18003efc5  jz      short loc_18003EFE0
0x18003efc7  mov     edx, 4Dh ; 'M'
0x18003efcc  mov     ecx, 401h
0x18003efd1  mov     r9d, eax
0x18003efd4  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003efdb  call    WPP_SF_D
0x18003efe0  jmp     loc_18003F0E9
0x18003efe5  mov     ebx, eax
0x18003efe7  mov     [rsp+0A8h+var_68], eax
0x18003efeb  call    cs:__imp_GetCommandLineW
0x18003eff1  test    byte ptr cs:xmmword_1800616A0, 2
0x18003eff8  jz      short loc_18003F018
0x18003effa  mov     edx, 0Dh
0x18003efff  mov     ecx, 401h
0x18003f004  mov     [rsp+0A8h+var_88], rax
0x18003f009  mov     r9d, ebx
0x18003f00c  lea     r8, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids
0x18003f013  call    WPP_SF_DS
0x18003f018  mov     r14, [rsp+0A8h+arg_18]
0x18003f020  mov     rsi, [rsp+0A8h+arg_10]
0x18003f028  test    ebx, ebx
0x18003f02a  jnz     loc_18003F0E9
0x18003f030  cmp     [rsp+0A8h+var_60], ebx
0x18003f034  jz      loc_18003F0E9
0x18003f03a  cmp     [rsp+0A8h+var_60], 0Ch
0x18003f03f  jnb     short loc_18003F072
0x18003f041  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f048  jz      short loc_18003F06B
0x18003f04a  lea     edx, [rbx+4Eh]
0x18003f04d  mov     dword ptr [rsp+0A8h+var_88], 0Ch
0x18003f055  mov     ecx, 401h
0x18003f05a  mov     r9d, [rsp+0A8h+var_60]
0x18003f05f  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f066  call    WPP_SF_Dd
0x18003f06b  mov     ebx, 54Fh
0x18003f070  jmp     short loc_18003F0E9
0x18003f072  mov     r15, [rsp+0A8h+hMem]
0x18003f077  mov     ecx, [r15+8]; netlong
0x18003f07b  call    cs:__imp_ntohl
0x18003f081  mov     ebx, eax
0x18003f083  test    eax, eax
0x18003f085  jnz     short loc_18003F0A6
0x18003f087  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f08e  jz      short loc_18003F06B
0x18003f090  lea     edx, [rax+4Fh]
0x18003f093  mov     ecx, 401h
0x18003f098  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f09f  call    WPP_SF_
0x18003f0a4  jmp     short loc_18003F06B
0x18003f0a6  lea     rcx, [rbx+0Ch]
0x18003f0aa  mov     eax, [rsp+0A8h+var_60]
0x18003f0ae  cmp     rax, rcx
0x18003f0b1  jnb     short loc_18003F0CA
0x18003f0b3  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f0ba  jz      short loc_18003F06B
0x18003f0bc  lea     eax, [rbx+0Ch]
0x18003f0bf  mov     edx, 50h ; 'P'
0x18003f0c4  mov     dword ptr [rsp+0A8h+var_88], eax
0x18003f0c8  jmp     short loc_18003F055
0x18003f0ca  mov     ecx, [r15]; netlong
0x18003f0cd  call    cs:__imp_ntohl
0x18003f0d3  mov     [r15], eax
0x18003f0d6  lea     rcx, [r15+0Ch]
0x18003f0da  mov     r9, rsi
0x18003f0dd  mov     r8, r14
0x18003f0e0  mov     edx, ebx
0x18003f0e2  call    ConvertFromBufferToClassInfo
0x18003f0e7  mov     ebx, eax
0x18003f0e9  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18003f0ee  test    rcx, rcx
0x18003f0f1  jz      short loc_18003F0F9
0x18003f0f3  call    cs:__imp_LocalFree
0x18003f0f9  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003f100  jz      short loc_18003F124
0x18003f102  mov     edx, 51h ; 'Q'
0x18003f107  mov     ecx, 404h
0x18003f10c  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18003f110  mov     r9, [rsp+0A8h+arg_8]
0x18003f118  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f11f  call    WPP_SF_qD
0x18003f124  mov     eax, ebx
0x18003f126  add     rsp, 88h
0x18003f12d  pop     r15
0x18003f12f  pop     r14
0x18003f131  pop     rsi
0x18003f132  pop     rbx
0x18003f133  retn
0x180047fb6  push    rbp
0x180047fb8  sub     rsp, 40h
0x180047fbc  mov     rbp, rdx
0x180047fbf  mov     rcx, [rcx]
0x180047fc2  mov     ecx, [rcx]; ExceptionCode
0x180047fc4  call    cs:__imp_I_RpcExceptionFilter
0x180047fca  nop
0x180047fcb  add     rsp, 40h
0x180047fcf  pop     rbp
0x180047fd0  retn
```
