# COfflineFilesCache::EnumItems(ulong,IEnumOfflineFilesItems * *)

- ea: `0x180004770`
- end: `0x180004a16`
- name: `?EnumItems@COfflineFilesCache@@UEAAJKPEAPEAUIEnumOfflineFilesItems@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(COfflineFilesCache *__hidden this, unsigned int, struct IEnumOfflineFilesItems **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004770`
- `0x180005410`
- `0x18000b390`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004867`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004867`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::EnumItems(COfflineFilesCache *this, int a2, struct IEnumOfflineFilesItems **a3)
{
  HRESULT v5; // edi
  _QWORD *v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // r14
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  unsigned int v12; // edx
  unsigned int v13; // r8d
  int v14; // r9d
  LPVOID ppv; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h] BYREF

  if ( a3 )
  {
    if ( (a2 & 0x7FFFFFC0) != 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          49,
          WPP_91a48976ead63973ddd357b80bae3284_Traceguids,
          a2 & 0x7FFFFFC0);
      return (unsigned int)-2147024809;
    }
    else
    {
      v6 = (_QWORD *)*((_QWORD *)this + 4);
      v5 = -2147467262;
      v17 = 0;
      v7 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v6;
      if ( *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 == *v6 )
        v7 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v6[1];
      if ( !v7 )
      {
        v8 = *((_DWORD *)this + 10);
        if ( v8 )
        {
          ppv = 0;
          v5 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
                   ppv,
                   v8,
                   &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
                   &v17);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          if ( v5 >= 0 )
          {
            v9 = v17;
            *a3 = 0;
            v5 = -2147024882;
            v10 = operator new(0x288u);
            v11 = v10;
            if ( v10 )
            {
              v10[2] = 1;
              *((_QWORD *)v10 + 2) = v9;
              *((_QWORD *)v10 + 3) = 0;
              *(_QWORD *)v10 = &CEnumOfflineFilesItems::`vftable';
              *((_QWORD *)v10 + 71) = v10 + 8;
              *((_QWORD *)v10 + 73) = 520;
              *((_QWORD *)v10 + 72) = v10 + 8;
              *((_QWORD *)v10 + 74) = 520;
              *((_QWORD *)v10 + 70) = v10 + 8;
              if ( v10 != (_DWORD *)-32LL )
                *((_WORD *)v10 + 16) = 0;
              v10[138] = 34078720;
              v10[152] = 0;
              v10[153] = a2;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
              *((_QWORD *)v11 + 77) = 0;
              *((_QWORD *)v11 + 78) = 0;
              *((_QWORD *)v11 + 79) = 0;
              *((_QWORD *)v11 + 80) = 0;
              v5 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, _QWORD, _DWORD, _DWORD *))(**((_QWORD **)v11 + 2)
                                                                                                 + 112LL))(
                     *((_QWORD *)v11 + 2),
                     v11 + 154,
                     0,
                     (unsigned int)v11[152],
                     v11[153],
                     v11 + 6);
              if ( v5 >= 0 )
              {
                v5 = CscCom_SetClientProxyBlanket(*((IUnknown **)v11 + 3), v12, v13, v14);
                if ( v5 >= 0 )
                  v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, struct IEnumOfflineFilesItems **))v11)(
                         v11,
                         &GUID_da70e815_c361_4407_bc0b_0d7046e5f2cd,
                         a3);
              }
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
      }
    }
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004770  mov     [rsp+arg_8], rbx
0x180004775  mov     [rsp+arg_18], rbp
0x18000477a  push    rsi
0x18000477b  push    rdi
0x18000477c  push    r14
0x18000477e  sub     rsp, 40h
0x180004782  mov     rsi, r8
0x180004785  mov     ebp, edx
0x180004787  test    r8, r8
0x18000478a  jnz     short loc_1800047C3
0x18000478c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004793  lea     rax, WPP_GLOBAL_Control
0x18000479a  cmp     rcx, rax
0x18000479d  jz      short loc_1800047B9
0x18000479f  test    byte ptr [rcx+1Ch], 2
0x1800047a3  jz      short loc_1800047B9
0x1800047a5  mov     rcx, [rcx+10h]
0x1800047a9  lea     edx, [r8+2Fh]
0x1800047ad  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x1800047b4  call    WPP_SF_
0x1800047b9  mov     edi, 80004003h
0x1800047be  jmp     loc_180004A01
0x1800047c3  mov     r9d, ebp
0x1800047c6  and     r9d, 7FFFFFC0h
0x1800047cd  jz      short loc_180004807
0x1800047cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047d6  lea     rax, WPP_GLOBAL_Control
0x1800047dd  cmp     rcx, rax
0x1800047e0  jz      short loc_1800047FD
0x1800047e2  test    byte ptr [rcx+1Ch], 2
0x1800047e6  jz      short loc_1800047FD
0x1800047e8  mov     rcx, [rcx+10h]
0x1800047ec  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x1800047f3  mov     edx, 31h ; '1'
0x1800047f8  call    WPP_SF_d
0x1800047fd  mov     edi, 80070057h
0x180004802  jmp     loc_180004A01
0x180004807  mov     rdx, [rcx+20h]
0x18000480b  mov     edi, 80004002h
0x180004810  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x180004817  mov     [rsp+58h+arg_10], 0
0x180004820  sub     rax, [rdx]
0x180004823  jnz     short loc_180004830
0x180004825  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x18000482c  sub     rax, [rdx+8]
0x180004830  test    rax, rax
0x180004833  jnz     loc_180004A01
0x180004839  mov     ebx, [rcx+28h]
0x18000483c  test    ebx, ebx
0x18000483e  jz      loc_180004A01
0x180004844  xor     edx, edx; pUnkOuter
0x180004846  mov     [rsp+58h+arg_0], rax
0x18000484b  lea     rax, [rsp+58h+arg_0]
0x180004850  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004857  mov     [rsp+58h+ppv], rax; ppv
0x18000485c  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004863  lea     r8d, [rdx+1]; dwClsContext
0x180004867  call    cs:__imp_CoCreateInstance
0x18000486d  mov     edi, eax
0x18000486f  test    eax, eax
0x180004871  js      short loc_1800048A5
0x180004873  mov     rcx, [rsp+58h+arg_0]
0x180004878  lea     r9, [rsp+58h+arg_10]
0x18000487d  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180004884  mov     edx, ebx
0x180004886  mov     rax, [rcx]
0x180004889  mov     rax, [rax+28h]
0x18000488d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004892  mov     rcx, [rsp+58h+arg_0]
0x180004897  mov     edi, eax
0x180004899  mov     rax, [rcx]
0x18000489c  mov     rax, [rax+10h]
0x1800048a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a5  test    edi, edi
0x1800048a7  js      loc_180004A01
0x1800048ad  mov     r14, [rsp+58h+arg_10]
0x1800048b2  mov     ecx, 288h; Size
0x1800048b7  mov     qword ptr [rsi], 0
0x1800048be  mov     edi, 8007000Eh
0x1800048c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800048c8  mov     rbx, rax
0x1800048cb  test    rax, rax
0x1800048ce  jz      loc_1800049F0
0x1800048d4  mov     dword ptr [rbx+8], 1
0x1800048db  lea     rdx, [rbx+20h]
0x1800048df  mov     [rbx+10h], r14
0x1800048e3  mov     ecx, 208h
0x1800048e8  mov     qword ptr [rbx+18h], 0
0x1800048f0  lea     rax, ??_7CEnumOfflineFilesItems@@6B@; const CEnumOfflineFilesItems::`vftable'
0x1800048f7  mov     [rbx], rax
0x1800048fa  mov     [rbx+238h], rdx
0x180004901  mov     [rbx+248h], rcx
0x180004908  mov     [rbx+240h], rdx
0x18000490f  mov     [rbx+250h], rcx
0x180004916  mov     [rbx+230h], rdx
0x18000491d  test    rdx, rdx
0x180004920  jz      short loc_180004927
0x180004922  xor     eax, eax
0x180004924  mov     [rdx], ax
0x180004927  mov     dword ptr [rbx+228h], 2080000h
0x180004931  mov     rcx, r14
0x180004934  mov     dword ptr [rbx+260h], 0
0x18000493e  mov     [rbx+264h], ebp
0x180004944  mov     rax, [r14]
0x180004947  mov     rax, [rax+8]
0x18000494b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004950  mov     qword ptr [rbx+268h], 0
0x18000495b  lea     r14, [rbx+18h]
0x18000495f  mov     qword ptr [rbx+270h], 0
0x18000496a  lea     rdx, [rbx+268h]
0x180004971  mov     qword ptr [rbx+278h], 0
0x18000497c  xor     r8d, r8d
0x18000497f  mov     qword ptr [rbx+280h], 0
0x18000498a  mov     rcx, [rbx+10h]
0x18000498e  mov     r9d, [rbx+260h]
0x180004995  mov     [rsp+58h+var_30], r14
0x18000499a  mov     rax, [rcx]
0x18000499d  mov     r10, [rax+70h]
0x1800049a1  mov     eax, [rbx+264h]
0x1800049a7  mov     dword ptr [rsp+58h+ppv], eax
0x1800049ab  mov     rax, r10
0x1800049ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b3  mov     edi, eax
0x1800049b5  test    eax, eax
0x1800049b7  js      short loc_1800049E1
0x1800049b9  mov     rcx, [r14]; pProxy
0x1800049bc  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x1800049c1  mov     edi, eax
0x1800049c3  test    eax, eax
0x1800049c5  js      short loc_1800049E1
0x1800049c7  mov     rax, [rbx]
0x1800049ca  lea     rdx, _GUID_da70e815_c361_4407_bc0b_0d7046e5f2cd
0x1800049d1  mov     r8, rsi
0x1800049d4  mov     rcx, rbx
0x1800049d7  mov     rax, [rax]
0x1800049da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049df  mov     edi, eax
0x1800049e1  mov     rax, [rbx]
0x1800049e4  mov     rcx, rbx
0x1800049e7  mov     rax, [rax+10h]
0x1800049eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f0  mov     rcx, [rsp+58h+arg_10]
0x1800049f5  mov     rax, [rcx]
0x1800049f8  mov     rax, [rax+10h]
0x1800049fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a01  mov     rbx, [rsp+58h+arg_8]
0x180004a06  mov     eax, edi
0x180004a08  mov     rbp, [rsp+58h+arg_18]
0x180004a0d  add     rsp, 40h
0x180004a11  pop     r14
0x180004a13  pop     rdi
0x180004a14  pop     rsi
0x180004a15  retn
```
