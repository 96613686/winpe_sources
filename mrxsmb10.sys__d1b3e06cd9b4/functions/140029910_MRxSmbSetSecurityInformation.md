# MRxSmbSetSecurityInformation

- ea: `0x140029910`
- end: `0x140029b17`
- name: `MRxSmbSetSecurityInformation`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x1400169c0`
- `0x140029910`
- `0x1400381d0`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140029a02`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140029a02`

## pseudocode

```c
__int64 __fastcall MRxSmbSetSecurityInformation(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  unsigned int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rdi
  ULONG v8; // eax
  __int128 v9; // [rsp+80h] [rbp-80h] BYREF
  __int64 v10; // [rsp+90h] [rbp-70h]
  _DWORD v11[40]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v12; // [rsp+150h] [rbp+50h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 64);
  v12 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_025766dafd213e249d026318cd94f89a_Traceguids);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 120) + 32LL) + 32LL) + 420LL) & 0x40000) != 0 )
  {
    v5 = MRxSmbDeferredCreate(a1);
    if ( !v5 )
    {
      v6 = *(_QWORD *)(v3 + 32);
      v7 = v6 ? *(_QWORD *)(v6 + 48) : 0LL;
      v9 = RxDefaultTransactionOptions;
      v10 = qword_14001F6B0;
      memset(v11, 0, 0x68u);
      v8 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 520));
      LOWORD(v9) = 3;
      LODWORD(v12) = *(unsigned __int16 *)(v7 + 8);
      HIDWORD(v12) = *(_DWORD *)(a1 + 512);
      v5 = SmbCeTransact(
             a1,
             (int)&v9,
             0,
             0,
             0,
             0,
             (__int64)&v12,
             8,
             0,
             0,
             *(_QWORD *)(a1 + 520),
             v8,
             0,
             0,
             (__int64)v11);
      if ( (v5 & 0x80000000) == 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return v5;
        if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_025766dafd213e249d026318cd94f89a_Traceguids, v11[15]);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_025766dafd213e249d026318cd94f89a_Traceguids,
        v5,
        *(_DWORD *)(a1 + 184));
    }
    return v5;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_025766dafd213e249d026318cd94f89a_Traceguids);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x140029910  push    rbp
0x140029912  push    rbx
0x140029913  push    rsi
0x140029914  push    rdi
0x140029915  push    r12
0x140029917  push    r15
0x140029919  lea     rbp, [rsp-18h]
0x14002991e  sub     rsp, 118h
0x140029925  mov     rdi, [rcx+38h]
0x140029929  mov     rbx, rcx
0x14002992c  mov     rsi, [rcx+40h]
0x140029930  mov     [rbp+40h+arg_0], 0
0x140029938  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002993f  lea     r12, WPP_GLOBAL_Control
0x140029946  cmp     rcx, r12
0x140029949  jz      short loc_140029967
0x14002994b  bt      dword ptr [rcx+2Ch], 0Ah
0x140029950  jnb     short loc_140029967
0x140029952  mov     rcx, [rcx+18h]
0x140029956  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x14002995d  mov     edx, 16h
0x140029962  call    WPP_SF_
0x140029967  mov     rax, [rdi+78h]
0x14002996b  mov     rcx, [rax+20h]
0x14002996f  mov     rax, [rcx+20h]
0x140029973  test    dword ptr [rax+1A4h], 40000h
0x14002997d  jnz     short loc_1400299B1
0x14002997f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029986  cmp     rcx, r12
0x140029989  jz      short loc_1400299A7
0x14002998b  bt      dword ptr [rcx+2Ch], 0Ah
0x140029990  jnb     short loc_1400299A7
0x140029992  mov     rcx, [rcx+18h]
0x140029996  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x14002999d  mov     edx, 17h
0x1400299a2  call    WPP_SF_
0x1400299a7  mov     eax, 0C00000BBh
0x1400299ac  jmp     loc_140029B06
0x1400299b1  mov     rcx, rbx
0x1400299b4  call    MRxSmbDeferredCreate
0x1400299b9  mov     edi, eax
0x1400299bb  test    eax, eax
0x1400299bd  jnz     loc_140029ACF
0x1400299c3  mov     rax, [rsi+20h]
0x1400299c7  test    rax, rax
0x1400299ca  jnz     short loc_1400299D0
0x1400299cc  xor     edi, edi
0x1400299ce  jmp     short loc_1400299D4
0x1400299d0  mov     rdi, [rax+30h]
0x1400299d4  movups  xmm0, cs:RxDefaultTransactionOptions
0x1400299db  lea     rcx, [rbp+40h+var_A0]; void *
0x1400299df  xor     edx, edx; Val
0x1400299e1  movsd   xmm1, cs:qword_14001F6B0
0x1400299e9  movups  [rbp+40h+var_C0], xmm0
0x1400299ed  lea     r8d, [rdx+68h]; Size
0x1400299f1  movsd   [rbp+40h+var_B0], xmm1
0x1400299f6  call    memset
0x1400299fb  mov     rcx, [rbx+208h]; SecurityDescriptor
0x140029a02  call    cs:__imp_RtlLengthSecurityDescriptor
0x140029a09  nop     dword ptr [rax+rax+00h]
0x140029a0e  mov     ecx, 3
0x140029a13  lea     rdx, [rbp+40h+var_C0]
0x140029a17  mov     word ptr [rbp+40h+var_C0], cx
0x140029a1b  xor     r9d, r9d
0x140029a1e  movzx   ecx, word ptr [rdi+8]
0x140029a22  xor     r8d, r8d
0x140029a25  mov     word ptr [rbp+40h+arg_0], cx
0x140029a29  xor     ecx, ecx
0x140029a2b  mov     word ptr [rbp+40h+arg_0+2], cx
0x140029a2f  mov     ecx, [rbx+200h]
0x140029a35  mov     dword ptr [rbp+40h+arg_0+4], ecx
0x140029a38  lea     rcx, [rbp+40h+var_A0]
0x140029a3c  mov     [rsp+140h+var_D0], rcx
0x140029a41  mov     rcx, rbx
0x140029a44  mov     [rsp+140h+var_D8], 0
0x140029a4c  mov     [rsp+140h+var_E0], 0
0x140029a55  mov     [rsp+140h+var_E8], eax
0x140029a59  mov     rax, [rbx+208h]
0x140029a60  mov     [rsp+140h+var_F0], rax
0x140029a65  lea     rax, [rbp+40h+arg_0]
0x140029a69  mov     [rsp+140h+var_F8], 0
0x140029a71  mov     [rsp+140h+var_100], 0
0x140029a7a  mov     [rsp+140h+var_108], 8
0x140029a82  mov     [rsp+140h+var_110], rax
0x140029a87  mov     [rsp+140h+var_118], 0
0x140029a8f  mov     [rsp+140h+var_120], 0
0x140029a98  call    SmbCeTransact
0x140029a9d  mov     edi, eax
0x140029a9f  test    eax, eax
0x140029aa1  js      short loc_140029ACF
0x140029aa3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029aaa  cmp     rcx, r12
0x140029aad  jz      short loc_140029B04
0x140029aaf  bt      dword ptr [rcx+2Ch], 0Ah
0x140029ab4  jnb     short loc_140029ACF
0x140029ab6  mov     r9d, [rbp+40h+var_64]
0x140029aba  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x140029ac1  mov     rcx, [rcx+18h]
0x140029ac5  mov     edx, 18h
0x140029aca  call    WPP_SF_d
0x140029acf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029ad6  cmp     rcx, r12
0x140029ad9  jz      short loc_140029B04
0x140029adb  bt      dword ptr [rcx+2Ch], 0Ah
0x140029ae0  jnb     short loc_140029B04
0x140029ae2  mov     eax, [rbx+0B8h]
0x140029ae8  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x140029aef  mov     rcx, [rcx+18h]
0x140029af3  mov     edx, 19h
0x140029af8  mov     r9d, edi
0x140029afb  mov     dword ptr [rsp+140h+var_120], eax
0x140029aff  call    WPP_SF_Dd
0x140029b04  mov     eax, edi
0x140029b06  add     rsp, 118h
0x140029b0d  pop     r15
0x140029b0f  pop     r12
0x140029b11  pop     rdi
0x140029b12  pop     rsi
0x140029b13  pop     rbx
0x140029b14  pop     rbp
0x140029b15  retn
```
