# DhcpLeaseIpAddressEx

- ea: `0x180007dd0`
- end: `0x180008204`
- name: `DhcpLeaseIpAddressEx`
- size: `1076`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, void *Source, rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180007d90`

## callees

- `0x180002760`
- `0x1800048c0`
- `0x180005162`
- `0x180005678`
- `0x180007dd0`
- `0x18000d5c8`
- `0x18000f4ec`
- `0x180010154`
- `0x1800110f8`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007f34`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008071`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000809c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007f34`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008071`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000809c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800080c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800080c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008183`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180008183`

## pseudocode

```c
__int64 __fastcall DhcpLeaseIpAddressEx(
        int a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        void *Source,
        rsize_t SourceSize)
{
  unsigned int v11; // ebx
  const void *v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  LPWSTR CommandLineW; // rax
  _OWORD *v17; // rcx
  int *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  int *v21; // rcx
  int *v22; // rax
  LPWSTR v23; // rax
  int v24; // ecx
  int v25; // r8d
  _OWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rdx
  HLOCAL hMem; // [rsp+50h] [rbp-3B8h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-3B0h]
  int v33; // [rsp+60h] [rbp-3A8h]
  __int64 v34; // [rsp+68h] [rbp-3A0h]
  __int64 v35; // [rsp+70h] [rbp-398h]
  __int64 v36; // [rsp+78h] [rbp-390h]
  __int64 v37; // [rsp+80h] [rbp-388h]
  _BYTE v38[272]; // [rsp+90h] [rbp-378h] BYREF
  int v39; // [rsp+1A0h] [rbp-268h] BYREF
  _BYTE v40[268]; // [rsp+1A4h] [rbp-264h] BYREF
  int v41; // [rsp+2B0h] [rbp-158h] BYREF
  char v42; // [rsp+2B4h] [rbp-154h] BYREF
  _BYTE Destination[267]; // [rsp+2B5h] [rbp-153h] BYREF

  v35 = a4;
  v33 = a1;
  v36 = a2;
  v37 = a5;
  v34 = a6;
  memset_0(&v42, 0, 0x100u);
  memset_0(v40, 0, 0x100u);
  hMem = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 222, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v11 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 223, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else if ( (Source == 0) == ((_DWORD)SourceSize == 0)
         && a5
         && a2
         && (v12 = *(const void **)a2) != 0
         && (v13 = *(_DWORD *)(a2 + 8)) != 0 )
  {
    v41 = *(_DWORD *)(a2 + 8);
    v14 = memcpy_s(Destination, 0xFEu, v12, v13);
    v11 = Win32FromErrno(v14);
    if ( !v11 )
    {
      v39 = SourceSize;
      if ( !Source || (v15 = memcpy_s(v40, 0xFFu, Source, (unsigned int)SourceSize), (v11 = Win32FromErrno(v15)) == 0) )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_DS(1028, 225, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
        }
        v17 = v38;
        v18 = &v39;
        v19 = 2;
        v20 = 2;
        do
        {
          *v17 = *(_OWORD *)v18;
          v17[1] = *((_OWORD *)v18 + 1);
          v17[2] = *((_OWORD *)v18 + 2);
          v17[3] = *((_OWORD *)v18 + 3);
          v17[4] = *((_OWORD *)v18 + 4);
          v17[5] = *((_OWORD *)v18 + 5);
          v17[6] = *((_OWORD *)v18 + 6);
          v17[7] = *((_OWORD *)v18 + 7);
          v17 += 8;
          v18 += 32;
          --v20;
        }
        while ( v20 );
        *(_DWORD *)v17 = *v18;
        v21 = &v39;
        v22 = &v41;
        do
        {
          *(_OWORD *)v21 = *(_OWORD *)v22;
          *((_OWORD *)v21 + 1) = *((_OWORD *)v22 + 1);
          *((_OWORD *)v21 + 2) = *((_OWORD *)v22 + 2);
          *((_OWORD *)v21 + 3) = *((_OWORD *)v22 + 3);
          *((_OWORD *)v21 + 4) = *((_OWORD *)v22 + 4);
          *((_OWORD *)v21 + 5) = *((_OWORD *)v22 + 5);
          *((_OWORD *)v21 + 6) = *((_OWORD *)v22 + 6);
          *((_OWORD *)v21 + 7) = *((_OWORD *)v22 + 7);
          v21 += 32;
          v22 += 32;
          --v19;
        }
        while ( v19 );
        *v21 = *v22;
        v11 = RpcCliLeaseIpAddressEx(
                (_DWORD)v21,
                a1,
                (unsigned int)&v39,
                a3,
                v35,
                (__int64)&hMem,
                v34,
                (__int64)v38,
                SourceSize);
        v32 = v11;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v23 = GetCommandLineW();
          WPP_SF_DDS(v24, 226, v25, v11, a1, (__int64)v23);
        }
        if ( !v11 )
        {
          v26 = LocalAlloc(0, 0x40u);
          *(_QWORD *)a5 = v26;
          *v26 = *(_OWORD *)a2;
          *(_DWORD *)(*(_QWORD *)a5 + 16LL) = *((_DWORD *)hMem + 4);
          *(_DWORD *)(*(_QWORD *)a5 + 28LL) = *((_DWORD *)hMem + 7);
          *(_QWORD *)(*(_QWORD *)a5 + 32LL) = *((unsigned int *)hMem + 8);
          *(_DWORD *)(*(_QWORD *)a5 + 20LL) = *((_DWORD *)hMem + 5);
          *(_DWORD *)(*(_QWORD *)a5 + 24LL) = *((_DWORD *)hMem + 6);
          if ( *((_DWORD *)hMem + 9) == -1 )
          {
            v27 = 0x7FFFFFFFFFFFFFFFLL;
            v28 = 0x7FFFFFFFFFFFFFFFLL;
          }
          else
          {
            v28 = *((unsigned int *)hMem + 9);
            v27 = 0x7FFFFFFFFFFFFFFFLL;
          }
          *(_QWORD *)(*(_QWORD *)a5 + 40LL) = v28;
          v29 = *((unsigned int *)hMem + 10);
          if ( (_DWORD)v29 == -1 )
            v29 = 0x7FFFFFFFFFFFFFFFLL;
          *(_QWORD *)(*(_QWORD *)a5 + 48LL) = v29;
          if ( *((_DWORD *)hMem + 11) != -1 )
            v27 = *((unsigned int *)hMem + 11);
          *(_QWORD *)(*(_QWORD *)a5 + 56LL) = v27;
          LocalFree(hMem);
          hMem = 0;
        }
      }
    }
  }
  else
  {
    v11 = 87;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 227, WPP_e15037783097355a5233924022d92169_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180007dd0  push    rbx
0x180007dd2  push    rsi
0x180007dd3  push    rdi
0x180007dd4  push    r12
0x180007dd6  push    r13
0x180007dd8  push    r14
0x180007dda  push    r15
0x180007ddc  sub     rsp, 3D0h
0x180007de3  mov     rax, cs:__security_cookie
0x180007dea  xor     rax, rsp
0x180007ded  mov     [rsp+408h+var_48], rax
0x180007df5  mov     [rsp+408h+var_398], r9
0x180007dfa  mov     r13d, r8d
0x180007dfd  mov     r14, rdx
0x180007e00  mov     r12d, ecx
0x180007e03  mov     [rsp+408h+var_3A8], ecx
0x180007e07  mov     [rsp+408h+var_390], rdx
0x180007e0c  mov     rdi, [rsp+408h+arg_20]
0x180007e14  mov     [rsp+408h+var_388], rdi
0x180007e1c  mov     rax, [rsp+408h+arg_28]
0x180007e24  mov     [rsp+408h+var_3A0], rax
0x180007e29  mov     r15, [rsp+408h+Source]
0x180007e31  mov     ebx, 100h
0x180007e36  mov     r8d, ebx; Size
0x180007e39  xor     edx, edx; Val
0x180007e3b  lea     rcx, [rsp+408h+var_154]; void *
0x180007e43  call    memset_0
0x180007e48  mov     r8d, ebx; Size
0x180007e4b  xor     edx, edx; Val
0x180007e4d  lea     rcx, [rsp+408h+var_264]; void *
0x180007e55  call    memset_0
0x180007e5a  mov     [rsp+408h+hMem], 0
0x180007e63  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007e6a  jz      short loc_180007E80
0x180007e6c  lea     edx, [rbx-22h]
0x180007e6f  mov     ecx, 404h
0x180007e74  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007e7b  call    WPP_SF_
0x180007e80  call    DhcpIsFSEGuestSystem
0x180007e85  test    eax, eax
0x180007e87  jnz     loc_180008194
0x180007e8d  xor     ecx, ecx
0x180007e8f  test    r15, r15
0x180007e92  setz    cl
0x180007e95  mov     esi, dword ptr [rsp+408h+SourceSize]
0x180007e9c  test    esi, esi
0x180007e9e  setz    al
0x180007ea1  cmp     ecx, eax
0x180007ea3  jz      short loc_180007EAF
0x180007ea5  mov     ebx, 57h ; 'W'
0x180007eaa  jmp     loc_1800081BD
0x180007eaf  test    rdi, rdi
0x180007eb2  jz      short loc_180007EA5
0x180007eb4  test    r14, r14
0x180007eb7  jz      short loc_180007EA5
0x180007eb9  mov     r8, [r14]; Source
0x180007ebc  test    r8, r8
0x180007ebf  jz      short loc_180007EA5
0x180007ec1  mov     eax, [r14+8]
0x180007ec5  test    eax, eax
0x180007ec7  jz      short loc_180007EA5
0x180007ec9  mov     [rsp+408h+var_158], eax
0x180007ed0  mov     r9d, eax; SourceSize
0x180007ed3  mov     edx, 0FEh; DestinationSize
0x180007ed8  lea     rcx, [rsp+408h+Destination]; Destination
0x180007ee0  call    memcpy_s
0x180007ee5  mov     ecx, eax
0x180007ee7  call    Win32FromErrno
0x180007eec  mov     ebx, eax
0x180007eee  test    eax, eax
0x180007ef0  jnz     loc_1800081BD
0x180007ef6  mov     [rsp+408h+var_268], esi
0x180007efd  test    r15, r15
0x180007f00  jz      short loc_180007F2B
0x180007f02  mov     r9, rsi; SourceSize
0x180007f05  mov     r8, r15; Source
0x180007f08  mov     edx, 0FFh; DestinationSize
0x180007f0d  lea     rcx, [rsp+408h+var_264]; Destination
0x180007f15  call    memcpy_s
0x180007f1a  mov     ecx, eax
0x180007f1c  call    Win32FromErrno
0x180007f21  mov     ebx, eax
0x180007f23  test    eax, eax
0x180007f25  jnz     loc_1800081BD
0x180007f2b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007f32  jz      short loc_180007F59
0x180007f34  call    cs:__imp_GetCommandLineW
0x180007f3a  mov     edx, 0E1h
0x180007f3f  mov     ecx, 404h
0x180007f44  mov     [rsp+408h+var_3E8], rax
0x180007f49  mov     r9d, r12d
0x180007f4c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007f53  call    WPP_SF_DS
0x180007f58  nop
0x180007f59  lea     rcx, [rsp+408h+var_378]
0x180007f61  lea     rax, [rsp+408h+var_268]
0x180007f69  mov     edx, 2
0x180007f6e  mov     r8d, edx
0x180007f71  lea     r9d, [rdx+7Eh]
0x180007f75  movups  xmm0, xmmword ptr [rax]
0x180007f78  movups  xmmword ptr [rcx], xmm0
0x180007f7b  movups  xmm1, xmmword ptr [rax+10h]
0x180007f7f  movups  xmmword ptr [rcx+10h], xmm1
0x180007f83  movups  xmm0, xmmword ptr [rax+20h]
0x180007f87  movups  xmmword ptr [rcx+20h], xmm0
0x180007f8b  movups  xmm1, xmmword ptr [rax+30h]
0x180007f8f  movups  xmmword ptr [rcx+30h], xmm1
0x180007f93  movups  xmm0, xmmword ptr [rax+40h]
0x180007f97  movups  xmmword ptr [rcx+40h], xmm0
0x180007f9b  movups  xmm1, xmmword ptr [rax+50h]
0x180007f9f  movups  xmmword ptr [rcx+50h], xmm1
0x180007fa3  movups  xmm0, xmmword ptr [rax+60h]
0x180007fa7  movups  xmmword ptr [rcx+60h], xmm0
0x180007fab  movups  xmm1, xmmword ptr [rax+70h]
0x180007faf  movups  xmmword ptr [rcx+70h], xmm1
0x180007fb3  add     rcx, r9
0x180007fb6  add     rax, r9
0x180007fb9  sub     r8, 1
0x180007fbd  jnz     short loc_180007F75
0x180007fbf  mov     eax, [rax]
0x180007fc1  mov     [rcx], eax
0x180007fc3  lea     rcx, [rsp+408h+var_268]
0x180007fcb  lea     rax, [rsp+408h+var_158]
0x180007fd3  movups  xmm0, xmmword ptr [rax]
0x180007fd6  movups  xmmword ptr [rcx], xmm0
0x180007fd9  movups  xmm1, xmmword ptr [rax+10h]
0x180007fdd  movups  xmmword ptr [rcx+10h], xmm1
0x180007fe1  movups  xmm0, xmmword ptr [rax+20h]
0x180007fe5  movups  xmmword ptr [rcx+20h], xmm0
0x180007fe9  movups  xmm1, xmmword ptr [rax+30h]
0x180007fed  movups  xmmword ptr [rcx+30h], xmm1
0x180007ff1  movups  xmm0, xmmword ptr [rax+40h]
0x180007ff5  movups  xmmword ptr [rcx+40h], xmm0
0x180007ff9  movups  xmm1, xmmword ptr [rax+50h]
0x180007ffd  movups  xmmword ptr [rcx+50h], xmm1
0x180008001  movups  xmm0, xmmword ptr [rax+60h]
0x180008005  movups  xmmword ptr [rcx+60h], xmm0
0x180008009  movups  xmm1, xmmword ptr [rax+70h]
0x18000800d  movups  xmmword ptr [rcx+70h], xmm1
0x180008011  add     rcx, r9
0x180008014  add     rax, r9
0x180008017  sub     rdx, 1
0x18000801b  jnz     short loc_180007FD3
0x18000801d  mov     eax, [rax]
0x18000801f  mov     [rcx], eax
0x180008021  mov     [rsp+408h+var_3C8], esi
0x180008025  lea     rax, [rsp+408h+var_378]
0x18000802d  mov     [rsp+408h+var_3D0], rax
0x180008032  mov     rax, [rsp+408h+var_3A0]
0x180008037  mov     [rsp+408h+var_3D8], rax
0x18000803c  lea     rax, [rsp+408h+hMem]
0x180008041  mov     [rsp+408h+var_3E0], rax
0x180008046  mov     rax, [rsp+408h+var_398]
0x18000804b  mov     [rsp+408h+var_3E8], rax
0x180008050  mov     r9d, r13d
0x180008053  lea     r8, [rsp+408h+var_268]
0x18000805b  mov     edx, r12d
0x18000805e  call    RpcCliLeaseIpAddressEx
0x180008063  mov     ebx, eax
0x180008065  mov     [rsp+408h+var_3B0], eax
0x180008069  jmp     short loc_180008093
0x18000806b  mov     ebx, eax
0x18000806d  mov     [rsp+408h+var_3B0], eax
0x180008071  call    cs:__imp_GetCommandLineW
0x180008077  mov     rdx, rax
0x18000807a  mov     ecx, ebx
0x18000807c  call    TraceRpcException
0x180008081  mov     r12d, [rsp+408h+var_3A8]
0x180008086  mov     r14, [rsp+408h+var_390]
0x18000808b  mov     rdi, [rsp+408h+var_388]
0x180008093  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000809a  jz      short loc_1800080B9
0x18000809c  call    cs:__imp_GetCommandLineW
0x1800080a2  mov     edx, 0E2h
0x1800080a7  mov     [rsp+408h+var_3E0], rax
0x1800080ac  mov     dword ptr [rsp+408h+var_3E8], r12d
0x1800080b1  mov     r9d, ebx
0x1800080b4  call    WPP_SF_DDS
0x1800080b9  test    ebx, ebx
0x1800080bb  jnz     loc_1800081BD
0x1800080c1  lea     edx, [rbx+40h]; uBytes
0x1800080c4  xor     ecx, ecx; uFlags
0x1800080c6  call    cs:__imp_LocalAlloc
0x1800080cc  mov     [rdi], rax
0x1800080cf  movups  xmm0, xmmword ptr [r14]
0x1800080d3  movdqu  xmmword ptr [rax], xmm0
0x1800080d7  mov     rdx, [rdi]
0x1800080da  mov     rax, [rsp+408h+hMem]
0x1800080df  mov     ecx, [rax+10h]
0x1800080e2  mov     [rdx+10h], ecx
0x1800080e5  mov     rdx, [rdi]
0x1800080e8  mov     rax, [rsp+408h+hMem]
0x1800080ed  mov     ecx, [rax+1Ch]
0x1800080f0  mov     [rdx+1Ch], ecx
0x1800080f3  mov     rax, [rsp+408h+hMem]
0x1800080f8  mov     ecx, [rax+20h]
0x1800080fb  mov     rax, [rdi]
0x1800080fe  mov     [rax+20h], rcx
0x180008102  mov     rdx, [rdi]
0x180008105  mov     rax, [rsp+408h+hMem]
0x18000810a  mov     ecx, [rax+14h]
0x18000810d  mov     [rdx+14h], ecx
0x180008110  mov     rdx, [rdi]
0x180008113  mov     rax, [rsp+408h+hMem]
0x180008118  mov     ecx, [rax+18h]
0x18000811b  mov     [rdx+18h], ecx
0x18000811e  mov     rax, [rsp+408h+hMem]
0x180008123  mov     ecx, [rax+24h]
0x180008126  mov     rax, [rdi]
0x180008129  or      r8d, 0FFFFFFFFh
0x18000812d  cmp     ecx, r8d
0x180008130  jnz     short loc_180008141
0x180008132  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18000813c  mov     rdx, rcx
0x18000813f  jmp     short loc_18000814E
0x180008141  mov     rdx, rcx
0x180008144  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18000814e  mov     [rax+28h], rdx
0x180008152  mov     rax, [rsp+408h+hMem]
0x180008157  mov     edx, [rax+28h]
0x18000815a  mov     rax, [rdi]
0x18000815d  cmp     edx, r8d
0x180008160  jnz     short loc_180008165
0x180008162  mov     rdx, rcx
0x180008165  mov     [rax+30h], rdx
0x180008169  mov     rax, [rsp+408h+hMem]
0x18000816e  mov     rdx, [rdi]
0x180008171  cmp     [rax+2Ch], r8d
0x180008175  jz      short loc_18000817A
0x180008177  mov     ecx, [rax+2Ch]
0x18000817a  mov     [rdx+38h], rcx
0x18000817e  mov     rcx, [rsp+408h+hMem]; hMem
0x180008183  call    cs:__imp_LocalFree
0x180008189  mov     [rsp+408h+hMem], 0
0x180008192  jmp     short loc_1800081BD
0x180008194  mov     ebx, 32h ; '2'
0x180008199  lea     edx, [rbx-30h]
0x18000819c  test    byte ptr cs:xmmword_18001E1E0, dl
0x1800081a2  jz      short loc_1800081BD
0x1800081a4  mov     edx, 0DFh
0x1800081a9  mov     ecx, 401h
0x1800081ae  mov     r9d, ebx
0x1800081b1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800081b8  call    WPP_SF_d
0x1800081bd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800081c4  jz      short loc_1800081DF
0x1800081c6  mov     edx, 0E3h
0x1800081cb  mov     ecx, 404h
0x1800081d0  mov     r9d, ebx
0x1800081d3  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800081da  call    WPP_SF_d
0x1800081df  mov     eax, ebx
0x1800081e1  mov     rcx, [rsp+408h+var_48]
0x1800081e9  xor     rcx, rsp; StackCookie
0x1800081ec  call    __security_check_cookie
0x1800081f1  add     rsp, 3D0h
0x1800081f8  pop     r15
0x1800081fa  pop     r14
0x1800081fc  pop     r13
0x1800081fe  pop     r12
0x180008200  pop     rdi
0x180008201  pop     rsi
0x180008202  pop     rbx
0x180008203  retn
0x180010cec  push    rbp
0x180010cee  sub     rsp, 50h
0x180010cf2  mov     rbp, rdx
0x180010cf5  mov     rcx, [rcx]
0x180010cf8  mov     ecx, [rcx]; ExceptionCode
0x180010cfa  call    cs:__imp_I_RpcExceptionFilter
0x180010d00  nop
0x180010d01  add     rsp, 50h
0x180010d05  pop     rbp
0x180010d06  retn
```
