# RegWriteMultiValuedString

- ea: `0x180038c44`
- end: `0x180038dca`
- name: `RegWriteMultiValuedString`
- size: `390`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180037098`
- `0x180037500`
- `0x180037ee0`
- `0x180038424`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000e510`
- `0x180038c44`
- `0x18004d052`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038d72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038d72`

## pseudocode

```c
__int64 __fastcall RegWriteMultiValuedString(HKEY hKey, LPCWSTR lpValueName, __int64 a3, unsigned int a4)
{
  unsigned int v4; // esi
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // edx
  unsigned int i; // ecx
  __int64 v14; // rax
  int v15; // r15d
  BYTE *v16; // rax
  BYTE *lpData; // rdi
  BYTE *v18; // rbp
  __int64 v19; // r8
  _WORD *v20; // rdx
  __int64 v21; // rax

  v4 = 0;
  if ( a3 )
  {
    v12 = 0;
    for ( i = 0; i < a4; v12 += v14 + 1 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(*(_QWORD *)(a3 + 8LL * i) + 2 * v14) );
      ++i;
    }
    v15 = v12 + 1;
    v16 = (BYTE *)IpsecAllocMem(2LL * (unsigned int)(v12 + 1));
    lpData = v16;
    if ( v16 )
    {
      v18 = v16;
      if ( a4 )
      {
        do
        {
          v19 = -1;
          v20 = *(_WORD **)(a3 + 8LL * v4);
          do
            ++v19;
          while ( v20[v19] );
          memcpy_0(v18, v20, 2 * v19);
          v21 = -1;
          do
            ++v21;
          while ( *(_WORD *)&v18[2 * v21] );
          ++v4;
          v18 += 2 * v21 + 2;
        }
        while ( v4 < a4 );
      }
      v9 = RegSetValueExW(hKey, lpValueName, 0, 7u, lpData, 2 * v15);
      if ( v9
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v9);
      }
      IpsecFreeMem(lpData);
    }
    else
    {
      v9 = 14;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = 152;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v9 = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = 151;
LABEL_5:
      WPP_SF_d(v10[2], v11, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v9);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180038c44  push    rbx
0x180038c46  push    rbp
0x180038c47  push    rsi
0x180038c48  push    rdi
0x180038c49  push    r12
0x180038c4b  push    r13
0x180038c4d  push    r14
0x180038c4f  push    r15
0x180038c51  sub     rsp, 38h
0x180038c55  xor     esi, esi
0x180038c57  mov     ebx, r9d
0x180038c5a  mov     r14, r8
0x180038c5d  mov     r12, rdx
0x180038c60  mov     r13, rcx
0x180038c63  test    r8, r8
0x180038c66  jnz     short loc_180038CA7
0x180038c68  lea     ebx, [rsi+57h]
0x180038c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c72  lea     rax, WPP_GLOBAL_Control
0x180038c79  cmp     rcx, rax
0x180038c7c  jz      loc_180038DB7
0x180038c82  test    byte ptr [rcx+1Ch], 10h
0x180038c86  jz      loc_180038DB7
0x180038c8c  lea     edx, [rbx+40h]
0x180038c8f  mov     rcx, [rcx+10h]
0x180038c93  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180038c9a  mov     r9d, ebx
0x180038c9d  call    WPP_SF_d
0x180038ca2  jmp     loc_180038DB7
0x180038ca7  mov     edx, esi
0x180038ca9  mov     ecx, esi
0x180038cab  test    ebx, ebx
0x180038cad  jz      short loc_180038CCD
0x180038caf  mov     eax, ecx
0x180038cb1  mov     r8, [r14+rax*8]
0x180038cb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038cb9  inc     rax
0x180038cbc  cmp     [r8+rax*2], si
0x180038cc1  jnz     short loc_180038CB9
0x180038cc3  inc     edx
0x180038cc5  inc     ecx
0x180038cc7  add     edx, eax
0x180038cc9  cmp     ecx, ebx
0x180038ccb  jb      short loc_180038CAF
0x180038ccd  lea     r15d, [rdx+1]
0x180038cd1  mov     ecx, r15d
0x180038cd4  add     rcx, rcx
0x180038cd7  call    IpsecAllocMem
0x180038cdc  mov     rdi, rax
0x180038cdf  test    rax, rax
0x180038ce2  jnz     short loc_180038D0F
0x180038ce4  lea     ebx, [rax+0Eh]
0x180038ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180038cee  lea     rax, WPP_GLOBAL_Control
0x180038cf5  cmp     rcx, rax
0x180038cf8  jz      loc_180038DB7
0x180038cfe  test    byte ptr [rcx+1Ch], 10h
0x180038d02  jz      loc_180038DB7
0x180038d08  mov     edx, 98h
0x180038d0d  jmp     short loc_180038C8F
0x180038d0f  xor     ecx, ecx
0x180038d11  mov     rbp, rdi
0x180038d14  test    ebx, ebx
0x180038d16  jz      short loc_180038D56
0x180038d18  mov     eax, esi
0x180038d1a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038d1e  mov     rdx, [r14+rax*8]; Src
0x180038d22  inc     r8
0x180038d25  cmp     [rdx+r8*2], cx
0x180038d2a  jnz     short loc_180038D22
0x180038d2c  add     r8, r8; Size
0x180038d2f  mov     rcx, rbp; void *
0x180038d32  call    memcpy_0
0x180038d37  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038d3b  xor     ecx, ecx
0x180038d3d  inc     rax
0x180038d40  cmp     [rbp+rax*2+0], cx
0x180038d45  jnz     short loc_180038D3D
0x180038d47  lea     rbp, [rbp+rax*2+0]
0x180038d4c  inc     esi
0x180038d4e  add     rbp, 2
0x180038d52  cmp     esi, ebx
0x180038d54  jb      short loc_180038D18
0x180038d56  lea     eax, [r15+r15]
0x180038d5a  mov     r9d, 7; dwType
0x180038d60  mov     [rsp+78h+cbData], eax; cbData
0x180038d64  xor     r8d, r8d; Reserved
0x180038d67  mov     rdx, r12; lpValueName
0x180038d6a  mov     [rsp+78h+lpData], rdi; lpData
0x180038d6f  mov     rcx, r13; hKey
0x180038d72  call    cs:__imp_RegSetValueExW
0x180038d78  mov     ebx, eax
0x180038d7a  test    eax, eax
0x180038d7c  jz      short loc_180038DAF
0x180038d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d85  lea     rax, WPP_GLOBAL_Control
0x180038d8c  cmp     rcx, rax
0x180038d8f  jz      short loc_180038DAF
0x180038d91  test    byte ptr [rcx+1Ch], 10h
0x180038d95  jz      short loc_180038DAF
0x180038d97  mov     rcx, [rcx+10h]
0x180038d9b  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180038da2  mov     edx, 99h
0x180038da7  mov     r9d, ebx
0x180038daa  call    WPP_SF_d
0x180038daf  mov     rcx, rdi; lpMem
0x180038db2  call    IpsecFreeMem
0x180038db7  mov     eax, ebx
0x180038db9  add     rsp, 38h
0x180038dbd  pop     r15
0x180038dbf  pop     r14
0x180038dc1  pop     r13
0x180038dc3  pop     r12
0x180038dc5  pop     rdi
0x180038dc6  pop     rsi
0x180038dc7  pop     rbp
0x180038dc8  pop     rbx
0x180038dc9  retn
```
