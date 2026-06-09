# Smb2ProcessSigningCapabilities

- ea: `0x140057930`
- end: `0x140057b41`
- name: `Smb2ProcessSigningCapabilities`
- size: `529`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140056aa0`
- `0x140056c30`

## callees

- `0x1400230b0`
- `0x140029764`
- `0x1400297fc`
- `0x14002ba84`
- `0x14002cdb0`
- `0x140057930`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140057a55`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140057a6c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140057a55`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140057a6c`

## pseudocode

```c
__int64 __fastcall Smb2ProcessSigningCapabilities(__int64 a1, unsigned __int16 *a2, __int64 a3, _DWORD *a4, __int64 a5)
{
  unsigned int v8; // edx
  __int64 i; // rdi
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 ConfigurationBlock; // rax
  __int64 v14; // r9

  if ( (*a4 & 0x20) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
    }
    Smb2LkmdTelCollectParsingFailureNegotiateHelper(a5, 28, a3, a4);
    return 3221225667LL;
  }
  else
  {
    *a4 |= 0x20u;
    if ( (unsigned int)a3 >= 4 )
    {
      v8 = *a2;
      if ( v8 == 1 )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v10 = *(unsigned __int16 *)(MRxSmbGetConfigurationBlock(a1) + 372);
          if ( (unsigned int)i >= (unsigned int)v10 )
            break;
          ConfigurationBlock = MRxSmbGetConfigurationBlock(v10);
          v14 = a2[1];
          if ( (_DWORD)v14 == *(_DWORD *)(ConfigurationBlock + 4 * i + 360) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_48214901e2dc3d654588515547715784_Traceguids, v14);
            }
            *(_DWORD *)(a1 + 600) = a2[1];
            return 0;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_48214901e2dc3d654588515547715784_Traceguids, a2[1], a1);
        }
        Smb2LkmdTelCollectParsingFailureNegotiateHelper(a5, 31, v11, v12);
        return 3221225667LL;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_48214901e2dc3d654588515547715784_Traceguids, v8);
        }
        Smb2LkmdTelCollectParsingFailureNegotiateHelper(a5, 30, a3, a4);
        return 3221225667LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_ddq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (unsigned int)a3);
      }
      Smb2LkmdTelCollectParsingFailureNegotiateHelper(a5, 29, a3, a4);
      return 3221225667LL;
    }
  }
}

```

## disassembly

```asm
0x140057930  mov     [rsp+arg_8], rbx
0x140057935  push    rsi
0x140057936  sub     rsp, 30h
0x14005793a  mov     eax, [r9]
0x14005793d  mov     rbx, rdx
0x140057940  mov     rsi, rcx
0x140057943  test    al, 20h
0x140057945  jz      short loc_14005799F
0x140057947  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005794e  lea     rax, WPP_GLOBAL_Control
0x140057955  cmp     rcx, rax
0x140057958  jz      short loc_14005797F
0x14005795a  mov     eax, [rcx+2Ch]
0x14005795d  test    al, 1
0x14005795f  jz      short loc_14005797F
0x140057961  cmp     byte ptr [rcx+29h], 1
0x140057965  jb      short loc_14005797F
0x140057967  mov     rcx, [rcx+18h]
0x14005796b  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x140057972  mov     edx, 0Bh
0x140057977  mov     r9, rsi
0x14005797a  call    WPP_SF_q
0x14005797f  mov     rcx, [rsp+38h+arg_20]
0x140057984  mov     edx, 1Ch
0x140057989  call    Smb2LkmdTelCollectParsingFailureNegotiateHelper
0x14005798e  mov     eax, 0C00000C3h
0x140057993  mov     rbx, [rsp+38h+arg_8]
0x140057998  add     rsp, 30h
0x14005799c  pop     rsi
0x14005799d  retn
0x14005799f  or      eax, 20h
0x1400579a2  mov     [r9], eax
0x1400579a5  cmp     r8d, 4
0x1400579a9  jnb     short loc_1400579F5
0x1400579ab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400579b2  lea     rax, WPP_GLOBAL_Control
0x1400579b9  cmp     rcx, rax
0x1400579bc  jz      short loc_1400579DC
0x1400579be  mov     eax, [rcx+2Ch]
0x1400579c1  test    al, 1
0x1400579c3  jz      short loc_1400579DC
0x1400579c5  cmp     byte ptr [rcx+29h], 1
0x1400579c9  jb      short loc_1400579DC
0x1400579cb  mov     rcx, [rcx+18h]
0x1400579cf  mov     r9d, r8d
0x1400579d2  mov     [rsp+38h+var_10], rsi
0x1400579d7  call    WPP_SF_ddq
0x1400579dc  mov     rcx, [rsp+38h+arg_20]
0x1400579e1  mov     edx, 1Dh
0x1400579e6  call    Smb2LkmdTelCollectParsingFailureNegotiateHelper
0x1400579eb  mov     eax, 0C00000C3h
0x1400579f0  jmp     loc_140057B35
0x1400579f5  movzx   edx, word ptr [rdx]
0x1400579f8  cmp     edx, 1
0x1400579fb  jz      short loc_140057A4E
0x1400579fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057a04  lea     rax, WPP_GLOBAL_Control
0x140057a0b  cmp     rcx, rax
0x140057a0e  jz      short loc_140057A35
0x140057a10  mov     eax, [rcx+2Ch]
0x140057a13  test    al, 1
0x140057a15  jz      short loc_140057A35
0x140057a17  cmp     byte ptr [rcx+29h], 1
0x140057a1b  jb      short loc_140057A35
0x140057a1d  mov     rcx, [rcx+18h]
0x140057a21  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x140057a28  mov     r9d, edx
0x140057a2b  mov     edx, 0Dh
0x140057a30  call    WPP_SF_d
0x140057a35  mov     rcx, [rsp+38h+arg_20]
0x140057a3a  mov     edx, 1Eh
0x140057a3f  call    Smb2LkmdTelCollectParsingFailureNegotiateHelper
0x140057a44  mov     eax, 0C00000C3h
0x140057a49  jmp     loc_140057B35
0x140057a4e  mov     [rsp+38h+arg_0], rdi
0x140057a53  xor     edi, edi
0x140057a55  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140057a5c  nop     dword ptr [rax+rax+00h]
0x140057a61  movzx   ecx, word ptr [rax+174h]
0x140057a68  cmp     edi, ecx
0x140057a6a  jnb     short loc_140057ADD
0x140057a6c  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140057a73  nop     dword ptr [rax+rax+00h]
0x140057a78  movzx   r9d, word ptr [rbx+2]
0x140057a7d  cmp     r9d, [rax+rdi*4+168h]
0x140057a85  jz      short loc_140057A8B
0x140057a87  inc     edi
0x140057a89  jmp     short loc_140057A55
0x140057a8b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057a92  lea     rax, WPP_GLOBAL_Control
0x140057a99  cmp     rcx, rax
0x140057a9c  jz      short loc_140057AC0
0x140057a9e  mov     eax, [rcx+2Ch]
0x140057aa1  test    al, 4
0x140057aa3  jz      short loc_140057AC0
0x140057aa5  cmp     byte ptr [rcx+29h], 2
0x140057aa9  jb      short loc_140057AC0
0x140057aab  mov     rcx, [rcx+18h]
0x140057aaf  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x140057ab6  mov     edx, 0Eh
0x140057abb  call    WPP_SF_d
0x140057ac0  movzx   eax, word ptr [rbx+2]
0x140057ac4  mov     rdi, [rsp+38h+arg_0]
0x140057ac9  mov     [rsi+258h], eax
0x140057acf  xor     eax, eax
0x140057ad1  mov     rbx, [rsp+38h+arg_8]
0x140057ad6  add     rsp, 30h
0x140057ada  pop     rsi
0x140057adb  retn
0x140057add  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057ae4  lea     rax, WPP_GLOBAL_Control
0x140057aeb  cmp     rcx, rax
0x140057aee  jz      short loc_140057B1C
0x140057af0  mov     eax, [rcx+2Ch]
0x140057af3  test    al, 1
0x140057af5  jz      short loc_140057B1C
0x140057af7  cmp     byte ptr [rcx+29h], 1
0x140057afb  jb      short loc_140057B1C
0x140057afd  movzx   r9d, word ptr [rbx+2]
0x140057b02  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x140057b09  mov     rcx, [rcx+18h]
0x140057b0d  mov     edx, 0Fh
0x140057b12  mov     [rsp+38h+var_18], rsi
0x140057b17  call    WPP_SF_dq
0x140057b1c  mov     rcx, [rsp+38h+arg_20]
0x140057b21  mov     edx, 1Fh
0x140057b26  call    Smb2LkmdTelCollectParsingFailureNegotiateHelper
0x140057b2b  mov     rdi, [rsp+38h+arg_0]
0x140057b30  mov     eax, 0C00000C3h
0x140057b35  mov     rbx, [rsp+38h+arg_8]
0x140057b3a  add     rsp, 30h
0x140057b3e  pop     rsi
0x140057b3f  retn
```
