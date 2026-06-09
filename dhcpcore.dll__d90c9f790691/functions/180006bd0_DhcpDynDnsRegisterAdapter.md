# DhcpDynDnsRegisterAdapter

- ea: `0x180006bd0`
- end: `0x18000718a`
- name: `DhcpDynDnsRegisterAdapter`
- size: `1466`
- prototype: `__int64 __fastcall(int *, _DWORD *, __int64, int, const wchar_t *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800042b8`

## callees

- `0x180006440`
- `0x180006bd0`
- `0x180007190`
- `0x180008ed0`
- `0x18001cef0`
- `0x18001d826`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d6dc`
- `0x18004d9e8`
- `0x18004dd6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006c6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006c6e`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x180006ee0`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x180006ee0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180006ec4`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180006ec4`

## pseudocode

```c
__int64 __fastcall DhcpDynDnsRegisterAdapter(
        int *a1,
        _DWORD *a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 v10; // rsi
  DWORD LastError; // ebx
  char v13; // al
  const wchar_t *v14; // r9
  _DWORD *v15; // rax
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // eax
  int v17; // edx
  int v18; // ecx
  char v19; // al
  int *v20; // rdi
  int *v21; // r9
  int *v22; // r8
  int *v23; // rdx
  int *v24; // rcx
  int *v25; // rax
  __int16 *v26; // rax
  __int64 v27; // rcx
  __int16 *v28; // rcx
  _DWORD *v29; // rax
  unsigned int v30; // r8d
  __int64 v31; // rdx
  __int64 v32; // rcx
  int *v33; // r10
  int *v34; // r8
  int *v35; // rdx
  int *v36; // rcx
  int *v37; // rax
  DWORD nSize; // [rsp+60h] [rbp-3F8h] BYREF
  __int128 v39; // [rsp+68h] [rbp-3F0h]
  _DWORD v40[2]; // [rsp+80h] [rbp-3D8h] BYREF
  __int64 v41; // [rsp+88h] [rbp-3D0h]
  int *v42; // [rsp+90h] [rbp-3C8h]
  WCHAR *v43; // [rsp+98h] [rbp-3C0h]
  __int64 v44; // [rsp+A0h] [rbp-3B8h]
  LPVOID lpMem; // [rsp+A8h] [rbp-3B0h]
  LPVOID v46; // [rsp+B0h] [rbp-3A8h]
  int v47; // [rsp+B8h] [rbp-3A0h]
  int v48; // [rsp+BCh] [rbp-39Ch]
  NET_IF_COMPARTMENT_ID v49; // [rsp+C8h] [rbp-390h]
  _DWORD v50[5]; // [rsp+D0h] [rbp-388h] BYREF
  __int16 v51; // [rsp+E4h] [rbp-374h]
  int v52; // [rsp+E8h] [rbp-370h]
  int v53; // [rsp+144h] [rbp-314h]
  __int16 v54; // [rsp+170h] [rbp-2E8h] BYREF
  WCHAR Buffer[256]; // [rsp+210h] [rbp-248h] BYREF

  memset_0(v50, 0, 0x140u);
  v10 = 80;
  memset_0(v40, 0, 0x50u);
  v39 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  nSize = 256;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize) )
  {
    LastError = GetLastError();
    goto LABEL_3;
  }
  v13 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 21, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids);
    v13 = xmmword_1800616A0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_S(1028, 22, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, a1);
      v13 = xmmword_1800616A0;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        WPP_SF_S(1028, 23, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, Buffer);
        v13 = xmmword_1800616A0;
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          v14 = a5;
          if ( !a5 )
            v14 = L"[PrimaryOnly]";
          WPP_SF_S(1028, 24, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, v14);
          v13 = xmmword_1800616A0;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
          {
            WPP_SF_d(1028, 25, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, 1);
            v13 = xmmword_1800616A0;
            if ( (xmmword_1800616A0 & 0x10) != 0 )
            {
              WPP_SF_d(1028, 26, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, a7);
              v13 = xmmword_1800616A0;
            }
          }
        }
      }
    }
  }
  if ( (v13 & 0x10) != 0 )
  {
    v33 = (int *)"REG_UNKNOWN  ";
    if ( (a4 & 0x80u) == 0 )
      v33 = &dword_180053E2C;
    v34 = (int *)"NO_REG  ";
    v35 = (int *)"REG_RAS ";
    if ( (a4 & 0x40) == 0 )
      v34 = &dword_180053E2C;
    v36 = (int *)"REG_PTR ";
    v37 = (int *)"REG_DOMAIN ";
    if ( (a4 & 0x10) == 0 )
      v35 = &dword_180053E2C;
    if ( (a4 & 8) == 0 )
      v36 = &dword_180053E2C;
    if ( (a4 & 2) == 0 )
      v37 = &dword_180053E2C;
    WPP_SF_ssssss(
      (_DWORD)v36,
      (_DWORD)v35,
      (_DWORD)v34,
      (unsigned int)&dword_180053E2C,
      (__int64)v37,
      (__int64)v36,
      (__int64)v35,
      (__int64)v34,
      (__int64)v33);
  }
  v40[1] = 1;
  v42 = a1;
  v48 = a4 | 0x100;
  v44 = (__int64)a5;
  v43 = Buffer;
  v41 = 0;
  v47 = 0;
  LOWORD(v39) = 2;
  v15 = DhcpAlloc(0xA0u);
  lpMem = v15;
  if ( !v15 )
    goto LABEL_60;
  *v15 = 1;
  *((_DWORD *)lpMem + 1) = 1;
  *((_WORD *)lpMem + 6) = 2;
  DWORD1(v39) = *a2;
  *((_OWORD *)lpMem + 2) = v39;
  *((_DWORD *)lpMem + 16) = 16;
  if ( a7 )
  {
    v29 = DhcpAlloc(((unsigned __int64)a7 << 6) + 96);
    v46 = v29;
    if ( v29 )
    {
      v30 = 0;
      *v29 = a7;
      *((_DWORD *)v46 + 1) = a7;
      *((_WORD *)v46 + 6) = 2;
      v31 = 0;
      do
      {
        v32 = v31;
        DWORD1(v39) = *(_DWORD *)(a6 + 4 * v31);
        ++v30;
        ++v31;
        v32 <<= 6;
        *(_OWORD *)((char *)v46 + v32 + 32) = v39;
        *(_DWORD *)((char *)v46 + v32 + 64) = 16;
      }
      while ( v30 < a7 );
      goto LABEL_20;
    }
LABEL_60:
    LastError = 8;
    goto LABEL_3;
  }
LABEL_20:
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  v40[0] = 80;
  v49 = CurrentThreadCompartmentId;
  LastError = DnsDhcpRegisterAddrs(v40);
  v19 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_D(1028, 28, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, LastError);
    v19 = xmmword_1800616A0;
  }
  v20 = &dword_180053FEC;
  if ( (v19 & 2) != 0 )
  {
    v21 = (int *)L"REG_UNKNOWN  ";
    v22 = (int *)L"NO_REG  ";
    v23 = (int *)L"REG_RAS ";
    if ( (a4 & 0x80u) == 0 )
      v21 = &dword_180053FEC;
    v24 = (int *)L"REG_PTR ";
    v25 = (int *)L"REG_DOMAIN ";
    if ( (a4 & 0x40) == 0 )
      v22 = &dword_180053FEC;
    if ( (a4 & 0x10) == 0 )
      v23 = &dword_180053FEC;
    if ( (a4 & 8) == 0 )
      v24 = &dword_180053FEC;
    if ( (a4 & 2) == 0 )
      v25 = &dword_180053FEC;
    WPP_SF_SdSSSSSSD(
      (_DWORD)v24,
      (_DWORD)v23,
      (_DWORD)v22,
      (_DWORD)a1,
      *a2,
      (__int64)&dword_180053FEC,
      (__int64)v25,
      (__int64)v24,
      (__int64)v23,
      (__int64)v22,
      (__int64)v21,
      LastError);
  }
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0zqqq_EtwEventWriteTransfer(v18, v17, (_DWORD)a1, *a2, a4, LastError);
  memset_0(v50, 0, 0xA0u);
  v52 = *a2;
  if ( a1 )
    v20 = a1;
  v54 = 0;
  v50[0] = LastError;
  v26 = &v54;
  v50[3] = 18;
  v27 = 2147483646;
  v53 = a4;
  v51 = 2;
  do
  {
    if ( !v27 )
      break;
    if ( !*(_WORD *)v20 )
      break;
    *v26 = *(_WORD *)v20;
    v20 = (int *)((char *)v20 + 2);
    ++v26;
    --v27;
    --v10;
  }
  while ( v10 );
  v28 = v26 - 1;
  if ( v10 )
    v28 = v26;
  *v28 = 0;
  TraceLogEx(v50);
LABEL_3:
  if ( lpMem )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, lpMem);
    lpMem = 0;
  }
  if ( v46 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v46);
  return LastError;
}

```

## disassembly

```asm
0x180006bd0  push    rbx
0x180006bd2  push    rsi
0x180006bd3  push    rdi
0x180006bd4  push    r12
0x180006bd6  push    r13
0x180006bd8  push    r14
0x180006bda  push    r15
0x180006bdc  sub     rsp, 420h
0x180006be3  mov     rax, cs:__security_cookie
0x180006bea  xor     rax, rsp
0x180006bed  mov     [rsp+458h+var_48], rax
0x180006bf5  mov     rdi, [rsp+458h+arg_20]
0x180006bfd  mov     r12, rdx
0x180006c00  mov     ebx, [rsp+458h+arg_30]
0x180006c07  mov     r15, rcx
0x180006c0a  xor     edx, edx; Val
0x180006c0c  lea     rcx, [rsp+458h+var_388]; void *
0x180006c14  mov     r8d, 140h; Size
0x180006c1a  mov     r14d, r9d
0x180006c1d  call    memset_0
0x180006c22  mov     esi, 50h ; 'P'
0x180006c27  lea     rcx, [rsp+458h+var_3D8]; void *
0x180006c2f  mov     r8d, esi; Size
0x180006c32  xor     edx, edx; Val
0x180006c34  call    memset_0
0x180006c39  xorps   xmm0, xmm0
0x180006c3c  lea     rcx, [rsp+458h+Buffer]; void *
0x180006c44  xor     edx, edx; Val
0x180006c46  mov     r8d, 200h; Size
0x180006c4c  movups  [rsp+458h+var_3F0], xmm0
0x180006c51  call    memset_0
0x180006c56  lea     r8, [rsp+458h+nSize]; nSize
0x180006c5b  mov     [rsp+458h+nSize], 100h
0x180006c63  lea     rdx, [rsp+458h+Buffer]; lpBuffer
0x180006c6b  lea     ecx, [rsi-4Fh]; NameType
0x180006c6e  call    cs:__imp_GetComputerNameExW
0x180006c74  xor     r13d, r13d
0x180006c77  test    eax, eax
0x180006c79  jnz     loc_180006D02
0x180006c7f  call    cs:__imp_GetLastError
0x180006c85  mov     ebx, eax
0x180006c87  cmp     [rsp+458h+lpMem], r13
0x180006c8f  jz      short loc_180006CB6
0x180006c91  mov     rcx, gs:60h
0x180006c9a  xor     edx, edx; dwFlags
0x180006c9c  mov     r8, [rsp+458h+lpMem]; lpMem
0x180006ca4  mov     rcx, [rcx+30h]; hHeap
0x180006ca8  call    cs:__imp_HeapFree
0x180006cae  mov     [rsp+458h+lpMem], r13
0x180006cb6  cmp     [rsp+458h+var_3A8], r13
0x180006cbe  jz      short loc_180006CDD
0x180006cc0  mov     rcx, gs:60h
0x180006cc9  xor     edx, edx; dwFlags
0x180006ccb  mov     r8, [rsp+458h+var_3A8]; lpMem
0x180006cd3  mov     rcx, [rcx+30h]; hHeap
0x180006cd7  call    cs:__imp_HeapFree
0x180006cdd  mov     eax, ebx
0x180006cdf  mov     rcx, [rsp+458h+var_48]
0x180006ce7  xor     rcx, rsp; StackCookie
0x180006cea  call    __security_check_cookie
0x180006cef  add     rsp, 420h
0x180006cf6  pop     r15
0x180006cf8  pop     r14
0x180006cfa  pop     r13
0x180006cfc  pop     r12
0x180006cfe  pop     rdi
0x180006cff  pop     rsi
0x180006d00  pop     rbx
0x180006d01  retn
0x180006d02  mov     al, byte ptr cs:xmmword_1800616A0
0x180006d08  test    al, 10h
0x180006d0a  jz      loc_180006DF7
0x180006d10  mov     edx, 15h
0x180006d15  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180006d1c  mov     ecx, 404h
0x180006d21  call    WPP_SF_
0x180006d26  mov     al, byte ptr cs:xmmword_1800616A0
0x180006d2c  test    al, 10h
0x180006d2e  jz      loc_180006DF7
0x180006d34  mov     edx, 16h
0x180006d39  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180006d40  mov     ecx, 404h
0x180006d45  mov     r9, r15
0x180006d48  call    WPP_SF_S
0x180006d4d  mov     al, byte ptr cs:xmmword_1800616A0
0x180006d53  test    al, 10h
0x180006d55  jz      loc_180006DF7
0x180006d5b  mov     edx, 17h
0x180006d60  lea     r9, [rsp+458h+Buffer]
0x180006d68  mov     ecx, 404h
0x180006d6d  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180006d74  call    WPP_SF_S
0x180006d79  mov     al, byte ptr cs:xmmword_1800616A0
0x180006d7f  test    al, 10h
0x180006d81  jz      short loc_180006DF7
0x180006d83  test    rdi, rdi
0x180006d86  lea     rax, aPrimaryonly; "[PrimaryOnly]"
0x180006d8d  mov     r9, rdi
0x180006d90  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180006d97  cmovz   r9, rax
0x180006d9b  mov     edx, 18h
0x180006da0  mov     ecx, 404h
0x180006da5  call    WPP_SF_S
0x180006daa  mov     al, byte ptr cs:xmmword_1800616A0
0x180006db0  test    al, 10h
0x180006db2  jz      short loc_180006DF7
0x180006db4  mov     edx, 19h
0x180006db9  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180006dc0  mov     ecx, 404h
0x180006dc5  lea     r9d, [rdx-18h]
0x180006dc9  call    WPP_SF_d
0x180006dce  mov     al, byte ptr cs:xmmword_1800616A0
0x180006dd4  test    al, 10h
0x180006dd6  jz      short loc_180006DF7
0x180006dd8  mov     edx, 1Ah
0x180006ddd  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180006de4  mov     ecx, 404h
0x180006de9  mov     r9d, ebx
0x180006dec  call    WPP_SF_d
0x180006df1  mov     al, byte ptr cs:xmmword_1800616A0
0x180006df7  mov     r11d, 2
0x180006dfd  test    al, 10h
0x180006dff  jnz     loc_1800070EC
0x180006e05  mov     eax, r14d
0x180006e08  mov     [rsp+458h+var_3D4], 1
0x180006e13  bts     eax, 8
0x180006e17  mov     [rsp+458h+var_3C8], r15
0x180006e1f  mov     [rsp+458h+var_39C], eax
0x180006e26  mov     ecx, 0A0h
0x180006e2b  lea     rax, [rsp+458h+Buffer]
0x180006e33  mov     [rsp+458h+var_3B8], rdi
0x180006e3b  mov     [rsp+458h+var_3C0], rax
0x180006e43  mov     [rsp+458h+var_3D0], r13
0x180006e4b  mov     [rsp+458h+var_3A0], r13d
0x180006e53  mov     word ptr [rsp+458h+var_3F0], r11w
0x180006e59  call    DhcpAlloc
0x180006e5e  mov     [rsp+458h+lpMem], rax
0x180006e66  test    rax, rax
0x180006e69  jz      loc_180007180
0x180006e6f  mov     dword ptr [rax], 1
0x180006e75  mov     edi, 10h
0x180006e7a  mov     rax, [rsp+458h+lpMem]
0x180006e82  mov     dword ptr [rax+4], 1
0x180006e89  mov     rax, [rsp+458h+lpMem]
0x180006e91  mov     word ptr [rax+0Ch], 2
0x180006e97  mov     eax, [r12]
0x180006e9b  mov     dword ptr [rsp+458h+var_3F0+4], eax
0x180006e9f  mov     rax, [rsp+458h+lpMem]
0x180006ea7  movups  xmm0, [rsp+458h+var_3F0]
0x180006eac  movdqu  xmmword ptr [rax+20h], xmm0
0x180006eb1  mov     rax, [rsp+458h+lpMem]
0x180006eb9  mov     [rax+40h], edi
0x180006ebc  test    ebx, ebx
0x180006ebe  jnz     loc_18000705C
0x180006ec4  call    cs:__imp_GetCurrentThreadCompartmentId
0x180006eca  lea     rcx, [rsp+458h+var_3D8]
0x180006ed2  mov     [rsp+458h+var_3D8], esi
0x180006ed9  mov     [rsp+458h+var_390], eax
0x180006ee0  call    cs:__imp_DnsDhcpRegisterAddrs
0x180006ee6  mov     ebx, eax
0x180006ee8  mov     al, byte ptr cs:xmmword_1800616A0
0x180006eee  test    dil, al
0x180006ef1  jnz     loc_180007038
0x180006ef7  mov     r10d, 2
0x180006efd  lea     rdi, dword_180053FEC
0x180006f04  test    r10b, al
0x180006f07  jz      short loc_180006F85
0x180006f09  mov     [rsp+458h+var_400], ebx
0x180006f0d  lea     r9, aRegUnknown_0; "REG_UNKNOWN  "
0x180006f14  test    r14b, 80h
0x180006f18  lea     r8, aNoReg_0; "NO_REG  "
0x180006f1f  lea     rdx, aRegRas_0; "REG_RAS "
0x180006f26  cmovz   r9, rdi
0x180006f2a  lea     rcx, aRegPtr_0; "REG_PTR "
0x180006f31  mov     [rsp+458h+var_408], r9
0x180006f36  lea     rax, aRegDomain_0; "REG_DOMAIN "
0x180006f3d  test    r14b, 40h
0x180006f41  mov     r9, r15
0x180006f44  cmovz   r8, rdi
0x180006f48  test    r14b, 10h
0x180006f4c  mov     [rsp+458h+var_410], r8
0x180006f51  cmovz   rdx, rdi
0x180006f55  test    r14b, 8
0x180006f59  mov     [rsp+458h+var_418], rdx
0x180006f5e  cmovz   rcx, rdi
0x180006f62  test    r10b, r14b
0x180006f65  mov     [rsp+458h+var_420], rcx
0x180006f6a  cmovz   rax, rdi
0x180006f6e  mov     [rsp+458h+var_428], rax
0x180006f73  mov     eax, [r12]
0x180006f77  mov     [rsp+458h+var_430], rdi
0x180006f7c  mov     dword ptr [rsp+458h+var_438], eax
0x180006f80  call    WPP_SF_SdSSSSSSD
0x180006f85  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x180006f8c  jnz     loc_180007166
0x180006f92  xor     edx, edx; Val
0x180006f94  lea     rcx, [rsp+458h+var_388]; void *
0x180006f9c  mov     r8d, 0A0h; Size
0x180006fa2  call    memset_0
0x180006fa7  mov     eax, [r12]
0x180006fab  test    r15, r15
0x180006fae  mov     r8d, 2
0x180006fb4  mov     [rsp+458h+var_370], eax
0x180006fbb  cmovnz  rdi, r15
0x180006fbf  mov     [rsp+458h+var_2E8], r13w
0x180006fc8  mov     [rsp+458h+var_388], ebx
0x180006fcf  lea     rax, [rsp+458h+var_2E8]
0x180006fd7  mov     [rsp+458h+var_37C], 12h
0x180006fe2  mov     ecx, 7FFFFFFEh
0x180006fe7  mov     [rsp+458h+var_314], r14d
0x180006fef  mov     [rsp+458h+var_374], r8w
0x180006ff8  test    rcx, rcx
0x180006ffb  jz      short loc_180007017
0x180006ffd  movzx   edx, word ptr [rdi]
0x180007000  test    dx, dx
0x180007003  jz      short loc_180007017
0x180007005  mov     [rax], dx
0x180007008  add     rdi, r8
0x18000700b  add     rax, r8
0x18000700e  dec     rcx
0x180007011  sub     rsi, 1
0x180007015  jnz     short loc_180006FF8
0x180007017  test    rsi, rsi
0x18000701a  lea     rcx, [rax-2]
0x18000701e  cmovnz  rcx, rax
0x180007022  mov     [rcx], r13w
0x180007026  lea     rcx, [rsp+458h+var_388]
0x18000702e  call    TraceLogEx
0x180007033  jmp     loc_180006C87
0x180007038  mov     edx, 1Ch
0x18000703d  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180007044  mov     ecx, 404h
0x180007049  mov     r9d, ebx
0x18000704c  call    WPP_SF_D
0x180007051  mov     al, byte ptr cs:xmmword_1800616A0
0x180007057  jmp     loc_180006EF7
0x18000705c  mov     rcx, rbx
0x18000705f  shl     rcx, 6
0x180007063  add     rcx, 60h ; '`'
0x180007067  call    DhcpAlloc
0x18000706c  mov     [rsp+458h+var_3A8], rax
0x180007074  test    rax, rax
0x180007077  jz      loc_180007180
0x18000707d  mov     r9, [rsp+458h+arg_28]
0x180007085  mov     r8d, r13d
0x180007088  mov     [rax], ebx
0x18000708a  mov     rax, [rsp+458h+var_3A8]
0x180007092  mov     [rax+4], ebx
0x180007095  mov     rax, [rsp+458h+var_3A8]
0x18000709d  mov     word ptr [rax+0Ch], 2
0x1800070a3  test    ebx, ebx
0x1800070a5  jz      loc_180006EC4
0x1800070ab  mov     rdx, r13
0x1800070ae  mov     eax, [r9+rdx*4]
0x1800070b2  mov     rcx, rdx
0x1800070b5  mov     dword ptr [rsp+458h+var_3F0+4], eax
0x1800070b9  inc     r8d
0x1800070bc  mov     rax, [rsp+458h+var_3A8]
0x1800070c4  inc     rdx
0x1800070c7  movups  xmm0, [rsp+458h+var_3F0]
0x1800070cc  shl     rcx, 6
0x1800070d0  movdqu  xmmword ptr [rcx+rax+20h], xmm0
0x1800070d6  mov     rax, [rsp+458h+var_3A8]
0x1800070de  mov     [rcx+rax+40h], edi
0x1800070e2  cmp     r8d, ebx
0x1800070e5  jb      short loc_1800070AE
0x1800070e7  jmp     loc_180006EC4
0x1800070ec  test    r14b, 80h
0x1800070f0  lea     r9, dword_180053E2C
0x1800070f7  lea     r10, aRegUnknown; "REG_UNKNOWN  "
0x1800070fe  cmovz   r10, r9
0x180007102  lea     r8, aNoReg; "NO_REG  "
0x180007109  test    r14b, 40h
0x18000710d  mov     [rsp+458h+var_418], r10
0x180007112  lea     rdx, aRegRas; "REG_RAS "
0x180007119  cmovz   r8, r9
0x18000711d  lea     rcx, aRegPtr; "REG_PTR "
0x180007124  test    r14b, 10h
0x180007128  mov     [rsp+458h+var_420], r8
0x18000712d  lea     rax, aRegDomain; "REG_DOMAIN "
0x180007134  cmovz   rdx, r9
0x180007138  test    r14b, 8
0x18000713c  mov     [rsp+458h+var_428], rdx
0x180007141  cmovz   rcx, r9
0x180007145  test    r11b, r14b
0x180007148  mov     [rsp+458h+var_430], rcx
0x18000714d  cmovz   rax, r9
0x180007151  mov     [rsp+458h+var_438], rax
0x180007156  call    WPP_SF_ssssss
0x18000715b  mov     r11d, 2
0x180007161  jmp     loc_180006E05
0x180007166  mov     r9d, [r12]
0x18000716a  mov     r8, r15
0x18000716d  mov     dword ptr [rsp+458h+var_430], ebx
0x180007171  mov     dword ptr [rsp+458h+var_438], r14d
0x180007176  call    McTemplateU0zqqq_EtwEventWriteTransfer
0x18000717b  jmp     loc_180006F92
0x180007180  mov     ebx, 8
0x180007185  jmp     loc_180006C87
```
