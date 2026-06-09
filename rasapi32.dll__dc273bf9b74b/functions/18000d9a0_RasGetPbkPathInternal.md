# RasGetPbkPathInternal

- ea: `0x18000d9a0`
- end: `0x18000dc04`
- name: `RasGetPbkPathInternal`
- size: `612`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800733c0`
- `0x1800c7c64`

## callees

- `0x18000beb0`
- `0x18000d5e0`
- `0x18000d9a0`
- `0x180010d10`
- `0x18004e580`
- `0x18007ec78`
- `0x18007efdc`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18000da92`
- `rtutils!TracePrintfExA` at `0x18000dae8`
- `rtutils!TracePrintfExA` at `0x18000db4e`
- `rtutils!TracePrintfExA` at `0x18000db8b`
- `rtutils!TracePrintfExA` at `0x18000da92`
- `rtutils!TracePrintfExA` at `0x18000dae8`
- `rtutils!TracePrintfExA` at `0x18000db4e`
- `rtutils!TracePrintfExA` at `0x18000db8b`

## string_xrefs

- `0x18000db81`: `RasGetPbkPathInternal: Invalid parameters received.`
- `0x18000da86`: `RasGetPbkPathInternal`
- `0x18000db44`: `RasGetPbkPathInternal: GetPublicPhonebookPath failed.`
- `0x18000dade`: `RasGetPbkPathInternal: GetPersonalPhonebookPath failed.`

## pseudocode

```c
__int64 __fastcall RasGetPbkPathInternal(int a1, __int64 a2, const wchar_t *a3, __int64 a4)
{
  unsigned int v4; // r14d
  _QWORD *v8; // rcx
  DWORD v9; // ecx
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9

  v4 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a4);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_SSc(v8[2], 122, (unsigned int)&WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a2, (__int64)a3, a1 != 0);
  }
  else if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_c(v8[2], 123, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, a4);
  }
  DebugInit();
  v9 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "RasGetPbkPathInternal");
    v9 = g_dwTraceId;
  }
  if ( !a3 || !v4 )
  {
    v10 = 87;
    if ( v9 != -1 )
      TracePrintfExA(v9, 0xCu, "RasGetPbkPathInternal: Invalid parameters received.");
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 124;
        v13 = 87;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    return v10;
  }
  v10 = 0;
  if ( a1 )
  {
    if ( !(unsigned int)GetPersonalPhonebookPath(a2, a3, v4) )
    {
      v10 = 635;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasGetPbkPathInternal: GetPersonalPhonebookPath failed.");
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 125;
LABEL_27:
          v13 = 635;
LABEL_41:
          WPP_SF_d(v11[2], v12, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
          goto LABEL_42;
        }
        goto LABEL_43;
      }
      return v10;
    }
LABEL_42:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  if ( (unsigned int)GetPublicPhonebookPath(a3, v4) )
    goto LABEL_42;
  v10 = 635;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasGetPbkPathInternal: GetPublicPhonebookPath failed.");
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 126;
      goto LABEL_27;
    }
LABEL_43:
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x1000) != 0 && *((_BYTE *)v11 + 25) >= 6u )
      WPP_SF_d(v11[2], 127, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000d9a0  push    rbx
0x18000d9a2  push    rbp
0x18000d9a3  push    rsi
0x18000d9a4  push    rdi
0x18000d9a5  push    r12
0x18000d9a7  push    r13
0x18000d9a9  push    r14
0x18000d9ab  push    r15
0x18000d9ad  sub     rsp, 38h
0x18000d9b1  mov     r14d, r9d
0x18000d9b4  mov     rdi, r8
0x18000d9b7  mov     rbp, rdx
0x18000d9ba  mov     esi, ecx
0x18000d9bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9c3  lea     r13, WPP_GLOBAL_Control
0x18000d9ca  mov     r12d, 1000h
0x18000d9d0  cmp     rcx, r13
0x18000d9d3  jz      short loc_18000DA03
0x18000d9d5  test    [rcx+1Ch], r12d
0x18000d9d9  jz      short loc_18000DA03
0x18000d9db  cmp     byte ptr [rcx+19h], 6
0x18000d9df  jb      short loc_18000DA03
0x18000d9e1  mov     rcx, [rcx+10h]
0x18000d9e5  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18000d9ec  test    esi, esi
0x18000d9ee  mov     edx, 79h ; 'y'
0x18000d9f3  setnz   r9b
0x18000d9f7  call    WPP_SF_c
0x18000d9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da03  test    rbp, rbp
0x18000da06  jz      short loc_18000DA46
0x18000da08  test    rdi, rdi
0x18000da0b  jz      short loc_18000DA46
0x18000da0d  cmp     rcx, r13
0x18000da10  jz      short loc_18000DA72
0x18000da12  test    [rcx+1Ch], r12d
0x18000da16  jz      short loc_18000DA72
0x18000da18  cmp     byte ptr [rcx+19h], 6
0x18000da1c  jb      short loc_18000DA72
0x18000da1e  mov     rcx, [rcx+10h]
0x18000da22  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18000da29  test    esi, esi
0x18000da2b  mov     edx, 7Ah ; 'z'
0x18000da30  mov     r9, rbp
0x18000da33  setnz   al
0x18000da36  mov     [rsp+78h+var_50], al
0x18000da3a  mov     [rsp+78h+var_58], rdi
0x18000da3f  call    WPP_SF_SSc
0x18000da44  jmp     short loc_18000DA72
0x18000da46  cmp     rcx, r13
0x18000da49  jz      short loc_18000DA72
0x18000da4b  test    [rcx+1Ch], r12d
0x18000da4f  jz      short loc_18000DA72
0x18000da51  cmp     byte ptr [rcx+19h], 6
0x18000da55  jb      short loc_18000DA72
0x18000da57  mov     rcx, [rcx+10h]
0x18000da5b  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18000da62  test    esi, esi
0x18000da64  mov     edx, 7Bh ; '{'
0x18000da69  setnz   r9b
0x18000da6d  call    WPP_SF_c
0x18000da72  call    DebugInit
0x18000da77  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000da7d  or      r15d, 0FFFFFFFFh
0x18000da81  cmp     ecx, r15d
0x18000da84  jz      short loc_18000DA9E
0x18000da86  lea     r8, aRasgetpbkpathi_2; "RasGetPbkPathInternal"
0x18000da8d  mov     edx, 0Ch; dwFlags
0x18000da92  call    cs:__imp_TracePrintfExA
0x18000da98  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000da9e  test    rdi, rdi
0x18000daa1  jz      loc_18000DB77
0x18000daa7  test    r14d, r14d
0x18000daaa  jz      loc_18000DB77
0x18000dab0  xor     ebx, ebx
0x18000dab2  test    esi, esi
0x18000dab4  jz      short loc_18000DB1F
0x18000dab6  mov     r8d, r14d
0x18000dab9  mov     rdx, rdi
0x18000dabc  mov     rcx, rbp
0x18000dabf  call    GetPersonalPhonebookPath
0x18000dac4  test    eax, eax
0x18000dac6  jnz     loc_18000DBC1
0x18000dacc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000dad2  mov     edi, 27Bh
0x18000dad7  mov     ebx, edi
0x18000dad9  cmp     ecx, r15d
0x18000dadc  jz      short loc_18000DAEE
0x18000dade  lea     r8, aRasgetpbkpathi_0; "RasGetPbkPathInternal: GetPersonalPhone"...
0x18000dae5  lea     edx, [rax+0Ch]; dwFlags
0x18000dae8  call    cs:__imp_TracePrintfExA
0x18000daee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daf5  cmp     rcx, r13
0x18000daf8  jz      loc_18000DBF1
0x18000dafe  test    [rcx+1Ch], r12d
0x18000db02  jz      loc_18000DBC8
0x18000db08  cmp     byte ptr [rcx+19h], 2
0x18000db0c  jb      loc_18000DBC8
0x18000db12  mov     edx, 7Dh ; '}'
0x18000db17  mov     r9d, edi
0x18000db1a  jmp     loc_18000DBB1
0x18000db1f  mov     edx, r14d; cchMax
0x18000db22  mov     rcx, rdi; psz
0x18000db25  call    GetPublicPhonebookPath
0x18000db2a  test    eax, eax
0x18000db2c  jnz     loc_18000DBC1
0x18000db32  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000db38  mov     edi, 27Bh
0x18000db3d  mov     ebx, edi
0x18000db3f  cmp     ecx, r15d
0x18000db42  jz      short loc_18000DB54
0x18000db44  lea     r8, aRasgetpbkpathi_1; "RasGetPbkPathInternal: GetPublicPhonebo"...
0x18000db4b  lea     edx, [rax+0Ch]; dwFlags
0x18000db4e  call    cs:__imp_TracePrintfExA
0x18000db54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db5b  cmp     rcx, r13
0x18000db5e  jz      loc_18000DBF1
0x18000db64  test    [rcx+1Ch], r12d
0x18000db68  jz      short loc_18000DBC8
0x18000db6a  cmp     byte ptr [rcx+19h], 2
0x18000db6e  jb      short loc_18000DBC8
0x18000db70  mov     edx, 7Eh ; '~'
0x18000db75  jmp     short loc_18000DB17
0x18000db77  mov     ebx, 57h ; 'W'
0x18000db7c  cmp     ecx, r15d
0x18000db7f  jz      short loc_18000DB91
0x18000db81  lea     r8, aRasgetpbkpathi; "RasGetPbkPathInternal: Invalid paramete"...
0x18000db88  lea     edx, [rbx-4Bh]; dwFlags
0x18000db8b  call    cs:__imp_TracePrintfExA
0x18000db91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db98  cmp     rcx, r13
0x18000db9b  jz      short loc_18000DBF1
0x18000db9d  test    [rcx+1Ch], r12d
0x18000dba1  jz      short loc_18000DBC8
0x18000dba3  cmp     byte ptr [rcx+19h], 2
0x18000dba7  jb      short loc_18000DBC8
0x18000dba9  mov     edx, 7Ch ; '|'
0x18000dbae  mov     r9d, ebx
0x18000dbb1  mov     rcx, [rcx+10h]
0x18000dbb5  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18000dbbc  call    WPP_SF_d
0x18000dbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbc8  cmp     rcx, r13
0x18000dbcb  jz      short loc_18000DBF1
0x18000dbcd  test    [rcx+1Ch], r12d
0x18000dbd1  jz      short loc_18000DBF1
0x18000dbd3  cmp     byte ptr [rcx+19h], 6
0x18000dbd7  jb      short loc_18000DBF1
0x18000dbd9  mov     rcx, [rcx+10h]
0x18000dbdd  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18000dbe4  mov     edx, 7Fh
0x18000dbe9  mov     r9d, ebx
0x18000dbec  call    WPP_SF_d
0x18000dbf1  mov     eax, ebx
0x18000dbf3  add     rsp, 38h
0x18000dbf7  pop     r15
0x18000dbf9  pop     r14
0x18000dbfb  pop     r13
0x18000dbfd  pop     r12
0x18000dbff  pop     rdi
0x18000dc00  pop     rsi
0x18000dc01  pop     rbp
0x18000dc02  pop     rbx
0x18000dc03  retn
```
