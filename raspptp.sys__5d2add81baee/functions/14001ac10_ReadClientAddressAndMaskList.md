# ReadClientAddressAndMaskList

- ea: `0x14001ac10`
- end: `0x14001ae54`
- name: `ReadClientAddressAndMaskList`
- size: `580`
- prototype: `__int64 __fastcall(NDIS_HANDLE ConfigurationHandle, PNDIS_STRING Keyword)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001a7d8`

## callees

- `0x140002990`
- `0x1400156a8`
- `0x14001ac10`

## import_xrefs

- `NDIS!NdisReadConfiguration` at `0x14001ac5d`
- `NDIS!NdisReadConfiguration` at `0x14001ada0`
- `NDIS!NdisReadConfiguration` at `0x14001ac5d`
- `NDIS!NdisReadConfiguration` at `0x14001ada0`

## pseudocode

```c
__int64 __fastcall ReadClientAddressAndMaskList(
        NDIS_HANDLE ConfigurationHandle,
        PNDIS_STRING Keyword,
        UNICODE_STRING *a3,
        __int64 *a4)
{
  unsigned int v4; // r14d
  unsigned int v6; // ebx
  PNDIS_CONFIGURATION_PARAMETER v7; // rdx
  unsigned int v8; // edi
  char v9; // si
  PWSTR Buffer; // r12
  WCHAR *v11; // rcx
  WCHAR v12; // ax
  __int64 v13; // r15
  unsigned int v14; // edi
  char v15; // si
  WCHAR *v16; // rcx
  WCHAR v17; // ax
  __int64 v18; // rcx
  PNDIS_CONFIGURATION_PARAMETER v19; // rdx
  unsigned int v20; // edi
  unsigned int v21; // esi
  char v22; // r14
  PWSTR v23; // r12
  WCHAR *v24; // rcx
  WCHAR v25; // ax
  __int64 v26; // rcx
  _BYTE v28[4]; // [rsp+30h] [rbp-30h] BYREF
  int Status; // [rsp+34h] [rbp-2Ch] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+38h] [rbp-28h] BYREF
  _OWORD v31[2]; // [rsp+40h] [rbp-20h] BYREF

  v4 = 0;
  Status = -1073741823;
  *a4 = 0;
  ParameterValue = 0;
  v6 = 0;
  NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, Keyword, NdisParameterMultiString);
  if ( !Status )
  {
    v7 = ParameterValue;
    v28[0] = 0;
    v8 = 0;
    v31[0] = 0;
    v9 = 0;
    Buffer = ParameterValue->ParameterData.StringData.Buffer;
    if ( (unsigned __int64)ParameterValue->ParameterData.StringData.Length >> 1 != 1 )
    {
      do
      {
        v11 = &Buffer[v8];
        v12 = *v11;
        if ( v9 )
        {
          v9 = v12 != 0 ? v9 : 0;
        }
        else if ( v12 )
        {
          v9 = 1;
          StringToIpAddressW(v11, v31, v28);
          v7 = ParameterValue;
          if ( v28[0] )
            ++v6;
        }
        ++v8;
      }
      while ( v8 < ((unsigned __int64)v7->ParameterData.StringData.Length >> 1) - 1 );
    }
    if ( v6 )
    {
      v13 = MyMemAlloc(8 * v6, 1280332880);
      if ( v13 )
      {
        v14 = 0;
        v15 = 0;
        if ( (unsigned __int64)ParameterValue->ParameterData.StringData.Length >> 1 != 1 )
        {
          do
          {
            if ( v14 >= v6 )
              break;
            v16 = &Buffer[v4];
            v17 = *v16;
            if ( v15 )
            {
              v15 = v17 != 0 ? v15 : 0;
            }
            else if ( v17 )
            {
              v15 = 1;
              StringToIpAddressW(v16, v31, v28);
              if ( v28[0] )
              {
                v18 = v14++;
                *(_DWORD *)(v13 + 8 * v18) = *(_DWORD *)((char *)v31 + 10);
                *(_DWORD *)(v13 + 8 * v18 + 4) = -1;
              }
            }
            ++v4;
          }
          while ( v4 < ((unsigned __int64)ParameterValue->ParameterData.StringData.Length >> 1) - 1 );
        }
        NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, a3, NdisParameterMultiString);
        if ( !Status )
        {
          v19 = ParameterValue;
          v20 = 0;
          v21 = 0;
          v22 = 0;
          v23 = ParameterValue->ParameterData.StringData.Buffer;
          if ( (unsigned __int64)ParameterValue->ParameterData.StringData.Length >> 1 != 1 )
          {
            do
            {
              if ( v20 >= v6 )
                break;
              v24 = &v23[v21];
              v25 = *v24;
              if ( v22 )
              {
                v22 = v25 != 0 ? v22 : 0;
              }
              else if ( v25 )
              {
                v22 = 1;
                StringToIpAddressW(v24, v31, v28);
                if ( v28[0] )
                {
                  v26 = v20++;
                  *(_DWORD *)(v13 + 8 * v26 + 4) = *(_DWORD *)((char *)v31 + 10);
                }
                v19 = ParameterValue;
              }
              ++v21;
            }
            while ( v21 < ((unsigned __int64)v19->ParameterData.StringData.Length >> 1) - 1 );
          }
        }
        *a4 = v13;
      }
      else
      {
        return 0;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14001ac10  mov     rax, rsp
0x14001ac13  mov     [rax+8], rbx
0x14001ac17  mov     [rax+20h], r9
0x14001ac1b  mov     [rax+18h], r8
0x14001ac1f  push    rbp
0x14001ac20  push    rsi
0x14001ac21  push    rdi
0x14001ac22  push    r12
0x14001ac24  push    r13
0x14001ac26  push    r14
0x14001ac28  push    r15
0x14001ac2a  mov     rbp, rsp
0x14001ac2d  sub     rsp, 60h
0x14001ac31  xor     r14d, r14d
0x14001ac34  mov     [rbp+Status], 0C0000001h
0x14001ac3b  mov     [r9], r14
0x14001ac3e  mov     r13, rcx
0x14001ac41  mov     r9, rdx; Keyword
0x14001ac44  mov     [rbp+ParameterValue], r14
0x14001ac48  mov     r8, rcx; ConfigurationHandle
0x14001ac4b  mov     dword ptr [rax-78h], 3
0x14001ac52  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001ac56  mov     ebx, r14d
0x14001ac59  lea     rcx, [rbp+Status]; Status
0x14001ac5d  call    cs:__imp_NdisReadConfiguration
0x14001ac64  nop     dword ptr [rax+rax+00h]
0x14001ac69  cmp     [rbp+Status], r14d
0x14001ac6d  jnz     loc_14001AE39
0x14001ac73  mov     rdx, [rbp+ParameterValue]
0x14001ac77  xorps   xmm0, xmm0
0x14001ac7a  mov     [rbp+var_30], r14b
0x14001ac7e  mov     edi, r14d
0x14001ac81  movups  [rbp+var_20], xmm0
0x14001ac85  mov     sil, r14b
0x14001ac88  movzx   eax, word ptr [rdx+8]
0x14001ac8c  mov     r12, [rdx+10h]
0x14001ac90  shr     rax, 1
0x14001ac93  cmp     rax, 1
0x14001ac97  jz      short loc_14001ACE5
0x14001ac99  mov     eax, edi
0x14001ac9b  lea     rcx, [r12+rax*2]
0x14001ac9f  movzx   eax, word ptr [rcx]
0x14001aca2  test    sil, sil
0x14001aca5  jnz     short loc_14001ACCA
0x14001aca7  test    ax, ax
0x14001acaa  jz      short loc_14001ACD2
0x14001acac  lea     r8, [rbp+var_30]
0x14001acb0  mov     sil, 1
0x14001acb3  lea     rdx, [rbp+var_20]
0x14001acb7  call    StringToIpAddressW
0x14001acbc  mov     rdx, [rbp+ParameterValue]
0x14001acc0  cmp     [rbp+var_30], r14b
0x14001acc4  jz      short loc_14001ACD2
0x14001acc6  inc     ebx
0x14001acc8  jmp     short loc_14001ACD2
0x14001acca  neg     ax
0x14001accd  sbb     al, al
0x14001accf  and     sil, al
0x14001acd2  movzx   ecx, word ptr [rdx+8]
0x14001acd6  inc     edi
0x14001acd8  shr     rcx, 1
0x14001acdb  dec     rcx
0x14001acde  mov     eax, edi
0x14001ace0  cmp     rax, rcx
0x14001ace3  jb      short loc_14001AC99
0x14001ace5  test    ebx, ebx
0x14001ace7  jz      loc_14001AE39
0x14001aced  lea     ecx, ds:0[rbx*8]
0x14001acf4  mov     edx, 4C505450h
0x14001acf9  call    MyMemAlloc
0x14001acfe  mov     r15, rax
0x14001ad01  test    rax, rax
0x14001ad04  jz      loc_14001AE36
0x14001ad0a  mov     rax, [rbp+ParameterValue]
0x14001ad0e  xor     edx, edx
0x14001ad10  mov     edi, r14d
0x14001ad13  mov     sil, dl
0x14001ad16  movzx   ecx, word ptr [rax+8]
0x14001ad1a  shr     rcx, 1
0x14001ad1d  cmp     rcx, 1
0x14001ad21  jz      short loc_14001AD89
0x14001ad23  cmp     edi, ebx
0x14001ad25  jnb     short loc_14001AD89
0x14001ad27  mov     eax, r14d
0x14001ad2a  lea     rcx, [r12+rax*2]
0x14001ad2e  movzx   eax, word ptr [rcx]
0x14001ad31  test    sil, sil
0x14001ad34  jnz     short loc_14001AD68
0x14001ad36  test    ax, ax
0x14001ad39  jz      short loc_14001AD70
0x14001ad3b  lea     r8, [rbp+var_30]
0x14001ad3f  mov     sil, 1
0x14001ad42  lea     rdx, [rbp+var_20]
0x14001ad46  call    StringToIpAddressW
0x14001ad4b  xor     edx, edx
0x14001ad4d  cmp     [rbp+var_30], dl
0x14001ad50  jz      short loc_14001AD70
0x14001ad52  mov     eax, dword ptr [rbp+var_20+0Ah]
0x14001ad55  mov     ecx, edi
0x14001ad57  inc     edi
0x14001ad59  mov     [r15+rcx*8], eax
0x14001ad5d  mov     dword ptr [r15+rcx*8+4], 0FFFFFFFFh
0x14001ad66  jmp     short loc_14001AD70
0x14001ad68  neg     ax
0x14001ad6b  sbb     al, al
0x14001ad6d  and     sil, al
0x14001ad70  mov     rax, [rbp+ParameterValue]
0x14001ad74  inc     r14d
0x14001ad77  movzx   ecx, word ptr [rax+8]
0x14001ad7b  shr     rcx, 1
0x14001ad7e  dec     rcx
0x14001ad81  mov     eax, r14d
0x14001ad84  cmp     rax, rcx
0x14001ad87  jb      short loc_14001AD23
0x14001ad89  mov     r9, [rbp+Keyword]; Keyword
0x14001ad8d  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14001ad91  mov     r8, r13; ConfigurationHandle
0x14001ad94  mov     [rsp+60h+ParameterType], 3; ParameterType
0x14001ad9c  lea     rcx, [rbp+Status]; Status
0x14001ada0  call    cs:__imp_NdisReadConfiguration
0x14001ada7  nop     dword ptr [rax+rax+00h]
0x14001adac  xor     r13d, r13d
0x14001adaf  cmp     [rbp+Status], r13d
0x14001adb3  jnz     short loc_14001AE2D
0x14001adb5  mov     rdx, [rbp+ParameterValue]
0x14001adb9  mov     edi, r13d
0x14001adbc  mov     esi, r13d
0x14001adbf  mov     r14b, r13b
0x14001adc2  movzx   eax, word ptr [rdx+8]
0x14001adc6  mov     r12, [rdx+10h]
0x14001adca  shr     rax, 1
0x14001adcd  cmp     rax, 1
0x14001add1  jz      short loc_14001AE2D
0x14001add3  cmp     edi, ebx
0x14001add5  jnb     short loc_14001AE2D
0x14001add7  mov     eax, esi
0x14001add9  lea     rcx, [r12+rax*2]
0x14001addd  movzx   eax, word ptr [rcx]
0x14001ade0  test    r14b, r14b
0x14001ade3  jnz     short loc_14001AE12
0x14001ade5  test    ax, ax
0x14001ade8  jz      short loc_14001AE1A
0x14001adea  lea     r8, [rbp+var_30]
0x14001adee  mov     r14b, 1
0x14001adf1  lea     rdx, [rbp+var_20]
0x14001adf5  call    StringToIpAddressW
0x14001adfa  cmp     [rbp+var_30], r13b
0x14001adfe  jz      short loc_14001AE0C
0x14001ae00  mov     eax, dword ptr [rbp+var_20+0Ah]
0x14001ae03  mov     ecx, edi
0x14001ae05  inc     edi
0x14001ae07  mov     [r15+rcx*8+4], eax
0x14001ae0c  mov     rdx, [rbp+ParameterValue]
0x14001ae10  jmp     short loc_14001AE1A
0x14001ae12  neg     ax
0x14001ae15  sbb     al, al
0x14001ae17  and     r14b, al
0x14001ae1a  movzx   ecx, word ptr [rdx+8]
0x14001ae1e  inc     esi
0x14001ae20  shr     rcx, 1
0x14001ae23  dec     rcx
0x14001ae26  mov     eax, esi
0x14001ae28  cmp     rax, rcx
0x14001ae2b  jb      short loc_14001ADD3
0x14001ae2d  mov     rax, [rbp+arg_18]
0x14001ae31  mov     [rax], r15
0x14001ae34  jmp     short loc_14001AE39
0x14001ae36  mov     ebx, r14d
0x14001ae39  mov     eax, ebx
0x14001ae3b  mov     rbx, [rsp+60h+arg_0]
0x14001ae43  add     rsp, 60h
0x14001ae47  pop     r15
0x14001ae49  pop     r14
0x14001ae4b  pop     r13
0x14001ae4d  pop     r12
0x14001ae4f  pop     rdi
0x14001ae50  pop     rsi
0x14001ae51  pop     rbp
0x14001ae52  retn
```
