# Query_CheckLocalQuery

- ea: `0x18000dfb8`
- end: `0x18000e2fb`
- name: `Query_CheckLocalQuery`
- size: `835`
- prototype: `__int64 __usercall@<rax>(PCNZWCH lpString1@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180013658`

## callees

- `0x18000dfb8`
- `0x18000e310`
- `0x18000edd0`
- `0x18000ee5c`
- `0x18000f020`
- `0x18000f5b4`
- `0x18002e894`
- `0x1800dfcac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e042`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e093`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e042`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e093`
- `WS2_32!__imp_closesocket` at `0x18000e170`
- `WS2_32!__imp_closesocket` at `0x18000e1a3`
- `WS2_32!__imp_closesocket` at `0x18000e170`
- `WS2_32!__imp_closesocket` at `0x18000e1a3`
- `WS2_32!__imp_socket` at `0x18000e157`
- `WS2_32!__imp_socket` at `0x18000e188`
- `WS2_32!__imp_socket` at `0x18000e157`
- `WS2_32!__imp_socket` at `0x18000e188`

## pseudocode

```c
__int64 __fastcall Query_CheckLocalQuery(
        WCHAR *lpString1,
        __int16 a2,
        unsigned int a3,
        int a4,
        unsigned int *a5,
        _QWORD *a6)
{
  int v6; // r14d
  __int64 cchCount2; // r9
  __int64 v12; // r9
  unsigned int MatchAndGetlocalMachineRecord; // ebx
  int v15; // ebp
  SOCKET v16; // rax
  SOCKET v17; // rax
  int v18; // r9d
  _QWORD *AAAARecord; // rax
  _QWORD *v20; // rcx
  __int64 v21; // [rsp+30h] [rbp-58h] BYREF
  int v22; // [rsp+38h] [rbp-50h]
  int v23; // [rsp+3Ch] [rbp-4Ch]

  v6 = 0;
  *a5 = 0;
  if ( a2 != 1 )
  {
    MatchAndGetlocalMachineRecord = 0;
    if ( a2 != 28 )
      goto LABEL_14;
  }
  *a6 = 0;
  if ( lpString1 != L"loopback" )
  {
    if ( !lpString1 )
      goto LABEL_13;
    cchCount2 = -1;
    do
      ++cchCount2;
    while ( lpString1[cchCount2] );
    if ( (_DWORD)cchCount2 != 8 )
    {
      if ( (_DWORD)cchCount2 != 9 || lpString1[8] != 46 )
      {
LABEL_8:
        if ( lpString1 != L"localhost" )
        {
          v12 = -1;
          do
            ++v12;
          while ( lpString1[v12] );
          if ( (_DWORD)v12 != 9 )
          {
            if ( (_DWORD)v12 != 10 || lpString1[9] != 46 )
              goto LABEL_13;
            LODWORD(v12) = 9;
          }
          if ( CompareStringW(0x7Fu, 1u, lpString1, v12, L"localhost", v12) != 2 )
          {
LABEL_13:
            MatchAndGetlocalMachineRecord = Query_MatchAndGetlocalMachineRecord(lpString1, a2, a3, a4, a5, a6);
            goto LABEL_14;
          }
        }
        goto LABEL_25;
      }
      LODWORD(cchCount2) = 8;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, cchCount2, L"loopback", cchCount2) == 2 )
      goto LABEL_25;
    goto LABEL_8;
  }
LABEL_25:
  *a5 = 1;
  MatchAndGetlocalMachineRecord = DnsInitWinsock();
  if ( MatchAndGetlocalMachineRecord )
    goto LABEL_38;
  v15 = 1;
  MatchAndGetlocalMachineRecord = 9501;
  v16 = socket(2, 1, 6);
  if ( v16 == -1 )
    v15 = 0;
  else
    closesocket(v16);
  v17 = socket(23, 1, 6);
  if ( v17 != -1 )
  {
    v6 = 1;
    closesocket(v17);
  }
  if ( !v15 )
    goto LABEL_36;
  if ( a3 )
  {
    v21 = 0;
    v22 = -65536;
    v23 = 16777343;
    AAAARecord = (_QWORD *)Dns_CreateAAAARecord((_DWORD)lpString1, (unsigned int)&v21, 1200, 1, 1);
  }
  else
  {
    if ( a2 != 1 )
      goto LABEL_36;
    AAAARecord = (_QWORD *)Dns_CreateARecord((_DWORD)lpString1, 16777343, 1200, v18, 1);
  }
  if ( AAAARecord )
  {
    MatchAndGetlocalMachineRecord = 0;
    *AAAARecord = *a6;
    *a6 = AAAARecord;
LABEL_36:
    if ( a2 != 28 || !v6 )
    {
      DnsShutdownWinsock();
      if ( !MatchAndGetlocalMachineRecord )
        goto LABEL_14;
      goto LABEL_38;
    }
    v23 = 0x1000000;
    v21 = 0;
    v22 = 0;
    v20 = (_QWORD *)Dns_CreateAAAARecord((_DWORD)lpString1, (unsigned int)&v21, 1200, 1, 1);
    if ( v20 )
    {
      MatchAndGetlocalMachineRecord = 0;
      *v20 = *a6;
      *a6 = v20;
      DnsShutdownWinsock();
      goto LABEL_14;
    }
  }
  MatchAndGetlocalMachineRecord = 14;
  DnsShutdownWinsock();
LABEL_38:
  if ( *a6 )
  {
    Dns_RecordListFree((LPVOID)*a6);
    *a6 = 0;
  }
LABEL_14:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_Dd(1035, 26, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, *a5, MatchAndGetlocalMachineRecord);
  return MatchAndGetlocalMachineRecord;
}

```

## disassembly

```asm
0x18000dfb8  push    rbx
0x18000dfba  push    rbp
0x18000dfbb  push    rsi
0x18000dfbc  push    rdi
0x18000dfbd  push    r12
0x18000dfbf  push    r13
0x18000dfc1  push    r14
0x18000dfc3  push    r15
0x18000dfc5  sub     rsp, 48h
0x18000dfc9  mov     r12, [rsp+88h+arg_20]
0x18000dfd1  xor     r14d, r14d
0x18000dfd4  mov     ebp, r9d
0x18000dfd7  mov     r13d, r8d
0x18000dfda  movzx   r15d, dx
0x18000dfde  mov     rdi, rcx
0x18000dfe1  lea     ebx, [r14+1]
0x18000dfe5  mov     [r12], r14d
0x18000dfe9  cmp     dx, bx
0x18000dfec  jnz     loc_18000E0E7
0x18000dff2  mov     rsi, [rsp+88h+arg_28]
0x18000dffa  lea     rax, aLoopback; "loopback"
0x18000e001  mov     [rsi], r14
0x18000e004  cmp     rdi, rax
0x18000e007  jz      loc_18000E133
0x18000e00d  test    rdi, rdi
0x18000e010  jz      loc_18000E0A8
0x18000e016  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000e01a  inc     r9; cchCount1
0x18000e01d  cmp     [rcx+r9*2], r14w
0x18000e022  jnz     short loc_18000E01A
0x18000e024  cmp     r9d, 8
0x18000e028  jnz     loc_18000E0FB
0x18000e02e  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x18000e033  mov     r8, rdi; lpString1
0x18000e036  mov     edx, ebx; dwCmpFlags
0x18000e038  mov     [rsp+88h+lpString2], rax; lpString2
0x18000e03d  mov     ecx, 7Fh; Locale
0x18000e042  call    cs:__imp_CompareStringW
0x18000e049  nop     dword ptr [rax+rax+00h]
0x18000e04e  cmp     eax, 2
0x18000e051  jz      loc_18000E133
0x18000e057  lea     rax, aLocalhost; "localhost"
0x18000e05e  cmp     rdi, rax
0x18000e061  jz      loc_18000E133
0x18000e067  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000e06b  inc     r9; cchCount1
0x18000e06e  cmp     [rdi+r9*2], r14w
0x18000e073  jnz     short loc_18000E06B
0x18000e075  cmp     r9d, 9
0x18000e079  jnz     loc_18000E11B
0x18000e07f  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x18000e084  mov     r8, rdi; lpString1
0x18000e087  mov     edx, ebx; dwCmpFlags
0x18000e089  mov     [rsp+88h+lpString2], rax; lpString2
0x18000e08e  mov     ecx, 7Fh; Locale
0x18000e093  call    cs:__imp_CompareStringW
0x18000e09a  nop     dword ptr [rax+rax+00h]
0x18000e09f  cmp     eax, 2
0x18000e0a2  jz      loc_18000E133
0x18000e0a8  mov     qword ptr [rsp+88h+cchCount2], rsi; __int64
0x18000e0ad  mov     r9d, ebp
0x18000e0b0  mov     r8d, r13d
0x18000e0b3  mov     [rsp+88h+lpString2], r12; __int64
0x18000e0b8  movzx   edx, r15w
0x18000e0bc  mov     rcx, rdi; lpString1
0x18000e0bf  call    Query_MatchAndGetlocalMachineRecord
0x18000e0c4  mov     ebx, eax
0x18000e0c6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000e0cd  jnz     loc_18000E2D8
0x18000e0d3  mov     eax, ebx
0x18000e0d5  add     rsp, 48h
0x18000e0d9  pop     r15
0x18000e0db  pop     r14
0x18000e0dd  pop     r13
0x18000e0df  pop     r12
0x18000e0e1  pop     rdi
0x18000e0e2  pop     rsi
0x18000e0e3  pop     rbp
0x18000e0e4  pop     rbx
0x18000e0e5  retn
0x18000e0e7  mov     ebx, r14d
0x18000e0ea  cmp     r15w, 1Ch
0x18000e0ef  jnz     short loc_18000E0C6
0x18000e0f1  mov     ebx, 1
0x18000e0f6  jmp     loc_18000DFF2
0x18000e0fb  cmp     r9d, 9
0x18000e0ff  jnz     loc_18000E057
0x18000e105  cmp     word ptr [rcx+10h], 2Eh ; '.'
0x18000e10a  jnz     loc_18000E057
0x18000e110  mov     r9d, 8
0x18000e116  jmp     loc_18000E02E
0x18000e11b  cmp     r9d, 0Ah
0x18000e11f  jnz     short loc_18000E0A8
0x18000e121  cmp     word ptr [rdi+12h], 2Eh ; '.'
0x18000e126  jnz     short loc_18000E0A8
0x18000e128  mov     r9d, 9
0x18000e12e  jmp     loc_18000E07F
0x18000e133  mov     [r12], ebx
0x18000e137  call    DnsInitWinsock
0x18000e13c  mov     ebx, eax
0x18000e13e  test    eax, eax
0x18000e140  jnz     loc_18000E211
0x18000e146  lea     ebp, [rax+1]
0x18000e149  mov     ebx, 251Dh
0x18000e14e  mov     edx, ebp; type
0x18000e150  lea     r8d, [rax+6]; protocol
0x18000e154  lea     ecx, [rax+2]; af
0x18000e157  call    cs:__imp_socket
0x18000e15e  nop     dword ptr [rax+rax+00h]
0x18000e163  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e167  jz      loc_18000E2D0
0x18000e16d  mov     rcx, rax; s
0x18000e170  call    cs:__imp_closesocket
0x18000e177  nop     dword ptr [rax+rax+00h]
0x18000e17c  mov     edx, 1; type
0x18000e181  lea     ecx, [rdx+16h]; af
0x18000e184  lea     r8d, [rdx+5]; protocol
0x18000e188  call    cs:__imp_socket
0x18000e18f  nop     dword ptr [rax+rax+00h]
0x18000e194  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e198  jz      short loc_18000E1AF
0x18000e19a  mov     rcx, rax; s
0x18000e19d  mov     r14d, 1
0x18000e1a3  call    cs:__imp_closesocket
0x18000e1aa  nop     dword ptr [rax+rax+00h]
0x18000e1af  test    ebp, ebp
0x18000e1b1  jz      short loc_18000E1F5
0x18000e1b3  mov     eax, 1
0x18000e1b8  test    r13d, r13d
0x18000e1bb  jnz     loc_18000E286
0x18000e1c1  cmp     r15w, ax
0x18000e1c5  jnz     short loc_18000E1FA
0x18000e1c7  mov     edx, 100007Fh
0x18000e1cc  mov     dword ptr [rsp+88h+lpString2], eax
0x18000e1d0  mov     r8d, 4B0h
0x18000e1d6  mov     rcx, rdi
0x18000e1d9  call    Dns_CreateARecord
0x18000e1de  mov     rcx, rax
0x18000e1e1  test    rax, rax
0x18000e1e4  jz      loc_18000E2BE
0x18000e1ea  mov     rax, [rsi]
0x18000e1ed  xor     ebx, ebx
0x18000e1ef  mov     [rcx], rax
0x18000e1f2  mov     [rsi], rcx
0x18000e1f5  mov     eax, 1
0x18000e1fa  cmp     r15w, 1Ch
0x18000e1ff  jz      short loc_18000E22A
0x18000e201  call    DnsShutdownWinsock
0x18000e206  xor     r14d, r14d
0x18000e209  test    ebx, ebx
0x18000e20b  jz      loc_18000E0C6
0x18000e211  mov     rcx, [rsi]; lpMem
0x18000e214  test    rcx, rcx
0x18000e217  jz      loc_18000E0C6
0x18000e21d  call    Dns_RecordListFree
0x18000e222  mov     [rsi], r14
0x18000e225  jmp     loc_18000E0C6
0x18000e22a  test    r14d, r14d
0x18000e22d  jz      short loc_18000E201
0x18000e22f  xor     r14d, r14d
0x18000e232  mov     [rsp+88h+var_4C], 1000000h
0x18000e23a  mov     r9d, eax
0x18000e23d  mov     [rsp+88h+var_58], r14
0x18000e242  mov     r8d, 4B0h
0x18000e248  mov     [rsp+88h+var_50], r14d
0x18000e24d  lea     rdx, [rsp+88h+var_58]
0x18000e252  mov     dword ptr [rsp+88h+lpString2], eax
0x18000e256  mov     rcx, rdi
0x18000e259  call    Dns_CreateAAAARecord
0x18000e25e  mov     rcx, rax
0x18000e261  test    rax, rax
0x18000e264  jnz     short loc_18000E270
0x18000e266  lea     ebx, [rax+0Eh]
0x18000e269  call    DnsShutdownWinsock
0x18000e26e  jmp     short loc_18000E211
0x18000e270  mov     rax, [rsi]
0x18000e273  mov     ebx, r14d
0x18000e276  mov     [rcx], rax
0x18000e279  mov     [rsi], rcx
0x18000e27c  call    DnsShutdownWinsock
0x18000e281  jmp     loc_18000E0C6
0x18000e286  mov     r9d, eax
0x18000e289  mov     [rsp+88h+var_58], 0
0x18000e292  mov     r8d, 4B0h
0x18000e298  mov     [rsp+88h+var_50], 0FFFF0000h
0x18000e2a0  lea     rdx, [rsp+88h+var_58]
0x18000e2a5  mov     [rsp+88h+var_4C], 100007Fh
0x18000e2ad  mov     rcx, rdi
0x18000e2b0  mov     dword ptr [rsp+88h+lpString2], eax
0x18000e2b4  call    Dns_CreateAAAARecord
0x18000e2b9  jmp     loc_18000E1DE
0x18000e2be  mov     ebx, 0Eh
0x18000e2c3  call    DnsShutdownWinsock
0x18000e2c8  xor     r14d, r14d
0x18000e2cb  jmp     loc_18000E211
0x18000e2d0  mov     ebp, r14d
0x18000e2d3  jmp     loc_18000E17C
0x18000e2d8  mov     r9d, [r12]
0x18000e2dc  lea     r8, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids
0x18000e2e3  mov     edx, 1Ah
0x18000e2e8  mov     dword ptr [rsp+88h+lpString2], ebx
0x18000e2ec  mov     ecx, 40Bh
0x18000e2f1  call    WPP_SF_Dd
0x18000e2f6  jmp     loc_18000E0D3
```
