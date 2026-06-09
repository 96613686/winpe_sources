# CreateFontPackage

- ea: `0x180002a70`
- end: `0x180002c71`
- name: `CreateFontPackage`
- size: `513`
- prototype: `unsigned int __cdecl(const unsigned __int8 *puchSrcBuffer, const unsigned int ulSrcBufferSize, unsigned __int8 **ppuchFontPackageBuffer, unsigned int *pulFontPackageBufferSize, unsigned int *pulBytesWritten, const unsigned __int16 usFlag, const unsigned __int16 usTTCIndex, const unsigned __int16 usSubsetFormat, const unsigned __int16 usSubsetLanguage, const unsigned __int16 usSubsetPlatform, const unsigned __int16 usSubsetEncoding, const unsigned __int16 *pusSubsetKeepList, const unsigned __int16 usSubsetListCount, CFP_ALLOCPROC lpfnAllocate, CFP_REALLOCPROC lpfnReAllocate, CFP_FREEPROC lpfnFree, void *lpvReserved)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002a70`
- `0x1800036f0`
- `0x180003b1c`
- `0x180005f70`
- `0x18000611c`
- `0x180007cd4`
- `0x180008714`
- `0x18001ac90`

## string_xrefs

- `0x180002c14`: `CreateFontPackage`

## pseudocode

```c
unsigned int __cdecl CreateFontPackage(
        const unsigned __int8 *puchSrcBuffer,
        const unsigned int ulSrcBufferSize,
        unsigned __int8 **ppuchFontPackageBuffer,
        unsigned int *pulFontPackageBufferSize,
        unsigned int *pulBytesWritten,
        const unsigned __int16 usFlag,
        const unsigned __int16 usTTCIndex,
        const unsigned __int16 usSubsetFormat,
        const unsigned __int16 usSubsetLanguage,
        const unsigned __int16 usSubsetPlatform,
        const unsigned __int16 usSubsetEncoding,
        const unsigned __int16 *pusSubsetKeepList,
        const unsigned __int16 usSubsetListCount,
        CFP_ALLOCPROC lpfnAllocate,
        CFP_REALLOCPROC lpfnReAllocate,
        CFP_FREEPROC lpfnFree,
        void *lpvReserved)
{
  unsigned __int16 DeltaTTF; // cx
  CFP_FREEPROC v20; // r8
  CFP_REALLOCPROC v22; // rdx
  int v24; // eax
  unsigned int v26; // ebx
  int v27; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v28; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v29; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v30; // [rsp+90h] [rbp-70h] BYREF
  CFP_REALLOCPROC v31; // [rsp+98h] [rbp-68h]
  CFP_FREEPROC v32; // [rsp+A0h] [rbp-60h]
  _QWORD v33[42]; // [rsp+B0h] [rbp-50h] BYREF

  DeltaTTF = 0;
  v30 = 0;
  v20 = lpfnFree;
  v22 = lpfnReAllocate;
  v31 = lpfnReAllocate;
  v24 = 0;
  v32 = lpfnFree;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  if ( !puchSrcBuffer )
    return 1100;
  if ( !ulSrcBufferSize )
    return 1101;
  if ( !ppuchFontPackageBuffer )
    return 1102;
  if ( !pulFontPackageBufferSize )
    return 1103;
  if ( !pulBytesWritten )
    return 1104;
  if ( (usFlag & 4) != 0 )
  {
    DeltaTTF = TTCOffsetTableOffset(puchSrcBuffer, ulSrcBufferSize, usTTCIndex, &v27);
    if ( DeltaTTF )
      return 1106;
    v24 = v27;
    v22 = v31;
    v20 = v32;
  }
  if ( (usFlag & 1) != 0 )
  {
    if ( usSubsetFormat > 2u )
      return 1107;
    DeltaTTF = CreateDeltaTTF(
                 (_DWORD)puchSrcBuffer,
                 ulSrcBufferSize,
                 (unsigned int)&v30,
                 (unsigned int)&v28,
                 (__int64)&v29,
                 usSubsetFormat,
                 usSubsetLanguage,
                 usSubsetPlatform,
                 usSubsetEncoding,
                 (usFlag >> 3) & 1,
                 (__int64)pusSubsetKeepList,
                 usSubsetListCount,
                 (__int64)v22,
                 (__int64)v20,
                 v24);
    if ( !DeltaTTF )
    {
      *ppuchFontPackageBuffer = v30;
      *pulFontPackageBufferSize = v28;
      *pulBytesWritten = v29;
    }
  }
  v26 = DeltaTTF;
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "CreateFontPackage");
  v33[0] = &FontSubsettingTelemetry::CreateFontPackage::`vftable';
  FontSubsettingTelemetry::CreateFontPackage::StartActivity((FontSubsettingTelemetry::CreateFontPackage *)v33);
  FontSubsettingTelemetry::CreateFontPackage::Stop((FontSubsettingTelemetry::CreateFontPackage *)v33, v26);
  FontSubsettingTelemetry::CreateFontPackage::~CreateFontPackage((FontSubsettingTelemetry::CreateFontPackage *)v33);
  return v26;
}

```

## disassembly

```asm
0x180002a70  push    rbp
0x180002a72  push    rbx
0x180002a73  push    rsi
0x180002a74  push    rdi
0x180002a75  push    r12
0x180002a77  push    r13
0x180002a79  push    r14
0x180002a7b  push    r15
0x180002a7d  lea     rbp, [rsp-118h]
0x180002a85  sub     rsp, 218h
0x180002a8c  mov     rax, cs:__security_cookie
0x180002a93  xor     rax, rsp
0x180002a96  mov     [rbp+150h+var_50], rax
0x180002a9d  mov     r15, [rbp+150h+pulBytesWritten]
0x180002aa4  mov     r12, rcx
0x180002aa7  mov     r13, [rbp+150h+pusSubsetKeepList]
0x180002aae  xor     ecx, ecx
0x180002ab0  mov     [rbp+150h+var_1C0], rcx
0x180002ab4  mov     rsi, r8
0x180002ab7  mov     r8, [rbp+150h+lpfnFree]
0x180002abe  mov     edi, edx
0x180002ac0  mov     rdx, [rbp+150h+lpfnReAllocate]
0x180002ac7  mov     r14, r9
0x180002aca  mov     [rbp+150h+var_1B8], rdx
0x180002ace  mov     eax, ecx
0x180002ad0  mov     [rbp+150h+var_1B0], r8
0x180002ad4  mov     [rbp+150h+var_1CC], ecx
0x180002ad7  mov     [rbp+150h+var_1C8], ecx
0x180002ada  mov     [rbp+150h+var_1D0], ecx
0x180002add  test    r12, r12
0x180002ae0  jnz     short loc_180002AEC
0x180002ae2  mov     eax, 44Ch
0x180002ae7  jmp     loc_180002C4E
0x180002aec  test    edi, edi
0x180002aee  jnz     short loc_180002AFA
0x180002af0  mov     eax, 44Dh
0x180002af5  jmp     loc_180002C4E
0x180002afa  test    rsi, rsi
0x180002afd  jnz     short loc_180002B09
0x180002aff  mov     eax, 44Eh
0x180002b04  jmp     loc_180002C4E
0x180002b09  test    r14, r14
0x180002b0c  jnz     short loc_180002B18
0x180002b0e  mov     eax, 44Fh
0x180002b13  jmp     loc_180002C4E
0x180002b18  test    r15, r15
0x180002b1b  jnz     short loc_180002B27
0x180002b1d  mov     eax, 450h
0x180002b22  jmp     loc_180002C4E
0x180002b27  movzx   ebx, [rbp+150h+usFlag]
0x180002b2e  test    bl, 4
0x180002b31  jz      short loc_180002B66
0x180002b33  movzx   r8d, [rbp+150h+usTTCIndex]
0x180002b3b  lea     r9, [rbp+150h+var_1D0]
0x180002b3f  mov     edx, edi
0x180002b41  mov     rcx, r12
0x180002b44  call    TTCOffsetTableOffset
0x180002b49  movzx   ecx, ax
0x180002b4c  test    ax, ax
0x180002b4f  jz      short loc_180002B5B
0x180002b51  mov     eax, 452h
0x180002b56  jmp     loc_180002C4E
0x180002b5b  mov     eax, [rbp+150h+var_1D0]
0x180002b5e  mov     rdx, [rbp+150h+var_1B8]
0x180002b62  mov     r8, [rbp+150h+var_1B0]
0x180002b66  test    bl, 1
0x180002b69  jz      loc_180002C11
0x180002b6f  movzx   ecx, [rbp+150h+usSubsetFormat]
0x180002b76  cmp     cx, 2
0x180002b7a  jbe     short loc_180002B86
0x180002b7c  mov     eax, 453h
0x180002b81  jmp     loc_180002C4E
0x180002b86  mov     [rsp+250h+var_1E0], eax
0x180002b8a  lea     r9, [rbp+150h+var_1CC]
0x180002b8e  movzx   eax, [rbp+150h+usSubsetListCount]
0x180002b95  mov     [rsp+250h+var_1E8], r8
0x180002b9a  lea     r8, [rbp+150h+var_1C0]
0x180002b9e  mov     [rsp+250h+var_1F0], rdx
0x180002ba3  mov     edx, edi
0x180002ba5  mov     [rsp+250h+var_1F8], ax
0x180002baa  movzx   eax, [rbp+150h+usSubsetEncoding]
0x180002bb1  mov     [rsp+250h+var_200], r13
0x180002bb6  shr     bx, 3
0x180002bba  and     bx, 1
0x180002bbe  mov     [rsp+250h+var_208], bx
0x180002bc3  mov     [rsp+250h+var_210], ax
0x180002bc8  movzx   eax, [rbp+150h+usSubsetPlatform]
0x180002bcf  mov     [rsp+250h+var_218], ax
0x180002bd4  movzx   eax, [rbp+150h+usSubsetLanguage]
0x180002bdb  mov     [rsp+250h+var_220], ax
0x180002be0  lea     rax, [rbp+150h+var_1C8]
0x180002be4  mov     [rsp+250h+var_228], cx
0x180002be9  mov     rcx, r12
0x180002bec  mov     [rsp+250h+var_230], rax
0x180002bf1  call    CreateDeltaTTF
0x180002bf6  movzx   ecx, ax
0x180002bf9  test    ax, ax
0x180002bfc  jnz     short loc_180002C11
0x180002bfe  mov     rax, [rbp+150h+var_1C0]
0x180002c02  mov     [rsi], rax
0x180002c05  mov     eax, [rbp+150h+var_1CC]
0x180002c08  mov     [r14], eax
0x180002c0b  mov     eax, [rbp+150h+var_1C8]
0x180002c0e  mov     [r15], eax
0x180002c11  movzx   ebx, cx
0x180002c14  lea     rdx, aCreatefontpack_0; "CreateFontPackage"
0x180002c1b  lea     rcx, [rbp+150h+var_1A0]
0x180002c1f  call    ??0?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180002c24  lea     rax, ??_7CreateFontPackage@FontSubsettingTelemetry@@6B@; const FontSubsettingTelemetry::CreateFontPackage::`vftable'
0x180002c2b  lea     rcx, [rbp+150h+var_1A0]; this
0x180002c2f  mov     [rbp+150h+var_1A0], rax
0x180002c33  call    ?StartActivity@CreateFontPackage@FontSubsettingTelemetry@@QEAAXXZ; FontSubsettingTelemetry::CreateFontPackage::StartActivity(void)
0x180002c38  mov     edx, ebx; unsigned int
0x180002c3a  lea     rcx, [rbp+150h+var_1A0]; this
0x180002c3e  call    ?Stop@CreateFontPackage@FontSubsettingTelemetry@@QEAAXK@Z; FontSubsettingTelemetry::CreateFontPackage::Stop(ulong)
0x180002c43  lea     rcx, [rbp+150h+var_1A0]; this
0x180002c47  call    ??1CreateFontPackage@FontSubsettingTelemetry@@QEAA@XZ; FontSubsettingTelemetry::CreateFontPackage::~CreateFontPackage(void)
0x180002c4c  mov     eax, ebx
0x180002c4e  mov     rcx, [rbp+150h+var_50]
0x180002c55  xor     rcx, rsp; StackCookie
0x180002c58  call    __security_check_cookie
0x180002c5d  add     rsp, 218h
0x180002c64  pop     r15
0x180002c66  pop     r14
0x180002c68  pop     r13
0x180002c6a  pop     r12
0x180002c6c  pop     rdi
0x180002c6d  pop     rsi
0x180002c6e  pop     rbx
0x180002c6f  pop     rbp
0x180002c70  retn
```
