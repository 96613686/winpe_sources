# CShareItemResult::Init(IShellItem *,IShellItem *,_SHARE_ITEM_TYPE,_SHARE_OPERATION_RESULT)

- ea: `0x180066028`
- end: `0x1800661a7`
- name: `?Init@CShareItemResult@@IEAAJPEAUIShellItem@@0W4_SHARE_ITEM_TYPE@@W4_SHARE_OPERATION_RESULT@@@Z`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065e44`

## callees

- `0x1800095a0`
- `0x18001c4a8`
- `0x180066028`
- `0x180066250`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006617c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006617c`
- `SHELL32!SHCreateItemFromParsingName` at `0x180066158`
- `SHELL32!SHCreateItemFromParsingName` at `0x180066170`
- `SHELL32!SHCreateItemFromParsingName` at `0x180066158`
- `SHELL32!SHCreateItemFromParsingName` at `0x180066170`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShareItemResult::Init(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  _QWORD *v9; // rdi
  void **v10; // rdi
  _QWORD *v11; // r14
  int v12; // eax
  HRESULT Related; // ebx
  PCWSTR pszPath; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+38h] [rbp-8h] BYREF
  PCWSTR v17; // [rsp+70h] [rbp+30h] BYREF

  v9 = (_QWORD *)(a1 + 8);
  if ( a1 != -8 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    if ( *v9 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
    *v9 = a2;
  }
  v10 = (void **)(a1 + 16);
  if ( a1 != -16 )
  {
    if ( *v10 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)*v10 + 16LL))(*v10);
    *v10 = 0;
  }
  v11 = (_QWORD *)(a1 + 24);
  if ( a1 != -24 )
  {
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    if ( *v11 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
    *v11 = a3;
  }
  *(_DWORD *)(a1 + 32) = a4;
  v12 = a5;
  *(_DWORD *)(a1 + 36) = a5;
  Related = 0;
  if ( !v12 )
  {
    v16 = 0;
    Related = GetRelatedItem<IIdentityName>(a2, a2, a3, a4, (__int64)&v16);
    if ( Related >= 0 )
    {
      v17 = 0;
      Related = (*(__int64 (__fastcall **)(__int64, __int64, PCWSTR *))(*(_QWORD *)v16 + 40LL))(v16, 2147844096LL, &v17);
      if ( Related >= 0 )
      {
        pszPath = 0;
        if ( (int)PathMapLocalToUNC(v17, (unsigned __int16 **)&pszPath) < 0 )
        {
          Related = SHCreateItemFromParsingName(v17, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v10);
        }
        else
        {
          Related = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v10);
          CoTaskMemFree((LPVOID)pszPath);
        }
        CoTaskMemFree((LPVOID)v17);
      }
    }
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v16);
  }
  return (unsigned int)Related;
}

```

## disassembly

```asm
0x180066028  mov     [rsp-28h+arg_8], rbx
0x18006602d  mov     [rsp-28h+arg_10], rsi
0x180066032  push    rbp
0x180066033  push    rdi
0x180066034  push    r12
0x180066036  push    r14
0x180066038  push    r15
0x18006603a  mov     rbp, rsp
0x18006603d  sub     rsp, 40h
0x180066041  mov     r12d, r9d
0x180066044  mov     r15, r8
0x180066047  mov     rsi, rdx
0x18006604a  mov     rbx, rcx
0x18006604d  lea     rdi, [rcx+8]
0x180066051  test    rdi, rdi
0x180066054  jz      short loc_180066081
0x180066056  test    rdx, rdx
0x180066059  jz      short loc_18006606A
0x18006605b  mov     rax, [rdx]
0x18006605e  mov     rcx, rdx
0x180066061  mov     rax, [rax+8]
0x180066065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006606a  mov     rcx, [rdi]
0x18006606d  test    rcx, rcx
0x180066070  jz      short loc_18006607E
0x180066072  mov     rax, [rcx]
0x180066075  mov     rax, [rax+10h]
0x180066079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006607e  mov     [rdi], rsi
0x180066081  lea     rdi, [rbx+10h]
0x180066085  test    rdi, rdi
0x180066088  jz      short loc_1800660A5
0x18006608a  mov     rcx, [rdi]
0x18006608d  test    rcx, rcx
0x180066090  jz      short loc_18006609E
0x180066092  mov     rax, [rcx]
0x180066095  mov     rax, [rax+10h]
0x180066099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006609e  mov     qword ptr [rdi], 0
0x1800660a5  lea     r14, [rbx+18h]
0x1800660a9  test    r14, r14
0x1800660ac  jz      short loc_1800660D9
0x1800660ae  test    r15, r15
0x1800660b1  jz      short loc_1800660C2
0x1800660b3  mov     rax, [r15]
0x1800660b6  mov     rcx, r15
0x1800660b9  mov     rax, [rax+8]
0x1800660bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660c2  mov     rcx, [r14]
0x1800660c5  test    rcx, rcx
0x1800660c8  jz      short loc_1800660D6
0x1800660ca  mov     rax, [rcx]
0x1800660cd  mov     rax, [rax+10h]
0x1800660d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660d6  mov     [r14], r15
0x1800660d9  mov     [rbx+20h], r12d
0x1800660dd  mov     eax, [rbp+arg_20]
0x1800660e0  mov     [rbx+24h], eax
0x1800660e3  xor     ebx, ebx
0x1800660e5  test    eax, eax
0x1800660e7  jnz     loc_18006618C
0x1800660ed  mov     [rbp+var_8], rbx
0x1800660f1  lea     rax, [rbp+var_8]
0x1800660f5  mov     [rsp+40h+var_20], rax
0x1800660fa  mov     rcx, rsi
0x1800660fd  call    ??$GetRelatedItem@UIIdentityName@@@@YAJPEAUIShellItem@@PEAUIBindCtx@@_NAEBU_GUID@@PEAPEAX@Z; GetRelatedItem<IIdentityName>(IShellItem *,IBindCtx *,bool,_GUID const &,void * *)
0x180066102  mov     ebx, eax
0x180066104  test    eax, eax
0x180066106  js      short loc_180066183
0x180066108  mov     [rbp+arg_0], 0
0x180066110  mov     rcx, [rbp+var_8]
0x180066114  mov     rax, [rcx]
0x180066117  lea     r8, [rbp+arg_0]
0x18006611b  mov     edx, 80058000h
0x180066120  mov     rax, [rax+28h]
0x180066124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066129  mov     ebx, eax
0x18006612b  test    eax, eax
0x18006612d  js      short loc_180066183
0x18006612f  mov     [rbp+pszPath], 0
0x180066137  lea     rdx, [rbp+pszPath]; unsigned __int16 **
0x18006613b  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x18006613f  call    ?PathMapLocalToUNC@@YAJPEBGPEAPEAG@Z; PathMapLocalToUNC(ushort const *,ushort * *)
0x180066144  mov     r9, rdi; ppv
0x180066147  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18006614e  xor     edx, edx; pbc
0x180066150  test    eax, eax
0x180066152  js      short loc_18006616C
0x180066154  mov     rcx, [rbp+pszPath]; pszPath
0x180066158  call    cs:__imp_SHCreateItemFromParsingName
0x18006615e  mov     ebx, eax
0x180066160  mov     rcx, [rbp+pszPath]; pv
0x180066164  call    cs:__imp_CoTaskMemFree
0x18006616a  jmp     short loc_180066178
0x18006616c  mov     rcx, [rbp+arg_0]; pszPath
0x180066170  call    cs:__imp_SHCreateItemFromParsingName
0x180066176  mov     ebx, eax
0x180066178  mov     rcx, [rbp+arg_0]; pv
0x18006617c  call    cs:__imp_CoTaskMemFree
0x180066182  nop
0x180066183  lea     rcx, [rbp+var_8]
0x180066187  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18006618c  mov     eax, ebx
0x18006618e  lea     r11, [rsp+40h+var_s0]
0x180066193  mov     rbx, [r11+38h]
0x180066197  mov     rsi, [r11+40h]
0x18006619b  mov     rsp, r11
0x18006619e  pop     r15
0x1800661a0  pop     r14
0x1800661a2  pop     r12
0x1800661a4  pop     rdi
0x1800661a5  pop     rbp
0x1800661a6  retn
```
