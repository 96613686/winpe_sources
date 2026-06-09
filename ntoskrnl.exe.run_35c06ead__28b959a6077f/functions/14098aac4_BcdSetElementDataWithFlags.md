# BcdSetElementDataWithFlags

- ea: `0x14098aac4`
- end: `0x14098ad64`
- name: `BcdSetElementDataWithFlags`
- size: `672`
- prototype: ``
- caller_count: `10`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x14079fe44`
- `0x1407a0158`
- `0x1407c8664`
- `0x14082ffcc`
- `0x140988764`
- `0x14098a660`
- `0x14098a9c0`
- `0x14098aaa4`
- `0x14098c020`
- `0x140ae3b40`

## callees

- `0x140541e90`
- `0x1406d9d70`
- `0x140987e20`
- `0x140989778`
- `0x1409897b0`
- `0x140989ab0`
- `0x14098aac4`
- `0x14098b544`
- `0x14098b748`
- `0x14098bc00`
- `0x14098bd64`
- `0x14098be90`
- `0x14098bef0`
- `0x14098cf8c`
- `0x14098d68c`
- `0x14098dc20`
- `0x140bae8e0`

## string_xrefs

- `0x14098ad0a`: `Failed to set registry data for element %s. Status: %x`
- `0x14098ac94`: `Failed to open key for object's elements. Status: %x`
- `0x14098ace7`: `Failed to open key for element %s. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdSetElementDataWithFlags(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  HANDLE v7; // rdi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  PVOID v15; // r15
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v19; // r8d
  int *v20; // [rsp+28h] [rbp-59h]
  _BYTE v21[4]; // [rsp+30h] [rbp-51h] BYREF
  int v22; // [rsp+34h] [rbp-4Dh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-41h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-39h] BYREF
  PVOID P; // [rsp+50h] [rbp-31h]
  __int64 v27; // [rsp+58h] [rbp-29h]
  wchar_t DstBuf[24]; // [rsp+60h] [rbp-21h] BYREF

  v27 = a4;
  v24 = a2;
  v22 = 0;
  if ( !a4 && a5 )
    return 3221225485LL;
  v23 = 0;
  v7 = 0;
  v21[0] = 0;
  Handle = 0;
  P = 0;
  if ( !a5 )
  {
    BiDeleteElement(a1, a2);
    return 0;
  }
  BiLogMessage(2, L"Setting element %08x", a2);
  LOBYTE(v8) = a1 & 1;
  v9 = BiAcquireBcdSyncMutant(v8);
  if ( v9 < 0 )
  {
    BiLogMessage(4, L"BcdSetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v9);
    return v19;
  }
  v10 = BiOpenKey(a1, L"Elements", 131101, &v23);
  v11 = v10;
  if ( v10 < 0 )
  {
    BiLogMessage(4, L"Failed to open key for object's elements. Status: %x", (unsigned int)v10);
    goto LABEL_22;
  }
  if ( !ultow_s(a2, DstBuf, 0x16u, 16) )
  {
    v13 = BiCreateKey(v23, DstBuf, 65538, 1, &Handle, v21);
    v11 = v13;
    if ( v13 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for element %s. Status: %x", DstBuf, (unsigned int)v13);
      v7 = Handle;
    }
    else
    {
      v20 = &v22;
      v14 = BiConvertElementToRegistryData(a2, v27, a5);
      v7 = Handle;
      v11 = v14;
      v15 = P;
      if ( v14 < 0 )
      {
        BiLogMessage(4, L"Failed to convert data for element %s. Status: %x", DstBuf, (unsigned int)v14);
      }
      else
      {
        v16 = BiConvertElementFormatToValueType(HIBYTE(a2) & 0xF);
        LODWORD(v20) = v22;
        v17 = BiSetRegistryValue(v7, L"Element", 0, v16, v15, v20);
        v11 = v17;
        if ( v17 < 0 )
          BiLogMessage(4, L"Failed to set registry data for element %s. Status: %x", DstBuf, (unsigned int)v17);
      }
      if ( v15 )
        ExFreePoolWithTag(v15, 0x4B444342u);
      if ( v11 >= 0 )
        goto LABEL_13;
    }
LABEL_22:
    if ( v21[0] )
    {
      BiDeleteKey(v7);
      v7 = 0;
    }
LABEL_13:
    if ( v7 )
      BiCloseKey(v7);
    goto LABEL_15;
  }
  v11 = -1073741823;
LABEL_15:
  if ( v23 )
    BiCloseKey(v23);
  if ( v11 >= 0 )
  {
    if ( (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v24) )
      BiSetFirmwareModifiedFromObject(a1);
  }
  LOBYTE(v12) = a1 & 1;
  BiReleaseBcdSyncMutant(v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14098aac4  push    rbp
0x14098aac6  push    rbx
0x14098aac7  push    rsi
0x14098aac8  push    rdi
0x14098aac9  push    r13
0x14098aacb  push    r14
0x14098aacd  push    r15
0x14098aacf  lea     rbp, [rsp-1Fh]
0x14098aad4  sub     rsp, 0A0h
0x14098aadb  mov     rax, cs:__security_cookie
0x14098aae2  xor     rax, rsp
0x14098aae5  mov     [rbp+4Fh+var_40], rax
0x14098aae9  mov     r15d, [rbp+4Fh+arg_20]
0x14098aaed  xor     ebx, ebx
0x14098aaef  mov     [rbp+4Fh+var_78], r9
0x14098aaf3  mov     esi, edx
0x14098aaf5  mov     [rbp+4Fh+var_90], edx
0x14098aaf8  mov     r14, rcx
0x14098aafb  mov     [rbp+4Fh+var_9C], ebx
0x14098aafe  test    r9, r9
0x14098ab01  jz      loc_14098AC81
0x14098ab07  mov     [rbp+4Fh+var_98], rbx
0x14098ab0b  mov     rdi, rbx
0x14098ab0e  mov     [rbp+4Fh+var_A0], bl
0x14098ab11  mov     [rbp+4Fh+Handle], rbx
0x14098ab15  mov     [rbp+4Fh+P], rbx
0x14098ab19  test    r15d, r15d
0x14098ab1c  jz      loc_14098ACB7
0x14098ab22  mov     r8d, esi
0x14098ab25  lea     rdx, aSettingElement; "Setting element %08x"
0x14098ab2c  mov     ecx, 2
0x14098ab31  call    BiLogMessage
0x14098ab36  mov     r13b, r14b
0x14098ab39  and     r13b, 1
0x14098ab3d  mov     cl, r13b
0x14098ab40  call    BiAcquireBcdSyncMutant
0x14098ab45  mov     r8d, eax
0x14098ab48  test    eax, eax
0x14098ab4a  js      loc_14098ACC0
0x14098ab50  lea     r9, [rbp+4Fh+var_98]
0x14098ab54  mov     r8d, 2001Dh
0x14098ab5a  lea     rdx, aElements; "Elements"
0x14098ab61  mov     rcx, r14
0x14098ab64  call    BiOpenKey
0x14098ab69  mov     ebx, eax
0x14098ab6b  test    eax, eax
0x14098ab6d  js      loc_14098AC91
0x14098ab73  mov     r9d, 10h; Radix
0x14098ab79  lea     rdx, [rbp+4Fh+DstBuf]; DstBuf
0x14098ab7d  mov     ecx, esi; Val
0x14098ab7f  lea     r8d, [r9+6]; SizeInWords
0x14098ab83  call    _ultow_s
0x14098ab88  test    eax, eax
0x14098ab8a  jnz     loc_14098ACD6
0x14098ab90  mov     rcx, [rbp+4Fh+var_98]
0x14098ab94  lea     rax, [rbp+4Fh+var_A0]
0x14098ab98  mov     [rsp+0D0h+var_A8], rax
0x14098ab9d  lea     rdx, [rbp+4Fh+DstBuf]
0x14098aba1  lea     rax, [rbp+4Fh+Handle]
0x14098aba5  mov     r9d, 1
0x14098abab  mov     r8d, 10002h
0x14098abb1  mov     [rsp+0D0h+var_B0], rax
0x14098abb6  call    BiCreateKey
0x14098abbb  mov     ebx, eax
0x14098abbd  test    eax, eax
0x14098abbf  js      loc_14098ACE0
0x14098abc5  mov     rdx, [rbp+4Fh+var_78]
0x14098abc9  lea     rax, [rbp+4Fh+var_9C]
0x14098abcd  mov     [rsp+0D0h+var_A8], rax
0x14098abd2  mov     r8d, r15d
0x14098abd5  lea     rax, [rbp+4Fh+P]
0x14098abd9  mov     ecx, esi
0x14098abdb  mov     [rsp+0D0h+var_B0], rax
0x14098abe0  call    BiConvertElementToRegistryData
0x14098abe5  mov     rdi, [rbp+4Fh+Handle]
0x14098abe9  mov     ebx, eax
0x14098abeb  mov     r15, [rbp+4Fh+P]
0x14098abef  test    eax, eax
0x14098abf1  js      loc_14098ACFE
0x14098abf7  shr     esi, 18h
0x14098abfa  and     esi, 0Fh
0x14098abfd  mov     ecx, esi
0x14098abff  call    BiConvertElementFormatToValueType
0x14098ac04  mov     r9d, eax
0x14098ac07  lea     rdx, aElement; "Element"
0x14098ac0e  mov     eax, [rbp+4Fh+var_9C]
0x14098ac11  xor     r8d, r8d
0x14098ac14  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14098ac18  mov     rcx, rdi
0x14098ac1b  mov     [rsp+0D0h+var_B0], r15
0x14098ac20  call    BiSetRegistryValue
0x14098ac25  mov     ebx, eax
0x14098ac27  test    eax, eax
0x14098ac29  js      loc_14098AD0A
0x14098ac2f  test    r15, r15
0x14098ac32  jnz     loc_14098AD16
0x14098ac38  test    ebx, ebx
0x14098ac3a  js      short loc_14098ACA5
0x14098ac3c  test    rdi, rdi
0x14098ac3f  jnz     loc_14098AD28
0x14098ac45  cmp     [rbp+4Fh+var_98], 0
0x14098ac4a  jnz     loc_14098AD35
0x14098ac50  test    ebx, ebx
0x14098ac52  jns     loc_14098AD43
0x14098ac58  mov     cl, r13b
0x14098ac5b  call    BiReleaseBcdSyncMutant
0x14098ac60  mov     eax, ebx
0x14098ac62  mov     rcx, [rbp+4Fh+var_40]
0x14098ac66  xor     rcx, rsp; StackCookie
0x14098ac69  call    __security_check_cookie
0x14098ac6e  add     rsp, 0A0h
0x14098ac75  pop     r15
0x14098ac77  pop     r14
0x14098ac79  pop     r13
0x14098ac7b  pop     rdi
0x14098ac7c  pop     rsi
0x14098ac7d  pop     rbx
0x14098ac7e  pop     rbp
0x14098ac7f  retn
0x14098ac81  test    r15d, r15d
0x14098ac84  jz      loc_14098AB07
0x14098ac8a  mov     eax, 0C000000Dh
0x14098ac8f  jmp     short loc_14098AC62
0x14098ac91  mov     r8d, eax
0x14098ac94  lea     rdx, aFailedToOpenKe_2; "Failed to open key for object's element"...
0x14098ac9b  mov     ecx, 4
0x14098aca0  call    BiLogMessage
0x14098aca5  cmp     [rbp+4Fh+var_A0], 0
0x14098aca9  jz      short loc_14098AC3C
0x14098acab  mov     rcx, rdi
0x14098acae  call    BiDeleteKey
0x14098acb3  xor     edi, edi
0x14098acb5  jmp     short loc_14098AC3C
0x14098acb7  call    BiDeleteElement
0x14098acbc  xor     eax, eax
0x14098acbe  jmp     short loc_14098AC62
0x14098acc0  lea     rdx, aBcdsetelementd; "BcdSetElementDataWithFlags: Failed to a"...
0x14098acc7  mov     ecx, 4
0x14098accc  call    BiLogMessage
0x14098acd1  mov     eax, r8d
0x14098acd4  jmp     short loc_14098AC62
0x14098acd6  mov     ebx, 0C0000001h
0x14098acdb  jmp     loc_14098AC45
0x14098ace0  mov     r9d, eax
0x14098ace3  lea     r8, [rbp+4Fh+DstBuf]
0x14098ace7  lea     rdx, aFailedToOpenKe_3; "Failed to open key for element %s. Stat"...
0x14098acee  mov     ecx, 4
0x14098acf3  call    BiLogMessage
0x14098acf8  mov     rdi, [rbp+4Fh+Handle]
0x14098acfc  jmp     short loc_14098ACA5
0x14098acfe  lea     rdx, aFailedToConver_3; "Failed to convert data for element %s. "...
0x14098ad05  jmp     loc_140B61A22
0x14098ad0a  lea     rdx, aFailedToSetReg; "Failed to set registry data for element"...
0x14098ad11  jmp     loc_140B61A22
0x14098ad16  mov     edx, 4B444342h; Tag
0x14098ad1b  mov     rcx, r15; P
0x14098ad1e  call    ExFreePoolWithTag
0x14098ad23  jmp     loc_14098AC38
0x14098ad28  mov     rcx, rdi; Handle
0x14098ad2b  call    BiCloseKey
0x14098ad30  jmp     loc_14098AC45
0x14098ad35  mov     rcx, [rbp+4Fh+var_98]; Handle
0x14098ad39  call    BiCloseKey
0x14098ad3e  jmp     loc_14098AC50
0x14098ad43  lea     rdx, [rbp+4Fh+var_90]
0x14098ad47  mov     rcx, r14
0x14098ad4a  call    BiIsLinkedToFirmwareVariable
0x14098ad4f  test    al, al
0x14098ad51  jz      loc_14098AC58
0x14098ad57  mov     rcx, r14
0x14098ad5a  call    BiSetFirmwareModifiedFromObject
0x14098ad5f  jmp     loc_14098AC58
0x140b61a22  mov     r9d, eax
0x140b61a25  lea     r8, [rbp+4Fh+DstBuf]
0x140b61a29  mov     ecx, 4
0x140b61a2e  call    BiLogMessage
0x140b61a33  nop
0x140b61a34  jmp     loc_14098AC2F
```
