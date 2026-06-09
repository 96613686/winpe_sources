# DDMAdminServerSetInfo

- ea: `0x1800057f0`
- end: `0x180005bae`
- name: `DDMAdminServerSetInfo`
- size: `958`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800057f0`
- `0x180007c0c`
- `0x180020e2c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005a77`
- `KERNEL32!HeapAlloc` at `0x180005a77`
- `KERNEL32!HeapFree` at `0x180005b9d`
- `KERNEL32!HeapFree` at `0x180005b9d`
- `rasman!RasGetDeviceConfigInfo` at `0x180005830`
- `rasman!RasSetDeviceConfigInfo` at `0x18000583a`

## pseudocode

```c
__int64 __fastcall DDMAdminServerSetInfo(unsigned int *a1, int a2)
{
  __int64 (__fastcall *v2)(int, int, int, int, void *); // rdi
  __int64 (__fastcall *v4)(__int64, unsigned int, unsigned int, __int64); // r12
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // r8d
  unsigned int *v9; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // r8
  unsigned int v15; // eax
  char *v16; // rax
  char *v17; // rsi
  unsigned int v18; // r10d
  int v19; // edi
  int v20; // r11d
  unsigned int v21; // r9d
  unsigned int v22; // edx
  __int64 v23; // r8
  unsigned int *v24; // r8
  int v25; // eax
  char *v26; // r8
  unsigned int v27; // eax
  unsigned int v28; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int dwBytes; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int dwBytes_4; // [rsp+40h] [rbp-C8h] BYREF
  int v31; // [rsp+44h] [rbp-C4h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+48h] [rbp-C0h] BYREF
  int *v33; // [rsp+58h] [rbp-B0h]
  int v34; // [rsp+60h] [rbp-A8h]
  int v35; // [rsp+64h] [rbp-A4h]
  int v36; // [rsp+68h] [rbp-A0h] BYREF
  char v37[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  v2 = (__int64 (__fastcall *)(int, int, int, int, void *))RasGetDeviceConfigInfo;
  v4 = (__int64 (__fastcall *)(__int64, unsigned int, unsigned int, __int64))RasSetDeviceConfigInfo;
  dwBytes = 0;
  v28 = 0;
  if ( dword_1800CF654 )
    v2 = DdmGetDeviceConfigInfo;
  dwBytes_4 = 0;
  v36 = 0;
  if ( dword_1800CF654 )
    v4 = DdmSetDeviceConfigInfo;
  memset_0(v37, 0, sizeof(v37));
  if ( (unsigned int)(a2 - 1) > 1 )
    return 87;
  v6 = DDMGetRestrictedPortCount(&dwBytes_4);
  if ( !v6 )
  {
    v7 = dwBytes_4;
    if ( dwBytes_4 == -1 )
    {
      v7 = 30000;
      v8 = 0x4000;
    }
    else
    {
      v8 = dwBytes_4;
    }
    v9 = (unsigned int *)*((_QWORD *)a1 + 1);
    if ( !v9 )
      return 87;
    if ( a2 != 1 )
    {
      if ( a2 != 2 )
      {
LABEL_34:
        v31 = 6;
        v15 = v2(0, (int)&v31, (int)&v28, (int)&dwBytes, 0);
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
        v6 = v2(0, (int)&v31, (int)&v28, (int)&dwBytes, v16);
        if ( v6 || (v18 = v28, v19 = 0, !v28) )
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
            v23 = *((_QWORD *)a1 + 1);
            if ( *(_WORD *)&v17[472 * v19 + 48] == 14 )
            {
              v21 = *(_DWORD *)(v23 + 16);
              v20 = 1;
              v22 = *(_DWORD *)(v23 + 20);
            }
          }
          v24 = (unsigned int *)*((_QWORD *)a1 + 1);
          v25 = (unsigned __int16)*(_DWORD *)&v17[472 * v19 + 48];
          if ( v25 == 8 )
          {
            v21 = *v24;
            v22 = v24[1];
LABEL_49:
            v26 = &v17[472 * v19];
            if ( v21 > *((_DWORD *)v26 + 11) )
              goto LABEL_52;
            *((_DWORD *)v26 + 7) = v21;
            *((_DWORD *)v26 + 1) = 1;
            *((_DWORD *)v26 + 3) = (v22 >> 1) & 1;
            *((_DWORD *)v26 + 2) = v22 & 1;
            v27 = v4(0, 1u, 472u, (__int64)&v17[472 * v19]);
            v18 = v28;
            v6 = v27;
            goto LABEL_51;
          }
          if ( v25 == 9 )
          {
            v21 = v24[2];
            v22 = v24[3];
            goto LABEL_49;
          }
          if ( v20 )
            goto LABEL_49;
LABEL_51:
          if ( ++v19 >= v18 )
            goto LABEL_52;
        }
      }
      if ( *a1 < 0x18 )
      {
        if ( (byte_1800CF404 & 0x10) == 0 )
          return 87;
        v11 = *a1;
        LOWORD(v36) = 0;
        FormatRRASErrorString(
          &v36,
          L"DDMAdminServerSetInfo: Invalid buffer received with size %d. Erroring out...",
          v11,
          4294967292LL);
        if ( (byte_1800CF404 & 0x10) == 0 )
          return 87;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v37[2 * v13 - 4] );
LABEL_19:
        v35 = 0;
        v34 = 2 * v13 + 2;
        v33 = &v36;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
          v12,
          2u,
          &v32);
        return 87;
      }
      if ( v9[4] > v7 || (v9[5] & 0xFFFFFFFC) != 0 )
        return 87;
    }
    if ( *a1 < 0x10 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        return 87;
      v14 = *a1;
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v36,
        L"DDMAdminServerSetInfo: Invalid buffer received with size %d. Erroring out...",
        v14,
        4294967292LL);
      if ( (byte_1800CF404 & 0x10) == 0 )
        return 87;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v37[2 * v13 - 4] );
      goto LABEL_19;
    }
    if ( *v9 > v8 || v9[2] > v7 || (v9[1] & 0xFFFFFFFC) != 0 || (v9[3] & 0xFFFFFFFC) != 0 )
      return 87;
    goto LABEL_34;
  }
  return v6;
}

```

## disassembly

```asm
0x1800057f0  mov     rax, rsp
0x1800057f3  mov     [rax+10h], rbx
0x1800057f7  mov     [rax+18h], rsi
0x1800057fb  mov     [rax+20h], rdi
0x1800057ff  push    rbp
0x180005800  push    r12
0x180005802  push    r13
0x180005804  push    r14
0x180005806  push    r15
0x180005808  lea     rbp, [rax-798h]
0x18000580f  sub     rsp, 870h
0x180005816  mov     rax, cs:__security_cookie
0x18000581d  xor     rax, rsp
0x180005820  mov     [rbp+790h+var_30], rax
0x180005827  mov     eax, cs:dword_1800CF654
0x18000582d  xor     r13d, r13d
0x180005830  mov     rdi, cs:__imp_RasGetDeviceConfigInfo
0x180005837  mov     r14, rcx
0x18000583a  mov     r12, cs:__imp_RasSetDeviceConfigInfo
0x180005841  lea     rcx, DdmGetDeviceConfigInfo
0x180005848  test    eax, eax
0x18000584a  mov     dword ptr [rsp+890h+dwBytes], r13d
0x18000584f  mov     r15d, edx
0x180005852  mov     [rsp+890h+var_860], r13d
0x180005857  cmovnz  rdi, rcx
0x18000585b  mov     dword ptr [rsp+890h+dwBytes+4], r13d
0x180005860  lea     rcx, DdmSetDeviceConfigInfo
0x180005867  mov     [rsp+890h+var_830], r13d
0x18000586c  cmovnz  r12, rcx
0x180005870  mov     r8d, 7FCh; Size
0x180005876  xor     edx, edx; Val
0x180005878  lea     rcx, [rsp+890h+var_82C]; void *
0x18000587d  call    memset_0
0x180005882  lea     eax, [r15-1]
0x180005886  cmp     eax, 1
0x180005889  ja      loc_180005970
0x18000588f  lea     rcx, [rsp+890h+dwBytes+4]; unsigned int *
0x180005894  call    ?DDMGetRestrictedPortCount@@YAKPEAK@Z; DDMGetRestrictedPortCount(ulong *)
0x180005899  mov     ebx, eax
0x18000589b  test    eax, eax
0x18000589d  jnz     loc_180005975
0x1800058a3  mov     ecx, dword ptr [rsp+890h+dwBytes+4]
0x1800058a7  cmp     ecx, 0FFFFFFFFh
0x1800058aa  jnz     short loc_1800058B9
0x1800058ac  mov     ecx, 7530h
0x1800058b1  mov     r8d, 4000h
0x1800058b7  jmp     short loc_1800058BC
0x1800058b9  mov     r8d, ecx
0x1800058bc  mov     rax, [r14+8]
0x1800058c0  test    rax, rax
0x1800058c3  jnz     short loc_1800058CF
0x1800058c5  mov     eax, 57h ; 'W'
0x1800058ca  jmp     loc_180005977
0x1800058cf  mov     edx, r15d
0x1800058d2  mov     r9d, 0FFFFFFFCh
0x1800058d8  sub     edx, 1
0x1800058db  jz      loc_1800059B3
0x1800058e1  cmp     edx, 1
0x1800058e4  jnz     loc_180005A23
0x1800058ea  cmp     dword ptr [r14], 18h
0x1800058ee  jnb     loc_1800059A8
0x1800058f4  test    cs:byte_1800CF404, 10h
0x1800058fb  jz      short loc_180005970
0x1800058fd  mov     r8d, [r14]
0x180005900  lea     rdx, aDdmadminserver_24; "DDMAdminServerSetInfo: Invalid buffer r"...
0x180005907  lea     rcx, [rsp+890h+var_830]
0x18000590c  mov     word ptr [rsp+890h+var_830], r13w
0x180005912  call    FormatRRASErrorString
0x180005917  test    cs:byte_1800CF404, 10h
0x18000591e  jz      short loc_180005970
0x180005920  lea     rcx, [rsp+890h+var_830]
0x180005925  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005929  inc     rax
0x18000592c  cmp     [rcx+rax*2], r13w
0x180005931  jnz     short loc_180005929
0x180005933  lea     eax, ds:2[rax*2]
0x18000593a  mov     [rsp+890h+var_834], r13d
0x18000593f  lea     rcx, [rsp+890h+var_830]
0x180005944  mov     [rsp+890h+var_838], eax
0x180005948  lea     rax, [rsp+890h+var_850]
0x18000594d  mov     [rsp+890h+var_840], rcx
0x180005952  mov     r9d, 2
0x180005958  mov     [rsp+890h+var_870], rax
0x18000595d  lea     rdx, RasDdmTraceInfo
0x180005964  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000596b  call    McGenEventWrite_EventWriteTransfer
0x180005970  mov     ebx, 57h ; 'W'
0x180005975  mov     eax, ebx
0x180005977  mov     rcx, [rbp+790h+var_30]
0x18000597e  xor     rcx, rsp; StackCookie
0x180005981  call    __security_check_cookie
0x180005986  lea     r11, [rsp+890h+var_20]
0x18000598e  mov     rbx, [r11+38h]
0x180005992  mov     rsi, [r11+40h]
0x180005996  mov     rdi, [r11+48h]
0x18000599a  mov     rsp, r11
0x18000599d  pop     r15
0x18000599f  pop     r14
0x1800059a1  pop     r13
0x1800059a3  pop     r12
0x1800059a5  pop     rbp
0x1800059a6  retn
0x1800059a8  cmp     [rax+10h], ecx
0x1800059ab  ja      short loc_180005970
0x1800059ad  test    [rax+14h], r9d
0x1800059b1  jnz     short loc_180005970
0x1800059b3  cmp     dword ptr [r14], 10h
0x1800059b7  jnb     short loc_1800059FD
0x1800059b9  test    cs:byte_1800CF404, 10h
0x1800059c0  jz      short loc_180005970
0x1800059c2  mov     r8d, [r14]
0x1800059c5  lea     rdx, aDdmadminserver_24; "DDMAdminServerSetInfo: Invalid buffer r"...
0x1800059cc  lea     rcx, [rsp+890h+var_830]
0x1800059d1  mov     word ptr [rsp+890h+var_830], r13w
0x1800059d7  call    FormatRRASErrorString
0x1800059dc  test    cs:byte_1800CF404, 10h
0x1800059e3  jz      short loc_180005970
0x1800059e5  lea     rcx, [rsp+890h+var_830]
0x1800059ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800059ee  inc     rax
0x1800059f1  cmp     [rcx+rax*2], r13w
0x1800059f6  jnz     short loc_1800059EE
0x1800059f8  jmp     loc_180005933
0x1800059fd  cmp     [rax], r8d
0x180005a00  ja      loc_180005970
0x180005a06  cmp     [rax+8], ecx
0x180005a09  ja      loc_180005970
0x180005a0f  test    [rax+4], r9d
0x180005a13  jnz     loc_180005970
0x180005a19  test    [rax+0Ch], r9d
0x180005a1d  jnz     loc_180005970
0x180005a23  lea     r9, [rsp+890h+dwBytes]
0x180005a28  mov     [rsp+890h+var_854], 6
0x180005a30  lea     r8, [rsp+890h+var_860]
0x180005a35  mov     [rsp+890h+var_870], r13
0x180005a3a  lea     rdx, [rsp+890h+var_854]
0x180005a3f  xor     ecx, ecx
0x180005a41  mov     rax, rdi
0x180005a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a49  mov     ebx, eax
0x180005a4b  test    eax, eax
0x180005a4d  jnz     short loc_180005A59
0x180005a4f  mov     ebx, 10DFh
0x180005a54  jmp     loc_180005975
0x180005a59  cmp     eax, 25Bh
0x180005a5e  jnz     loc_180005975
0x180005a64  mov     r8d, dword ptr [rsp+890h+dwBytes]; dwBytes
0x180005a69  mov     ebx, 8
0x180005a6e  mov     rcx, cs:hHeap; hHeap
0x180005a75  mov     edx, ebx; dwFlags
0x180005a77  call    cs:__imp_HeapAlloc
0x180005a7e  nop     dword ptr [rax+rax+00h]
0x180005a83  mov     rsi, rax
0x180005a86  test    rax, rax
0x180005a89  jz      loc_180005975
0x180005a8f  mov     [rsp+890h+var_870], rax
0x180005a94  lea     r9, [rsp+890h+dwBytes]
0x180005a99  mov     rax, rdi
0x180005a9c  lea     r8, [rsp+890h+var_860]
0x180005aa1  lea     rdx, [rsp+890h+var_854]
0x180005aa6  xor     ecx, ecx
0x180005aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aad  mov     ebx, eax
0x180005aaf  test    eax, eax
0x180005ab1  jnz     loc_180005B91
0x180005ab7  mov     r10d, [rsp+890h+var_860]
0x180005abc  mov     edi, r13d
0x180005abf  test    r10d, r10d
0x180005ac2  jz      loc_180005B91
0x180005ac8  mov     eax, r15d
0x180005acb  mov     r11d, r13d
0x180005ace  mov     r9d, r13d
0x180005ad1  mov     edx, r13d
0x180005ad4  sub     eax, 1
0x180005ad7  jz      short loc_180005B05
0x180005ad9  cmp     eax, 1
0x180005adc  jnz     loc_180005B86
0x180005ae2  mov     r8, [r14+8]
0x180005ae6  mov     eax, edi
0x180005ae8  imul    rcx, rax, 1D8h
0x180005aef  cmp     word ptr [rcx+rsi+30h], 0Eh
0x180005af5  jnz     short loc_180005B05
0x180005af7  mov     r9d, [r8+10h]
0x180005afb  mov     r11d, 1
0x180005b01  mov     edx, [r8+14h]
0x180005b05  mov     r8, [r14+8]
0x180005b09  mov     eax, edi
0x180005b0b  imul    rcx, rax, 1D8h
0x180005b12  mov     eax, [rcx+rsi+30h]
0x180005b16  movzx   eax, ax
0x180005b19  cmp     eax, 8
0x180005b1c  jnz     short loc_180005B27
0x180005b1e  mov     r9d, [r8]
0x180005b21  mov     edx, [r8+4]
0x180005b25  jmp     short loc_180005B3B
0x180005b27  cmp     eax, 9
0x180005b2a  jnz     short loc_180005B36
0x180005b2c  mov     r9d, [r8+8]
0x180005b30  mov     edx, [r8+0Ch]
0x180005b34  jmp     short loc_180005B3B
0x180005b36  test    r11d, r11d
0x180005b39  jz      short loc_180005B86
0x180005b3b  mov     eax, edi
0x180005b3d  imul    r8, rax, 1D8h
0x180005b44  add     r8, rsi
0x180005b47  cmp     r9d, [r8+2Ch]
0x180005b4b  ja      short loc_180005B91
0x180005b4d  mov     eax, edx
0x180005b4f  mov     [r8+1Ch], r9d
0x180005b53  mov     ecx, 1
0x180005b58  shr     edx, 1
0x180005b5a  and     edx, ecx
0x180005b5c  mov     [r8+4], ecx
0x180005b60  and     eax, ecx
0x180005b62  mov     [r8+0Ch], edx
0x180005b66  mov     [r8+8], eax
0x180005b6a  mov     edx, ecx
0x180005b6c  mov     r9, r8
0x180005b6f  xor     ecx, ecx
0x180005b71  mov     r8d, 1D8h
0x180005b77  mov     rax, r12
0x180005b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b7f  mov     r10d, [rsp+890h+var_860]
0x180005b84  mov     ebx, eax
0x180005b86  inc     edi
0x180005b88  cmp     edi, r10d
0x180005b8b  jb      loc_180005AC8
0x180005b91  mov     rcx, cs:hHeap; hHeap
0x180005b98  mov     r8, rsi; lpMem
0x180005b9b  xor     edx, edx; dwFlags
0x180005b9d  call    cs:__imp_HeapFree
0x180005ba4  nop     dword ptr [rax+rax+00h]
0x180005ba9  jmp     loc_180005975
```
