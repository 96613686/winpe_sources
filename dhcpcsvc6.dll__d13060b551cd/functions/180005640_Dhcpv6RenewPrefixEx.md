# Dhcpv6RenewPrefixEx

- ea: `0x180005640`
- end: `0x180005b23`
- name: `Dhcpv6RenewPrefixEx`
- size: `1251`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, __int64, int *, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180005580`

## callees

- `0x180001e70`
- `0x180001ff0`
- `0x180002650`
- `0x180003650`
- `0x180005640`
- `0x180006e44`
- `0x1800072fc`
- `0x180007891`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800058fd`
- `RPCRT4!NdrClientCall3` at `0x1800058fd`
- `RPCRT4!I_RpcExceptionFilter` at `0x180007a5e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180007a5e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005874`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005922`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005961`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005874`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005922`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005961`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057d4`

## pseudocode

```c
__int64 __fastcall Dhcpv6RenewPrefixEx(const WCHAR *a1, __int64 a2, __int64 a3, int *a4, unsigned int a5, int a6)
{
  unsigned __int16 v9; // si
  _QWORD *v10; // r12
  unsigned int Pointer; // ebx
  void *v12; // rax
  unsigned __int16 i; // r8
  __int64 v14; // rdx
  LPWSTR CommandLineW; // rax
  int v16; // ecx
  CLIENT_CALL_RETURN v17; // rax
  CLIENT_CALL_RETURN v18; // rcx
  LPWSTR v19; // rax
  int v20; // ecx
  int v21; // r8d
  __int64 v22; // rdi
  time_t v23; // rax
  time_t *v24; // rcx
  __int64 v25; // rdi
  time_t v26; // rax
  __int64 v27; // r8
  int v28; // ecx
  int v30; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v31; // [rsp+68h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+78h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+88h] [rbp-A0h]
  int v34; // [rsp+98h] [rbp-90h]
  NET_LUID v35; // [rsp+A0h] [rbp-88h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-80h] BYREF
  CLIENT_CALL_RETURN v37; // [rsp+B8h] [rbp-70h]
  __int64 v38; // [rsp+C0h] [rbp-68h]
  time_t *Time; // [rsp+C8h] [rbp-60h]
  _QWORD *v40; // [rsp+D0h] [rbp-58h]
  _QWORD *v41; // [rsp+D8h] [rbp-50h]
  _QWORD *v42; // [rsp+E0h] [rbp-48h]

  v9 = 0;
  v35.Value = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v36 = 0;
  v30 = -1;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 28, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 29, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
  }
  else if ( a1
         && a3
         && a4
         && a5 < 2
         && (v10 = (_QWORD *)(a3 + 8), *(_QWORD *)(a3 + 8))
         && *(_DWORD *)a3
         && *(_QWORD *)(a3 + 64)
         && *(_DWORD *)(a3 + 72) )
  {
    Pointer = Dhcpv6AdapterNameToIfId(a1, &v35);
    if ( !Pointer )
    {
      v12 = DhcpAlloc(*(unsigned int *)(a3 + 72));
      *((_QWORD *)&v36 + 1) = v12;
      if ( !v12 )
        goto LABEL_14;
      memcpy_0(v12, *(const void **)(a3 + 64), *(unsigned int *)(a3 + 72));
      LOWORD(v36) = *(_WORD *)(a3 + 72);
      LODWORD(v31) = *(_DWORD *)(a3 + 16);
      Time = (time_t *)(a3 + 24);
      DWORD1(v31) = *(_DWORD *)(a3 + 24);
      v40 = (_QWORD *)(a3 + 32);
      *((_QWORD *)&v31 + 1) = *(unsigned int *)(a3 + 32);
      v41 = (_QWORD *)(a3 + 40);
      LODWORD(v33) = *(_DWORD *)(a3 + 40);
      v42 = (_QWORD *)(a3 + 48);
      DWORD1(v33) = *(_DWORD *)(a3 + 48);
      LODWORD(v32) = *(_DWORD *)a3;
      *((_QWORD *)&v32 + 1) = LocalAlloc(0x40u, 32LL * (unsigned int)v32);
      if ( *((_QWORD *)&v32 + 1) )
      {
        v38 = a3 + 8;
        for ( i = 0; i < (unsigned int)v32; ++i )
        {
          v14 = 32LL * i;
          *(_DWORD *)(v14 + *((_QWORD *)&v32 + 1) + 16) = *(unsigned __int8 *)(v14 + *v10 + 16);
          *(_QWORD *)(v14 + *((_QWORD *)&v32 + 1) + 20) = *(_QWORD *)(v14 + *v10 + 20);
          *(_OWORD *)(v14 + *((_QWORD *)&v32 + 1)) = *(_OWORD *)(v14 + *v10);
        }
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(
            v16,
            30,
            (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
            (_DWORD)a1,
            (__int64)CommandLineW);
        }
        v37.Simple = 0;
        v17.Pointer = NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                        1u,
                        0,
                        0,
                        &v35,
                        a2,
                        &v31,
                        &v36,
                        &v30,
                        a5,
                        a6).Pointer;
        Pointer = (unsigned int)v17.Pointer;
        v37.Pointer = v17.Pointer;
        v34 = (int)v17.Pointer;
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          v19 = GetCommandLineW();
          WPP_SF_DSS(v20, 31, v21, Pointer, (__int64)a1, (__int64)v19);
        }
        if ( !Pointer )
        {
          if ( HIDWORD(v31) <= *(_DWORD *)a3 )
          {
            *a4 = v30;
            *(_DWORD *)(a3 + 56) = DWORD2(v33);
            v22 = DWORD1(v31);
            v23 = time((time_t *const)v18.Pointer);
            v24 = Time;
            *Time = v22 + v23;
            v25 = DWORD2(v31);
            v26 = time(v24);
            *v40 = v25 + v26;
            *v41 = (unsigned int)v33;
            *v42 = DWORD1(v33);
            if ( HIDWORD(v31) )
            {
              *(_DWORD *)a3 = HIDWORD(v31);
              do
              {
                if ( v9 >= (unsigned int)v32 )
                  break;
                v27 = 32LL * v9;
                *(_OWORD *)(v27 + *v10) = *(_OWORD *)(v27 + *((_QWORD *)&v32 + 1));
                *(_OWORD *)(v27 + *v10 + 16) = *(_OWORD *)(v27 + *((_QWORD *)&v32 + 1) + 16);
                ++v9;
              }
              while ( (unsigned int)v9 < HIDWORD(v31) );
            }
          }
          else
          {
            *(_DWORD *)a3 = HIDWORD(v31);
            Pointer = 234;
          }
        }
      }
      else
      {
LABEL_14:
        Pointer = 8;
      }
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree((void **)&v32 + 1);
  DhcpMidlUserFree((void **)&v36 + 1);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v28, 32, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180005640  mov     rax, rsp
0x180005643  mov     [rax+20h], r9
0x180005647  mov     [rax+18h], r8
0x18000564b  mov     [rax+10h], rdx
0x18000564f  mov     [rax+8], rcx
0x180005653  push    rbx
0x180005654  push    rsi
0x180005655  push    rdi
0x180005656  push    r12
0x180005658  push    r13
0x18000565a  push    r14
0x18000565c  push    r15
0x18000565e  sub     rsp, 0F0h
0x180005665  mov     rdi, r9
0x180005668  mov     r14, r8
0x18000566b  mov     r15, rcx
0x18000566e  xor     esi, esi
0x180005670  mov     [rax-88h], rsi
0x180005677  xorps   xmm0, xmm0
0x18000567a  movups  [rsp+128h+var_C0], xmm0
0x18000567f  movups  [rsp+128h+var_B0], xmm0
0x180005684  movups  xmmword ptr [rax-0A0h], xmm0
0x18000568b  movups  xmmword ptr [rax-80h], xmm0
0x18000568f  mov     [rsp+128h+var_C8], 0FFFFFFFFh
0x180005697  test    byte ptr cs:xmmword_18000F160, 10h
0x18000569e  jz      short loc_1800056B2
0x1800056a0  lea     edx, [rsi+1Ch]
0x1800056a3  mov     r9, rcx
0x1800056a6  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800056ad  call    WPP_SF_S
0x1800056b2  call    DhcpIsFSEGuestSystem
0x1800056b7  test    eax, eax
0x1800056b9  jnz     loc_180005AAC
0x1800056bf  test    r15, r15
0x1800056c2  jz      loc_180005AA5
0x1800056c8  test    r14, r14
0x1800056cb  jz      loc_180005AA5
0x1800056d1  test    rdi, rdi
0x1800056d4  jz      loc_180005AA5
0x1800056da  cmp     [rsp+128h+arg_20], 2
0x1800056e2  jnb     loc_180005AA5
0x1800056e8  lea     r12, [r14+8]
0x1800056ec  cmp     [r12], rsi
0x1800056f0  jz      loc_180005AA5
0x1800056f6  cmp     [r14], esi
0x1800056f9  jz      loc_180005AA5
0x1800056ff  cmp     [r14+40h], rsi
0x180005703  jz      loc_180005AA5
0x180005709  cmp     [r14+48h], esi
0x18000570d  jz      loc_180005AA5
0x180005713  lea     rdx, [rsp+128h+var_88]
0x18000571b  mov     rcx, r15
0x18000571e  call    Dhcpv6AdapterNameToIfId
0x180005723  mov     ebx, eax
0x180005725  test    eax, eax
0x180005727  jnz     loc_180005AD3
0x18000572d  mov     ecx, [r14+48h]
0x180005731  call    DhcpAlloc
0x180005736  mov     [rsp+128h+var_78], rax
0x18000573e  test    rax, rax
0x180005741  jnz     short loc_18000574D
0x180005743  mov     ebx, 8
0x180005748  jmp     loc_180005AD3
0x18000574d  mov     r8d, [r14+48h]; Size
0x180005751  mov     rdx, [r14+40h]; Src
0x180005755  mov     rcx, rax; void *
0x180005758  call    memcpy_0
0x18000575d  movzx   eax, word ptr [r14+48h]
0x180005762  mov     [rsp+128h+var_80], ax
0x18000576a  mov     eax, [r14+10h]
0x18000576e  mov     dword ptr [rsp+128h+var_C0], eax
0x180005772  lea     rax, [r14+18h]
0x180005776  mov     [rsp+128h+Time], rax
0x18000577e  mov     eax, [rax]
0x180005780  mov     dword ptr [rsp+128h+var_C0+4], eax
0x180005784  lea     rax, [r14+20h]
0x180005788  mov     [rsp+128h+var_58], rax
0x180005790  mov     eax, [rax]
0x180005792  mov     dword ptr [rsp+128h+var_C0+8], eax
0x180005796  lea     rax, [r14+28h]
0x18000579a  mov     [rsp+128h+var_50], rax
0x1800057a2  mov     eax, [rax]
0x1800057a4  mov     [rsp+128h+var_A0], eax
0x1800057ab  lea     rax, [r14+30h]
0x1800057af  mov     [rsp+128h+var_48], rax
0x1800057b7  mov     eax, [rax]
0x1800057b9  mov     [rsp+128h+var_9C], eax
0x1800057c0  mov     dword ptr [rsp+128h+var_C0+0Ch], esi
0x1800057c4  mov     edx, [r14]
0x1800057c7  mov     dword ptr [rsp+128h+var_B0], edx
0x1800057cb  shl     rdx, 5; uBytes
0x1800057cf  mov     ecx, 40h ; '@'; uFlags
0x1800057d4  call    cs:__imp_LocalAlloc
0x1800057da  mov     qword ptr [rsp+128h+var_B0+8], rax
0x1800057e2  test    rax, rax
0x1800057e5  jz      loc_180005743
0x1800057eb  mov     [rsp+128h+var_68], r12
0x1800057f3  movzx   r8d, si
0x1800057f7  mov     r13d, 1
0x1800057fd  cmp     dword ptr [rsp+128h+var_B0], esi
0x180005801  jbe     short loc_18000586B
0x180005803  movzx   edx, r8w
0x180005807  shl     rdx, 5
0x18000580b  mov     rax, [r12]
0x18000580f  movzx   ecx, byte ptr [rdx+rax+10h]
0x180005814  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x18000581c  mov     [rdx+rax+10h], ecx
0x180005820  mov     rax, [r12]
0x180005824  mov     ecx, [rdx+rax+14h]
0x180005828  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005830  mov     [rdx+rax+14h], ecx
0x180005834  mov     rax, [r12]
0x180005838  mov     ecx, [rdx+rax+18h]
0x18000583c  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005844  mov     [rdx+rax+18h], ecx
0x180005848  mov     rax, [r12]
0x18000584c  movups  xmm0, xmmword ptr [rdx+rax]
0x180005850  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005858  movdqu  xmmword ptr [rdx+rax], xmm0
0x18000585d  add     r8w, r13w
0x180005861  movzx   eax, r8w
0x180005865  cmp     eax, dword ptr [rsp+128h+var_B0]
0x180005869  jb      short loc_180005803
0x18000586b  test    byte ptr cs:xmmword_18000F160, 10h
0x180005872  jz      short loc_180005894
0x180005874  call    cs:__imp_GetCommandLineW
0x18000587a  mov     edx, 1Eh
0x18000587f  mov     [rsp+128h+var_108], rax
0x180005884  mov     r9, r15
0x180005887  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000588e  call    WPP_SF_SS
0x180005893  nop
0x180005894  mov     [rsp+128h+var_70], rsi
0x18000589c  mov     eax, [rsp+128h+arg_28]
0x1800058a3  mov     [rsp+128h+var_D8], eax
0x1800058a7  mov     eax, [rsp+128h+arg_20]
0x1800058ae  mov     [rsp+128h+var_E0], eax
0x1800058b2  lea     rax, [rsp+128h+var_C8]
0x1800058b7  mov     [rsp+128h+var_E8], rax
0x1800058bc  lea     rax, [rsp+128h+var_80]
0x1800058c4  mov     [rsp+128h+var_F0], rax
0x1800058c9  lea     rax, [rsp+128h+var_C0]
0x1800058ce  mov     [rsp+128h+var_F8], rax
0x1800058d3  mov     rax, [rsp+128h+arg_8]
0x1800058db  mov     [rsp+128h+var_100], rax
0x1800058e0  lea     rax, [rsp+128h+var_88]
0x1800058e8  mov     [rsp+128h+var_108], rax
0x1800058ed  xor     r9d, r9d
0x1800058f0  xor     r8d, r8d; pReturnValue
0x1800058f3  mov     edx, r13d; nProcNum
0x1800058f6  lea     rcx, pProxyInfo; pProxyInfo
0x1800058fd  call    cs:__imp_NdrClientCall3
0x180005903  mov     rbx, rax
0x180005906  mov     [rsp+128h+var_70], rax
0x18000590e  mov     [rsp+128h+var_90], eax
0x180005915  jmp     short loc_180005958
0x180005917  mov     edi, eax
0x180005919  mov     ebx, eax
0x18000591b  mov     [rsp+128h+var_90], eax
0x180005922  call    cs:__imp_GetCommandLineW
0x180005928  mov     rdx, rax
0x18000592b  mov     ecx, ebx
0x18000592d  call    TraceRpcException
0x180005932  xor     esi, esi
0x180005934  lea     r13d, [rsi+1]
0x180005938  mov     rdi, [rsp+128h+arg_18]
0x180005940  mov     r14, [rsp+128h+arg_10]
0x180005948  mov     r15, [rsp+128h+arg_0]
0x180005950  mov     r12, [rsp+128h+var_68]
0x180005958  test    byte ptr cs:xmmword_18000F160, 10h
0x18000595f  jz      short loc_18000597E
0x180005961  call    cs:__imp_GetCommandLineW
0x180005967  mov     edx, 1Fh
0x18000596c  mov     [rsp+128h+var_100], rax
0x180005971  mov     [rsp+128h+var_108], r15
0x180005976  mov     r9d, ebx
0x180005979  call    WPP_SF_DSS
0x18000597e  test    ebx, ebx
0x180005980  jnz     loc_180005AD3
0x180005986  mov     eax, dword ptr [rsp+128h+var_C0+0Ch]
0x18000598a  cmp     eax, [r14]
0x18000598d  jbe     short loc_18000599C
0x18000598f  mov     [r14], eax
0x180005992  mov     ebx, 0EAh
0x180005997  jmp     loc_180005AD3
0x18000599c  mov     eax, [rsp+128h+var_C8]
0x1800059a0  mov     [rdi], eax
0x1800059a2  mov     eax, [rsp+128h+var_98]
0x1800059a9  mov     [r14+38h], eax
0x1800059ad  mov     edi, dword ptr [rsp+128h+var_C0+4]
0x1800059b1  call    time
0x1800059b6  add     rax, rdi
0x1800059b9  mov     rcx, [rsp+128h+Time]; Time
0x1800059c1  mov     [rcx], rax
0x1800059c4  mov     edi, dword ptr [rsp+128h+var_C0+8]
0x1800059c8  call    time
0x1800059cd  add     rax, rdi
0x1800059d0  mov     rcx, [rsp+128h+var_58]
0x1800059d8  mov     [rcx], rax
0x1800059db  mov     eax, [rsp+128h+var_A0]
0x1800059e2  mov     rcx, [rsp+128h+var_50]
0x1800059ea  mov     [rcx], rax
0x1800059ed  mov     eax, [rsp+128h+var_9C]
0x1800059f4  mov     rcx, [rsp+128h+var_48]
0x1800059fc  mov     [rcx], rax
0x1800059ff  mov     eax, dword ptr [rsp+128h+var_C0+0Ch]
0x180005a03  test    eax, eax
0x180005a05  jz      loc_180005AD3
0x180005a0b  mov     [r14], eax
0x180005a0e  movzx   eax, si
0x180005a11  cmp     eax, dword ptr [rsp+128h+var_B0]
0x180005a15  jnb     loc_180005AD3
0x180005a1b  movzx   r8d, si
0x180005a1f  shl     r8, 5
0x180005a23  mov     rcx, [r12]
0x180005a27  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005a2f  movups  xmm0, xmmword ptr [r8+rax]
0x180005a34  movdqu  xmmword ptr [r8+rcx], xmm0
0x180005a3a  mov     rdx, [r12]
0x180005a3e  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005a46  mov     ecx, [r8+rax+14h]
0x180005a4b  mov     [r8+rdx+14h], ecx
0x180005a50  mov     rdx, [r12]
0x180005a54  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005a5c  mov     ecx, [r8+rax+10h]
0x180005a61  mov     [r8+rdx+10h], ecx
0x180005a66  mov     rdx, [r12]
0x180005a6a  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005a72  mov     ecx, [r8+rax+18h]
0x180005a77  mov     [r8+rdx+18h], ecx
0x180005a7c  mov     rdx, [r12]
0x180005a80  mov     rax, qword ptr [rsp+128h+var_B0+8]
0x180005a88  mov     ecx, [r8+rax+1Ch]
0x180005a8d  mov     [r8+rdx+1Ch], ecx
0x180005a92  add     si, r13w
0x180005a96  movzx   eax, si
0x180005a99  cmp     eax, dword ptr [rsp+128h+var_C0+0Ch]
0x180005a9d  jb      loc_180005A0E
0x180005aa3  jmp     short loc_180005AD3
0x180005aa5  mov     ebx, 57h ; 'W'
0x180005aaa  jmp     short loc_180005AD3
0x180005aac  mov     r9d, 32h ; '2'
0x180005ab2  mov     ebx, r9d
0x180005ab5  test    byte ptr cs:xmmword_18000F160, 2
0x180005abc  jz      short loc_180005AD3
0x180005abe  lea     edx, [r9-15h]
0x180005ac2  mov     ecx, 401h
0x180005ac7  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005ace  call    WPP_SF_D
0x180005ad3  lea     rcx, [rsp+128h+var_B0+8]
0x180005adb  call    DhcpMidlUserFree
0x180005ae0  lea     rcx, [rsp+128h+var_78]
0x180005ae8  call    DhcpMidlUserFree
0x180005aed  test    byte ptr cs:xmmword_18000F160, 10h
0x180005af4  jz      short loc_180005B0E
0x180005af6  mov     edx, 20h ; ' '
0x180005afb  mov     dword ptr [rsp+128h+var_108], ebx
0x180005aff  mov     r9, r15
0x180005b02  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005b09  call    WPP_SF_SD
0x180005b0e  mov     eax, ebx
0x180005b10  add     rsp, 0F0h
0x180005b17  pop     r15
0x180005b19  pop     r14
0x180005b1b  pop     r13
0x180005b1d  pop     r12
0x180005b1f  pop     rdi
0x180005b20  pop     rsi
0x180005b21  pop     rbx
0x180005b22  retn
0x180007a50  push    rbp
0x180007a52  sub     rsp, 60h
0x180007a56  mov     rbp, rdx
0x180007a59  mov     rcx, [rcx]
0x180007a5c  mov     ecx, [rcx]; ExceptionCode
0x180007a5e  call    cs:__imp_I_RpcExceptionFilter
0x180007a64  nop
0x180007a65  add     rsp, 60h
0x180007a69  pop     rbp
0x180007a6a  retn
```
