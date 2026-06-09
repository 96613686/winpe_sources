# LoadDevicesFromRasman

- ea: `0x180014250`
- end: `0x180014567`
- name: `LoadDevicesFromRasman`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180016308`

## callees

- `0x180014250`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001452a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001452a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014351`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800142e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014351`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014538`
- `rasman!RasRpcDisconnectServer` at `0x180014547`
- `rasman!RasRpcDisconnectServer` at `0x180014547`
- `rasman!RasGetDeviceConfigInfo` at `0x1800142b8`
- `rasman!RasGetDeviceConfigInfo` at `0x180014303`
- `rasman!RasGetDeviceConfigInfo` at `0x1800142b8`
- `rasman!RasGetDeviceConfigInfo` at `0x180014303`
- `rasman!RasRpcConnectServer` at `0x180014282`
- `rasman!RasRpcConnectServer` at `0x180014282`

## pseudocode

```c
__int64 __fastcall LoadDevicesFromRasman(_QWORD *a1, unsigned int *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int DeviceConfigInfo; // eax
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rdi
  _DWORD *v10; // rsi
  char *v11; // r13
  unsigned int v12; // r14d
  HANDLE v13; // rax
  char *v14; // rax
  char *v15; // rdx
  _WORD *v16; // r9
  __int64 v17; // r8
  __int64 v18; // rcx
  _WORD *v19; // rax
  _WORD *v20; // rcx
  int v21; // r9d
  int v22; // ecx
  unsigned int v23; // r8d
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // r8
  _OWORD *v27; // rcx
  _OWORD *v28; // rax
  __int128 v29; // xmm1
  HANDLE v30; // rax
  int v32; // [rsp+30h] [rbp-10h] BYREF
  __int64 v33; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v34; // [rsp+90h] [rbp+50h] BYREF
  SIZE_T dwBytes; // [rsp+98h] [rbp+58h] BYREF

  v33 = 0;
  v34 = 0;
  LODWORD(dwBytes) = 0;
  v32 = 0;
  v4 = RasRpcConnectServer(0, &v33);
  if ( !v4 )
  {
    v5 = 6;
    if ( v33 )
      v5 = *(_DWORD *)(v33 + 12);
    v32 = v5;
    DeviceConfigInfo = RasGetDeviceConfigInfo(v33, &v32, &v34, &dwBytes, 0);
    v4 = 0;
    if ( DeviceConfigInfo != 603 )
      v4 = DeviceConfigInfo;
    if ( !v4 )
    {
      v7 = dwBytes;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, v7);
      v4 = RasGetDeviceConfigInfo(v33, &v32, &v34, &dwBytes, v9);
      if ( v4 )
        goto LABEL_47;
      if ( v34 && (unsigned int)(*v9 - 1) <= 4 )
      {
        v4 = 13;
        goto LABEL_47;
      }
      v10 = v9;
      v11 = 0;
      v12 = 0;
      if ( !v34 )
      {
LABEL_47:
        if ( v9 )
        {
          v30 = GetProcessHeap();
          HeapFree(v30, 0, v9);
        }
        goto LABEL_49;
      }
      while ( 1 )
      {
        v13 = GetProcessHeap();
        v14 = (char *)HeapAlloc(v13, 0, 0x318u);
        v15 = v14;
        if ( !v14 )
        {
          v4 = 14;
          goto LABEL_47;
        }
        *((_QWORD *)v14 + 98) = 0;
        v16 = (_WORD *)v10 + 107;
        *((_DWORD *)v14 + 73) = 0;
        v17 = 129;
        *((_DWORD *)v14 + 1) = v10[2];
        *((_DWORD *)v14 + 2) = v10[3];
        *((_DWORD *)v14 + 3) = v10[4];
        *(_DWORD *)v14 = v10[7];
        v18 = 2147483646;
        *((_DWORD *)v14 + 76) = v10[12];
        v19 = v14 + 28;
        do
        {
          if ( !v18 )
            break;
          if ( !*v16 )
            break;
          *v19++ = *v16++;
          --v18;
          --v17;
        }
        while ( v17 );
        v20 = v19 - 1;
        if ( v17 )
          v20 = v19;
        *v20 = 0;
        v21 = v10[10];
        v22 = (unsigned __int16)*((_DWORD *)v15 + 76);
        *((_DWORD *)v15 + 4) = v21;
        v23 = v10[11];
        *((_DWORD *)v15 + 5) = v23;
        *((_DWORD *)v15 + 6) = v23;
        switch ( v22 )
        {
          case 8:
            v24 = *a2;
            break;
          case 9:
            v24 = a2[1];
            break;
          case 14:
            v24 = a2[2];
            break;
          case 15:
            v24 = a2[3];
            break;
          case 16:
            v24 = a2[4];
            break;
          default:
            v24 = v23;
            goto LABEL_31;
        }
        *((_DWORD *)v15 + 6) = v24;
LABEL_31:
        if ( v23 <= v24 )
          v24 = v23;
        else
          *((_DWORD *)v15 + 5) = v24;
        if ( *(_DWORD *)v15 > v24 )
          *(_DWORD *)v15 = v24;
        if ( v21 == v24 || (v25 = 1, v22 == 13) )
          v25 = 0;
        v26 = 3;
        *((_DWORD *)v15 + 72) = v25;
        *((_QWORD *)v15 + 37) = 0;
        v27 = v15 + 308;
        v28 = v10;
        do
        {
          *v27 = *v28;
          v27[1] = v28[1];
          v27[2] = v28[2];
          v27[3] = v28[3];
          v27[4] = v28[4];
          v27[5] = v28[5];
          v27[6] = v28[6];
          v29 = v28[7];
          v28 += 8;
          v27[7] = v29;
          v27 += 8;
          --v26;
        }
        while ( v26 );
        *v27 = *v28;
        v27[1] = v28[1];
        v27[2] = v28[2];
        v27[3] = v28[3];
        v27[4] = v28[4];
        *((_QWORD *)v27 + 10) = *((_QWORD *)v28 + 10);
        if ( *a1 )
          *((_QWORD *)v11 + 98) = v15;
        else
          *a1 = v15;
        ++v12;
        v10 += 118;
        v11 = v15;
        if ( v12 >= v34 )
          goto LABEL_47;
      }
    }
  }
LABEL_49:
  if ( v33 )
    RasRpcDisconnectServer();
  return v4;
}

```

## disassembly

```asm
0x180014250  mov     [rsp-38h+arg_0], rbx
0x180014255  push    rbp
0x180014256  push    rsi
0x180014257  push    rdi
0x180014258  push    r12
0x18001425a  push    r13
0x18001425c  push    r14
0x18001425e  push    r15
0x180014260  mov     rbp, rsp
0x180014263  sub     rsp, 40h
0x180014267  xor     eax, eax
0x180014269  mov     r15, rdx
0x18001426c  mov     r12, rcx
0x18001426f  mov     [rbp+var_8], rax
0x180014273  lea     rdx, [rbp+var_8]
0x180014277  mov     [rbp+arg_10], eax
0x18001427a  xor     ecx, ecx
0x18001427c  mov     dword ptr [rbp+dwBytes], eax
0x18001427f  mov     [rbp+var_10], eax
0x180014282  call    cs:__imp_RasRpcConnectServer
0x180014288  xor     r11d, r11d
0x18001428b  mov     ebx, eax
0x18001428d  test    eax, eax
0x18001428f  jnz     loc_18001453E
0x180014295  mov     rcx, [rbp+var_8]
0x180014299  lea     eax, [rbx+6]
0x18001429c  test    rcx, rcx
0x18001429f  jz      short loc_1800142A4
0x1800142a1  mov     eax, [rcx+0Ch]
0x1800142a4  lea     r9, [rbp+dwBytes]
0x1800142a8  mov     [rbp+var_10], eax
0x1800142ab  lea     r8, [rbp+arg_10]
0x1800142af  mov     [rsp+40h+var_20], r11
0x1800142b4  lea     rdx, [rbp+var_10]
0x1800142b8  call    cs:__imp_RasGetDeviceConfigInfo
0x1800142be  xor     r11d, r11d
0x1800142c1  cmp     eax, 25Bh
0x1800142c6  mov     ebx, r11d
0x1800142c9  cmovnz  ebx, eax
0x1800142cc  test    ebx, ebx
0x1800142ce  jnz     loc_18001453E
0x1800142d4  mov     ebx, dword ptr [rbp+dwBytes]
0x1800142d7  call    cs:__imp_GetProcessHeap
0x1800142dd  mov     r8d, ebx; dwBytes
0x1800142e0  xor     edx, edx; dwFlags
0x1800142e2  mov     rcx, rax; hHeap
0x1800142e5  call    cs:__imp_HeapAlloc
0x1800142eb  mov     rcx, [rbp+var_8]
0x1800142ef  lea     r9, [rbp+dwBytes]
0x1800142f3  lea     r8, [rbp+arg_10]
0x1800142f7  mov     [rsp+40h+var_20], rax
0x1800142fc  lea     rdx, [rbp+var_10]
0x180014300  mov     rdi, rax
0x180014303  call    cs:__imp_RasGetDeviceConfigInfo
0x180014309  xor     r11d, r11d
0x18001430c  mov     ebx, eax
0x18001430e  test    eax, eax
0x180014310  jnz     loc_180014525
0x180014316  mov     ecx, [rbp+arg_10]
0x180014319  test    ecx, ecx
0x18001431b  jz      short loc_18001432F
0x18001431d  mov     eax, [rdi]
0x18001431f  dec     eax
0x180014321  cmp     eax, 4
0x180014324  ja      short loc_18001432F
0x180014326  lea     ebx, [r11+0Dh]
0x18001432a  jmp     loc_180014525
0x18001432f  mov     rsi, rdi
0x180014332  mov     r13, r11
0x180014335  mov     r14d, r11d
0x180014338  test    ecx, ecx
0x18001433a  jz      loc_180014525
0x180014340  call    cs:__imp_GetProcessHeap
0x180014346  xor     edx, edx; dwFlags
0x180014348  mov     r8d, 318h; dwBytes
0x18001434e  mov     rcx, rax; hHeap
0x180014351  call    cs:__imp_HeapAlloc
0x180014357  xor     r11d, r11d
0x18001435a  mov     rdx, rax
0x18001435d  test    rax, rax
0x180014360  jz      loc_180014520
0x180014366  mov     [rax+310h], r11
0x18001436d  lea     r9, [rsi+0D6h]
0x180014374  mov     [rax+124h], r11d
0x18001437b  mov     r8d, 81h
0x180014381  mov     ecx, [rsi+8]
0x180014384  mov     [rax+4], ecx
0x180014387  mov     ecx, [rsi+0Ch]
0x18001438a  mov     [rax+8], ecx
0x18001438d  mov     ecx, [rsi+10h]
0x180014390  mov     [rax+0Ch], ecx
0x180014393  mov     ecx, [rsi+1Ch]
0x180014396  mov     [rax], ecx
0x180014398  mov     ecx, 7FFFFFFEh
0x18001439d  mov     eax, [rsi+30h]
0x1800143a0  mov     [rdx+130h], eax
0x1800143a6  lea     rax, [rdx+1Ch]
0x1800143aa  test    rcx, rcx
0x1800143ad  jz      short loc_1800143CE
0x1800143af  movzx   r10d, word ptr [r9]
0x1800143b3  test    r10w, r10w
0x1800143b7  jz      short loc_1800143CE
0x1800143b9  mov     [rax], r10w
0x1800143bd  add     r9, 2
0x1800143c1  add     rax, 2
0x1800143c5  dec     rcx
0x1800143c8  sub     r8, 1
0x1800143cc  jnz     short loc_1800143AA
0x1800143ce  test    r8, r8
0x1800143d1  lea     rcx, [rax-2]
0x1800143d5  cmovnz  rcx, rax
0x1800143d9  mov     [rcx], r11w
0x1800143dd  mov     r9d, [rsi+28h]
0x1800143e1  mov     ecx, [rdx+130h]
0x1800143e7  movzx   ecx, cx
0x1800143ea  mov     [rdx+10h], r9d
0x1800143ee  mov     r8d, [rsi+2Ch]
0x1800143f2  mov     [rdx+14h], r8d
0x1800143f6  mov     [rdx+18h], r8d
0x1800143fa  cmp     ecx, 8
0x1800143fd  jnz     short loc_180014404
0x1800143ff  mov     eax, [r15]
0x180014402  jmp     short loc_18001442E
0x180014404  cmp     ecx, 9
0x180014407  jnz     short loc_18001440F
0x180014409  mov     eax, [r15+4]
0x18001440d  jmp     short loc_18001442E
0x18001440f  cmp     ecx, 0Eh
0x180014412  jnz     short loc_18001441A
0x180014414  mov     eax, [r15+8]
0x180014418  jmp     short loc_18001442E
0x18001441a  cmp     ecx, 0Fh
0x18001441d  jnz     short loc_180014425
0x18001441f  mov     eax, [r15+0Ch]
0x180014423  jmp     short loc_18001442E
0x180014425  cmp     ecx, 10h
0x180014428  jnz     short loc_180014433
0x18001442a  mov     eax, [r15+10h]
0x18001442e  mov     [rdx+18h], eax
0x180014431  jmp     short loc_180014436
0x180014433  mov     eax, r8d
0x180014436  cmp     r8d, eax
0x180014439  jbe     short loc_180014440
0x18001443b  mov     [rdx+14h], eax
0x18001443e  jmp     short loc_180014443
0x180014440  mov     eax, r8d
0x180014443  cmp     [rdx], eax
0x180014445  jbe     short loc_180014449
0x180014447  mov     [rdx], eax
0x180014449  cmp     r9d, eax
0x18001444c  jz      short loc_180014458
0x18001444e  mov     eax, 1
0x180014453  cmp     ecx, 0Dh
0x180014456  jnz     short loc_18001445B
0x180014458  mov     eax, r11d
0x18001445b  mov     r8d, 3
0x180014461  mov     [rdx+120h], eax
0x180014467  mov     [rdx+128h], r11
0x18001446e  lea     rcx, [rdx+134h]
0x180014475  mov     rax, rsi
0x180014478  lea     r9d, [r8+7Dh]
0x18001447c  movups  xmm0, xmmword ptr [rax]
0x18001447f  movups  xmmword ptr [rcx], xmm0
0x180014482  movups  xmm1, xmmword ptr [rax+10h]
0x180014486  movups  xmmword ptr [rcx+10h], xmm1
0x18001448a  movups  xmm0, xmmword ptr [rax+20h]
0x18001448e  movups  xmmword ptr [rcx+20h], xmm0
0x180014492  movups  xmm1, xmmword ptr [rax+30h]
0x180014496  movups  xmmword ptr [rcx+30h], xmm1
0x18001449a  movups  xmm0, xmmword ptr [rax+40h]
0x18001449e  movups  xmmword ptr [rcx+40h], xmm0
0x1800144a2  movups  xmm1, xmmword ptr [rax+50h]
0x1800144a6  movups  xmmword ptr [rcx+50h], xmm1
0x1800144aa  movups  xmm0, xmmword ptr [rax+60h]
0x1800144ae  movups  xmmword ptr [rcx+60h], xmm0
0x1800144b2  movups  xmm1, xmmword ptr [rax+70h]
0x1800144b6  add     rax, r9
0x1800144b9  movups  xmmword ptr [rcx+70h], xmm1
0x1800144bd  add     rcx, r9
0x1800144c0  sub     r8, 1
0x1800144c4  jnz     short loc_18001447C
0x1800144c6  movups  xmm0, xmmword ptr [rax]
0x1800144c9  movups  xmmword ptr [rcx], xmm0
0x1800144cc  movups  xmm1, xmmword ptr [rax+10h]
0x1800144d0  movups  xmmword ptr [rcx+10h], xmm1
0x1800144d4  movups  xmm0, xmmword ptr [rax+20h]
0x1800144d8  movups  xmmword ptr [rcx+20h], xmm0
0x1800144dc  movups  xmm1, xmmword ptr [rax+30h]
0x1800144e0  movups  xmmword ptr [rcx+30h], xmm1
0x1800144e4  movups  xmm0, xmmword ptr [rax+40h]
0x1800144e8  movups  xmmword ptr [rcx+40h], xmm0
0x1800144ec  mov     rax, [rax+50h]
0x1800144f0  mov     [rcx+50h], rax
0x1800144f4  cmp     [r12], r11
0x1800144f8  jnz     short loc_180014500
0x1800144fa  mov     [r12], rdx
0x1800144fe  jmp     short loc_180014507
0x180014500  mov     [r13+310h], rdx
0x180014507  inc     r14d
0x18001450a  add     rsi, 1D8h
0x180014511  mov     r13, rdx
0x180014514  cmp     r14d, [rbp+arg_10]
0x180014518  jb      loc_180014340
0x18001451e  jmp     short loc_180014525
0x180014520  mov     ebx, 0Eh
0x180014525  test    rdi, rdi
0x180014528  jz      short loc_18001453E
0x18001452a  call    cs:__imp_GetProcessHeap
0x180014530  mov     r8, rdi; lpMem
0x180014533  xor     edx, edx; dwFlags
0x180014535  mov     rcx, rax; hHeap
0x180014538  call    cs:__imp_HeapFree
0x18001453e  mov     rcx, [rbp+var_8]
0x180014542  test    rcx, rcx
0x180014545  jz      short loc_18001454D
0x180014547  call    cs:__imp_RasRpcDisconnectServer
0x18001454d  mov     eax, ebx
0x18001454f  mov     rbx, [rsp+40h+arg_0]
0x180014557  add     rsp, 40h
0x18001455b  pop     r15
0x18001455d  pop     r14
0x18001455f  pop     r13
0x180014561  pop     r12
0x180014563  pop     rdi
0x180014564  pop     rsi
0x180014565  pop     rbp
0x180014566  retn
```
