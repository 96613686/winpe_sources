# MRxSmbQuerySecurityInformation

- ea: `0x140029170`
- end: `0x14002942c`
- name: `MRxSmbQuerySecurityInformation`
- size: `700`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000e01c`
- `0x1400169c0`
- `0x140029170`
- `0x1400381d0`

## import_xrefs

- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400293c0`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400293c0`

## pseudocode

```c
__int64 __fastcall MRxSmbQuerySecurityInformation(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  void *v4; // r15
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // r14d
  ULONG v11; // edx
  __int16 v12; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v13[22]; // [rsp+82h] [rbp-7Eh]
  ULONG v14[28]; // [rsp+A0h] [rbp-60h] BYREF
  int v15; // [rsp+140h] [rbp+40h] BYREF
  __int64 v16; // [rsp+148h] [rbp+48h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 64);
  v4 = *(void **)(a1 + 456);
  v16 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_025766dafd213e249d026318cd94f89a_Traceguids);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 120) + 32LL) + 32LL) + 420LL) & 0x40000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_025766dafd213e249d026318cd94f89a_Traceguids);
    }
    return 3221225659LL;
  }
  v6 = MRxSmbDeferredCreate(a1);
  if ( !v6 )
  {
    v7 = *(_QWORD *)(v3 + 32);
    if ( v7 )
      v8 = *(_QWORD *)(v7 + 48);
    else
      v8 = 0;
    *(_OWORD *)v13 = *(__int128 *)((char *)&RxDefaultTransactionOptions + 2);
    *(_QWORD *)&v13[14] = qword_14001F6B0;
    memset(v14, 0, 0x68u);
    v12 = 6;
    LODWORD(v16) = *(unsigned __int16 *)(v8 + 8);
    v15 = -1163019603;
    HIDWORD(v16) = *(_DWORD *)(a1 + 512);
    v6 = SmbCeTransact(
           a1,
           (int)&v12,
           0,
           0,
           0,
           0,
           (__int64)&v16,
           8,
           (__int64)&v15,
           4,
           0,
           0,
           (__int64)v4,
           *(_DWORD *)(a1 + 472),
           (__int64)v14);
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741789 )
    {
      if ( v6 == -2147483643 )
        v6 = -1073741629;
      goto LABEL_30;
    }
    v9 = v15;
    v10 = v15;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_025766dafd213e249d026318cd94f89a_Traceguids, v14[15], v6);
      v9 = v15;
    }
    if ( v9 <= *(_DWORD *)(a1 + 472) )
    {
      if ( v6 != -1073741789 )
        goto LABEL_25;
    }
    else if ( v9 >= 0x14 )
    {
      v6 = -2147483643;
      goto LABEL_25;
    }
    v10 = 0;
    v6 = -1073741629;
LABEL_25:
    *(_QWORD *)(a1 + 184) = v10;
    if ( v6 >= 0 )
    {
      v11 = *(_DWORD *)(a1 + 472);
      if ( v14[15] < v11 )
        v11 = v14[15];
      if ( !RtlValidRelativeSecurityDescriptor(v4, v11, 0) )
        v6 = -1073741629;
    }
  }
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_025766dafd213e249d026318cd94f89a_Traceguids,
      (unsigned int)v6,
      *(_DWORD *)(a1 + 184));
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140029170  mov     [rsp-8+arg_10], rbx
0x140029175  mov     [rsp-8+arg_18], rsi
0x14002917a  push    rbp
0x14002917b  push    rdi
0x14002917c  push    r13
0x14002917e  push    r14
0x140029180  push    r15
0x140029182  lea     rbp, [rsp-10h]
0x140029187  sub     rsp, 110h
0x14002918e  mov     rbx, [rcx+38h]
0x140029192  mov     rdi, rcx
0x140029195  mov     rsi, [rcx+40h]
0x140029199  mov     r15, [rcx+1C8h]
0x1400291a0  mov     [rbp+30h+arg_8], 0
0x1400291a8  mov     [rbp+30h+arg_0], 0
0x1400291af  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400291b6  lea     rdx, WPP_GLOBAL_Control
0x1400291bd  cmp     rcx, rdx
0x1400291c0  jz      short loc_1400291E5
0x1400291c2  bt      dword ptr [rcx+2Ch], 0Ah
0x1400291c7  jnb     short loc_1400291E5
0x1400291c9  mov     rcx, [rcx+18h]
0x1400291cd  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x1400291d4  mov     edx, 12h
0x1400291d9  call    WPP_SF_
0x1400291de  lea     rdx, WPP_GLOBAL_Control
0x1400291e5  mov     rax, [rbx+78h]
0x1400291e9  mov     rcx, [rax+20h]
0x1400291ed  mov     rax, [rcx+20h]
0x1400291f1  test    dword ptr [rax+1A4h], 40000h
0x1400291fb  jnz     short loc_14002922F
0x1400291fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029204  cmp     rcx, rdx
0x140029207  jz      short loc_140029225
0x140029209  bt      dword ptr [rcx+2Ch], 0Ah
0x14002920e  jnb     short loc_140029225
0x140029210  mov     rcx, [rcx+18h]
0x140029214  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x14002921b  mov     edx, 13h
0x140029220  call    WPP_SF_
0x140029225  mov     eax, 0C00000BBh
0x14002922a  jmp     loc_14002940F
0x14002922f  mov     rcx, rdi
0x140029232  call    MRxSmbDeferredCreate
0x140029237  mov     ebx, eax
0x140029239  test    eax, eax
0x14002923b  jnz     loc_1400293D1
0x140029241  mov     rax, [rsi+20h]
0x140029245  test    rax, rax
0x140029248  jnz     short loc_14002924E
0x14002924a  xor     ebx, ebx
0x14002924c  jmp     short loc_140029252
0x14002924e  mov     rbx, [rax+30h]
0x140029252  movups  xmm0, cs:RxDefaultTransactionOptions+2
0x140029259  lea     rcx, [rbp+30h+var_90]; void *
0x14002925d  xor     edx, edx; Val
0x14002925f  movsd   xmm1, cs:qword_14001F6B0
0x140029267  movups  xmmword ptr [rbp+30h+var_AE], xmm0
0x14002926b  lea     r8d, [rdx+68h]; Size
0x14002926f  movsd   qword ptr [rbp+30h+var_AE+0Eh], xmm1
0x140029274  call    memset
0x140029279  mov     eax, 6
0x14002927e  lea     rdx, [rbp+30h+var_B0]
0x140029282  mov     [rbp+30h+var_B0], ax
0x140029286  xor     r9d, r9d
0x140029289  movzx   eax, word ptr [rbx+8]
0x14002928d  xor     r8d, r8d
0x140029290  mov     word ptr [rbp+30h+arg_8], ax
0x140029294  mov     rcx, rdi
0x140029297  xor     eax, eax
0x140029299  mov     [rbp+30h+arg_0], 0BAADBAADh
0x1400292a0  mov     word ptr [rbp+30h+arg_8+2], ax
0x1400292a4  mov     eax, [rdi+200h]
0x1400292aa  mov     dword ptr [rbp+30h+arg_8+4], eax
0x1400292ad  lea     rax, [rbp+30h+var_90]
0x1400292b1  mov     [rsp+130h+var_C0], rax
0x1400292b6  mov     eax, [rdi+1D8h]
0x1400292bc  mov     [rsp+130h+var_C8], eax
0x1400292c0  lea     rax, [rbp+30h+arg_0]
0x1400292c4  mov     [rsp+130h+var_D0], r15
0x1400292c9  mov     [rsp+130h+var_D8], 0
0x1400292d1  mov     [rsp+130h+var_E0], 0
0x1400292da  mov     [rsp+130h+var_E8], 4
0x1400292e2  mov     [rsp+130h+var_F0], rax
0x1400292e7  lea     rax, [rbp+30h+arg_8]
0x1400292eb  mov     [rsp+130h+var_F8], 8
0x1400292f3  mov     [rsp+130h+var_100], rax
0x1400292f8  mov     [rsp+130h+var_108], 0
0x140029300  mov     [rsp+130h+var_110], 0
0x140029309  call    SmbCeTransact
0x14002930e  mov     ecx, 80000000h
0x140029313  mov     ebx, eax
0x140029315  add     eax, ecx
0x140029317  test    ecx, eax
0x140029319  jnz     short loc_140029339
0x14002931b  cmp     ebx, 0C0000023h
0x140029321  jz      short loc_140029339
0x140029323  cmp     ebx, 80000005h
0x140029329  jnz     loc_1400293D1
0x14002932f  mov     ebx, 0C00000C3h
0x140029334  jmp     loc_1400293D1
0x140029339  mov     eax, [rbp+30h+arg_0]
0x14002933c  mov     r14d, eax
0x14002933f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029346  lea     rdx, WPP_GLOBAL_Control
0x14002934d  cmp     rcx, rdx
0x140029350  jz      short loc_140029379
0x140029352  bt      dword ptr [rcx+2Ch], 0Ah
0x140029357  jnb     short loc_140029379
0x140029359  mov     r9d, [rbp+30h+SecurityDescriptorLength]
0x14002935d  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x140029364  mov     rcx, [rcx+18h]
0x140029368  mov     edx, 14h
0x14002936d  mov     dword ptr [rsp+130h+var_110], ebx
0x140029371  call    WPP_SF_Dd
0x140029376  mov     eax, [rbp+30h+arg_0]
0x140029379  mov     esi, 0C00000C3h
0x14002937e  cmp     eax, [rdi+1D8h]
0x140029384  jbe     short loc_140029392
0x140029386  cmp     eax, 14h
0x140029389  jb      short loc_14002939A
0x14002938b  mov     ebx, 80000005h
0x140029390  jmp     short loc_14002939F
0x140029392  cmp     ebx, 0C0000023h
0x140029398  jnz     short loc_14002939F
0x14002939a  xor     r14d, r14d
0x14002939d  mov     ebx, esi
0x14002939f  mov     eax, r14d
0x1400293a2  mov     [rdi+0B8h], rax
0x1400293a9  test    ebx, ebx
0x1400293ab  js      short loc_1400293D1
0x1400293ad  mov     edx, [rdi+1D8h]
0x1400293b3  mov     rcx, r15; SecurityDescriptorInput
0x1400293b6  cmp     [rbp+30h+SecurityDescriptorLength], edx
0x1400293b9  cmovb   edx, [rbp+30h+SecurityDescriptorLength]; SecurityDescriptorLength
0x1400293bd  xor     r8d, r8d; RequiredInformation
0x1400293c0  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400293c7  nop     dword ptr [rax+rax+00h]
0x1400293cc  test    al, al
0x1400293ce  cmovz   ebx, esi
0x1400293d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400293d8  lea     rax, WPP_GLOBAL_Control
0x1400293df  cmp     rcx, rax
0x1400293e2  jz      short loc_14002940D
0x1400293e4  bt      dword ptr [rcx+2Ch], 0Ah
0x1400293e9  jnb     short loc_14002940D
0x1400293eb  mov     eax, [rdi+0B8h]
0x1400293f1  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x1400293f8  mov     rcx, [rcx+18h]
0x1400293fc  mov     edx, 15h
0x140029401  mov     r9d, ebx
0x140029404  mov     dword ptr [rsp+130h+var_110], eax
0x140029408  call    WPP_SF_Dd
0x14002940d  mov     eax, ebx
0x14002940f  lea     r11, [rsp+130h+var_20]
0x140029417  mov     rbx, [r11+40h]
0x14002941b  mov     rsi, [r11+48h]
0x14002941f  mov     rsp, r11
0x140029422  pop     r15
0x140029424  pop     r14
0x140029426  pop     r13
0x140029428  pop     rdi
0x140029429  pop     rbp
0x14002942a  retn
```
