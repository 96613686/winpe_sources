# UpdateJobInfo

- ea: `0x180006cd8`
- end: `0x180006fa0`
- name: `UpdateJobInfo`
- size: `712`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180005a14`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x180006b18`
- `0x180006c2c`
- `0x180006cd8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180006d98`
- `KERNEL32!LocalAlloc` at `0x180006ea2`
- `KERNEL32!LocalAlloc` at `0x180006d98`
- `KERNEL32!LocalAlloc` at `0x180006ea2`
- `KERNEL32!GetLastError` at `0x180006d58`
- `KERNEL32!GetLastError` at `0x180006d58`
- `KERNEL32!LocalFree` at `0x180006e27`
- `KERNEL32!LocalFree` at `0x180006f65`
- `KERNEL32!LocalFree` at `0x180006f73`
- `KERNEL32!LocalFree` at `0x180006f81`
- `KERNEL32!LocalFree` at `0x180006e27`
- `KERNEL32!LocalFree` at `0x180006f65`
- `KERNEL32!LocalFree` at `0x180006f73`
- `KERNEL32!LocalFree` at `0x180006f81`
- `WINSPOOL!GetJobA` at `0x180006d4e`
- `WINSPOOL!GetJobA` at `0x180006df5`
- `WINSPOOL!GetJobA` at `0x180006d4e`
- `WINSPOOL!GetJobA` at `0x180006df5`
- `WINSPOOL!SetJobA` at `0x180006f30`
- `WINSPOOL!SetJobA` at `0x180006f30`

## pseudocode

```c
__int64 __fastcall UpdateJobInfo(__int64 a1, __int64 a2)
{
  BYTE *v5; // rax
  BYTE *v6; // rbx
  char *v7; // rdi
  void *v8; // r14
  void *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  SIZE_T v13; // rsi
  char *v14; // rax
  __int64 v15; // rax
  const char *v16; // r8
  SIZE_T v17; // rdx
  char *v18; // rcx
  DWORD pcbNeeded; // [rsp+60h] [rbp+8h] BYREF

  pcbNeeded = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
  if ( !GetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(a1 + 104), 2u, 0, 0, &pcbNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20006;
  }
  v5 = (BYTE *)LocalAlloc(0, pcbNeeded);
  v6 = v5;
  if ( v5 )
  {
    if ( !GetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(a1 + 104), 2u, v5, pcbNeeded, &pcbNeeded) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
      LocalFree(v6);
      return 20006;
    }
    v7 = 0;
    v8 = (void *)StoreIpAddr(a1);
    v9 = v8;
    if ( !v8 )
      v9 = *(void **)(a2 + 56);
    *((_QWORD *)v6 + 3) = v9;
    *((_QWORD *)v6 + 5) = *(_QWORD *)(a2 + 56);
    v10 = *(_QWORD *)(a2 + 72);
    if ( !v10 )
    {
      v10 = *(_QWORD *)(a2 + 48);
      if ( !v10 )
      {
        v10 = qword_1800136F0;
        if ( *(_QWORD *)(a2 + 24) )
          v10 = *(_QWORD *)(a2 + 24);
      }
    }
    *((_QWORD *)v6 + 4) = v10;
    v11 = *(_QWORD *)(a2 + 8);
    if ( v11 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_BYTE *)(v11 + v12) );
      v13 = (int)v12 + 9;
      v14 = (char *)LocalAlloc(0, v13);
      v7 = v14;
      if ( v14 )
      {
        if ( v13 )
        {
          if ( v13 <= 0x7FFFFFFF )
          {
            v15 = 2147483646;
            v16 = "job=lpd";
            v17 = v13;
            v18 = v7;
            do
            {
              if ( !v15 )
                break;
              if ( !*v16 )
                break;
              *v18++ = *v16++;
              --v15;
              --v17;
            }
            while ( v17 );
            v14 = v18 - 1;
            if ( v17 )
              v14 = v18;
          }
          *v14 = 0;
        }
        StringCchCatA(v7, v13, *(STRSAFE_LPCSTR *)(a2 + 8));
        *((_QWORD *)v6 + 8) = v7;
      }
    }
    *((_DWORD *)v6 + 28) = 0;
    if ( !SetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(a1 + 104), 2u, v6, 0)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids, 0);
    }
    LocalFree(v6);
    if ( v8 )
      LocalFree(v8);
    if ( v7 )
      LocalFree(v7);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20001;
  }
}

```

## disassembly

```asm
0x180006cd8  mov     [rsp+arg_8], rbx
0x180006cdd  mov     [rsp+arg_10], rbp
0x180006ce2  push    rsi
0x180006ce3  push    rdi
0x180006ce4  push    r13
0x180006ce6  push    r14
0x180006ce8  push    r15
0x180006cea  sub     rsp, 30h
0x180006cee  mov     rbp, rdx
0x180006cf1  mov     [rsp+58h+arg_0], 0
0x180006cf9  mov     r15, rcx
0x180006cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d03  lea     r13, WPP_GLOBAL_Control
0x180006d0a  cmp     rcx, r13
0x180006d0d  jz      short loc_180006D2A
0x180006d0f  test    byte ptr [rcx+1Ch], 1
0x180006d13  jz      short loc_180006D2A
0x180006d15  mov     rcx, [rcx+10h]
0x180006d19  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006d20  mov     edx, 1Bh
0x180006d25  call    WPP_SF_
0x180006d2a  mov     edx, [r15+68h]; JobId
0x180006d2e  lea     rax, [rsp+58h+arg_0]
0x180006d33  mov     rcx, [r15+60h]; hPrinter
0x180006d37  xor     r9d, r9d; pJob
0x180006d3a  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x180006d3f  mov     [rsp+58h+cbBuf], 0; cbBuf
0x180006d47  lea     edi, [r9+2]
0x180006d4b  mov     r8d, edi; Level
0x180006d4e  call    cs:__imp_GetJobA
0x180006d54  test    eax, eax
0x180006d56  jnz     short loc_180006D92
0x180006d58  call    cs:__imp_GetLastError
0x180006d5e  cmp     eax, 7Ah ; 'z'
0x180006d61  jz      short loc_180006D92
0x180006d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d6a  cmp     rcx, r13
0x180006d6d  jz      short loc_180006D88
0x180006d6f  test    byte ptr [rcx+1Ch], 8
0x180006d73  jz      short loc_180006D88
0x180006d75  mov     rcx, [rcx+10h]
0x180006d79  lea     edx, [rdi+1Ah]
0x180006d7c  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006d83  call    WPP_SF_
0x180006d88  mov     eax, 4E26h
0x180006d8d  jmp     loc_180006F89
0x180006d92  mov     edx, [rsp+58h+arg_0]; uBytes
0x180006d96  xor     ecx, ecx; uFlags
0x180006d98  call    cs:__imp_LocalAlloc
0x180006d9e  mov     rbx, rax
0x180006da1  test    rax, rax
0x180006da4  jnz     short loc_180006DD5
0x180006da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dad  cmp     rcx, r13
0x180006db0  jz      short loc_180006DCB
0x180006db2  test    byte ptr [rcx+1Ch], 8
0x180006db6  jz      short loc_180006DCB
0x180006db8  mov     rcx, [rcx+10h]
0x180006dbc  lea     edx, [rax+1Dh]
0x180006dbf  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006dc6  call    WPP_SF_
0x180006dcb  mov     eax, 4E21h
0x180006dd0  jmp     loc_180006F89
0x180006dd5  mov     edx, [r15+68h]; JobId
0x180006dd9  lea     rax, [rsp+58h+arg_0]
0x180006dde  mov     rcx, [r15+60h]; hPrinter
0x180006de2  mov     r9, rbx; pJob
0x180006de5  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x180006dea  mov     r8d, edi; Level
0x180006ded  mov     eax, [rsp+58h+arg_0]
0x180006df1  mov     [rsp+58h+cbBuf], eax; cbBuf
0x180006df5  call    cs:__imp_GetJobA
0x180006dfb  test    eax, eax
0x180006dfd  jnz     short loc_180006E32
0x180006dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e06  cmp     rcx, r13
0x180006e09  jz      short loc_180006E24
0x180006e0b  test    byte ptr [rcx+1Ch], 8
0x180006e0f  jz      short loc_180006E24
0x180006e11  mov     rcx, [rcx+10h]
0x180006e15  lea     edx, [rax+1Eh]
0x180006e18  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006e1f  call    WPP_SF_
0x180006e24  mov     rcx, rbx; hMem
0x180006e27  call    cs:__imp_LocalFree
0x180006e2d  jmp     loc_180006D88
0x180006e32  mov     rcx, r15
0x180006e35  xor     edi, edi
0x180006e37  call    StoreIpAddr
0x180006e3c  mov     r14, rax
0x180006e3f  mov     rcx, rax
0x180006e42  test    rax, rax
0x180006e45  jnz     short loc_180006E4B
0x180006e47  mov     rcx, [rbp+38h]
0x180006e4b  mov     [rbx+18h], rcx
0x180006e4f  mov     rax, [rbp+38h]
0x180006e53  mov     [rbx+28h], rax
0x180006e57  mov     rax, [rbp+48h]
0x180006e5b  test    rax, rax
0x180006e5e  jnz     short loc_180006E79
0x180006e60  mov     rax, [rbp+30h]
0x180006e64  test    rax, rax
0x180006e67  jnz     short loc_180006E79
0x180006e69  cmp     [rbp+18h], rdi
0x180006e6d  mov     rax, cs:qword_1800136F0
0x180006e74  cmovnz  rax, [rbp+18h]
0x180006e79  mov     [rbx+20h], rax
0x180006e7d  mov     rcx, [rbp+8]
0x180006e81  test    rcx, rcx
0x180006e84  jz      loc_180006F10
0x180006e8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006e8e  inc     rax
0x180006e91  cmp     [rcx+rax], dil
0x180006e95  jnz     short loc_180006E8E
0x180006e97  add     eax, 9
0x180006e9a  xor     ecx, ecx; uFlags
0x180006e9c  movsxd  rsi, eax
0x180006e9f  mov     rdx, rsi; uBytes
0x180006ea2  call    cs:__imp_LocalAlloc
0x180006ea8  mov     rdi, rax
0x180006eab  test    rax, rax
0x180006eae  jz      short loc_180006F10
0x180006eb0  test    rsi, rsi
0x180006eb3  jz      short loc_180006EFD
0x180006eb5  cmp     rsi, 7FFFFFFFh
0x180006ebc  ja      short loc_180006EFA
0x180006ebe  mov     eax, 7FFFFFFEh
0x180006ec3  lea     r8, aJobLpd; "job=lpd"
0x180006eca  mov     rdx, rsi
0x180006ecd  mov     rcx, rdi
0x180006ed0  test    rax, rax
0x180006ed3  jz      short loc_180006EEF
0x180006ed5  mov     r9b, [r8]
0x180006ed8  test    r9b, r9b
0x180006edb  jz      short loc_180006EEF
0x180006edd  mov     [rcx], r9b
0x180006ee0  inc     r8
0x180006ee3  inc     rcx
0x180006ee6  dec     rax
0x180006ee9  sub     rdx, 1
0x180006eed  jnz     short loc_180006ED0
0x180006eef  test    rdx, rdx
0x180006ef2  lea     rax, [rcx-1]
0x180006ef6  cmovnz  rax, rcx
0x180006efa  mov     byte ptr [rax], 0
0x180006efd  mov     r8, [rbp+8]; pszSrc
0x180006f01  mov     rdx, rsi; cchDest
0x180006f04  mov     rcx, rdi; pszDest
0x180006f07  call    StringCchCatA
0x180006f0c  mov     [rbx+40h], rdi
0x180006f10  mov     dword ptr [rbx+70h], 0
0x180006f17  mov     r9, rbx; pJob
0x180006f1a  mov     edx, [r15+68h]; JobId
0x180006f1e  mov     r8d, 2; Level
0x180006f24  mov     rcx, [r15+60h]; hPrinter
0x180006f28  mov     [rsp+58h+cbBuf], 0; Command
0x180006f30  call    cs:__imp_SetJobA
0x180006f36  test    eax, eax
0x180006f38  jnz     short loc_180006F62
0x180006f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f41  cmp     rcx, r13
0x180006f44  jz      short loc_180006F62
0x180006f46  test    byte ptr [rcx+1Ch], 8
0x180006f4a  jz      short loc_180006F62
0x180006f4c  mov     rcx, [rcx+10h]
0x180006f50  lea     edx, [rax+1Fh]
0x180006f53  xor     r9d, r9d
0x180006f56  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006f5d  call    WPP_SF_d
0x180006f62  mov     rcx, rbx; hMem
0x180006f65  call    cs:__imp_LocalFree
0x180006f6b  test    r14, r14
0x180006f6e  jz      short loc_180006F79
0x180006f70  mov     rcx, r14; hMem
0x180006f73  call    cs:__imp_LocalFree
0x180006f79  test    rdi, rdi
0x180006f7c  jz      short loc_180006F87
0x180006f7e  mov     rcx, rdi; hMem
0x180006f81  call    cs:__imp_LocalFree
0x180006f87  xor     eax, eax
0x180006f89  mov     rbx, [rsp+58h+arg_8]
0x180006f8e  mov     rbp, [rsp+58h+arg_10]
0x180006f93  add     rsp, 30h
0x180006f97  pop     r15
0x180006f99  pop     r14
0x180006f9b  pop     r13
0x180006f9d  pop     rdi
0x180006f9e  pop     rsi
0x180006f9f  retn
```
