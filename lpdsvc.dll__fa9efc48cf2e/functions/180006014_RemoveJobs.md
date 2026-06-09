# RemoveJobs

- ea: `0x180006014`
- end: `0x1800063ad`
- name: `RemoveJobs`
- size: `921`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007354`

## callees

- `0x180001ce0`
- `0x180002e7c`
- `0x180003d4c`
- `0x180006014`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180006160`
- `KERNEL32!LocalAlloc` at `0x180006160`
- `KERNEL32!GetLastError` at `0x180006122`
- `KERNEL32!GetLastError` at `0x180006122`
- `KERNEL32!LocalFree` at `0x1800062f9`
- `KERNEL32!LocalFree` at `0x1800062f9`
- `WINSPOOL!OpenPrinterA` at `0x1800060cc`
- `WINSPOOL!OpenPrinterA` at `0x1800060cc`
- `WINSPOOL!GetJobA` at `0x180006118`
- `WINSPOOL!GetJobA` at `0x180006194`
- `WINSPOOL!GetJobA` at `0x180006118`
- `WINSPOOL!GetJobA` at `0x180006194`
- `WINSPOOL!SetJobA` at `0x180006294`
- `WINSPOOL!SetJobA` at `0x180006294`

## pseudocode

```c
__int64 __fastcall RemoveJobs(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // r14
  __int64 v4; // r15
  int v5; // esi
  _QWORD *v6; // rdi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const CHAR *v9; // r9
  __int64 v10; // rax
  int v11; // edx
  _BYTE *v12; // rcx
  const CHAR *v13; // rax
  CHAR i; // cl
  bool v15; // zf
  const CHAR *v16; // r11
  const CHAR *v17; // r10
  const CHAR *v18; // rax
  int v19; // ecx
  int v20; // edx
  const CHAR *v21; // rax
  int v22; // ecx
  int v23; // edx
  DWORD pcbNeeded; // [rsp+30h] [rbp-40h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-38h] BYREF
  LPCSTR v27[4]; // [rsp+40h] [rbp-30h] BYREF

  phPrinter = 0;
  pcbNeeded = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *(_QWORD *)(a1 + 112);
  if ( !v3 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(v2[2], 71, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20003;
  }
  if ( !*(_QWORD *)(a1 + 88) )
    goto LABEL_59;
  if ( !OpenPrinterA(*(LPSTR *)(a1 + 88), &phPrinter, 0) )
  {
    v2 = WPP_GLOBAL_Control;
LABEL_59:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(v2[2], 72, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20004;
  }
  v4 = 0;
  *(_QWORD *)(a1 + 96) = phPrinter;
  v5 = 1;
  if ( !*(_DWORD *)(v3 + 132) )
  {
LABEL_57:
    *(_WORD *)(a1 + 20) = 10;
    return 0;
  }
  do
  {
    if ( GetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(v3 + 4 * v4 + 92), 1u, 0, 0, &pcbNeeded) || GetLastError() == 122 )
    {
      v6 = LocalAlloc(0, pcbNeeded);
      if ( !v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
        return 20001;
      }
      if ( GetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(v3 + 4 * v4 + 92), 1u, (LPBYTE)v6, pcbNeeded, &pcbNeeded) )
      {
        v9 = (const CHAR *)v6[3];
        if ( !v9 )
          goto LABEL_50;
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
        v11 = 0;
        v12 = (_BYTE *)v6[3];
        if ( *v9 != 41 )
        {
          while ( ++v11 < (unsigned int)v10 )
          {
            if ( *++v12 == 41 )
              goto LABEL_30;
          }
          goto LABEL_49;
        }
        if ( !(_DWORD)v10 )
          goto LABEL_50;
LABEL_30:
        *v12 = 0;
        v13 = v9;
        for ( i = *v9; i != 32 && ((i - 9) & 0xFB) != 0; i = *v13 )
          ++v13;
        v15 = v13[1] == 40;
        *v13 = 0;
        if ( !v15 )
          goto LABEL_49;
        v16 = *(const CHAR **)v3;
        v17 = v13 + 2;
        v18 = v9;
        do
        {
          v19 = (unsigned __int8)v18[*(_QWORD *)v3 - (_QWORD)v9];
          v20 = *(unsigned __int8 *)v18 - v19;
          if ( v20 )
            break;
          ++v18;
        }
        while ( v19 );
        if ( !v20 )
        {
          v21 = v17;
          do
          {
            v22 = (unsigned __int8)v21[a1 + 120 - (_QWORD)v17];
            v23 = *(unsigned __int8 *)v21 - v22;
            if ( v23 )
              break;
            ++v21;
          }
          while ( v22 );
          if ( !v23 )
          {
            SetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(v3 + 4 * v4 + 92), 0, 0, 3u);
LABEL_49:
            LocalFree(v6);
            goto LABEL_50;
          }
        }
        v27[2] = v9;
        v27[0] = (LPCSTR)(a1 + 120);
        v27[1] = v16;
        v27[3] = v17;
        LpdReportEvent(0xC0000FA7, 4u, v27, 0);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
LABEL_48:
          v5 = 0;
          goto LABEL_49;
        }
        v8 = 76;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_48;
        v8 = 75;
      }
      WPP_SF_(v7[2], v8, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
      goto LABEL_48;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    v5 = 0;
LABEL_50:
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (unsigned int)v4 < *(_DWORD *)(v3 + 132) );
  if ( v5 )
    goto LABEL_57;
  return 20003;
}

```

## disassembly

```asm
0x180006014  mov     [rsp-28h+arg_8], rbx
0x180006019  mov     [rsp-28h+arg_10], rsi
0x18000601e  push    rbp
0x18000601f  push    rdi
0x180006020  push    r12
0x180006022  push    r14
0x180006024  push    r15
0x180006026  mov     rbp, rsp
0x180006029  sub     rsp, 70h
0x18000602d  mov     rax, cs:__security_cookie
0x180006034  xor     rax, rsp
0x180006037  mov     [rbp+var_10], rax
0x18000603b  mov     rbx, rcx
0x18000603e  mov     [rbp+phPrinter], 0
0x180006046  mov     [rbp+var_40], 0
0x18000604d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006054  lea     rdi, WPP_GLOBAL_Control
0x18000605b  lea     rsi, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006062  cmp     rcx, rdi
0x180006065  jz      short loc_180006085
0x180006067  test    byte ptr [rcx+1Ch], 1
0x18000606b  jz      short loc_180006085
0x18000606d  mov     rcx, [rcx+10h]
0x180006071  mov     edx, 46h ; 'F'
0x180006076  mov     r8, rsi
0x180006079  call    WPP_SF_
0x18000607e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006085  mov     r14, [rbx+70h]
0x180006089  test    r14, r14
0x18000608c  jnz     short loc_1800060B6
0x18000608e  cmp     rcx, rdi
0x180006091  jz      loc_18000631A
0x180006097  test    byte ptr [rcx+1Ch], 8
0x18000609b  jz      loc_18000631A
0x1800060a1  mov     rcx, [rcx+10h]
0x1800060a5  lea     edx, [r14+47h]
0x1800060a9  mov     r8, rsi
0x1800060ac  call    WPP_SF_
0x1800060b1  jmp     loc_18000631A
0x1800060b6  cmp     qword ptr [rbx+58h], 0
0x1800060bb  jz      loc_180006367
0x1800060c1  mov     rcx, [rbx+58h]; pPrinterName
0x1800060c5  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800060c9  xor     r8d, r8d; pDefault
0x1800060cc  call    cs:__imp_OpenPrinterA
0x1800060d2  test    eax, eax
0x1800060d4  jz      loc_180006360
0x1800060da  mov     rax, [rbp+phPrinter]
0x1800060de  xor     r15d, r15d
0x1800060e1  mov     [rbx+60h], rax
0x1800060e5  mov     esi, 1
0x1800060ea  cmp     [r14+84h], r15d
0x1800060f1  jbe     loc_180006356
0x1800060f7  mov     edx, [r14+r15*4+5Ch]; JobId
0x1800060fc  lea     rax, [rbp+var_40]
0x180006100  mov     rcx, [rbx+60h]; hPrinter
0x180006104  xor     r9d, r9d; pJob
0x180006107  mov     [rsp+70h+pcbNeeded], rax; pcbNeeded
0x18000610c  mov     [rsp+70h+cbBuf], 0; cbBuf
0x180006114  lea     r8d, [r9+1]; Level
0x180006118  call    cs:__imp_GetJobA
0x18000611e  test    eax, eax
0x180006120  jnz     short loc_18000615B
0x180006122  call    cs:__imp_GetLastError
0x180006128  cmp     eax, 7Ah ; 'z'
0x18000612b  jz      short loc_18000615B
0x18000612d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006134  cmp     rcx, rdi
0x180006137  jz      short loc_180006154
0x180006139  test    byte ptr [rcx+1Ch], 8
0x18000613d  jz      short loc_180006154
0x18000613f  mov     rcx, [rcx+10h]
0x180006143  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x18000614a  mov     edx, 49h ; 'I'
0x18000614f  call    WPP_SF_
0x180006154  xor     esi, esi
0x180006156  jmp     loc_180006306
0x18000615b  mov     edx, [rbp+var_40]; uBytes
0x18000615e  xor     ecx, ecx; uFlags
0x180006160  call    cs:__imp_LocalAlloc
0x180006166  mov     rdi, rax
0x180006169  test    rax, rax
0x18000616c  jz      loc_180006321
0x180006172  mov     ecx, [rbp+var_40]
0x180006175  lea     rax, [rbp+var_40]
0x180006179  mov     edx, [r14+r15*4+5Ch]; JobId
0x18000617e  mov     r9, rdi; pJob
0x180006181  mov     [rsp+70h+pcbNeeded], rax; pcbNeeded
0x180006186  mov     r8d, 1; Level
0x18000618c  mov     [rsp+70h+cbBuf], ecx; cbBuf
0x180006190  mov     rcx, [rbx+60h]; hPrinter
0x180006194  call    cs:__imp_GetJobA
0x18000619a  test    eax, eax
0x18000619c  jnz     short loc_1800061C9
0x18000619e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061a5  lea     rax, WPP_GLOBAL_Control
0x1800061ac  cmp     rcx, rax
0x1800061af  jz      loc_1800062F4
0x1800061b5  test    byte ptr [rcx+1Ch], 8
0x1800061b9  jz      loc_1800062F4
0x1800061bf  mov     edx, 4Bh ; 'K'
0x1800061c4  jmp     loc_1800062E4
0x1800061c9  mov     r9, [rdi+18h]
0x1800061cd  test    r9, r9
0x1800061d0  jz      loc_1800062FF
0x1800061d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800061da  inc     rax
0x1800061dd  cmp     byte ptr [r9+rax], 0
0x1800061e2  jnz     short loc_1800061DA
0x1800061e4  xor     edx, edx
0x1800061e6  mov     rcx, r9
0x1800061e9  cmp     byte ptr [r9], 29h ; ')'
0x1800061ed  jz      short loc_180006203
0x1800061ef  inc     edx
0x1800061f1  cmp     edx, eax
0x1800061f3  jnb     loc_1800062F6
0x1800061f9  inc     rcx
0x1800061fc  cmp     byte ptr [rcx], 29h ; ')'
0x1800061ff  jnz     short loc_1800061EF
0x180006201  jmp     short loc_18000620B
0x180006203  test    eax, eax
0x180006205  jz      loc_1800062FF
0x18000620b  mov     byte ptr [rcx], 0
0x18000620e  mov     rax, r9
0x180006211  mov     cl, [r9]
0x180006214  jmp     short loc_180006223
0x180006216  sub     cl, 9
0x180006219  test    cl, 0FBh
0x18000621c  jz      short loc_180006228
0x18000621e  inc     rax
0x180006221  mov     cl, [rax]
0x180006223  cmp     cl, 20h ; ' '
0x180006226  jnz     short loc_180006216
0x180006228  cmp     byte ptr [rax+1], 28h ; '('
0x18000622c  mov     byte ptr [rax], 0
0x18000622f  jnz     loc_1800062F6
0x180006235  mov     r11, [r14]
0x180006238  lea     r10, [rax+2]
0x18000623c  mov     r8, r11
0x18000623f  mov     rax, r9
0x180006242  sub     r8, r9
0x180006245  movzx   edx, byte ptr [rax]
0x180006248  movzx   ecx, byte ptr [rax+r8]
0x18000624d  sub     edx, ecx
0x18000624f  jnz     short loc_180006258
0x180006251  inc     rax
0x180006254  test    ecx, ecx
0x180006256  jnz     short loc_180006245
0x180006258  test    edx, edx
0x18000625a  jnz     short loc_18000629C
0x18000625c  lea     r8, [rbx+78h]
0x180006260  mov     rax, r10
0x180006263  sub     r8, r10
0x180006266  movzx   edx, byte ptr [rax]
0x180006269  movzx   ecx, byte ptr [rax+r8]
0x18000626e  sub     edx, ecx
0x180006270  jnz     short loc_180006279
0x180006272  inc     rax
0x180006275  test    ecx, ecx
0x180006277  jnz     short loc_180006266
0x180006279  test    edx, edx
0x18000627b  jnz     short loc_18000629C
0x18000627d  mov     edx, [r14+r15*4+5Ch]; JobId
0x180006282  xor     r9d, r9d; pJob
0x180006285  mov     rcx, [rbx+60h]; hPrinter
0x180006289  xor     r8d, r8d; Level
0x18000628c  mov     [rsp+70h+cbBuf], 3; Command
0x180006294  call    cs:__imp_SetJobA
0x18000629a  jmp     short loc_1800062F6
0x18000629c  lea     rax, [rbx+78h]
0x1800062a0  mov     [rbp+var_20], r9
0x1800062a4  xor     r9d, r9d
0x1800062a7  mov     [rbp+var_30], rax
0x1800062ab  mov     edx, 4
0x1800062b0  mov     [rbp+var_28], r11
0x1800062b4  lea     r8, [rbp+var_30]
0x1800062b8  mov     [rbp+var_18], r10
0x1800062bc  mov     ecx, 0C0000FA7h; dwEventID
0x1800062c1  call    LpdReportEvent
0x1800062c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062cd  lea     rax, WPP_GLOBAL_Control
0x1800062d4  cmp     rcx, rax
0x1800062d7  jz      short loc_1800062F4
0x1800062d9  test    byte ptr [rcx+1Ch], 8
0x1800062dd  jz      short loc_1800062F4
0x1800062df  mov     edx, 4Ch ; 'L'
0x1800062e4  mov     rcx, [rcx+10h]
0x1800062e8  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x1800062ef  call    WPP_SF_
0x1800062f4  xor     esi, esi
0x1800062f6  mov     rcx, rdi; hMem
0x1800062f9  call    cs:__imp_LocalFree
0x1800062ff  lea     rdi, WPP_GLOBAL_Control
0x180006306  inc     r15d
0x180006309  cmp     r15d, [r14+84h]
0x180006310  jb      loc_1800060F7
0x180006316  test    esi, esi
0x180006318  jnz     short loc_180006356
0x18000631a  mov     eax, 4E23h
0x18000631f  jmp     short loc_180006388
0x180006321  mov     rcx, cs:WPP_GLOBAL_Control
0x180006328  lea     rax, WPP_GLOBAL_Control
0x18000632f  cmp     rcx, rax
0x180006332  jz      short loc_18000634F
0x180006334  test    byte ptr [rcx+1Ch], 8
0x180006338  jz      short loc_18000634F
0x18000633a  mov     rcx, [rcx+10h]
0x18000633e  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006345  mov     edx, 4Ah ; 'J'
0x18000634a  call    WPP_SF_
0x18000634f  mov     eax, 4E21h
0x180006354  jmp     short loc_180006388
0x180006356  mov     word ptr [rbx+14h], 0Ah
0x18000635c  xor     eax, eax
0x18000635e  jmp     short loc_180006388
0x180006360  mov     rcx, cs:WPP_GLOBAL_Control
0x180006367  cmp     rcx, rdi
0x18000636a  jz      short loc_180006383
0x18000636c  test    byte ptr [rcx+1Ch], 8
0x180006370  jz      short loc_180006383
0x180006372  mov     rcx, [rcx+10h]
0x180006376  mov     edx, 48h ; 'H'
0x18000637b  mov     r8, rsi
0x18000637e  call    WPP_SF_
0x180006383  mov     eax, 4E24h
0x180006388  mov     rcx, [rbp+var_10]
0x18000638c  xor     rcx, rsp; StackCookie
0x18000638f  call    __security_check_cookie
0x180006394  lea     r11, [rsp+70h+var_s0]
0x180006399  mov     rbx, [r11+38h]
0x18000639d  mov     rsi, [r11+40h]
0x1800063a1  mov     rsp, r11
0x1800063a4  pop     r15
0x1800063a6  pop     r14
0x1800063a8  pop     r12
0x1800063aa  pop     rdi
0x1800063ab  pop     rbp
0x1800063ac  retn
```
