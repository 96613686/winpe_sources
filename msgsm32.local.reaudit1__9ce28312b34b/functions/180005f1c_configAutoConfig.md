# configAutoConfig

- ea: `0x180005f1c`
- end: `0x180006321`
- name: `configAutoConfig`
- size: `1029`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005920`
- `0x180005ce4`

## callees

- `0x180004f60`
- `0x180005350`
- `0x180005850`
- `0x180005f1c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f92`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006253`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006273`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006293`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062b3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062f3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006253`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006273`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006293`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062b3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062fd`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180006097`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800060e4`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180006167`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800061b8`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180006097`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800060e4`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180006167`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800061b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000624a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000626a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000628a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062aa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062ca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000624a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000626a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000628a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062aa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062ca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062ea`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180005f75`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180005f75`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180005f7e`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180006307`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180005f7e`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180006307`

## pseudocode

```c
__int64 __fastcall configAutoConfig(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  HCURSOR CursorW; // rax
  __int64 v4; // r13
  __int64 v5; // rdi
  _DWORD *v6; // r15
  _DWORD *v7; // r12
  __int64 v8; // r14
  __int64 v9; // rax
  __int64 v10; // rsi
  DWORD Time; // eax
  DWORD v12; // ebx
  DWORD v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ecx
  unsigned int v16; // edi
  __int64 v17; // rdx
  DWORD v18; // eax
  DWORD v19; // ebx
  DWORD v20; // eax
  unsigned int v21; // ecx
  unsigned int v22; // r8d
  __int64 v23; // rdx
  HGLOBAL v24; // rbx
  HGLOBAL v25; // rbx
  HGLOBAL v26; // rbx
  HGLOBAL v27; // rbx
  HGLOBAL v28; // rbx
  HGLOBAL v29; // rbx
  HLOCAL v31; // [rsp+20h] [rbp-58h]
  __int64 v32; // [rsp+28h] [rbp-50h]
  HGLOBAL hMem; // [rsp+30h] [rbp-48h] BYREF
  HGLOBAL v34; // [rsp+38h] [rbp-40h] BYREF
  HGLOBAL v35; // [rsp+40h] [rbp-38h] BYREF
  HGLOBAL v36; // [rsp+48h] [rbp-30h] BYREF
  HGLOBAL v37; // [rsp+50h] [rbp-28h] BYREF
  HGLOBAL v38; // [rsp+58h] [rbp-20h] BYREF
  HCURSOR hCursor; // [rsp+60h] [rbp-18h]
  unsigned int v43; // [rsp+D8h] [rbp+60h]

  v37 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v34 = 0;
  hMem = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  hCursor = SetCursor(CursorW);
  v31 = LocalAlloc(0x40u, 0x28Eu);
  v4 = GlobalAllocLock(&v37, 32000);
  v32 = GlobalAllocLock(&v38, 3250);
  v5 = v32;
  v6 = (_DWORD *)GlobalAllocLock(&v35, 16);
  v7 = (_DWORD *)GlobalAllocLock(&v36, 20);
  v8 = GlobalAllocLock(&v34, 68);
  v9 = GlobalAllocLock(&hMem, 124);
  v10 = v9;
  if ( !v31 || !v4 || !v32 || !v6 || !v7 || !v8 || !v9 )
  {
    v43 = 31;
    goto LABEL_31;
  }
  *v7 = 65585;
  v7[1] = 8000;
  v7[2] = 1625;
  v7[3] = 65;
  v7[4] = 20971520;
  *v6 = 65537;
  v6[1] = 8000;
  v6[2] = 16000;
  v6[3] = 1048578;
  v43 = 0;
  Time = timeGetTime();
  *(_DWORD *)v8 = 68;
  *(_QWORD *)(v8 + 4) = v6;
  v12 = Time;
  *(_QWORD *)(v8 + 52) = v31;
  *(_QWORD *)(v8 + 12) = v7;
  *(_DWORD *)v10 = 124;
  *(_QWORD *)(v10 + 16) = v4;
  *(_DWORD *)(v10 + 24) = 32000;
  *(_QWORD *)(v10 + 40) = v32;
  *(_DWORD *)(v10 + 48) = 3250;
  *(_DWORD *)(v10 + 64) = 20;
  gsm610Encode(v8, v10);
  v13 = timeGetTime();
  if ( v13 == v12 )
    v14 = -1;
  else
    v14 = 2000 * v6[1] / (v13 - v12);
  v15 = *(_DWORD *)(a1 + 64);
  if ( 0xFFFFFFFF / v15 >= v14 )
    v14 = v14 * v15 / 0x64;
  v16 = 0xFFFF;
  if ( v14 > 0xFFFF )
  {
    v14 = 0xFFFF;
    goto LABEL_16;
  }
  LODWORD(v17) = 0;
  if ( v14 )
  {
LABEL_16:
    LODWORD(v17) = 0;
    do
    {
      if ( (unsigned int)v17 >= 6 )
        break;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( *((_DWORD *)&gaRateListFormat[1] + 3 * v17) < v14 );
  }
  *a2 = v17 - 1;
  v18 = timeGetTime();
  *(_DWORD *)v8 = 68;
  *(_QWORD *)(v8 + 4) = v7;
  v19 = v18;
  *(_QWORD *)(v8 + 52) = v31;
  *(_QWORD *)(v8 + 12) = v6;
  *(_QWORD *)(v10 + 16) = v32;
  *(_DWORD *)v10 = 124;
  *(_DWORD *)(v10 + 24) = 3250;
  *(_QWORD *)(v10 + 40) = v4;
  *(_DWORD *)(v10 + 48) = 32000;
  *(_DWORD *)(v10 + 64) = 20;
  gsm610Decode(v8, v10);
  v20 = timeGetTime();
  if ( v20 == v19 )
    v21 = -1;
  else
    v21 = 2000 * v6[1] / (v20 - v19);
  v22 = *(_DWORD *)(a1 + 64);
  if ( 0xFFFFFFFF / v22 >= v21 )
    v21 = v21 * v22 / 0x64;
  if ( v21 > 0xFFFF || (LODWORD(v23) = 0, (v16 = v21) != 0) )
  {
    LODWORD(v23) = 0;
    do
    {
      if ( (unsigned int)v23 >= 6 )
        break;
      v23 = (unsigned int)(v23 + 1);
    }
    while ( *((_DWORD *)&gaRateListFormat[1] + 3 * v23) < v16 );
  }
  v5 = v32;
  *a3 = v23 - 1;
LABEL_31:
  v24 = hMem;
  if ( hMem )
  {
    if ( v10 )
      GlobalUnlock(hMem);
    GlobalFree(v24);
  }
  v25 = v34;
  if ( v34 )
  {
    if ( v8 )
      GlobalUnlock(v34);
    GlobalFree(v25);
  }
  v26 = v35;
  if ( v35 )
  {
    if ( v6 )
      GlobalUnlock(v35);
    GlobalFree(v26);
  }
  v27 = v36;
  if ( v36 )
  {
    if ( v7 )
      GlobalUnlock(v36);
    GlobalFree(v27);
  }
  v28 = v37;
  if ( v37 )
  {
    if ( v4 )
      GlobalUnlock(v37);
    GlobalFree(v28);
  }
  v29 = v38;
  if ( v38 )
  {
    if ( v5 )
      GlobalUnlock(v38);
    GlobalFree(v29);
  }
  LocalFree(v31);
  SetCursor(hCursor);
  return v43;
}

```

## disassembly

```asm
0x180005f1c  mov     [rsp-40h+arg_10], r8
0x180005f21  mov     [rsp-40h+arg_8], rdx
0x180005f26  mov     [rsp-40h+arg_0], rcx
0x180005f2b  push    rbp
0x180005f2c  push    rbx
0x180005f2d  push    rsi
0x180005f2e  push    rdi
0x180005f2f  push    r12
0x180005f31  push    r13
0x180005f33  push    r14
0x180005f35  push    r15
0x180005f37  mov     rbp, rsp
0x180005f3a  sub     rsp, 78h
0x180005f3e  mov     edx, 7F02h; lpCursorName
0x180005f43  mov     [rbp+var_28], 0
0x180005f4b  xor     ecx, ecx; hInstance
0x180005f4d  mov     [rbp+var_20], 0
0x180005f55  mov     [rbp+var_38], 0
0x180005f5d  mov     [rbp+var_30], 0
0x180005f65  mov     [rbp+var_40], 0
0x180005f6d  mov     [rbp+hMem], 0
0x180005f75  call    cs:__imp_LoadCursorW
0x180005f7b  mov     rcx, rax; hCursor
0x180005f7e  call    cs:__imp_SetCursor
0x180005f84  mov     edx, 28Eh; uBytes
0x180005f89  mov     ecx, 40h ; '@'; uFlags
0x180005f8e  mov     [rbp+hCursor], rax
0x180005f92  call    cs:__imp_LocalAlloc
0x180005f98  mov     edx, 7D00h
0x180005f9d  lea     rcx, [rbp+var_28]
0x180005fa1  mov     rbx, rax
0x180005fa4  mov     [rbp+var_58], rax
0x180005fa8  call    GlobalAllocLock
0x180005fad  mov     edx, 0CB2h
0x180005fb2  lea     rcx, [rbp+var_20]
0x180005fb6  mov     r13, rax
0x180005fb9  call    GlobalAllocLock
0x180005fbe  mov     edx, 10h
0x180005fc3  mov     [rbp+var_50], rax
0x180005fc7  lea     rcx, [rbp+var_38]
0x180005fcb  mov     rdi, rax
0x180005fce  call    GlobalAllocLock
0x180005fd3  mov     edx, 14h
0x180005fd8  lea     rcx, [rbp+var_30]
0x180005fdc  mov     r15, rax
0x180005fdf  call    GlobalAllocLock
0x180005fe4  mov     edx, 44h ; 'D'
0x180005fe9  lea     rcx, [rbp+var_40]
0x180005fed  mov     r12, rax
0x180005ff0  call    GlobalAllocLock
0x180005ff5  mov     edx, 7Ch ; '|'
0x180005ffa  lea     rcx, [rbp+hMem]
0x180005ffe  mov     r14, rax
0x180006001  call    GlobalAllocLock
0x180006006  mov     rsi, rax
0x180006009  test    rbx, rbx
0x18000600c  jz      loc_180006232
0x180006012  test    r13, r13
0x180006015  jz      loc_180006232
0x18000601b  test    rdi, rdi
0x18000601e  jz      loc_180006232
0x180006024  test    r15, r15
0x180006027  jz      loc_180006232
0x18000602d  test    r12, r12
0x180006030  jz      loc_180006232
0x180006036  test    r14, r14
0x180006039  jz      loc_180006232
0x18000603f  test    rax, rax
0x180006042  jz      loc_180006232
0x180006048  mov     dword ptr [r12], 10031h
0x180006050  mov     ecx, 1F40h
0x180006055  mov     [r12+4], ecx
0x18000605a  mov     dword ptr [r12+8], 659h
0x180006063  mov     dword ptr [r12+0Ch], 41h ; 'A'
0x18000606c  mov     dword ptr [r12+10h], 1400000h
0x180006075  mov     dword ptr [r15], 10001h
0x18000607c  mov     [r15+4], ecx
0x180006080  mov     dword ptr [r15+8], 3E80h
0x180006088  mov     dword ptr [r15+0Ch], 100002h
0x180006090  mov     [rbp+arg_18], 0
0x180006097  call    cs:__imp_timeGetTime
0x18000609d  mov     dword ptr [r14], 44h ; 'D'
0x1800060a4  mov     rdx, rsi
0x1800060a7  mov     [r14+4], r15
0x1800060ab  mov     ebx, eax
0x1800060ad  mov     rax, [rbp+var_58]
0x1800060b1  mov     rcx, r14
0x1800060b4  mov     [r14+34h], rax
0x1800060b8  mov     [r14+0Ch], r12
0x1800060bc  mov     dword ptr [rsi], 7Ch ; '|'
0x1800060c2  mov     [rsi+10h], r13
0x1800060c6  mov     dword ptr [rsi+18h], 7D00h
0x1800060cd  mov     [rsi+28h], rdi
0x1800060d1  mov     dword ptr [rsi+30h], 0CB2h
0x1800060d8  mov     dword ptr [rsi+40h], 14h
0x1800060df  call    gsm610Encode
0x1800060e4  call    cs:__imp_timeGetTime
0x1800060ea  mov     ecx, eax
0x1800060ec  or      r9d, 0FFFFFFFFh
0x1800060f0  sub     ecx, ebx
0x1800060f2  jnz     short loc_1800060F9
0x1800060f4  mov     r8d, r9d
0x1800060f7  jmp     short loc_180006108
0x1800060f9  imul    eax, [r15+4], 7D0h
0x180006101  xor     edx, edx
0x180006103  div     ecx
0x180006105  mov     r8d, eax
0x180006108  mov     rcx, [rbp+arg_0]
0x18000610c  xor     edx, edx
0x18000610e  mov     eax, r9d
0x180006111  mov     ecx, [rcx+40h]
0x180006114  div     ecx
0x180006116  cmp     eax, r8d
0x180006119  jb      short loc_18000612D
0x18000611b  imul    ecx, r8d
0x18000611f  mov     eax, 51EB851Fh
0x180006124  mul     ecx
0x180006126  mov     r8d, edx
0x180006129  shr     r8d, 5
0x18000612d  mov     edi, 0FFFFh
0x180006132  lea     r9, gaRateListFormat
0x180006139  cmp     r8d, edi
0x18000613c  jbe     short loc_180006143
0x18000613e  mov     r8d, edi
0x180006141  jmp     short loc_18000614A
0x180006143  xor     edx, edx
0x180006145  test    r8d, r8d
0x180006148  jz      short loc_18000615E
0x18000614a  xor     edx, edx
0x18000614c  cmp     edx, 6
0x18000614f  jnb     short loc_18000615E
0x180006151  inc     edx
0x180006153  lea     rcx, [rdx+rdx*2]
0x180006157  cmp     [r9+rcx*4+8], r8d
0x18000615c  jb      short loc_18000614C
0x18000615e  mov     rcx, [rbp+arg_8]
0x180006162  lea     eax, [rdx-1]
0x180006165  mov     [rcx], eax
0x180006167  call    cs:__imp_timeGetTime
0x18000616d  mov     dword ptr [r14], 44h ; 'D'
0x180006174  mov     rdx, rsi
0x180006177  mov     [r14+4], r12
0x18000617b  mov     ebx, eax
0x18000617d  mov     rax, [rbp+var_58]
0x180006181  mov     rcx, r14
0x180006184  mov     [r14+34h], rax
0x180006188  mov     rax, [rbp+var_50]
0x18000618c  mov     [r14+0Ch], r15
0x180006190  mov     [rsi+10h], rax
0x180006194  mov     dword ptr [rsi], 7Ch ; '|'
0x18000619a  mov     dword ptr [rsi+18h], 0CB2h
0x1800061a1  mov     [rsi+28h], r13
0x1800061a5  mov     dword ptr [rsi+30h], 7D00h
0x1800061ac  mov     dword ptr [rsi+40h], 14h
0x1800061b3  call    gsm610Decode
0x1800061b8  call    cs:__imp_timeGetTime
0x1800061be  mov     ecx, eax
0x1800061c0  sub     ecx, ebx
0x1800061c2  jnz     short loc_1800061C9
0x1800061c4  or      ecx, 0FFFFFFFFh
0x1800061c7  jmp     short loc_1800061D7
0x1800061c9  imul    eax, [r15+4], 7D0h
0x1800061d1  xor     edx, edx
0x1800061d3  div     ecx
0x1800061d5  mov     ecx, eax
0x1800061d7  mov     rax, [rbp+arg_0]
0x1800061db  xor     edx, edx
0x1800061dd  mov     r8d, [rax+40h]
0x1800061e1  or      eax, 0FFFFFFFFh
0x1800061e4  div     r8d
0x1800061e7  cmp     eax, ecx
0x1800061e9  jb      short loc_1800061FC
0x1800061eb  imul    r8d, ecx
0x1800061ef  mov     eax, 51EB851Fh
0x1800061f4  mul     r8d
0x1800061f7  mov     ecx, edx
0x1800061f9  shr     ecx, 5
0x1800061fc  cmp     ecx, edi
0x1800061fe  ja      short loc_180006208
0x180006200  xor     edx, edx
0x180006202  mov     edi, ecx
0x180006204  test    ecx, ecx
0x180006206  jz      short loc_180006223
0x180006208  xor     edx, edx
0x18000620a  lea     r8, gaRateListFormat
0x180006211  cmp     edx, 6
0x180006214  jnb     short loc_180006223
0x180006216  inc     edx
0x180006218  lea     rcx, [rdx+rdx*2]
0x18000621c  cmp     [r8+rcx*4+8], edi
0x180006221  jb      short loc_180006211
0x180006223  mov     rcx, [rbp+arg_10]
0x180006227  lea     eax, [rdx-1]
0x18000622a  mov     rdi, [rbp+var_50]
0x18000622e  mov     [rcx], eax
0x180006230  jmp     short loc_180006239
0x180006232  mov     [rbp+arg_18], 1Fh
0x180006239  mov     rbx, [rbp+hMem]
0x18000623d  test    rbx, rbx
0x180006240  jz      short loc_180006259
0x180006242  test    rsi, rsi
0x180006245  jz      short loc_180006250
0x180006247  mov     rcx, rbx; hMem
0x18000624a  call    cs:__imp_GlobalUnlock
0x180006250  mov     rcx, rbx; hMem
0x180006253  call    cs:__imp_GlobalFree
0x180006259  mov     rbx, [rbp+var_40]
0x18000625d  test    rbx, rbx
0x180006260  jz      short loc_180006279
0x180006262  test    r14, r14
0x180006265  jz      short loc_180006270
0x180006267  mov     rcx, rbx; hMem
0x18000626a  call    cs:__imp_GlobalUnlock
0x180006270  mov     rcx, rbx; hMem
0x180006273  call    cs:__imp_GlobalFree
0x180006279  mov     rbx, [rbp+var_38]
0x18000627d  test    rbx, rbx
0x180006280  jz      short loc_180006299
0x180006282  test    r15, r15
0x180006285  jz      short loc_180006290
0x180006287  mov     rcx, rbx; hMem
0x18000628a  call    cs:__imp_GlobalUnlock
0x180006290  mov     rcx, rbx; hMem
0x180006293  call    cs:__imp_GlobalFree
0x180006299  mov     rbx, [rbp+var_30]
0x18000629d  test    rbx, rbx
0x1800062a0  jz      short loc_1800062B9
0x1800062a2  test    r12, r12
0x1800062a5  jz      short loc_1800062B0
0x1800062a7  mov     rcx, rbx; hMem
0x1800062aa  call    cs:__imp_GlobalUnlock
0x1800062b0  mov     rcx, rbx; hMem
0x1800062b3  call    cs:__imp_GlobalFree
0x1800062b9  mov     rbx, [rbp+var_28]
0x1800062bd  test    rbx, rbx
0x1800062c0  jz      short loc_1800062D9
0x1800062c2  test    r13, r13
0x1800062c5  jz      short loc_1800062D0
0x1800062c7  mov     rcx, rbx; hMem
0x1800062ca  call    cs:__imp_GlobalUnlock
0x1800062d0  mov     rcx, rbx; hMem
0x1800062d3  call    cs:__imp_GlobalFree
0x1800062d9  mov     rbx, [rbp+var_20]
0x1800062dd  test    rbx, rbx
0x1800062e0  jz      short loc_1800062F9
0x1800062e2  test    rdi, rdi
0x1800062e5  jz      short loc_1800062F0
0x1800062e7  mov     rcx, rbx; hMem
0x1800062ea  call    cs:__imp_GlobalUnlock
0x1800062f0  mov     rcx, rbx; hMem
0x1800062f3  call    cs:__imp_GlobalFree
0x1800062f9  mov     rcx, [rbp+var_58]; hMem
0x1800062fd  call    cs:__imp_LocalFree
0x180006303  mov     rcx, [rbp+hCursor]; hCursor
0x180006307  call    cs:__imp_SetCursor
0x18000630d  mov     eax, [rbp+arg_18]
0x180006310  add     rsp, 78h
0x180006314  pop     r15
0x180006316  pop     r14
0x180006318  pop     r13
0x18000631a  pop     r12
0x18000631c  pop     rdi
0x18000631d  pop     rsi
0x18000631e  pop     rbx
0x18000631f  pop     rbp
0x180006320  retn
```
