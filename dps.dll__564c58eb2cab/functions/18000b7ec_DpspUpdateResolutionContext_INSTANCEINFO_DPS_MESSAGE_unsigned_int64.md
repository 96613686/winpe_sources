# DpspUpdateResolutionContext(INSTANCEINFO *,_DPS_MESSAGE *,unsigned __int64)

- ea: `0x18000b7ec`
- end: `0x18000ba0d`
- name: `?DpspUpdateResolutionContext@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@_K@Z`
- size: `545`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *, struct _DPS_MESSAGE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004de4`

## callees

- `0x1800013a0`
- `0x180008dc0`
- `0x180008ea0`
- `0x180009090`
- `0x18000a856`
- `0x18000b7ec`
- `0x18000bc1c`
- `0x18000bcb8`
- `0x18000c90c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b918`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000b946`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000b946`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b90e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b90e`

## string_xrefs

- `0x18000b9ef`: `DpspUpdateResolutionContext`

## pseudocode

```c
__int64 __fastcall DpspUpdateResolutionContext(struct INSTANCEINFO *a1, struct _DPS_MESSAGE *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int Args; // eax
  __int64 v7; // rdx
  __int64 v8; // r10
  size_t v9; // rbp
  int v10; // eax
  int v11; // r8d
  void *v12; // rax
  signed int LastError; // eax
  __int64 v14; // rcx
  _OWORD *v15; // rax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF

  LODWORD(Size) = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v4 = 0;
      WdipCopyGuid((char *)a1 + 40, (char *)a2 + 128);
      v5 = *((_DWORD *)a2 + 36);
      *((_DWORD *)a1 + 23) = v5;
      if ( (v5 & 0x20) != 0 )
        *((_QWORD *)a1 + 15) = *(_QWORD *)((char *)a2 + 148);
      if ( (v5 & 1) != 0 )
      {
        Args = ULongSub(*((_DWORD *)a2 + 31), *((_DWORD *)a2 + 40), (unsigned int *)&Size);
        v4 = Args;
        if ( Args >= 0 )
        {
          v9 = (unsigned int)Size;
          v10 = WdipValidateMessagePayloadRange(v8, v7, (unsigned int)Size);
          v4 = v10;
          if ( v10 >= 0 )
          {
            v12 = (void *)WdipAlloc(v9);
            *((_QWORD *)a1 + 96) = v12;
            if ( !v12 )
            {
              v4 = -2147024882;
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
                (int)L"DpspUpdateResolutionContext",
                2090,
                (int)L"Error = %d",
                14);
              return v4;
            }
            memset_0(v12, 0, v9);
            if ( CopySid(Size, *((PSID *)a1 + 96), (char *)a2 + *((unsigned int *)a2 + 40) + 40) )
              goto LABEL_29;
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            if ( (v4 & 0x80000000) == 0 )
            {
LABEL_29:
              if ( !IsValidSid(*((PSID *)a1 + 96)) )
              {
                v4 = -2147467259;
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
                  (int)L"DpspUpdateResolutionContext",
                  2102,
                  (int)L"Error = %d",
                  5);
                return v4;
              }
              v14 = *((_QWORD *)a1 + 98);
              *((_DWORD *)a1 + 27) = *((_DWORD *)a2 + 39);
              WdipFree(v14);
              *((_QWORD *)a1 + 98) = 0;
              v15 = (_OWORD *)WdipAlloc(32);
              *((_QWORD *)a1 + 98) = v15;
              if ( !v15 )
              {
                v4 = -2147024882;
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
                  (int)L"DpspUpdateResolutionContext",
                  2110,
                  (int)L"Error = %d",
                  14);
                return v4;
              }
              *v15 = 0;
              v15[1] = 0;
              v10 = StringCchCopyW(*((unsigned __int16 **)a1 + 98), 0x7FFFFFFFu, L"Winsta0\\Default");
              v4 = v10;
              if ( v10 >= 0 )
                return v4;
              v11 = 2117;
            }
            else
            {
              LOBYTE(v10) = v4;
              v11 = 2098;
            }
          }
          else
          {
            v11 = 2087;
          }
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
            (int)L"DpspUpdateResolutionContext",
            v11,
            (int)L"Error = %d",
            v10);
          return v4;
        }
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (int)L"DpspUpdateResolutionContext",
          2075,
          (int)L"Error = %d",
          Args);
      }
    }
    else
    {
      v4 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspUpdateResolutionContext",
        2054,
        (int)L"Error = %d",
        87);
    }
  }
  else
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspUpdateResolutionContext",
      2053,
      (int)L"Error = %d",
      87);
  }
  return v4;
}

```

## disassembly

```asm
0x18000b7ec  push    rbx
0x18000b7ee  push    rbp
0x18000b7ef  push    rsi
0x18000b7f0  push    rdi
0x18000b7f1  sub     rsp, 38h
0x18000b7f5  mov     dword ptr [rsp+58h+Size], 0
0x18000b7fd  mov     r10, r8
0x18000b800  mov     rsi, rdx
0x18000b803  mov     rdi, rcx
0x18000b806  test    rcx, rcx
0x18000b809  jnz     short loc_18000B823
0x18000b80b  mov     ebx, 80070057h
0x18000b810  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000b818  mov     r8d, 805h
0x18000b81e  jmp     loc_18000B9E8
0x18000b823  test    rsi, rsi
0x18000b826  jnz     short loc_18000B840
0x18000b828  mov     ebx, 80070057h
0x18000b82d  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000b835  mov     r8d, 806h
0x18000b83b  jmp     loc_18000B9E8
0x18000b840  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18000b844  add     rcx, 28h ; '('
0x18000b848  xor     ebx, ebx
0x18000b84a  call    WdipCopyGuid
0x18000b84f  mov     ecx, [rsi+90h]
0x18000b855  mov     [rdi+5Ch], ecx
0x18000b858  test    cl, 20h
0x18000b85b  jz      short loc_18000B868
0x18000b85d  mov     rax, [rsi+94h]
0x18000b864  mov     [rdi+78h], rax
0x18000b868  test    cl, 1
0x18000b86b  jz      loc_18000BA02
0x18000b871  mov     edx, [rsi+0A0h]; unsigned int
0x18000b877  lea     r8, [rsp+58h+Size]; unsigned int *
0x18000b87c  mov     ecx, [rsi+7Ch]; unsigned int
0x18000b87f  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x18000b884  mov     ebx, eax
0x18000b886  test    eax, eax
0x18000b888  jns     short loc_18000B89C
0x18000b88a  movzx   ecx, ax
0x18000b88d  mov     r8d, 81Bh
0x18000b893  mov     dword ptr [rsp+58h+Args], ecx
0x18000b897  jmp     loc_18000B9E8
0x18000b89c  mov     ebp, dword ptr [rsp+58h+Size]
0x18000b8a0  mov     rcx, r10
0x18000b8a3  mov     r8d, ebp
0x18000b8a6  call    WdipValidateMessagePayloadRange
0x18000b8ab  mov     ebx, eax
0x18000b8ad  test    eax, eax
0x18000b8af  jns     short loc_18000B8BC
0x18000b8b1  mov     r8d, 827h
0x18000b8b7  jmp     loc_18000B9E1
0x18000b8bc  mov     rcx, rbp
0x18000b8bf  call    WdipAlloc
0x18000b8c4  mov     [rdi+300h], rax
0x18000b8cb  test    rax, rax
0x18000b8ce  jnz     short loc_18000B8E8
0x18000b8d0  mov     ebx, 8007000Eh
0x18000b8d5  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000b8dd  mov     r8d, 82Ah
0x18000b8e3  jmp     loc_18000B9E8
0x18000b8e8  mov     r8, rbp; Size
0x18000b8eb  xor     edx, edx; Val
0x18000b8ed  mov     rcx, rax; void *
0x18000b8f0  call    memset_0
0x18000b8f5  mov     r8d, [rsi+0A0h]
0x18000b8fc  mov     rdx, [rdi+300h]; pDestinationSid
0x18000b903  add     r8, 28h ; '('
0x18000b907  mov     ecx, dword ptr [rsp+58h+Size]; nDestinationSidLength
0x18000b90b  add     r8, rsi; pSourceSid
0x18000b90e  call    cs:__imp_CopySid
0x18000b914  test    eax, eax
0x18000b916  jnz     short loc_18000B93F
0x18000b918  call    cs:__imp_GetLastError
0x18000b91e  mov     ebx, eax
0x18000b920  test    eax, eax
0x18000b922  jle     short loc_18000B92D
0x18000b924  movzx   ebx, ax
0x18000b927  or      ebx, 80070000h
0x18000b92d  test    ebx, ebx
0x18000b92f  jns     short loc_18000B93F
0x18000b931  movzx   eax, bx
0x18000b934  mov     r8d, 832h
0x18000b93a  jmp     loc_18000B9E4
0x18000b93f  mov     rcx, [rdi+300h]; pSid
0x18000b946  call    cs:__imp_IsValidSid
0x18000b94c  test    eax, eax
0x18000b94e  jnz     short loc_18000B968
0x18000b950  mov     ebx, 80004005h
0x18000b955  mov     dword ptr [rsp+58h+Args], 4005h
0x18000b95d  mov     r8d, 836h
0x18000b963  jmp     loc_18000B9E8
0x18000b968  mov     eax, [rsi+9Ch]
0x18000b96e  mov     rcx, [rdi+310h]
0x18000b975  mov     [rdi+6Ch], eax
0x18000b978  call    WdipFree
0x18000b97d  mov     ecx, 20h ; ' '
0x18000b982  mov     qword ptr [rdi+310h], 0
0x18000b98d  call    WdipAlloc
0x18000b992  mov     [rdi+310h], rax
0x18000b999  test    rax, rax
0x18000b99c  jnz     short loc_18000B9B3
0x18000b99e  mov     ebx, 8007000Eh
0x18000b9a3  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000b9ab  mov     r8d, 83Eh
0x18000b9b1  jmp     short loc_18000B9E8
0x18000b9b3  xorps   xmm0, xmm0
0x18000b9b6  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x18000b9bd  movups  xmmword ptr [rax], xmm0
0x18000b9c0  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000b9c5  movups  xmmword ptr [rax+10h], xmm0
0x18000b9c9  mov     rcx, [rdi+310h]; unsigned __int16 *
0x18000b9d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b9d5  mov     ebx, eax
0x18000b9d7  test    eax, eax
0x18000b9d9  jns     short loc_18000BA02
0x18000b9db  mov     r8d, 845h; int
0x18000b9e1  movzx   eax, ax
0x18000b9e4  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000b9e8  lea     r9, aErrorD; "Error = %d"
0x18000b9ef  lea     rdx, aDpspupdatereso; "DpspUpdateResolutionContext"
0x18000b9f6  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b9fd  call    WdipTraceError
0x18000ba02  mov     eax, ebx
0x18000ba04  add     rsp, 38h
0x18000ba08  pop     rdi
0x18000ba09  pop     rsi
0x18000ba0a  pop     rbp
0x18000ba0b  pop     rbx
0x18000ba0c  retn
```
