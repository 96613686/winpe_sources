# CToolbar::SaveRestoreFromReg(int,HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800ab0f0`
- end: `0x1800ab7be`
- name: `?SaveRestoreFromReg@CToolbar@@AEAAHHPEAUHKEY__@@PEBG1@Z`
- size: `1742`
- prototype: `__int64 __usercall@<rax>(CToolbar *__hidden this@<rcx>, int@<edx>, HKEY@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800134f0`

## callees

- `0x18001637c`
- `0x180016908`
- `0x180016cec`
- `0x180036850`
- `0x1800ab0f0`
- `0x1800ab7c4`
- `0x1800ac4a0`
- `0x180114520`
- `0x180114ebc`
- `0x1801422c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab19a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab2cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab19a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab2cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab772`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab1ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab362`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab1ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ab362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab2df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab2df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab780`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ab2ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ab2ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab308`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab336`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab39d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab336`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab39d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab2c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab2c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab78b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ab20d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ab20d`
- `USER32!SendMessageW` at `0x1800ab478`
- `USER32!SendMessageW` at `0x1800ab70d`
- `USER32!SendMessageW` at `0x1800ab740`
- `USER32!SendMessageW` at `0x1800ab478`
- `USER32!SendMessageW` at `0x1800ab70d`
- `USER32!SendMessageW` at `0x1800ab740`
- `USER32!InvalidateRect` at `0x1800ab74f`
- `USER32!InvalidateRect` at `0x1800ab74f`

## pseudocode

```c
__int64 __fastcall CToolbar::SaveRestoreFromReg(
        CToolbar *this,
        int a2,
        HKEY a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpValueName)
{
  unsigned int v8; // r14d
  int v9; // ecx
  BYTE *v10; // rcx
  int v11; // ebx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v14; // rax
  int v15; // r12d
  SIZE_T v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // ecx
  const struct _TBBUTTONDATA *v20; // rdx
  HANDLE v21; // rax
  unsigned __int64 v22; // rsi
  HANDLE v23; // rax
  BYTE *v24; // r13
  HWND *v25; // r15
  int v26; // esi
  HWND v27; // rax
  int v28; // ebx
  __int64 v29; // rax
  HWND v30; // rcx
  __int64 v31; // rcx
  signed int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 v35; // rdx
  INT_PTR iString; // rdx
  int v37; // esi
  int i; // edx
  int v39; // eax
  __int128 v40; // xmm1
  __int64 v41; // rcx
  __int64 v42; // rax
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  signed int v46; // ebx
  __int64 v47; // rsi
  __int64 v48; // rcx
  HWND v49; // r13
  BYTE *v50; // r14
  HANDLE v51; // rax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  BYTE *v54; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPARAM lParam[2]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *lpData[2]; // [rsp+70h] [rbp-90h]
  SIZE_T dwBytes[2]; // [rsp+80h] [rbp-80h]
  struct _TBBUTTON v59; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v60[24]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE *v61; // [rsp+D8h] [rbp-28h]
  BYTE *v62; // [rsp+E0h] [rbp-20h]
  int v63; // [rsp+E8h] [rbp-18h]
  int v64; // [rsp+ECh] [rbp-14h]
  unsigned int v65; // [rsp+F0h] [rbp-10h]
  int v66; // [rsp+F4h] [rbp-Ch]
  struct _TBBUTTON v67; // [rsp+F8h] [rbp-8h] BYREF
  DWORD Type; // [rsp+120h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v70[128]; // [rsp+130h] [rbp+30h] BYREF

  v8 = 0;
  if ( a2 )
  {
    lParam[0] = 0;
    memset_0(&lParam[1], 0, 0x50u);
    v9 = *((_DWORD *)this + 66);
    lpData[1] = 0;
    dwBytes[0] = 0;
    v59.iBitmap = v9;
    HIDWORD(dwBytes[1]) = -1;
    LODWORD(dwBytes[1]) = 4 * v9;
    CCSendNotify((char *)this + 56, 4294966574LL, lParam);
    v10 = lpData[1];
    v11 = 0;
    if ( lpData[1] )
    {
      v15 = 0;
    }
    else
    {
      v12 = dwBytes[1];
      ProcessHeap = GetProcessHeap();
      v14 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v12);
      v11 = 0;
      lpData[1] = v14;
      v10 = v14;
      v15 = 1;
    }
    v16 = dwBytes[0];
    if ( !dwBytes[0] )
      v16 = (SIZE_T)v10;
    dwBytes[0] = v16;
    if ( v10 )
    {
      hKey = 0;
      if ( !RegCreateKeyExW(a3, a4, 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
      {
        if ( *((int *)this + 66) > 0 )
        {
          do
          {
            v17 = *((_QWORD *)this + 18);
            v18 = 80LL * v11;
            v19 = *(_DWORD *)(v17 + v18 + 4);
            if ( !v19 )
              v19 = ((unsigned __int8)~*(_BYTE *)(v17 + v18 + 8) >> 3) | 0xFFFFFFFE;
            *(_DWORD *)dwBytes[0] = v19;
            v20 = (const struct _TBBUTTONDATA *)(*((_QWORD *)this + 18) + v18);
            dwBytes[0] += 4LL;
            HIDWORD(dwBytes[1]) = v11;
            CToolbar::TBOutputStruct(this, v20, (struct _TBBUTTON *)&v59.fsState);
            CCSendNotify((char *)this + 56, 4294966574LL, lParam);
            ++v11;
          }
          while ( v11 < *((_DWORD *)this + 66) );
        }
        LOBYTE(v8) = RegSetValueExW(hKey, lpValueName, 0, 3u, lpData[1], dwBytes[1]) == 0;
        RegCloseKey(hKey);
      }
      if ( v15 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, lpData[1]);
      }
    }
  }
  else
  {
    hKey = 0;
    if ( !RegOpenKeyExW(a3, a4, 0, 0x20019u, &hKey) )
    {
      cbData = 0;
      if ( !RegQueryValueExW(hKey, lpValueName, 0, 0, 0, &cbData) )
      {
        v22 = (int)cbData;
        if ( cbData > 4 )
        {
          v23 = GetProcessHeap();
          v54 = (BYTE *)HeapAlloc(v23, 8u, (unsigned int)v22);
          v24 = v54;
          if ( v54 )
          {
            Type = 0;
            cbData = v22;
            if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, v54, &cbData) && Type == 3 && cbData == (_DWORD)v22 )
            {
              memset_0(v60, 0, 0x58u);
              v61 = v54;
              v25 = (HWND *)((char *)this + 56);
              v65 = v22 >> 2;
              v62 = v54;
              v64 = -1;
              v66 = 4;
              v63 = v22;
              v26 = 0;
              if ( !CCSendNotify((char *)this + 56, 4294966575LL, v60) )
              {
                if ( *((_QWORD *)this + 21) )
                {
                  memset_0(lParam, 0, 0x48u);
                  v27 = *v25;
                  LODWORD(lParam[0]) = 72;
                  v28 = 0;
                  for ( lParam[1] = (LPARAM)v27; v28 < *((_DWORD *)this + 66); ++v28 )
                  {
                    v29 = *((_QWORD *)this + 18);
                    if ( (*(_BYTE *)(v29 + 80LL * v28 + 9) & 1) == 0 )
                    {
                      v30 = (HWND)*((_QWORD *)this + 21);
                      lpData[0] = (BYTE *)*(int *)(v29 + 80LL * v28 + 4);
                      SendMessageW(v30, 0x433u, 0, (LPARAM)lParam);
                    }
                  }
                }
                if ( (unsigned int)CToolbar::TBReallocButtons(this, v65) )
                {
                  v31 = *((int *)this + 66);
                  v32 = v65;
                  if ( (int)v31 < (int)v65 )
                  {
                    memset_0((void *)(*((_QWORD *)this + 18) + 80 * v31), 0, 32LL * (int)(v65 - v31));
                    v32 = v65;
                  }
                  *((_DWORD *)this + 66) = v32;
                  if ( v32 > 0 )
                  {
                    do
                    {
                      v33 = *((_QWORD *)this + 18);
                      v64 = v26;
                      v34 = 80LL * v26;
                      if ( *(int *)v62 >= 0 )
                      {
                        *(_BYTE *)(v33 + v34 + 9) = 0;
                        *(_DWORD *)(*((_QWORD *)this + 18) + v34 + 4) = *(_DWORD *)v62;
                        *(_DWORD *)(v34 + *((_QWORD *)this + 18)) = -1;
                      }
                      else
                      {
                        *(_BYTE *)(v33 + v34 + 9) = 1;
                        *(_DWORD *)(v34 + *((_QWORD *)this + 18)) = 8;
                        *(_DWORD *)(*((_QWORD *)this + 18) + v34 + 4) = 0;
                        *(_BYTE *)(*((_QWORD *)this + 18) + v34 + 8) = *(_DWORD *)v62 != -1 ? 8 : 0;
                      }
                      v35 = *((_QWORD *)this + 18);
                      v62 += 4;
                      CToolbar::TBOutputStruct(this, (const struct _TBBUTTONDATA *)(v34 + v35), &v67);
                      CCSendNotify((char *)this + 56, 4294966575LL, v60);
                      iString = v67.iString;
                      if ( WORD1(v67.iString) )
                        iString = 0;
                      v67.iString = iString;
                      CToolbar::TBInputStruct(this, (struct _TBBUTTONDATA *)(v34 + *((_QWORD *)this + 18)), &v67);
                      ++v26;
                    }
                    while ( v26 < *((_DWORD *)this + 66) );
                  }
                  if ( !CCSendNotify((char *)this + 56, 4294966593LL, 0) )
                  {
                    v37 = 0;
                    memset_0(lParam, 0, 0x50u);
                    for ( i = 0;
                          (unsigned int)CToolbar::GetAdjustInfo(this, i, (struct _TBBUTTONDATA *)lParam, v70, dwOptions);
                          i = v37 )
                    {
                      if ( (lParam[1] & 0x100) == 0 || HIDWORD(lParam[0]) )
                      {
                        v39 = CToolbar::PositionFromID(this, SHIDWORD(lParam[0]));
                        if ( v39 >= 0 )
                        {
                          v40 = *(_OWORD *)lpData;
                          v41 = 5LL * v39;
                          v42 = *((_QWORD *)this + 18);
                          v41 *= 2;
                          *(_OWORD *)(v42 + 8 * v41) = *(_OWORD *)lParam;
                          v43 = *(_OWORD *)dwBytes;
                          *(_OWORD *)(v42 + 8 * v41 + 16) = v40;
                          v44 = *(_OWORD *)&v59.iBitmap;
                          *(_OWORD *)(v42 + 8 * v41 + 32) = v43;
                          v45 = *(_OWORD *)&v59.dwData;
                          *(_OWORD *)(v42 + 8 * v41 + 48) = v44;
                          *(_OWORD *)(v42 + 8 * v41 + 64) = v45;
                        }
                      }
                      ++v37;
                      memset_0(lParam, 0, 0x50u);
                    }
                    CCSendNotify((char *)this + 56, 4294966592LL, 0);
                  }
                  v46 = *((_DWORD *)this + 66) - 1;
                  if ( v46 >= 0 )
                  {
                    v47 = v46;
                    do
                    {
                      v48 = *((_QWORD *)this + 18);
                      if ( *(int *)(v48 + 80 * v47) >= 0 )
                      {
                        v49 = (HWND)*((_QWORD *)this + 21);
                        if ( v49 && (*(_BYTE *)(v48 + 80 * v47 + 9) & 1) == 0 )
                        {
                          v50 = (BYTE *)*(int *)(v48 + 80 * v47 + 4);
                          if ( (_DWORD)v50 )
                          {
                            memset_0(lParam, 0, 0x48u);
                            lParam[1] = *((_QWORD *)this + 7);
                            lParam[0] = 72;
                            lpData[0] = v50;
                            *(_QWORD *)&v59.iBitmap = -1;
                            SendMessageW(v49, 0x432u, 0, (LPARAM)lParam);
                          }
                          v8 = 0;
                        }
                      }
                      else
                      {
                        CToolbar::DeleteButton(this, v46);
                      }
                      --v47;
                      --v46;
                    }
                    while ( v46 >= 0 );
                    v24 = v54;
                  }
                  LOBYTE(v8) = *((_DWORD *)this + 66) != 0;
                  SendMessageW(*v25, 0x421u, 0, 0);
                  InvalidateRect(*v25, 0, 1);
                  *((_DWORD *)this + 95) &= ~0x10000u;
                  *((_DWORD *)this + 95) |= 0x10u;
                  *((_DWORD *)this + 74) = -1;
                  *((_DWORD *)this + 75) = -1;
                }
              }
            }
            v51 = GetProcessHeap();
            HeapFree(v51, 0, v24);
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800ab0f0  mov     [rsp-8+arg_8], rbx
0x1800ab0f5  push    rbp
0x1800ab0f6  push    rsi
0x1800ab0f7  push    rdi
0x1800ab0f8  push    r12
0x1800ab0fa  push    r13
0x1800ab0fc  push    r14
0x1800ab0fe  push    r15
0x1800ab100  lea     rbp, [rsp-140h]
0x1800ab108  sub     rsp, 240h
0x1800ab10f  mov     rax, cs:__security_cookie
0x1800ab116  xor     rax, rsp
0x1800ab119  mov     [rbp+170h+var_40], rax
0x1800ab120  mov     r15, [rbp+170h+lpValueName]
0x1800ab127  xor     r12d, r12d
0x1800ab12a  mov     r13, r9
0x1800ab12d  mov     rsi, r8
0x1800ab130  mov     rdi, rcx
0x1800ab133  mov     r14d, r12d
0x1800ab136  test    edx, edx
0x1800ab138  jz      loc_1800AB2EA
0x1800ab13e  xor     edx, edx; Val
0x1800ab140  mov     [rsp+270h+lParam], r12
0x1800ab145  lea     r8d, [r12+50h]; Size
0x1800ab14a  lea     rcx, [rsp+270h+lParam+8]; void *
0x1800ab14f  call    memset_0
0x1800ab154  mov     ecx, [rdi+108h]
0x1800ab15a  lea     r8, [rsp+270h+lParam]
0x1800ab15f  mov     [rsp+270h+lpData+8], r12
0x1800ab164  mov     edx, 0FFFFFD2Eh
0x1800ab169  mov     [rbp+170h+dwBytes], r12
0x1800ab16d  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800ab171  mov     [rbp+170h+var_1E0.iBitmap], ecx
0x1800ab174  lea     eax, ds:0[rcx*4]
0x1800ab17b  mov     dword ptr [rbp+170h+dwBytes+0Ch], r12d
0x1800ab17f  lea     rcx, [rdi+38h]
0x1800ab183  mov     dword ptr [rbp+170h+dwBytes+8], eax
0x1800ab186  call    CCSendNotify
0x1800ab18b  mov     rcx, [rsp+270h+lpData+8]
0x1800ab190  xor     ebx, ebx
0x1800ab192  test    rcx, rcx
0x1800ab195  jnz     short loc_1800AB1C1
0x1800ab197  mov     ebx, dword ptr [rbp+170h+dwBytes+8]
0x1800ab19a  call    cs:__imp_GetProcessHeap
0x1800ab1a0  mov     r8d, ebx; dwBytes
0x1800ab1a3  lea     edx, [r12+9]; dwFlags
0x1800ab1a8  mov     rcx, rax; hHeap
0x1800ab1ab  call    cs:__imp_HeapAlloc
0x1800ab1b1  xor     ebx, ebx
0x1800ab1b3  mov     [rsp+270h+lpData+8], rax
0x1800ab1b8  mov     rcx, rax
0x1800ab1bb  lea     r12d, [rbx+1]
0x1800ab1bf  jmp     short loc_1800AB1C4
0x1800ab1c1  mov     r12d, ebx
0x1800ab1c4  mov     rax, [rbp+170h+dwBytes]
0x1800ab1c8  test    rax, rax
0x1800ab1cb  cmovz   rax, rcx
0x1800ab1cf  mov     [rbp+170h+dwBytes], rax
0x1800ab1d3  test    rcx, rcx
0x1800ab1d6  jz      loc_1800AB791
0x1800ab1dc  mov     [rsp+270h+lpdwDisposition], rbx; lpdwDisposition
0x1800ab1e1  lea     rax, [rsp+270h+hKey]
0x1800ab1e6  mov     [rsp+270h+phkResult], rax; phkResult
0x1800ab1eb  xor     r9d, r9d; lpClass
0x1800ab1ee  mov     [rsp+270h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800ab1f3  xor     r8d, r8d; Reserved
0x1800ab1f6  mov     [rsp+270h+samDesired], 2000000h; samDesired
0x1800ab1fe  mov     rdx, r13; lpSubKey
0x1800ab201  mov     rcx, rsi; hKey
0x1800ab204  mov     [rsp+270h+dwOptions], ebx; dwOptions
0x1800ab208  mov     [rsp+270h+hKey], rbx
0x1800ab20d  call    cs:__imp_RegCreateKeyExW
0x1800ab213  test    eax, eax
0x1800ab215  jnz     loc_1800AB2C6
0x1800ab21b  cmp     [rdi+108h], r14d
0x1800ab222  jle     short loc_1800AB28B
0x1800ab224  movsxd  rax, ebx
0x1800ab227  lea     rdx, [rax+rax*4]
0x1800ab22b  mov     rax, [rdi+90h]
0x1800ab232  shl     rdx, 4
0x1800ab236  mov     ecx, [rax+rdx+4]
0x1800ab23a  test    ecx, ecx
0x1800ab23c  jnz     short loc_1800AB24D
0x1800ab23e  mov     al, [rax+rdx+8]
0x1800ab242  not     al
0x1800ab244  movzx   ecx, al
0x1800ab247  shr     ecx, 3
0x1800ab24a  or      ecx, 0FFFFFFFEh
0x1800ab24d  mov     rax, [rbp+170h+dwBytes]
0x1800ab251  lea     r8, [rbp+170h+var_1E0.fsState]; struct _TBBUTTON *
0x1800ab255  mov     [rax], ecx
0x1800ab257  mov     rcx, rdi; this
0x1800ab25a  add     rdx, [rdi+90h]; struct _TBBUTTONDATA *
0x1800ab261  add     [rbp+170h+dwBytes], 4
0x1800ab266  mov     dword ptr [rbp+170h+dwBytes+0Ch], ebx
0x1800ab269  call    ?TBOutputStruct@CToolbar@@AEBAXPEBU_TBBUTTONDATA@@PEAU_TBBUTTON@@@Z; CToolbar::TBOutputStruct(_TBBUTTONDATA const *,_TBBUTTON *)
0x1800ab26e  lea     r8, [rsp+270h+lParam]
0x1800ab273  mov     edx, 0FFFFFD2Eh
0x1800ab278  lea     rcx, [rdi+38h]
0x1800ab27c  call    CCSendNotify
0x1800ab281  inc     ebx
0x1800ab283  cmp     ebx, [rdi+108h]
0x1800ab289  jl      short loc_1800AB224
0x1800ab28b  mov     eax, dword ptr [rbp+170h+dwBytes+8]
0x1800ab28e  mov     r9d, 3; dwType
0x1800ab294  mov     rcx, [rsp+270h+hKey]; hKey
0x1800ab299  xor     r8d, r8d; Reserved
0x1800ab29c  mov     [rsp+270h+samDesired], eax; cbData
0x1800ab2a0  mov     rdx, r15; lpValueName
0x1800ab2a3  mov     rax, [rsp+270h+lpData+8]
0x1800ab2a8  mov     qword ptr [rsp+270h+dwOptions], rax; lpData
0x1800ab2ad  call    cs:__imp_RegSetValueExW
0x1800ab2b3  mov     rcx, [rsp+270h+hKey]; hKey
0x1800ab2b8  xor     ebx, ebx
0x1800ab2ba  test    eax, eax
0x1800ab2bc  setz    r14b
0x1800ab2c0  call    cs:__imp_RegCloseKey
0x1800ab2c6  test    r12d, r12d
0x1800ab2c9  jz      loc_1800AB791
0x1800ab2cf  call    cs:__imp_GetProcessHeap
0x1800ab2d5  mov     r8, [rsp+270h+lpData+8]; lpMem
0x1800ab2da  xor     edx, edx; dwFlags
0x1800ab2dc  mov     rcx, rax; hHeap
0x1800ab2df  call    cs:__imp_HeapFree
0x1800ab2e5  jmp     loc_1800AB791
0x1800ab2ea  lea     rax, [rsp+270h+hKey]
0x1800ab2ef  mov     [rsp+270h+hKey], r12
0x1800ab2f4  mov     r9d, 20019h; samDesired
0x1800ab2fa  mov     qword ptr [rsp+270h+dwOptions], rax; phkResult
0x1800ab2ff  xor     r8d, r8d; ulOptions
0x1800ab302  mov     rdx, r13; lpSubKey
0x1800ab305  mov     rcx, rsi; hKey
0x1800ab308  call    cs:__imp_RegOpenKeyExW
0x1800ab30e  test    eax, eax
0x1800ab310  jnz     loc_1800AB791
0x1800ab316  mov     rcx, [rsp+270h+hKey]; hKey
0x1800ab31b  lea     rax, [rbp+170h+cbData]
0x1800ab31f  mov     qword ptr [rsp+270h+samDesired], rax; lpcbData
0x1800ab324  xor     r9d, r9d; lpType
0x1800ab327  xor     r8d, r8d; lpReserved
0x1800ab32a  mov     qword ptr [rsp+270h+dwOptions], r12; lpData
0x1800ab32f  mov     rdx, r15; lpValueName
0x1800ab332  mov     [rbp+170h+cbData], r12d
0x1800ab336  call    cs:__imp_RegQueryValueExW
0x1800ab33c  test    eax, eax
0x1800ab33e  jnz     loc_1800AB786
0x1800ab344  movsxd  rsi, [rbp+170h+cbData]
0x1800ab348  cmp     esi, 4
0x1800ab34b  jbe     loc_1800AB786
0x1800ab351  call    cs:__imp_GetProcessHeap
0x1800ab357  mov     r8d, esi; dwBytes
0x1800ab35a  mov     edx, 8; dwFlags
0x1800ab35f  mov     rcx, rax; hHeap
0x1800ab362  call    cs:__imp_HeapAlloc
0x1800ab368  mov     [rsp+270h+var_220], rax
0x1800ab36d  mov     r13, rax
0x1800ab370  test    rax, rax
0x1800ab373  jz      loc_1800AB786
0x1800ab379  mov     rcx, [rsp+270h+hKey]; hKey
0x1800ab37e  lea     rax, [rbp+170h+cbData]
0x1800ab382  mov     qword ptr [rsp+270h+samDesired], rax; lpcbData
0x1800ab387  lea     r9, [rbp+170h+Type]; lpType
0x1800ab38b  xor     r8d, r8d; lpReserved
0x1800ab38e  mov     qword ptr [rsp+270h+dwOptions], r13; lpData
0x1800ab393  mov     rdx, r15; lpValueName
0x1800ab396  mov     [rbp+170h+Type], r12d
0x1800ab39a  mov     [rbp+170h+cbData], esi
0x1800ab39d  call    cs:__imp_RegQueryValueExW
0x1800ab3a3  test    eax, eax
0x1800ab3a5  jnz     loc_1800AB772
0x1800ab3ab  cmp     [rbp+170h+Type], 3
0x1800ab3af  jnz     loc_1800AB772
0x1800ab3b5  cmp     [rbp+170h+cbData], esi
0x1800ab3b8  jnz     loc_1800AB772
0x1800ab3be  xor     edx, edx; Val
0x1800ab3c0  lea     r8d, [rax+58h]; Size
0x1800ab3c4  lea     rcx, [rbp+170h+var_1B0]; void *
0x1800ab3c8  call    memset_0
0x1800ab3cd  mov     rax, rsi
0x1800ab3d0  mov     [rbp+170h+var_198], r13
0x1800ab3d4  shr     rax, 2
0x1800ab3d8  lea     r15, [rdi+38h]
0x1800ab3dc  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800ab3e0  mov     [rbp+170h+var_180], eax
0x1800ab3e3  lea     r8, [rbp+170h+var_1B0]
0x1800ab3e7  mov     [rbp+170h+var_190], r13
0x1800ab3eb  mov     edx, 0FFFFFD2Fh
0x1800ab3f0  mov     [rbp+170h+var_184], r12d
0x1800ab3f4  mov     rcx, r15
0x1800ab3f7  mov     [rbp+170h+var_17C], 4
0x1800ab3fe  mov     [rbp+170h+var_188], esi
0x1800ab401  call    CCSendNotify
0x1800ab406  xor     esi, esi
0x1800ab408  test    rax, rax
0x1800ab40b  jnz     loc_1800AB772
0x1800ab411  lea     ebx, [rsi+48h]
0x1800ab414  cmp     [rdi+0A8h], rsi
0x1800ab41b  jz      short loc_1800AB488
0x1800ab41d  mov     r8d, ebx; Size
0x1800ab420  lea     rcx, [rsp+270h+lParam]; void *
0x1800ab425  xor     edx, edx; Val
0x1800ab427  call    memset_0
0x1800ab42c  mov     rax, [r15]
0x1800ab42f  mov     dword ptr [rsp+270h+lParam], ebx
0x1800ab433  mov     ebx, esi
0x1800ab435  mov     [rsp+270h+lParam+8], rax
0x1800ab43a  cmp     [rdi+108h], esi
0x1800ab440  jle     short loc_1800AB488
0x1800ab442  movsxd  rax, ebx
0x1800ab445  lea     rcx, [rax+rax*4]
0x1800ab449  mov     rax, [rdi+90h]
0x1800ab450  add     rcx, rcx
0x1800ab453  test    byte ptr [rax+rcx*8+9], 1
0x1800ab458  jnz     short loc_1800AB47E
0x1800ab45a  movsxd  rax, dword ptr [rax+rcx*8+4]
0x1800ab45f  lea     r9, [rsp+270h+lParam]; lParam
0x1800ab464  mov     rcx, [rdi+0A8h]; hWnd
0x1800ab46b  xor     r8d, r8d; wParam
0x1800ab46e  mov     edx, 433h; Msg
0x1800ab473  mov     [rsp+270h+lpData], rax
0x1800ab478  call    cs:__imp_SendMessageW
0x1800ab47e  inc     ebx
0x1800ab480  cmp     ebx, [rdi+108h]
0x1800ab486  jl      short loc_1800AB442
0x1800ab488  mov     edx, [rbp+170h+var_180]; unsigned int
0x1800ab48b  mov     rcx, rdi; this
0x1800ab48e  call    ?TBReallocButtons@CToolbar@@AEAAHI@Z; CToolbar::TBReallocButtons(uint)
0x1800ab493  test    eax, eax
0x1800ab495  jz      loc_1800AB772
0x1800ab49b  movsxd  rcx, dword ptr [rdi+108h]
0x1800ab4a2  mov     eax, [rbp+170h+var_180]
0x1800ab4a5  cmp     ecx, eax
0x1800ab4a7  jge     short loc_1800AB4CB
0x1800ab4a9  sub     eax, ecx
0x1800ab4ab  xor     edx, edx; Val
0x1800ab4ad  lea     rcx, [rcx+rcx*4]
0x1800ab4b1  movsxd  r8, eax
0x1800ab4b4  shl     rcx, 4
0x1800ab4b8  add     rcx, [rdi+90h]; void *
0x1800ab4bf  shl     r8, 5; Size
0x1800ab4c3  call    memset_0
0x1800ab4c8  mov     eax, [rbp+170h+var_180]
0x1800ab4cb  mov     [rdi+108h], eax
0x1800ab4d1  test    eax, eax
0x1800ab4d3  jle     loc_1800AB5B8
0x1800ab4d9  mov     rcx, [rdi+90h]
0x1800ab4e0  movsxd  rax, esi
0x1800ab4e3  mov     [rbp+170h+var_184], esi
0x1800ab4e6  lea     rbx, [rax+rax*4]
0x1800ab4ea  mov     rax, [rbp+170h+var_190]
0x1800ab4ee  shl     rbx, 4
0x1800ab4f2  cmp     [rax], r14d
0x1800ab4f5  jge     short loc_1800AB531
0x1800ab4f7  mov     byte ptr [rcx+rbx+9], 1
0x1800ab4fc  mov     rax, [rdi+90h]
0x1800ab503  mov     dword ptr [rbx+rax], 8
0x1800ab50a  mov     rax, [rdi+90h]
0x1800ab511  mov     [rax+rbx+4], r14d
0x1800ab516  mov     rax, [rbp+170h+var_190]
0x1800ab51a  mov     rdx, [rdi+90h]
0x1800ab521  mov     ecx, [rax]
0x1800ab523  inc     ecx
0x1800ab525  neg     ecx
0x1800ab527  sbb     al, al
0x1800ab529  and     al, 8
0x1800ab52b  mov     [rdx+rbx+8], al
0x1800ab52f  jmp     short loc_1800AB552
0x1800ab531  mov     [rcx+rbx+9], r14b
0x1800ab536  mov     rax, [rbp+170h+var_190]
0x1800ab53a  mov     rdx, [rdi+90h]
0x1800ab541  mov     ecx, [rax]
0x1800ab543  mov     [rdx+rbx+4], ecx
0x1800ab547  mov     rax, [rdi+90h]
0x1800ab54e  mov     [rbx+rax], r12d
0x1800ab552  mov     rdx, [rdi+90h]
0x1800ab559  lea     r8, [rbp+170h+var_178]; struct _TBBUTTON *
0x1800ab55d  add     [rbp+170h+var_190], 4
0x1800ab562  add     rdx, rbx; struct _TBBUTTONDATA *
0x1800ab565  mov     rcx, rdi; this
0x1800ab568  call    ?TBOutputStruct@CToolbar@@AEBAXPEBU_TBBUTTONDATA@@PEAU_TBBUTTON@@@Z; CToolbar::TBOutputStruct(_TBBUTTONDATA const *,_TBBUTTON *)
0x1800ab56d  lea     r8, [rbp+170h+var_1B0]
0x1800ab571  mov     edx, 0FFFFFD2Fh
0x1800ab576  mov     rcx, r15
0x1800ab579  call    CCSendNotify
0x1800ab57e  mov     rdx, [rbp+170h+var_178.iString]
0x1800ab582  lea     r8, [rbp+170h+var_178]; struct _TBBUTTON *
0x1800ab586  mov     rcx, rdx
0x1800ab589  shr     rcx, 10h
0x1800ab58d  test    cx, cx
0x1800ab590  mov     rcx, rdi; this
0x1800ab593  cmovnz  rdx, r14
0x1800ab597  mov     [rbp+170h+var_178.iString], rdx
0x1800ab59b  mov     rdx, [rdi+90h]
0x1800ab5a2  add     rdx, rbx; struct _TBBUTTONDATA *
0x1800ab5a5  call    ?TBInputStruct@CToolbar@@AEBAXPEAU_TBBUTTONDATA@@PEBU_TBBUTTON@@@Z; CToolbar::TBInputStruct(_TBBUTTONDATA *,_TBBUTTON const *)
0x1800ab5aa  inc     esi
0x1800ab5ac  cmp     esi, [rdi+108h]
0x1800ab5b2  jl      loc_1800AB4D9
0x1800ab5b8  xor     r8d, r8d
0x1800ab5bb  mov     edx, 0FFFFFD41h
  ... truncated ...
```
