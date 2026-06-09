# RegInsertNetComponents

- ea: `0x1800dbf74`
- end: `0x1800dc1c5`
- name: `RegInsertNetComponents`
- size: `593`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040a68`

## callees

- `0x180002418`
- `0x18000b0f4`
- `0x18004e580`
- `0x18004e984`
- `0x1800dbf74`
- `0x1800dc7dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dc042`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dc042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc16c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc17b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc16c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc17b`

## string_xrefs

- `0x1800dc010`: `NETCOMPONENTS`

## pseudocode

```c
__int64 __fastcall RegInsertNetComponents(HKEY hKey, __int64 *a2)
{
  char *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v8; // eax
  __int64 i; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rsi
  unsigned int inserted; // edi
  char *v14; // rcx
  __int64 v15; // rdx
  HKEY hKeya; // [rsp+78h] [rbp+10h] BYREF

  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
    v4 = (char *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v5 = 87;
    if ( v4 == (char *)&WPP_GLOBAL_Control || v4[28] >= 0 || (unsigned __int8)v4[25] < 6u )
      return v5;
    v6 = 30;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v4 + 2), v6, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v5);
    return v5;
  }
  hKeya = 0;
  v8 = RegCreateKeyExA(hKey, "NETCOMPONENTS", 0, 0, 0, 0x20206u, 0, &hKeya, 0);
  v5 = v8;
  if ( v8 )
  {
    v4 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v8);
      v4 = (char *)WPP_GLOBAL_Control;
    }
    if ( v4 == (char *)&WPP_GLOBAL_Control || v4[28] >= 0 || (unsigned __int8)v4[25] < 6u )
      return v5;
    v6 = 32;
    goto LABEL_10;
  }
  for ( i = *a2; i; i = *(_QWORD *)(i + 8) )
  {
    v10 = *(_QWORD *)(i + 16);
    v11 = StrDupAFromTInternal(*(LPCWCH *)v10);
    v12 = v11;
    if ( !v11 )
    {
      v14 = (char *)WPP_GLOBAL_Control;
      inserted = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 0);
          v14 = (char *)WPP_GLOBAL_Control;
        }
        if ( v14 != (char *)&WPP_GLOBAL_Control && v14[28] < 0 && (unsigned __int8)v14[25] >= 6u )
        {
          v15 = 34;
LABEL_38:
          WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, inserted);
        }
      }
LABEL_39:
      RegCloseKey(hKeya);
      return inserted;
    }
    inserted = RegInsertString(hKeya, v11, *(_QWORD *)(v10 + 8));
    Free0(v12);
    if ( inserted )
    {
      v14 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v15 = 35;
        goto LABEL_38;
      }
      goto LABEL_39;
    }
  }
  RegCloseKey(hKeya);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dbf74  mov     [rsp+arg_0], rbx
0x1800dbf79  mov     [rsp+arg_10], rsi
0x1800dbf7e  push    rdi
0x1800dbf7f  push    r13
0x1800dbf81  push    r14
0x1800dbf83  sub     rsp, 50h
0x1800dbf87  mov     rdi, rdx
0x1800dbf8a  mov     rbx, rcx
0x1800dbf8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbf94  lea     r14, WPP_GLOBAL_Control
0x1800dbf9b  lea     r13, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dbfa2  cmp     rcx, r14
0x1800dbfa5  jz      short loc_1800DBFCB
0x1800dbfa7  test    byte ptr [rcx+1Ch], 80h
0x1800dbfab  jz      short loc_1800DBFCB
0x1800dbfad  cmp     byte ptr [rcx+19h], 6
0x1800dbfb1  jb      short loc_1800DBFCB
0x1800dbfb3  mov     rcx, [rcx+10h]
0x1800dbfb7  mov     edx, 1Dh
0x1800dbfbc  mov     r8, r13
0x1800dbfbf  call    WPP_SF_
0x1800dbfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbfcb  test    rdi, rdi
0x1800dbfce  jnz     short loc_1800DBFFD
0x1800dbfd0  lea     ebx, [rdi+57h]
0x1800dbfd3  cmp     rcx, r14
0x1800dbfd6  jz      short loc_1800DBFF6
0x1800dbfd8  test    byte ptr [rcx+1Ch], 80h
0x1800dbfdc  jz      short loc_1800DBFF6
0x1800dbfde  cmp     byte ptr [rcx+19h], 6
0x1800dbfe2  jb      short loc_1800DBFF6
0x1800dbfe4  lea     edx, [rdi+1Eh]
0x1800dbfe7  mov     rcx, [rcx+10h]
0x1800dbfeb  mov     r9d, ebx
0x1800dbfee  mov     r8, r13
0x1800dbff1  call    WPP_SF_d
0x1800dbff6  mov     eax, ebx
0x1800dbff8  jmp     loc_1800DC1AF
0x1800dbffd  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1800dc006  lea     rax, [rsp+68h+hKey]
0x1800dc00b  mov     [rsp+68h+phkResult], rax; phkResult
0x1800dc010  lea     rdx, aNetcomponents_1; "NETCOMPONENTS"
0x1800dc017  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800dc020  xor     r9d, r9d; lpClass
0x1800dc023  mov     [rsp+68h+samDesired], 20206h; samDesired
0x1800dc02b  xor     r8d, r8d; Reserved
0x1800dc02e  mov     rcx, rbx; hKey
0x1800dc031  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800dc039  mov     [rsp+68h+hKey], 0
0x1800dc042  call    cs:__imp_RegCreateKeyExA
0x1800dc048  mov     ebx, eax
0x1800dc04a  test    eax, eax
0x1800dc04c  jz      short loc_1800DC0A8
0x1800dc04e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc055  cmp     rcx, r14
0x1800dc058  jz      short loc_1800DBFF6
0x1800dc05a  test    byte ptr [rcx+1Ch], 80h
0x1800dc05e  jz      short loc_1800DC081
0x1800dc060  cmp     byte ptr [rcx+19h], 2
0x1800dc064  jb      short loc_1800DC081
0x1800dc066  mov     rcx, [rcx+10h]
0x1800dc06a  mov     edx, 1Fh
0x1800dc06f  mov     r9d, eax
0x1800dc072  mov     r8, r13
0x1800dc075  call    WPP_SF_d
0x1800dc07a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc081  cmp     rcx, r14
0x1800dc084  jz      loc_1800DBFF6
0x1800dc08a  test    byte ptr [rcx+1Ch], 80h
0x1800dc08e  jz      loc_1800DBFF6
0x1800dc094  cmp     byte ptr [rcx+19h], 6
0x1800dc098  jb      loc_1800DBFF6
0x1800dc09e  mov     edx, 20h ; ' '
0x1800dc0a3  jmp     loc_1800DBFE7
0x1800dc0a8  mov     rbx, [rdi]
0x1800dc0ab  test    rbx, rbx
0x1800dc0ae  jz      loc_1800DC176
0x1800dc0b4  mov     rdi, [rbx+10h]
0x1800dc0b8  mov     rcx, [rdi]; lpWideCharStr
0x1800dc0bb  call    StrDupAFromTInternal
0x1800dc0c0  mov     rsi, rax
0x1800dc0c3  test    rax, rax
0x1800dc0c6  jz      short loc_1800DC10C
0x1800dc0c8  mov     r8, [rdi+8]
0x1800dc0cc  mov     rdx, rax
0x1800dc0cf  mov     rcx, [rsp+68h+hKey]
0x1800dc0d4  call    RegInsertString
0x1800dc0d9  mov     rcx, rsi
0x1800dc0dc  mov     edi, eax
0x1800dc0de  call    Free0
0x1800dc0e3  test    edi, edi
0x1800dc0e5  jnz     short loc_1800DC0ED
0x1800dc0e7  mov     rbx, [rbx+8]
0x1800dc0eb  jmp     short loc_1800DC0AB
0x1800dc0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc0f4  cmp     rcx, r14
0x1800dc0f7  jz      short loc_1800DC167
0x1800dc0f9  test    byte ptr [rcx+1Ch], 80h
0x1800dc0fd  jz      short loc_1800DC167
0x1800dc0ff  cmp     byte ptr [rcx+19h], 6
0x1800dc103  jb      short loc_1800DC167
0x1800dc105  mov     edx, 23h ; '#'
0x1800dc10a  jmp     short loc_1800DC158
0x1800dc10c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc113  mov     edi, 8
0x1800dc118  cmp     rcx, r14
0x1800dc11b  jz      short loc_1800DC167
0x1800dc11d  test    byte ptr [rcx+1Ch], 80h
0x1800dc121  jz      short loc_1800DC142
0x1800dc123  cmp     byte ptr [rcx+19h], 2
0x1800dc127  jb      short loc_1800DC142
0x1800dc129  mov     rcx, [rcx+10h]
0x1800dc12d  lea     edx, [rdi+19h]
0x1800dc130  xor     r9d, r9d
0x1800dc133  mov     r8, r13
0x1800dc136  call    WPP_SF_d
0x1800dc13b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc142  cmp     rcx, r14
0x1800dc145  jz      short loc_1800DC167
0x1800dc147  test    byte ptr [rcx+1Ch], 80h
0x1800dc14b  jz      short loc_1800DC167
0x1800dc14d  cmp     byte ptr [rcx+19h], 6
0x1800dc151  jb      short loc_1800DC167
0x1800dc153  mov     edx, 22h ; '"'
0x1800dc158  mov     rcx, [rcx+10h]
0x1800dc15c  mov     r9d, edi
0x1800dc15f  mov     r8, r13
0x1800dc162  call    WPP_SF_d
0x1800dc167  mov     rcx, [rsp+68h+hKey]; hKey
0x1800dc16c  call    cs:__imp_RegCloseKey
0x1800dc172  mov     eax, edi
0x1800dc174  jmp     short loc_1800DC1AF
0x1800dc176  mov     rcx, [rsp+68h+hKey]; hKey
0x1800dc17b  call    cs:__imp_RegCloseKey
0x1800dc181  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc188  cmp     rcx, r14
0x1800dc18b  jz      short loc_1800DC1AD
0x1800dc18d  test    byte ptr [rcx+1Ch], 80h
0x1800dc191  jz      short loc_1800DC1AD
0x1800dc193  cmp     byte ptr [rcx+19h], 6
0x1800dc197  jb      short loc_1800DC1AD
0x1800dc199  mov     rcx, [rcx+10h]
0x1800dc19d  mov     edx, 24h ; '$'
0x1800dc1a2  xor     r9d, r9d
0x1800dc1a5  mov     r8, r13
0x1800dc1a8  call    WPP_SF_d
0x1800dc1ad  xor     eax, eax
0x1800dc1af  lea     r11, [rsp+68h+var_18]
0x1800dc1b4  mov     rbx, [r11+20h]
0x1800dc1b8  mov     rsi, [r11+30h]
0x1800dc1bc  mov     rsp, r11
0x1800dc1bf  pop     r14
0x1800dc1c1  pop     r13
0x1800dc1c3  pop     rdi
0x1800dc1c4  retn
```
