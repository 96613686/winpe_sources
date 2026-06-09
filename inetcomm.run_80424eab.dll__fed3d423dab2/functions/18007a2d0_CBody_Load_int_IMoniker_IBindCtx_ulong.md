# CBody::Load(int,IMoniker *,IBindCtx *,ulong)

- ea: `0x18007a2d0`
- end: `0x18007a47c`
- name: `?Load@CBody@@UEAAJHPEAUIMoniker@@PEAUIBindCtx@@K@Z`
- size: `428`
- prototype: `__int64 __fastcall(CBody *__hidden this, int, struct IMoniker *, struct IBindCtx *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002098`
- `0x18007a2d0`
- `0x18007a4e4`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x18007a388`
- `SHLWAPI!StrCmpW` at `0x18007a388`
- `urlmon!FindMimeFromData` at `0x18007a36f`
- `urlmon!FindMimeFromData` at `0x18007a36f`
- `ole32!CoTaskMemFree` at `0x18007a394`
- `ole32!CoTaskMemFree` at `0x18007a394`
- `ole32!CoCreateInstance` at `0x18007a3bf`
- `ole32!CoCreateInstance` at `0x18007a3bf`

## pseudocode

```c
__int64 __fastcall CBody::Load(CBody *this, unsigned int a2, struct IMoniker *a3, struct IBindCtx *a4, unsigned int a5)
{
  int v10; // ebx
  HRESULT v11; // ebx
  LPWSTR ppwzMimeOut; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+48h] [rbp-30h] BYREF
  LPCWSTR pwzUrl; // [rsp+50h] [rbp-28h] BYREF
  _DWORD v15[2]; // [rsp+58h] [rbp-20h] BYREF
  struct IMoniker *v16; // [rsp+60h] [rbp-18h]
  LPVOID ppv; // [rsp+C0h] [rbp+48h] BYREF

  ppv = 0;
  v13 = 0;
  v15[1] = 0;
  pwzUrl = 0;
  if ( !a3 )
    return 2147942487LL;
  if ( ((unsigned int (__fastcall *)(struct IMoniker *, _QWORD, _QWORD, LPCWSTR *))a3->lpVtbl->GetDisplayName)(
         a3,
         0,
         0,
         &pwzUrl)
    || (ppwzMimeOut = 0, FindMimeFromData(0, pwzUrl, 0, 0, 0, 0, &ppwzMimeOut, 0) < 0)
    || (v10 = StrCmpW(ppwzMimeOut, L"message/rfc822"), CoTaskMemFree(ppwzMimeOut), v10) )
  {
    v15[0] = 1;
    v16 = a3;
    goto LABEL_11;
  }
  v11 = CoCreateInstance(&CLSID_IMimeMessage, 0, 1u, &GUID_fd853cd5_7f86_11d0_8252_00c04fd85ab4, &ppv);
  if ( v11 >= 0 )
  {
    v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
            ppv,
            &GUID_79eac9c9_baf9_11ce_8c82_00aa004ba90b,
            &v13);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMoniker *, struct IBindCtx *, unsigned int))(*(_QWORD *)v13 + 40LL))(
              v13,
              a2,
              a3,
              a4,
              a5);
      if ( v11 >= 0 )
      {
        v16 = (struct IMoniker *)ppv;
        v15[0] = 0;
LABEL_11:
        v11 = CBody::LoadFromData((CBody *)((char *)this - 200), (struct BODYINITDATA_tag *)v15);
      }
    }
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
  if ( pwzUrl )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007a2d0  push    rbp
0x18007a2d2  push    rbx
0x18007a2d3  push    rsi
0x18007a2d4  push    rdi
0x18007a2d5  push    r14
0x18007a2d7  push    r15
0x18007a2d9  mov     rbp, rsp
0x18007a2dc  sub     rsp, 78h
0x18007a2e0  mov     [rbp+ppv], 0
0x18007a2e8  mov     r14, r9
0x18007a2eb  mov     [rbp+var_30], 0
0x18007a2f3  mov     rdi, r8
0x18007a2f6  mov     [rbp+var_1C], 0
0x18007a2fd  mov     r15d, edx
0x18007a300  mov     [rbp+pwzUrl], 0
0x18007a308  mov     rsi, rcx
0x18007a30b  test    r8, r8
0x18007a30e  jnz     short loc_18007A31A
0x18007a310  mov     eax, 80070057h
0x18007a315  jmp     loc_18007A46F
0x18007a31a  mov     rax, [r8]
0x18007a31d  lea     r9, [rbp+pwzUrl]
0x18007a321  xor     r8d, r8d
0x18007a324  xor     edx, edx
0x18007a326  mov     rcx, rdi
0x18007a329  mov     rax, [rax+0A0h]
0x18007a330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a335  test    eax, eax
0x18007a337  jnz     loc_18007A422
0x18007a33d  mov     rdx, [rbp+pwzUrl]; pwzUrl
0x18007a341  xor     r9d, r9d; cbSize
0x18007a344  mov     [rsp+78h+dwReserved], eax; dwReserved
0x18007a348  xor     r8d, r8d; pBuffer
0x18007a34b  lea     rax, [rbp+var_38]
0x18007a34f  mov     [rbp+var_38], 0
0x18007a357  mov     [rsp+78h+ppwzMimeOut], rax; ppwzMimeOut
0x18007a35c  xor     ecx, ecx; pBC
0x18007a35e  mov     [rsp+78h+dwMimeFlags], 0; dwMimeFlags
0x18007a366  mov     [rsp+78h+pwzMimeProposed], 0; pwzMimeProposed
0x18007a36f  call    cs:__imp_FindMimeFromData
0x18007a375  test    eax, eax
0x18007a377  js      loc_18007A422
0x18007a37d  mov     rcx, [rbp+var_38]; psz1
0x18007a381  lea     rdx, aMessageRfc822; "message/rfc822"
0x18007a388  call    cs:__imp_StrCmpW
0x18007a38e  mov     rcx, [rbp+var_38]; pv
0x18007a392  mov     ebx, eax
0x18007a394  call    cs:__imp_CoTaskMemFree
0x18007a39a  test    ebx, ebx
0x18007a39c  jnz     loc_18007A422
0x18007a3a2  lea     rax, [rbp+ppv]
0x18007a3a6  xor     edx, edx; pUnkOuter
0x18007a3a8  lea     r9, _GUID_fd853cd5_7f86_11d0_8252_00c04fd85ab4; riid
0x18007a3af  mov     [rsp+78h+pwzMimeProposed], rax; ppv
0x18007a3b4  lea     r8d, [rbx+1]; dwClsContext
0x18007a3b8  lea     rcx, CLSID_IMimeMessage; rclsid
0x18007a3bf  call    cs:__imp_CoCreateInstance
0x18007a3c5  mov     ebx, eax
0x18007a3c7  test    eax, eax
0x18007a3c9  js      short loc_18007A43F
0x18007a3cb  mov     rcx, [rbp+ppv]
0x18007a3cf  lea     r8, [rbp+var_30]
0x18007a3d3  lea     rdx, _GUID_79eac9c9_baf9_11ce_8c82_00aa004ba90b
0x18007a3da  mov     rax, [rcx]
0x18007a3dd  mov     rax, [rax]
0x18007a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3e5  mov     ebx, eax
0x18007a3e7  test    eax, eax
0x18007a3e9  js      short loc_18007A43F
0x18007a3eb  mov     edx, [rbp+arg_20]
0x18007a3ee  mov     r9, r14
0x18007a3f1  mov     rcx, [rbp+var_30]
0x18007a3f5  mov     r8, rdi
0x18007a3f8  mov     dword ptr [rsp+78h+pwzMimeProposed], edx
0x18007a3fc  mov     edx, r15d
0x18007a3ff  mov     rax, [rcx]
0x18007a402  mov     rax, [rax+28h]
0x18007a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a40b  mov     ebx, eax
0x18007a40d  test    eax, eax
0x18007a40f  js      short loc_18007A43F
0x18007a411  mov     rax, [rbp+ppv]
0x18007a415  mov     [rbp+var_18], rax
0x18007a419  mov     [rbp+var_20], 0
0x18007a420  jmp     short loc_18007A42D
0x18007a422  mov     [rbp+var_20], 1
0x18007a429  mov     [rbp+var_18], rdi
0x18007a42d  lea     rcx, [rsi-0C8h]; this
0x18007a434  lea     rdx, [rbp+var_20]; struct BODYINITDATA_tag *
0x18007a438  call    ?LoadFromData@CBody@@AEAAJPEAUBODYINITDATA_tag@@@Z; CBody::LoadFromData(BODYINITDATA_tag *)
0x18007a43d  mov     ebx, eax
0x18007a43f  lea     rcx, [rbp+ppv]
0x18007a443  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007a448  lea     rcx, [rbp+var_30]
0x18007a44c  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007a451  mov     rdx, [rbp+pwzUrl]
0x18007a455  test    rdx, rdx
0x18007a458  jz      short loc_18007A46D
0x18007a45a  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007a461  mov     rax, [rcx]
0x18007a464  mov     rax, [rax+28h]
0x18007a468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a46d  mov     eax, ebx
0x18007a46f  add     rsp, 78h
0x18007a473  pop     r15
0x18007a475  pop     r14
0x18007a477  pop     rdi
0x18007a478  pop     rsi
0x18007a479  pop     rbx
0x18007a47a  pop     rbp
0x18007a47b  retn
```
