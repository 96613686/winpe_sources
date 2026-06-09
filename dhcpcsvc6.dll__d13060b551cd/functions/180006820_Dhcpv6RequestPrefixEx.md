# Dhcpv6RequestPrefixEx

- ea: `0x180006820`
- end: `0x180006ca7`
- name: `Dhcpv6RequestPrefixEx`
- size: `1159`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, __int64, time_t *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180006770`

## callees

- `0x180001ff0`
- `0x180002650`
- `0x180003650`
- `0x180006820`
- `0x180006e44`
- `0x1800072fc`
- `0x180007891`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006a5f`
- `RPCRT4!NdrClientCall3` at `0x180006a5f`
- `RPCRT4!I_RpcExceptionFilter` at `0x180007a3c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180007a3c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800069e2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006a84`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006ac7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800069e2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006a84`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006ac7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006952`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006952`

## pseudocode

```c
__int64 __fastcall Dhcpv6RequestPrefixEx(const WCHAR *a1, __int64 a2, __int64 a3, time_t *a4, int a5)
{
  unsigned __int16 v8; // si
  unsigned int Pointer; // ebx
  _QWORD *v10; // r12
  _DWORD *v11; // r13
  _DWORD *v12; // rdi
  unsigned __int16 i; // r8
  __int64 v14; // rdx
  LPWSTR CommandLineW; // rax
  int v16; // ecx
  CLIENT_CALL_RETURN v17; // rax
  LPWSTR v18; // rax
  int v19; // ecx
  int v20; // r8d
  __int64 v21; // rdi
  __int64 v22; // rdi
  time_t *const v23; // rcx
  __int64 v24; // r8
  int v25; // ecx
  int v27; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+78h] [rbp-90h]
  int v31; // [rsp+88h] [rbp-80h]
  __int128 v32; // [rsp+90h] [rbp-78h] BYREF
  NET_LUID v33; // [rsp+A0h] [rbp-68h] BYREF
  CLIENT_CALL_RETURN v34; // [rsp+A8h] [rbp-60h]
  __int64 v35; // [rsp+B0h] [rbp-58h]
  __int64 v36; // [rsp+B8h] [rbp-50h]
  __int64 v37; // [rsp+C0h] [rbp-48h]
  void **v38; // [rsp+C8h] [rbp-40h]

  v8 = 0;
  v33.Value = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v32 = 0;
  v27 = -1;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 20, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 21, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
  }
  else
  {
    if ( !a1
      || !a3
      || !a4
      || (v10 = (_QWORD *)(a3 + 8), (*(_QWORD *)(a3 + 8) == 0) != (*(_DWORD *)a3 == 0))
      || (v38 = (void **)(a3 + 64),
          v11 = (_DWORD *)(a3 + 72),
          v36 = a3 + 72,
          (*(_QWORD *)(a3 + 64) == 0) != (*(_DWORD *)(a3 + 72) == 0))
      || (v12 = (_DWORD *)(a3 + 16), v37 = a3 + 16, !*(_DWORD *)(a3 + 16)) )
    {
      Pointer = 87;
      goto LABEL_32;
    }
    Pointer = Dhcpv6AdapterNameToIfId(a1, &v33);
    if ( !Pointer )
    {
      v35 = a3 + 8;
      *(_QWORD *)((char *)&v28 + 4) = 0;
      HIDWORD(v28) = 0;
      LODWORD(v28) = *v12;
      if ( *v10 )
      {
        LODWORD(v29) = *(_DWORD *)a3;
        *((_QWORD *)&v29 + 1) = LocalAlloc(Pointer + 64, 32LL * (unsigned int)v29);
        if ( !*((_QWORD *)&v29 + 1) )
        {
          Pointer = 8;
          goto LABEL_32;
        }
        for ( i = 0; i < (unsigned int)v29; ++i )
        {
          v14 = 32LL * i;
          *(_DWORD *)(v14 + *((_QWORD *)&v29 + 1) + 16) = *(unsigned __int8 *)(v14 + *v10 + 16);
          *(_DWORD *)(v14 + *((_QWORD *)&v29 + 1) + 20) = *(_DWORD *)(v14 + *v10 + 20);
          *(_QWORD *)(v14 + *((_QWORD *)&v29 + 1) + 24) = *(unsigned int *)(v14 + *v10 + 24);
          *(_OWORD *)(v14 + *((_QWORD *)&v29 + 1)) = *(_OWORD *)(v14 + *v10);
        }
      }
      if ( (xmmword_18000F160 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_SS(
          v16,
          22,
          (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
          (_DWORD)a1,
          (__int64)CommandLineW);
      }
      v34.Simple = 0;
      v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, 0, &v33, a2, &v28, &v32, &v27, a5).Pointer;
      Pointer = (unsigned int)v17.Pointer;
      v34.Pointer = v17.Pointer;
      v31 = (int)v17.Pointer;
      if ( (xmmword_18000F160 & 0x10) != 0 )
      {
        v18 = GetCommandLineW();
        WPP_SF_DSS(v19, 23, v20, Pointer, (__int64)a1, (__int64)v18);
      }
      if ( !Pointer )
      {
        if ( HIDWORD(v28) > *(_DWORD *)a3 || (unsigned int)(unsigned __int16)v32 > *v11 )
        {
          *(_DWORD *)a3 = HIDWORD(v28);
          *v11 = (unsigned __int16)v32;
          Pointer = 234;
        }
        else
        {
          *(_DWORD *)a4 = v27;
          *v12 = v28;
          *(_DWORD *)(a3 + 56) = DWORD2(v30);
          v21 = DWORD1(v28);
          *(_QWORD *)(a3 + 24) = v21 + time(a4);
          v22 = DWORD2(v28);
          *(_QWORD *)(a3 + 32) = v22 + time(v23);
          *(_QWORD *)(a3 + 40) = (unsigned int)v30;
          *(_QWORD *)(a3 + 48) = DWORD1(v30);
          memcpy_0(*v38, *((const void **)&v32 + 1), (unsigned __int16)v32);
          *v11 = (unsigned __int16)v32;
          if ( HIDWORD(v28) )
          {
            *(_DWORD *)a3 = HIDWORD(v28);
            do
            {
              if ( v8 >= (unsigned int)v29 )
                break;
              v24 = 32LL * v8;
              *(_OWORD *)(v24 + *v10) = *(_OWORD *)(v24 + *((_QWORD *)&v29 + 1));
              *(_OWORD *)(v24 + *v10 + 16) = *(_OWORD *)(v24 + *((_QWORD *)&v29 + 1) + 16);
              ++v8;
            }
            while ( (unsigned int)v8 < HIDWORD(v28) );
          }
        }
      }
    }
  }
LABEL_32:
  DhcpMidlUserFree((void **)&v29 + 1);
  DhcpMidlUserFree((void **)&v32 + 1);
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v25, 24, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180006820  mov     rax, rsp
0x180006823  mov     [rax+20h], r9
0x180006827  mov     [rax+18h], r8
0x18000682b  mov     [rax+10h], rdx
0x18000682f  mov     [rax+8], rcx
0x180006833  push    rbx
0x180006834  push    rsi
0x180006835  push    rdi
0x180006836  push    r12
0x180006838  push    r13
0x18000683a  push    r14
0x18000683c  push    r15
0x18000683e  sub     rsp, 0D0h
0x180006845  mov     rbx, r9
0x180006848  mov     r14, r8
0x18000684b  mov     r15, rcx
0x18000684e  xor     esi, esi
0x180006850  mov     [rax-68h], rsi
0x180006854  xorps   xmm0, xmm0
0x180006857  movups  [rsp+108h+var_B0], xmm0
0x18000685c  movups  [rsp+108h+var_A0], xmm0
0x180006861  movups  [rsp+108h+var_90], xmm0
0x180006866  movups  xmmword ptr [rax-78h], xmm0
0x18000686a  mov     [rsp+108h+var_B8], 0FFFFFFFFh
0x180006872  test    byte ptr cs:xmmword_18000F160, 10h
0x180006879  jz      short loc_18000688D
0x18000687b  lea     edx, [rsi+14h]
0x18000687e  mov     r9, rcx
0x180006881  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006888  call    WPP_SF_S
0x18000688d  call    DhcpIsFSEGuestSystem
0x180006892  test    eax, eax
0x180006894  jnz     loc_180006C33
0x18000689a  test    r15, r15
0x18000689d  jnz     short loc_1800068A9
0x18000689f  mov     ebx, 57h ; 'W'
0x1800068a4  jmp     loc_180006C5A
0x1800068a9  test    r14, r14
0x1800068ac  jz      short loc_18000689F
0x1800068ae  test    rbx, rbx
0x1800068b1  jz      short loc_18000689F
0x1800068b3  lea     r12, [r14+8]
0x1800068b7  mov     ecx, esi
0x1800068b9  cmp     [r12], rsi
0x1800068bd  setz    cl
0x1800068c0  mov     eax, esi
0x1800068c2  cmp     [r14], esi
0x1800068c5  setz    al
0x1800068c8  cmp     ecx, eax
0x1800068ca  jnz     short loc_18000689F
0x1800068cc  lea     rax, [r14+40h]
0x1800068d0  mov     [rsp+108h+var_40], rax
0x1800068d8  lea     r13, [r14+48h]
0x1800068dc  mov     [rsp+108h+var_50], r13
0x1800068e4  mov     ecx, esi
0x1800068e6  cmp     [rax], rsi
0x1800068e9  setz    cl
0x1800068ec  mov     eax, esi
0x1800068ee  cmp     [r13+0], esi
0x1800068f2  setz    al
0x1800068f5  cmp     ecx, eax
0x1800068f7  jnz     short loc_18000689F
0x1800068f9  lea     rdi, [r14+10h]
0x1800068fd  mov     [rsp+108h+var_48], rdi
0x180006905  cmp     [rdi], esi
0x180006907  jz      short loc_18000689F
0x180006909  lea     rdx, [rsp+108h+var_68]
0x180006911  mov     rcx, r15
0x180006914  call    Dhcpv6AdapterNameToIfId
0x180006919  mov     ebx, eax
0x18000691b  test    eax, eax
0x18000691d  jnz     loc_180006C5A
0x180006923  mov     [rsp+108h+var_58], r12
0x18000692b  mov     qword ptr [rsp+108h+var_B0+4], rsi
0x180006930  mov     dword ptr [rsp+108h+var_B0+0Ch], esi
0x180006934  mov     eax, [rdi]
0x180006936  mov     dword ptr [rsp+108h+var_B0], eax
0x18000693a  cmp     [r12], rsi
0x18000693e  jz      loc_1800069D9
0x180006944  mov     edx, [r14]
0x180006947  mov     dword ptr [rsp+108h+var_A0], edx
0x18000694b  shl     rdx, 5; uBytes
0x18000694f  lea     ecx, [rbx+40h]; uFlags
0x180006952  call    cs:__imp_LocalAlloc
0x180006958  mov     qword ptr [rsp+108h+var_A0+8], rax
0x18000695d  test    rax, rax
0x180006960  jnz     short loc_18000696A
0x180006962  lea     ebx, [rax+8]
0x180006965  jmp     loc_180006C5A
0x18000696a  movzx   r8d, si
0x18000696e  cmp     dword ptr [rsp+108h+var_A0], esi
0x180006972  jbe     short loc_1800069D9
0x180006974  movzx   edx, r8w
0x180006978  shl     rdx, 5
0x18000697c  mov     rax, [r12]
0x180006980  movzx   ecx, byte ptr [rdx+rax+10h]
0x180006985  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x18000698a  mov     [rdx+rax+10h], ecx
0x18000698e  mov     rax, [r12]
0x180006992  mov     ecx, [rdx+rax+14h]
0x180006996  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x18000699b  mov     [rdx+rax+14h], ecx
0x18000699f  mov     rax, [r12]
0x1800069a3  mov     ecx, [rdx+rax+18h]
0x1800069a7  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x1800069ac  mov     [rdx+rax+18h], ecx
0x1800069b0  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x1800069b5  mov     [rdx+rax+1Ch], esi
0x1800069b9  mov     rax, [r12]
0x1800069bd  movups  xmm0, xmmword ptr [rdx+rax]
0x1800069c1  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x1800069c6  movdqu  xmmword ptr [rdx+rax], xmm0
0x1800069cb  inc     r8w
0x1800069cf  movzx   eax, r8w
0x1800069d3  cmp     eax, dword ptr [rsp+108h+var_A0]
0x1800069d7  jb      short loc_180006974
0x1800069d9  test    byte ptr cs:xmmword_18000F160, 10h
0x1800069e0  jz      short loc_180006A02
0x1800069e2  call    cs:__imp_GetCommandLineW
0x1800069e8  mov     edx, 16h
0x1800069ed  mov     [rsp+108h+var_E8], rax
0x1800069f2  mov     r9, r15
0x1800069f5  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800069fc  call    WPP_SF_SS
0x180006a01  nop
0x180006a02  mov     [rsp+108h+var_60], rsi
0x180006a0a  mov     eax, [rsp+108h+arg_20]
0x180006a11  mov     [rsp+108h+var_C0], eax
0x180006a15  lea     rax, [rsp+108h+var_B8]
0x180006a1a  mov     [rsp+108h+var_C8], rax
0x180006a1f  lea     rax, [rsp+108h+var_78]
0x180006a27  mov     [rsp+108h+var_D0], rax
0x180006a2c  lea     rax, [rsp+108h+var_B0]
0x180006a31  mov     [rsp+108h+var_D8], rax
0x180006a36  mov     rax, [rsp+108h+arg_8]
0x180006a3e  mov     [rsp+108h+var_E0], rax
0x180006a43  lea     rax, [rsp+108h+var_68]
0x180006a4b  mov     [rsp+108h+var_E8], rax
0x180006a50  xor     r9d, r9d
0x180006a53  xor     r8d, r8d; pReturnValue
0x180006a56  xor     edx, edx; nProcNum
0x180006a58  lea     rcx, pProxyInfo; pProxyInfo
0x180006a5f  call    cs:__imp_NdrClientCall3
0x180006a65  mov     rbx, rax
0x180006a68  mov     [rsp+108h+var_60], rax
0x180006a70  mov     [rsp+108h+var_80], eax
0x180006a77  jmp     short loc_180006ABE
0x180006a79  mov     edi, eax
0x180006a7b  mov     ebx, eax
0x180006a7d  mov     [rsp+108h+var_80], eax
0x180006a84  call    cs:__imp_GetCommandLineW
0x180006a8a  mov     rdx, rax
0x180006a8d  mov     ecx, ebx
0x180006a8f  call    TraceRpcException
0x180006a94  xor     esi, esi
0x180006a96  mov     r14, [rsp+108h+arg_10]
0x180006a9e  mov     r15, [rsp+108h+arg_0]
0x180006aa6  mov     r12, [rsp+108h+var_58]
0x180006aae  mov     r13, [rsp+108h+var_50]
0x180006ab6  mov     rdi, [rsp+108h+var_48]
0x180006abe  test    byte ptr cs:xmmword_18000F160, 10h
0x180006ac5  jz      short loc_180006AE4
0x180006ac7  call    cs:__imp_GetCommandLineW
0x180006acd  mov     edx, 17h
0x180006ad2  mov     [rsp+108h+var_E0], rax
0x180006ad7  mov     [rsp+108h+var_E8], r15
0x180006adc  mov     r9d, ebx
0x180006adf  call    WPP_SF_DSS
0x180006ae4  test    ebx, ebx
0x180006ae6  jnz     loc_180006C5A
0x180006aec  mov     ecx, dword ptr [rsp+108h+var_B0+0Ch]
0x180006af0  cmp     ecx, [r14]
0x180006af3  ja      loc_180006C1D
0x180006af9  movzx   eax, [rsp+108h+var_78]
0x180006b01  cmp     eax, [r13+0]
0x180006b05  ja      loc_180006C1D
0x180006b0b  mov     eax, [rsp+108h+var_B8]
0x180006b0f  mov     rcx, [rsp+108h+Time]; Time
0x180006b17  mov     [rcx], eax
0x180006b19  mov     eax, dword ptr [rsp+108h+var_B0]
0x180006b1d  mov     [rdi], eax
0x180006b1f  mov     eax, dword ptr [rsp+108h+var_90+8]
0x180006b26  mov     [r14+38h], eax
0x180006b2a  mov     edi, dword ptr [rsp+108h+var_B0+4]
0x180006b2e  call    time
0x180006b33  add     rax, rdi
0x180006b36  mov     [r14+18h], rax
0x180006b3a  mov     edi, dword ptr [rsp+108h+var_B0+8]
0x180006b3e  call    time
0x180006b43  add     rax, rdi
0x180006b46  mov     [r14+20h], rax
0x180006b4a  mov     eax, dword ptr [rsp+108h+var_90]
0x180006b4e  mov     [r14+28h], rax
0x180006b52  mov     eax, dword ptr [rsp+108h+var_90+4]
0x180006b56  mov     [r14+30h], rax
0x180006b5a  movzx   r8d, [rsp+108h+var_78]; Size
0x180006b63  mov     rdx, [rsp+108h+Src]; Src
0x180006b6b  mov     rcx, [rsp+108h+var_40]
0x180006b73  mov     rcx, [rcx]; void *
0x180006b76  call    memcpy_0
0x180006b7b  movzx   eax, [rsp+108h+var_78]
0x180006b83  mov     [r13+0], eax
0x180006b87  mov     eax, dword ptr [rsp+108h+var_B0+0Ch]
0x180006b8b  test    eax, eax
0x180006b8d  jz      loc_180006C5A
0x180006b93  mov     [r14], eax
0x180006b96  movzx   eax, si
0x180006b99  cmp     eax, dword ptr [rsp+108h+var_A0]
0x180006b9d  jnb     loc_180006C5A
0x180006ba3  movzx   r8d, si
0x180006ba7  shl     r8, 5
0x180006bab  mov     rcx, [r12]
0x180006baf  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180006bb4  movups  xmm0, xmmword ptr [r8+rax]
0x180006bb9  movdqu  xmmword ptr [r8+rcx], xmm0
0x180006bbf  mov     rdx, [r12]
0x180006bc3  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180006bc8  mov     ecx, [r8+rax+14h]
0x180006bcd  mov     [r8+rdx+14h], ecx
0x180006bd2  mov     rdx, [r12]
0x180006bd6  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180006bdb  mov     ecx, [r8+rax+10h]
0x180006be0  mov     [r8+rdx+10h], ecx
0x180006be5  mov     rdx, [r12]
0x180006be9  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180006bee  mov     ecx, [r8+rax+18h]
0x180006bf3  mov     [r8+rdx+18h], ecx
0x180006bf8  mov     rdx, [r12]
0x180006bfc  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180006c01  mov     ecx, [r8+rax+1Ch]
0x180006c06  mov     [r8+rdx+1Ch], ecx
0x180006c0b  inc     si
0x180006c0e  movzx   eax, si
0x180006c11  cmp     eax, dword ptr [rsp+108h+var_B0+0Ch]
0x180006c15  jb      loc_180006B96
0x180006c1b  jmp     short loc_180006C5A
0x180006c1d  mov     [r14], ecx
0x180006c20  movzx   eax, [rsp+108h+var_78]
0x180006c28  mov     [r13+0], eax
0x180006c2c  mov     ebx, 0EAh
0x180006c31  jmp     short loc_180006C5A
0x180006c33  mov     r9d, 32h ; '2'
0x180006c39  mov     ebx, r9d
0x180006c3c  test    byte ptr cs:xmmword_18000F160, 2
0x180006c43  jz      short loc_180006C5A
0x180006c45  lea     edx, [r9-1Dh]
0x180006c49  mov     ecx, 401h
0x180006c4e  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006c55  call    WPP_SF_D
0x180006c5a  lea     rcx, [rsp+108h+var_A0+8]
0x180006c5f  call    DhcpMidlUserFree
0x180006c64  lea     rcx, [rsp+108h+Src]
0x180006c6c  call    DhcpMidlUserFree
0x180006c71  test    byte ptr cs:xmmword_18000F160, 10h
0x180006c78  jz      short loc_180006C92
0x180006c7a  mov     edx, 18h
0x180006c7f  mov     dword ptr [rsp+108h+var_E8], ebx
0x180006c83  mov     r9, r15
0x180006c86  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006c8d  call    WPP_SF_SD
0x180006c92  mov     eax, ebx
0x180006c94  add     rsp, 0D0h
0x180006c9b  pop     r15
0x180006c9d  pop     r14
0x180006c9f  pop     r13
0x180006ca1  pop     r12
0x180006ca3  pop     rdi
0x180006ca4  pop     rsi
0x180006ca5  pop     rbx
0x180006ca6  retn
0x180007a2e  push    rbp
0x180007a30  sub     rsp, 50h
0x180007a34  mov     rbp, rdx
0x180007a37  mov     rcx, [rcx]
0x180007a3a  mov     ecx, [rcx]; ExceptionCode
0x180007a3c  call    cs:__imp_I_RpcExceptionFilter
0x180007a42  nop
0x180007a43  add     rsp, 50h
0x180007a47  pop     rbp
0x180007a48  retn
```
