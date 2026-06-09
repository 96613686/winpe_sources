# NatDeregisterCallout

- ea: `0x1400292ac`
- end: `0x14002983f`
- name: `NatDeregisterCallout`
- size: `1427`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ca0`
- `0x14002adb0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400292ac`

## import_xrefs

- `fwpkclnt!FwpsInjectionHandleDestroy0` at `0x1400297ba`
- `fwpkclnt!FwpsInjectionHandleDestroy0` at `0x1400297ba`
- `fwpkclnt!FwpmEngineOpen0` at `0x14002938b`
- `fwpkclnt!FwpmEngineOpen0` at `0x14002938b`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400295ca`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140029617`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140029664`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400296b1`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400296fe`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400295ca`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140029617`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x140029664`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400296b1`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x1400296fe`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14002940e`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x140029457`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x1400294a0`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x1400294e6`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14002952f`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14002957c`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14002940e`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x140029457`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x1400294a0`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x1400294e6`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14002952f`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14002957c`
- `fwpkclnt!FwpmEngineClose0` at `0x140029744`
- `fwpkclnt!FwpmEngineClose0` at `0x140029744`

## pseudocode

```c
__int64 __fastcall NatDeregisterCallout(int a1)
{
  PDEVICE_OBJECT v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  HANDLE engineHandle; // [rsp+58h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
  }
  engineHandle = 0;
  if ( !IsNatCalloutActive )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 0;
    }
    v3 = 69;
LABEL_104:
    WPP_SF_d(v2->AttachedDevice, v3, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, 0);
    return 0;
  }
  IsNatCalloutActive = 0;
  v4 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( !v4 )
  {
    v6 = FwpmFilterDeleteByKey0(engineHandle, &key);
    if ( v6
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v6);
    }
    v7 = FwpmFilterDeleteByKey0(engineHandle, &stru_14002FA68);
    if ( v7
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v7);
    }
    if ( FwpmFilterDeleteByKey0(engineHandle, &stru_14002FA78)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
    }
    v8 = FwpmFilterDeleteByKey0(engineHandle, &stru_14002FAF8);
    if ( v8
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v8);
    }
    v9 = FwpmFilterDeleteByKey0(engineHandle, &stru_14002FA48);
    if ( v9
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v9);
    }
    if ( a1 )
    {
      v10 = FwpmFilterDeleteByKey0(engineHandle, &stru_14002FAB8);
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v10);
        }
      }
    }
    do
      v11 = FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_14002FAC8);
    while ( v11 == -1071513590 );
    if ( v11
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v11);
    }
    do
      v12 = FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_14002FAA8);
    while ( v12 == -1071513590 );
    if ( v12
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v12);
    }
    do
      v13 = FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_14002FAD8);
    while ( v13 == -1071513590 );
    if ( v13
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v13);
    }
    do
      v14 = FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_14002FA88);
    while ( v14 == -1071513590 );
    if ( v14
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v14);
    }
    do
      v15 = FwpiCalloutUnregisterAndDeleteByKey0(engineHandle, &xmmword_14002FA98);
    while ( v15 == -1071513590 );
    if ( v15
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v15);
    }
    v16 = FwpmEngineClose0(engineHandle);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_94:
        if ( gNetworkInjectionHandle != (HANDLE)-1LL )
        {
          FwpsInjectionHandleDestroy0(gNetworkInjectionHandle);
          gNetworkInjectionHandle = (HANDLE)-1LL;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return 0;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
        {
          return 0;
        }
        v3 = 84;
        goto LABEL_104;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v16);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
    }
    goto LABEL_94;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, 3221225473LL);
    }
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400292ac  mov     [rsp-18h+arg_0], rbx
0x1400292b1  mov     [rsp-18h+arg_10], rsi
0x1400292b6  push    rbp
0x1400292b7  push    rdi
0x1400292b8  push    r15
0x1400292ba  mov     rbp, rsp
0x1400292bd  sub     rsp, 30h
0x1400292c1  mov     ebx, ecx
0x1400292c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400292ca  lea     rsi, WPP_GLOBAL_Control
0x1400292d1  lea     r15, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x1400292d8  mov     dil, 2
0x1400292db  cmp     rcx, rsi
0x1400292de  jz      short loc_1400292FF
0x1400292e0  mov     eax, [rcx+2Ch]
0x1400292e3  test    dil, al
0x1400292e6  jz      short loc_1400292FF
0x1400292e8  cmp     byte ptr [rcx+29h], 6
0x1400292ec  jb      short loc_1400292FF
0x1400292ee  mov     rcx, [rcx+18h]
0x1400292f2  mov     edx, 43h ; 'C'
0x1400292f7  mov     r8, r15
0x1400292fa  call    WPP_SF_
0x1400292ff  cmp     cs:IsNatCalloutActive, 0
0x140029306  mov     [rbp+arg_8], 0
0x14002930e  jnz     short loc_14002936F
0x140029310  mov     rcx, cs:WPP_GLOBAL_Control
0x140029317  cmp     rcx, rsi
0x14002931a  jz      loc_140029829
0x140029320  mov     eax, [rcx+2Ch]
0x140029323  test    dil, al
0x140029326  jz      short loc_14002933F
0x140029328  cmp     byte ptr [rcx+29h], 5
0x14002932c  jb      short loc_14002933F
0x14002932e  mov     rcx, [rcx+18h]
0x140029332  mov     edx, 44h ; 'D'
0x140029337  mov     r8, r15
0x14002933a  call    WPP_SF_
0x14002933f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029346  cmp     rcx, rsi
0x140029349  jz      loc_140029829
0x14002934f  mov     eax, [rcx+2Ch]
0x140029352  test    dil, al
0x140029355  jz      loc_140029829
0x14002935b  cmp     byte ptr [rcx+29h], 6
0x14002935f  jb      loc_140029829
0x140029365  mov     edx, 45h ; 'E'
0x14002936a  jmp     loc_14002981A
0x14002936f  xor     r9d, r9d; session
0x140029372  mov     cs:IsNatCalloutActive, 0
0x140029379  lea     rax, [rbp+arg_8]
0x14002937d  xor     r8d, r8d; authIdentity
0x140029380  xor     ecx, ecx; serverName
0x140029382  mov     [rsp+30h+engineHandle], rax; engineHandle
0x140029387  lea     edx, [r9+0Ah]; authnService
0x14002938b  call    cs:__imp_FwpmEngineOpen0
0x140029392  nop     dword ptr [rax+rax+00h]
0x140029397  test    eax, eax
0x140029399  jz      short loc_140029403
0x14002939b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400293a2  mov     ebx, 0C0000001h
0x1400293a7  cmp     rcx, rsi
0x1400293aa  jz      short loc_1400293FC
0x1400293ac  mov     edx, [rcx+2Ch]
0x1400293af  test    dil, dl
0x1400293b2  jz      short loc_1400293CE
0x1400293b4  cmp     [rcx+29h], dil
0x1400293b8  jb      short loc_1400293CE
0x1400293ba  mov     rcx, [rcx+18h]
0x1400293be  mov     edx, 46h ; 'F'
0x1400293c3  mov     r9d, eax
0x1400293c6  mov     r8, r15
0x1400293c9  call    WPP_SF_d
0x1400293ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400293d5  cmp     rcx, rsi
0x1400293d8  jz      short loc_1400293FC
0x1400293da  mov     edx, [rcx+2Ch]
0x1400293dd  test    dil, dl
0x1400293e0  jz      short loc_1400293FC
0x1400293e2  cmp     byte ptr [rcx+29h], 6
0x1400293e6  jb      short loc_1400293FC
0x1400293e8  mov     rcx, [rcx+18h]
0x1400293ec  mov     edx, 47h ; 'G'
0x1400293f1  mov     r9d, ebx
0x1400293f4  mov     r8, r15
0x1400293f7  call    WPP_SF_d
0x1400293fc  mov     eax, ebx
0x1400293fe  jmp     loc_14002982B
0x140029403  mov     rcx, [rbp+arg_8]; engineHandle
0x140029407  lea     rdx, key; key
0x14002940e  call    cs:__imp_FwpmFilterDeleteByKey0
0x140029415  nop     dword ptr [rax+rax+00h]
0x14002941a  test    eax, eax
0x14002941c  jz      short loc_14002944C
0x14002941e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029425  cmp     rcx, rsi
0x140029428  jz      short loc_14002944C
0x14002942a  mov     edx, [rcx+2Ch]
0x14002942d  test    dil, dl
0x140029430  jz      short loc_14002944C
0x140029432  cmp     [rcx+29h], dil
0x140029436  jb      short loc_14002944C
0x140029438  mov     rcx, [rcx+18h]
0x14002943c  mov     edx, 48h ; 'H'
0x140029441  mov     r9d, eax
0x140029444  mov     r8, r15
0x140029447  call    WPP_SF_d
0x14002944c  mov     rcx, [rbp+arg_8]; engineHandle
0x140029450  lea     rdx, stru_14002FA68; key
0x140029457  call    cs:__imp_FwpmFilterDeleteByKey0
0x14002945e  nop     dword ptr [rax+rax+00h]
0x140029463  test    eax, eax
0x140029465  jz      short loc_140029495
0x140029467  mov     rcx, cs:WPP_GLOBAL_Control
0x14002946e  cmp     rcx, rsi
0x140029471  jz      short loc_140029495
0x140029473  mov     edx, [rcx+2Ch]
0x140029476  test    dil, dl
0x140029479  jz      short loc_140029495
0x14002947b  cmp     [rcx+29h], dil
0x14002947f  jb      short loc_140029495
0x140029481  mov     rcx, [rcx+18h]
0x140029485  mov     edx, 49h ; 'I'
0x14002948a  mov     r9d, eax
0x14002948d  mov     r8, r15
0x140029490  call    WPP_SF_d
0x140029495  mov     rcx, [rbp+arg_8]; engineHandle
0x140029499  lea     rdx, stru_14002FA78; key
0x1400294a0  call    cs:__imp_FwpmFilterDeleteByKey0
0x1400294a7  nop     dword ptr [rax+rax+00h]
0x1400294ac  test    eax, eax
0x1400294ae  jz      short loc_1400294DB
0x1400294b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400294b7  cmp     rcx, rsi
0x1400294ba  jz      short loc_1400294DB
0x1400294bc  mov     eax, [rcx+2Ch]
0x1400294bf  test    dil, al
0x1400294c2  jz      short loc_1400294DB
0x1400294c4  cmp     [rcx+29h], dil
0x1400294c8  jb      short loc_1400294DB
0x1400294ca  mov     rcx, [rcx+18h]
0x1400294ce  mov     edx, 4Ah ; 'J'
0x1400294d3  mov     r8, r15
0x1400294d6  call    WPP_SF_
0x1400294db  mov     rcx, [rbp+arg_8]; engineHandle
0x1400294df  lea     rdx, stru_14002FAF8; key
0x1400294e6  call    cs:__imp_FwpmFilterDeleteByKey0
0x1400294ed  nop     dword ptr [rax+rax+00h]
0x1400294f2  test    eax, eax
0x1400294f4  jz      short loc_140029524
0x1400294f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400294fd  cmp     rcx, rsi
0x140029500  jz      short loc_140029524
0x140029502  mov     edx, [rcx+2Ch]
0x140029505  test    dil, dl
0x140029508  jz      short loc_140029524
0x14002950a  cmp     [rcx+29h], dil
0x14002950e  jb      short loc_140029524
0x140029510  mov     rcx, [rcx+18h]
0x140029514  mov     edx, 4Bh ; 'K'
0x140029519  mov     r9d, eax
0x14002951c  mov     r8, r15
0x14002951f  call    WPP_SF_d
0x140029524  mov     rcx, [rbp+arg_8]; engineHandle
0x140029528  lea     rdx, stru_14002FA48; key
0x14002952f  call    cs:__imp_FwpmFilterDeleteByKey0
0x140029536  nop     dword ptr [rax+rax+00h]
0x14002953b  test    eax, eax
0x14002953d  jz      short loc_14002956D
0x14002953f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029546  cmp     rcx, rsi
0x140029549  jz      short loc_14002956D
0x14002954b  mov     edx, [rcx+2Ch]
0x14002954e  test    dil, dl
0x140029551  jz      short loc_14002956D
0x140029553  cmp     [rcx+29h], dil
0x140029557  jb      short loc_14002956D
0x140029559  mov     rcx, [rcx+18h]
0x14002955d  mov     edx, 4Ch ; 'L'
0x140029562  mov     r9d, eax
0x140029565  mov     r8, r15
0x140029568  call    WPP_SF_d
0x14002956d  test    ebx, ebx
0x14002956f  jz      short loc_1400295BA
0x140029571  mov     rcx, [rbp+arg_8]; engineHandle
0x140029575  lea     rdx, stru_14002FAB8; key
0x14002957c  call    cs:__imp_FwpmFilterDeleteByKey0
0x140029583  nop     dword ptr [rax+rax+00h]
0x140029588  test    eax, eax
0x14002958a  jz      short loc_1400295BA
0x14002958c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029593  cmp     rcx, rsi
0x140029596  jz      short loc_1400295BA
0x140029598  mov     edx, [rcx+2Ch]
0x14002959b  test    dil, dl
0x14002959e  jz      short loc_1400295BA
0x1400295a0  cmp     [rcx+29h], dil
0x1400295a4  jb      short loc_1400295BA
0x1400295a6  mov     rcx, [rcx+18h]
0x1400295aa  mov     edx, 4Dh ; 'M'
0x1400295af  mov     r9d, eax
0x1400295b2  mov     r8, r15
0x1400295b5  call    WPP_SF_d
0x1400295ba  mov     ebx, 0C022000Ah
0x1400295bf  mov     rcx, [rbp+arg_8]
0x1400295c3  lea     rdx, xmmword_14002FAC8
0x1400295ca  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x1400295d1  nop     dword ptr [rax+rax+00h]
0x1400295d6  cmp     eax, ebx
0x1400295d8  jz      short loc_1400295BF
0x1400295da  test    eax, eax
0x1400295dc  jz      short loc_14002960C
0x1400295de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295e5  cmp     rcx, rsi
0x1400295e8  jz      short loc_14002960C
0x1400295ea  mov     edx, [rcx+2Ch]
0x1400295ed  test    dil, dl
0x1400295f0  jz      short loc_14002960C
0x1400295f2  cmp     [rcx+29h], dil
0x1400295f6  jb      short loc_14002960C
0x1400295f8  mov     rcx, [rcx+18h]
0x1400295fc  mov     edx, 4Eh ; 'N'
0x140029601  mov     r9d, eax
0x140029604  mov     r8, r15
0x140029607  call    WPP_SF_d
0x14002960c  mov     rcx, [rbp+arg_8]
0x140029610  lea     rdx, xmmword_14002FAA8
0x140029617  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x14002961e  nop     dword ptr [rax+rax+00h]
0x140029623  cmp     eax, ebx
0x140029625  jz      short loc_14002960C
0x140029627  test    eax, eax
0x140029629  jz      short loc_140029659
0x14002962b  mov     rcx, cs:WPP_GLOBAL_Control
0x140029632  cmp     rcx, rsi
0x140029635  jz      short loc_140029659
0x140029637  mov     edx, [rcx+2Ch]
0x14002963a  test    dil, dl
0x14002963d  jz      short loc_140029659
0x14002963f  cmp     [rcx+29h], dil
0x140029643  jb      short loc_140029659
0x140029645  mov     rcx, [rcx+18h]
0x140029649  mov     edx, 4Fh ; 'O'
0x14002964e  mov     r9d, eax
0x140029651  mov     r8, r15
0x140029654  call    WPP_SF_d
0x140029659  mov     rcx, [rbp+arg_8]
0x14002965d  lea     rdx, xmmword_14002FAD8
0x140029664  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x14002966b  nop     dword ptr [rax+rax+00h]
0x140029670  cmp     eax, ebx
0x140029672  jz      short loc_140029659
0x140029674  test    eax, eax
0x140029676  jz      short loc_1400296A6
0x140029678  mov     rcx, cs:WPP_GLOBAL_Control
0x14002967f  cmp     rcx, rsi
0x140029682  jz      short loc_1400296A6
0x140029684  mov     edx, [rcx+2Ch]
0x140029687  test    dil, dl
0x14002968a  jz      short loc_1400296A6
0x14002968c  cmp     [rcx+29h], dil
0x140029690  jb      short loc_1400296A6
0x140029692  mov     rcx, [rcx+18h]
0x140029696  mov     edx, 50h ; 'P'
0x14002969b  mov     r9d, eax
0x14002969e  mov     r8, r15
0x1400296a1  call    WPP_SF_d
0x1400296a6  mov     rcx, [rbp+arg_8]
0x1400296aa  lea     rdx, xmmword_14002FA88
0x1400296b1  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x1400296b8  nop     dword ptr [rax+rax+00h]
0x1400296bd  cmp     eax, ebx
0x1400296bf  jz      short loc_1400296A6
0x1400296c1  test    eax, eax
0x1400296c3  jz      short loc_1400296F3
0x1400296c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400296cc  cmp     rcx, rsi
0x1400296cf  jz      short loc_1400296F3
0x1400296d1  mov     edx, [rcx+2Ch]
0x1400296d4  test    dil, dl
0x1400296d7  jz      short loc_1400296F3
0x1400296d9  cmp     [rcx+29h], dil
0x1400296dd  jb      short loc_1400296F3
0x1400296df  mov     rcx, [rcx+18h]
0x1400296e3  mov     edx, 51h ; 'Q'
0x1400296e8  mov     r9d, eax
0x1400296eb  mov     r8, r15
0x1400296ee  call    WPP_SF_d
0x1400296f3  mov     rcx, [rbp+arg_8]
0x1400296f7  lea     rdx, xmmword_14002FA98
0x1400296fe  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x140029705  nop     dword ptr [rax+rax+00h]
0x14002970a  cmp     eax, ebx
0x14002970c  jz      short loc_1400296F3
0x14002970e  test    eax, eax
0x140029710  jz      short loc_140029740
0x140029712  mov     rcx, cs:WPP_GLOBAL_Control
0x140029719  cmp     rcx, rsi
0x14002971c  jz      short loc_140029740
0x14002971e  mov     edx, [rcx+2Ch]
  ... truncated ...
```
