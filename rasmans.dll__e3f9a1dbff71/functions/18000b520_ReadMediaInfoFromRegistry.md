# ReadMediaInfoFromRegistry

- ea: `0x18000b520`
- end: `0x18000b7eb`
- name: `ReadMediaInfoFromRegistry`
- size: `715`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180009348`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000b520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b6a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b6a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b62e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b62e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b771`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b771`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b594`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b77a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b77a`

## string_xrefs

- `0x18000b620`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
__int64 __fastcall ReadMediaInfoFromRegistry(unsigned __int16 *a1)
{
  BYTE *v2; // rdi
  DWORD LastError; // eax
  unsigned int v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int16 v11; // r9
  BYTE *v12; // r8
  __int64 v13; // rax
  BYTE *v14; // r10
  unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  __int64 v18; // rax
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 126, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
  }
  hKey = 0;
  cbData = 2000;
  Type = 0;
  v2 = (BYTE *)LocalAlloc(0x40u, 0x7D0u);
  if ( !v2 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_12;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, LastError);
    }
    v5 = WPP_GLOBAL_Control;
LABEL_12:
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 6u )
    {
      v6 = 128;
LABEL_46:
      WPP_SF_d(v5[1].Flink, v6, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v4);
      return v4;
    }
    return v4;
  }
  v7 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 1u, &hKey);
  v4 = v7;
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v9 = 129;
LABEL_21:
      v10 = v7;
LABEL_22:
      WPP_SF_d(v8[1].Flink, v9, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v10);
    }
  }
  else
  {
    v7 = RegQueryValueExA(hKey, "Medias", 0, &Type, v2, &cbData);
    v4 = v7;
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v9 = 130;
        goto LABEL_21;
      }
    }
    else
    {
      v11 = 0;
      v12 = v2;
      if ( *v2 )
      {
        while ( 1 )
        {
          v13 = 2147483646;
          v14 = v12;
          v15 = &a1[8 * v11 + 1];
          v16 = 16;
          do
          {
            if ( !v13 )
              break;
            if ( !*v14 )
              break;
            *(_BYTE *)v15 = *v14;
            v15 = (unsigned __int16 *)((char *)v15 + 1);
            ++v14;
            --v13;
            --v16;
          }
          while ( v16 );
          v17 = (unsigned __int16 *)((char *)v15 - 1);
          v4 = v16 == 0 ? 0x8007007A : 0;
          if ( v16 )
            v17 = v15;
          *(_BYTE *)v17 = 0;
          if ( !v16 )
            break;
          v18 = -1;
          do
            ++v18;
          while ( v12[v18] );
          ++v11;
          v12 += v18 + 1;
          if ( !*v12 )
            goto LABEL_39;
        }
        v10 = (unsigned __int16)v4;
        v4 = (unsigned __int16)v4;
        if ( (_WORD)v4 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v9 = 131;
            goto LABEL_22;
          }
        }
      }
      else
      {
LABEL_39:
        *a1 = v11;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v2);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v6 = 132;
    goto LABEL_46;
  }
  return v4;
}

```

## disassembly

```asm
0x18000b520  push    rbx
0x18000b522  push    rbp
0x18000b523  push    rsi
0x18000b524  push    rdi
0x18000b525  push    r12
0x18000b527  push    r13
0x18000b529  push    r15
0x18000b52b  sub     rsp, 30h
0x18000b52f  mov     rsi, rcx
0x18000b532  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b539  lea     r12, WPP_GLOBAL_Control
0x18000b540  lea     r13, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18000b547  mov     r15d, 2000h
0x18000b54d  cmp     rcx, r12
0x18000b550  jz      short loc_18000B56F
0x18000b552  test    [rcx+1Ch], r15d
0x18000b556  jz      short loc_18000B56F
0x18000b558  cmp     byte ptr [rcx+19h], 6
0x18000b55c  jb      short loc_18000B56F
0x18000b55e  mov     rcx, [rcx+10h]
0x18000b562  mov     edx, 7Eh ; '~'
0x18000b567  mov     r8, r13
0x18000b56a  call    WPP_SF_
0x18000b56f  mov     edx, 7D0h; uBytes
0x18000b574  mov     [rsp+68h+hKey], 0
0x18000b580  mov     ecx, 40h ; '@'; uFlags
0x18000b585  mov     [rsp+68h+cbData], edx
0x18000b589  mov     [rsp+68h+Type], 0
0x18000b594  call    cs:__imp_LocalAlloc
0x18000b59a  mov     rdi, rax
0x18000b59d  test    rax, rax
0x18000b5a0  jnz     short loc_18000B60A
0x18000b5a2  call    cs:__imp_GetLastError
0x18000b5a8  mov     ebx, eax
0x18000b5aa  test    eax, eax
0x18000b5ac  jz      short loc_18000B5DC
0x18000b5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5b5  cmp     rcx, r12
0x18000b5b8  jz      loc_18000B7AC
0x18000b5be  test    [rcx+1Ch], r15d
0x18000b5c2  jz      short loc_18000B5E3
0x18000b5c4  cmp     byte ptr [rcx+19h], 2
0x18000b5c8  jb      short loc_18000B5E3
0x18000b5ca  mov     rcx, [rcx+10h]
0x18000b5ce  lea     edx, [rdi+7Fh]
0x18000b5d1  mov     r9d, eax
0x18000b5d4  mov     r8, r13
0x18000b5d7  call    WPP_SF_d
0x18000b5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5e3  cmp     rcx, r12
0x18000b5e6  jz      loc_18000B7AC
0x18000b5ec  test    [rcx+1Ch], r15d
0x18000b5f0  jz      loc_18000B7AC
0x18000b5f6  cmp     byte ptr [rcx+19h], 6
0x18000b5fa  jb      loc_18000B7AC
0x18000b600  mov     edx, 80h
0x18000b605  jmp     loc_18000B79D
0x18000b60a  lea     rax, [rsp+68h+hKey]
0x18000b612  mov     r9d, 1; samDesired
0x18000b618  xor     r8d, r8d; ulOptions
0x18000b61b  mov     [rsp+68h+phkResult], rax; phkResult
0x18000b620  lea     rdx, aSystemCurrentc_20; "System\\CurrentControlSet\\Services\\Ra"...
0x18000b627  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b62e  call    cs:__imp_RegOpenKeyExA
0x18000b634  mov     ebx, eax
0x18000b636  test    eax, eax
0x18000b638  jz      short loc_18000B677
0x18000b63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b641  cmp     rcx, r12
0x18000b644  jz      loc_18000B764
0x18000b64a  test    [rcx+1Ch], r15d
0x18000b64e  jz      loc_18000B764
0x18000b654  cmp     byte ptr [rcx+19h], 2
0x18000b658  jb      loc_18000B764
0x18000b65e  mov     edx, 81h
0x18000b663  mov     r9d, eax
0x18000b666  mov     rcx, [rcx+10h]
0x18000b66a  mov     r8, r13
0x18000b66d  call    WPP_SF_d
0x18000b672  jmp     loc_18000B764
0x18000b677  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b67f  lea     rax, [rsp+68h+cbData]
0x18000b684  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000b689  lea     r9, [rsp+68h+Type]; lpType
0x18000b691  xor     r8d, r8d; lpReserved
0x18000b694  mov     [rsp+68h+phkResult], rdi; lpData
0x18000b699  lea     rdx, aMedias; "Medias"
0x18000b6a0  call    cs:__imp_RegQueryValueExA
0x18000b6a6  mov     ebx, eax
0x18000b6a8  test    eax, eax
0x18000b6aa  jz      short loc_18000B6D7
0x18000b6ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6b3  cmp     rcx, r12
0x18000b6b6  jz      loc_18000B764
0x18000b6bc  test    [rcx+1Ch], r15d
0x18000b6c0  jz      loc_18000B764
0x18000b6c6  cmp     byte ptr [rcx+19h], 2
0x18000b6ca  jb      loc_18000B764
0x18000b6d0  mov     edx, 82h
0x18000b6d5  jmp     short loc_18000B663
0x18000b6d7  xor     r9d, r9d
0x18000b6da  mov     r8, rdi
0x18000b6dd  cmp     [rdi], r9b
0x18000b6e0  jz      short loc_18000B760
0x18000b6e2  lea     rbp, [rsi+2]
0x18000b6e6  movzx   ecx, r9w
0x18000b6ea  mov     eax, 7FFFFFFEh
0x18000b6ef  shl     rcx, 4
0x18000b6f3  mov     r10, r8
0x18000b6f6  add     rcx, rbp
0x18000b6f9  mov     edx, 10h
0x18000b6fe  test    rax, rax
0x18000b701  jz      short loc_18000B722
0x18000b703  mov     r11b, [r10]
0x18000b706  test    r11b, r11b
0x18000b709  jz      short loc_18000B722
0x18000b70b  mov     [rcx], r11b
0x18000b70e  mov     r11d, 1
0x18000b714  add     rcx, r11
0x18000b717  add     r10, r11
0x18000b71a  sub     rax, r11
0x18000b71d  sub     rdx, r11
0x18000b720  jnz     short loc_18000B6FE
0x18000b722  mov     rax, rdx
0x18000b725  neg     rax
0x18000b728  lea     rax, [rcx-1]
0x18000b72c  sbb     ebx, ebx
0x18000b72e  not     ebx
0x18000b730  and     ebx, 8007007Ah
0x18000b736  test    rdx, rdx
0x18000b739  cmovnz  rax, rcx
0x18000b73d  mov     byte ptr [rax], 0
0x18000b740  jz      short loc_18000B7BD
0x18000b742  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b746  inc     rax
0x18000b749  cmp     byte ptr [r8+rax], 0
0x18000b74e  jnz     short loc_18000B746
0x18000b750  inc     r8
0x18000b753  inc     r9w
0x18000b757  add     r8, rax
0x18000b75a  cmp     byte ptr [r8], 0
0x18000b75e  jnz     short loc_18000B6E6
0x18000b760  mov     [rsi], r9w
0x18000b764  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b76c  test    rcx, rcx
0x18000b76f  jz      short loc_18000B777
0x18000b771  call    cs:__imp_RegCloseKey
0x18000b777  mov     rcx, rdi; hMem
0x18000b77a  call    cs:__imp_LocalFree
0x18000b780  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b787  cmp     rcx, r12
0x18000b78a  jz      short loc_18000B7AC
0x18000b78c  test    [rcx+1Ch], r15d
0x18000b790  jz      short loc_18000B7AC
0x18000b792  cmp     byte ptr [rcx+19h], 6
0x18000b796  jb      short loc_18000B7AC
0x18000b798  mov     edx, 84h
0x18000b79d  mov     rcx, [rcx+10h]
0x18000b7a1  mov     r9d, ebx
0x18000b7a4  mov     r8, r13
0x18000b7a7  call    WPP_SF_d
0x18000b7ac  mov     eax, ebx
0x18000b7ae  add     rsp, 30h
0x18000b7b2  pop     r15
0x18000b7b4  pop     r13
0x18000b7b6  pop     r12
0x18000b7b8  pop     rdi
0x18000b7b9  pop     rsi
0x18000b7ba  pop     rbp
0x18000b7bb  pop     rbx
0x18000b7bc  retn
0x18000b7bd  movzx   r9d, bx
0x18000b7c1  mov     ebx, r9d
0x18000b7c4  test    r9d, r9d
0x18000b7c7  jz      short loc_18000B764
0x18000b7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7d0  cmp     rcx, r12
0x18000b7d3  jz      short loc_18000B764
0x18000b7d5  test    [rcx+1Ch], r15d
0x18000b7d9  jz      short loc_18000B764
0x18000b7db  cmp     byte ptr [rcx+19h], 2
0x18000b7df  jb      short loc_18000B764
0x18000b7e1  mov     edx, 83h
0x18000b7e6  jmp     loc_18000B666
```
