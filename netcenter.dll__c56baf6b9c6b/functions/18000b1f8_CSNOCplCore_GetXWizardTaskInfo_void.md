# CSNOCplCore::GetXWizardTaskInfo(void)

- ea: `0x18000b1f8`
- end: `0x18000b37d`
- name: `?GetXWizardTaskInfo@CSNOCplCore@@AEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000bf2c`

## callees

- `0x180007e50`
- `0x18000b1f8`
- `0x18000bab0`
- `0x180014274`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b233`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b233`

## string_xrefs

- `0x18000b271`: `createnewbtn`
- `0x18000b262`: `createnewarea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSNOCplCore::GetXWizardTaskInfo(CSNOCplCore *this)
{
  HRESULT v2; // ebx
  unsigned int i; // esi
  __int64 v4; // rdi
  const unsigned __int16 *v5; // r15
  const wchar_t *v6; // rbp
  int v7; // r8d
  void *v8; // rcx
  int v9; // eax
  HRESULT v10; // eax
  LPVOID pv; // [rsp+68h] [rbp+10h] BYREF
  LPVOID v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = 0;
  v2 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &GUID_777ba87a_2498_4875_933a_3067de883070, &v13);
  if ( v2 >= 0 )
  {
    v2 = -2147418113;
    for ( i = 0; i < 2; ++i )
    {
      v4 = 32LL * (int)i;
      if ( *(_DWORD *)((char *)&g_rgTaskProp + v4) == 1 )
      {
        v5 = L"createnewarea";
        if ( i )
          v5 = 0;
        v6 = L"createnewbtn";
        if ( i )
          v6 = 0;
        pv = 0;
        v2 = (*(__int64 (__fastcall **)(LPVOID, void *, char *, LPVOID *))(*(_QWORD *)v13 + 168LL))(
               v13,
               &unk_180028498,
               &byte_18003238C[v4],
               &pv);
        if ( v2 )
          goto LABEL_15;
        v8 = pv;
        v9 = *((_DWORD *)pv + 1);
        *(_DWORD *)((char *)&g_rgTaskProp + v4 + 28) = v9;
        if ( v6 && (v9 & 3) != 3 )
        {
          v2 = CSNOCplCore::HideElement(this, v5, v7, 1);
          v8 = pv;
        }
        v10 = 0;
        if ( v2 != 1 )
          v10 = v2;
        v2 = v10;
        CoTaskMemFree(v8);
        if ( v2 )
        {
LABEL_15:
          dword_18003239C[8 * i] = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              100,
              &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
              (unsigned int)v2);
          if ( v6 )
            CSNOCplCore::HideElement(this, v5, v7, 1);
          v2 = 0;
        }
      }
    }
  }
  ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&v13);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b1f8  mov     r11, rsp
0x18000b1fb  mov     [r11+8], rbx
0x18000b1ff  push    rbp
0x18000b200  push    rsi
0x18000b201  push    rdi
0x18000b202  push    r14
0x18000b204  push    r15
0x18000b206  sub     rsp, 30h
0x18000b20a  mov     r14, rcx
0x18000b20d  mov     qword ptr [r11+18h], 0
0x18000b215  lea     rax, [r11+18h]
0x18000b219  mov     [r11-38h], rax
0x18000b21d  lea     r9, _GUID_777ba87a_2498_4875_933a_3067de883070; riid
0x18000b224  xor     edx, edx; pUnkOuter
0x18000b226  mov     r8d, 401h; dwClsContext
0x18000b22c  lea     rcx, CLSID_CXWizard; rclsid
0x18000b233  call    cs:__imp_CoCreateInstance
0x18000b239  mov     ebx, eax
0x18000b23b  test    eax, eax
0x18000b23d  js      loc_18000B360
0x18000b243  mov     ebx, 8000FFFFh
0x18000b248  xor     esi, esi
0x18000b24a  lea     rdx, ?g_rgTaskProp@@3PAUtagTASKPROP@@A; tagTASKPROP near * g_rgTaskProp
0x18000b251  movsxd  rdi, esi
0x18000b254  shl     rdi, 5
0x18000b258  cmp     dword ptr [rdi+rdx], 1
0x18000b25c  jnz     loc_18000B355
0x18000b262  lea     r15, aCreatenewarea; "createnewarea"
0x18000b269  xor     eax, eax
0x18000b26b  test    esi, esi
0x18000b26d  cmovnz  r15, rax
0x18000b271  lea     rbp, aCreatenewbtn; "createnewbtn"
0x18000b278  cmovnz  rbp, rax
0x18000b27c  mov     [rsp+58h+pv], rax
0x18000b281  mov     rcx, [rsp+58h+arg_10]
0x18000b286  mov     rax, [rcx]
0x18000b289  lea     r8, [rdx+0Ch]
0x18000b28d  add     r8, rdi
0x18000b290  lea     r9, [rsp+58h+pv]
0x18000b295  lea     rdx, unk_180028498
0x18000b29c  mov     rax, [rax+0A8h]
0x18000b2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a8  mov     ebx, eax
0x18000b2aa  test    eax, eax
0x18000b2ac  jnz     short loc_18000B2F7
0x18000b2ae  mov     rcx, [rsp+58h+pv]
0x18000b2b3  mov     eax, [rcx+4]
0x18000b2b6  lea     rdx, ?g_rgTaskProp@@3PAUtagTASKPROP@@A; tagTASKPROP near * g_rgTaskProp
0x18000b2bd  mov     [rdi+rdx+1Ch], eax
0x18000b2c1  test    rbp, rbp
0x18000b2c4  jz      short loc_18000B2E3
0x18000b2c6  and     eax, 3
0x18000b2c9  cmp     al, 3
0x18000b2cb  jz      short loc_18000B2E3
0x18000b2cd  lea     r9d, [rbx+1]; int
0x18000b2d1  mov     rdx, r15; unsigned __int16 *
0x18000b2d4  mov     rcx, r14; this
0x18000b2d7  call    ?HideElement@CSNOCplCore@@AEAAJPEBGHH@Z; CSNOCplCore::HideElement(ushort const *,int,int)
0x18000b2dc  mov     ebx, eax
0x18000b2de  mov     rcx, [rsp+58h+pv]; pv
0x18000b2e3  xor     eax, eax
0x18000b2e5  cmp     ebx, 1
0x18000b2e8  cmovnz  eax, ebx
0x18000b2eb  mov     ebx, eax
0x18000b2ed  call    cs:__imp_CoTaskMemFree
0x18000b2f3  test    ebx, ebx
0x18000b2f5  jz      short loc_18000B34E
0x18000b2f7  lea     rax, dword_18003239C
0x18000b2fe  mov     dword ptr [rax+rdi], 0
0x18000b305  lea     rax, WPP_GLOBAL_Control
0x18000b30c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b313  cmp     rcx, rax
0x18000b316  jz      short loc_18000B336
0x18000b318  test    byte ptr [rcx+1Ch], 2
0x18000b31c  jz      short loc_18000B336
0x18000b31e  mov     edx, 64h ; 'd'
0x18000b323  mov     r9d, ebx
0x18000b326  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000b32d  mov     rcx, [rcx+10h]
0x18000b331  call    WPP_SF_d
0x18000b336  test    rbp, rbp
0x18000b339  jz      short loc_18000B34C
0x18000b33b  mov     r9d, 1; int
0x18000b341  mov     rdx, r15; unsigned __int16 *
0x18000b344  mov     rcx, r14; this
0x18000b347  call    ?HideElement@CSNOCplCore@@AEAAJPEBGHH@Z; CSNOCplCore::HideElement(ushort const *,int,int)
0x18000b34c  xor     ebx, ebx
0x18000b34e  lea     rdx, ?g_rgTaskProp@@3PAUtagTASKPROP@@A; tagTASKPROP near * g_rgTaskProp
0x18000b355  inc     esi
0x18000b357  cmp     esi, 2
0x18000b35a  jb      loc_18000B251
0x18000b360  lea     rcx, [rsp+58h+arg_10]
0x18000b365  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x18000b36a  mov     eax, ebx
0x18000b36c  mov     rbx, [rsp+58h+arg_0]
0x18000b371  add     rsp, 30h
0x18000b375  pop     r15
0x18000b377  pop     r14
0x18000b379  pop     rdi
0x18000b37a  pop     rsi
0x18000b37b  pop     rbp
0x18000b37c  retn
```
