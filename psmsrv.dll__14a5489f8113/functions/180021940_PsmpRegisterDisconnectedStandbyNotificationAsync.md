# PsmpRegisterDisconnectedStandbyNotificationAsync

- ea: `0x180021940`
- end: `0x180021bbb`
- name: `PsmpRegisterDisconnectedStandbyNotificationAsync`
- size: `635`
- prototype: `__int64 __fastcall(__int64, void *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017f60`
- `0x18001b7e0`
- `0x180021940`

## import_xrefs

- `ntdll!TpReleaseWait` at `0x180021b84`
- `ntdll!TpReleaseWait` at `0x180021b84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b7b`
- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x1800219f7`
- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x180021a4b`
- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x1800219f7`
- `CSystemEventsBrokerClient!CSebCreateWellKnownEvent` at `0x180021a4b`
- `EventAggregation!EaCreateAggregation` at `0x180021b43`
- `EventAggregation!EaCreateAggregation` at `0x180021b43`

## pseudocode

```c
__int64 __fastcall PsmpRegisterDisconnectedStandbyNotificationAsync(__int64 a1, void *a2, __int64 a3)
{
  int Aggregation; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int128 v9; // [rsp+48h] [rbp-C0h]
  __int128 v10; // [rsp+88h] [rbp-80h] BYREF
  __int128 v11; // [rsp+98h] [rbp-70h]
  __int128 v12; // [rsp+A8h] [rbp-60h]
  __int64 v13; // [rsp+B8h] [rbp-50h]
  _OWORD v14[3]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v15; // [rsp+F8h] [rbp-10h]
  __int128 v16; // [rsp+100h] [rbp-8h] BYREF
  __int128 v17; // [rsp+110h] [rbp+8h]
  __int128 v18; // [rsp+120h] [rbp+18h]
  __int64 v19; // [rsp+130h] [rbp+28h]
  unsigned __int64 v20; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int64 v21; // [rsp+140h] [rbp+38h] BYREF
  _OWORD v22[3]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v23; // [rsp+178h] [rbp+70h]
  __int128 v24; // [rsp+180h] [rbp+78h]
  __int128 v25; // [rsp+190h] [rbp+88h]
  __int128 v26; // [rsp+1A0h] [rbp+98h]
  __int64 v27; // [rsp+1B0h] [rbp+A8h]

  LODWORD(v19) = 0;
  *(_QWORD *)&v9 = 0;
  *((_QWORD *)&v9 + 1) = 0x10000101DLL;
  v16 = 0;
  v20 = 0;
  v17 = 0;
  v15 = 0;
  v18 = 0;
  v21 = 0;
  memset(v14, 0, sizeof(v14));
  v11 = 0x100000001uLL;
  v10 = v9;
  v12 = 0;
  v13 = 0;
  Aggregation = CSebCreateWellKnownEvent(&v10, &v20);
  if ( Aggregation >= 0 )
  {
    DWORD2(v9) = 4152;
    v11 = 0x100000001uLL;
    v10 = v9;
    v12 = 0;
    v13 = 0;
    Aggregation = CSebCreateWellKnownEvent(&v10, &v21);
    if ( Aggregation >= 0 )
    {
      v19 = 0;
      v23 = 1;
      *(_QWORD *)&v16 = 1;
      *((_QWORD *)&v14[0] + 1) = &v16;
      *((_QWORD *)&v16 + 1) = 0x200000000LL;
      v17 = (unsigned __int64)v22;
      v22[1] = v20;
      v25 = v21;
      v22[0] = 0;
      v24 = 0;
      v18 = 0;
      v22[2] = 0;
      LODWORD(v22[0]) = 0;
      v26 = 0;
      LODWORD(v24) = 0;
      v27 = 1;
      Aggregation = EaCreateAggregation(
                      v14,
                      PsmpDisconnectedStandbyStartCallback,
                      PsmpDisconnectedStandbyStopCallback,
                      0,
                      0,
                      0,
                      0,
                      &qword_18003FE80);
      if ( Aggregation < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 41;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 40;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 39;
LABEL_13:
      WPP_SF_d(v6[2], v7, &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids, (unsigned int)Aggregation);
    }
  }
  CloseHandle(a2);
  return TpReleaseWait(a3);
}

```

## disassembly

```asm
0x180021940  mov     rax, rsp
0x180021943  mov     [rax+8], rbx
0x180021947  push    rbp
0x180021948  push    rsi
0x180021949  push    rdi
0x18002194a  lea     rbp, [rax-108h]
0x180021951  sub     rsp, 1F0h
0x180021958  movaps  xmmword ptr [rax-28h], xmm6
0x18002195c  movaps  xmmword ptr [rax-38h], xmm7
0x180021960  movaps  xmmword ptr [rax-48h], xmm8
0x180021965  mov     rax, cs:__security_cookie
0x18002196c  xor     rax, rsp
0x18002196f  mov     [rbp+100h+var_50], rax
0x180021976  xorps   xmm0, xmm0
0x180021979  xor     eax, eax
0x18002197b  xorps   xmm6, xmm6
0x18002197e  mov     dword ptr [rbp+100h+var_D8], eax
0x180021981  movups  [rsp+200h+var_1C8+8], xmm6
0x180021986  xor     ecx, ecx
0x180021988  mov     rbx, rdx
0x18002198b  lea     esi, [rax+1]
0x18002198e  mov     dword ptr [rsp+200h+var_1B8], 101Dh
0x180021996  movups  [rsp+200h+var_1B8+8], xmm6
0x18002199b  mov     dword ptr [rsp+200h+var_1B8+4], esi
0x18002199f  lea     rdx, [rbp+100h+var_D0]
0x1800219a3  movq    xmm8, rcx
0x1800219a8  mov     dword ptr [rsp+200h+var_1B8+0Ch], esi
0x1800219ac  movups  [rbp+100h+var_108], xmm0
0x1800219b0  mov     dword ptr [rsp+200h+var_1B8+8], esi
0x1800219b4  lea     rcx, [rbp+100h+var_180]
0x1800219b8  movups  xmm7, [rsp+200h+var_1B8+8]
0x1800219bd  mov     rdi, r8
0x1800219c0  mov     [rbp+100h+var_D0], rax
0x1800219c4  movups  [rbp+100h+var_F8], xmm0
0x1800219c8  mov     [rbp+100h+var_110], rax
0x1800219cc  movups  [rbp+100h+var_E8], xmm0
0x1800219d0  mov     [rbp+100h+var_C8], rax
0x1800219d4  movups  [rbp+100h+var_140], xmm0
0x1800219d8  movups  [rbp+100h+var_130], xmm0
0x1800219dc  movups  [rbp+100h+var_120], xmm0
0x1800219e0  movups  xmm0, [rsp+200h+var_1C8+8]
0x1800219e5  movaps  [rbp+100h+var_170], xmm7
0x1800219e9  movaps  [rbp+100h+var_180], xmm0
0x1800219ed  movaps  [rbp+100h+var_160], xmm6
0x1800219f1  movsd   [rbp+100h+var_150], xmm8
0x1800219f7  call    cs:__imp_CSebCreateWellKnownEvent
0x1800219fd  test    eax, eax
0x1800219ff  jns     short loc_180021A24
0x180021a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a08  test    [rcx+1Ch], sil
0x180021a0c  jz      loc_180021B78
0x180021a12  cmp     byte ptr [rcx+19h], 2
0x180021a16  jb      loc_180021B78
0x180021a1c  lea     edx, [rsi+26h]
0x180021a1f  jmp     loc_180021B65
0x180021a24  mov     dword ptr [rsp+200h+var_1B8], 1038h
0x180021a2c  lea     rdx, [rbp+100h+var_C8]
0x180021a30  movups  xmm0, [rsp+200h+var_1C8+8]
0x180021a35  lea     rcx, [rbp+100h+var_180]
0x180021a39  movaps  [rbp+100h+var_170], xmm7
0x180021a3d  movaps  [rbp+100h+var_180], xmm0
0x180021a41  movaps  [rbp+100h+var_160], xmm6
0x180021a45  movsd   [rbp+100h+var_150], xmm8
0x180021a4b  call    cs:__imp_CSebCreateWellKnownEvent
0x180021a51  test    eax, eax
0x180021a53  jns     short loc_180021A7A
0x180021a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a5c  test    [rcx+1Ch], sil
0x180021a60  jz      loc_180021B78
0x180021a66  cmp     byte ptr [rcx+19h], 2
0x180021a6a  jb      loc_180021B78
0x180021a70  mov     edx, 28h ; '('
0x180021a75  jmp     loc_180021B65
0x180021a7a  xor     eax, eax
0x180021a7c  lea     r8, PsmpDisconnectedStandbyStopCallback
0x180021a83  mov     [rbp+100h+var_90], rax
0x180021a87  lea     rdx, PsmpDisconnectedStandbyStartCallback
0x180021a8e  mov     [rbp+100h+var_58], rax
0x180021a95  lea     rcx, [rbp+100h+var_140]
0x180021a99  xorps   xmm0, xmm0
0x180021a9c  mov     [rbp+100h+var_D8], rax
0x180021aa0  xorps   xmm1, xmm1
0x180021aa3  mov     byte ptr [rbp+100h+var_90], sil
0x180021aa7  movups  [rbp+100h+var_108], xmm0
0x180021aab  lea     rax, [rbp+100h+var_108]
0x180021aaf  mov     dword ptr [rbp+100h+var_108], esi
0x180021ab2  mov     qword ptr [rbp+100h+var_140+8], rax
0x180021ab6  xor     r9d, r9d
0x180021ab9  lea     rax, [rbp+100h+var_C0]
0x180021abd  mov     dword ptr [rbp+100h+var_108+8], 0
0x180021ac4  movups  [rbp+100h+var_F8], xmm0
0x180021ac8  mov     qword ptr [rbp+100h+var_F8], rax
0x180021acc  mov     rax, [rbp+100h+var_D0]
0x180021ad0  movups  [rbp+100h+var_B0], xmm1
0x180021ad4  mov     qword ptr [rbp+100h+var_B0], rax
0x180021ad8  mov     rax, [rbp+100h+var_C8]
0x180021adc  movups  [rbp+100h+var_78], xmm0
0x180021ae3  mov     qword ptr [rbp+100h+var_78], rax
0x180021aea  lea     rax, qword_18003FE80
0x180021af1  mov     qword ptr [rsp+200h+var_1C8], rax
0x180021af6  mov     dword ptr [rsp+200h+var_1D0], 0
0x180021afe  movups  [rbp+100h+var_C0], xmm1
0x180021b02  mov     qword ptr [rsp+200h+var_1D8], 0
0x180021b0b  movups  [rbp+100h+var_88], xmm0
0x180021b0f  mov     [rsp+200h+var_1E0], 0
0x180021b18  movups  [rbp+100h+var_E8], xmm0
0x180021b1c  mov     dword ptr [rbp+100h+var_108+0Ch], 2
0x180021b23  movups  [rbp+100h+var_A0], xmm1
0x180021b27  mov     dword ptr [rbp+100h+var_C0], 0
0x180021b2e  movups  [rbp+100h+var_68], xmm0
0x180021b35  mov     dword ptr [rbp+100h+var_88], 0
0x180021b3c  mov     byte ptr [rbp+100h+var_58], sil
0x180021b43  call    cs:__imp_EaCreateAggregation
0x180021b49  test    eax, eax
0x180021b4b  jns     short loc_180021B78
0x180021b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b54  test    [rcx+1Ch], sil
0x180021b58  jz      short loc_180021B78
0x180021b5a  cmp     byte ptr [rcx+19h], 2
0x180021b5e  jb      short loc_180021B78
0x180021b60  mov     edx, 29h ; ')'
0x180021b65  mov     rcx, [rcx+10h]
0x180021b69  lea     r8, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x180021b70  mov     r9d, eax
0x180021b73  call    WPP_SF_d
0x180021b78  mov     rcx, rbx; hObject
0x180021b7b  call    cs:__imp_CloseHandle
0x180021b81  mov     rcx, rdi
0x180021b84  call    cs:__imp_TpReleaseWait
0x180021b8a  mov     rcx, [rbp+100h+var_50]
0x180021b91  xor     rcx, rsp; StackCookie
0x180021b94  call    __security_check_cookie
0x180021b99  lea     r11, [rsp+200h+var_10]
0x180021ba1  mov     rbx, [r11+20h]
0x180021ba5  movaps  xmm6, xmmword ptr [r11-10h]
0x180021baa  movaps  xmm7, xmmword ptr [r11-20h]
0x180021baf  movaps  xmm8, xmmword ptr [r11-30h]
0x180021bb4  mov     rsp, r11
0x180021bb7  pop     rdi
0x180021bb8  pop     rsi
0x180021bb9  pop     rbp
0x180021bba  retn
```
