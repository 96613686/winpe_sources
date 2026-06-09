# COfflineFilesCache::_CreateItemEnumerator(IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,ulong,ulong,IEnumOfflineFilesItems * *)

- ea: `0x180003950`
- end: `0x180003c8f`
- name: `?_CreateItemEnumerator@COfflineFilesCache@@AEAAJPEAUIOfflineFilesItemFilter@@000KKPEAPEAUIEnumOfflineFilesItems@@@Z`
- size: `831`
- prototype: `__int64 __fastcall(COfflineFilesCache *__hidden this, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, unsigned int, unsigned int, struct IEnumOfflineFilesItems **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d670`

## callees

- `0x180003950`
- `0x180005410`
- `0x18000b390`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003a8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003a8f`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::_CreateItemEnumerator(
        COfflineFilesCache *this,
        struct IOfflineFilesItemFilter *a2,
        struct IOfflineFilesItemFilter *a3,
        struct IOfflineFilesItemFilter *a4,
        struct IOfflineFilesItemFilter *a5,
        unsigned int a6,
        unsigned int a7,
        struct IEnumOfflineFilesItems **ppv)
{
  struct IEnumOfflineFilesItems **v8; // r12
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rdx
  HRESULT Instance; // edi
  __int64 v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rbp
  _DWORD *v21; // rax
  _DWORD *v22; // rbx
  unsigned int v23; // edx
  unsigned int v24; // r8d
  int v25; // r9d
  __int64 v26[11]; // [rsp+40h] [rbp-58h] BYREF

  v8 = ppv;
  if ( !ppv )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)((_DWORD)ppv + 47),
        WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
    return 2147500035LL;
  }
  v13 = a6 & 0xFFFFFFFC;
  if ( (a6 & 0xFFFFFFFC) != 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      return 2147942487LL;
    v15 = 48;
LABEL_14:
    WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_91a48976ead63973ddd357b80bae3284_Traceguids, v13);
    return 2147942487LL;
  }
  v13 = a7 & 0x7FFFFFC0;
  if ( (a7 & 0x7FFFFFC0) != 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      return 2147942487LL;
    v15 = 49;
    goto LABEL_14;
  }
  v16 = (_QWORD *)*((_QWORD *)this + 5);
  Instance = -2147467262;
  v26[0] = 0;
  v18 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v16;
  if ( *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 == *v16 )
    v18 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v16[1];
  if ( !v18 )
  {
    v19 = *((_DWORD *)this + 12);
    if ( v19 )
    {
      ppv = 0;
      Instance = CoCreateInstance(
                   &CLSID_StdGlobalInterfaceTable,
                   0,
                   1u,
                   &GUID_00000146_0000_0000_c000_000000000046,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct IEnumOfflineFilesItems **, _QWORD, GUID *, __int64 *))(*ppv)[5].lpVtbl)(
                     ppv,
                     v19,
                     &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
                     v26);
        ((void (__fastcall *)(struct IEnumOfflineFilesItems **))(*ppv)[2].lpVtbl)(ppv);
      }
      if ( Instance >= 0 )
      {
        v20 = v26[0];
        *v8 = 0;
        Instance = -2147024882;
        v21 = operator new(0x288u);
        v22 = v21;
        if ( v21 )
        {
          v21[2] = 1;
          *((_QWORD *)v21 + 2) = v20;
          *((_QWORD *)v21 + 3) = 0;
          *(_QWORD *)v21 = &CEnumOfflineFilesItems::`vftable';
          *((_QWORD *)v21 + 71) = v21 + 8;
          *((_QWORD *)v21 + 73) = 520;
          *((_QWORD *)v21 + 72) = v21 + 8;
          *((_QWORD *)v21 + 74) = 520;
          *((_QWORD *)v21 + 70) = v21 + 8;
          if ( v21 != (_DWORD *)-32LL )
            *((_WORD *)v21 + 16) = 0;
          v21[138] = 34078720;
          v21[153] = a7;
          v21[152] = a6;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
          *((_QWORD *)v22 + 77) = a2;
          *((_QWORD *)v22 + 78) = a3;
          *((_QWORD *)v22 + 79) = a4;
          *((_QWORD *)v22 + 80) = a5;
          if ( a2 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a2->lpVtbl->AddRef)(a2);
          if ( a3 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a3->lpVtbl->AddRef)(a3);
          if ( a4 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a4->lpVtbl->AddRef)(a4);
          if ( a5 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a5->lpVtbl->AddRef)(a5);
          Instance = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, _QWORD, _DWORD, _DWORD *))(**((_QWORD **)v22 + 2) + 112LL))(
                       *((_QWORD *)v22 + 2),
                       v22 + 154,
                       0,
                       (unsigned int)v22[152],
                       v22[153],
                       v22 + 6);
          if ( Instance >= 0 )
          {
            Instance = CscCom_SetClientProxyBlanket(*((IUnknown **)v22 + 3), v23, v24, v25);
            if ( Instance >= 0 )
              Instance = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, struct IEnumOfflineFilesItems **))v22)(
                           v22,
                           &GUID_da70e815_c361_4407_bc0b_0d7046e5f2cd,
                           v8);
          }
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v22 + 16LL))(v22);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26[0] + 16LL))(v26[0]);
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003950  push    rbx
0x180003952  push    rbp
0x180003953  push    rsi
0x180003954  push    rdi
0x180003955  push    r12
0x180003957  push    r13
0x180003959  push    r14
0x18000395b  push    r15
0x18000395d  sub     rsp, 58h
0x180003961  mov     r12, [rsp+98h+arg_38]
0x180003969  mov     rsi, r9
0x18000396c  mov     r14, r8
0x18000396f  mov     r15, rdx
0x180003972  test    r12, r12
0x180003975  jnz     short loc_1800039AF
0x180003977  mov     rcx, cs:WPP_GLOBAL_Control
0x18000397e  lea     rax, WPP_GLOBAL_Control
0x180003985  cmp     rcx, rax
0x180003988  jz      short loc_1800039A5
0x18000398a  test    byte ptr [rcx+1Ch], 2
0x18000398e  jz      short loc_1800039A5
0x180003990  mov     rcx, [rcx+10h]
0x180003994  lea     edx, [r12+2Fh]
0x180003999  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x1800039a0  call    WPP_SF_
0x1800039a5  mov     eax, 80004003h
0x1800039aa  jmp     loc_180003C7E
0x1800039af  mov     r13d, [rsp+98h+arg_28]
0x1800039b7  mov     r9d, r13d
0x1800039ba  and     r9d, 0FFFFFFFCh
0x1800039be  jz      short loc_1800039E0
0x1800039c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039c7  lea     rax, WPP_GLOBAL_Control
0x1800039ce  cmp     rcx, rax
0x1800039d1  jz      short loc_180003A1F
0x1800039d3  test    byte ptr [rcx+1Ch], 2
0x1800039d7  jz      short loc_180003A1F
0x1800039d9  mov     edx, 30h ; '0'
0x1800039de  jmp     short loc_180003A0F
0x1800039e0  mov     r9d, [rsp+98h+arg_30]
0x1800039e8  and     r9d, 7FFFFFC0h
0x1800039ef  jz      short loc_180003A29
0x1800039f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039f8  lea     rax, WPP_GLOBAL_Control
0x1800039ff  cmp     rcx, rax
0x180003a02  jz      short loc_180003A1F
0x180003a04  test    byte ptr [rcx+1Ch], 2
0x180003a08  jz      short loc_180003A1F
0x180003a0a  mov     edx, 31h ; '1'
0x180003a0f  mov     rcx, [rcx+10h]
0x180003a13  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x180003a1a  call    WPP_SF_d
0x180003a1f  mov     eax, 80070057h
0x180003a24  jmp     loc_180003C7E
0x180003a29  mov     rdx, [rcx+28h]
0x180003a2d  mov     edi, 80004002h
0x180003a32  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x180003a39  mov     [rsp+98h+var_58], 0
0x180003a42  sub     rax, [rdx]
0x180003a45  jnz     short loc_180003A52
0x180003a47  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x180003a4e  sub     rax, [rdx+8]
0x180003a52  test    rax, rax
0x180003a55  jnz     loc_180003C7C
0x180003a5b  mov     ebx, [rcx+30h]
0x180003a5e  test    ebx, ebx
0x180003a60  jz      loc_180003C7C
0x180003a66  xor     edx, edx; pUnkOuter
0x180003a68  mov     [rsp+98h+arg_38], rax
0x180003a70  lea     rax, [rsp+98h+arg_38]
0x180003a78  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003a7f  mov     [rsp+98h+ppv], rax; ppv
0x180003a84  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003a8b  lea     r8d, [rdx+1]; dwClsContext
0x180003a8f  call    cs:__imp_CoCreateInstance
0x180003a95  mov     edi, eax
0x180003a97  test    eax, eax
0x180003a99  js      short loc_180003AD3
0x180003a9b  mov     rcx, [rsp+98h+arg_38]
0x180003aa3  lea     r9, [rsp+98h+var_58]
0x180003aa8  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180003aaf  mov     edx, ebx
0x180003ab1  mov     rax, [rcx]
0x180003ab4  mov     rax, [rax+28h]
0x180003ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abd  mov     rcx, [rsp+98h+arg_38]
0x180003ac5  mov     edi, eax
0x180003ac7  mov     rax, [rcx]
0x180003aca  mov     rax, [rax+10h]
0x180003ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad3  test    edi, edi
0x180003ad5  js      loc_180003C7C
0x180003adb  mov     rbp, [rsp+98h+var_58]
0x180003ae0  mov     ecx, 288h; Size
0x180003ae5  mov     qword ptr [r12], 0
0x180003aed  mov     edi, 8007000Eh
0x180003af2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003af7  mov     rbx, rax
0x180003afa  test    rax, rax
0x180003afd  jz      loc_180003C6B
0x180003b03  mov     dword ptr [rbx+8], 1
0x180003b0a  lea     rdx, [rbx+20h]
0x180003b0e  mov     [rbx+10h], rbp
0x180003b12  mov     ecx, 208h
0x180003b17  mov     qword ptr [rbx+18h], 0
0x180003b1f  lea     rax, ??_7CEnumOfflineFilesItems@@6B@; const CEnumOfflineFilesItems::`vftable'
0x180003b26  mov     [rbx], rax
0x180003b29  mov     [rbx+238h], rdx
0x180003b30  mov     [rbx+248h], rcx
0x180003b37  mov     [rbx+240h], rdx
0x180003b3e  mov     [rbx+250h], rcx
0x180003b45  mov     [rbx+230h], rdx
0x180003b4c  test    rdx, rdx
0x180003b4f  jz      short loc_180003B56
0x180003b51  xor     eax, eax
0x180003b53  mov     [rdx], ax
0x180003b56  mov     eax, [rsp+98h+arg_30]
0x180003b5d  mov     rcx, rbp
0x180003b60  mov     dword ptr [rbx+228h], 2080000h
0x180003b6a  mov     [rbx+264h], eax
0x180003b70  mov     [rbx+260h], r13d
0x180003b77  mov     rax, [rbp+0]
0x180003b7b  mov     rax, [rax+8]
0x180003b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b84  mov     rdi, [rsp+98h+arg_20]
0x180003b8c  mov     [rbx+268h], r15
0x180003b93  mov     [rbx+270h], r14
0x180003b9a  mov     [rbx+278h], rsi
0x180003ba1  mov     [rbx+280h], rdi
0x180003ba8  test    r15, r15
0x180003bab  jz      short loc_180003BBC
0x180003bad  mov     rax, [r15]
0x180003bb0  mov     rcx, r15
0x180003bb3  mov     rax, [rax+8]
0x180003bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbc  test    r14, r14
0x180003bbf  jz      short loc_180003BD0
0x180003bc1  mov     rax, [r14]
0x180003bc4  mov     rcx, r14
0x180003bc7  mov     rax, [rax+8]
0x180003bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd0  test    rsi, rsi
0x180003bd3  jz      short loc_180003BE4
0x180003bd5  mov     rax, [rsi]
0x180003bd8  mov     rcx, rsi
0x180003bdb  mov     rax, [rax+8]
0x180003bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be4  test    rdi, rdi
0x180003be7  jz      short loc_180003BF8
0x180003be9  mov     rax, [rdi]
0x180003bec  mov     rcx, rdi
0x180003bef  mov     rax, [rax+8]
0x180003bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf8  mov     r8d, [rbx+264h]
0x180003bff  lea     rsi, [rbx+18h]
0x180003c03  mov     rcx, [rbx+10h]
0x180003c07  lea     rdx, [rbx+268h]
0x180003c0e  mov     r9d, [rbx+260h]
0x180003c15  mov     [rsp+98h+var_70], rsi
0x180003c1a  mov     dword ptr [rsp+98h+ppv], r8d
0x180003c1f  xor     r8d, r8d
0x180003c22  mov     rax, [rcx]
0x180003c25  mov     rax, [rax+70h]
0x180003c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2e  mov     edi, eax
0x180003c30  test    eax, eax
0x180003c32  js      short loc_180003C5C
0x180003c34  mov     rcx, [rsi]; pProxy
0x180003c37  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x180003c3c  mov     edi, eax
0x180003c3e  test    eax, eax
0x180003c40  js      short loc_180003C5C
0x180003c42  mov     rax, [rbx]
0x180003c45  lea     rdx, _GUID_da70e815_c361_4407_bc0b_0d7046e5f2cd
0x180003c4c  mov     r8, r12
0x180003c4f  mov     rcx, rbx
0x180003c52  mov     rax, [rax]
0x180003c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5a  mov     edi, eax
0x180003c5c  mov     rax, [rbx]
0x180003c5f  mov     rcx, rbx
0x180003c62  mov     rax, [rax+10h]
0x180003c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c6b  mov     rcx, [rsp+98h+var_58]
0x180003c70  mov     rax, [rcx]
0x180003c73  mov     rax, [rax+10h]
0x180003c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c7c  mov     eax, edi
0x180003c7e  add     rsp, 58h
0x180003c82  pop     r15
0x180003c84  pop     r14
0x180003c86  pop     r13
0x180003c88  pop     r12
0x180003c8a  pop     rdi
0x180003c8b  pop     rsi
0x180003c8c  pop     rbp
0x180003c8d  pop     rbx
0x180003c8e  retn
```
