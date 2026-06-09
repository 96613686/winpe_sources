# NatInitiateTranslation

- ea: `0x1400078cc`
- end: `0x140007c8e`
- name: `NatInitiateTranslation`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140006f00`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400078cc`
- `0x14002adb0`
- `0x14002c6d0`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!KeSetTimerEx` at `0x14000798d`
- `ntoskrnl!KeSetTimerEx` at `0x14000798d`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400079ce`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400079ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400079ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400079ef`
- `cng!SystemPrng` at `0x140007b24`
- `cng!SystemPrng` at `0x140007b3f`
- `cng!SystemPrng` at `0x140007b24`
- `cng!SystemPrng` at `0x140007b3f`

## pseudocode

```c
__int64 NatInitiateTranslation()
{
  unsigned __int64 v0; // rbx
  ULONG MaximumProcessorCount; // eax
  unsigned __int64 v2; // rbp
  ULONG v3; // esi
  void *Pool2; // rax
  __int64 v5; // r8
  void *v6; // rdi
  ULONG v7; // edx
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned int v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  unsigned __int16 v17; // [rsp+20h] [rbp-258h] BYREF
  __int64 v18; // [rsp+28h] [rbp-250h]
  _WORD v19[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  v17 = 0;
  memset(v19, 0, 0x202u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
  }
  v18 = 600000000;
  KeSetTimerEx(&TimerObject, (LARGE_INTEGER)-600000000LL, 60000, &TimerDpcObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids);
  }
  v0 = 0;
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  v2 = (unsigned __int64)MaximumProcessorCount << 6;
  v3 = MaximumProcessorCount;
  Pool2 = (void *)ExAllocatePool2(64, v2 + 112, 543322950);
  v6 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, v2 + 112);
    v7 = 0;
    v0 = ((unsigned __int64)v6 + 63) & 0xFFFFFFFFFFFFFFC0uLL;
    *(_DWORD *)v0 = 1668041806;
    *(_DWORD *)(v0 + 4) = 4194368;
    *(_DWORD *)(v0 + 8) = 63;
    *(_QWORD *)(v0 + 16) = 0;
    *(_QWORD *)(v0 + 24) = v6;
    if ( v3 )
    {
      v5 = 0;
      do
      {
        v8 = v5++ << 6;
        v9 = v8 + v0 + 64;
        v10 = v0 + v8 + 80;
        *(_QWORD *)(v9 + 8) = v9;
        *(_QWORD *)v9 = v9;
        *(_QWORD *)(v9 + 24) = v10;
        *(_QWORD *)(v9 + 16) = v10;
        *(_DWORD *)(v9 + 40) = v7++;
      }
      while ( v7 < v3 );
    }
  }
  NatShimPool = v0;
  if ( v0 )
  {
    if ( ReservedPortsLowerRange == DefaultStartPort && ReservedPortsUpperRange == DefaultEndPort )
    {
      ReservePort = 1;
      SystemPrng(&v19[1], 512, v5);
      v19[0] = 0;
      SystemPrng(&v17, 2, v14);
      v17 %= 0x7D0u;
      DefaultStartPort = ((unsigned __int8)(v17 + 97) << 8) | (unsigned __int8)((unsigned __int16)(v17 - 4511) >> 8);
      ReservedPortsLowerRange = DefaultStartPort;
      DefaultEndPort = ((unsigned __int8)(v17 + 24) << 8) | (unsigned __int8)((unsigned __int16)(v17 - 2536) >> 8);
      ReservedPortsUpperRange = DefaultEndPort;
    }
    else
    {
      ReservePort = 0;
    }
    v15 = NatRegisterCallout();
    v11 = v15;
    if ( v15 >= 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v13 = 55;
        goto LABEL_43;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          53,
          WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
          (unsigned int)v15);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v13 = 54;
        goto LABEL_43;
      }
    }
  }
  else
  {
    v11 = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, 3221225495LL);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v13 = 50;
LABEL_43:
        WPP_SF_d(v12->AttachedDevice, v13, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v11);
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1400078cc  push    rbx
0x1400078ce  push    rbp
0x1400078cf  push    rsi
0x1400078d0  push    rdi
0x1400078d1  push    r12
0x1400078d3  sub     rsp, 250h
0x1400078da  mov     rax, cs:__security_cookie
0x1400078e1  xor     rax, rsp
0x1400078e4  mov     [rsp+278h+var_38], rax
0x1400078ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078f3  lea     r12, WPP_GLOBAL_Control
0x1400078fa  cmp     rcx, r12
0x1400078fd  jz      short loc_140007921
0x1400078ff  mov     eax, [rcx+2Ch]
0x140007902  test    al, 1
0x140007904  jz      short loc_140007921
0x140007906  cmp     byte ptr [rcx+29h], 6
0x14000790a  jb      short loc_140007921
0x14000790c  mov     rcx, [rcx+18h]
0x140007910  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140007917  mov     edx, 30h ; '0'
0x14000791c  call    WPP_SF_
0x140007921  xor     eax, eax
0x140007923  lea     rcx, [rsp+278h+var_248]; void *
0x140007928  xor     edx, edx; Val
0x14000792a  mov     [rsp+278h+var_258], ax
0x14000792f  mov     r8d, 202h; Size
0x140007935  call    memset
0x14000793a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007941  cmp     rcx, r12
0x140007944  jz      short loc_140007968
0x140007946  mov     eax, [rcx+2Ch]
0x140007949  test    al, 1
0x14000794b  jz      short loc_140007968
0x14000794d  cmp     byte ptr [rcx+29h], 6
0x140007951  jb      short loc_140007968
0x140007953  mov     rcx, [rcx+18h]
0x140007957  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x14000795e  mov     edx, 10h
0x140007963  call    WPP_SF_
0x140007968  mov     [rsp+278h+var_250], 23C34600h
0x140007971  lea     r9, TimerDpcObject; Dpc
0x140007978  mov     rdx, [rsp+278h+var_250]
0x14000797d  lea     rcx, TimerObject; Timer
0x140007984  neg     rdx; DueTime
0x140007987  mov     r8d, 0EA60h; Period
0x14000798d  call    cs:__imp_KeSetTimerEx
0x140007994  nop     dword ptr [rax+rax+00h]
0x140007999  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079a0  cmp     rcx, r12
0x1400079a3  jz      short loc_1400079C7
0x1400079a5  mov     eax, [rcx+2Ch]
0x1400079a8  test    al, 1
0x1400079aa  jz      short loc_1400079C7
0x1400079ac  cmp     byte ptr [rcx+29h], 6
0x1400079b0  jb      short loc_1400079C7
0x1400079b2  mov     rcx, [rcx+18h]
0x1400079b6  lea     r8, WPP_f31671e38d5b33600ddc283ab761c181_Traceguids
0x1400079bd  mov     edx, 11h
0x1400079c2  call    WPP_SF_
0x1400079c7  mov     ecx, 0FFFFh; GroupNumber
0x1400079cc  xor     ebx, ebx
0x1400079ce  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400079d5  nop     dword ptr [rax+rax+00h]
0x1400079da  mov     ebp, eax
0x1400079dc  mov     r8d, 20627346h
0x1400079e2  shl     rbp, 6
0x1400079e6  lea     ecx, [rbx+40h]
0x1400079e9  mov     esi, eax
0x1400079eb  lea     rdx, [rbp+70h]
0x1400079ef  call    cs:__imp_ExAllocatePool2
0x1400079f6  nop     dword ptr [rax+rax+00h]
0x1400079fb  mov     rdi, rax
0x1400079fe  test    rax, rax
0x140007a01  jz      short loc_140007A72
0x140007a03  lea     r8, [rbp+70h]; Size
0x140007a07  xor     edx, edx; Val
0x140007a09  mov     rcx, rax; void *
0x140007a0c  call    memset
0x140007a11  lea     rbx, [rdi+3Fh]
0x140007a15  xor     edx, edx
0x140007a17  and     rbx, 0FFFFFFFFFFFFFFC0h
0x140007a1b  mov     dword ptr [rbx], 636C4C4Eh
0x140007a21  mov     dword ptr [rbx+4], 400040h
0x140007a28  mov     dword ptr [rbx+8], 3Fh ; '?'
0x140007a2f  mov     qword ptr [rbx+10h], 0
0x140007a37  mov     [rbx+18h], rdi
0x140007a3b  test    esi, esi
0x140007a3d  jz      short loc_140007A72
0x140007a3f  xor     r8d, r8d
0x140007a42  mov     rax, r8
0x140007a45  lea     rcx, [rbx+40h]
0x140007a49  shl     rax, 6
0x140007a4d  inc     r8
0x140007a50  add     rcx, rax
0x140007a53  add     rax, 50h ; 'P'
0x140007a57  add     rax, rbx
0x140007a5a  mov     [rcx+8], rcx
0x140007a5e  mov     [rcx], rcx
0x140007a61  mov     [rcx+18h], rax
0x140007a65  mov     [rcx+10h], rax
0x140007a69  mov     [rcx+28h], edx
0x140007a6c  inc     edx
0x140007a6e  cmp     edx, esi
0x140007a70  jb      short loc_140007A42
0x140007a72  mov     cs:NatShimPool, rbx
0x140007a79  test    rbx, rbx
0x140007a7c  jnz     short loc_140007AE8
0x140007a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a85  mov     ebx, 0C0000017h
0x140007a8a  cmp     rcx, r12
0x140007a8d  jz      loc_140007C6D
0x140007a93  mov     eax, [rcx+2Ch]
0x140007a96  test    al, 1
0x140007a98  jz      short loc_140007AB8
0x140007a9a  cmp     byte ptr [rcx+29h], 2
0x140007a9e  jb      short loc_140007AB8
0x140007aa0  mov     rcx, [rcx+18h]
0x140007aa4  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140007aab  mov     edx, 31h ; '1'
0x140007ab0  mov     r9d, ebx
0x140007ab3  call    WPP_SF_d
0x140007ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x140007abf  cmp     rcx, r12
0x140007ac2  jz      loc_140007C6D
0x140007ac8  mov     edx, [rcx+2Ch]
0x140007acb  test    dl, 1
0x140007ace  jz      loc_140007C6D
0x140007ad4  cmp     byte ptr [rcx+29h], 6
0x140007ad8  jb      loc_140007C6D
0x140007ade  mov     edx, 32h ; '2'
0x140007ae3  jmp     loc_140007C5A
0x140007ae8  movzx   eax, cs:DefaultStartPort
0x140007aef  cmp     cs:ReservedPortsLowerRange, ax
0x140007af6  jnz     loc_140007BCF
0x140007afc  movzx   eax, cs:DefaultEndPort
0x140007b03  cmp     cs:ReservedPortsUpperRange, ax
0x140007b0a  jnz     loc_140007BCF
0x140007b10  mov     edx, 200h
0x140007b15  mov     cs:ReservePort, 1
0x140007b1f  lea     rcx, [rsp+278h+var_246]
0x140007b24  call    cs:__imp_SystemPrng
0x140007b2b  nop     dword ptr [rax+rax+00h]
0x140007b30  xor     eax, eax
0x140007b32  lea     rcx, [rsp+278h+var_258]
0x140007b37  mov     [rsp+278h+var_248], ax
0x140007b3c  lea     edx, [rax+2]
0x140007b3f  call    cs:__imp_SystemPrng
0x140007b46  nop     dword ptr [rax+rax+00h]
0x140007b4b  movzx   r9d, [rsp+278h+var_258]
0x140007b51  mov     r10d, 0FFh
0x140007b57  mov     eax, 10624DD3h
0x140007b5c  mul     r9d
0x140007b5f  shr     edx, 7
0x140007b62  imul    eax, edx, 7D0h
0x140007b68  sub     r9d, eax
0x140007b6b  movzx   edx, r9w
0x140007b6f  mov     [rsp+278h+var_258], r9w
0x140007b75  lea     eax, [r9+61h]
0x140007b79  add     r9b, 18h
0x140007b7d  movzx   ecx, al
0x140007b80  lea     r8d, [rdx+0EE61h]
0x140007b87  shl     cx, 8
0x140007b8b  shr     r8d, 8
0x140007b8f  and     r8w, r10w
0x140007b93  movzx   eax, r9b
0x140007b97  or      r8w, cx
0x140007b9b  shl     ax, 8
0x140007b9f  lea     ecx, [rdx+0F618h]
0x140007ba5  mov     cs:DefaultStartPort, r8w
0x140007bad  shr     ecx, 8
0x140007bb0  and     cx, r10w
0x140007bb4  mov     cs:ReservedPortsLowerRange, r8w
0x140007bbc  or      cx, ax
0x140007bbf  mov     cs:DefaultEndPort, cx
0x140007bc6  mov     cs:ReservedPortsUpperRange, cx
0x140007bcd  jmp     short loc_140007BD9
0x140007bcf  mov     cs:ReservePort, 0
0x140007bd9  mov     ecx, cs:ReservePort
0x140007bdf  call    NatRegisterCallout
0x140007be4  mov     ebx, eax
0x140007be6  test    eax, eax
0x140007be8  jns     short loc_140007C3C
0x140007bea  mov     rcx, cs:WPP_GLOBAL_Control
0x140007bf1  cmp     rcx, r12
0x140007bf4  jz      short loc_140007C6D
0x140007bf6  mov     edx, [rcx+2Ch]
0x140007bf9  test    dl, 1
0x140007bfc  jz      short loc_140007C1C
0x140007bfe  cmp     byte ptr [rcx+29h], 2
0x140007c02  jb      short loc_140007C1C
0x140007c04  mov     rcx, [rcx+18h]
0x140007c08  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140007c0f  mov     edx, 35h ; '5'
0x140007c14  mov     r9d, eax
0x140007c17  call    WPP_SF_d
0x140007c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c23  cmp     rcx, r12
0x140007c26  jz      short loc_140007C6D
0x140007c28  mov     eax, [rcx+2Ch]
0x140007c2b  test    al, 1
0x140007c2d  jz      short loc_140007C6D
0x140007c2f  cmp     byte ptr [rcx+29h], 6
0x140007c33  jb      short loc_140007C6D
0x140007c35  mov     edx, 36h ; '6'
0x140007c3a  jmp     short loc_140007C5A
0x140007c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c43  cmp     rcx, r12
0x140007c46  jz      short loc_140007C6D
0x140007c48  mov     eax, [rcx+2Ch]
0x140007c4b  test    al, 1
0x140007c4d  jz      short loc_140007C6D
0x140007c4f  cmp     byte ptr [rcx+29h], 6
0x140007c53  jb      short loc_140007C6D
0x140007c55  mov     edx, 37h ; '7'
0x140007c5a  mov     rcx, [rcx+18h]
0x140007c5e  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140007c65  mov     r9d, ebx
0x140007c68  call    WPP_SF_d
0x140007c6d  mov     eax, ebx
0x140007c6f  mov     rcx, [rsp+278h+var_38]
0x140007c77  xor     rcx, rsp; StackCookie
0x140007c7a  call    __security_check_cookie
0x140007c7f  add     rsp, 250h
0x140007c86  pop     r12
0x140007c88  pop     rdi
0x140007c89  pop     rsi
0x140007c8a  pop     rbp
0x140007c8b  pop     rbx
0x140007c8c  retn
```
