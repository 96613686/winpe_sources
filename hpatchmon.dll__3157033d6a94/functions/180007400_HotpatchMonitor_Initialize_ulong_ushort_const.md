# HotpatchMonitor::Initialize(ulong,ushort * * const)

- ea: `0x180007400`
- end: `0x18000758c`
- name: `?Initialize@HotpatchMonitor@@UEAAJKQEAPEAG@Z`
- size: `396`
- prototype: `__int64 __fastcall(HotpatchMonitor *this, __int64, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180002fb0`

## callees

- `0x1800011cc`
- `0x180002270`
- `0x180007400`
- `0x18000cd68`
- `0x18000d3ec`
- `0x1800114a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800074b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800074da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800074b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800074da`

## pseudocode

```c
__int64 __fastcall HotpatchMonitor::Initialize(HotpatchMonitor *this, __int64 a2, unsigned __int16 **const a3)
{
  int v4; // ebx
  unsigned int v5; // ebx
  HANDLE EventW; // rax
  HANDLE v7; // rax
  bool v8; // zf
  signed int HotpatchAutoRemediationSettings; // eax
  unsigned int v10; // ecx
  unsigned int v12; // [rsp+30h] [rbp-9h] BYREF
  int v13; // [rsp+34h] [rbp-5h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp+7h] BYREF
  unsigned int *v15; // [rsp+60h] [rbp+27h]
  __int64 v16; // [rsp+68h] [rbp+2Fh]
  unsigned int *v17; // [rsp+70h] [rbp+37h]
  __int64 v18; // [rsp+78h] [rbp+3Fh]

  *((_QWORD *)this + 12) = -1;
  *((_OWORD *)this + 4) = 0;
  v12 = 0;
  *((_OWORD *)this + 5) = 0;
  v4 = McGenEventRegister_EventRegister(this, a2, a3);
  if ( v4 )
  {
    v5 = v4 | 0x10000000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v12 = v5;
      v15 = &v12;
      v16 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &dword_180018F0C, 0, 0, 3, v14);
    }
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 9) = EventW;
    if ( !EventW )
      return GetLastError() | 0x10000000;
    v7 = CreateEventW(0, 1, 0, 0);
    v8 = *((_QWORD *)this + 9) == 0;
    *((_QWORD *)this + 8) = v7;
    if ( v8 )
    {
      return GetLastError() | 0x10000000;
    }
    else
    {
      HotpatchAutoRemediationSettings = RegUtil::GetHotpatchAutoRemediationSettings(&v12);
      v10 = 0;
      if ( HotpatchAutoRemediationSettings >= 0 )
        v10 = v12;
      *((_DWORD *)this + 14) = v10;
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v13 = *((_DWORD *)this + 14);
        v15 = (unsigned int *)&v13;
        v17 = &v12;
        v12 = HotpatchAutoRemediationSettings;
        v18 = 4;
        v16 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, word_1800187B2, 0, 0, 4, v14);
      }
      *((_DWORD *)this + 23) = *((_DWORD *)this + 14);
      return (unsigned int)etwConsumer::initialize((HotpatchMonitor *)((char *)this + 104));
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180007400  mov     [rsp-8+arg_8], rbx
0x180007405  mov     [rsp-8+arg_10], rdi
0x18000740a  push    rbp
0x18000740b  lea     rbp, [rsp-57h]
0x180007410  sub     rsp, 90h
0x180007417  mov     rax, cs:__security_cookie
0x18000741e  xor     rax, rsp
0x180007421  mov     [rbp+57h+var_10], rax
0x180007425  xorps   xmm0, xmm0
0x180007428  mov     qword ptr [rcx+60h], 0FFFFFFFFFFFFFFFFh
0x180007430  movups  xmmword ptr [rcx+40h], xmm0
0x180007434  mov     rdi, rcx
0x180007437  mov     [rbp+57h+var_60], 0
0x18000743e  movups  xmmword ptr [rcx+50h], xmm0
0x180007442  call    McGenEventRegister_EventRegister
0x180007447  mov     ebx, eax
0x180007449  test    eax, eax
0x18000744b  jz      short loc_1800074A2
0x18000744d  mov     eax, cs:dword_18001E048
0x180007453  bts     ebx, 1Ch
0x180007457  cmp     eax, 5
0x18000745a  jbe     loc_180007569
0x180007460  lea     rax, [rbp+57h+var_60]
0x180007464  mov     [rbp+57h+var_60], ebx
0x180007467  mov     [rbp+57h+var_30], rax
0x18000746b  lea     rdx, dword_180018F0C
0x180007472  lea     rax, [rbp+57h+var_50]
0x180007476  mov     [rbp+57h+var_28], 4
0x18000747e  mov     [rsp+90h+var_68], rax
0x180007483  lea     rcx, dword_18001E048
0x18000748a  xor     r9d, r9d
0x18000748d  mov     [rsp+90h+var_70], 3
0x180007495  xor     r8d, r8d
0x180007498  call    _tlgWriteTransfer_EventWriteTransfer
0x18000749d  jmp     loc_180007569
0x1800074a2  xor     r9d, r9d; lpName
0x1800074a5  xor     r8d, r8d; bInitialState
0x1800074a8  xor     ecx, ecx; lpEventAttributes
0x1800074aa  lea     ebx, [r9+1]
0x1800074ae  mov     edx, ebx; bManualReset
0x1800074b0  call    cs:__imp_CreateEventW
0x1800074b6  mov     [rdi+48h], rax
0x1800074ba  test    rax, rax
0x1800074bd  jnz     short loc_1800074D0
0x1800074bf  call    cs:__imp_GetLastError
0x1800074c5  mov     ebx, eax
0x1800074c7  bts     ebx, 1Ch
0x1800074cb  jmp     loc_180007569
0x1800074d0  xor     r9d, r9d; lpName
0x1800074d3  xor     r8d, r8d; bInitialState
0x1800074d6  mov     edx, ebx; bManualReset
0x1800074d8  xor     ecx, ecx; lpEventAttributes
0x1800074da  call    cs:__imp_CreateEventW
0x1800074e0  cmp     qword ptr [rdi+48h], 0
0x1800074e5  mov     [rdi+40h], rax
0x1800074e9  jz      short loc_1800074BF
0x1800074eb  lea     rcx, [rbp+57h+var_60]; unsigned int *
0x1800074ef  call    ?GetHotpatchAutoRemediationSettings@RegUtil@@SAJPEAK@Z; RegUtil::GetHotpatchAutoRemediationSettings(ulong *)
0x1800074f4  xor     ecx, ecx
0x1800074f6  mov     edx, eax
0x1800074f8  test    eax, eax
0x1800074fa  cmovns  ecx, [rbp+57h+var_60]
0x1800074fe  mov     [rdi+38h], ecx
0x180007501  mov     eax, cs:dword_18001E048
0x180007507  cmp     eax, 5
0x18000750a  jbe     short loc_180007558
0x18000750c  mov     eax, [rdi+38h]
0x18000750f  lea     rcx, [rbp+57h+var_5C]
0x180007513  mov     [rbp+57h+var_5C], eax
0x180007516  xor     r9d, r9d
0x180007519  lea     rax, [rbp+57h+var_60]
0x18000751d  mov     [rbp+57h+var_30], rcx
0x180007521  lea     rcx, [rbp+57h+var_50]
0x180007525  mov     [rbp+57h+var_20], rax
0x180007529  mov     eax, 4
0x18000752e  mov     [rsp+90h+var_68], rcx
0x180007533  mov     [rbp+57h+var_60], edx
0x180007536  lea     rcx, dword_18001E048
0x18000753d  xor     r8d, r8d
0x180007540  mov     [rbp+57h+var_18], rax
0x180007544  lea     rdx, word_1800187B2
0x18000754b  mov     [rbp+57h+var_28], rax
0x18000754f  mov     [rsp+90h+var_70], eax
0x180007553  call    _tlgWriteTransfer_EventWriteTransfer
0x180007558  mov     eax, [rdi+38h]
0x18000755b  lea     rcx, [rdi+68h]; this
0x18000755f  mov     [rdi+5Ch], eax
0x180007562  call    ?initialize@etwConsumer@@QEAAJXZ; etwConsumer::initialize(void)
0x180007567  mov     ebx, eax
0x180007569  mov     eax, ebx
0x18000756b  mov     rcx, [rbp+57h+var_10]
0x18000756f  xor     rcx, rsp; StackCookie
0x180007572  call    __security_check_cookie
0x180007577  lea     r11, [rsp+90h+var_s0]
0x18000757f  mov     rbx, [r11+18h]
0x180007583  mov     rdi, [r11+20h]
0x180007587  mov     rsp, r11
0x18000758a  pop     rbp
0x18000758b  retn
```
