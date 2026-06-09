# P2PReadHeaderListToCopy(char const *,char const *,char * * &)

- ea: `0x18009e1d4`
- end: `0x18009e43d`
- name: `?P2PReadHeaderListToCopy@@YAXPEBD0AEAPEAPEAD@Z`
- size: `617`
- prototype: `void __fastcall(const char *, const char *, char ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ed04`

## callees

- `0x18009e1d4`
- `0x18009e444`
- `0x1800a3de8`
- `0x1800a5fc8`
- `0x1800a7558`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e3d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e3f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009e226`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009e226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e3b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e3b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009e25f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009e2bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009e25f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009e2bf`

## string_xrefs

- `0x18009e20d`: `Software\Microsoft\Windows NT\CurrentVersion\PeerDist\Service\`

## pseudocode

```c
void __fastcall P2PReadHeaderListToCopy(const char *a1, const char *a2, char ***a3)
{
  char *pvData; // rbx
  char *v4; // rax
  DWORD v5; // ecx
  int v6; // edi
  unsigned int v7; // r8d
  unsigned int v8; // edi
  SIZE_T v9; // rax
  char **v10; // rax
  char **v11; // rsi
  unsigned int v12; // r8d
  DWORD v13; // r9d
  unsigned int v14; // edx
  __int64 v15; // rax
  DWORD LastError; // eax
  char **v17; // [rsp+70h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+38h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+40h] BYREF
  int v20; // [rsp+84h] [rbp+44h]

  v20 = HIDWORD(a3);
  hkey = 0;
  pcbData = 0;
  v17 = 0;
  pvData = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\Service\\",
          0,
          0x20119u,
          &hkey) )
  {
    pcbData = 0;
    RegGetValueA(hkey, 0, "ExtraHeaders", 2u, 0, 0, &pcbData);
    if ( pcbData )
    {
      v4 = (char *)operator new[](pcbData + 1, (const struct std::nothrow_t *)&std::nothrow);
      pvData = v4;
      if ( v4 )
      {
        memset_0(v4, 0, pcbData + 1);
        if ( !RegGetValueA(hkey, 0, "ExtraHeaders", 2u, 0, pvData, &pcbData) )
        {
          v5 = pcbData;
          if ( pcbData > 1 )
          {
            v6 = 0;
            v7 = 0;
            if ( pcbData != 1 )
            {
              do
              {
                if ( pvData[v7] == 44 )
                {
                  pvData[v7] = 0;
                  ++v6;
                  v5 = pcbData;
                }
                ++v7;
              }
              while ( v7 < v5 - 1 );
            }
            v8 = v6 + 1;
            v9 = 8LL * (v8 + 1);
            if ( !is_mul_ok(v8 + 1, 8u) )
              v9 = -1;
            v10 = (char **)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
            v17 = v10;
            v11 = v10;
            if ( v10 )
            {
              memset_0(v10, 0, 8LL * (v8 + 1));
              *v11 = pvData;
              v12 = 1;
              v13 = pcbData;
              v14 = 0;
              if ( pcbData != 1 )
              {
                do
                {
                  if ( v12 >= v8 )
                    break;
                  if ( !pvData[v14] )
                  {
                    v15 = v12++;
                    v11[v15] = &pvData[v14 + 1];
                    v13 = pcbData;
                  }
                  ++v14;
                }
                while ( v14 < v13 - 1 );
              }
              if ( P2PHeaderListToCopy )
                P2PDeleteHeaderList(&P2PHeaderListToCopy);
              P2PHeaderListToCopy = v11;
              pvData = 0;
              v17 = 0;
            }
          }
        }
      }
    }
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( pvData
    && !HeapFree(hBitsHeap, 0, pvData)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids,
      pvData,
      LastError);
  }
  P2PDeleteHeaderList(&v17);
}

```

## disassembly

```asm
0x18009e1d4  mov     r11, rsp
0x18009e1d7  mov     [r11+20h], rbx
0x18009e1db  mov     [r11+18h], r8
0x18009e1df  mov     [r11+10h], rdx
0x18009e1e3  mov     [r11+8], rcx
0x18009e1e7  push    rbp
0x18009e1e8  push    rsi
0x18009e1e9  push    rdi
0x18009e1ea  push    r14
0x18009e1ec  push    r15
0x18009e1ee  mov     rbp, rsp
0x18009e1f1  sub     rsp, 40h
0x18009e1f5  xor     r15d, r15d
0x18009e1f8  lea     rax, [rbp+hkey]
0x18009e1fc  mov     r9d, 20119h; samDesired
0x18009e202  mov     [rbp+hkey], r15
0x18009e206  xor     r8d, r8d; ulOptions
0x18009e209  mov     [rbp+arg_10], r15d
0x18009e20d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18009e214  mov     [rbp+arg_0], r15
0x18009e218  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009e21f  mov     [r11-48h], rax
0x18009e223  mov     ebx, r15d
0x18009e226  call    cs:__imp_RegOpenKeyExA
0x18009e22c  test    eax, eax
0x18009e22e  jnz     loc_18009E3B0
0x18009e234  mov     rcx, [rbp+hkey]; hkey
0x18009e238  lea     rax, [rbp+arg_10]
0x18009e23c  mov     [rsp+40h+pcbData], rax; pcbData
0x18009e241  lea     edi, [r15+2]
0x18009e245  mov     [rsp+40h+pvData], r15; pvData
0x18009e24a  lea     r8, aExtraheaders; "ExtraHeaders"
0x18009e251  mov     r9d, edi; dwFlags
0x18009e254  mov     [rsp+40h+pdwType], r15; pdwType
0x18009e259  xor     edx, edx; lpSubKey
0x18009e25b  mov     [rbp+arg_10], r15d
0x18009e25f  call    cs:__imp_RegGetValueA
0x18009e265  mov     eax, [rbp+arg_10]
0x18009e268  test    eax, eax
0x18009e26a  jz      loc_18009E3B0
0x18009e270  lea     ecx, [rax+1]; unsigned __int64
0x18009e273  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009e27a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009e27f  mov     rbx, rax
0x18009e282  test    rax, rax
0x18009e285  jz      loc_18009E3B0
0x18009e28b  mov     r8d, [rbp+arg_10]
0x18009e28f  xor     edx, edx; Val
0x18009e291  inc     r8d; Size
0x18009e294  mov     rcx, rax; void *
0x18009e297  call    memset_0
0x18009e29c  mov     rcx, [rbp+hkey]; hkey
0x18009e2a0  lea     rax, [rbp+arg_10]
0x18009e2a4  mov     [rsp+40h+pcbData], rax; pcbData
0x18009e2a9  lea     r8, aExtraheaders; "ExtraHeaders"
0x18009e2b0  mov     [rsp+40h+pvData], rbx; pvData
0x18009e2b5  mov     r9d, edi; dwFlags
0x18009e2b8  xor     edx, edx; lpSubKey
0x18009e2ba  mov     [rsp+40h+pdwType], r15; pdwType
0x18009e2bf  call    cs:__imp_RegGetValueA
0x18009e2c5  test    eax, eax
0x18009e2c7  jnz     loc_18009E3B0
0x18009e2cd  mov     ecx, [rbp+arg_10]
0x18009e2d0  cmp     ecx, 1
0x18009e2d3  jbe     loc_18009E3B0
0x18009e2d9  lea     eax, [rcx-1]
0x18009e2dc  mov     edi, r15d
0x18009e2df  mov     r8d, r15d
0x18009e2e2  test    eax, eax
0x18009e2e4  jz      short loc_18009E303
0x18009e2e6  mov     eax, r8d
0x18009e2e9  cmp     byte ptr [rax+rbx], 2Ch ; ','
0x18009e2ed  jnz     short loc_18009E2F8
0x18009e2ef  mov     [rax+rbx], r15b
0x18009e2f3  inc     edi
0x18009e2f5  mov     ecx, [rbp+arg_10]
0x18009e2f8  inc     r8d
0x18009e2fb  lea     eax, [rcx-1]
0x18009e2fe  cmp     r8d, eax
0x18009e301  jb      short loc_18009E2E6
0x18009e303  inc     edi
0x18009e305  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009e30c  mov     eax, 8
0x18009e311  lea     r14d, [rdi+1]
0x18009e315  mul     r14
0x18009e318  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009e31f  cmovb   rax, rcx
0x18009e323  mov     rcx, rax; unsigned __int64
0x18009e326  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009e32b  mov     [rbp+arg_0], rax
0x18009e32f  mov     rsi, rax
0x18009e332  test    rax, rax
0x18009e335  jz      short loc_18009E3B0
0x18009e337  lea     r8, ds:0[r14*8]; Size
0x18009e33f  xor     edx, edx; Val
0x18009e341  mov     rcx, rax; void *
0x18009e344  call    memset_0
0x18009e349  mov     [rsi], rbx
0x18009e34c  mov     r8d, 1
0x18009e352  mov     r9d, [rbp+arg_10]
0x18009e356  mov     edx, r15d
0x18009e359  lea     ecx, [r9-1]
0x18009e35d  test    ecx, ecx
0x18009e35f  jz      short loc_18009E38D
0x18009e361  cmp     r8d, edi
0x18009e364  jnb     short loc_18009E38D
0x18009e366  mov     eax, edx
0x18009e368  cmp     [rax+rbx], r15b
0x18009e36c  jnz     short loc_18009E383
0x18009e36e  lea     rcx, [rbx+1]
0x18009e372  add     rcx, rax
0x18009e375  mov     eax, r8d
0x18009e378  inc     r8d
0x18009e37b  mov     [rsi+rax*8], rcx
0x18009e37f  mov     r9d, [rbp+arg_10]
0x18009e383  inc     edx
0x18009e385  lea     eax, [r9-1]
0x18009e389  cmp     edx, eax
0x18009e38b  jb      short loc_18009E361
0x18009e38d  cmp     cs:?P2PHeaderListToCopy@@3PEAPEADEA, r15; char * * P2PHeaderListToCopy
0x18009e394  jz      short loc_18009E3A2
0x18009e396  lea     rcx, ?P2PHeaderListToCopy@@3PEAPEADEA; char ***
0x18009e39d  call    ?P2PDeleteHeaderList@@YAXAEAPEAPEAD@Z; P2PDeleteHeaderList(char * * &)
0x18009e3a2  mov     cs:?P2PHeaderListToCopy@@3PEAPEADEA, rsi; char * * P2PHeaderListToCopy
0x18009e3a9  mov     rbx, r15
0x18009e3ac  mov     [rbp+arg_0], r15
0x18009e3b0  mov     rcx, [rbp+hkey]; hKey
0x18009e3b4  test    rcx, rcx
0x18009e3b7  jz      short loc_18009E3C3
0x18009e3b9  call    cs:__imp_RegCloseKey
0x18009e3bf  mov     [rbp+hkey], r15
0x18009e3c3  test    rbx, rbx
0x18009e3c6  jz      short loc_18009E420
0x18009e3c8  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18009e3cf  mov     r8, rbx; lpMem
0x18009e3d2  xor     edx, edx; dwFlags
0x18009e3d4  call    cs:__imp_HeapFree
0x18009e3da  test    eax, eax
0x18009e3dc  jnz     short loc_18009E420
0x18009e3de  mov     rax, cs:WPP_GLOBAL_Control
0x18009e3e5  lea     rcx, WPP_GLOBAL_Control
0x18009e3ec  cmp     rax, rcx
0x18009e3ef  jz      short loc_18009E420
0x18009e3f1  test    byte ptr [rax+1Ch], 4
0x18009e3f5  jz      short loc_18009E420
0x18009e3f7  call    cs:__imp_GetLastError
0x18009e3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e404  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18009e40b  mov     edx, 0Bh
0x18009e410  mov     dword ptr [rsp+40h+pdwType], eax
0x18009e414  mov     r9, rbx
0x18009e417  mov     rcx, [rcx+10h]
0x18009e41b  call    WPP_SF_qD
0x18009e420  lea     rcx, [rbp+arg_0]; char ***
0x18009e424  call    ?P2PDeleteHeaderList@@YAXAEAPEAPEAD@Z; P2PDeleteHeaderList(char * * &)
0x18009e429  mov     rbx, [rsp+40h+arg_18]
0x18009e431  add     rsp, 40h
0x18009e435  pop     r15
0x18009e437  pop     r14
0x18009e439  pop     rdi
0x18009e43a  pop     rsi
0x18009e43b  pop     rbp
0x18009e43c  retn
```
