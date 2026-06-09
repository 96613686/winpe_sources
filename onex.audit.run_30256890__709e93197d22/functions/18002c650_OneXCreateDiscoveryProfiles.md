# OneXCreateDiscoveryProfiles

- ea: `0x18002c650`
- end: `0x18002c8c4`
- name: `OneXCreateDiscoveryProfiles`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x18002aa58`
- `0x18002c650`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x18002c83c`
- `MobileNetworking!FreeMemory` at `0x18002c85a`
- `MobileNetworking!FreeMemory` at `0x18002c874`
- `MobileNetworking!FreeMemory` at `0x18002c83c`
- `MobileNetworking!FreeMemory` at `0x18002c85a`
- `MobileNetworking!FreeMemory` at `0x18002c874`

## string_xrefs

- `0x18002c828`: `OneXCreateDiscoveryProfiles`

## pseudocode

```c
__int64 __fastcall OneXCreateDiscoveryProfiles(int a1, signed int a2, int a3, _DWORD *a4, _QWORD *a5, _QWORD *a6)
{
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rdi
  _QWORD *v14; // rsi
  unsigned int v15; // eax
  __int64 i; // rbx
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v20; // [rsp+70h] [rbp+30h] BYREF

  v20 = 0;
  v18 = 0;
  v19 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 201, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v10[7], 202, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( a1 != 1 )
  {
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 68) & 1) == 0 )
      goto LABEL_27;
    v11 = 203;
    v12 = 50;
    goto LABEL_11;
  }
  if ( a2 >= 2 )
  {
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 68) & 1) == 0 )
      goto LABEL_27;
    v11 = 204;
    v12 = 87;
LABEL_11:
    WPP_SF_d(v10[7], v11, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
    goto LABEL_27;
  }
  v13 = a6;
  if ( a6 && (v14 = a5) != 0 && a4 )
  {
    *a4 = 0;
    *v14 = 0;
    *v13 = 0;
    v15 = ProfileMgrCreateDiscoveryProfiles(a2, a3, &v20, &v19, &v18);
    if ( !v15 )
    {
      *a4 = v20;
      *v14 = v19;
      *v13 = v18;
      goto LABEL_30;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 206, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v15);
  }
  else if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
  {
    WPP_SF_(v10[7], 205, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
  }
LABEL_27:
  FreeMemory(&v19, "OneXCreateDiscoveryProfiles", 2150);
  for ( i = 0; (unsigned int)i < v20; i = (unsigned int)(i + 1) )
    FreeMemory(v18 + 8 * i, "OneXCreateDiscoveryProfiles", 2153);
  FreeMemory(&v18, "OneXCreateDiscoveryProfiles", 2155);
LABEL_30:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 207, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18002c650  mov     [rsp-28h+arg_8], rbx
0x18002c655  mov     [rsp-28h+arg_10], rsi
0x18002c65a  push    rbp
0x18002c65b  push    rdi
0x18002c65c  push    r12
0x18002c65e  push    r14
0x18002c660  push    r15
0x18002c662  mov     rbp, rsp
0x18002c665  sub     rsp, 40h
0x18002c669  mov     r14, r9
0x18002c66c  mov     [rbp+arg_0], 0
0x18002c673  mov     r12d, r8d
0x18002c676  mov     [rbp+var_10], 0
0x18002c67e  mov     r15d, edx
0x18002c681  mov     [rbp+var_8], 0
0x18002c689  mov     ebx, ecx
0x18002c68b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c692  lea     rax, WPP_GLOBAL_Control
0x18002c699  cmp     rcx, rax
0x18002c69c  jz      short loc_18002C6FB
0x18002c69e  test    dword ptr [rcx+44h], 800h
0x18002c6a5  jz      short loc_18002C6CA
0x18002c6a7  mov     rcx, [rcx+38h]
0x18002c6ab  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c6b2  mov     edx, 0C9h
0x18002c6b7  call    WPP_SF_
0x18002c6bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6c3  lea     rax, WPP_GLOBAL_Control
0x18002c6ca  cmp     rcx, rax
0x18002c6cd  jz      short loc_18002C6FB
0x18002c6cf  test    dword ptr [rcx+44h], 100h
0x18002c6d6  jz      short loc_18002C6FB
0x18002c6d8  mov     rcx, [rcx+38h]
0x18002c6dc  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c6e3  mov     edx, 0CAh
0x18002c6e8  call    WPP_SF_
0x18002c6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6f4  lea     rax, WPP_GLOBAL_Control
0x18002c6fb  cmp     ebx, 1
0x18002c6fe  jz      short loc_18002C733
0x18002c700  cmp     rcx, rax
0x18002c703  jz      loc_18002C821
0x18002c709  test    byte ptr [rcx+44h], 1
0x18002c70d  jz      loc_18002C821
0x18002c713  mov     edx, 0CBh
0x18002c718  mov     r9d, 32h ; '2'
0x18002c71e  mov     rcx, [rcx+38h]
0x18002c722  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c729  call    WPP_SF_d
0x18002c72e  jmp     loc_18002C821
0x18002c733  cmp     r15d, 2
0x18002c737  jl      short loc_18002C757
0x18002c739  cmp     rcx, rax
0x18002c73c  jz      loc_18002C821
0x18002c742  test    byte ptr [rcx+44h], 1
0x18002c746  jz      loc_18002C821
0x18002c74c  mov     edx, 0CCh
0x18002c751  lea     r9d, [rdx-75h]
0x18002c755  jmp     short loc_18002C71E
0x18002c757  mov     rdi, [rbp+arg_28]
0x18002c75b  test    rdi, rdi
0x18002c75e  jz      loc_18002C801
0x18002c764  mov     rsi, [rbp+arg_20]
0x18002c768  test    rsi, rsi
0x18002c76b  jz      loc_18002C801
0x18002c771  test    r14, r14
0x18002c774  jz      loc_18002C801
0x18002c77a  mov     dword ptr [r14], 0
0x18002c781  lea     rax, [rbp+var_10]
0x18002c785  mov     qword ptr [rsi], 0
0x18002c78c  lea     r9, [rbp+var_8]
0x18002c790  lea     r8, [rbp+arg_0]
0x18002c794  mov     qword ptr [rdi], 0
0x18002c79b  mov     edx, r12d
0x18002c79e  mov     [rsp+40h+var_20], rax
0x18002c7a3  mov     ecx, r15d
0x18002c7a6  call    ProfileMgrCreateDiscoveryProfiles
0x18002c7ab  mov     ebx, eax
0x18002c7ad  test    eax, eax
0x18002c7af  jz      short loc_18002C7E4
0x18002c7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7b8  lea     rdi, WPP_GLOBAL_Control
0x18002c7bf  cmp     rcx, rdi
0x18002c7c2  jz      short loc_18002C828
0x18002c7c4  test    byte ptr [rcx+44h], 1
0x18002c7c8  jz      short loc_18002C828
0x18002c7ca  mov     rcx, [rcx+38h]
0x18002c7ce  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c7d5  mov     edx, 0CEh
0x18002c7da  mov     r9d, eax
0x18002c7dd  call    WPP_SF_d
0x18002c7e2  jmp     short loc_18002C828
0x18002c7e4  mov     eax, [rbp+arg_0]
0x18002c7e7  mov     [r14], eax
0x18002c7ea  mov     rax, [rbp+var_8]
0x18002c7ee  mov     [rsi], rax
0x18002c7f1  mov     rax, [rbp+var_10]
0x18002c7f5  mov     [rdi], rax
0x18002c7f8  lea     rdi, WPP_GLOBAL_Control
0x18002c7ff  jmp     short loc_18002C87C
0x18002c801  cmp     rcx, rax
0x18002c804  jz      short loc_18002C821
0x18002c806  test    byte ptr [rcx+44h], 1
0x18002c80a  jz      short loc_18002C821
0x18002c80c  mov     rcx, [rcx+38h]
0x18002c810  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c817  mov     edx, 0CDh
0x18002c81c  call    WPP_SF_
0x18002c821  lea     rdi, WPP_GLOBAL_Control
0x18002c828  lea     rsi, aOnexcreatedisc_0; "OneXCreateDiscoveryProfiles"
0x18002c82f  mov     r8d, 866h
0x18002c835  mov     rdx, rsi
0x18002c838  lea     rcx, [rbp+var_8]
0x18002c83c  call    cs:__imp_FreeMemory
0x18002c842  xor     ebx, ebx
0x18002c844  cmp     [rbp+arg_0], ebx
0x18002c847  jbe     short loc_18002C867
0x18002c849  mov     rax, [rbp+var_10]
0x18002c84d  mov     r8d, 869h
0x18002c853  mov     rdx, rsi
0x18002c856  lea     rcx, [rax+rbx*8]
0x18002c85a  call    cs:__imp_FreeMemory
0x18002c860  inc     ebx
0x18002c862  cmp     ebx, [rbp+arg_0]
0x18002c865  jb      short loc_18002C849
0x18002c867  mov     r8d, 86Bh
0x18002c86d  lea     rcx, [rbp+var_10]
0x18002c871  mov     rdx, rsi
0x18002c874  call    cs:__imp_FreeMemory
0x18002c87a  xor     ebx, ebx
0x18002c87c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c883  cmp     rcx, rdi
0x18002c886  jz      short loc_18002C8A9
0x18002c888  test    dword ptr [rcx+44h], 800h
0x18002c88f  jz      short loc_18002C8A9
0x18002c891  mov     rcx, [rcx+38h]
0x18002c895  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c89c  mov     edx, 0CFh
0x18002c8a1  mov     r9d, ebx
0x18002c8a4  call    WPP_SF_D
0x18002c8a9  lea     r11, [rsp+40h+var_s0]
0x18002c8ae  mov     eax, ebx
0x18002c8b0  mov     rbx, [r11+38h]
0x18002c8b4  mov     rsi, [r11+40h]
0x18002c8b8  mov     rsp, r11
0x18002c8bb  pop     r15
0x18002c8bd  pop     r14
0x18002c8bf  pop     r12
0x18002c8c1  pop     rdi
0x18002c8c2  pop     rbp
0x18002c8c3  retn
```
