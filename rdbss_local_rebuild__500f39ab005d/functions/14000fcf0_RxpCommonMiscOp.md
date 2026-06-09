# RxpCommonMiscOp

- ea: `0x14000fcf0`
- end: `0x14000ff8f`
- name: `RxpCommonMiscOp`
- size: `671`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `6`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018b80`
- `0x140018e90`
- `0x140044830`
- `0x140044960`
- `0x140073d00`
- `0x140074f80`

## callees

- `0x140007ca0`
- `0x140009b80`
- `0x14000fcf0`
- `0x140016d40`
- `0x140016e20`
- `0x140017280`
- `0x14001e3b0`
- `0x140025d00`
- `0x140057660`
- `0x140065690`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000fdc5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fdc5`

## string_xrefs

- `0x140026a22`: `RxpCommonMiscOp`

## pseudocode

```c
__int64 __fastcall RxpCommonMiscOp(
        PRX_CONTEXT RxContext,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall *a4)(PRX_CONTEXT, __int64, __int64))
{
  unsigned int v8; // eax
  unsigned int v9; // esi
  unsigned int v10; // r15d
  int v11; // esi
  unsigned int v13; // eax
  unsigned int v14; // ebx
  const CHAR *v15; // [rsp+20h] [rbp-38h]
  ULONG v16; // [rsp+28h] [rbp-30h]

  if ( (unsigned __int16)(*(_WORD *)a3 + 5087) > 1u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids, 3221225485LL);
    }
    return 3221225485LL;
  }
  else if ( ((__int64)RxContext->RdbssDbgExtension & 2) != 0 )
  {
    v8 = _RxAcquireFcb((PFCB)a3, RxContext, 2u, 0, v15, v16);
    v9 = v8;
    if ( !v8 )
    {
      v10 = a4(RxContext, a2, a3);
      v11 = *(_BYTE *)(*(_QWORD *)(a3 + 8) + 26LL) & 0x80;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
          (unsigned __int8)v11);
      }
      if ( (_BYTE)v11 )
      {
        if ( (unsigned __int64)RxContext > 0xFFFFFFFFFFFFFFFDuLL )
        {
LABEL_9:
          ExReleaseResourceLite(*(PERESOURCE *)(a3 + 8));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids, v10);
          }
          return v10;
        }
        if ( *(_DWORD *)(*(_QWORD *)(a3 + 304) + 296LL)
          && (*(_DWORD *)(a3 + 156) & 0x80000) == 0
          && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(RxContext, a3) )
        {
          RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a3);
        }
      }
      if ( (unsigned __int64)RxContext <= 0xFFFFFFFFFFFFFFFDuLL )
        LOBYTE(RxContext->Flags) = 0;
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids, v8);
    }
    return v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids);
    }
    v13 = RxFsdPostRequest(RxContext);
    v14 = v13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids, v13);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x14000fcf0  mov     [rsp+arg_8], rbx
0x14000fcf5  mov     [rsp+arg_10], r8
0x14000fcfa  mov     [rsp+arg_0], rcx
0x14000fcff  push    rsi
0x14000fd00  push    rdi
0x14000fd01  push    r12
0x14000fd03  push    r14
0x14000fd05  push    r15
0x14000fd07  sub     rsp, 30h
0x14000fd0b  mov     r14, r9
0x14000fd0e  mov     rbx, r8
0x14000fd11  mov     r15, rdx
0x14000fd14  mov     rdi, rcx
0x14000fd17  mov     eax, 13DFh
0x14000fd1c  add     ax, [r8]
0x14000fd20  cmp     ax, 1
0x14000fd24  ja      loc_14000FE71
0x14000fd2a  mov     eax, [rcx+78h]
0x14000fd2d  test    al, 2
0x14000fd2f  jz      loc_14000FEC6
0x14000fd35  xor     r9d, r9d; LineNumber
0x14000fd38  mov     r8d, 2; Mode
0x14000fd3e  mov     rdx, rcx; RxContext
0x14000fd41  mov     rcx, rbx; Fcb
0x14000fd44  call    __RxAcquireFcb
0x14000fd49  mov     esi, eax
0x14000fd4b  mov     dword ptr [rsp+58h+var_38], eax
0x14000fd4f  test    eax, eax
0x14000fd51  jnz     loc_14000FE3D
0x14000fd57  mov     r8, rbx
0x14000fd5a  mov     rdx, r15
0x14000fd5d  mov     rcx, rdi
0x14000fd60  mov     rax, r14
0x14000fd63  call    _guard_dispatch_icall
0x14000fd68  mov     r15d, eax
0x14000fd6b  mov     dword ptr [rsp+58h+var_38], eax
0x14000fd6f  mov     rcx, [rbx+8]
0x14000fd73  movzx   edx, byte ptr [rcx+1Ah]
0x14000fd77  cmp     rdi, 0FFFFFFFFFFFFFFFDh
0x14000fd7b  jbe     loc_14000FE69
0x14000fd81  mov     r12b, 1
0x14000fd84  mov     rax, [rbx+8]
0x14000fd88  movzx   esi, byte ptr [rax+1Ah]
0x14000fd8c  and     sil, 80h
0x14000fd90  lea     r14, WPP_GLOBAL_Control
0x14000fd97  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd9e  cmp     rcx, r14
0x14000fda1  jz      short loc_14000FDB0
0x14000fda3  test    dword ptr [rcx+2Ch], 100h
0x14000fdaa  jnz     loc_14000FF40
0x14000fdb0  test    sil, sil
0x14000fdb3  jnz     short loc_14000FDFE
0x14000fdb5  test    r12b, r12b
0x14000fdb8  jnz     short loc_14000FDC1
0x14000fdba  mov     [rdi+0A8h], r12b
0x14000fdc1  mov     rcx, [rbx+8]; Resource
0x14000fdc5  call    cs:__imp_ExReleaseResourceLite
0x14000fdcc  nop     dword ptr [rax+rax+00h]
0x14000fdd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fdd8  cmp     rcx, r14
0x14000fddb  jz      short loc_14000FDE8
0x14000fddd  mov     eax, [rcx+2Ch]
0x14000fde0  test    al, 2
0x14000fde2  jnz     loc_14000FF68
0x14000fde8  mov     eax, r15d
0x14000fdeb  mov     rbx, [rsp+58h+arg_8]
0x14000fdf0  add     rsp, 30h
0x14000fdf4  pop     r15
0x14000fdf6  pop     r14
0x14000fdf8  pop     r12
0x14000fdfa  pop     rdi
0x14000fdfb  pop     rsi
0x14000fdfc  retn
0x14000fdfe  test    r12b, r12b
0x14000fe01  jnz     short loc_14000FDC1
0x14000fe03  mov     rax, [rbx+130h]
0x14000fe0a  cmp     dword ptr [rax+128h], 0
0x14000fe11  jz      short loc_14000FDB5
0x14000fe13  test    dword ptr [rbx+9Ch], 80000h
0x14000fe1d  jnz     short loc_14000FDB5
0x14000fe1f  mov     rdx, rbx
0x14000fe22  mov     rcx, rdi
0x14000fe25  call    RxIsSafeToProcessBufferingStateChange
0x14000fe2a  test    al, al
0x14000fe2c  jz      short loc_14000FDB5
0x14000fe2e  xor     edx, edx
0x14000fe30  mov     rcx, rbx; Instance
0x14000fe33  call    RxProcessFcbChangeBufferingStateRequestInternal
0x14000fe38  jmp     loc_14000FDB5
0x14000fe3d  lea     r14, WPP_GLOBAL_Control
0x14000fe44  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe4b  cmp     rcx, r14
0x14000fe4e  jnz     loc_14000FF0D
0x14000fe54  mov     eax, esi
0x14000fe56  mov     rbx, [rsp+58h+arg_8]
0x14000fe5b  add     rsp, 30h
0x14000fe5f  pop     r15
0x14000fe61  pop     r14
0x14000fe63  pop     r12
0x14000fe65  pop     rdi
0x14000fe66  pop     rsi
0x14000fe67  retn
0x14000fe69  xor     r12b, r12b
0x14000fe6c  jmp     loc_14000FD84
0x14000fe71  lea     r14, WPP_GLOBAL_Control
0x14000fe78  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe7f  cmp     rcx, r14
0x14000fe82  jnz     short loc_14000FE9C
0x14000fe84  mov     eax, 0C000000Dh
0x14000fe89  mov     rbx, [rsp+58h+arg_8]
0x14000fe8e  add     rsp, 30h
0x14000fe92  pop     r15
0x14000fe94  pop     r14
0x14000fe96  pop     r12
0x14000fe98  pop     rdi
0x14000fe99  pop     rsi
0x14000fe9a  retn
0x14000fe9c  mov     eax, [rcx+2Ch]
0x14000fe9f  test    al, 2
0x14000fea1  jz      short loc_14000FE84
0x14000fea3  cmp     byte ptr [rcx+29h], 4
0x14000fea7  jb      short loc_14000FE84
0x14000fea9  mov     edx, 0Ah
0x14000feae  mov     r9d, 0C000000Dh
0x14000feb4  lea     r8, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids
0x14000febb  mov     rcx, [rcx+18h]
0x14000febf  call    WPP_SF_d
0x14000fec4  jmp     short loc_14000FE84
0x14000fec6  lea     r14, WPP_GLOBAL_Control
0x14000fecd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fed4  cmp     rcx, r14
0x14000fed7  jz      loc_140027A82
0x14000fedd  mov     eax, [rcx+2Ch]
0x14000fee0  test    al, 2
0x14000fee2  jz      loc_140027A82
0x14000fee8  cmp     byte ptr [rcx+29h], 4
0x14000feec  jb      loc_140027A82
0x14000fef2  mov     edx, 0Bh
0x14000fef7  lea     r8, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids
0x14000fefe  mov     rcx, [rcx+18h]
0x14000ff02  call    WPP_SF_
0x14000ff07  nop
0x14000ff08  jmp     loc_140027A82
0x14000ff0d  mov     edx, [rcx+2Ch]
0x14000ff10  test    dl, 2
0x14000ff13  jz      loc_14000FE54
0x14000ff19  cmp     byte ptr [rcx+29h], 4
0x14000ff1d  jb      loc_14000FE54
0x14000ff23  mov     edx, 0Dh
0x14000ff28  mov     r9d, esi
0x14000ff2b  lea     r8, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids
0x14000ff32  mov     rcx, [rcx+18h]
0x14000ff36  call    WPP_SF_d
0x14000ff3b  jmp     loc_14000FE54
0x14000ff40  cmp     byte ptr [rcx+29h], 4
0x14000ff44  jb      loc_14000FDB0
0x14000ff4a  movzx   r9d, sil
0x14000ff4e  mov     edx, 0Dh
0x14000ff53  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14000ff5a  mov     rcx, [rcx+18h]
0x14000ff5e  call    WPP_SF_d
0x14000ff63  jmp     loc_14000FDB0
0x14000ff68  cmp     byte ptr [rcx+29h], 4
0x14000ff6c  jb      loc_14000FDE8
0x14000ff72  mov     edx, 0Eh
0x14000ff77  mov     r9d, r15d
0x14000ff7a  lea     r8, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids
0x14000ff81  mov     rcx, [rcx+18h]
0x14000ff85  call    WPP_SF_d
0x14000ff8a  jmp     loc_14000FDE8
0x140026a10  push    rbp; SerialNumber
0x140026a12  sub     rsp, 20h
0x140026a16  mov     rbp, rdx
0x140026a19  test    cl, cl
0x140026a1b  jz      short loc_140026A2F
0x140026a1d  mov     edx, 74h ; 't'
0x140026a22  lea     rcx, aRxpcommonmisco; "RxpCommonMiscOp"
0x140026a29  call    RxLogAbnormalTermination
0x140026a2e  nop
0x140026a2f  mov     rdx, [rbp+70h]; MrxFcb
0x140026a33  mov     rcx, [rbp+60h]; RxContext
0x140026a37  call    __RxReleaseFcb
0x140026a3c  lea     rax, WPP_GLOBAL_Control
0x140026a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140026a4a  cmp     rcx, rax
0x140026a4d  jz      short loc_140026A76
0x140026a4f  mov     eax, [rcx+2Ch]
0x140026a52  test    al, 2
0x140026a54  jz      short loc_140026A76
0x140026a56  cmp     byte ptr [rcx+29h], 4
0x140026a5a  jb      short loc_140026A76
0x140026a5c  mov     edx, 0Eh
0x140026a61  mov     r9d, [rbp+20h]
0x140026a65  lea     r8, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids
0x140026a6c  mov     rcx, [rcx+18h]
0x140026a70  call    WPP_SF_d
0x140026a75  nop
0x140026a76  add     rsp, 20h
0x140026a7a  pop     rbp
0x140026a7b  retn
0x140027a82  mov     rcx, rdi; RxContext
0x140027a85  call    RxFsdPostRequest
0x140027a8a  mov     ebx, eax
0x140027a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a93  cmp     rcx, r14
0x140027a96  jz      short loc_140027ABE
0x140027a98  mov     edx, [rcx+2Ch]
0x140027a9b  test    dl, 2
0x140027a9e  jz      short loc_140027ABE
0x140027aa0  cmp     byte ptr [rcx+29h], 4
0x140027aa4  jb      short loc_140027ABE
0x140027aa6  mov     edx, 0Ch
0x140027aab  mov     r9d, eax
0x140027aae  lea     r8, WPP_29627f90a70a35ca85bb4242fcf2d251_Traceguids
0x140027ab5  mov     rcx, [rcx+18h]
0x140027ab9  call    WPP_SF_d
0x140027abe  mov     eax, ebx
0x140027ac0  jmp     loc_14000FDEB
```
