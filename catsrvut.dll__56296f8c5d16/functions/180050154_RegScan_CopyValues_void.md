# RegScan::CopyValues(void)

- ea: `0x180050154`
- end: `0x1800504ba`
- name: `?CopyValues@RegScan@@AEAAJXZ`
- size: `870`
- prototype: `__int64 __fastcall(RegScan *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004fed4`

## callees

- `0x180005944`
- `0x180008dd0`
- `0x180050154`
- `0x180050adc`
- `0x180055822`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800503a1`
- `msvcrt!_wcsicmp` at `0x1800503a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050416`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050416`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050307`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005033b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050307`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005033b`

## string_xrefs

- `0x1800501a5`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800501f0`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800502b0`: `com\complus\src\comcat\regscan\regscan.cpp`

## pseudocode

```c
LSTATUS __fastcall RegScan::CopyValues(RegScan *this)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rax
  void *v4; // rsp
  __int64 v5; // rax
  BYTE *lpData; // rdi
  void *v7; // rsp
  unsigned int v8; // r13d
  BYTE *v9; // rsi
  __int64 v10; // rcx
  const WCHAR *v11; // r15
  HKEY v12; // rcx
  LSTATUS result; // eax
  bool v14; // cc
  HKEY v15; // rcx
  DWORD v16; // r14d
  int v17; // esi
  const BYTE *v18; // r12
  DWORD v19; // edi
  bool v20; // zf
  unsigned __int16 *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  BYTE Data[4]; // [rsp+30h] [rbp+0h] BYREF
  void *Buf2; // [rsp+38h] [rbp+8h]
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  void *Buf1; // [rsp+48h] [rbp+18h]
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD lpcbData; // [rsp+54h] [rbp+24h] BYREF
  int v31; // [rsp+58h] [rbp+28h] BYREF
  __int16 v32; // [rsp+5Ch] [rbp+2Ch]
  int v33; // [rsp+60h] [rbp+30h]
  const unsigned __int16 *v34; // [rsp+68h] [rbp+38h]
  __int64 v35; // [rsp+70h] [rbp+40h]
  __int64 v36; // [rsp+78h] [rbp+48h]
  int v37; // [rsp+80h] [rbp+50h]
  int v38; // [rsp+84h] [rbp+54h]

  if ( !*((_QWORD *)this + 6) )
  {
    v31 = 0;
    v34 = L"m_hkeyDest";
    v32 = 21;
    v33 = -1073605930;
    v35 = 0;
    v36 = 0;
    v38 = 1;
    v37 = 1;
    CError::WriteToLog((CError *)&v31, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x224u, L"m_hkeyDest");
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v31 = 0;
    v34 = L"m_hkeySource";
    v32 = 21;
    v33 = -1073605930;
    v35 = 0;
    v36 = 0;
    v38 = 1;
    v37 = 1;
    CError::WriteToLog((CError *)&v31, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x225u, L"m_hkeySource");
  }
  v2 = (unsigned int)(*((_DWORD *)this + 15) + 1);
  v3 = v2 + 15;
  if ( v2 + 15 <= v2 )
    v3 = 0xFFFFFFFFFFFFFF0LL;
  v4 = alloca(v3 & 0xFFFFFFFFFFFFFFF0uLL);
  v5 = v2 + 15;
  lpData = Data;
  Buf1 = Data;
  if ( v2 + 15 < v2 )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v7 = alloca(v5 & 0xFFFFFFFFFFFFFFF0uLL);
  v8 = 0;
  v9 = Data;
  Buf2 = Data;
  while ( 1 )
  {
    if ( v8 >= *((_DWORD *)this + 6) )
      return 0;
    v10 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v10 + 16LL * v8 + 8) )
      break;
LABEL_43:
    ++v8;
  }
  v11 = *(const WCHAR **)(v10 + 16LL * v8);
  if ( !v11 )
  {
    v34 = L"lpValueName";
    v32 = 21;
    v31 = 0;
    v33 = -1073605930;
    v35 = 0;
    v36 = 0;
    v38 = 1;
    v37 = 1;
    CError::WriteToLog((CError *)&v31, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x23Cu, L"lpValueName");
  }
  v12 = (HKEY)*((_QWORD *)this + 5);
  cbData = *((_DWORD *)this + 15);
  *(_DWORD *)Data = 0;
  result = RegQueryValueExW(v12, v11, 0, (LPDWORD)Data, lpData, &cbData);
  v14 = result <= 0;
  if ( result )
    goto LABEL_45;
  v15 = (HKEY)*((_QWORD *)this + 6);
  lpcbData = *((_DWORD *)this + 15);
  Type = 0;
  result = RegQueryValueExW(v15, v11, 0, &Type, v9, &lpcbData);
  if ( (result & 0xFFFFFFFD) == 0 )
  {
    v16 = cbData;
    v17 = 1;
    v18 = lpData;
    if ( !result )
    {
      v19 = Type;
      if ( Type == *(_DWORD *)Data && lpcbData == cbData && !memcmp_0(Buf1, Buf2, cbData) )
      {
        v17 = 0;
LABEL_36:
        lpData = (BYTE *)Buf1;
        if ( *(_DWORD *)(*((_QWORD *)this + 12) + 116LL)
          && *(_DWORD *)Data == 1
          && (unsigned int)RegScan::IsRegisteredFileName(this, (unsigned __int16 *)Buf1)
          && (++*(_DWORD *)(*((_QWORD *)this + 12) + 128LL), v17) )
        {
          v9 = (BYTE *)Buf2;
          if ( Type == 1 )
            RegScanUtil::RefCountFile((const WCHAR *)Buf2, 1, 0);
        }
        else
        {
          v9 = (BYTE *)Buf2;
        }
        goto LABEL_43;
      }
      if ( *(_DWORD *)Data == 1 )
      {
        v20 = v19 == 1;
        v21 = (unsigned __int16 *)Buf1;
        if ( !v20 || _wcsicmp((const wchar_t *)Buf1, (const wchar_t *)Buf2) )
        {
          if ( (unsigned int)RegScan::IsRegisteredFileName(this, v21) )
          {
            v22 = *((_QWORD *)this + 12);
            *((_DWORD *)this + 22) |= 8u;
            v18 = *(const BYTE **)(v22 + 104);
            v23 = -1;
            do
              ++v23;
            while ( *(_WORD *)&v18[2 * v23] );
            v16 = 2 * v23;
          }
        }
        else
        {
          v17 = 0;
        }
      }
      v24 = *((_DWORD *)this + 22);
      if ( (v24 & 1) != 0 && (v24 & 4) != 0 && (v24 & 8) != 0 && (v24 & 2) == 0 )
        v17 = *(_DWORD *)(*((_QWORD *)this + 12) + 112LL);
      if ( !v17 )
        goto LABEL_36;
    }
    result = RegSetValueExW(*((HKEY *)this + 6), v11, 0, *(DWORD *)Data, v18, v16);
    v14 = result <= 0;
    if ( result )
      goto LABEL_45;
    goto LABEL_36;
  }
  v14 = result <= 0;
LABEL_45:
  if ( !v14 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180050154  push    rbp
0x180050156  push    rbx
0x180050157  push    rsi
0x180050158  push    rdi
0x180050159  push    r12
0x18005015b  push    r13
0x18005015d  push    r14
0x18005015f  push    r15
0x180050161  sub     rsp, 98h
0x180050168  lea     rbp, [rsp+30h]
0x18005016d  mov     rax, cs:__security_cookie
0x180050174  xor     rax, rbp
0x180050177  mov     [rbp+0A0h+var_48], rax
0x18005017b  mov     eax, 15h
0x180050180  xor     r14d, r14d
0x180050183  mov     rbx, rcx
0x180050186  lea     r12d, [rax-14h]
0x18005018a  cmp     [rcx+30h], r14
0x18005018e  jnz     short loc_1800501D5
0x180050190  lea     r9, aMHkeydest; "m_hkeyDest"
0x180050197  mov     [rbp+0A0h+var_78], r14d
0x18005019b  mov     r8d, 224h; unsigned int
0x1800501a1  mov     [rbp+0A0h+var_68], r9
0x1800501a5  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800501ac  mov     [rbp+0A0h+var_74], ax
0x1800501b0  lea     rcx, [rbp+0A0h+var_78]; this
0x1800501b4  mov     [rbp+0A0h+var_70], 0C00212D6h
0x1800501bb  mov     [rbp+0A0h+var_60], r14
0x1800501bf  mov     [rbp+0A0h+var_58], r14
0x1800501c3  mov     [rbp+0A0h+var_4C], r12d
0x1800501c7  mov     [rbp+0A0h+var_50], r12d
0x1800501cb  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800501d0  lea     eax, [r12+14h]
0x1800501d5  cmp     [rbx+28h], r14
0x1800501d9  jnz     short loc_18005021B
0x1800501db  lea     r9, aMHkeysource; "m_hkeySource"
0x1800501e2  mov     [rbp+0A0h+var_78], r14d
0x1800501e6  mov     r8d, 225h; unsigned int
0x1800501ec  mov     [rbp+0A0h+var_68], r9
0x1800501f0  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800501f7  mov     [rbp+0A0h+var_74], ax
0x1800501fb  lea     rcx, [rbp+0A0h+var_78]; this
0x1800501ff  mov     [rbp+0A0h+var_70], 0C00212D6h
0x180050206  mov     [rbp+0A0h+var_60], r14
0x18005020a  mov     [rbp+0A0h+var_58], r14
0x18005020e  mov     [rbp+0A0h+var_4C], r12d
0x180050212  mov     [rbp+0A0h+var_50], r12d
0x180050216  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18005021b  mov     eax, [rbx+3Ch]
0x18005021e  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180050228  add     eax, r12d
0x18005022b  mov     ecx, eax
0x18005022d  add     rax, 0Fh
0x180050231  cmp     rax, rcx
0x180050234  ja      short loc_180050239
0x180050236  mov     rax, rdx
0x180050239  and     rax, 0FFFFFFFFFFFFFFF0h
0x18005023d  call    _alloca_probe
0x180050242  sub     rsp, rax
0x180050245  lea     rax, [rcx+0Fh]
0x180050249  lea     rdi, [rsp+0D0h+Data]
0x18005024e  mov     [rbp+0A0h+Buf1], rdi
0x180050252  cmp     rax, rcx
0x180050255  ja      short loc_18005025A
0x180050257  mov     rax, rdx
0x18005025a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18005025e  call    _alloca_probe
0x180050263  sub     rsp, rax
0x180050266  lea     rdx, aLpvaluename; "lpValueName"
0x18005026d  mov     r13d, r14d
0x180050270  lea     rsi, [rsp+0D0h+Data]
0x180050275  mov     [rbp+0A0h+Buf2], rsi
0x180050279  cmp     r13d, [rbx+18h]
0x18005027d  jnb     loc_18005049B
0x180050283  mov     rcx, [rbx+10h]
0x180050287  mov     eax, r13d
0x18005028a  add     rax, rax
0x18005028d  cmp     [rcx+rax*8+8], r14d
0x180050292  jz      loc_180050485
0x180050298  mov     r15, [rcx+rax*8]
0x18005029c  test    r15, r15
0x18005029f  jnz     short loc_1800502E1
0x1800502a1  lea     eax, [r15+15h]
0x1800502a5  mov     [rbp+0A0h+var_68], rdx
0x1800502a9  mov     r9, rdx; unsigned __int16 *
0x1800502ac  mov     [rbp+0A0h+var_74], ax
0x1800502b0  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800502b7  mov     [rbp+0A0h+var_78], r14d
0x1800502bb  mov     r8d, 23Ch; unsigned int
0x1800502c1  mov     [rbp+0A0h+var_70], 0C00212D6h
0x1800502c8  lea     rcx, [rbp+0A0h+var_78]; this
0x1800502cc  mov     [rbp+0A0h+var_60], r14
0x1800502d0  mov     [rbp+0A0h+var_58], r14
0x1800502d4  mov     [rbp+0A0h+var_4C], r12d
0x1800502d8  mov     [rbp+0A0h+var_50], r12d
0x1800502dc  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800502e1  mov     eax, [rbx+3Ch]
0x1800502e4  lea     r9, [rbp+0A0h+Data]; lpType
0x1800502e8  mov     rcx, [rbx+28h]; hKey
0x1800502ec  xor     r8d, r8d; lpReserved
0x1800502ef  mov     [rbp+0A0h+cbData], eax
0x1800502f2  mov     rdx, r15; lpValueName
0x1800502f5  lea     rax, [rbp+0A0h+cbData]
0x1800502f9  mov     dword ptr [rbp+0A0h+Data], r14d
0x1800502fd  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180050302  mov     [rsp+0D0h+lpData], rdi; lpData
0x180050307  call    cs:__imp_RegQueryValueExW
0x18005030d  test    eax, eax
0x18005030f  jnz     loc_18005048F
0x180050315  mov     eax, [rbx+3Ch]
0x180050318  lea     r9, [rbp+0A0h+Type]; lpType
0x18005031c  mov     rcx, [rbx+30h]; hKey
0x180050320  xor     r8d, r8d; lpReserved
0x180050323  mov     [rbp+0A0h+var_7C], eax
0x180050326  mov     rdx, r15; lpValueName
0x180050329  lea     rax, [rbp+0A0h+var_7C]
0x18005032d  mov     [rbp+0A0h+Type], r14d
0x180050331  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180050336  mov     [rsp+0D0h+lpData], rsi; lpData
0x18005033b  call    cs:__imp_RegQueryValueExW
0x180050341  test    eax, 0FFFFFFFDh
0x180050346  jnz     loc_18005048D
0x18005034c  mov     r14d, [rbp+0A0h+cbData]
0x180050350  mov     esi, r12d
0x180050353  mov     r12, rdi
0x180050356  test    eax, eax
0x180050358  jnz     loc_1800503FE
0x18005035e  mov     edi, [rbp+0A0h+Type]
0x180050361  cmp     edi, dword ptr [rbp+0A0h+Data]
0x180050364  jnz     short loc_18005038B
0x180050366  cmp     [rbp+0A0h+var_7C], r14d
0x18005036a  jnz     short loc_18005038B
0x18005036c  mov     rdx, [rbp+0A0h+Buf2]; Buf2
0x180050370  mov     r8d, r14d; Size
0x180050373  mov     rcx, [rbp+0A0h+Buf1]; Buf1
0x180050377  call    memcmp_0
0x18005037c  test    eax, eax
0x18005037e  jnz     short loc_18005038B
0x180050380  xor     r14d, r14d
0x180050383  mov     esi, r14d
0x180050386  jmp     loc_180050428
0x18005038b  cmp     dword ptr [rbp+0A0h+Data], 1
0x18005038f  jnz     short loc_1800503E0
0x180050391  cmp     edi, 1
0x180050394  mov     rdi, [rbp+0A0h+Buf1]
0x180050398  jnz     short loc_1800503B1
0x18005039a  mov     rdx, [rbp+0A0h+Buf2]; String2
0x18005039e  mov     rcx, rdi; String1
0x1800503a1  call    cs:__imp__wcsicmp
0x1800503a7  xor     ecx, ecx
0x1800503a9  test    eax, eax
0x1800503ab  jnz     short loc_1800503B1
0x1800503ad  mov     esi, ecx
0x1800503af  jmp     short loc_1800503E0
0x1800503b1  mov     rdx, rdi; unsigned __int16 *
0x1800503b4  mov     rcx, rbx; this
0x1800503b7  call    ?IsRegisteredFileName@RegScan@@AEAAHPEAG@Z; RegScan::IsRegisteredFileName(ushort *)
0x1800503bc  xor     ecx, ecx
0x1800503be  test    eax, eax
0x1800503c0  jz      short loc_1800503E0
0x1800503c2  mov     rax, [rbx+60h]
0x1800503c6  or      dword ptr [rbx+58h], 8
0x1800503ca  mov     r12, [rax+68h]
0x1800503ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800503d2  inc     rax
0x1800503d5  cmp     [r12+rax*2], cx
0x1800503da  jnz     short loc_1800503D2
0x1800503dc  lea     r14d, [rax+rax]
0x1800503e0  mov     eax, [rbx+58h]
0x1800503e3  test    al, 1
0x1800503e5  jz      short loc_1800503FA
0x1800503e7  test    al, 4
0x1800503e9  jz      short loc_1800503FA
0x1800503eb  test    al, 8
0x1800503ed  jz      short loc_1800503FA
0x1800503ef  test    al, 2
0x1800503f1  jnz     short loc_1800503FA
0x1800503f3  mov     rax, [rbx+60h]
0x1800503f7  mov     esi, [rax+70h]
0x1800503fa  test    esi, esi
0x1800503fc  jz      short loc_180050425
0x1800503fe  mov     r9d, dword ptr [rbp+0A0h+Data]; dwType
0x180050402  xor     r8d, r8d; Reserved
0x180050405  mov     rcx, [rbx+30h]; hKey
0x180050409  mov     rdx, r15; lpValueName
0x18005040c  mov     dword ptr [rsp+0D0h+lpcbData], r14d; cbData
0x180050411  mov     [rsp+0D0h+lpData], r12; lpData
0x180050416  call    cs:__imp_RegSetValueExW
0x18005041c  xor     r14d, r14d
0x18005041f  test    eax, eax
0x180050421  jnz     short loc_18005048F
0x180050423  jmp     short loc_180050428
0x180050425  xor     r14d, r14d
0x180050428  mov     rax, [rbx+60h]
0x18005042c  mov     r12d, 1
0x180050432  mov     rdi, [rbp+0A0h+Buf1]
0x180050436  cmp     [rax+74h], r14d
0x18005043a  jz      short loc_18005047A
0x18005043c  cmp     dword ptr [rbp+0A0h+Data], r12d
0x180050440  jnz     short loc_18005047A
0x180050442  mov     rdx, rdi; unsigned __int16 *
0x180050445  mov     rcx, rbx; this
0x180050448  call    ?IsRegisteredFileName@RegScan@@AEAAHPEAG@Z; RegScan::IsRegisteredFileName(ushort *)
0x18005044d  test    eax, eax
0x18005044f  jz      short loc_18005047A
0x180050451  mov     rax, [rbx+60h]
0x180050455  add     [rax+80h], r12d
0x18005045c  test    esi, esi
0x18005045e  jz      short loc_18005047A
0x180050460  mov     rsi, [rbp+0A0h+Buf2]
0x180050464  cmp     [rbp+0A0h+Type], r12d
0x180050468  jnz     short loc_18005047E
0x18005046a  xor     r8d, r8d
0x18005046d  mov     edx, r12d
0x180050470  mov     rcx, rsi
0x180050473  call    ?RefCountFile@RegScanUtil@@CAJPEAGW4REF_COUNT_TYPE@1@K@Z; RegScanUtil::RefCountFile(ushort *,RegScanUtil::REF_COUNT_TYPE,ulong)
0x180050478  jmp     short loc_18005047E
0x18005047a  mov     rsi, [rbp+0A0h+Buf2]
0x18005047e  lea     rdx, aLpvaluename; "lpValueName"
0x180050485  add     r13d, r12d
0x180050488  jmp     loc_180050279
0x18005048d  test    eax, eax
0x18005048f  jle     short loc_18005049D
0x180050491  movzx   eax, ax
0x180050494  or      eax, 80070000h
0x180050499  jmp     short loc_18005049D
0x18005049b  xor     eax, eax
0x18005049d  mov     rcx, [rbp+0A0h+var_48]
0x1800504a1  xor     rcx, rbp; StackCookie
0x1800504a4  call    __security_check_cookie
0x1800504a9  lea     rsp, [rbp+68h]
0x1800504ad  pop     r15
0x1800504af  pop     r14
0x1800504b1  pop     r13
0x1800504b3  pop     r12
0x1800504b5  pop     rdi
0x1800504b6  pop     rsi
0x1800504b7  pop     rbx
0x1800504b8  pop     rbp
0x1800504b9  retn
```
