# CfgMgrHelper::SetSessionVariable(ushort const *,tagVARIANT const &)

- ea: `0x18003661c`
- end: `0x1800366b2`
- name: `?SetSessionVariable@CfgMgrHelper@@QEAAJPEBGAEBUtagVARIANT@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(LPVOID *ppv, OLECHAR *psz, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013e50`

## callees

- `0x18003661c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003664d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003664d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003665c`
- `OLEAUT32!__imp_SysAllocString` at `0x18003665c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800366a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800366a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CfgMgrHelper::SetSessionVariable(LPVOID *ppv, OLECHAR *psz, const struct tagVARIANT *a3)
{
  HRESULT Instance; // ebx
  BSTR v7; // rax
  OLECHAR *v8; // rsi
  LPVOID v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  IRecordInfo *pRecInfo; // [rsp+40h] [rbp-38h]

  if ( *ppv
    || (Instance = CoCreateInstance(
                     &GUID_66d0db14_5638_475f_a386_629522d8c461,
                     0,
                     1u,
                     &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                     ppv),
        Instance >= 0) )
  {
    v7 = SysAllocString(psz);
    v8 = v7;
    if ( v7 )
    {
      v9 = *ppv;
      v11 = *(_OWORD *)&a3->vt;
      pRecInfo = a3->pRecInfo;
      Instance = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(*(_QWORD *)v9 + 104LL))(v9, v7, &v11);
      SysFreeString(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003661c  push    rbx
0x18003661e  push    rbp
0x18003661f  push    rsi
0x180036620  push    rdi
0x180036621  sub     rsp, 58h
0x180036625  mov     rbp, r8
0x180036628  mov     rsi, rdx
0x18003662b  mov     rdi, rcx
0x18003662e  cmp     qword ptr [rcx], 0
0x180036632  jnz     short loc_180036659
0x180036634  mov     [rsp+78h+ppv], rcx; ppv
0x180036639  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180036640  xor     edx, edx; pUnkOuter
0x180036642  lea     r8d, [rdx+1]; dwClsContext
0x180036646  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18003664d  call    cs:__imp_CoCreateInstance
0x180036653  mov     ebx, eax
0x180036655  test    eax, eax
0x180036657  js      short loc_1800366A7
0x180036659  mov     rcx, rsi; psz
0x18003665c  call    cs:__imp_SysAllocString
0x180036662  mov     rsi, rax
0x180036665  test    rax, rax
0x180036668  jnz     short loc_180036671
0x18003666a  mov     ebx, 8007000Eh
0x18003666f  jmp     short loc_1800366A7
0x180036671  mov     rcx, [rdi]
0x180036674  movups  xmm0, xmmword ptr [rbp+0]
0x180036678  movaps  [rsp+78h+var_48], xmm0
0x18003667d  movsd   xmm1, qword ptr [rbp+10h]
0x180036682  movsd   [rsp+78h+var_38], xmm1
0x180036688  mov     rax, [rcx]
0x18003668b  lea     r8, [rsp+78h+var_48]
0x180036690  mov     rdx, rsi
0x180036693  mov     rax, [rax+68h]
0x180036697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003669c  mov     ebx, eax
0x18003669e  mov     rcx, rsi; bstrString
0x1800366a1  call    cs:__imp_SysFreeString
0x1800366a7  mov     eax, ebx
0x1800366a9  add     rsp, 58h
0x1800366ad  pop     rdi
0x1800366ae  pop     rsi
0x1800366af  pop     rbp
0x1800366b0  pop     rbx
0x1800366b1  retn
```
