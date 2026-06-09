# ReadMediaInfoFromRegistry

- ea: `0x18000b8a8`
- end: `0x18000bba8`
- name: `ReadMediaInfoFromRegistry`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000944c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000b8a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b930`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b9c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b9c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000ba3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000ba3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b91c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b91c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb28`

## string_xrefs

- `0x18000b9b4`: `System\CurrentControlSet\Services\Rasman\Parameters`

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
0x18000b8a8  push    rbx
0x18000b8aa  push    rbp
0x18000b8ab  push    rsi
0x18000b8ac  push    rdi
0x18000b8ad  push    r12
0x18000b8af  push    r13
0x18000b8b1  push    r15
0x18000b8b3  sub     rsp, 30h
0x18000b8b7  mov     rsi, rcx
0x18000b8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8c1  lea     r12, WPP_GLOBAL_Control
0x18000b8c8  lea     r13, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18000b8cf  mov     r15d, 2000h
0x18000b8d5  cmp     rcx, r12
0x18000b8d8  jz      short loc_18000B8F7
0x18000b8da  test    [rcx+1Ch], r15d
0x18000b8de  jz      short loc_18000B8F7
0x18000b8e0  cmp     byte ptr [rcx+19h], 6
0x18000b8e4  jb      short loc_18000B8F7
0x18000b8e6  mov     rcx, [rcx+10h]
0x18000b8ea  mov     edx, 7Eh ; '~'
0x18000b8ef  mov     r8, r13
0x18000b8f2  call    WPP_SF_
0x18000b8f7  mov     edx, 7D0h; uBytes
0x18000b8fc  mov     [rsp+68h+hKey], 0
0x18000b908  mov     ecx, 40h ; '@'; uFlags
0x18000b90d  mov     [rsp+68h+cbData], edx
0x18000b911  mov     [rsp+68h+Type], 0
0x18000b91c  call    cs:__imp_LocalAlloc
0x18000b923  nop     dword ptr [rax+rax+00h]
0x18000b928  mov     rdi, rax
0x18000b92b  test    rax, rax
0x18000b92e  jnz     short loc_18000B99E
0x18000b930  call    cs:__imp_GetLastError
0x18000b937  nop     dword ptr [rax+rax+00h]
0x18000b93c  mov     ebx, eax
0x18000b93e  test    eax, eax
0x18000b940  jz      short loc_18000B970
0x18000b942  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b949  cmp     rcx, r12
0x18000b94c  jz      loc_18000BB60
0x18000b952  test    [rcx+1Ch], r15d
0x18000b956  jz      short loc_18000B977
0x18000b958  cmp     byte ptr [rcx+19h], 2
0x18000b95c  jb      short loc_18000B977
0x18000b95e  mov     rcx, [rcx+10h]
0x18000b962  lea     edx, [rdi+7Fh]
0x18000b965  mov     r9d, eax
0x18000b968  mov     r8, r13
0x18000b96b  call    WPP_SF_d
0x18000b970  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b977  cmp     rcx, r12
0x18000b97a  jz      loc_18000BB60
0x18000b980  test    [rcx+1Ch], r15d
0x18000b984  jz      loc_18000BB60
0x18000b98a  cmp     byte ptr [rcx+19h], 6
0x18000b98e  jb      loc_18000BB60
0x18000b994  mov     edx, 80h
0x18000b999  jmp     loc_18000BB51
0x18000b99e  lea     rax, [rsp+68h+hKey]
0x18000b9a6  mov     r9d, 1; samDesired
0x18000b9ac  xor     r8d, r8d; ulOptions
0x18000b9af  mov     [rsp+68h+phkResult], rax; phkResult
0x18000b9b4  lea     rdx, aSystemCurrentc_20; "System\\CurrentControlSet\\Services\\Ra"...
0x18000b9bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b9c2  call    cs:__imp_RegOpenKeyExA
0x18000b9c9  nop     dword ptr [rax+rax+00h]
0x18000b9ce  mov     ebx, eax
0x18000b9d0  test    eax, eax
0x18000b9d2  jz      short loc_18000BA11
0x18000b9d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9db  cmp     rcx, r12
0x18000b9de  jz      loc_18000BB0C
0x18000b9e4  test    [rcx+1Ch], r15d
0x18000b9e8  jz      loc_18000BB0C
0x18000b9ee  cmp     byte ptr [rcx+19h], 2
0x18000b9f2  jb      loc_18000BB0C
0x18000b9f8  mov     edx, 81h
0x18000b9fd  mov     r9d, eax
0x18000ba00  mov     rcx, [rcx+10h]
0x18000ba04  mov     r8, r13
0x18000ba07  call    WPP_SF_d
0x18000ba0c  jmp     loc_18000BB0C
0x18000ba11  mov     rcx, [rsp+68h+hKey]; hKey
0x18000ba19  lea     rax, [rsp+68h+cbData]
0x18000ba1e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000ba23  lea     r9, [rsp+68h+Type]; lpType
0x18000ba2b  xor     r8d, r8d; lpReserved
0x18000ba2e  mov     [rsp+68h+phkResult], rdi; lpData
0x18000ba33  lea     rdx, aMedias; "Medias"
0x18000ba3a  call    cs:__imp_RegQueryValueExA
0x18000ba41  nop     dword ptr [rax+rax+00h]
0x18000ba46  mov     ebx, eax
0x18000ba48  test    eax, eax
0x18000ba4a  jz      short loc_18000BA77
0x18000ba4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba53  cmp     rcx, r12
0x18000ba56  jz      loc_18000BB0C
0x18000ba5c  test    [rcx+1Ch], r15d
0x18000ba60  jz      loc_18000BB0C
0x18000ba66  cmp     byte ptr [rcx+19h], 2
0x18000ba6a  jb      loc_18000BB0C
0x18000ba70  mov     edx, 82h
0x18000ba75  jmp     short loc_18000B9FD
0x18000ba77  xor     r9d, r9d
0x18000ba7a  mov     r8, rdi
0x18000ba7d  cmp     [rdi], r9b
0x18000ba80  jz      loc_18000BB08
0x18000ba86  lea     rbp, [rsi+2]
0x18000ba8a  movzx   ecx, r9w
0x18000ba8e  mov     eax, 7FFFFFFEh
0x18000ba93  shl     rcx, 4
0x18000ba97  mov     r10, r8
0x18000ba9a  add     rcx, rbp
0x18000ba9d  mov     edx, 10h
0x18000baa2  test    rax, rax
0x18000baa5  jz      short loc_18000BAC6
0x18000baa7  mov     r11b, [r10]
0x18000baaa  test    r11b, r11b
0x18000baad  jz      short loc_18000BAC6
0x18000baaf  mov     [rcx], r11b
0x18000bab2  mov     r11d, 1
0x18000bab8  add     rcx, r11
0x18000babb  add     r10, r11
0x18000babe  sub     rax, r11
0x18000bac1  sub     rdx, r11
0x18000bac4  jnz     short loc_18000BAA2
0x18000bac6  mov     rax, rdx
0x18000bac9  neg     rax
0x18000bacc  lea     rax, [rcx-1]
0x18000bad0  sbb     ebx, ebx
0x18000bad2  not     ebx
0x18000bad4  and     ebx, 8007007Ah
0x18000bada  test    rdx, rdx
0x18000badd  cmovnz  rax, rcx
0x18000bae1  mov     byte ptr [rax], 0
0x18000bae4  jz      loc_18000BB72
0x18000baea  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000baee  inc     rax
0x18000baf1  cmp     byte ptr [r8+rax], 0
0x18000baf6  jnz     short loc_18000BAEE
0x18000baf8  inc     r8
0x18000bafb  inc     r9w
0x18000baff  add     r8, rax
0x18000bb02  cmp     byte ptr [r8], 0
0x18000bb06  jnz     short loc_18000BA8A
0x18000bb08  mov     [rsi], r9w
0x18000bb0c  mov     rcx, [rsp+68h+hKey]; hKey
0x18000bb14  test    rcx, rcx
0x18000bb17  jz      short loc_18000BB25
0x18000bb19  call    cs:__imp_RegCloseKey
0x18000bb20  nop     dword ptr [rax+rax+00h]
0x18000bb25  mov     rcx, rdi; hMem
0x18000bb28  call    cs:__imp_LocalFree
0x18000bb2f  nop     dword ptr [rax+rax+00h]
0x18000bb34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb3b  cmp     rcx, r12
0x18000bb3e  jz      short loc_18000BB60
0x18000bb40  test    [rcx+1Ch], r15d
0x18000bb44  jz      short loc_18000BB60
0x18000bb46  cmp     byte ptr [rcx+19h], 6
0x18000bb4a  jb      short loc_18000BB60
0x18000bb4c  mov     edx, 84h
0x18000bb51  mov     rcx, [rcx+10h]
0x18000bb55  mov     r9d, ebx
0x18000bb58  mov     r8, r13
0x18000bb5b  call    WPP_SF_d
0x18000bb60  mov     eax, ebx
0x18000bb62  add     rsp, 30h
0x18000bb66  pop     r15
0x18000bb68  pop     r13
0x18000bb6a  pop     r12
0x18000bb6c  pop     rdi
0x18000bb6d  pop     rsi
0x18000bb6e  pop     rbp
0x18000bb6f  pop     rbx
0x18000bb70  retn
0x18000bb72  movzx   r9d, bx
0x18000bb76  mov     ebx, r9d
0x18000bb79  test    r9d, r9d
0x18000bb7c  jz      short loc_18000BB0C
0x18000bb7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb85  cmp     rcx, r12
0x18000bb88  jz      short loc_18000BB0C
0x18000bb8a  test    [rcx+1Ch], r15d
0x18000bb8e  jz      loc_18000BB0C
0x18000bb94  cmp     byte ptr [rcx+19h], 2
0x18000bb98  jb      loc_18000BB0C
0x18000bb9e  mov     edx, 83h
0x18000bba3  jmp     loc_18000BA00
```
