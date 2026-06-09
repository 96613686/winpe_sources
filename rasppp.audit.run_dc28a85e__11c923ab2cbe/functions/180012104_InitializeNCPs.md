# InitializeNCPs

- ea: `0x180012104`
- end: `0x180012464`
- name: `InitializeNCPs`
- size: `864`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ecac`
- `0x180015a80`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000cf3c`
- `0x1800115d0`
- `0x180012104`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180012387`: `FsmInit for IPv4 CP failed as the VPN server is not configured for IPv4`
- `0x1800122cf`: `FsmInit for IPv4 CP failed as the VPN server is not configured for IPv6`

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
              v7 = ((__int64 (__fastcall *)(__int64, _DWORD *))qword_18004DAA0)(v17 + 1968, v28);
              if ( v7 || (v28[0] & 8) == 0 )
              {
                if ( byte_18004DF33 < 0 )
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
            v7 = ((__int64 (__fastcall *)(__int64, _DWORD *))qword_18004DAA0)(v20 + 1968, v28);
            if ( v7 || (v8 = 1, (v28[0] & 1) == 0) )
            {
              if ( byte_18004DF33 < 0 )
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
    if ( ((unsigned __int8)v8 & (unsigned __int8)byte_18004DF34) != 0 )
    {
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, L"Will not initialize CP %x", *(unsigned int *)&v12[v14]);
      v8 = 1;
      if ( (byte_18004DF34 & 1) != 0 )
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
0x180012104  mov     [rsp-8+arg_8], rbx
0x180012109  mov     [rsp-8+arg_10], rsi
0x18001210e  push    rbp
0x18001210f  push    rdi
0x180012110  push    r12
0x180012112  push    r14
0x180012114  push    r15
0x180012116  lea     rbp, [rsp-740h]
0x18001211e  sub     rsp, 840h
0x180012125  mov     rax, cs:__security_cookie
0x18001212c  xor     rax, rsp
0x18001212f  mov     [rbp+760h+var_30], rax
0x180012136  mov     r12d, edx
0x180012139  mov     r14, rcx
0x18001213c  xor     eax, eax
0x18001213e  lea     rcx, [rsp+860h+var_82C]; void *
0x180012143  xor     edx, edx; Val
0x180012145  mov     [rsp+860h+var_830], eax
0x180012149  mov     r8d, 7FCh; Size
0x18001214f  call    memset_0
0x180012154  mov     eax, [r14+38h]
0x180012158  test    al, al
0x18001215a  jns     short loc_180012163
0x18001215c  xor     eax, eax
0x18001215e  jmp     loc_180012438
0x180012163  xor     r15d, r15d
0x180012166  xor     ebx, ebx
0x180012168  bts     eax, 7
0x18001216c  mov     [r14+38h], eax
0x180012170  lea     r10d, [r15+1]
0x180012174  mov     edi, r10d
0x180012177  mov     r9d, dword ptr cs:PppConfigInfo
0x18001217e  cmp     edi, r9d
0x180012181  jnb     loc_1800123C0
0x180012187  mov     edx, edi
0x180012189  mov     rcx, r14
0x18001218c  call    GetPointerToCPCB
0x180012191  mov     rdx, cs:CpTable
0x180012198  mov     rsi, rax
0x18001219b  mov     dword ptr [rax+2Ch], 0
0x1800121a2  mov     eax, edi
0x1800121a4  imul    rcx, rax, 0B0h
0x1800121ab  test    byte ptr [rcx+rdx+0A8h], 2
0x1800121b3  jnz     short loc_180012214
0x1800121b5  test    cs:byte_18004DF34, r10b
0x1800121bc  jz      loc_1800123B1
0x1800121c2  xor     eax, eax
0x1800121c4  mov     word ptr [rsp+860h+var_830], ax
0x1800121c9  mov     r8d, [rcx+rdx]
0x1800121cd  lea     rdx, aWillNotInitial; "Will not initialize CP %x"
0x1800121d4  lea     rcx, [rsp+860h+var_830]
0x1800121d9  call    FormatRRASErrorString
0x1800121de  mov     r10d, 1
0x1800121e4  test    cs:byte_18004DF34, r10b
0x1800121eb  jz      loc_1800123B1
0x1800121f1  lea     r8, [rsp+860h+var_830]
0x1800121f6  lea     rdx, RasPppTraceInfo
0x1800121fd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012204  call    McTemplateU0z_EventWriteTransfer
0x180012209  mov     r10d, 1
0x18001220f  jmp     loc_1800123B1
0x180012214  mov     ecx, [rcx+rdx]
0x180012217  sub     ecx, 8021h
0x18001221d  jz      loc_18001231A
0x180012223  sub     ecx, 36h ; '6'
0x180012226  jz      short loc_180012265
0x180012228  cmp     ecx, 0A6h
0x18001222e  jnz     loc_1800123AD
0x180012234  mov     edx, edi
0x180012236  mov     [rsi+2Ch], r10d
0x18001223a  mov     rcx, r14
0x18001223d  call    FsmInit
0x180012242  test    eax, eax
0x180012244  jnz     short loc_18001225A
0x180012246  test    r12d, 1080h
0x18001224d  jz      short loc_18001225A
0x18001224f  bts     dword ptr [r14+38h], 0Dh
0x180012255  mov     ebx, 2E5h
0x18001225a  mov     r10d, 1
0x180012260  jmp     loc_1800123AD
0x180012265  bt      r12d, 1Bh
0x18001226a  jnb     loc_1800123AD
0x180012270  mov     rcx, [r14+8]
0x180012274  mov     eax, [rcx+528h]
0x18001227a  cmp     eax, 0FFFFFFFFh
0x18001227d  jz      short loc_18001228D
0x18001227f  cmp     qword ptr [rcx+538h], 0FFFFFFFFFFFFFFFFh
0x180012287  jz      loc_1800123AD
0x18001228d  test    byte ptr [r14+38h], 4
0x180012292  jz      short loc_1800122F6
0x180012294  cmp     eax, 2
0x180012297  jz      short loc_1800122F6
0x180012299  mov     rax, cs:qword_18004DAA0
0x1800122a0  lea     rdx, [rsp+860h+var_840]
0x1800122a5  add     rcx, 7B0h
0x1800122ac  mov     [rsp+860h+var_840], 0
0x1800122b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b9  mov     ebx, eax
0x1800122bb  test    eax, eax
0x1800122bd  jnz     short loc_1800122C6
0x1800122bf  test    byte ptr [rsp+860h+var_840], 8
0x1800122c4  jnz     short loc_1800122F0
0x1800122c6  test    cs:byte_18004DF33, 80h
0x1800122cd  jz      short loc_1800122E9
0x1800122cf  lea     r8, aFsminitForIpv4_0; "FsmInit for IPv4 CP failed as the VPN s"...
0x1800122d6  lea     rdx, RasPppTraceError
0x1800122dd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800122e4  call    McTemplateU0z_EventWriteTransfer
0x1800122e9  xor     ebx, ebx
0x1800122eb  jmp     loc_180012209
0x1800122f0  mov     r10d, 1
0x1800122f6  mov     edx, edi
0x1800122f8  mov     [rsi+2Ch], r10d
0x1800122fc  mov     rcx, r14
0x1800122ff  call    FsmInit
0x180012304  test    eax, eax
0x180012306  jz      loc_18001225A
0x18001230c  mov     r10d, 1
0x180012312  mov     r15d, r10d
0x180012315  jmp     loc_1800123AD
0x18001231a  test    r12b, 8
0x18001231e  jz      loc_1800123AD
0x180012324  mov     rcx, [r14+8]
0x180012328  mov     eax, [rcx+528h]
0x18001232e  cmp     eax, 0FFFFFFFFh
0x180012331  jz      short loc_18001233D
0x180012333  cmp     qword ptr [rcx+530h], 0FFFFFFFFFFFFFFFFh
0x18001233b  jz      short loc_1800123AD
0x18001233d  test    byte ptr [r14+38h], 4
0x180012342  jz      short loc_180012393
0x180012344  cmp     eax, 2
0x180012347  jz      short loc_180012393
0x180012349  mov     rax, cs:qword_18004DAA0
0x180012350  lea     rdx, [rsp+860h+var_840]
0x180012355  add     rcx, 7B0h
0x18001235c  mov     [rsp+860h+var_840], 0
0x180012364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012369  mov     ebx, eax
0x18001236b  test    eax, eax
0x18001236d  jnz     short loc_18001237A
0x18001236f  lea     r10d, [rax+1]
0x180012373  test    byte ptr [rsp+860h+var_840], r10b
0x180012378  jnz     short loc_180012393
0x18001237a  test    cs:byte_18004DF33, 80h
0x180012381  jz      loc_1800122E9
0x180012387  lea     r8, aFsminitForIpv4; "FsmInit for IPv4 CP failed as the VPN s"...
0x18001238e  jmp     loc_1800122D6
0x180012393  mov     edx, edi
0x180012395  mov     [rsi+2Ch], r10d
0x180012399  mov     rcx, r14
0x18001239c  call    FsmInit
0x1800123a1  test    eax, eax
0x1800123a3  mov     r10d, 1
0x1800123a9  cmovnz  r15d, r10d
0x1800123ad  test    ebx, ebx
0x1800123af  jnz     short loc_1800123B9
0x1800123b1  add     edi, r10d
0x1800123b4  jmp     loc_180012177
0x1800123b9  mov     r9d, dword ptr cs:PppConfigInfo
0x1800123c0  test    r15d, r15d
0x1800123c3  jz      short loc_1800123C9
0x1800123c5  test    ebx, ebx
0x1800123c7  jz      short loc_180012436
0x1800123c9  test    ebx, ebx
0x1800123cb  mov     eax, 2D0h
0x1800123d0  mov     edi, r10d
0x1800123d3  cmovz   ebx, eax
0x1800123d6  cmp     r9d, r10d
0x1800123d9  jbe     short loc_180012436
0x1800123db  mov     edx, edi
0x1800123dd  mov     rcx, r14
0x1800123e0  call    GetPointerToCPCB
0x1800123e5  mov     rsi, rax
0x1800123e8  cmp     [rax+30h], r10d
0x1800123ec  jnz     short loc_18001242E
0x1800123ee  mov     rcx, [rax+10h]
0x1800123f2  test    rcx, rcx
0x1800123f5  jz      short loc_18001241F
0x1800123f7  mov     edx, edi
0x1800123f9  imul    r8, rdx, 0B0h
0x180012400  mov     rdx, cs:CpTable
0x180012407  mov     rax, [r8+rdx+28h]
0x18001240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012411  mov     r10d, 1
0x180012417  mov     qword ptr [rsi+10h], 0
0x18001241f  mov     qword ptr [rsi+2Ch], 0
0x180012427  mov     r9d, dword ptr cs:PppConfigInfo
0x18001242e  add     edi, r10d
0x180012431  cmp     edi, r9d
0x180012434  jb      short loc_1800123DB
0x180012436  mov     eax, ebx
0x180012438  mov     rcx, [rbp+760h+var_30]
0x18001243f  xor     rcx, rsp; StackCookie
0x180012442  call    __security_check_cookie
0x180012447  lea     r11, [rsp+860h+var_20]
0x18001244f  mov     rbx, [r11+38h]
0x180012453  mov     rsi, [r11+40h]
0x180012457  mov     rsp, r11
0x18001245a  pop     r15
0x18001245c  pop     r14
0x18001245e  pop     r12
0x180012460  pop     rdi
0x180012461  pop     rbp
0x180012462  retn
```
