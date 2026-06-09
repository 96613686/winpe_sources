# InitializeNCPs

- ea: `0x180011b08`
- end: `0x180011e67`
- name: `InitializeNCPs`
- size: `863`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e86c`
- `0x180015320`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000cb10`
- `0x180011064`
- `0x180011b08`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180011d8b`: `FsmInit for IPv4 CP failed as the VPN server is not configured for IPv4`
- `0x180011cd3`: `FsmInit for IPv4 CP failed as the VPN server is not configured for IPv6`

## pseudocode

```c
__int64 __fastcall InitializeNCPs(__int64 a1, int a2)
{
  int v4; // eax
  int v6; // r15d
  unsigned int v7; // ebx
  unsigned int v8; // r10d
  unsigned int i; // edi
  unsigned int v10; // r9d
  __int64 PointerToCPCB; // rax
  _BYTE *v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rcx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // eax
  const wchar_t *v19; // r8
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // rax
  unsigned int v25; // r9d
  int v26; // r10d
  __int64 v27; // rsi
  _DWORD v28[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  char v30[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v4 = *(_DWORD *)(a1 + 56);
  if ( (v4 & 0x80u) != 0 )
    return 0;
  v6 = 0;
  v7 = 0;
  *(_DWORD *)(a1 + 56) = v4 | 0x80;
  v8 = 1;
  for ( i = 1; ; i += v8 )
  {
    v10 = PppConfigInfo;
    if ( i >= (unsigned int)PppConfigInfo )
      break;
    PointerToCPCB = GetPointerToCPCB(a1, i);
    v12 = CpTable;
    v13 = PointerToCPCB;
    *(_DWORD *)(PointerToCPCB + 44) = 0;
    v14 = 176LL * i;
    if ( (v12[v14 + 168] & 2) != 0 )
    {
      v15 = *(_DWORD *)&v12[v14] - 32801;
      if ( v15 )
      {
        v16 = v15 - 54;
        if ( v16 )
        {
          if ( v16 == 166 )
          {
            *(_DWORD *)(PointerToCPCB + 44) = v8;
            if ( !(unsigned int)FsmInit(a1, i) && (a2 & 0x1080) != 0 )
            {
              *(_DWORD *)(a1 + 56) |= 0x2000u;
              v7 = 741;
            }
            goto LABEL_16;
          }
        }
        else if ( (a2 & 0x8000000) != 0 )
        {
          v17 = *(_QWORD *)(a1 + 8);
          v18 = *(_DWORD *)(v17 + 1320);
          if ( v18 == -1 || *(_QWORD *)(v17 + 1336) != -1 )
          {
            if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && v18 != 2 )
            {
              v28[0] = 0;
              v7 = ((__int64 (__fastcall *)(__int64, _DWORD *))qword_18004CAA0)(v17 + 1968, v28);
              if ( v7 || (v28[0] & 8) == 0 )
              {
                if ( byte_18004CF33 < 0 )
                {
                  v19 = L"FsmInit for IPv4 CP failed as the VPN server is not configured for IPv6";
                  goto LABEL_26;
                }
                goto LABEL_27;
              }
              v8 = 1;
            }
            *(_DWORD *)(v13 + 44) = v8;
            if ( (unsigned int)FsmInit(a1, i) )
            {
              v8 = 1;
              v6 = 1;
            }
            else
            {
LABEL_16:
              v8 = 1;
            }
          }
        }
      }
      else if ( (a2 & 8) != 0 )
      {
        v20 = *(_QWORD *)(a1 + 8);
        v21 = *(_DWORD *)(v20 + 1320);
        if ( v21 == -1 || *(_QWORD *)(v20 + 1328) != -1 )
        {
          if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && v21 != 2 )
          {
            v28[0] = 0;
            v7 = ((__int64 (__fastcall *)(__int64, _DWORD *))qword_18004CAA0)(v20 + 1968, v28);
            if ( v7 || (v8 = 1, (v28[0] & 1) == 0) )
            {
              if ( byte_18004CF33 < 0 )
              {
                v19 = L"FsmInit for IPv4 CP failed as the VPN server is not configured for IPv4";
LABEL_26:
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, v19);
              }
LABEL_27:
              v7 = 0;
LABEL_9:
              v8 = 1;
              continue;
            }
          }
          *(_DWORD *)(v13 + 44) = v8;
          v22 = FsmInit(a1, i);
          v8 = 1;
          if ( v22 )
            v6 = 1;
        }
      }
      if ( v7 )
      {
        v10 = PppConfigInfo;
        break;
      }
      continue;
    }
    if ( ((unsigned __int8)v8 & (unsigned __int8)byte_18004CF34) != 0 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"Will not initialize CP %x", *(unsigned int *)&v12[v14]);
      v8 = 1;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v29);
        goto LABEL_9;
      }
    }
  }
  if ( !v6 || v7 )
  {
    v23 = v8;
    if ( !v7 )
      v7 = 720;
    if ( v10 > v8 )
    {
      do
      {
        v24 = GetPointerToCPCB(a1, v23);
        v27 = v24;
        if ( *(_DWORD *)(v24 + 48) == v26 )
        {
          if ( *(_QWORD *)(v24 + 16) )
          {
            (*((void (**)(void))CpTable + 22 * v23 + 5))();
            v26 = 1;
            *(_QWORD *)(v27 + 16) = 0;
          }
          *(_QWORD *)(v27 + 44) = 0;
          v25 = PppConfigInfo;
        }
        v23 += v26;
      }
      while ( v23 < v25 );
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180011b08  mov     [rsp-8+arg_8], rbx
0x180011b0d  mov     [rsp-8+arg_10], rsi
0x180011b12  push    rbp
0x180011b13  push    rdi
0x180011b14  push    r12
0x180011b16  push    r14
0x180011b18  push    r15
0x180011b1a  lea     rbp, [rsp-740h]
0x180011b22  sub     rsp, 840h
0x180011b29  mov     rax, cs:__security_cookie
0x180011b30  xor     rax, rsp
0x180011b33  mov     [rbp+760h+var_30], rax
0x180011b3a  mov     r12d, edx
0x180011b3d  mov     r14, rcx
0x180011b40  xor     eax, eax
0x180011b42  lea     rcx, [rsp+860h+var_82C]; void *
0x180011b47  xor     edx, edx; Val
0x180011b49  mov     [rsp+860h+var_830], eax
0x180011b4d  mov     r8d, 7FCh; Size
0x180011b53  call    memset_0
0x180011b58  mov     eax, [r14+38h]
0x180011b5c  test    al, al
0x180011b5e  jns     short loc_180011B67
0x180011b60  xor     eax, eax
0x180011b62  jmp     loc_180011E3C
0x180011b67  xor     r15d, r15d
0x180011b6a  xor     ebx, ebx
0x180011b6c  bts     eax, 7
0x180011b70  mov     [r14+38h], eax
0x180011b74  lea     r10d, [r15+1]
0x180011b78  mov     edi, r10d
0x180011b7b  mov     r9d, dword ptr cs:PppConfigInfo
0x180011b82  cmp     edi, r9d
0x180011b85  jnb     loc_180011DC4
0x180011b8b  mov     edx, edi
0x180011b8d  mov     rcx, r14
0x180011b90  call    GetPointerToCPCB
0x180011b95  mov     rdx, cs:CpTable
0x180011b9c  mov     rsi, rax
0x180011b9f  mov     dword ptr [rax+2Ch], 0
0x180011ba6  mov     eax, edi
0x180011ba8  imul    rcx, rax, 0B0h
0x180011baf  test    byte ptr [rcx+rdx+0A8h], 2
0x180011bb7  jnz     short loc_180011C18
0x180011bb9  test    cs:byte_18004CF34, r10b
0x180011bc0  jz      loc_180011DB5
0x180011bc6  xor     eax, eax
0x180011bc8  mov     word ptr [rsp+860h+var_830], ax
0x180011bcd  mov     r8d, [rcx+rdx]
0x180011bd1  lea     rdx, aWillNotInitial; "Will not initialize CP %x"
0x180011bd8  lea     rcx, [rsp+860h+var_830]
0x180011bdd  call    FormatRRASErrorString
0x180011be2  mov     r10d, 1
0x180011be8  test    cs:byte_18004CF34, r10b
0x180011bef  jz      loc_180011DB5
0x180011bf5  lea     r8, [rsp+860h+var_830]
0x180011bfa  lea     rdx, RasPppTraceInfo
0x180011c01  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011c08  call    McTemplateU0z_EventWriteTransfer
0x180011c0d  mov     r10d, 1
0x180011c13  jmp     loc_180011DB5
0x180011c18  mov     ecx, [rcx+rdx]
0x180011c1b  sub     ecx, 8021h
0x180011c21  jz      loc_180011D1E
0x180011c27  sub     ecx, 36h ; '6'
0x180011c2a  jz      short loc_180011C69
0x180011c2c  cmp     ecx, 0A6h
0x180011c32  jnz     loc_180011DB1
0x180011c38  mov     edx, edi
0x180011c3a  mov     [rsi+2Ch], r10d
0x180011c3e  mov     rcx, r14
0x180011c41  call    FsmInit
0x180011c46  test    eax, eax
0x180011c48  jnz     short loc_180011C5E
0x180011c4a  test    r12d, 1080h
0x180011c51  jz      short loc_180011C5E
0x180011c53  bts     dword ptr [r14+38h], 0Dh
0x180011c59  mov     ebx, 2E5h
0x180011c5e  mov     r10d, 1
0x180011c64  jmp     loc_180011DB1
0x180011c69  bt      r12d, 1Bh
0x180011c6e  jnb     loc_180011DB1
0x180011c74  mov     rcx, [r14+8]
0x180011c78  mov     eax, [rcx+528h]
0x180011c7e  cmp     eax, 0FFFFFFFFh
0x180011c81  jz      short loc_180011C91
0x180011c83  cmp     qword ptr [rcx+538h], 0FFFFFFFFFFFFFFFFh
0x180011c8b  jz      loc_180011DB1
0x180011c91  test    byte ptr [r14+38h], 4
0x180011c96  jz      short loc_180011CFA
0x180011c98  cmp     eax, 2
0x180011c9b  jz      short loc_180011CFA
0x180011c9d  mov     rax, cs:qword_18004CAA0
0x180011ca4  lea     rdx, [rsp+860h+var_840]
0x180011ca9  add     rcx, 7B0h
0x180011cb0  mov     [rsp+860h+var_840], 0
0x180011cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cbd  mov     ebx, eax
0x180011cbf  test    eax, eax
0x180011cc1  jnz     short loc_180011CCA
0x180011cc3  test    byte ptr [rsp+860h+var_840], 8
0x180011cc8  jnz     short loc_180011CF4
0x180011cca  test    cs:byte_18004CF33, 80h
0x180011cd1  jz      short loc_180011CED
0x180011cd3  lea     r8, aFsminitForIpv4_0; "FsmInit for IPv4 CP failed as the VPN s"...
0x180011cda  lea     rdx, RasPppTraceError
0x180011ce1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011ce8  call    McTemplateU0z_EventWriteTransfer
0x180011ced  xor     ebx, ebx
0x180011cef  jmp     loc_180011C0D
0x180011cf4  mov     r10d, 1
0x180011cfa  mov     edx, edi
0x180011cfc  mov     [rsi+2Ch], r10d
0x180011d00  mov     rcx, r14
0x180011d03  call    FsmInit
0x180011d08  test    eax, eax
0x180011d0a  jz      loc_180011C5E
0x180011d10  mov     r10d, 1
0x180011d16  mov     r15d, r10d
0x180011d19  jmp     loc_180011DB1
0x180011d1e  test    r12b, 8
0x180011d22  jz      loc_180011DB1
0x180011d28  mov     rcx, [r14+8]
0x180011d2c  mov     eax, [rcx+528h]
0x180011d32  cmp     eax, 0FFFFFFFFh
0x180011d35  jz      short loc_180011D41
0x180011d37  cmp     qword ptr [rcx+530h], 0FFFFFFFFFFFFFFFFh
0x180011d3f  jz      short loc_180011DB1
0x180011d41  test    byte ptr [r14+38h], 4
0x180011d46  jz      short loc_180011D97
0x180011d48  cmp     eax, 2
0x180011d4b  jz      short loc_180011D97
0x180011d4d  mov     rax, cs:qword_18004CAA0
0x180011d54  lea     rdx, [rsp+860h+var_840]
0x180011d59  add     rcx, 7B0h
0x180011d60  mov     [rsp+860h+var_840], 0
0x180011d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d6d  mov     ebx, eax
0x180011d6f  test    eax, eax
0x180011d71  jnz     short loc_180011D7E
0x180011d73  lea     r10d, [rax+1]
0x180011d77  test    byte ptr [rsp+860h+var_840], r10b
0x180011d7c  jnz     short loc_180011D97
0x180011d7e  test    cs:byte_18004CF33, 80h
0x180011d85  jz      loc_180011CED
0x180011d8b  lea     r8, aFsminitForIpv4; "FsmInit for IPv4 CP failed as the VPN s"...
0x180011d92  jmp     loc_180011CDA
0x180011d97  mov     edx, edi
0x180011d99  mov     [rsi+2Ch], r10d
0x180011d9d  mov     rcx, r14
0x180011da0  call    FsmInit
0x180011da5  test    eax, eax
0x180011da7  mov     r10d, 1
0x180011dad  cmovnz  r15d, r10d
0x180011db1  test    ebx, ebx
0x180011db3  jnz     short loc_180011DBD
0x180011db5  add     edi, r10d
0x180011db8  jmp     loc_180011B7B
0x180011dbd  mov     r9d, dword ptr cs:PppConfigInfo
0x180011dc4  test    r15d, r15d
0x180011dc7  jz      short loc_180011DCD
0x180011dc9  test    ebx, ebx
0x180011dcb  jz      short loc_180011E3A
0x180011dcd  test    ebx, ebx
0x180011dcf  mov     eax, 2D0h
0x180011dd4  mov     edi, r10d
0x180011dd7  cmovz   ebx, eax
0x180011dda  cmp     r9d, r10d
0x180011ddd  jbe     short loc_180011E3A
0x180011ddf  mov     edx, edi
0x180011de1  mov     rcx, r14
0x180011de4  call    GetPointerToCPCB
0x180011de9  mov     rsi, rax
0x180011dec  cmp     [rax+30h], r10d
0x180011df0  jnz     short loc_180011E32
0x180011df2  mov     rcx, [rax+10h]
0x180011df6  test    rcx, rcx
0x180011df9  jz      short loc_180011E23
0x180011dfb  mov     edx, edi
0x180011dfd  imul    r8, rdx, 0B0h
0x180011e04  mov     rdx, cs:CpTable
0x180011e0b  mov     rax, [r8+rdx+28h]
0x180011e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e15  mov     r10d, 1
0x180011e1b  mov     qword ptr [rsi+10h], 0
0x180011e23  mov     qword ptr [rsi+2Ch], 0
0x180011e2b  mov     r9d, dword ptr cs:PppConfigInfo
0x180011e32  add     edi, r10d
0x180011e35  cmp     edi, r9d
0x180011e38  jb      short loc_180011DDF
0x180011e3a  mov     eax, ebx
0x180011e3c  mov     rcx, [rbp+760h+var_30]
0x180011e43  xor     rcx, rsp; StackCookie
0x180011e46  call    __security_check_cookie
0x180011e4b  lea     r11, [rsp+860h+var_20]
0x180011e53  mov     rbx, [r11+38h]
0x180011e57  mov     rsi, [r11+40h]
0x180011e5b  mov     rsp, r11
0x180011e5e  pop     r15
0x180011e60  pop     r14
0x180011e62  pop     r12
0x180011e64  pop     rdi
0x180011e65  pop     rbp
0x180011e66  retn
```
