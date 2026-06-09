# DDMAdminServerSetInfo

- ea: `0x180005650`
- end: `0x1800059e9`
- name: `DDMAdminServerSetInfo`
- size: `921`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005650`
- `0x180007b7c`
- `0x180020098`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800058c9`
- `KERNEL32!HeapAlloc` at `0x1800058c9`
- `KERNEL32!HeapFree` at `0x1800059de`
- `KERNEL32!HeapFree` at `0x1800059de`
- `rasman!RasGetDeviceConfigInfo` at `0x180005686`
- `rasman!RasSetDeviceConfigInfo` at `0x180005690`

## pseudocode

```c
__int64 __fastcall DDMAdminServerSetInfo(int *a1, int a2)
{
  __int64 (__fastcall *v2)(int, int, int, int, void *); // rdi
  __int64 (__fastcall *v4)(__int64, unsigned int, unsigned int, __int64); // r12
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // r8d
  unsigned int *v9; // rax
  unsigned int v11; // edx
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int v14; // edx
  unsigned int v15; // eax
  char *v16; // rax
  char *v17; // rsi
  unsigned int v18; // r10d
  int v19; // edi
  int v20; // r11d
  unsigned int v21; // r8d
  unsigned int v22; // edx
  __int64 v23; // rax
  char *v24; // r9
  int v25; // eax
  unsigned int *v26; // rax
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int dwBytes; // [rsp+34h] [rbp-CCh] BYREF
  int dwBytes_4; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v32; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+40h] [rbp-C0h] BYREF
  int *v34; // [rsp+50h] [rbp-B0h]
  int v35; // [rsp+58h] [rbp-A8h]
  int v36; // [rsp+5Ch] [rbp-A4h]
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  char v38[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v2 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  v4 = (__int64 (__fastcall *)(__int64, unsigned int, unsigned int, __int64))RasSetDeviceConfigInfo;
  dwBytes = 0;
  v29 = 0;
  if ( dword_1800C8654 )
    v2 = DdmGetDeviceConfigInfo;
  dwBytes_4 = 0;
  v32 = 0;
  if ( dword_1800C8654 )
    v4 = DdmSetDeviceConfigInfo;
  v37 = 0;
  memset_0(v38, 0, sizeof(v38));
  if ( (unsigned int)(a2 - 1) > 1 )
    return 87;
  v6 = DDMGetRestrictedPortCount(&v32);
  if ( !v6 )
  {
    v7 = v32;
    if ( v32 == -1 )
    {
      v7 = 0x4000;
      v8 = 30000;
    }
    else
    {
      v8 = v32;
    }
    v9 = (unsigned int *)*((_QWORD *)a1 + 1);
    if ( !v9 )
      return 87;
    if ( a2 != 1 )
    {
      if ( a2 != 2 )
      {
LABEL_34:
        dwBytes_4 = 6;
        v15 = v2(0, (int)&dwBytes_4, (int)&v29, (int)&dwBytes, 0);
        v6 = v15;
        if ( !v15 )
          return 4319;
        if ( v15 != 603 )
          return v6;
        v6 = 8;
        v16 = (char *)HeapAlloc(hHeap, 8u, dwBytes);
        v17 = v16;
        if ( !v16 )
          return v6;
        v6 = v2(0, (int)&dwBytes_4, (int)&v29, (int)&dwBytes, v16);
        if ( v6 || (v18 = v29, v19 = 0, !v29) )
        {
LABEL_52:
          HeapFree(hHeap, 0, v17);
          return v6;
        }
        while ( 1 )
        {
          v20 = 0;
          v21 = 0;
          v22 = 0;
          if ( a2 != 1 )
          {
            if ( a2 != 2 )
              goto LABEL_51;
            if ( *(_WORD *)&v17[472 * v19 + 48] == 14 )
            {
              v23 = *((_QWORD *)a1 + 1);
              v20 = 1;
              v21 = *(_DWORD *)(v23 + 16);
              v22 = *(_DWORD *)(v23 + 20);
            }
          }
          v24 = &v17[472 * v19];
          v25 = (unsigned __int16)*((_DWORD *)v24 + 12);
          if ( v25 == 8 )
          {
            v26 = (unsigned int *)*((_QWORD *)a1 + 1);
            v21 = *v26;
            v22 = v26[1];
LABEL_49:
            if ( v21 > *((_DWORD *)v24 + 11) )
              goto LABEL_52;
            *((_DWORD *)v24 + 7) = v21;
            *((_DWORD *)v24 + 1) = 1;
            *((_DWORD *)v24 + 3) = (v22 >> 1) & 1;
            *((_DWORD *)v24 + 2) = v22 & 1;
            v28 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))v4)(0, 1, 472);
            v18 = v29;
            v6 = v28;
            goto LABEL_51;
          }
          if ( v25 == 9 )
          {
            v27 = *((_QWORD *)a1 + 1);
            v21 = *(_DWORD *)(v27 + 8);
            v22 = *(_DWORD *)(v27 + 12);
            goto LABEL_49;
          }
          if ( v20 )
            goto LABEL_49;
LABEL_51:
          if ( ++v19 >= v18 )
            goto LABEL_52;
        }
      }
      v11 = *a1;
      if ( (unsigned int)*a1 < 0x18 )
      {
        if ( (byte_1800C8404 & 0x10) == 0 )
          return 87;
        LOWORD(v37) = 0;
        FormatRRASErrorString(
          &v37,
          L"DDMAdminServerSetInfo: Invalid buffer received with size %d. Erroring out...",
          v11,
          4294967292LL);
        if ( (byte_1800C8404 & 0x10) == 0 )
          return 87;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v38[2 * v13 - 4] );
LABEL_19:
        v36 = 0;
        v35 = 2 * v13 + 2;
        v34 = &v37;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
          v12,
          2u,
          &v33);
        return 87;
      }
      if ( v9[4] > v8 || (v9[5] & 0xFFFFFFFC) != 0 )
        return 87;
    }
    v14 = *a1;
    if ( (unsigned int)*a1 < 0x10 )
    {
      if ( (byte_1800C8404 & 0x10) == 0 )
        return 87;
      LOWORD(v37) = 0;
      FormatRRASErrorString(
        &v37,
        L"DDMAdminServerSetInfo: Invalid buffer received with size %d. Erroring out...",
        v14,
        4294967292LL);
      if ( (byte_1800C8404 & 0x10) == 0 )
        return 87;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v38[2 * v13 - 4] );
      goto LABEL_19;
    }
    if ( *v9 > v7 || v9[2] > v8 || (v9[1] & 0xFFFFFFFC) != 0 || (v9[3] & 0xFFFFFFFC) != 0 )
      return 87;
    goto LABEL_34;
  }
  return v6;
}

```

## disassembly

```asm
0x180005650  push    rbp
0x180005652  push    rbx
0x180005653  push    rsi
0x180005654  push    rdi
0x180005655  push    r12
0x180005657  push    r13
0x180005659  push    r14
0x18000565b  push    r15
0x18000565d  lea     rbp, [rsp-778h]
0x180005665  sub     rsp, 878h
0x18000566c  mov     rax, cs:__security_cookie
0x180005673  xor     rax, rsp
0x180005676  mov     [rbp+7B0h+var_50], rax
0x18000567d  mov     eax, cs:dword_1800C8654
0x180005683  xor     r13d, r13d
0x180005686  mov     rdi, cs:__imp_RasGetDeviceConfigInfo
0x18000568d  mov     r14, rcx
0x180005690  mov     r12, cs:__imp_RasSetDeviceConfigInfo
0x180005697  lea     rcx, DdmGetDeviceConfigInfo
0x18000569e  test    eax, eax
0x1800056a0  mov     dword ptr [rsp+8B0h+dwBytes], r13d
0x1800056a5  mov     r15d, edx
0x1800056a8  mov     [rsp+8B0h+var_880], r13d
0x1800056ad  cmovnz  rdi, rcx
0x1800056b1  mov     dword ptr [rsp+8B0h+dwBytes+4], r13d
0x1800056b6  lea     rcx, DdmSetDeviceConfigInfo
0x1800056bd  mov     [rsp+8B0h+var_874], r13d
0x1800056c2  cmovnz  r12, rcx
0x1800056c6  mov     [rsp+8B0h+var_850], r13d
0x1800056cb  xor     edx, edx; Val
0x1800056cd  lea     rcx, [rsp+8B0h+var_84C]; void *
0x1800056d2  mov     r8d, 7FCh; Size
0x1800056d8  call    memset_0
0x1800056dd  lea     eax, [r15-1]
0x1800056e1  cmp     eax, 1
0x1800056e4  ja      loc_1800057CD
0x1800056ea  lea     rcx, [rsp+8B0h+var_874]; unsigned int *
0x1800056ef  call    ?DDMGetRestrictedPortCount@@YAKPEAK@Z; DDMGetRestrictedPortCount(ulong *)
0x1800056f4  mov     ebx, eax
0x1800056f6  test    eax, eax
0x1800056f8  jnz     loc_1800057D2
0x1800056fe  mov     ecx, [rsp+8B0h+var_874]
0x180005702  cmp     ecx, 0FFFFFFFFh
0x180005705  jnz     short loc_180005714
0x180005707  mov     ecx, 4000h
0x18000570c  mov     r8d, 7530h
0x180005712  jmp     short loc_180005717
0x180005714  mov     r8d, ecx
0x180005717  mov     rax, [r14+8]
0x18000571b  test    rax, rax
0x18000571e  jnz     short loc_18000572A
0x180005720  mov     eax, 57h ; 'W'
0x180005725  jmp     loc_1800057D4
0x18000572a  mov     edx, r15d
0x18000572d  mov     r9d, 0FFFFFFFCh
0x180005733  sub     edx, 1
0x180005736  jz      loc_180005803
0x18000573c  cmp     edx, 1
0x18000573f  jnz     loc_180005875
0x180005745  mov     edx, [r14]
0x180005748  cmp     edx, 18h
0x18000574b  jnb     loc_1800057F7
0x180005751  test    cs:byte_1800C8404, 10h
0x180005758  jz      short loc_1800057CD
0x18000575a  mov     r8d, edx
0x18000575d  mov     word ptr [rsp+8B0h+var_850], r13w
0x180005763  lea     rdx, aDdmadminserver_24; "DDMAdminServerSetInfo: Invalid buffer r"...
0x18000576a  lea     rcx, [rsp+8B0h+var_850]
0x18000576f  call    FormatRRASErrorString
0x180005774  test    cs:byte_1800C8404, 10h
0x18000577b  jz      short loc_1800057CD
0x18000577d  lea     rcx, [rsp+8B0h+var_850]
0x180005782  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005786  inc     rax
0x180005789  cmp     [rcx+rax*2], r13w
0x18000578e  jnz     short loc_180005786
0x180005790  lea     eax, ds:2[rax*2]
0x180005797  mov     [rsp+8B0h+var_854], r13d
0x18000579c  lea     rcx, [rsp+8B0h+var_850]
0x1800057a1  mov     [rsp+8B0h+var_858], eax
0x1800057a5  lea     rax, [rsp+8B0h+var_870]
0x1800057aa  mov     [rsp+8B0h+var_860], rcx
0x1800057af  mov     r9d, 2
0x1800057b5  mov     [rsp+8B0h+var_890], rax
0x1800057ba  lea     rdx, RasDdmTraceInfo
0x1800057c1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800057c8  call    McGenEventWrite_EventWriteTransfer
0x1800057cd  mov     ebx, 57h ; 'W'
0x1800057d2  mov     eax, ebx
0x1800057d4  mov     rcx, [rbp+7B0h+var_50]
0x1800057db  xor     rcx, rsp; StackCookie
0x1800057de  call    __security_check_cookie
0x1800057e3  add     rsp, 878h
0x1800057ea  pop     r15
0x1800057ec  pop     r14
0x1800057ee  pop     r13
0x1800057f0  pop     r12
0x1800057f2  pop     rdi
0x1800057f3  pop     rsi
0x1800057f4  pop     rbx
0x1800057f5  pop     rbp
0x1800057f6  retn
0x1800057f7  cmp     [rax+10h], r8d
0x1800057fb  ja      short loc_1800057CD
0x1800057fd  test    [rax+14h], r9d
0x180005801  jnz     short loc_1800057CD
0x180005803  mov     edx, [r14]
0x180005806  cmp     edx, 10h
0x180005809  jnb     short loc_18000584F
0x18000580b  test    cs:byte_1800C8404, 10h
0x180005812  jz      short loc_1800057CD
0x180005814  mov     r8d, edx
0x180005817  mov     word ptr [rsp+8B0h+var_850], r13w
0x18000581d  lea     rdx, aDdmadminserver_24; "DDMAdminServerSetInfo: Invalid buffer r"...
0x180005824  lea     rcx, [rsp+8B0h+var_850]
0x180005829  call    FormatRRASErrorString
0x18000582e  test    cs:byte_1800C8404, 10h
0x180005835  jz      short loc_1800057CD
0x180005837  lea     rcx, [rsp+8B0h+var_850]
0x18000583c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005840  inc     rax
0x180005843  cmp     [rcx+rax*2], r13w
0x180005848  jnz     short loc_180005840
0x18000584a  jmp     loc_180005790
0x18000584f  cmp     [rax], ecx
0x180005851  ja      loc_1800057CD
0x180005857  cmp     [rax+8], r8d
0x18000585b  ja      loc_1800057CD
0x180005861  test    [rax+4], r9d
0x180005865  jnz     loc_1800057CD
0x18000586b  test    [rax+0Ch], r9d
0x18000586f  jnz     loc_1800057CD
0x180005875  lea     r9, [rsp+8B0h+dwBytes]
0x18000587a  mov     dword ptr [rsp+8B0h+dwBytes+4], 6
0x180005882  lea     r8, [rsp+8B0h+var_880]
0x180005887  mov     [rsp+8B0h+var_890], r13
0x18000588c  lea     rdx, [rsp+8B0h+dwBytes+4]
0x180005891  xor     ecx, ecx
0x180005893  mov     rax, rdi
0x180005896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589b  mov     ebx, eax
0x18000589d  test    eax, eax
0x18000589f  jnz     short loc_1800058AB
0x1800058a1  mov     ebx, 10DFh
0x1800058a6  jmp     loc_1800057D2
0x1800058ab  cmp     eax, 25Bh
0x1800058b0  jnz     loc_1800057D2
0x1800058b6  mov     r8d, dword ptr [rsp+8B0h+dwBytes]; dwBytes
0x1800058bb  mov     ebx, 8
0x1800058c0  mov     rcx, cs:hHeap; hHeap
0x1800058c7  mov     edx, ebx; dwFlags
0x1800058c9  call    cs:__imp_HeapAlloc
0x1800058cf  mov     rsi, rax
0x1800058d2  test    rax, rax
0x1800058d5  jz      loc_1800057D2
0x1800058db  mov     [rsp+8B0h+var_890], rax
0x1800058e0  lea     r9, [rsp+8B0h+dwBytes]
0x1800058e5  mov     rax, rdi
0x1800058e8  lea     r8, [rsp+8B0h+var_880]
0x1800058ed  lea     rdx, [rsp+8B0h+dwBytes+4]
0x1800058f2  xor     ecx, ecx
0x1800058f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f9  mov     ebx, eax
0x1800058fb  test    eax, eax
0x1800058fd  jnz     loc_1800059D2
0x180005903  mov     r10d, [rsp+8B0h+var_880]
0x180005908  mov     edi, r13d
0x18000590b  test    r10d, r10d
0x18000590e  jz      loc_1800059D2
0x180005914  mov     eax, r15d
0x180005917  mov     r11d, r13d
0x18000591a  mov     r8d, r13d
0x18000591d  mov     edx, r13d
0x180005920  sub     eax, 1
0x180005923  jz      short loc_180005950
0x180005925  cmp     eax, 1
0x180005928  jnz     loc_1800059C7
0x18000592e  mov     eax, edi
0x180005930  imul    rcx, rax, 1D8h
0x180005937  cmp     word ptr [rcx+rsi+30h], 0Eh
0x18000593d  jnz     short loc_180005950
0x18000593f  mov     rax, [r14+8]
0x180005943  mov     r11d, 1
0x180005949  mov     r8d, [rax+10h]
0x18000594d  mov     edx, [rax+14h]
0x180005950  mov     eax, edi
0x180005952  imul    r9, rax, 1D8h
0x180005959  add     r9, rsi
0x18000595c  mov     eax, [r9+30h]
0x180005960  movzx   eax, ax
0x180005963  cmp     eax, 8
0x180005966  jnz     short loc_180005974
0x180005968  mov     rax, [r14+8]
0x18000596c  mov     r8d, [rax]
0x18000596f  mov     edx, [rax+4]
0x180005972  jmp     short loc_18000598B
0x180005974  cmp     eax, 9
0x180005977  jnz     short loc_180005986
0x180005979  mov     rax, [r14+8]
0x18000597d  mov     r8d, [rax+8]
0x180005981  mov     edx, [rax+0Ch]
0x180005984  jmp     short loc_18000598B
0x180005986  test    r11d, r11d
0x180005989  jz      short loc_1800059C7
0x18000598b  cmp     r8d, [r9+2Ch]
0x18000598f  ja      short loc_1800059D2
0x180005991  mov     eax, edx
0x180005993  mov     [r9+1Ch], r8d
0x180005997  mov     ecx, 1
0x18000599c  shr     edx, 1
0x18000599e  and     edx, ecx
0x1800059a0  mov     [r9+4], ecx
0x1800059a4  and     eax, ecx
0x1800059a6  mov     [r9+0Ch], edx
0x1800059aa  mov     edx, ecx
0x1800059ac  mov     [r9+8], eax
0x1800059b0  xor     ecx, ecx
0x1800059b2  mov     r8d, 1D8h
0x1800059b8  mov     rax, r12
0x1800059bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c0  mov     r10d, [rsp+8B0h+var_880]
0x1800059c5  mov     ebx, eax
0x1800059c7  inc     edi
0x1800059c9  cmp     edi, r10d
0x1800059cc  jb      loc_180005914
0x1800059d2  mov     rcx, cs:hHeap; hHeap
0x1800059d9  mov     r8, rsi; lpMem
0x1800059dc  xor     edx, edx; dwFlags
0x1800059de  call    cs:__imp_HeapFree
0x1800059e4  jmp     loc_1800057D2
```
