# DfscPopulateDomainNameCache

- ea: `0x140022cd8`
- end: `0x140022fff`
- name: `DfscPopulateDomainNameCache`
- size: `807`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140015050`
- `0x140021c60`

## callees

- `0x140002570`
- `0x1400027f8`
- `0x140002aa0`
- `0x14000328c`
- `0x140006380`
- `0x14001a8a4`
- `0x14001c2e4`
- `0x14001ef20`
- `0x140021fa0`
- `0x140022118`
- `0x140022cd8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140022d97`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022dd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022e82`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022eb3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022d97`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022dd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022e82`
- `ntoskrnl!RtlInitUnicodeString` at `0x140022eb3`

## pseudocode

```c
__int64 __fastcall DfscPopulateDomainNameCache(__int64 a1, __int64 a2)
{
  _QWORD *CurrentDcContext; // r15
  const WCHAR *v6; // r12
  int v7; // ebx
  unsigned int DomainReferral; // eax
  const WCHAR *v9; // rdi
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  int v12; // edx
  __int64 DomainCache; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v15; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF

  v15 = 0;
  memset(v16, 0, 0x108u);
  DestinationString = 0;
  CurrentDcContext = (_QWORD *)DfscGetCurrentDcContext(a2);
  if ( CurrentDcContext )
  {
    v6 = (const WCHAR *)CurrentDcContext[1];
    v7 = 0;
    if ( v6 )
    {
      memset(v16, 0, 0x108u);
      RtlInitUnicodeString(&DestinationString, 0);
      DfscInitDfsPath(&DestinationString.Length, (struct _UNICODE_STRING *)&v16[1]);
      DfscInitDfsPath(&DestinationString.Length, (struct _UNICODE_STRING *)&v16[13]);
      v16[30] = a2;
      v16[31] = a1;
      RtlInitUnicodeString(&v15, v6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, &v15);
      }
      DomainReferral = DfscGetDomainReferral(v16, &v15, CurrentDcContext + 2);
      v7 = DomainReferral;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids,
          DomainReferral);
      }
      v9 = (const WCHAR *)CurrentDcContext[6];
      if ( v7 >= 0 )
      {
LABEL_27:
        DomainCache = DfscGetDomainCache(a2);
        if ( v6 != (const WCHAR *)CurrentDcContext[1] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
              WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, v6);
            v12 = 0;
          }
          CurrentDcContext[1] = v6;
        }
        if ( *(_DWORD *)(DomainCache + 44) == v12 )
        {
          v7 = -1073741628;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
LABEL_40:
            DfscReleaseDcContext(CurrentDcContext);
            return (unsigned int)v7;
          }
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids);
        }
      }
      else
      {
        while ( (unsigned __int64)v9 <= CurrentDcContext[7] )
        {
          v10 = v9;
          if ( v9 != v6 )
          {
            memset(v16, 0, 0x108u);
            RtlInitUnicodeString(&DestinationString, 0);
            DfscInitDfsPath(&DestinationString.Length, (struct _UNICODE_STRING *)&v16[1]);
            DfscInitDfsPath(&DestinationString.Length, (struct _UNICODE_STRING *)&v16[13]);
            RtlInitUnicodeString(&v15, v9);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, &v15);
            }
            v11 = DfscGetDomainReferral(v16, &v15, CurrentDcContext + 2);
            v7 = v11;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, v11);
            }
            v10 = v9;
          }
          while ( *v9 )
            ++v9;
          ++v9;
          if ( v7 >= 0 )
          {
            v6 = v10;
            goto LABEL_27;
          }
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids,
        (unsigned int)v7);
    }
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140022cd8  push    rbp
0x140022cda  push    rbx
0x140022cdb  push    rsi
0x140022cdc  push    rdi
0x140022cdd  push    r12
0x140022cdf  push    r13
0x140022ce1  push    r14
0x140022ce3  push    r15
0x140022ce5  lea     rbp, [rsp-58h]
0x140022cea  sub     rsp, 158h
0x140022cf1  mov     r13, rdx
0x140022cf4  mov     rdi, rcx
0x140022cf7  xorps   xmm0, xmm0
0x140022cfa  lea     rcx, [rsp+190h+var_150]; void *
0x140022cff  xor     edx, edx; Val
0x140022d01  mov     r8d, 108h; Size
0x140022d07  movups  xmmword ptr [rsp+190h+var_160.Length], xmm0
0x140022d0c  call    memset
0x140022d11  xorps   xmm0, xmm0
0x140022d14  mov     rcx, r13
0x140022d17  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x140022d1c  call    DfscGetCurrentDcContext
0x140022d21  mov     r15, rax
0x140022d24  xor     eax, eax
0x140022d26  test    r15, r15
0x140022d29  jnz     short loc_140022D61
0x140022d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d32  lea     r14, WPP_GLOBAL_Control
0x140022d39  cmp     rcx, r14
0x140022d3c  jz      short loc_140022D5A
0x140022d3e  test    dword ptr [rcx+2Ch], 100000h
0x140022d45  jz      short loc_140022D5A
0x140022d47  mov     rcx, [rcx+18h]
0x140022d4b  lea     edx, [rax+0Ah]
0x140022d4e  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x140022d55  call    WPP_SF_
0x140022d5a  xor     eax, eax
0x140022d5c  jmp     loc_140022FEA
0x140022d61  mov     r12, [r15+8]
0x140022d65  lea     r14, WPP_GLOBAL_Control
0x140022d6c  lea     rsi, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x140022d73  mov     ebx, eax
0x140022d75  test    r12, r12
0x140022d78  jz      loc_140022FB7
0x140022d7e  xor     edx, edx; Val
0x140022d80  lea     rcx, [rsp+190h+var_150]; void *
0x140022d85  mov     r8d, 108h; Size
0x140022d8b  call    memset
0x140022d90  xor     edx, edx; SourceString
0x140022d92  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x140022d97  call    cs:__imp_RtlInitUnicodeString
0x140022d9e  nop     dword ptr [rax+rax+00h]
0x140022da3  lea     rdx, [rsp+190h+var_148]
0x140022da8  lea     rcx, [rsp+190h+DestinationString]
0x140022dad  call    DfscInitDfsPath
0x140022db2  lea     rdx, [rbp+90h+var_E8]
0x140022db6  lea     rcx, [rsp+190h+DestinationString]
0x140022dbb  call    DfscInitDfsPath
0x140022dc0  mov     rdx, r12; SourceString
0x140022dc3  mov     [rbp+90h+var_60], r13
0x140022dc7  lea     rcx, [rsp+190h+var_160]; DestinationString
0x140022dcc  mov     [rbp+90h+var_58], rdi
0x140022dd0  call    cs:__imp_RtlInitUnicodeString
0x140022dd7  nop     dword ptr [rax+rax+00h]
0x140022ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140022de3  cmp     rcx, r14
0x140022de6  jz      short loc_140022E07
0x140022de8  test    dword ptr [rcx+2Ch], 400000h
0x140022def  jz      short loc_140022E07
0x140022df1  mov     rcx, [rcx+18h]
0x140022df5  lea     r9, [rsp+190h+var_160]
0x140022dfa  mov     edx, 0Bh
0x140022dff  mov     r8, rsi
0x140022e02  call    WPP_SF_Z
0x140022e07  lea     r8, [r15+10h]
0x140022e0b  lea     rdx, [rsp+190h+var_160]
0x140022e10  lea     rcx, [rsp+190h+var_150]
0x140022e15  call    DfscGetDomainReferral
0x140022e1a  mov     ebx, eax
0x140022e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022e23  cmp     rcx, r14
0x140022e26  jz      short loc_140022E45
0x140022e28  test    dword ptr [rcx+2Ch], 400000h
0x140022e2f  jz      short loc_140022E45
0x140022e31  mov     rcx, [rcx+18h]
0x140022e35  mov     edx, 0Ch
0x140022e3a  mov     r9d, eax
0x140022e3d  mov     r8, rsi
0x140022e40  call    WPP_SF_D
0x140022e45  mov     rdi, [r15+30h]
0x140022e49  xor     edx, edx
0x140022e4b  test    ebx, ebx
0x140022e4d  jns     loc_140022F47
0x140022e53  cmp     rdi, [r15+38h]
0x140022e57  ja      loc_140022FB7
0x140022e5d  mov     rax, rdi
0x140022e60  cmp     rdi, r12
0x140022e63  jz      loc_140022F33
0x140022e69  xor     edx, edx; Val
0x140022e6b  lea     rcx, [rsp+190h+var_150]; void *
0x140022e70  mov     r8d, 108h; Size
0x140022e76  call    memset
0x140022e7b  xor     edx, edx; SourceString
0x140022e7d  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x140022e82  call    cs:__imp_RtlInitUnicodeString
0x140022e89  nop     dword ptr [rax+rax+00h]
0x140022e8e  lea     rdx, [rsp+190h+var_148]
0x140022e93  lea     rcx, [rsp+190h+DestinationString]
0x140022e98  call    DfscInitDfsPath
0x140022e9d  lea     rdx, [rbp+90h+var_E8]
0x140022ea1  lea     rcx, [rsp+190h+DestinationString]
0x140022ea6  call    DfscInitDfsPath
0x140022eab  mov     rdx, rdi; SourceString
0x140022eae  lea     rcx, [rsp+190h+var_160]; DestinationString
0x140022eb3  call    cs:__imp_RtlInitUnicodeString
0x140022eba  nop     dword ptr [rax+rax+00h]
0x140022ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ec6  cmp     rcx, r14
0x140022ec9  jz      short loc_140022EEA
0x140022ecb  test    dword ptr [rcx+2Ch], 400000h
0x140022ed2  jz      short loc_140022EEA
0x140022ed4  mov     rcx, [rcx+18h]
0x140022ed8  lea     r9, [rsp+190h+var_160]
0x140022edd  mov     edx, 0Dh
0x140022ee2  mov     r8, rsi
0x140022ee5  call    WPP_SF_Z
0x140022eea  lea     r8, [r15+10h]
0x140022eee  lea     rdx, [rsp+190h+var_160]
0x140022ef3  lea     rcx, [rsp+190h+var_150]
0x140022ef8  call    DfscGetDomainReferral
0x140022efd  mov     ebx, eax
0x140022eff  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f06  cmp     rcx, r14
0x140022f09  jz      short loc_140022F28
0x140022f0b  test    dword ptr [rcx+2Ch], 400000h
0x140022f12  jz      short loc_140022F28
0x140022f14  mov     rcx, [rcx+18h]
0x140022f18  mov     edx, 0Eh
0x140022f1d  mov     r9d, eax
0x140022f20  mov     r8, rsi
0x140022f23  call    WPP_SF_D
0x140022f28  mov     rax, rdi
0x140022f2b  xor     edx, edx
0x140022f2d  jmp     short loc_140022F33
0x140022f2f  add     rdi, 2
0x140022f33  cmp     [rdi], dx
0x140022f36  jnz     short loc_140022F2F
0x140022f38  add     rdi, 2
0x140022f3c  test    ebx, ebx
0x140022f3e  js      loc_140022E53
0x140022f44  mov     r12, rax
0x140022f47  mov     rcx, r13
0x140022f4a  call    DfscGetDomainCache
0x140022f4f  mov     rdi, rax
0x140022f52  cmp     r12, [r15+8]
0x140022f56  jz      short loc_140022F87
0x140022f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f5f  cmp     rcx, r14
0x140022f62  jz      short loc_140022F83
0x140022f64  test    dword ptr [rcx+2Ch], 400000h
0x140022f6b  jz      short loc_140022F81
0x140022f6d  mov     rcx, [rcx+18h]
0x140022f71  mov     edx, 0Fh
0x140022f76  mov     r9, r12
0x140022f79  mov     r8, rsi
0x140022f7c  call    WPP_SF_S
0x140022f81  xor     edx, edx
0x140022f83  mov     [r15+8], r12
0x140022f87  cmp     [rdi+2Ch], edx
0x140022f8a  jnz     short loc_140022FB7
0x140022f8c  mov     ebx, 0C00000C4h
0x140022f91  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f98  cmp     rcx, r14
0x140022f9b  jz      short loc_140022FE0
0x140022f9d  test    dword ptr [rcx+2Ch], 100000h
0x140022fa4  jz      short loc_140022FB7
0x140022fa6  mov     rcx, [rcx+18h]
0x140022faa  mov     edx, 10h
0x140022faf  mov     r8, rsi
0x140022fb2  call    WPP_SF_
0x140022fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140022fbe  cmp     rcx, r14
0x140022fc1  jz      short loc_140022FE0
0x140022fc3  test    dword ptr [rcx+2Ch], 400000h
0x140022fca  jz      short loc_140022FE0
0x140022fcc  mov     rcx, [rcx+18h]
0x140022fd0  mov     edx, 11h
0x140022fd5  mov     r9d, ebx
0x140022fd8  mov     r8, rsi
0x140022fdb  call    WPP_SF_D
0x140022fe0  mov     rcx, r15; P
0x140022fe3  call    DfscReleaseDcContext
0x140022fe8  mov     eax, ebx
0x140022fea  add     rsp, 158h
0x140022ff1  pop     r15
0x140022ff3  pop     r14
0x140022ff5  pop     r13
0x140022ff7  pop     r12
0x140022ff9  pop     rdi
0x140022ffa  pop     rsi
0x140022ffb  pop     rbx
0x140022ffc  pop     rbp
0x140022ffd  retn
```
