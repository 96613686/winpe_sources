# SaveDevicesToRouter

- ea: `0x180015fd0`
- end: `0x180016302`
- name: `SaveDevicesToRouter`
- size: `818`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016308`

## callees

- `0x180015fd0`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016045`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001620d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001620d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800161fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800161fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800161cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800161cd`
- `rasman!RasRpcDisconnectServer` at `0x1800162e5`
- `rasman!RasRpcDisconnectServer` at `0x1800162e5`
- `rasman!RasSetDeviceConfigInfo` at `0x1800162b5`
- `rasman!RasSetDeviceConfigInfo` at `0x1800162b5`
- `rasman!RasRpcConnectServer` at `0x180015ffa`
- `rasman!RasRpcConnectServer` at `0x180015ffa`

## string_xrefs

- `0x1800161bf`: `System\CurrentControlSet\Services\PptpProtocol\Parameters`

## pseudocode

```c
__int64 __fastcall SaveDevicesToRouter(BYTE *lpData, unsigned int *a2)
{
  unsigned int v4; // esi
  unsigned int v5; // ebp
  BYTE *v6; // rax
  unsigned __int64 v7; // rcx
  size_t v8; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // r15
  unsigned int v12; // r12d
  _DWORD *i; // rdi
  _DWORD *v14; // rcx
  BYTE *v15; // rax
  __int64 v16; // rdx
  __int128 v17; // xmm0
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  HANDLE v25; // rax
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF
  __int64 v28; // [rsp+88h] [rbp+20h] BYREF

  v28 = 0;
  v4 = RasRpcConnectServer(0, &v28);
  if ( !v4 )
  {
    v5 = 0;
    v6 = lpData;
    do
    {
      v6 = (BYTE *)*((_QWORD *)v6 + 98);
      ++v5;
    }
    while ( v6 );
    v7 = 472LL * v5;
    if ( v7 > 0xFFFFFFFF )
    {
      v4 = 87;
    }
    else
    {
      v8 = (unsigned int)v7;
      ProcessHeap = GetProcessHeap();
      v10 = HeapAlloc(ProcessHeap, 0, (unsigned int)v8);
      v11 = v10;
      if ( !v10 )
      {
        v4 = 8;
        goto LABEL_55;
      }
      memset_0(v10, 0, v8);
      v12 = 0;
      for ( i = v11; v12 < v5; i += 118 )
      {
        v14 = i;
        v15 = lpData + 308;
        v16 = 3;
        do
        {
          v17 = *(_OWORD *)v15;
          v15 += 128;
          *(_OWORD *)v14 = v17;
          v14 += 32;
          *((_OWORD *)v14 - 7) = *((_OWORD *)v15 - 7);
          *((_OWORD *)v14 - 6) = *((_OWORD *)v15 - 6);
          *((_OWORD *)v14 - 5) = *((_OWORD *)v15 - 5);
          *((_OWORD *)v14 - 4) = *((_OWORD *)v15 - 4);
          *((_OWORD *)v14 - 3) = *((_OWORD *)v15 - 3);
          *((_OWORD *)v14 - 2) = *((_OWORD *)v15 - 2);
          *((_OWORD *)v14 - 1) = *((_OWORD *)v15 - 1);
          --v16;
        }
        while ( v16 );
        *(_OWORD *)v14 = *(_OWORD *)v15;
        *((_OWORD *)v14 + 1) = *((_OWORD *)v15 + 1);
        *((_OWORD *)v14 + 2) = *((_OWORD *)v15 + 2);
        *((_OWORD *)v14 + 3) = *((_OWORD *)v15 + 3);
        *((_OWORD *)v14 + 4) = *((_OWORD *)v15 + 4);
        *((_QWORD *)v14 + 10) = *((_QWORD *)v15 + 10);
        i[1] = 1;
        i[2] = *((_DWORD *)lpData + 1);
        i[3] = *((_DWORD *)lpData + 2);
        i[4] = *((_DWORD *)lpData + 3);
        v18 = (unsigned __int16)*((_DWORD *)lpData + 76);
        switch ( v18 )
        {
          case 8:
            v19 = *a2;
            break;
          case 9:
            v19 = a2[1];
            break;
          case 14:
            v19 = a2[2];
            break;
          case 15:
            v19 = a2[3];
            break;
          case 16:
            v19 = a2[4];
            break;
          default:
LABEL_22:
            v19 = *(_DWORD *)lpData;
            goto LABEL_23;
        }
        if ( *(_DWORD *)lpData <= v19 )
          goto LABEL_22;
        *(_DWORD *)lpData = v19;
LABEL_23:
        i[7] = v19;
        i[11] = *((_DWORD *)lpData + 5);
        i[9] = -1;
        i[8] = 3;
        if ( *((_WORD *)lpData + 152) == 8 )
        {
          v20 = *(_DWORD *)lpData;
          hKey = 0;
          if ( v20 > *((_DWORD *)lpData + 5) )
          {
            if ( v20 >= *a2 )
              v20 = *a2;
            i[11] = v20;
          }
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Services\\PptpProtocol\\Parameters",
                  0,
                  0x20006u,
                  &hKey) )
            RegSetValueExW(hKey, L"NumberLineDevices", 0, 4u, lpData, 4u);
          if ( hKey )
            RegCloseKey(hKey);
        }
        if ( *((_WORD *)lpData + 152) == 9 )
        {
          v21 = *(_DWORD *)lpData;
          if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
          {
            if ( v21 >= a2[1] )
              v21 = a2[1];
            i[11] = v21;
          }
        }
        if ( *((_WORD *)lpData + 152) == 14 )
        {
          v22 = *(_DWORD *)lpData;
          if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
          {
            if ( v22 >= a2[2] )
              v22 = a2[2];
            i[11] = v22;
          }
        }
        if ( *((_WORD *)lpData + 152) == 15 )
        {
          v23 = *(_DWORD *)lpData;
          if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
          {
            if ( v23 >= a2[3] )
              v23 = a2[3];
            i[11] = v23;
          }
        }
        if ( *((_WORD *)lpData + 152) == 16 )
        {
          v24 = *(_DWORD *)lpData;
          if ( *(_DWORD *)lpData > *((_DWORD *)lpData + 5) )
          {
            if ( v24 >= a2[4] )
              v24 = a2[4];
            i[11] = v24;
          }
        }
        lpData = (BYTE *)*((_QWORD *)lpData + 98);
        ++v12;
      }
      v4 = RasSetDeviceConfigInfo(v28, v5, 472 * v5, v11);
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v11);
    }
  }
LABEL_55:
  if ( v28 )
    RasRpcDisconnectServer();
  return v4;
}

```

## disassembly

```asm
0x180015fd0  mov     rax, rsp
0x180015fd3  mov     [rax+8], rbx
0x180015fd7  push    rbp
0x180015fd8  push    rsi
0x180015fd9  push    rdi
0x180015fda  push    r12
0x180015fdc  push    r13
0x180015fde  push    r14
0x180015fe0  push    r15
0x180015fe2  sub     rsp, 30h
0x180015fe6  mov     r14, rdx
0x180015fe9  mov     qword ptr [rax+20h], 0
0x180015ff1  mov     rbx, rcx
0x180015ff4  lea     rdx, [rax+20h]
0x180015ff8  xor     ecx, ecx
0x180015ffa  call    cs:__imp_RasRpcConnectServer
0x180016000  mov     esi, eax
0x180016002  test    eax, eax
0x180016004  jnz     loc_1800162D8
0x18001600a  xor     ebp, ebp
0x18001600c  mov     rax, rbx
0x18001600f  mov     rax, [rax+310h]
0x180016016  inc     ebp
0x180016018  test    rax, rax
0x18001601b  jnz     short loc_18001600F
0x18001601d  mov     eax, ebp
0x18001601f  mov     r13d, 0FFFFFFFFh
0x180016025  imul    rcx, rax, 1D8h
0x18001602c  cmp     rcx, r13
0x18001602f  ja      loc_1800162D3
0x180016035  mov     edi, ecx
0x180016037  call    cs:__imp_GetProcessHeap
0x18001603d  mov     r8d, edi; dwBytes
0x180016040  xor     edx, edx; dwFlags
0x180016042  mov     rcx, rax; hHeap
0x180016045  call    cs:__imp_HeapAlloc
0x18001604b  mov     r15, rax
0x18001604e  test    rax, rax
0x180016051  jnz     short loc_18001605B
0x180016053  lea     esi, [rax+8]
0x180016056  jmp     loc_1800162D8
0x18001605b  mov     r8, rdi; Size
0x18001605e  xor     edx, edx; Val
0x180016060  mov     rcx, r15; void *
0x180016063  call    memset_0
0x180016068  xor     r12d, r12d
0x18001606b  mov     rdi, r15
0x18001606e  test    ebp, ebp
0x180016070  jz      loc_1800162A1
0x180016076  lea     esi, [r12+8]
0x18001607b  mov     rcx, rdi
0x18001607e  lea     rax, [rbx+134h]
0x180016085  mov     edx, 3
0x18001608a  movups  xmm0, xmmword ptr [rax]
0x18001608d  lea     rax, [rax+80h]
0x180016094  movups  xmmword ptr [rcx], xmm0
0x180016097  lea     rcx, [rcx+80h]
0x18001609e  movups  xmm1, xmmword ptr [rax-70h]
0x1800160a2  movups  xmmword ptr [rcx-70h], xmm1
0x1800160a6  movups  xmm0, xmmword ptr [rax-60h]
0x1800160aa  movups  xmmword ptr [rcx-60h], xmm0
0x1800160ae  movups  xmm1, xmmword ptr [rax-50h]
0x1800160b2  movups  xmmword ptr [rcx-50h], xmm1
0x1800160b6  movups  xmm0, xmmword ptr [rax-40h]
0x1800160ba  movups  xmmword ptr [rcx-40h], xmm0
0x1800160be  movups  xmm1, xmmword ptr [rax-30h]
0x1800160c2  movups  xmmword ptr [rcx-30h], xmm1
0x1800160c6  movups  xmm0, xmmword ptr [rax-20h]
0x1800160ca  movups  xmmword ptr [rcx-20h], xmm0
0x1800160ce  movups  xmm1, xmmword ptr [rax-10h]
0x1800160d2  movups  xmmword ptr [rcx-10h], xmm1
0x1800160d6  sub     rdx, 1
0x1800160da  jnz     short loc_18001608A
0x1800160dc  movups  xmm0, xmmword ptr [rax]
0x1800160df  movups  xmmword ptr [rcx], xmm0
0x1800160e2  movups  xmm1, xmmword ptr [rax+10h]
0x1800160e6  movups  xmmword ptr [rcx+10h], xmm1
0x1800160ea  movups  xmm0, xmmword ptr [rax+20h]
0x1800160ee  movups  xmmword ptr [rcx+20h], xmm0
0x1800160f2  movups  xmm1, xmmword ptr [rax+30h]
0x1800160f6  movups  xmmword ptr [rcx+30h], xmm1
0x1800160fa  movups  xmm0, xmmword ptr [rax+40h]
0x1800160fe  movups  xmmword ptr [rcx+40h], xmm0
0x180016102  mov     rax, [rax+50h]
0x180016106  mov     [rcx+50h], rax
0x18001610a  mov     dword ptr [rdi+4], 1
0x180016111  mov     eax, [rbx+4]
0x180016114  mov     [rdi+8], eax
0x180016117  mov     eax, [rbx+8]
0x18001611a  mov     [rdi+0Ch], eax
0x18001611d  mov     eax, [rbx+0Ch]
0x180016120  mov     [rdi+10h], eax
0x180016123  mov     eax, [rbx+130h]
0x180016129  movzx   eax, ax
0x18001612c  cmp     eax, esi
0x18001612e  jnz     short loc_180016135
0x180016130  mov     eax, [r14]
0x180016133  jmp     short loc_180016154
0x180016135  cmp     eax, 9
0x180016138  jnz     short loc_180016140
0x18001613a  mov     eax, [r14+4]
0x18001613e  jmp     short loc_180016154
0x180016140  cmp     eax, 0Eh
0x180016143  jnz     short loc_18001614B
0x180016145  mov     eax, [r14+8]
0x180016149  jmp     short loc_180016154
0x18001614b  cmp     eax, 0Fh
0x18001614e  jnz     short loc_18001615C
0x180016150  mov     eax, [r14+0Ch]
0x180016154  cmp     [rbx], eax
0x180016156  jbe     short loc_180016167
0x180016158  mov     [rbx], eax
0x18001615a  jmp     short loc_180016169
0x18001615c  cmp     eax, 10h
0x18001615f  jnz     short loc_180016167
0x180016161  mov     eax, [r14+10h]
0x180016165  jmp     short loc_180016154
0x180016167  mov     eax, [rbx]
0x180016169  mov     [rdi+1Ch], eax
0x18001616c  mov     eax, [rbx+14h]
0x18001616f  mov     [rdi+2Ch], eax
0x180016172  mov     [rdi+24h], r13d
0x180016176  mov     dword ptr [rdi+20h], 3
0x18001617d  movzx   eax, word ptr [rbx+130h]
0x180016184  cmp     eax, esi
0x180016186  jnz     loc_180016213
0x18001618c  mov     eax, [rbx]
0x18001618e  mov     [rsp+68h+hKey], 0
0x18001619a  cmp     eax, [rbx+14h]
0x18001619d  jbe     short loc_1800161A9
0x18001619f  cmp     eax, [r14]
0x1800161a2  cmovnb  eax, [r14]
0x1800161a6  mov     [rdi+2Ch], eax
0x1800161a9  lea     rax, [rsp+68h+hKey]
0x1800161b1  mov     r9d, 20006h; samDesired
0x1800161b7  xor     r8d, r8d; ulOptions
0x1800161ba  mov     [rsp+68h+phkResult], rax; phkResult
0x1800161bf  lea     rdx, c_szRegKeyPptpProtocolParam; "System\\CurrentControlSet\\Services\\Pp"...
0x1800161c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800161cd  call    cs:__imp_RegOpenKeyExW
0x1800161d3  test    eax, eax
0x1800161d5  jnz     short loc_180016200
0x1800161d7  mov     rcx, [rsp+68h+hKey]; hKey
0x1800161df  lea     rdx, c_szRegValNumberLineDevices; "NumberLineDevices"
0x1800161e6  mov     eax, 4
0x1800161eb  xor     r8d, r8d; Reserved
0x1800161ee  mov     [rsp+68h+cbData], eax; cbData
0x1800161f2  mov     r9d, eax; dwType
0x1800161f5  mov     [rsp+68h+phkResult], rbx; lpData
0x1800161fa  call    cs:__imp_RegSetValueExW
0x180016200  mov     rcx, [rsp+68h+hKey]; hKey
0x180016208  test    rcx, rcx
0x18001620b  jz      short loc_180016213
0x18001620d  call    cs:__imp_RegCloseKey
0x180016213  cmp     word ptr [rbx+130h], 9
0x18001621b  jnz     short loc_180016230
0x18001621d  mov     eax, [rbx]
0x18001621f  cmp     eax, [rbx+14h]
0x180016222  jbe     short loc_180016230
0x180016224  cmp     eax, [r14+4]
0x180016228  cmovnb  eax, [r14+4]
0x18001622d  mov     [rdi+2Ch], eax
0x180016230  cmp     word ptr [rbx+130h], 0Eh
0x180016238  jnz     short loc_18001624D
0x18001623a  mov     eax, [rbx]
0x18001623c  cmp     eax, [rbx+14h]
0x18001623f  jbe     short loc_18001624D
0x180016241  cmp     eax, [r14+8]
0x180016245  cmovnb  eax, [r14+8]
0x18001624a  mov     [rdi+2Ch], eax
0x18001624d  cmp     word ptr [rbx+130h], 0Fh
0x180016255  jnz     short loc_18001626A
0x180016257  mov     eax, [rbx]
0x180016259  cmp     eax, [rbx+14h]
0x18001625c  jbe     short loc_18001626A
0x18001625e  cmp     eax, [r14+0Ch]
0x180016262  cmovnb  eax, [r14+0Ch]
0x180016267  mov     [rdi+2Ch], eax
0x18001626a  cmp     word ptr [rbx+130h], 10h
0x180016272  jnz     short loc_180016287
0x180016274  mov     eax, [rbx]
0x180016276  cmp     eax, [rbx+14h]
0x180016279  jbe     short loc_180016287
0x18001627b  cmp     eax, [r14+10h]
0x18001627f  cmovnb  eax, [r14+10h]
0x180016284  mov     [rdi+2Ch], eax
0x180016287  mov     rbx, [rbx+310h]
0x18001628e  inc     r12d
0x180016291  add     rdi, 1D8h
0x180016298  cmp     r12d, ebp
0x18001629b  jb      loc_18001607B
0x1800162a1  mov     rcx, [rsp+68h+arg_18]
0x1800162a9  mov     r9, r15
0x1800162ac  imul    r8d, ebp, 1D8h
0x1800162b3  mov     edx, ebp
0x1800162b5  call    cs:__imp_RasSetDeviceConfigInfo
0x1800162bb  mov     esi, eax
0x1800162bd  call    cs:__imp_GetProcessHeap
0x1800162c3  mov     r8, r15; lpMem
0x1800162c6  xor     edx, edx; dwFlags
0x1800162c8  mov     rcx, rax; hHeap
0x1800162cb  call    cs:__imp_HeapFree
0x1800162d1  jmp     short loc_1800162D8
0x1800162d3  mov     esi, 57h ; 'W'
0x1800162d8  mov     rcx, [rsp+68h+arg_18]
0x1800162e0  test    rcx, rcx
0x1800162e3  jz      short loc_1800162EB
0x1800162e5  call    cs:__imp_RasRpcDisconnectServer
0x1800162eb  mov     rbx, [rsp+68h+arg_0]
0x1800162f0  mov     eax, esi
0x1800162f2  add     rsp, 30h
0x1800162f6  pop     r15
0x1800162f8  pop     r14
0x1800162fa  pop     r13
0x1800162fc  pop     r12
0x1800162fe  pop     rdi
0x1800162ff  pop     rsi
0x180016300  pop     rbp
0x180016301  retn
```
