# FillInUnimodemParams

- ea: `0x180011184`
- end: `0x18001139d`
- name: `FillInUnimodemParams`
- size: `537`
- prototype: `DWORD __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014f2c`

## callees

- `0x180011184`
- `0x180015a94`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800111e9`
- `msvcrt!_stricmp` at `0x180011207`
- `msvcrt!_stricmp` at `0x180011225`
- `msvcrt!_stricmp` at `0x180011259`
- `msvcrt!_stricmp` at `0x180011275`
- `msvcrt!_stricmp` at `0x1800111e9`
- `msvcrt!_stricmp` at `0x180011207`
- `msvcrt!_stricmp` at `0x180011225`
- `msvcrt!_stricmp` at `0x180011259`
- `msvcrt!_stricmp` at `0x180011275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011312`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x180011308`
- `api-ms-win-core-comm-l1-1-0!GetCommState` at `0x180011308`
- `api-ms-win-core-comm-l1-1-0!SetCommState` at `0x180011365`
- `api-ms-win-core-comm-l1-1-0!SetCommState` at `0x180011365`

## pseudocode

```c
DWORD __fastcall FillInUnimodemParams(__int64 a1, _DWORD *a2)
{
  char v3; // r12
  int v4; // esi
  unsigned __int16 v5; // bp
  const char *v7; // rbx
  unsigned int v8; // edi
  char v9; // r13
  _BYTE *v10; // r10
  __int64 v11; // r9
  __int64 v12; // r8
  _BYTE *v13; // rdx
  _BYTE *v14; // rax
  void *v15; // rcx
  BYTE ByteSize; // cl
  BYTE Parity; // cl
  BYTE StopBits; // cl
  char v20; // [rsp+20h] [rbp-68h]
  _DCB DCB; // [rsp+28h] [rbp-60h] BYREF

  v3 = -34;
  v4 = 0;
  v5 = 0;
  v7 = (const char *)(a2 + 2);
  v8 = -16843010;
  v9 = -34;
  v20 = -34;
  memset(&DCB, 0, sizeof(DCB));
  if ( *a2 )
  {
    while ( 1 )
    {
      if ( !_stricmp(v7, "WordSize") )
      {
        v3 = ValueToNum(v7);
      }
      else if ( !_stricmp(v7, "Parity") )
      {
        v9 = ValueToNum(v7);
      }
      else
      {
        if ( _stricmp(v7, "StopBits") )
        {
          if ( !_stricmp(v7, "PhoneNumber") )
          {
            v8 = 0;
          }
          else
          {
            if ( _stricmp(v7, "ConnectBps") )
              return 604;
            v8 = 1;
          }
LABEL_14:
          if ( *((_DWORD *)v7 + 8) != 1 )
            return 604;
          v10 = (_BYTE *)*((_QWORD *)v7 + 6);
          v11 = 2147483646;
          v12 = 100;
          v13 = (_BYTE *)(a1 + 100LL * v8 + 260);
          do
          {
            if ( !v11 )
              break;
            if ( !*v10 )
              break;
            *v13++ = *v10++;
            --v11;
            --v12;
          }
          while ( v12 );
          v14 = v13 - 1;
          if ( v12 )
            v14 = v13;
          *v14 = 0;
          goto LABEL_22;
        }
        v20 = ValueToNum(v7);
      }
      v4 = 1;
      if ( v8 != -16843010 )
        goto LABEL_14;
LABEL_22:
      ++v5;
      v7 += 56;
      if ( (unsigned int)v5 >= *a2 )
      {
        if ( v4 )
        {
          v15 = *(void **)(a1 + 888);
          if ( v15 != (void *)-1LL )
          {
            if ( !GetCommState(v15, &DCB) )
              return GetLastError();
            ByteSize = DCB.ByteSize;
            if ( v3 != -34 )
              ByteSize = v3;
            DCB.ByteSize = ByteSize;
            Parity = DCB.Parity;
            if ( v9 != -34 )
              Parity = v9;
            DCB.Parity = Parity;
            StopBits = DCB.StopBits;
            if ( v20 != -34 )
              StopBits = v20;
            DCB.StopBits = StopBits;
            if ( !SetCommState(*(HANDLE *)(a1 + 888), &DCB) )
              return GetLastError();
          }
        }
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011184  mov     [rsp+arg_10], rbx
0x180011189  push    rbp
0x18001118a  push    rsi
0x18001118b  push    rdi
0x18001118c  push    r12
0x18001118e  push    r13
0x180011190  push    r14
0x180011192  push    r15
0x180011194  sub     rsp, 50h
0x180011198  mov     rax, cs:__security_cookie
0x18001119f  xor     rax, rsp
0x1800111a2  mov     [rsp+88h+var_40], rax
0x1800111a7  mov     r15, rdx
0x1800111aa  mov     r12b, 0DEh
0x1800111ad  xorps   xmm0, xmm0
0x1800111b0  xor     eax, eax
0x1800111b2  xor     esi, esi
0x1800111b4  xor     ebp, ebp
0x1800111b6  mov     dl, r12b
0x1800111b9  mov     r14, rcx
0x1800111bc  lea     rbx, [r15+8]
0x1800111c0  mov     edi, 0FEFEFEFEh
0x1800111c5  mov     r13b, r12b
0x1800111c8  mov     dword ptr [rsp+88h+var_68], edx
0x1800111cc  movups  xmmword ptr [rsp+88h+DCB.DCBlength], xmm0
0x1800111d1  movups  xmmword ptr [rsp+88h+DCB.wReserved], xmm0
0x1800111d6  cmp     [r15], eax
0x1800111d9  jbe     loc_18001136F
0x1800111df  lea     rdx, aWordsize; "WordSize"
0x1800111e6  mov     rcx, rbx; String1
0x1800111e9  call    cs:__imp__stricmp
0x1800111ef  mov     rcx, rbx; String1
0x1800111f2  test    eax, eax
0x1800111f4  jnz     short loc_180011200
0x1800111f6  call    ValueToNum
0x1800111fb  mov     r12d, eax
0x1800111fe  jmp     short loc_18001123B
0x180011200  lea     rdx, aParity; "Parity"
0x180011207  call    cs:__imp__stricmp
0x18001120d  mov     rcx, rbx; String1
0x180011210  test    eax, eax
0x180011212  jnz     short loc_18001121E
0x180011214  call    ValueToNum
0x180011219  mov     r13d, eax
0x18001121c  jmp     short loc_18001123B
0x18001121e  lea     rdx, aStopbits; "StopBits"
0x180011225  call    cs:__imp__stricmp
0x18001122b  mov     rcx, rbx; String1
0x18001122e  test    eax, eax
0x180011230  jnz     short loc_180011252
0x180011232  call    ValueToNum
0x180011237  mov     dword ptr [rsp+88h+var_68], eax
0x18001123b  mov     r11d, 1
0x180011241  mov     esi, r11d
0x180011244  cmp     edi, 0FEFEFEFEh
0x18001124a  jz      loc_1800112DE
0x180011250  jmp     short loc_18001128A
0x180011252  lea     rdx, aPhonenumber; "PhoneNumber"
0x180011259  call    cs:__imp__stricmp
0x18001125f  test    eax, eax
0x180011261  jnz     short loc_18001126B
0x180011263  xor     edi, edi
0x180011265  lea     r11d, [rax+1]
0x180011269  jmp     short loc_18001128A
0x18001126b  lea     rdx, aConnectbps; "ConnectBps"
0x180011272  mov     rcx, rbx; String1
0x180011275  call    cs:__imp__stricmp
0x18001127b  test    eax, eax
0x18001127d  jnz     loc_180011396
0x180011283  lea     r11d, [rax+1]
0x180011287  mov     edi, r11d
0x18001128a  cmp     [rbx+20h], r11d
0x18001128e  jnz     loc_180011396
0x180011294  mov     r10, [rbx+30h]
0x180011298  mov     r9d, 7FFFFFFEh
0x18001129e  mov     eax, edi
0x1800112a0  mov     r8d, 64h ; 'd'
0x1800112a6  imul    rdx, rax, 64h ; 'd'
0x1800112aa  add     rdx, 104h
0x1800112b1  add     rdx, r14
0x1800112b4  test    r9, r9
0x1800112b7  jz      short loc_1800112D0
0x1800112b9  mov     al, [r10]
0x1800112bc  test    al, al
0x1800112be  jz      short loc_1800112D0
0x1800112c0  mov     [rdx], al
0x1800112c2  add     r10, r11
0x1800112c5  add     rdx, r11
0x1800112c8  sub     r9, r11
0x1800112cb  sub     r8, r11
0x1800112ce  jnz     short loc_1800112B4
0x1800112d0  test    r8, r8
0x1800112d3  lea     rax, [rdx-1]
0x1800112d7  cmovnz  rax, rdx
0x1800112db  mov     byte ptr [rax], 0
0x1800112de  add     bp, r11w
0x1800112e2  add     rbx, 38h ; '8'
0x1800112e6  movzx   eax, bp
0x1800112e9  cmp     eax, [r15]
0x1800112ec  jb      loc_1800111DF
0x1800112f2  test    esi, esi
0x1800112f4  jz      short loc_18001136F
0x1800112f6  mov     rcx, [r14+378h]; hFile
0x1800112fd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011301  jz      short loc_18001136F
0x180011303  lea     rdx, [rsp+88h+DCB]; lpDCB
0x180011308  call    cs:__imp_GetCommState
0x18001130e  test    eax, eax
0x180011310  jnz     short loc_18001131A
0x180011312  call    cs:__imp_GetLastError
0x180011318  jmp     short loc_180011371
0x18001131a  movzx   ecx, [rsp+88h+DCB.ByteSize]
0x18001131f  mov     r8b, 0DEh
0x180011322  mov     edx, dword ptr [rsp+88h+var_68]
0x180011326  cmp     r12b, r8b
0x180011329  movzx   eax, r12b
0x18001132d  cmovnz  ecx, eax
0x180011330  cmp     r13b, r8b
0x180011333  mov     [rsp+88h+DCB.ByteSize], cl
0x180011337  movzx   ecx, [rsp+88h+DCB.Parity]
0x18001133c  movzx   eax, r13b
0x180011340  cmovnz  ecx, eax
0x180011343  cmp     dl, r8b
0x180011346  mov     [rsp+88h+DCB.Parity], cl
0x18001134a  movzx   ecx, [rsp+88h+DCB.StopBits]
0x18001134f  movzx   eax, dl
0x180011352  lea     rdx, [rsp+88h+DCB]; lpDCB
0x180011357  cmovnz  ecx, eax
0x18001135a  mov     [rsp+88h+DCB.StopBits], cl
0x18001135e  mov     rcx, [r14+378h]; hFile
0x180011365  call    cs:__imp_SetCommState
0x18001136b  test    eax, eax
0x18001136d  jz      short loc_180011312
0x18001136f  xor     eax, eax
0x180011371  mov     rcx, [rsp+88h+var_40]
0x180011376  xor     rcx, rsp; StackCookie
0x180011379  call    __security_check_cookie
0x18001137e  mov     rbx, [rsp+88h+arg_10]
0x180011386  add     rsp, 50h
0x18001138a  pop     r15
0x18001138c  pop     r14
0x18001138e  pop     r13
0x180011390  pop     r12
0x180011392  pop     rdi
0x180011393  pop     rsi
0x180011394  pop     rbp
0x180011395  retn
0x180011396  mov     eax, 25Ch
0x18001139b  jmp     short loc_180011371
```
