# Dhcpv6AddNICtoListEx

- ea: `0x180014e18`
- end: `0x1800152b1`
- name: `Dhcpv6AddNICtoListEx`
- size: `1177`
- prototype: `__int64 __fastcall(_QWORD *, RTL_SRWLOCK **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180010340`

## callees

- `0x180005bcc`
- `0x180005e8c`
- `0x1800075b0`
- `0x18000bc88`
- `0x18000c740`
- `0x18000fca0`
- `0x180014e18`
- `0x1800152b8`
- `0x1800157f4`
- `0x180016350`
- `0x1800179c8`
- `0x1800311c4`
- `0x180032afc`
- `0x180033900`
- `0x1800345dc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001524d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001524d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015075`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015075`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150ba`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180014e8e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180014e8e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180014e55`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180014e55`
- `WS2_32!WSACreateEvent` at `0x180014ed2`
- `WS2_32!WSACreateEvent` at `0x180014ed2`
- `WS2_32!__imp_WSAGetLastError` at `0x180014ef6`
- `WS2_32!__imp_WSAGetLastError` at `0x180014ef6`

## pseudocode

```c
__int64 __fastcall Dhcpv6AddNICtoListEx(_QWORD *a1, RTL_SRWLOCK **a2)
{
  HANDLE Semaphore; // rbp
  unsigned int Context; // eax
  RTL_SRWLOCK *v6; // rdi
  unsigned int v7; // r15d
  HANDLE v8; // rax
  int Error; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r8
  int Ptr_high; // eax
  RTL_SRWLOCK **v14; // rax
  int v15; // eax
  int Ptr; // r9d
  __int64 Ptr_low; // rcx
  __int64 v18; // r8
  int v19; // r11d
  int v20; // r10d
  int v21; // eax
  RTL_SRWLOCK *v23; // [rsp+B8h] [rbp+10h] BYREF

  v23 = 0;
  *a2 = 0;
  Semaphore = CreateSemaphoreExW(0, 1, 1, 0, 0, 0x1F0003u);
  Context = Dhcpv6MakeContext(a1, (__int64 *)&v23);
  v6 = v23;
  v7 = Context;
  if ( !Context )
  {
    InitializeSRWLock(v23 + 76);
    v6[73].Ptr = Semaphore;
    HIDWORD(v6[1112].Ptr) = 0;
    HIDWORD(v6[74].Ptr) = 0;
    v6[63].Ptr = 0;
    v6[64].Ptr = 0;
    v6[1120].Ptr = 0;
    v6[1121].Ptr = 0;
    v6[1114].Ptr = 0;
    v8 = WSACreateEvent();
    v6[1113].Ptr = v8;
    if ( !v8 && (xmmword_1800423E0 & 2) != 0 )
    {
      Error = WSAGetLastError();
      WPP_SF_qDJ(*a1, v10, v11, 0, Error, *a1);
    }
    v6[65].Ptr = 0;
    v6[66].Ptr = 0;
    v6[68].Ptr = 0;
    LOWORD(v6[69].Ptr) = 0;
    v6[72].Ptr = 0;
    v6[78].Ptr = &v6[77];
    v6[77].Ptr = &v6[77];
    v6[80].Ptr = &v6[79];
    v6[79].Ptr = &v6[79];
    v6[14].Ptr = &v6[13];
    v6[13].Ptr = &v6[13];
    v6[16].Ptr = &v6[15];
    v6[15].Ptr = &v6[15];
    v6[23].Ptr = &v6[22];
    v6[22].Ptr = &v6[22];
    LODWORD(v6[1115].Ptr) = 1;
    HIDWORD(v6[1115].Ptr) = 128;
    if ( (unsigned int)DhcpIsFSEGuestSystem() )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 56, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      RefillDhcpv6Context((__int64)v6);
    }
    else
    {
      Dhcpv6RegFillParams((__int64)v6, 1, v12);
      Dhcpv6RegFillSendOptions((_DWORD)v6 + 616, (__int64)v6[7].Ptr, v6[82].Ptr, (int)v6[83].Ptr);
    }
    if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
      LODWORD(v6[1111].Ptr) = 0;
    else
      HIDWORD(v6[1107].Ptr) &= 0xFFFFFE7F;
    if ( LODWORD(v6[1129].Ptr) )
    {
      InitializeInterfaceIaid(v6);
      goto LABEL_17;
    }
    if ( LODWORD(v6[17].Ptr) || (v7 = Dhcpv6GenerateAndStoreInterfaceIaid(v6)) == 0 )
    {
LABEL_17:
      Dhcpv6RegReadClassId((__int64)v6);
      if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
        Ptr_high = HIDWORD(v6[1109].Ptr);
      else
        Ptr_high = (HIDWORD(v6[1107].Ptr) >> 4) & 1;
      if ( Ptr_high )
        Dhcpv6RegReadOptionCache((__int64)&v6[79], (HKEY)v6[81].Ptr);
      EnterCriticalSection(&Dhcpv6GlobalNicListCritSect);
      v14 = (RTL_SRWLOCK **)off_1800420A8;
      if ( *off_1800420A8 != (_UNKNOWN *)&Dhcpv6GlobalNICList )
        __fastfail(3u);
      v6->Ptr = &Dhcpv6GlobalNICList;
      v6[1].Ptr = v14;
      *v14 = v6;
      off_1800420A8 = (_UNKNOWN **)v6;
      _InterlockedAdd(&Dhcpv6GlobalAdaptersCount, 1u);
      LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
      if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
      {
        if ( (xmmword_1800423E0 & 0x10) != 0 )
        {
          v15 = g_fVelocityDhcpv6ContextBitfieldUpdate;
          if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
          {
            Ptr = (int)v6[1111].Ptr;
            v15 = g_fVelocityDhcpv6ContextBitfieldUpdate;
          }
          else
          {
            Ptr = (HIDWORD(v6[1107].Ptr) >> 7) & 3;
          }
          if ( v15 )
          {
            Ptr_low = LODWORD(v6[1109].Ptr);
            v15 = g_fVelocityDhcpv6ContextBitfieldUpdate;
          }
          else
          {
            Ptr_low = (HIDWORD(v6[1107].Ptr) >> 3) & 1;
          }
          if ( v15 )
          {
            v18 = HIDWORD(v6[1108].Ptr);
            v15 = g_fVelocityDhcpv6ContextBitfieldUpdate;
          }
          else
          {
            v18 = (HIDWORD(v6[1107].Ptr) >> 1) & 1;
          }
          if ( v15 )
          {
            v19 = (int)v6[1108].Ptr;
            v15 = g_fVelocityDhcpv6ContextBitfieldUpdate;
          }
          else
          {
            v19 = HIDWORD(v6[1107].Ptr) & 1;
          }
          if ( v15 )
          {
            v20 = (int)v6[1110].Ptr;
            v15 = g_fVelocityDhcpv6ContextBitfieldUpdate;
          }
          else
          {
            v20 = (HIDWORD(v6[1107].Ptr) >> 5) & 1;
          }
          if ( v15 )
            v21 = HIDWORD(v6[1109].Ptr);
          else
            v21 = (HIDWORD(v6[1107].Ptr) >> 4) & 1;
          WPP_SF_qllllldl(Ptr_low, 57, v18, v6, v21, v20, v19, v18, Ptr_low, Ptr, HIDWORD(v6[1111].Ptr));
        }
      }
      else if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        WPP_SF_qllllldl(
          HIDWORD(v6[1107].Ptr) & 1,
          58,
          (HIDWORD(v6[1107].Ptr) >> 1) & 1,
          v6,
          (HIDWORD(v6[1107].Ptr) >> 4) & 1,
          (HIDWORD(v6[1107].Ptr) >> 5) & 1,
          HIDWORD(v6[1107].Ptr) & 1,
          (HIDWORD(v6[1107].Ptr) >> 1) & 1,
          (HIDWORD(v6[1107].Ptr) >> 3) & 1,
          (HIDWORD(v6[1107].Ptr) >> 7) & 3,
          (HIDWORD(v6[1107].Ptr) >> 9) & 1);
      }
      goto LABEL_54;
    }
  }
  if ( Semaphore != (HANDLE)-1LL )
    CloseHandle(Semaphore);
  if ( v6 )
  {
    DhcpFree((LPVOID *)&v23);
    v6 = 0;
  }
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_dJ(1025, 59, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v7, *a1);
LABEL_54:
  *a2 = v6;
  return v7;
}

```

## disassembly

```asm
0x180014e18  mov     rax, rsp
0x180014e1b  push    rbx
0x180014e1c  push    rbp
0x180014e1d  push    rsi
0x180014e1e  push    rdi
0x180014e1f  push    r12
0x180014e21  push    r13
0x180014e23  push    r14
0x180014e25  push    r15
0x180014e27  sub     rsp, 68h
0x180014e2b  xor     r13d, r13d
0x180014e2e  mov     dword ptr [rax-80h], 1F0003h
0x180014e35  mov     [rax+10h], r13
0x180014e39  mov     r12, rdx
0x180014e3c  mov     r14, rcx
0x180014e3f  mov     [rdx], r13
0x180014e42  xor     r9d, r9d; lpName
0x180014e45  mov     [rsp+0A8h+dwFlags], r13d; dwFlags
0x180014e4a  lea     eax, [r13+1]
0x180014e4e  xor     ecx, ecx; lpSemaphoreAttributes
0x180014e50  mov     r8d, eax; lMaximumCount
0x180014e53  mov     edx, eax; lInitialCount
0x180014e55  call    cs:__imp_CreateSemaphoreExW
0x180014e5c  nop     dword ptr [rax+rax+00h]
0x180014e61  lea     rdx, [rsp+0A8h+arg_8]
0x180014e69  mov     rcx, r14
0x180014e6c  mov     rbp, rax
0x180014e6f  call    Dhcpv6MakeContext
0x180014e74  mov     rdi, [rsp+0A8h+arg_8]
0x180014e7c  mov     r15d, eax
0x180014e7f  test    eax, eax
0x180014e81  jnz     loc_180015244
0x180014e87  lea     rcx, [rdi+260h]; SRWLock
0x180014e8e  call    cs:__imp_InitializeSRWLock
0x180014e95  nop     dword ptr [rax+rax+00h]
0x180014e9a  mov     [rdi+248h], rbp
0x180014ea1  mov     [rdi+22C4h], r13d
0x180014ea8  mov     [rdi+254h], r13d
0x180014eaf  mov     [rdi+1F8h], r13
0x180014eb6  mov     [rdi+200h], r13
0x180014ebd  mov     [rdi+2300h], r13
0x180014ec4  mov     [rdi+2308h], r13
0x180014ecb  mov     [rdi+22D0h], r13
0x180014ed2  call    cs:__imp_WSACreateEvent
0x180014ed9  nop     dword ptr [rax+rax+00h]
0x180014ede  mov     [rdi+22C8h], rax
0x180014ee5  mov     rbx, rax
0x180014ee8  test    rax, rax
0x180014eeb  jnz     short loc_180014F16
0x180014eed  test    byte ptr cs:xmmword_1800423E0, 2
0x180014ef4  jz      short loc_180014F16
0x180014ef6  call    cs:__imp_WSAGetLastError
0x180014efd  nop     dword ptr [rax+rax+00h]
0x180014f02  mov     rcx, [r14]
0x180014f05  mov     r9, rbx
0x180014f08  mov     [rsp+0A8h+var_80], rcx
0x180014f0d  mov     [rsp+0A8h+dwFlags], eax
0x180014f11  call    WPP_SF_qDJ
0x180014f16  mov     [rdi+208h], r13
0x180014f1d  lea     rax, [rdi+68h]
0x180014f21  mov     [rdi+210h], r13
0x180014f28  lea     rbx, [rdi+268h]
0x180014f2f  mov     [rdi+220h], r13
0x180014f36  lea     rsi, [rdi+278h]
0x180014f3d  mov     [rdi+228h], r13w
0x180014f45  mov     [rdi+240h], r13
0x180014f4c  mov     [rbx+8], rbx
0x180014f50  mov     [rbx], rbx
0x180014f53  mov     [rsi+8], rsi
0x180014f57  mov     [rsi], rsi
0x180014f5a  mov     [rax+8], rax
0x180014f5e  mov     [rax], rax
0x180014f61  lea     rax, [rdi+78h]
0x180014f65  mov     [rax+8], rax
0x180014f69  mov     [rax], rax
0x180014f6c  lea     rax, [rdi+0B0h]
0x180014f73  mov     [rax+8], rax
0x180014f77  mov     [rax], rax
0x180014f7a  mov     dword ptr [rdi+22D8h], 1
0x180014f84  mov     dword ptr [rdi+22DCh], 80h
0x180014f8e  call    DhcpIsFSEGuestSystem
0x180014f93  test    eax, eax
0x180014f95  jz      short loc_180014FC0
0x180014f97  test    byte ptr cs:xmmword_1800423E0, 10h
0x180014f9e  jz      short loc_180014FB6
0x180014fa0  mov     edx, 38h ; '8'
0x180014fa5  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180014fac  mov     ecx, 404h
0x180014fb1  call    WPP_SF_
0x180014fb6  mov     rcx, rdi
0x180014fb9  call    RefillDhcpv6Context
0x180014fbe  jmp     short loc_180014FE7
0x180014fc0  mov     edx, 1
0x180014fc5  mov     rcx, rdi
0x180014fc8  call    Dhcpv6RegFillParams
0x180014fcd  mov     r9d, [rdi+298h]
0x180014fd4  mov     rcx, rbx
0x180014fd7  mov     r8, [rdi+290h]
0x180014fde  mov     rdx, [rdi+38h]
0x180014fe2  call    Dhcpv6RegFillSendOptions
0x180014fe7  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, r13d
0x180014fee  jz      short loc_180014FF9
0x180014ff0  mov     [rdi+22B8h], r13d
0x180014ff7  jmp     short loc_180015003
0x180014ff9  and     dword ptr [rdi+229Ch], 0FFFFFE7Fh
0x180015003  cmp     [rdi+2348h], r13d
0x18001500a  jz      short loc_180015016
0x18001500c  mov     rcx, rdi
0x18001500f  call    InitializeInterfaceIaid
0x180015014  jmp     short loc_180015032
0x180015016  cmp     [rdi+88h], r13d
0x18001501d  jnz     short loc_180015032
0x18001501f  mov     rcx, rdi
0x180015022  call    Dhcpv6GenerateAndStoreInterfaceIaid
0x180015027  mov     r15d, eax
0x18001502a  test    eax, eax
0x18001502c  jnz     loc_180015244
0x180015032  mov     rcx, rdi
0x180015035  call    Dhcpv6RegReadClassId
0x18001503a  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, r13d
0x180015041  mov     ebp, 1
0x180015046  jz      short loc_180015050
0x180015048  mov     eax, [rdi+22ACh]
0x18001504e  jmp     short loc_18001505B
0x180015050  mov     eax, [rdi+229Ch]
0x180015056  shr     eax, 4
0x180015059  and     eax, ebp
0x18001505b  test    eax, eax
0x18001505d  jz      short loc_18001506E
0x18001505f  mov     rdx, [rdi+288h]
0x180015066  mov     rcx, rsi
0x180015069  call    Dhcpv6RegReadOptionCache
0x18001506e  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x180015075  call    cs:__imp_EnterCriticalSection
0x18001507c  nop     dword ptr [rax+rax+00h]
0x180015081  mov     rax, cs:off_1800420A8
0x180015088  lea     rcx, Dhcpv6GlobalNICList
0x18001508f  cmp     [rax], rcx
0x180015092  jz      short loc_18001509B
0x180015094  mov     ecx, 3
0x180015099  int     29h; Win8: RtlFailFast(ecx)
0x18001509b  mov     [rdi], rcx
0x18001509e  mov     [rdi+8], rax
0x1800150a2  mov     [rax], rdi
0x1800150a5  mov     cs:off_1800420A8, rdi
0x1800150ac  lock add cs:Dhcpv6GlobalAdaptersCount, ebp
0x1800150b3  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x1800150ba  call    cs:__imp_LeaveCriticalSection
0x1800150c1  nop     dword ptr [rax+rax+00h]
0x1800150c6  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, r13d
0x1800150cd  jz      loc_1800151D2
0x1800150d3  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800150da  jz      loc_180015298
0x1800150e0  mov     ebx, [rdi+22BCh]
0x1800150e6  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800150ec  test    eax, eax
0x1800150ee  jz      short loc_1800150FF
0x1800150f0  mov     r9d, [rdi+22B8h]
0x1800150f7  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x1800150fd  jmp     short loc_18001510E
0x1800150ff  mov     r9d, [rdi+229Ch]
0x180015106  shr     r9d, 7
0x18001510a  and     r9d, 3
0x18001510e  test    eax, eax
0x180015110  jz      short loc_180015120
0x180015112  mov     ecx, [rdi+22A8h]
0x180015118  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001511e  jmp     short loc_18001512B
0x180015120  mov     ecx, [rdi+229Ch]
0x180015126  shr     ecx, 3
0x180015129  and     ecx, ebp
0x18001512b  test    eax, eax
0x18001512d  jz      short loc_18001513E
0x18001512f  mov     r8d, [rdi+22A4h]
0x180015136  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001513c  jmp     short loc_18001514B
0x18001513e  mov     r8d, [rdi+229Ch]
0x180015145  shr     r8d, 1
0x180015148  and     r8d, ebp
0x18001514b  test    eax, eax
0x18001514d  jz      short loc_18001515E
0x18001514f  mov     r11d, [rdi+22A0h]
0x180015156  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001515c  jmp     short loc_180015168
0x18001515e  mov     r11d, [rdi+229Ch]
0x180015165  and     r11d, ebp
0x180015168  test    eax, eax
0x18001516a  jz      short loc_18001517B
0x18001516c  mov     r10d, [rdi+22B0h]
0x180015173  mov     eax, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x180015179  jmp     short loc_180015189
0x18001517b  mov     r10d, [rdi+229Ch]
0x180015182  shr     r10d, 5
0x180015186  and     r10d, ebp
0x180015189  test    eax, eax
0x18001518b  jz      short loc_180015195
0x18001518d  mov     eax, [rdi+22ACh]
0x180015193  jmp     short loc_1800151A0
0x180015195  mov     eax, [rdi+229Ch]
0x18001519b  shr     eax, 4
0x18001519e  and     eax, ebp
0x1800151a0  mov     [rsp+0A8h+var_58], ebx
0x1800151a4  mov     edx, 39h ; '9'
0x1800151a9  mov     [rsp+0A8h+var_60], r9d
0x1800151ae  mov     [rsp+0A8h+var_68], ecx
0x1800151b2  mov     [rsp+0A8h+var_70], r8d
0x1800151b7  mov     [rsp+0A8h+var_78], r11d
0x1800151bc  mov     dword ptr [rsp+0A8h+var_80], r10d
0x1800151c1  mov     [rsp+0A8h+dwFlags], eax
0x1800151c5  mov     r9, rdi
0x1800151c8  call    WPP_SF_qllllldl
0x1800151cd  jmp     loc_180015298
0x1800151d2  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800151d9  jz      loc_180015298
0x1800151df  mov     ebx, [rdi+229Ch]
0x1800151e5  mov     edx, 3Ah ; ':'
0x1800151ea  mov     r11d, ebx
0x1800151ed  mov     r10d, ebx
0x1800151f0  mov     r9d, ebx
0x1800151f3  shr     r11d, 9
0x1800151f7  mov     r8d, ebx
0x1800151fa  shr     r10d, 7
0x1800151fe  mov     eax, ebx
0x180015200  shr     r9d, 3
0x180015204  mov     ecx, ebx
0x180015206  shr     r8d, 1
0x180015209  and     r11d, ebp
0x18001520c  shr     eax, 5
0x18001520f  mov     [rsp+0A8h+var_58], r11d
0x180015214  and     r10d, 3
0x180015218  mov     [rsp+0A8h+var_60], r10d
0x18001521d  and     r9d, ebp
0x180015220  mov     [rsp+0A8h+var_68], r9d
0x180015225  and     r8d, ebp
0x180015228  mov     [rsp+0A8h+var_70], r8d
0x18001522d  and     ecx, ebp
0x18001522f  and     eax, ebp
0x180015231  mov     [rsp+0A8h+var_78], ecx
0x180015235  shr     ebx, 4
0x180015238  and     ebx, ebp
0x18001523a  mov     dword ptr [rsp+0A8h+var_80], eax
0x18001523e  mov     [rsp+0A8h+dwFlags], ebx
0x180015242  jmp     short loc_1800151C5
0x180015244  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180015248  jz      short loc_180015259
0x18001524a  mov     rcx, rbp; hObject
0x18001524d  call    cs:__imp_CloseHandle
0x180015254  nop     dword ptr [rax+rax+00h]
0x180015259  test    rdi, rdi
0x18001525c  jz      short loc_18001526E
0x18001525e  lea     rcx, [rsp+0A8h+arg_8]
0x180015266  call    DhcpFree
0x18001526b  mov     rdi, r13
0x18001526e  test    byte ptr cs:xmmword_1800423E0, 2
0x180015275  jz      short loc_180015298
0x180015277  mov     rax, [r14]
0x18001527a  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180015281  mov     edx, 3Bh ; ';'
0x180015286  mov     qword ptr [rsp+0A8h+dwFlags], rax
0x18001528b  mov     ecx, 401h
0x180015290  mov     r9d, r15d
0x180015293  call    WPP_SF_dJ
0x180015298  mov     [r12], rdi
0x18001529c  mov     eax, r15d
0x18001529f  add     rsp, 68h
0x1800152a3  pop     r15
0x1800152a5  pop     r14
0x1800152a7  pop     r13
0x1800152a9  pop     r12
0x1800152ab  pop     rdi
0x1800152ac  pop     rsi
0x1800152ad  pop     rbp
0x1800152ae  pop     rbx
0x1800152af  retn
```
