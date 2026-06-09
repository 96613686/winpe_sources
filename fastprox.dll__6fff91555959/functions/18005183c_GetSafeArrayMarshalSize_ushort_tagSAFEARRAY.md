# GetSafeArrayMarshalSize(ushort,tagSAFEARRAY *)

- ea: `0x18005183c`
- end: `0x1800519ac`
- name: `?GetSafeArrayMarshalSize@@YAKGPEAUtagSAFEARRAY@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int16, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800516a0`

## callees

- `0x180037120`
- `0x18005183c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMarshalSizeMax` at `0x180051955`
- `api-ms-win-core-com-l1-1-0!CoGetMarshalSizeMax` at `0x180051955`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800518a3`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800518a3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180051889`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180051889`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180051873`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180051873`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800518b6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800518b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800518d5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800519a1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800518d5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800519a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSafeArrayMarshalSize(__int16 a1, struct tagSAFEARRAY *a2)
{
  unsigned int v4; // ebx
  int v5; // esi
  UINT Elemsize; // edi
  int i; // ecx
  __int64 v9; // rax
  LPUNKNOWN *v10; // r15
  int j; // edi
  HRESULT MarshalSizeMax; // eax
  LONG plUbound; // [rsp+30h] [rbp-20h] BYREF
  LONG plLbound; // [rsp+34h] [rbp-1Ch] BYREF
  void *ppvData[3]; // [rsp+38h] [rbp-18h] BYREF
  ULONG pulSize; // [rsp+90h] [rbp+40h] BYREF

  plLbound = 0;
  plUbound = 0;
  if ( SafeArrayGetLBound(a2, 1u, &plLbound) < 0 || SafeArrayGetUBound(a2, 1u, &plUbound) < 0 )
    return 0;
  v4 = 8;
  v5 = plUbound - plLbound + 1;
  Elemsize = SafeArrayGetElemsize(a2);
  ppvData[0] = 0;
  SafeArrayAccessData(a2, ppvData);
  ppvData[1] = a2;
  if ( a1 == 8 )
  {
    for ( i = 0; i < v5; ++i )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(*((_QWORD *)ppvData[0] + (unsigned int)i) + 2 * v9) );
      v4 += 2 * v9 + 4;
    }
  }
  else if ( a1 == 13 )
  {
    v10 = (LPUNKNOWN *)ppvData[0];
    for ( j = 0; j < v5; ++j )
    {
      pulSize = 0;
      MarshalSizeMax = CoGetMarshalSizeMax(&pulSize, &IID_IWbemClassObject, v10[j], 0, 0, 0);
      if ( MarshalSizeMax < 0 )
      {
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
            (unsigned int)MarshalSizeMax);
        }
        SafeArrayUnaccessData(a2);
        return 0;
      }
      v4 += pulSize;
    }
  }
  else
  {
    v4 = v5 * Elemsize + 8;
  }
  SafeArrayUnaccessData(a2);
  return v4;
}

```

## disassembly

```asm
0x18005183c  mov     [rsp-28h+arg_0], rbx
0x180051841  mov     [rsp-28h+arg_8], rsi
0x180051846  push    rbp
0x180051847  push    rdi
0x180051848  push    r12
0x18005184a  push    r14
0x18005184c  push    r15
0x18005184e  mov     rbp, rsp
0x180051851  sub     rsp, 50h
0x180051855  mov     r14, rdx
0x180051858  movzx   r15d, cx
0x18005185c  xor     r12d, r12d
0x18005185f  mov     [rbp+plLbound], r12d
0x180051863  mov     [rbp+plUbound], r12d
0x180051867  lea     r8, [rbp+plLbound]; plLbound
0x18005186b  lea     edx, [r12+1]; nDim
0x180051870  mov     rcx, r14; psa
0x180051873  call    cs:__imp_SafeArrayGetLBound
0x180051879  test    eax, eax
0x18005187b  js      short loc_1800518F6
0x18005187d  lea     r8, [rbp+plUbound]; plUbound
0x180051881  lea     edx, [r12+1]; nDim
0x180051886  mov     rcx, r14; psa
0x180051889  call    cs:__imp_SafeArrayGetUBound
0x18005188f  test    eax, eax
0x180051891  js      short loc_1800518F6
0x180051893  lea     ebx, [r12+8]
0x180051898  mov     esi, [rbp+plUbound]
0x18005189b  sub     esi, [rbp+plLbound]
0x18005189e  inc     esi
0x1800518a0  mov     rcx, r14; psa
0x1800518a3  call    cs:__imp_SafeArrayGetElemsize
0x1800518a9  mov     edi, eax
0x1800518ab  mov     [rbp+ppvData], r12
0x1800518af  lea     rdx, [rbp+ppvData]; ppvData
0x1800518b3  mov     rcx, r14; psa
0x1800518b6  call    cs:__imp_SafeArrayAccessData
0x1800518bc  mov     [rbp+var_10], r14
0x1800518c0  cmp     r15w, bx
0x1800518c4  jz      short loc_1800518FA
0x1800518c6  cmp     r15w, 0Dh
0x1800518cb  jz      short loc_180051927
0x1800518cd  imul    edi, esi
0x1800518d0  add     ebx, edi
0x1800518d2  mov     rcx, r14; psa
0x1800518d5  call    cs:__imp_SafeArrayUnaccessData
0x1800518db  mov     eax, ebx
0x1800518dd  lea     r11, [rsp+50h+var_s0]
0x1800518e2  mov     rbx, [r11+30h]
0x1800518e6  mov     rsi, [r11+38h]
0x1800518ea  mov     rsp, r11
0x1800518ed  pop     r15
0x1800518ef  pop     r14
0x1800518f1  pop     r12
0x1800518f3  pop     rdi
0x1800518f4  pop     rbp
0x1800518f5  retn
0x1800518f6  xor     eax, eax
0x1800518f8  jmp     short loc_1800518DD
0x1800518fa  mov     r8, [rbp+ppvData]
0x1800518fe  mov     ecx, r12d
0x180051901  test    esi, esi
0x180051903  jle     short loc_1800518D2
0x180051905  mov     eax, ecx
0x180051907  mov     rdx, [r8+rax*8]
0x18005190b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005190f  inc     rax
0x180051912  cmp     [rdx+rax*2], r12w
0x180051917  jnz     short loc_18005190F
0x180051919  lea     ebx, [rbx+rax*2]
0x18005191c  add     ebx, 4
0x18005191f  inc     ecx
0x180051921  cmp     ecx, esi
0x180051923  jl      short loc_180051905
0x180051925  jmp     short loc_1800518D2
0x180051927  mov     r15, [rbp+ppvData]
0x18005192b  mov     edi, r12d
0x18005192e  cmp     edi, esi
0x180051930  jge     short loc_1800518D2
0x180051932  mov     [rbp+pulSize], r12d
0x180051936  movsxd  r8, edi
0x180051939  mov     [rsp+50h+mshlflags], r12d; mshlflags
0x18005193e  mov     [rsp+50h+pvDestContext], r12; pvDestContext
0x180051943  xor     r9d, r9d; dwDestContext
0x180051946  mov     r8, [r15+r8*8]; pUnk
0x18005194a  lea     rdx, IID_IWbemClassObject; riid
0x180051951  lea     rcx, [rbp+pulSize]; pulSize
0x180051955  call    cs:__imp_CoGetMarshalSizeMax
0x18005195b  test    eax, eax
0x18005195d  js      short loc_180051966
0x18005195f  add     ebx, [rbp+pulSize]
0x180051962  inc     edi
0x180051964  jmp     short loc_18005192E
0x180051966  lea     rdx, WPP_GLOBAL_Control
0x18005196d  mov     rcx, cs:WPP_GLOBAL_Control
0x180051974  cmp     rcx, rdx
0x180051977  jz      short loc_18005199E
0x180051979  test    byte ptr [rcx+1Ch], 1
0x18005197d  jz      short loc_18005199E
0x18005197f  cmp     byte ptr [rcx+19h], 2
0x180051983  jb      short loc_18005199E
0x180051985  mov     edx, 14h
0x18005198a  mov     r9d, eax
0x18005198d  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180051994  mov     rcx, [rcx+10h]
0x180051998  call    WPP_SF_d
0x18005199d  nop
0x18005199e  mov     rcx, r14; psa
0x1800519a1  call    cs:__imp_SafeArrayUnaccessData
0x1800519a7  jmp     loc_1800518F6
```
