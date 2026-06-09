# DeviceEncryptionResourceManager::CheckForNetworkReadyNoLock(bool *)

- ea: `0x18001472c`
- end: `0x1800148cb`
- name: `?CheckForNetworkReadyNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z`
- size: `415`
- prototype: `__int64 __fastcall(DeviceEncryptionResourceManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014564`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x180014030`
- `0x180014538`
- `0x18001472c`
- `0x180015820`
- `0x180016628`

## pseudocode

```c
__int64 __fastcall DeviceEncryptionResourceManager::CheckForNetworkReadyNoLock(
        DeviceEncryptionResourceManager *this,
        bool *a2)
{
  int v2; // eax
  unsigned int v5; // eax
  unsigned int v6; // edx
  int v7; // ebx
  FveEasNetworkStatus *v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int CurrentStatus; // eax
  char v13; // [rsp+40h] [rbp+8h] BYREF
  struct FveEasNetworkStatus *v14; // [rsp+48h] [rbp+10h] BYREF

  v2 = *((_DWORD *)this + 23);
  v13 = 0;
  *a2 = 0;
  if ( v2 != -1 )
  {
    v7 = 0;
LABEL_22:
    if ( v2 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
      *a2 = 1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
    }
    return (unsigned int)v7;
  }
  if ( !*((_QWORD *)this + 12) )
  {
    v14 = 0;
    v5 = FveEasNetworkStatus::Create(&v14);
    v7 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v5);
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
    v8 = (FveEasNetworkStatus *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = v14;
    if ( v8 )
      FveEasNetworkStatus::`scalar deleting destructor'(v8, v6);
  }
  v9 = *((_QWORD *)this + 12);
  v14 = this;
  v10 = FveEasNetworkStatus::RegisterForStatusChange__lambda_08ba28ade71fe181232279e2da981e97___(v9, &v14);
  v7 = v10;
  if ( !v10 )
    goto LABEL_19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v10);
  if ( v7 >= 0 )
  {
LABEL_19:
    CurrentStatus = FveEasNetworkStatusImpl::GetCurrentStatus(**((_QWORD **)this + 12) + 8LL, &v13);
    v7 = CurrentStatus;
    if ( !CurrentStatus )
      goto LABEL_20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, CurrentStatus);
    if ( v7 >= 0 )
    {
LABEL_20:
      v2 = v13 != 0;
      *((_DWORD *)this + 23) = v2;
      goto LABEL_22;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001472c  mov     r11, rsp
0x18001472f  mov     [r11+18h], rbx
0x180014733  mov     [r11+20h], rsi
0x180014737  push    rdi
0x180014738  push    r14
0x18001473a  push    r15
0x18001473c  sub     rsp, 20h
0x180014740  mov     eax, [rcx+5Ch]
0x180014743  lea     r14, WPP_GLOBAL_Control
0x18001474a  mov     [rsp+38h+arg_0], 0
0x18001474f  mov     rsi, rdx
0x180014752  mov     byte ptr [rdx], 0
0x180014755  mov     rdi, rcx
0x180014758  lea     r15, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x18001475f  cmp     eax, 0FFFFFFFFh
0x180014762  jnz     loc_180014865
0x180014768  cmp     qword ptr [rcx+60h], 0
0x18001476d  jnz     short loc_1800147CB
0x18001476f  lea     rcx, [r11+10h]; struct FveEasNetworkStatus **
0x180014773  mov     qword ptr [r11+10h], 0
0x18001477b  call    ?Create@FveEasNetworkStatus@@SAJPEAPEAV1@@Z; FveEasNetworkStatus::Create(FveEasNetworkStatus * *)
0x180014780  mov     ebx, eax
0x180014782  test    eax, eax
0x180014784  jz      short loc_1800147B4
0x180014786  mov     rcx, cs:WPP_GLOBAL_Control
0x18001478d  cmp     rcx, r14
0x180014790  jz      short loc_1800147AC
0x180014792  test    byte ptr [rcx+1Ch], 40h
0x180014796  jz      short loc_1800147AC
0x180014798  mov     rcx, [rcx+10h]
0x18001479c  mov     edx, 3Ah ; ':'
0x1800147a1  mov     r9d, eax
0x1800147a4  mov     r8, r15
0x1800147a7  call    WPP_SF_d
0x1800147ac  test    ebx, ebx
0x1800147ae  js      loc_1800148B5
0x1800147b4  mov     rcx, [rdi+60h]; this
0x1800147b8  mov     rax, [rsp+38h+arg_8]
0x1800147bd  mov     [rdi+60h], rax
0x1800147c1  test    rcx, rcx
0x1800147c4  jz      short loc_1800147CB
0x1800147c6  call    ??_GFveEasNetworkStatus@@QEAAPEAXI@Z; FveEasNetworkStatus::`scalar deleting destructor'(uint)
0x1800147cb  mov     rcx, [rdi+60h]
0x1800147cf  lea     rdx, [rsp+38h+arg_8]
0x1800147d4  mov     [rsp+38h+arg_8], rdi
0x1800147d9  call    FveEasNetworkStatus__RegisterForStatusChange__lambda_08ba28ade71fe181232279e2da981e97___
0x1800147de  mov     ebx, eax
0x1800147e0  test    eax, eax
0x1800147e2  jz      short loc_180014812
0x1800147e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147eb  cmp     rcx, r14
0x1800147ee  jz      short loc_18001480A
0x1800147f0  test    byte ptr [rcx+1Ch], 40h
0x1800147f4  jz      short loc_18001480A
0x1800147f6  mov     rcx, [rcx+10h]
0x1800147fa  mov     edx, 3Bh ; ';'
0x1800147ff  mov     r9d, eax
0x180014802  mov     r8, r15
0x180014805  call    WPP_SF_d
0x18001480a  test    ebx, ebx
0x18001480c  js      loc_1800148B5
0x180014812  mov     rax, [rdi+60h]
0x180014816  lea     rdx, [rsp+38h+arg_0]
0x18001481b  mov     rcx, [rax]
0x18001481e  add     rcx, 8
0x180014822  call    ?GetCurrentStatus@FveEasNetworkStatusImpl@@SAJAEBV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@AEAUFveEasNetworkStatusArgs@@@Z; FveEasNetworkStatusImpl::GetCurrentStatus(Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> const &,FveEasNetworkStatusArgs &)
0x180014827  mov     ebx, eax
0x180014829  test    eax, eax
0x18001482b  jz      short loc_180014857
0x18001482d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014834  cmp     rcx, r14
0x180014837  jz      short loc_180014853
0x180014839  test    byte ptr [rcx+1Ch], 40h
0x18001483d  jz      short loc_180014853
0x18001483f  mov     rcx, [rcx+10h]
0x180014843  mov     edx, 3Ch ; '<'
0x180014848  mov     r9d, eax
0x18001484b  mov     r8, r15
0x18001484e  call    WPP_SF_d
0x180014853  test    ebx, ebx
0x180014855  js      short loc_1800148B5
0x180014857  xor     eax, eax
0x180014859  cmp     [rsp+38h+arg_0], al
0x18001485d  setnz   al
0x180014860  mov     [rdi+5Ch], eax
0x180014863  jmp     short loc_180014867
0x180014865  xor     ebx, ebx
0x180014867  cmp     eax, 1
0x18001486a  jnz     short loc_180014892
0x18001486c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014873  cmp     rcx, r14
0x180014876  jz      short loc_18001488D
0x180014878  test    byte ptr [rcx+1Ch], 8
0x18001487c  jz      short loc_18001488D
0x18001487e  mov     rcx, [rcx+10h]
0x180014882  lea     edx, [rax+3Ch]
0x180014885  mov     r8, r15
0x180014888  call    WPP_SF_
0x18001488d  mov     byte ptr [rsi], 1
0x180014890  jmp     short loc_1800148B5
0x180014892  mov     rcx, cs:WPP_GLOBAL_Control
0x180014899  cmp     rcx, r14
0x18001489c  jz      short loc_1800148B5
0x18001489e  test    byte ptr [rcx+1Ch], 8
0x1800148a2  jz      short loc_1800148B5
0x1800148a4  mov     rcx, [rcx+10h]
0x1800148a8  mov     edx, 3Eh ; '>'
0x1800148ad  mov     r8, r15
0x1800148b0  call    WPP_SF_
0x1800148b5  mov     rsi, [rsp+38h+arg_18]
0x1800148ba  mov     eax, ebx
0x1800148bc  mov     rbx, [rsp+38h+arg_10]
0x1800148c1  add     rsp, 20h
0x1800148c5  pop     r15
0x1800148c7  pop     r14
0x1800148c9  pop     rdi
0x1800148ca  retn
```
