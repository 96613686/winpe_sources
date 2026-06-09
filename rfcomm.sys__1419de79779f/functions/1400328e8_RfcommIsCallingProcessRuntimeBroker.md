# RfcommIsCallingProcessRuntimeBroker

- ea: `0x1400328e8`
- end: `0x140032cef`
- name: `RfcommIsCallingProcessRuntimeBroker`
- size: `1031`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140032148`

## callees

- `0x140003cb4`
- `0x140003d98`
- `0x140004080`
- `0x1400322b8`
- `0x1400328e8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140032936`
- `ntoskrnl!ExAllocatePool2` at `0x140032b9f`
- `ntoskrnl!ExAllocatePool2` at `0x140032936`
- `ntoskrnl!ExAllocatePool2` at `0x140032b9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032aba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032aba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ca0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140032b66`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140032bd4`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140032b66`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140032bd4`
- `ntoskrnl!_wcsicmp` at `0x140032c26`
- `ntoskrnl!_wcsicmp` at `0x140032c26`

## string_xrefs

- `0x140032a62`: `\Windows\System32\RuntimeBroker.exe`

## pseudocode

```c
char __fastcall RfcommIsCallingProcessRuntimeBroker(__int64 a1)
{
  __int64 v1; // rbp
  char v2; // r15
  signed __int64 Pool2; // rsi
  int v4; // eax
  __int64 v5; // rdx
  PVOID v6; // r14
  signed int v7; // ebx
  __int64 v8; // r11
  __int64 v9; // rax
  _WORD *v10; // rcx
  _WORD *v11; // r8
  _WORD *v12; // rcx
  __int64 v13; // rcx
  _WORD *v14; // rax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rcx
  _WORD *v17; // rax
  unsigned __int64 v18; // rax
  wchar_t *v19; // rcx
  unsigned __int64 i; // rdi
  _WORD *v21; // rcx
  NTSTATUS InformationProcess; // eax
  int v23; // edx
  __int64 *v24; // rbx
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  int v28; // edx
  signed __int32 v30[8]; // [rsp+0h] [rbp-88h] BYREF
  PULONG ReturnLength; // [rsp+20h] [rbp-68h]
  PVOID P; // [rsp+90h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v2 = 0;
  _InterlockedOr(v30, 0);
  if ( *(_QWORD *)(v1 + 360) )
    goto LABEL_38;
  Pool2 = ExAllocatePool2(64, 520, 1835230802);
  if ( Pool2 )
  {
    P = 0;
    v4 = RfcommExpandSystemRoot((wchar_t **)&P);
    v6 = P;
    v7 = v4;
    if ( v4 >= 0 )
    {
      v8 = 2147483646;
      v9 = 2147483646;
      v5 = 260;
      v10 = P;
      v11 = (_WORD *)Pool2;
      do
      {
        if ( !v9 )
          break;
        if ( !*v10 )
          break;
        *v11++ = *v10++;
        --v9;
        --v5;
      }
      while ( v5 );
      v12 = v11 - 1;
      v7 = v5 == 0 ? 0x80000005 : 0;
      if ( v5 )
        v12 = v11;
      *v12 = 0;
      if ( v5 )
      {
        v13 = 260;
        v14 = (_WORD *)Pool2;
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v13;
        }
        while ( v13 );
        LODWORD(v5) = -1073741811;
        v7 = v13 == 0 ? 0xC000000D : 0;
        if ( v13 )
        {
          v15 = (520 - ((2 * (260 - v13)) & (unsigned __int64)-(__int64)(v13 != 0))) >> 1;
          if ( v15 - 1 > 0x7FFFFFFE )
          {
            v7 = -1073741811;
          }
          else
          {
            v16 = (520 - ((2 * (260 - v13)) & (unsigned __int64)-(__int64)(v13 != 0))) >> 1;
            v17 = (_WORD *)Pool2;
            do
            {
              if ( !*v17 )
                break;
              ++v17;
              --v16;
            }
            while ( v16 );
            v7 = v16 == 0 ? 0xC000000D : 0;
            if ( v16 )
              v18 = v15 - v16;
            else
              v18 = 0;
            if ( v16 )
            {
              v19 = RuntimeBrokerFileName;
              v5 = Pool2 + 2 * v18;
              for ( i = v15 - v18; i; --i )
              {
                if ( !v8 )
                  break;
                if ( !*v19 )
                  break;
                *(_WORD *)v5 = *v19++;
                v5 += 2;
                --v8;
              }
              v21 = (_WORD *)(v5 - 2);
              if ( i )
                v21 = (_WORD *)v5;
              v7 = i == 0 ? 0x80000005 : 0;
              *v21 = 0;
            }
          }
        }
      }
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    if ( v7 >= 0 )
    {
      Pool2 &= -(__int64)(_InterlockedCompareExchange64((volatile signed __int64 *)(v1 + 360), Pool2, 0) != 0);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_S(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          19,
          37,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          *(_QWORD *)(v1 + 360));
      if ( !Pool2 )
        goto LABEL_38;
    }
    ExFreePoolWithTag((PVOID)Pool2, 0);
    if ( v7 >= 0 )
    {
LABEL_38:
      LODWORD(P) = 0;
      InformationProcess = ZwQueryInformationProcess(
                             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                             ProcessImageFileName,
                             0,
                             0,
                             (PULONG)&P);
      if ( InformationProcess == -1073741820 && (unsigned int)P > 0x10 )
      {
        v24 = (__int64 *)ExAllocatePool2(64, (unsigned int)P + 2LL, 1835230802);
        if ( v24 )
        {
          if ( ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessImageFileName, v24, (ULONG)P, (PULONG)&P) >= 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_SS(
                WPP_GLOBAL_Control->DeviceExtension,
                v25,
                v26,
                v27,
                (_DWORD)ReturnLength,
                v24[1],
                *(_QWORD *)(v1 + 360));
            _InterlockedOr(v30, 0);
            if ( _wcsicmp((const wchar_t *)v24[1], *(const wchar_t **)(v1 + 360)) )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_S(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  19,
                  41,
                  (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
                  v24[1]);
            }
            else
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_S(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  19,
                  40,
                  (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
                  v24[1]);
              v2 = 1;
            }
          }
          ExFreePoolWithTag(v24, 0);
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v23,
          19,
          38,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          InformationProcess);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400328e8  push    rbx
0x1400328ea  push    rbp
0x1400328eb  push    rsi
0x1400328ec  push    rdi
0x1400328ed  push    r12
0x1400328ef  push    r13
0x1400328f1  push    r14
0x1400328f3  push    r15
0x1400328f5  sub     rsp, 48h
0x1400328f9  mov     rbp, [rcx+40h]
0x1400328fd  xor     r12d, r12d
0x140032900  mov     r15b, r12b
0x140032903  lock or [rsp+88h+var_88], r12d
0x140032908  mov     rax, [rbp+168h]
0x14003290f  lea     r13, WPP_RECORDER_INITIALIZED
0x140032916  lea     r14, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003291d  test    rax, rax
0x140032920  jnz     loc_140032B3E
0x140032926  mov     edi, 208h
0x14003292b  lea     ecx, [rax+40h]
0x14003292e  mov     edx, edi
0x140032930  mov     r8d, 6D636652h
0x140032936  call    cs:__imp_ExAllocatePool2
0x14003293d  nop     dword ptr [rax+rax+00h]
0x140032942  mov     rsi, rax
0x140032945  test    rax, rax
0x140032948  jz      loc_140032CDA
0x14003294e  lea     rcx, [rsp+88h+P]
0x140032956  mov     [rsp+88h+P], r12
0x14003295e  call    RfcommExpandSystemRoot
0x140032963  mov     r14, [rsp+88h+P]
0x14003296b  mov     ebx, eax
0x14003296d  test    eax, eax
0x14003296f  js      loc_140032AB0
0x140032975  mov     r11d, 7FFFFFFEh
0x14003297b  mov     r10d, 104h
0x140032981  mov     eax, r11d
0x140032984  mov     edx, r10d
0x140032987  mov     rcx, r14
0x14003298a  mov     r8, rsi
0x14003298d  test    rax, rax
0x140032990  jz      short loc_1400329B1
0x140032992  movzx   r9d, word ptr [rcx]
0x140032996  test    r9w, r9w
0x14003299a  jz      short loc_1400329B1
0x14003299c  mov     [r8], r9w
0x1400329a0  add     rcx, 2
0x1400329a4  add     r8, 2
0x1400329a8  dec     rax
0x1400329ab  sub     rdx, 1
0x1400329af  jnz     short loc_14003298D
0x1400329b1  mov     rax, rdx
0x1400329b4  lea     rcx, [r8-2]
0x1400329b8  neg     rax
0x1400329bb  mov     r9d, 80000005h
0x1400329c1  sbb     ebx, ebx
0x1400329c3  not     ebx
0x1400329c5  and     ebx, r9d
0x1400329c8  test    rdx, rdx
0x1400329cb  cmovnz  rcx, r8
0x1400329cf  mov     [rcx], r12w
0x1400329d3  jz      loc_140032AB0
0x1400329d9  mov     rcx, r10
0x1400329dc  mov     rax, rsi
0x1400329df  cmp     [rax], r12w
0x1400329e3  jz      short loc_1400329EF
0x1400329e5  add     rax, 2
0x1400329e9  sub     rcx, 1
0x1400329ed  jnz     short loc_1400329DF
0x1400329ef  mov     rax, rcx
0x1400329f2  mov     edx, 0C000000Dh
0x1400329f7  neg     rax
0x1400329fa  sbb     ebx, ebx
0x1400329fc  not     ebx
0x1400329fe  and     ebx, edx
0x140032a00  test    rcx, rcx
0x140032a03  jz      loc_140032AB0
0x140032a09  sub     r10, rcx
0x140032a0c  add     r10, r10
0x140032a0f  neg     rcx
0x140032a12  sbb     rax, rax
0x140032a15  and     rax, r10
0x140032a18  sub     rdi, rax
0x140032a1b  shr     rdi, 1
0x140032a1e  lea     rax, [rdi-1]
0x140032a22  cmp     rax, r11
0x140032a25  ja      loc_140032AAE
0x140032a2b  mov     rcx, rdi
0x140032a2e  mov     rax, rsi
0x140032a31  cmp     [rax], r12w
0x140032a35  jz      short loc_140032A41
0x140032a37  add     rax, 2
0x140032a3b  sub     rcx, 1
0x140032a3f  jnz     short loc_140032A31
0x140032a41  mov     rax, rcx
0x140032a44  neg     rax
0x140032a47  sbb     ebx, ebx
0x140032a49  not     ebx
0x140032a4b  and     ebx, edx
0x140032a4d  test    rcx, rcx
0x140032a50  jz      short loc_140032A5A
0x140032a52  mov     rax, rdi
0x140032a55  sub     rax, rcx
0x140032a58  jmp     short loc_140032A5D
0x140032a5a  mov     rax, r12
0x140032a5d  test    rcx, rcx
0x140032a60  jz      short loc_140032AB0
0x140032a62  lea     rcx, RuntimeBrokerFileName; "\\Windows\\System32\\RuntimeBroker.exe"
0x140032a69  lea     rdx, [rsi+rax*2]
0x140032a6d  sub     rdi, rax
0x140032a70  jz      short loc_140032A93
0x140032a72  test    r11, r11
0x140032a75  jz      short loc_140032A93
0x140032a77  movzx   eax, word ptr [rcx]
0x140032a7a  test    ax, ax
0x140032a7d  jz      short loc_140032A93
0x140032a7f  mov     [rdx], ax
0x140032a82  add     rcx, 2
0x140032a86  add     rdx, 2
0x140032a8a  dec     r11
0x140032a8d  sub     rdi, 1
0x140032a91  jnz     short loc_140032A72
0x140032a93  test    rdi, rdi
0x140032a96  lea     rcx, [rdx-2]
0x140032a9a  cmovnz  rcx, rdx
0x140032a9e  neg     rdi
0x140032aa1  sbb     ebx, ebx
0x140032aa3  not     ebx
0x140032aa5  and     ebx, r9d
0x140032aa8  mov     [rcx], r12w
0x140032aac  jmp     short loc_140032AB0
0x140032aae  mov     ebx, edx
0x140032ab0  test    r14, r14
0x140032ab3  jz      short loc_140032AC6
0x140032ab5  xor     edx, edx; Tag
0x140032ab7  mov     rcx, r14; P
0x140032aba  call    cs:__imp_ExFreePoolWithTag
0x140032ac1  nop     dword ptr [rax+rax+00h]
0x140032ac6  test    ebx, ebx
0x140032ac8  js      short loc_140032B1E
0x140032aca  xor     eax, eax
0x140032acc  lock cmpxchg [rbp+168h], rsi
0x140032ad5  neg     rax
0x140032ad8  sbb     rcx, rcx
0x140032adb  and     rsi, rcx
0x140032ade  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032ae5  lea     r14, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140032aec  jz      short loc_140032B19
0x140032aee  mov     rcx, cs:WPP_GLOBAL_Control
0x140032af5  mov     r9d, 25h ; '%'
0x140032afb  mov     rax, [rbp+168h]
0x140032b02  mov     [rsp+88h+var_60], rax
0x140032b07  mov     [rsp+88h+ReturnLength], r14
0x140032b0c  mov     rcx, [rcx+40h]
0x140032b10  lea     r8d, [r9-12h]
0x140032b14  call    WPP_RECORDER_SF_S
0x140032b19  test    rsi, rsi
0x140032b1c  jz      short loc_140032B3E
0x140032b1e  xor     edx, edx; Tag
0x140032b20  mov     rcx, rsi; P
0x140032b23  call    cs:__imp_ExFreePoolWithTag
0x140032b2a  nop     dword ptr [rax+rax+00h]
0x140032b2f  test    ebx, ebx
0x140032b31  js      loc_140032CDA
0x140032b37  lea     r14, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140032b3e  xor     r9d, r9d; ProcessInformationLength
0x140032b41  mov     dword ptr [rsp+88h+P], r12d
0x140032b49  lea     rax, [rsp+88h+P]
0x140032b51  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140032b55  xor     r8d, r8d; ProcessInformation
0x140032b58  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x140032b5d  mov     rcx, rsi; ProcessHandle
0x140032b60  lea     edi, [r9+1Bh]
0x140032b64  mov     edx, edi; ProcessInformationClass
0x140032b66  call    cs:__imp_ZwQueryInformationProcess
0x140032b6d  nop     dword ptr [rax+rax+00h]
0x140032b72  cmp     eax, 0C0000004h
0x140032b77  jnz     loc_140032CAE
0x140032b7d  cmp     dword ptr [rsp+88h+P], 10h
0x140032b85  jbe     loc_140032CAE
0x140032b8b  mov     edx, dword ptr [rsp+88h+P]
0x140032b92  lea     ecx, [rdi+25h]
0x140032b95  add     rdx, 2
0x140032b99  mov     r8d, 6D636652h
0x140032b9f  call    cs:__imp_ExAllocatePool2
0x140032ba6  nop     dword ptr [rax+rax+00h]
0x140032bab  mov     rbx, rax
0x140032bae  test    rax, rax
0x140032bb1  jz      loc_140032CDA
0x140032bb7  mov     r9d, dword ptr [rsp+88h+P]; ProcessInformationLength
0x140032bbf  lea     rax, [rsp+88h+P]
0x140032bc7  mov     r8, rbx; ProcessInformation
0x140032bca  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x140032bcf  mov     edx, edi; ProcessInformationClass
0x140032bd1  mov     rcx, rsi; ProcessHandle
0x140032bd4  call    cs:__imp_ZwQueryInformationProcess
0x140032bdb  nop     dword ptr [rax+rax+00h]
0x140032be0  test    eax, eax
0x140032be2  js      loc_140032C9B
0x140032be8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032bef  jz      short loc_140032C16
0x140032bf1  mov     rax, [rbp+168h]
0x140032bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140032bff  mov     [rsp+88h+var_58], rax
0x140032c04  mov     rax, [rbx+8]
0x140032c08  mov     [rsp+88h+var_60], rax
0x140032c0d  mov     rcx, [rcx+40h]
0x140032c11  call    WPP_RECORDER_SF_SS
0x140032c16  lock or [rsp+88h+var_88], r12d
0x140032c1b  mov     rdx, [rbp+168h]; Str2
0x140032c22  mov     rcx, [rbx+8]; Str1
0x140032c26  call    cs:__imp__wcsicmp
0x140032c2d  nop     dword ptr [rax+rax+00h]
0x140032c32  test    eax, eax
0x140032c34  jnz     short loc_140032C6A
0x140032c36  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032c3d  jz      short loc_140032C65
0x140032c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c46  lea     r9d, [rax+28h]
0x140032c4a  mov     rax, [rbx+8]
0x140032c4e  lea     r8d, [r9-15h]
0x140032c52  mov     [rsp+88h+var_60], rax
0x140032c57  mov     [rsp+88h+ReturnLength], r14
0x140032c5c  mov     rcx, [rcx+40h]
0x140032c60  call    WPP_RECORDER_SF_S
0x140032c65  mov     r15b, 1
0x140032c68  jmp     short loc_140032C9B
0x140032c6a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032c71  jz      short loc_140032C9B
0x140032c73  mov     rcx, cs:WPP_GLOBAL_Control
0x140032c7a  mov     r9d, 29h ; ')'
0x140032c80  mov     rax, [rbx+8]
0x140032c84  mov     [rsp+88h+var_60], rax
0x140032c89  mov     [rsp+88h+ReturnLength], r14
0x140032c8e  mov     rcx, [rcx+40h]
0x140032c92  lea     r8d, [r9-16h]
0x140032c96  call    WPP_RECORDER_SF_S
0x140032c9b  xor     edx, edx; Tag
0x140032c9d  mov     rcx, rbx; P
0x140032ca0  call    cs:__imp_ExFreePoolWithTag
0x140032ca7  nop     dword ptr [rax+rax+00h]
0x140032cac  jmp     short loc_140032CDA
0x140032cae  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032cb5  jz      short loc_140032CDA
0x140032cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032cbe  mov     r9d, 26h ; '&'
0x140032cc4  mov     dword ptr [rsp+88h+var_60], eax
0x140032cc8  mov     [rsp+88h+ReturnLength], r14
0x140032ccd  mov     rcx, [rcx+40h]
0x140032cd1  lea     r8d, [r9-13h]
0x140032cd5  call    WPP_RECORDER_SF_d
0x140032cda  mov     al, r15b
0x140032cdd  add     rsp, 48h
0x140032ce1  pop     r15
0x140032ce3  pop     r14
0x140032ce5  pop     r13
0x140032ce7  pop     r12
0x140032ce9  pop     rdi
0x140032cea  pop     rsi
0x140032ceb  pop     rbp
0x140032cec  pop     rbx
0x140032ced  retn
```
